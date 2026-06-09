# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x14000448c`
- end: `0x140004508`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b194`
- `0x14000b5b4`

## callees

- `0x14000448c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400044ce`
- `msvcrt!memcpy_s` at `0x1400044ce`

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
0x14000448c  mov     [rsp+arg_0], rbx
0x140004491  mov     [rsp+arg_8], rsi
0x140004496  push    rdi
0x140004497  sub     rsp, 20h
0x14000449b  mov     rbx, r9
0x14000449e  mov     rdi, rcx
0x1400044a1  cmp     rcx, rdx
0x1400044a4  jz      short loc_1400044E8
0x1400044a6  test    r8, r8
0x1400044a9  jz      short loc_1400044E8
0x1400044ab  cmp     byte ptr [r8], 0
0x1400044af  jz      short loc_1400044E8
0x1400044b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400044b5  inc     rax
0x1400044b8  cmp     byte ptr [r8+rax], 0
0x1400044bd  jnz     short loc_1400044B5
0x1400044bf  lea     rsi, [rax+1]
0x1400044c3  sub     rdx, rdi; DestinationSize
0x1400044c6  cmp     rdx, rsi
0x1400044c9  jb      short loc_1400044E8
0x1400044cb  mov     r9, rsi; SourceSize
0x1400044ce  call    cs:__imp_memcpy_s
0x1400044d5  nop     dword ptr [rax+rax+00h]
0x1400044da  test    rbx, rbx
0x1400044dd  jz      short loc_1400044E2
0x1400044df  mov     [rbx], rdi
0x1400044e2  lea     rax, [rsi+rdi]
0x1400044e6  jmp     short loc_1400044F7
0x1400044e8  test    rbx, rbx
0x1400044eb  jz      short loc_1400044F4
0x1400044ed  mov     qword ptr [r9], 0
0x1400044f4  mov     rax, rdi
0x1400044f7  mov     rbx, [rsp+28h+arg_0]
0x1400044fc  mov     rsi, [rsp+28h+arg_8]
0x140004501  add     rsp, 20h
0x140004505  pop     rdi
0x140004506  retn
```
