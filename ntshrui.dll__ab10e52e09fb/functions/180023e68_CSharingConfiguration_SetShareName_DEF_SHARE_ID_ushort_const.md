# CSharingConfiguration::_SetShareName(DEF_SHARE_ID,ushort const *)

- ea: `0x180023e68`
- end: `0x180023f44`
- name: `?_SetShareName@CSharingConfiguration@@AEAAJW4DEF_SHARE_ID@@PEBG@Z`
- size: `220`
- prototype: `int(CSharingConfiguration *__hidden this, enum DEF_SHARE_ID, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055018`
- `0x1800557b4`

## callees

- `0x180023e68`
- `0x180023f4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023eb2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023eb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023f0f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023f0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023f33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023f33`

## pseudocode

```c
__int64 __fastcall CSharingConfiguration::_SetShareName(
        CSharingConfiguration *this,
        enum DEF_SHARE_ID a2,
        const BYTE *a3)
{
  LSTATUS v5; // eax
  CSharingConfiguration *v6; // rcx
  int v7; // ebx
  unsigned __int64 v8; // r8
  const WCHAR *RegValue; // rax
  DWORD v10; // r8d
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Sharing",
         0,
         0,
         0,
         0x102u,
         0,
         &hKey,
         0);
  v7 = v5;
  if ( v5 > 0 )
    v7 = (unsigned __int16)v5 | 0x80070000;
  if ( v7 >= 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&a3[2 * v8] );
    if ( v8 >= 0x7FFFFFFF )
    {
      LOWORD(v7) = 534;
    }
    else
    {
      RegValue = CSharingConfiguration::_GetRegValue(v6, a2);
      v7 = RegSetValueExW(hKey, RegValue, 0, 1u, a3, v10);
      if ( v7 <= 0 )
      {
LABEL_11:
        RegCloseKey(hKey);
        return (unsigned int)v7;
      }
    }
    v7 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_11;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023e68  mov     r11, rsp
0x180023e6b  mov     [r11+8], rcx
0x180023e6f  push    rbx
0x180023e70  push    rbp
0x180023e71  push    rsi
0x180023e72  push    rdi
0x180023e73  sub     rsp, 58h
0x180023e77  xor     ebp, ebp
0x180023e79  lea     rax, [r11+8]
0x180023e7d  mov     [r11-38h], rbp
0x180023e81  mov     rdi, r8
0x180023e84  mov     [r11-40h], rax
0x180023e88  mov     esi, edx
0x180023e8a  mov     [r11-48h], rbp
0x180023e8e  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180023e95  mov     [rsp+78h+samDesired], 102h; samDesired
0x180023e9d  xor     r9d, r9d; lpClass
0x180023ea0  xor     r8d, r8d; Reserved
0x180023ea3  mov     [rsp+78h+dwOptions], ebp; dwOptions
0x180023ea7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023eae  mov     [r11+8], rbp
0x180023eb2  call    cs:__imp_RegCreateKeyExW
0x180023eb8  mov     ebx, eax
0x180023eba  test    eax, eax
0x180023ebc  jle     short loc_180023EC7
0x180023ebe  movzx   ebx, ax
0x180023ec1  or      ebx, 80070000h
0x180023ec7  test    ebx, ebx
0x180023ec9  js      short loc_180023F39
0x180023ecb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023ecf  inc     r8
0x180023ed2  cmp     [rdi+r8*2], bp
0x180023ed7  jnz     short loc_180023ECF
0x180023ed9  cmp     r8, 7FFFFFFFh
0x180023ee0  jnb     short loc_180023F1D
0x180023ee2  mov     edx, esi; enum DEF_SHARE_ID
0x180023ee4  lea     r8d, ds:2[r8*2]
0x180023eec  call    ?_GetRegValue@CSharingConfiguration@@AEAAPEBGW4DEF_SHARE_ID@@@Z; CSharingConfiguration::_GetRegValue(DEF_SHARE_ID)
0x180023ef1  mov     rcx, [rsp+78h+hKey]; hKey
0x180023ef9  mov     rdx, rax; lpValueName
0x180023efc  mov     [rsp+78h+samDesired], r8d; cbData
0x180023f01  mov     r9d, 1; dwType
0x180023f07  xor     r8d, r8d; Reserved
0x180023f0a  mov     qword ptr [rsp+78h+dwOptions], rdi; lpData
0x180023f0f  call    cs:__imp_RegSetValueExW
0x180023f15  mov     ebx, eax
0x180023f17  test    eax, eax
0x180023f19  jle     short loc_180023F2B
0x180023f1b  jmp     short loc_180023F22
0x180023f1d  mov     ebx, 216h
0x180023f22  movzx   ebx, bx
0x180023f25  or      ebx, 80070000h
0x180023f2b  mov     rcx, [rsp+78h+hKey]; hKey
0x180023f33  call    cs:__imp_RegCloseKey
0x180023f39  mov     eax, ebx
0x180023f3b  add     rsp, 58h
0x180023f3f  pop     rdi
0x180023f40  pop     rsi
0x180023f41  pop     rbp
0x180023f42  pop     rbx
0x180023f43  retn
```
