# CRDPENCONResolver::IsTSListenerPort(ushort,int *)

- ea: `0x140071cfc`
- end: `0x1400721d5`
- name: `?IsTSListenerPort@CRDPENCONResolver@@CAJGPEAH@Z`
- size: `1241`
- prototype: `__int64 __fastcall(unsigned __int16, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400718d0`

## callees

- `0x1400019e8`
- `0x140001b00`
- `0x14000b7d8`
- `0x14001e158`
- `0x140071cfc`
- `0x140072af8`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x140071ef2`
- `KERNEL32!LocalAlloc` at `0x140071ef2`
- `KERNEL32!LocalFree` at `0x1400721b2`
- `KERNEL32!LocalFree` at `0x1400721b2`
- `ADVAPI32!RegOpenKeyExW` at `0x140071d67`
- `ADVAPI32!RegOpenKeyExW` at `0x140071fdb`
- `ADVAPI32!RegOpenKeyExW` at `0x140071d67`
- `ADVAPI32!RegOpenKeyExW` at `0x140071fdb`
- `ADVAPI32!RegEnumKeyExW` at `0x140071f47`
- `ADVAPI32!RegEnumKeyExW` at `0x140071f47`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140071e3e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140071e3e`
- `ADVAPI32!RegCloseKey` at `0x140071fb8`
- `ADVAPI32!RegCloseKey` at `0x14007218d`
- `ADVAPI32!RegCloseKey` at `0x1400721a0`
- `ADVAPI32!RegCloseKey` at `0x140071fb8`
- `ADVAPI32!RegCloseKey` at `0x14007218d`
- `ADVAPI32!RegCloseKey` at `0x1400721a0`
- `ADVAPI32!RegQueryValueExW` at `0x14007205d`
- `ADVAPI32!RegQueryValueExW` at `0x14007205d`

## string_xrefs

- `0x140071d89`: `RegOpenKeyEx failed: 0x%x`

## pseudocode

