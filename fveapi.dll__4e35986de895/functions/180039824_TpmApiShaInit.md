# TpmApiShaInit

- ea: `0x180039824`
- end: `0x18003998a`
- name: `TpmApiShaInit`
- size: `358`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `11`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bb28`
- `0x180039640`
- `0x18003f3e4`
- `0x1800572e0`
- `0x18008a8b8`
- `0x18008ac18`
- `0x1800dcb94`
- `0x1800dd7a4`
- `0x1800dd90c`
- `0x1800ddadc`
- `0x1800fee84`

## callees

- `0x180039824`
- `0x180039990`
- `0x1800db840`
- `0x180129010`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003987c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180039949`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003987c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180039949`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003996e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003996e`
- `bcrypt!BCryptCreateHash` at `0x1800398f0`
- `bcrypt!BCryptCreateHash` at `0x1800398f0`

## pseudocode

```c
__int64 __fastcall TpmApiShaInit(LPCWSTR pszAlgId, BCRYPT_HASH_HANDLE *phHash, volatile signed __int64 *a3)
{
  int v6; // ebx
  NTSTATUS v7; // esi
  NTSTATUS Hash; // eax
  BCRYPT_ALG_HANDLE phAlgorithm[2]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+10h] BYREF
  LPCWSTR pszImplementation; // [rsp+88h] [rbp+20h] BYREF

  if ( !phHash )
    return (unsigned int)-2144796412;
  v6 = 0;
  phAlgorithm[0] = 0;
  if ( *a3 )
  {
LABEL_8:
    if ( v6 < 0 )
      return (unsigned int)v6;
    goto LABEL_9;
  }
  pszImplementation = 0;
  v11 = 0;
  TpmApiRegistryGetAlgorithmProvider((unsigned __int16 **)&pszImplementation, &v11);
  v7 = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, pszImplementation, 0);
  if ( v7 < 0 && pszImplementation && TpmApiDefaultToExistingProviders() )
    v7 = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, 0, 0);
  if ( qword_1801746C8 )
    qword_1801746C8(0, pszImplementation);
  if ( v7 < 0 )
  {
    v6 = v7 | 0x10000000;
    goto LABEL_8;
  }
  if ( !_InterlockedCompareExchange64(a3, (signed __int64)phAlgorithm[0], 0) )
    goto LABEL_8;
  BCryptCloseAlgorithmProvider(phAlgorithm[0], 0);
LABEL_9:
  Hash = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)a3, phHash, 0, 0, 0, 0, 0);
  if ( Hash < 0 )
    return (unsigned int)(Hash | 0x10000000);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180039824  mov     rax, rsp
0x180039827  mov     [rax+8], rbx
0x18003982b  mov     [rax+18h], rsi
0x18003982f  push    rdi
0x180039830  push    r14
0x180039832  push    r15
0x180039834  sub     rsp, 50h
0x180039838  mov     rdi, r8
0x18003983b  mov     r15, rdx
0x18003983e  mov     r14, rcx
0x180039841  test    rdx, rdx
0x180039844  jz      loc_180039919
0x18003984a  xor     ebx, ebx
0x18003984c  mov     [rax-28h], rbx
0x180039850  cmp     [r8], rbx
0x180039853  jnz     short loc_1800398C7
0x180039855  lea     rdx, [rax+10h]; unsigned int *
0x180039859  mov     [rax+20h], rbx
0x18003985d  lea     rcx, [rax+20h]; unsigned __int16 **
0x180039861  mov     [rax+10h], ebx
0x180039864  call    ?TpmApiRegistryGetAlgorithmProvider@@YAJPEAPEAGPEAK@Z; TpmApiRegistryGetAlgorithmProvider(ushort * *,ulong *)
0x180039869  mov     r8, [rsp+68h+pszImplementation]; pszImplementation
0x180039871  lea     rcx, [rsp+68h+phAlgorithm]; phAlgorithm
0x180039876  xor     r9d, r9d; dwFlags
0x180039879  mov     rdx, r14; pszAlgId
0x18003987c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180039883  nop     dword ptr [rax+rax+00h]
0x180039888  mov     esi, eax
0x18003988a  test    eax, eax
0x18003988c  js      loc_180039920
0x180039892  mov     rax, cs:qword_1801746C8
0x180039899  test    rax, rax
0x18003989c  jz      short loc_1800398AD
0x18003989e  mov     rdx, [rsp+68h+pszImplementation]
0x1800398a6  xor     ecx, ecx
0x1800398a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398ad  test    esi, esi
0x1800398af  js      loc_18003995C
0x1800398b5  mov     rcx, [rsp+68h+phAlgorithm]
0x1800398ba  xor     eax, eax
0x1800398bc  lock cmpxchg [rdi], rcx
0x1800398c1  jnz     loc_180039967
0x1800398c7  test    ebx, ebx
0x1800398c9  js      short loc_180039900
0x1800398cb  mov     rcx, [rdi]; hAlgorithm
0x1800398ce  xor     r9d, r9d; cbHashObject
0x1800398d1  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800398d9  xor     r8d, r8d; pbHashObject
0x1800398dc  mov     [rsp+68h+cbSecret], 0; cbSecret
0x1800398e4  mov     rdx, r15; phHash
0x1800398e7  mov     [rsp+68h+pbSecret], 0; pbSecret
0x1800398f0  call    cs:__imp_BCryptCreateHash
0x1800398f7  nop     dword ptr [rax+rax+00h]
0x1800398fc  test    eax, eax
0x1800398fe  js      short loc_18003997F
0x180039900  lea     r11, [rsp+68h+var_18]
0x180039905  mov     eax, ebx
0x180039907  mov     rbx, [r11+20h]
0x18003990b  mov     rsi, [r11+30h]
0x18003990f  mov     rsp, r11
0x180039912  pop     r15
0x180039914  pop     r14
0x180039916  pop     rdi
0x180039917  retn
0x180039919  mov     ebx, 80290104h
0x18003991e  jmp     short loc_180039900
0x180039920  cmp     [rsp+68h+pszImplementation], rbx
0x180039928  jz      loc_180039892
0x18003992e  call    ?TpmApiDefaultToExistingProviders@@YAEXZ; TpmApiDefaultToExistingProviders(void)
0x180039933  test    al, al
0x180039935  jz      loc_180039892
0x18003993b  xor     r9d, r9d; dwFlags
0x18003993e  lea     rcx, [rsp+68h+phAlgorithm]; phAlgorithm
0x180039943  xor     r8d, r8d; pszImplementation
0x180039946  mov     rdx, r14; pszAlgId
0x180039949  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180039950  nop     dword ptr [rax+rax+00h]
0x180039955  mov     esi, eax
0x180039957  jmp     loc_180039892
0x18003995c  mov     ebx, esi
0x18003995e  bts     ebx, 1Ch
0x180039962  jmp     loc_1800398C7
0x180039967  mov     rcx, [rsp+68h+phAlgorithm]; hAlgorithm
0x18003996c  xor     edx, edx; dwFlags
0x18003996e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180039975  nop     dword ptr [rax+rax+00h]
0x18003997a  jmp     loc_1800398CB
0x18003997f  mov     ebx, eax
0x180039981  bts     ebx, 1Ch
0x180039985  jmp     loc_180039900
```
