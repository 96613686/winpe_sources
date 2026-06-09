# SSFMapUrlToPathEx(ISAPI_CONTEXT *,char *,_HSE_URL_MAPEX_INFO *,ulong *)

- ea: `0x180008f58`
- end: `0x180009175`
- name: `?SSFMapUrlToPathEx@@YAJPEAVISAPI_CONTEXT@@PEADPEAU_HSE_URL_MAPEX_INFO@@PEAK@Z`
- size: `541`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, char *, struct _HSE_URL_MAPEX_INFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180008f58`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008fc3`
- `iisutil!PuDbgPrint` at `0x18000901f`
- `iisutil!PuDbgPrint` at `0x18000910e`
- `iisutil!PuDbgPrint` at `0x180009161`
- `iisutil!PuDbgPrint` at `0x180008fc3`
- `iisutil!PuDbgPrint` at `0x18000901f`
- `iisutil!PuDbgPrint` at `0x18000910e`
- `iisutil!PuDbgPrint` at `0x180009161`

## string_xrefs

- `0x180008fb1`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009018`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800090f0`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000914a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008f97`: `\n  HSE_REQ_MAP_URL_TO_PATH_EX[%p]: Function Entry\n    URL='%s'\n  <END>\n\n`
- `0x180008fa3`: `SSFMapUrlToPathEx`
- `0x180009006`: `SSFMapUrlToPathEx`
- `0x1800090e5`: `SSFMapUrlToPathEx`
- `0x18000913e`: `SSFMapUrlToPathEx`
- `0x180008ffa`: `\n  HSE_REQ_MA_URL_TO_PATH_EX[%p]: Failed to get interface to server core\n  <END>\n\n`
- `0x180009132`: `\n  HSE_REQ_MAP_URL_TO_PATH_EX[%p]: Parameter validation failure\n    URL: '%s'\n    HSE_URL_MAPEX_INFO: %p\n  <END>\n\n`
- `0x1800090f7`: `\n  HSE_REQ_MAP_URL_TO_PATH_EX[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFMapUrlToPathEx(
        struct ISAPI_CONTEXT *a1,
        char *a2,
        struct _HSE_URL_MAPEX_INFO *a3,
        unsigned int *a4)
{
  int v4; // r11d
  __int64 v9; // rcx
  int *v10; // r11
  __int64 v11; // r8
  __int64 result; // rax
  unsigned int v13; // edi
  int v14; // [rsp+90h] [rbp+8h] BYREF

  v4 = g_dwDebugFlags;
  v14 = 0;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      454,
      "SSFMapUrlToPathEx",
      "\r\n  HSE_REQ_MAP_URL_TO_PATH_EX[%p]: Function Entry\r\n    URL='%s'\r\n  <END>\r\n\r\n",
      a1,
      a2);
    v4 = g_dwDebugFlags;
  }
  v9 = *((_QWORD *)a1 + 24);
  if ( !v9 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        468,
        "SSFMapUrlToPathEx",
        "\r\n  HSE_REQ_MA_URL_TO_PATH_EX[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 || !a3 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        491,
        "SSFMapUrlToPathEx",
        "\r\n"
        "  HSE_REQ_MAP_URL_TO_PATH_EX[%p]: Parameter validation failure\r\n"
        "    URL: '%s'\r\n"
        "    HSE_URL_MAPEX_INFO: %p\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a2,
        a3);
    return 2147942487LL;
  }
  v14 = 260;
  v10 = &v14;
  *(_QWORD *)&a3->dwReserved1 = 0;
  if ( a4 )
    v10 = (int *)a4;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  result = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, struct _HSE_URL_MAPEX_INFO *, int, int *, DWORD *, DWORD *, DWORD *, _DWORD))(*(_QWORD *)v9 + 40LL))(
             v9,
             a2,
             (unsigned int)(v11 + 1),
             a3,
             260,
             v10,
             &a3->cchMatchingPath,
             &a3->cchMatchingURL,
             &a3->dwFlags,
             0);
  v13 = result;
  if ( (int)result < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        529,
        "SSFMapUrlToPathEx",
        "\r\n  HSE_REQ_MAP_URL_TO_PATH_EX[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        result);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180008f58  mov     rax, rsp
0x180008f5b  push    rbx
0x180008f5c  push    rbp
0x180008f5d  push    rsi
0x180008f5e  push    rdi
0x180008f5f  sub     rsp, 68h
0x180008f63  mov     r11d, cs:g_dwDebugFlags
0x180008f6a  mov     rbp, r9
0x180008f6d  test    r11b, 3
0x180008f71  mov     dword ptr [rax+8], 0
0x180008f78  mov     rdi, r8
0x180008f7b  mov     rsi, rdx
0x180008f7e  setnz   r10b
0x180008f82  mov     rbx, rcx
0x180008f85  bt      r11d, 1Ah
0x180008f8a  setb    al
0x180008f8d  test    al, r10b
0x180008f90  jz      short loc_180008FD0
0x180008f92  mov     [rsp+88h+var_58], rdx
0x180008f97  lea     rax, aHseReqMapUrlTo_7; "\r\n  HSE_REQ_MAP_URL_TO_PATH_EX[%p]: F"...
0x180008f9e  mov     [rsp+88h+var_60], rcx
0x180008fa3  lea     r9, aSsfmapurltopat; "SSFMapUrlToPathEx"
0x180008faa  mov     rcx, cs:g_pDebug
0x180008fb1  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008fb8  mov     r8d, 1C6h
0x180008fbe  mov     [rsp+88h+var_68], rax
0x180008fc3  call    cs:__imp_PuDbgPrint
0x180008fc9  mov     r11d, cs:g_dwDebugFlags
0x180008fd0  mov     rcx, [rbx+0C0h]
0x180008fd7  test    rcx, rcx
0x180008fda  jnz     short loc_18000902A
0x180008fdc  test    r11b, 3
0x180008fe0  setnz   cl
0x180008fe3  bt      r11d, 14h
0x180008fe8  setb    al
0x180008feb  test    al, cl
0x180008fed  jz      loc_180009167
0x180008ff3  mov     rcx, cs:g_pDebug
0x180008ffa  lea     rax, aHseReqMaUrlToP; "\r\n  HSE_REQ_MA_URL_TO_PATH_EX[%p]: Fa"...
0x180009001  mov     [rsp+88h+var_60], rbx
0x180009006  lea     r9, aSsfmapurltopat; "SSFMapUrlToPathEx"
0x18000900d  mov     r8d, 1D4h
0x180009013  mov     [rsp+88h+var_68], rax
0x180009018  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000901f  call    cs:__imp_PuDbgPrint
0x180009025  jmp     loc_180009167
0x18000902a  test    rsi, rsi
0x18000902d  jz      loc_180009118
0x180009033  test    rdi, rdi
0x180009036  jz      loc_180009118
0x18000903c  test    rbp, rbp
0x18000903f  mov     [rsp+88h+arg_0], 104h
0x18000904a  lea     r11, [rsp+88h+arg_0]
0x180009052  mov     qword ptr [rdi+110h], 0
0x18000905d  mov     rax, [rcx]
0x180009060  cmovnz  r11, rbp
0x180009064  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009068  inc     r8
0x18000906b  cmp     byte ptr [rsi+r8], 0
0x180009070  jnz     short loc_180009068
0x180009072  mov     rax, [rax+28h]
0x180009076  lea     rdx, [rdi+104h]
0x18000907d  mov     [rsp+88h+var_40], 0
0x180009085  lea     r9, [rdi+10Ch]
0x18000908c  mov     [rsp+88h+var_48], rdx
0x180009091  lea     r10, [rdi+108h]
0x180009098  mov     [rsp+88h+var_50], r9
0x18000909d  inc     r8d
0x1800090a0  mov     [rsp+88h+var_58], r10
0x1800090a5  mov     r9, rdi
0x1800090a8  mov     [rsp+88h+var_60], r11
0x1800090ad  mov     rdx, rsi
0x1800090b0  mov     dword ptr [rsp+88h+var_68], 104h
0x1800090b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090bd  mov     edi, eax
0x1800090bf  test    eax, eax
0x1800090c1  jns     loc_18000916C
0x1800090c7  mov     ecx, cs:g_dwDebugFlags
0x1800090cd  test    cl, 3
0x1800090d0  setnz   dl
0x1800090d3  bt      ecx, 14h
0x1800090d7  setb    cl
0x1800090da  test    cl, dl
0x1800090dc  jz      short loc_180009114
0x1800090de  mov     rcx, cs:g_pDebug
0x1800090e5  lea     r9, aSsfmapurltopat; "SSFMapUrlToPathEx"
0x1800090ec  mov     dword ptr [rsp+88h+var_58], eax
0x1800090f0  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800090f7  lea     rax, aHseReqMapUrlTo_6; "\r\n  HSE_REQ_MAP_URL_TO_PATH_EX[%p]: F"...
0x1800090fe  mov     [rsp+88h+var_60], rbx
0x180009103  mov     r8d, 211h
0x180009109  mov     [rsp+88h+var_68], rax
0x18000910e  call    cs:__imp_PuDbgPrint
0x180009114  mov     eax, edi
0x180009116  jmp     short loc_18000916C
0x180009118  test    r11b, 3
0x18000911c  setnz   cl
0x18000911f  bt      r11d, 14h
0x180009124  setb    al
0x180009127  test    al, cl
0x180009129  jz      short loc_180009167
0x18000912b  mov     rcx, cs:g_pDebug
0x180009132  lea     rax, aHseReqMapUrlTo_2; "\r\n  HSE_REQ_MAP_URL_TO_PATH_EX[%p]: P"...
0x180009139  mov     [rsp+88h+var_50], rdi
0x18000913e  lea     r9, aSsfmapurltopat; "SSFMapUrlToPathEx"
0x180009145  mov     [rsp+88h+var_58], rsi
0x18000914a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009151  mov     [rsp+88h+var_60], rbx
0x180009156  mov     r8d, 1EBh
0x18000915c  mov     [rsp+88h+var_68], rax
0x180009161  call    cs:__imp_PuDbgPrint
0x180009167  mov     eax, 80070057h
0x18000916c  add     rsp, 68h
0x180009170  pop     rdi
0x180009171  pop     rsi
0x180009172  pop     rbp
0x180009173  pop     rbx
0x180009174  retn
```
