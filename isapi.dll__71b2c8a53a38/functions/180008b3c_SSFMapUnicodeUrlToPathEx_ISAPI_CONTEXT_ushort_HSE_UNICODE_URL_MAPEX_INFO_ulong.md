# SSFMapUnicodeUrlToPathEx(ISAPI_CONTEXT *,ushort *,_HSE_UNICODE_URL_MAPEX_INFO *,ulong *)

- ea: `0x180008b3c`
- end: `0x180008d67`
- name: `?SSFMapUnicodeUrlToPathEx@@YAJPEAVISAPI_CONTEXT@@PEAGPEAU_HSE_UNICODE_URL_MAPEX_INFO@@PEAK@Z`
- size: `555`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, const char *, struct _HSE_UNICODE_URL_MAPEX_INFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180008b3c`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008baf`
- `iisutil!PuDbgPrint` at `0x180008c0b`
- `iisutil!PuDbgPrint` at `0x180008cf4`
- `iisutil!PuDbgPrint` at `0x180008d47`
- `iisutil!PuDbgPrint` at `0x180008baf`
- `iisutil!PuDbgPrint` at `0x180008c0b`
- `iisutil!PuDbgPrint` at `0x180008cf4`
- `iisutil!PuDbgPrint` at `0x180008d47`

## string_xrefs

