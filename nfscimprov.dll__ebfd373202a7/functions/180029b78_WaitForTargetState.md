# WaitForTargetState

- ea: `0x180029b78`
- end: `0x180029c27`
- name: `WaitForTargetState`
- size: `175`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002a6f8`
- `0x18002a80c`
- `0x18002aa74`

## callees

- `0x180029660`
- `0x180029b78`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029bcd`
- `KERNEL32!GetLastError` at `0x180029bcd`
- `KERNEL32!GetComputerNameExW` at `0x180029bc3`
- `KERNEL32!GetComputerNameExW` at `0x180029bc3`
- `KERNEL32!Sleep` at `0x180029bf5`
- `KERNEL32!Sleep` at `0x180029bf5`

## pseudocode

```c
DWORD __fastcall WaitForTargetState(int a1, int a2)
{
  int v4; // r8d
  int v6; // [rsp+30h] [rbp-A8h] BYREF
  DWORD nSize; // [rsp+34h] [rbp-A4h] BYREF
  int v8; // [rsp+38h] [rbp-A0h] BYREF
  WCHAR Buffer[64]; // [rsp+40h] [rbp-98h] BYREF

  v6 = 0;
  nSize = 64;
  v8 = -1;
  if ( !GetComputerNameExW(ComputerNamePhysicalDnsHostname, Buffer, &nSize) )
    return GetLastError();
  do
  {
    if ( (unsigned int)EvaluateCurrentResourceState(a1, a2, v4, (unsigned int)&v6, (__int64)&v8) )
      break;
    Sleep(0x64u);
  }
  while ( !v6 );
  return v6;
}

```

## disassembly

```asm
0x180029b78  mov     [rsp+arg_8], rsi
0x180029b7d  push    rdi
0x180029b7e  sub     rsp, 0D0h
0x180029b85  mov     rax, cs:__security_cookie
0x180029b8c  xor     rax, rsp
0x180029b8f  mov     [rsp+0D8h+var_18], rax
0x180029b97  mov     edi, edx
0x180029b99  mov     [rsp+0D8h+var_A8], 0
0x180029ba1  mov     rsi, rcx
0x180029ba4  mov     [rsp+0D8h+nSize], 40h ; '@'
0x180029bac  lea     rdx, [rsp+0D8h+Buffer]; lpBuffer
0x180029bb1  mov     [rsp+0D8h+var_A0], 0FFFFFFFFh
0x180029bb9  mov     ecx, 5; NameType
0x180029bbe  lea     r8, [rsp+0D8h+nSize]; nSize
0x180029bc3  call    cs:__imp_GetComputerNameExW
0x180029bc9  test    eax, eax
0x180029bcb  jnz     short loc_180029BD5
0x180029bcd  call    cs:__imp_GetLastError
0x180029bd3  jmp     short loc_180029C06
0x180029bd5  lea     rax, [rsp+0D8h+var_A0]
0x180029bda  mov     edx, edi
0x180029bdc  lea     r9, [rsp+0D8h+var_A8]
0x180029be1  mov     [rsp+0D8h+var_B8], rax
0x180029be6  mov     rcx, rsi
0x180029be9  call    EvaluateCurrentResourceState
0x180029bee  test    eax, eax
0x180029bf0  jnz     short loc_180029C02
0x180029bf2  lea     ecx, [rax+64h]; dwMilliseconds
0x180029bf5  call    cs:__imp_Sleep
0x180029bfb  cmp     [rsp+0D8h+var_A8], 0
0x180029c00  jz      short loc_180029BD5
0x180029c02  mov     eax, [rsp+0D8h+var_A8]
0x180029c06  mov     rcx, [rsp+0D8h+var_18]
0x180029c0e  xor     rcx, rsp; StackCookie
0x180029c11  call    __security_check_cookie
0x180029c16  mov     rsi, [rsp+0D8h+arg_8]
0x180029c1e  add     rsp, 0D0h
0x180029c25  pop     rdi
0x180029c26  retn
```
