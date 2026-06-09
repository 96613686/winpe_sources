# CRDPENCONResolver::IsTSListenerPort(ushort,int *)

- ea: `0x140073e6c`
- end: `0x140074345`
- name: `?IsTSListenerPort@CRDPENCONResolver@@CAJGPEAH@Z`
- size: `1241`
- prototype: `__int64 __fastcall(unsigned __int16, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140073a40`

## callees

- `0x1400019e8`
- `0x140001b00`
- `0x14000b7d8`
- `0x14001e158`
- `0x140073e6c`
- `0x140074c68`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x140074062`
- `KERNEL32!LocalAlloc` at `0x140074062`
- `KERNEL32!LocalFree` at `0x140074322`
- `KERNEL32!LocalFree` at `0x140074322`
- `ADVAPI32!RegOpenKeyExW` at `0x140073ed7`
- `ADVAPI32!RegOpenKeyExW` at `0x14007414b`
- `ADVAPI32!RegOpenKeyExW` at `0x140073ed7`
- `ADVAPI32!RegOpenKeyExW` at `0x14007414b`
- `ADVAPI32!RegEnumKeyExW` at `0x1400740b7`
- `ADVAPI32!RegEnumKeyExW` at `0x1400740b7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140073fae`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140073fae`
- `ADVAPI32!RegCloseKey` at `0x140074128`
- `ADVAPI32!RegCloseKey` at `0x1400742fd`
- `ADVAPI32!RegCloseKey` at `0x140074310`
- `ADVAPI32!RegCloseKey` at `0x140074128`
- `ADVAPI32!RegCloseKey` at `0x1400742fd`
- `ADVAPI32!RegCloseKey` at `0x140074310`
- `ADVAPI32!RegQueryValueExW` at `0x1400741cd`
- `ADVAPI32!RegQueryValueExW` at `0x1400741cd`

## string_xrefs

