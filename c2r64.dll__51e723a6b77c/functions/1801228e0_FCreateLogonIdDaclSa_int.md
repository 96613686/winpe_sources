# FCreateLogonIdDaclSa(int)

- ea: `0x1801228e0`
- end: `0x1801229cd`
- name: `?FCreateLogonIdDaclSa@@YA_NH@Z`
- size: `237`
- prototype: `bool __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180123508`

## callees

- `0x180020988`
- `0x1801228e0`
- `0x180122ea8`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180122928`
- `KERNEL32!LocalAlloc` at `0x180122928`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18012294b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18012294b`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18012296b`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18012296b`

## pseudocode

```c
char __fastcall FCreateLogonIdDaclSa(int a1)
{
  __int64 v1; // rsi
  char v2; // bl
  void **v3; // rax
  void * near *v4; // rax
  __int64 v5; // rdx
  struct _SECURITY_ATTRIBUTES near **v6; // rcx

  v1 = a1;
  v2 = 0;
  (&vrgpLogonIdACL)[a1] = (struct _ACL * near *)MsoCreateLogonIdAcl(dword_1801AF4A0[a1] & 0xEEE0FFFF | 0x120000);
  v3 = (void **)LocalAlloc(0x40u, 0x28u);
  (&vrgpsdLogonId)[v1] = v3;
  if ( v3
    && (&vrgpLogonIdACL)[v1]
    && InitializeSecurityDescriptor(v3, 1u)
    && SetSecurityDescriptorDacl((&vrgpsdLogonId)[v1], 1, (PACL)(&vrgpLogonIdACL)[v1], 0) )
  {
    v4 = (&vrgpsdLogonId)[v1];
    v5 = 3 * v1;
    dword_18021D260[2 * v5] = 0;
    v6 = &(&vrgsaLogonId)[3 * v1];
    qword_18021D258[v5] = (__int64)v4;
    *(_DWORD *)v6 = 24;
    v2 = 1;
    (&vrgpsaLogonId)[v1] = v6;
  }
  else
  {
    FreeLogonIdDaclSa(v1);
  }
  return v2;
}

```

## disassembly

```asm
0x1801228e0  mov     [rsp+arg_0], rbx
0x1801228e5  mov     [rsp+arg_8], rsi
0x1801228ea  mov     [rsp+arg_10], rdi
0x1801228ef  push    r14
0x1801228f1  sub     rsp, 20h
0x1801228f5  movsxd  rsi, ecx
0x1801228f8  lea     r14, __NULL_IMPORT_DESCRIPTOR
0x1801228ff  xor     ebx, ebx
0x180122901  mov     ecx, ds:rva dword_1801AF4A0[r14+rsi*4]
0x180122909  and     ecx, 0EEF2FFFFh
0x18012290f  or      ecx, 120000h; unsigned int
0x180122915  call    ?MsoCreateLogonIdAcl@@YAPEAU_ACL@@K@Z; MsoCreateLogonIdAcl(ulong)
0x18012291a  lea     edx, [rbx+28h]; uBytes
0x18012291d  mov     rva ?vrgpLogonIdACL@@3PAPEAU_ACL@@A[r14+rsi*8], rax; _ACL * near * vrgpLogonIdACL ...
0x180122925  lea     ecx, [rbx+40h]; uFlags
0x180122928  call    cs:__imp_LocalAlloc
0x18012292e  mov     rva ?vrgpsdLogonId@@3PAPEAXA[r14+rsi*8], rax; void * near * vrgpsdLogonId ...
0x180122936  test    rax, rax
0x180122939  jz      short loc_1801229AE
0x18012293b  cmp     rva ?vrgpLogonIdACL@@3PAPEAU_ACL@@A[r14+rsi*8], rbx; _ACL * near * vrgpLogonIdACL ...
0x180122943  jz      short loc_1801229AE
0x180122945  lea     edx, [rbx+1]; dwRevision
0x180122948  mov     rcx, rax; pSecurityDescriptor
0x18012294b  call    cs:__imp_InitializeSecurityDescriptor
0x180122951  test    eax, eax
0x180122953  jz      short loc_1801229AE
0x180122955  mov     r8, rva ?vrgpLogonIdACL@@3PAPEAU_ACL@@A[r14+rsi*8]; pDacl
0x18012295d  lea     edx, [rbx+1]; bDaclPresent
0x180122960  mov     rcx, rva ?vrgpsdLogonId@@3PAPEAXA[r14+rsi*8]; pSecurityDescriptor
0x180122968  xor     r9d, r9d; bDaclDefaulted
0x18012296b  call    cs:__imp_SetSecurityDescriptorDacl
0x180122971  test    eax, eax
0x180122973  jz      short loc_1801229AE
0x180122975  mov     rax, rva ?vrgpsdLogonId@@3PAPEAXA[r14+rsi*8]; void * near * vrgpsdLogonId ...
0x18012297d  lea     rdx, [rsi+rsi*2]
0x180122981  lea     rcx, rva ?vrgsaLogonId@@3PAU_SECURITY_ATTRIBUTES@@A[r14]; _SECURITY_ATTRIBUTES near * vrgsaLogonId ...
0x180122988  mov     rva dword_18021D260[r14+rdx*8], ebx
0x180122990  lea     rcx, [rcx+rdx*8]
0x180122994  mov     rva qword_18021D258[r14+rdx*8], rax
0x18012299c  mov     dword ptr [rcx], 18h
0x1801229a2  mov     bl, 1
0x1801229a4  mov     rva ?vrgpsaLogonId@@3PAPEAU_SECURITY_ATTRIBUTES@@A[r14+rsi*8], rcx; _SECURITY_ATTRIBUTES * near * vrgpsaLogonId ...
0x1801229ac  jmp     short loc_1801229B5
0x1801229ae  mov     ecx, esi; int
0x1801229b0  call    ?FreeLogonIdDaclSa@@YAXH@Z; FreeLogonIdDaclSa(int)
0x1801229b5  mov     rsi, [rsp+28h+arg_8]
0x1801229ba  mov     al, bl
0x1801229bc  mov     rbx, [rsp+28h+arg_0]
0x1801229c1  mov     rdi, [rsp+28h+arg_10]
0x1801229c6  add     rsp, 20h
0x1801229ca  pop     r14
0x1801229cc  retn
```
