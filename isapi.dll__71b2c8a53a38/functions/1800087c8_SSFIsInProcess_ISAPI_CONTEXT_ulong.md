# SSFIsInProcess(ISAPI_CONTEXT *,ulong *)

- ea: `0x1800087c8`
- end: `0x180008891`
- name: `?SSFIsInProcess@@YAJPEAVISAPI_CONTEXT@@PEAK@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x1800087c8`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008820`
- `iisutil!PuDbgPrint` at `0x180008871`
- `iisutil!PuDbgPrint` at `0x180008820`
- `iisutil!PuDbgPrint` at `0x180008871`

## string_xrefs

- `0x180008819`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000886a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFIsInProcess(struct ISAPI_CONTEXT *a1, unsigned int *a2)
{
  int v2; // r9d

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      3389,
      "SSFIsInProcess",
      "\r\n  HSE_REQ_IS_IN_PROCESS[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v2 = g_dwDebugFlags;
  }
  if ( a2 )
  {
    *a2 = 0;
    return 0;
  }
  else
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3401,
        "SSFIsInProcess",
        "\r\n  HSE_REQ_IS_IN_PROCESS[%p]: Parameter validation failure\r\n    AppFlag Ptr: NULL\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800087c8  mov     [rsp+arg_0], rbx
0x1800087cd  push    rdi
0x1800087ce  sub     rsp, 30h
0x1800087d2  mov     r9d, cs:g_dwDebugFlags
0x1800087d9  mov     rbx, rdx
0x1800087dc  test    r9b, 3
0x1800087e0  mov     rdi, rcx
0x1800087e3  setnz   r8b
0x1800087e7  bt      r9d, 1Ah
0x1800087ec  setb    al
0x1800087ef  test    al, r8b
0x1800087f2  jz      short loc_18000882D
0x1800087f4  mov     [rsp+38h+var_10], rcx
0x1800087f9  lea     rax, aHseReqIsInProc_0; "\r\n  HSE_REQ_IS_IN_PROCESS[%p]: Functi"...
0x180008800  mov     rcx, cs:g_pDebug
0x180008807  lea     r9, aSsfisinprocess; "SSFIsInProcess"
0x18000880e  mov     r8d, 0D3Dh
0x180008814  mov     [rsp+38h+var_18], rax
0x180008819  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008820  call    cs:__imp_PuDbgPrint
0x180008826  mov     r9d, cs:g_dwDebugFlags
0x18000882d  test    rbx, rbx
0x180008830  jnz     short loc_18000887E
0x180008832  test    r9b, 3
0x180008836  setnz   cl
0x180008839  bt      r9d, 14h
0x18000883e  setb    al
0x180008841  test    al, cl
0x180008843  jz      short loc_180008877
0x180008845  mov     rcx, cs:g_pDebug
0x18000884c  lea     rax, aHseReqIsInProc_1; "\r\n  HSE_REQ_IS_IN_PROCESS[%p]: Parame"...
0x180008853  mov     [rsp+38h+var_10], rdi
0x180008858  lea     r9, aSsfisinprocess; "SSFIsInProcess"
0x18000885f  mov     r8d, 0D49h
0x180008865  mov     [rsp+38h+var_18], rax
0x18000886a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008871  call    cs:__imp_PuDbgPrint
0x180008877  mov     eax, 80070057h
0x18000887c  jmp     short loc_180008886
0x18000887e  mov     dword ptr [rbx], 0
0x180008884  xor     eax, eax
0x180008886  mov     rbx, [rsp+38h+arg_0]
0x18000888b  add     rsp, 30h
0x18000888f  pop     rdi
0x180008890  retn
```
