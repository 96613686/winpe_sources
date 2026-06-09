# SSFGetMetadataProperty(ISAPI_CONTEXT *,unsigned __int64,uchar *,ulong *)

- ea: `0x180007c50`
- end: `0x180007d96`
- name: `?SSFGetMetadataProperty@@YAJPEAVISAPI_CONTEXT@@_KPEAEPEAK@Z`
- size: `326`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, unsigned __int64, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180007c50`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007cb7`
- `iisutil!PuDbgPrint` at `0x180007d08`
- `iisutil!PuDbgPrint` at `0x180007d85`
- `iisutil!PuDbgPrint` at `0x180007cb7`
- `iisutil!PuDbgPrint` at `0x180007d08`
- `iisutil!PuDbgPrint` at `0x180007d85`

## string_xrefs

- `0x180007c9e`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007d01`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007d67`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFGetMetadataProperty(
        struct ISAPI_CONTEXT *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  int v4; // r11d
  int v10; // eax
  unsigned int v11; // edi

  v4 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      4283,
      "SSFGetMetadataProperty",
      "\r\n  HSE_REQ_GET_METADATA_PROPERTY[%p]: Function Entry\r\n    PropertyID: 0x%08x (%d)\r\n  <END>\r\n\r\n",
      a1,
      a2,
      a2);
    v4 = g_dwDebugFlags;
  }
  if ( a4 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int8 *, _QWORD, unsigned int *))(**((_QWORD **)a1 + 24)
                                                                                               + 184LL))(
            *((_QWORD *)a1 + 24),
            a2,
            a3,
            *a4,
            a4);
    v11 = v10;
    if ( v10 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4319,
        "SSFGetMetadataProperty",
        "\r\n  HSE_REQ_GET_METADATA_PROPERTY[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        v10);
    return v11;
  }
  else
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        4298,
        "SSFGetMetadataProperty",
        "\r\n"
        "  HSE_REQ_GET_METADATA_PROPERTY[%p]: Parameter validation failure\r\n"
        "    Buffer Ptr: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180007c50  push    rbx
0x180007c52  push    rbp
0x180007c53  push    rsi
0x180007c54  push    rdi
0x180007c55  sub     rsp, 48h
0x180007c59  mov     r11d, cs:g_dwDebugFlags
0x180007c60  mov     rsi, r9
0x180007c63  test    r11b, 3
0x180007c67  mov     rbp, r8
0x180007c6a  mov     rdi, rdx
0x180007c6d  mov     rbx, rcx
0x180007c70  setnz   r10b
0x180007c74  bt      r11d, 1Ah
0x180007c79  setb    al
0x180007c7c  test    al, r10b
0x180007c7f  jz      short loc_180007CC4
0x180007c81  mov     [rsp+68h+var_30], rdx
0x180007c86  lea     rax, aHseReqGetMetad_2; "\r\n  HSE_REQ_GET_METADATA_PROPERTY[%p]"...
0x180007c8d  mov     [rsp+68h+var_38], rdx
0x180007c92  lea     r9, aSsfgetmetadata; "SSFGetMetadataProperty"
0x180007c99  mov     [rsp+68h+var_40], rcx
0x180007c9e  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007ca5  mov     rcx, cs:g_pDebug
0x180007cac  mov     r8d, 10BBh
0x180007cb2  mov     [rsp+68h+var_48], rax
0x180007cb7  call    cs:__imp_PuDbgPrint
0x180007cbd  mov     r11d, cs:g_dwDebugFlags
0x180007cc4  test    rsi, rsi
0x180007cc7  jnz     short loc_180007D15
0x180007cc9  test    r11b, 3
0x180007ccd  setnz   cl
0x180007cd0  bt      r11d, 14h
0x180007cd5  setb    al
0x180007cd8  test    al, cl
0x180007cda  jz      short loc_180007D0E
0x180007cdc  mov     rcx, cs:g_pDebug
0x180007ce3  lea     rax, aHseReqGetMetad_1; "\r\n  HSE_REQ_GET_METADATA_PROPERTY[%p]"...
0x180007cea  mov     [rsp+68h+var_40], rbx
0x180007cef  lea     r9, aSsfgetmetadata; "SSFGetMetadataProperty"
0x180007cf6  mov     r8d, 10CAh
0x180007cfc  mov     [rsp+68h+var_48], rax
0x180007d01  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007d08  call    cs:__imp_PuDbgPrint
0x180007d0e  mov     eax, 80070057h
0x180007d13  jmp     short loc_180007D8D
0x180007d15  mov     rcx, [rbx+0C0h]
0x180007d1c  mov     edx, edi
0x180007d1e  mov     r9d, [rsi]
0x180007d21  mov     r8, rbp
0x180007d24  mov     [rsp+68h+var_48], rsi
0x180007d29  mov     rax, [rcx]
0x180007d2c  mov     rax, [rax+0B8h]
0x180007d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d38  mov     edi, eax
0x180007d3a  test    eax, eax
0x180007d3c  jns     short loc_180007D8B
0x180007d3e  mov     ecx, cs:g_dwDebugFlags
0x180007d44  test    cl, 3
0x180007d47  setnz   dl
0x180007d4a  bt      ecx, 14h
0x180007d4e  setb    cl
0x180007d51  test    cl, dl
0x180007d53  jz      short loc_180007D8B
0x180007d55  mov     rcx, cs:g_pDebug
0x180007d5c  lea     r9, aSsfgetmetadata; "SSFGetMetadataProperty"
0x180007d63  mov     dword ptr [rsp+68h+var_38], eax
0x180007d67  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007d6e  lea     rax, aHseReqGetMetad; "\r\n  HSE_REQ_GET_METADATA_PROPERTY[%p]"...
0x180007d75  mov     [rsp+68h+var_40], rbx
0x180007d7a  mov     r8d, 10DFh
0x180007d80  mov     [rsp+68h+var_48], rax
0x180007d85  call    cs:__imp_PuDbgPrint
0x180007d8b  mov     eax, edi
0x180007d8d  add     rsp, 48h
0x180007d91  pop     rdi
0x180007d92  pop     rsi
0x180007d93  pop     rbp
0x180007d94  pop     rbx
0x180007d95  retn
```
