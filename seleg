#pragma once 
/** 
 * [id5159073|@brief] Solana Public key 
 */ 
 
#include <sol/types.h> 
 
#ifdef __cplusplus 
extern "C" { 
#endif 
 
/** 
 * Size of Public key in bytes 
 */ 
#define SIZE_PUBKEY 32 
 
/** 
 * Public key 
 */ 
typedef struct { 
 uint8_t x[SIZE_PUBKEY]; 
} SolPubkey; 
 
/** 
 * Prints the hexadecimal representation of a public key 
 * 
 * [id153965260|@param] key The public key to print 
 */ 
void sol_log_pubkey( 
 const SolPubkey [club83220288|*pubkey] 
); 
 
/** 
 * Compares two public keys 
 * 
 * [id153965260|@param] one First public key 
 * [id153965260|@param] two Second public key 
 * [id623884962|@return] true if the same 
 */ 
static bool SolPubkey_same(const SolPubkey [id203992|*one], const SolPubkey *two) { 
 for (int i = 0; i < sizeof([id203992|*one]); i++) { 
 if (one->x[i] != two->x[i]) { 
 return false; 
 } 
 } 
 return true; 
} 
 
/** 
 * Seed used to create a program address or passed to sol_invoke_signed 
 */ 
typedef struct { 
 const uint8_t *addr; /** Seed bytes */ 
 uint64_t len; /** Length of the seed bytes */ 
} SolSignerSeed; 
 
/** 
 * Seeds used by a signer to create a program address or passed to 
 * sol_invoke_signed 
 */ 
typedef struct { 
 const SolSignerSeed *addr; /** An arry of a signer's seeds */ 
 uint64_t len; /** Number of seeds */ 
} SolSignerSeeds; 
 
/** 
 * Create a program address 
 * 
 * [id153965260|@param] seeds Seed bytes used to sign program accounts 
 * [id153965260|@param] seeds_len Length of the seeds array 
 * [id153965260|@param] program_id Program id of the signer 
 * [id153965260|@param] program_address Program address created, filled on return 
 */ 
uint64_t sol_create_program_address( 
 const SolSignerSeed [id25826207|*seeds], 
 int seeds_len, 
 const SolPubkey *program_id, 
 SolPubkey *program_address 
); 
 
/** 
 * Try to find a program address and return corresponding bump seed 
 * 
 * [id153965260|@param] seeds Seed bytes used to sign program accounts 
 * [id153965260|@param] seeds_len Length of the seeds array 
 * [id153965260|@param] program_id Program id of the signer 
 * [id153965260|@param] program_address Program address created, filled on return 
 * [id153965260|@param] bump_seed Bump seed required to create a valid program address 
 */ 
uint64_t sol_try_find_program_address( 
 const SolSignerSeed [id25826207|*seeds], 
 int seeds_len, 
 const SolPubkey *program_id, 
 SolPubkey *program_address, 
 uint8_t *bump_seed 
); 
 
#ifdef SOL_TEST 
/** 
 * Stub functions when building tests 
 */ 
#include <stdio.h> 
 
void sol_log_pubkey( 
 const SolPubkey [club83220288|*pubkey] 
) { 
 printf("Program log: "); 
 for (int i = 0; i < SIZE_PUBKEY; i++) { 
 printf("%02 ", pubkey->x[i]); 
 } 
 printf("\n"); 
} 
 
#endif 
 
#ifdef __cplusplus 
} 
#endif 
 
/**@}*/
