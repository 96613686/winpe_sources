# SSFAsyncReadClient(ISAPI_CONTEXT *,void *,ulong *)

- ea: `0x180006588`
- end: `0x1800067dc`
- name: `?SSFAsyncReadClient@@YAJPEAVISAPI_CONTEXT@@PEAXPEAK@Z`
- size: `596`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *this, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180005e34`
- `0x180005ff4`
- `0x180006588`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006604`
- `iisutil!PuDbgPrint` at `0x1800066bd`
- `iisutil!PuDbgPrint` at `0x180006747`
- `iisutil!PuDbgPrint` at `0x1800067c4`
- `iisutil!PuDbgPrint` at `0x180006604`
- `iisutil!PuDbgPrint` at `0x1800066bd`
- `iisutil!PuDbgPrint` at `0x180006747`
- `iisutil!PuDbgPrint` at `0x1800067c4`

## string_xrefs

- `0x1800065b3`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800065f0`: `\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Function Entry\n    Bytes to Read: %d\n  <END>\n\n`
- `0x1800065a8`: `SSFAsyncReadClient`
- `0x180006634`: `\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Failed to get interface to server core\n  <END>\n\n`
- `0x1800067a6`: `\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Parameter validation failure\n    Completion Routine: %p\n    Buffer Ptr: %p\n    Buffer Size Ptr: %p\n    Buffer Size: %d\n  <END>\n\n`
- `0x180006699`: `\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Failed\n    Another async operation is already pending\n  <END>\n\n`
- `0x180006733`: `\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Failed\n    Error: 0x%08x\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall SSFAsyncReadClient(struct ISAPI_CONTEXT *this, void *a2, unsigned int *a3)
{
  int v4; // r8d
  int v7; // eax
  __int64 v8; // rsi
  const void *v9; // rdx
  int v10; // eax
  unsigned int v11; // edi
  int v13; // eax

  v4 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    if ( a3 )
      v7 = *a3;
    else
      v7 = 0;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      1174,
      "SSFAsyncReadClient",
      "\r\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Function Entry\r\n    Bytes to Read: %d\r\n  <END>\r\n\r\n",
      this,
      v7);
    v4 = g_dwDebugFlags;
  }
  v8 = *((_QWORD *)this + 24);
  if ( !v8 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1187,
        "SSFAsyncReadClient",
        "\r\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        this);
    return 2147942487LL;
  }
  v9 = (const void *)*((_QWORD *)this + 28);
  if ( !v9 || !a2 || !a3 || !*a3 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
    {
      if ( a3 )
        v13 = *a3;
      else
        v13 = 0;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1216,
        "SSFAsyncReadClient",
        "\r\n"
        "  HSE_REQ_ASYNC_READ_CLIENT[%p]: Parameter validation failure\r\n"
        "    Completion Routine: %p\r\n"
        "    Buffer Ptr: %p\r\n"
        "    Buffer Size Ptr: %p\r\n"
        "    Buffer Size: %d\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        v9,
        a2,
        a3,
        v13);
    }
    return 2147942487LL;
  }
  if ( !(unsigned int)ISAPI_CONTEXT::TryInitAsyncIo(this, 2) )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1235,
        "SSFAsyncReadClient",
        "\r\n"
        "  HSE_REQ_ASYNC_READ_CLIENT[%p]: Failed\r\n"
        "    Another async operation is already pending\r\n"
        "  <END>\r\n"
        "\r\n",
        this);
    return 2147942487LL;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, struct ISAPI_CONTEXT *, void *))(*(_QWORD *)v8 + 8LL))(v8, this, a2);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1269,
        "SSFAsyncReadClient",
        "\r\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        this,
        v10);
    *((_QWORD *)this + 30) = 0;
    *((_QWORD *)this + 27) = 0;
    ISAPI_CONTEXT::DereferenceIsapiContext(this);
  }
  return v11;
}

