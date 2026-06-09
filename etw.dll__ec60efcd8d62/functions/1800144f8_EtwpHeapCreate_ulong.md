# EtwpHeapCreate(ulong)

- ea: `0x1800144f8`
- end: `0x18001454f`
- name: `?EtwpHeapCreate@@YAPEAU_TRACE_STREAM_HEAP@@K@Z`
- size: `87`
- prototype: `struct _TRACE_STREAM_HEAP *__fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f90c`
- `0x18000ff6c`
- `0x180012674`

## callees

- `0x180001eb2`
- `0x180001ff0`
- `0x1800144f8`

## pseudocode

```c
struct _TRACE_STREAM_HEAP *__fastcall EtwpHeapCreate(int a1)
{
  unsigned __int64 v2; // rsi
  _DWORD *v3; // rax
  _DWORD *v4; // rbx

  v2 = (unsigned int)(8 * a1 + 8);
  v3 = operator new(v2, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( !v3 )
    return 0;
  memset_0(v3, 0, (unsigned int)v2);
  v4[1] = a1;
  return (struct _TRACE_STREAM_HEAP *)v4;
}

```

## disassembly

```asm
0x1800144f8  mov     [rsp+arg_0], rbx
0x1800144fd  mov     [rsp+arg_8], rsi
0x180014502  push    rdi
0x180014503  sub     rsp, 20h
0x180014507  lea     eax, ds:8[rcx*8]
0x18001450e  mov     edi, ecx
0x180014510  mov     ecx, eax; unsigned __int64
0x180014512  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014519  mov     esi, eax
0x18001451b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014520  mov     rbx, rax
0x180014523  test    rax, rax
0x180014526  jz      short loc_18001453A
0x180014528  mov     r8d, esi; Size
0x18001452b  xor     edx, edx; Val
0x18001452d  mov     rcx, rax; void *
0x180014530  call    memset_0
0x180014535  mov     [rbx+4], edi
0x180014538  jmp     short loc_18001453C
0x18001453a  xor     ebx, ebx
0x18001453c  mov     rsi, [rsp+28h+arg_8]
0x180014541  mov     rax, rbx
0x180014544  mov     rbx, [rsp+28h+arg_0]
0x180014549  add     rsp, 20h
0x18001454d  pop     rdi
0x18001454e  retn
```
