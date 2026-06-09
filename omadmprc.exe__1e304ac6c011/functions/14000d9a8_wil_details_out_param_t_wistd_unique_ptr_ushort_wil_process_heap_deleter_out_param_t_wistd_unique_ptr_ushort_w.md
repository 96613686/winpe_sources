# wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)

- ea: `0x14000d9a8`
- end: `0x14000d9ed`
- name: `??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140015c6d`
- `0x140015cb5`

## callees

- `0x14000d9a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d9c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d9c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d9da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d9da`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(
        __int64 a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
  }
}

```

## disassembly

```asm
0x14000d9a8  push    rbx
0x14000d9aa  sub     rsp, 20h
0x14000d9ae  cmp     byte ptr [rcx+10h], 0
0x14000d9b2  jz      short loc_14000D9E6
0x14000d9b4  mov     rdx, [rcx]
0x14000d9b7  mov     rax, [rcx+8]
0x14000d9bb  mov     rbx, [rdx]
0x14000d9be  mov     [rdx], rax
0x14000d9c1  test    rbx, rbx
0x14000d9c4  jz      short loc_14000D9E6
0x14000d9c6  call    cs:__imp_GetProcessHeap
0x14000d9cd  nop     dword ptr [rax+rax+00h]
0x14000d9d2  mov     r8, rbx; lpMem
0x14000d9d5  xor     edx, edx; dwFlags
0x14000d9d7  mov     rcx, rax; hHeap
0x14000d9da  call    cs:__imp_HeapFree
0x14000d9e1  nop     dword ptr [rax+rax+00h]
0x14000d9e6  add     rsp, 20h
0x14000d9ea  pop     rbx
0x14000d9eb  retn
```
