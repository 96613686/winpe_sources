# archive_names_from_file

- ea: `0x140005bbc`
- end: `0x140005d74`
- name: `archive_names_from_file`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400069a8`

## callees

- `0x140001b96`
- `0x140004b20`
- `0x140005390`
- `0x140005bbc`
- `0x140006ea4`
- `0x1400071a4`
- `0x140007298`
- `0x140007314`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005d41`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005d5c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005d41`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005d5c`
- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x140005c07`
- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x140005c07`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x140005be9`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x140005be9`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x140005c2f`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x140005c2f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005cfa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005d04`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005d0d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005cfa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005d04`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140005d0d`

## string_xrefs

- `0x140005d62`: `Unexpected end of filename list; directory expected after -C`
- `0x140005d2c`: `Can't open %s`
- `0x140005d4a`: `Couldn't open %s`

## pseudocode

```c
void __fastcall archive_names_from_file(__int64 a1, __int64 a2)
{
  int v2; // ebp
  _BYTE *v4; // rsi
  void *v6; // rax
  void *v7; // rdi
  FILE *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  _BYTE *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8

  v2 = *(_DWORD *)(a1 + 36);
  v4 = *(_BYTE **)(a1 + 16);
  *(_BYTE *)(a1 + 193) = 0;
  v6 = calloc(1u, 0x40u);
  v7 = v6;
  if ( !v6 )
    lafe_errc(1);
  *((_DWORD *)v6 + 14) = v2 & 0x100;
  *((_QWORD *)v6 + 5) = _o__strdup(v4);
  if ( *v4 != 45 || v4[1] )
    v8 = (FILE *)_o_fopen(v4, "r");
  else
    v8 = o___acrt_iob_func_0(0);
  *(_QWORD *)v7 = v8;
  if ( !v8 )
  {
    _o__errno(v10, v9, v11);
    lafe_errc(1);
  }
  *((_QWORD *)v7 + 6) = 0x2000;
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 3) = 0;
  while ( 1 )
  {
    v12 = (_BYTE *)lafe_line_reader_next(v7);
    v14 = (__int64)v12;
    if ( !v12 )
      break;
    if ( *(_BYTE *)(a1 + 193) )
    {
      if ( *v12 )
      {
        set_chdir(a1, v12, v13);
      }
      else
      {
        lafe_warnc(0, "Meaningless argument for -C: ''");
        *(_DWORD *)(a1 + 188) = 1;
      }
      *(_BYTE *)(a1 + 193) = 0;
    }
    else if ( (*(_DWORD *)(a1 + 36) & 0x100) != 0 || *v12 != 45 || v12[1] != 67 || v12[2] )
    {
      if ( *v12 != 47 )
        do_chdir(a1);
      write_hierarchy(a1, a2, v14);
    }
    else
    {
      *(_BYTE *)(a1 + 193) = 1;
    }
  }
  free(*((void **)v7 + 1));
  free(*((void **)v7 + 5));
  free(v7);
  if ( *(_BYTE *)(a1 + 193) )
  {
    _o__errno(v16, v15, v17);
    lafe_errc(1);
  }
}

```

## disassembly

