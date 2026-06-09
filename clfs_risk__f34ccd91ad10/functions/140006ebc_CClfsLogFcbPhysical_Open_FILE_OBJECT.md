# CClfsLogFcbPhysical::Open(_FILE_OBJECT *)

- ea: `0x140006ebc`
- end: `0x140006f9e`
- name: `?Open@CClfsLogFcbPhysical@@QEAAJPEAU_FILE_OBJECT@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140005f1c`
- `0x140076e00`

## callees

- `0x140005840`
- `0x140006ebc`
- `0x14000714c`
- `0x140007180`
- `0x140017f20`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140006f27`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140006f27`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006ee1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006ee1`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::Open(CClfsLogFcbPhysical *this, struct _FILE_OBJECT *a2)
{
  CClfsLogCcb *v4; // rax
  CClfsLogCcb *v5; // rbx
  int v6; // r15d

  v4 = (CClfsLogCcb *)ExAllocateFromNPagedLookasideList(&CClfsLogCcb::m_laList);
  if ( v4 )
    v5 = CClfsLogCcb::CClfsLogCcb(v4);
  else
    v5 = 0;
  if ( !v5 )
    return 3221225626LL;
  _InterlockedIncrement((volatile signed __int32 *)v5 + 6);
  *((_BYTE *)v5 + 64) = 0;
  *((_QWORD *)v5 + 9) = a2;
  _InterlockedOr((volatile signed __int32 *)v5 + 7, 1u);
  v6 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  CClfsLogCcb::Link(v5, (struct _LIST_ENTRY *)this + 25);
  a2->FsContext = (char *)this + 56;
  a2->FsContext2 = v5;
  a2->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 48LL))(this);
  if ( v6 )
    ClfsReleaseResourceLite((char *)this + 200);
  return 0;
}

```

## disassembly

```asm
0x140006ebc  mov     [rsp+arg_8], rbx
0x140006ec1  mov     [rsp+arg_18], rsi
0x140006ec6  mov     [rsp+arg_0], rcx
0x140006ecb  push    rdi
0x140006ecc  push    r14
0x140006ece  push    r15
0x140006ed0  sub     rsp, 20h
0x140006ed4  mov     r14, rdx
0x140006ed7  mov     rdi, rcx
0x140006eda  lea     rcx, ?m_laList@CClfsLogCcb@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140006ee1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140006ee8  nop     dword ptr [rax+rax+00h]
0x140006eed  test    rax, rax
0x140006ef0  jz      loc_140006F90
0x140006ef6  mov     rcx, rax; this
0x140006ef9  call    ??0CClfsLogCcb@@QEAA@XZ; CClfsLogCcb::CClfsLogCcb(void)
0x140006efe  mov     rbx, rax
0x140006f01  test    rbx, rbx
0x140006f04  jz      loc_140006F97
0x140006f0a  lock inc dword ptr [rbx+18h]
0x140006f0e  mov     byte ptr [rbx+40h], 0
0x140006f12  mov     [rbx+48h], r14
0x140006f16  lock or dword ptr [rbx+1Ch], 1
0x140006f1b  lea     rsi, [rdi+0C8h]
0x140006f22  mov     dl, 1; Wait
0x140006f24  mov     rcx, rsi; Resource
0x140006f27  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140006f2e  nop     dword ptr [rax+rax+00h]
0x140006f33  movzx   r15d, al
0x140006f37  mov     [rsp+38h+arg_10], r15d
0x140006f3c  lea     rdx, [rdi+190h]; struct _LIST_ENTRY *
0x140006f43  mov     rcx, rbx; this
0x140006f46  call    ?Link@CClfsLogCcb@@QEAAXPEAU_LIST_ENTRY@@@Z; CClfsLogCcb::Link(_LIST_ENTRY *)
0x140006f4b  lea     rdx, [rdi+38h]
0x140006f4f  mov     [r14+18h], rdx
0x140006f53  mov     [r14+20h], rbx
0x140006f57  mov     rax, [rdi]
0x140006f5a  mov     rax, [rax+30h]
0x140006f5e  mov     rcx, rdi
0x140006f61  call    _guard_dispatch_icall
0x140006f66  mov     [r14+28h], rax
0x140006f6a  test    r15d, r15d
0x140006f6d  jnz     short loc_140006F86
0x140006f6f  xor     eax, eax
0x140006f71  mov     rbx, [rsp+38h+arg_8]
0x140006f76  mov     rsi, [rsp+38h+arg_18]
0x140006f7b  add     rsp, 20h
0x140006f7f  pop     r15
0x140006f81  pop     r14
0x140006f83  pop     rdi
0x140006f84  retn
0x140006f86  mov     rcx, rsi
0x140006f89  call    ClfsReleaseResourceLite
0x140006f8e  jmp     short loc_140006F6F
0x140006f90  xor     ebx, ebx
0x140006f92  jmp     loc_140006F01
0x140006f97  mov     eax, 0C000009Ah
0x140006f9c  jmp     short loc_140006F71
0x140018e3f  push    rbp
0x140018e41  sub     rsp, 20h
0x140018e45  mov     rbp, rdx
0x140018e48  cmp     dword ptr [rbp+50h], 0
0x140018e4c  jz      short loc_140018E5F
0x140018e4e  mov     rcx, [rbp+40h]
0x140018e52  add     rcx, 0C8h
0x140018e59  call    ClfsReleaseResourceLite
0x140018e5e  nop
0x140018e5f  add     rsp, 20h
0x140018e63  pop     rbp
0x140018e64  retn
```
