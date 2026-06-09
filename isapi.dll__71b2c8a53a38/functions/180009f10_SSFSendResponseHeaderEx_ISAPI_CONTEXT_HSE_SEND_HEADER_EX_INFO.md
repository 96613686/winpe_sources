# SSFSendResponseHeaderEx(ISAPI_CONTEXT *,_HSE_SEND_HEADER_EX_INFO *)

- ea: `0x180009f10`
- end: `0x18000a0f9`
- name: `?SSFSendResponseHeaderEx@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_SEND_HEADER_EX_INFO@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct _HSE_SEND_HEADER_EX_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180009f10`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180009f88`
- `iisutil!PuDbgPrint` at `0x180009fff`
- `iisutil!PuDbgPrint` at `0x18000a093`
- `iisutil!PuDbgPrint` at `0x18000a0e3`
- `iisutil!PuDbgPrint` at `0x180009f88`
- `iisutil!PuDbgPrint` at `0x180009fff`
- `iisutil!PuDbgPrint` at `0x18000a093`
- `iisutil!PuDbgPrint` at `0x18000a0e3`

## string_xrefs

- `0x180009f32`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFSendResponseHeaderEx(struct ISAPI_CONTEXT *a1, struct _HSE_SEND_HEADER_EX_INFO *a2)
{
  int v2; // r9d
  __int64 v5; // rcx
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // edi

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      188,
      "SSFSendResponseHeaderEx",
      "\r\n"
      "  HSE_REQ_SEND_RESPONSE_HEADER_EX[%p]: Function Entry\r\n"
      "    Status: '%s'\r\n"
      "    Headers: '%s'\r\n"
      "    KeepConn: %d\r\n",
      a1,
      a2->pszStatus,
      a2->pszHeader,
      a2->fKeepConn);
    v2 = g_dwDebugFlags;
  }
  v5 = *((_QWORD *)a1 + 24);
  if ( !v5 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        201,
        "SSFSendResponseHeaderEx",
        "\r\n  HSE_REQ_SEND_RESPONSE_HEADER_EX[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        220,
        "SSFSendResponseHeaderEx",
        "\r\n"
        "  HSE_REQ_SEND_RESPONSE_HEADER_EX[%p]: Parameter validation failure\r\n"
        "    pHeaderInfo: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
    return 2147942487LL;
  }
  if ( a2->fKeepConn && *((_DWORD *)a1 + 62) )
    *((_DWORD *)a1 + 63) = 1;
  v7 = (*(__int64 (__fastcall **)(__int64, bool, LPCSTR, LPCSTR, int))(*(_QWORD *)v5 + 24LL))(
         v5,
         *((_DWORD *)a1 + 63) == 0,
         a2->pszStatus,
         a2->pszHeader,
         1);
  v8 = g_dwDebugFlags;
  v9 = v7;
  if ( v7 >= 0 )
  {
    *((_DWORD *)a1 + 64) = 1;
    if ( (v8 & 0x4000000) != 0 && (v8 & 3) != 0 && (v8 & 0x200000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        278,
        "SSFSendResponseHeaderEx",
        "\r\n  HSE_REQ_SEND_RESPONSE_HEADER_EX[%p]: Succeeded\r\n  <END>\r\n",
        a1);
  }
  else if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      260,
      "SSFSendResponseHeaderEx",
      "\r\n  HSE_REQ_SEND_RESPONSE_HEADER_EX[%p]: Failed.\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v7);
  }
  return v9;
}

```

## disassembly

