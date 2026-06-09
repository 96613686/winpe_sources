# InternalSecurityContext::InitializeCertInfo(bool)

- ea: `0x180017460`
- end: `0x1800174d2`
- name: `?InitializeCertInfo@InternalSecurityContext@@UEAAJ_N@Z`
- size: `114`
- prototype: `__int64 __fastcall(InternalSecurityContext *__hidden this, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180013c74`
- `0x180016f30`
- `0x180017460`

## pseudocode

```c
__int64 __fastcall InternalSecurityContext::InitializeCertInfo(InternalSecurityContext *this, unsigned __int8 a2)
{
  int v3; // ebx

  v3 = RTSecurityContextBase::HandleInternalCert(this, a2);
  *((_DWORD *)this + 17) = v3;
  if ( (unsigned int)InternalSecurityContext::s_allocatedUserSidLength < *((_DWORD *)this + 11) )
    LODWORD(InternalSecurityContext::s_allocatedUserSidLength) = *((_DWORD *)this + 11);
  if ( (unsigned int)InternalSecurityContext::s_allocatedUserCertLength < *((_DWORD *)this + 12) )
    LODWORD(InternalSecurityContext::s_allocatedUserCertLength) = *((_DWORD *)this + 12);
  if ( InternalSecurityContext::s_allocatedProviderNameLength < *((_DWORD *)this + 13) )
    InternalSecurityContext::s_allocatedProviderNameLength = *((_DWORD *)this + 13);
  if ( v3 < 0 )
    LogMsgHR(v3, (wchar_t *)L"rt/rtsecctx", 0x10Eu);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017460  mov     [rsp+arg_0], rbx
0x180017465  push    rdi
0x180017466  sub     rsp, 20h
0x18001746a  movzx   edx, dl; int
0x18001746d  mov     rdi, rcx
0x180017470  call    ?HandleInternalCert@RTSecurityContextBase@@IEAAJH@Z; RTSecurityContextBase::HandleInternalCert(int)
0x180017475  mov     ebx, eax
0x180017477  mov     [rdi+44h], eax
0x18001747a  mov     eax, [rdi+2Ch]
0x18001747d  cmp     cs:?s_allocatedUserSidLength@InternalSecurityContext@@0KA, eax; ulong InternalSecurityContext::s_allocatedUserSidLength
0x180017483  jnb     short loc_18001748B
0x180017485  mov     cs:?s_allocatedUserSidLength@InternalSecurityContext@@0KA, eax; ulong InternalSecurityContext::s_allocatedUserSidLength
0x18001748b  mov     eax, [rdi+30h]
0x18001748e  cmp     cs:?s_allocatedUserCertLength@InternalSecurityContext@@0KA, eax; ulong InternalSecurityContext::s_allocatedUserCertLength
0x180017494  jnb     short loc_18001749C
0x180017496  mov     cs:?s_allocatedUserCertLength@InternalSecurityContext@@0KA, eax; ulong InternalSecurityContext::s_allocatedUserCertLength
0x18001749c  mov     eax, [rdi+34h]
0x18001749f  cmp     cs:?s_allocatedProviderNameLength@InternalSecurityContext@@0KA, eax; ulong InternalSecurityContext::s_allocatedProviderNameLength
0x1800174a5  jnb     short loc_1800174AD
0x1800174a7  mov     cs:?s_allocatedProviderNameLength@InternalSecurityContext@@0KA, eax; ulong InternalSecurityContext::s_allocatedProviderNameLength
0x1800174ad  test    ebx, ebx
0x1800174af  jns     short loc_1800174C5
0x1800174b1  mov     r8d, 10Eh; unsigned __int16
0x1800174b7  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x1800174be  mov     ecx, ebx; int
0x1800174c0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800174c5  mov     eax, ebx
0x1800174c7  mov     rbx, [rsp+28h+arg_0]
0x1800174cc  add     rsp, 20h
0x1800174d0  pop     rdi
0x1800174d1  retn
```
