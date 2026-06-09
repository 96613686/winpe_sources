# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002bf8`
- end: `0x180002c6d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d2c`
- `0x180005138`

## callees

- `0x180002bf8`
- `0x18000b36c`

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
0x180002bf8  mov     [rsp+arg_0], rbx
0x180002bfd  mov     [rsp+arg_8], rsi
0x180002c02  push    rdi
0x180002c03  sub     rsp, 20h
0x180002c07  mov     rbx, r9
0x180002c0a  mov     rdi, rcx
0x180002c0d  cmp     rcx, rdx
0x180002c10  jz      short loc_180002C4D
0x180002c12  test    r8, r8
0x180002c15  jz      short loc_180002C4D
0x180002c17  cmp     byte ptr [r8], 0
0x180002c1b  jz      short loc_180002C4D
0x180002c1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002c21  inc     rax
0x180002c24  cmp     byte ptr [r8+rax], 0
0x180002c29  jnz     short loc_180002C21
0x180002c2b  lea     rsi, [rax+1]
0x180002c2f  sub     rdx, rdi; DestinationSize
0x180002c32  cmp     rdx, rsi
0x180002c35  jb      short loc_180002C4D
0x180002c37  mov     r9, rsi; SourceSize
0x180002c3a  call    memcpy_s
0x180002c3f  test    rbx, rbx
0x180002c42  jz      short loc_180002C47
0x180002c44  mov     [rbx], rdi
0x180002c47  lea     rax, [rsi+rdi]
0x180002c4b  jmp     short loc_180002C5C
0x180002c4d  test    rbx, rbx
0x180002c50  jz      short loc_180002C59
0x180002c52  mov     qword ptr [r9], 0
0x180002c59  mov     rax, rdi
0x180002c5c  mov     rbx, [rsp+28h+arg_0]
0x180002c61  mov     rsi, [rsp+28h+arg_8]
0x180002c66  add     rsp, 20h
0x180002c6a  pop     rdi
0x180002c6b  retn
```
