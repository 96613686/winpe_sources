# EapMsChapv2EncryptPassword

- ea: `0x18000d930`
- end: `0x18000daf8`
- name: `EapMsChapv2EncryptPassword`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b9b4`

## callees

- `0x180003bd0`
- `0x18000d930`
- `0x18001e494`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000dac3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000dac3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000d9d3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000d9d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d98f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000daad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dab8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d98f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000daad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dad1`
- `CRYPT32!CryptProtectData` at `0x18000da25`
- `CRYPT32!CryptProtectData` at `0x18000da25`

## pseudocode

```c
DWORD __fastcall EapMsChapv2EncryptPassword(__int64 *a1, void *a2)
{
  __int64 v2; // rbp
  void *v3; // rdi
  DWORD v4; // esi
  _BYTE *v6; // r14
  __int64 v7; // r12
  int v9; // ebx
  __int64 v10; // r12
  DWORD LastError; // ebx
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-48h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-38h] BYREF
  void *v14; // [rsp+90h] [rbp+8h] BYREF

  v2 = *a1;
  v3 = 0;
  v14 = 0;
  v4 = 0;
  pDataOut = 0;
  v6 = (_BYTE *)(v2 + 269);
  pDataIn = 0;
  if ( *(_DWORD *)(v2 + 784) )
  {
    v7 = 257;
    do
    {
      *v6++ = 0;
      --v7;
    }
    while ( v7 );
    LocalFree(0);
    LocalFree(pDataOut.pbData);
    return 0;
  }
  else
  {
    v9 = 0;
    if ( *v6 )
    {
      v10 = 257;
      pDataIn.pbData = (BYTE *)(v2 + 269);
      pDataIn.cbData = 257;
      if ( !NtCurrentTeb()->IsImpersonating && a2 )
      {
        if ( !ImpersonateLoggedOnUser(a2) )
        {
          LastError = GetLastError();
          LocalFree(0);
          LocalFree(pDataOut.pbData);
          return LastError;
        }
        v9 = 1;
      }
      if ( CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
      {
        v4 = AllocateUserDataWithEncPwd(v2, &v14, &pDataOut);
        if ( v4 )
        {
          v3 = v14;
        }
        else
        {
          do
          {
            *v6++ = 0;
            --v10;
          }
          while ( v10 );
          LocalFree((HLOCAL)v2);
          *a1 = (__int64)v14;
        }
      }
      else
      {
        v4 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids, v4);
      }
    }
    LocalFree(v3);
    LocalFree(pDataOut.pbData);
    if ( v9 != 1 || RevertToSelf() || v4 )
      return v4;
    else
      return GetLastError();
  }
}

```

## disassembly

