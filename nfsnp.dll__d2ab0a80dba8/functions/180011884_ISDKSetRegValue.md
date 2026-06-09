# ISDKSetRegValue

- ea: `0x180011884`
- end: `0x18001195c`
- name: `ISDKSetRegValue`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001151c`

## callees

- `0x180011884`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180011910`
- `KERNEL32!SetLastError` at `0x180011947`
- `KERNEL32!SetLastError` at `0x180011910`
- `KERNEL32!SetLastError` at `0x180011947`
- `ADVAPI32!RegCreateKeyExW` at `0x1800118d4`
- `ADVAPI32!RegCreateKeyExW` at `0x1800118d4`
- `ADVAPI32!RegSetValueExW` at `0x180011904`
- `ADVAPI32!RegSetValueExW` at `0x180011904`
- `ADVAPI32!RegCloseKey` at `0x18001193d`
- `ADVAPI32!RegCloseKey` at `0x18001193d`

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
0x180011884  mov     r11, rsp
0x180011887  mov     [r11+8], rbx
0x18001188b  push    rdi
0x18001188c  sub     rsp, 50h
0x180011890  lea     rax, [r11+38h]
0x180011894  mov     dword ptr [r11+38h], 0
0x18001189c  mov     [r11-18h], rax
0x1800118a0  mov     rbx, r9
0x1800118a3  lea     rax, [r11+40h]
0x1800118a7  mov     qword ptr [r11+40h], 0
0x1800118af  mov     [r11-20h], rax
0x1800118b3  mov     rdi, r8
0x1800118b6  mov     qword ptr [r11-28h], 0
0x1800118be  xor     r9d, r9d; lpClass
0x1800118c1  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800118c9  xor     r8d, r8d; Reserved
0x1800118cc  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800118d4  call    cs:__imp_RegCreateKeyExW
0x1800118da  test    eax, eax
0x1800118dc  jnz     short loc_180011945
0x1800118de  mov     eax, [rsp+58h+cbData]
0x1800118e5  xor     r8d, r8d; Reserved
0x1800118e8  mov     r9d, [rsp+58h+dwType]; dwType
0x1800118f0  mov     rdx, rdi; lpValueName
0x1800118f3  mov     rcx, [rsp+58h+hKey]; hKey
0x1800118fb  mov     [rsp+58h+samDesired], eax; cbData
0x1800118ff  mov     qword ptr [rsp+58h+dwOptions], rbx; lpData
0x180011904  call    cs:__imp_RegSetValueExW
0x18001190a  test    eax, eax
0x18001190c  jz      short loc_18001191A
0x18001190e  mov     ecx, eax; dwErrCode
0x180011910  call    cs:__imp_SetLastError
0x180011916  xor     ebx, ebx
0x180011918  jmp     short loc_180011935
0x18001191a  mov     rcx, [rsp+58h+arg_40]
0x180011922  mov     ebx, 1
0x180011927  test    rcx, rcx
0x18001192a  jz      short loc_180011935
0x18001192c  mov     eax, [rsp+58h+arg_30]
0x180011933  mov     [rcx], eax
0x180011935  mov     rcx, [rsp+58h+hKey]; hKey
0x18001193d  call    cs:__imp_RegCloseKey
0x180011943  jmp     short loc_18001194F
0x180011945  mov     ecx, eax; dwErrCode
0x180011947  call    cs:__imp_SetLastError
0x18001194d  xor     ebx, ebx
0x18001194f  mov     eax, ebx
0x180011951  mov     rbx, [rsp+58h+arg_0]
0x180011956  add     rsp, 50h
0x18001195a  pop     rdi
0x18001195b  retn
```
