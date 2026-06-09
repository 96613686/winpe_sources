# SSFMapUrlToPath(ISAPI_CONTEXT *,char *,ulong *)

- ea: `0x180008d70`
- end: `0x180008f4f`
- name: `?SSFMapUrlToPath@@YAJPEAVISAPI_CONTEXT@@PEADPEAK@Z`
- size: `479`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, char *, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180008d70`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008dd7`
- `iisutil!PuDbgPrint` at `0x180008e2b`
- `iisutil!PuDbgPrint` at `0x180008eb3`
- `iisutil!PuDbgPrint` at `0x180008f39`
- `iisutil!PuDbgPrint` at `0x180008dd7`
- `iisutil!PuDbgPrint` at `0x180008e2b`
- `iisutil!PuDbgPrint` at `0x180008eb3`
- `iisutil!PuDbgPrint` at `0x180008f39`

## string_xrefs

- `0x180008d8d`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180008db3`: `\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Function Entry\n    URL: %s\n  <END>\n\n`
- `0x180008d82`: `SSFMapUrlToPath`
- `0x180008e0e`: `\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Failed to get interface to server core\n  <END>\n\n`
- `0x180008f25`: `\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Parameter validation failure\n    Buffer: '%s'\n    Buffer Size Ptr: %p\n    Buffer Size: %d\n`
- `0x180008e95`: `\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`
- `0x180008edf`: `\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Succeeded\n    Mapped URL: %s\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFMapUrlToPath(struct ISAPI_CONTEXT *a1, char *a2, const char *a3)
{
  int v3; // r10d
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // eax
  unsigned int v10; // ebx
  int v12; // eax
  __int64 v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+40h] [rbp-28h]

  v3 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      327,
      "SSFMapUrlToPath",
      "\r\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Function Entry\r\n    URL: %s\r\n  <END>\r\n\r\n",
      a1,
      a2);
    v3 = g_dwDebugFlags;
  }
  v7 = *((_QWORD *)a1 + 24);
  if ( !v7 )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        340,
        "SSFMapUrlToPath",
        "\r\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 || !a3 || (v8 = *(unsigned int *)a3, !(_DWORD)v8) )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
    {
      if ( a3 )
        v12 = *(_DWORD *)a3;
      else
        v12 = 0;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        365,
        "SSFMapUrlToPath",
        "\r\n"
        "  HSE_REQ_MAP_URL_TO_PATH[%p]: Parameter validation failure\r\n"
        "    Buffer: '%s'\r\n"
        "    Buffer Size Ptr: %p\r\n"
        "    Buffer Size: %d\r\n",
        a1,
        a3,
        v12,
        v14);
    }
    return 2147942487LL;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, char *, __int64, const char *, _DWORD))(*(_QWORD *)v7 + 32LL))(
         v7,
         a2,
         v8,
         a3,
         0);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( (g_dwDebugFlags & 0x4000000) != 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        404,
        "SSFMapUrlToPath",
        "\r\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Succeeded\r\n    Mapped URL: %s\r\n  <END>\r\n\r\n",
        a1,
        a2);
  }
  else if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
  {
    LODWORD(v13) = v9;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      388,
      "SSFMapUrlToPath",
      "\r\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v13);
  }
  return v10;
}

