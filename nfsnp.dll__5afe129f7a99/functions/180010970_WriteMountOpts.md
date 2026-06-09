# WriteMountOpts

- ea: `0x180010970`
- end: `0x180010be3`
- name: `WriteMountOpts`
- size: `627`
- prototype: `LSTATUS __fastcall(HKEY hKey, wchar_t *Source, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010bec`

## callees

- `0x180010970`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800109e6`
- `msvcrt!wcscat_s` at `0x1800109e6`
- `msvcrt!wcscpy_s` at `0x1800109c9`
- `msvcrt!wcscpy_s` at `0x1800109c9`
- `ADVAPI32!RegCreateKeyExW` at `0x180010a2d`
- `ADVAPI32!RegCreateKeyExW` at `0x180010a2d`
- `ADVAPI32!RegSetValueExW` at `0x180010a65`
- `ADVAPI32!RegSetValueExW` at `0x180010a90`
- `ADVAPI32!RegSetValueExW` at `0x180010abb`
- `ADVAPI32!RegSetValueExW` at `0x180010ae6`
- `ADVAPI32!RegSetValueExW` at `0x180010b11`
- `ADVAPI32!RegSetValueExW` at `0x180010b3c`
- `ADVAPI32!RegSetValueExW` at `0x180010b72`
- `ADVAPI32!RegSetValueExW` at `0x180010bab`
- `ADVAPI32!RegSetValueExW` at `0x180010a65`
- `ADVAPI32!RegSetValueExW` at `0x180010a90`
- `ADVAPI32!RegSetValueExW` at `0x180010abb`
- `ADVAPI32!RegSetValueExW` at `0x180010ae6`
- `ADVAPI32!RegSetValueExW` at `0x180010b11`
- `ADVAPI32!RegSetValueExW` at `0x180010b3c`
- `ADVAPI32!RegSetValueExW` at `0x180010b72`
- `ADVAPI32!RegSetValueExW` at `0x180010bab`
- `ADVAPI32!RegCloseKey` at `0x180010bbc`
- `ADVAPI32!RegCloseKey` at `0x180010bbc`

## string_xrefs

- `0x1800109d5`: `\Mount`
- `0x180010a4f`: `ReadBuffer`
- `0x180010a7e`: `WriteBuffer`
- `0x180010aff`: `MountType`

## pseudocode

```c
LSTATUS __fastcall WriteMountOpts(HKEY hKey, wchar_t *Source, __int64 a3)
{
  LSTATUS result; // eax
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+5Ch] [rbp-A4h] BYREF
  wchar_t Destination[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKeya = 0;
  dwDisposition = 0;
  *(_DWORD *)Data = 0;
  Destination[259] = 0;
  wcscpy_s(Destination, 0x104u, Source);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  result = RegCreateKeyExW(hKey, Destination, 0, 0, 0, 0xF003Fu, 0, &hKeya, &dwDisposition);
  if ( !result )
  {
    RegSetValueExW(hKeya, L"ReadBuffer", 0, 4u, (const BYTE *)(a3 + 12), 4u);
    RegSetValueExW(hKeya, L"WriteBuffer", 0, 4u, (const BYTE *)(a3 + 16), 4u);
    RegSetValueExW(hKeya, L"Timeout", 0, 4u, (const BYTE *)(a3 + 20), 4u);
    RegSetValueExW(hKeya, L"Retransmissions", 0, 4u, (const BYTE *)(a3 + 24), 4u);
    RegSetValueExW(hKeya, L"MountType", 0, 4u, (const BYTE *)(a3 + 28), 4u);
    RegSetValueExW(hKeya, L"SecFlavors", 0, 4u, (const BYTE *)(a3 + 60), 4u);
    *(_DWORD *)Data = *(_DWORD *)(a3 + 56) & 1;
    RegSetValueExW(hKeya, L"Locking", 0, 4u, Data, 4u);
    *(_DWORD *)Data = (*(_DWORD *)(a3 + 56) >> 2) & 1;
    RegSetValueExW(hKeya, L"Version3", 0, 4u, Data, 4u);
    return RegCloseKey(hKeya);
  }
  return result;
}

