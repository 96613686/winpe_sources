# WriteFileAccessAndCaseOpts

- ea: `0x18000f64c`
- end: `0x18000f7a9`
- name: `WriteFileAccessAndCaseOpts`
- size: `349`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000fc20`

## callees

- `0x18000f64c`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000f6a5`
- `msvcrt!wcscpy_s` at `0x18000f6a5`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f6e6`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f6e6`
- `ADVAPI32!RegSetValueExW` at `0x18000f718`
- `ADVAPI32!RegSetValueExW` at `0x18000f74b`
- `ADVAPI32!RegSetValueExW` at `0x18000f77e`
- `ADVAPI32!RegSetValueExW` at `0x18000f718`
- `ADVAPI32!RegSetValueExW` at `0x18000f74b`
- `ADVAPI32!RegSetValueExW` at `0x18000f77e`
- `ADVAPI32!RegCloseKey` at `0x18000f789`
- `ADVAPI32!RegCloseKey` at `0x18000f789`

## string_xrefs

- `0x18000f754`: `NFSReaddir`
- `0x18000f702`: `Access`

## pseudocode

```c
LSTATUS __fastcall WriteFileAccessAndCaseOpts(HKEY hKey, wchar_t *Source, __int64 a3)
{
  LSTATUS result; // eax
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+70h] [rbp-90h] BYREF

  dwDisposition[0] = 0;
  *(_DWORD *)Data = 0;
  hKeya = 0;
  Destination[259] = 0;
  wcscpy_s(Destination, 0x104u, Source);
  result = RegCreateKeyExW(hKey, Destination, 0, 0, 0, 0xF003Fu, 0, &hKeya, dwDisposition);
  if ( !result )
  {
    RegSetValueExW(hKeya, L"Access", 0, 4u, (const BYTE *)(a3 + 32), 4u);
    *(_DWORD *)Data = (*(_DWORD *)(a3 + 56) >> 7) & 1;
    RegSetValueExW(hKeya, L"NFSLookup", 0, 4u, Data, 4u);
    *(_DWORD *)Data = (*(_DWORD *)(a3 + 56) >> 8) & 1;
    RegSetValueExW(hKeya, L"NFSReaddir", 0, 4u, Data, 4u);
    return RegCloseKey(hKeya);
  }
  return result;
}

```

## disassembly

```asm
0x18000f64c  push    rbp
0x18000f64e  push    rbx
0x18000f64f  push    rdi
0x18000f650  lea     rbp, [rsp-190h]
0x18000f658  sub     rsp, 290h
0x18000f65f  mov     rax, cs:__security_cookie
0x18000f666  xor     rax, rsp
0x18000f669  mov     [rbp+1A0h+var_20], rax
0x18000f670  mov     rdi, r8
0x18000f673  mov     [rsp+2A0h+dwDisposition], 0
0x18000f67b  mov     r8, rdx; Source
0x18000f67e  mov     dword ptr [rsp+2A0h+Data], 0
0x18000f686  mov     rbx, rcx
0x18000f689  mov     [rsp+2A0h+hKey], 0
0x18000f692  xor     eax, eax
0x18000f694  lea     rcx, [rsp+2A0h+Destination]; Destination
0x18000f699  mov     edx, 104h; SizeInWords
0x18000f69e  mov     [rbp+1A0h+var_2A], ax
0x18000f6a5  call    cs:__imp_wcscpy_s
0x18000f6ab  lea     rax, [rsp+2A0h+dwDisposition]
0x18000f6b0  xor     r9d, r9d; lpClass
0x18000f6b3  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x18000f6b8  lea     rdx, [rsp+2A0h+Destination]; lpSubKey
0x18000f6bd  lea     rax, [rsp+2A0h+hKey]
0x18000f6c2  xor     r8d, r8d; Reserved
0x18000f6c5  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18000f6ca  mov     rcx, rbx; hKey
0x18000f6cd  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000f6d6  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x18000f6de  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x18000f6e6  call    cs:__imp_RegCreateKeyExW
0x18000f6ec  test    eax, eax
0x18000f6ee  jnz     loc_18000F78F
0x18000f6f4  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f6f9  lea     rax, [rdi+20h]
0x18000f6fd  mov     ebx, 4
0x18000f702  lea     rdx, aAccess; "Access"
0x18000f709  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18000f70d  mov     r9d, ebx; dwType
0x18000f710  xor     r8d, r8d; Reserved
0x18000f713  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18000f718  call    cs:__imp_RegSetValueExW
0x18000f71e  mov     eax, [rdi+38h]
0x18000f721  lea     rdx, aNfslookup; "NFSLookup"
0x18000f728  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f72d  mov     r9d, ebx; dwType
0x18000f730  shr     eax, 7
0x18000f733  xor     r8d, r8d; Reserved
0x18000f736  and     eax, 1
0x18000f739  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18000f73d  mov     dword ptr [rsp+2A0h+Data], eax
0x18000f741  lea     rax, [rsp+2A0h+Data]
0x18000f746  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18000f74b  call    cs:__imp_RegSetValueExW
0x18000f751  mov     eax, [rdi+38h]
0x18000f754  lea     rdx, aNfsreaddir; "NFSReaddir"
0x18000f75b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f760  mov     r9d, ebx; dwType
0x18000f763  shr     eax, 8
0x18000f766  xor     r8d, r8d; Reserved
0x18000f769  and     eax, 1
0x18000f76c  mov     [rsp+2A0h+samDesired], ebx; cbData
0x18000f770  mov     dword ptr [rsp+2A0h+Data], eax
0x18000f774  lea     rax, [rsp+2A0h+Data]
0x18000f779  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18000f77e  call    cs:__imp_RegSetValueExW
0x18000f784  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000f789  call    cs:__imp_RegCloseKey
0x18000f78f  mov     rcx, [rbp+1A0h+var_20]
0x18000f796  xor     rcx, rsp; StackCookie
0x18000f799  call    __security_check_cookie
0x18000f79e  add     rsp, 290h
0x18000f7a5  pop     rdi
0x18000f7a6  pop     rbx
0x18000f7a7  pop     rbp
0x18000f7a8  retn
```
