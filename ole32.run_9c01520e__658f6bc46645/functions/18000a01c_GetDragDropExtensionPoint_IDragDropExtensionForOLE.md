# GetDragDropExtensionPoint(IDragDropExtensionForOLE * *)

- ea: `0x18000a01c`
- end: `0x18000a17d`
- name: `?GetDragDropExtensionPoint@@YAJPEAPEAUIDragDropExtensionForOLE@@@Z`
- size: `353`
- prototype: `HRESULT __fastcall(IDragDropExtensionForOLE **ppExtension)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009654`
- `0x18000a254`
- `0x18003674c`
- `0x180044d0c`

## callees

- `0x18000a01c`
- `0x180046460`
- `0x180047484`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a075`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a075`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a0dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a0dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a14a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a14a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000a10e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000a10e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a137`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a137`

## string_xrefs

- `0x18000a056`: `SOFTWARE\Microsoft\Ole\Extensions`
- `0x18000a0c5`: `DragDropExtension`

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
0x18000a01c  mov     [rsp-8+arg_8], rbx
0x18000a021  mov     [rsp-8+arg_10], rdi
0x18000a026  push    rbp
0x18000a027  lea     rbp, [rsp-170h]
0x18000a02f  sub     rsp, 270h
0x18000a036  mov     rax, cs:__security_cookie
0x18000a03d  xor     rax, rsp
0x18000a040  mov     [rbp+170h+var_10], rax
0x18000a047  and     qword ptr [ppExtension], 0
0x18000a04b  lea     rax, [rsp+270h+hkeyOle]
0x18000a050  and     [rsp+270h+hkeyOle], 0
0x18000a056  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Ole\\Extensions"
0x18000a05d  mov     rdi, ppExtension
0x18000a060  mov     [rsp+270h+phkResult], rax; phkResult
0x18000a065  mov     ppExtension, 0FFFFFFFF80000002h; hKey
0x18000a06c  mov     r9d, 1; samDesired
0x18000a072  xor     r8d, r8d; ulOptions
0x18000a075  call    cs:__imp_RegOpenKeyExW
0x18000a07c  nop     dword ptr [rax+rax+00h]
0x18000a081  mov     ebx, eax
0x18000a083  test    eax, eax
0x18000a085  jle     short loc_18000A090
0x18000a087  movzx   ebx, ax
0x18000a08a  or      ebx, 80070000h
0x18000a090  test    ebx, ebx
0x18000a092  js      loc_18000A156
0x18000a098  mov     ebx, 208h
0x18000a09d  lea     ppExtension, [rsp+270h+pszCLSID]; void *
0x18000a0a2  mov     r8d, ebx; Size
0x18000a0a5  xor     edx, edx; Val
0x18000a0a7  call    memset_0
0x18000a0ac  mov     ppExtension, [rsp+270h+hkeyOle]; hKey
0x18000a0b1  lea     rax, [rsp+270h+cb]
0x18000a0b6  and     [rsp+270h+dwType], 0
0x18000a0bb  lea     r9, [rsp+270h+dwType]; lpType
0x18000a0c0  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000a0c5  lea     rdx, aDragdropextens; "DragDropExtension"
0x18000a0cc  lea     rax, [rsp+270h+pszCLSID]
0x18000a0d1  mov     [rsp+270h+cb], ebx
0x18000a0d5  xor     r8d, r8d; lpReserved
0x18000a0d8  mov     [rsp+270h+phkResult], rax; lpData
0x18000a0dd  call    cs:__imp_RegQueryValueExW
0x18000a0e4  nop     dword ptr [rax+rax+00h]
0x18000a0e9  mov     ebx, eax
0x18000a0eb  test    eax, eax
0x18000a0ed  jle     short loc_18000A0F8
0x18000a0ef  movzx   ebx, ax
0x18000a0f2  or      ebx, 80070000h
0x18000a0f8  test    ebx, ebx
0x18000a0fa  js      short loc_18000A145
0x18000a0fc  xorps   xmm0, xmm0
0x18000a0ff  lea     rdx, [rsp+270h+clsid]; pclsid
0x18000a104  lea     ppExtension, [rsp+270h+pszCLSID]; lpsz
0x18000a109  movups  xmmword ptr [rsp+270h+clsid.Data1], xmm0
0x18000a10e  call    cs:__imp_CLSIDFromString
0x18000a115  nop     dword ptr [rax+rax+00h]
0x18000a11a  mov     ebx, eax
0x18000a11c  test    eax, eax
0x18000a11e  js      short loc_18000A145
0x18000a120  xor     edx, edx; pUnkOuter
0x18000a122  mov     [rsp+270h+phkResult], rdi; ppv
0x18000a127  lea     r9, _GUID_043250db_3b6a_4141_8f21_aa2ed2be3355; riid
0x18000a12e  lea     ppExtension, [rsp+270h+clsid]; rclsid
0x18000a133  lea     r8d, [rdx+1]; dwClsContext
0x18000a137  call    cs:__imp_CoCreateInstance
0x18000a13e  nop     dword ptr [rax+rax+00h]
0x18000a143  mov     ebx, eax
0x18000a145  mov     ppExtension, [rsp+270h+hkeyOle]; hKey
0x18000a14a  call    cs:__imp_RegCloseKey
0x18000a151  nop     dword ptr [rax+rax+00h]
0x18000a156  mov     eax, ebx
0x18000a158  mov     ppExtension, [rbp+170h+var_10]
0x18000a15f  xor     ppExtension, rsp; StackCookie
0x18000a162  call    __security_check_cookie
0x18000a167  lea     r11, [rsp+270h+var_s0]
0x18000a16f  mov     rbx, [r11+18h]
0x18000a173  mov     rdi, [r11+20h]
0x18000a177  mov     rsp, r11
0x18000a17a  pop     rbp
0x18000a17b  retn
```
