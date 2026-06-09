# Copy<TaskAllocator>(uchar const *,unsigned __int64)

- ea: `0x18000503c`
- end: `0x180005083`
- name: `??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z`
- size: `71`
- prototype: `void *__fastcall(void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800067cc`
- `0x180007980`
- `0x18000e780`
- `0x18000e950`

## callees

- `0x18000503c`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005054`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000503c  mov     [rsp+arg_0], rbx
0x180005041  mov     [rsp+arg_8], rsi
0x180005046  push    rdi
0x180005047  sub     rsp, 20h
0x18000504b  mov     rsi, rcx
0x18000504e  mov     rdi, rdx
0x180005051  mov     rcx, rdx; cb
0x180005054  call    cs:__imp_CoTaskMemAlloc
0x18000505a  mov     rbx, rax
0x18000505d  test    rax, rax
0x180005060  jz      short loc_180005070
0x180005062  mov     r8, rdi; Size
0x180005065  mov     rdx, rsi; Src
0x180005068  mov     rcx, rax; void *
0x18000506b  call    memcpy_0
0x180005070  mov     rsi, [rsp+28h+arg_8]
0x180005075  mov     rax, rbx
0x180005078  mov     rbx, [rsp+28h+arg_0]
0x18000507d  add     rsp, 20h
0x180005081  pop     rdi
0x180005082  retn
```
