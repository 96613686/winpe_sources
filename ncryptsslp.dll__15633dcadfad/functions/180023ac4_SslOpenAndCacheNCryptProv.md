# SslOpenAndCacheNCryptProv

- ea: `0x180023ac4`
- end: `0x180023bfd`
- name: `SslOpenAndCacheNCryptProv`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011110`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x18000b654`
- `0x1800115b0`
- `0x180023ac4`
- `0x180024fb0`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180023b57`
- `ncrypt!NCryptOpenStorageProvider` at `0x180023b57`
- `ncrypt!NCryptFreeObject` at `0x180023bdc`
- `ncrypt!NCryptFreeObject` at `0x180023bdc`
- `ntdll!RtlReleaseResource` at `0x180023bc1`
- `ntdll!RtlReleaseResource` at `0x180023bc1`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023b86`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023b86`

## string_xrefs

- `0x180023b11`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsncryptprovider.c`
- `0x180023b69`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsncryptprovider.c`

## pseudocode

```c
__int64 __fastcall SslOpenAndCacheNCryptProv(__int64 a1, _WORD *a2, __int64 *a3)
{
  __int64 v3; // rax
  unsigned int v7; // r14d
  __int64 v8; // rax
  _QWORD *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rbx
  __int64 *v12; // r15
  SECURITY_STATUS v13; // eax
  __int64 v14; // rbx
  _QWORD *v15; // rax
  NCRYPT_HANDLE v16; // rcx

  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  v7 = 2 * v3 + 2;
  v8 = SafeAllocaAllocateFromHeap((unsigned int)(2 * v3 + 26));
  v9 = (_QWORD *)v8;
  if ( !v8 )
  {
    v10 = -1073741801;
    DebugTraceError(
      3221225495LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
      120);
    return v10;
  }
  v11 = v8 + 24;
  memmove((void *)(v8 + 24), a2, v7);
  v12 = v9 + 2;
  v9[1] = v11;
  v9[2] = 0;
  *v9 = 0;
  v13 = NCryptOpenStorageProvider(v9 + 2, a2, 0);
  v10 = v13;
  if ( v13 < 0 )
  {
    DebugTraceError(
      (unsigned int)v13,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
      137);
LABEL_13:
    v16 = v9[2];
    if ( v16 )
      NCryptFreeObject(v16);
    MSCryptFree(v9);
    return v10;
  }
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(a1 + 24), 1u);
  v14 = SslLookupCachedNCryptProv(a1, a2);
  if ( !v14 )
  {
    v15 = *(_QWORD **)(a1 + 8);
    if ( v15 )
      *v15 = v9;
    else
      *(_QWORD *)a1 = v9;
    *(_QWORD *)(a1 + 8) = v9;
    v9 = 0;
    v14 = *v12;
    ++*(_DWORD *)(a1 + 16);
  }
  RtlReleaseResource((PRTL_RESOURCE)(a1 + 24));
  *a3 = v14;
  v10 = 0;
  if ( v9 )
    goto LABEL_13;
  return v10;
}

```

## disassembly

```asm
0x180023ac4  push    rbx
0x180023ac6  push    rbp
0x180023ac7  push    rsi
0x180023ac8  push    rdi
0x180023ac9  push    r12
0x180023acb  push    r13
0x180023acd  push    r14
0x180023acf  push    r15
0x180023ad1  sub     rsp, 28h
0x180023ad5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023ad9  mov     r12, r8
0x180023adc  xor     r13d, r13d
0x180023adf  mov     rbp, rdx
0x180023ae2  mov     rsi, rcx
0x180023ae5  inc     rax
0x180023ae8  cmp     [rdx+rax*2], r13w
0x180023aed  jnz     short loc_180023AE5
0x180023aef  lea     r14d, ds:2[rax*2]
0x180023af7  lea     ecx, [r14+18h]
0x180023afb  call    SafeAllocaAllocateFromHeap
0x180023b00  mov     rdi, rax
0x180023b03  test    rax, rax
0x180023b06  jnz     short loc_180023B2E
0x180023b08  lea     r9d, [rax+78h]
0x180023b0c  mov     ecx, 0C0000017h
0x180023b11  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023b18  mov     ebx, 0C0000017h
0x180023b1d  lea     rdx, aStatus; "Status"
0x180023b24  call    DebugTraceError
0x180023b29  jmp     loc_180023BEA
0x180023b2e  lea     rbx, [rax+18h]
0x180023b32  mov     r8d, r14d; Size
0x180023b35  mov     rcx, rbx; void *
0x180023b38  mov     rdx, rbp; Src
0x180023b3b  call    memmove
0x180023b40  lea     r15, [rdi+10h]
0x180023b44  mov     [rdi+8], rbx
0x180023b48  mov     rcx, r15; phProvider
0x180023b4b  mov     [r15], r13
0x180023b4e  xor     r8d, r8d; dwFlags
0x180023b51  mov     [rdi], r13
0x180023b54  mov     rdx, rbp; pszProviderName
0x180023b57  call    cs:__imp_NCryptOpenStorageProvider
0x180023b5d  mov     ebx, eax
0x180023b5f  test    eax, eax
0x180023b61  jns     short loc_180023B80
0x180023b63  mov     r9d, 89h
0x180023b69  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023b70  lea     rdx, aStatus; "Status"
0x180023b77  mov     ecx, eax
0x180023b79  call    DebugTraceError
0x180023b7e  jmp     short loc_180023BD3
0x180023b80  mov     dl, 1; Wait
0x180023b82  lea     rcx, [rsi+18h]; Resource
0x180023b86  call    cs:__imp_RtlAcquireResourceExclusive
0x180023b8c  mov     rdx, rbp
0x180023b8f  mov     rcx, rsi
0x180023b92  call    SslLookupCachedNCryptProv
0x180023b97  mov     rbx, rax
0x180023b9a  test    rax, rax
0x180023b9d  jnz     short loc_180023BBD
0x180023b9f  mov     rax, [rsi+8]
0x180023ba3  test    rax, rax
0x180023ba6  jnz     short loc_180023BAD
0x180023ba8  mov     [rsi], rdi
0x180023bab  jmp     short loc_180023BB0
0x180023bad  mov     [rax], rdi
0x180023bb0  mov     [rsi+8], rdi
0x180023bb4  mov     rdi, r13
0x180023bb7  mov     rbx, [r15]
0x180023bba  inc     dword ptr [rsi+10h]
0x180023bbd  lea     rcx, [rsi+18h]; Resource
0x180023bc1  call    cs:__imp_RtlReleaseResource
0x180023bc7  mov     [r12], rbx
0x180023bcb  mov     ebx, r13d
0x180023bce  test    rdi, rdi
0x180023bd1  jz      short loc_180023BEA
0x180023bd3  mov     rcx, [rdi+10h]; hObject
0x180023bd7  test    rcx, rcx
0x180023bda  jz      short loc_180023BE2
0x180023bdc  call    cs:__imp_NCryptFreeObject
0x180023be2  mov     rcx, rdi
0x180023be5  call    MSCryptFree
0x180023bea  mov     eax, ebx
0x180023bec  add     rsp, 28h
0x180023bf0  pop     r15
0x180023bf2  pop     r14
0x180023bf4  pop     r13
0x180023bf6  pop     r12
0x180023bf8  pop     rdi
0x180023bf9  pop     rsi
0x180023bfa  pop     rbp
0x180023bfb  pop     rbx
0x180023bfc  retn
```
