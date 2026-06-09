# myFindDomainSidInCache(ushort const *,void * *)

- ea: `0x18002a1a4`
- end: `0x18002a285`
- name: `?myFindDomainSidInCache@@YAKPEBGPEAPEAX@Z`
- size: `225`
- prototype: `__int64 __fastcall(wchar_t *String1, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a290`

## callees

- `0x18002a1a4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a1e5`
- `msvcrt!_wcsicmp` at `0x18002a203`
- `msvcrt!_wcsicmp` at `0x18002a1e5`
- `msvcrt!_wcsicmp` at `0x18002a203`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a227`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a227`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a267`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a270`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a21d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a24c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a21d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a24c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002a25a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002a25a`

## pseudocode

```c
__int64 __fastcall myFindDomainSidInCache(wchar_t *String1, void **a2)
{
  unsigned int v2; // esi
  unsigned int i; // ebx
  __int64 v6; // rdi
  const wchar_t *v7; // rdx
  const wchar_t *v8; // rdx
  DWORD LengthSid; // eax
  HLOCAL v10; // rax
  void *v11; // rbp
  void *v12; // rbx
  DWORD v13; // eax

  v2 = 0;
  for ( i = 0; i < g_cDomainCache; ++i )
  {
    v6 = 56LL * i;
    if ( *(_QWORD *)((char *)g_pDomainCache + v6 + 32) )
    {
      if ( (v7 = *(const wchar_t **)((char *)g_pDomainCache + v6)) != 0 && !_wcsicmp(String1, v7)
        || (v8 = *(const wchar_t **)((char *)g_pDomainCache + v6 + 8)) != 0 && !_wcsicmp(String1, v8) )
      {
        LengthSid = GetLengthSid(*(PSID *)((char *)g_pDomainCache + v6 + 32));
        v10 = LocalAlloc(0, LengthSid);
        *a2 = v10;
        v11 = v10;
        if ( v10 )
        {
          v12 = *(void **)((char *)g_pDomainCache + v6 + 32);
          v13 = GetLengthSid(v12);
          if ( !CopySid(v13, v11, v12) )
          {
            LocalFree(*a2);
            *a2 = 0;
            return GetLastError();
          }
        }
        else
        {
          return 14;
        }
        return v2;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002a1a4  push    rbx
0x18002a1a6  push    rbp
0x18002a1a7  push    rsi
0x18002a1a8  push    rdi
0x18002a1a9  push    r14
0x18002a1ab  sub     rsp, 20h
0x18002a1af  xor     esi, esi
0x18002a1b1  mov     r14, rdx
0x18002a1b4  xor     ebx, ebx
0x18002a1b6  mov     rbp, rcx
0x18002a1b9  cmp     ebx, cs:?g_cDomainCache@@3KA; ulong g_cDomainCache
0x18002a1bf  jnb     loc_18002A278
0x18002a1c5  mov     eax, ebx
0x18002a1c7  imul    rdi, rax, 38h ; '8'
0x18002a1cb  mov     rax, cs:?g_pDomainCache@@3PEAU_DS_DOMAIN_TRUSTSW@@EA; _DS_DOMAIN_TRUSTSW * g_pDomainCache
0x18002a1d2  cmp     [rdi+rax+20h], rsi
0x18002a1d7  jz      short loc_18002A20D
0x18002a1d9  mov     rdx, [rdi+rax]; String2
0x18002a1dd  test    rdx, rdx
0x18002a1e0  jz      short loc_18002A1EF
0x18002a1e2  mov     rcx, rbp; String1
0x18002a1e5  call    cs:__imp__wcsicmp
0x18002a1eb  test    eax, eax
0x18002a1ed  jz      short loc_18002A211
0x18002a1ef  mov     rax, cs:?g_pDomainCache@@3PEAU_DS_DOMAIN_TRUSTSW@@EA; _DS_DOMAIN_TRUSTSW * g_pDomainCache
0x18002a1f6  mov     rdx, [rdi+rax+8]; String2
0x18002a1fb  test    rdx, rdx
0x18002a1fe  jz      short loc_18002A20D
0x18002a200  mov     rcx, rbp; String1
0x18002a203  call    cs:__imp__wcsicmp
0x18002a209  test    eax, eax
0x18002a20b  jz      short loc_18002A211
0x18002a20d  inc     ebx
0x18002a20f  jmp     short loc_18002A1B9
0x18002a211  mov     rcx, cs:?g_pDomainCache@@3PEAU_DS_DOMAIN_TRUSTSW@@EA; _DS_DOMAIN_TRUSTSW * g_pDomainCache
0x18002a218  mov     rcx, [rdi+rcx+20h]; pSid
0x18002a21d  call    cs:__imp_GetLengthSid
0x18002a223  mov     edx, eax; uBytes
0x18002a225  xor     ecx, ecx; uFlags
0x18002a227  call    cs:__imp_LocalAlloc
0x18002a22d  mov     [r14], rax
0x18002a230  mov     rbp, rax
0x18002a233  test    rax, rax
0x18002a236  jnz     short loc_18002A23D
0x18002a238  lea     esi, [rax+0Eh]
0x18002a23b  jmp     short loc_18002A278
0x18002a23d  mov     rax, cs:?g_pDomainCache@@3PEAU_DS_DOMAIN_TRUSTSW@@EA; _DS_DOMAIN_TRUSTSW * g_pDomainCache
0x18002a244  mov     rbx, [rdi+rax+20h]
0x18002a249  mov     rcx, rbx; pSid
0x18002a24c  call    cs:__imp_GetLengthSid
0x18002a252  mov     r8, rbx; pSourceSid
0x18002a255  mov     rdx, rbp; pDestinationSid
0x18002a258  mov     ecx, eax; nDestinationSidLength
0x18002a25a  call    cs:__imp_CopySid
0x18002a260  test    eax, eax
0x18002a262  jnz     short loc_18002A278
0x18002a264  mov     rcx, [r14]; hMem
0x18002a267  call    cs:__imp_LocalFree
0x18002a26d  mov     [r14], rsi
0x18002a270  call    cs:__imp_GetLastError
0x18002a276  mov     esi, eax
0x18002a278  mov     eax, esi
0x18002a27a  add     rsp, 20h
0x18002a27e  pop     r14
0x18002a280  pop     rdi
0x18002a281  pop     rsi
0x18002a282  pop     rbp
0x18002a283  pop     rbx
0x18002a284  retn
```