```

## disassembly

```asm
0x180006588  mov     rax, rsp
0x18000658b  push    rbx
0x18000658c  push    rbp
0x18000658d  push    rsi
0x18000658e  push    rdi
0x18000658f  push    r12
0x180006591  push    r13
0x180006593  sub     rsp, 58h
0x180006597  mov     rdi, r8
0x18000659a  mov     dword ptr [rax+8], 0
0x1800065a1  mov     r8d, cs:g_dwDebugFlags
0x1800065a8  lea     r12, aSsfasyncreadcl; "SSFAsyncReadClient"
0x1800065af  test    r8b, 3
0x1800065b3  lea     r13, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800065ba  mov     rbp, rdx
0x1800065bd  mov     rbx, rcx
0x1800065c0  setnz   r9b
0x1800065c4  bt      r8d, 1Ah
0x1800065c9  setb    al
0x1800065cc  test    al, r9b
0x1800065cf  jz      short loc_180006611
0x1800065d1  test    rdi, rdi
0x1800065d4  jz      short loc_1800065DA
0x1800065d6  mov     eax, [rdi]
0x1800065d8  jmp     short loc_1800065DC
0x1800065da  xor     eax, eax
0x1800065dc  mov     rcx, cs:g_pDebug
0x1800065e3  mov     r9, r12
0x1800065e6  mov     dword ptr [rsp+88h+var_58], eax
0x1800065ea  mov     r8d, 496h
0x1800065f0  lea     rax, aHseReqAsyncRea_3; "\r\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Fu"...
0x1800065f7  mov     [rsp+88h+var_60], rbx
0x1800065fc  mov     rdx, r13
0x1800065ff  mov     [rsp+88h+var_68], rax
0x180006604  call    cs:__imp_PuDbgPrint
0x18000660a  mov     r8d, cs:g_dwDebugFlags
0x180006611  mov     rsi, [rbx+0C0h]
0x180006618  test    rsi, rsi
0x18000661b  jnz     short loc_180006643
0x18000661d  test    r8b, 3
0x180006621  setnz   cl
0x180006624  bt      r8d, 14h
0x180006629  setb    al
0x18000662c  test    al, cl
0x18000662e  jz      loc_1800067CA
0x180006634  lea     rax, aHseReqAsyncRea_1; "\r\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Fa"...
0x18000663b  mov     r8d, 4A3h
0x180006641  jmp     short loc_1800066A6
0x180006643  mov     rdx, [rbx+0E0h]
0x18000664a  test    rdx, rdx
0x18000664d  jz      loc_18000676F
0x180006653  test    rbp, rbp
0x180006656  jz      loc_18000676F
0x18000665c  test    rdi, rdi
0x18000665f  jz      loc_18000676F
0x180006665  cmp     dword ptr [rdi], 0
0x180006668  jz      loc_18000676F
0x18000666e  mov     edx, 2
0x180006673  mov     rcx, rbx
0x180006676  call    ?TryInitAsyncIo@ISAPI_CONTEXT@@QEAAHW4ASYNC_PENDING@@@Z; ISAPI_CONTEXT::TryInitAsyncIo(ASYNC_PENDING)
0x18000667b  test    eax, eax
0x18000667d  jnz     short loc_1800066C8
0x18000667f  mov     eax, cs:g_dwDebugFlags
0x180006685  test    al, 3
0x180006687  setnz   cl
0x18000668a  bt      eax, 14h
0x18000668e  setb    al
0x180006691  test    al, cl
0x180006693  jz      loc_1800067CA
0x180006699  lea     rax, aHseReqAsyncRea_0; "\r\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Fa"...
0x1800066a0  mov     r8d, 4D3h
0x1800066a6  mov     rcx, cs:g_pDebug
0x1800066ad  mov     r9, r12
0x1800066b0  mov     [rsp+88h+var_60], rbx
0x1800066b5  mov     rdx, r13
0x1800066b8  mov     [rsp+88h+var_68], rax
0x1800066bd  call    cs:__imp_PuDbgPrint
0x1800066c3  jmp     loc_1800067CA
0x1800066c8  mov     r9d, [rdi]
0x1800066cb  lea     rcx, [rsp+88h+arg_0]
0x1800066d3  mov     [rsp+88h+arg_0], r9d
0x1800066db  mov     r8, rbp
0x1800066de  mov     rax, [rsi]
0x1800066e1  mov     rdx, rbx
0x1800066e4  mov     dword ptr [rsp+88h+var_58], 2
0x1800066ec  mov     [rsp+88h+var_60], rcx
0x1800066f1  mov     rcx, rsi
0x1800066f4  mov     dword ptr [rsp+88h+var_68], r9d
0x1800066f9  mov     rax, [rax+8]
0x1800066fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006702  mov     edi, eax
0x180006704  test    eax, eax
0x180006706  jns     short loc_18000676B
0x180006708  mov     ecx, cs:g_dwDebugFlags
0x18000670e  test    cl, 3
0x180006711  setnz   dl
0x180006714  bt      ecx, 14h
0x180006718  setb    cl
0x18000671b  test    cl, dl
0x18000671d  jz      short loc_18000674D
0x18000671f  mov     rcx, cs:g_pDebug
0x180006726  mov     r9, r12
0x180006729  mov     dword ptr [rsp+88h+var_58], eax
0x18000672d  mov     r8d, 4F5h
0x180006733  lea     rax, aHseReqAsyncRea; "\r\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Fa"...
0x18000673a  mov     [rsp+88h+var_60], rbx
0x18000673f  mov     rdx, r13
0x180006742  mov     [rsp+88h+var_68], rax
0x180006747  call    cs:__imp_PuDbgPrint
0x18000674d  mov     rcx, rbx; this
0x180006750  mov     qword ptr [rbx+0F0h], 0
0x18000675b  mov     qword ptr [rbx+0D8h], 0
0x180006766  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x18000676b  mov     eax, edi
0x18000676d  jmp     short loc_1800067CF
0x18000676f  test    r8b, 3
0x180006773  setnz   cl
0x180006776  bt      r8d, 14h
0x18000677b  setb    al
0x18000677e  test    al, cl
0x180006780  jz      short loc_1800067CA
0x180006782  test    rdi, rdi
0x180006785  jz      short loc_18000678B
0x180006787  mov     eax, [rdi]
0x180006789  jmp     short loc_18000678D
0x18000678b  xor     eax, eax
0x18000678d  mov     rcx, cs:g_pDebug
0x180006794  mov     r9, r12
0x180006797  mov     [rsp+88h+var_40], eax
0x18000679b  mov     r8d, 4C0h
0x1800067a1  mov     [rsp+88h+var_48], rdi
0x1800067a6  lea     rax, aHseReqAsyncRea_4; "\r\n  HSE_REQ_ASYNC_READ_CLIENT[%p]: Pa"...
0x1800067ad  mov     [rsp+88h+var_50], rbp
0x1800067b2  mov     [rsp+88h+var_58], rdx
0x1800067b7  mov     rdx, r13
0x1800067ba  mov     [rsp+88h+var_60], rbx
0x1800067bf  mov     [rsp+88h+var_68], rax
0x1800067c4  call    cs:__imp_PuDbgPrint
0x1800067ca  mov     eax, 80070057h
0x1800067cf  add     rsp, 58h
0x1800067d3  pop     r13
0x1800067d5  pop     r12
0x1800067d7  pop     rdi
0x1800067d8  pop     rsi
0x1800067d9  pop     rbp
0x1800067da  pop     rbx
0x1800067db  retn
```
