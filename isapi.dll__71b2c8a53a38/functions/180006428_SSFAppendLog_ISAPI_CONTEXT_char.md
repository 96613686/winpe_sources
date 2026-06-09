# SSFAppendLog(ISAPI_CONTEXT *,char *)

- ea: `0x180006428`
- end: `0x180006582`
- name: `?SSFAppendLog@@YAJPEAVISAPI_CONTEXT@@PEAD@Z`
- size: `346`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180006428`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006484`
- `iisutil!PuDbgPrint` at `0x180006503`
- `iisutil!PuDbgPrint` at `0x18000656f`
- `iisutil!PuDbgPrint` at `0x180006484`
- `iisutil!PuDbgPrint` at `0x180006503`
- `iisutil!PuDbgPrint` at `0x18000656f`

## string_xrefs

- `0x180006473`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800064f7`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180006551`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFAppendLog(struct ISAPI_CONTEXT *a1, char *a2)
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
      1870,
      "SSFAppendLog",
      "\r\n  HSE_REQ_APPEND_LOG_PARAMETER[%p]: Function Entry\r\n    Extra Param: '%s'\r\n  <END>\r\n\r\n",
      a1,
      a2);
    v2 = g_dwDebugFlags;
  }
  v5 = *((_QWORD *)a1 + 24);
  if ( !v5 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1883,
        "SSFAppendLog",
        "\r\n  HSE_REQ_APPEND_LOG_PARAMETER[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1902,
        "SSFAppendLog",
        "\r\n"
        "  HSE_REQ_APPEND_LOG_PARAMETER[%p]: Parameter validation failure\r\n"
        "    Extra Param: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
    return 2147942487LL;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v5 + 80LL))(v5, a2, 0);
  v8 = v7;
  if ( v7 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      1920,
      "SSFAppendLog",
      "\r\n  HSE_REQ_APPEND_LOG_PARAMETER[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v7);
  return v8;
}

```

## disassembly

```asm
0x180006428  mov     r11, rsp
0x18000642b  mov     [r11+8], rbx
0x18000642f  push    rdi
0x180006430  sub     rsp, 40h
0x180006434  mov     r9d, cs:g_dwDebugFlags
0x18000643b  mov     rdi, rdx
0x18000643e  test    r9b, 3
0x180006442  mov     rbx, rcx
0x180006445  setnz   r8b
0x180006449  bt      r9d, 1Ah
0x18000644e  setb    al
0x180006451  test    al, r8b
0x180006454  jz      short loc_180006491
0x180006456  mov     [r11-18h], rdx
0x18000645a  lea     rax, aHseReqAppendLo_1; "\r\n  HSE_REQ_APPEND_LOG_PARAMETER[%p]:"...
0x180006461  mov     [r11-20h], rcx
0x180006465  lea     r9, aSsfappendlog; "SSFAppendLog"
0x18000646c  mov     rcx, cs:g_pDebug
0x180006473  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000647a  mov     r8d, 74Eh
0x180006480  mov     [r11-28h], rax
0x180006484  call    cs:__imp_PuDbgPrint
0x18000648a  mov     r9d, cs:g_dwDebugFlags
0x180006491  mov     rcx, [rbx+0C0h]
0x180006498  test    rcx, rcx
0x18000649b  jnz     short loc_1800064BF
0x18000649d  test    r9b, 3
0x1800064a1  setnz   cl
0x1800064a4  bt      r9d, 14h
0x1800064a9  setb    al
0x1800064ac  test    al, cl
0x1800064ae  jz      short loc_180006509
0x1800064b0  lea     rax, aHseReqAppendLo_0; "\r\n  HSE_REQ_APPEND_LOG_PARAMETER[%p]:"...
0x1800064b7  mov     r8d, 75Bh
0x1800064bd  jmp     short loc_1800064E4
0x1800064bf  test    rdi, rdi
0x1800064c2  jnz     short loc_180006510
0x1800064c4  test    r9b, 3
0x1800064c8  setnz   cl
0x1800064cb  bt      r9d, 14h
0x1800064d0  setb    al
0x1800064d3  test    al, cl
0x1800064d5  jz      short loc_180006509
0x1800064d7  lea     rax, aHseReqAppendLo_3; "\r\n  HSE_REQ_APPEND_LOG_PARAMETER[%p]:"...
0x1800064de  mov     r8d, 76Eh
0x1800064e4  mov     rcx, cs:g_pDebug
0x1800064eb  lea     r9, aSsfappendlog; "SSFAppendLog"
0x1800064f2  mov     [rsp+48h+var_20], rbx
0x1800064f7  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800064fe  mov     [rsp+48h+var_28], rax
0x180006503  call    cs:__imp_PuDbgPrint
0x180006509  mov     eax, 80070057h
0x18000650e  jmp     short loc_180006577
0x180006510  mov     rax, [rcx]
0x180006513  xor     r8d, r8d
0x180006516  mov     rdx, rdi
0x180006519  mov     rax, [rax+50h]
0x18000651d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006522  mov     edi, eax
0x180006524  test    eax, eax
0x180006526  jns     short loc_180006575
0x180006528  mov     ecx, cs:g_dwDebugFlags
0x18000652e  test    cl, 3
0x180006531  setnz   dl
0x180006534  bt      ecx, 14h
0x180006538  setb    cl
0x18000653b  test    cl, dl
0x18000653d  jz      short loc_180006575
0x18000653f  mov     rcx, cs:g_pDebug
0x180006546  lea     r9, aSsfappendlog; "SSFAppendLog"
0x18000654d  mov     [rsp+48h+var_18], eax
0x180006551  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006558  lea     rax, aHseReqAppendLo_2; "\r\n  HSE_REQ_APPEND_LOG_PARAMETER[%p]:"...
0x18000655f  mov     [rsp+48h+var_20], rbx
0x180006564  mov     r8d, 780h
0x18000656a  mov     [rsp+48h+var_28], rax
0x18000656f  call    cs:__imp_PuDbgPrint
0x180006575  mov     eax, edi
0x180006577  mov     rbx, [rsp+48h+arg_0]
0x18000657c  add     rsp, 40h
0x180006580  pop     rdi
0x180006581  retn
```
