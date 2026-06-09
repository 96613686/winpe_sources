# HwCfgIndexToGuid

- ea: `0x180004a04`
- end: `0x180004c0c`
- name: `HwCfgIndexToGuid`
- size: `520`
- prototype: `__int64 __fastcall(int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180004e74`

## callees

- `0x18000480c`
- `0x180004a04`
- `0x180008df2`
- `0x180008e30`

## import_xrefs

- `ntdll!RtlGUIDFromString` at `0x180004b23`
- `ntdll!RtlGUIDFromString` at `0x180004b23`
- `ntdll!RtlInitUnicodeStringEx` at `0x180004b11`
- `ntdll!RtlInitUnicodeStringEx` at `0x180004b11`
- `ADVAPI32!RegEnumKeyExW` at `0x180004ae4`
- `ADVAPI32!RegEnumKeyExW` at `0x180004ae4`
- `ADVAPI32!RegOpenKeyExW` at `0x180004b45`
- `ADVAPI32!RegOpenKeyExW` at `0x180004b45`
- `ADVAPI32!RegCloseKey` at `0x180004a9d`
- `ADVAPI32!RegCloseKey` at `0x180004bd0`
- `ADVAPI32!RegCloseKey` at `0x180004bdf`
- `ADVAPI32!RegCloseKey` at `0x180004a9d`
- `ADVAPI32!RegCloseKey` at `0x180004bd0`
- `ADVAPI32!RegCloseKey` at `0x180004bdf`
- `ADVAPI32!RegQueryValueExW` at `0x180004b7a`
- `ADVAPI32!RegQueryValueExW` at `0x180004b7a`

## pseudocode

```c
__int64 __fastcall HwCfgIndexToGuid(int a1, void *a2)
{
  unsigned int RootKey; // ebx
  DWORD i; // esi
  LSTATUS v6; // eax
  DWORD cchName; // [rsp+40h] [rbp-59h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-55h] BYREF
  DWORD Type; // [rsp+48h] [rbp-51h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-4Dh] BYREF
  HKEY v12; // [rsp+50h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-41h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  GUID Guid; // [rsp+70h] [rbp-29h] BYREF
  WCHAR Name[40]; // [rsp+80h] [rbp-19h] BYREF

  v12 = 0;
  hKey = 0;
  cchName = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  DestinationString = 0;
  Guid = 0;
  if ( !a2 )
    return 87;
  RootKey = HwCfgGetRootKey(0x20019u, &v12);
  if ( RootKey )
    goto LABEL_21;
  for ( i = 0; ; ++i )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    cchName = 39;
    v6 = RegEnumKeyExW(v12, i, Name, &cchName, 0, 0, 0, 0);
    RootKey = v6;
    if ( v6 == 234 )
      continue;
    if ( v6 )
      break;
    if ( cchName >= 0x26
      && !RtlInitUnicodeStringEx(&DestinationString, Name)
      && !RtlGUIDFromString(&DestinationString, &Guid)
      && !RegOpenKeyExW(v12, Name, 0, RootKey + 1, &hKey) )
    {
      cbData = 4;
      RootKey = RegQueryValueExW(hKey, L"Id", 0, &Type, Data, &cbData);
      if ( !RootKey && Type == 4 && cbData == 4 && a1 == *(_DWORD *)Data )
      {
        memcpy_0(a2, Name, 2LL * (cchName + 1));
        goto LABEL_21;
      }
    }
  }
  if ( v6 == 259 )
    RootKey = 1168;
LABEL_21:
  if ( v12 )
    RegCloseKey(v12);
  if ( hKey )
    RegCloseKey(hKey);
  return RootKey;
}

```

## disassembly

