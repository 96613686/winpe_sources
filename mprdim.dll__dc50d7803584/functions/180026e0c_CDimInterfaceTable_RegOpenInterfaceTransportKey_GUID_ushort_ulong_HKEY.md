# CDimInterfaceTable::RegOpenInterfaceTransportKey(_GUID,ushort *,ulong,HKEY__ * &)

- ea: `0x180026e0c`
- end: `0x1800272fb`
- name: `?RegOpenInterfaceTransportKey@CDimInterfaceTable@@AEAAKU_GUID@@PEAGKAEAPEAUHKEY__@@@Z`
- size: `1263`
- prototype: `unsigned int __usercall@<eax>(CDimInterfaceTable *__hidden this@<rcx>, struct _GUID *@<rdx>, wchar_t *String1@<r8>, unsigned int@<r9d>, HKEY *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006cf8`
- `0x18000886c`

## callees

- `0x1800014d0`
- `0x180002130`
- `0x18000df70`
- `0x180026e0c`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180026fb8`
- `msvcrt!_wcsicmp` at `0x180027166`
- `msvcrt!_wcsicmp` at `0x180026fb8`
- `msvcrt!_wcsicmp` at `0x180027166`
- `ADVAPI32!RegOpenKeyExW` at `0x18002718e`
- `ADVAPI32!RegOpenKeyExW` at `0x18002718e`
- `ADVAPI32!RegCloseKey` at `0x180026fc7`
- `ADVAPI32!RegCloseKey` at `0x180027207`
- `ADVAPI32!RegCloseKey` at `0x180027281`
- `ADVAPI32!RegCloseKey` at `0x1800272ac`
- `ADVAPI32!RegCloseKey` at `0x1800272bc`
- `ADVAPI32!RegCloseKey` at `0x1800272ce`
- `ADVAPI32!RegCloseKey` at `0x180026fc7`
- `ADVAPI32!RegCloseKey` at `0x180027207`
- `ADVAPI32!RegCloseKey` at `0x180027281`
- `ADVAPI32!RegCloseKey` at `0x1800272ac`
- `ADVAPI32!RegCloseKey` at `0x1800272bc`
- `ADVAPI32!RegCloseKey` at `0x1800272ce`
- `ADVAPI32!RegQueryValueExW` at `0x1800271e4`
- `ADVAPI32!RegQueryValueExW` at `0x1800271e4`
- `ADVAPI32!RegEnumKeyExW` at `0x1800270dc`
- `ADVAPI32!RegEnumKeyExW` at `0x1800270dc`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180027044`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180027044`

## string_xrefs

- `0x1800271d8`: `ProtocolId`
- `0x180026eb7`: `RegOpenInterfaceTransportKey: RegOpenInterfacesKey failed with error %d`
- `0x180026f54`: `RegOpenInterfaceTransportKey: RegOpenInterfaceKey failed with error %d`
- `0x18002705f`: `RegOpenInterfaceTransportKey: GetSubKeys failed with error %d`
- `0x1800270f7`: `RegOpenInterfaceTransportKey: RegEnumKeyEx failed with error %d`
- `0x1800271a7`: `RegOpenInterfaceTransportKey: RegOpenKeyEx failed with error %d`
- `0x180027226`: `RegOpenInterfaceTransportKey: RegQueryValueEx failed with error %d`

## pseudocode

```c
__int64 __fastcall CDimInterfaceTable::RegOpenInterfaceTransportKey(
        CDimInterfaceTable *this,
        struct _GUID *a2,
        wchar_t *String1,
        int a4,
        HKEY *phkResult)
{
  unsigned int v8; // eax
  CDimInterfaceTable *v9; // rcx
  unsigned int v10; // ebx
  __int128 *v11; // r9
  unsigned int i; // ebx
  unsigned int v13; // eax
  __int128 *v14; // r9
  DWORD v15; // r13d
  __int128 *v16; // r9
  unsigned int v17; // eax
  __int128 *v18; // r9
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v21; // [rsp+68h] [rbp-98h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[4]; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+7Ch] [rbp-84h] BYREF
  int v27; // [rsp+80h] [rbp-80h]
  HKEY v28; // [rsp+88h] [rbp-78h] BYREF
  __int128 v29; // [rsp+90h] [rbp-70h] BYREF
  int v30; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v31; // [rsp+A4h] [rbp-5Ch]
  __int128 v32; // [rsp+B4h] [rbp-4Ch]
  int v33; // [rsp+C4h] [rbp-3Ch]
  int v34; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v35[2044]; // [rsp+D4h] [rbp-2Ch] BYREF
  WCHAR Name[264]; // [rsp+8D0h] [rbp+7D0h] BYREF
  wchar_t String2[264]; // [rsp+AE0h] [rbp+9E0h] BYREF

  v27 = a4;
  v28 = 0;
  hKey = 0;
  v34 = 0;
  v21 = 0;
  memset_0(v35, 0, sizeof(v35));
  v30 = 0;
  v33 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v8 = CDimInterfaceTable::RegOpenInterfacesKey(this, a2, &v28, &v21);
  v10 = v8;
  if ( v8 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_51;
    LOWORD(v34) = 0;
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v34, L"RegOpenInterfaceTransportKey: RegOpenInterfacesKey failed with error %d", v8);
LABEL_4:
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      v11 = &v29;
      if ( a2 )
        LODWORD(v11) = (_DWORD)a2;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceError,
        (unsigned int)&v34,
        (_DWORD)v11,
        0,
        (__int64)&v30);
    }
    goto LABEL_51;
  }
  for ( i = 0; i < v21; ++i )
  {
    v13 = CDimInterfaceTable::RegOpenInterfaceKey(v9, v28, i, &hKey, String2);
    if ( v13 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v34) = 0;
        LOWORD(v30) = 0;
        FormatRRASErrorString(&v34, L"RegOpenInterfaceTransportKey: RegOpenInterfaceKey failed with error %d", v13);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v14 = &v29;
          if ( a2 )
            LODWORD(v14) = (_DWORD)a2;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v34,
            (_DWORD)v14,
            0,
            (__int64)&v30);
        }
      }
    }
    else
    {
      if ( !_wcsicmp(String1, String2) )
        break;
      RegCloseKey(hKey);
      hKey = 0;
    }
  }
  if ( !hKey )
    goto LABEL_50;
  cSubKeys = 0;
  v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v10 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_51;
    LOWORD(v34) = 0;
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v34, L"RegOpenInterfaceTransportKey: GetSubKeys failed with error %d", v10);
    goto LABEL_4;
  }
  Type = 0;
  v15 = 0;
  *(_DWORD *)Data = 0;
  while ( v15 < cSubKeys )
  {
    cchName = 257;
    cbData = 4;
    v10 = RegEnumKeyExW(hKey, v15, Name, &cchName, 0, 0, 0, 0);
    if ( v10 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_47;
      LOWORD(v34) = 0;
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v34, L"RegOpenInterfaceTransportKey: RegEnumKeyEx failed with error %d", v10);
LABEL_28:
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v16 = &v29;
        if ( a2 )
          LODWORD(v16) = (_DWORD)a2;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)&v34,
          (_DWORD)v16,
          0,
          (__int64)&v30);
      }
      goto LABEL_47;
    }
    if ( !_wcsicmp(Name, L"IKEv2CustomPolicy") )
      goto LABEL_48;
    v17 = RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, phkResult);
    if ( v17 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_47;
      LOWORD(v34) = 0;
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v34, L"RegOpenInterfaceTransportKey: RegOpenKeyEx failed with error %d", v17);
      goto LABEL_28;
    }
    v10 = RegQueryValueExW(*phkResult, L"ProtocolId", 0, &Type, Data, &cbData);
    if ( v10 )
      goto LABEL_41;
    if ( Type != 4 )
    {
      v10 = 1015;
LABEL_41:
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v34) = 0;
        LOWORD(v30) = 0;
        FormatRRASErrorString(&v34, L"RegOpenInterfaceTransportKey: RegQueryValueEx failed with error %d", v10);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v18 = &v29;
          if ( a2 )
            LODWORD(v18) = (_DWORD)a2;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v34,
            (_DWORD)v18,
            0,
            (__int64)&v30);
        }
      }
      RegCloseKey(*phkResult);
      *phkResult = 0;
