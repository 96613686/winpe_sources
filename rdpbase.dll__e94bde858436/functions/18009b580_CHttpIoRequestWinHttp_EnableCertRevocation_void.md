# CHttpIoRequestWinHttp::EnableCertRevocation(void)

- ea: `0x18009b580`
- end: `0x18009b751`
- name: `?EnableCertRevocation@CHttpIoRequestWinHttp@@UEAAJXZ`
- size: `465`
- prototype: `__int64 __fastcall(CHttpIoRequestWinHttp *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001aa0`
- `0x180001e7c`
- `0x18009b580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b69d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b69d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009b63f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009b63f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009b73e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009b73e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b5ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b5ca`
- `WINHTTP!WinHttpSetOption` at `0x18009b68f`
- `WINHTTP!WinHttpSetOption` at `0x18009b68f`

## string_xrefs

- `0x18009b5f5`: `RegOpenKeyEx failed. Continuing with default value.`

## pseudocode

```c
__int64 __fastcall CHttpIoRequestWinHttp::EnableCertRevocation(HINTERNET *this)
{
  unsigned int v2; // ebx
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  char *v6; // rdx
  const char *v7; // rax
  signed int LastError; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char *v13; // [rsp+50h] [rbp+7h] BYREF
  const char *v14; // [rsp+58h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+60h] [rbp+17h] BYREF
  const char *v16; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v17; // [rsp+70h] [rbp+27h] BYREF
  const char *v18; // [rsp+78h] [rbp+2Fh] BYREF
  const char *v19; // [rsp+80h] [rbp+37h] BYREF
  int Data; // [rsp+B8h] [rbp+6Fh] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+77h] BYREF
  int Buffer; // [rsp+C8h] [rbp+7Fh] BYREF

  cbData = 4;
  v2 = 0;
  Buffer = 1;
  hKey = 0;
  Data = 0;
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Terminal Server Gateway\\Transports\\Rpc",
         0,
         0x20019u,
         &hKey) )
  {
    if ( (unsigned int)CallbackContext <= 4 )
      goto LABEL_14;
    v14 = "EnableCertRevocation";
    v6 = byte_1801B0B03;
    v7 = "RegOpenKeyEx failed. Continuing with default value.";
    goto LABEL_4;
  }
  if ( RegQueryValueExW(hKey, L"CheckForRevocation", 0, 0, (LPBYTE)&Data, &cbData) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v14 = "EnableCertRevocation";
      v6 = byte_1801B0AD9;
      v7 = "RegQueryValueEx failed. Continuing with default value.";
LABEL_4:
      v13 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v3,
        (_DWORD)v6,
        v4,
        v5,
        (__int64)&v13,
        (__int64)&v14);
    }
  }
  else if ( Data == 1 && !WinHttpSetOption(this[3], 0x4Fu, &Buffer, 4u) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v13) = 3183;
      v16 = "WinHttpSetOption failed";
      LODWORD(v14) = v2;
      v17 = "EnableCertRevocation";
      v18 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttp\\httpiowinhttp.cpp";
      v19 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)byte_1801B0A8D,
        v10,
        v11,
        (__int64)&v19,
        (__int64)&v14,
        (__int64)&v18,
        (__int64)&v13,
        (__int64)&v17,
        (__int64)&v16);
    }
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18009b580  push    rbp
0x18009b582  push    rbx
0x18009b583  push    rdi
0x18009b584  lea     rbp, [rsp-47h]
0x18009b589  sub     rsp, 90h
0x18009b590  mov     rdi, rcx
0x18009b593  mov     [rbp+57h+cbData], 4
0x18009b59a  xor     ebx, ebx
0x18009b59c  mov     [rbp+57h+Buffer], 1
0x18009b5a3  lea     rax, [rbp+57h+hKey]
0x18009b5a7  mov     [rbp+57h+hKey], rbx
0x18009b5ab  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009b5b2  mov     [rbp+57h+Data], ebx
0x18009b5b5  mov     r9d, 20019h; samDesired
0x18009b5bb  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18009b5c0  xor     r8d, r8d; ulOptions
0x18009b5c3  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Terminal Server Ga"...
0x18009b5ca  call    cs:__imp_RegOpenKeyExW
0x18009b5d0  test    eax, eax
0x18009b5d2  jz      short loc_18009B61C
0x18009b5d4  mov     eax, cs:CallbackContext
0x18009b5da  cmp     eax, 4
0x18009b5dd  jbe     loc_18009B735
0x18009b5e3  lea     rax, aEnablecertrevo; "EnableCertRevocation"
0x18009b5ea  mov     [rbp+57h+var_48], rax
0x18009b5ee  lea     rdx, byte_1801B0B03
0x18009b5f5  lea     rax, aRegopenkeyexFa_0; "RegOpenKeyEx failed. Continuing with de"...
0x18009b5fc  mov     [rbp+57h+var_50], rax
0x18009b600  lea     rax, [rbp+57h+var_48]
0x18009b604  mov     [rsp+0A0h+lpcbData], rax
0x18009b609  lea     rax, [rbp+57h+var_50]
0x18009b60d  mov     [rsp+0A0h+phkResult], rax
0x18009b612  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009b617  jmp     loc_18009B735
0x18009b61c  mov     rcx, [rbp+57h+hKey]; hKey
0x18009b620  lea     rax, [rbp+57h+cbData]
0x18009b624  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18009b629  lea     rdx, aCheckforrevoca; "CheckForRevocation"
0x18009b630  lea     rax, [rbp+57h+Data]
0x18009b634  xor     r9d, r9d; lpType
0x18009b637  xor     r8d, r8d; lpReserved
0x18009b63a  mov     [rsp+0A0h+phkResult], rax; lpData
0x18009b63f  call    cs:__imp_RegQueryValueExW
0x18009b645  test    eax, eax
0x18009b647  jz      short loc_18009B673
0x18009b649  mov     eax, cs:CallbackContext
0x18009b64f  cmp     eax, 4
0x18009b652  jbe     loc_18009B735
0x18009b658  lea     rax, aEnablecertrevo; "EnableCertRevocation"
0x18009b65f  mov     [rbp+57h+var_48], rax
0x18009b663  lea     rdx, byte_1801B0AD9
0x18009b66a  lea     rax, aRegqueryvaluee; "RegQueryValueEx failed. Continuing with"...
0x18009b671  jmp     short loc_18009B5FC
0x18009b673  cmp     [rbp+57h+Data], 1
0x18009b677  jnz     loc_18009B735
0x18009b67d  mov     rcx, [rdi+18h]; hInternet
0x18009b681  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18009b685  mov     r9d, 4; dwBufferLength
0x18009b68b  lea     edx, [r9+4Bh]; dwOption
0x18009b68f  call    cs:__imp_WinHttpSetOption
0x18009b695  test    eax, eax
0x18009b697  jnz     loc_18009B735
0x18009b69d  call    cs:__imp_GetLastError
0x18009b6a3  mov     ebx, eax
0x18009b6a5  test    eax, eax
0x18009b6a7  jle     short loc_18009B6B2
0x18009b6a9  movzx   ebx, ax
0x18009b6ac  or      ebx, 80070000h
0x18009b6b2  mov     eax, cs:CallbackContext
0x18009b6b8  cmp     eax, 2
0x18009b6bb  jbe     short loc_18009B735
0x18009b6bd  lea     rax, aWinhttpsetopti_0; "WinHttpSetOption failed"
0x18009b6c4  mov     dword ptr [rbp+57h+var_50], 0C6Fh
0x18009b6cb  mov     [rbp+57h+var_38], rax
0x18009b6cf  lea     rdx, byte_1801B0A8D
0x18009b6d6  lea     rax, aEnablecertrevo; "EnableCertRevocation"
0x18009b6dd  mov     dword ptr [rbp+57h+var_48], ebx
0x18009b6e0  mov     [rbp+57h+var_30], rax
0x18009b6e4  lea     rax, aOnecoreTermsrv_8; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x18009b6eb  mov     [rbp+57h+var_28], rax
0x18009b6ef  lea     rax, aErrorCondition; "Error condition failed"
0x18009b6f6  mov     [rbp+57h+var_20], rax
0x18009b6fa  lea     rax, [rbp+57h+var_38]
0x18009b6fe  mov     [rsp+0A0h+var_58], rax
0x18009b703  lea     rax, [rbp+57h+var_30]
0x18009b707  mov     [rsp+0A0h+var_60], rax
0x18009b70c  lea     rax, [rbp+57h+var_50]
0x18009b710  mov     [rsp+0A0h+var_68], rax
0x18009b715  lea     rax, [rbp+57h+var_28]
0x18009b719  mov     [rsp+0A0h+var_70], rax
0x18009b71e  lea     rax, [rbp+57h+var_48]
0x18009b722  mov     [rsp+0A0h+lpcbData], rax
0x18009b727  lea     rax, [rbp+57h+var_20]
0x18009b72b  mov     [rsp+0A0h+phkResult], rax
0x18009b730  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009b735  mov     rcx, [rbp+57h+hKey]; hKey
0x18009b739  test    rcx, rcx
0x18009b73c  jz      short loc_18009B744
0x18009b73e  call    cs:__imp_RegCloseKey
0x18009b744  mov     eax, ebx
0x18009b746  add     rsp, 90h
0x18009b74d  pop     rdi
0x18009b74e  pop     rbx
0x18009b74f  pop     rbp
0x18009b750  retn
```
