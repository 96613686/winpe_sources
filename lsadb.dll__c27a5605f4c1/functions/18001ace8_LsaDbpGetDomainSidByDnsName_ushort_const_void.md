# LsaDbpGetDomainSidByDnsName(ushort const *,void * *)

- ea: `0x18001ace8`
- end: `0x18001ae7b`
- name: `?LsaDbpGetDomainSidByDnsName@@YAJPEBGPEAPEAX@Z`
- size: `403`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a894`

## callees

- `0x180001670`
- `0x18001ace8`
- `0x1800372f4`
- `0x18003acd0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ae01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ae01`
- `ntdll!RtlCopySid` at `0x18001ae33`
- `ntdll!RtlCopySid` at `0x18001ae33`
- `ntdll!RtlLengthSid` at `0x18001adf1`
- `ntdll!RtlLengthSid` at `0x18001adf1`
- `NTDSA!MatchDomainDnByDnsName` at `0x18001ad20`
- `NTDSA!MatchDomainDnByDnsName` at `0x18001addb`
- `NTDSA!MatchDomainDnByDnsName` at `0x18001ad20`
- `NTDSA!MatchDomainDnByDnsName` at `0x18001addb`

## pseudocode

```c
__int64 __fastcall LsaDbpGetDomainSidByDnsName(const unsigned __int16 *a1, void **a2)
{
  __int64 v4; // rdx
  int matched; // edi
  unsigned __int64 v6; // rdi
  ULONG *p_DestinationSidLength; // rbx
  unsigned __int64 v8; // rcx
  __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  _DWORD *v12; // rax
  HLOCAL v13; // rax
  __int64 v15; // [rsp+0h] [rbp-20h] BYREF
  ULONG DestinationSidLength; // [rsp+20h] [rbp+0h] BYREF
  __int64 v17; // [rsp+28h] [rbp+8h] BYREF

  *a2 = 0;
  DestinationSidLength = 0;
  matched = MatchDomainDnByDnsName(a1, 0, &DestinationSidLength);
  if ( matched >= 0 )
  {
    v6 = DestinationSidLength;
    p_DestinationSidLength = 0;
    if ( !DestinationSidLength )
      goto LABEL_10;
    if ( DestinationSidLength > (unsigned __int64)g_ulMaxStackAllocSize )
      goto LABEL_10;
    v8 = DestinationSidLength + g_ulAdditionalProbeSize + 8;
    if ( v8 < DestinationSidLength || !(unsigned int)VerifyStackAvailable(v8, v4) )
      goto LABEL_10;
    v9 = v6 + 23;
    if ( v6 + 23 <= v6 + 8 )
      v9 = 0xFFFFFFFFFFFFFF0LL;
    v10 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
    v11 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
    p_DestinationSidLength = &DestinationSidLength;
    if ( &v15 == (__int64 *)-32LL || (DestinationSidLength = 1801679955, (p_DestinationSidLength = (ULONG *)&v17) == 0) )
    {
LABEL_10:
      if ( v6 + 8 >= v6 )
      {
        v12 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        if ( !v12 )
          return (unsigned int)-1073741801;
        *v12 = 1885431112;
        p_DestinationSidLength = v12 + 2;
      }
      if ( !p_DestinationSidLength )
        return (unsigned int)-1073741801;
    }
    matched = MatchDomainDnByDnsName(a1, p_DestinationSidLength, &DestinationSidLength);
    if ( matched < 0 )
      goto LABEL_22;
    if ( p_DestinationSidLength[1] )
    {
      DestinationSidLength = RtlLengthSid(p_DestinationSidLength + 6);
      v13 = LocalAlloc(0x40u, DestinationSidLength);
      *a2 = v13;
      if ( !v13 )
      {
        if ( *(p_DestinationSidLength - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
        return (unsigned int)-1073741801;
      }
      RtlCopySid(DestinationSidLength, v13, p_DestinationSidLength + 6);
    }
    if ( p_DestinationSidLength )
    {
LABEL_22:
      if ( *(p_DestinationSidLength - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
    }
  }
  if ( !*a2 )
    return (unsigned int)-1073741601;
  return (unsigned int)matched;
}

```

## disassembly

```asm
0x18001ace8  push    rbp
0x18001acea  push    rbx
0x18001aceb  push    rsi
0x18001acec  push    rdi
0x18001aced  push    r14
0x18001acef  sub     rsp, 40h
0x18001acf3  lea     rbp, [rsp+20h]
0x18001acf8  mov     rax, cs:__security_cookie
0x18001acff  xor     rax, rbp
0x18001ad02  mov     [rbp+40h+var_30], rax
0x18001ad06  mov     r14, rdx
0x18001ad09  mov     qword ptr [rdx], 0
0x18001ad10  xor     edx, edx
0x18001ad12  mov     [rbp+40h+DestinationSidLength], 0
0x18001ad19  lea     r8, [rbp+40h+DestinationSidLength]
0x18001ad1d  mov     rsi, rcx
0x18001ad20  call    cs:__imp_MatchDomainDnByDnsName
0x18001ad26  mov     edi, eax
0x18001ad28  test    eax, eax
0x18001ad2a  js      loc_18001AE56
0x18001ad30  mov     edi, [rbp+40h+DestinationSidLength]
0x18001ad33  xor     ebx, ebx
0x18001ad35  test    rdi, rdi
0x18001ad38  jz      short loc_18001AD9B
0x18001ad3a  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001ad41  ja      short loc_18001AD9B
0x18001ad43  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001ad4a  add     rcx, 8
0x18001ad4e  add     rcx, rdi
0x18001ad51  cmp     rcx, rdi
0x18001ad54  jb      short loc_18001AD9B
0x18001ad56  call    VerifyStackAvailable
0x18001ad5b  test    eax, eax
0x18001ad5d  jz      short loc_18001AD9B
0x18001ad5f  lea     rax, [rdi+8]
0x18001ad63  lea     rcx, [rax+0Fh]
0x18001ad67  cmp     rcx, rax
0x18001ad6a  ja      short loc_18001AD76
0x18001ad6c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001ad76  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001ad7a  mov     rax, rcx
0x18001ad7d  call    _alloca_probe
0x18001ad82  sub     rsp, rcx
0x18001ad85  lea     rbx, [rsp+60h+DestinationSidLength]
0x18001ad8a  test    rbx, rbx
0x18001ad8d  jz      short loc_18001AD9B
0x18001ad8f  mov     dword ptr [rbx], 6B637453h
0x18001ad95  add     rbx, 8
0x18001ad99  jnz     short loc_18001ADD1
0x18001ad9b  lea     rcx, [rdi+8]
0x18001ad9f  cmp     rcx, rdi
0x18001ada2  jb      short loc_18001ADC2
0x18001ada4  mov     rax, cs:g_pfnAllocate
0x18001adab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adb0  mov     rbx, rax
0x18001adb3  test    rax, rax
0x18001adb6  jz      short loc_18001ADC7
0x18001adb8  mov     dword ptr [rax], 70616548h
0x18001adbe  add     rbx, 8
0x18001adc2  test    rbx, rbx
0x18001adc5  jnz     short loc_18001ADD1
0x18001adc7  mov     edi, 0C0000017h
0x18001adcc  jmp     loc_18001AE62
0x18001add1  lea     r8, [rbp+40h+DestinationSidLength]
0x18001add5  mov     rdx, rbx
0x18001add8  mov     rcx, rsi
0x18001addb  call    cs:__imp_MatchDomainDnByDnsName
0x18001ade1  mov     edi, eax
0x18001ade3  test    eax, eax
0x18001ade5  js      short loc_18001AE3E
0x18001ade7  cmp     dword ptr [rbx+4], 0
0x18001adeb  jbe     short loc_18001AE39
0x18001aded  lea     rcx, [rbx+18h]; Sid
0x18001adf1  call    cs:__imp_RtlLengthSid
0x18001adf7  mov     edx, eax; uBytes
0x18001adf9  mov     ecx, 40h ; '@'; uFlags
0x18001adfe  mov     [rbp+40h+DestinationSidLength], edx
0x18001ae01  call    cs:__imp_LocalAlloc
0x18001ae07  mov     [r14], rax
0x18001ae0a  test    rax, rax
0x18001ae0d  jnz     short loc_18001AE29
0x18001ae0f  lea     rcx, [rbx-8]
0x18001ae13  cmp     dword ptr [rcx], 70616548h
0x18001ae19  jnz     short loc_18001ADC7
0x18001ae1b  mov     rax, cs:g_pfnFree
0x18001ae22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae27  jmp     short loc_18001ADC7
0x18001ae29  mov     ecx, [rbp+40h+DestinationSidLength]; DestinationSidLength
0x18001ae2c  lea     r8, [rbx+18h]; SourceSid
0x18001ae30  mov     rdx, rax; DestinationSid
0x18001ae33  call    cs:__imp_RtlCopySid
0x18001ae39  test    rbx, rbx
0x18001ae3c  jz      short loc_18001AE56
0x18001ae3e  lea     rcx, [rbx-8]
0x18001ae42  cmp     dword ptr [rcx], 70616548h
0x18001ae48  jnz     short loc_18001AE56
0x18001ae4a  mov     rax, cs:g_pfnFree
0x18001ae51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae56  cmp     qword ptr [r14], 0
0x18001ae5a  mov     eax, 0C00000DFh
0x18001ae5f  cmovz   edi, eax
0x18001ae62  mov     eax, edi
0x18001ae64  mov     rcx, [rbp+40h+var_30]
0x18001ae68  xor     rcx, rbp; StackCookie
0x18001ae6b  call    __security_check_cookie
0x18001ae70  lea     rsp, [rbp+20h]
0x18001ae74  pop     r14
0x18001ae76  pop     rdi
0x18001ae77  pop     rsi
0x18001ae78  pop     rbx
0x18001ae79  pop     rbp
0x18001ae7a  retn
```
