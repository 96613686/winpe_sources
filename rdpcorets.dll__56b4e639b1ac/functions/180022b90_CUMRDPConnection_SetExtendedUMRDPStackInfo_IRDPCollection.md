# CUMRDPConnection::SetExtendedUMRDPStackInfo(IRDPCollection *)

- ea: `0x180022b90`
- end: `0x180022ee0`
- name: `?SetExtendedUMRDPStackInfo@CUMRDPConnection@@IEAAJPEAUIRDPCollection@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(CUMRDPConnection *__hidden this, struct IRDPCollection *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800527c0`

## callees

- `0x1800015f0`
- `0x18000f784`
- `0x180022b90`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022c1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022c97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022c1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022c97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022c38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022cb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022c38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022cb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022be2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022c62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022be2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022c62`

## string_xrefs

- `0x180022bb9`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x180022c13`: `MaxCompressionLevel`
- `0x180022deb`: `MaxCompressionLevel`
- `0x180022d51`: `RDPENCSTACK_COMPRESSION_DISABLED`
- `0x180022d7c`: `Failed to set the property RDPENC_STACK_PROP_COMPRESSION_DISABLED`
- `0x180022e16`: `Failed to set the property CONN_MAX_COMPRESSIONLEVEL`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::SetExtendedUMRDPStackInfo(CUMRDPConnection *this, struct IRDPCollection *a2)
{
  int v2; // ebx
  unsigned int v5; // r14d
  unsigned int v6; // r15d
  unsigned int v7; // esi
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  int v11; // ebx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const char *v17; // rax
  __int16 *v18; // rdx
  int v20; // [rsp+50h] [rbp-19h] BYREF
  const char *v21; // [rsp+58h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  const char *v23; // [rsp+68h] [rbp-1h] BYREF
  const char *v24; // [rsp+70h] [rbp+7h] BYREF
  const char *v25; // [rsp+78h] [rbp+Fh] BYREF
  _QWORD v26[8]; // [rsp+80h] [rbp+17h] BYREF
  DWORD cbData; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int Data; // [rsp+E0h] [rbp+77h] BYREF
  DWORD Type; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = 0;
  Data = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  v5 = 0;
  v6 = 0;
  v7 = 3;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MaxCompressionLevel", 0, &Type, (LPBYTE)&Data, &cbData) && !Data )
    {
      v7 = 0;
      v6 = 1;
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"SendBufferSize", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      v5 = Data;
      v2 = 1;
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v2 )
  {
    v8 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const WCHAR *, _QWORD))(*(_QWORD *)a2 + 72LL))(
           a2,
           L"SendBufferSize",
           v5);
    if ( v8 < 0 && (unsigned int)dword_1801B76C8 > 3 )
    {
      v20 = v8;
      v21 = "SetExtendedUMRDPStackInfo";
      v23 = "SetPropertyUnsignedLong(CONN_SET_SENDBUF_SIZE) failed.";
      v24 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)qword_180193118,
        v9,
        v10,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v20,
        (__int64)&v21);
    }
  }
  v11 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 64LL))(
          a2,
          L"RDPENCSTACK_COMPRESSION_DISABLED",
          v6);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const WCHAR *, _QWORD))(*(_QWORD *)a2 + 72LL))(
            a2,
            L"MaxCompressionLevel",
            v7);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 64LL))(
              a2,
              L"AlwaysEncryptClientToServerData",
              *((unsigned int *)this + 206));
      if ( v11 >= 0 || (unsigned int)dword_1801B76C8 <= 2 )
        return (unsigned int)v11;
      v17 = "Failed to set the property CONN_PROPERTY_ALWAYS_ENCRYPT_CS_DATA";
      LODWORD(v21) = 6454;
      v18 = (__int16 *)byte_180193025;
    }
    else
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        return (unsigned int)v11;
      v17 = "Failed to set the property CONN_MAX_COMPRESSIONLEVEL";
      LODWORD(v21) = 6451;
      v18 = &word_180193076;
    }
    v26[0] = v17;
    v24 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v23 = "Error HResult failed";
    v20 = v11;
    v25 = "SetExtendedUMRDPStackInfo";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v14,
      (_DWORD)v18,
      v15,
      v16,
      (__int64)&v23,
      (__int64)&v20,
      (__int64)&v24,
      (__int64)&v21,
      (__int64)&v25,
      (__int64)v26);
    return (unsigned int)v11;
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v23 = "SetExtendedUMRDPStackInfo";
    v24 = "Failed to set the property RDPENC_STACK_PROP_COMPRESSION_DISABLED";
    v20 = 6448;
    v25 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v26[0] = "Error HResult failed";
    LODWORD(v21) = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)&byte_1801930C7,
      v12,
      v13,
      (__int64)v26,
      (__int64)&v21,
      (__int64)&v25,
      (__int64)&v20,
      (__int64)&v23,
      (__int64)&v24);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180022b90  push    rbp
