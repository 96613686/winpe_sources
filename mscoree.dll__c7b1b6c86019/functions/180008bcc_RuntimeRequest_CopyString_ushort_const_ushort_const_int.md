# RuntimeRequest::CopyString(ushort const * *,ushort const *,int)

- ea: `0x180008bcc`
- end: `0x180008c5a`
- name: `?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z`
- size: `142`
- prototype: `int(RuntimeRequest *__hidden this, const unsigned __int16 **, const unsigned __int16 *, int)`
- caller_count: `9`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008484`
- `0x18000883c`
- `0x180009af4`
- `0x180029b70`
- `0x18002a8b4`
- `0x18002c01c`
- `0x18002c1d0`
- `0x18002ca2c`
- `0x18002dfb4`

## callees

- `0x180003740`
- `0x180003840`
- `0x180008bcc`
- `0x18000c1a8`

## pseudocode

```c
__int64 __fastcall RuntimeRequest::CopyString(RuntimeRequest *this, unsigned __int16 **a2, wchar_t *a3, int a4)
{
  __int64 v7; // rax
  unsigned __int64 v8; // rsi
  unsigned __int128 v10; // rax
  unsigned __int16 *v11; // rax

  if ( *a2 )
  {
    operator delete(*a2);
    *a2 = 0;
  }
  if ( a4 && a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = v7 + 1;
    if ( v7 == -1 )
      return 2148734230LL;
    v10 = v8 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v8, 2u) )
      *(_QWORD *)&v10 = -1;
    v11 = (unsigned __int16 *)operator new(v10, *((const struct NoThrow **)&v10 + 1));
    *a2 = v11;
    if ( !v11 )
      return 2147942414LL;
    wcscpy_s(v11, v8, a3);
  }
  else
  {
    *a2 = a3;
  }
  return 0;
}

```

## disassembly

```asm
0x180008bcc  push    rbx
0x180008bce  push    rbp
0x180008bcf  push    rsi
0x180008bd0  push    rdi
0x180008bd1  sub     rsp, 28h
0x180008bd5  mov     rcx, [rdx]; void *
0x180008bd8  xor     ebp, ebp
0x180008bda  mov     esi, r9d
0x180008bdd  mov     rbx, r8
0x180008be0  mov     rdi, rdx
0x180008be3  test    rcx, rcx
0x180008be6  jz      short loc_180008BF0
0x180008be8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008bed  mov     [rdi], rbp
0x180008bf0  test    esi, esi
0x180008bf2  jz      short loc_180008C4C
0x180008bf4  test    rbx, rbx
0x180008bf7  jz      short loc_180008C4C
0x180008bf9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008bfd  mov     rax, rcx
0x180008c00  inc     rax
0x180008c03  cmp     [rbx+rax*2], bp
0x180008c07  jnz     short loc_180008C00
0x180008c09  lea     rsi, [rax+1]
0x180008c0d  test    rsi, rsi
0x180008c10  jnz     short loc_180008C19
0x180008c12  mov     eax, 80131516h
0x180008c17  jmp     short loc_180008C51
0x180008c19  mov     eax, 2
0x180008c1e  mul     rsi
0x180008c21  cmovb   rax, rcx
0x180008c25  mov     rcx, rax; unsigned __int64
0x180008c28  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180008c2d  mov     [rdi], rax
0x180008c30  test    rax, rax
0x180008c33  jz      short loc_180008C45
0x180008c35  mov     r8, rbx; Source
0x180008c38  mov     rdx, rsi; SizeInWords
0x180008c3b  mov     rcx, rax; Destination
0x180008c3e  call    wcscpy_s
0x180008c43  jmp     short loc_180008C4F
0x180008c45  mov     eax, 8007000Eh
0x180008c4a  jmp     short loc_180008C51
0x180008c4c  mov     [rdi], rbx
0x180008c4f  xor     eax, eax
0x180008c51  add     rsp, 28h
0x180008c55  pop     rdi
0x180008c56  pop     rsi
0x180008c57  pop     rbp
0x180008c58  pop     rbx
0x180008c59  retn
```
