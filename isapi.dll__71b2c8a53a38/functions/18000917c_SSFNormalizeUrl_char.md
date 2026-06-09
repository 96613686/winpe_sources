# SSFNormalizeUrl(char *)

- ea: `0x18000917c`
- end: `0x180009283`
- name: `?SSFNormalizeUrl@@YAJPEAD@Z`
- size: `263`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x18000917c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800091cb`
- `iisutil!PuDbgPrint` at `0x180009217`
- `iisutil!PuDbgPrint` at `0x180009275`
- `iisutil!PuDbgPrint` at `0x1800091cb`
- `iisutil!PuDbgPrint` at `0x180009217`
- `iisutil!PuDbgPrint` at `0x180009275`
- `iisutil!NormalizeUrl` at `0x180009227`
- `iisutil!NormalizeUrl` at `0x180009227`

## string_xrefs

- `0x1800091c4`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009210`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000925c`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFNormalizeUrl(char *a1)
{
  int v1; // r8d
  int v4; // eax
  unsigned int v5; // ebx

  v1 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      3810,
      "SSFNormalizeUrl",
      "\r\n  HSE_REQ_NORMALIZE_URL[]: Function Entry\r\n    URL: '%s'\r\n  <END>\r\n\r\n",
      a1);
    v1 = g_dwDebugFlags;
  }
  if ( a1 )
  {
    v4 = NormalizeUrl(a1);
    v5 = v4;
    if ( v4 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3842,
        "SSFNormalizeUrl",
        "\r\n  HSE_REQ_NORMALIZE_URL[]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        v4);
    return v5;
  }
  else
  {
    if ( (v1 & 3) != 0 && (v1 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3825,
        "SSFNormalizeUrl",
        "\r\n  HSE_REQ_NORMALIZE_URL[]: Parameter validation failure\r\n    URL: NULL\r\n  <END>\r\n\r\n");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000917c  push    rbx
0x18000917e  sub     rsp, 30h
0x180009182  mov     r8d, cs:g_dwDebugFlags
0x180009189  mov     rbx, rcx
0x18000918c  test    r8b, 3
0x180009190  setnz   dl
0x180009193  bt      r8d, 1Ah
0x180009198  setb    al
0x18000919b  test    al, dl
0x18000919d  jz      short loc_1800091D8
0x18000919f  mov     [rsp+38h+var_10], rcx
0x1800091a4  lea     rax, aHseReqNormaliz_0; "\r\n  HSE_REQ_NORMALIZE_URL[]: Function"...
0x1800091ab  mov     rcx, cs:g_pDebug
0x1800091b2  lea     r9, aSsfnormalizeur; "SSFNormalizeUrl"
0x1800091b9  mov     r8d, 0EE2h
0x1800091bf  mov     [rsp+38h+var_18], rax
0x1800091c4  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800091cb  call    cs:__imp_PuDbgPrint
0x1800091d1  mov     r8d, cs:g_dwDebugFlags
0x1800091d8  test    rbx, rbx
0x1800091db  jnz     short loc_180009224
0x1800091dd  test    r8b, 3
0x1800091e1  setnz   cl
0x1800091e4  bt      r8d, 14h
0x1800091e9  setb    al
0x1800091ec  test    al, cl
0x1800091ee  jz      short loc_18000921D
0x1800091f0  mov     rcx, cs:g_pDebug
0x1800091f7  lea     rax, aHseReqNormaliz_1; "\r\n  HSE_REQ_NORMALIZE_URL[]: Paramete"...
0x1800091fe  lea     r9, aSsfnormalizeur; "SSFNormalizeUrl"
0x180009205  mov     [rsp+38h+var_18], rax
0x18000920a  mov     r8d, 0EF1h
0x180009210  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009217  call    cs:__imp_PuDbgPrint
0x18000921d  mov     eax, 80070057h
0x180009222  jmp     short loc_18000927D
0x180009224  mov     rcx, rbx
0x180009227  call    cs:__imp_?NormalizeUrl@@YAJPEAD@Z; NormalizeUrl(char *)
0x18000922d  mov     ebx, eax
0x18000922f  test    eax, eax
0x180009231  jns     short loc_18000927B
0x180009233  mov     ecx, cs:g_dwDebugFlags
0x180009239  test    cl, 3
0x18000923c  setnz   dl
0x18000923f  bt      ecx, 14h
0x180009243  setb    cl
0x180009246  test    cl, dl
0x180009248  jz      short loc_18000927B
0x18000924a  mov     rcx, cs:g_pDebug
0x180009251  lea     r9, aSsfnormalizeur; "SSFNormalizeUrl"
0x180009258  mov     dword ptr [rsp+38h+var_10], eax
0x18000925c  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009263  lea     rax, aHseReqNormaliz; "\r\n  HSE_REQ_NORMALIZE_URL[]: Failed\r"...
0x18000926a  mov     r8d, 0F02h
0x180009270  mov     [rsp+38h+var_18], rax
0x180009275  call    cs:__imp_PuDbgPrint
0x18000927b  mov     eax, ebx
0x18000927d  add     rsp, 30h
0x180009281  pop     rbx
0x180009282  retn
```
