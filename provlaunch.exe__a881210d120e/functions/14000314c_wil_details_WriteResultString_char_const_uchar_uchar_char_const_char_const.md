# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x14000314c`
- end: `0x1400031c1`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005610`
- `0x140005a14`

## callees

- `0x14000314c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000318e`
- `msvcrt!memcpy_s` at `0x14000318e`

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
0x14000314c  mov     [rsp+arg_0], rbx
0x140003151  mov     [rsp+arg_8], rsi
0x140003156  push    rdi
0x140003157  sub     rsp, 20h
0x14000315b  mov     rbx, r9
0x14000315e  mov     rdi, rcx
0x140003161  cmp     rcx, rdx
0x140003164  jz      short loc_1400031A2
0x140003166  test    r8, r8
0x140003169  jz      short loc_1400031A2
0x14000316b  cmp     byte ptr [r8], 0
0x14000316f  jz      short loc_1400031A2
0x140003171  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003175  inc     rax
0x140003178  cmp     byte ptr [r8+rax], 0
0x14000317d  jnz     short loc_140003175
0x14000317f  lea     rsi, [rax+1]
0x140003183  sub     rdx, rdi; DestinationSize
0x140003186  cmp     rdx, rsi
0x140003189  jb      short loc_1400031A2
0x14000318b  mov     r9, rsi; SourceSize
0x14000318e  call    cs:__imp_memcpy_s
0x140003194  test    rbx, rbx
0x140003197  jz      short loc_14000319C
0x140003199  mov     [rbx], rdi
0x14000319c  lea     rax, [rsi+rdi]
0x1400031a0  jmp     short loc_1400031B1
0x1400031a2  test    rbx, rbx
0x1400031a5  jz      short loc_1400031AE
0x1400031a7  mov     qword ptr [r9], 0
0x1400031ae  mov     rax, rdi
0x1400031b1  mov     rbx, [rsp+28h+arg_0]
0x1400031b6  mov     rsi, [rsp+28h+arg_8]
0x1400031bb  add     rsp, 20h
0x1400031bf  pop     rdi
0x1400031c0  retn
```
