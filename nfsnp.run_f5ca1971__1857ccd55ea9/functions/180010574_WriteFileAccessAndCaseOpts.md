# WriteFileAccessAndCaseOpts

- ea: `0x180010574`
- end: `0x1800106f6`
- name: `WriteFileAccessAndCaseOpts`
- size: `386`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180010bec`

## callees

- `0x180010574`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800105cd`
- `msvcrt!wcscpy_s` at `0x1800105cd`
- `ADVAPI32!RegCreateKeyExW` at `0x180010614`
- `ADVAPI32!RegCreateKeyExW` at `0x180010614`
- `ADVAPI32!RegSetValueExW` at `0x18001064c`
- `ADVAPI32!RegSetValueExW` at `0x180010685`
- `ADVAPI32!RegSetValueExW` at `0x1800106be`
- `ADVAPI32!RegSetValueExW` at `0x18001064c`
- `ADVAPI32!RegSetValueExW` at `0x180010685`
- `ADVAPI32!RegSetValueExW` at `0x1800106be`
- `ADVAPI32!RegCloseKey` at `0x1800106cf`
- `ADVAPI32!RegCloseKey` at `0x1800106cf`

## string_xrefs

- `0x180010694`: `NFSReaddir`
- `0x180010636`: `Access`

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
0x180010574  push    rbp
0x180010576  push    rbx
0x180010577  push    rdi
0x180010578  lea     rbp, [rsp-190h]
0x180010580  sub     rsp, 290h
0x180010587  mov     rax, cs:__security_cookie
0x18001058e  xor     rax, rsp
0x180010591  mov     [rbp+1A0h+var_20], rax
0x180010598  mov     rdi, r8
0x18001059b  mov     [rsp+2A0h+dwDisposition], 0
0x1800105a3  mov     r8, rdx; Source
0x1800105a6  mov     dword ptr [rsp+2A0h+Data], 0
0x1800105ae  mov     rbx, rcx
0x1800105b1  mov     [rsp+2A0h+hKey], 0
0x1800105ba  xor     eax, eax
0x1800105bc  lea     rcx, [rsp+2A0h+Destination]; Destination
0x1800105c1  mov     edx, 104h; SizeInWords
0x1800105c6  mov     [rbp+1A0h+var_2A], ax
0x1800105cd  call    cs:__imp_wcscpy_s
0x1800105d4  nop     dword ptr [rax+rax+00h]
0x1800105d9  lea     rax, [rsp+2A0h+dwDisposition]
0x1800105de  xor     r9d, r9d; lpClass
0x1800105e1  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x1800105e6  lea     rdx, [rsp+2A0h+Destination]; lpSubKey
0x1800105eb  lea     rax, [rsp+2A0h+hKey]
0x1800105f0  xor     r8d, r8d; Reserved
0x1800105f3  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800105f8  mov     rcx, rbx; hKey
0x1800105fb  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010604  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x18001060c  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x180010614  call    cs:__imp_RegCreateKeyExW
0x18001061b  nop     dword ptr [rax+rax+00h]
0x180010620  test    eax, eax
0x180010622  jnz     loc_1800106DB
0x180010628  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001062d  lea     rax, [rdi+20h]
0x180010631  mov     ebx, 4
0x180010636  lea     rdx, aAccess; "Access"
0x18001063d  mov     [rsp+2A0h+samDesired], ebx; cbData
0x180010641  mov     r9d, ebx; dwType
0x180010644  xor     r8d, r8d; Reserved
0x180010647  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18001064c  call    cs:__imp_RegSetValueExW
0x180010653  nop     dword ptr [rax+rax+00h]
0x180010658  mov     eax, [rdi+38h]
0x18001065b  lea     rdx, aNfslookup; "NFSLookup"
0x180010662  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180010667  mov     r9d, ebx; dwType
0x18001066a  shr     eax, 7
0x18001066d  xor     r8d, r8d; Reserved
0x180010670  and     eax, 1
0x180010673  mov     [rsp+2A0h+samDesired], ebx; cbData
0x180010677  mov     dword ptr [rsp+2A0h+Data], eax
0x18001067b  lea     rax, [rsp+2A0h+Data]
0x180010680  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x180010685  call    cs:__imp_RegSetValueExW
0x18001068c  nop     dword ptr [rax+rax+00h]
0x180010691  mov     eax, [rdi+38h]
0x180010694  lea     rdx, aNfsreaddir; "NFSReaddir"
0x18001069b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800106a0  mov     r9d, ebx; dwType
0x1800106a3  shr     eax, 8
0x1800106a6  xor     r8d, r8d; Reserved
0x1800106a9  and     eax, 1
0x1800106ac  mov     [rsp+2A0h+samDesired], ebx; cbData
0x1800106b0  mov     dword ptr [rsp+2A0h+Data], eax
0x1800106b4  lea     rax, [rsp+2A0h+Data]
0x1800106b9  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x1800106be  call    cs:__imp_RegSetValueExW
0x1800106c5  nop     dword ptr [rax+rax+00h]
0x1800106ca  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800106cf  call    cs:__imp_RegCloseKey
0x1800106d6  nop     dword ptr [rax+rax+00h]
0x1800106db  mov     rcx, [rbp+1A0h+var_20]
0x1800106e2  xor     rcx, rsp; StackCookie
0x1800106e5  call    __security_check_cookie
0x1800106ea  add     rsp, 290h
0x1800106f1  pop     rdi
0x1800106f2  pop     rbx
0x1800106f3  pop     rbp
0x1800106f4  retn
```
