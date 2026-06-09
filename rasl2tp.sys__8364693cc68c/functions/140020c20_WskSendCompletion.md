# WskSendCompletion

- ea: `0x140020c20`
- end: `0x140020d0a`
- name: `WskSendCompletion`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004830`
- `0x140020c20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020c7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020c7f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020ca0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140020ca0`
- `ntoskrnl!IoFreeIrp` at `0x140020cd0`
- `ntoskrnl!IoFreeIrp` at `0x140020cd0`
- `ntoskrnl!IoFreeMdl` at `0x140020ce8`
- `ntoskrnl!IoFreeMdl` at `0x140020ce8`

## pseudocode

```c
__int64 __fastcall WskSendCompletion(__int64 a1, IRP *a2, struct _NPAGED_LOOKASIDE_LIST **a3)
{
  struct _MDL *v5; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v6; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rsi

  if ( a3 )
  {
    ((void (__fastcall *)(ULONGLONG, struct _NPAGED_LOOKASIDE_LIST *, struct _NPAGED_LOOKASIDE_LIST *, _QWORD, struct _NPAGED_LOOKASIDE_LIST *, NTSTATUS))(*a3)->L.ListEntry.Flink)(
      (*a3)->L.ListHead.Region,
      a3[1],
      a3[2],
      *((unsigned int *)a3 + 6),
      a3[4],
      a2->IoStatus.Status);
    v5 = (struct _MDL *)a3[7];
    if ( v5 )
      IoFreeMdl(v5);
    v6 = a3[5];
    if ( v6 )
    {
      ExFreePoolWithTag(v6, 0);
      a3[5] = 0;
    }
    v7 = *a3;
    ExFreeToNPagedLookasideList(*a3 + 2, a3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v7[4], 0xFFFFFFFF) == 1 )
      ((void (__fastcall *)(struct _NPAGED_LOOKASIDE_LIST *))v7[4].L.ListHead.Region)(v7);
  }
  if ( a2 )
    IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140020c20  push    rbx
0x140020c22  sub     rsp, 40h
0x140020c26  mov     [rsp+48h+arg_10], rdi
0x140020c2b  mov     rdi, r8
0x140020c2e  mov     rbx, rdx
0x140020c31  test    r8, r8
0x140020c34  jz      loc_140020CC3
0x140020c3a  mov     rcx, [r8]
0x140020c3d  mov     edx, [rdx+30h]
0x140020c40  mov     r9d, [r8+18h]
0x140020c44  mov     [rsp+48h+var_20], edx
0x140020c48  mov     rdx, [r8+20h]
0x140020c4c  mov     rax, [rcx+40h]
0x140020c50  mov     rcx, [rcx+8]
0x140020c54  mov     r8, [r8+10h]
0x140020c58  mov     [rsp+48h+var_28], rdx
0x140020c5d  mov     rdx, [rdi+8]
0x140020c61  mov     [rsp+48h+arg_0], rsi
0x140020c66  call    _guard_dispatch_icall
0x140020c6b  mov     rcx, [rdi+38h]; Mdl
0x140020c6f  test    rcx, rcx
0x140020c72  jnz     short loc_140020CE8
0x140020c74  mov     rcx, [rdi+28h]; P
0x140020c78  test    rcx, rcx
0x140020c7b  jz      short loc_140020C93
0x140020c7d  xor     edx, edx; Tag
0x140020c7f  call    cs:__imp_ExFreePoolWithTag
0x140020c86  nop     dword ptr [rax+rax+00h]
0x140020c8b  mov     qword ptr [rdi+28h], 0
0x140020c93  mov     rsi, [rdi]
0x140020c96  mov     rdx, rdi; Entry
0x140020c99  lea     rcx, [rsi+100h]; Lookaside
0x140020ca0  call    cs:__imp_ExFreeToNPagedLookasideList
0x140020ca7  nop     dword ptr [rax+rax+00h]
0x140020cac  mov     eax, 0FFFFFFFFh
0x140020cb1  lock xadd [rsi+200h], eax
0x140020cb9  cmp     eax, 1
0x140020cbc  jz      short loc_140020CF9
0x140020cbe  mov     rsi, [rsp+48h+arg_0]
0x140020cc3  mov     rdi, [rsp+48h+arg_10]
0x140020cc8  test    rbx, rbx
0x140020ccb  jz      short loc_140020CDC
0x140020ccd  mov     rcx, rbx; Irp
0x140020cd0  call    cs:__imp_IoFreeIrp
0x140020cd7  nop     dword ptr [rax+rax+00h]
0x140020cdc  mov     eax, 0C0000016h
0x140020ce1  add     rsp, 40h
0x140020ce5  pop     rbx
0x140020ce6  retn
0x140020ce8  call    cs:__imp_IoFreeMdl
0x140020cef  nop     dword ptr [rax+rax+00h]
0x140020cf4  jmp     loc_140020C74
0x140020cf9  mov     rax, [rsi+208h]
0x140020d00  mov     rcx, rsi
0x140020d03  call    _guard_dispatch_icall
0x140020d08  jmp     short loc_140020CBE
```
