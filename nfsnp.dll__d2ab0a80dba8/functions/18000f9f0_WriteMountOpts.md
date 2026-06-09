# WriteMountOpts

- ea: `0x18000f9f0`
- end: `0x18000fc1a`
- name: `WriteMountOpts`
- size: `554`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000fc20`

## callees

- `0x18000f9f0`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000fa60`
- `msvcrt!wcscat_s` at `0x18000fa60`
- `msvcrt!wcscpy_s` at `0x18000fa49`
- `msvcrt!wcscpy_s` at `0x18000fa49`
- `ADVAPI32!RegCreateKeyExW` at `0x18000faa1`
- `ADVAPI32!RegCreateKeyExW` at `0x18000faa1`
- `ADVAPI32!RegSetValueExW` at `0x18000fad3`
- `ADVAPI32!RegSetValueExW` at `0x18000faf8`
- `ADVAPI32!RegSetValueExW` at `0x18000fb1d`
- `ADVAPI32!RegSetValueExW` at `0x18000fb42`
- `ADVAPI32!RegSetValueExW` at `0x18000fb67`
- `ADVAPI32!RegSetValueExW` at `0x18000fb8c`
- `ADVAPI32!RegSetValueExW` at `0x18000fbbc`
- `ADVAPI32!RegSetValueExW` at `0x18000fbef`
- `ADVAPI32!RegSetValueExW` at `0x18000fad3`
- `ADVAPI32!RegSetValueExW` at `0x18000faf8`
- `ADVAPI32!RegSetValueExW` at `0x18000fb1d`
- `ADVAPI32!RegSetValueExW` at `0x18000fb42`
- `ADVAPI32!RegSetValueExW` at `0x18000fb67`
- `ADVAPI32!RegSetValueExW` at `0x18000fb8c`
- `ADVAPI32!RegSetValueExW` at `0x18000fbbc`
- `ADVAPI32!RegSetValueExW` at `0x18000fbef`
- `ADVAPI32!RegCloseKey` at `0x18000fbfa`
- `ADVAPI32!RegCloseKey` at `0x18000fbfa`

## string_xrefs

