# NlGetTrustedDomainNames(_DOMAIN_INFO *,ushort *,ushort * *,ushort * *)

- ea: `0x18000b06c`
- end: `0x18000b355`
- name: `?NlGetTrustedDomainNames@@YAKPEAU_DOMAIN_INFO@@PEAGPEAPEAG2@Z`
- size: `745`
- prototype: `unsigned int(struct _DOMAIN_INFO *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ea0`

## callees

- `0x180003250`
- `0x180003320`
- `0x1800037f0`
- `0x18000b06c`
- `0x180088fe8`
- `0x1800892fc`
- `0x180089414`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b0c5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b105`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b0c5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b105`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b2e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b325`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b2e1`
- `ntdll!RtlLeaveCriticalSection` at `0x18000b325`
- `ntdll!RtlEnterCriticalSection` at `0x18000b13a`
- `ntdll!RtlEnterCriticalSection` at `0x18000b22e`
- `ntdll!RtlEnterCriticalSection` at `0x18000b13a`
- `ntdll!RtlEnterCriticalSection` at `0x18000b22e`
- `netutils!NetApiBufferFree` at `0x18000b2f5`
- `netutils!NetApiBufferFree` at `0x18000b30d`
- `netutils!NetApiBufferFree` at `0x18000b2f5`
- `netutils!NetApiBufferFree` at `0x18000b30d`
- `netutils!NetpwNameCompare` at `0x18000b175`
- `netutils!NetpwNameCompare` at `0x18000b268`
- `netutils!NetpwNameCompare` at `0x18000b175`
- `netutils!NetpwNameCompare` at `0x18000b268`

## pseudocode

```c
__int64 __fastcall NlGetTrustedDomainNames(
        struct _RTL_CRITICAL_SECTION *a1,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        LPVOID *a4)
{
  unsigned int v4; // r14d
  bool v6; // zf
  int v10; // eax
  int cbMultiByte; // ebx
  CHAR *lpMultiByteStr; // rax
  const char *v13; // rdi
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int i; // ebp
  char *v17; // rcx
  const char *v18; // rcx
  struct TRUSTED_DOMAIN *v19; // rax
  char *v20; // rcx
  unsigned __int16 *v21; // rax
  struct _RTL_CRITICAL_SECTION *v22; // rcx
  const CHAR *v23; // rcx
  unsigned __int16 *v24; // rax
  struct _RTL_CRITICAL_SECTION *v25; // rcx
  struct _RTL_CRITICAL_SECTION *v26; // rbp
  __int64 v27; // r15
  __int64 v28; // rcx
  const unsigned __int16 *v29; // rcx
  void *v30; // rcx
  unsigned __int16 *v31; // rax
  void *v32; // rcx
  unsigned __int16 *v33; // rax
  unsigned __int16 *v35; // [rsp+A0h] [rbp+18h] BYREF

  v4 = 0;
  v6 = NlGlobalMemberWorkstation == 0;
  *a3 = 0;
  *a4 = 0;
  if ( v6 )
  {
    v26 = a1 + 10;
    v13 = 0;
    RtlEnterCriticalSection(a1 + 10);
    while ( 1 )
    {
      if ( v4 >= HIDWORD(a1[12].DebugInfo) )
        goto LABEL_40;
      v27 = 56LL * v4;
      v28 = *(_QWORD *)(v27 + a1[11].SpinCount);
      if ( v28 )
      {
        if ( !(unsigned int)NetpwNameCompare(v28, a2, 6) )
          break;
      }
      v29 = *(const unsigned __int16 **)(v27 + a1[11].SpinCount + 8);
      if ( v29 )
      {
        if ( (unsigned int)NlEqualDnsName(v29, a2) )
          break;
      }
      ++v4;
    }
    v30 = *(void **)(v27 + a1[11].SpinCount);
    if ( !v30 || (v31 = (unsigned __int16 *)NetpAllocWStrFromWStr(v30), (*a4 = v31) != 0) )
    {
      v32 = *(void **)(v27 + a1[11].SpinCount + 8);
      if ( !v32 || (v33 = (unsigned __int16 *)NetpAllocWStrFromWStr(v32), (*a3 = v33) != 0) )
      {
LABEL_40:
        v25 = v26;
        goto LABEL_41;
      }
    }
    v22 = v26;
LABEL_35:
    v15 = 8;
    RtlLeaveCriticalSection(v22);
    goto LABEL_36;
  }
  v10 = WideCharToMultiByte(0xFDE9u, 0, a2, -1, 0, 0, 0, 0);
  cbMultiByte = v10;
  if ( !v10 || (lpMultiByteStr = (CHAR *)NetpMemoryAllocate((unsigned int)(v10 + 1)), (v13 = lpMultiByteStr) == 0) )
  {
LABEL_6:
    v13 = 0;
    v15 = 8;
LABEL_36:
    if ( *a3 )
    {
      NetApiBufferFree(*a3);
      *a3 = 0;
    }
    if ( *a4 )
    {
      NetApiBufferFree(*a4);
      *a4 = 0;
    }
    goto LABEL_42;
  }
  v14 = WideCharToMultiByte(0xFDE9u, 0, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( !v14 )
  {
    NetpMemoryFree(v13);
    goto LABEL_6;
  }
  v13[v14] = 0;
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  for ( i = 0; ; ++i )
  {
    if ( i >= NlGlobalTrustedDomainCount )
      goto LABEL_21;
    v17 = (char *)NlGlobalTrustedDomainList + 40 * i;
    if ( v17 )
    {
      if ( !(unsigned int)NetpwNameCompare(v17, a2, 6) )
        break;
    }
    v18 = (const char *)*((_QWORD *)NlGlobalTrustedDomainList + 5 * i + 4);
    if ( v18 )
    {
      if ( (unsigned int)NlEqualDnsNameUtf8(v18, v13) )
        break;
    }
  }
  v19 = NlGlobalTrustedDomainList;
  v20 = (char *)NlGlobalTrustedDomainList + 40 * i;
  if ( v20 )
  {
    v21 = (unsigned __int16 *)NetpAllocWStrFromWStr(v20);
    *a4 = v21;
    if ( !v21 )
      goto LABEL_16;
    v19 = NlGlobalTrustedDomainList;
  }
  v23 = (const CHAR *)*((_QWORD *)v19 + 5 * i + 4);
  if ( v23 )
  {
    v35 = 0;
    if ( NetpAllocWStrFromUtf8StrAsRequired(v23, 0xFFFFFFFF, 0, 0, &v35) )
    {
      *a3 = 0;
      goto LABEL_16;
    }
    v24 = v35;
    *a3 = v35;
    if ( !v24 )
    {
LABEL_16:
      v22 = &NlGlobalDcDiscoveryCritSect;
      goto LABEL_35;
    }
  }
LABEL_21:
  v25 = &NlGlobalDcDiscoveryCritSect;
LABEL_41:
  RtlLeaveCriticalSection(v25);
  v15 = 0;
LABEL_42:
  if ( v13 )
    NetpMemoryFree(v13);
  return v15;
}

```

