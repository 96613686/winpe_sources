# FwComputeNewQuarantineStateHiddenIFCorrection(ulong,_FW_IF_QUARANTINE_STATE *)

- ea: `0x18002d37c`
- end: `0x18002d606`
- name: `?FwComputeNewQuarantineStateHiddenIFCorrection@@YAEKPEAU_FW_IF_QUARANTINE_STATE@@@Z`
- size: `650`
- prototype: `unsigned __int8 __fastcall(unsigned int, struct _FW_IF_QUARANTINE_STATE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002dda8`

## callees

- `0x18002d37c`
- `0x18002d60c`
- `0x18002dcc0`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d5d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d5d8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d443`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d443`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d4b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d4f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d4b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d4f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d476`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d476`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002d51c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002d51c`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Class_KeyW` at `0x18002d3fd`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Class_KeyW` at `0x18002d3fd`

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
                  WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids,
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
0x18002d37c  push    rbp
0x18002d37e  push    rbx
0x18002d37f  push    rsi
0x18002d380  push    rdi
0x18002d381  push    r14
0x18002d383  push    r15
0x18002d385  lea     rbp, [rsp-3B8h]
0x18002d38d  sub     rsp, 4B8h
0x18002d394  mov     rax, cs:__security_cookie
0x18002d39b  xor     rax, rsp
0x18002d39e  mov     [rbp+3E0h+var_40], rax
0x18002d3a5  xor     r15d, r15d
0x18002d3a8  lea     rax, [rsp+4E0h+hKey]
0x18002d3ad  mov     r14, rdx
0x18002d3b0  mov     [rsp+4E0h+ulFlags], r15d; ulFlags
0x18002d3b5  mov     esi, ecx
0x18002d3b7  mov     [rsp+4E0h+hKey], r15
0x18002d3bc  xorps   xmm0, xmm0
0x18002d3bf  mov     [rsp+4E0h+phkResult], r15
0x18002d3c4  lea     r9d, [r15+1]; Disposition
0x18002d3c8  mov     [rsp+4E0h+cchName], r15d
0x18002d3cd  xor     edx, edx; pszClassName
0x18002d3cf  mov     [rsp+4E0h+cbData], r15d
0x18002d3d4  mov     r8d, 20019h; samDesired
0x18002d3da  mov     dword ptr [rsp+4E0h+var_47C], r15d
0x18002d3df  lea     rcx, GUID_DEVCLASS_NET; ClassGuid
0x18002d3e6  mov     [rsp+4E0h+var_480], r15d
0x18002d3eb  mov     bl, r15b
0x18002d3ee  mov     [rsp+4E0h+var_4A0], r15
0x18002d3f3  movups  xmmword ptr [rsp+4E0h+pclsid.Data1], xmm0
0x18002d3f8  mov     [rsp+4E0h+phkClass], rax; phkClass
0x18002d3fd  call    cs:__imp_CM_Open_Class_KeyW
0x18002d404  nop     dword ptr [rax+rax+00h]
0x18002d409  test    eax, eax
0x18002d40b  jnz     loc_18002D5E4
0x18002d411  mov     edi, r15d
0x18002d414  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18002d419  lea     r9, [rsp+4E0h+cchName]; lpcchName
0x18002d41e  mov     [rsp+4E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002d423  lea     r8, [rbp+3E0h+Name]; lpName
0x18002d42a  mov     [rsp+4E0h+lpcchClass], r15; lpcchClass
0x18002d42f  mov     edx, edi; dwIndex
0x18002d431  mov     qword ptr [rsp+4E0h+ulFlags], r15; lpClass
0x18002d436  mov     [rsp+4E0h+phkClass], r15; lpReserved
0x18002d43b  mov     [rsp+4E0h+cchName], 104h
0x18002d443  call    cs:__imp_RegEnumKeyExW
0x18002d44a  nop     dword ptr [rax+rax+00h]
0x18002d44f  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18002d454  test    eax, eax
0x18002d456  jnz     loc_18002D5D8
0x18002d45c  lea     rax, [rsp+4E0h+phkResult]
0x18002d461  mov     r9d, 20019h; samDesired
0x18002d467  xor     r8d, r8d; ulOptions
0x18002d46a  mov     [rsp+4E0h+phkClass], rax; phkResult
0x18002d46f  lea     rdx, [rbp+3E0h+Name]; lpSubKey
0x18002d476  call    cs:__imp_RegOpenKeyExW
0x18002d47d  nop     dword ptr [rax+rax+00h]
0x18002d482  test    eax, eax
0x18002d484  jnz     loc_18002D56E
0x18002d48a  mov     rcx, [rsp+4E0h+phkResult]; hKey
0x18002d48f  lea     rax, [rsp+4E0h+cbData]
0x18002d494  mov     qword ptr [rsp+4E0h+ulFlags], rax; lpcbData
0x18002d499  lea     rdx, ValueName; "NetCfgInstanceId"
0x18002d4a0  lea     rax, [rbp+3E0h+Data]
0x18002d4a4  mov     [rsp+4E0h+cbData], 104h
0x18002d4ac  xor     r9d, r9d; lpType
0x18002d4af  mov     [rsp+4E0h+phkClass], rax; lpData
0x18002d4b4  xor     r8d, r8d; lpReserved
0x18002d4b7  call    cs:__imp_RegQueryValueExW
0x18002d4be  nop     dword ptr [rax+rax+00h]
0x18002d4c3  test    eax, eax
0x18002d4c5  jnz     loc_18002D55D
0x18002d4cb  mov     rcx, [rsp+4E0h+phkResult]; hKey
0x18002d4d0  lea     rax, [rsp+4E0h+var_480]
0x18002d4d5  mov     qword ptr [rsp+4E0h+ulFlags], rax; lpcbData
0x18002d4da  lea     rdx, aCharacteristic; "Characteristics"
0x18002d4e1  lea     rax, [rsp+4E0h+var_47C]
0x18002d4e6  mov     [rsp+4E0h+var_480], 4
0x18002d4ee  xor     r9d, r9d; lpType
0x18002d4f1  mov     [rsp+4E0h+phkClass], rax; lpData
0x18002d4f6  xor     r8d, r8d; lpReserved
0x18002d4f9  call    cs:__imp_RegQueryValueExW
0x18002d500  nop     dword ptr [rax+rax+00h]
0x18002d505  test    eax, eax
0x18002d507  jnz     short loc_18002D55D
0x18002d509  test    [rsp+4E0h+var_47C], 8
0x18002d50e  mov     bl, r15b
0x18002d511  jnz     short loc_18002D575
0x18002d513  lea     rdx, [rsp+4E0h+pclsid]; pclsid
0x18002d518  lea     rcx, [rbp+3E0h+Data]; lpsz
0x18002d51c  call    cs:__imp_CLSIDFromString
0x18002d523  nop     dword ptr [rax+rax+00h]
0x18002d528  test    eax, eax
0x18002d52a  js      short loc_18002D55D
0x18002d52c  lea     rdx, [rsp+4E0h+var_4A0]; unsigned __int64 *
0x18002d531  lea     rcx, [rsp+4E0h+pclsid]; struct _GUID *
0x18002d536  call    FwDynDataGetInterfaceIndex
0x18002d53b  mov     ecx, r15d
0x18002d53e  test    esi, esi
0x18002d540  jz      short loc_18002D55D
0x18002d542  mov     eax, ecx
0x18002d544  lea     rax, [rax+rax*2]
0x18002d548  shl     rax, 5
0x18002d54c  mov     rax, [rax+r14]
0x18002d550  cmp     rax, [rsp+4E0h+var_4A0]
0x18002d555  jz      short loc_18002D592
0x18002d557  inc     ecx
0x18002d559  cmp     ecx, esi
0x18002d55b  jb      short loc_18002D542
0x18002d55d  mov     rcx, [rsp+4E0h+phkResult]; hKey
0x18002d562  call    cs:__imp_RegCloseKey
0x18002d569  nop     dword ptr [rax+rax+00h]
0x18002d56e  inc     edi
0x18002d570  jmp     loc_18002D414
0x18002d575  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d57c  lea     rax, WPP_GLOBAL_Control
0x18002d583  cmp     rcx, rax
0x18002d586  jz      short loc_18002D58E
0x18002d588  test    byte ptr [rcx+1Ch], 4
0x18002d58c  jnz     short loc_18002D5BD
0x18002d58e  mov     bl, 1
0x18002d590  jmp     short loc_18002D513
0x18002d592  mov     eax, ecx
0x18002d594  lea     rax, [rax+rax*2]
0x18002d598  shl     rax, 5
0x18002d59c  add     rax, r14
0x18002d59f  jz      short loc_18002D55D
0x18002d5a1  cmp     bl, 1
0x18002d5a4  jnz     short loc_18002D55D
0x18002d5a6  cmp     [rax+8], r15d
0x18002d5aa  jnz     short loc_18002D55D
0x18002d5ac  mov     dword ptr [rax+8], 1
0x18002d5b3  mov     [rax+10h], r15d
0x18002d5b7  mov     [rax+38h], r15d
0x18002d5bb  jmp     short loc_18002D55D
0x18002d5bd  mov     rcx, [rcx+10h]
0x18002d5c1  lea     r9, [rbp+3E0h+Data]
0x18002d5c5  mov     edx, 0B1h
0x18002d5ca  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x18002d5d1  call    WPP_SF_S
0x18002d5d6  jmp     short loc_18002D58E
0x18002d5d8  call    cs:__imp_RegCloseKey
0x18002d5df  nop     dword ptr [rax+rax+00h]
0x18002d5e4  mov     al, bl
0x18002d5e6  mov     rcx, [rbp+3E0h+var_40]
0x18002d5ed  xor     rcx, rsp; StackCookie
0x18002d5f0  call    __security_check_cookie
0x18002d5f5  add     rsp, 4B8h
0x18002d5fc  pop     r15
0x18002d5fe  pop     r14
0x18002d600  pop     rdi
0x18002d601  pop     rsi
0x18002d602  pop     rbx
0x18002d603  pop     rbp
0x18002d604  retn
```
