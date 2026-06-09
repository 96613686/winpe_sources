# FwComputeNewQuarantineStateHiddenIFCorrection(ulong,_FW_IF_QUARANTINE_STATE *)

- ea: `0x180029b84`
- end: `0x180029ddd`
- name: `?FwComputeNewQuarantineStateHiddenIFCorrection@@YAEKPEAU_FW_IF_QUARANTINE_STATE@@@Z`
- size: `601`
- prototype: `unsigned __int8 __fastcall(unsigned int, struct _FW_IF_QUARANTINE_STATE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a810`

## callees

- `0x180029b84`
- `0x180029de4`
- `0x18002a470`
- `0x18006f520`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029db6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029db6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029cad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029ce9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029cad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029ce9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029c72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029c72`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180029c45`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180029c45`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180029d06`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180029d06`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Class_KeyW` at `0x180029c05`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Class_KeyW` at `0x180029c05`

## pseudocode

```c
char __fastcall FwComputeNewQuarantineStateHiddenIFCorrection(unsigned int a1, struct _FW_IF_QUARANTINE_STATE *a2)
{
  char v4; // bl
  DWORD i; // edi
  unsigned int v6; // ecx
  _DWORD *v7; // rax
  unsigned __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v14; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v15[4]; // [rsp+64h] [rbp-9Ch] BYREF
  GUID pclsid; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR Data[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF

  hKey = 0;
  phkResult = 0;
  cchName = 0;
  cbData = 0;
  *(_DWORD *)v15 = 0;
  v14 = 0;
  v4 = 0;
  v9 = 0;
  pclsid = 0;
  if ( !CM_Open_Class_KeyW(&GUID_DEVCLASS_NET, 0, 0x20019u, 1u, &hKey, 0) )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
        break;
      if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
      {
        cbData = 260;
        if ( !RegQueryValueExW(phkResult, L"NetCfgInstanceId", 0, 0, (LPBYTE)Data, &cbData) )
        {
          v14 = 4;
          if ( !RegQueryValueExW(phkResult, L"Characteristics", 0, 0, v15, &v14) )
          {
            v4 = 0;
            if ( (v15[0] & 8) != 0 )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
              {
                WPP_SF_S(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  177,
                  WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids,
                  Data);
              }
              v4 = 1;
            }
            if ( CLSIDFromString(Data, &pclsid) >= 0 )
            {
              FwDynDataGetInterfaceIndex(&pclsid, &v9);
              v6 = 0;
              if ( a1 )
              {
                while ( *((_QWORD *)a2 + 12 * v6) != v9 )
                {
                  if ( ++v6 >= a1 )
                    goto LABEL_12;
                }
                v7 = (_DWORD *)((char *)a2 + 96 * v6);
                if ( v7 && v4 == 1 && !v7[2] )
                {
                  v7[2] = 1;
                  v7[4] = 0;
                  v7[14] = 0;
                }
              }
            }
          }
        }
LABEL_12:
        RegCloseKey(phkResult);
      }
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x180029b84  push    rbp
0x180029b86  push    rbx
0x180029b87  push    rsi
0x180029b88  push    rdi
0x180029b89  push    r14
0x180029b8b  push    r15
0x180029b8d  lea     rbp, [rsp-3B8h]
0x180029b95  sub     rsp, 4B8h
0x180029b9c  mov     rax, cs:__security_cookie
0x180029ba3  xor     rax, rsp
0x180029ba6  mov     [rbp+3E0h+var_40], rax
0x180029bad  xor     r15d, r15d
0x180029bb0  lea     rax, [rsp+4E0h+hKey]
0x180029bb5  mov     r14, rdx
0x180029bb8  mov     [rsp+4E0h+ulFlags], r15d; ulFlags
0x180029bbd  mov     esi, ecx
0x180029bbf  mov     [rsp+4E0h+hKey], r15
0x180029bc4  xorps   xmm0, xmm0
0x180029bc7  mov     [rsp+4E0h+phkResult], r15
0x180029bcc  lea     r9d, [r15+1]; Disposition
0x180029bd0  mov     [rsp+4E0h+cchName], r15d
0x180029bd5  xor     edx, edx; pszClassName
0x180029bd7  mov     [rsp+4E0h+cbData], r15d
0x180029bdc  mov     r8d, 20019h; samDesired
0x180029be2  mov     dword ptr [rsp+4E0h+var_47C], r15d
0x180029be7  lea     rcx, GUID_DEVCLASS_NET; ClassGuid
0x180029bee  mov     [rsp+4E0h+var_480], r15d
0x180029bf3  mov     bl, r15b
0x180029bf6  mov     [rsp+4E0h+var_4A0], r15
0x180029bfb  movups  xmmword ptr [rsp+4E0h+pclsid.Data1], xmm0
0x180029c00  mov     [rsp+4E0h+phkClass], rax; phkClass
0x180029c05  call    cs:__imp_CM_Open_Class_KeyW
0x180029c0b  test    eax, eax
0x180029c0d  jnz     loc_180029DBC
0x180029c13  mov     edi, r15d
0x180029c16  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180029c1b  lea     r9, [rsp+4E0h+cchName]; lpcchName
0x180029c20  mov     [rsp+4E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180029c25  lea     r8, [rbp+3E0h+Name]; lpName
0x180029c2c  mov     [rsp+4E0h+lpcchClass], r15; lpcchClass
0x180029c31  mov     edx, edi; dwIndex
0x180029c33  mov     qword ptr [rsp+4E0h+ulFlags], r15; lpClass
0x180029c38  mov     [rsp+4E0h+phkClass], r15; lpReserved
0x180029c3d  mov     [rsp+4E0h+cchName], 104h
0x180029c45  call    cs:__imp_RegEnumKeyExW
0x180029c4b  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180029c50  test    eax, eax
0x180029c52  jnz     loc_180029DB6
0x180029c58  lea     rax, [rsp+4E0h+phkResult]
0x180029c5d  mov     r9d, 20019h; samDesired
0x180029c63  xor     r8d, r8d; ulOptions
0x180029c66  mov     [rsp+4E0h+phkClass], rax; phkResult
0x180029c6b  lea     rdx, [rbp+3E0h+Name]; lpSubKey
0x180029c72  call    cs:__imp_RegOpenKeyExW
0x180029c78  test    eax, eax
0x180029c7a  jnz     loc_180029D4C
0x180029c80  mov     rcx, [rsp+4E0h+phkResult]; hKey
0x180029c85  lea     rax, [rsp+4E0h+cbData]
0x180029c8a  mov     qword ptr [rsp+4E0h+ulFlags], rax; lpcbData
0x180029c8f  lea     rdx, ValueName; "NetCfgInstanceId"
0x180029c96  lea     rax, [rbp+3E0h+Data]
0x180029c9a  mov     [rsp+4E0h+cbData], 104h
0x180029ca2  xor     r9d, r9d; lpType
0x180029ca5  mov     [rsp+4E0h+phkClass], rax; lpData
0x180029caa  xor     r8d, r8d; lpReserved
0x180029cad  call    cs:__imp_RegQueryValueExW
0x180029cb3  test    eax, eax
0x180029cb5  jnz     loc_180029D41
0x180029cbb  mov     rcx, [rsp+4E0h+phkResult]; hKey
0x180029cc0  lea     rax, [rsp+4E0h+var_480]
0x180029cc5  mov     qword ptr [rsp+4E0h+ulFlags], rax; lpcbData
0x180029cca  lea     rdx, aCharacteristic; "Characteristics"
0x180029cd1  lea     rax, [rsp+4E0h+var_47C]
0x180029cd6  mov     [rsp+4E0h+var_480], 4
0x180029cde  xor     r9d, r9d; lpType
0x180029ce1  mov     [rsp+4E0h+phkClass], rax; lpData
0x180029ce6  xor     r8d, r8d; lpReserved
0x180029ce9  call    cs:__imp_RegQueryValueExW
0x180029cef  test    eax, eax
0x180029cf1  jnz     short loc_180029D41
0x180029cf3  test    [rsp+4E0h+var_47C], 8
0x180029cf8  mov     bl, r15b
0x180029cfb  jnz     short loc_180029D53
0x180029cfd  lea     rdx, [rsp+4E0h+pclsid]; pclsid
0x180029d02  lea     rcx, [rbp+3E0h+Data]; lpsz
0x180029d06  call    cs:__imp_CLSIDFromString
0x180029d0c  test    eax, eax
0x180029d0e  js      short loc_180029D41
0x180029d10  lea     rdx, [rsp+4E0h+var_4A0]; unsigned __int64 *
0x180029d15  lea     rcx, [rsp+4E0h+pclsid]; struct _GUID *
0x180029d1a  call    FwDynDataGetInterfaceIndex
0x180029d1f  mov     ecx, r15d
0x180029d22  test    esi, esi
0x180029d24  jz      short loc_180029D41
0x180029d26  mov     eax, ecx
0x180029d28  lea     rax, [rax+rax*2]
0x180029d2c  shl     rax, 5
0x180029d30  mov     rax, [rax+r14]
0x180029d34  cmp     rax, [rsp+4E0h+var_4A0]
0x180029d39  jz      short loc_180029D70
0x180029d3b  inc     ecx
0x180029d3d  cmp     ecx, esi
0x180029d3f  jb      short loc_180029D26
0x180029d41  mov     rcx, [rsp+4E0h+phkResult]; hKey
0x180029d46  call    cs:__imp_RegCloseKey
0x180029d4c  inc     edi
0x180029d4e  jmp     loc_180029C16
0x180029d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d5a  lea     rax, WPP_GLOBAL_Control
0x180029d61  cmp     rcx, rax
0x180029d64  jz      short loc_180029D6C
0x180029d66  test    byte ptr [rcx+1Ch], 4
0x180029d6a  jnz     short loc_180029D9B
0x180029d6c  mov     bl, 1
0x180029d6e  jmp     short loc_180029CFD
0x180029d70  mov     eax, ecx
0x180029d72  lea     rax, [rax+rax*2]
0x180029d76  shl     rax, 5
0x180029d7a  add     rax, r14
0x180029d7d  jz      short loc_180029D41
0x180029d7f  cmp     bl, 1
0x180029d82  jnz     short loc_180029D41
0x180029d84  cmp     [rax+8], r15d
0x180029d88  jnz     short loc_180029D41
0x180029d8a  mov     dword ptr [rax+8], 1
0x180029d91  mov     [rax+10h], r15d
0x180029d95  mov     [rax+38h], r15d
0x180029d99  jmp     short loc_180029D41
0x180029d9b  mov     rcx, [rcx+10h]
0x180029d9f  lea     r9, [rbp+3E0h+Data]
0x180029da3  mov     edx, 0B1h
0x180029da8  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x180029daf  call    WPP_SF_S
0x180029db4  jmp     short loc_180029D6C
0x180029db6  call    cs:__imp_RegCloseKey
0x180029dbc  mov     al, bl
0x180029dbe  mov     rcx, [rbp+3E0h+var_40]
0x180029dc5  xor     rcx, rsp; StackCookie
0x180029dc8  call    __security_check_cookie
0x180029dcd  add     rsp, 4B8h
0x180029dd4  pop     r15
0x180029dd6  pop     r14
0x180029dd8  pop     rdi
0x180029dd9  pop     rsi
0x180029dda  pop     rbx
0x180029ddb  pop     rbp
0x180029ddc  retn
```
