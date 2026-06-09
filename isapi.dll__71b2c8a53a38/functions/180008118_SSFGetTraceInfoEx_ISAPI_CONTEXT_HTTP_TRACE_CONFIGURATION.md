# SSFGetTraceInfoEx(ISAPI_CONTEXT *,HTTP_TRACE_CONFIGURATION *)

- ea: `0x180008118`
- end: `0x1800082a9`
- name: `?SSFGetTraceInfoEx@@YAJPEAVISAPI_CONTEXT@@PEAUHTTP_TRACE_CONFIGURATION@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct HTTP_TRACE_CONFIGURATION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180006044`
- `0x180008118`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800081c3`
- `iisutil!PuDbgPrint` at `0x180008211`
- `iisutil!PuDbgPrint` at `0x180008280`
- `iisutil!PuDbgPrint` at `0x1800081c3`
- `iisutil!PuDbgPrint` at `0x180008211`
- `iisutil!PuDbgPrint` at `0x180008280`

## string_xrefs

- `0x1800081bc`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000820a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008262`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFGetTraceInfoEx(struct ISAPI_CONTEXT *a1, struct HTTP_TRACE_CONFIGURATION *a2)
{
  int v2; // ebx
  __int64 v4; // r14
  LPCGUID pProviderGuid; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v11[39]; // [rsp+48h] [rbp-50h] BYREF

  v2 = g_dwDebugFlags;
  v4 = *((_QWORD *)a1 + 24);
  if ( (g_dwDebugFlags & 0x4000000) != 0 )
  {
    pProviderGuid = a2->pProviderGuid;
    v10 = 39;
    memset(v11, 0, sizeof(v11));
    if ( (int)ConvertCLSIDToString(pProviderGuid, v11, &v10) < 0 )
      strcpy(v11, "?");
    if ( (v2 & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4682,
        "SSFGetTraceInfoEx",
        "\r\n  HSE_REQ_GET_TRACE_INFO_EX[%p]: Function Entry\r\n   GUID - %s\r\n  <END>\r\n\r\n",
        a1,
        v11);
      v2 = g_dwDebugFlags;
    }
  }
  if ( a2 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, struct HTTP_TRACE_CONFIGURATION *))(*(_QWORD *)v4 + 216LL))(v4, a2);
    v9 = v8;
    if ( v8 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4715,
        "SSFGetTraceInfoEx",
        "\r\n  HSE_REQ_GET_TRACE_INFO_EX[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        v8);
    return v9;
  }
  else
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4694,
        "SSFGetTraceInfoEx",
        "\r\n  HSE_REQ_GET_TRACE_INFO_EX[%p]: Failed\r\n    NULL parameter passed to the call\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180008118  mov     r11, rsp
0x18000811b  mov     [r11+18h], rbx
0x18000811f  push    rsi
0x180008120  push    rdi
0x180008121  push    r14
0x180008123  sub     rsp, 80h
0x18000812a  mov     rax, cs:__security_cookie
0x180008131  xor     rax, rsp
0x180008134  mov     [rsp+98h+var_28], rax
0x180008139  mov     ebx, cs:g_dwDebugFlags
0x18000813f  mov     rsi, rdx
0x180008142  mov     r14, [rcx+0C0h]
0x180008149  mov     rdi, rcx
0x18000814c  bt      ebx, 1Ah
0x180008150  jnb     short loc_1800081CF
0x180008152  mov     rcx, [rsi]
0x180008155  lea     r8, [r11-58h]
0x180008159  xorps   xmm0, xmm0
0x18000815c  mov     [rsp+98h+var_58], 27h ; '''
0x180008164  xor     eax, eax
0x180008166  lea     rdx, [r11-50h]
0x18000816a  movups  [rsp+98h+var_50], xmm0
0x18000816f  movups  xmmword ptr [rsp+98h+var_40], xmm0
0x180008174  mov     [r11-31h], rax
0x180008178  call    ConvertCLSIDToString
0x18000817d  test    eax, eax
0x18000817f  jns     short loc_180008188
0x180008181  mov     word ptr [rsp+98h+var_50], 3Fh ; '?'
0x180008188  test    bl, 3
0x18000818b  jz      short loc_1800081CF
0x18000818d  mov     rcx, cs:g_pDebug
0x180008194  lea     rax, [rsp+98h+var_50]
0x180008199  mov     [rsp+98h+var_68], rax
0x18000819e  lea     r9, aSsfgettraceinf; "SSFGetTraceInfoEx"
0x1800081a5  lea     rax, aHseReqGetTrace_5; "\r\n  HSE_REQ_GET_TRACE_INFO_EX[%p]: Fu"...
0x1800081ac  mov     [rsp+98h+var_70], rdi
0x1800081b1  mov     r8d, 124Ah
0x1800081b7  mov     [rsp+98h+var_78], rax
0x1800081bc  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800081c3  call    cs:__imp_PuDbgPrint
0x1800081c9  mov     ebx, cs:g_dwDebugFlags
0x1800081cf  test    rsi, rsi
0x1800081d2  jnz     short loc_18000821E
0x1800081d4  test    bl, 3
0x1800081d7  setnz   cl
0x1800081da  bt      ebx, 14h
0x1800081de  setb    al
0x1800081e1  test    al, cl
0x1800081e3  jz      short loc_180008217
0x1800081e5  mov     rcx, cs:g_pDebug
0x1800081ec  lea     rax, aHseReqGetTrace_6; "\r\n  HSE_REQ_GET_TRACE_INFO_EX[%p]: Fa"...
0x1800081f3  mov     [rsp+98h+var_70], rdi
0x1800081f8  lea     r9, aSsfgettraceinf; "SSFGetTraceInfoEx"
0x1800081ff  mov     r8d, 1256h
0x180008205  mov     [rsp+98h+var_78], rax
0x18000820a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008211  call    cs:__imp_PuDbgPrint
0x180008217  mov     eax, 80070057h
0x18000821c  jmp     short loc_180008288
0x18000821e  mov     rax, [r14]
0x180008221  mov     rdx, rsi
0x180008224  mov     rcx, r14
0x180008227  mov     rax, [rax+0D8h]
0x18000822e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008233  mov     ebx, eax
0x180008235  test    eax, eax
0x180008237  jns     short loc_180008286
0x180008239  mov     ecx, cs:g_dwDebugFlags
0x18000823f  test    cl, 3
0x180008242  setnz   dl
0x180008245  bt      ecx, 14h
0x180008249  setb    cl
0x18000824c  test    cl, dl
0x18000824e  jz      short loc_180008286
0x180008250  mov     rcx, cs:g_pDebug
0x180008257  lea     r9, aSsfgettraceinf; "SSFGetTraceInfoEx"
0x18000825e  mov     dword ptr [rsp+98h+var_68], eax
0x180008262  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008269  lea     rax, aHseReqGetTrace; "\r\n  HSE_REQ_GET_TRACE_INFO_EX[%p]: Fa"...
0x180008270  mov     [rsp+98h+var_70], rdi
0x180008275  mov     r8d, 126Bh
0x18000827b  mov     [rsp+98h+var_78], rax
0x180008280  call    cs:__imp_PuDbgPrint
0x180008286  mov     eax, ebx
0x180008288  mov     rcx, [rsp+98h+var_28]
0x18000828d  xor     rcx, rsp; StackCookie
0x180008290  call    __security_check_cookie
0x180008295  mov     rbx, [rsp+98h+arg_10]
0x18000829d  add     rsp, 80h
0x1800082a4  pop     r14
0x1800082a6  pop     rdi
0x1800082a7  pop     rsi
0x1800082a8  retn
```
