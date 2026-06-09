# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1400043f8`
- end: `0x14000446d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ae84`
- `0x14000b288`

## callees

- `0x1400043f8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000443a`
- `msvcrt!memcpy_s` at `0x14000443a`

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
0x1400043f8  mov     [rsp+arg_0], rbx
0x1400043fd  mov     [rsp+arg_8], rsi
0x140004402  push    rdi
0x140004403  sub     rsp, 20h
0x140004407  mov     rbx, r9
0x14000440a  mov     rdi, rcx
0x14000440d  cmp     rcx, rdx
0x140004410  jz      short loc_14000444E
0x140004412  test    r8, r8
0x140004415  jz      short loc_14000444E
0x140004417  cmp     byte ptr [r8], 0
0x14000441b  jz      short loc_14000444E
0x14000441d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004421  inc     rax
0x140004424  cmp     byte ptr [r8+rax], 0
0x140004429  jnz     short loc_140004421
0x14000442b  lea     rsi, [rax+1]
0x14000442f  sub     rdx, rdi; DestinationSize
0x140004432  cmp     rdx, rsi
0x140004435  jb      short loc_14000444E
0x140004437  mov     r9, rsi; SourceSize
0x14000443a  call    cs:__imp_memcpy_s
0x140004440  test    rbx, rbx
0x140004443  jz      short loc_140004448
0x140004445  mov     [rbx], rdi
0x140004448  lea     rax, [rsi+rdi]
0x14000444c  jmp     short loc_14000445D
0x14000444e  test    rbx, rbx
0x140004451  jz      short loc_14000445A
0x140004453  mov     qword ptr [r9], 0
0x14000445a  mov     rax, rdi
0x14000445d  mov     rbx, [rsp+28h+arg_0]
0x140004462  mov     rsi, [rsp+28h+arg_8]
0x140004467  add     rsp, 20h
0x14000446b  pop     rdi
0x14000446c  retn
```
