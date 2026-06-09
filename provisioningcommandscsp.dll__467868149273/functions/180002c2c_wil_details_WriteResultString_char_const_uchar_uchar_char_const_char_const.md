# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002c2c`
- end: `0x180002ca8`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f7c`
- `0x18000539c`

## callees

- `0x180002c2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002c6e`
- `msvcrt!memcpy_s` at `0x180002c6e`

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
0x180002c2c  mov     [rsp+arg_0], rbx
0x180002c31  mov     [rsp+arg_8], rsi
0x180002c36  push    rdi
0x180002c37  sub     rsp, 20h
0x180002c3b  mov     rbx, r9
0x180002c3e  mov     rdi, rcx
0x180002c41  cmp     rcx, rdx
0x180002c44  jz      short loc_180002C88
0x180002c46  test    r8, r8
0x180002c49  jz      short loc_180002C88
0x180002c4b  cmp     byte ptr [r8], 0
0x180002c4f  jz      short loc_180002C88
0x180002c51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002c55  inc     rax
0x180002c58  cmp     byte ptr [r8+rax], 0
0x180002c5d  jnz     short loc_180002C55
0x180002c5f  lea     rsi, [rax+1]
0x180002c63  sub     rdx, rdi; DestinationSize
0x180002c66  cmp     rdx, rsi
0x180002c69  jb      short loc_180002C88
0x180002c6b  mov     r9, rsi; SourceSize
0x180002c6e  call    cs:__imp_memcpy_s
0x180002c75  nop     dword ptr [rax+rax+00h]
0x180002c7a  test    rbx, rbx
0x180002c7d  jz      short loc_180002C82
0x180002c7f  mov     [rbx], rdi
0x180002c82  lea     rax, [rsi+rdi]
0x180002c86  jmp     short loc_180002C97
0x180002c88  test    rbx, rbx
0x180002c8b  jz      short loc_180002C94
0x180002c8d  mov     qword ptr [r9], 0
0x180002c94  mov     rax, rdi
0x180002c97  mov     rbx, [rsp+28h+arg_0]
0x180002c9c  mov     rsi, [rsp+28h+arg_8]
0x180002ca1  add     rsp, 20h
0x180002ca5  pop     rdi
0x180002ca6  retn
```
