# SSFGetAnonymousToken(ISAPI_CONTEXT *,char *,void * *,int)

- ea: `0x1800071cc`
- end: `0x1800073cb`
- name: `?SSFGetAnonymousToken@@YAJPEAVISAPI_CONTEXT@@PEADPEAPEAXH@Z`
- size: `511`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, char *, void **, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x1800071cc`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007259`
- `iisutil!PuDbgPrint` at `0x18000732e`
- `iisutil!PuDbgPrint` at `0x1800073a7`
- `iisutil!PuDbgPrint` at `0x180007259`
- `iisutil!PuDbgPrint` at `0x18000732e`
- `iisutil!PuDbgPrint` at `0x1800073a7`

## string_xrefs

- `0x180007240`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007309`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007389`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007219`: `\n  HSE_REQ_GET_UNICODE_ANONYMOUS_TOKEN[%p]: Function Entry\n    URL: '%S'\n  <END>\n\n`
- `0x1800071e8`: `SSFGetAnonymousToken`
- `0x18000722c`: `\n  HSE_REQ_GET_ANONYMOUS_TOKEN[%p]: Function Entry\n    URL: '%s\n  <END>\n\n`
- `0x180007356`: `\n  HSE_REQ_GET_UNICODE_ANONYMOUS_TOKEN[%p]: Parameter validation failure\n    URL: '%S'\n    Token Ptr: %p\n  <END>\n\n`
- `0x180007375`: `\n  HSE_REQ_GET_ANONYMOUS_TOKEN[%p]: Parameter validation failure\n    URL: '%s'\n    Token Ptr: %p\n  <END>\n\n`
- `0x180007322`: `\n  HSE_REQ_GET_%sANONYMOUS_TOKEN[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFGetAnonymousToken(struct ISAPI_CONTEXT *a1, char *a2, void **a3, int a4)
{
  int v4; // eax
  __int64 v5; // r14
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // ebx
  const char *v13; // rax
  void *v15; // [rsp+70h] [rbp+8h] BYREF

  v4 = g_dwDebugFlags;
  v5 = *((_QWORD *)a1 + 24);
  v15 = 0;
  if ( (g_dwDebugFlags & 0x4000000) != 0 )
  {
    if ( a4 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3619,
          "SSFGetAnonymousToken",
          "\r\n  HSE_REQ_GET_UNICODE_ANONYMOUS_TOKEN[%p]: Function Entry\r\n    URL: '%S'\r\n  <END>\r\n\r\n",
          a1,
          a2);
LABEL_7:
        v4 = g_dwDebugFlags;
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3629,
        "SSFGetAnonymousToken",
        "\r\n  HSE_REQ_GET_ANONYMOUS_TOKEN[%p]: Function Entry\r\n    URL: '%s\r\n  <END>\r\n\r\n",
        a1,
        a2);
      goto LABEL_7;
    }
  }
  if ( a2 && a3 )
  {
    v10 = -1;
    if ( a4 )
    {
      do
        ++v10;
      while ( *(_WORD *)&a2[2 * v10] );
      v11 = 2 * v10 + 2;
    }
    else
    {
      do
        ++v10;
      while ( a2[v10] );
      v11 = v10 + 1;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int64, void **, int))(*(_QWORD *)v5 + 144LL))(
            v5,
            a2,
            v11,
            1,
            &v15,
            a4);
    if ( v12 >= 0 )
    {
      *a3 = v15;
    }
    else if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    {
      v13 = "UNICODE_";
      if ( !a4 )
        v13 = (const char *)word_180016DBA;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3691,
        "SSFGetAnonymousToken",
        "\r\n  HSE_REQ_GET_%sANONYMOUS_TOKEN[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        v13,
        a1,
        v12);
    }
    return (unsigned int)v12;
  }
  else
  {
    if ( a4 )
    {
      if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3650,
          "SSFGetAnonymousToken",
          "\r\n"
          "  HSE_REQ_GET_UNICODE_ANONYMOUS_TOKEN[%p]: Parameter validation failure\r\n"
          "    URL: '%S'\r\n"
          "    Token Ptr: %p\r\n"
          "  <END>\r\n"
          "\r\n",
          a1,
          a2,
          a3);
    }
    else if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3665,
        "SSFGetAnonymousToken",
        "\r\n"
        "  HSE_REQ_GET_ANONYMOUS_TOKEN[%p]: Parameter validation failure\r\n"
        "    URL: '%s'\r\n"
        "    Token Ptr: %p\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a2,
        a3);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800071cc  mov     [rsp+arg_8], rbx
0x1800071d1  mov     [rsp+arg_10], rbp
0x1800071d6  push    rsi
0x1800071d7  push    rdi
0x1800071d8  push    r13
0x1800071da  push    r14
0x1800071dc  push    r15
0x1800071de  sub     rsp, 40h
0x1800071e2  mov     eax, cs:g_dwDebugFlags
0x1800071e8  lea     r13, aSsfgetanonymou; "SSFGetAnonymousToken"
0x1800071ef  mov     r14, [rcx+0C0h]
0x1800071f6  xor     r15d, r15d
0x1800071f9  mov     [rsp+68h+arg_0], r15
0x1800071fe  mov     ebp, r9d
0x180007201  mov     rsi, r8
0x180007204  mov     rbx, rdx
0x180007207  mov     rdi, rcx
0x18000720a  bt      eax, 1Ah
0x18000720e  jnb     short loc_180007265
0x180007210  test    r9d, r9d
0x180007213  jz      short loc_180007228
0x180007215  test    al, 3
0x180007217  jz      short loc_180007265
0x180007219  lea     rax, aHseReqGetUnico_0; "\r\n  HSE_REQ_GET_UNICODE_ANONYMOUS_TOK"...
0x180007220  mov     r8d, 0E23h
0x180007226  jmp     short loc_180007239
0x180007228  test    al, 3
0x18000722a  jz      short loc_180007265
0x18000722c  lea     rax, aHseReqGetAnony; "\r\n  HSE_REQ_GET_ANONYMOUS_TOKEN[%p]: "...
0x180007233  mov     r8d, 0E2Dh
0x180007239  mov     rcx, cs:g_pDebug
0x180007240  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007247  mov     [rsp+68h+var_38], rbx
0x18000724c  mov     r9, r13
0x18000724f  mov     [rsp+68h+var_40], rdi
0x180007254  mov     [rsp+68h+var_48], rax
0x180007259  call    cs:__imp_PuDbgPrint
0x18000725f  mov     eax, cs:g_dwDebugFlags
0x180007265  test    rbx, rbx
0x180007268  jz      loc_180007342
0x18000726e  test    rsi, rsi
0x180007271  jz      loc_180007342
0x180007277  mov     rax, [r14]
0x18000727a  mov     r10, [rax+90h]
0x180007281  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007285  test    ebp, ebp
0x180007287  jz      short loc_18000729D
0x180007289  inc     rax
0x18000728c  cmp     [rbx+rax*2], r15w
0x180007291  jnz     short loc_180007289
0x180007293  lea     r8, ds:2[rax*2]
0x18000729b  jmp     short loc_1800072AA
0x18000729d  inc     rax
0x1800072a0  cmp     [rbx+rax], r15b
0x1800072a4  jnz     short loc_18000729D
0x1800072a6  lea     r8, [rax+1]
0x1800072aa  lea     rax, [rsp+68h+arg_0]
0x1800072af  mov     dword ptr [rsp+68h+var_40], ebp
0x1800072b3  mov     [rsp+68h+var_48], rax
0x1800072b8  mov     r9d, 1
0x1800072be  mov     rax, r10
0x1800072c1  mov     rdx, rbx
0x1800072c4  mov     rcx, r14
0x1800072c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072cc  mov     ebx, eax
0x1800072ce  test    eax, eax
0x1800072d0  jns     short loc_180007338
0x1800072d2  mov     ecx, cs:g_dwDebugFlags
0x1800072d8  test    cl, 3
0x1800072db  setnz   dl
0x1800072de  bt      ecx, 14h
0x1800072e2  setb    cl
0x1800072e5  test    cl, dl
0x1800072e7  jz      short loc_180007334
0x1800072e9  mov     dword ptr [rsp+68h+var_30], ebx
0x1800072ed  lea     rcx, word_180016DBA
0x1800072f4  test    ebp, ebp
0x1800072f6  mov     [rsp+68h+var_38], rdi
0x1800072fb  lea     rax, aUnicode; "UNICODE_"
0x180007302  mov     r9, r13
0x180007305  cmovz   rax, rcx
0x180007309  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007310  mov     rcx, cs:g_pDebug
0x180007317  mov     r8d, 0E6Bh
0x18000731d  mov     [rsp+68h+var_40], rax
0x180007322  lea     rax, aHseReqGetSanon; "\r\n  HSE_REQ_GET_%sANONYMOUS_TOKEN[%p]"...
0x180007329  mov     [rsp+68h+var_48], rax
0x18000732e  call    cs:__imp_PuDbgPrint
0x180007334  mov     eax, ebx
0x180007336  jmp     short loc_1800073B2
0x180007338  mov     rax, [rsp+68h+arg_0]
0x18000733d  mov     [rsi], rax
0x180007340  jmp     short loc_180007334
0x180007342  test    ebp, ebp
0x180007344  jz      short loc_180007365
0x180007346  test    al, 3
0x180007348  setnz   cl
0x18000734b  bt      eax, 14h
0x18000734f  setb    al
0x180007352  test    al, cl
0x180007354  jz      short loc_1800073AD
0x180007356  lea     rax, aHseReqGetUnico_1; "\r\n  HSE_REQ_GET_UNICODE_ANONYMOUS_TOK"...
0x18000735d  mov     r8d, 0E42h
0x180007363  jmp     short loc_180007382
0x180007365  test    al, 3
0x180007367  setnz   cl
0x18000736a  bt      eax, 14h
0x18000736e  setb    al
0x180007371  test    al, cl
0x180007373  jz      short loc_1800073AD
0x180007375  lea     rax, aHseReqGetAnony_1; "\r\n  HSE_REQ_GET_ANONYMOUS_TOKEN[%p]: "...
0x18000737c  mov     r8d, 0E51h
0x180007382  mov     rcx, cs:g_pDebug
0x180007389  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007390  mov     [rsp+68h+var_30], rsi
0x180007395  mov     r9, r13
0x180007398  mov     [rsp+68h+var_38], rbx
0x18000739d  mov     [rsp+68h+var_40], rdi
0x1800073a2  mov     [rsp+68h+var_48], rax
0x1800073a7  call    cs:__imp_PuDbgPrint
0x1800073ad  mov     eax, 80070057h
0x1800073b2  lea     r11, [rsp+68h+var_28]
0x1800073b7  mov     rbx, [r11+38h]
0x1800073bb  mov     rbp, [r11+40h]
0x1800073bf  mov     rsp, r11
0x1800073c2  pop     r15
0x1800073c4  pop     r14
0x1800073c6  pop     r13
0x1800073c8  pop     rdi
0x1800073c9  pop     rsi
0x1800073ca  retn
```
