# SetCallbackList

- ea: `0x18003f830`
- end: `0x18003fa40`
- name: `SetCallbackList`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003ff50`

## callees

- `0x18003bea0`
- `0x18003c364`
- `0x18003f830`
- `0x1800419a4`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f8ad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f982`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f8ad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f982`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003f902`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003f902`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f9e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fa12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f9e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fa12`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f9bb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003f9bb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f8e8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f8e8`

## pseudocode

```c
LSTATUS __fastcall SetCallbackList(HKEY a1, __int64 *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  __int64 v6; // rdi
  __int64 v7; // r14
  WCHAR *v8; // rsi
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
  result = RegCreateKeyExW(a1, L"Callback", 0, (LPWSTR)&WideCharStr, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
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
        v8 = (WCHAR *)PszFromDeviceAndPort(*(_QWORD *)(v7 + 8), *(_QWORD *)v7);
        if ( !v8 )
        {
          v5 = 8;
          break;
        }
        v5 = RegCreateKeyExW(hKey, v8, 0, (LPWSTR)&WideCharStr, 0, 0x20006u, 0, &phkResult, &dwDisposition);
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
0x18003f830  mov     [rsp-8+arg_10], rbx
0x18003f835  push    rbp
0x18003f836  push    rsi
0x18003f837  push    rdi
0x18003f838  push    r14
0x18003f83a  push    r15
0x18003f83c  lea     rbp, [rsp-0B0h]
0x18003f844  sub     rsp, 1B0h
0x18003f84b  mov     rax, cs:__security_cookie
0x18003f852  xor     rax, rsp
0x18003f855  mov     [rbp+0D0h+var_30], rax
0x18003f85c  xor     r15d, r15d
0x18003f85f  lea     rax, [rsp+1D0h+dwDisposition]
0x18003f864  mov     [rsp+1D0h+lpdwDisposition], rax; lpdwDisposition
0x18003f869  lea     r9, WideCharStr; lpClass
0x18003f870  lea     rax, [rsp+1D0h+hKey]
0x18003f875  mov     [rsp+1D0h+cchName], r15d
0x18003f87a  mov     [rsp+1D0h+phkResult], rax; phkResult
0x18003f87f  mov     rdi, rdx
0x18003f882  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003f887  lea     rdx, aCallback; "Callback"
0x18003f88e  mov     [rsp+1D0h+samDesired], 2000Eh; samDesired
0x18003f896  xor     r8d, r8d; Reserved
0x18003f899  mov     [rsp+1D0h+dwOptions], r15d; dwOptions
0x18003f89e  mov     [rsp+1D0h+dwDisposition], r15d
0x18003f8a3  mov     [rsp+1D0h+hKey], r15
0x18003f8a8  mov     [rsp+1D0h+var_170], r15
0x18003f8ad  call    cs:__imp_RegCreateKeyExW
0x18003f8b3  test    eax, eax
0x18003f8b5  jnz     loc_18003FA1A
0x18003f8bb  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18003f8c0  lea     r9, [rsp+1D0h+cchName]; lpcchName
0x18003f8c5  mov     [rsp+1D0h+phkResult], r15; lpftLastWriteTime
0x18003f8ca  lea     r8, [rsp+1D0h+Name]; lpName
0x18003f8cf  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpcchClass
0x18003f8d4  xor     edx, edx; dwIndex
0x18003f8d6  mov     qword ptr [rsp+1D0h+samDesired], r15; lpClass
0x18003f8db  mov     qword ptr [rsp+1D0h+dwOptions], r15; lpReserved
0x18003f8e0  mov     [rsp+1D0h+cchName], 94h
0x18003f8e8  call    cs:__imp_RegEnumKeyExW
0x18003f8ee  test    eax, eax
0x18003f8f0  jnz     short loc_18003F90C
0x18003f8f2  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18003f8f7  lea     rdx, [rsp+1D0h+Name]; lpSubKey
0x18003f8fc  xor     r9d, r9d; Reserved
0x18003f8ff  xor     r8d, r8d; samDesired
0x18003f902  call    cs:__imp_RegDeleteKeyExW
0x18003f908  test    eax, eax
0x18003f90a  jz      short loc_18003F8BB
0x18003f90c  cmp     eax, 103h
0x18003f911  mov     ebx, r15d
0x18003f914  cmovnz  ebx, eax
0x18003f917  test    ebx, ebx
0x18003f919  jnz     loc_18003FA0D
0x18003f91f  mov     rdi, [rdi]
0x18003f922  mov     ebx, r15d
0x18003f925  test    rdi, rdi
0x18003f928  jz      loc_18003FA0D
0x18003f92e  mov     r14, [rdi+10h]
0x18003f932  mov     rdx, [r14]
0x18003f935  mov     rcx, [r14+8]
0x18003f939  call    PszFromDeviceAndPort
0x18003f93e  mov     rsi, rax
0x18003f941  test    rax, rax
0x18003f944  jz      loc_18003FA08
0x18003f94a  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18003f94f  lea     rax, [rsp+1D0h+dwDisposition]
0x18003f954  mov     [rsp+1D0h+lpdwDisposition], rax; lpdwDisposition
0x18003f959  lea     r9, WideCharStr; lpClass
0x18003f960  lea     rax, [rsp+1D0h+var_170]
0x18003f965  xor     r8d, r8d; Reserved
0x18003f968  mov     [rsp+1D0h+phkResult], rax; phkResult
0x18003f96d  mov     rdx, rsi; lpSubKey
0x18003f970  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003f975  mov     [rsp+1D0h+samDesired], 20006h; samDesired
0x18003f97d  mov     [rsp+1D0h+dwOptions], r15d; dwOptions
0x18003f982  call    cs:__imp_RegCreateKeyExW
0x18003f988  mov     ebx, eax
0x18003f98a  test    eax, eax
0x18003f98c  jnz     short loc_18003F9FE
0x18003f98e  mov     eax, [r14+18h]
0x18003f992  lea     r9d, [rbx+4]; dwType
0x18003f996  mov     rcx, [rsp+1D0h+var_170]; hKey
0x18003f99b  lea     rdx, aDevicetype; "DeviceType"
0x18003f9a2  mov     dword ptr [rsp+1D0h+Data], eax
0x18003f9a6  xor     r8d, r8d; Reserved
0x18003f9a9  lea     rax, [rsp+1D0h+Data]
0x18003f9ae  mov     [rsp+1D0h+samDesired], 4; cbData
0x18003f9b6  mov     qword ptr [rsp+1D0h+dwOptions], rax; lpData
0x18003f9bb  call    cs:__imp_RegSetValueExW
0x18003f9c1  mov     ebx, eax
0x18003f9c3  test    eax, eax
0x18003f9c5  jnz     short loc_18003F9DE
0x18003f9c7  mov     r8, [r14+10h]
0x18003f9cb  lea     rdx, aNumber; "Number"
0x18003f9d2  mov     rcx, [rsp+1D0h+var_170]; hKey
0x18003f9d7  call    SetRegSz
0x18003f9dc  mov     ebx, eax
0x18003f9de  mov     rcx, [rsp+1D0h+var_170]; hKey
0x18003f9e3  call    cs:__imp_RegCloseKey
0x18003f9e9  mov     rcx, rsi
0x18003f9ec  call    Free0
0x18003f9f1  test    ebx, ebx
0x18003f9f3  jnz     short loc_18003FA0D
0x18003f9f5  mov     rdi, [rdi+8]
0x18003f9f9  jmp     loc_18003F925
0x18003f9fe  mov     rcx, rsi
0x18003fa01  call    Free0
0x18003fa06  jmp     short loc_18003FA0D
0x18003fa08  mov     ebx, 8
0x18003fa0d  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18003fa12  call    cs:__imp_RegCloseKey
0x18003fa18  mov     eax, ebx
0x18003fa1a  mov     rcx, [rbp+0D0h+var_30]
0x18003fa21  xor     rcx, rsp; StackCookie
0x18003fa24  call    __security_check_cookie
0x18003fa29  mov     rbx, [rsp+1D0h+arg_10]
0x18003fa31  add     rsp, 1B0h
0x18003fa38  pop     r15
0x18003fa3a  pop     r14
0x18003fa3c  pop     rdi
0x18003fa3d  pop     rsi
0x18003fa3e  pop     rbp
0x18003fa3f  retn
```
