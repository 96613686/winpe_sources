# SSFRaiseTraceEvent(ISAPI_CONTEXT *,HTTP_TRACE_EVENT *)

- ea: `0x18000928c`
- end: `0x180009420`
- name: `?SSFRaiseTraceEvent@@YAJPEAVISAPI_CONTEXT@@PEAUHTTP_TRACE_EVENT@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct HTTP_TRACE_EVENT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x18000928c`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180009343`
- `iisutil!PuDbgPrint` at `0x180009394`
- `iisutil!PuDbgPrint` at `0x180009403`
- `iisutil!PuDbgPrint` at `0x180009343`
- `iisutil!PuDbgPrint` at `0x180009394`
- `iisutil!PuDbgPrint` at `0x180009403`

## string_xrefs

- `0x180009334`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000938d`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800093e5`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFRaiseTraceEvent(struct ISAPI_CONTEXT *a1, struct HTTP_TRACE_EVENT *a2)
{
  int v2; // r9d
  __int64 v4; // rsi
  int v7; // eax
  unsigned int v8; // ebx

  v2 = g_dwDebugFlags;
  v4 = *((_QWORD *)a1 + 24);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4785,
      "SSFRaiseTraceEvent",
      "\r\n"
      "  HSE_REQ_RAISE_TRACE_EVENT[%p]: Function Entry\r\n"
      "   TraceEvent[%p]:\r\n"
      "     pProviderGuid:%s\n"
      "     dwArea:%d\n"
      "     pEventClassGuid:%s\n"
      "     pActivityGuid:%s\n"
      "     pRelatedActivityGuid:%s\n"
      "     dwEventType:%d\n"
      "     pszEventTypeName:%s\n"
      "     dwEventVersion:%d\n"
      "     dwVerbosity:%d\n"
      "     dwTimeStamp:%d\n"
      "     cEventItems:%d\n"
      "  <END>\r\n"
      "\r\n",
      a1,
      a2,
      "GUID",
      a2->dwArea,
      "GUID",
      "GUID",
      "GUID",
      a2->dwEvent,
      (const char *)a2->pszEventName,
      a2->dwEventVersion,
      a2->dwVerbosity,
      a2->dwTimeStamp,
      a2->cEventItems);
    v2 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, struct HTTP_TRACE_EVENT *))(*(_QWORD *)v4 + 224LL))(v4, a2);
    v8 = v7;
    if ( v7 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4816,
        "SSFRaiseTraceEvent",
        "\r\n  HSE_REQ_RAISE_TRACE_EVENT[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
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
        4797,
        "SSFRaiseTraceEvent",
        "\r\n  HSE_REQ_RAISE_TRACE_EVENT[%p]: Failed\r\n    NULL parameter passed to the call\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000928c  mov     r11, rsp
0x18000928f  mov     [r11+8], rbx
0x180009293  mov     [r11+10h], rsi
0x180009297  push    rdi
0x180009298  sub     rsp, 90h
0x18000929f  mov     r9d, cs:g_dwDebugFlags
0x1800092a6  mov     rbx, rdx
0x1800092a9  mov     rsi, [rcx+0C0h]
0x1800092b0  test    r9b, 3
0x1800092b4  mov     rdi, rcx
0x1800092b7  setnz   r8b
0x1800092bb  bt      r9d, 1Ah
0x1800092c0  setb    al
0x1800092c3  test    al, r8b
0x1800092c6  jz      loc_180009350
0x1800092cc  mov     eax, [rdx+48h]
0x1800092cf  lea     rcx, aGuid; "GUID"
0x1800092d6  mov     [r11-10h], eax
0x1800092da  lea     r9, aSsfraisetracee; "SSFRaiseTraceEvent"
0x1800092e1  mov     eax, [rdx+40h]
0x1800092e4  mov     r8d, 12B1h
0x1800092ea  mov     [r11-18h], eax
0x1800092ee  mov     eax, [rdx+2Ch]
0x1800092f1  mov     [rsp+98h+var_20], eax
0x1800092f5  mov     eax, [rdx+28h]
0x1800092f8  mov     [rsp+98h+var_28], eax
0x1800092fc  mov     rax, [rdx+20h]
0x180009300  mov     [r11-30h], rax
0x180009304  mov     eax, [rdx+18h]
0x180009307  mov     [rsp+98h+var_38], eax
0x18000930b  mov     eax, [rdx+8]
0x18000930e  mov     [r11-40h], rcx
0x180009312  mov     [r11-48h], rcx
0x180009316  mov     [r11-50h], rcx
0x18000931a  mov     [rsp+98h+var_58], eax
0x18000931e  lea     rax, aHseReqRaiseTra; "\r\n  HSE_REQ_RAISE_TRACE_EVENT[%p]: Fu"...
0x180009325  mov     [r11-60h], rcx
0x180009329  mov     rcx, cs:g_pDebug
0x180009330  mov     [r11-68h], rdx
0x180009334  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000933b  mov     [r11-70h], rdi
0x18000933f  mov     [r11-78h], rax
0x180009343  call    cs:__imp_PuDbgPrint
0x180009349  mov     r9d, cs:g_dwDebugFlags
0x180009350  test    rbx, rbx
0x180009353  jnz     short loc_1800093A1
0x180009355  test    r9b, 3
0x180009359  setnz   cl
0x18000935c  bt      r9d, 14h
0x180009361  setb    al
0x180009364  test    al, cl
0x180009366  jz      short loc_18000939A
0x180009368  mov     rcx, cs:g_pDebug
0x18000936f  lea     rax, aHseReqRaiseTra_0; "\r\n  HSE_REQ_RAISE_TRACE_EVENT[%p]: Fa"...
0x180009376  mov     [rsp+98h+var_70], rdi
0x18000937b  lea     r9, aSsfraisetracee; "SSFRaiseTraceEvent"
0x180009382  mov     r8d, 12BDh
0x180009388  mov     [rsp+98h+var_78], rax
0x18000938d  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009394  call    cs:__imp_PuDbgPrint
0x18000939a  mov     eax, 80070057h
0x18000939f  jmp     short loc_18000940B
0x1800093a1  mov     rax, [rsi]
0x1800093a4  mov     rdx, rbx
0x1800093a7  mov     rcx, rsi
0x1800093aa  mov     rax, [rax+0E0h]
0x1800093b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093b6  mov     ebx, eax
0x1800093b8  test    eax, eax
0x1800093ba  jns     short loc_180009409
0x1800093bc  mov     ecx, cs:g_dwDebugFlags
0x1800093c2  test    cl, 3
0x1800093c5  setnz   dl
0x1800093c8  bt      ecx, 14h
0x1800093cc  setb    cl
0x1800093cf  test    cl, dl
0x1800093d1  jz      short loc_180009409
0x1800093d3  mov     rcx, cs:g_pDebug
0x1800093da  lea     r9, aSsfraisetracee; "SSFRaiseTraceEvent"
0x1800093e1  mov     [rsp+98h+var_68], eax
0x1800093e5  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800093ec  lea     rax, aHseReqRaiseTra_1; "\r\n  HSE_REQ_RAISE_TRACE_EVENT[%p]: Fa"...
0x1800093f3  mov     [rsp+98h+var_70], rdi
0x1800093f8  mov     r8d, 12D0h
0x1800093fe  mov     [rsp+98h+var_78], rax
0x180009403  call    cs:__imp_PuDbgPrint
0x180009409  mov     eax, ebx
0x18000940b  lea     r11, [rsp+98h+var_8]
0x180009413  mov     rbx, [r11+10h]
0x180009417  mov     rsi, [r11+18h]
0x18000941b  mov     rsp, r11
0x18000941e  pop     rdi
0x18000941f  retn
```