LABEL_47:
      v10 = 0;
      goto LABEL_48;
    }
    if ( v27 == *(_DWORD *)Data )
      break;
    RegCloseKey(*phkResult);
    *phkResult = 0;
LABEL_48:
    ++v15;
  }
  if ( !*phkResult )
LABEL_50:
    v10 = 905;
LABEL_51:
  if ( v28 )
    RegCloseKey(v28);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 && *phkResult )
  {
    RegCloseKey(*phkResult);
    *phkResult = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x180026e0c  push    rbp
0x180026e0e  push    rbx
0x180026e0f  push    rsi
0x180026e10  push    r13
0x180026e12  push    r14
0x180026e14  lea     rbp, [rsp-0C00h]
0x180026e1c  sub     rsp, 0D00h
0x180026e23  mov     rax, cs:__security_cookie
0x180026e2a  xor     rax, rsp
0x180026e2d  mov     [rbp+0C20h+var_30], rax
0x180026e34  mov     r14, [rbp+0C20h+phkResult]
0x180026e3b  mov     r13, r8
0x180026e3e  mov     rsi, rdx
0x180026e41  mov     [rbp+0C20h+var_CA0], r9d
0x180026e45  mov     rbx, rcx
0x180026e48  mov     [rbp+0C20h+var_C98], 0
0x180026e50  xor     eax, eax
0x180026e52  mov     [rsp+0D20h+hKey], 0
0x180026e5b  xor     edx, edx; Val
0x180026e5d  mov     [rbp+0C20h+var_C50], eax
0x180026e60  mov     r8d, 7FCh; Size
0x180026e66  mov     [rsp+0D20h+var_CB8], 0
0x180026e6e  lea     rcx, [rbp+0C20h+var_C4C]; void *
0x180026e72  call    memset_0
0x180026e77  xorps   xmm0, xmm0
0x180026e7a  lea     r9, [rsp+0D20h+var_CB8]; unsigned int *
0x180026e7f  xor     eax, eax
0x180026e81  lea     r8, [rbp+0C20h+var_C98]; HKEY *
0x180026e85  mov     rdx, rsi; struct _GUID *
0x180026e88  mov     [rbp+0C20h+var_C80], eax
0x180026e8b  mov     rcx, rbx; this
0x180026e8e  mov     [rbp+0C20h+var_C5C], eax
0x180026e91  movups  [rbp+0C20h+var_C7C], xmm0
0x180026e95  movups  [rbp+0C20h+var_C6C], xmm0
0x180026e99  movups  [rbp+0C20h+var_C90], xmm0
0x180026e9d  call    ?RegOpenInterfacesKey@CDimInterfaceTable@@AEAAKPEAU_GUID@@AEAPEAUHKEY__@@AEAK@Z; CDimInterfaceTable::RegOpenInterfacesKey(_GUID *,HKEY__ * &,ulong &)
0x180026ea2  mov     ebx, eax
0x180026ea4  test    eax, eax
0x180026ea6  jz      short loc_180026F18
0x180026ea8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180026eaf  jz      loc_1800272A3
0x180026eb5  xor     ecx, ecx
0x180026eb7  lea     rdx, aRegopeninterfa_2; "RegOpenInterfaceTransportKey: RegOpenIn"...
0x180026ebe  mov     word ptr [rbp+0C20h+var_C50], cx
0x180026ec2  mov     r8d, eax
0x180026ec5  mov     word ptr [rbp+0C20h+var_C80], cx
0x180026ec9  lea     rcx, [rbp+0C20h+var_C50]
0x180026ecd  call    FormatRRASErrorString
0x180026ed2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180026ed9  jz      loc_1800272A3
0x180026edf  test    rsi, rsi
0x180026ee2  lea     rax, [rbp+0C20h+var_C80]
0x180026ee6  mov     [rsp+0D20h+lpcbMaxSubKeyLen], rax
0x180026eeb  lea     r9, [rbp+0C20h+var_C90]
0x180026eef  cmovnz  r9, rsi
0x180026ef3  mov     [rsp+0D20h+lpcSubKeys], 0
0x180026efc  lea     r8, [rbp+0C20h+var_C50]
0x180026f00  lea     rdx, RasDimParamTraceError
0x180026f07  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026f0e  call    McTemplateU0zjzz_EventWriteTransfer
0x180026f13  jmp     loc_1800272A3
0x180026f18  xor     ebx, ebx
0x180026f1a  cmp     ebx, [rsp+0D20h+var_CB8]
0x180026f1e  jnb     loc_180026FDD
0x180026f24  mov     rdx, [rbp+0C20h+var_C98]; HKEY
0x180026f28  lea     rax, [rbp+0C20h+String2]
0x180026f2f  lea     r9, [rsp+0D20h+hKey]; HKEY *
0x180026f34  mov     [rsp+0D20h+lpcSubKeys], rax; unsigned __int16 *
0x180026f39  mov     r8d, ebx; unsigned int
0x180026f3c  call    ?RegOpenInterfaceKey@CDimInterfaceTable@@AEAAKPEAUHKEY__@@KAEAPEAU2@PEAG@Z; CDimInterfaceTable::RegOpenInterfaceKey(HKEY__ *,ulong,HKEY__ * &,ushort *)
0x180026f41  test    eax, eax
0x180026f43  jz      short loc_180026FAE
0x180026f45  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180026f4c  jz      loc_180026FD6
0x180026f52  xor     ecx, ecx
0x180026f54  lea     rdx, aRegopeninterfa_4; "RegOpenInterfaceTransportKey: RegOpenIn"...
0x180026f5b  mov     word ptr [rbp+0C20h+var_C50], cx
0x180026f5f  mov     r8d, eax
0x180026f62  mov     word ptr [rbp+0C20h+var_C80], cx
0x180026f66  lea     rcx, [rbp+0C20h+var_C50]
0x180026f6a  call    FormatRRASErrorString
0x180026f6f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180026f76  jz      short loc_180026FD6
0x180026f78  test    rsi, rsi
0x180026f7b  lea     rax, [rbp+0C20h+var_C80]
0x180026f7f  mov     [rsp+0D20h+lpcbMaxSubKeyLen], rax
0x180026f84  lea     r9, [rbp+0C20h+var_C90]
0x180026f88  cmovnz  r9, rsi
0x180026f8c  mov     [rsp+0D20h+lpcSubKeys], 0
0x180026f95  lea     r8, [rbp+0C20h+var_C50]
0x180026f99  lea     rdx, RasDimParamTraceError
0x180026fa0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026fa7  call    McTemplateU0zjzz_EventWriteTransfer
0x180026fac  jmp     short loc_180026FD6
0x180026fae  lea     rdx, [rbp+0C20h+String2]; String2
0x180026fb5  mov     rcx, r13; String1
0x180026fb8  call    cs:__imp__wcsicmp
0x180026fbe  test    eax, eax
0x180026fc0  jz      short loc_180026FDD
0x180026fc2  mov     rcx, [rsp+0D20h+hKey]; hKey
0x180026fc7  call    cs:__imp_RegCloseKey
0x180026fcd  mov     [rsp+0D20h+hKey], 0
0x180026fd6  inc     ebx
0x180026fd8  jmp     loc_180026F1A
0x180026fdd  mov     rcx, [rsp+0D20h+hKey]; hKey
0x180026fe2  test    rcx, rcx
0x180026fe5  jz      loc_18002729E
0x180026feb  mov     [rsp+0D20h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180026ff4  lea     rax, [rsp+0D20h+cSubKeys]
0x180026ff9  mov     [rsp+0D20h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180027002  xor     r9d, r9d; lpReserved
0x180027005  mov     [rsp+0D20h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18002700e  xor     r8d, r8d; lpcchClass
0x180027011  mov     [rsp+0D20h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18002701a  xor     edx, edx; lpClass
0x18002701c  mov     [rsp+0D20h+lpcValues], 0; lpcValues
0x180027025  mov     [rsp+0D20h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18002702e  mov     [rsp+0D20h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180027037  mov     [rsp+0D20h+lpcSubKeys], rax; lpcSubKeys
0x18002703c  mov     [rsp+0D20h+cSubKeys], 0
0x180027044  call    cs:__imp_RegQueryInfoKeyW
0x18002704a  mov     ebx, eax
0x18002704c  test    eax, eax
0x18002704e  jz      short loc_180027076
0x180027050  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180027057  jz      loc_1800272A3
0x18002705d  xor     eax, eax
0x18002705f  lea     rdx, aRegopeninterfa_1; "RegOpenInterfaceTransportKey: GetSubKey"...
0x180027066  mov     word ptr [rbp+0C20h+var_C50], ax
0x18002706a  mov     r8d, ebx
0x18002706d  mov     word ptr [rbp+0C20h+var_C80], ax
0x180027071  jmp     loc_180026EC9
0x180027076  mov     [rsp+0D20h+Type], 0
0x18002707e  xor     r13d, r13d
0x180027081  mov     dword ptr [rsp+0D20h+Data], 0
0x180027089  cmp     r13d, [rsp+0D20h+cSubKeys]
0x18002708e  jnb     loc_180027298
0x180027094  mov     rcx, [rsp+0D20h+hKey]; hKey
0x180027099  lea     r9, [rsp+0D20h+cchName]; lpcchName
0x18002709e  mov     [rsp+0D20h+lpcValues], 0; lpftLastWriteTime
0x1800270a7  lea     r8, [rbp+0C20h+Name]; lpName
0x1800270ae  mov     [rsp+0D20h+lpcbMaxClassLen], 0; lpcchClass
0x1800270b7  mov     edx, r13d; dwIndex
0x1800270ba  mov     [rsp+0D20h+lpcbMaxSubKeyLen], 0; lpClass
0x1800270c3  mov     [rsp+0D20h+lpcSubKeys], 0; lpReserved
0x1800270cc  mov     [rsp+0D20h+cchName], 101h
0x1800270d4  mov     [rsp+0D20h+cbData], 4
0x1800270dc  call    cs:__imp_RegEnumKeyExW
0x1800270e2  mov     ebx, eax
0x1800270e4  test    eax, eax
0x1800270e6  jz      short loc_180027158
0x1800270e8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x1800270ef  jz      loc_18002728E
0x1800270f5  xor     eax, eax
0x1800270f7  lea     rdx, aRegopeninterfa; "RegOpenInterfaceTransportKey: RegEnumKe"...
0x1800270fe  mov     word ptr [rbp+0C20h+var_C50], ax
0x180027102  mov     r8d, ebx
0x180027105  mov     word ptr [rbp+0C20h+var_C80], ax
0x180027109  lea     rcx, [rbp+0C20h+var_C50]
0x18002710d  call    FormatRRASErrorString
0x180027112  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180027119  jz      loc_18002728E
0x18002711f  test    rsi, rsi
0x180027122  lea     rax, [rbp+0C20h+var_C80]
0x180027126  mov     [rsp+0D20h+lpcbMaxSubKeyLen], rax
0x18002712b  lea     r9, [rbp+0C20h+var_C90]
0x18002712f  cmovnz  r9, rsi
0x180027133  mov     [rsp+0D20h+lpcSubKeys], 0
0x18002713c  lea     r8, [rbp+0C20h+var_C50]
0x180027140  lea     rdx, RasDimParamTraceError
0x180027147  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002714e  call    McTemplateU0zjzz_EventWriteTransfer
0x180027153  jmp     loc_18002728E
0x180027158  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x18002715f  lea     rcx, [rbp+0C20h+Name]; String1
0x180027166  call    cs:__imp__wcsicmp
0x18002716c  test    eax, eax
0x18002716e  jz      loc_180027290
0x180027174  mov     rcx, [rsp+0D20h+hKey]; hKey
0x180027179  lea     rdx, [rbp+0C20h+Name]; lpSubKey
0x180027180  mov     r9d, 2001Fh; samDesired
0x180027186  mov     [rsp+0D20h+lpcSubKeys], r14; phkResult
0x18002718b  xor     r8d, r8d; ulOptions
0x18002718e  call    cs:__imp_RegOpenKeyExW
0x180027194  test    eax, eax
0x180027196  jz      short loc_1800271BE
0x180027198  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002719f  jz      loc_18002728E
0x1800271a5  xor     ecx, ecx
0x1800271a7  lea     rdx, aRegopeninterfa_0; "RegOpenInterfaceTransportKey: RegOpenKe"...
0x1800271ae  mov     word ptr [rbp+0C20h+var_C50], cx
0x1800271b2  mov     r8d, eax
0x1800271b5  mov     word ptr [rbp+0C20h+var_C80], cx
0x1800271b9  jmp     loc_180027109
0x1800271be  mov     rcx, [r14]; hKey
0x1800271c1  lea     rax, [rsp+0D20h+cbData]
0x1800271c6  mov     [rsp+0D20h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800271cb  lea     r9, [rsp+0D20h+Type]; lpType
0x1800271d0  lea     rax, [rsp+0D20h+Data]
0x1800271d5  xor     r8d, r8d; lpReserved
0x1800271d8  lea     rdx, aProtocolid; "ProtocolId"
0x1800271df  mov     [rsp+0D20h+lpcSubKeys], rax; lpData
0x1800271e4  call    cs:__imp_RegQueryValueExW
0x1800271ea  mov     ebx, eax
0x1800271ec  test    eax, eax
0x1800271ee  jnz     short loc_18002721B
0x1800271f0  cmp     [rsp+0D20h+Type], 4
0x1800271f5  jnz     short loc_180027216
0x1800271f7  mov     eax, [rbp+0C20h+var_CA0]
0x1800271fa  cmp     eax, dword ptr [rsp+0D20h+Data]
0x1800271fe  jz      loc_180027298
0x180027204  mov     rcx, [r14]; hKey
0x180027207  call    cs:__imp_RegCloseKey
0x18002720d  mov     qword ptr [r14], 0
0x180027214  jmp     short loc_180027290
0x180027216  mov     ebx, 3F7h
0x18002721b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180027222  jz      short loc_18002727E
0x180027224  xor     eax, eax
0x180027226  lea     rdx, aRegopeninterfa_3; "RegOpenInterfaceTransportKey: RegQueryV"...
0x18002722d  mov     r8d, ebx
0x180027230  mov     word ptr [rbp+0C20h+var_C50], ax
0x180027234  lea     rcx, [rbp+0C20h+var_C50]
0x180027238  mov     word ptr [rbp+0C20h+var_C80], ax
0x18002723c  call    FormatRRASErrorString
0x180027241  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180027248  jz      short loc_18002727E
0x18002724a  test    rsi, rsi
0x18002724d  lea     rax, [rbp+0C20h+var_C80]
0x180027251  mov     [rsp+0D20h+lpcbMaxSubKeyLen], rax
0x180027256  lea     r9, [rbp+0C20h+var_C90]
0x18002725a  cmovnz  r9, rsi
0x18002725e  mov     [rsp+0D20h+lpcSubKeys], 0
0x180027267  lea     r8, [rbp+0C20h+var_C50]
0x18002726b  lea     rdx, RasDimParamTraceError
0x180027272  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180027279  call    McTemplateU0zjzz_EventWriteTransfer
0x18002727e  mov     rcx, [r14]; hKey
0x180027281  call    cs:__imp_RegCloseKey
0x180027287  mov     qword ptr [r14], 0
0x18002728e  xor     ebx, ebx
0x180027290  inc     r13d
0x180027293  jmp     loc_180027089
0x180027298  cmp     qword ptr [r14], 0
0x18002729c  jnz     short loc_1800272A3
0x18002729e  mov     ebx, 389h
0x1800272a3  mov     rcx, [rbp+0C20h+var_C98]; hKey
0x1800272a7  test    rcx, rcx
0x1800272aa  jz      short loc_1800272B2
0x1800272ac  call    cs:__imp_RegCloseKey
0x1800272b2  mov     rcx, [rsp+0D20h+hKey]; hKey
0x1800272b7  test    rcx, rcx
0x1800272ba  jz      short loc_1800272C2
0x1800272bc  call    cs:__imp_RegCloseKey
0x1800272c2  test    ebx, ebx
0x1800272c4  jz      short loc_1800272DB
0x1800272c6  mov     rcx, [r14]; hKey
0x1800272c9  test    rcx, rcx
0x1800272cc  jz      short loc_1800272DB
0x1800272ce  call    cs:__imp_RegCloseKey
0x1800272d4  mov     qword ptr [r14], 0
0x1800272db  mov     eax, ebx
0x1800272dd  mov     rcx, [rbp+0C20h+var_30]
0x1800272e4  xor     rcx, rsp; StackCookie
0x1800272e7  call    __security_check_cookie
0x1800272ec  add     rsp, 0D00h
0x1800272f3  pop     r14
0x1800272f5  pop     r13
0x1800272f7  pop     rsi
0x1800272f8  pop     rbx
0x1800272f9  pop     rbp
0x1800272fa  retn
```
