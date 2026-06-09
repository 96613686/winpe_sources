# GetLocalDTCProfileIntExW(ushort const *,ushort const *,ulong)

- ea: `0x1800849ac`
- end: `0x180084af1`
- name: `?GetLocalDTCProfileIntExW@@YAKPEBG0K@Z`
- size: `325`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800490e0`
- `0x18009e404`

## callees

- `0x1800849ac`
- `0x180084bf4`
- `0x1800b83ee`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084a94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084a94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084a66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084a66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084ab7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084ac7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084ab7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084ac7`

## pseudocode

```c
__int64 __fastcall GetLocalDTCProfileIntExW(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HKEY v3; // rdx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v10; // [rsp+50h] [rbp-B0h]
  wchar_t v11; // [rsp+54h] [rbp-ACh]
  _BYTE v12[510]; // [rsp+56h] [rbp-AAh] BYREF
  __int16 v13; // [rsp+254h] [rbp+154h]

  v10 = *(_DWORD *)L"\\\\";
  v11 = asc_180135F20[2];
  hKey = 0;
  phkResult = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  memset_0(v12, 0, 0x200u);
  v13 = 0;
  if ( (unsigned int)RegConnectHostnameW(0, v3, &hKey) )
    return 0;
  if ( RegOpenKeyExW(hKey, L"Software\\Microsoft\\MSDTC", 0, 0x20119u, &phkResult)
    || RegQueryValueExW(phkResult, a2, 0, &Type, Data, &cbData)
    || Type != 4 )
  {
    *(_DWORD *)Data = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x1800849ac  mov     [rsp-8+arg_0], rbx
0x1800849b1  push    rbp
0x1800849b2  lea     rbp, [rsp-170h]
0x1800849ba  sub     rsp, 270h
0x1800849c1  mov     rax, cs:__security_cookie
0x1800849c8  xor     rax, rsp
0x1800849cb  mov     [rbp+170h+var_10], rax
0x1800849d2  mov     eax, dword ptr cs:asc_180135F20; "\\\\"
0x1800849d8  lea     rcx, [rsp+270h+var_21A]; void *
0x1800849dd  mov     [rsp+270h+var_220], eax
0x1800849e1  mov     rbx, rdx
0x1800849e4  movzx   eax, word ptr cs:asc_180135F20+4; ""
0x1800849eb  xor     edx, edx; Val
0x1800849ed  mov     r8d, 200h; Size
0x1800849f3  mov     [rsp+270h+var_21C], ax
0x1800849f8  mov     [rsp+270h+hKey], 0
0x180084a01  mov     [rsp+270h+var_230], 0
0x180084a0a  mov     [rsp+270h+Type], 0
0x180084a12  mov     dword ptr [rsp+270h+Data], 0
0x180084a1a  mov     [rsp+270h+cbData], 4
0x180084a22  call    memset_0
0x180084a27  xor     eax, eax
0x180084a29  lea     r8, [rsp+270h+hKey]; HKEY *
0x180084a2e  xor     ecx, ecx; unsigned __int16 *
0x180084a30  mov     [rbp+170h+var_1C], ax
0x180084a37  call    ?RegConnectHostnameW@@YAJPEBGPEAUHKEY__@@PEAPEAU1@@Z; RegConnectHostnameW(ushort const *,HKEY__ *,HKEY__ * *)
0x180084a3c  test    eax, eax
0x180084a3e  jz      short loc_180084A47
0x180084a40  xor     eax, eax
0x180084a42  jmp     loc_180084AD1
0x180084a47  mov     rcx, [rsp+270h+hKey]; hKey
0x180084a4c  lea     rax, [rsp+270h+var_230]
0x180084a51  mov     r9d, 20119h; samDesired
0x180084a57  mov     [rsp+270h+phkResult], rax; phkResult
0x180084a5c  xor     r8d, r8d; ulOptions
0x180084a5f  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\MSDTC"
0x180084a66  call    cs:__imp_RegOpenKeyExW
0x180084a6c  test    eax, eax
0x180084a6e  jnz     short loc_180084AA5
0x180084a70  mov     rcx, [rsp+270h+var_230]; hKey
0x180084a75  lea     rax, [rsp+270h+cbData]
0x180084a7a  mov     [rsp+270h+lpcbData], rax; lpcbData
0x180084a7f  lea     r9, [rsp+270h+Type]; lpType
0x180084a84  lea     rax, [rsp+270h+Data]
0x180084a89  xor     r8d, r8d; lpReserved
0x180084a8c  mov     rdx, rbx; lpValueName
0x180084a8f  mov     [rsp+270h+phkResult], rax; lpData
0x180084a94  call    cs:__imp_RegQueryValueExW
0x180084a9a  test    eax, eax
0x180084a9c  jnz     short loc_180084AA5
0x180084a9e  cmp     [rsp+270h+Type], 4
0x180084aa3  jz      short loc_180084AAD
0x180084aa5  mov     dword ptr [rsp+270h+Data], 0
0x180084aad  mov     rcx, [rsp+270h+var_230]; hKey
0x180084ab2  test    rcx, rcx
0x180084ab5  jz      short loc_180084ABD
0x180084ab7  call    cs:__imp_RegCloseKey
0x180084abd  mov     rcx, [rsp+270h+hKey]; hKey
0x180084ac2  test    rcx, rcx
0x180084ac5  jz      short loc_180084ACD
0x180084ac7  call    cs:__imp_RegCloseKey
0x180084acd  mov     eax, dword ptr [rsp+270h+Data]
0x180084ad1  mov     rcx, [rbp+170h+var_10]
0x180084ad8  xor     rcx, rsp; StackCookie
0x180084adb  call    __security_check_cookie
0x180084ae0  mov     rbx, [rsp+270h+arg_0]
0x180084ae8  add     rsp, 270h
0x180084aef  pop     rbp
0x180084af0  retn
```
