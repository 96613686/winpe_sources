# FCreateUserDaclSa(int)

- ea: `0x1801229d0`
- end: `0x180122b25`
- name: `?FCreateUserDaclSa@@YA_NH@Z`
- size: `341`
- prototype: `bool __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180123538`

## callees

- `0x180020ad0`
- `0x180122178`
- `0x1801229d0`
- `0x180122d2c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180122a79`
- `KERNEL32!LocalAlloc` at `0x180122a79`
- `KERNEL32!GlobalFree` at `0x180122a29`
- `KERNEL32!GlobalFree` at `0x180122a29`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180122a9e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180122a9e`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180122abf`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180122abf`

## pseudocode

```c
char __fastcall FCreateUserDaclSa(unsigned __int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbp
  char v5; // bl
  int v6; // esi
  BOOL v7; // eax
  struct _ACL **v8; // rax
  void **v9; // rax
  void * near *v10; // rax
  __int64 v11; // rdx
  struct _SECURITY_ATTRIBUTES near **v12; // rcx
  unsigned int v14; // [rsp+50h] [rbp+8h] BYREF
  void *v15; // [rsp+58h] [rbp+10h] BYREF

  v4 = (int)a1;
  v5 = 0;
  v6 = dword_1801AF4A0[(int)a1];
  if ( !vpUserSID )
  {
    v15 = 0;
    v7 = FAllocateAndRetrieveUserSid(1, &v15);
    a1 = (unsigned __int64)v15 & -(__int64)v7;
    if ( a1 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&vpUserSID, a1, 0) )
        GlobalFree((HGLOBAL)a1);
    }
  }
  if ( vpUserSID )
  {
    v15 = vpUserSID;
    v14 = v6 & 0xEEE0FFFF | 0x120000;
    v8 = (struct _ACL **)MsoCreateAcl((const unsigned int *const)a1, a2, &v14, a4, &v15);
  }
  else
  {
    v8 = 0;
  }
  (&vrgpUserACL)[v4] = v8;
  v9 = (void **)LocalAlloc(0x40u, 0x28u);
  (&vrgpsdUser)[v4] = v9;
  if ( v9
    && (&vrgpUserACL)[v4]
    && InitializeSecurityDescriptor(v9, 1u)
    && SetSecurityDescriptorDacl((&vrgpsdUser)[v4], 1, (PACL)(&vrgpUserACL)[v4], 0) )
  {
    v10 = (&vrgpsdUser)[v4];
    v11 = 3 * v4;
    v12 = &(&vrgsaUser)[3 * v4];
    dword_18021D120[2 * v11] = 0;
    *(_DWORD *)v12 = 24;
    v5 = 1;
    (&vrgpsaUser)[v4] = v12;
    qword_18021D118[v11] = (__int64)v10;
  }
  else
  {
    FreeUserDaclSa(v4);
  }
  return v5;
}

