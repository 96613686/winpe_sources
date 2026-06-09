# CscPqpDestroyHandle

- ea: `0x14002cd0c`
- end: `0x14002cdb4`
- name: `CscPqpDestroyHandle`
- size: `168`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002cb18`
- `0x14004635c`
- `0x1400487a8`

## callees

- `0x14002cd0c`
- `0x140060870`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd57`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd57`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd90`
- `ntoskrnl!ZwClose` at `0x14002cd74`
- `ntoskrnl!ZwClose` at `0x14002cd74`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002cd43`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002cd43`

## pseudocode

```c
void __fastcall CscPqpDestroyHandle(__int64 *a1)
{
  __int64 v1; // rbx
  struct _PAGED_LOOKASIDE_LIST *v3; // rcx
  void *v4; // rdi
  void *v5; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = *(struct _PAGED_LOOKASIDE_LIST **)(v1 + 152);
    if ( v3 )
      CscPqpDestroyPagedLookasideList(v3);
    v4 = *(void **)(v1 + 96);
    if ( v4 )
    {
      ExDeleteResourceLite(*(PERESOURCE *)(v1 + 96));
      ExFreePoolWithTag(v4, 0x22407343u);
      *(_QWORD *)(v1 + 96) = 0;
    }
    v5 = *(void **)(v1 + 8);
    if ( v5 )
    {
      ZwClose(v5);
      *(_QWORD *)(v1 + 8) = 0;
    }
    ExFreePoolWithTag((PVOID)v1, 0x24407343u);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x14002cd0c  mov     [rsp+arg_0], rbx
0x14002cd11  mov     [rsp+arg_8], rsi
0x14002cd16  push    rdi
0x14002cd17  sub     rsp, 20h
0x14002cd1b  mov     rbx, [rcx]
0x14002cd1e  mov     rsi, rcx
0x14002cd21  test    rbx, rbx
0x14002cd24  jz      short loc_14002CDA3
0x14002cd26  mov     rcx, [rbx+98h]; P
0x14002cd2d  test    rcx, rcx
0x14002cd30  jz      short loc_14002CD37
0x14002cd32  call    CscPqpDestroyPagedLookasideList
0x14002cd37  mov     rdi, [rbx+60h]
0x14002cd3b  test    rdi, rdi
0x14002cd3e  jz      short loc_14002CD6B
0x14002cd40  mov     rcx, rdi; Resource
0x14002cd43  call    cs:__imp_ExDeleteResourceLite
0x14002cd4a  nop     dword ptr [rax+rax+00h]
0x14002cd4f  mov     edx, 22407343h; Tag
0x14002cd54  mov     rcx, rdi; P
0x14002cd57  call    cs:__imp_ExFreePoolWithTag
0x14002cd5e  nop     dword ptr [rax+rax+00h]
0x14002cd63  mov     qword ptr [rbx+60h], 0
0x14002cd6b  mov     rcx, [rbx+8]; Handle
0x14002cd6f  test    rcx, rcx
0x14002cd72  jz      short loc_14002CD88
0x14002cd74  call    cs:__imp_ZwClose
0x14002cd7b  nop     dword ptr [rax+rax+00h]
0x14002cd80  mov     qword ptr [rbx+8], 0
0x14002cd88  mov     edx, 24407343h; Tag
0x14002cd8d  mov     rcx, rbx; P
0x14002cd90  call    cs:__imp_ExFreePoolWithTag
0x14002cd97  nop     dword ptr [rax+rax+00h]
0x14002cd9c  mov     qword ptr [rsi], 0
0x14002cda3  mov     rbx, [rsp+28h+arg_0]
0x14002cda8  mov     rsi, [rsp+28h+arg_8]
0x14002cdad  add     rsp, 20h
0x14002cdb1  pop     rdi
0x14002cdb2  retn
```
