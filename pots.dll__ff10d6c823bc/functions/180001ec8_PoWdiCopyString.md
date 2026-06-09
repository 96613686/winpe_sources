# PoWdiCopyString

- ea: `0x180001ec8`
- end: `0x180001f2a`
- name: `PoWdiCopyString`
- size: `98`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023a4`
- `0x180002530`

## callees

- `0x180001ec8`
- `0x1800048f6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ef4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001ef4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001f02`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001f02`

## pseudocode

```c
void *__fastcall PoWdiCopyString(_WORD *Src)
{
  void *v2; // rbx
  __int64 v3; // rax
  SIZE_T v4; // rsi
  HANDLE ProcessHeap; // rax
  void *v6; // rax

  if ( !Src )
    return 0;
  v3 = -1;
  do
    ++v3;
  while ( Src[v3] );
  v4 = 2 * v3 + 2;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 0, v4);
  v2 = v6;
  if ( v6 )
    memcpy_0(v6, Src, v4);
  return v2;
}

```

## disassembly

```asm
0x180001ec8  push    rbx
0x180001eca  push    rbp
0x180001ecb  push    rsi
0x180001ecc  push    rdi
0x180001ecd  sub     rsp, 28h
0x180001ed1  xor     ebp, ebp
0x180001ed3  mov     rdi, rcx
0x180001ed6  test    rcx, rcx
0x180001ed9  jnz     short loc_180001EDF
0x180001edb  mov     ebx, ebp
0x180001edd  jmp     short loc_180001F1E
0x180001edf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001ee3  inc     rax
0x180001ee6  cmp     [rcx+rax*2], bp
0x180001eea  jnz     short loc_180001EE3
0x180001eec  lea     rsi, ds:2[rax*2]
0x180001ef4  call    cs:__imp_GetProcessHeap
0x180001efa  mov     r8, rsi; dwBytes
0x180001efd  xor     edx, edx; dwFlags
0x180001eff  mov     rcx, rax; hHeap
0x180001f02  call    cs:__imp_HeapAlloc
0x180001f08  mov     rbx, rax
0x180001f0b  test    rax, rax
0x180001f0e  jz      short loc_180001F1E
0x180001f10  mov     r8, rsi; Size
0x180001f13  mov     rdx, rdi; Src
0x180001f16  mov     rcx, rax; void *
0x180001f19  call    memcpy_0
0x180001f1e  mov     rax, rbx
0x180001f21  add     rsp, 28h
0x180001f25  pop     rdi
0x180001f26  pop     rsi
0x180001f27  pop     rbp
0x180001f28  pop     rbx
0x180001f29  retn
```