```

## disassembly

```asm
0x1801229d0  mov     rax, rsp
0x1801229d3  mov     [rax+18h], rbx
0x1801229d7  mov     [rax+20h], rbp
0x1801229db  push    rsi
0x1801229dc  push    rdi
0x1801229dd  push    r14
0x1801229df  sub     rsp, 30h
0x1801229e3  movsxd  rbp, ecx
0x1801229e6  lea     r14, __NULL_IMPORT_DESCRIPTOR
0x1801229ed  xor     ebx, ebx
0x1801229ef  cmp     cs:?vpUserSID@@3PEAXEA, rbx; void * vpUserSID
0x1801229f6  mov     esi, ds:rva dword_1801AF4A0[r14+rbp*4]
0x1801229fe  jnz     short loc_180122A2F
0x180122a00  lea     rdx, [rax+10h]; void **
0x180122a04  mov     [rax+10h], rbx
0x180122a08  lea     ecx, [rbx+1]; unsigned int
0x180122a0b  call    ?FAllocateAndRetrieveUserSid@@YAHKPEAPEAX@Z; FAllocateAndRetrieveUserSid(ulong,void * *)
0x180122a10  neg     eax
0x180122a12  sbb     rcx, rcx
0x180122a15  and     rcx, [rsp+48h+arg_8]; hMem
0x180122a1a  jz      short loc_180122A2F
0x180122a1c  xor     eax, eax
0x180122a1e  lock cmpxchg cs:?vpUserSID@@3PEAXEA, rcx; void * vpUserSID
0x180122a27  jz      short loc_180122A2F
0x180122a29  call    cs:__imp_GlobalFree
0x180122a2f  mov     rax, cs:?vpUserSID@@3PEAXEA; void * vpUserSID
0x180122a36  test    rax, rax
0x180122a39  jz      short loc_180122A66
0x180122a3b  and     esi, 0EEF2FFFFh
0x180122a41  mov     [rsp+48h+arg_8], rax
0x180122a46  or      esi, 120000h
0x180122a4c  lea     rax, [rsp+48h+arg_8]
0x180122a51  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180122a56  mov     [rsp+48h+arg_0], esi
0x180122a5a  mov     [rsp+48h+var_28], rax; void **
0x180122a5f  call    ?MsoCreateAcl@@YAPEAU_ACL@@QEBKH0HQEAPEAX@Z; MsoCreateAcl(ulong const * const,int,ulong const * const,int,void * * const)
0x180122a64  jmp     short loc_180122A69
0x180122a66  mov     rax, rbx
0x180122a69  mov     edx, 28h ; '('; uBytes
0x180122a6e  mov     rva ?vrgpUserACL@@3PAPEAU_ACL@@A[r14+rbp*8], rax; _ACL * near * vrgpUserACL ...
0x180122a76  lea     ecx, [rdx+18h]; uFlags
0x180122a79  call    cs:__imp_LocalAlloc
0x180122a7f  mov     rva ?vrgpsdUser@@3PAPEAXA[r14+rbp*8], rax; void * near * vrgpsdUser ...
0x180122a87  test    rax, rax
0x180122a8a  jz      short loc_180122B09
0x180122a8c  cmp     rva ?vrgpUserACL@@3PAPEAU_ACL@@A[r14+rbp*8], rbx; _ACL * near * vrgpUserACL ...
0x180122a94  jz      short loc_180122B09
0x180122a96  mov     edx, 1; dwRevision
0x180122a9b  mov     rcx, rax; pSecurityDescriptor
0x180122a9e  call    cs:__imp_InitializeSecurityDescriptor
0x180122aa4  test    eax, eax
0x180122aa6  jz      short loc_180122B09
0x180122aa8  mov     r8, rva ?vrgpUserACL@@3PAPEAU_ACL@@A[r14+rbp*8]; pDacl
0x180122ab0  xor     r9d, r9d; bDaclDefaulted
0x180122ab3  mov     rcx, rva ?vrgpsdUser@@3PAPEAXA[r14+rbp*8]; pSecurityDescriptor
0x180122abb  lea     edx, [r9+1]; bDaclPresent
0x180122abf  call    cs:__imp_SetSecurityDescriptorDacl
0x180122ac5  test    eax, eax
0x180122ac7  jz      short loc_180122B09
0x180122ac9  mov     rax, rva ?vrgpsdUser@@3PAPEAXA[r14+rbp*8]; void * near * vrgpsdUser ...
0x180122ad1  lea     rdx, ds:0[rbp*2]
0x180122ad9  add     rdx, rbp
0x180122adc  lea     rcx, rva ?vrgsaUser@@3PAU_SECURITY_ATTRIBUTES@@A[r14]; _SECURITY_ATTRIBUTES near * vrgsaUser ...
0x180122ae3  lea     rcx, [rcx+rdx*8]
0x180122ae7  mov     rva dword_18021D120[r14+rdx*8], ebx
0x180122aef  mov     dword ptr [rcx], 18h
0x180122af5  mov     bl, 1
0x180122af7  mov     rva ?vrgpsaUser@@3PAPEAU_SECURITY_ATTRIBUTES@@A[r14+rbp*8], rcx; _SECURITY_ATTRIBUTES * near * vrgpsaUser ...
0x180122aff  mov     rva qword_18021D118[r14+rdx*8], rax
0x180122b07  jmp     short loc_180122B10
0x180122b09  mov     ecx, ebp; int
0x180122b0b  call    ?FreeUserDaclSa@@YAXH@Z; FreeUserDaclSa(int)
0x180122b10  mov     rbp, [rsp+48h+arg_18]
0x180122b15  mov     al, bl
0x180122b17  mov     rbx, [rsp+48h+arg_10]
0x180122b1c  add     rsp, 30h
0x180122b20  pop     r14
0x180122b22  pop     rdi
0x180122b23  pop     rsi
0x180122b24  retn
```