```

## disassembly

```asm
0x180008d70  push    rbx
0x180008d72  push    rbp
0x180008d73  push    rsi
0x180008d74  push    rdi
0x180008d75  push    r14
0x180008d77  sub     rsp, 40h
0x180008d7b  mov     r10d, cs:g_dwDebugFlags
0x180008d82  lea     rbp, aSsfmapurltopat_0; "SSFMapUrlToPath"
0x180008d89  test    r10b, 3
0x180008d8d  lea     r14, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008d94  mov     rbx, r8
0x180008d97  mov     rsi, rdx
0x180008d9a  setnz   r9b
0x180008d9e  mov     rdi, rcx
0x180008da1  bt      r10d, 1Ah
0x180008da6  setb    al
0x180008da9  test    al, r9b
0x180008dac  jz      short loc_180008DE4
0x180008dae  mov     [rsp+68h+var_38], rdx
0x180008db3  lea     rax, aHseReqMapUrlTo_0; "\r\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Func"...
0x180008dba  mov     [rsp+68h+var_40], rcx
0x180008dbf  mov     r9, rbp
0x180008dc2  mov     rcx, cs:g_pDebug
0x180008dc9  mov     r8d, 147h
0x180008dcf  mov     rdx, r14
0x180008dd2  mov     [rsp+68h+var_48], rax
0x180008dd7  call    cs:__imp_PuDbgPrint
0x180008ddd  mov     r10d, cs:g_dwDebugFlags
0x180008de4  mov     rcx, [rdi+0C0h]
0x180008deb  test    rcx, rcx
0x180008dee  jnz     short loc_180008E36
0x180008df0  test    r10b, 3
0x180008df4  setnz   cl
0x180008df7  bt      r10d, 14h
0x180008dfc  setb    al
0x180008dff  test    al, cl
0x180008e01  jz      loc_180008F3F
0x180008e07  mov     rcx, cs:g_pDebug
0x180008e0e  lea     rax, aHseReqMapUrlTo_3; "\r\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Fail"...
0x180008e15  mov     [rsp+68h+var_40], rdi
0x180008e1a  mov     r9, rbp
0x180008e1d  mov     r8d, 154h
0x180008e23  mov     [rsp+68h+var_48], rax
0x180008e28  mov     rdx, r14
0x180008e2b  call    cs:__imp_PuDbgPrint
0x180008e31  jmp     loc_180008F3F
0x180008e36  test    rsi, rsi
0x180008e39  jz      loc_180008EEE
0x180008e3f  test    rbx, rbx
0x180008e42  jz      loc_180008EEE
0x180008e48  mov     r8d, [rbx]
0x180008e4b  test    r8d, r8d
0x180008e4e  jz      loc_180008EEE
0x180008e54  mov     rax, [rcx]
0x180008e57  mov     r9, rbx
0x180008e5a  mov     rdx, rsi
0x180008e5d  mov     dword ptr [rsp+68h+var_48], 0
0x180008e65  mov     rax, [rax+20h]
0x180008e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e6e  mov     ecx, cs:g_dwDebugFlags
0x180008e74  mov     ebx, eax
0x180008e76  test    eax, eax
0x180008e78  jns     short loc_180008EC0
0x180008e7a  test    cl, 3
0x180008e7d  setnz   dl
0x180008e80  bt      ecx, 14h
0x180008e84  setb    cl
0x180008e87  test    cl, dl
0x180008e89  jz      short loc_180008EB9
0x180008e8b  mov     dword ptr [rsp+68h+var_38], eax
0x180008e8f  mov     r8d, 184h
0x180008e95  lea     rax, aHseReqMapUrlTo_1; "\r\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Fail"...
0x180008e9c  mov     rcx, cs:g_pDebug
0x180008ea3  mov     r9, rbp
0x180008ea6  mov     [rsp+68h+var_40], rdi
0x180008eab  mov     rdx, r14
0x180008eae  mov     [rsp+68h+var_48], rax
0x180008eb3  call    cs:__imp_PuDbgPrint
0x180008eb9  mov     eax, ebx
0x180008ebb  jmp     loc_180008F44
0x180008ec0  test    cl, 3
0x180008ec3  setnz   dl
0x180008ec6  bt      ecx, 1Ah
0x180008eca  setb    al
0x180008ecd  and     dl, al
0x180008ecf  bt      ecx, 15h
0x180008ed3  setb    al
0x180008ed6  test    al, dl
0x180008ed8  jz      short loc_180008EB9
0x180008eda  mov     [rsp+68h+var_38], rsi
0x180008edf  lea     rax, aHseReqMapUrlTo_8; "\r\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Succ"...
0x180008ee6  mov     r8d, 194h
0x180008eec  jmp     short loc_180008E9C
0x180008eee  test    r10b, 3
0x180008ef2  setnz   cl
0x180008ef5  bt      r10d, 14h
0x180008efa  setb    al
0x180008efd  test    al, cl
0x180008eff  jz      short loc_180008F3F
0x180008f01  test    rbx, rbx
0x180008f04  jz      short loc_180008F0A
0x180008f06  mov     eax, [rbx]
0x180008f08  jmp     short loc_180008F0C
0x180008f0a  xor     eax, eax
0x180008f0c  mov     rcx, cs:g_pDebug
0x180008f13  mov     r9, rbp
0x180008f16  mov     [rsp+68h+var_30], eax
0x180008f1a  mov     r8d, 16Dh
0x180008f20  mov     [rsp+68h+var_38], rbx
0x180008f25  lea     rax, aHseReqMapUrlTo_4; "\r\n  HSE_REQ_MAP_URL_TO_PATH[%p]: Para"...
0x180008f2c  mov     [rsp+68h+var_40], rdi
0x180008f31  mov     rdx, r14
0x180008f34  mov     [rsp+68h+var_48], rax
0x180008f39  call    cs:__imp_PuDbgPrint
0x180008f3f  mov     eax, 80070057h
0x180008f44  add     rsp, 40h
0x180008f48  pop     r14
0x180008f4a  pop     rdi
0x180008f4b  pop     rsi
0x180008f4c  pop     rbp
0x180008f4d  pop     rbx
0x180008f4e  retn
```
