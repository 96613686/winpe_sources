# SSFGetTraceInfo(ISAPI_CONTEXT *,_HSE_TRACE_INFO *)

- ea: `0x180007fd8`
- end: `0x18000810f`
- name: `?SSFGetTraceInfo@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_TRACE_INFO@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct _HSE_TRACE_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180007fd8`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008037`
- `iisutil!PuDbgPrint` at `0x180008088`
- `iisutil!PuDbgPrint` at `0x1800080f7`
- `iisutil!PuDbgPrint` at `0x180008037`
- `iisutil!PuDbgPrint` at `0x180008088`
- `iisutil!PuDbgPrint` at `0x1800080f7`

## string_xrefs

- `0x180008030`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008081`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800080d9`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFGetTraceInfo(struct ISAPI_CONTEXT *a1, struct _HSE_TRACE_INFO *a2)
{
  int v2; // r9d
  __int64 v4; // rsi
  int v7; // eax
  unsigned int v8; // ebx
  const void *v9; // [rsp+28h] [rbp-20h]

  v2 = g_dwDebugFlags;
  v4 = *((_QWORD *)a1 + 24);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4586,
      "SSFGetTraceInfo",
      "\r\n  HSE_REQ_GET_TRACE_INFO[%p]: Function Entry\r\n  <END>\r\n\r\n",
      v9);
    v2 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, struct _HSE_TRACE_INFO *))(*(_QWORD *)v4 + 256LL))(v4, a2);
    v8 = v7;
    if ( v7 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4621,
        "SSFGetTraceInfo",
        "\r\n  HSE_REQ_GET_TRACE_INFO[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        v7);
    return v8;
  }
  else
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4602,
        "SSFGetTraceInfo",
        "\r\n  HSE_REQ_GET_TRACE_INFO[%p]: Failed\r\n    NULL parameter passed to the call\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180007fd8  mov     [rsp+arg_0], rbx
0x180007fdd  mov     [rsp+arg_8], rsi
0x180007fe2  push    rdi
0x180007fe3  sub     rsp, 40h
0x180007fe7  mov     r9d, cs:g_dwDebugFlags
0x180007fee  mov     rbx, rdx
0x180007ff1  mov     rsi, [rcx+0C0h]
0x180007ff8  test    r9b, 3
0x180007ffc  mov     rdi, rcx
0x180007fff  setnz   r8b
0x180008003  bt      r9d, 1Ah
0x180008008  setb    al
0x18000800b  test    al, r8b
0x18000800e  jz      short loc_180008044
0x180008010  mov     rcx, cs:g_pDebug
0x180008017  lea     rax, aHseReqGetTrace_3; "\r\n  HSE_REQ_GET_TRACE_INFO[%p]: Funct"...
0x18000801e  lea     r9, aSsfgettraceinf_0; "SSFGetTraceInfo"
0x180008025  mov     [rsp+48h+var_28], rax
0x18000802a  mov     r8d, 11EAh
0x180008030  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008037  call    cs:__imp_PuDbgPrint
0x18000803d  mov     r9d, cs:g_dwDebugFlags
0x180008044  test    rbx, rbx
0x180008047  jnz     short loc_180008095
0x180008049  test    r9b, 3
0x18000804d  setnz   cl
0x180008050  bt      r9d, 14h
0x180008055  setb    al
0x180008058  test    al, cl
0x18000805a  jz      short loc_18000808E
0x18000805c  mov     rcx, cs:g_pDebug
0x180008063  lea     rax, aHseReqGetTrace_4; "\r\n  HSE_REQ_GET_TRACE_INFO[%p]: Faile"...
0x18000806a  mov     [rsp+48h+var_20], rdi
0x18000806f  lea     r9, aSsfgettraceinf_0; "SSFGetTraceInfo"
0x180008076  mov     r8d, 11FAh
0x18000807c  mov     [rsp+48h+var_28], rax
0x180008081  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008088  call    cs:__imp_PuDbgPrint
0x18000808e  mov     eax, 80070057h
0x180008093  jmp     short loc_1800080FF
0x180008095  mov     rax, [rsi]
0x180008098  mov     rdx, rbx
0x18000809b  mov     rcx, rsi
0x18000809e  mov     rax, [rax+100h]
0x1800080a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080aa  mov     ebx, eax
0x1800080ac  test    eax, eax
0x1800080ae  jns     short loc_1800080FD
0x1800080b0  mov     ecx, cs:g_dwDebugFlags
0x1800080b6  test    cl, 3
0x1800080b9  setnz   dl
0x1800080bc  bt      ecx, 14h
0x1800080c0  setb    cl
0x1800080c3  test    cl, dl
0x1800080c5  jz      short loc_1800080FD
0x1800080c7  mov     rcx, cs:g_pDebug
0x1800080ce  lea     r9, aSsfgettraceinf_0; "SSFGetTraceInfo"
0x1800080d5  mov     [rsp+48h+var_18], eax
0x1800080d9  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800080e0  lea     rax, aHseReqGetTrace_0; "\r\n  HSE_REQ_GET_TRACE_INFO[%p]: Faile"...
0x1800080e7  mov     [rsp+48h+var_20], rdi
0x1800080ec  mov     r8d, 120Dh
0x1800080f2  mov     [rsp+48h+var_28], rax
0x1800080f7  call    cs:__imp_PuDbgPrint
0x1800080fd  mov     eax, ebx
0x1800080ff  mov     rbx, [rsp+48h+arg_0]
0x180008104  mov     rsi, [rsp+48h+arg_8]
0x180008109  add     rsp, 40h
0x18000810d  pop     rdi
0x18000810e  retn
```