```asm
0x18000d930  mov     rax, rsp
0x18000d933  mov     [rax+18h], rbp
0x18000d937  push    rsi
0x18000d938  push    rdi
0x18000d939  push    r12
0x18000d93b  push    r14
0x18000d93d  push    r15
0x18000d93f  sub     rsp, 60h
0x18000d943  mov     rbp, [rcx]
0x18000d946  xor     edi, edi
0x18000d948  xorps   xmm0, xmm0
0x18000d94b  mov     [rax+8], rdi
0x18000d94f  xorps   xmm1, xmm1
0x18000d952  xor     esi, esi
0x18000d954  movups  xmmword ptr [rax-48h], xmm0
0x18000d958  mov     r15, rcx
0x18000d95b  lea     r14, [rbp+10Dh]
0x18000d962  movups  xmmword ptr [rax-38h], xmm1
0x18000d966  cmp     [rbp+310h], esi
0x18000d96c  jz      short loc_18000D99C
0x18000d96e  mov     r12d, 101h
0x18000d974  mov     [r14], sil
0x18000d977  lea     r14, [r14+1]
0x18000d97b  sub     r12, 1
0x18000d97f  jnz     short loc_18000D974
0x18000d981  mov     rcx, rdi; hMem
0x18000d984  call    cs:__imp_LocalFree
0x18000d98a  mov     rcx, [rsp+88h+var_48.pbData]; hMem
0x18000d98f  call    cs:__imp_LocalFree
0x18000d995  mov     eax, esi
0x18000d997  jmp     loc_18000DAE3
0x18000d99c  mov     [rsp+88h+arg_8], rbx
0x18000d9a4  xor     ebx, ebx
0x18000d9a6  cmp     [r14], bl
0x18000d9a9  jz      loc_18000DAAA
0x18000d9af  mov     r12d, 101h
0x18000d9b5  mov     [rsp+88h+pDataIn.pbData], r14
0x18000d9ba  mov     [rsp+88h+pDataIn.cbData], r12d
0x18000d9bf  mov     eax, gs:179Ch
0x18000d9c7  test    eax, eax
0x18000d9c9  jnz     short loc_18000DA05
0x18000d9cb  test    rdx, rdx
0x18000d9ce  jz      short loc_18000DA05
0x18000d9d0  mov     rcx, rdx; hToken
0x18000d9d3  call    cs:__imp_ImpersonateLoggedOnUser
0x18000d9d9  test    eax, eax
0x18000d9db  jnz     short loc_18000DA00
0x18000d9dd  call    cs:__imp_GetLastError
0x18000d9e3  mov     rcx, rdi; hMem
0x18000d9e6  mov     ebx, eax
0x18000d9e8  call    cs:__imp_LocalFree
0x18000d9ee  mov     rcx, [rsp+88h+var_48.pbData]; hMem
0x18000d9f3  call    cs:__imp_LocalFree
0x18000d9f9  mov     eax, ebx
0x18000d9fb  jmp     loc_18000DADB
0x18000da00  mov     ebx, 1
0x18000da05  lea     rax, [rsp+88h+var_48]
0x18000da0a  xor     r9d, r9d; pvReserved
0x18000da0d  mov     [rsp+88h+pDataOut], rax; pDataOut
0x18000da12  lea     rcx, [rsp+88h+pDataIn]; pDataIn
0x18000da17  mov     [rsp+88h+dwFlags], esi; dwFlags
0x18000da1b  xor     r8d, r8d; pOptionalEntropy
0x18000da1e  xor     edx, edx; szDataDescr
0x18000da20  mov     [rsp+88h+pPromptStruct], rsi; pPromptStruct
0x18000da25  call    cs:__imp_CryptProtectData
0x18000da2b  test    eax, eax
0x18000da2d  jnz     short loc_18000DA64
0x18000da2f  call    cs:__imp_GetLastError
0x18000da35  mov     esi, eax
0x18000da37  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da3e  lea     rax, WPP_GLOBAL_Control
0x18000da45  cmp     rcx, rax
0x18000da48  jz      short loc_18000DAAA
0x18000da4a  mov     rcx, [rcx+10h]
0x18000da4e  lea     r8, WPP_9a88a148f8143f60aba93b564c187a5e_Traceguids
0x18000da55  mov     edx, 0Eh
0x18000da5a  mov     r9d, esi
0x18000da5d  call    WPP_SF_d
0x18000da62  jmp     short loc_18000DAAA
0x18000da64  lea     r8, [rsp+88h+var_48]
0x18000da69  mov     rcx, rbp
0x18000da6c  lea     rdx, [rsp+88h+arg_0]
0x18000da74  call    AllocateUserDataWithEncPwd
0x18000da79  mov     esi, eax
0x18000da7b  test    eax, eax
0x18000da7d  jnz     short loc_18000DAA2
0x18000da7f  mov     [r14], dil
0x18000da82  lea     r14, [r14+1]
0x18000da86  sub     r12, 1
0x18000da8a  jnz     short loc_18000DA7F
0x18000da8c  mov     rcx, rbp; hMem
0x18000da8f  call    cs:__imp_LocalFree
0x18000da95  mov     rax, [rsp+88h+arg_0]
0x18000da9d  mov     [r15], rax
0x18000daa0  jmp     short loc_18000DAAA
0x18000daa2  mov     rdi, [rsp+88h+arg_0]
0x18000daaa  mov     rcx, rdi; hMem
0x18000daad  call    cs:__imp_LocalFree
0x18000dab3  mov     rcx, [rsp+88h+var_48.pbData]; hMem
0x18000dab8  call    cs:__imp_LocalFree
0x18000dabe  cmp     ebx, 1
0x18000dac1  jnz     short loc_18000DAD9
0x18000dac3  call    cs:__imp_RevertToSelf
0x18000dac9  test    eax, eax
0x18000dacb  jnz     short loc_18000DAD9
0x18000dacd  test    esi, esi
0x18000dacf  jnz     short loc_18000DAD9
0x18000dad1  call    cs:__imp_GetLastError
0x18000dad7  jmp     short loc_18000DADB
0x18000dad9  mov     eax, esi
0x18000dadb  mov     rbx, [rsp+88h+arg_8]
0x18000dae3  mov     rbp, [rsp+88h+arg_10]
0x18000daeb  add     rsp, 60h
0x18000daef  pop     r15
0x18000daf1  pop     r14
0x18000daf3  pop     r12
0x18000daf5  pop     rdi
0x18000daf6  pop     rsi
0x18000daf7  retn
```
