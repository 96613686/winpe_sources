# CTVOCache::FindCacheEntry(uchar * const,char const *,void *)

- ea: `0x180017000`
- end: `0x1800170a2`
- name: `?FindCacheEntry@CTVOCache@@QEAAPEAU_TVO_CACHE_ENTRY@@QEAEPEBDPEAX@Z`
- size: `162`
- prototype: `struct _TVO_CACHE_ENTRY *__fastcall(CTVOCache *this, unsigned __int8 *const, const char *, const CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e410`

## callees

- `0x180017000`

## import_xrefs

- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x18001709a`
- `CRYPT32!I_CryptEnumMatchingLruEntries` at `0x18001709a`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18001708c`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18001708c`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180017058`
- `CRYPT32!I_CryptGetLruEntryData` at `0x180017058`
- `CRYPT32!I_CryptFindLruEntry` at `0x18001702b`
- `CRYPT32!I_CryptFindLruEntry` at `0x18001702b`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x18001707f`
- `CRYPT32!CertIsValidCRLForCertificate` at `0x18001707f`

## pseudocode

```c
struct _TVO_CACHE_ENTRY *__fastcall CTVOCache::FindCacheEntry(
        CTVOCache *this,
        unsigned __int8 *const a2,
        const char *a3,
        const CERT_CONTEXT *a4)
{
  __int64 v4; // rcx
  __int64 i; // rax
  __int64 v8; // rbx
  struct _TVO_CACHE_ENTRY *result; // rax
  __int64 LruEntryData; // rax
  __int64 v11; // rdi
  _QWORD v12[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = *(_QWORD *)this;
  v12[1] = a2;
  v12[0] = 32;
  for ( i = I_CryptFindLruEntry(v4, v12); ; i = I_CryptEnumMatchingLruEntries(v8) )
  {
    v8 = i;
    result = 0;
    if ( !v8 )
      break;
    LruEntryData = I_CryptGetLruEntryData(v8);
    v11 = LruEntryData;
    if ( a3 == *(const char **)(LruEntryData + 32)
      && (a3 != (const char *)2 || !a4 || CertIsValidCRLForCertificate(a4, *(PCCRL_CONTEXT *)(LruEntryData + 40), 0, 0)) )
    {
      I_CryptReleaseLruEntry(v8);
      return (struct _TVO_CACHE_ENTRY *)v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180017000  mov     [rsp+arg_8], rbx
0x180017005  mov     [rsp+arg_10], rbp
0x18001700a  push    rsi
0x18001700b  sub     rsp, 30h
0x18001700f  mov     rcx, [rcx]
0x180017012  mov     rbp, r9
0x180017015  mov     [rsp+38h+var_10], rdx
0x18001701a  mov     rsi, r8
0x18001701d  lea     rdx, [rsp+38h+var_18]
0x180017022  mov     [rsp+38h+var_18], 20h ; ' '
0x18001702b  call    cs:__imp_I_CryptFindLruEntry
0x180017031  mov     [rsp+38h+arg_0], rdi
0x180017036  mov     rbx, rax
0x180017039  xor     eax, eax
0x18001703b  test    rbx, rbx
0x18001703e  jnz     short loc_180017055
0x180017040  mov     rdi, [rsp+38h+arg_0]
0x180017045  mov     rbx, [rsp+38h+arg_8]
0x18001704a  mov     rbp, [rsp+38h+arg_10]
0x18001704f  add     rsp, 30h
0x180017053  pop     rsi
0x180017054  retn
0x180017055  mov     rcx, rbx
0x180017058  call    cs:__imp_I_CryptGetLruEntryData
0x18001705e  mov     rdi, rax
0x180017061  cmp     rsi, [rax+20h]
0x180017065  jnz     short loc_180017097
0x180017067  cmp     rsi, 2
0x18001706b  jnz     short loc_180017089
0x18001706d  test    rbp, rbp
0x180017070  jz      short loc_180017089
0x180017072  mov     rdx, [rax+28h]; pCrl
0x180017076  xor     r9d, r9d; pvReserved
0x180017079  xor     r8d, r8d; dwFlags
0x18001707c  mov     rcx, rbp; pCert
0x18001707f  call    cs:__imp_CertIsValidCRLForCertificate
0x180017085  test    eax, eax
0x180017087  jz      short loc_180017097
0x180017089  mov     rcx, rbx
0x18001708c  call    cs:__imp_I_CryptReleaseLruEntry
0x180017092  mov     rax, rdi
0x180017095  jmp     short loc_180017040
0x180017097  mov     rcx, rbx
0x18001709a  call    cs:__imp_I_CryptEnumMatchingLruEntries
0x1800170a0  jmp     short loc_180017036
```
