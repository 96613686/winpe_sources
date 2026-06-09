# SetBufferSizes

- ea: `0x18000e8ac`
- end: `0x18000ea20`
- name: `SetBufferSizes`
- size: `372`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c738`
- `0x18000f1c8`

## callees

- `0x18000e8ac`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000e92f`
- `msvcrt!wcscat_s` at `0x18000e92f`
- `msvcrt!wcsncpy_s` at `0x18000e912`
- `msvcrt!wcsncpy_s` at `0x18000e912`
- `ADVAPI32!RegCloseKey` at `0x18000e9eb`
- `ADVAPI32!RegCloseKey` at `0x18000e9eb`
- `ADVAPI32!RegQueryValueExW` at `0x18000e9a4`
- `ADVAPI32!RegQueryValueExW` at `0x18000e9da`
- `ADVAPI32!RegQueryValueExW` at `0x18000e9a4`
- `ADVAPI32!RegQueryValueExW` at `0x18000e9da`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e963`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e963`

## string_xrefs

- `0x18000e91e`: `\Mount`
- `0x18000e98d`: `ReadBuffer`
- `0x18000e9bf`: `WriteBuffer`

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
0x18000e8ac  push    rbp
0x18000e8ae  push    rbx
0x18000e8af  push    rdi
0x18000e8b0  lea     rbp, [rsp-170h]
0x18000e8b8  sub     rsp, 270h
0x18000e8bf  mov     rax, cs:__security_cookie
0x18000e8c6  xor     rax, rsp
0x18000e8c9  mov     [rbp+180h+var_20], rax
0x18000e8d0  mov     r9d, 103h; MaxCount
0x18000e8d6  mov     [rsp+280h+hKey], 0
0x18000e8df  mov     rdi, r8
0x18000e8e2  mov     dword ptr [rsp+280h+Data], 0
0x18000e8ea  mov     rbx, rcx
0x18000e8ed  mov     dword ptr [rsp+280h+var_248], 0
0x18000e8f5  xor     eax, eax
0x18000e8f7  mov     [rsp+280h+cbData], 0
0x18000e8ff  mov     r8, rdx; Source
0x18000e902  mov     [rbp+180h+var_2A], ax
0x18000e909  lea     edx, [r9+1]; SizeInWords
0x18000e90d  lea     rcx, [rsp+280h+Destination]; Destination
0x18000e912  call    cs:__imp_wcsncpy_s
0x18000e919  nop     dword ptr [rax+rax+00h]
0x18000e91e  lea     r8, aMount; "\\Mount"
0x18000e925  mov     edx, 104h; SizeInWords
0x18000e92a  lea     rcx, [rsp+280h+Destination]; Destination
0x18000e92f  call    cs:__imp_wcscat_s
0x18000e936  nop     dword ptr [rax+rax+00h]
0x18000e93b  mov     eax, 100000h
0x18000e940  lea     rdx, [rsp+280h+Destination]; lpSubKey
0x18000e945  mov     dword ptr [rsp+280h+Data], eax
0x18000e949  mov     r9d, 20019h; samDesired
0x18000e94f  mov     dword ptr [rsp+280h+var_248], eax
0x18000e953  xor     r8d, r8d; ulOptions
0x18000e956  lea     rax, [rsp+280h+hKey]
0x18000e95b  mov     rcx, rbx; hKey
0x18000e95e  mov     [rsp+280h+phkResult], rax; phkResult
0x18000e963  call    cs:__imp_RegOpenKeyExW
0x18000e96a  nop     dword ptr [rax+rax+00h]
0x18000e96f  test    eax, eax
0x18000e971  jnz     loc_18000E9F7
0x18000e977  mov     rcx, [rsp+280h+hKey]; hKey
0x18000e97c  lea     ebx, [rax+4]
0x18000e97f  lea     rax, [rsp+280h+cbData]
0x18000e984  mov     [rsp+280h+cbData], ebx
0x18000e988  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000e98d  lea     rdx, aReadbuffer; "ReadBuffer"
0x18000e994  lea     rax, [rsp+280h+Data]
0x18000e999  xor     r9d, r9d; lpType
0x18000e99c  xor     r8d, r8d; lpReserved
0x18000e99f  mov     [rsp+280h+phkResult], rax; lpData
0x18000e9a4  call    cs:__imp_RegQueryValueExW
0x18000e9ab  nop     dword ptr [rax+rax+00h]
0x18000e9b0  mov     rcx, [rsp+280h+hKey]; hKey
0x18000e9b5  lea     rax, [rsp+280h+cbData]
0x18000e9ba  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000e9bf  lea     rdx, aWritebuffer; "WriteBuffer"
0x18000e9c6  lea     rax, [rsp+280h+var_248]
0x18000e9cb  mov     [rsp+280h+cbData], ebx
0x18000e9cf  xor     r9d, r9d; lpType
0x18000e9d2  mov     [rsp+280h+phkResult], rax; lpData
0x18000e9d7  xor     r8d, r8d; lpReserved
0x18000e9da  call    cs:__imp_RegQueryValueExW
0x18000e9e1  nop     dword ptr [rax+rax+00h]
0x18000e9e6  mov     rcx, [rsp+280h+hKey]; hKey
0x18000e9eb  call    cs:__imp_RegCloseKey
0x18000e9f2  nop     dword ptr [rax+rax+00h]
0x18000e9f7  mov     eax, dword ptr [rsp+280h+Data]
0x18000e9fb  mov     [rdi+0Ch], eax
0x18000e9fe  mov     eax, dword ptr [rsp+280h+var_248]
0x18000ea02  mov     [rdi+10h], eax
0x18000ea05  mov     rcx, [rbp+180h+var_20]
0x18000ea0c  xor     rcx, rsp; StackCookie
0x18000ea0f  call    __security_check_cookie
0x18000ea14  add     rsp, 270h
0x18000ea1b  pop     rdi
0x18000ea1c  pop     rbx
0x18000ea1d  pop     rbp
0x18000ea1e  retn
```
