# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800038ac`
- end: `0x18000391d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005954`
- `0x180005aa0`

## callees

- `0x1800038ac`
- `0x180005818`
- `0x180006710`

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
0x1800038ac  mov     [rsp+arg_0], rbx
0x1800038b1  mov     [rsp+arg_8], rsi
0x1800038b6  push    rdi
0x1800038b7  sub     rsp, 20h
0x1800038bb  mov     rbx, r9
0x1800038be  mov     rdi, rcx
0x1800038c1  cmp     rcx, rdx
0x1800038c4  jz      short loc_1800038FD
0x1800038c6  test    r8, r8
0x1800038c9  jz      short loc_1800038FD
0x1800038cb  cmp     byte ptr [r8], 0
0x1800038cf  jz      short loc_1800038FD
0x1800038d1  mov     rcx, r8; this
0x1800038d4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800038d9  sub     rdx, rdi; DestinationSize
0x1800038dc  mov     rsi, rax
0x1800038df  cmp     rdx, rax
0x1800038e2  jb      short loc_1800038FD
0x1800038e4  mov     r9, rax; SourceSize
0x1800038e7  mov     rcx, rdi; Destination
0x1800038ea  call    memcpy_s
0x1800038ef  test    rbx, rbx
0x1800038f2  jz      short loc_1800038F7
0x1800038f4  mov     [rbx], rdi
0x1800038f7  lea     rax, [rsi+rdi]
0x1800038fb  jmp     short loc_18000390C
0x1800038fd  test    rbx, rbx
0x180003900  jz      short loc_180003909
0x180003902  mov     qword ptr [r9], 0
0x180003909  mov     rax, rdi
0x18000390c  mov     rbx, [rsp+28h+arg_0]
0x180003911  mov     rsi, [rsp+28h+arg_8]
0x180003916  add     rsp, 20h
0x18000391a  pop     rdi
0x18000391b  retn
```
