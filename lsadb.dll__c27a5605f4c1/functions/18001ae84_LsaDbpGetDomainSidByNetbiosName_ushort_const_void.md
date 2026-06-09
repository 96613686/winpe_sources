# LsaDbpGetDomainSidByNetbiosName(ushort const *,void * *)

- ea: `0x18001ae84`
- end: `0x18001b017`
- name: `?LsaDbpGetDomainSidByNetbiosName@@YAJPEBGPEAPEAX@Z`
- size: `403`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a894`
- `0x18001e138`

## callees

- `0x180001670`
- `0x18001ae84`
- `0x1800372f4`
- `0x18003acd0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001af9d`
- `ntdll!RtlCopySid` at `0x18001afcf`
- `ntdll!RtlCopySid` at `0x18001afcf`
- `ntdll!RtlLengthSid` at `0x18001af8d`
- `ntdll!RtlLengthSid` at `0x18001af8d`
- `NTDSA!MatchDomainDnByNetbiosName` at `0x18001aebc`
- `NTDSA!MatchDomainDnByNetbiosName` at `0x18001af77`
- `NTDSA!MatchDomainDnByNetbiosName` at `0x18001aebc`
- `NTDSA!MatchDomainDnByNetbiosName` at `0x18001af77`

## pseudocode

```c
__int64 __fastcall LsaDbpGetDomainSidByNetbiosName(const unsigned __int16 *a1, void **a2)
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
  matched = MatchDomainDnByNetbiosName(a1, 0, &DestinationSidLength);
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
    matched = MatchDomainDnByNetbiosName(a1, p_DestinationSidLength, &DestinationSidLength);
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
0x18001ae84  push    rbp
0x18001ae86  push    rbx
0x18001ae87  push    rsi
0x18001ae88  push    rdi
0x18001ae89  push    r14
0x18001ae8b  sub     rsp, 40h
0x18001ae8f  lea     rbp, [rsp+20h]
0x18001ae94  mov     rax, cs:__security_cookie
0x18001ae9b  xor     rax, rbp
0x18001ae9e  mov     [rbp+40h+var_30], rax
0x18001aea2  mov     r14, rdx
0x18001aea5  mov     qword ptr [rdx], 0
0x18001aeac  xor     edx, edx
0x18001aeae  mov     [rbp+40h+DestinationSidLength], 0
0x18001aeb5  lea     r8, [rbp+40h+DestinationSidLength]
0x18001aeb9  mov     rsi, rcx
0x18001aebc  call    cs:__imp_MatchDomainDnByNetbiosName
0x18001aec2  mov     edi, eax
0x18001aec4  test    eax, eax
0x18001aec6  js      loc_18001AFF2
0x18001aecc  mov     edi, [rbp+40h+DestinationSidLength]
0x18001aecf  xor     ebx, ebx
0x18001aed1  test    rdi, rdi
0x18001aed4  jz      short loc_18001AF37
0x18001aed6  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001aedd  ja      short loc_18001AF37
0x18001aedf  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001aee6  add     rcx, 8
0x18001aeea  add     rcx, rdi
0x18001aeed  cmp     rcx, rdi
0x18001aef0  jb      short loc_18001AF37
0x18001aef2  call    VerifyStackAvailable
0x18001aef7  test    eax, eax
0x18001aef9  jz      short loc_18001AF37
0x18001aefb  lea     rax, [rdi+8]
0x18001aeff  lea     rcx, [rax+0Fh]
0x18001af03  cmp     rcx, rax
0x18001af06  ja      short loc_18001AF12
0x18001af08  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001af12  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001af16  mov     rax, rcx
0x18001af19  call    _alloca_probe
0x18001af1e  sub     rsp, rcx
0x18001af21  lea     rbx, [rsp+60h+DestinationSidLength]
0x18001af26  test    rbx, rbx
0x18001af29  jz      short loc_18001AF37
0x18001af2b  mov     dword ptr [rbx], 6B637453h
0x18001af31  add     rbx, 8
0x18001af35  jnz     short loc_18001AF6D
0x18001af37  lea     rcx, [rdi+8]
0x18001af3b  cmp     rcx, rdi
0x18001af3e  jb      short loc_18001AF5E
0x18001af40  mov     rax, cs:g_pfnAllocate
0x18001af47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af4c  mov     rbx, rax
0x18001af4f  test    rax, rax
0x18001af52  jz      short loc_18001AF63
0x18001af54  mov     dword ptr [rax], 70616548h
0x18001af5a  add     rbx, 8
0x18001af5e  test    rbx, rbx
0x18001af61  jnz     short loc_18001AF6D
0x18001af63  mov     edi, 0C0000017h
0x18001af68  jmp     loc_18001AFFE
0x18001af6d  lea     r8, [rbp+40h+DestinationSidLength]
0x18001af71  mov     rdx, rbx
0x18001af74  mov     rcx, rsi
0x18001af77  call    cs:__imp_MatchDomainDnByNetbiosName
0x18001af7d  mov     edi, eax
0x18001af7f  test    eax, eax
0x18001af81  js      short loc_18001AFDA
0x18001af83  cmp     dword ptr [rbx+4], 0
0x18001af87  jbe     short loc_18001AFD5
0x18001af89  lea     rcx, [rbx+18h]; Sid
0x18001af8d  call    cs:__imp_RtlLengthSid
0x18001af93  mov     edx, eax; uBytes
0x18001af95  mov     ecx, 40h ; '@'; uFlags
0x18001af9a  mov     [rbp+40h+DestinationSidLength], edx
0x18001af9d  call    cs:__imp_LocalAlloc
0x18001afa3  mov     [r14], rax
0x18001afa6  test    rax, rax
0x18001afa9  jnz     short loc_18001AFC5
0x18001afab  lea     rcx, [rbx-8]
0x18001afaf  cmp     dword ptr [rcx], 70616548h
0x18001afb5  jnz     short loc_18001AF63
0x18001afb7  mov     rax, cs:g_pfnFree
0x18001afbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afc3  jmp     short loc_18001AF63
0x18001afc5  mov     ecx, [rbp+40h+DestinationSidLength]; DestinationSidLength
0x18001afc8  lea     r8, [rbx+18h]; SourceSid
0x18001afcc  mov     rdx, rax; DestinationSid
0x18001afcf  call    cs:__imp_RtlCopySid
0x18001afd5  test    rbx, rbx
0x18001afd8  jz      short loc_18001AFF2
0x18001afda  lea     rcx, [rbx-8]
0x18001afde  cmp     dword ptr [rcx], 70616548h
0x18001afe4  jnz     short loc_18001AFF2
0x18001afe6  mov     rax, cs:g_pfnFree
0x18001afed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aff2  cmp     qword ptr [r14], 0
0x18001aff6  mov     eax, 0C00000DFh
0x18001affb  cmovz   edi, eax
0x18001affe  mov     eax, edi
0x18001b000  mov     rcx, [rbp+40h+var_30]
0x18001b004  xor     rcx, rbp; StackCookie
0x18001b007  call    __security_check_cookie
0x18001b00c  lea     rsp, [rbp+20h]
0x18001b010  pop     r14
0x18001b012  pop     rdi
0x18001b013  pop     rsi
0x18001b014  pop     rbx
0x18001b015  pop     rbp
0x18001b016  retn
```
