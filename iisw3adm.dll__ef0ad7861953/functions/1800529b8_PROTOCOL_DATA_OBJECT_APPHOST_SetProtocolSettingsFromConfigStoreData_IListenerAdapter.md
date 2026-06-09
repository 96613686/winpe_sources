# PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData(IListenerAdapter *)

- ea: `0x1800529b8`
- end: `0x180052cc4`
- name: `?SetProtocolSettingsFromConfigStoreData@PROTOCOL_DATA_OBJECT_APPHOST@@QEAAJPEAUIListenerAdapter@@@Z`
- size: `780`
- prototype: `__int64 __fastcall(PROTOCOL_DATA_OBJECT_APPHOST *__hidden this, struct IListenerAdapter *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800526d0`

## callees

- `0x1800529b8`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180052a31`
- `OLEAUT32!__imp_SysAllocString` at `0x180052a31`
- `OLEAUT32!__imp_SysFreeString` at `0x180052aff`
- `OLEAUT32!__imp_SysFreeString` at `0x180052bcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c95`
- `OLEAUT32!__imp_SysFreeString` at `0x180052caf`
- `OLEAUT32!__imp_SysFreeString` at `0x180052aff`
- `OLEAUT32!__imp_SysFreeString` at `0x180052bcc`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c95`
- `OLEAUT32!__imp_SysFreeString` at `0x180052caf`
- `iisutil!PuDbgPrint` at `0x180052a9d`
- `iisutil!PuDbgPrint` at `0x180052b8e`
- `iisutil!PuDbgPrint` at `0x180052c5b`
- `iisutil!PuDbgPrint` at `0x180052a9d`
- `iisutil!PuDbgPrint` at `0x180052b8e`
- `iisutil!PuDbgPrint` at `0x180052c5b`
- `iisutil!PuDbgPrintError` at `0x180052a24`
- `iisutil!PuDbgPrintError` at `0x180052af0`
- `iisutil!PuDbgPrintError` at `0x180052a24`
- `iisutil!PuDbgPrintError` at `0x180052af0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052ab0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052ba4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052c71`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052ab0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052ba4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180052c71`

## string_xrefs

- `0x180052acf`: ` Failed copying string property \n`
- `0x1800529fd`: ` Failed reading identity property \n`
- `0x180052b33`: ` Failed reading protocolManagerDll property \n`
- `0x180052b76`: ` ProtocolManagerDll = '%s' \n`
- `0x180052c00`: ` Failed reading ProtocolManagerDllInitFunction property \n`
- `0x180052c4a`: ` ProtocolManagerDllInitFunction = '%s' \n`
- `0x1800529e9`: `PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData`
- `0x180052a0c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_apphost.cxx`
- `0x180052a85`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_apphost.cxx`
- `0x180052add`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_apphost.cxx`
- `0x180052b5c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_apphost.cxx`
- `0x180052c2c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocolstore_apphost.cxx`

## pseudocode

```c
__int64 __fastcall PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData(
        PROTOCOL_DATA_OBJECT_APPHOST *this,
        struct IListenerAdapter *a2)
{
  __int64 v2; // rax
  int v5; // eax
  int v6; // ebx
  BSTR v7; // rsi
  BSTR v8; // rax
  __int64 v9; // r8
  BSTR v10; // rcx
  BSTR bstrString; // [rsp+78h] [rbp+40h] BYREF

