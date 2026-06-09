# ProcessIsapiRequest(IIsapiCore *,ISAPI_CORE_DATA *,ISAPI_DLL *,ulong *)

- ea: `0x1800038ec`
- end: `0x180003bb3`
- name: `?ProcessIsapiRequest@@YAJPEAVIIsapiCore@@PEAUISAPI_CORE_DATA@@PEAVISAPI_DLL@@PEAK@Z`
- size: `711`
- prototype: `__int64 __fastcall(struct IIsapiCore *, struct ISAPI_CORE_DATA *, struct ISAPI_DLL *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b3d0`

## callees

- `0x1800038ec`
- `0x180005c8c`
- `0x180005e34`
- `0x180005f08`
- `0x180005f90`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039aa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800039a0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800039a0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003a3c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003a3c`
- `iisutil!PuDbgPrint` at `0x180003a29`
- `iisutil!PuDbgPrint` at `0x180003aad`
- `iisutil!PuDbgPrint` at `0x180003b40`
- `iisutil!PuDbgPrint` at `0x180003b8d`
- `iisutil!PuDbgPrint` at `0x180003a29`
- `iisutil!PuDbgPrint` at `0x180003aad`
- `iisutil!PuDbgPrint` at `0x180003b40`
- `iisutil!PuDbgPrint` at `0x180003b8d`

## string_xrefs

- `0x1800039f8`: `\n  Calling into HttpExtensionProc\n    Extension: '%S'\n    pECB: %p\n  <END>\n\n`
- `0x180003a04`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180003a7c`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180003b13`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180003b54`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180003aa1`: `\n  HttpExtensionProc returned HSE_STATUS_PENDING\n    Extension: '%S'\n    pECB: %p\n  <END>\n\n`
- `0x180003b34`: `\n  HttpExtensionProc returned %s\n    Extension: '%S'\n    pECB: %p\n  <END>\n\n`
- `0x180003b79`: `\n  HttpExtensionProc returned unknown status 0x%08x (%d)\n    Extension: '%S'\n    pECB: %p\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall ProcessIsapiRequest(
        struct IIsapiCore *a1,
        struct ISAPI_CORE_DATA *a2,
        struct ISAPI_DLL *a3,
        unsigned int *a4)
{
  __int64 v4; // rax
  ISAPI_CONTEXT *v9; // rax
  ISAPI_CONTEXT *v10; // rbx
  __int64 (__fastcall *v11)(ISAPI_CONTEXT *); // rdi
  void *Token; // rax
  signed int LastError; // eax
  unsigned int v14; // edi
  unsigned int v15; // edi
  const char *v16; // rax
  ISAPI_CONTEXT *v18; // [rsp+80h] [rbp+8h] BYREF

  v4 = *(_QWORD *)a1;
  v18 = 0;
  if ( (*(int (__fastcall **)(struct IIsapiCore *, __int64, ISAPI_CONTEXT **))(v4 + 232))(a1, 264, &v18) < 0 )
    return (unsigned int)-2147024888;
  if ( !v18 )
    return (unsigned int)-2147024888;
  v9 = ISAPI_CONTEXT::ISAPI_CONTEXT(v18, a1, a2);
  v10 = v9;
  if ( !v9 )
    return (unsigned int)-2147024888;
  *((_QWORD *)v9 + 20) = GetServerVariable;
  *((_QWORD *)v9 + 21) = WriteClient;
  *((_QWORD *)v9 + 22) = ReadClient;
  *((_QWORD *)v9 + 23) = ServerSupportFunction;
  v11 = (__int64 (__fastcall *)(ISAPI_CONTEXT *))*((_QWORD *)a3 + 23);
  Token = ISAPI_CONTEXT::QueryToken(v9);
  if ( !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    ISAPI_CONTEXT::DereferenceIsapiContext(v10);
    return v14;
  }
  ISAPI_CONTEXT::ReferenceIsapiContext(v10);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
      189,
      "ProcessIsapiRequest",
      "\r\n  Calling into HttpExtensionProc\r\n    Extension: '%S'\r\n    pECB: %p\r\n  <END>\r\n\r\n",
      *(const wchar_t **)(*((_QWORD *)v10 + 25) + 24LL),
      v10);
  v15 = v11(v10);
  RevertToSelf();
  ISAPI_CONTEXT::DereferenceIsapiContext(v10);
  if ( v15 == 3 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        211,
        "ProcessIsapiRequest",
        "\r\n  HttpExtensionProc returned HSE_STATUS_PENDING\r\n    Extension: '%S'\r\n    pECB: %p\r\n  <END>\r\n\r\n",
        *(const wchar_t **)(*((_QWORD *)v10 + 25) + 24LL),
        v10);
  }
  else
  {
    if ( (g_dwDebugFlags & 0x10000000) != 0 )
    {
      if ( ((v15 - 1) & 0xFFFFFFFC) != 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
            255,
            "ProcessIsapiRequest",
            "\r\n"
            "  HttpExtensionProc returned unknown status 0x%08x (%d)\r\n"
            "    Extension: '%S'\r\n"
            "    pECB: %p\r\n"
            "  <END>\r\n"
            "\r\n",
            v15,
            v15,
            *(const wchar_t **)(*((_QWORD *)v10 + 25) + 24LL),
            v10);
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        if ( v15 == 1 )
        {
          v16 = "HSE_STATUS_SUCCESS";
        }
        else
        {
          v16 = "HSE_STATUS_SUCCESS_AND_KEEP_CONN";
          if ( v15 != 2 )
            v16 = "HSE_STATUS_ERROR";
        }
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
          242,
          "ProcessIsapiRequest",
          "\r\n  HttpExtensionProc returned %s\r\n    Extension: '%S'\r\n    pECB: %p\r\n  <END>\r\n\r\n",
          v16,
          *(const wchar_t **)(*((_QWORD *)v10 + 25) + 24LL),
          v10);
      }
    }
    ISAPI_CONTEXT::DereferenceIsapiContext(v10);
  }
  *a4 = v15;
  return 0;
}