- `0x180008b9d`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008c04`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008cd6`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008d30`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008b83`: `\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH_EX[%p]: Function Entry\n    URL='%S'\n  <END>\n\n`
- `0x180008b8f`: `SSFMapUnicodeUrlToPathEx`
- `0x180008bf2`: `SSFMapUnicodeUrlToPathEx`
- `0x180008ccb`: `SSFMapUnicodeUrlToPathEx`
- `0x180008d24`: `SSFMapUnicodeUrlToPathEx`
- `0x180008be6`: `\n  HSE_REQ_MA_UNICODE_URL_TO_PATH_EX[%p]: Failed to get interface to server core\n  <END>\n\n`
- `0x180008d18`: `\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH_EX[%p]: Parameter validation failure\n    URL: '%s'\n    pHseMapInfo: %p\n  <END>\n\n`
- `0x180008cdd`: `\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH_EX[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFMapUnicodeUrlToPathEx(
        struct ISAPI_CONTEXT *a1,
        const char *a2,
        struct _HSE_UNICODE_URL_MAPEX_INFO *a3,
        unsigned int *a4)
{
  int v4; // r11d
  __int64 v9; // rcx
  int *v10; // r11
  __int64 v11; // r8
  __int64 result; // rax
  unsigned int v13; // edi
  int v14; // [rsp+80h] [rbp+8h] BYREF

  v4 = g_dwDebugFlags;
  v14 = 0;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      694,
      "SSFMapUnicodeUrlToPathEx",
      "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH_EX[%p]: Function Entry\r\n    URL='%S'\r\n  <END>\r\n\r\n",
      a1,
      (const wchar_t *)a2);
    v4 = g_dwDebugFlags;
  }
  v9 = *((_QWORD *)a1 + 24);
  if ( !v9 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        707,
        "SSFMapUnicodeUrlToPathEx",
        "\r\n  HSE_REQ_MA_UNICODE_URL_TO_PATH_EX[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 || !a3 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        730,
        "SSFMapUnicodeUrlToPathEx",
        "\r\n"
        "  HSE_REQ_MAP_UNICODE_URL_TO_PATH_EX[%p]: Parameter validation failure\r\n"
        "    URL: '%s'\r\n"
        "    pHseMapInfo: %p\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a2,
        a3);
    return 2147942487LL;
  }
  v14 = 520;
  v10 = &v14;
  if ( a4 )
    v10 = (int *)a4;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)&a2[2 * v11] );
  result = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, struct _HSE_UNICODE_URL_MAPEX_INFO *, int, int *, DWORD *, DWORD *, DWORD *, int))(*(_QWORD *)v9 + 40LL))(
             v9,
             a2,
             (unsigned int)(2 * v11 + 2),
             a3,
             520,
             v10,
             &a3->cchMatchingPath,
             &a3->cchMatchingURL,
             &a3->dwFlags,
             1);
  v13 = result;
  if ( (int)result < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        765,
        "SSFMapUnicodeUrlToPathEx",
        "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH_EX[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        result);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180008b3c  mov     rax, rsp
0x180008b3f  mov     [rax+10h], rbx
0x180008b43  mov     [rax+18h], rbp
0x180008b47  push    rsi
0x180008b48  push    rdi
0x180008b49  push    r14
0x180008b4b  sub     rsp, 60h
0x180008b4f  mov     r11d, cs:g_dwDebugFlags
0x180008b56  xor     r14d, r14d
0x180008b59  test    r11b, 3
0x180008b5d  mov     [rax+8], r14d
0x180008b61  mov     rbp, r9
0x180008b64  mov     rsi, r8
0x180008b67  setnz   r10b
0x180008b6b  mov     rdi, rdx
0x180008b6e  bt      r11d, 1Ah
0x180008b73  mov     rbx, rcx
0x180008b76  setb    al
0x180008b79  test    al, r10b
0x180008b7c  jz      short loc_180008BBC
0x180008b7e  mov     [rsp+78h+var_48], rdx
0x180008b83  lea     rax, aHseReqMapUnico_0; "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH_E"...
0x180008b8a  mov     [rsp+78h+var_50], rcx
0x180008b8f  lea     r9, aSsfmapunicodeu_0; "SSFMapUnicodeUrlToPathEx"
0x180008b96  mov     rcx, cs:g_pDebug
0x180008b9d  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008ba4  mov     r8d, 2B6h
0x180008baa  mov     [rsp+78h+var_58], rax
0x180008baf  call    cs:__imp_PuDbgPrint
0x180008bb5  mov     r11d, cs:g_dwDebugFlags
0x180008bbc  mov     rcx, [rbx+0C0h]
0x180008bc3  test    rcx, rcx
0x180008bc6  jnz     short loc_180008C16
0x180008bc8  test    r11b, 3
0x180008bcc  setnz   cl
0x180008bcf  bt      r11d, 14h
0x180008bd4  setb    al
0x180008bd7  test    al, cl
0x180008bd9  jz      loc_180008D4D
0x180008bdf  mov     rcx, cs:g_pDebug
0x180008be6  lea     rax, aHseReqMaUnicod_0; "\r\n  HSE_REQ_MA_UNICODE_URL_TO_PATH_EX"...
0x180008bed  mov     [rsp+78h+var_50], rbx
0x180008bf2  lea     r9, aSsfmapunicodeu_0; "SSFMapUnicodeUrlToPathEx"
0x180008bf9  mov     r8d, 2C3h
0x180008bff  mov     [rsp+78h+var_58], rax
0x180008c04  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008c0b  call    cs:__imp_PuDbgPrint
0x180008c11  jmp     loc_180008D4D
0x180008c16  test    rdi, rdi
0x180008c19  jz      loc_180008CFE
0x180008c1f  test    rsi, rsi
0x180008c22  jz      loc_180008CFE
0x180008c28  test    rbp, rbp
0x180008c2b  mov     [rsp+78h+arg_0], 208h
0x180008c36  mov     rax, [rcx]
0x180008c39  lea     r11, [rsp+78h+arg_0]
0x180008c41  cmovnz  r11, rbp
0x180008c45  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008c49  inc     r8
0x180008c4c  cmp     [rdi+r8*2], r14w
0x180008c51  jnz     short loc_180008C49
0x180008c53  mov     rax, [rax+28h]
0x180008c57  lea     rdx, [rsi+208h]
0x180008c5e  mov     [rsp+78h+var_30], 1
0x180008c66  lea     r9, [rsi+210h]
0x180008c6d  mov     [rsp+78h+var_38], rdx
0x180008c72  lea     r10, [rsi+20Ch]
0x180008c79  mov     [rsp+78h+var_40], r9
0x180008c7e  lea     r8d, ds:2[r8*2]
0x180008c86  mov     [rsp+78h+var_48], r10
0x180008c8b  mov     r9, rsi
0x180008c8e  mov     [rsp+78h+var_50], r11
0x180008c93  mov     rdx, rdi
0x180008c96  mov     dword ptr [rsp+78h+var_58], 208h
0x180008c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ca3  mov     edi, eax
0x180008ca5  test    eax, eax
0x180008ca7  jns     loc_180008D52
0x180008cad  mov     ecx, cs:g_dwDebugFlags
0x180008cb3  test    cl, 3
0x180008cb6  setnz   dl
0x180008cb9  bt      ecx, 14h
0x180008cbd  setb    cl
0x180008cc0  test    cl, dl
0x180008cc2  jz      short loc_180008CFA
0x180008cc4  mov     rcx, cs:g_pDebug
0x180008ccb  lea     r9, aSsfmapunicodeu_0; "SSFMapUnicodeUrlToPathEx"
0x180008cd2  mov     dword ptr [rsp+78h+var_48], eax
0x180008cd6  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008cdd  lea     rax, aHseReqMapUnico_3; "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH_E"...
0x180008ce4  mov     [rsp+78h+var_50], rbx
0x180008ce9  mov     r8d, 2FDh
0x180008cef  mov     [rsp+78h+var_58], rax
0x180008cf4  call    cs:__imp_PuDbgPrint
0x180008cfa  mov     eax, edi
0x180008cfc  jmp     short loc_180008D52
0x180008cfe  test    r11b, 3
0x180008d02  setnz   cl
0x180008d05  bt      r11d, 14h
0x180008d0a  setb    al
0x180008d0d  test    al, cl
0x180008d0f  jz      short loc_180008D4D
0x180008d11  mov     rcx, cs:g_pDebug
0x180008d18  lea     rax, aHseReqMapUnico_2; "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH_E"...
0x180008d1f  mov     [rsp+78h+var_40], rsi
0x180008d24  lea     r9, aSsfmapunicodeu_0; "SSFMapUnicodeUrlToPathEx"
0x180008d2b  mov     [rsp+78h+var_48], rdi
0x180008d30  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008d37  mov     [rsp+78h+var_50], rbx
0x180008d3c  mov     r8d, 2DAh
0x180008d42  mov     [rsp+78h+var_58], rax
0x180008d47  call    cs:__imp_PuDbgPrint
0x180008d4d  mov     eax, 80070057h
0x180008d52  lea     r11, [rsp+78h+var_18]
0x180008d57  mov     rbx, [r11+28h]
0x180008d5b  mov     rbp, [r11+30h]
0x180008d5f  mov     rsp, r11
0x180008d62  pop     r14
0x180008d64  pop     rdi
0x180008d65  pop     rsi
0x180008d66  retn
```
