# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1400072fc`
- end: `0x14000736c`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a924`

## callees

- `0x1400072fc`
- `0x14000a7c8`
- `0x14000bebc`

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
0x1400072fc  mov     [rsp+arg_0], rbx
0x140007301  mov     [rsp+arg_8], rsi
0x140007306  push    rdi
0x140007307  sub     rsp, 20h
0x14000730b  mov     rbx, r9
0x14000730e  mov     rdi, rcx
0x140007311  cmp     rcx, rdx
0x140007314  jz      short loc_14000734D
0x140007316  test    r8, r8
0x140007319  jz      short loc_14000734D
0x14000731b  cmp     byte ptr [r8], 0
0x14000731f  jz      short loc_14000734D
0x140007321  mov     rcx, r8; this
0x140007324  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140007329  sub     rdx, rdi; DestinationSize
0x14000732c  mov     rsi, rax
0x14000732f  cmp     rdx, rax
0x140007332  jb      short loc_14000734D
0x140007334  mov     r9, rax; SourceSize
0x140007337  mov     rcx, rdi; Destination
0x14000733a  call    memcpy_s
0x14000733f  test    rbx, rbx
0x140007342  jz      short loc_140007347
0x140007344  mov     [rbx], rdi
0x140007347  lea     rax, [rsi+rdi]
0x14000734b  jmp     short loc_14000735C
0x14000734d  test    rbx, rbx
0x140007350  jz      short loc_140007359
0x140007352  mov     qword ptr [r9], 0
0x140007359  mov     rax, rdi
0x14000735c  mov     rbx, [rsp+28h+arg_0]
0x140007361  mov     rsi, [rsp+28h+arg_8]
0x140007366  add     rsp, 20h
0x14000736a  pop     rdi
0x14000736b  retn
```
