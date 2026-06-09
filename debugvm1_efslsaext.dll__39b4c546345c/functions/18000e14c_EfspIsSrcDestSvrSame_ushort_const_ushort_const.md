# EfspIsSrcDestSvrSame(ushort const *,ushort const *)

- ea: `0x18000e14c`
- end: `0x18000e246`
- name: `?EfspIsSrcDestSvrSame@@YAHPEBG0@Z`
- size: `250`
- prototype: `__int64 __fastcall(wchar_t *String2, wchar_t *String1)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b424`

## callees

- `0x18000e14c`
- `0x180012040`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e174`
- `msvcrt!_wcsicmp` at `0x18000e19e`
- `msvcrt!_wcsicmp` at `0x18000e1c6`
- `msvcrt!_wcsicmp` at `0x18000e215`
- `msvcrt!_wcsicmp` at `0x18000e174`
- `msvcrt!_wcsicmp` at `0x18000e19e`
- `msvcrt!_wcsicmp` at `0x18000e1c6`
- `msvcrt!_wcsicmp` at `0x18000e215`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000e1fb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000e1fb`

## pseudocode

```c
__int64 __fastcall EfspIsSrcDestSvrSame(wchar_t *String2, wchar_t *String1)
{
  unsigned int v4; // ebx
  char v5; // bp
  char v6; // di
  const wchar_t *v7; // rdx
  DWORD nSize[4]; // [rsp+20h] [rbp-88h] BYREF
  WCHAR Buffer[32]; // [rsp+30h] [rbp-78h] BYREF

  if ( !_wcsicmp(String2, String1) )
    return 1;
  v4 = 0;
  if ( *String2 == 46 && !String2[1] || (v5 = 0, !_wcsicmp(String2, L"localhost")) )
    v5 = 1;
  if ( *String1 == 46 && !String1[1] || (v6 = 0, !_wcsicmp(String1, L"localhost")) )
    v6 = 1;
  if ( v5 )
  {
    if ( v6 )
      return 1;
  }
  else if ( !v6 )
  {
    return v4;
  }
  nSize[0] = 16;
  if ( GetComputerNameW(Buffer, nSize) )
  {
    v7 = String1;
    if ( !v5 )
      v7 = String2;
    LOBYTE(v4) = _wcsicmp(Buffer, v7) == 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18000e14c  mov     [rsp+arg_10], rbx
0x18000e151  push    rbp
0x18000e152  push    rsi
0x18000e153  push    rdi
0x18000e154  push    r14
0x18000e156  push    r15
0x18000e158  sub     rsp, 80h
0x18000e15f  mov     rax, cs:__security_cookie
0x18000e166  xor     rax, rsp
0x18000e169  mov     [rsp+0A8h+var_38], rax
0x18000e16e  mov     r14, rdx
0x18000e171  mov     rsi, rcx
0x18000e174  call    cs:__imp__wcsicmp
0x18000e17a  xor     r15d, r15d
0x18000e17d  test    eax, eax
0x18000e17f  jz      short loc_18000E1DD
0x18000e181  cmp     word ptr [rsi], 2Eh ; '.'
0x18000e185  mov     ebx, r15d
0x18000e188  jnz     short loc_18000E191
0x18000e18a  cmp     [rsi+2], r15w
0x18000e18f  jz      short loc_18000E1A8
0x18000e191  lea     rdx, aLocalhost; "localhost"
0x18000e198  mov     rcx, rsi; String1
0x18000e19b  mov     bpl, r15b
0x18000e19e  call    cs:__imp__wcsicmp
0x18000e1a4  test    eax, eax
0x18000e1a6  jnz     short loc_18000E1AB
0x18000e1a8  mov     bpl, 1
0x18000e1ab  cmp     word ptr [r14], 2Eh ; '.'
0x18000e1b0  jnz     short loc_18000E1B9
0x18000e1b2  cmp     [r14+2], r15w
0x18000e1b7  jz      short loc_18000E1D0
0x18000e1b9  lea     rdx, aLocalhost; "localhost"
0x18000e1c0  mov     rcx, r14; String1
0x18000e1c3  mov     dil, r15b
0x18000e1c6  call    cs:__imp__wcsicmp
0x18000e1cc  test    eax, eax
0x18000e1ce  jnz     short loc_18000E1D3
0x18000e1d0  mov     dil, 1
0x18000e1d3  test    bpl, bpl
0x18000e1d6  jz      short loc_18000E1E4
0x18000e1d8  test    dil, dil
0x18000e1db  jz      short loc_18000E1E9
0x18000e1dd  mov     ebx, 1
0x18000e1e2  jmp     short loc_18000E220
0x18000e1e4  test    dil, dil
0x18000e1e7  jz      short loc_18000E220
0x18000e1e9  lea     rdx, [rsp+0A8h+nSize]; nSize
0x18000e1ee  mov     [rsp+0A8h+nSize], 10h
0x18000e1f6  lea     rcx, [rsp+0A8h+Buffer]; lpBuffer
0x18000e1fb  call    cs:__imp_GetComputerNameW
0x18000e201  test    eax, eax
0x18000e203  jz      short loc_18000E220
0x18000e205  lea     rcx, [rsp+0A8h+Buffer]; String1
0x18000e20a  mov     rdx, r14
0x18000e20d  test    bpl, bpl
0x18000e210  jnz     short loc_18000E215
0x18000e212  mov     rdx, rsi; String2
0x18000e215  call    cs:__imp__wcsicmp
0x18000e21b  test    eax, eax
0x18000e21d  setz    bl
0x18000e220  mov     eax, ebx
0x18000e222  mov     rcx, [rsp+0A8h+var_38]
0x18000e227  xor     rcx, rsp; StackCookie
0x18000e22a  call    __security_check_cookie
0x18000e22f  mov     rbx, [rsp+0A8h+arg_10]
0x18000e237  add     rsp, 80h
0x18000e23e  pop     r15
0x18000e240  pop     r14
0x18000e242  pop     rdi
0x18000e243  pop     rsi
0x18000e244  pop     rbp
0x18000e245  retn
```