```

## disassembly

```asm
0x1800038ec  mov     r11, rsp
0x1800038ef  push    rbx
0x1800038f0  push    rsi
0x1800038f1  push    rdi
0x1800038f2  push    r14
0x1800038f4  sub     rsp, 58h
0x1800038f8  mov     rax, [rcx]
0x1800038fb  mov     rsi, r8
0x1800038fe  mov     rdi, rdx
0x180003901  mov     qword ptr [r11+8], 0
0x180003909  lea     r8, [r11+8]
0x18000390d  mov     edx, 108h
0x180003912  mov     r14, r9
0x180003915  mov     rbx, rcx
0x180003918  mov     rax, [rax+0E8h]
0x18000391f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003924  test    eax, eax
0x180003926  js      loc_180003BA2
0x18000392c  mov     rcx, [rsp+78h+arg_0]; this
0x180003934  test    rcx, rcx
0x180003937  jz      loc_180003BA2
0x18000393d  mov     r8, rdi; struct ISAPI_CORE_DATA *
0x180003940  mov     rdx, rbx; struct IIsapiCore *
0x180003943  call    ??0ISAPI_CONTEXT@@QEAA@PEAVIIsapiCore@@PEAUISAPI_CORE_DATA@@@Z; ISAPI_CONTEXT::ISAPI_CONTEXT(IIsapiCore *,ISAPI_CORE_DATA *)
0x180003948  mov     rbx, rax
0x18000394b  test    rax, rax
0x18000394e  jz      loc_180003BA2
0x180003954  lea     rax, ?GetServerVariable@@YAHPEAXPEAD0PEAK@Z; GetServerVariable(void *,char *,void *,ulong *)
0x18000395b  mov     rcx, rbx; this
0x18000395e  mov     [rbx+0A0h], rax
0x180003965  lea     rax, ?WriteClient@@YAHPEAX0PEAKK@Z; WriteClient(void *,void *,ulong *,ulong)
0x18000396c  mov     [rbx+0A8h], rax
0x180003973  lea     rax, ?ReadClient@@YAHPEAX0PEAK@Z; ReadClient(void *,void *,ulong *)
0x18000397a  mov     [rbx+0B0h], rax
0x180003981  lea     rax, ?ServerSupportFunction@@YAHPEAXK0PEAK1@Z; ServerSupportFunction(void *,ulong,void *,ulong *,ulong *)
0x180003988  mov     [rbx+0B8h], rax
0x18000398f  mov     rdi, [rsi+0B8h]
0x180003996  call    ?QueryToken@ISAPI_CONTEXT@@QEAAPEAXXZ; ISAPI_CONTEXT::QueryToken(void)
0x18000399b  mov     rdx, rax; Token
0x18000399e  xor     ecx, ecx; Thread
0x1800039a0  call    cs:__imp_SetThreadToken
0x1800039a6  test    eax, eax
0x1800039a8  jnz     short loc_1800039CC
0x1800039aa  call    cs:__imp_GetLastError
0x1800039b0  mov     edi, eax
0x1800039b2  test    eax, eax
0x1800039b4  jle     short loc_1800039BF
0x1800039b6  movzx   edi, ax
0x1800039b9  or      edi, 80070000h
0x1800039bf  mov     rcx, rbx; this
0x1800039c2  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x1800039c7  jmp     loc_180003BA7
0x1800039cc  mov     rcx, rbx; this
0x1800039cf  call    ?ReferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::ReferenceIsapiContext(void)
0x1800039d4  mov     eax, cs:g_dwDebugFlags
0x1800039da  lea     rsi, aProcessisapire; "ProcessIsapiRequest"
0x1800039e1  test    al, 3
0x1800039e3  setnz   cl
0x1800039e6  bt      eax, 1Ch
0x1800039ea  setb    al
0x1800039ed  test    al, cl
0x1800039ef  jz      short loc_180003A2F
0x1800039f1  mov     rcx, [rbx+0C8h]
0x1800039f8  lea     rax, aCallingIntoHtt; "\r\n  Calling into HttpExtensionProc\r"...
0x1800039ff  mov     [rsp+78h+var_48], rbx
0x180003a04  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003a0b  mov     r9, rsi
0x180003a0e  mov     r8d, 0BDh
0x180003a14  mov     rcx, [rcx+18h]
0x180003a18  mov     [rsp+78h+var_50], rcx
0x180003a1d  mov     rcx, cs:g_pDebug
0x180003a24  mov     [rsp+78h+var_58], rax
0x180003a29  call    cs:__imp_PuDbgPrint
0x180003a2f  mov     rcx, rbx
0x180003a32  mov     rax, rdi
0x180003a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a3a  mov     edi, eax
0x180003a3c  call    cs:__imp_RevertToSelf
0x180003a42  mov     rcx, rbx; this
0x180003a45  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x180003a4a  mov     ecx, edi
0x180003a4c  sub     ecx, 1
0x180003a4f  jz      short loc_180003AB8
0x180003a51  sub     ecx, 1
0x180003a54  jz      short loc_180003AB8
0x180003a56  cmp     ecx, 1
0x180003a59  jnz     short loc_180003AB8
0x180003a5b  mov     eax, cs:g_dwDebugFlags
0x180003a61  test    al, 3
0x180003a63  setnz   cl
0x180003a66  bt      eax, 1Ch
0x180003a6a  setb    al
0x180003a6d  test    al, cl
0x180003a6f  jz      loc_180003B9B
0x180003a75  mov     rax, [rbx+0C8h]
0x180003a7c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003a83  mov     rcx, cs:g_pDebug
0x180003a8a  mov     r9, rsi
0x180003a8d  mov     [rsp+78h+var_48], rbx
0x180003a92  mov     r8d, 0D3h
0x180003a98  mov     rax, [rax+18h]
0x180003a9c  mov     [rsp+78h+var_50], rax
0x180003aa1  lea     rax, aHttpextensionp; "\r\n  HttpExtensionProc returned HSE_ST"...
0x180003aa8  mov     [rsp+78h+var_58], rax
0x180003aad  call    cs:__imp_PuDbgPrint
0x180003ab3  jmp     loc_180003B9B
0x180003ab8  mov     ecx, cs:g_dwDebugFlags
0x180003abe  bt      ecx, 1Ch
0x180003ac2  jnb     loc_180003B93
0x180003ac8  lea     eax, [rdi-1]
0x180003acb  test    eax, 0FFFFFFFCh
0x180003ad0  jnz     short loc_180003B48
0x180003ad2  cmp     edi, 3
0x180003ad5  jz      short loc_180003B48
0x180003ad7  test    cl, 3
0x180003ada  jz      loc_180003B93
0x180003ae0  mov     rax, [rbx+0C8h]
0x180003ae7  mov     rcx, [rax+18h]
0x180003aeb  cmp     edi, 1
0x180003aee  jnz     short loc_180003AF9
0x180003af0  lea     rax, aHseStatusSucce_0; "HSE_STATUS_SUCCESS"
0x180003af7  jmp     short loc_180003B0E
0x180003af9  cmp     edi, 2
0x180003afc  lea     rax, aHseStatusSucce; "HSE_STATUS_SUCCESS_AND_KEEP_CONN"
0x180003b03  lea     rdx, aHseStatusError; "HSE_STATUS_ERROR"
0x180003b0a  cmovnz  rax, rdx
0x180003b0e  mov     [rsp+78h+var_40], rbx
0x180003b13  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003b1a  mov     [rsp+78h+var_48], rcx
0x180003b1f  mov     r9, rsi
0x180003b22  mov     rcx, cs:g_pDebug
0x180003b29  mov     r8d, 0F2h
0x180003b2f  mov     [rsp+78h+var_50], rax
0x180003b34  lea     rax, aHttpextensionp_0; "\r\n  HttpExtensionProc returned %s\r\n"...
0x180003b3b  mov     [rsp+78h+var_58], rax
0x180003b40  call    cs:__imp_PuDbgPrint
0x180003b46  jmp     short loc_180003B93
0x180003b48  test    cl, 3
0x180003b4b  jz      short loc_180003B93
0x180003b4d  mov     rax, [rbx+0C8h]
0x180003b54  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003b5b  mov     rcx, cs:g_pDebug
0x180003b62  mov     r9, rsi
0x180003b65  mov     [rsp+78h+var_38], rbx
0x180003b6a  mov     r8d, 0FFh
0x180003b70  mov     rax, [rax+18h]
0x180003b74  mov     [rsp+78h+var_40], rax
0x180003b79  lea     rax, aHttpextensionp_2; "\r\n  HttpExtensionProc returned unknow"...
0x180003b80  mov     dword ptr [rsp+78h+var_48], edi
0x180003b84  mov     dword ptr [rsp+78h+var_50], edi
0x180003b88  mov     [rsp+78h+var_58], rax
0x180003b8d  call    cs:__imp_PuDbgPrint
0x180003b93  mov     rcx, rbx; this
0x180003b96  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x180003b9b  mov     [r14], edi
0x180003b9e  xor     eax, eax
0x180003ba0  jmp     short loc_180003BA9
0x180003ba2  mov     edi, 80070008h
0x180003ba7  mov     eax, edi
0x180003ba9  add     rsp, 58h
0x180003bad  pop     r14
0x180003baf  pop     rdi
0x180003bb0  pop     rsi
0x180003bb1  pop     rbx
0x180003bb2  retn
```
