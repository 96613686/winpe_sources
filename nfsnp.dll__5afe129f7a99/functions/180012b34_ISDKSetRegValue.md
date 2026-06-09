# ISDKSetRegValue

- ea: `0x180012b34`
- end: `0x180012c2b`
- name: `ISDKSetRegValue`
- size: `247`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, const BYTE *, DWORD dwType, DWORD cbData, DWORD, HKEY hKey, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800127a4`

## callees

- `0x180012b34`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180012bcc`
- `KERNEL32!SetLastError` at `0x180012c0f`
- `KERNEL32!SetLastError` at `0x180012bcc`
- `KERNEL32!SetLastError` at `0x180012c0f`
- `ADVAPI32!RegCreateKeyExW` at `0x180012b84`
- `ADVAPI32!RegCreateKeyExW` at `0x180012b84`
- `ADVAPI32!RegSetValueExW` at `0x180012bba`
- `ADVAPI32!RegSetValueExW` at `0x180012bba`
- `ADVAPI32!RegCloseKey` at `0x180012bff`
- `ADVAPI32!RegCloseKey` at `0x180012bff`

## pseudocode

```c
__int64 __fastcall ISDKSetRegValue(
        HKEY a1,
        const WCHAR *a2,
        const WCHAR *a3,
        const BYTE *a4,
        DWORD dwType,
        DWORD cbData,
        DWORD a7,
        HKEY hKey,
        _DWORD *a9)
{
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  unsigned int v13; // ebx

  a7 = 0;
  hKey = 0;
  v11 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, &a7);
  if ( v11 )
  {
    SetLastError(v11);
    return 0;
  }
  else
  {
    v12 = RegSetValueExW(hKey, a3, 0, dwType, a4, cbData);
    if ( v12 )
    {
      SetLastError(v12);
      v13 = 0;
    }
    else
    {
      v13 = 1;
      if ( a9 )
        *a9 = a7;
    }
    RegCloseKey(hKey);
  }
  return v13;
}

```

## disassembly

```asm
0x180012b34  mov     r11, rsp
0x180012b37  mov     [r11+8], rbx
0x180012b3b  push    rdi
0x180012b3c  sub     rsp, 50h
0x180012b40  lea     rax, [r11+38h]
0x180012b44  mov     dword ptr [r11+38h], 0
0x180012b4c  mov     [r11-18h], rax
0x180012b50  mov     rbx, r9
0x180012b53  lea     rax, [r11+40h]
0x180012b57  mov     qword ptr [r11+40h], 0
0x180012b5f  mov     [r11-20h], rax
0x180012b63  mov     rdi, r8
0x180012b66  mov     qword ptr [r11-28h], 0
0x180012b6e  xor     r9d, r9d; lpClass
0x180012b71  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180012b79  xor     r8d, r8d; Reserved
0x180012b7c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180012b84  call    cs:__imp_RegCreateKeyExW
0x180012b8b  nop     dword ptr [rax+rax+00h]
0x180012b90  test    eax, eax
0x180012b92  jnz     short loc_180012C0D
0x180012b94  mov     eax, [rsp+58h+cbData]
0x180012b9b  xor     r8d, r8d; Reserved
0x180012b9e  mov     r9d, [rsp+58h+dwType]; dwType
0x180012ba6  mov     rdx, rdi; lpValueName
0x180012ba9  mov     rcx, [rsp+58h+hKey]; hKey
0x180012bb1  mov     [rsp+58h+samDesired], eax; cbData
0x180012bb5  mov     qword ptr [rsp+58h+dwOptions], rbx; lpData
0x180012bba  call    cs:__imp_RegSetValueExW
0x180012bc1  nop     dword ptr [rax+rax+00h]
0x180012bc6  test    eax, eax
0x180012bc8  jz      short loc_180012BDC
0x180012bca  mov     ecx, eax; dwErrCode
0x180012bcc  call    cs:__imp_SetLastError
0x180012bd3  nop     dword ptr [rax+rax+00h]
0x180012bd8  xor     ebx, ebx
0x180012bda  jmp     short loc_180012BF7
0x180012bdc  mov     rcx, [rsp+58h+arg_40]
0x180012be4  mov     ebx, 1
0x180012be9  test    rcx, rcx
0x180012bec  jz      short loc_180012BF7
0x180012bee  mov     eax, [rsp+58h+arg_30]
0x180012bf5  mov     [rcx], eax
0x180012bf7  mov     rcx, [rsp+58h+hKey]; hKey
0x180012bff  call    cs:__imp_RegCloseKey
0x180012c06  nop     dword ptr [rax+rax+00h]
0x180012c0b  jmp     short loc_180012C1D
0x180012c0d  mov     ecx, eax; dwErrCode
0x180012c0f  call    cs:__imp_SetLastError
0x180012c16  nop     dword ptr [rax+rax+00h]
0x180012c1b  xor     ebx, ebx
0x180012c1d  mov     eax, ebx
0x180012c1f  mov     rbx, [rsp+58h+arg_0]
0x180012c24  add     rsp, 50h
0x180012c28  pop     rdi
0x180012c29  retn
```
