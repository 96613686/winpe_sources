# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800044bc`
- end: `0x18000452d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800079f4`

## callees

- `0x1800044bc`
- `0x1800077d8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800044fa`
- `msvcrt!memcpy_s` at `0x1800044fa`

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
0x1800044bc  mov     [rsp+arg_0], rbx
0x1800044c1  mov     [rsp+arg_8], rsi
0x1800044c6  push    rdi
0x1800044c7  sub     rsp, 20h
0x1800044cb  mov     rbx, r9
0x1800044ce  mov     rdi, rcx
0x1800044d1  cmp     rcx, rdx
0x1800044d4  jz      short loc_18000450E
0x1800044d6  test    r8, r8
0x1800044d9  jz      short loc_18000450E
0x1800044db  cmp     byte ptr [r8], 0
0x1800044df  jz      short loc_18000450E
0x1800044e1  mov     rcx, r8; this
0x1800044e4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800044e9  sub     rdx, rdi; DestinationSize
0x1800044ec  mov     rsi, rax
0x1800044ef  cmp     rdx, rax
0x1800044f2  jb      short loc_18000450E
0x1800044f4  mov     r9, rax; SourceSize
0x1800044f7  mov     rcx, rdi; Destination
0x1800044fa  call    cs:__imp_memcpy_s
0x180004500  test    rbx, rbx
0x180004503  jz      short loc_180004508
0x180004505  mov     [rbx], rdi
0x180004508  lea     rax, [rsi+rdi]
0x18000450c  jmp     short loc_18000451D
0x18000450e  test    rbx, rbx
0x180004511  jz      short loc_18000451A
0x180004513  mov     qword ptr [r9], 0
0x18000451a  mov     rax, rdi
0x18000451d  mov     rbx, [rsp+28h+arg_0]
0x180004522  mov     rsi, [rsp+28h+arg_8]
0x180004527  add     rsp, 20h
0x18000452b  pop     rdi
0x18000452c  retn
```
