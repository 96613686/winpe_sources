# SSFIsConnected(ISAPI_CONTEXT *,int *)

- ea: `0x18000866c`
- end: `0x1800087c2`
- name: `?SSFIsConnected@@YAJPEAVISAPI_CONTEXT@@PEAH@Z`
- size: `342`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x18000866c`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800086c4`
- `iisutil!PuDbgPrint` at `0x180008743`
- `iisutil!PuDbgPrint` at `0x1800087af`
- `iisutil!PuDbgPrint` at `0x1800086c4`
- `iisutil!PuDbgPrint` at `0x180008743`
- `iisutil!PuDbgPrint` at `0x1800087af`

## string_xrefs

- `0x1800086bd`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008737`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008791`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFIsConnected(struct ISAPI_CONTEXT *a1, int *a2)
{
  int v2; // r9d
  __int64 v5; // rcx
  int v7; // eax
  unsigned int v8; // edi

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      1775,
      "SSFIsConnected",
      "\r\n  HSE_REQ_IS_CONNECTED[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v2 = g_dwDebugFlags;
  }
  v5 = *((_QWORD *)a1 + 24);
  if ( !v5 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1788,
        "SSFIsConnected",
        "\r\n  HSE_REQ_IS_CONNECTED[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1807,
        "SSFIsConnected",
        "\r\n  HSE_REQ_IS_CONNECTED[%p]: Parameter validation failure\r\n    IsConnected Ptr: NULL\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 128LL))(v5, a2);
  v8 = v7;
  if ( v7 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      1825,
      "SSFIsConnected",
      "\r\n  HSE_REQ_IS_CONNECTED[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v7);
  return v8;
}

```

## disassembly

```asm
0x18000866c  mov     [rsp+arg_0], rbx
0x180008671  push    rdi
0x180008672  sub     rsp, 40h
0x180008676  mov     r9d, cs:g_dwDebugFlags
0x18000867d  mov     rdi, rdx
0x180008680  test    r9b, 3
0x180008684  mov     rbx, rcx
0x180008687  setnz   r8b
0x18000868b  bt      r9d, 1Ah
0x180008690  setb    al
0x180008693  test    al, r8b
0x180008696  jz      short loc_1800086D1
0x180008698  mov     [rsp+48h+var_20], rcx
0x18000869d  lea     rax, aHseReqIsConnec_3; "\r\n  HSE_REQ_IS_CONNECTED[%p]: Functio"...
0x1800086a4  mov     rcx, cs:g_pDebug
0x1800086ab  lea     r9, aSsfisconnected; "SSFIsConnected"
0x1800086b2  mov     r8d, 6EFh
0x1800086b8  mov     [rsp+48h+var_28], rax
0x1800086bd  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800086c4  call    cs:__imp_PuDbgPrint
0x1800086ca  mov     r9d, cs:g_dwDebugFlags
0x1800086d1  mov     rcx, [rbx+0C0h]
0x1800086d8  test    rcx, rcx
0x1800086db  jnz     short loc_1800086FF
0x1800086dd  test    r9b, 3
0x1800086e1  setnz   cl
0x1800086e4  bt      r9d, 14h
0x1800086e9  setb    al
0x1800086ec  test    al, cl
0x1800086ee  jz      short loc_180008749
0x1800086f0  lea     rax, aHseReqIsConnec_1; "\r\n  HSE_REQ_IS_CONNECTED[%p]: Failed "...
0x1800086f7  mov     r8d, 6FCh
0x1800086fd  jmp     short loc_180008724
0x1800086ff  test    rdi, rdi
0x180008702  jnz     short loc_180008750
0x180008704  test    r9b, 3
0x180008708  setnz   cl
0x18000870b  bt      r9d, 14h
0x180008710  setb    al
0x180008713  test    al, cl
0x180008715  jz      short loc_180008749
0x180008717  lea     rax, aHseReqIsConnec_0; "\r\n  HSE_REQ_IS_CONNECTED[%p]: Paramet"...
0x18000871e  mov     r8d, 70Fh
0x180008724  mov     rcx, cs:g_pDebug
0x18000872b  lea     r9, aSsfisconnected; "SSFIsConnected"
0x180008732  mov     [rsp+48h+var_20], rbx
0x180008737  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000873e  mov     [rsp+48h+var_28], rax
0x180008743  call    cs:__imp_PuDbgPrint
0x180008749  mov     eax, 80070057h
0x18000874e  jmp     short loc_1800087B7
0x180008750  mov     rax, [rcx]
0x180008753  mov     rdx, rdi
0x180008756  mov     rax, [rax+80h]
0x18000875d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008762  mov     edi, eax
0x180008764  test    eax, eax
0x180008766  jns     short loc_1800087B5
0x180008768  mov     ecx, cs:g_dwDebugFlags
0x18000876e  test    cl, 3
0x180008771  setnz   dl
0x180008774  bt      ecx, 14h
0x180008778  setb    cl
0x18000877b  test    cl, dl
0x18000877d  jz      short loc_1800087B5
0x18000877f  mov     rcx, cs:g_pDebug
0x180008786  lea     r9, aSsfisconnected; "SSFIsConnected"
0x18000878d  mov     [rsp+48h+var_18], eax
0x180008791  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008798  lea     rax, aHseReqIsConnec_2; "\r\n  HSE_REQ_IS_CONNECTED[%p]: Failed"...
0x18000879f  mov     [rsp+48h+var_20], rbx
0x1800087a4  mov     r8d, 721h
0x1800087aa  mov     [rsp+48h+var_28], rax
0x1800087af  call    cs:__imp_PuDbgPrint
0x1800087b5  mov     eax, edi
0x1800087b7  mov     rbx, [rsp+48h+arg_0]
0x1800087bc  add     rsp, 40h
0x1800087c0  pop     rdi
0x1800087c1  retn
```
