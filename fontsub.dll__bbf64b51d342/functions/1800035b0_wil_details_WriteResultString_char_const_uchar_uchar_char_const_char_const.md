# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800035b0`
- end: `0x180003621`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005afc`
- `0x180005c38`

## callees

- `0x1800035b0`
- `0x180005a2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800035ee`
- `msvcrt!memcpy_s` at `0x1800035ee`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // rdx
  rsize_t v9; // rdx
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_BYTE *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v10];
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x1800035b0  mov     [rsp+arg_0], rbx
0x1800035b5  mov     [rsp+arg_8], rsi
0x1800035ba  push    rdi
0x1800035bb  sub     rsp, 20h
0x1800035bf  mov     rbx, r9
0x1800035c2  mov     rdi, rcx
0x1800035c5  cmp     rcx, rdx
0x1800035c8  jz      short loc_180003602
0x1800035ca  test    r8, r8
0x1800035cd  jz      short loc_180003602
0x1800035cf  cmp     byte ptr [r8], 0
0x1800035d3  jz      short loc_180003602
0x1800035d5  mov     rcx, r8; this
0x1800035d8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800035dd  sub     rdx, rdi; DestinationSize
0x1800035e0  mov     rsi, rax
0x1800035e3  cmp     rdx, rax
0x1800035e6  jb      short loc_180003602
0x1800035e8  mov     r9, rax; SourceSize
0x1800035eb  mov     rcx, rdi; Destination
0x1800035ee  call    cs:__imp_memcpy_s
0x1800035f4  test    rbx, rbx
0x1800035f7  jz      short loc_1800035FC
0x1800035f9  mov     [rbx], rdi
0x1800035fc  lea     rax, [rsi+rdi]
0x180003600  jmp     short loc_180003611
0x180003602  test    rbx, rbx
0x180003605  jz      short loc_18000360E
0x180003607  mov     qword ptr [r9], 0
0x18000360e  mov     rax, rdi
0x180003611  mov     rbx, [rsp+28h+arg_0]
0x180003616  mov     rsi, [rsp+28h+arg_8]
0x18000361b  add     rsp, 20h
0x18000361f  pop     rdi
0x180003620  retn
```
