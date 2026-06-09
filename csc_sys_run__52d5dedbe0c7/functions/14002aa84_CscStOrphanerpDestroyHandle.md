# CscStOrphanerpDestroyHandle

- ea: `0x14002aa84`
- end: `0x14002ab3c`
- name: `CscStOrphanerpDestroyHandle`
- size: `184`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140017f10`
- `0x14002a798`
- `0x14002a9b8`

## callees

- `0x14002aa84`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002aac2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ab18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002aac2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ab18`
- `ntoskrnl!ZwClose` at `0x14002aadf`
- `ntoskrnl!ZwClose` at `0x14002aafc`
- `ntoskrnl!ZwClose` at `0x14002aadf`
- `ntoskrnl!ZwClose` at `0x14002aafc`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002aaae`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002aaae`

## pseudocode

```c
void __fastcall CscStOrphanerpDestroyHandle(__int64 *a1)
{
  __int64 v1; // rbx
  void *v3; // rdi
  void *v4; // rcx
  void *v5; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = *(void **)(v1 + 8);
    if ( v3 )
    {
      ExDeleteResourceLite(*(PERESOURCE *)(v1 + 8));
      ExFreePoolWithTag(v3, 0x22407343u);
      *(_QWORD *)(v1 + 8) = 0;
    }
    v4 = *(void **)(v1 + 16);
    if ( v4 )
    {
      ZwClose(v4);
      *(_QWORD *)(v1 + 16) = 0;
    }
    v5 = *(void **)(v1 + 24);
    if ( v5 )
    {
      ZwClose(v5);
      *(_QWORD *)(v1 + 24) = 0;
    }
    ExFreePoolWithTag((PVOID)v1, 0x28407343u);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x14002aa84  mov     [rsp+arg_0], rbx
0x14002aa89  mov     [rsp+arg_8], rsi
0x14002aa8e  push    rdi
0x14002aa8f  sub     rsp, 20h
0x14002aa93  mov     rbx, [rcx]
0x14002aa96  mov     rsi, rcx
0x14002aa99  test    rbx, rbx
0x14002aa9c  jz      loc_14002AB2B
0x14002aaa2  mov     rdi, [rbx+8]
0x14002aaa6  test    rdi, rdi
0x14002aaa9  jz      short loc_14002AAD6
0x14002aaab  mov     rcx, rdi; Resource
0x14002aaae  call    cs:__imp_ExDeleteResourceLite
0x14002aab5  nop     dword ptr [rax+rax+00h]
0x14002aaba  mov     edx, 22407343h; Tag
0x14002aabf  mov     rcx, rdi; P
0x14002aac2  call    cs:__imp_ExFreePoolWithTag
0x14002aac9  nop     dword ptr [rax+rax+00h]
0x14002aace  mov     qword ptr [rbx+8], 0
0x14002aad6  mov     rcx, [rbx+10h]; Handle
0x14002aada  test    rcx, rcx
0x14002aadd  jz      short loc_14002AAF3
0x14002aadf  call    cs:__imp_ZwClose
0x14002aae6  nop     dword ptr [rax+rax+00h]
0x14002aaeb  mov     qword ptr [rbx+10h], 0
0x14002aaf3  mov     rcx, [rbx+18h]; Handle
0x14002aaf7  test    rcx, rcx
0x14002aafa  jz      short loc_14002AB10
0x14002aafc  call    cs:__imp_ZwClose
0x14002ab03  nop     dword ptr [rax+rax+00h]
0x14002ab08  mov     qword ptr [rbx+18h], 0
0x14002ab10  mov     edx, 28407343h; Tag
0x14002ab15  mov     rcx, rbx; P
0x14002ab18  call    cs:__imp_ExFreePoolWithTag
0x14002ab1f  nop     dword ptr [rax+rax+00h]
0x14002ab24  mov     qword ptr [rsi], 0
0x14002ab2b  mov     rbx, [rsp+28h+arg_0]
0x14002ab30  mov     rsi, [rsp+28h+arg_8]
0x14002ab35  add     rsp, 20h
0x14002ab39  pop     rdi
0x14002ab3a  retn
```
