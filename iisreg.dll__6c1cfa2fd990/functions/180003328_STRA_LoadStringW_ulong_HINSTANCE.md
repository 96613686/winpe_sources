# STRA::LoadStringW(ulong,HINSTANCE__ *)

- ea: `0x180003328`
- end: `0x1800033a6`
- name: `?LoadStringW@STRA@@QEAAJKPEAUHINSTANCE__@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(STRA *__hidden this, unsigned int, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002330`

## callees

- `0x180003278`
- `0x180003328`
- `0x180003650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000337b`
- `KERNEL32!GetLastError` at `0x18000337b`
- `USER32!LoadStringA` at `0x180003357`
- `USER32!LoadStringA` at `0x180003357`

## pseudocode

```c
signed int __fastcall STRA::LoadStringW(STRA *this, UINT a2, HINSTANCE a3)
{
  unsigned int StringA; // eax
  signed int result; // eax
  CHAR Buffer[320]; // [rsp+30h] [rbp-158h] BYREF

  StringA = LoadStringA(a3, a2, Buffer, 320);
  if ( StringA )
    return STRA::AuxAppend(this, (const unsigned __int8 *)Buffer, StringA, 0, 1);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003328  push    rbx
0x18000332a  sub     rsp, 180h
0x180003331  mov     rax, cs:__security_cookie
0x180003338  xor     rax, rsp
0x18000333b  mov     [rsp+188h+var_18], rax
0x180003343  mov     rax, r8
0x180003346  mov     rbx, rcx
0x180003349  mov     rcx, rax; hInstance
0x18000334c  lea     r8, [rsp+188h+Buffer]; lpBuffer
0x180003351  mov     r9d, 140h; cchBufferMax
0x180003357  call    cs:__imp_LoadStringA
0x18000335d  test    eax, eax
0x18000335f  jz      short loc_18000337B
0x180003361  xor     r9d, r9d; unsigned int
0x180003364  mov     [rsp+188h+var_168], 1; bool
0x180003369  mov     r8d, eax; Size
0x18000336c  lea     rdx, [rsp+188h+Buffer]; Src
0x180003371  mov     rcx, rbx; this
0x180003374  call    ?AuxAppend@STRA@@AEAAJPEBEKK_N@Z; STRA::AuxAppend(uchar const *,ulong,ulong,bool)
0x180003379  jmp     short loc_18000338D
0x18000337b  call    cs:__imp_GetLastError
0x180003381  test    eax, eax
0x180003383  jle     short loc_18000338D
0x180003385  movzx   eax, ax
0x180003388  or      eax, 80070000h
0x18000338d  mov     rcx, [rsp+188h+var_18]
0x180003395  xor     rcx, rsp; StackCookie
0x180003398  call    __security_check_cookie
0x18000339d  add     rsp, 180h
0x1800033a4  pop     rbx
0x1800033a5  retn
```
