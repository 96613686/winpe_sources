# SetBufferSizes

- ea: `0x18000dc1c`
- end: `0x18000dd67`
- name: `SetBufferSizes`
- size: `331`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000be24`
- `0x18000e454`

## callees

- `0x18000dc1c`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000dc99`
- `msvcrt!wcscat_s` at `0x18000dc99`
- `msvcrt!wcsncpy_s` at `0x18000dc82`
- `msvcrt!wcsncpy_s` at `0x18000dc82`
- `ADVAPI32!RegCloseKey` at `0x18000dd39`
- `ADVAPI32!RegCloseKey` at `0x18000dd39`
- `ADVAPI32!RegQueryValueExW` at `0x18000dcfe`
- `ADVAPI32!RegQueryValueExW` at `0x18000dd2e`
- `ADVAPI32!RegQueryValueExW` at `0x18000dcfe`
- `ADVAPI32!RegQueryValueExW` at `0x18000dd2e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dcc7`
- `ADVAPI32!RegOpenKeyExW` at `0x18000dcc7`

## string_xrefs

- `0x18000dc88`: `\Mount`
- `0x18000dce7`: `ReadBuffer`
- `0x18000dd13`: `WriteBuffer`

## pseudocode

```c
__int64 __fastcall SetBufferSizes(HKEY hKey, wchar_t *Source, __int64 a3)
{
  __int64 result; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v8[4]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Destination[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKeya = 0;
  cbData = 0;
  Destination[259] = 0;
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  *(_DWORD *)Data = 0x100000;
  *(_DWORD *)v8 = 0x100000;
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    cbData = 4;
    RegQueryValueExW(hKeya, L"ReadBuffer", 0, 0, Data, &cbData);
    cbData = 4;
    RegQueryValueExW(hKeya, L"WriteBuffer", 0, 0, v8, &cbData);
    RegCloseKey(hKeya);
  }
  *(_DWORD *)(a3 + 12) = *(_DWORD *)Data;
  result = *(unsigned int *)v8;
  *(_DWORD *)(a3 + 16) = *(_DWORD *)v8;
  return result;
}

```

## disassembly

```asm
0x18000dc1c  push    rbp
0x18000dc1e  push    rbx
0x18000dc1f  push    rdi
0x18000dc20  lea     rbp, [rsp-170h]
0x18000dc28  sub     rsp, 270h
0x18000dc2f  mov     rax, cs:__security_cookie
0x18000dc36  xor     rax, rsp
0x18000dc39  mov     [rbp+180h+var_20], rax
0x18000dc40  mov     r9d, 103h; MaxCount
0x18000dc46  mov     [rsp+280h+hKey], 0
0x18000dc4f  mov     rdi, r8
0x18000dc52  mov     dword ptr [rsp+280h+Data], 0
0x18000dc5a  mov     rbx, rcx
0x18000dc5d  mov     dword ptr [rsp+280h+var_248], 0
0x18000dc65  xor     eax, eax
0x18000dc67  mov     [rsp+280h+cbData], 0
0x18000dc6f  mov     r8, rdx; Source
0x18000dc72  mov     [rbp+180h+var_2A], ax
0x18000dc79  lea     edx, [r9+1]; SizeInWords
0x18000dc7d  lea     rcx, [rsp+280h+Destination]; Destination
0x18000dc82  call    cs:__imp_wcsncpy_s
0x18000dc88  lea     r8, aMount; "\\Mount"
0x18000dc8f  mov     edx, 104h; SizeInWords
0x18000dc94  lea     rcx, [rsp+280h+Destination]; Destination
0x18000dc99  call    cs:__imp_wcscat_s
0x18000dc9f  mov     eax, 100000h
0x18000dca4  lea     rdx, [rsp+280h+Destination]; lpSubKey
0x18000dca9  mov     dword ptr [rsp+280h+Data], eax
0x18000dcad  mov     r9d, 20019h; samDesired
0x18000dcb3  mov     dword ptr [rsp+280h+var_248], eax
0x18000dcb7  xor     r8d, r8d; ulOptions
0x18000dcba  lea     rax, [rsp+280h+hKey]
0x18000dcbf  mov     rcx, rbx; hKey
0x18000dcc2  mov     [rsp+280h+phkResult], rax; phkResult
0x18000dcc7  call    cs:__imp_RegOpenKeyExW
0x18000dccd  test    eax, eax
0x18000dccf  jnz     short loc_18000DD3F
0x18000dcd1  mov     rcx, [rsp+280h+hKey]; hKey
0x18000dcd6  lea     ebx, [rax+4]
0x18000dcd9  lea     rax, [rsp+280h+cbData]
0x18000dcde  mov     [rsp+280h+cbData], ebx
0x18000dce2  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000dce7  lea     rdx, aReadbuffer; "ReadBuffer"
0x18000dcee  lea     rax, [rsp+280h+Data]
0x18000dcf3  xor     r9d, r9d; lpType
0x18000dcf6  xor     r8d, r8d; lpReserved
0x18000dcf9  mov     [rsp+280h+phkResult], rax; lpData
0x18000dcfe  call    cs:__imp_RegQueryValueExW
0x18000dd04  mov     rcx, [rsp+280h+hKey]; hKey
0x18000dd09  lea     rax, [rsp+280h+cbData]
0x18000dd0e  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000dd13  lea     rdx, aWritebuffer; "WriteBuffer"
0x18000dd1a  lea     rax, [rsp+280h+var_248]
0x18000dd1f  mov     [rsp+280h+cbData], ebx
0x18000dd23  xor     r9d, r9d; lpType
0x18000dd26  mov     [rsp+280h+phkResult], rax; lpData
0x18000dd2b  xor     r8d, r8d; lpReserved
0x18000dd2e  call    cs:__imp_RegQueryValueExW
0x18000dd34  mov     rcx, [rsp+280h+hKey]; hKey
0x18000dd39  call    cs:__imp_RegCloseKey
0x18000dd3f  mov     eax, dword ptr [rsp+280h+Data]
0x18000dd43  mov     [rdi+0Ch], eax
0x18000dd46  mov     eax, dword ptr [rsp+280h+var_248]
0x18000dd4a  mov     [rdi+10h], eax
0x18000dd4d  mov     rcx, [rbp+180h+var_20]
0x18000dd54  xor     rcx, rsp; StackCookie
0x18000dd57  call    __security_check_cookie
0x18000dd5c  add     rsp, 270h
0x18000dd63  pop     rdi
0x18000dd64  pop     rbx
0x18000dd65  pop     rbp
0x18000dd66  retn
```