  v2 = *(_QWORD *)a2;
  bstrString = 0;
  v5 = (*(__int64 (__fastcall **)(struct IListenerAdapter *, BSTR *))(v2 + 64))(a2, &bstrString);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
        53,
        "PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData",
        v5,
        " Failed reading identity property \n");
    bstrString = SysAllocString(&SourceString);
    if ( !bstrString )
    {
      v6 = -2147024882;
      goto LABEL_41;
    }
  }
  v7 = L"NULL";
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v8 = L"NULL";
    if ( bstrString )
      v8 = bstrString;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
      69,
      "PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData",
      " Identity = '%s' \n",
      (const char *)v8);
  }
  if ( bstrString )
  {
    v6 = STRU::Copy((PROTOCOL_DATA_OBJECT_APPHOST *)((char *)this + 104), bstrString);
    if ( v6 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_41;
      v9 = 79;
      goto LABEL_14;
    }
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v6 = (*(__int64 (__fastcall **)(struct IListenerAdapter *, BSTR *))(*(_QWORD *)a2 + 72LL))(a2, &bstrString);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
        92,
        "PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData",
        v6,
        " Failed reading protocolManagerDll property \n");
    goto LABEL_41;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    v10 = L"NULL";
    if ( bstrString )
      v10 = bstrString;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
      100,
      "PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData",
      " ProtocolManagerDll = '%s' \n",
      (const char *)v10);
  }
  if ( bstrString )
  {
    v6 = STRU::Copy((PROTOCOL_DATA_OBJECT_APPHOST *)((char *)this + 160), bstrString);
    if ( v6 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_41;
      v9 = 110;
      goto LABEL_14;
    }
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v6 = (*(__int64 (__fastcall **)(struct IListenerAdapter *, BSTR *))(*(_QWORD *)a2 + 80LL))(a2, &bstrString);
  if ( v6 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
        123,
        "PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData",
        v6,
        " Failed reading ProtocolManagerDllInitFunction property \n");
    goto LABEL_41;
  }
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x40000000) != 0 )
  {
    if ( bstrString )
      v7 = bstrString;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
      131,
      "PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData",
      " ProtocolManagerDllInitFunction = '%s' \n",
      (const char *)v7);
  }
  if ( bstrString )
  {
    v6 = STRU::Copy((PROTOCOL_DATA_OBJECT_APPHOST *)((char *)this + 216), bstrString);
    if ( v6 >= 0 )
    {
      SysFreeString(bstrString);
      bstrString = 0;
      goto LABEL_41;
    }
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_41;
    v9 = 141;
LABEL_14:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocolstore_apphost.cxx",
      v9,
      "PROTOCOL_DATA_OBJECT_APPHOST::SetProtocolSettingsFromConfigStoreData",
      v6,
      " Failed copying string property \n");
LABEL_41:
    if ( bstrString )
      SysFreeString(bstrString);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800529b8  push    rbp
