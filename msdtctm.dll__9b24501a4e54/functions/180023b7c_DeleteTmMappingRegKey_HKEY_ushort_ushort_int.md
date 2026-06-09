# DeleteTmMappingRegKey(HKEY__ *,ushort *,ushort *,int)

- ea: `0x180023b7c`
- end: `0x180023d21`
- name: `?DeleteTmMappingRegKey@@YAJPEAUHKEY__@@PEAG1H@Z`
- size: `421`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019c70`
- `0x18001dfb0`
- `0x180023160`

## callees

- `0x1800063b0`
- `0x18001a134`
- `0x18001ebdc`
- `0x180023b7c`
- `0x1800828a0`
- `0x1800846c0`
- `0x1800858a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023cf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023cf4`
- `CLUSAPI!ClusterRegCloseKey` at `0x180023d04`
- `CLUSAPI!ClusterRegCloseKey` at `0x180023d04`
- `CLUSAPI!ClusterRegDeleteKey` at `0x180023ca0`
- `CLUSAPI!ClusterRegDeleteKey` at `0x180023ca0`
- `CLUSAPI!ClusterRegOpenKey` at `0x180023c1a`
- `CLUSAPI!ClusterRegOpenKey` at `0x180023c1a`

## string_xrefs

- `0x180023ccb`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180023c33`: `ClusterRegOpenKey failed`
- `0x180023cdb`: `DeleteTmMappingRegKey`
- `0x180023cb9`: `ClusterRegDeleteKey failed`
- `0x180023bb0`: `DeleteTmMappingRegKey (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@3111): DeleteTmMappingRegKey: NULL != pwszMappingType`
- `0x180023bc2`: `DeleteTmMappingRegKey (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@3112): DeleteTmMappingRegKey: NULL != pwszMappingName`

## pseudocode

```c
__int64 __fastcall DeleteTmMappingRegKey(HKEY hKey, unsigned __int16 *a2, unsigned __int16 *a3, int a4)
{
  signed int StringW; // ebx
  LONG v9; // eax
  LONG v10; // eax
  HKEY phkResult; // [rsp+40h] [rbp-28h] BYREF
  LPCWSTR lpszSubKey; // [rsp+78h] [rbp+10h] BYREF

  lpszSubKey = 0;
  phkResult = 0;
  if ( !a2 )
    DtcInternalErrorW(
      L"DeleteTmMappingRegKey (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@3111): DeleteTmMappingRegKey: NULL != pwszMappingType");
  if ( !a3 )
    DtcInternalErrorW(
      L"DeleteTmMappingRegKey (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@3112): DeleteTmMappingRegKey: NULL != pwszMappingName");
  StringW = MakeStringW((unsigned __int16 **)&lpszSubKey, L"%s\\%s\\%s", L"MSDTC\\TMMapping", a2, a3);
  if ( StringW < 0 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      3117,
      L"DeleteTmMappingRegKey",
      StringW,
      L"MakeStringW failed");
    goto LABEL_22;
  }
  v9 = ClusterRegOpenKey(hKey, lpszSubKey, 0x20106u, &phkResult);
  if ( v9 )
  {
    if ( v9 > 0 )
      StringW = (unsigned __int16)v9 | 0x80070000;
    else
      StringW = v9;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      3125,
      L"DeleteTmMappingRegKey",
      StringW,
      L"ClusterRegOpenKey failed");
    goto LABEL_22;
  }
  if ( a4 )
    goto LABEL_17;
  DisplayLocMessageToConsole(0x67u);
  StringW = DisplayClusterRegKeyInfo(hKey, a2, a3);
  if ( StringW < 0 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      3136,
      L"DeleteTmMappingRegKey",
      StringW,
      L"DisplayClusterRegKeyInfo failed");
    goto LABEL_22;
  }
  DisplayLocMessageToConsole(0x6Au);
  if ( (unsigned int)GetUserResponseFromCmdLine() )
  {
LABEL_17:
    v10 = ClusterRegDeleteKey(hKey, lpszSubKey);
    if ( v10 )
    {
      if ( v10 > 0 )
        StringW = (unsigned __int16)v10 | 0x80070000;
      else
        StringW = v10;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        3153,
        L"DeleteTmMappingRegKey",
        StringW,
        L"ClusterRegDeleteKey failed");
    }
  }
  else
  {
    DisplayLocMessageToConsole(0x6Eu);
    StringW = -2147467259;
  }
LABEL_22:
  CoTaskMemFree((LPVOID)lpszSubKey);
  if ( phkResult )
    ClusterRegCloseKey(phkResult);
  return (unsigned int)StringW;
}

```

## disassembly