```asm
0x140005bbc  push    rbx
0x140005bbe  push    rbp
0x140005bbf  push    rsi
0x140005bc0  push    rdi
0x140005bc1  push    r12
0x140005bc3  push    r14
0x140005bc5  sub     rsp, 28h
0x140005bc9  mov     ebp, [rcx+24h]
0x140005bcc  mov     r14, rdx
0x140005bcf  mov     rsi, [rcx+10h]
0x140005bd3  mov     edx, 40h ; '@'; Size
0x140005bd8  mov     rbx, rcx
0x140005bdb  mov     byte ptr [rcx+0C1h], 0
0x140005be2  lea     r12d, [rdx-3Fh]
0x140005be6  mov     ecx, r12d; Count
0x140005be9  call    cs:__imp_calloc
0x140005bef  mov     rdi, rax
0x140005bf2  test    rax, rax
0x140005bf5  jz      loc_140005D29
0x140005bfb  and     ebp, 100h
0x140005c01  mov     rcx, rsi
0x140005c04  mov     [rax+38h], ebp
0x140005c07  call    cs:__imp__o__strdup
0x140005c0d  mov     [rdi+28h], rax
0x140005c11  cmp     byte ptr [rsi], 2Dh ; '-'
0x140005c14  jnz     short loc_140005C25
0x140005c16  cmp     byte ptr [rsi+1], 0
0x140005c1a  jnz     short loc_140005C25
0x140005c1c  xor     ecx, ecx; Ix
0x140005c1e  call    _o___acrt_iob_func_0
0x140005c23  jmp     short loc_140005C35
0x140005c25  lea     rdx, aR; "r"
0x140005c2c  mov     rcx, rsi
0x140005c2f  call    cs:__imp__o_fopen
0x140005c35  mov     [rdi], rax
0x140005c38  test    rax, rax
0x140005c3b  jz      loc_140005D41
0x140005c41  mov     qword ptr [rdi+30h], 2000h
0x140005c49  mov     qword ptr [rdi+8], 0
0x140005c51  mov     qword ptr [rdi+10h], 0
0x140005c59  mov     qword ptr [rdi+20h], 0
0x140005c61  mov     qword ptr [rdi+18h], 0
0x140005c69  jmp     short loc_140005CE2
0x140005c6b  cmp     byte ptr [rbx+0C1h], 0
0x140005c72  jz      short loc_140005CA4
0x140005c74  cmp     byte ptr [rsi], 0
0x140005c77  jz      short loc_140005C86
0x140005c79  mov     rdx, rsi
0x140005c7c  mov     rcx, rbx
0x140005c7f  call    set_chdir
0x140005c84  jmp     short loc_140005C9B
0x140005c86  lea     rdx, aMeaninglessArg; "Meaningless argument for -C: ''"
0x140005c8d  xor     ecx, ecx
0x140005c8f  call    lafe_warnc
0x140005c94  mov     [rbx+0BCh], r12d
0x140005c9b  mov     byte ptr [rbx+0C1h], 0
0x140005ca2  jmp     short loc_140005CE2
0x140005ca4  test    dword ptr [rbx+24h], 100h
0x140005cab  jnz     short loc_140005CC7
0x140005cad  cmp     byte ptr [rsi], 2Dh ; '-'
0x140005cb0  jnz     short loc_140005CC7
0x140005cb2  cmp     byte ptr [rsi+1], 43h ; 'C'
0x140005cb6  jnz     short loc_140005CC7
0x140005cb8  cmp     byte ptr [rsi+2], 0
0x140005cbc  jnz     short loc_140005CC7
0x140005cbe  mov     [rbx+0C1h], r12b
0x140005cc5  jmp     short loc_140005CE2
0x140005cc7  cmp     byte ptr [rsi], 2Fh ; '/'
0x140005cca  jz      short loc_140005CD4
0x140005ccc  mov     rcx, rbx
0x140005ccf  call    do_chdir
0x140005cd4  mov     r8, rsi
0x140005cd7  mov     rdx, r14
0x140005cda  mov     rcx, rbx
0x140005cdd  call    write_hierarchy
0x140005ce2  mov     rcx, rdi
0x140005ce5  call    lafe_line_reader_next
0x140005cea  mov     rsi, rax
0x140005ced  test    rax, rax
0x140005cf0  jnz     loc_140005C6B
0x140005cf6  mov     rcx, [rdi+8]; Block
0x140005cfa  call    cs:__imp_free
0x140005d00  mov     rcx, [rdi+28h]; Block
0x140005d04  call    cs:__imp_free
0x140005d0a  mov     rcx, rdi; Block
0x140005d0d  call    cs:__imp_free
0x140005d13  cmp     byte ptr [rbx+0C1h], 0
0x140005d1a  jnz     short loc_140005D5C
0x140005d1c  add     rsp, 28h
0x140005d20  pop     r14
0x140005d22  pop     r12
0x140005d24  pop     rdi
0x140005d25  pop     rsi
0x140005d26  pop     rbp
0x140005d27  pop     rbx
0x140005d28  retn
0x140005d29  mov     r9, rsi
0x140005d2c  lea     r8, aCanTOpenS; "Can't open %s"
0x140005d33  mov     edx, 0Ch
0x140005d38  mov     ecx, r12d; Code
0x140005d3b  call    lafe_errc
0x140005d41  call    cs:__imp__o__errno
0x140005d47  mov     r9, rsi
0x140005d4a  lea     r8, aCouldnTOpenS; "Couldn't open %s"
0x140005d51  mov     ecx, r12d; Code
0x140005d54  mov     edx, [rax]
0x140005d56  call    lafe_errc
0x140005d5c  call    cs:__imp__o__errno
0x140005d62  lea     r8, aUnexpectedEndO; "Unexpected end of filename list; direct"...
0x140005d69  mov     ecx, r12d; Code
0x140005d6c  mov     edx, [rax]
0x140005d6e  call    lafe_errc
```
