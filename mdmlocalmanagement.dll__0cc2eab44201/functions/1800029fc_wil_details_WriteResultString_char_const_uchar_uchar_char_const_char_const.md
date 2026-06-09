# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800029fc`
- end: `0x180002a71`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800049ac`
- `0x180004db8`

## callees

- `0x1800029fc`
- `0x180005df8`

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
0x1800029fc  mov     [rsp+arg_0], rbx
0x180002a01  mov     [rsp+arg_8], rsi
0x180002a06  push    rdi
0x180002a07  sub     rsp, 20h
0x180002a0b  mov     rbx, r9
0x180002a0e  mov     rdi, rcx
0x180002a11  cmp     rcx, rdx
0x180002a14  jz      short loc_180002A51
0x180002a16  test    r8, r8
0x180002a19  jz      short loc_180002A51
0x180002a1b  cmp     byte ptr [r8], 0
0x180002a1f  jz      short loc_180002A51
0x180002a21  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002a25  inc     rax
0x180002a28  cmp     byte ptr [r8+rax], 0
0x180002a2d  jnz     short loc_180002A25
0x180002a2f  lea     rsi, [rax+1]
0x180002a33  sub     rdx, rdi; DestinationSize
0x180002a36  cmp     rdx, rsi
0x180002a39  jb      short loc_180002A51
0x180002a3b  mov     r9, rsi; SourceSize
0x180002a3e  call    memcpy_s
0x180002a43  test    rbx, rbx
0x180002a46  jz      short loc_180002A4B
0x180002a48  mov     [rbx], rdi
0x180002a4b  lea     rax, [rsi+rdi]
0x180002a4f  jmp     short loc_180002A60
0x180002a51  test    rbx, rbx
0x180002a54  jz      short loc_180002A5D
0x180002a56  mov     qword ptr [r9], 0
0x180002a5d  mov     rax, rdi
0x180002a60  mov     rbx, [rsp+28h+arg_0]
0x180002a65  mov     rsi, [rsp+28h+arg_8]
0x180002a6a  add     rsp, 20h
0x180002a6e  pop     rdi
0x180002a6f  retn
```