```c
__int64 __fastcall CRDPENCONResolver::IsTSListenerPort(__int16 a1, int *a2)
{
  WCHAR *v4; // rdi
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  __int16 *v9; // rdx
  const char **v10; // rax
  unsigned __int64 v11; // rax
  DWORD v12; // ebx
  LSTATUS v13; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v15; // eax
  char v16; // si
  unsigned int v17; // eax
  int v18; // r8d
  int v19; // edx
  LSTATUS v20; // eax
  int *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-51h]
  const char **lpcbMaxValueNameLen; // [rsp+40h] [rbp-39h]
  int *lpcbMaxValueLen; // [rsp+48h] [rbp-31h]
  int v25; // [rsp+60h] [rbp-19h] BYREF
  int v26; // [rsp+64h] [rbp-15h] BYREF
  int v27; // [rsp+68h] [rbp-11h] BYREF
  const char *v28; // [rsp+70h] [rbp-9h] BYREF
  const char *v29; // [rsp+78h] [rbp-1h] BYREF
  const char *v30; // [rsp+80h] [rbp+7h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+90h] [rbp+17h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+1Fh] BYREF
  BYTE Data[52]; // [rsp+9Ch] [rbp+23h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD cSubKeys; // [rsp+F0h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+F8h] [rbp+7Fh] BYREF

  cbData = 4;
  *a2 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  phkResult = 0;
  v4 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0,
         0x20019u,
         &hKey) )
  {
    v8 = -2147467259;
    if ( (unsigned int)dword_140150118 <= 2 )
      goto LABEL_39;
    v27 = -2147467259;
    v30 = "RegOpenKeyEx failed: 0x%x";
    v28 = "IsTSListenerPort";
    lpcbMaxValueLen = &v27;
    v9 = &word_14013E506;
    v25 = 753;
    lpcbMaxValueNameLen = &v28;
    lpcbMaxSubKeyLen = &v26;
    v10 = &v30;
    v26 = -2147467259;
    goto LABEL_4;
  }
  v8 = -2147467259;
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    if ( (unsigned int)dword_140150118 <= 2 )
      goto LABEL_39;
    v26 = -2147467259;
    v28 = "RegQueryInfoKey failed: 0x%x";
    v30 = "IsTSListenerPort";
    lpcbMaxValueLen = &v26;
    v9 = (__int16 *)byte_14013E4BD;
    v25 = 766;
    lpcbMaxValueNameLen = &v30;
    lpcbMaxSubKeyLen = &v27;
    v10 = &v28;
    v27 = -2147467259;
LABEL_4:
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconresolver.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (_DWORD)v9,
      v6,
      v7,
      (__int64)v10,
      (__int64)lpcbMaxSubKeyLen,
      (__int64)&v29,
      (__int64)&v25,
      (__int64)lpcbMaxValueNameLen,
      (__int64)lpcbMaxValueLen);
    goto LABEL_39;
  }
  if ( cbMaxSubKeyLen == -1 || (v11 = 2LL * (cbMaxSubKeyLen + 1), v5 = -1, v11 > 0xFFFFFFFF) )
  {
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v30 = "IsTSListenerPort";
      v28 = "Subkey length too long";
      v26 = 777;
      v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconresolver.cpp";
      v25 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&dword_14013E594,
        v6,
        v7,
        (__int64)&v28,
        (__int64)&v25,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v30);
    }
  }
  else
  {
    v4 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)v11);
    if ( v4 )
    {
      v12 = 0;
      if ( !cSubKeys )
      {
LABEL_32:
        *a2 = 0;
        v8 = 1;
        goto LABEL_39;
      }
      while ( 1 )
      {
        cchName = cbMaxSubKeyLen + 1;
        cbData = 4;
        v13 = RegEnumKeyExW(hKey, v12, v4, &cchName, 0, 0, 0, 0);
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DLD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              &WPP_aabd390f80d63268e0df741d2a119417_Traceguids,
              CurrentThreadActivityIdPrefix,
              v13,
              v12);
          }
          goto LABEL_31;
        }
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        v15 = RegOpenKeyExW(hKey, v4, 0, 0x20019u, &phkResult);
        v16 = v15;
        if ( v15 )
          break;
        v20 = RegQueryValueExW(phkResult, L"PortNumber", 0, 0, Data, &cbData);
        v16 = v20;
        if ( v20 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
          {
            goto LABEL_31;
          }
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 32;
LABEL_24:
          WPP_SF_DDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v18, v17, v16, (__int64)v4);
          goto LABEL_31;
        }
        if ( a1 == *(_WORD *)Data )
        {
          v8 = 0;
          *a2 = 1;
          goto LABEL_39;
        }
LABEL_31:
        if ( ++v12 >= cSubKeys )
          goto LABEL_32;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_31;
      }
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 31;
      goto LABEL_24;
    }
  }
  if ( (unsigned int)dword_140150118 > 2 )
  {
    v30 = "IsTSListenerPort";
    v28 = "Failed to allocate variable pszSubKeyName";
    v26 = 780;
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconresolver.cpp";
    v25 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)&byte_14013E54F,
      v6,
      v7,
      (__int64)&v28,
      (__int64)&v25,
      (__int64)&v29,
      (__int64)&v26,
      (__int64)&v30);
  }
  v8 = -2147024882;
LABEL_39:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v4 )
    LocalFree(v4);
  return v8;
}

```

## disassembly

