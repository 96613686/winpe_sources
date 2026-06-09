# SSFGetVirtualPathToken(ISAPI_CONTEXT *,char *,void * *,int)

- ea: `0x1800082b0`
- end: `0x18000849d`
- name: `?SSFGetVirtualPathToken@@YAJPEAVISAPI_CONTEXT@@PEADPEAPEAXH@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, char *, void **, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x1800082b0`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000833d`
- `iisutil!PuDbgPrint` at `0x180008412`
- `iisutil!PuDbgPrint` at `0x180008479`
- `iisutil!PuDbgPrint` at `0x18000833d`
- `iisutil!PuDbgPrint` at `0x180008412`
- `iisutil!PuDbgPrint` at `0x180008479`

## string_xrefs

- `0x180008324`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800083ed`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000845b`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800082fd`: `\n  HSE_REQ_GET_UNICODE_VIRTUAL_PATH_TOKEN[%p]: Function Entry\n    URL: '%S'\n  <END>\n\n`
- `0x1800082cc`: `SSFGetVirtualPathToken`
- `0x180008310`: `\n  HSE_REQ_GET_VIRTUAL_PATH_TOKEN[%p]: Function Entry\n    URL: '%s'\n  <END>\n\n`
- `0x180008434`: `\n  HSE_REQ_GET_UNICODE_VIRTUAL_PATH_TOKEN[%p]: Parameter validation failure\n    URL: '%S'\n    Token Ptr: %p\n  <END>\n\n`
- `0x180008447`: `\n  HSE_REQ_GET_VIRTUAL_PATH_TOKEN[%p]: Parameter validation failure\n    URL: '%s'\n    Token Ptr: %p\n  <END>\n\n`
- `0x180008406`: `\n  HSE_REQ_GET_%sVIRTUAL_PATH_TOKEN[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFGetVirtualPathToken(struct ISAPI_CONTEXT *a1, char *a2, void **a3, int a4)
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
          3509,
          "SSFGetVirtualPathToken",
          "\r\n  HSE_REQ_GET_UNICODE_VIRTUAL_PATH_TOKEN[%p]: Function Entry\r\n    URL: '%S'\r\n  <END>\r\n\r\n",
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
        3519,
        "SSFGetVirtualPathToken",
        "\r\n  HSE_REQ_GET_VIRTUAL_PATH_TOKEN[%p]: Function Entry\r\n    URL: '%s'\r\n  <END>\r\n\r\n",
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
            2,
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
        3582,
        "SSFGetVirtualPathToken",
        "\r\n  HSE_REQ_GET_%sVIRTUAL_PATH_TOKEN[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        v13,
        a1,
        v12);
    }
    return (unsigned int)v12;
  }
  else
  {
    if ( (v4 & 0x100000) != 0 )
    {
      if ( a4 )
      {
        if ( (v4 & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
            3541,
            "SSFGetVirtualPathToken",
            "\r\n"
            "  HSE_REQ_GET_UNICODE_VIRTUAL_PATH_TOKEN[%p]: Parameter validation failure\r\n"
            "    URL: '%S'\r\n"
            "    Token Ptr: %p\r\n"
            "  <END>\r\n"
            "\r\n",
            a1,
            a2,
            a3);
      }
      else if ( (v4 & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3555,
          "SSFGetVirtualPathToken",
          "\r\n"
          "  HSE_REQ_GET_VIRTUAL_PATH_TOKEN[%p]: Parameter validation failure\r\n"
          "    URL: '%s'\r\n"
          "    Token Ptr: %p\r\n"
          "  <END>\r\n"
          "\r\n",
          a1,
          a2,
          a3);
      }
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800082b0  mov     [rsp+arg_8], rbx
0x1800082b5  mov     [rsp+arg_10], rbp
0x1800082ba  push    rsi
0x1800082bb  push    rdi
0x1800082bc  push    r13
0x1800082be  push    r14
0x1800082c0  push    r15
0x1800082c2  sub     rsp, 40h
0x1800082c6  mov     eax, cs:g_dwDebugFlags
0x1800082cc  lea     r13, aSsfgetvirtualp; "SSFGetVirtualPathToken"
0x1800082d3  mov     r14, [rcx+0C0h]
0x1800082da  xor     r15d, r15d
0x1800082dd  mov     [rsp+68h+arg_0], r15
0x1800082e2  mov     ebp, r9d
0x1800082e5  mov     rsi, r8
0x1800082e8  mov     rbx, rdx
0x1800082eb  mov     rdi, rcx
0x1800082ee  bt      eax, 1Ah
0x1800082f2  jnb     short loc_180008349
0x1800082f4  test    r9d, r9d
0x1800082f7  jz      short loc_18000830C
0x1800082f9  test    al, 3
0x1800082fb  jz      short loc_180008349
0x1800082fd  lea     rax, aHseReqGetUnico_2; "\r\n  HSE_REQ_GET_UNICODE_VIRTUAL_PATH_"...
0x180008304  mov     r8d, 0DB5h
0x18000830a  jmp     short loc_18000831D
0x18000830c  test    al, 3
0x18000830e  jz      short loc_180008349
0x180008310  lea     rax, aHseReqGetVirtu; "\r\n  HSE_REQ_GET_VIRTUAL_PATH_TOKEN[%p"...
0x180008317  mov     r8d, 0DBFh
0x18000831d  mov     rcx, cs:g_pDebug
0x180008324  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000832b  mov     [rsp+68h+var_38], rbx
0x180008330  mov     r9, r13
0x180008333  mov     [rsp+68h+var_40], rdi
0x180008338  mov     [rsp+68h+var_48], rax
0x18000833d  call    cs:__imp_PuDbgPrint
0x180008343  mov     eax, cs:g_dwDebugFlags
0x180008349  test    rbx, rbx
0x18000834c  jz      loc_180008426
0x180008352  test    rsi, rsi
0x180008355  jz      loc_180008426
0x18000835b  mov     rax, [r14]
0x18000835e  mov     r10, [rax+90h]
0x180008365  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008369  test    ebp, ebp
0x18000836b  jz      short loc_180008381
0x18000836d  inc     rax
0x180008370  cmp     [rbx+rax*2], r15w
0x180008375  jnz     short loc_18000836D
0x180008377  lea     r8, ds:2[rax*2]
0x18000837f  jmp     short loc_18000838E
0x180008381  inc     rax
0x180008384  cmp     [rbx+rax], r15b
0x180008388  jnz     short loc_180008381
0x18000838a  lea     r8, [rax+1]
0x18000838e  lea     rax, [rsp+68h+arg_0]
0x180008393  mov     dword ptr [rsp+68h+var_40], ebp
0x180008397  mov     [rsp+68h+var_48], rax
0x18000839c  mov     r9d, 2
0x1800083a2  mov     rax, r10
0x1800083a5  mov     rdx, rbx
0x1800083a8  mov     rcx, r14
0x1800083ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083b0  mov     ebx, eax
0x1800083b2  test    eax, eax
0x1800083b4  jns     short loc_18000841C
0x1800083b6  mov     ecx, cs:g_dwDebugFlags
0x1800083bc  test    cl, 3
0x1800083bf  setnz   dl
0x1800083c2  bt      ecx, 14h
0x1800083c6  setb    cl
0x1800083c9  test    cl, dl
0x1800083cb  jz      short loc_180008418
0x1800083cd  mov     dword ptr [rsp+68h+var_30], ebx
0x1800083d1  lea     rcx, word_180016DBA
0x1800083d8  test    ebp, ebp
0x1800083da  mov     [rsp+68h+var_38], rdi
0x1800083df  lea     rax, aUnicode; "UNICODE_"
0x1800083e6  mov     r9, r13
0x1800083e9  cmovz   rax, rcx
0x1800083ed  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800083f4  mov     rcx, cs:g_pDebug
0x1800083fb  mov     r8d, 0DFEh
0x180008401  mov     [rsp+68h+var_40], rax
0x180008406  lea     rax, aHseReqGetSvirt; "\r\n  HSE_REQ_GET_%sVIRTUAL_PATH_TOKEN["...
0x18000840d  mov     [rsp+68h+var_48], rax
0x180008412  call    cs:__imp_PuDbgPrint
0x180008418  mov     eax, ebx
0x18000841a  jmp     short loc_180008484
0x18000841c  mov     rax, [rsp+68h+arg_0]
0x180008421  mov     [rsi], rax
0x180008424  jmp     short loc_180008418
0x180008426  bt      eax, 14h
0x18000842a  jnb     short loc_18000847F
0x18000842c  test    ebp, ebp
0x18000842e  jz      short loc_180008443
0x180008430  test    al, 3
0x180008432  jz      short loc_18000847F
0x180008434  lea     rax, aHseReqGetUnico_3; "\r\n  HSE_REQ_GET_UNICODE_VIRTUAL_PATH_"...
0x18000843b  mov     r8d, 0DD5h
0x180008441  jmp     short loc_180008454
0x180008443  test    al, 3
0x180008445  jz      short loc_18000847F
0x180008447  lea     rax, aHseReqGetVirtu_1; "\r\n  HSE_REQ_GET_VIRTUAL_PATH_TOKEN[%p"...
0x18000844e  mov     r8d, 0DE3h
0x180008454  mov     rcx, cs:g_pDebug
0x18000845b  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008462  mov     [rsp+68h+var_30], rsi
0x180008467  mov     r9, r13
0x18000846a  mov     [rsp+68h+var_38], rbx
0x18000846f  mov     [rsp+68h+var_40], rdi
0x180008474  mov     [rsp+68h+var_48], rax
0x180008479  call    cs:__imp_PuDbgPrint
0x18000847f  mov     eax, 80070057h
0x180008484  lea     r11, [rsp+68h+var_28]
0x180008489  mov     rbx, [r11+38h]
0x18000848d  mov     rbp, [r11+40h]
0x180008491  mov     rsp, r11
0x180008494  pop     r15
0x180008496  pop     r14
0x180008498  pop     r13
0x18000849a  pop     rdi
0x18000849b  pop     rsi
0x18000849c  retn
```