- `0x18000fa4f`: `\Mount`
- `0x18000fabd`: `ReadBuffer`
- `0x18000fae6`: `WriteBuffer`
- `0x18000fb55`: `MountType`

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
0x18000f9f0  push    rbp
0x18000f9f2  push    rbx
0x18000f9f3  push    rdi
0x18000f9f4  lea     rbp, [rsp-180h]
0x18000f9fc  sub     rsp, 280h
0x18000fa03  mov     rax, cs:__security_cookie
0x18000fa0a  xor     rax, rsp
0x18000fa0d  mov     [rbp+190h+var_20], rax
0x18000fa14  mov     rdi, r8
0x18000fa17  mov     [rsp+290h+hKey], 0
0x18000fa20  mov     r8, rdx; Source
0x18000fa23  mov     [rsp+290h+dwDisposition], 0
0x18000fa2b  mov     rbx, rcx
0x18000fa2e  mov     dword ptr [rsp+290h+Data], 0
0x18000fa36  xor     eax, eax
0x18000fa38  lea     rcx, [rsp+290h+Destination]; Destination
0x18000fa3d  mov     edx, 104h; SizeInWords
0x18000fa42  mov     [rbp+190h+var_2A], ax
0x18000fa49  call    cs:__imp_wcscpy_s
0x18000fa4f  lea     r8, aMount; "\\Mount"
0x18000fa56  mov     edx, 104h; SizeInWords
0x18000fa5b  lea     rcx, [rsp+290h+Destination]; Destination
0x18000fa60  call    cs:__imp_wcscat_s
0x18000fa66  lea     rax, [rsp+290h+dwDisposition]
0x18000fa6b  xor     r9d, r9d; lpClass
0x18000fa6e  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x18000fa73  lea     rdx, [rsp+290h+Destination]; lpSubKey
0x18000fa78  lea     rax, [rsp+290h+hKey]
0x18000fa7d  xor     r8d, r8d; Reserved
0x18000fa80  mov     [rsp+290h+phkResult], rax; phkResult
0x18000fa85  mov     rcx, rbx; hKey
0x18000fa88  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000fa91  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x18000fa99  mov     [rsp+290h+dwOptions], 0; dwOptions
0x18000faa1  call    cs:__imp_RegCreateKeyExW
0x18000faa7  test    eax, eax
0x18000faa9  jnz     loc_18000FC00
0x18000faaf  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fab4  lea     rax, [rdi+0Ch]
0x18000fab8  mov     ebx, 4
0x18000fabd  lea     rdx, aReadbuffer; "ReadBuffer"
0x18000fac4  mov     [rsp+290h+samDesired], ebx; cbData
0x18000fac8  mov     r9d, ebx; dwType
0x18000facb  xor     r8d, r8d; Reserved
0x18000face  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18000fad3  call    cs:__imp_RegSetValueExW
0x18000fad9  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fade  lea     rax, [rdi+10h]
0x18000fae2  mov     [rsp+290h+samDesired], ebx; cbData
0x18000fae6  lea     rdx, aWritebuffer; "WriteBuffer"
0x18000faed  mov     r9d, ebx; dwType
0x18000faf0  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18000faf5  xor     r8d, r8d; Reserved
0x18000faf8  call    cs:__imp_RegSetValueExW
0x18000fafe  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fb03  lea     rax, [rdi+14h]
0x18000fb07  mov     [rsp+290h+samDesired], ebx; cbData
0x18000fb0b  lea     rdx, aTimeout; "Timeout"
0x18000fb12  mov     r9d, ebx; dwType
0x18000fb15  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18000fb1a  xor     r8d, r8d; Reserved
0x18000fb1d  call    cs:__imp_RegSetValueExW
0x18000fb23  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fb28  lea     rax, [rdi+18h]
0x18000fb2c  mov     [rsp+290h+samDesired], ebx; cbData
0x18000fb30  lea     rdx, aRetransmission; "Retransmissions"
0x18000fb37  mov     r9d, ebx; dwType
0x18000fb3a  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18000fb3f  xor     r8d, r8d; Reserved
0x18000fb42  call    cs:__imp_RegSetValueExW
0x18000fb48  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fb4d  lea     rax, [rdi+1Ch]
0x18000fb51  mov     [rsp+290h+samDesired], ebx; cbData
0x18000fb55  lea     rdx, aMounttype; "MountType"
0x18000fb5c  mov     r9d, ebx; dwType
0x18000fb5f  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18000fb64  xor     r8d, r8d; Reserved
0x18000fb67  call    cs:__imp_RegSetValueExW
0x18000fb6d  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fb72  lea     rax, [rdi+3Ch]
0x18000fb76  mov     [rsp+290h+samDesired], ebx; cbData
0x18000fb7a  lea     rdx, aSecflavors; "SecFlavors"
0x18000fb81  mov     r9d, ebx; dwType
0x18000fb84  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18000fb89  xor     r8d, r8d; Reserved
0x18000fb8c  call    cs:__imp_RegSetValueExW
0x18000fb92  mov     eax, [rdi+38h]
0x18000fb95  lea     rdx, aLocking; "Locking"
0x18000fb9c  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fba1  and     eax, 1
0x18000fba4  mov     dword ptr [rsp+290h+Data], eax
0x18000fba8  mov     r9d, ebx; dwType
0x18000fbab  lea     rax, [rsp+290h+Data]
0x18000fbb0  mov     [rsp+290h+samDesired], ebx; cbData
0x18000fbb4  xor     r8d, r8d; Reserved
0x18000fbb7  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18000fbbc  call    cs:__imp_RegSetValueExW
0x18000fbc2  mov     eax, [rdi+38h]
0x18000fbc5  lea     rdx, aVersion3; "Version3"
0x18000fbcc  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fbd1  mov     r9d, ebx; dwType
0x18000fbd4  shr     eax, 2
0x18000fbd7  xor     r8d, r8d; Reserved
0x18000fbda  and     eax, 1
0x18000fbdd  mov     [rsp+290h+samDesired], ebx; cbData
0x18000fbe1  mov     dword ptr [rsp+290h+Data], eax
0x18000fbe5  lea     rax, [rsp+290h+Data]
0x18000fbea  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18000fbef  call    cs:__imp_RegSetValueExW
0x18000fbf5  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fbfa  call    cs:__imp_RegCloseKey
0x18000fc00  mov     rcx, [rbp+190h+var_20]
0x18000fc07  xor     rcx, rsp; StackCookie
0x18000fc0a  call    __security_check_cookie
0x18000fc0f  add     rsp, 280h
0x18000fc16  pop     rdi
0x18000fc17  pop     rbx
0x18000fc18  pop     rbp
0x18000fc19  retn
```
