# MvSetPrimaryAppProvisioningComplete(int)

- ea: `0x180033b88`
- end: `0x180033c3f`
- name: `?MvSetPrimaryAppProvisioningComplete@@YAJH@Z`
- size: `183`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f95c`

## callees

- `0x180033b88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033c2f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180033c2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033bfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033bfd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033bdc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033bdc`

## pseudocode

```c
__int64 __fastcall MvSetPrimaryAppProvisioningComplete()
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
  v0 = RegSetValueExW(hKey, L"PrimaryAppProvisioning", 0, 4u, Data, 4u);
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
0x180033b88  mov     r11, rsp
0x180033b8b  push    rbx
0x180033b8c  sub     rsp, 60h
0x180033b90  mov     rdx, cs:?gc_wszRegMultivariantStatus@@3PEBGEB; lpSubKey
0x180033b97  lea     rax, [r11+10h]
0x180033b9b  mov     qword ptr [r11-28h], 0
0x180033ba3  xor     r9d, r9d; lpClass
0x180033ba6  mov     [r11-30h], rax
0x180033baa  xor     r8d, r8d; Reserved
0x180033bad  mov     qword ptr [r11-38h], 0
0x180033bb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033bbc  mov     [rsp+68h+samDesired], 2; samDesired
0x180033bc4  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180033bcc  mov     dword ptr [rsp+68h+Data], 1
0x180033bd4  mov     qword ptr [r11+10h], 0
0x180033bdc  call    cs:__imp_RegCreateKeyExW
0x180033be2  mov     ebx, eax
0x180033be4  test    eax, eax
0x180033be6  jz      short loc_180033C0B
0x180033be8  jle     short loc_180033BF3
0x180033bea  movzx   ebx, ax
0x180033bed  or      ebx, 80070000h
0x180033bf3  mov     rcx, [rsp+68h+hKey]; hKey
0x180033bf8  test    rcx, rcx
0x180033bfb  jz      short loc_180033C03
0x180033bfd  call    cs:__imp_RegCloseKey
0x180033c03  mov     eax, ebx
0x180033c05  add     rsp, 60h
0x180033c09  pop     rbx
0x180033c0a  retn
0x180033c0b  mov     rcx, [rsp+68h+hKey]; hKey
0x180033c10  lea     rax, [rsp+68h+Data]
0x180033c15  xor     ebx, ebx
0x180033c17  lea     rdx, ?gc_wszPrimaryAppProvisioning@@3QBGB; "PrimaryAppProvisioning"
0x180033c1e  xor     r8d, r8d; Reserved
0x180033c21  lea     r9d, [rbx+4]; dwType
0x180033c25  mov     [rsp+68h+samDesired], r9d; cbData
0x180033c2a  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180033c2f  call    cs:__imp_RegSetValueExW
0x180033c35  test    eax, eax
0x180033c37  jz      short loc_180033BF3
0x180033c39  jg      short loc_180033BEA
0x180033c3b  mov     ebx, eax
0x180033c3d  jmp     short loc_180033BF3
```
