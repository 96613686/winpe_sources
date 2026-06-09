# GetLocalMachineName(_bstr_t *)

- ea: `0x1800161a8`
- end: `0x18001621a`
- name: `?GetLocalMachineName@@YAKPEAV_bstr_t@@@Z`
- size: `114`
- prototype: `DWORD __fastcall(struct _bstr_t *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c9c0`
- `0x18000ce94`
- `0x180010590`
- `0x180012f40`
- `0x1800176ec`

## callees

- `0x180005740`
- `0x1800161a8`
- `0x18001e380`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x1800161e6`
- `KERNEL32!GetComputerNameW` at `0x1800161e6`
- `KERNEL32!GetLastError` at `0x1800161f0`
- `KERNEL32!GetLastError` at `0x1800161f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall GetLocalMachineName(struct _bstr_t *a1)
{
  DWORD nSize; // [rsp+20h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+28h] [rbp-30h] BYREF

  nSize = 16;
  memset(Buffer, 0, sizeof(Buffer));
  if ( !GetComputerNameW(Buffer, &nSize) )
    return GetLastError();
  _bstr_t::operator=(a1, Buffer);
  return 0;
}

```

## disassembly

```asm
0x1800161a8  push    rbx
0x1800161aa  sub     rsp, 50h
0x1800161ae  mov     rax, cs:__security_cookie
0x1800161b5  xor     rax, rsp
0x1800161b8  mov     [rsp+58h+var_10], rax
0x1800161bd  xorps   xmm0, xmm0
0x1800161c0  mov     [rsp+58h+nSize], 10h
0x1800161c8  mov     rbx, rcx
0x1800161cb  lea     rdx, [rsp+58h+nSize]; nSize
0x1800161d0  xor     eax, eax
0x1800161d2  lea     rcx, [rsp+58h+Buffer]; lpBuffer
0x1800161d7  movups  xmmword ptr [rsp+58h+var_2E], xmm0
0x1800161dc  mov     [rsp+58h+Buffer], ax
0x1800161e1  movups  xmmword ptr [rsp+58h+var_2E+0Eh], xmm0
0x1800161e6  call    cs:__imp_GetComputerNameW
0x1800161ec  test    eax, eax
0x1800161ee  jnz     short loc_1800161F8
0x1800161f0  call    cs:__imp_GetLastError
0x1800161f6  jmp     short loc_180016207
0x1800161f8  lea     rdx, [rsp+58h+Buffer]
0x1800161fd  mov     rcx, rbx
0x180016200  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x180016205  xor     eax, eax
0x180016207  mov     rcx, [rsp+58h+var_10]
0x18001620c  xor     rcx, rsp; StackCookie
0x18001620f  call    __security_check_cookie
0x180016214  add     rsp, 50h
0x180016218  pop     rbx
0x180016219  retn
```
