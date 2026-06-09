# SetCallbackList

- ea: `0x1800c42ec`
- end: `0x1800c44fc`
- name: `SetCallbackList`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800c4744`

## callees

- `0x18000b0f4`
- `0x1800c0cc0`
- `0x1800c42ec`
- `0x1800c5414`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c43a4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c43a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4477`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c4477`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4369`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c443e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4369`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c443e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c43be`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c43be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c449f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c44ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c449f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c44ce`

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
0x1800c42ec  mov     [rsp-8+arg_10], rbx
0x1800c42f1  push    rbp
0x1800c42f2  push    rsi
0x1800c42f3  push    rdi
0x1800c42f4  push    r14
0x1800c42f6  push    r15
0x1800c42f8  lea     rbp, [rsp-0B0h]
0x1800c4300  sub     rsp, 1B0h
0x1800c4307  mov     rax, cs:__security_cookie
0x1800c430e  xor     rax, rsp
0x1800c4311  mov     [rbp+0D0h+var_30], rax
0x1800c4318  xor     r15d, r15d
0x1800c431b  lea     rax, [rsp+1D0h+dwDisposition]
0x1800c4320  mov     [rsp+1D0h+lpdwDisposition], rax; lpdwDisposition
0x1800c4325  lea     r9, Data; lpClass
0x1800c432c  lea     rax, [rsp+1D0h+hKey]
0x1800c4331  mov     [rsp+1D0h+cchName], r15d
0x1800c4336  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800c433b  mov     rdi, rdx
0x1800c433e  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800c4343  lea     rdx, aCallback; "Callback"
0x1800c434a  mov     [rsp+1D0h+samDesired], 2000Eh; samDesired
0x1800c4352  xor     r8d, r8d; Reserved
0x1800c4355  mov     [rsp+1D0h+dwOptions], r15d; dwOptions
0x1800c435a  mov     [rsp+1D0h+dwDisposition], r15d
0x1800c435f  mov     [rsp+1D0h+hKey], r15
0x1800c4364  mov     [rsp+1D0h+var_170], r15
0x1800c4369  call    cs:__imp_RegCreateKeyExW
0x1800c436f  test    eax, eax
0x1800c4371  jnz     loc_1800C44D6
0x1800c4377  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800c437c  lea     r9, [rsp+1D0h+cchName]; lpcchName
0x1800c4381  mov     [rsp+1D0h+phkResult], r15; lpftLastWriteTime
0x1800c4386  lea     r8, [rsp+1D0h+Name]; lpName
0x1800c438b  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpcchClass
0x1800c4390  xor     edx, edx; dwIndex
0x1800c4392  mov     qword ptr [rsp+1D0h+samDesired], r15; lpClass
0x1800c4397  mov     qword ptr [rsp+1D0h+dwOptions], r15; lpReserved
0x1800c439c  mov     [rsp+1D0h+cchName], 94h
0x1800c43a4  call    cs:__imp_RegEnumKeyExW
0x1800c43aa  test    eax, eax
0x1800c43ac  jnz     short loc_1800C43C8
0x1800c43ae  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800c43b3  lea     rdx, [rsp+1D0h+Name]; lpSubKey
0x1800c43b8  xor     r9d, r9d; Reserved
0x1800c43bb  xor     r8d, r8d; samDesired
0x1800c43be  call    cs:__imp_RegDeleteKeyExW
0x1800c43c4  test    eax, eax
0x1800c43c6  jz      short loc_1800C4377
0x1800c43c8  cmp     eax, 103h
0x1800c43cd  mov     ebx, r15d
0x1800c43d0  cmovnz  ebx, eax
0x1800c43d3  test    ebx, ebx
0x1800c43d5  jnz     loc_1800C44C9
0x1800c43db  mov     rdi, [rdi]
0x1800c43de  mov     ebx, r15d
0x1800c43e1  test    rdi, rdi
0x1800c43e4  jz      loc_1800C44C9
0x1800c43ea  mov     r14, [rdi+10h]
0x1800c43ee  mov     rdx, [r14]
0x1800c43f1  mov     rcx, [r14+8]
0x1800c43f5  call    PszFromDeviceAndPort
0x1800c43fa  mov     rsi, rax
0x1800c43fd  test    rax, rax
0x1800c4400  jz      loc_1800C44C4
0x1800c4406  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800c440b  lea     rax, [rsp+1D0h+dwDisposition]
0x1800c4410  mov     [rsp+1D0h+lpdwDisposition], rax; lpdwDisposition
0x1800c4415  lea     r9, Data; lpClass
0x1800c441c  lea     rax, [rsp+1D0h+var_170]
0x1800c4421  xor     r8d, r8d; Reserved
0x1800c4424  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800c4429  mov     rdx, rsi; lpSubKey
0x1800c442c  mov     [rsp+1D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800c4431  mov     [rsp+1D0h+samDesired], 20006h; samDesired
0x1800c4439  mov     [rsp+1D0h+dwOptions], r15d; dwOptions
0x1800c443e  call    cs:__imp_RegCreateKeyExW
0x1800c4444  mov     ebx, eax
0x1800c4446  test    eax, eax
0x1800c4448  jnz     short loc_1800C44BA
0x1800c444a  mov     eax, [r14+18h]
0x1800c444e  lea     r9d, [rbx+4]; dwType
0x1800c4452  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1800c4457  lea     rdx, aDevicetype; "DeviceType"
0x1800c445e  mov     dword ptr [rsp+1D0h+Data], eax
0x1800c4462  xor     r8d, r8d; Reserved
0x1800c4465  lea     rax, [rsp+1D0h+Data]
0x1800c446a  mov     [rsp+1D0h+samDesired], 4; cbData
0x1800c4472  mov     qword ptr [rsp+1D0h+dwOptions], rax; lpData
0x1800c4477  call    cs:__imp_RegSetValueExW
0x1800c447d  mov     ebx, eax
0x1800c447f  test    eax, eax
0x1800c4481  jnz     short loc_1800C449A
0x1800c4483  mov     r8, [r14+10h]
0x1800c4487  lea     rdx, aNumber; "Number"
0x1800c448e  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1800c4493  call    SetRegSz
0x1800c4498  mov     ebx, eax
0x1800c449a  mov     rcx, [rsp+1D0h+var_170]; hKey
0x1800c449f  call    cs:__imp_RegCloseKey
0x1800c44a5  mov     rcx, rsi
0x1800c44a8  call    Free0
0x1800c44ad  test    ebx, ebx
0x1800c44af  jnz     short loc_1800C44C9
0x1800c44b1  mov     rdi, [rdi+8]
0x1800c44b5  jmp     loc_1800C43E1
0x1800c44ba  mov     rcx, rsi
0x1800c44bd  call    Free0
0x1800c44c2  jmp     short loc_1800C44C9
0x1800c44c4  mov     ebx, 8
0x1800c44c9  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800c44ce  call    cs:__imp_RegCloseKey
0x1800c44d4  mov     eax, ebx
0x1800c44d6  mov     rcx, [rbp+0D0h+var_30]
0x1800c44dd  xor     rcx, rsp; StackCookie
0x1800c44e0  call    __security_check_cookie
0x1800c44e5  mov     rbx, [rsp+1D0h+arg_10]
0x1800c44ed  add     rsp, 1B0h
0x1800c44f4  pop     r15
0x1800c44f6  pop     r14
0x1800c44f8  pop     rdi
0x1800c44f9  pop     rsi
0x1800c44fa  pop     rbp
0x1800c44fb  retn
```
