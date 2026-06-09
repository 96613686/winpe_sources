# MvSetLanguageProvisioningComplete(int)

- ea: `0x180033a08`
- end: `0x180033abf`
- name: `?MvSetLanguageProvisioningComplete@@YAJH@Z`
- size: `183`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800162f0`
- `0x180018068`

## callees

- `0x180033a08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033aaf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033aaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033a7d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033a5c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033a5c`

## pseudocode

```c
__int64 __fastcall MvSetLanguageProvisioningComplete()
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  BYTE Data[24]; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  *(_DWORD *)Data = 1;
  hKey = 0;
  v0 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegMultivariantStatus, 0, 0, 0, 2u, 0, &hKey, 0);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 <= 0 )
      goto LABEL_4;
    goto LABEL_3;
  }
  v1 = 0;
  v0 = RegSetValueExW(hKey, L"LanguageSet", 0, 4u, Data, 4u);
  if ( v0 )
  {
    if ( v0 > 0 )
    {
LABEL_3:
      v1 = (unsigned __int16)v0 | 0x80070000;
      goto LABEL_4;
    }
    v1 = v0;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180033a08  mov     r11, rsp
0x180033a0b  push    rbx
0x180033a0c  sub     rsp, 60h
0x180033a10  mov     rdx, cs:?gc_wszRegMultivariantStatus@@3PEBGEB; lpSubKey
0x180033a17  lea     rax, [r11+10h]
0x180033a1b  mov     qword ptr [r11-28h], 0
0x180033a23  xor     r9d, r9d; lpClass
0x180033a26  mov     [r11-30h], rax
0x180033a2a  xor     r8d, r8d; Reserved
0x180033a2d  mov     qword ptr [r11-38h], 0
0x180033a35  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033a3c  mov     [rsp+68h+samDesired], 2; samDesired
0x180033a44  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180033a4c  mov     dword ptr [rsp+68h+Data], 1
0x180033a54  mov     qword ptr [r11+10h], 0
0x180033a5c  call    cs:__imp_RegCreateKeyExW
0x180033a62  mov     ebx, eax
0x180033a64  test    eax, eax
0x180033a66  jz      short loc_180033A8B
0x180033a68  jle     short loc_180033A73
0x180033a6a  movzx   ebx, ax
0x180033a6d  or      ebx, 80070000h
0x180033a73  mov     rcx, [rsp+68h+hKey]; hKey
0x180033a78  test    rcx, rcx
0x180033a7b  jz      short loc_180033A83
0x180033a7d  call    cs:__imp_RegCloseKey
0x180033a83  mov     eax, ebx
0x180033a85  add     rsp, 60h
0x180033a89  pop     rbx
0x180033a8a  retn
0x180033a8b  mov     rcx, [rsp+68h+hKey]; hKey
0x180033a90  lea     rax, [rsp+68h+Data]
0x180033a95  xor     ebx, ebx
0x180033a97  lea     rdx, ?gc_wszLanguageSet@@3QBGB; "LanguageSet"
0x180033a9e  xor     r8d, r8d; Reserved
0x180033aa1  lea     r9d, [rbx+4]; dwType
0x180033aa5  mov     [rsp+68h+samDesired], r9d; cbData
0x180033aaa  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180033aaf  call    cs:__imp_RegSetValueExW
0x180033ab5  test    eax, eax
0x180033ab7  jz      short loc_180033A73
0x180033ab9  jg      short loc_180033A6A
0x180033abb  mov     ebx, eax
0x180033abd  jmp     short loc_180033A73
```
