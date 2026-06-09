# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002bec`
- end: `0x180002c61`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e30`
- `0x180005234`

## callees

- `0x180002bec`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002c2e`
- `msvcrt!memcpy_s` at `0x180002c2e`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *a1, char *a2, _BYTE *a3, _QWORD *a4)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  rsize_t v8; // rdx

  if ( a1 == a2 )
    goto LABEL_10;
  if ( !a3 )
    goto LABEL_10;
  if ( !*a3 )
    goto LABEL_10;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v7 = v6 + 1;
  v8 = a2 - a1;
  if ( v8 >= v6 + 1 )
  {
    memcpy_s(a1, v8, a3, v6 + 1);
    if ( a4 )
      *a4 = a1;
    return &a1[v7];
  }
  else
  {
LABEL_10:
    if ( a4 )
      *a4 = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x180002bec  mov     [rsp+arg_0], rbx
0x180002bf1  mov     [rsp+arg_8], rsi
0x180002bf6  push    rdi
0x180002bf7  sub     rsp, 20h
0x180002bfb  mov     rbx, r9
0x180002bfe  mov     rdi, rcx
0x180002c01  cmp     rcx, rdx
0x180002c04  jz      short loc_180002C42
0x180002c06  test    r8, r8
0x180002c09  jz      short loc_180002C42
0x180002c0b  cmp     byte ptr [r8], 0
0x180002c0f  jz      short loc_180002C42
0x180002c11  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002c15  inc     rax
0x180002c18  cmp     byte ptr [r8+rax], 0
0x180002c1d  jnz     short loc_180002C15
0x180002c1f  lea     rsi, [rax+1]
0x180002c23  sub     rdx, rdi; DestinationSize
0x180002c26  cmp     rdx, rsi
0x180002c29  jb      short loc_180002C42
0x180002c2b  mov     r9, rsi; SourceSize
0x180002c2e  call    cs:__imp_memcpy_s
0x180002c34  test    rbx, rbx
0x180002c37  jz      short loc_180002C3C
0x180002c39  mov     [rbx], rdi
0x180002c3c  lea     rax, [rsi+rdi]
0x180002c40  jmp     short loc_180002C51
0x180002c42  test    rbx, rbx
0x180002c45  jz      short loc_180002C4E
0x180002c47  mov     qword ptr [r9], 0
0x180002c4e  mov     rax, rdi
0x180002c51  mov     rbx, [rsp+28h+arg_0]
0x180002c56  mov     rsi, [rsp+28h+arg_8]
0x180002c5b  add     rsp, 20h
0x180002c5f  pop     rdi
0x180002c60  retn
```
