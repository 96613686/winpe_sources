# GetStartValue(unsigned __int64 *)

- ea: `0x180002dc4`
- end: `0x180002f1d`
- name: `?GetStartValue@@YAJPEA_K@Z`
- size: `345`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180004220`

## callees

- `0x180002dc4`
- `0x180004770`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002e64`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002e64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002e9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002e9e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002ee3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002ee3`

## string_xrefs

- `0x180002e1f`: `SYSTEM\CurrentControlSet\Services\FDResPub\ServiceData`

## pseudocode

```c
__int64 __fastcall GetStartValue(BYTE *lpData)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp+28h] BYREF
  DWORD Type; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  if ( !lpData )
    return 2147942487LL;
  *(_QWORD *)lpData = 0;
  dwDisposition = 0;
  hKey = 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\FDResPub\\ServiceData",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         &dwDisposition);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    Type = 0;
    cbData = 8;
    RegQueryValueExW(hKey, L"FirstStart", 0, &Type, lpData, &cbData);
    *(_QWORD *)lpData = (*(_QWORD *)lpData + 1LL) & -(__int64)(*(_QWORD *)lpData < 0xFFFFFFFF);
    cbData = 8;
    v5 = RegSetValueExW(hKey, L"FirstStart", 0, 3u, lpData, 8u);
    if ( v5 )
    {
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      else
        v4 = v5;
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x180002dc4  push    rbp
0x180002dc6  push    rbx
0x180002dc7  push    rdi
0x180002dc8  mov     rbp, rsp
0x180002dcb  sub     rsp, 50h
0x180002dcf  mov     rdi, rcx
0x180002dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dd9  lea     rax, WPP_GLOBAL_Control
0x180002de0  cmp     rcx, rax
0x180002de3  jz      short loc_180002E00
0x180002de5  cmp     byte ptr [rcx+19h], 4
0x180002de9  jb      short loc_180002E00
0x180002deb  mov     rcx, [rcx+10h]
0x180002def  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002df6  mov     edx, 0Ah
0x180002dfb  call    WPP_SF_s
0x180002e00  test    rdi, rdi
0x180002e03  jnz     short loc_180002E0F
0x180002e05  mov     eax, 80070057h
0x180002e0a  jmp     loc_180002F15
0x180002e0f  lea     rax, [rbp+dwDisposition]
0x180002e13  mov     qword ptr [rdi], 0
0x180002e1a  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180002e1f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\FD"...
0x180002e26  lea     rax, [rbp+hKey]
0x180002e2a  mov     [rbp+dwDisposition], 0
0x180002e31  mov     [rsp+50h+phkResult], rax; phkResult
0x180002e36  xor     r9d, r9d; lpClass
0x180002e39  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180002e42  xor     r8d, r8d; Reserved
0x180002e45  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x180002e4d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002e54  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180002e5c  mov     [rbp+hKey], 0
0x180002e64  call    cs:__imp_RegCreateKeyExW
0x180002e6a  mov     ebx, eax
0x180002e6c  test    eax, eax
0x180002e6e  jnz     loc_180002F08
0x180002e74  mov     rcx, [rbp+hKey]; hKey
0x180002e78  lea     r9, [rbp+Type]; lpType
0x180002e7c  mov     [rbp+Type], eax
0x180002e7f  lea     rdx, ValueName; "FirstStart"
0x180002e86  lea     rax, [rbp+cbData]
0x180002e8a  mov     [rbp+cbData], 8
0x180002e91  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x180002e96  xor     r8d, r8d; lpReserved
0x180002e99  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x180002e9e  call    cs:__imp_RegQueryValueExW
0x180002ea4  mov     rax, [rdi]
0x180002ea7  lea     r9d, [rbx+3]; dwType
0x180002eab  mov     r8d, 0FFFFFFFFh
0x180002eb1  mov     [rsp+50h+samDesired], 8; cbData
0x180002eb9  cmp     rax, r8
0x180002ebc  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x180002ec1  lea     rdx, ValueName; "FirstStart"
0x180002ec8  lea     rcx, [rax+1]
0x180002ecc  sbb     rax, rax
0x180002ecf  and     rax, rcx
0x180002ed2  xor     r8d, r8d; Reserved
0x180002ed5  mov     [rdi], rax
0x180002ed8  mov     rcx, [rbp+hKey]; hKey
0x180002edc  mov     [rbp+cbData], 8
0x180002ee3  call    cs:__imp_RegSetValueExW
0x180002ee9  test    eax, eax
0x180002eeb  jz      short loc_180002EFC
0x180002eed  jg      short loc_180002EF3
0x180002eef  mov     ebx, eax
0x180002ef1  jmp     short loc_180002EFC
0x180002ef3  movzx   ebx, ax
0x180002ef6  or      ebx, 80070000h
0x180002efc  mov     rcx, [rbp+hKey]; hKey
0x180002f00  call    cs:__imp_RegCloseKey
0x180002f06  jmp     short loc_180002F13
0x180002f08  jle     short loc_180002F13
0x180002f0a  movzx   ebx, ax
0x180002f0d  or      ebx, 80070000h
0x180002f13  mov     eax, ebx
0x180002f15  add     rsp, 50h
0x180002f19  pop     rdi
0x180002f1a  pop     rbx
0x180002f1b  pop     rbp
0x180002f1c  retn
```
