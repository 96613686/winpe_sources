# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18001069c`
- end: `0x18001070d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013d54`

## callees

- `0x18001069c`
- `0x180013bd4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800106da`
- `msvcrt!memcpy_s` at `0x1800106da`

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
0x18001069c  mov     [rsp+arg_0], rbx
0x1800106a1  mov     [rsp+arg_8], rsi
0x1800106a6  push    rdi
0x1800106a7  sub     rsp, 20h
0x1800106ab  mov     rbx, r9
0x1800106ae  mov     rdi, rcx
0x1800106b1  cmp     rcx, rdx
0x1800106b4  jz      short loc_1800106EE
0x1800106b6  test    r8, r8
0x1800106b9  jz      short loc_1800106EE
0x1800106bb  cmp     byte ptr [r8], 0
0x1800106bf  jz      short loc_1800106EE
0x1800106c1  mov     rcx, r8; this
0x1800106c4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800106c9  sub     rdx, rdi; DestinationSize
0x1800106cc  mov     rsi, rax
0x1800106cf  cmp     rdx, rax
0x1800106d2  jb      short loc_1800106EE
0x1800106d4  mov     r9, rax; SourceSize
0x1800106d7  mov     rcx, rdi; Destination
0x1800106da  call    cs:__imp_memcpy_s
0x1800106e0  test    rbx, rbx
0x1800106e3  jz      short loc_1800106E8
0x1800106e5  mov     [rbx], rdi
0x1800106e8  lea     rax, [rsi+rdi]
0x1800106ec  jmp     short loc_1800106FD
0x1800106ee  test    rbx, rbx
0x1800106f1  jz      short loc_1800106FA
0x1800106f3  mov     qword ptr [r9], 0
0x1800106fa  mov     rax, rdi
0x1800106fd  mov     rbx, [rsp+28h+arg_0]
0x180010702  mov     rsi, [rsp+28h+arg_8]
0x180010707  add     rsp, 20h
0x18001070b  pop     rdi
0x18001070c  retn
```
