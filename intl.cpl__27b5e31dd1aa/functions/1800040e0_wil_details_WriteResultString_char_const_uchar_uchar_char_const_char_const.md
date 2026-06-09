# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800040e0`
- end: `0x180004151`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d70`
- `0x180005eac`

## callees

- `0x1800040e0`
- `0x180005c48`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000411e`
- `msvcrt!memcpy_s` at `0x18000411e`

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
0x1800040e0  mov     [rsp+arg_0], rbx
0x1800040e5  mov     [rsp+arg_8], rsi
0x1800040ea  push    rdi
0x1800040eb  sub     rsp, 20h
0x1800040ef  mov     rbx, r9
0x1800040f2  mov     rdi, rcx
0x1800040f5  cmp     rcx, rdx
0x1800040f8  jz      short loc_180004132
0x1800040fa  test    r8, r8
0x1800040fd  jz      short loc_180004132
0x1800040ff  cmp     byte ptr [r8], 0
0x180004103  jz      short loc_180004132
0x180004105  mov     rcx, r8; this
0x180004108  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000410d  sub     rdx, rdi; DestinationSize
0x180004110  mov     rsi, rax
0x180004113  cmp     rdx, rax
0x180004116  jb      short loc_180004132
0x180004118  mov     r9, rax; SourceSize
0x18000411b  mov     rcx, rdi; Destination
0x18000411e  call    cs:__imp_memcpy_s
0x180004124  test    rbx, rbx
0x180004127  jz      short loc_18000412C
0x180004129  mov     [rbx], rdi
0x18000412c  lea     rax, [rsi+rdi]
0x180004130  jmp     short loc_180004141
0x180004132  test    rbx, rbx
0x180004135  jz      short loc_18000413E
0x180004137  mov     qword ptr [r9], 0
0x18000413e  mov     rax, rdi
0x180004141  mov     rbx, [rsp+28h+arg_0]
0x180004146  mov     rsi, [rsp+28h+arg_8]
0x18000414b  add     rsp, 20h
0x18000414f  pop     rdi
0x180004150  retn
```