```

## disassembly

```asm
0x180010970  push    rbp
0x180010972  push    rbx
0x180010973  push    rdi
0x180010974  lea     rbp, [rsp-180h]
0x18001097c  sub     rsp, 280h
0x180010983  mov     rax, cs:__security_cookie
0x18001098a  xor     rax, rsp
0x18001098d  mov     [rbp+190h+var_20], rax
0x180010994  mov     rdi, r8
0x180010997  mov     [rsp+290h+hKey], 0
0x1800109a0  mov     r8, rdx; Source
0x1800109a3  mov     [rsp+290h+dwDisposition], 0
0x1800109ab  mov     rbx, rcx
0x1800109ae  mov     dword ptr [rsp+290h+Data], 0
0x1800109b6  xor     eax, eax
0x1800109b8  lea     rcx, [rsp+290h+Destination]; Destination
0x1800109bd  mov     edx, 104h; SizeInWords
0x1800109c2  mov     [rbp+190h+var_2A], ax
0x1800109c9  call    cs:__imp_wcscpy_s
0x1800109d0  nop     dword ptr [rax+rax+00h]
0x1800109d5  lea     r8, aMount; "\\Mount"
0x1800109dc  mov     edx, 104h; SizeInWords
0x1800109e1  lea     rcx, [rsp+290h+Destination]; Destination
0x1800109e6  call    cs:__imp_wcscat_s
0x1800109ed  nop     dword ptr [rax+rax+00h]
0x1800109f2  lea     rax, [rsp+290h+dwDisposition]
0x1800109f7  xor     r9d, r9d; lpClass
0x1800109fa  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x1800109ff  lea     rdx, [rsp+290h+Destination]; lpSubKey
0x180010a04  lea     rax, [rsp+290h+hKey]
0x180010a09  xor     r8d, r8d; Reserved
0x180010a0c  mov     [rsp+290h+phkResult], rax; phkResult
0x180010a11  mov     rcx, rbx; hKey
0x180010a14  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010a1d  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x180010a25  mov     [rsp+290h+dwOptions], 0; dwOptions
0x180010a2d  call    cs:__imp_RegCreateKeyExW
0x180010a34  nop     dword ptr [rax+rax+00h]
0x180010a39  test    eax, eax
0x180010a3b  jnz     loc_180010BC8
0x180010a41  mov     rcx, [rsp+290h+hKey]; hKey
0x180010a46  lea     rax, [rdi+0Ch]
0x180010a4a  mov     ebx, 4
0x180010a4f  lea     rdx, aReadbuffer; "ReadBuffer"
0x180010a56  mov     [rsp+290h+samDesired], ebx; cbData
0x180010a5a  mov     r9d, ebx; dwType
0x180010a5d  xor     r8d, r8d; Reserved
0x180010a60  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180010a65  call    cs:__imp_RegSetValueExW
0x180010a6c  nop     dword ptr [rax+rax+00h]
0x180010a71  mov     rcx, [rsp+290h+hKey]; hKey
0x180010a76  lea     rax, [rdi+10h]
0x180010a7a  mov     [rsp+290h+samDesired], ebx; cbData
0x180010a7e  lea     rdx, aWritebuffer; "WriteBuffer"
0x180010a85  mov     r9d, ebx; dwType
0x180010a88  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180010a8d  xor     r8d, r8d; Reserved
0x180010a90  call    cs:__imp_RegSetValueExW
0x180010a97  nop     dword ptr [rax+rax+00h]
0x180010a9c  mov     rcx, [rsp+290h+hKey]; hKey
0x180010aa1  lea     rax, [rdi+14h]
0x180010aa5  mov     [rsp+290h+samDesired], ebx; cbData
0x180010aa9  lea     rdx, aTimeout; "Timeout"
0x180010ab0  mov     r9d, ebx; dwType
0x180010ab3  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180010ab8  xor     r8d, r8d; Reserved
0x180010abb  call    cs:__imp_RegSetValueExW
0x180010ac2  nop     dword ptr [rax+rax+00h]
0x180010ac7  mov     rcx, [rsp+290h+hKey]; hKey
0x180010acc  lea     rax, [rdi+18h]
0x180010ad0  mov     [rsp+290h+samDesired], ebx; cbData
0x180010ad4  lea     rdx, aRetransmission; "Retransmissions"
0x180010adb  mov     r9d, ebx; dwType
0x180010ade  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180010ae3  xor     r8d, r8d; Reserved
0x180010ae6  call    cs:__imp_RegSetValueExW
0x180010aed  nop     dword ptr [rax+rax+00h]
0x180010af2  mov     rcx, [rsp+290h+hKey]; hKey
0x180010af7  lea     rax, [rdi+1Ch]
0x180010afb  mov     [rsp+290h+samDesired], ebx; cbData
0x180010aff  lea     rdx, aMounttype; "MountType"
0x180010b06  mov     r9d, ebx; dwType
0x180010b09  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180010b0e  xor     r8d, r8d; Reserved
0x180010b11  call    cs:__imp_RegSetValueExW
0x180010b18  nop     dword ptr [rax+rax+00h]
0x180010b1d  mov     rcx, [rsp+290h+hKey]; hKey
0x180010b22  lea     rax, [rdi+3Ch]
0x180010b26  mov     [rsp+290h+samDesired], ebx; cbData
0x180010b2a  lea     rdx, aSecflavors; "SecFlavors"
0x180010b31  mov     r9d, ebx; dwType
0x180010b34  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180010b39  xor     r8d, r8d; Reserved
0x180010b3c  call    cs:__imp_RegSetValueExW
0x180010b43  nop     dword ptr [rax+rax+00h]
0x180010b48  mov     eax, [rdi+38h]
0x180010b4b  lea     rdx, aLocking; "Locking"
0x180010b52  mov     rcx, [rsp+290h+hKey]; hKey
0x180010b57  and     eax, 1
0x180010b5a  mov     dword ptr [rsp+290h+Data], eax
0x180010b5e  mov     r9d, ebx; dwType
0x180010b61  lea     rax, [rsp+290h+Data]
0x180010b66  mov     [rsp+290h+samDesired], ebx; cbData
0x180010b6a  xor     r8d, r8d; Reserved
0x180010b6d  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180010b72  call    cs:__imp_RegSetValueExW
0x180010b79  nop     dword ptr [rax+rax+00h]
0x180010b7e  mov     eax, [rdi+38h]
0x180010b81  lea     rdx, aVersion3; "Version3"
0x180010b88  mov     rcx, [rsp+290h+hKey]; hKey
0x180010b8d  mov     r9d, ebx; dwType
0x180010b90  shr     eax, 2
0x180010b93  xor     r8d, r8d; Reserved
0x180010b96  and     eax, 1
0x180010b99  mov     [rsp+290h+samDesired], ebx; cbData
0x180010b9d  mov     dword ptr [rsp+290h+Data], eax
0x180010ba1  lea     rax, [rsp+290h+Data]
0x180010ba6  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180010bab  call    cs:__imp_RegSetValueExW
0x180010bb2  nop     dword ptr [rax+rax+00h]
0x180010bb7  mov     rcx, [rsp+290h+hKey]; hKey
0x180010bbc  call    cs:__imp_RegCloseKey
0x180010bc3  nop     dword ptr [rax+rax+00h]
0x180010bc8  mov     rcx, [rbp+190h+var_20]
0x180010bcf  xor     rcx, rsp; StackCookie
0x180010bd2  call    __security_check_cookie
0x180010bd7  add     rsp, 280h
0x180010bde  pop     rdi
0x180010bdf  pop     rbx
0x180010be0  pop     rbp
0x180010be1  retn
```
