# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180022250`
- end: `0x1800222e0`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027e60`

## callees

- `0x180022250`
- `0x180029fd0`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(char *a1, char *a2, _WORD *a3, _QWORD *a4)
{
  __int64 v6; // rax
  unsigned __int64 v8; // rsi
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
  v8 = 2 * v6 + 2;
  v9 = a2 - a1;
  if ( v9 >= v8 )
  {
    memcpy_s(a1, v9, a3, 2 * v6 + 2);
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
0x180022250  mov     [rsp+arg_0], rbx
0x180022255  mov     [rsp+arg_8], rsi
0x18002225a  push    rdi
0x18002225b  sub     rsp, 20h
0x18002225f  mov     rbx, r9
0x180022262  mov     rdi, rcx
0x180022265  cmp     rcx, rdx
0x180022268  jz      short loc_1800222C1
0x18002226a  test    r8, r8
0x18002226d  jz      short loc_1800222C1
0x18002226f  cmp     word ptr [r8], 0
0x180022274  jz      short loc_1800222C1
0x180022276  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002227d  nop     dword ptr [rax]
0x180022280  cmp     word ptr [r8+rax*2+2], 0
0x180022287  lea     rax, [rax+1]
0x18002228b  jnz     short loc_180022280
0x18002228d  lea     rsi, ds:2[rax*2]
0x180022295  sub     rdx, rdi; DestinationSize
0x180022298  cmp     rdx, rsi
0x18002229b  jb      short loc_1800222C1
0x18002229d  mov     r9, rsi; SourceSize
0x1800222a0  call    memcpy_s
0x1800222a5  test    rbx, rbx
0x1800222a8  jz      short loc_1800222AD
0x1800222aa  mov     [rbx], rdi
0x1800222ad  lea     rax, [rsi+rdi]
0x1800222b1  mov     rbx, [rsp+28h+arg_0]
0x1800222b6  mov     rsi, [rsp+28h+arg_8]
0x1800222bb  add     rsp, 20h
0x1800222bf  pop     rdi
0x1800222c0  retn
0x1800222c1  test    rbx, rbx
0x1800222c4  jz      short loc_1800222CD
0x1800222c6  mov     qword ptr [r9], 0
0x1800222cd  mov     rbx, [rsp+28h+arg_0]
0x1800222d2  mov     rax, rdi
0x1800222d5  mov     rsi, [rsp+28h+arg_8]
0x1800222da  add     rsp, 20h
0x1800222de  pop     rdi
0x1800222df  retn
```
