# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140003130`
- end: `0x1400031a5`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400079f4`
- `0x140007df8`

## callees

- `0x140003130`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140003172`
- `msvcrt!memcpy_s` at `0x140003172`

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
0x140003130  mov     [rsp+arg_0], rbx
0x140003135  mov     [rsp+arg_8], rsi
0x14000313a  push    rdi
0x14000313b  sub     rsp, 20h
0x14000313f  mov     rbx, r9
0x140003142  mov     rdi, rcx
0x140003145  cmp     rcx, rdx
0x140003148  jz      short loc_140003186
0x14000314a  test    r8, r8
0x14000314d  jz      short loc_140003186
0x14000314f  cmp     byte ptr [r8], 0
0x140003153  jz      short loc_140003186
0x140003155  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003159  inc     rax
0x14000315c  cmp     byte ptr [r8+rax], 0
0x140003161  jnz     short loc_140003159
0x140003163  lea     rsi, [rax+1]
0x140003167  sub     rdx, rdi; DestinationSize
0x14000316a  cmp     rdx, rsi
0x14000316d  jb      short loc_140003186
0x14000316f  mov     r9, rsi; SourceSize
0x140003172  call    cs:__imp_memcpy_s
0x140003178  test    rbx, rbx
0x14000317b  jz      short loc_140003180
0x14000317d  mov     [rbx], rdi
0x140003180  lea     rax, [rsi+rdi]
0x140003184  jmp     short loc_140003195
0x140003186  test    rbx, rbx
0x140003189  jz      short loc_140003192
0x14000318b  mov     qword ptr [r9], 0
0x140003192  mov     rax, rdi
0x140003195  mov     rbx, [rsp+28h+arg_0]
0x14000319a  mov     rsi, [rsp+28h+arg_8]
0x14000319f  add     rsp, 20h
0x1400031a3  pop     rdi
0x1400031a4  retn
```