```asm
0x180023b7c  mov     rax, rsp
0x180023b7f  mov     [rax+8], rbx
0x180023b83  mov     [rax+18h], rbp
0x180023b87  push    rsi
0x180023b88  push    rdi
0x180023b89  push    r15
0x180023b8b  sub     rsp, 50h
0x180023b8f  mov     qword ptr [rax+10h], 0
0x180023b97  mov     r15d, r9d
0x180023b9a  mov     qword ptr [rax-28h], 0
0x180023ba2  mov     rdi, r8
0x180023ba5  mov     rsi, rdx
0x180023ba8  mov     rbp, rcx
0x180023bab  test    rdx, rdx
0x180023bae  jnz     short loc_180023BBD
0x180023bb0  lea     rcx, aDeletetmmappin; "DeleteTmMappingRegKey (com\\complus\\dt"...
0x180023bb7  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180023bbd  test    rdi, rdi
0x180023bc0  jnz     short loc_180023BCF
0x180023bc2  lea     rcx, aDeletetmmappin_1; "DeleteTmMappingRegKey (com\\complus\\dt"...
0x180023bc9  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180023bcf  mov     r9, rsi
0x180023bd2  mov     [rsp+68h+var_48], rdi
0x180023bd7  lea     r8, szSubKey; "MSDTC\\TMMapping"
0x180023bde  lea     rdx, aSSS; "%s\\%s\\%s"
0x180023be5  lea     rcx, [rsp+68h+lpszSubKey]; unsigned __int16 **
0x180023bea  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180023bef  mov     ebx, eax
0x180023bf1  test    eax, eax
0x180023bf3  jns     short loc_180023C07
0x180023bf5  lea     rax, aMakestringwFai; "MakeStringW failed"
0x180023bfc  mov     r9d, 0C2Dh
0x180023c02  jmp     loc_180023CC6
0x180023c07  mov     rdx, [rsp+68h+lpszSubKey]; lpszSubKey
0x180023c0c  lea     r9, [rsp+68h+phkResult]; phkResult
0x180023c11  mov     r8d, 20106h; samDesired
0x180023c17  mov     rcx, rbp; hKey
0x180023c1a  call    cs:__imp_ClusterRegOpenKey
0x180023c20  test    eax, eax
0x180023c22  jz      short loc_180023C45
0x180023c24  jg      short loc_180023C2A
0x180023c26  mov     ebx, eax
0x180023c28  jmp     short loc_180023C33
0x180023c2a  movzx   ebx, ax
0x180023c2d  or      ebx, 80070000h
0x180023c33  lea     rax, aClusterregopen; "ClusterRegOpenKey failed"
0x180023c3a  mov     r9d, 0C35h
0x180023c40  jmp     loc_180023CC6
0x180023c45  test    r15d, r15d
0x180023c48  jnz     short loc_180023C98
0x180023c4a  lea     ecx, [r15+67h]; uID
0x180023c4e  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x180023c53  mov     r8, rdi; unsigned __int16 *
0x180023c56  mov     rdx, rsi; unsigned __int16 *
0x180023c59  mov     rcx, rbp; hKey
0x180023c5c  call    ?DisplayClusterRegKeyInfo@@YAJPEAUHKEY__@@PEAG1@Z; DisplayClusterRegKeyInfo(HKEY__ *,ushort *,ushort *)
0x180023c61  mov     ebx, eax
0x180023c63  test    eax, eax
0x180023c65  jns     short loc_180023C76
0x180023c67  lea     rax, aDisplaycluster_0; "DisplayClusterRegKeyInfo failed"
0x180023c6e  mov     r9d, 0C40h
0x180023c74  jmp     short loc_180023CC6
0x180023c76  mov     ecx, 6Ah ; 'j'; uID
0x180023c7b  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x180023c80  call    ?GetUserResponseFromCmdLine@@YAHXZ; GetUserResponseFromCmdLine(void)
0x180023c85  test    eax, eax
0x180023c87  jnz     short loc_180023C98
0x180023c89  lea     ecx, [rax+6Eh]; uID
0x180023c8c  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x180023c91  mov     ebx, 80004005h
0x180023c96  jmp     short loc_180023CEF
0x180023c98  mov     rdx, [rsp+68h+lpszSubKey]; lpszSubKey
0x180023c9d  mov     rcx, rbp; hKey
0x180023ca0  call    cs:__imp_ClusterRegDeleteKey
0x180023ca6  test    eax, eax
0x180023ca8  jz      short loc_180023CEF
0x180023caa  jg      short loc_180023CB0
0x180023cac  mov     ebx, eax
0x180023cae  jmp     short loc_180023CB9
0x180023cb0  movzx   ebx, ax
0x180023cb3  or      ebx, 80070000h
0x180023cb9  lea     rax, aClusterregdele; "ClusterRegDeleteKey failed"
0x180023cc0  mov     r9d, 0C51h
0x180023cc6  mov     [rsp+68h+var_38], rax
0x180023ccb  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180023cd2  mov     edx, 1
0x180023cd7  mov     [rsp+68h+var_40], ebx
0x180023cdb  lea     rax, aDeletetmmappin_0; "DeleteTmMappingRegKey"
0x180023ce2  mov     [rsp+68h+var_48], rax
0x180023ce7  lea     ecx, [rdx+2]
0x180023cea  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180023cef  mov     rcx, [rsp+68h+lpszSubKey]; pv
0x180023cf4  call    cs:__imp_CoTaskMemFree
0x180023cfa  mov     rcx, [rsp+68h+phkResult]; hKey
0x180023cff  test    rcx, rcx
0x180023d02  jz      short loc_180023D0A
0x180023d04  call    cs:__imp_ClusterRegCloseKey
0x180023d0a  lea     r11, [rsp+68h+var_18]
0x180023d0f  mov     eax, ebx
0x180023d11  mov     rbx, [r11+20h]
0x180023d15  mov     rbp, [r11+30h]
0x180023d19  mov     rsp, r11
0x180023d1c  pop     r15
0x180023d1e  pop     rdi
0x180023d1f  pop     rsi
0x180023d20  retn
```
