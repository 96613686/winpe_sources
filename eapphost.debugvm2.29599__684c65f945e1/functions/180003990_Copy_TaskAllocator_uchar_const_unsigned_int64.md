# Copy<TaskAllocator>(uchar const *,unsigned __int64)

- ea: `0x180003990`
- end: `0x1800039d7`
- name: `??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z`
- size: `71`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003cec`
- `0x1800052f4`
- `0x180006c30`
- `0x180006db0`

## callees

- `0x180003990`
- `0x180033d78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800039a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800039a8`

## pseudocode

```c
void *__fastcall Copy<TaskAllocator>(void *Src, size_t Size)
{
  void *v4; // rax
  void *v5; // rbx

  v4 = CoTaskMemAlloc(Size);
  v5 = v4;
  if ( v4 )
    memcpy_0(v4, Src, Size);
  return v5;
}

```

## disassembly

```asm
0x180003990  mov     [rsp+arg_0], rbx
0x180003995  mov     [rsp+arg_8], rsi
0x18000399a  push    rdi
0x18000399b  sub     rsp, 20h
0x18000399f  mov     rsi, rcx
0x1800039a2  mov     rdi, rdx
0x1800039a5  mov     rcx, rdx; cb
0x1800039a8  call    cs:__imp_CoTaskMemAlloc
0x1800039ae  mov     rbx, rax
0x1800039b1  test    rax, rax
0x1800039b4  jz      short loc_1800039C4
0x1800039b6  mov     r8, rdi; Size
0x1800039b9  mov     rdx, rsi; Src
0x1800039bc  mov     rcx, rax; void *
0x1800039bf  call    memcpy_0
0x1800039c4  mov     rsi, [rsp+28h+arg_8]
0x1800039c9  mov     rax, rbx
0x1800039cc  mov     rbx, [rsp+28h+arg_0]
0x1800039d1  add     rsp, 20h
0x1800039d5  pop     rdi
0x1800039d6  retn
```
