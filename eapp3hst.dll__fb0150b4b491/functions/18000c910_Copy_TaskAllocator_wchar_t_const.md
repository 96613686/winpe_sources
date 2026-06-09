# Copy<TaskAllocator>(wchar_t const *)

- ea: `0x18000c910`
- end: `0x18000c95e`
- name: `??$Copy@VTaskAllocator@@@@YAPEA_WPEB_W@Z`
- size: `78`
- prototype: `void *__fastcall(_WORD *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000d200`
- `0x18000df60`

## callees

- `0x18000c910`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c936`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall Copy<TaskAllocator>(_WORD *Src)
{
  __int64 v1; // rax
  SIZE_T v3; // rsi
  void *v4; // rax
  void *v5; // rbx

  v1 = -1;
  do
    ++v1;
  while ( Src[v1] );
  v3 = 2 * v1 + 2;
  v4 = CoTaskMemAlloc(v3);
  v5 = v4;
  if ( v4 )
    memcpy_0(v4, Src, v3);
  return v5;
}

```

## disassembly

```asm
0x18000c910  push    rbx
0x18000c912  push    rbp
0x18000c913  push    rsi
0x18000c914  push    rdi
0x18000c915  sub     rsp, 28h
0x18000c919  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c91d  mov     rdi, rcx
0x18000c920  xor     ebp, ebp
0x18000c922  inc     rax
0x18000c925  cmp     [rcx+rax*2], bp
0x18000c929  jnz     short loc_18000C922
0x18000c92b  lea     rsi, ds:2[rax*2]
0x18000c933  mov     rcx, rsi; cb
0x18000c936  call    cs:__imp_CoTaskMemAlloc
0x18000c93c  mov     rbx, rax
0x18000c93f  test    rax, rax
0x18000c942  jz      short loc_18000C952
0x18000c944  mov     r8, rsi; Size
0x18000c947  mov     rdx, rdi; Src
0x18000c94a  mov     rcx, rax; void *
0x18000c94d  call    memcpy_0
0x18000c952  mov     rax, rbx
0x18000c955  add     rsp, 28h
0x18000c959  pop     rdi
0x18000c95a  pop     rsi
0x18000c95b  pop     rbp
0x18000c95c  pop     rbx
0x18000c95d  retn
```
