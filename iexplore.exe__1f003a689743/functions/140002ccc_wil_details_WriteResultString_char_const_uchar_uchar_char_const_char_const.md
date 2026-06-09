# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140002ccc`
- end: `0x140002d3d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004a9c`

## callees

- `0x140002ccc`
- `0x14000496c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002d0a`
- `msvcrt!memcpy_s` at `0x140002d0a`

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
0x140002ccc  mov     [rsp+arg_0], rbx
0x140002cd1  mov     [rsp+arg_8], rsi
0x140002cd6  push    rdi
0x140002cd7  sub     rsp, 20h
0x140002cdb  mov     rbx, r9
0x140002cde  mov     rdi, rcx
0x140002ce1  cmp     rcx, rdx
0x140002ce4  jz      short loc_140002D1E
0x140002ce6  test    r8, r8
0x140002ce9  jz      short loc_140002D1E
0x140002ceb  cmp     byte ptr [r8], 0
0x140002cef  jz      short loc_140002D1E
0x140002cf1  mov     rcx, r8; this
0x140002cf4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140002cf9  sub     rdx, rdi; DestinationSize
0x140002cfc  mov     rsi, rax
0x140002cff  cmp     rdx, rax
0x140002d02  jb      short loc_140002D1E
0x140002d04  mov     r9, rax; SourceSize
0x140002d07  mov     rcx, rdi; Destination
0x140002d0a  call    cs:__imp_memcpy_s
0x140002d10  test    rbx, rbx
0x140002d13  jz      short loc_140002D18
0x140002d15  mov     [rbx], rdi
0x140002d18  lea     rax, [rsi+rdi]
0x140002d1c  jmp     short loc_140002D2D
0x140002d1e  test    rbx, rbx
0x140002d21  jz      short loc_140002D2A
0x140002d23  mov     qword ptr [r9], 0
0x140002d2a  mov     rax, rdi
0x140002d2d  mov     rbx, [rsp+28h+arg_0]
0x140002d32  mov     rsi, [rsp+28h+arg_8]
0x140002d37  add     rsp, 20h
0x140002d3b  pop     rdi
0x140002d3c  retn
```
