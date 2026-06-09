# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180005508`
- end: `0x18000558a`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `130`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009940`
- `0x180009b64`

## callees

- `0x180005508`
- `0x1800097b0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000555c`
- `msvcrt!memcpy_s` at `0x18000555c`

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
0x180005508  push    rbx
0x18000550a  push    rbp
0x18000550b  push    rsi
0x18000550c  push    rdi
0x18000550d  push    r14
0x18000550f  sub     rsp, 20h
0x180005513  mov     rbx, r9
0x180005516  mov     rsi, r8
0x180005519  mov     rbp, rdx
0x18000551c  mov     rdi, rcx
0x18000551f  cmp     rcx, rdx
0x180005522  jz      short loc_180005570
0x180005524  test    r8, r8
0x180005527  jz      short loc_180005570
0x180005529  cmp     byte ptr [r8], 0
0x18000552d  jz      short loc_180005570
0x18000552f  mov     rcx, r8; this
0x180005532  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005537  sub     rbp, rdi
0x18000553a  mov     r14, rax
0x18000553d  cmp     rbp, rax
0x180005540  jnb     short loc_180005550
0x180005542  test    rbx, rbx
0x180005545  jz      short loc_18000557C
0x180005547  mov     qword ptr [rbx], 0
0x18000554e  jmp     short loc_18000557C
0x180005550  mov     r9, r14; SourceSize
0x180005553  mov     r8, rsi; Source
0x180005556  mov     rdx, rbp; DestinationSize
0x180005559  mov     rcx, rdi; Destination
0x18000555c  call    cs:__imp_memcpy_s
0x180005562  test    rbx, rbx
0x180005565  jz      short loc_18000556A
0x180005567  mov     [rbx], rdi
0x18000556a  lea     rax, [r14+rdi]
0x18000556e  jmp     short loc_18000557F
0x180005570  test    rbx, rbx
0x180005573  jz      short loc_18000557C
0x180005575  mov     qword ptr [r9], 0
0x18000557c  mov     rax, rdi
0x18000557f  add     rsp, 20h
0x180005583  pop     r14
0x180005585  pop     rdi
0x180005586  pop     rsi
0x180005587  pop     rbp
0x180005588  pop     rbx
0x180005589  retn
```