```asm
0x180009f10  mov     r11, rsp
0x180009f13  push    rbx
0x180009f14  push    rsi
0x180009f15  push    rdi
0x180009f16  push    r12
0x180009f18  push    r14
0x180009f1a  push    r15
0x180009f1c  sub     rsp, 58h
0x180009f20  mov     r9d, cs:g_dwDebugFlags
0x180009f27  lea     r15, aSsfsendrespons_0; "SSFSendResponseHeaderEx"
0x180009f2e  test    r9b, 3
0x180009f32  lea     r12, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009f39  mov     rsi, rdx
0x180009f3c  mov     rbx, rcx
0x180009f3f  setnz   r8b
0x180009f43  bt      r9d, 1Ah
0x180009f48  setb    al
0x180009f4b  test    al, r8b
0x180009f4e  jz      short loc_180009F95
0x180009f50  mov     eax, [rdx+18h]
0x180009f53  mov     r9, r15
0x180009f56  mov     [rsp+88h+var_48], eax
0x180009f5a  mov     r8d, 0BCh
0x180009f60  mov     rax, [rdx+8]
0x180009f64  mov     [r11-50h], rax
0x180009f68  mov     rax, [rdx]
0x180009f6b  mov     rdx, r12
0x180009f6e  mov     [r11-58h], rax
0x180009f72  lea     rax, aHseReqSendResp_0; "\r\n  HSE_REQ_SEND_RESPONSE_HEADER_EX[%"...
0x180009f79  mov     [r11-60h], rcx
0x180009f7d  mov     rcx, cs:g_pDebug
0x180009f84  mov     [r11-68h], rax
0x180009f88  call    cs:__imp_PuDbgPrint
0x180009f8e  mov     r9d, cs:g_dwDebugFlags
0x180009f95  mov     rcx, [rbx+0C0h]
0x180009f9c  test    rcx, rcx
0x180009f9f  jnz     short loc_180009FC3
0x180009fa1  test    r9b, 3
0x180009fa5  setnz   cl
0x180009fa8  bt      r9d, 14h
0x180009fad  setb    al
0x180009fb0  test    al, cl
0x180009fb2  jz      short loc_18000A005
0x180009fb4  lea     rax, aHseReqSendResp_7; "\r\n  HSE_REQ_SEND_RESPONSE_HEADER_EX[%"...
0x180009fbb  mov     r8d, 0C9h
0x180009fc1  jmp     short loc_180009FE8
0x180009fc3  test    rsi, rsi
0x180009fc6  jnz     short loc_18000A00F
0x180009fc8  test    r9b, 3
0x180009fcc  setnz   cl
0x180009fcf  bt      r9d, 14h
0x180009fd4  setb    al
0x180009fd7  test    al, cl
0x180009fd9  jz      short loc_18000A005
0x180009fdb  lea     rax, aHseReqSendResp_6; "\r\n  HSE_REQ_SEND_RESPONSE_HEADER_EX[%"...
0x180009fe2  mov     r8d, 0DCh
0x180009fe8  mov     rcx, cs:g_pDebug
0x180009fef  mov     r9, r15
0x180009ff2  mov     [rsp+88h+var_60], rbx
0x180009ff7  mov     rdx, r12
0x180009ffa  mov     [rsp+88h+var_68], rax
0x180009fff  call    cs:__imp_PuDbgPrint
0x18000a005  mov     eax, 80070057h
0x18000a00a  jmp     loc_18000A0EB
0x18000a00f  cmp     dword ptr [rsi+18h], 0
0x18000a013  mov     r8d, 1
0x18000a019  jz      short loc_18000A02B
0x18000a01b  cmp     dword ptr [rbx+0F8h], 0
0x18000a022  jz      short loc_18000A02B
0x18000a024  mov     [rbx+0FCh], r8d
0x18000a02b  mov     rax, [rcx]
0x18000a02e  xor     edx, edx
0x18000a030  cmp     [rbx+0FCh], edx
0x18000a036  mov     r9, [rsi+8]
0x18000a03a  mov     dword ptr [rsp+88h+var_68], r8d
0x18000a03f  setz    dl
0x18000a042  mov     rax, [rax+18h]
0x18000a046  mov     r8, [rsi]
0x18000a049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a04e  mov     ecx, cs:g_dwDebugFlags
0x18000a054  mov     edi, eax
0x18000a056  test    eax, eax
0x18000a058  jns     short loc_18000A09B
0x18000a05a  test    cl, 3
0x18000a05d  setnz   dl
0x18000a060  bt      ecx, 14h
0x18000a064  setb    cl
0x18000a067  test    cl, dl
0x18000a069  jz      short loc_18000A0E9
0x18000a06b  mov     rcx, cs:g_pDebug
0x18000a072  mov     r9, r15
0x18000a075  mov     [rsp+88h+var_58], eax
0x18000a079  mov     r8d, 104h
0x18000a07f  lea     rax, aHseReqSendResp_2; "\r\n  HSE_REQ_SEND_RESPONSE_HEADER_EX[%"...
0x18000a086  mov     [rsp+88h+var_60], rbx
0x18000a08b  mov     rdx, r12
0x18000a08e  mov     [rsp+88h+var_68], rax
0x18000a093  call    cs:__imp_PuDbgPrint
0x18000a099  jmp     short loc_18000A0E9
0x18000a09b  test    cl, 3
0x18000a09e  mov     dword ptr [rbx+100h], 1
0x18000a0a8  setnz   dl
0x18000a0ab  bt      ecx, 1Ah
0x18000a0af  setb    al
0x18000a0b2  and     dl, al
0x18000a0b4  bt      ecx, 15h
0x18000a0b8  setb    al
0x18000a0bb  test    al, dl
0x18000a0bd  jz      short loc_18000A0E9
0x18000a0bf  mov     rcx, cs:g_pDebug
0x18000a0c6  lea     rax, aHseReqSendResp_9; "\r\n  HSE_REQ_SEND_RESPONSE_HEADER_EX[%"...
0x18000a0cd  mov     [rsp+88h+var_60], rbx
0x18000a0d2  mov     r9, r15
0x18000a0d5  mov     r8d, 116h
0x18000a0db  mov     [rsp+88h+var_68], rax
0x18000a0e0  mov     rdx, r12
0x18000a0e3  call    cs:__imp_PuDbgPrint
0x18000a0e9  mov     eax, edi
0x18000a0eb  add     rsp, 58h
0x18000a0ef  pop     r15
0x18000a0f1  pop     r14
0x18000a0f3  pop     r12
0x18000a0f5  pop     rdi
0x18000a0f6  pop     rsi
0x18000a0f7  pop     rbx
0x18000a0f8  retn
```
