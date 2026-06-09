# CClfsRequest::AllocateKernelWriteContext(_FILE_OBJECT *,_CLFS_KERNEL_WRITE_CONTEXT &)

- ea: `0x14000bc60`
- end: `0x14000bd00`
- name: `?AllocateKernelWriteContext@CClfsRequest@@SAJPEAU_FILE_OBJECT@@AEAU_CLFS_KERNEL_WRITE_CONTEXT@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(struct _FILE_OBJECT *, struct _CLFS_KERNEL_WRITE_CONTEXT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005ba4c`

## callees

- `0x14000bc60`
- `0x140058660`
- `0x140058670`
- `0x1400587c0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000bcea`
- `ntoskrnl!IoFreeIrp` at `0x14000bcea`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000bcaa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000bcaa`
- `ntoskrnl!IoAllocateIrp` at `0x14000bc8f`
- `ntoskrnl!IoAllocateIrp` at `0x14000bc8f`

## pseudocode

```c
__int64 __fastcall CClfsRequest::AllocateKernelWriteContext(
        struct _FILE_OBJECT *a1,
        struct _CLFS_KERNEL_WRITE_CONTEXT *a2)
{
  struct CClfsLogFcbCommon *v4; // rsi
  struct _FILE_OBJECT *const v5; // rcx
  struct CClfsLogCcb *v6; // rax
  _QWORD *v7; // rdx
  struct CClfsLogCcb *v8; // rbp
  PIRP Irp; // rax
  CClfsRequest *v10; // rax
  CClfsRequest *v11; // rax

  v4 = CClfsLogFcbCommon::FcbFromFileObject(a1);
  v6 = CClfsLogFcbCommon::CcbFromFileObject(v5);
  *v7 = 0;
  v8 = v6;
  v7[1] = 0;
  Irp = IoAllocateIrp(1, 0);
  *(_QWORD *)a2 = Irp;
  if ( Irp )
  {
    v10 = (CClfsRequest *)ExAllocateFromNPagedLookasideList(&CClfsRequest::m_laList);
    if ( v10 )
    {
      v11 = CClfsRequest::CClfsRequest(v10, a1, v4, v8);
      *((_QWORD *)a2 + 1) = v11;
      if ( v11 )
        return 0;
    }
    else
    {
      *((_QWORD *)a2 + 1) = 0;
    }
    IoFreeIrp(*(PIRP *)a2);
    *(_QWORD *)a2 = 0;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000bc60  push    rbx
0x14000bc62  push    rbp
0x14000bc63  push    rsi
0x14000bc64  push    rdi
0x14000bc65  push    r14
0x14000bc67  sub     rsp, 20h
0x14000bc6b  mov     rbx, rdx
0x14000bc6e  mov     rdi, rcx
0x14000bc71  call    ?FcbFromFileObject@CClfsLogFcbCommon@@SAPEAV1@QEAU_FILE_OBJECT@@@Z; CClfsLogFcbCommon::FcbFromFileObject(_FILE_OBJECT * const)
0x14000bc76  mov     rsi, rax
0x14000bc79  call    ?CcbFromFileObject@CClfsLogFcbCommon@@SAPEAVCClfsLogCcb@@QEAU_FILE_OBJECT@@@Z; CClfsLogFcbCommon::CcbFromFileObject(_FILE_OBJECT * const)
0x14000bc7e  xor     r14d, r14d
0x14000bc81  mov     cl, 1; StackSize
0x14000bc83  mov     [rdx], r14
0x14000bc86  mov     rbp, rax
0x14000bc89  mov     [rdx+8], r14
0x14000bc8d  xor     edx, edx; ChargeQuota
0x14000bc8f  call    cs:__imp_IoAllocateIrp
0x14000bc96  nop     dword ptr [rax+rax+00h]
0x14000bc9b  mov     [rbx], rax
0x14000bc9e  test    rax, rax
0x14000bca1  jz      short loc_14000BCF9
0x14000bca3  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14000bcaa  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000bcb1  nop     dword ptr [rax+rax+00h]
0x14000bcb6  test    rax, rax
0x14000bcb9  jz      short loc_14000BCE3
0x14000bcbb  mov     r9, rbp; struct CClfsLogCcb *
0x14000bcbe  mov     r8, rsi; struct CClfsLogFcbCommon *
0x14000bcc1  mov     rdx, rdi; struct _FILE_OBJECT *
0x14000bcc4  mov     rcx, rax; this
0x14000bcc7  call    ??0CClfsRequest@@QEAA@PEAU_FILE_OBJECT@@PEAVCClfsLogFcbCommon@@PEAVCClfsLogCcb@@@Z; CClfsRequest::CClfsRequest(_FILE_OBJECT *,CClfsLogFcbCommon *,CClfsLogCcb *)
0x14000bccc  mov     [rbx+8], rax
0x14000bcd0  test    rax, rax
0x14000bcd3  jz      short loc_14000BCE7
0x14000bcd5  xor     eax, eax
0x14000bcd7  add     rsp, 20h
0x14000bcdb  pop     r14
0x14000bcdd  pop     rdi
0x14000bcde  pop     rsi
0x14000bcdf  pop     rbp
0x14000bce0  pop     rbx
0x14000bce1  retn
0x14000bce3  mov     [rbx+8], r14
0x14000bce7  mov     rcx, [rbx]; Irp
0x14000bcea  call    cs:__imp_IoFreeIrp
0x14000bcf1  nop     dword ptr [rax+rax+00h]
0x14000bcf6  mov     [rbx], r14
0x14000bcf9  mov     eax, 0C000009Ah
0x14000bcfe  jmp     short loc_14000BCD7
```
