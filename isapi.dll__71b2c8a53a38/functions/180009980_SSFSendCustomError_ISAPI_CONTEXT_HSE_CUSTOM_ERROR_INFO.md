# SSFSendCustomError(ISAPI_CONTEXT *,_HSE_CUSTOM_ERROR_INFO *)

- ea: `0x180009980`
- end: `0x180009b81`
- name: `?SSFSendCustomError@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_CUSTOM_ERROR_INFO@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *this, struct _HSE_CUSTOM_ERROR_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180005e34`
- `0x180005ff4`
- `0x180009980`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800099f8`
- `iisutil!PuDbgPrint` at `0x180009ade`
- `iisutil!PuDbgPrint` at `0x180009b55`
- `iisutil!PuDbgPrint` at `0x1800099f8`
- `iisutil!PuDbgPrint` at `0x180009ade`
- `iisutil!PuDbgPrint` at `0x180009b55`

## string_xrefs

- `0x18000999c`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180009aba`: `\n  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Failed\n    Another async operation is already pending\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFSendCustomError(struct ISAPI_CONTEXT *this, struct _HSE_CUSTOM_ERROR_INFO *a2)
{
  int v3; // edx
  CHAR *pszStatus; // rax
  int uHttpSubError; // ecx
  __int64 v7; // rsi
  int v9; // eax
  unsigned int v10; // esi

  v3 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    if ( a2 )
    {
      pszStatus = a2->pszStatus;
      uHttpSubError = a2->uHttpSubError;
    }
    else
    {
      pszStatus = 0;
      uHttpSubError = 0;
    }
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      2625,
      "SSFSendCustomError",
      "\r\n"
      "  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Function Entry\r\n"
      "    Status: '%s'\r\n"
      "    SubError Code: %d\r\n"
      "  <END>\r\n"
      "\r\n",
      this,
      pszStatus,
      uHttpSubError);
    v3 = g_dwDebugFlags;
  }
  v7 = *((_QWORD *)this + 24);
  if ( !v7 )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2638,
        "SSFSendCustomError",
        "\r\n  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        this);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2653,
        "SSFSendCustomError",
        "\r\n"
        "  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Parameter validation failure\r\n"
        "    Custom Error Info Ptr: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
    return 2147942487LL;
  }
  if ( a2->pszStatus && !*a2->pszStatus )
  {
    if ( (v3 & 3) != 0 && (v3 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2674,
        "SSFSendCustomError",
        "\r\n"
        "  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Parameter validation failure\r\n"
        "    Status is an empty string\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
    return 2147942487LL;
  }
  if ( a2->fAsync && !(unsigned int)ISAPI_CONTEXT::TryInitAsyncIo(this, 3) )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2696,
        "SSFSendCustomError",
        "\r\n"
        "  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Failed\r\n"
        "    Another async operation is already pending\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
    return 2147942487LL;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, CHAR *, _QWORD))(*(_QWORD *)v7 + 104LL))(
         v7,
         (unsigned __int64)this & -(__int64)a2->fAsync,
         a2->pszStatus,
         a2->uHttpSubError);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        2718,
        "SSFSendCustomError",
        "\r\n  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        this,
        v9);
    if ( a2->fAsync )
    {
      *((_DWORD *)this + 54) = 0;
      ISAPI_CONTEXT::DereferenceIsapiContext(this);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180009980  push    rbx
0x180009982  push    rsi
0x180009983  push    rdi
0x180009984  push    r12
0x180009986  push    r15
0x180009988  sub     rsp, 40h
0x18000998c  mov     rdi, rdx
0x18000998f  lea     r15, aSsfsendcustome; "SSFSendCustomError"
0x180009996  mov     edx, cs:g_dwDebugFlags
0x18000999c  lea     r12, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800099a3  test    dl, 3
0x1800099a6  mov     rbx, rcx
0x1800099a9  setnz   r8b
0x1800099ad  bt      edx, 1Ah
0x1800099b1  setb    al
0x1800099b4  test    al, r8b
0x1800099b7  jz      short loc_180009A04
0x1800099b9  test    rdi, rdi
0x1800099bc  jz      short loc_1800099C7
0x1800099be  mov     rax, [rdi]
0x1800099c1  movzx   ecx, word ptr [rdi+8]
0x1800099c5  jmp     short loc_1800099CB
0x1800099c7  xor     eax, eax
0x1800099c9  xor     ecx, ecx
0x1800099cb  mov     [rsp+68h+var_30], ecx
0x1800099cf  mov     r9, r15
0x1800099d2  mov     rcx, cs:g_pDebug
0x1800099d9  mov     r8d, 0A41h
0x1800099df  mov     [rsp+68h+var_38], rax
0x1800099e4  mov     rdx, r12
0x1800099e7  lea     rax, aHseReqSendCust_2; "\r\n  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Fu"...
0x1800099ee  mov     [rsp+68h+var_40], rbx
0x1800099f3  mov     [rsp+68h+var_48], rax
0x1800099f8  call    cs:__imp_PuDbgPrint
0x1800099fe  mov     edx, cs:g_dwDebugFlags
0x180009a04  mov     rsi, [rbx+0C0h]
0x180009a0b  test    rsi, rsi
0x180009a0e  jnz     short loc_180009A37
0x180009a10  test    dl, 3
0x180009a13  setnz   cl
0x180009a16  bt      edx, 14h
0x180009a1a  setb    al
0x180009a1d  test    al, cl
0x180009a1f  jz      loc_180009AE4
0x180009a25  lea     rax, aHseReqSendCust_0; "\r\n  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Fa"...
0x180009a2c  mov     r8d, 0A4Eh
0x180009a32  jmp     loc_180009AC7
0x180009a37  test    rdi, rdi
0x180009a3a  jnz     short loc_180009A60
0x180009a3c  test    dl, 3
0x180009a3f  setnz   cl
0x180009a42  bt      edx, 14h
0x180009a46  setb    al
0x180009a49  test    al, cl
0x180009a4b  jz      loc_180009AE4
0x180009a51  lea     rax, aHseReqSendCust_4; "\r\n  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Pa"...
0x180009a58  mov     r8d, 0A5Dh
0x180009a5e  jmp     short loc_180009AC7
0x180009a60  mov     rax, [rdi]
0x180009a63  test    rax, rax
0x180009a66  jz      short loc_180009A8D
0x180009a68  cmp     byte ptr [rax], 0
0x180009a6b  jnz     short loc_180009A8D
0x180009a6d  test    dl, 3
0x180009a70  setnz   cl
0x180009a73  bt      edx, 14h
0x180009a77  setb    al
0x180009a7a  test    al, cl
0x180009a7c  jz      short loc_180009AE4
0x180009a7e  lea     rax, aHseReqSendCust_1; "\r\n  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Pa"...
0x180009a85  mov     r8d, 0A72h
0x180009a8b  jmp     short loc_180009AC7
0x180009a8d  cmp     dword ptr [rdi+0Ch], 0
0x180009a91  jz      short loc_180009AEE
0x180009a93  mov     edx, 3
0x180009a98  mov     rcx, rbx
0x180009a9b  call    ?TryInitAsyncIo@ISAPI_CONTEXT@@QEAAHW4ASYNC_PENDING@@@Z; ISAPI_CONTEXT::TryInitAsyncIo(ASYNC_PENDING)
0x180009aa0  test    eax, eax
0x180009aa2  jnz     short loc_180009AEE
0x180009aa4  mov     eax, cs:g_dwDebugFlags
0x180009aaa  test    al, 3
0x180009aac  setnz   cl
0x180009aaf  bt      eax, 14h
0x180009ab3  setb    al
0x180009ab6  test    al, cl
0x180009ab8  jz      short loc_180009AE4
0x180009aba  lea     rax, aHseReqSendCust_3; "\r\n  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Fa"...
0x180009ac1  mov     r8d, 0A88h
0x180009ac7  mov     rcx, cs:g_pDebug
0x180009ace  mov     r9, r15
0x180009ad1  mov     [rsp+68h+var_40], rbx
0x180009ad6  mov     rdx, r12
0x180009ad9  mov     [rsp+68h+var_48], rax
0x180009ade  call    cs:__imp_PuDbgPrint
0x180009ae4  mov     eax, 80070057h
0x180009ae9  jmp     loc_180009B75
0x180009aee  mov     eax, [rdi+0Ch]
0x180009af1  mov     rcx, rsi
0x180009af4  mov     r8, [rsi]
0x180009af7  neg     eax
0x180009af9  movzx   r9d, word ptr [rdi+8]
0x180009afe  sbb     rdx, rdx
0x180009b01  and     rdx, rbx
0x180009b04  mov     rax, [r8+68h]
0x180009b08  mov     r8, [rdi]
0x180009b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b10  mov     esi, eax
0x180009b12  test    eax, eax
0x180009b14  jns     short loc_180009B73
0x180009b16  mov     ecx, cs:g_dwDebugFlags
0x180009b1c  test    cl, 3
0x180009b1f  setnz   dl
0x180009b22  bt      ecx, 14h
0x180009b26  setb    cl
0x180009b29  test    cl, dl
0x180009b2b  jz      short loc_180009B5B
0x180009b2d  mov     rcx, cs:g_pDebug
0x180009b34  mov     r9, r15
0x180009b37  mov     dword ptr [rsp+68h+var_38], eax
0x180009b3b  mov     r8d, 0A9Eh
0x180009b41  lea     rax, aHseReqSendCust; "\r\n  HSE_REQ_SEND_CUSTOM_ERROR[%p]: Fa"...
0x180009b48  mov     [rsp+68h+var_40], rbx
0x180009b4d  mov     rdx, r12
0x180009b50  mov     [rsp+68h+var_48], rax
0x180009b55  call    cs:__imp_PuDbgPrint
0x180009b5b  cmp     dword ptr [rdi+0Ch], 0
0x180009b5f  jz      short loc_180009B73
0x180009b61  mov     rcx, rbx; this
0x180009b64  mov     dword ptr [rbx+0D8h], 0
0x180009b6e  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x180009b73  mov     eax, esi
0x180009b75  add     rsp, 40h
0x180009b79  pop     r15
0x180009b7b  pop     r12
0x180009b7d  pop     rdi
0x180009b7e  pop     rsi
0x180009b7f  pop     rbx
0x180009b80  retn
```
