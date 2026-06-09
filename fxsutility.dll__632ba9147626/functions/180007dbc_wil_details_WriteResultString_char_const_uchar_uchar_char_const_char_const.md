# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180007dbc`
- end: `0x180007e31`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bdc8`
- `0x18000c1cc`

## callees

- `0x180007dbc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007dfe`
- `msvcrt!memcpy_s` at `0x180007dfe`

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
0x180007dbc  mov     [rsp+arg_0], rbx
0x180007dc1  mov     [rsp+arg_8], rsi
0x180007dc6  push    rdi
0x180007dc7  sub     rsp, 20h
0x180007dcb  mov     rbx, r9
0x180007dce  mov     rdi, rcx
0x180007dd1  cmp     rcx, rdx
0x180007dd4  jz      short loc_180007E12
0x180007dd6  test    r8, r8
0x180007dd9  jz      short loc_180007E12
0x180007ddb  cmp     byte ptr [r8], 0
0x180007ddf  jz      short loc_180007E12
0x180007de1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007de5  inc     rax
0x180007de8  cmp     byte ptr [r8+rax], 0
0x180007ded  jnz     short loc_180007DE5
0x180007def  lea     rsi, [rax+1]
0x180007df3  sub     rdx, rdi; DestinationSize
0x180007df6  cmp     rdx, rsi
0x180007df9  jb      short loc_180007E12
0x180007dfb  mov     r9, rsi; SourceSize
0x180007dfe  call    cs:__imp_memcpy_s
0x180007e04  test    rbx, rbx
0x180007e07  jz      short loc_180007E0C
0x180007e09  mov     [rbx], rdi
0x180007e0c  lea     rax, [rsi+rdi]
0x180007e10  jmp     short loc_180007E21
0x180007e12  test    rbx, rbx
0x180007e15  jz      short loc_180007E1E
0x180007e17  mov     qword ptr [r9], 0
0x180007e1e  mov     rax, rdi
0x180007e21  mov     rbx, [rsp+28h+arg_0]
0x180007e26  mov     rsi, [rsp+28h+arg_8]
0x180007e2b  add     rsp, 20h
0x180007e2f  pop     rdi
0x180007e30  retn
```
