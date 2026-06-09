# RasTlsGetLocalMachineName(ushort * *)

- ea: `0x180032a98`
- end: `0x180032b5d`
- name: `?RasTlsGetLocalMachineName@@YAKPEAPEAG@Z`
- size: `197`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002318c`
- `0x180075400`

## callees

- `0x180032a98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032af3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032af3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032b3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032b3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180032abb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180032b24`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180032abb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180032b24`

## pseudocode

```c
__int64 __fastcall RasTlsGetLocalMachineName(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rdi
  DWORD LastError; // ebx
  WCHAR *v4; // rax
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF

  nSize = 0;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize)
    || (v2 = 0, LastError = GetLastError(), LastError == 234) )
  {
    v4 = (WCHAR *)LocalAlloc(0x40u, 2LL * nSize + 2);
    v2 = v4;
    if ( v4 && GetComputerNameExW(ComputerNameDnsFullyQualified, v4, &nSize) )
    {
      *a1 = v2;
      v2 = 0;
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  LocalFree(v2);
  return LastError;
}

```

## disassembly

```asm
0x180032a98  mov     rax, rsp
0x180032a9b  mov     [rax+8], rbx
0x180032a9f  mov     [rax+18h], rsi
0x180032aa3  push    rdi
0x180032aa4  sub     rsp, 20h
0x180032aa8  xor     edx, edx; lpBuffer
0x180032aaa  mov     dword ptr [rax+10h], 0
0x180032ab1  mov     rsi, rcx
0x180032ab4  lea     r8, [rax+10h]; nSize
0x180032ab8  lea     ecx, [rdx+3]; NameType
0x180032abb  call    cs:__imp_GetComputerNameExW
0x180032ac2  nop     dword ptr [rax+rax+00h]
0x180032ac7  test    eax, eax
0x180032ac9  jnz     short loc_180032AE2
0x180032acb  xor     edi, edi
0x180032acd  call    cs:__imp_GetLastError
0x180032ad4  nop     dword ptr [rax+rax+00h]
0x180032ad9  mov     ebx, eax
0x180032adb  cmp     eax, 0EAh
0x180032ae0  jnz     short loc_180032B3B
0x180032ae2  mov     edx, [rsp+28h+nSize]
0x180032ae6  mov     ecx, 40h ; '@'; uFlags
0x180032aeb  lea     rdx, ds:2[rdx*2]; uBytes
0x180032af3  call    cs:__imp_LocalAlloc
0x180032afa  nop     dword ptr [rax+rax+00h]
0x180032aff  mov     rdi, rax
0x180032b02  test    rax, rax
0x180032b05  jnz     short loc_180032B17
0x180032b07  call    cs:__imp_GetLastError
0x180032b0e  nop     dword ptr [rax+rax+00h]
0x180032b13  mov     ebx, eax
0x180032b15  jmp     short loc_180032B3B
0x180032b17  lea     r8, [rsp+28h+nSize]; nSize
0x180032b1c  mov     rdx, rdi; lpBuffer
0x180032b1f  mov     ecx, 3; NameType
0x180032b24  call    cs:__imp_GetComputerNameExW
0x180032b2b  nop     dword ptr [rax+rax+00h]
0x180032b30  test    eax, eax
0x180032b32  jz      short loc_180032B07
0x180032b34  mov     [rsi], rdi
0x180032b37  xor     edi, edi
0x180032b39  xor     ebx, ebx
0x180032b3b  mov     rcx, rdi; hMem
0x180032b3e  call    cs:__imp_LocalFree
0x180032b45  nop     dword ptr [rax+rax+00h]
0x180032b4a  mov     rsi, [rsp+28h+arg_10]
0x180032b4f  mov     eax, ebx
0x180032b51  mov     rbx, [rsp+28h+arg_0]
0x180032b56  add     rsp, 20h
0x180032b5a  pop     rdi
0x180032b5b  retn
```