0x1800529ba  push    rbx
0x1800529bb  push    rsi
0x1800529bc  push    rdi
0x1800529bd  push    r13
0x1800529bf  push    r14
0x1800529c1  mov     rbp, rsp
0x1800529c4  sub     rsp, 38h
0x1800529c8  mov     rax, [rdx]
0x1800529cb  mov     rdi, rdx
0x1800529ce  mov     r14, rcx
0x1800529d1  mov     [rbp+bstrString], 0
0x1800529d9  lea     rdx, [rbp+bstrString]
0x1800529dd  mov     rcx, rdi
0x1800529e0  mov     rax, [rax+40h]
0x1800529e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529e9  lea     r13, aProtocolDataOb; "PROTOCOL_DATA_OBJECT_APPHOST::SetProtoc"...
0x1800529f0  test    eax, eax
0x1800529f2  jns     short loc_180052A4A
0x1800529f4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800529fb  jz      short loc_180052A2A
0x1800529fd  lea     rcx, aFailedReadingI; " Failed reading identity property \n"
0x180052a04  mov     r9, r13
0x180052a07  mov     [rsp+38h+var_10], rcx
0x180052a0c  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052a13  mov     rcx, cs:g_pDebug
0x180052a1a  mov     r8d, 35h ; '5'
0x180052a20  mov     dword ptr [rsp+38h+var_18], eax
0x180052a24  call    cs:__imp_PuDbgPrintError
0x180052a2a  lea     rcx, SourceString; psz
0x180052a31  call    cs:__imp_SysAllocString
0x180052a37  mov     [rbp+bstrString], rax
0x180052a3b  test    rax, rax
0x180052a3e  jnz     short loc_180052A4A
0x180052a40  mov     ebx, 8007000Eh
0x180052a45  jmp     loc_180052CA3
0x180052a4a  mov     eax, cs:g_dwDebugFlags
0x180052a50  lea     rsi, aNull_0; "NULL"
0x180052a57  test    al, 3
0x180052a59  setnz   cl
0x180052a5c  bt      eax, 1Eh
0x180052a60  setb    al
0x180052a63  test    al, cl
0x180052a65  jz      short loc_180052AA3
0x180052a67  mov     rdx, [rbp+bstrString]
0x180052a6b  mov     rax, rsi
0x180052a6e  mov     rcx, cs:g_pDebug
0x180052a75  test    rdx, rdx
0x180052a78  mov     r9, r13
0x180052a7b  mov     r8d, 45h ; 'E'
0x180052a81  cmovnz  rax, rdx
0x180052a85  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052a8c  mov     [rsp+38h+var_10], rax
0x180052a91  lea     rax, aIdentityS; " Identity = '%s' \n"
0x180052a98  mov     [rsp+38h+var_18], rax
0x180052a9d  call    cs:__imp_PuDbgPrint
0x180052aa3  mov     rdx, [rbp+bstrString]
0x180052aa7  test    rdx, rdx
0x180052aaa  jz      short loc_180052B0D
0x180052aac  lea     rcx, [r14+68h]
0x180052ab0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180052ab6  mov     ebx, eax
0x180052ab8  test    eax, eax
0x180052aba  jns     short loc_180052AFB
0x180052abc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180052ac3  jz      loc_180052CA3
0x180052ac9  mov     r8d, 4Fh ; 'O'
0x180052acf  lea     rax, aFailedCopyingS; " Failed copying string property \n"
0x180052ad6  mov     rcx, cs:g_pDebug
0x180052add  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052ae4  mov     [rsp+38h+var_10], rax
0x180052ae9  mov     r9, r13
0x180052aec  mov     dword ptr [rsp+38h+var_18], ebx
0x180052af0  call    cs:__imp_PuDbgPrintError
0x180052af6  jmp     loc_180052CA3
0x180052afb  mov     rcx, [rbp+bstrString]; bstrString
0x180052aff  call    cs:__imp_SysFreeString
0x180052b05  mov     [rbp+bstrString], 0
0x180052b0d  mov     rax, [rdi]
0x180052b10  lea     rdx, [rbp+bstrString]
0x180052b14  mov     rcx, rdi
0x180052b17  mov     rax, [rax+48h]
0x180052b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b20  mov     ebx, eax
0x180052b22  test    eax, eax
0x180052b24  jns     short loc_180052B42
0x180052b26  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180052b2d  jz      loc_180052CA3
0x180052b33  lea     rax, aFailedReadingP_0; " Failed reading protocolManagerDll prop"...
0x180052b3a  mov     r8d, 5Ch ; '\'
0x180052b40  jmp     short loc_180052AD6
0x180052b42  mov     eax, cs:g_dwDebugFlags
0x180052b48  test    al, 3
0x180052b4a  setnz   cl
0x180052b4d  bt      eax, 1Eh
0x180052b51  setb    al
0x180052b54  test    al, cl
0x180052b56  jz      short loc_180052B94
0x180052b58  mov     rax, [rbp+bstrString]
0x180052b5c  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052b63  test    rax, rax
0x180052b66  mov     rcx, rsi
0x180052b69  mov     r9, r13
0x180052b6c  mov     r8d, 64h ; 'd'
0x180052b72  cmovnz  rcx, rax
0x180052b76  lea     rax, aProtocolmanage_0; " ProtocolManagerDll = '%s' \n"
0x180052b7d  mov     [rsp+38h+var_10], rcx
0x180052b82  mov     rcx, cs:g_pDebug
0x180052b89  mov     [rsp+38h+var_18], rax
0x180052b8e  call    cs:__imp_PuDbgPrint
0x180052b94  mov     rdx, [rbp+bstrString]
0x180052b98  test    rdx, rdx
0x180052b9b  jz      short loc_180052BDA
0x180052b9d  lea     rcx, [r14+0A0h]
0x180052ba4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180052baa  mov     ebx, eax
0x180052bac  test    eax, eax
0x180052bae  jns     short loc_180052BC8
0x180052bb0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180052bb7  jz      loc_180052CA3
0x180052bbd  mov     r8d, 6Eh ; 'n'
0x180052bc3  jmp     loc_180052ACF
0x180052bc8  mov     rcx, [rbp+bstrString]; bstrString
0x180052bcc  call    cs:__imp_SysFreeString
0x180052bd2  mov     [rbp+bstrString], 0
0x180052bda  mov     rax, [rdi]
0x180052bdd  lea     rdx, [rbp+bstrString]
0x180052be1  mov     rcx, rdi
0x180052be4  mov     rax, [rax+50h]
0x180052be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052bed  mov     ebx, eax
0x180052bef  test    eax, eax
0x180052bf1  jns     short loc_180052C12
0x180052bf3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180052bfa  jz      loc_180052CA3
0x180052c00  lea     rax, aFailedReadingP; " Failed reading ProtocolManagerDllInitF"...
0x180052c07  mov     r8d, 7Bh ; '{'
0x180052c0d  jmp     loc_180052AD6
0x180052c12  mov     eax, cs:g_dwDebugFlags
0x180052c18  test    al, 3
0x180052c1a  setnz   cl
0x180052c1d  bt      eax, 1Eh
0x180052c21  setb    al
0x180052c24  test    al, cl
0x180052c26  jz      short loc_180052C61
0x180052c28  mov     rax, [rbp+bstrString]
0x180052c2c  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180052c33  mov     rcx, cs:g_pDebug
0x180052c3a  test    rax, rax
0x180052c3d  mov     r9, r13
0x180052c40  mov     r8d, 83h
0x180052c46  cmovnz  rsi, rax
0x180052c4a  lea     rax, aProtocolmanage; " ProtocolManagerDllInitFunction = '%s' "...
0x180052c51  mov     [rsp+38h+var_10], rsi
0x180052c56  mov     [rsp+38h+var_18], rax
0x180052c5b  call    cs:__imp_PuDbgPrint
0x180052c61  mov     rdx, [rbp+bstrString]
0x180052c65  test    rdx, rdx
0x180052c68  jz      short loc_180052CB5
0x180052c6a  lea     rcx, [r14+0D8h]
0x180052c71  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180052c77  mov     ebx, eax
0x180052c79  test    eax, eax
0x180052c7b  jns     short loc_180052C91
0x180052c7d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180052c84  jz      short loc_180052CA3
0x180052c86  mov     r8d, 8Dh
0x180052c8c  jmp     loc_180052ACF
0x180052c91  mov     rcx, [rbp+bstrString]; bstrString
0x180052c95  call    cs:__imp_SysFreeString
0x180052c9b  mov     [rbp+bstrString], 0
0x180052ca3  mov     rdx, [rbp+bstrString]
0x180052ca7  test    rdx, rdx
0x180052caa  jz      short loc_180052CB5
0x180052cac  mov     rcx, rdx; bstrString
0x180052caf  call    cs:__imp_SysFreeString
0x180052cb5  mov     eax, ebx
0x180052cb7  add     rsp, 38h
0x180052cbb  pop     r14
0x180052cbd  pop     r13
0x180052cbf  pop     rdi
0x180052cc0  pop     rsi
0x180052cc1  pop     rbx
0x180052cc2  pop     rbp
0x180052cc3  retn
```
