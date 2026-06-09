# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002d3c`
- end: `0x180002db1`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006c98`
- `0x18000709c`

## callees

- `0x180002d3c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002d7e`
- `msvcrt!memcpy_s` at `0x180002d7e`

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
0x180002d3c  mov     [rsp+arg_0], rbx
0x180002d41  mov     [rsp+arg_8], rsi
0x180002d46  push    rdi
0x180002d47  sub     rsp, 20h
0x180002d4b  mov     rbx, r9
0x180002d4e  mov     rdi, rcx
0x180002d51  cmp     rcx, rdx
0x180002d54  jz      short loc_180002D92
0x180002d56  test    r8, r8
0x180002d59  jz      short loc_180002D92
0x180002d5b  cmp     byte ptr [r8], 0
0x180002d5f  jz      short loc_180002D92
0x180002d61  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002d65  inc     rax
0x180002d68  cmp     byte ptr [r8+rax], 0
0x180002d6d  jnz     short loc_180002D65
0x180002d6f  lea     rsi, [rax+1]
0x180002d73  sub     rdx, rdi; DestinationSize
0x180002d76  cmp     rdx, rsi
0x180002d79  jb      short loc_180002D92
0x180002d7b  mov     r9, rsi; SourceSize
0x180002d7e  call    cs:__imp_memcpy_s
0x180002d84  test    rbx, rbx
0x180002d87  jz      short loc_180002D8C
0x180002d89  mov     [rbx], rdi
0x180002d8c  lea     rax, [rsi+rdi]
0x180002d90  jmp     short loc_180002DA1
0x180002d92  test    rbx, rbx
0x180002d95  jz      short loc_180002D9E
0x180002d97  mov     qword ptr [r9], 0
0x180002d9e  mov     rax, rdi
0x180002da1  mov     rbx, [rsp+28h+arg_0]
0x180002da6  mov     rsi, [rsp+28h+arg_8]
0x180002dab  add     rsp, 20h
0x180002daf  pop     rdi
0x180002db0  retn
```
