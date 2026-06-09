# SetMountType

- ea: `0x18000f264`
- end: `0x18000f37e`
- name: `SetMountType`
- size: `282`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c738`
- `0x18000f1c8`

## callees

- `0x18000f264`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f2df`
- `msvcrt!wcscat_s` at `0x18000f2df`
- `msvcrt!wcsncpy_s` at `0x18000f2c2`
- `msvcrt!wcsncpy_s` at `0x18000f2c2`
- `ADVAPI32!RegCloseKey` at `0x18000f34d`
- `ADVAPI32!RegCloseKey` at `0x18000f34d`
- `ADVAPI32!RegQueryValueExW` at `0x18000f33c`
- `ADVAPI32!RegQueryValueExW` at `0x18000f33c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f306`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f306`

## string_xrefs

- `0x18000f2ce`: `\Mount`
- `0x18000f325`: `MountType`

## pseudocode

```c
__int64 __fastcall SetMountType(HKEY hKey, wchar_t *Source, __int64 a3)
{
  __int64 result; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  *(_DWORD *)Data = 1;
  cbData = 4;
  Destination[259] = 0;
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    RegQueryValueExW(hKeya, L"MountType", 0, 0, Data, &cbData);
    RegCloseKey(hKeya);
  }
  result = *(unsigned int *)Data;
  *(_DWORD *)(*(_QWORD *)a3 + 28LL) = *(_DWORD *)Data;
  return result;
}

```

## disassembly

```asm
0x18000f264  push    rbp
0x18000f266  push    rbx
0x18000f267  push    rdi
0x18000f268  lea     rbp, [rsp-160h]
0x18000f270  sub     rsp, 260h
0x18000f277  mov     rax, cs:__security_cookie
0x18000f27e  xor     rax, rsp
0x18000f281  mov     [rbp+170h+var_20], rax
0x18000f288  mov     r9d, 103h; MaxCount
0x18000f28e  mov     [rsp+270h+hKey], 0
0x18000f297  mov     rdi, r8
0x18000f29a  mov     dword ptr [rsp+270h+Data], 1
0x18000f2a2  mov     rbx, rcx
0x18000f2a5  mov     [rsp+270h+cbData], 4
0x18000f2ad  xor     eax, eax
0x18000f2af  lea     rcx, [rsp+270h+Destination]; Destination
0x18000f2b4  mov     r8, rdx; Source
0x18000f2b7  mov     [rbp+170h+var_2A], ax
0x18000f2be  lea     edx, [r9+1]; SizeInWords
0x18000f2c2  call    cs:__imp_wcsncpy_s
0x18000f2c9  nop     dword ptr [rax+rax+00h]
0x18000f2ce  lea     r8, aMount; "\\Mount"
0x18000f2d5  mov     edx, 104h; SizeInWords
0x18000f2da  lea     rcx, [rsp+270h+Destination]; Destination
0x18000f2df  call    cs:__imp_wcscat_s
0x18000f2e6  nop     dword ptr [rax+rax+00h]
0x18000f2eb  lea     rax, [rsp+270h+hKey]
0x18000f2f0  mov     r9d, 20019h; samDesired
0x18000f2f6  xor     r8d, r8d; ulOptions
0x18000f2f9  mov     [rsp+270h+phkResult], rax; phkResult
0x18000f2fe  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000f303  mov     rcx, rbx; hKey
0x18000f306  call    cs:__imp_RegOpenKeyExW
0x18000f30d  nop     dword ptr [rax+rax+00h]
0x18000f312  test    eax, eax
0x18000f314  jnz     short loc_18000F359
0x18000f316  mov     rcx, [rsp+270h+hKey]; hKey
0x18000f31b  lea     rax, [rsp+270h+cbData]
0x18000f320  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000f325  lea     rdx, aMounttype; "MountType"
0x18000f32c  lea     rax, [rsp+270h+Data]
0x18000f331  xor     r9d, r9d; lpType
0x18000f334  xor     r8d, r8d; lpReserved
0x18000f337  mov     [rsp+270h+phkResult], rax; lpData
0x18000f33c  call    cs:__imp_RegQueryValueExW
0x18000f343  nop     dword ptr [rax+rax+00h]
0x18000f348  mov     rcx, [rsp+270h+hKey]; hKey
0x18000f34d  call    cs:__imp_RegCloseKey
0x18000f354  nop     dword ptr [rax+rax+00h]
0x18000f359  mov     rcx, [rdi]
0x18000f35c  mov     eax, dword ptr [rsp+270h+Data]
0x18000f360  mov     [rcx+1Ch], eax
0x18000f363  mov     rcx, [rbp+170h+var_20]
0x18000f36a  xor     rcx, rsp; StackCookie
0x18000f36d  call    __security_check_cookie
0x18000f372  add     rsp, 260h
0x18000f379  pop     rdi
0x18000f37a  pop     rbx
0x18000f37b  pop     rbp
0x18000f37c  retn
```
