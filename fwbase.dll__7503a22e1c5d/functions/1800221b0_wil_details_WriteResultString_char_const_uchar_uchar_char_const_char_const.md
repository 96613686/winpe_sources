# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800221b0`
- end: `0x18002223b`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180027b60`
- `0x180027e60`

## callees

- `0x1800221b0`
- `0x180029fd0`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *a1, char *a2, _BYTE *a3, _QWORD *a4)
{
  __int64 v6; // rax
  __int64 v8; // rsi
  rsize_t v9; // rdx

  if ( a1 == a2 )
    goto LABEL_10;
  if ( !a3 )
    goto LABEL_10;
  if ( !*a3 )
    goto LABEL_10;
  v6 = -1;
  while ( a3[++v6] != 0 )
    ;
  v8 = v6 + 1;
  v9 = a2 - a1;
  if ( v9 >= v6 + 1 )
  {
    memcpy_s(a1, v9, a3, v6 + 1);
    if ( a4 )
      *a4 = a1;
    return &a1[v8];
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
0x1800221b0  mov     [rsp+arg_0], rbx
0x1800221b5  mov     [rsp+arg_8], rsi
0x1800221ba  push    rdi
0x1800221bb  sub     rsp, 20h
0x1800221bf  mov     rbx, r9
0x1800221c2  mov     rdi, rcx
0x1800221c5  cmp     rcx, rdx
0x1800221c8  jz      short loc_18002221C
0x1800221ca  test    r8, r8
0x1800221cd  jz      short loc_18002221C
0x1800221cf  cmp     byte ptr [r8], 0
0x1800221d3  jz      short loc_18002221C
0x1800221d5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800221dc  nop     dword ptr [rax+00h]
0x1800221e0  cmp     byte ptr [r8+rax+1], 0
0x1800221e6  lea     rax, [rax+1]
0x1800221ea  jnz     short loc_1800221E0
0x1800221ec  lea     rsi, [rax+1]
0x1800221f0  sub     rdx, rdi; DestinationSize
0x1800221f3  cmp     rdx, rsi
0x1800221f6  jb      short loc_18002221C
0x1800221f8  mov     r9, rsi; SourceSize
0x1800221fb  call    memcpy_s
0x180022200  test    rbx, rbx
0x180022203  jz      short loc_180022208
0x180022205  mov     [rbx], rdi
0x180022208  lea     rax, [rsi+rdi]
0x18002220c  mov     rbx, [rsp+28h+arg_0]
0x180022211  mov     rsi, [rsp+28h+arg_8]
0x180022216  add     rsp, 20h
0x18002221a  pop     rdi
0x18002221b  retn
0x18002221c  test    rbx, rbx
0x18002221f  jz      short loc_180022228
0x180022221  mov     qword ptr [r9], 0
0x180022228  mov     rbx, [rsp+28h+arg_0]
0x18002222d  mov     rax, rdi
0x180022230  mov     rsi, [rsp+28h+arg_8]
0x180022235  add     rsp, 20h
0x180022239  pop     rdi
0x18002223a  retn
```
