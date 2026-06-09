# CEventLogResult::copyString(ushort const *)

- ea: `0x180028b0c`
- end: `0x180028b6e`
- name: `?copyString@CEventLogResult@@CAPEAGPEBG@Z`
- size: `98`
- prototype: `unsigned __int16 *__fastcall(wchar_t *Source)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18002875c`
- `0x180028b74`
- `0x18002931c`
- `0x180029468`
- `0x18002962c`
- `0x18002976c`

## callees

- `0x18000e4e0`
- `0x180028b0c`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180028b58`
- `msvcrt!wcscpy_s` at `0x180028b58`

## pseudocode

```c
unsigned __int16 *__fastcall CEventLogResult::copyString(wchar_t *Source)
{
  __int64 v2; // rax
  rsize_t v3; // rsi
  unsigned __int128 v4; // rax
  unsigned __int64 v5; // kr00_8
  wchar_t *v6; // rax
  wchar_t *v7; // rdi

  if ( !Source )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( Source[v2] );
  v3 = v2 + 1;
  v5 = v2 + 1;
  v4 = (unsigned __int64)(v2 + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v5, 2u) )
    *(_QWORD *)&v4 = -1;
  v6 = (wchar_t *)operator new[](v4, *((const struct std::nothrow_t **)&v4 + 1));
  v7 = v6;
  if ( !v6 )
    return 0;
  wcscpy_s(v6, v3, Source);
  return v7;
}

```

## disassembly

```asm
0x180028b0c  push    rbx
0x180028b0e  push    rbp
0x180028b0f  push    rsi
0x180028b10  push    rdi
0x180028b11  sub     rsp, 28h
0x180028b15  xor     ebp, ebp
0x180028b17  mov     rbx, rcx
0x180028b1a  test    rcx, rcx
0x180028b1d  jz      short loc_180028B63
0x180028b1f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180028b23  mov     rax, rcx
0x180028b26  inc     rax
0x180028b29  cmp     [rbx+rax*2], bp
0x180028b2d  jnz     short loc_180028B26
0x180028b2f  lea     rsi, [rax+1]
0x180028b33  mov     eax, 2
0x180028b38  mul     rsi
0x180028b3b  cmovb   rax, rcx
0x180028b3f  mov     rcx, rax; Size
0x180028b42  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180028b47  mov     rdi, rax
0x180028b4a  test    rax, rax
0x180028b4d  jz      short loc_180028B63
0x180028b4f  mov     r8, rbx; Source
0x180028b52  mov     rdx, rsi; SizeInWords
0x180028b55  mov     rcx, rax; Destination
0x180028b58  call    cs:__imp_wcscpy_s
0x180028b5e  mov     rax, rdi
0x180028b61  jmp     short loc_180028B65
0x180028b63  xor     eax, eax
0x180028b65  add     rsp, 28h
0x180028b69  pop     rdi
0x180028b6a  pop     rsi
0x180028b6b  pop     rbp
0x180028b6c  pop     rbx
0x180028b6d  retn
```
