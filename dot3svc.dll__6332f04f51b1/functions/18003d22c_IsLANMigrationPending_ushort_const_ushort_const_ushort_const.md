# IsLANMigrationPending(ushort const *,ushort const *,ushort const *)

- ea: `0x18003d22c`
- end: `0x18003d37b`
- name: `?IsLANMigrationPending@@YA_NPEBG00@Z`
- size: `335`
- prototype: `unsigned __int8 __fastcall(unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035348`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18003d22c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d2b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d2dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d2b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d2dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d315`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d315`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d32f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d33e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d32f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d33e`

## pseudocode

```c
unsigned __int8 __fastcall IsLANMigrationPending(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int8 v3; // bl
  LSTATUS v4; // edi
  HKEY hKey; // [rsp+60h] [rbp+28h] BYREF
  const unsigned __int16 *Data; // [rsp+68h] [rbp+30h] BYREF
  const unsigned __int16 *cbData; // [rsp+70h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+40h] BYREF

  cbData = a3;
  Data = a2;
  hKey = (HKEY)a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 12, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids);
  }
  phkResult = 0;
  hKey = 0;
  LODWORD(cbData) = 0;
  LODWORD(Data) = 0;
  v3 = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Wlansvc\\MigrationData\\Upgrade",
         0,
         0x20019u,
         &phkResult);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\dot3svc\\MigrationData", 0, 0x20019u, &hKey) || !v4 )
  {
    LODWORD(cbData) = 4;
    if ( RegQueryValueExW(hKey, L"dot3svcMigrationDone", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData) || !(_DWORD)Data )
      v3 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 13, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18003d22c  mov     [rsp-20h+cbData], r8
0x18003d231  mov     [rsp-20h+Data], rdx
0x18003d236  mov     [rsp-20h+hKey], rcx
0x18003d23b  push    rbp
0x18003d23c  push    rbx
0x18003d23d  push    rdi
0x18003d23e  push    r12
0x18003d240  mov     rbp, rsp
0x18003d243  sub     rsp, 38h
0x18003d247  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d24e  lea     r12, WPP_GLOBAL_Control
0x18003d255  cmp     rcx, r12
0x18003d258  jz      short loc_18003D275
0x18003d25a  test    byte ptr [rcx+1Ch], 10h
0x18003d25e  jz      short loc_18003D275
0x18003d260  mov     rcx, [rcx+10h]
0x18003d264  lea     r8, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids
0x18003d26b  mov     edx, 0Ch
0x18003d270  call    WPP_SF_
0x18003d275  lea     rax, [rbp+arg_18]
0x18003d279  mov     [rbp+arg_18], 0
0x18003d281  mov     r9d, 20019h; samDesired
0x18003d287  mov     [rsp+38h+phkResult], rax; phkResult
0x18003d28c  xor     r8d, r8d; ulOptions
0x18003d28f  mov     [rbp+hKey], 0
0x18003d297  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Wlansvc\\Migration"...
0x18003d29e  mov     dword ptr [rbp+cbData], 0
0x18003d2a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d2ac  mov     dword ptr [rbp+Data], 0
0x18003d2b3  xor     bl, bl
0x18003d2b5  call    cs:__imp_RegOpenKeyExW
0x18003d2bb  mov     r9d, 20019h; samDesired
0x18003d2c1  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\dot3svc\\Migration"...
0x18003d2c8  mov     edi, eax
0x18003d2ca  xor     r8d, r8d; ulOptions
0x18003d2cd  lea     rax, [rbp+hKey]
0x18003d2d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d2d8  mov     [rsp+38h+phkResult], rax; phkResult
0x18003d2dd  call    cs:__imp_RegOpenKeyExW
0x18003d2e3  test    eax, eax
0x18003d2e5  jz      short loc_18003D2EB
0x18003d2e7  test    edi, edi
0x18003d2e9  jnz     short loc_18003D326
0x18003d2eb  mov     rcx, [rbp+hKey]; hKey
0x18003d2ef  lea     rax, [rbp+cbData]
0x18003d2f3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003d2f8  lea     rdx, aDot3svcmigrati; "dot3svcMigrationDone"
0x18003d2ff  lea     rax, [rbp+Data]
0x18003d303  mov     dword ptr [rbp+cbData], 4
0x18003d30a  xor     r9d, r9d; lpType
0x18003d30d  mov     [rsp+38h+phkResult], rax; lpData
0x18003d312  xor     r8d, r8d; lpReserved
0x18003d315  call    cs:__imp_RegQueryValueExW
0x18003d31b  test    eax, eax
0x18003d31d  jnz     short loc_18003D324
0x18003d31f  cmp     dword ptr [rbp+Data], eax
0x18003d322  jnz     short loc_18003D326
0x18003d324  mov     bl, 1
0x18003d326  mov     rcx, [rbp+hKey]; hKey
0x18003d32a  test    rcx, rcx
0x18003d32d  jz      short loc_18003D335
0x18003d32f  call    cs:__imp_RegCloseKey
0x18003d335  mov     rcx, [rbp+arg_18]; hKey
0x18003d339  test    rcx, rcx
0x18003d33c  jz      short loc_18003D344
0x18003d33e  call    cs:__imp_RegCloseKey
0x18003d344  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d34b  cmp     rcx, r12
0x18003d34e  jz      short loc_18003D36F
0x18003d350  test    byte ptr [rcx+1Ch], 10h
0x18003d354  jz      short loc_18003D36F
0x18003d356  mov     rcx, [rcx+10h]
0x18003d35a  lea     r8, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids
0x18003d361  movzx   r9d, bl
0x18003d365  mov     edx, 0Dh
0x18003d36a  call    WPP_SF_d
0x18003d36f  mov     al, bl
0x18003d371  add     rsp, 38h
0x18003d375  pop     r12
0x18003d377  pop     rdi
0x18003d378  pop     rbx
0x18003d379  pop     rbp
0x18003d37a  retn
```
