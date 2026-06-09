# wil::details::out_param_t<wistd::unique_ptr<uchar,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::process_heap_deleter>>(void)

- ea: `0x18000f4fc`
- end: `0x18000f541`
- name: `??1?$out_param_t@V?$unique_ptr@EUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(__int64)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800107e8`
- `0x180040350`
- `0x180057799`
- `0x1800577cf`
- `0x1800577f3`
- `0x180057a77`
- `0x180057baf`
- `0x180057c87`
- `0x18005841a`
- `0x18005842c`
- `0x180058699`
- `0x180058732`

## callees

- `0x18000f4fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f51a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f51a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f52e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f52e`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::process_heap_deleter>>(
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
0x18000f4fc  push    rbx
0x18000f4fe  sub     rsp, 20h
0x18000f502  cmp     byte ptr [rcx+10h], 0
0x18000f506  jz      short loc_18000F53A
0x18000f508  mov     rdx, [rcx]
0x18000f50b  mov     rax, [rcx+8]
0x18000f50f  mov     rbx, [rdx]
0x18000f512  mov     [rdx], rax
0x18000f515  test    rbx, rbx
0x18000f518  jz      short loc_18000F53A
0x18000f51a  call    cs:__imp_GetProcessHeap
0x18000f521  nop     dword ptr [rax+rax+00h]
0x18000f526  mov     r8, rbx; lpMem
0x18000f529  xor     edx, edx; dwFlags
0x18000f52b  mov     rcx, rax; hHeap
0x18000f52e  call    cs:__imp_HeapFree
0x18000f535  nop     dword ptr [rax+rax+00h]
0x18000f53a  add     rsp, 20h
0x18000f53e  pop     rbx
0x18000f53f  retn
```