## disassembly

```asm
0x18000b06c  mov     rax, rsp
0x18000b06f  push    rbx
0x18000b070  push    rbp
0x18000b071  push    rsi
0x18000b072  push    rdi
0x18000b073  push    r12
0x18000b075  push    r13
0x18000b077  push    r14
0x18000b079  push    r15
0x18000b07b  sub     rsp, 48h
0x18000b07f  xor     r14d, r14d
0x18000b082  mov     r12, r9
0x18000b085  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r14d; int NlGlobalMemberWorkstation
0x18000b08c  mov     rsi, r8
0x18000b08f  mov     r13, rdx
0x18000b092  mov     [r8], r14
0x18000b095  mov     rbx, rcx
0x18000b098  mov     [r9], r14
0x18000b09b  jz      loc_18000B221
0x18000b0a1  mov     [rax-50h], r14
0x18000b0a5  mov     r8, rdx; lpWideCharStr
0x18000b0a8  mov     [rax-58h], r14
0x18000b0ac  or      ebp, 0FFFFFFFFh
0x18000b0af  mov     [rax-60h], r14d
0x18000b0b3  mov     r15d, 0FDE9h
0x18000b0b9  mov     r9d, ebp; cchWideChar
0x18000b0bc  mov     [rax-68h], r14
0x18000b0c0  mov     ecx, r15d; CodePage
0x18000b0c3  xor     edx, edx; dwFlags
0x18000b0c5  call    cs:__imp_WideCharToMultiByte
0x18000b0cc  nop     dword ptr [rax+rax+00h]
0x18000b0d1  mov     ebx, eax
0x18000b0d3  test    eax, eax
0x18000b0d5  jz      short loc_18000B11D
0x18000b0d7  lea     ecx, [rax+1]
0x18000b0da  call    NetpMemoryAllocate
0x18000b0df  mov     rdi, rax
0x18000b0e2  test    rax, rax
0x18000b0e5  jz      short loc_18000B11D
0x18000b0e7  mov     [rsp+88h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18000b0ec  mov     r9d, ebp; cchWideChar
0x18000b0ef  mov     [rsp+88h+lpDefaultChar], r14; lpDefaultChar
0x18000b0f4  mov     r8, r13; lpWideCharStr
0x18000b0f7  mov     [rsp+88h+cbMultiByte], ebx; cbMultiByte
0x18000b0fb  xor     edx, edx; dwFlags
0x18000b0fd  mov     ecx, r15d; CodePage
0x18000b100  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x18000b105  call    cs:__imp_WideCharToMultiByte
0x18000b10c  nop     dword ptr [rax+rax+00h]
0x18000b111  test    eax, eax
0x18000b113  jnz     short loc_18000B12A
0x18000b115  mov     rcx, rdi
0x18000b118  call    NetpMemoryFree
0x18000b11d  mov     rdi, r14
0x18000b120  mov     ebx, 8
0x18000b125  jmp     loc_18000B2ED
0x18000b12a  cdqe
0x18000b12c  lea     r15, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDcDiscoveryCritSect
0x18000b133  mov     rcx, r15; CriticalSection
0x18000b136  mov     [rax+rdi], r14b
0x18000b13a  call    cs:__imp_RtlEnterCriticalSection
0x18000b141  nop     dword ptr [rax+rax+00h]
0x18000b146  mov     ebp, r14d
0x18000b149  cmp     ebp, cs:?NlGlobalTrustedDomainCount@@3KA; ulong NlGlobalTrustedDomainCount
0x18000b14f  jnb     loc_18000B214
0x18000b155  mov     eax, ebp
0x18000b157  lea     rbx, [rax+rax*4]
0x18000b15b  mov     rax, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18000b162  lea     rcx, [rax+rbx*8]
0x18000b166  test    rcx, rcx
0x18000b169  jz      short loc_18000B185
0x18000b16b  xor     r9d, r9d
0x18000b16e  mov     rdx, r13
0x18000b171  lea     r8d, [r9+6]
0x18000b175  call    cs:__imp_NetpwNameCompare
0x18000b17c  nop     dword ptr [rax+rax+00h]
0x18000b181  test    eax, eax
0x18000b183  jz      short loc_18000B1A6
0x18000b185  mov     rax, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18000b18c  mov     rcx, [rax+rbx*8+20h]; char *
0x18000b191  test    rcx, rcx
0x18000b194  jz      short loc_18000B1A2
0x18000b196  mov     rdx, rdi; char *
0x18000b199  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x18000b19e  test    eax, eax
0x18000b1a0  jnz     short loc_18000B1A6
0x18000b1a2  inc     ebp
0x18000b1a4  jmp     short loc_18000B149
0x18000b1a6  mov     rax, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18000b1ad  lea     rcx, [rax+rbx*8]; Src
0x18000b1b1  test    rcx, rcx
0x18000b1b4  jz      short loc_18000B1D3
0x18000b1b6  call    NetpAllocWStrFromWStr
0x18000b1bb  mov     [r12], rax
0x18000b1bf  test    rax, rax
0x18000b1c2  jnz     short loc_18000B1CC
0x18000b1c4  mov     rcx, r15
0x18000b1c7  jmp     loc_18000B2DC
0x18000b1cc  mov     rax, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18000b1d3  mov     rcx, [rax+rbx*8+20h]; lpMultiByteStr
0x18000b1d8  test    rcx, rcx
0x18000b1db  jz      short loc_18000B214
0x18000b1dd  lea     rax, [rsp+88h+arg_10]
0x18000b1e5  mov     [rsp+88h+arg_10], r14
0x18000b1ed  xor     r9d, r9d; unsigned __int16 *
0x18000b1f0  mov     [rsp+88h+lpMultiByteStr], rax; unsigned __int16 **
0x18000b1f5  xor     r8d, r8d; unsigned int
0x18000b1f8  or      edx, 0FFFFFFFFh; cbMultiByte
0x18000b1fb  call    ?NetpAllocWStrFromUtf8StrAsRequired@@YAKPEADKKPEAGPEAPEAG@Z; NetpAllocWStrFromUtf8StrAsRequired(char *,ulong,ulong,ushort *,ushort * *)
0x18000b200  test    eax, eax
0x18000b202  jnz     short loc_18000B21C
0x18000b204  mov     rax, [rsp+88h+arg_10]
0x18000b20c  mov     [rsi], rax
0x18000b20f  test    rax, rax
0x18000b212  jz      short loc_18000B1C4
0x18000b214  mov     rcx, r15
0x18000b217  jmp     loc_18000B325
0x18000b21c  mov     [rsi], r14
0x18000b21f  jmp     short loc_18000B1C4
0x18000b221  lea     rbp, [rcx+190h]
0x18000b228  mov     rdi, r14
0x18000b22b  mov     rcx, rbp; CriticalSection
0x18000b22e  call    cs:__imp_RtlEnterCriticalSection
0x18000b235  nop     dword ptr [rax+rax+00h]
0x18000b23a  cmp     r14d, [rbx+1E4h]
0x18000b241  jnb     loc_18000B31F
0x18000b247  mov     eax, r14d
0x18000b24a  imul    r15, rax, 38h ; '8'
0x18000b24e  mov     rax, [rbx+1D8h]
0x18000b255  mov     rcx, [r15+rax]
0x18000b259  test    rcx, rcx
0x18000b25c  jz      short loc_18000B278
0x18000b25e  xor     r9d, r9d
0x18000b261  mov     rdx, r13
0x18000b264  lea     r8d, [r9+6]
0x18000b268  call    cs:__imp_NetpwNameCompare
0x18000b26f  nop     dword ptr [rax+rax+00h]
0x18000b274  test    eax, eax
0x18000b276  jz      short loc_18000B29A
0x18000b278  mov     rax, [rbx+1D8h]
0x18000b27f  mov     rcx, [r15+rax+8]; unsigned __int16 *
0x18000b284  test    rcx, rcx
0x18000b287  jz      short loc_18000B295
0x18000b289  mov     rdx, r13; unsigned __int16 *
0x18000b28c  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18000b291  test    eax, eax
0x18000b293  jnz     short loc_18000B29A
0x18000b295  inc     r14d
0x18000b298  jmp     short loc_18000B23A
0x18000b29a  mov     rax, [rbx+1D8h]
0x18000b2a1  xor     r14d, r14d
0x18000b2a4  mov     rcx, [r15+rax]; Src
0x18000b2a8  test    rcx, rcx
0x18000b2ab  jz      short loc_18000B2BB
0x18000b2ad  call    NetpAllocWStrFromWStr
0x18000b2b2  mov     [r12], rax
0x18000b2b6  test    rax, rax
0x18000b2b9  jz      short loc_18000B2D9
0x18000b2bb  mov     rax, [rbx+1D8h]
0x18000b2c2  mov     rcx, [r15+rax+8]; Src
0x18000b2c7  test    rcx, rcx
0x18000b2ca  jz      short loc_18000B322
0x18000b2cc  call    NetpAllocWStrFromWStr
0x18000b2d1  mov     [rsi], rax
0x18000b2d4  test    rax, rax
0x18000b2d7  jnz     short loc_18000B322
0x18000b2d9  mov     rcx, rbp; CriticalSection
0x18000b2dc  mov     ebx, 8
0x18000b2e1  call    cs:__imp_RtlLeaveCriticalSection
0x18000b2e8  nop     dword ptr [rax+rax+00h]
0x18000b2ed  mov     rcx, [rsi]; Buffer
0x18000b2f0  test    rcx, rcx
0x18000b2f3  jz      short loc_18000B304
0x18000b2f5  call    cs:__imp_NetApiBufferFree
0x18000b2fc  nop     dword ptr [rax+rax+00h]
0x18000b301  mov     [rsi], r14
0x18000b304  mov     rcx, [r12]; Buffer
0x18000b308  test    rcx, rcx
0x18000b30b  jz      short loc_18000B334
0x18000b30d  call    cs:__imp_NetApiBufferFree
0x18000b314  nop     dword ptr [rax+rax+00h]
0x18000b319  mov     [r12], r14
0x18000b31d  jmp     short loc_18000B334
0x18000b31f  xor     r14d, r14d
0x18000b322  mov     rcx, rbp; CriticalSection
0x18000b325  call    cs:__imp_RtlLeaveCriticalSection
0x18000b32c  nop     dword ptr [rax+rax+00h]
0x18000b331  mov     ebx, r14d
0x18000b334  test    rdi, rdi
0x18000b337  jz      short loc_18000B341
0x18000b339  mov     rcx, rdi
0x18000b33c  call    NetpMemoryFree
0x18000b341  mov     eax, ebx
0x18000b343  add     rsp, 48h
0x18000b347  pop     r15
0x18000b349  pop     r14
0x18000b34b  pop     r13
0x18000b34d  pop     r12
0x18000b34f  pop     rdi
0x18000b350  pop     rsi
0x18000b351  pop     rbp
0x18000b352  pop     rbx
0x18000b353  retn
```
