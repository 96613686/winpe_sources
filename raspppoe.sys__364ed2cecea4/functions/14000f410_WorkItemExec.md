# WorkItemExec

- ea: `0x14000f410`
- end: `0x14000f48c`
- name: `WorkItemExec`
- size: `124`
- prototype: `NDIS_IO_WORKITEM_FUNCTION`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140006b80`
- `0x14000f410`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f46f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000f46f`
- `NDIS!NdisFreeIoWorkItem` at `0x14000f45c`
- `NDIS!NdisFreeIoWorkItem` at `0x14000f45c`

## pseudocode

```c
void __fastcall WorkItemExec(char *WorkItemContext, NDIS_HANDLE NdisIoWorkItemHandle)
{
  void (__fastcall *v2)(char *, _QWORD); // rax
  void (__fastcall *v4)(char *, _QWORD); // rax

  v2 = (void (__fastcall *)(char *, _QWORD))*((_QWORD *)WorkItemContext + 6);
  *(_DWORD *)WorkItemContext = 2;
  if ( v2 )
    v2(WorkItemContext + 16, *((unsigned int *)WorkItemContext + 1));
  v4 = (void (__fastcall *)(char *, _QWORD))*((_QWORD *)WorkItemContext + 7);
  *(_DWORD *)WorkItemContext = 3;
  if ( v4 )
    v4(WorkItemContext + 16, *((unsigned int *)WorkItemContext + 1));
  NdisFreeIoWorkItem(*((NDIS_HANDLE *)WorkItemContext + 8));
  ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)WorkItemContext + 1), WorkItemContext);
}

```

## disassembly

```asm
0x14000f410  mov     [rsp+arg_0], rbx
0x14000f415  mov     [rsp+arg_8], rsi
0x14000f41a  push    rdi
0x14000f41b  sub     rsp, 20h
0x14000f41f  mov     rax, [rcx+30h]
0x14000f423  mov     rbx, rcx
0x14000f426  mov     dword ptr [rcx], 2
0x14000f42c  test    rax, rax
0x14000f42f  jz      short loc_14000F43D
0x14000f431  mov     edx, [rcx+4]
0x14000f434  add     rcx, 10h
0x14000f438  call    _guard_dispatch_icall
0x14000f43d  mov     rax, [rbx+38h]
0x14000f441  mov     dword ptr [rbx], 3
0x14000f447  test    rax, rax
0x14000f44a  jz      short loc_14000F458
0x14000f44c  mov     edx, [rbx+4]
0x14000f44f  lea     rcx, [rbx+10h]
0x14000f453  call    _guard_dispatch_icall
0x14000f458  mov     rcx, [rbx+40h]; NdisIoWorkItemHandle
0x14000f45c  call    cs:__imp_NdisFreeIoWorkItem
0x14000f463  nop     dword ptr [rax+rax+00h]
0x14000f468  mov     rcx, [rbx+8]; Lookaside
0x14000f46c  mov     rdx, rbx; Entry
0x14000f46f  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000f476  nop     dword ptr [rax+rax+00h]
0x14000f47b  mov     rbx, [rsp+28h+arg_0]
0x14000f480  mov     rsi, [rsp+28h+arg_8]
0x14000f485  add     rsp, 20h
0x14000f489  pop     rdi
0x14000f48a  retn
```
