# SetCallbackList

- ea: `0x180009eac`
- end: `0x18000a0bc`
- name: `SetCallbackList`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000a4f0`

## callees

- `0x1800089c0`
- `0x1800089d8`
- `0x180009eac`
- `0x18000afb4`
- `0x18000b100`

## import_xrefs

- `KERNEL32!RegSetValueExW` at `0x18000a037`
- `KERNEL32!RegSetValueExW` at `0x18000a037`
- `KERNEL32!RegDeleteKeyExW` at `0x180009f7e`
- `KERNEL32!RegDeleteKeyExW` at `0x180009f7e`
- `KERNEL32!RegCreateKeyExW` at `0x180009f29`
- `KERNEL32!RegCreateKeyExW` at `0x180009ffe`
- `KERNEL32!RegCreateKeyExW` at `0x180009f29`
- `KERNEL32!RegCreateKeyExW` at `0x180009ffe`
- `KERNEL32!RegCloseKey` at `0x18000a05f`
- `KERNEL32!RegCloseKey` at `0x18000a08e`
- `KERNEL32!RegCloseKey` at `0x18000a05f`
- `KERNEL32!RegCloseKey` at `0x18000a08e`
- `KERNEL32!RegEnumKeyExW` at `0x180009f64`
- `KERNEL32!RegEnumKeyExW` at `0x180009f64`

## pseudocode

```c
LSTATUS __fastcall SetCallbackList(HKEY a1, __int64 *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  __int64 v6; // rdi
  __int64 v7; // r14
  const WCHAR *v8; // rsi
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[152]; // [rsp+70h] [rbp-90h] BYREF

  cchName = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  result = RegCreateKeyExW(a1, L"Callback", 0, (LPWSTR)&::Data, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    do
    {
      cchName = 148;
      v4 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
      if ( v4 )
        break;
      v4 = RegDeleteKeyExW(hKey, Name, 0, 0);
    }
    while ( !v4 );
    v5 = 0;
    if ( v4 != 259 )
      v5 = v4;
    if ( !v5 )
    {
      v6 = *a2;
      v5 = 0;
      while ( v6 )
      {
        v7 = *(_QWORD *)(v6 + 16);
        v8 = (const WCHAR *)PszFromDeviceAndPort(*(_QWORD *)(v7 + 8), *(_QWORD *)v7);
        if ( !v8 )
        {
          v5 = 8;
          break;
        }
        v5 = RegCreateKeyExW(hKey, v8, 0, (LPWSTR)&::Data, 0, 0x20006u, 0, &phkResult, &dwDisposition);
        if ( v5 )
        {
          Free0(v8);
          break;
        }
        *(_DWORD *)Data = *(_DWORD *)(v7 + 24);
        v5 = RegSetValueExW(phkResult, L"DeviceType", 0, 4u, Data, 4u);
        if ( !v5 )
          v5 = SetRegSz(phkResult, L"Number");
        RegCloseKey(phkResult);
        Free0(v8);
        if ( v5 )
          break;
        v6 = *(_QWORD *)(v6 + 8);
      }
    }
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180009eac  mov     [rsp-8+arg_10], rbx
0x180009eb1  push    rbp
0x180009eb2  push    rsi
0x180009eb3  push    rdi
0x180009eb4  push    r14
0x180009eb6  push    r15
0x180009eb8  lea     rbp, [rsp-0B0h]
0x180009ec0  sub     rsp, 1B0h
0x180009ec7  mov     rax, cs:__security_cookie
0x180009ece  xor     rax, rsp
0x180009ed1  mov     [rbp+0D0h+var_30], rax
0x180009ed8  xor     r15d, r15d
0x180009edb  lea     rax, [rsp+1D0h+dwDisposition]
0x180009ee0  mov     [rsp+1D0h+lpdwDisposition], rax; lpdwDisposition
0x180009ee5  lea     r9, Data; lpClass
0x180009eec  lea     rax, [rsp+1D0h+hKey]
0x180009ef1  mov     [rsp+1D0h+cchName], r15d
0x180009ef6  mov     [rsp+1D0h+phkResult], rax; phkResult
0x180009efb  mov     rdi, rdx
0x180009efe  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180009f03  lea     rdx, aCallback; "Callback"
0x180009f0a  mov     [rsp+1D0h+samDesired], 2000Eh; samDesired
0x180009f12  xor     r8d, r8d; Reserved
0x180009f15  mov     [rsp+1D0h+dwOptions], r15d; dwOptions
0x180009f1a  mov     [rsp+1D0h+dwDisposition], r15d
0x180009f1f  mov     [rsp+1D0h+hKey], r15
0x180009f24  mov     [rsp+1D0h+var_170], r15
0x180009f29  call    cs:__imp_RegCreateKeyExW
0x180009f2f  test    eax, eax
0x180009f31  jnz     loc_18000A096
0x180009f37  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180009f3c  lea     r9, [rsp+1D0h+cchName]; lpcchName
0x180009f41  mov     [rsp+1D0h+phkResult], r15; lpftLastWriteTime
0x180009f46  lea     r8, [rsp+1D0h+Name]; lpName
0x180009f4b  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpcchClass
0x180009f50  xor     edx, edx; dwIndex
0x180009f52  mov     qword ptr [rsp+1D0h+samDesired], r15; lpClass
0x180009f57  mov     qword ptr [rsp+1D0h+dwOptions], r15; lpReserved
0x180009f5c  mov     [rsp+1D0h+cchName], 94h
0x180009f64  call    cs:__imp_RegEnumKeyExW
0x180009f6a  test    eax, eax
0x180009f6c  jnz     short loc_180009F88
0x180009f6e  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180009f73  lea     rdx, [rsp+1D0h+Name]; lpSubKey
0x180009f78  xor     r9d, r9d; Reserved
0x180009f7b  xor     r8d, r8d; samDesired
0x180009f7e  call    cs:__imp_RegDeleteKeyExW
0x180009f84  test    eax, eax
0x180009f86  jz      short loc_180009F37
0x180009f88  cmp     eax, 103h
0x180009f8d  mov     ebx, r15d
0x180009f90  cmovnz  ebx, eax
0x180009f93  test    ebx, ebx
0x180009f95  jnz     loc_18000A089
0x180009f9b  mov     rdi, [rdi]
0x180009f9e  mov     ebx, r15d
0x180009fa1  test    rdi, rdi
0x180009fa4  jz      loc_18000A089
0x180009faa  mov     r14, [rdi+10h]
0x180009fae  mov     rdx, [r14]
0x180009fb1  mov     rcx, [r14+8]
0x180009fb5  call    PszFromDeviceAndPort
0x180009fba  mov     rsi, rax
0x180009fbd  test    rax, rax
0x180009fc0  jz      loc_18000A084
0x180009fc6  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180009fcb  lea     rax, [rsp+1D0h+dwDisposition]
0x180009fd0  mov     [rsp+1D0h+lpdwDisposition], rax; lpdwDisposition
0x180009fd5  lea     r9, Data; lpClass
0x180009fdc  lea     rax, [rsp+1D0h+var_170]
0x180009fe1  xor     r8d, r8d; Reserved
0x180009fe4  mov     [rsp+1D0h+phkResult], rax; phkResult
0x180009fe9  mov     rdx, rsi; lpSubKey
0x180009fec  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180009ff1  mov     [rsp+1D0h+samDesired], 20006h; samDesired
0x180009ff9  mov     [rsp+1D0h+dwOptions], r15d; dwOptions
0x180009ffe  call    cs:__imp_RegCreateKeyExW
0x18000a004  mov     ebx, eax
0x18000a006  test    eax, eax
0x18000a008  jnz     short loc_18000A07A
0x18000a00a  mov     eax, [r14+18h]
0x18000a00e  lea     r9d, [rbx+4]; dwType
0x18000a012  mov     rcx, [rsp+1D0h+var_170]; hKey
0x18000a017  lea     rdx, aDevicetype; "DeviceType"
0x18000a01e  mov     dword ptr [rsp+1D0h+Data], eax
0x18000a022  xor     r8d, r8d; Reserved
0x18000a025  lea     rax, [rsp+1D0h+Data]
0x18000a02a  mov     [rsp+1D0h+samDesired], 4; cbData
0x18000a032  mov     qword ptr [rsp+1D0h+dwOptions], rax; lpData
0x18000a037  call    cs:__imp_RegSetValueExW
0x18000a03d  mov     ebx, eax
0x18000a03f  test    eax, eax
0x18000a041  jnz     short loc_18000A05A
0x18000a043  mov     r8, [r14+10h]
0x18000a047  lea     rdx, aNumber; "Number"
0x18000a04e  mov     rcx, [rsp+1D0h+var_170]; hKey
0x18000a053  call    SetRegSz
0x18000a058  mov     ebx, eax
0x18000a05a  mov     rcx, [rsp+1D0h+var_170]; hKey
0x18000a05f  call    cs:__imp_RegCloseKey
0x18000a065  mov     rcx, rsi
0x18000a068  call    Free0
0x18000a06d  test    ebx, ebx
0x18000a06f  jnz     short loc_18000A089
0x18000a071  mov     rdi, [rdi+8]
0x18000a075  jmp     loc_180009FA1
0x18000a07a  mov     rcx, rsi
0x18000a07d  call    Free0
0x18000a082  jmp     short loc_18000A089
0x18000a084  mov     ebx, 8
0x18000a089  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18000a08e  call    cs:__imp_RegCloseKey
0x18000a094  mov     eax, ebx
0x18000a096  mov     rcx, [rbp+0D0h+var_30]
0x18000a09d  xor     rcx, rsp; StackCookie
0x18000a0a0  call    __security_check_cookie
0x18000a0a5  mov     rbx, [rsp+1D0h+arg_10]
0x18000a0ad  add     rsp, 1B0h
0x18000a0b4  pop     r15
0x18000a0b6  pop     r14
0x18000a0b8  pop     rdi
0x18000a0b9  pop     rsi
0x18000a0ba  pop     rbp
0x18000a0bb  retn
```