- `0x140073ef9`: `RegOpenKeyEx failed: 0x%x`

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
    if ( (unsigned int)dword_140152118 <= 2 )
      goto LABEL_39;
    v27 = -2147467259;
    v30 = "RegOpenKeyEx failed: 0x%x";
    v28 = "IsTSListenerPort";
    lpcbMaxValueLen = &v27;
    v9 = word_14014063A;
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
    if ( (unsigned int)dword_140152118 <= 2 )
      goto LABEL_39;
    v26 = -2147467259;
    v28 = "RegQueryInfoKey failed: 0x%x";
    v30 = "IsTSListenerPort";
    lpcbMaxValueLen = &v26;
    v9 = (__int16 *)qword_1401406C8;
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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v30 = "IsTSListenerPort";
      v28 = "Subkey length too long";
      v26 = 777;
      v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconresolver.cpp";
      v25 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)byte_140140683,
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
  if ( (unsigned int)dword_140152118 > 2 )
  {
    v30 = "IsTSListenerPort";
    v28 = "Failed to allocate variable pszSubKeyName";
    v26 = 780;
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenconresolver.cpp";
    v25 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)byte_1401405F5,
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
0x140073e6c  mov     [rsp-8+arg_0], rbx
0x140073e71  push    rbp
0x140073e72  push    rsi
0x140073e73  push    rdi
0x140073e74  push    r12
0x140073e76  push    r13
0x140073e78  push    r14
0x140073e7a  push    r15
0x140073e7c  lea     rbp, [rsp-27h]
0x140073e81  sub     rsp, 0A0h
0x140073e88  xor     r13d, r13d
0x140073e8b  mov     [rbp+57h+cbData], 4
0x140073e92  mov     [rdx], r13d
0x140073e95  lea     rax, [rbp+57h+hKey]
0x140073e99  mov     r15, rdx
0x140073e9c  mov     [rbp+57h+cSubKeys], r13d
0x140073ea0  movzx   r12d, cx
0x140073ea4  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x140073ea8  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x140073eaf  mov     [rbp+57h+cchName], r13d
0x140073eb3  mov     r9d, 20019h; samDesired
0x140073eb9  mov     dword ptr [rbp+57h+Data], r13d
0x140073ebd  xor     r8d, r8d; ulOptions
0x140073ec0  mov     [rbp+57h+hKey], r13
0x140073ec4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140073ecb  mov     [rbp+57h+var_48], r13
0x140073ecf  mov     edi, r13d
0x140073ed2  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140073ed7  call    cs:__imp_RegOpenKeyExW
0x140073edd  test    eax, eax
0x140073edf  jz      loc_140073F72
0x140073ee5  mov     eax, cs:dword_140152118
0x140073eeb  mov     ebx, 80004005h
0x140073ef0  cmp     eax, 2
0x140073ef3  jbe     loc_1400742F4
0x140073ef9  lea     rax, aRegopenkeyexFa; "RegOpenKeyEx failed: 0x%x"
0x140073f00  mov     [rbp+57h+var_68], 80004005h
0x140073f07  mov     [rbp+57h+var_50], rax
0x140073f0b  lea     rsi, aIstslistenerpo; "IsTSListenerPort"
0x140073f12  lea     rax, [rbp+57h+var_68]
0x140073f16  mov     [rbp+57h+var_60], rsi
0x140073f1a  mov     [rsp+0D0h+lpcbMaxValueLen], rax
0x140073f1f  lea     rdx, word_14014063A
0x140073f26  lea     rax, [rbp+57h+var_60]
0x140073f2a  mov     [rbp+57h+var_70], 2F1h
0x140073f31  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x140073f36  lea     rax, [rbp+57h+var_70]
0x140073f3a  mov     [rsp+0D0h+lpcValues], rax
0x140073f3f  lea     rax, [rbp+57h+var_58]
0x140073f43  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x140073f48  lea     rax, [rbp+57h+var_6C]
0x140073f4c  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140073f51  lea     rax, [rbp+57h+var_50]
0x140073f55  mov     [rbp+57h+var_6C], ebx
0x140073f58  lea     r14, aOnecoreTermsrv_11; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140073f5f  mov     [rsp+0D0h+phkResult], rax
0x140073f64  mov     [rbp+57h+var_58], r14
0x140073f68  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140073f6d  jmp     loc_1400742F4
0x140073f72  mov     rcx, [rbp+57h+hKey]; hKey
0x140073f76  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x140073f7a  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x140073f7f  xor     r9d, r9d; lpReserved
0x140073f82  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140073f87  xor     r8d, r8d; lpcchClass
0x140073f8a  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x140073f8f  xor     edx, edx; lpClass
0x140073f91  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x140073f96  mov     [rsp+0D0h+lpcValues], r13; lpcValues
0x140073f9b  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x140073fa0  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140073fa5  lea     rax, [rbp+57h+cSubKeys]
0x140073fa9  mov     [rsp+0D0h+phkResult], rax; lpcSubKeys
0x140073fae  call    cs:__imp_RegQueryInfoKeyW
0x140073fb4  mov     ebx, 80004005h
0x140073fb9  test    eax, eax
0x140073fbb  jz      short loc_140074030
0x140073fbd  mov     eax, cs:dword_140152118
0x140073fc3  cmp     eax, 2
0x140073fc6  jbe     loc_1400742F4
0x140073fcc  lea     rax, aRegqueryinfoke_0; "RegQueryInfoKey failed: 0x%x"
0x140073fd3  mov     [rbp+57h+var_6C], 80004005h
0x140073fda  mov     [rbp+57h+var_60], rax
0x140073fde  lea     rsi, aIstslistenerpo; "IsTSListenerPort"
0x140073fe5  lea     rax, [rbp+57h+var_6C]
0x140073fe9  mov     [rbp+57h+var_50], rsi
0x140073fed  mov     [rsp+0D0h+lpcbMaxValueLen], rax
0x140073ff2  lea     rdx, qword_1401406C8
0x140073ff9  lea     rax, [rbp+57h+var_50]
0x140073ffd  mov     [rbp+57h+var_70], 2FEh
0x140074004  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x140074009  lea     rax, [rbp+57h+var_70]
0x14007400d  mov     [rsp+0D0h+lpcValues], rax
0x140074012  lea     rax, [rbp+57h+var_58]
0x140074016  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x14007401b  lea     rax, [rbp+57h+var_68]
0x14007401f  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140074024  lea     rax, [rbp+57h+var_60]
0x140074028  mov     [rbp+57h+var_68], ebx
0x14007402b  jmp     loc_140073F58
0x140074030  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x140074033  lea     rsi, aIstslistenerpo; "IsTSListenerPort"
0x14007403a  lea     r14, aOnecoreTermsrv_11; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140074041  add     eax, 1
0x140074044  jz      loc_14007422D
0x14007404a  add     rax, rax
0x14007404d  mov     ecx, 0FFFFFFFFh
0x140074052  cmp     rax, rcx
0x140074055  ja      loc_14007422D
0x14007405b  mov     edx, eax; uBytes
0x14007405d  mov     ecx, 40h ; '@'; uFlags
0x140074062  call    cs:__imp_LocalAlloc
0x140074068  mov     rdi, rax
0x14007406b  test    rax, rax
0x14007406e  jz      loc_14007428E
0x140074074  mov     ebx, r13d
0x140074077  mov     r14d, 1
0x14007407d  cmp     [rbp+57h+cSubKeys], r13d
0x140074081  jbe     loc_140074217
0x140074087  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14007408a  lea     r9, [rbp+57h+cchName]; lpcchName
0x14007408e  mov     rcx, [rbp+57h+hKey]; hKey
0x140074092  inc     eax
0x140074094  mov     [rsp+0D0h+lpcValues], r13; lpftLastWriteTime
0x140074099  mov     r8, rdi; lpName
0x14007409c  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcchClass
0x1400740a1  mov     edx, ebx; dwIndex
0x1400740a3  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpClass
0x1400740a8  mov     [rbp+57h+cchName], eax
0x1400740ab  mov     [rbp+57h+cbData], 4
0x1400740b2  mov     [rsp+0D0h+phkResult], r13; lpReserved
0x1400740b7  call    cs:__imp_RegEnumKeyExW
0x1400740bd  mov     esi, eax
0x1400740bf  test    eax, eax
0x1400740c1  jz      short loc_14007411F
0x1400740c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400740ca  lea     rax, WPP_GLOBAL_Control
0x1400740d1  cmp     rcx, rax
0x1400740d4  jz      loc_14007420B
0x1400740da  test    [rcx+1Ch], r14b
0x1400740de  jz      loc_14007420B
0x1400740e4  cmp     byte ptr [rcx+19h], 3
0x1400740e8  jb      loc_14007420B
0x1400740ee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400740f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400740fa  lea     r8, WPP_aabd390f80d63268e0df741d2a119417_Traceguids
0x140074101  mov     edx, 1Eh
0x140074106  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], ebx
0x14007410a  mov     r9d, eax
0x14007410d  mov     dword ptr [rsp+0D0h+phkResult], esi
0x140074111  mov     rcx, [rcx+10h]
0x140074115  call    WPP_SF_DLD
0x14007411a  jmp     loc_14007420B
0x14007411f  mov     rcx, [rbp+57h+var_48]; hKey
0x140074123  test    rcx, rcx
0x140074126  jz      short loc_140074132
0x140074128  call    cs:__imp_RegCloseKey
0x14007412e  mov     [rbp+57h+var_48], r13
0x140074132  mov     rcx, [rbp+57h+hKey]; hKey
0x140074136  lea     rax, [rbp+57h+var_48]
0x14007413a  mov     r9d, 20019h; samDesired
0x140074140  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140074145  xor     r8d, r8d; ulOptions
0x140074148  mov     rdx, rdi; lpSubKey
0x14007414b  call    cs:__imp_RegOpenKeyExW
0x140074151  mov     esi, eax
0x140074153  test    eax, eax
0x140074155  jz      short loc_1400741AA
0x140074157  mov     rcx, cs:WPP_GLOBAL_Control
0x14007415e  lea     rax, WPP_GLOBAL_Control
0x140074165  cmp     rcx, rax
0x140074168  jz      loc_14007420B
0x14007416e  test    [rcx+1Ch], r14b
0x140074172  jz      loc_14007420B
0x140074178  cmp     byte ptr [rcx+19h], 3
0x14007417c  jb      loc_14007420B
0x140074182  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140074187  mov     edx, 1Fh
0x14007418c  mov     rcx, cs:WPP_GLOBAL_Control
0x140074193  mov     r9d, eax
0x140074196  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rdi
0x14007419b  mov     dword ptr [rsp+0D0h+phkResult], esi
0x14007419f  mov     rcx, [rcx+10h]
0x1400741a3  call    WPP_SF_DDS
0x1400741a8  jmp     short loc_14007420B
0x1400741aa  mov     rcx, [rbp+57h+var_48]; hKey
0x1400741ae  lea     rax, [rbp+57h+cbData]
0x1400741b2  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x1400741b7  lea     rdx, ValueName; "PortNumber"
0x1400741be  lea     rax, [rbp+57h+Data]
0x1400741c2  xor     r9d, r9d; lpType
0x1400741c5  xor     r8d, r8d; lpReserved
0x1400741c8  mov     [rsp+0D0h+phkResult], rax; lpData
0x1400741cd  call    cs:__imp_RegQueryValueExW
0x1400741d3  mov     esi, eax
0x1400741d5  test    eax, eax
0x1400741d7  jz      short loc_140074204
0x1400741d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400741e0  lea     rax, WPP_GLOBAL_Control
0x1400741e7  cmp     rcx, rax
0x1400741ea  jz      short loc_14007420B
0x1400741ec  test    [rcx+1Ch], r14b
0x1400741f0  jz      short loc_14007420B
0x1400741f2  cmp     byte ptr [rcx+19h], 3
0x1400741f6  jb      short loc_14007420B
0x1400741f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400741fd  mov     edx, 20h ; ' '
0x140074202  jmp     short loc_14007418C
0x140074204  cmp     r12w, word ptr [rbp+57h+Data]
0x140074209  jz      short loc_140074222
0x14007420b  add     ebx, r14d
0x14007420e  cmp     ebx, [rbp+57h+cSubKeys]
0x140074211  jb      loc_140074087
0x140074217  mov     [r15], r13d
0x14007421a  mov     ebx, r14d
0x14007421d  jmp     loc_1400742F4
0x140074222  mov     ebx, r13d
0x140074225  mov     [r15], r14d
0x140074228  jmp     loc_1400742F4
0x14007422d  mov     eax, cs:dword_140152118
0x140074233  cmp     eax, 2
0x140074236  jbe     short loc_14007428E
0x140074238  lea     rax, aSubkeyLengthTo; "Subkey length too long"
0x14007423f  mov     [rbp+57h+var_50], rsi
0x140074243  mov     [rbp+57h+var_60], rax
0x140074247  lea     rdx, byte_140140683
0x14007424e  lea     rax, [rbp+57h+var_50]
0x140074252  mov     [rbp+57h+var_6C], 309h
0x140074259  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x14007425e  lea     rax, [rbp+57h+var_6C]
0x140074262  mov     [rsp+0D0h+lpcValues], rax
0x140074267  lea     rax, [rbp+57h+var_58]
0x14007426b  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x140074270  lea     rax, [rbp+57h+var_70]
0x140074274  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x140074279  lea     rax, [rbp+57h+var_60]
0x14007427d  mov     [rsp+0D0h+phkResult], rax
0x140074282  mov     [rbp+57h+var_58], r14
0x140074286  mov     [rbp+57h+var_70], ebx
0x140074289  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14007428e  mov     eax, cs:dword_140152118
0x140074294  cmp     eax, 2
0x140074297  jbe     short loc_1400742EF
0x140074299  lea     rax, aFailedToAlloca_2; "Failed to allocate variable pszSubKeyNa"...
0x1400742a0  mov     [rbp+57h+var_50], rsi
0x1400742a4  mov     [rbp+57h+var_60], rax
0x1400742a8  lea     rdx, byte_1401405F5
0x1400742af  lea     rax, [rbp+57h+var_50]
0x1400742b3  mov     [rbp+57h+var_6C], 30Ch
0x1400742ba  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x1400742bf  lea     rax, [rbp+57h+var_6C]
0x1400742c3  mov     [rsp+0D0h+lpcValues], rax
0x1400742c8  lea     rax, [rbp+57h+var_58]
0x1400742cc  mov     [rsp+0D0h+lpcbMaxClassLen], rax
0x1400742d1  lea     rax, [rbp+57h+var_70]
0x1400742d5  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax
0x1400742da  lea     rax, [rbp+57h+var_60]
0x1400742de  mov     [rsp+0D0h+phkResult], rax
0x1400742e3  mov     [rbp+57h+var_58], r14
0x1400742e7  mov     [rbp+57h+var_70], ebx
0x1400742ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400742ef  mov     ebx, 8007000Eh
0x1400742f4  mov     rcx, [rbp+57h+var_48]; hKey
0x1400742f8  test    rcx, rcx
0x1400742fb  jz      short loc_140074307
0x1400742fd  call    cs:__imp_RegCloseKey
0x140074303  mov     [rbp+57h+var_48], r13
0x140074307  mov     rcx, [rbp+57h+hKey]; hKey
0x14007430b  test    rcx, rcx
0x14007430e  jz      short loc_14007431A
0x140074310  call    cs:__imp_RegCloseKey
0x140074316  mov     [rbp+57h+hKey], r13
0x14007431a  test    rdi, rdi
0x14007431d  jz      short loc_140074328
0x14007431f  mov     rcx, rdi; hMem
0x140074322  call    cs:__imp_LocalFree
0x140074328  mov     eax, ebx
0x14007432a  mov     rbx, [rsp+0D0h+arg_0]
0x140074332  add     rsp, 0A0h
0x140074339  pop     r15
0x14007433b  pop     r14
0x14007433d  pop     r13
0x14007433f  pop     r12
0x140074341  pop     rdi
0x140074342  pop     rsi
0x140074343  pop     rbp
0x140074344  retn
```
