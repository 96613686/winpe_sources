# SetLocationList

- ea: `0x18000a2b0`
- end: `0x18000a4e9`
- name: `SetLocationList`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a4f0`

## callees

- `0x180008ddc`
- `0x18000a2b0`
- `0x18000b100`

## import_xrefs

- `KERNEL32!RegSetValueExW` at `0x18000a45c`
- `KERNEL32!RegSetValueExW` at `0x18000a491`
- `KERNEL32!RegSetValueExW` at `0x18000a45c`
- `KERNEL32!RegSetValueExW` at `0x18000a491`
- `KERNEL32!RegDeleteKeyExW` at `0x18000a36f`
- `KERNEL32!RegDeleteKeyExW` at `0x18000a36f`
- `KERNEL32!RegCreateKeyExW` at `0x18000a320`
- `KERNEL32!RegCreateKeyExW` at `0x18000a423`
- `KERNEL32!RegCreateKeyExW` at `0x18000a320`
- `KERNEL32!RegCreateKeyExW` at `0x18000a423`
- `KERNEL32!RegCloseKey` at `0x18000a49d`
- `KERNEL32!RegCloseKey` at `0x18000a4bd`
- `KERNEL32!RegCloseKey` at `0x18000a49d`
- `KERNEL32!RegCloseKey` at `0x18000a4bd`
- `KERNEL32!RegEnumKeyExW` at `0x18000a357`
- `KERNEL32!RegEnumKeyExW` at `0x18000a357`
- `rtutils!TracePrintfExA` at `0x18000a3e7`
- `rtutils!TracePrintfExA` at `0x18000a3e7`

## pseudocode

```c
LSTATUS __fastcall SetLocationList(HKEY a1, __int64 *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  __int64 v6; // rdi
  _DWORD *v7; // rsi
  HRESULT v8; // eax
  LPDWORD lpcchClass; // [rsp+38h] [rbp-19h]
  BYTE Data[8]; // [rsp+58h] [rbp+7h] BYREF
  DWORD cchName; // [rsp+60h] [rbp+Fh] BYREF
  DWORD dwDisposition; // [rsp+64h] [rbp+13h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+17h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+1Fh] BYREF
  WCHAR Name[12]; // [rsp+78h] [rbp+27h] BYREF

  cchName = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  result = RegCreateKeyExW(a1, L"Location", 0, (LPWSTR)&::Data, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    do
    {
      cchName = 12;
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
      if ( v6 )
      {
        do
        {
          v7 = *(_DWORD **)(v6 + 16);
          LODWORD(lpcchClass) = *v7;
          v8 = StringCchPrintfExW(Name, 0xCu, 0, 0, 0x100u, L"%d", lpcchClass);
          if ( v8 < 0 && g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "LToT: StringCchPrintfEx failed. hr= 0x%x", v8);
          v5 = RegCreateKeyExW(hKey, Name, 0, (LPWSTR)&::Data, 0, 0x20006u, 0, &phkResult, &dwDisposition);
          if ( v5 )
            break;
          *(_DWORD *)Data = v7[1];
          v5 = RegSetValueExW(phkResult, L"Prefix", 0, 4u, Data, 4u);
          if ( !v5 )
          {
            *(_DWORD *)Data = v7[2];
            v5 = RegSetValueExW(phkResult, L"Suffix", 0, 4u, Data, 4u);
          }
          RegCloseKey(phkResult);
          if ( v5 )
            break;
          v6 = *(_QWORD *)(v6 + 8);
        }
        while ( v6 );
      }
      else
      {
        v5 = 0;
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
0x18000a2b0  mov     r11, rsp
0x18000a2b3  mov     [r11+18h], rbx
0x18000a2b7  mov     [r11+20h], rsi
0x18000a2bb  push    rbp
0x18000a2bc  push    rdi
0x18000a2bd  push    r14
0x18000a2bf  lea     rbp, [r11-5Fh]
0x18000a2c3  sub     rsp, 90h
0x18000a2ca  mov     rax, cs:__security_cookie
0x18000a2d1  xor     rax, rsp
0x18000a2d4  mov     [rbp+57h+var_18], rax
0x18000a2d8  xor     r14d, r14d
0x18000a2db  lea     rax, [rbp+57h+dwDisposition]
0x18000a2df  mov     [r11-68h], rax
0x18000a2e3  lea     r9, Data; lpClass
0x18000a2ea  lea     rax, [rbp+57h+hKey]
0x18000a2ee  mov     [rbp+57h+cchName], r14d
0x18000a2f2  mov     [r11-70h], rax
0x18000a2f6  mov     rdi, rdx
0x18000a2f9  mov     [r11-78h], r14
0x18000a2fd  lea     rdx, aLocation; "Location"
0x18000a304  mov     [rsp+0A0h+samDesired], 2000Eh; samDesired
0x18000a30c  xor     r8d, r8d; Reserved
0x18000a30f  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x18000a314  mov     [rbp+57h+dwDisposition], r14d
0x18000a318  mov     [rbp+57h+hKey], r14
0x18000a31c  mov     [rbp+57h+phkResult], r14
0x18000a320  call    cs:__imp_RegCreateKeyExW
0x18000a326  test    eax, eax
0x18000a328  jnz     loc_18000A4C5
0x18000a32e  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a332  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000a336  mov     [rsp+0A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000a33b  lea     r8, [rbp+57h+Name]; lpName
0x18000a33f  mov     [rsp+0A0h+lpcchClass], r14; lpcchClass
0x18000a344  xor     edx, edx; dwIndex
0x18000a346  mov     qword ptr [rsp+0A0h+samDesired], r14; lpClass
0x18000a34b  mov     qword ptr [rsp+0A0h+dwOptions], r14; lpReserved
0x18000a350  mov     [rbp+57h+cchName], 0Ch
0x18000a357  call    cs:__imp_RegEnumKeyExW
0x18000a35d  test    eax, eax
0x18000a35f  jnz     short loc_18000A379
0x18000a361  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a365  lea     rdx, [rbp+57h+Name]; lpSubKey
0x18000a369  xor     r9d, r9d; Reserved
0x18000a36c  xor     r8d, r8d; samDesired
0x18000a36f  call    cs:__imp_RegDeleteKeyExW
0x18000a375  test    eax, eax
0x18000a377  jz      short loc_18000A32E
0x18000a379  cmp     eax, 103h
0x18000a37e  mov     ebx, r14d
0x18000a381  cmovnz  ebx, eax
0x18000a384  test    ebx, ebx
0x18000a386  jnz     loc_18000A4B9
0x18000a38c  mov     rdi, [rdi]
0x18000a38f  test    rdi, rdi
0x18000a392  jz      loc_18000A4B6
0x18000a398  mov     rsi, [rdi+10h]
0x18000a39c  lea     rcx, [rbp+57h+Name]; pszDest
0x18000a3a0  xor     r9d, r9d; pcchRemaining
0x18000a3a3  xor     r8d, r8d; ppszDestEnd
0x18000a3a6  mov     eax, [rsi]
0x18000a3a8  mov     dword ptr [rsp+0A0h+lpcchClass], eax
0x18000a3ac  lea     edx, [r9+0Ch]; cchDest
0x18000a3b0  lea     rax, aD; "%d"
0x18000a3b7  mov     qword ptr [rsp+0A0h+samDesired], rax; pszFormat
0x18000a3bc  mov     [rsp+0A0h+dwOptions], 100h; dwFlags
0x18000a3c4  call    StringCchPrintfExW
0x18000a3c9  test    eax, eax
0x18000a3cb  jns     short loc_18000A3ED
0x18000a3cd  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a3d3  cmp     ecx, 0FFFFFFFFh
0x18000a3d6  jz      short loc_18000A3ED
0x18000a3d8  mov     r9d, eax
0x18000a3db  lea     r8, aLtotStringcchp; "LToT: StringCchPrintfEx failed. hr= 0x%"...
0x18000a3e2  mov     edx, 0Ch; dwFlags
0x18000a3e7  call    cs:__imp_TracePrintfExA
0x18000a3ed  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a3f1  lea     rax, [rbp+57h+dwDisposition]
0x18000a3f5  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x18000a3fa  lea     r9, Data; lpClass
0x18000a401  lea     rax, [rbp+57h+phkResult]
0x18000a405  xor     r8d, r8d; Reserved
0x18000a408  mov     [rsp+0A0h+lpftLastWriteTime], rax; phkResult
0x18000a40d  lea     rdx, [rbp+57h+Name]; lpSubKey
0x18000a411  mov     [rsp+0A0h+lpcchClass], r14; lpSecurityAttributes
0x18000a416  mov     [rsp+0A0h+samDesired], 20006h; samDesired
0x18000a41e  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x18000a423  call    cs:__imp_RegCreateKeyExW
0x18000a429  mov     ebx, eax
0x18000a42b  test    eax, eax
0x18000a42d  jnz     loc_18000A4B9
0x18000a433  mov     eax, [rsi+4]
0x18000a436  lea     r9d, [rbx+4]; dwType
0x18000a43a  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000a43e  lea     rdx, aPrefix; "Prefix"
0x18000a445  mov     dword ptr [rbp+57h+Data], eax
0x18000a448  xor     r8d, r8d; Reserved
0x18000a44b  lea     rax, [rbp+57h+Data]
0x18000a44f  mov     [rsp+0A0h+samDesired], 4; cbData
0x18000a457  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x18000a45c  call    cs:__imp_RegSetValueExW
0x18000a462  mov     ebx, eax
0x18000a464  test    eax, eax
0x18000a466  jnz     short loc_18000A499
0x18000a468  mov     eax, [rsi+8]
0x18000a46b  lea     r9d, [rbx+4]; dwType
0x18000a46f  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000a473  lea     rdx, aSuffix; "Suffix"
0x18000a47a  mov     dword ptr [rbp+57h+Data], eax
0x18000a47d  xor     r8d, r8d; Reserved
0x18000a480  lea     rax, [rbp+57h+Data]
0x18000a484  mov     [rsp+0A0h+samDesired], 4; cbData
0x18000a48c  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x18000a491  call    cs:__imp_RegSetValueExW
0x18000a497  mov     ebx, eax
0x18000a499  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000a49d  call    cs:__imp_RegCloseKey
0x18000a4a3  test    ebx, ebx
0x18000a4a5  jnz     short loc_18000A4B9
0x18000a4a7  mov     rdi, [rdi+8]
0x18000a4ab  test    rdi, rdi
0x18000a4ae  jnz     loc_18000A398
0x18000a4b4  jmp     short loc_18000A4B9
0x18000a4b6  mov     ebx, r14d
0x18000a4b9  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a4bd  call    cs:__imp_RegCloseKey
0x18000a4c3  mov     eax, ebx
0x18000a4c5  mov     rcx, [rbp+57h+var_18]
0x18000a4c9  xor     rcx, rsp; StackCookie
0x18000a4cc  call    __security_check_cookie
0x18000a4d1  lea     r11, [rsp+0A0h+var_10]
0x18000a4d9  mov     rbx, [r11+30h]
0x18000a4dd  mov     rsi, [r11+38h]
0x18000a4e1  mov     rsp, r11
0x18000a4e4  pop     r14
0x18000a4e6  pop     rdi
0x18000a4e7  pop     rbp
0x18000a4e8  retn
```
