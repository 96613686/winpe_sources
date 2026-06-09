# CEventLogResult::copyString(ushort const *)

- ea: `0x180025f50`
- end: `0x180025fb2`
- name: `?copyString@CEventLogResult@@CAPEAGPEBG@Z`
- size: `98`
- prototype: `unsigned __int16 *__fastcall(wchar_t *Source)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180025bb0`
- `0x180025fb8`
- `0x180026764`
- `0x1800268b0`
- `0x180026a70`
- `0x180026bb0`

## callees

- `0x18000342c`
- `0x180025f50`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180025f9c`
- `msvcrt!wcscpy_s` at `0x180025f9c`

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
0x180025f50  push    rbx
0x180025f52  push    rbp
0x180025f53  push    rsi
0x180025f54  push    rdi
0x180025f55  sub     rsp, 28h
0x180025f59  xor     ebp, ebp
0x180025f5b  mov     rbx, rcx
0x180025f5e  test    rcx, rcx
0x180025f61  jz      short loc_180025FA7
0x180025f63  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180025f67  mov     rax, rcx
0x180025f6a  inc     rax
0x180025f6d  cmp     [rbx+rax*2], bp
0x180025f71  jnz     short loc_180025F6A
0x180025f73  lea     rsi, [rax+1]
0x180025f77  mov     eax, 2
0x180025f7c  mul     rsi
0x180025f7f  cmovb   rax, rcx
0x180025f83  mov     rcx, rax; Size
0x180025f86  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180025f8b  mov     rdi, rax
0x180025f8e  test    rax, rax
0x180025f91  jz      short loc_180025FA7
0x180025f93  mov     r8, rbx; Source
0x180025f96  mov     rdx, rsi; SizeInWords
0x180025f99  mov     rcx, rax; Destination
0x180025f9c  call    cs:__imp_wcscpy_s
0x180025fa2  mov     rax, rdi
0x180025fa5  jmp     short loc_180025FA9
0x180025fa7  xor     eax, eax
0x180025fa9  add     rsp, 28h
0x180025fad  pop     rdi
0x180025fae  pop     rsi
0x180025faf  pop     rbp
0x180025fb0  pop     rbx
0x180025fb1  retn
```
