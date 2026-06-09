# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000315c`
- end: `0x1800031de`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `130`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006900`
- `0x180006b20`

## callees

- `0x18000315c`
- `0x180006768`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800031b0`
- `msvcrt!memcpy_s` at `0x1800031b0`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v8; // rax
  rsize_t v9; // rbp
  rsize_t v10; // r14

  if ( Destination == a2 || !a3 || !*(_BYTE *)a3 )
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
  v8 = wil::details::ResultStringSize(a3, a2);
  v9 = a2 - Destination;
  v10 = v8;
  if ( v9 < v8 )
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
  memcpy_s(Destination, v9, a3, v8);
  if ( a4 )
    *a4 = Destination;
  return &Destination[v10];
}

```

## disassembly

```asm
0x18000315c  push    rbx
0x18000315e  push    rbp
0x18000315f  push    rsi
0x180003160  push    rdi
0x180003161  push    r14
0x180003163  sub     rsp, 20h
0x180003167  mov     rbx, r9
0x18000316a  mov     rsi, r8
0x18000316d  mov     rbp, rdx
0x180003170  mov     rdi, rcx
0x180003173  cmp     rcx, rdx
0x180003176  jz      short loc_1800031C4
0x180003178  test    r8, r8
0x18000317b  jz      short loc_1800031C4
0x18000317d  cmp     byte ptr [r8], 0
0x180003181  jz      short loc_1800031C4
0x180003183  mov     rcx, r8; this
0x180003186  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000318b  sub     rbp, rdi
0x18000318e  mov     r14, rax
0x180003191  cmp     rbp, rax
0x180003194  jnb     short loc_1800031A4
0x180003196  test    rbx, rbx
0x180003199  jz      short loc_1800031D0
0x18000319b  mov     qword ptr [rbx], 0
0x1800031a2  jmp     short loc_1800031D0
0x1800031a4  mov     r9, r14; SourceSize
0x1800031a7  mov     r8, rsi; Source
0x1800031aa  mov     rdx, rbp; DestinationSize
0x1800031ad  mov     rcx, rdi; Destination
0x1800031b0  call    cs:__imp_memcpy_s
0x1800031b6  test    rbx, rbx
0x1800031b9  jz      short loc_1800031BE
0x1800031bb  mov     [rbx], rdi
0x1800031be  lea     rax, [r14+rdi]
0x1800031c2  jmp     short loc_1800031D3
0x1800031c4  test    rbx, rbx
0x1800031c7  jz      short loc_1800031D0
0x1800031c9  mov     qword ptr [r9], 0
0x1800031d0  mov     rax, rdi
0x1800031d3  add     rsp, 20h
0x1800031d7  pop     r14
0x1800031d9  pop     rdi
0x1800031da  pop     rsi
0x1800031db  pop     rbp
0x1800031dc  pop     rbx
0x1800031dd  retn
```
