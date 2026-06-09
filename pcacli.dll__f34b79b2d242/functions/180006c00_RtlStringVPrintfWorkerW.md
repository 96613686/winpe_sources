# RtlStringVPrintfWorkerW

- ea: `0x180006c00`
- end: `0x180006c6f`
- name: `RtlStringVPrintfWorkerW`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f00`
- `0x18000908c`

## callees

- `0x180006c00`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006c27`
- `msvcrt!_vsnwprintf` at `0x180006c27`

## pseudocode

```c
__int64 __fastcall RtlStringVPrintfWorkerW(
        wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        const wchar_t *a4,
        va_list Args)
{
  unsigned __int64 v5; // rbx
  int v8; // eax
  unsigned int v9; // ecx
  __int64 result; // rax

  v5 = a2 - 1;
  v8 = _vsnwprintf(a1, a2 - 1, a4, Args);
  if ( v8 < 0 || v8 > v5 )
  {
    a1[v5] = 0;
    v9 = -2147483643;
  }
  else
  {
    v9 = 0;
    if ( v8 == v5 )
      a1[v5] = 0;
    else
      v5 = v8;
  }
  result = v9;
  if ( a3 )
    *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x180006c00  mov     [rsp+arg_0], rbx
0x180006c05  mov     [rsp+arg_8], rsi
0x180006c0a  push    rdi
0x180006c0b  sub     rsp, 20h
0x180006c0f  mov     rax, r9
0x180006c12  lea     rbx, [rdx-1]
0x180006c16  mov     r9, [rsp+28h+Args]; Args
0x180006c1b  mov     rdi, r8
0x180006c1e  mov     r8, rax; Format
0x180006c21  mov     rdx, rbx; BufferCount
0x180006c24  mov     rsi, rcx
0x180006c27  call    cs:__imp__vsnwprintf
0x180006c2d  test    eax, eax
0x180006c2f  js      short loc_180006C5C
0x180006c31  cdqe
0x180006c33  cmp     rax, rbx
0x180006c36  ja      short loc_180006C5C
0x180006c38  xor     ecx, ecx
0x180006c3a  cmp     rax, rbx
0x180006c3d  jz      short loc_180006C69
0x180006c3f  mov     rbx, rax
0x180006c42  mov     eax, ecx
0x180006c44  test    rdi, rdi
0x180006c47  jz      short loc_180006C4C
0x180006c49  mov     [rdi], rbx
0x180006c4c  mov     rbx, [rsp+28h+arg_0]
0x180006c51  mov     rsi, [rsp+28h+arg_8]
0x180006c56  add     rsp, 20h
0x180006c5a  pop     rdi
0x180006c5b  retn
0x180006c5c  xor     ecx, ecx
0x180006c5e  mov     [rsi+rbx*2], cx
0x180006c62  mov     ecx, 80000005h
0x180006c67  jmp     short loc_180006C42
0x180006c69  mov     [rsi+rbx*2], cx
0x180006c6d  jmp     short loc_180006C42
```
