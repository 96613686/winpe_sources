# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800038ac`
- end: `0x180003921`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: `char *__fastcall(char *, char *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800057b4`
- `0x180005bb8`

## callees

- `0x1800038ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800038ee`
- `msvcrt!memcpy_s` at `0x1800038ee`

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
0x1800038ac  mov     [rsp+arg_0], rbx
0x1800038b1  mov     [rsp+arg_8], rsi
0x1800038b6  push    rdi
0x1800038b7  sub     rsp, 20h
0x1800038bb  mov     rbx, r9
0x1800038be  mov     rdi, rcx
0x1800038c1  cmp     rcx, rdx
0x1800038c4  jz      short loc_180003902
0x1800038c6  test    r8, r8
0x1800038c9  jz      short loc_180003902
0x1800038cb  cmp     byte ptr [r8], 0
0x1800038cf  jz      short loc_180003902
0x1800038d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800038d5  inc     rax
0x1800038d8  cmp     byte ptr [r8+rax], 0
0x1800038dd  jnz     short loc_1800038D5
0x1800038df  lea     rsi, [rax+1]
0x1800038e3  sub     rdx, rdi; DestinationSize
0x1800038e6  cmp     rdx, rsi
0x1800038e9  jb      short loc_180003902
0x1800038eb  mov     r9, rsi; SourceSize
0x1800038ee  call    cs:__imp_memcpy_s
0x1800038f4  test    rbx, rbx
0x1800038f7  jz      short loc_1800038FC
0x1800038f9  mov     [rbx], rdi
0x1800038fc  lea     rax, [rsi+rdi]
0x180003900  jmp     short loc_180003911
0x180003902  test    rbx, rbx
0x180003905  jz      short loc_18000390E
0x180003907  mov     qword ptr [r9], 0
0x18000390e  mov     rax, rdi
0x180003911  mov     rbx, [rsp+28h+arg_0]
0x180003916  mov     rsi, [rsp+28h+arg_8]
0x18000391b  add     rsp, 20h
0x18000391f  pop     rdi
0x180003920  retn
```
