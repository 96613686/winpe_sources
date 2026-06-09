# SSFMapUnicodeUrlToPath(ISAPI_CONTEXT *,ushort *,ulong *)

- ea: `0x18000896c`
- end: `0x180008b34`
- name: `?SSFMapUnicodeUrlToPath@@YAJPEAVISAPI_CONTEXT@@PEAGPEAK@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x18000896c`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800089cf`
- `iisutil!PuDbgPrint` at `0x180008a2b`
- `iisutil!PuDbgPrint` at `0x180008ab7`
- `iisutil!PuDbgPrint` at `0x180008b19`
- `iisutil!PuDbgPrint` at `0x1800089cf`
- `iisutil!PuDbgPrint` at `0x180008a2b`
- `iisutil!PuDbgPrint` at `0x180008ab7`
- `iisutil!PuDbgPrint` at `0x180008b19`

## string_xrefs

- `0x1800089be`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008a24`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008a99`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008af1`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800089a5`: `\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH[%p]: Function Entry\n    URL='%S'\n  <END>\n\n`
- `0x1800089b0`: `SSFMapUnicodeUrlToPath`
- `0x180008a12`: `SSFMapUnicodeUrlToPath`
- `0x180008a8e`: `SSFMapUnicodeUrlToPath`
- `0x180008ae6`: `SSFMapUnicodeUrlToPath`
- `0x180008a06`: `\n  HSE_REQ_MA_UNICODE_URL_TO_PATH[%p]: Failed to get interface to server core\n  <END>\n\n`
- `0x180008afd`: `\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH[%p]: Parameter validation failure\n    Buffer: '%S'\n    Buffer Size Ptr: %p\n    Buffer Size: %d\n  <END>\n\n`
- `0x180008aa0`: `\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFMapUnicodeUrlToPath(struct ISAPI_CONTEXT *a1, unsigned __int16 *a2, unsigned int *a3)
{
  int v3; // r10d
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 result; // rax
  unsigned int v10; // ebx
  int v11; // eax

  v3 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      580,
      "SSFMapUnicodeUrlToPath",
      "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH[%p]: Function Entry\r\n    URL='%S'\r\n  <END>\r\n\r\n",
      a1,
      a2);
    v3 = g_dwDebugFlags;
  }
  v7 = *((_QWORD *)a1 + 24);
  if ( !v7 )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        593,
        "SSFMapUnicodeUrlToPath",
        "\r\n  HSE_REQ_MA_UNICODE_URL_TO_PATH[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 || !a3 || (v8 = *a3, !(_DWORD)v8) )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
    {
      if ( a3 )
        v11 = *a3;
      else
        v11 = 0;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        619,
        "SSFMapUnicodeUrlToPath",
        "\r\n"
        "  HSE_REQ_MAP_UNICODE_URL_TO_PATH[%p]: Parameter validation failure\r\n"
        "    Buffer: '%S'\r\n"
        "    Buffer Size Ptr: %p\r\n"
        "    Buffer Size: %d\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a2,
        a3,
        v11);
    }
    return 2147942487LL;
  }
  result = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64, unsigned int *, int))(*(_QWORD *)v7 + 32LL))(
             v7,
             a2,
             v8,
             a3,
             1);
  v10 = result;
  if ( (int)result < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        642,
        "SSFMapUnicodeUrlToPath",
        "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        result);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18000896c  mov     r11, rsp
0x18000896f  mov     [r11+8], rbx
0x180008973  mov     [r11+10h], rsi
0x180008977  push    rdi
0x180008978  sub     rsp, 50h
0x18000897c  mov     r10d, cs:g_dwDebugFlags
0x180008983  mov     rbx, r8
0x180008986  test    r10b, 3
0x18000898a  mov     rsi, rdx
0x18000898d  mov     rdi, rcx
0x180008990  setnz   r9b
0x180008994  bt      r10d, 1Ah
0x180008999  setb    al
0x18000899c  test    al, r9b
0x18000899f  jz      short loc_1800089DC
0x1800089a1  mov     [r11-28h], rdx
0x1800089a5  lea     rax, aHseReqMapUnico_6; "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH[%"...
0x1800089ac  mov     [r11-30h], rcx
0x1800089b0  lea     r9, aSsfmapunicodeu; "SSFMapUnicodeUrlToPath"
0x1800089b7  mov     rcx, cs:g_pDebug
0x1800089be  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800089c5  mov     r8d, 244h
0x1800089cb  mov     [r11-38h], rax
0x1800089cf  call    cs:__imp_PuDbgPrint
0x1800089d5  mov     r10d, cs:g_dwDebugFlags
0x1800089dc  mov     rcx, [rdi+0C0h]
0x1800089e3  test    rcx, rcx
0x1800089e6  jnz     short loc_180008A36
0x1800089e8  test    r10b, 3
0x1800089ec  setnz   cl
0x1800089ef  bt      r10d, 14h
0x1800089f4  setb    al
0x1800089f7  test    al, cl
0x1800089f9  jz      loc_180008B1F
0x1800089ff  mov     rcx, cs:g_pDebug
0x180008a06  lea     rax, aHseReqMaUnicod; "\r\n  HSE_REQ_MA_UNICODE_URL_TO_PATH[%p"...
0x180008a0d  mov     [rsp+58h+var_30], rdi
0x180008a12  lea     r9, aSsfmapunicodeu; "SSFMapUnicodeUrlToPath"
0x180008a19  mov     r8d, 251h
0x180008a1f  mov     [rsp+58h+var_38], rax
0x180008a24  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008a2b  call    cs:__imp_PuDbgPrint
0x180008a31  jmp     loc_180008B1F
0x180008a36  test    rsi, rsi
0x180008a39  jz      loc_180008AC1
0x180008a3f  test    rbx, rbx
0x180008a42  jz      short loc_180008AC1
0x180008a44  mov     r8d, [rbx]
0x180008a47  test    r8d, r8d
0x180008a4a  jz      short loc_180008AC1
0x180008a4c  mov     rax, [rcx]
0x180008a4f  mov     r9, rbx
0x180008a52  mov     rdx, rsi
0x180008a55  mov     dword ptr [rsp+58h+var_38], 1
0x180008a5d  mov     rax, [rax+20h]
0x180008a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a66  mov     ebx, eax
0x180008a68  test    eax, eax
0x180008a6a  jns     loc_180008B24
0x180008a70  mov     ecx, cs:g_dwDebugFlags
0x180008a76  test    cl, 3
0x180008a79  setnz   dl
0x180008a7c  bt      ecx, 14h
0x180008a80  setb    cl
0x180008a83  test    cl, dl
0x180008a85  jz      short loc_180008ABD
0x180008a87  mov     rcx, cs:g_pDebug
0x180008a8e  lea     r9, aSsfmapunicodeu; "SSFMapUnicodeUrlToPath"
0x180008a95  mov     dword ptr [rsp+58h+var_28], eax
0x180008a99  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008aa0  lea     rax, aHseReqMapUnico; "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH[%"...
0x180008aa7  mov     [rsp+58h+var_30], rdi
0x180008aac  mov     r8d, 282h
0x180008ab2  mov     [rsp+58h+var_38], rax
0x180008ab7  call    cs:__imp_PuDbgPrint
0x180008abd  mov     eax, ebx
0x180008abf  jmp     short loc_180008B24
0x180008ac1  test    r10b, 3
0x180008ac5  setnz   cl
0x180008ac8  bt      r10d, 14h
0x180008acd  setb    al
0x180008ad0  test    al, cl
0x180008ad2  jz      short loc_180008B1F
0x180008ad4  test    rbx, rbx
0x180008ad7  jz      short loc_180008ADD
0x180008ad9  mov     eax, [rbx]
0x180008adb  jmp     short loc_180008ADF
0x180008add  xor     eax, eax
0x180008adf  mov     rcx, cs:g_pDebug
0x180008ae6  lea     r9, aSsfmapunicodeu; "SSFMapUnicodeUrlToPath"
0x180008aed  mov     [rsp+58h+var_18], eax
0x180008af1  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008af8  mov     [rsp+58h+var_20], rbx
0x180008afd  lea     rax, aHseReqMapUnico_5; "\r\n  HSE_REQ_MAP_UNICODE_URL_TO_PATH[%"...
0x180008b04  mov     [rsp+58h+var_28], rsi
0x180008b09  mov     r8d, 26Bh
0x180008b0f  mov     [rsp+58h+var_30], rdi
0x180008b14  mov     [rsp+58h+var_38], rax
0x180008b19  call    cs:__imp_PuDbgPrint
0x180008b1f  mov     eax, 80070057h
0x180008b24  mov     rbx, [rsp+58h+arg_0]
0x180008b29  mov     rsi, [rsp+58h+arg_8]
0x180008b2e  add     rsp, 50h
0x180008b32  pop     rdi
0x180008b33  retn
```