0x180022b92  push    rbx
0x180022b93  push    rsi
0x180022b94  push    rdi
0x180022b95  push    r13
0x180022b97  push    r14
0x180022b99  push    r15
0x180022b9b  lea     rbp, [rsp-27h]
0x180022ba0  sub     rsp, 90h
0x180022ba7  xor     ebx, ebx
0x180022ba9  lea     rax, [rbp+57h+hKey]
0x180022bad  mov     rdi, rdx
0x180022bb0  mov     [rbp+57h+Data], ebx
0x180022bb3  mov     r13, rcx
0x180022bb6  mov     [rbp+57h+cbData], ebx
0x180022bb9  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x180022bc0  mov     [rbp+57h+Type], ebx
0x180022bc3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022bca  mov     [rbp+57h+hKey], rbx
0x180022bce  mov     r9d, 20019h; samDesired
0x180022bd4  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180022bd9  xor     r8d, r8d; ulOptions
0x180022bdc  xor     r14d, r14d
0x180022bdf  xor     r15d, r15d
0x180022be2  call    cs:__imp_RegOpenKeyExW
0x180022be8  lea     esi, [rbx+3]
0x180022beb  test    eax, eax
0x180022bed  jnz     short loc_180022C2F
0x180022bef  mov     rcx, [rbp+57h+hKey]; hKey
0x180022bf3  lea     rax, [rbp+57h+cbData]
0x180022bf7  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180022bfc  lea     r9, [rbp+57h+Type]; lpType
0x180022c00  lea     rax, [rbp+57h+Data]
0x180022c04  mov     [rbp+57h+cbData], 4
0x180022c0b  xor     r8d, r8d; lpReserved
0x180022c0e  mov     [rsp+0C0h+phkResult], rax; lpData
0x180022c13  lea     rdx, aMaxcompression; "MaxCompressionLevel"
0x180022c1a  call    cs:__imp_RegQueryValueExW
0x180022c20  test    eax, eax
0x180022c22  jnz     short loc_180022C2F
0x180022c24  cmp     [rbp+57h+Data], ebx
0x180022c27  jnz     short loc_180022C2F
0x180022c29  xor     esi, esi
0x180022c2b  lea     r15d, [r14+1]
0x180022c2f  mov     rcx, [rbp+57h+hKey]; hKey
0x180022c33  test    rcx, rcx
0x180022c36  jz      short loc_180022C42
0x180022c38  call    cs:__imp_RegCloseKey
0x180022c3e  mov     [rbp+57h+hKey], rbx
0x180022c42  lea     rax, [rbp+57h+hKey]
0x180022c46  mov     r9d, 20019h; samDesired
0x180022c4c  xor     r8d, r8d; ulOptions
0x180022c4f  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180022c54  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x180022c5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022c62  call    cs:__imp_RegOpenKeyExW
0x180022c68  test    eax, eax
0x180022c6a  jnz     short loc_180022CAE
0x180022c6c  mov     rcx, [rbp+57h+hKey]; hKey
0x180022c70  lea     rax, [rbp+57h+cbData]
0x180022c74  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180022c79  lea     r9, [rbp+57h+Type]; lpType
0x180022c7d  lea     rax, [rbp+57h+Data]
0x180022c81  mov     [rbp+57h+cbData], 4
0x180022c88  xor     r8d, r8d; lpReserved
0x180022c8b  mov     [rsp+0C0h+phkResult], rax; lpData
0x180022c90  lea     rdx, aSendbuffersize; "SendBufferSize"
0x180022c97  call    cs:__imp_RegQueryValueExW
0x180022c9d  test    eax, eax
0x180022c9f  jnz     short loc_180022CAE
0x180022ca1  cmp     [rbp+57h+Type], 4
0x180022ca5  jnz     short loc_180022CAE
0x180022ca7  mov     r14d, [rbp+57h+Data]
0x180022cab  lea     ebx, [rax+1]
0x180022cae  mov     rcx, [rbp+57h+hKey]; hKey
0x180022cb2  test    rcx, rcx
0x180022cb5  jz      short loc_180022CC5
0x180022cb7  call    cs:__imp_RegCloseKey
0x180022cbd  mov     [rbp+57h+hKey], 0
0x180022cc5  test    ebx, ebx
0x180022cc7  jz      short loc_180022D47
0x180022cc9  mov     rax, [rdi]
0x180022ccc  lea     rdx, aSendbuffersize; "SendBufferSize"
0x180022cd3  mov     r8d, r14d
0x180022cd6  mov     rcx, rdi
0x180022cd9  mov     rax, [rax+48h]
0x180022cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ce2  test    eax, eax
0x180022ce4  jns     short loc_180022D47
0x180022ce6  mov     ecx, cs:dword_1801B76C8
0x180022cec  cmp     ecx, 3
0x180022cef  jbe     short loc_180022D47
0x180022cf1  mov     [rbp+57h+var_70], eax
0x180022cf4  lea     r14, aSetextendedumr; "SetExtendedUMRDPStackInfo"
0x180022cfb  lea     rax, aSetpropertyuns; "SetPropertyUnsignedLong(CONN_SET_SENDBU"...
0x180022d02  mov     [rbp+57h+var_68], r14
0x180022d06  mov     [rbp+57h+var_58], rax
0x180022d0a  lea     rdx, qword_180193118
0x180022d11  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180022d18  mov     [rbp+57h+var_50], rax
0x180022d1c  lea     rax, [rbp+57h+var_68]
0x180022d20  mov     [rsp+0C0h+var_88], rax
0x180022d25  lea     rax, [rbp+57h+var_70]
0x180022d29  mov     [rsp+0C0h+var_90], rax
0x180022d2e  lea     rax, [rbp+57h+var_58]
0x180022d32  mov     [rsp+0C0h+lpcbData], rax
0x180022d37  lea     rax, [rbp+57h+var_50]
0x180022d3b  mov     [rsp+0C0h+phkResult], rax
0x180022d40  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180022d45  jmp     short loc_180022D4E
0x180022d47  lea     r14, aSetextendedumr; "SetExtendedUMRDPStackInfo"
0x180022d4e  mov     rax, [rdi]
0x180022d51  lea     rdx, aRdpencstackCom; "RDPENCSTACK_COMPRESSION_DISABLED"
0x180022d58  mov     r8d, r15d
0x180022d5b  mov     rcx, rdi
0x180022d5e  mov     rax, [rax+40h]
0x180022d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d67  mov     ebx, eax
0x180022d69  test    eax, eax
0x180022d6b  jns     short loc_180022DE8
0x180022d6d  mov     ecx, cs:dword_1801B76C8
0x180022d73  cmp     ecx, 2
0x180022d76  jbe     loc_180022ECC
0x180022d7c  lea     rax, aFailedToSetThe_19; "Failed to set the property RDPENC_STACK"...
0x180022d83  mov     [rbp+57h+var_58], r14
0x180022d87  mov     [rbp+57h+var_50], rax
0x180022d8b  lea     rdx, byte_1801930C7
0x180022d92  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180022d99  mov     [rbp+57h+var_70], 1930h
0x180022da0  mov     [rbp+57h+var_48], rax
0x180022da4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180022dab  mov     [rbp+57h+var_40], rax
0x180022daf  lea     rax, [rbp+57h+var_50]
0x180022db3  mov     [rsp+0C0h+var_78], rax
0x180022db8  lea     rax, [rbp+57h+var_58]
0x180022dbc  mov     [rsp+0C0h+var_80], rax
0x180022dc1  lea     rax, [rbp+57h+var_70]
0x180022dc5  mov     [rsp+0C0h+var_88], rax
0x180022dca  lea     rax, [rbp+57h+var_48]
0x180022dce  mov     [rsp+0C0h+var_90], rax
0x180022dd3  lea     rax, [rbp+57h+var_68]
0x180022dd7  mov     [rsp+0C0h+lpcbData], rax
0x180022ddc  lea     rax, [rbp+57h+var_40]
0x180022de0  mov     dword ptr [rbp+57h+var_68], ebx
0x180022de3  jmp     loc_180022EC2
0x180022de8  mov     rax, [rdi]
0x180022deb  lea     rdx, aMaxcompression; "MaxCompressionLevel"
0x180022df2  mov     r8d, esi
0x180022df5  mov     rcx, rdi
0x180022df8  mov     rax, [rax+48h]
0x180022dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e01  mov     ebx, eax
0x180022e03  test    eax, eax
0x180022e05  jns     short loc_180022E2D
0x180022e07  mov     eax, cs:dword_1801B76C8
0x180022e0d  cmp     eax, 2
0x180022e10  jbe     loc_180022ECC
0x180022e16  lea     rax, aFailedToSetThe_1; "Failed to set the property CONN_MAX_COM"...
0x180022e1d  mov     dword ptr [rbp+57h+var_68], 1933h
0x180022e24  lea     rdx, word_180193076
0x180022e2b  jmp     short loc_180022E70
0x180022e2d  mov     rax, [rdi]
0x180022e30  lea     rdx, aAlwaysencryptc; "AlwaysEncryptClientToServerData"
0x180022e37  mov     r8d, [r13+338h]
0x180022e3e  mov     rcx, rdi
0x180022e41  mov     rax, [rax+40h]
0x180022e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e4a  mov     ebx, eax
0x180022e4c  test    eax, eax
0x180022e4e  jns     short loc_180022ECC
0x180022e50  mov     eax, cs:dword_1801B76C8
0x180022e56  cmp     eax, 2
0x180022e59  jbe     short loc_180022ECC
0x180022e5b  lea     rax, aFailedToSetThe_6; "Failed to set the property CONN_PROPERT"...
0x180022e62  mov     dword ptr [rbp+57h+var_68], 1936h
0x180022e69  lea     rdx, byte_180193025
0x180022e70  mov     [rbp+57h+var_40], rax
0x180022e74  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180022e7b  mov     [rbp+57h+var_50], rax
0x180022e7f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180022e86  mov     [rbp+57h+var_58], rax
0x180022e8a  lea     rax, [rbp+57h+var_40]
0x180022e8e  mov     [rsp+0C0h+var_78], rax
0x180022e93  lea     rax, [rbp+57h+var_48]
0x180022e97  mov     [rsp+0C0h+var_80], rax
0x180022e9c  lea     rax, [rbp+57h+var_68]
0x180022ea0  mov     [rsp+0C0h+var_88], rax
0x180022ea5  lea     rax, [rbp+57h+var_50]
0x180022ea9  mov     [rsp+0C0h+var_90], rax
0x180022eae  lea     rax, [rbp+57h+var_70]
0x180022eb2  mov     [rsp+0C0h+lpcbData], rax
0x180022eb7  lea     rax, [rbp+57h+var_58]
0x180022ebb  mov     [rbp+57h+var_70], ebx
0x180022ebe  mov     [rbp+57h+var_48], r14
0x180022ec2  mov     [rsp+0C0h+phkResult], rax
0x180022ec7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022ecc  mov     eax, ebx
0x180022ece  add     rsp, 90h
0x180022ed5  pop     r15
0x180022ed7  pop     r14
0x180022ed9  pop     r13
0x180022edb  pop     rdi
0x180022edc  pop     rsi
0x180022edd  pop     rbx
0x180022ede  pop     rbp
0x180022edf  retn
```
