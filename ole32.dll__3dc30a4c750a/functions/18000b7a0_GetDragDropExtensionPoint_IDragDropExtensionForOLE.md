# GetDragDropExtensionPoint(IDragDropExtensionForOLE * *)

- ea: `0x18000b7a0`
- end: `0x18000b8eb`
- name: `?GetDragDropExtensionPoint@@YAJPEAPEAUIDragDropExtensionForOLE@@@Z`
- size: `331`
- prototype: `HRESULT __fastcall(IDragDropExtensionForOLE **ppExtension)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ad74`
- `0x18000b9bc`
- `0x1800340d8`
- `0x18004254c`

## callees

- `0x18000b7a0`
- `0x180052390`
- `0x180053014`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b7ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b7ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b864`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b864`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b88f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b88f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b8b2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b8b2`

## string_xrefs

- `0x18000b7f5`: `SOFTWARE\Microsoft\Ole\Extensions`
- `0x18000b859`: `DragDropExtension`

## pseudocode

```c
__int64 __fastcall GetDragDropExtensionPoint(LPVOID *ppExtension)
{
  LSTATUS v2; // eax
  int v3; // ebx
  LSTATUS v4; // eax
  unsigned int cb; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int dwType; // [rsp+34h] [rbp-CCh] BYREF
  HKEY__ *hkeyOle; // [rsp+38h] [rbp-C8h] BYREF
  _GUID clsid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR pszCLSID[264]; // [rsp+50h] [rbp-B0h] BYREF

  *ppExtension = 0;
  hkeyOle = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Ole\\Extensions", 0, 1u, &hkeyOle);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    memset_0(pszCLSID, 0, 0x208u);
    dwType = 0;
    cb = 520;
    v4 = RegQueryValueExW(hkeyOle, L"DragDropExtension", 0, &dwType, (LPBYTE)pszCLSID, &cb);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
    {
      clsid = 0;
      v3 = CLSIDFromString(pszCLSID, &clsid);
      if ( v3 >= 0 )
        v3 = CoCreateInstance(&clsid, 0, 1u, &GUID_043250db_3b6a_4141_8f21_aa2ed2be3355, ppExtension);
    }
    RegCloseKey(hkeyOle);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b7a0  mov     [rsp-8+arg_8], rbx
0x18000b7a5  mov     [rsp-8+arg_10], rdi
0x18000b7aa  push    rbp
0x18000b7ab  lea     rbp, [rsp-170h]
0x18000b7b3  sub     rsp, 270h
0x18000b7ba  mov     rax, cs:__security_cookie
0x18000b7c1  xor     rax, rsp
0x18000b7c4  mov     [rbp+170h+var_10], rax
0x18000b7cb  mov     rdi, ppExtension
0x18000b7ce  mov     qword ptr [ppExtension], 0
0x18000b7d5  lea     rax, [rsp+270h+hkeyOle]
0x18000b7da  mov     [rsp+270h+hkeyOle], 0
0x18000b7e3  mov     ppExtension, 0FFFFFFFF80000002h; hKey
0x18000b7ea  mov     [rsp+270h+phkResult], rax; phkResult
0x18000b7ef  mov     r9d, 1; samDesired
0x18000b7f5  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Ole\\Extensions"
0x18000b7fc  xor     r8d, r8d; ulOptions
0x18000b7ff  call    cs:__imp_RegOpenKeyExW
0x18000b805  mov     ebx, eax
0x18000b807  test    eax, eax
0x18000b809  jle     short loc_18000B814
0x18000b80b  movzx   ebx, ax
0x18000b80e  or      ebx, 80070000h
0x18000b814  test    ebx, ebx
0x18000b816  js      loc_18000B8C5
0x18000b81c  mov     ebx, 208h
0x18000b821  lea     ppExtension, [rsp+270h+pszCLSID]; void *
0x18000b826  mov     r8d, ebx; Size
0x18000b829  xor     edx, edx; Val
0x18000b82b  call    memset_0
0x18000b830  mov     ppExtension, [rsp+270h+hkeyOle]; hKey
0x18000b835  lea     rax, [rsp+270h+cb]
0x18000b83a  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000b83f  lea     r9, [rsp+270h+dwType]; lpType
0x18000b844  lea     rax, [rsp+270h+pszCLSID]
0x18000b849  mov     [rsp+270h+dwType], 0
0x18000b851  xor     r8d, r8d; lpReserved
0x18000b854  mov     [rsp+270h+phkResult], rax; lpData
0x18000b859  lea     rdx, aDragdropextens; "DragDropExtension"
0x18000b860  mov     [rsp+270h+cb], ebx
0x18000b864  call    cs:__imp_RegQueryValueExW
0x18000b86a  mov     ebx, eax
0x18000b86c  test    eax, eax
0x18000b86e  jle     short loc_18000B879
0x18000b870  movzx   ebx, ax
0x18000b873  or      ebx, 80070000h
0x18000b879  test    ebx, ebx
0x18000b87b  js      short loc_18000B8BA
0x18000b87d  xorps   xmm0, xmm0
0x18000b880  lea     rdx, [rsp+270h+clsid]; pclsid
0x18000b885  lea     ppExtension, [rsp+270h+pszCLSID]; lpsz
0x18000b88a  movups  xmmword ptr [rsp+270h+clsid.Data1], xmm0
0x18000b88f  call    cs:__imp_CLSIDFromString
0x18000b895  mov     ebx, eax
0x18000b897  test    eax, eax
0x18000b899  js      short loc_18000B8BA
0x18000b89b  xor     edx, edx; pUnkOuter
0x18000b89d  mov     [rsp+270h+phkResult], rdi; ppv
0x18000b8a2  lea     r9, _GUID_043250db_3b6a_4141_8f21_aa2ed2be3355; riid
0x18000b8a9  lea     ppExtension, [rsp+270h+clsid]; rclsid
0x18000b8ae  lea     r8d, [rdx+1]; dwClsContext
0x18000b8b2  call    cs:__imp_CoCreateInstance
0x18000b8b8  mov     ebx, eax
0x18000b8ba  mov     ppExtension, [rsp+270h+hkeyOle]; hKey
0x18000b8bf  call    cs:__imp_RegCloseKey
0x18000b8c5  mov     eax, ebx
0x18000b8c7  mov     ppExtension, [rbp+170h+var_10]
0x18000b8ce  xor     ppExtension, rsp; StackCookie
0x18000b8d1  call    __security_check_cookie
0x18000b8d6  lea     r11, [rsp+270h+var_s0]
0x18000b8de  mov     rbx, [r11+18h]
0x18000b8e2  mov     rdi, [r11+20h]
0x18000b8e6  mov     rsp, r11
0x18000b8e9  pop     rbp
0x18000b8ea  retn
```
