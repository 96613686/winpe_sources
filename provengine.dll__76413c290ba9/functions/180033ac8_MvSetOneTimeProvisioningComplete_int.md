# MvSetOneTimeProvisioningComplete(int)

- ea: `0x180033ac8`
- end: `0x180033b7f`
- name: `?MvSetOneTimeProvisioningComplete@@YAJH@Z`
- size: `183`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018068`

## callees

- `0x180033ac8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033b6f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033b6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033b3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033b3d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033b1c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033b1c`

## pseudocode

```c
__int64 __fastcall MvSetOneTimeProvisioningComplete()
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
  v0 = RegSetValueExW(hKey, L"OneTimeProvisioning", 0, 4u, Data, 4u);
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
0x180033ac8  mov     r11, rsp
0x180033acb  push    rbx
0x180033acc  sub     rsp, 60h
0x180033ad0  mov     rdx, cs:?gc_wszRegMultivariantStatus@@3PEBGEB; lpSubKey
0x180033ad7  lea     rax, [r11+10h]
0x180033adb  mov     qword ptr [r11-28h], 0
0x180033ae3  xor     r9d, r9d; lpClass
0x180033ae6  mov     [r11-30h], rax
0x180033aea  xor     r8d, r8d; Reserved
0x180033aed  mov     qword ptr [r11-38h], 0
0x180033af5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033afc  mov     [rsp+68h+samDesired], 2; samDesired
0x180033b04  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180033b0c  mov     dword ptr [rsp+68h+Data], 1
0x180033b14  mov     qword ptr [r11+10h], 0
0x180033b1c  call    cs:__imp_RegCreateKeyExW
0x180033b22  mov     ebx, eax
0x180033b24  test    eax, eax
0x180033b26  jz      short loc_180033B4B
0x180033b28  jle     short loc_180033B33
0x180033b2a  movzx   ebx, ax
0x180033b2d  or      ebx, 80070000h
0x180033b33  mov     rcx, [rsp+68h+hKey]; hKey
0x180033b38  test    rcx, rcx
0x180033b3b  jz      short loc_180033B43
0x180033b3d  call    cs:__imp_RegCloseKey
0x180033b43  mov     eax, ebx
0x180033b45  add     rsp, 60h
0x180033b49  pop     rbx
0x180033b4a  retn
0x180033b4b  mov     rcx, [rsp+68h+hKey]; hKey
0x180033b50  lea     rax, [rsp+68h+Data]
0x180033b55  xor     ebx, ebx
0x180033b57  lea     rdx, ?gc_wszOneTimeProvisioning@@3QBGB; "OneTimeProvisioning"
0x180033b5e  xor     r8d, r8d; Reserved
0x180033b61  lea     r9d, [rbx+4]; dwType
0x180033b65  mov     [rsp+68h+samDesired], r9d; cbData
0x180033b6a  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180033b6f  call    cs:__imp_RegSetValueExW
0x180033b75  test    eax, eax
0x180033b77  jz      short loc_180033B33
0x180033b79  jg      short loc_180033B2A
0x180033b7b  mov     ebx, eax
0x180033b7d  jmp     short loc_180033B33
```
