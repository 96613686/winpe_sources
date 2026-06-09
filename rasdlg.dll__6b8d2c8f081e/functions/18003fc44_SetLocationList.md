# SetLocationList

- ea: `0x18003fc44`
- end: `0x18003fe41`
- name: `SetLocationList`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003ff50`

## callees

- `0x18003c2e4`
- `0x18003fc44`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003fcb4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003fd7b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003fcb4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003fd7b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003fd03`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003fd03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fe15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fe15`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fdb4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fde9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fdb4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fde9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003fceb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003fceb`

## pseudocode

```c
LSTATUS __fastcall SetLocationList(HKEY a1, __int64 *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  __int64 v6; // rdi
  unsigned int *v7; // rsi
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
  result = RegCreateKeyExW(a1, L"Location", 0, (LPWSTR)&WideCharStr, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
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
          v7 = *(unsigned int **)(v6 + 16);
          LToT(*v7, Name, 12);
          v5 = RegCreateKeyExW(hKey, Name, 0, (LPWSTR)&WideCharStr, 0, 0x20006u, 0, &phkResult, &dwDisposition);
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
0x18003fc44  mov     r11, rsp
0x18003fc47  mov     [r11+18h], rbx
0x18003fc4b  mov     [r11+20h], rsi
0x18003fc4f  push    rbp
0x18003fc50  push    rdi
0x18003fc51  push    r14
0x18003fc53  lea     rbp, [r11-5Fh]
0x18003fc57  sub     rsp, 90h
0x18003fc5e  mov     rax, cs:__security_cookie
0x18003fc65  xor     rax, rsp
0x18003fc68  mov     [rbp+57h+var_18], rax
0x18003fc6c  xor     r14d, r14d
0x18003fc6f  lea     rax, [rbp+57h+dwDisposition]
0x18003fc73  mov     [r11-68h], rax
0x18003fc77  lea     r9, WideCharStr; lpClass
0x18003fc7e  lea     rax, [rbp+57h+hKey]
0x18003fc82  mov     [rbp+57h+cchName], r14d
0x18003fc86  mov     [r11-70h], rax
0x18003fc8a  mov     rdi, rdx
0x18003fc8d  mov     [r11-78h], r14
0x18003fc91  lea     rdx, aLocation; "Location"
0x18003fc98  mov     [rsp+0A0h+samDesired], 2000Eh; samDesired
0x18003fca0  xor     r8d, r8d; Reserved
0x18003fca3  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x18003fca8  mov     [rbp+57h+dwDisposition], r14d
0x18003fcac  mov     [rbp+57h+hKey], r14
0x18003fcb0  mov     [rbp+57h+phkResult], r14
0x18003fcb4  call    cs:__imp_RegCreateKeyExW
0x18003fcba  test    eax, eax
0x18003fcbc  jnz     loc_18003FE1D
0x18003fcc2  mov     rcx, [rbp+57h+hKey]; hKey
0x18003fcc6  lea     r9, [rbp+57h+cchName]; lpcchName
0x18003fcca  mov     [rsp+0A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18003fccf  lea     r8, [rbp+57h+Name]; lpName
0x18003fcd3  mov     [rsp+0A0h+lpcchClass], r14; lpcchClass
0x18003fcd8  xor     edx, edx; dwIndex
0x18003fcda  mov     qword ptr [rsp+0A0h+samDesired], r14; lpClass
0x18003fcdf  mov     qword ptr [rsp+0A0h+dwOptions], r14; lpReserved
0x18003fce4  mov     [rbp+57h+cchName], 0Ch
0x18003fceb  call    cs:__imp_RegEnumKeyExW
0x18003fcf1  test    eax, eax
0x18003fcf3  jnz     short loc_18003FD0D
0x18003fcf5  mov     rcx, [rbp+57h+hKey]; hKey
0x18003fcf9  lea     rdx, [rbp+57h+Name]; lpSubKey
0x18003fcfd  xor     r9d, r9d; Reserved
0x18003fd00  xor     r8d, r8d; samDesired
0x18003fd03  call    cs:__imp_RegDeleteKeyExW
0x18003fd09  test    eax, eax
0x18003fd0b  jz      short loc_18003FCC2
0x18003fd0d  cmp     eax, 103h
0x18003fd12  mov     ebx, r14d
0x18003fd15  cmovnz  ebx, eax
0x18003fd18  test    ebx, ebx
0x18003fd1a  jnz     loc_18003FE11
0x18003fd20  mov     rdi, [rdi]
0x18003fd23  test    rdi, rdi
0x18003fd26  jz      loc_18003FE0E
0x18003fd2c  mov     rsi, [rdi+10h]
0x18003fd30  lea     rdx, [rbp+57h+Name]
0x18003fd34  mov     r9d, 0Ah
0x18003fd3a  mov     ecx, [rsi]
0x18003fd3c  lea     r8d, [r9+2]
0x18003fd40  call    LToT
0x18003fd45  mov     rcx, [rbp+57h+hKey]; hKey
0x18003fd49  lea     rax, [rbp+57h+dwDisposition]
0x18003fd4d  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x18003fd52  lea     r9, WideCharStr; lpClass
0x18003fd59  lea     rax, [rbp+57h+phkResult]
0x18003fd5d  xor     r8d, r8d; Reserved
0x18003fd60  mov     [rsp+0A0h+lpftLastWriteTime], rax; phkResult
0x18003fd65  lea     rdx, [rbp+57h+Name]; lpSubKey
0x18003fd69  mov     [rsp+0A0h+lpcchClass], r14; lpSecurityAttributes
0x18003fd6e  mov     [rsp+0A0h+samDesired], 20006h; samDesired
0x18003fd76  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x18003fd7b  call    cs:__imp_RegCreateKeyExW
0x18003fd81  mov     ebx, eax
0x18003fd83  test    eax, eax
0x18003fd85  jnz     loc_18003FE11
0x18003fd8b  mov     eax, [rsi+4]
0x18003fd8e  lea     r9d, [rbx+4]; dwType
0x18003fd92  mov     rcx, [rbp+57h+phkResult]; hKey
0x18003fd96  lea     rdx, aPrefix; "Prefix"
0x18003fd9d  mov     dword ptr [rbp+57h+Data], eax
0x18003fda0  xor     r8d, r8d; Reserved
0x18003fda3  lea     rax, [rbp+57h+Data]
0x18003fda7  mov     [rsp+0A0h+samDesired], 4; cbData
0x18003fdaf  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x18003fdb4  call    cs:__imp_RegSetValueExW
0x18003fdba  mov     ebx, eax
0x18003fdbc  test    eax, eax
0x18003fdbe  jnz     short loc_18003FDF1
0x18003fdc0  mov     eax, [rsi+8]
0x18003fdc3  lea     r9d, [rbx+4]; dwType
0x18003fdc7  mov     rcx, [rbp+57h+phkResult]; hKey
0x18003fdcb  lea     rdx, aSuffix; "Suffix"
0x18003fdd2  mov     dword ptr [rbp+57h+Data], eax
0x18003fdd5  xor     r8d, r8d; Reserved
0x18003fdd8  lea     rax, [rbp+57h+Data]
0x18003fddc  mov     [rsp+0A0h+samDesired], 4; cbData
0x18003fde4  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x18003fde9  call    cs:__imp_RegSetValueExW
0x18003fdef  mov     ebx, eax
0x18003fdf1  mov     rcx, [rbp+57h+phkResult]; hKey
0x18003fdf5  call    cs:__imp_RegCloseKey
0x18003fdfb  test    ebx, ebx
0x18003fdfd  jnz     short loc_18003FE11
0x18003fdff  mov     rdi, [rdi+8]
0x18003fe03  test    rdi, rdi
0x18003fe06  jnz     loc_18003FD2C
0x18003fe0c  jmp     short loc_18003FE11
0x18003fe0e  mov     ebx, r14d
0x18003fe11  mov     rcx, [rbp+57h+hKey]; hKey
0x18003fe15  call    cs:__imp_RegCloseKey
0x18003fe1b  mov     eax, ebx
0x18003fe1d  mov     rcx, [rbp+57h+var_18]
0x18003fe21  xor     rcx, rsp; StackCookie
0x18003fe24  call    __security_check_cookie
0x18003fe29  lea     r11, [rsp+0A0h+var_10]
0x18003fe31  mov     rbx, [r11+30h]
0x18003fe35  mov     rsi, [r11+38h]
0x18003fe39  mov     rsp, r11
0x18003fe3c  pop     r14
0x18003fe3e  pop     rdi
0x18003fe3f  pop     rbp
0x18003fe40  retn
```
