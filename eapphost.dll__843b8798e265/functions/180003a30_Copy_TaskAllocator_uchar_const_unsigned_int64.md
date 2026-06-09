# Copy<TaskAllocator>(uchar const *,unsigned __int64)

- ea: `0x180003a30`
- end: `0x180003a7e`
- name: `??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003dc8`
- `0x180005448`
- `0x180006ec0`
- `0x180007040`

## callees

- `0x180003a30`
- `0x180035138`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003a48`

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
0x180003a30  mov     [rsp+arg_0], rbx
0x180003a35  mov     [rsp+arg_8], rsi
0x180003a3a  push    rdi
0x180003a3b  sub     rsp, 20h
0x180003a3f  mov     rsi, rcx
0x180003a42  mov     rdi, rdx
0x180003a45  mov     rcx, rdx; cb
0x180003a48  call    cs:__imp_CoTaskMemAlloc
0x180003a4f  nop     dword ptr [rax+rax+00h]
0x180003a54  mov     rbx, rax
0x180003a57  test    rax, rax
0x180003a5a  jz      short loc_180003A6A
0x180003a5c  mov     r8, rdi; Size
0x180003a5f  mov     rdx, rsi; Src
0x180003a62  mov     rcx, rax; void *
0x180003a65  call    memcpy_0
0x180003a6a  mov     rsi, [rsp+28h+arg_8]
0x180003a6f  mov     rax, rbx
0x180003a72  mov     rbx, [rsp+28h+arg_0]
0x180003a77  add     rsp, 20h
0x180003a7b  pop     rdi
0x180003a7c  retn
```
