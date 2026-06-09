# CFveApiBase::OkToExportKey(void)

- ea: `0x180046094`
- end: `0x180046145`
- name: `?OkToExportKey@CFveApiBase@@SAJXZ`
- size: `177`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d5a0`
- `0x1800771dc`
- `0x180077da0`
- `0x1800bae5c`

## callees

- `0x180046094`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800460bc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800460bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004611e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801209fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004611e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801209fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800460f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800460f1`

## pseudocode

```c
__int64 CFveApiBase::OkToExportKey(void)
{
  int v0; // edi
  unsigned int v1; // ebx
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  v0 = 0;
  if ( ((unsigned __int8)TlsGetValue(CFveApiBase::_TlsIndex) & 1) != 0 )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, 0, 0, 0x20019u, &hKey) )
      v0 = -2144272328;
    v1 = v0;
  }
  else
  {
    v1 = -2144272328;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180046094  mov     [rsp+arg_0], rbx
0x180046099  push    rdi
0x18004609a  sub     rsp, 50h
0x18004609e  mov     rax, cs:__security_cookie
0x1800460a5  xor     rax, rsp
0x1800460a8  mov     [rsp+58h+var_18], rax
0x1800460ad  mov     [rsp+58h+hKey], 0
0x1800460b6  mov     ecx, cs:?_TlsIndex@CFveApiBase@@1KA; dwTlsIndex
0x1800460bc  call    cs:__imp_TlsGetValue
0x1800460c3  nop     dword ptr [rax+rax+00h]
0x1800460c8  and     al, 1
0x1800460ca  mov     edi, 0
0x1800460cf  mov     [rsp+58h+var_24], edi
0x1800460d3  jz      short loc_18004610B
0x1800460d5  lea     rax, [rsp+58h+hKey]
0x1800460da  mov     [rsp+58h+phkResult], rax; phkResult
0x1800460df  mov     r9d, 20019h; samDesired
0x1800460e5  xor     r8d, r8d; ulOptions
0x1800460e8  xor     edx, edx; lpSubKey
0x1800460ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800460f1  call    cs:__imp_RegOpenKeyExW
0x1800460f8  nop     dword ptr [rax+rax+00h]
0x1800460fd  mov     ebx, 80310038h
0x180046102  test    eax, eax
0x180046104  cmovnz  edi, ebx
0x180046107  mov     ebx, edi
0x180046109  jmp     short loc_180046110
0x18004610b  mov     ebx, 80310038h
0x180046110  mov     [rsp+58h+var_24], ebx
0x180046114  mov     rcx, [rsp+58h+hKey]; hKey
0x180046119  test    rcx, rcx
0x18004611c  jz      short loc_18004612A
0x18004611e  call    cs:__imp_RegCloseKey
0x180046125  nop     dword ptr [rax+rax+00h]
0x18004612a  mov     eax, ebx
0x18004612c  mov     rcx, [rsp+58h+var_18]
0x180046131  xor     rcx, rsp; StackCookie
0x180046134  call    __security_check_cookie
0x180046139  mov     rbx, [rsp+58h+arg_0]
0x18004613e  add     rsp, 50h
0x180046142  pop     rdi
0x180046143  retn
0x1801209e8  push    rbp
0x1801209ea  sub     rsp, 30h
0x1801209ee  mov     rbp, rdx
0x1801209f1  mov     rcx, [rbp+38h]; hKey
0x1801209f5  test    rcx, rcx
0x1801209f8  jz      short loc_180120A07
0x1801209fa  call    cs:__imp_RegCloseKey
0x180120a01  nop     dword ptr [rax+rax+00h]
0x180120a06  nop
0x180120a07  add     rsp, 30h
0x180120a0b  pop     rbp
0x180120a0c  retn
```