```asm
0x140071cfc  mov     [rsp-8+arg_0], rbx
0x140071d01  push    rbp
0x140071d02  push    rsi
0x140071d03  push    rdi
0x140071d04  push    r12
0x140071d06  push    r13
0x140071d08  push    r14
0x140071d0a  push    r15
0x140071d0c  lea     rbp, [rsp-27h]
0x140071d11  sub     rsp, 0A0h
0x140071d18  xor     r13d, r13d
0x140071d1b  mov     [rbp+57h+cbData], 4
0x140071d22  mov     [rdx], r13d
0x140071d25  lea     rax, [rbp+57h+hKey]
0x140071d29  mov     r15, rdx
0x140071d2c  mov     [rbp+57h+cSubKeys], r13d
0x140071d30  movzx   r12d, cx
0x140071d34  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x140071d38  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x140071d3f  mov     [rbp+57h+cchName], r13d
0x140071d43  mov     r9d, 20019h; samDesired
0x140071d49  mov     dword ptr [rbp+57h+Data], r13d
0x140071d4d  xor     r8d, r8d; ulOptions
0x140071d50  mov     [rbp+57h+hKey], r13
0x140071d54  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140071d5b  mov     [rbp+57h+var_48], r13
0x140071d5f  mov     edi, r13d
0x140071d62  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140071d67  call    cs:__imp_RegOpenKeyExW
0x140071d6d  test    eax, eax
0x140071d6f  jz      loc_140071E02
0x140071d75  mov     eax, cs:dword_140150118
0x140071d7b  mov     ebx, 80004005h
0x140071d80  cmp     eax, 2
0x140071d83  jbe     loc_140072184
0x140071d89  lea     rax, aRegopenkeyexFa; "RegOpenKeyEx failed: 0x%x"
0x140071d90  mov     [rbp+57h+var_68], 80004005h
0x140071d97  mov     [rbp+57h+var_50], rax
0x140071d9b  lea     rsi, aIstslistenerpo; "IsTSListenerPort"
0x140071da2  lea     rax, [rbp+57h+var_68]
0x140071da6  mov     [rbp+57h+var_60], rsi
0x140071daa  mov     [rsp+0D0h+lpcbMaxValueLen], rax
0x140071daf  lea     rdx, word_14013E506
0x140071db6  lea     rax, [rbp+57h+var_60]
0x140071dba  mov     [rbp+57h+var_70], 2F1h
0x140071dc1  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x140071dc6  lea     rax, [rbp+57h+var_70]
0x140071dca  mov     [rsp+0D0h+lpcValues], rax
0x140071dcf  lea     rax, [rbp+57h+var_58]
0x140071dd3  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x140071dd8  lea     rax, [rbp+57h+var_6C]
0x140071ddc  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140071de1  lea     rax, [rbp+57h+var_50]
0x140071de5  mov     [rbp+57h+var_6C], ebx
0x140071de8  lea     r14, aOnecoreTermsrv_11; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140071def  mov     [rsp+0D0h+phkResult], rax
0x140071df4  mov     [rbp+57h+var_58], r14
0x140071df8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140071dfd  jmp     loc_140072184
0x140071e02  mov     rcx, [rbp+57h+hKey]; hKey
0x140071e06  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x140071e0a  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x140071e0f  xor     r9d, r9d; lpReserved
0x140071e12  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140071e17  xor     r8d, r8d; lpcchClass
0x140071e1a  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x140071e1f  xor     edx, edx; lpClass
0x140071e21  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x140071e26  mov     [rsp+0D0h+lpcValues], r13; lpcValues
0x140071e2b  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x140071e30  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140071e35  lea     rax, [rbp+57h+cSubKeys]
0x140071e39  mov     [rsp+0D0h+phkResult], rax; lpcSubKeys
0x140071e3e  call    cs:__imp_RegQueryInfoKeyW
0x140071e44  mov     ebx, 80004005h
0x140071e49  test    eax, eax
0x140071e4b  jz      short loc_140071EC0
0x140071e4d  mov     eax, cs:dword_140150118
0x140071e53  cmp     eax, 2
0x140071e56  jbe     loc_140072184
0x140071e5c  lea     rax, aRegqueryinfoke_0; "RegQueryInfoKey failed: 0x%x"
0x140071e63  mov     [rbp+57h+var_6C], 80004005h
0x140071e6a  mov     [rbp+57h+var_60], rax
0x140071e6e  lea     rsi, aIstslistenerpo; "IsTSListenerPort"
0x140071e75  lea     rax, [rbp+57h+var_6C]
0x140071e79  mov     [rbp+57h+var_50], rsi
0x140071e7d  mov     [rsp+0D0h+lpcbMaxValueLen], rax
0x140071e82  lea     rdx, byte_14013E4BD
0x140071e89  lea     rax, [rbp+57h+var_50]
0x140071e8d  mov     [rbp+57h+var_70], 2FEh
0x140071e94  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x140071e99  lea     rax, [rbp+57h+var_70]
0x140071e9d  mov     [rsp+0D0h+lpcValues], rax
0x140071ea2  lea     rax, [rbp+57h+var_58]
0x140071ea6  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x140071eab  lea     rax, [rbp+57h+var_68]
0x140071eaf  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140071eb4  lea     rax, [rbp+57h+var_60]
0x140071eb8  mov     [rbp+57h+var_68], ebx
0x140071ebb  jmp     loc_140071DE8
0x140071ec0  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x140071ec3  lea     rsi, aIstslistenerpo; "IsTSListenerPort"
0x140071eca  lea     r14, aOnecoreTermsrv_11; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140071ed1  add     eax, 1
0x140071ed4  jz      loc_1400720BD
0x140071eda  add     rax, rax
0x140071edd  mov     ecx, 0FFFFFFFFh
0x140071ee2  cmp     rax, rcx
0x140071ee5  ja      loc_1400720BD
0x140071eeb  mov     edx, eax; uBytes
0x140071eed  mov     ecx, 40h ; '@'; uFlags
0x140071ef2  call    cs:__imp_LocalAlloc
0x140071ef8  mov     rdi, rax
0x140071efb  test    rax, rax
0x140071efe  jz      loc_14007211E
0x140071f04  mov     ebx, r13d
0x140071f07  mov     r14d, 1
0x140071f0d  cmp     [rbp+57h+cSubKeys], r13d
0x140071f11  jbe     loc_1400720A7
0x140071f17  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x140071f1a  lea     r9, [rbp+57h+cchName]; lpcchName
0x140071f1e  mov     rcx, [rbp+57h+hKey]; hKey
0x140071f22  inc     eax
0x140071f24  mov     [rsp+0D0h+lpcValues], r13; lpftLastWriteTime
0x140071f29  mov     r8, rdi; lpName
0x140071f2c  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcchClass
0x140071f31  mov     edx, ebx; dwIndex
0x140071f33  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpClass
0x140071f38  mov     [rbp+57h+cchName], eax
0x140071f3b  mov     [rbp+57h+cbData], 4
0x140071f42  mov     [rsp+0D0h+phkResult], r13; lpReserved
0x140071f47  call    cs:__imp_RegEnumKeyExW
0x140071f4d  mov     esi, eax
0x140071f4f  test    eax, eax
0x140071f51  jz      short loc_140071FAF
0x140071f53  mov     rcx, cs:WPP_GLOBAL_Control
0x140071f5a  lea     rax, WPP_GLOBAL_Control
0x140071f61  cmp     rcx, rax
0x140071f64  jz      loc_14007209B
0x140071f6a  test    [rcx+1Ch], r14b
0x140071f6e  jz      loc_14007209B
0x140071f74  cmp     byte ptr [rcx+19h], 3
0x140071f78  jb      loc_14007209B
0x140071f7e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140071f83  mov     rcx, cs:WPP_GLOBAL_Control
0x140071f8a  lea     r8, WPP_aabd390f80d63268e0df741d2a119417_Traceguids
0x140071f91  mov     edx, 1Eh
0x140071f96  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], ebx
0x140071f9a  mov     r9d, eax
0x140071f9d  mov     dword ptr [rsp+0D0h+phkResult], esi
0x140071fa1  mov     rcx, [rcx+10h]
0x140071fa5  call    WPP_SF_DLD
0x140071faa  jmp     loc_14007209B
0x140071faf  mov     rcx, [rbp+57h+var_48]; hKey
0x140071fb3  test    rcx, rcx
0x140071fb6  jz      short loc_140071FC2
0x140071fb8  call    cs:__imp_RegCloseKey
0x140071fbe  mov     [rbp+57h+var_48], r13
0x140071fc2  mov     rcx, [rbp+57h+hKey]; hKey
0x140071fc6  lea     rax, [rbp+57h+var_48]
0x140071fca  mov     r9d, 20019h; samDesired
0x140071fd0  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140071fd5  xor     r8d, r8d; ulOptions
0x140071fd8  mov     rdx, rdi; lpSubKey
0x140071fdb  call    cs:__imp_RegOpenKeyExW
0x140071fe1  mov     esi, eax
0x140071fe3  test    eax, eax
0x140071fe5  jz      short loc_14007203A
0x140071fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x140071fee  lea     rax, WPP_GLOBAL_Control
0x140071ff5  cmp     rcx, rax
0x140071ff8  jz      loc_14007209B
0x140071ffe  test    [rcx+1Ch], r14b
0x140072002  jz      loc_14007209B
0x140072008  cmp     byte ptr [rcx+19h], 3
0x14007200c  jb      loc_14007209B
0x140072012  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140072017  mov     edx, 1Fh
0x14007201c  mov     rcx, cs:WPP_GLOBAL_Control
0x140072023  mov     r9d, eax
0x140072026  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdi
0x14007202b  mov     dword ptr [rsp+0D0h+phkResult], esi
0x14007202f  mov     rcx, [rcx+10h]
0x140072033  call    WPP_SF_DDS
0x140072038  jmp     short loc_14007209B
0x14007203a  mov     rcx, [rbp+57h+var_48]; hKey
0x14007203e  lea     rax, [rbp+57h+cbData]
0x140072042  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x140072047  lea     rdx, ValueName; "PortNumber"
0x14007204e  lea     rax, [rbp+57h+Data]
0x140072052  xor     r9d, r9d; lpType
0x140072055  xor     r8d, r8d; lpReserved
0x140072058  mov     [rsp+0D0h+phkResult], rax; lpData
0x14007205d  call    cs:__imp_RegQueryValueExW
0x140072063  mov     esi, eax
0x140072065  test    eax, eax
0x140072067  jz      short loc_140072094
0x140072069  mov     rcx, cs:WPP_GLOBAL_Control
0x140072070  lea     rax, WPP_GLOBAL_Control
0x140072077  cmp     rcx, rax
0x14007207a  jz      short loc_14007209B
0x14007207c  test    [rcx+1Ch], r14b
0x140072080  jz      short loc_14007209B
0x140072082  cmp     byte ptr [rcx+19h], 3
0x140072086  jb      short loc_14007209B
0x140072088  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007208d  mov     edx, 20h ; ' '
0x140072092  jmp     short loc_14007201C
0x140072094  cmp     r12w, word ptr [rbp+57h+Data]
0x140072099  jz      short loc_1400720B2
0x14007209b  add     ebx, r14d
0x14007209e  cmp     ebx, [rbp+57h+cSubKeys]
0x1400720a1  jb      loc_140071F17
0x1400720a7  mov     [r15], r13d
0x1400720aa  mov     ebx, r14d
0x1400720ad  jmp     loc_140072184
0x1400720b2  mov     ebx, r13d
0x1400720b5  mov     [r15], r14d
0x1400720b8  jmp     loc_140072184
0x1400720bd  mov     eax, cs:dword_140150118
0x1400720c3  cmp     eax, 2
0x1400720c6  jbe     short loc_14007211E
0x1400720c8  lea     rax, aSubkeyLengthTo; "Subkey length too long"
0x1400720cf  mov     [rbp+57h+var_50], rsi
0x1400720d3  mov     [rbp+57h+var_60], rax
0x1400720d7  lea     rdx, dword_14013E594
0x1400720de  lea     rax, [rbp+57h+var_50]
0x1400720e2  mov     [rbp+57h+var_6C], 309h
0x1400720e9  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x1400720ee  lea     rax, [rbp+57h+var_6C]
0x1400720f2  mov     [rsp+0D0h+lpcValues], rax
0x1400720f7  lea     rax, [rbp+57h+var_58]
0x1400720fb  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x140072100  lea     rax, [rbp+57h+var_70]
0x140072104  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140072109  lea     rax, [rbp+57h+var_60]
0x14007210d  mov     [rsp+0D0h+phkResult], rax
0x140072112  mov     [rbp+57h+var_58], r14
0x140072116  mov     [rbp+57h+var_70], ebx
0x140072119  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007211e  mov     eax, cs:dword_140150118
0x140072124  cmp     eax, 2
0x140072127  jbe     short loc_14007217F
0x140072129  lea     rax, aFailedToAlloca_2; "Failed to allocate variable pszSubKeyNa"...
0x140072130  mov     [rbp+57h+var_50], rsi
0x140072134  mov     [rbp+57h+var_60], rax
0x140072138  lea     rdx, byte_14013E54F
0x14007213f  lea     rax, [rbp+57h+var_50]
0x140072143  mov     [rbp+57h+var_6C], 30Ch
0x14007214a  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x14007214f  lea     rax, [rbp+57h+var_6C]
0x140072153  mov     [rsp+0D0h+lpcValues], rax
0x140072158  lea     rax, [rbp+57h+var_58]
0x14007215c  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x140072161  lea     rax, [rbp+57h+var_70]
0x140072165  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x14007216a  lea     rax, [rbp+57h+var_60]
0x14007216e  mov     [rsp+0D0h+phkResult], rax
0x140072173  mov     [rbp+57h+var_58], r14
0x140072177  mov     [rbp+57h+var_70], ebx
0x14007217a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007217f  mov     ebx, 8007000Eh
0x140072184  mov     rcx, [rbp+57h+var_48]; hKey
0x140072188  test    rcx, rcx
0x14007218b  jz      short loc_140072197
0x14007218d  call    cs:__imp_RegCloseKey
0x140072193  mov     [rbp+57h+var_48], r13
0x140072197  mov     rcx, [rbp+57h+hKey]; hKey
0x14007219b  test    rcx, rcx
0x14007219e  jz      short loc_1400721AA
0x1400721a0  call    cs:__imp_RegCloseKey
0x1400721a6  mov     [rbp+57h+hKey], r13
0x1400721aa  test    rdi, rdi
0x1400721ad  jz      short loc_1400721B8
0x1400721af  mov     rcx, rdi; hMem
0x1400721b2  call    cs:__imp_LocalFree
0x1400721b8  mov     eax, ebx
0x1400721ba  mov     rbx, [rsp+0D0h+arg_0]
0x1400721c2  add     rsp, 0A0h
0x1400721c9  pop     r15
0x1400721cb  pop     r14
0x1400721cd  pop     r13
0x1400721cf  pop     r12
0x1400721d1  pop     rdi
0x1400721d2  pop     rsi
0x1400721d3  pop     rbp
0x1400721d4  retn
```