```asm
0x180004a04  mov     [rsp-8+arg_0], rbx
0x180004a09  mov     [rsp-8+arg_10], rsi
0x180004a0e  push    rbp
0x180004a0f  push    r14
0x180004a11  push    r15
0x180004a13  lea     rbp, [rsp-47h]
0x180004a18  sub     rsp, 0E0h
0x180004a1f  mov     rax, cs:__security_cookie
0x180004a26  xor     rax, rsp
0x180004a29  mov     [rbp+57h+var_20], rax
0x180004a2d  mov     [rbp+57h+var_A0], 0
0x180004a35  xorps   xmm0, xmm0
0x180004a38  mov     [rbp+57h+hKey], 0
0x180004a40  xorps   xmm1, xmm1
0x180004a43  mov     [rbp+57h+cchName], 0
0x180004a4a  mov     r14, rdx
0x180004a4d  mov     [rbp+57h+Type], 0
0x180004a54  mov     r15d, ecx
0x180004a57  mov     [rbp+57h+cbData], 0
0x180004a5e  mov     dword ptr [rbp+57h+Data], 0
0x180004a65  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180004a69  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm1
0x180004a6d  test    rdx, rdx
0x180004a70  jnz     short loc_180004A7A
0x180004a72  lea     ebx, [rdx+57h]
0x180004a75  jmp     loc_180004BE5
0x180004a7a  lea     rdx, [rbp+57h+var_A0]
0x180004a7e  mov     ecx, 20019h; samDesired
0x180004a83  call    HwCfgGetRootKey
0x180004a88  mov     ebx, eax
0x180004a8a  test    eax, eax
0x180004a8c  jnz     loc_180004BC5
0x180004a92  xor     esi, esi
0x180004a94  mov     rcx, [rbp+57h+hKey]; hKey
0x180004a98  test    rcx, rcx
0x180004a9b  jz      short loc_180004AAB
0x180004a9d  call    cs:__imp_RegCloseKey
0x180004aa3  mov     [rbp+57h+hKey], 0
0x180004aab  mov     rcx, [rbp+57h+var_A0]; hKey
0x180004aaf  lea     r9, [rbp+57h+cchName]; lpcchName
0x180004ab3  mov     [rsp+0F0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180004abc  lea     r8, [rbp+57h+Name]; lpName
0x180004ac0  mov     [rsp+0F0h+lpcchClass], 0; lpcchClass
0x180004ac9  mov     edx, esi; dwIndex
0x180004acb  mov     [rsp+0F0h+lpClass], 0; lpClass
0x180004ad4  mov     [rsp+0F0h+lpReserved], 0; lpReserved
0x180004add  mov     [rbp+57h+cchName], 27h ; '''
0x180004ae4  call    cs:__imp_RegEnumKeyExW
0x180004aea  mov     ebx, eax
0x180004aec  cmp     eax, 0EAh
0x180004af1  jz      loc_180004B98
0x180004af7  test    eax, eax
0x180004af9  jnz     loc_180004BB7
0x180004aff  cmp     [rbp+57h+cchName], 26h ; '&'
0x180004b03  jb      loc_180004B98
0x180004b09  lea     rdx, [rbp+57h+Name]; SourceString
0x180004b0d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180004b11  call    cs:__imp_RtlInitUnicodeStringEx
0x180004b17  test    eax, eax
0x180004b19  jnz     short loc_180004B98
0x180004b1b  lea     rdx, [rbp+57h+Guid]; Guid
0x180004b1f  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x180004b23  call    cs:__imp_RtlGUIDFromString
0x180004b29  test    eax, eax
0x180004b2b  jnz     short loc_180004B98
0x180004b2d  mov     rcx, [rbp+57h+var_A0]; hKey
0x180004b31  lea     rax, [rbp+57h+hKey]
0x180004b35  lea     r9d, [rbx+1]; samDesired
0x180004b39  mov     [rsp+0F0h+lpReserved], rax; phkResult
0x180004b3e  xor     r8d, r8d; ulOptions
0x180004b41  lea     rdx, [rbp+57h+Name]; lpSubKey
0x180004b45  call    cs:__imp_RegOpenKeyExW
0x180004b4b  test    eax, eax
0x180004b4d  jnz     short loc_180004B98
0x180004b4f  mov     rcx, [rbp+57h+hKey]; hKey
0x180004b53  lea     rax, [rbp+57h+cbData]
0x180004b57  mov     [rsp+0F0h+lpClass], rax; lpcbData
0x180004b5c  lea     r9, [rbp+57h+Type]; lpType
0x180004b60  lea     rax, [rbp+57h+Data]
0x180004b64  mov     [rbp+57h+cbData], 4
0x180004b6b  xor     r8d, r8d; lpReserved
0x180004b6e  mov     [rsp+0F0h+lpReserved], rax; lpData
0x180004b73  lea     rdx, aId; "Id"
0x180004b7a  call    cs:__imp_RegQueryValueExW
0x180004b80  mov     ebx, eax
0x180004b82  test    eax, eax
0x180004b84  jnz     short loc_180004B98
0x180004b86  cmp     [rbp+57h+Type], 4
0x180004b8a  jnz     short loc_180004B98
0x180004b8c  cmp     [rbp+57h+cbData], 4
0x180004b90  jnz     short loc_180004B98
0x180004b92  cmp     r15d, dword ptr [rbp+57h+Data]
0x180004b96  jz      short loc_180004B9F
0x180004b98  inc     esi
0x180004b9a  jmp     loc_180004A94
0x180004b9f  mov     r8d, [rbp+57h+cchName]
0x180004ba3  lea     rdx, [rbp+57h+Name]; Src
0x180004ba7  inc     r8d
0x180004baa  mov     rcx, r14; void *
0x180004bad  add     r8, r8; Size
0x180004bb0  call    memcpy_0
0x180004bb5  jmp     short loc_180004BC5
0x180004bb7  cmp     ebx, 103h
0x180004bbd  mov     eax, 490h
0x180004bc2  cmovz   ebx, eax
0x180004bc5  cmp     [rbp+57h+var_A0], 0
0x180004bca  jz      short loc_180004BD6
0x180004bcc  mov     rcx, [rbp+57h+var_A0]; hKey
0x180004bd0  call    cs:__imp_RegCloseKey
0x180004bd6  mov     rcx, [rbp+57h+hKey]; hKey
0x180004bda  test    rcx, rcx
0x180004bdd  jz      short loc_180004BE5
0x180004bdf  call    cs:__imp_RegCloseKey
0x180004be5  mov     eax, ebx
0x180004be7  mov     rcx, [rbp+57h+var_20]
0x180004beb  xor     rcx, rsp; StackCookie
0x180004bee  call    __security_check_cookie
0x180004bf3  lea     r11, [rsp+0F0h+var_10]
0x180004bfb  mov     rbx, [r11+20h]
0x180004bff  mov     rsi, [r11+30h]
0x180004c03  mov     rsp, r11
0x180004c06  pop     r15
0x180004c08  pop     r14
0x180004c0a  pop     rbp
0x180004c0b  retn
```
