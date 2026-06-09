# UninitialializeSubRdrDialectTable

- ea: `0x1400432d8`
- end: `0x140043346`
- name: `UninitialializeSubRdrDialectTable`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14007f05c`
- `0x140080ce4`

## callees

- `0x1400432d8`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140043333`
- `ntoskrnl!ExDeleteResourceLite` at `0x140043333`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400432f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043315`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400432f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043315`

## pseudocode

```c
NTSTATUS __fastcall UninitialializeSubRdrDialectTable(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  NTSTATUS result; // eax

  v2 = *(void **)(a1 + 2216);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0x6D536C44u);
    v3 = *(void **)(a1 + 2224);
    *(_QWORD *)(a1 + 2216) = 0;
    ExFreePoolWithTag(v3, 0x6D536C44u);
    *(_QWORD *)(a1 + 2224) = 0;
    return ExDeleteResourceLite((PERESOURCE)(a1 + 2232));
  }
  return result;
}

```

## disassembly

```asm
0x1400432d8  push    rbx
0x1400432da  sub     rsp, 20h
0x1400432de  mov     rbx, rcx
0x1400432e1  mov     rcx, [rcx+8A8h]; P
0x1400432e8  test    rcx, rcx
0x1400432eb  jz      short loc_14004333F
0x1400432ed  mov     edx, 6D536C44h; Tag
0x1400432f2  call    cs:__imp_ExFreePoolWithTag
0x1400432f9  nop     dword ptr [rax+rax+00h]
0x1400432fe  mov     rcx, [rbx+8B0h]; P
0x140043305  mov     edx, 6D536C44h; Tag
0x14004330a  mov     qword ptr [rbx+8A8h], 0
0x140043315  call    cs:__imp_ExFreePoolWithTag
0x14004331c  nop     dword ptr [rax+rax+00h]
0x140043321  lea     rcx, [rbx+8B8h]; Resource
0x140043328  mov     qword ptr [rbx+8B0h], 0
0x140043333  call    cs:__imp_ExDeleteResourceLite
0x14004333a  nop     dword ptr [rax+rax+00h]
0x14004333f  add     rsp, 20h
0x140043343  pop     rbx
0x140043344  retn
```
