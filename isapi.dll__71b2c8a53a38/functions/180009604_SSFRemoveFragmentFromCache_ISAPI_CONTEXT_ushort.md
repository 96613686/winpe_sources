# SSFRemoveFragmentFromCache(ISAPI_CONTEXT *,ushort *)

- ea: `0x180009604`
- end: `0x180009798`
- name: `?SSFRemoveFragmentFromCache@@YAJPEAVISAPI_CONTEXT@@PEAG@Z`
- size: `404`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180009604`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000966b`
- `iisutil!PuDbgPrint` at `0x1800096c0`
- `iisutil!PuDbgPrint` at `0x180009711`
- `iisutil!PuDbgPrint` at `0x180009780`
- `iisutil!PuDbgPrint` at `0x18000966b`
- `iisutil!PuDbgPrint` at `0x1800096c0`
- `iisutil!PuDbgPrint` at `0x180009711`
- `iisutil!PuDbgPrint` at `0x180009780`

## string_xrefs

- `0x18000965a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800096b9`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800096ff`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009762`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009641`: `\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE[%p]: Function Entry\n    Fragment Name: '%S'\n  <END>\n\n`
- `0x18000964c`: `SSFRemoveFragmentFromCache`
- `0x1800096a7`: `SSFRemoveFragmentFromCache`
- `0x1800096f3`: `SSFRemoveFragmentFromCache`
- `0x180009757`: `SSFRemoveFragmentFromCache`
- `0x18000969b`: `\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE[%p]: Failed to get interface to server core\n  <END>\n\n`
- `0x1800096e7`: `\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE[%p]: Parameter validation failure\n    Fragment Name: '%s'\n  <END>\n\n`
- `0x180009769`: `\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFRemoveFragmentFromCache(struct ISAPI_CONTEXT *a1, unsigned __int16 *a2)
{
  int v2; // r9d
  __int64 v4; // rsi
  int v7; // eax
  unsigned int v8; // edi

  v2 = g_dwDebugFlags;
  v4 = *((_QWORD *)a1 + 24);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4184,
      "SSFRemoveFragmentFromCache",
      "\r\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE[%p]: Function Entry\r\n    Fragment Name: '%S'\r\n  <END>\r\n\r\n",
      a1,
      a2);
    v2 = g_dwDebugFlags;
  }
  if ( !v4 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4195,
        "SSFRemoveFragmentFromCache",
        "\r\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4215,
        "SSFRemoveFragmentFromCache",
        "\r\n"
        "  HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE[%p]: Parameter validation failure\r\n"
        "    Fragment Name: '%s'\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        0);
    return 2147942487LL;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v4 + 176LL))(v4, a2);
  v8 = v7;
  if ( v7 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4233,
      "SSFRemoveFragmentFromCache",
      "\r\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v7);
  return v8;
}

```

## disassembly

```asm
0x180009604  mov     r11, rsp
0x180009607  mov     [r11+8], rbx
0x18000960b  mov     [r11+10h], rsi
0x18000960f  push    rdi
0x180009610  sub     rsp, 40h
0x180009614  mov     r9d, cs:g_dwDebugFlags
0x18000961b  mov     rdi, rdx
0x18000961e  mov     rsi, [rcx+0C0h]
0x180009625  test    r9b, 3
0x180009629  mov     rbx, rcx
0x18000962c  setnz   r8b
0x180009630  bt      r9d, 1Ah
0x180009635  setb    al
0x180009638  test    al, r8b
0x18000963b  jz      short loc_180009678
0x18000963d  mov     [r11-18h], rdx
0x180009641  lea     rax, aHseReqRemoveFr_1; "\r\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACH"...
0x180009648  mov     [r11-20h], rcx
0x18000964c  lea     r9, aSsfremovefragm; "SSFRemoveFragmentFromCache"
0x180009653  mov     rcx, cs:g_pDebug
0x18000965a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009661  mov     r8d, 1058h
0x180009667  mov     [r11-28h], rax
0x18000966b  call    cs:__imp_PuDbgPrint
0x180009671  mov     r9d, cs:g_dwDebugFlags
0x180009678  test    rsi, rsi
0x18000967b  jnz     short loc_1800096C8
0x18000967d  test    r9b, 3
0x180009681  setnz   cl
0x180009684  bt      r9d, 14h
0x180009689  setb    al
0x18000968c  test    al, cl
0x18000968e  jz      loc_180009717
0x180009694  mov     rcx, cs:g_pDebug
0x18000969b  lea     rax, aHseReqRemoveFr_3; "\r\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACH"...
0x1800096a2  mov     [rsp+48h+var_20], rbx
0x1800096a7  lea     r9, aSsfremovefragm; "SSFRemoveFragmentFromCache"
0x1800096ae  mov     r8d, 1063h
0x1800096b4  mov     [rsp+48h+var_28], rax
0x1800096b9  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800096c0  call    cs:__imp_PuDbgPrint
0x1800096c6  jmp     short loc_180009717
0x1800096c8  test    rdi, rdi
0x1800096cb  jnz     short loc_18000971E
0x1800096cd  test    r9b, 3
0x1800096d1  setnz   cl
0x1800096d4  bt      r9d, 14h
0x1800096d9  setb    al
0x1800096dc  test    al, cl
0x1800096de  jz      short loc_180009717
0x1800096e0  mov     rcx, cs:g_pDebug
0x1800096e7  lea     rax, aHseReqRemoveFr; "\r\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACH"...
0x1800096ee  mov     [rsp+48h+var_18], rdi
0x1800096f3  lea     r9, aSsfremovefragm; "SSFRemoveFragmentFromCache"
0x1800096fa  mov     [rsp+48h+var_20], rbx
0x1800096ff  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009706  mov     r8d, 1077h
0x18000970c  mov     [rsp+48h+var_28], rax
0x180009711  call    cs:__imp_PuDbgPrint
0x180009717  mov     eax, 80070057h
0x18000971c  jmp     short loc_180009788
0x18000971e  mov     rax, [rsi]
0x180009721  mov     rdx, rdi
0x180009724  mov     rcx, rsi
0x180009727  mov     rax, [rax+0B0h]
0x18000972e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009733  mov     edi, eax
0x180009735  test    eax, eax
0x180009737  jns     short loc_180009786
0x180009739  mov     ecx, cs:g_dwDebugFlags
0x18000973f  test    cl, 3
0x180009742  setnz   dl
0x180009745  bt      ecx, 14h
0x180009749  setb    cl
0x18000974c  test    cl, dl
0x18000974e  jz      short loc_180009786
0x180009750  mov     rcx, cs:g_pDebug
0x180009757  lea     r9, aSsfremovefragm; "SSFRemoveFragmentFromCache"
0x18000975e  mov     dword ptr [rsp+48h+var_18], eax
0x180009762  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009769  lea     rax, aHseReqRemoveFr_0; "\r\n  HSE_REQ_REMOVE_FRAGMENT_FROM_CACH"...
0x180009770  mov     [rsp+48h+var_20], rbx
0x180009775  mov     r8d, 1089h
0x18000977b  mov     [rsp+48h+var_28], rax
0x180009780  call    cs:__imp_PuDbgPrint
0x180009786  mov     eax, edi
0x180009788  mov     rbx, [rsp+48h+arg_0]
0x18000978d  mov     rsi, [rsp+48h+arg_8]
0x180009792  add     rsp, 40h
0x180009796  pop     rdi
0x180009797  retn
```
