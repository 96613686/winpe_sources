# InternalSecurityContext::CreateEmptySecurityContext(void)

- ea: `0x180016500`
- end: `0x1800165ca`
- name: `?CreateEmptySecurityContext@InternalSecurityContext@@SAPEAV1@XZ`
- size: `202`
- prototype: `struct InternalSecurityContext *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b398`

## callees

- `0x180016500`
- `0x180021010`
- `0x180023c5a`

## pseudocode

```c
struct InternalSecurityContext *InternalSecurityContext::CreateEmptySecurityContext(void)
{
  char *v0; // rax
  char *v1; // rdi
  void *v2; // rax
  void *v3; // rax

  v0 = (char *)MmAllocate(0x48u);
  v1 = v0;
  if ( v0 )
  {
    memset_0(v0 + 8, 0, 0x40u);
    *((_DWORD *)v1 + 8) = 1;
    *((_DWORD *)v1 + 15) = 1;
    *((_DWORD *)v1 + 16) = 2;
    *(_QWORD *)v1 = &InternalSecurityContext::`vftable';
  }
  else
  {
    v1 = 0;
  }
  if ( (_DWORD)InternalSecurityContext::s_allocatedUserSidLength )
  {
    *((_QWORD *)v1 + 1) = MmAllocate((unsigned int)InternalSecurityContext::s_allocatedUserSidLength);
    *((_DWORD *)v1 + 11) = InternalSecurityContext::s_allocatedUserSidLength;
  }
  if ( (_DWORD)InternalSecurityContext::s_allocatedUserCertLength )
  {
    v2 = MmAllocate((unsigned int)InternalSecurityContext::s_allocatedUserCertLength);
    *((_DWORD *)v1 + 12) = InternalSecurityContext::s_allocatedUserCertLength;
    *((_QWORD *)v1 + 2) = v2;
  }
  if ( InternalSecurityContext::s_allocatedProviderNameLength )
  {
    v3 = MmAllocate(saturated_mul(InternalSecurityContext::s_allocatedProviderNameLength, 2u));
    *((_DWORD *)v1 + 13) = InternalSecurityContext::s_allocatedProviderNameLength;
    *((_QWORD *)v1 + 3) = v3;
  }
  return (struct InternalSecurityContext *)v1;
}

```

## disassembly

```asm
0x180016500  mov     [rsp+arg_8], rbx
0x180016505  push    rdi
0x180016506  sub     rsp, 20h
0x18001650a  mov     ecx, 48h ; 'H'; unsigned __int64
0x18001650f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180016514  mov     [rsp+28h+arg_0], rax
0x180016519  mov     rdi, rax
0x18001651c  test    rax, rax
0x18001651f  jz      short loc_18001654E
0x180016521  xor     edx, edx; Val
0x180016523  lea     rcx, [rax+8]; void *
0x180016527  lea     r8d, [rdx+40h]; Size
0x18001652b  call    memset_0
0x180016530  mov     eax, 1
0x180016535  mov     [rdi+20h], eax
0x180016538  mov     [rdi+3Ch], eax
0x18001653b  lea     rax, ??_7InternalSecurityContext@@6B@; const InternalSecurityContext::`vftable'
0x180016542  mov     dword ptr [rdi+40h], 2
0x180016549  mov     [rdi], rax
0x18001654c  jmp     short loc_180016550
0x18001654e  xor     edi, edi
0x180016550  mov     eax, cs:?s_allocatedUserSidLength@InternalSecurityContext@@0KA; ulong InternalSecurityContext::s_allocatedUserSidLength
0x180016556  test    eax, eax
0x180016558  jz      short loc_18001656E
0x18001655a  mov     ecx, eax; unsigned __int64
0x18001655c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180016561  mov     [rdi+8], rax
0x180016565  mov     eax, cs:?s_allocatedUserSidLength@InternalSecurityContext@@0KA; ulong InternalSecurityContext::s_allocatedUserSidLength
0x18001656b  mov     [rdi+2Ch], eax
0x18001656e  mov     ecx, cs:?s_allocatedUserCertLength@InternalSecurityContext@@0KA; unsigned __int64
0x180016574  test    ecx, ecx
0x180016576  jz      short loc_18001658A
0x180016578  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001657d  mov     ecx, cs:?s_allocatedUserCertLength@InternalSecurityContext@@0KA; ulong InternalSecurityContext::s_allocatedUserCertLength
0x180016583  mov     [rdi+30h], ecx
0x180016586  mov     [rdi+10h], rax
0x18001658a  mov     ecx, cs:?s_allocatedProviderNameLength@InternalSecurityContext@@0KA; ulong InternalSecurityContext::s_allocatedProviderNameLength
0x180016590  test    ecx, ecx
0x180016592  jz      short loc_1800165BC
0x180016594  mov     eax, 2
0x180016599  mul     rcx
0x18001659c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800165a3  cmovb   rax, rcx
0x1800165a7  mov     rcx, rax; unsigned __int64
0x1800165aa  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800165af  mov     ecx, cs:?s_allocatedProviderNameLength@InternalSecurityContext@@0KA; ulong InternalSecurityContext::s_allocatedProviderNameLength
0x1800165b5  mov     [rdi+34h], ecx
0x1800165b8  mov     [rdi+18h], rax
0x1800165bc  mov     rbx, [rsp+28h+arg_8]
0x1800165c1  mov     rax, rdi
0x1800165c4  add     rsp, 20h
0x1800165c8  pop     rdi
0x1800165c9  retn
```
