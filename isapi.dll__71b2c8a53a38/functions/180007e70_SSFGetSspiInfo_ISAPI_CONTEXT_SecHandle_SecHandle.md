# SSFGetSspiInfo(ISAPI_CONTEXT *,_SecHandle *,_SecHandle *)

- ea: `0x180007e70`
- end: `0x180007fcf`
- name: `?SSFGetSspiInfo@@YAJPEAVISAPI_CONTEXT@@PEAU_SecHandle@@1@Z`
- size: `351`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct _SecHandle *, struct _SecHandle *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180007e70`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007ed2`
- `iisutil!PuDbgPrint` at `0x180007f67`
- `iisutil!PuDbgPrint` at `0x180007fba`
- `iisutil!PuDbgPrint` at `0x180007ed2`
- `iisutil!PuDbgPrint` at `0x180007f67`
- `iisutil!PuDbgPrint` at `0x180007fba`

## string_xrefs

- `0x180007ecb`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007f49`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007fa3`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFGetSspiInfo(struct ISAPI_CONTEXT *a1, struct _SecHandle *a2, struct _SecHandle *a3)
{
  int v3; // r10d
  __int64 v5; // r14
  __int64 result; // rax
  unsigned int v9; // ebx

  v3 = g_dwDebugFlags;
  v5 = *((_QWORD *)a1 + 24);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      3432,
      "SSFGetSspiInfo",
      "\r\n  HSE_REQ_GET_SSPI_INFO[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v3 = g_dwDebugFlags;
  }
  if ( a2 && a3 )
  {
    result = (*(__int64 (__fastcall **)(__int64, struct _SecHandle *, __int64, struct _SecHandle *, int))(*(_QWORD *)v5 + 136LL))(
               v5,
               a3,
               16,
               a2,
               16);
    v9 = result;
    if ( (int)result < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
          3474,
          "SSFGetSspiInfo",
          "\r\n  HSE_REQ_GET_SSPI_INFO[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
          a1,
          result);
      return v9;
    }
  }
  else
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3451,
        "SSFGetSspiInfo",
        "\r\n"
        "  HSE_REQ_GET_SSPI_INFO[%p]: Parameter validation Failure\r\n"
        "    Context Handle Ptr: %p\r\n"
        "    Credential Handle Ptr: %p\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a2,
        a3);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007e70  push    rbx
0x180007e72  push    rsi
0x180007e73  push    rdi
0x180007e74  push    r14
0x180007e76  sub     rsp, 48h
0x180007e7a  mov     r10d, cs:g_dwDebugFlags
0x180007e81  mov     rbx, r8
0x180007e84  mov     r14, [rcx+0C0h]
0x180007e8b  test    r10b, 3
0x180007e8f  mov     rsi, rdx
0x180007e92  mov     rdi, rcx
0x180007e95  setnz   r9b
0x180007e99  bt      r10d, 1Ah
0x180007e9e  setb    al
0x180007ea1  test    al, r9b
0x180007ea4  jz      short loc_180007EDF
0x180007ea6  mov     [rsp+68h+var_40], rcx
0x180007eab  lea     rax, aHseReqGetSspiI; "\r\n  HSE_REQ_GET_SSPI_INFO[%p]: Functi"...
0x180007eb2  mov     rcx, cs:g_pDebug
0x180007eb9  lea     r9, aSsfgetsspiinfo; "SSFGetSspiInfo"
0x180007ec0  mov     r8d, 0D68h
0x180007ec6  mov     [rsp+68h+var_48], rax
0x180007ecb  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007ed2  call    cs:__imp_PuDbgPrint
0x180007ed8  mov     r10d, cs:g_dwDebugFlags
0x180007edf  test    rsi, rsi
0x180007ee2  jz      loc_180007F71
0x180007ee8  test    rbx, rbx
0x180007eeb  jz      loc_180007F71
0x180007ef1  mov     rax, [r14]
0x180007ef4  mov     r8d, 10h
0x180007efa  mov     r9, rsi
0x180007efd  mov     dword ptr [rsp+68h+var_48], r8d
0x180007f02  mov     rdx, rbx
0x180007f05  mov     rcx, r14
0x180007f08  mov     rax, [rax+88h]
0x180007f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f14  mov     ebx, eax
0x180007f16  test    eax, eax
0x180007f18  jns     loc_180007FC5
0x180007f1e  mov     ecx, cs:g_dwDebugFlags
0x180007f24  test    cl, 3
0x180007f27  setnz   r8b
0x180007f2b  bt      ecx, 14h
0x180007f2f  setb    cl
0x180007f32  test    cl, r8b
0x180007f35  jz      short loc_180007F6D
0x180007f37  mov     rcx, cs:g_pDebug
0x180007f3e  lea     r9, aSsfgetsspiinfo; "SSFGetSspiInfo"
0x180007f45  mov     dword ptr [rsp+68h+var_38], eax
0x180007f49  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007f50  lea     rax, aHseReqGetSspiI_1; "\r\n  HSE_REQ_GET_SSPI_INFO[%p]: Failed"...
0x180007f57  mov     [rsp+68h+var_40], rdi
0x180007f5c  mov     r8d, 0D92h
0x180007f62  mov     [rsp+68h+var_48], rax
0x180007f67  call    cs:__imp_PuDbgPrint
0x180007f6d  mov     eax, ebx
0x180007f6f  jmp     short loc_180007FC5
0x180007f71  test    r10b, 3
0x180007f75  setnz   cl
0x180007f78  bt      r10d, 14h
0x180007f7d  setb    al
0x180007f80  test    al, cl
0x180007f82  jz      short loc_180007FC0
0x180007f84  mov     rcx, cs:g_pDebug
0x180007f8b  lea     rax, aHseReqGetSspiI_0; "\r\n  HSE_REQ_GET_SSPI_INFO[%p]: Parame"...
0x180007f92  mov     [rsp+68h+var_30], rbx
0x180007f97  lea     r9, aSsfgetsspiinfo; "SSFGetSspiInfo"
0x180007f9e  mov     [rsp+68h+var_38], rsi
0x180007fa3  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007faa  mov     [rsp+68h+var_40], rdi
0x180007faf  mov     r8d, 0D7Bh
0x180007fb5  mov     [rsp+68h+var_48], rax
0x180007fba  call    cs:__imp_PuDbgPrint
0x180007fc0  mov     eax, 80070057h
0x180007fc5  add     rsp, 48h
0x180007fc9  pop     r14
0x180007fcb  pop     rdi
0x180007fcc  pop     rsi
0x180007fcd  pop     rbx
0x180007fce  retn
```
