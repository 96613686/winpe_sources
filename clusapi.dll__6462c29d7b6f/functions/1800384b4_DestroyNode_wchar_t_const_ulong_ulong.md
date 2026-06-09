# DestroyNode(wchar_t const *,ulong,ulong)

- ea: `0x1800384b4`
- end: `0x18003853e`
- name: `?DestroyNode@@YAKPEB_WKK@Z`
- size: `138`
- prototype: `unsigned int __fastcall(const wchar_t *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180058330`

## callees

- `0x180002f50`
- `0x1800384b4`
- `0x1800a001c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003850a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003850a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800384fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800384fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800384f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800384f0`

## pseudocode

```c
DWORD __fastcall DestroyNode(unsigned __int64 a1, unsigned int a2, unsigned int a3)
{
  int v7; // eax
  __int64 v8; // rdx
  DWORD nSize[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[256]; // [rsp+30h] [rbp-228h] BYREF

  nSize[0] = 256;
  if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, nSize) )
    return GetLastError();
  v7 = _o__wcsicmp(a1);
  return ClRtlCleanupNode((WCHAR *)(a1 & -(__int64)(v7 != 0)), v8, a2, a3);
}

```

## disassembly

```asm
0x1800384b4  push    rbx
0x1800384b6  push    rsi
0x1800384b7  push    rdi
0x1800384b8  sub     rsp, 240h
0x1800384bf  mov     rax, cs:__security_cookie
0x1800384c6  xor     rax, rsp
0x1800384c9  mov     [rsp+258h+var_28], rax
0x1800384d1  mov     esi, r8d
0x1800384d4  mov     [rsp+258h+nSize], 100h
0x1800384dc  mov     edi, edx
0x1800384de  lea     r8, [rsp+258h+nSize]; nSize
0x1800384e3  mov     rbx, rcx
0x1800384e6  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x1800384eb  mov     ecx, 1; NameType
0x1800384f0  call    cs:__imp_GetComputerNameExW
0x1800384f6  test    eax, eax
0x1800384f8  jnz     short loc_180038502
0x1800384fa  call    cs:__imp_GetLastError
0x180038500  jmp     short loc_180038523
0x180038502  lea     rdx, [rsp+258h+Buffer]
0x180038507  mov     rcx, rbx
0x18003850a  call    cs:__imp__o__wcsicmp
0x180038510  mov     r9d, esi
0x180038513  mov     r8d, edi
0x180038516  neg     eax
0x180038518  sbb     rcx, rcx
0x18003851b  and     rcx, rbx
0x18003851e  call    ClRtlCleanupNode
0x180038523  mov     rcx, [rsp+258h+var_28]
0x18003852b  xor     rcx, rsp; StackCookie
0x18003852e  call    __security_check_cookie
0x180038533  add     rsp, 240h
0x18003853a  pop     rdi
0x18003853b  pop     rsi
0x18003853c  pop     rbx
0x18003853d  retn
```
