# W3_CGI_HANDLER::OnCompletion(ulong,long)

- ea: `0x180004678`
- end: `0x1800047db`
- name: `?OnCompletion@W3_CGI_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KJ@Z`
- size: `355`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000259c`

## callees

- `0x180002c18`
- `0x18000337c`
- `0x180004678`
- `0x180005914`
- `0x180008010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800046d8`
- `iisutil!PuDbgPrint` at `0x1800046d8`

## string_xrefs

- `0x1800046d1`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x1800046b3`: `Error %x on CGI_HANDLER::OnCompletion\n`
- `0x1800046bf`: `W3_CGI_HANDLER::OnCompletion`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::OnCompletion(__int64 a1, int a2, int a3)
{
  int v6; // edi
  int v7; // esi
  __int64 v8; // rax
  __int64 v9; // rdi
  const char *v10; // r8
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-48h]

  if ( *(_DWORD *)(a1 + 8392) )
    return W3_CGI_HANDLER::DoWork(a1);
  v6 = 0;
  if ( a3 < 0 )
  {
    v6 = a3;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
        1794,
        "W3_CGI_HANDLER::OnCompletion",
        "Error %x on CGI_HANDLER::OnCompletion\n",
        a3);
  }
  v7 = 0;
  if ( v6 != -2147024858 )
    v7 = v6;
  v8 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 48) + 32LL))(*(_QWORD *)(a1 + 48));
  v9 = v8;
  if ( v7 < 0 )
  {
    if ( v7 == -2147024888 )
    {
      v10 = "Internal Server Error";
      v11 = 500;
      v12 = -2147024888;
      goto LABEL_20;
    }
LABEL_18:
    if ( *(_DWORD *)(a1 + 8) != 1 )
      goto LABEL_21;
    v10 = "Bad Request";
    v11 = 400;
    v12 = v7;
LABEL_20:
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v8 + 24LL))(
      v8,
      v11,
      v10,
      0,
      v12,
      0,
      0);
    goto LABEL_21;
  }
  if ( *(_DWORD *)(a1 + 8) == 4 )
    goto LABEL_18;
  if ( *(_DWORD *)(a1 + 8) == 1 )
  {
    *(_DWORD *)(a1 + 60) -= a2;
    *(_DWORD *)(a1 + 8304) = a2;
  }
  if ( (int)W3_CGI_HANDLER::CGIContinueOnClientCompletion((W3_CGI_HANDLER *)a1) >= 0 )
    return 1;
  if ( (unsigned int)(*(_DWORD *)(a1 + 8) - 3) > 1 )
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v9 + 24LL))(
      v9,
      502,
      "Bad Gateway",
      2,
      0,
      0,
      0);
LABEL_21:
  W3_CGI_HANDLER::SetCgiStateDoneWithRequest((W3_CGI_HANDLER *)a1);
  return 0;
}

```

## disassembly

```asm
0x180004678  push    rbx
0x18000467a  push    rbp
0x18000467b  push    rsi
0x18000467c  push    rdi
0x18000467d  sub     rsp, 48h
0x180004681  cmp     dword ptr [rcx+20C8h], 0
0x180004688  mov     ebp, edx
0x18000468a  mov     rbx, rcx
0x18000468d  jz      short loc_180004699
0x18000468f  call    ?DoWork@W3_CGI_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; W3_CGI_HANDLER::DoWork(void)
0x180004694  jmp     loc_1800047D2
0x180004699  xor     edi, edi
0x18000469b  test    r8d, r8d
0x18000469e  jns     short loc_1800046DE
0x1800046a0  test    cs:g_dwDebugFlags, 3
0x1800046a7  mov     edi, r8d
0x1800046aa  jz      short loc_1800046DE
0x1800046ac  mov     rcx, cs:g_pDebug
0x1800046b3  lea     rax, aErrorXOnCgiHan; "Error %x on CGI_HANDLER::OnCompletion\n"
0x1800046ba  mov     dword ptr [rsp+68h+var_40], r8d
0x1800046bf  lea     r9, aW3CgiHandlerOn_0; "W3_CGI_HANDLER::OnCompletion"
0x1800046c6  mov     r8d, 702h
0x1800046cc  mov     [rsp+68h+var_48], rax
0x1800046d1  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800046d8  call    cs:__imp_PuDbgPrint
0x1800046de  mov     rcx, [rbx+30h]
0x1800046e2  xor     esi, esi
0x1800046e4  cmp     edi, 80070026h
0x1800046ea  cmovnz  esi, edi
0x1800046ed  mov     rax, [rcx]
0x1800046f0  mov     rax, [rax+20h]
0x1800046f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046f9  mov     rdi, rax
0x1800046fc  test    esi, esi
0x1800046fe  js      short loc_18000476E
0x180004700  cmp     dword ptr [rbx+8], 4
0x180004704  jz      loc_180004796
0x18000470a  cmp     dword ptr [rbx+8], 1
0x18000470e  jnz     short loc_180004719
0x180004710  sub     [rbx+3Ch], ebp
0x180004713  mov     [rbx+2070h], ebp
0x180004719  mov     rcx, rbx; this
0x18000471c  call    ?CGIContinueOnClientCompletion@W3_CGI_HANDLER@@AEAAJXZ; W3_CGI_HANDLER::CGIContinueOnClientCompletion(void)
0x180004721  test    eax, eax
0x180004723  js      short loc_18000472F
0x180004725  mov     eax, 1
0x18000472a  jmp     loc_1800047D2
0x18000472f  mov     eax, [rbx+8]
0x180004732  sub     eax, 3
0x180004735  cmp     eax, 1
0x180004738  jbe     loc_1800047C8
0x18000473e  mov     rax, [rdi]
0x180004741  lea     r8, aBadGateway; "Bad Gateway"
0x180004748  mov     [rsp+68h+var_38], 0
0x180004750  mov     edx, 1F6h
0x180004755  mov     [rsp+68h+var_40], 0
0x18000475e  mov     r9d, 2
0x180004764  mov     dword ptr [rsp+68h+var_48], 0
0x18000476c  jmp     short loc_1800047BC
0x18000476e  mov     ecx, 80070008h
0x180004773  cmp     esi, ecx
0x180004775  jnz     short loc_180004796
0x180004777  xor     r9d, r9d
0x18000477a  lea     r8, aInternalServer; "Internal Server Error"
0x180004781  mov     [rsp+68h+var_38], r9d
0x180004786  mov     edx, 1F4h
0x18000478b  mov     [rsp+68h+var_40], r9
0x180004790  mov     dword ptr [rsp+68h+var_48], ecx
0x180004794  jmp     short loc_1800047B9
0x180004796  cmp     dword ptr [rbx+8], 1
0x18000479a  jnz     short loc_1800047C8
0x18000479c  xor     r9d, r9d
0x18000479f  lea     r8, aBadRequest; "Bad Request"
0x1800047a6  mov     [rsp+68h+var_38], r9d
0x1800047ab  mov     edx, 190h
0x1800047b0  mov     [rsp+68h+var_40], r9
0x1800047b5  mov     dword ptr [rsp+68h+var_48], esi
0x1800047b9  mov     rax, [rax]
0x1800047bc  mov     rax, [rax+18h]
0x1800047c0  mov     rcx, rdi
0x1800047c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c8  mov     rcx, rbx; this
0x1800047cb  call    ?SetCgiStateDoneWithRequest@W3_CGI_HANDLER@@QEAAJXZ; W3_CGI_HANDLER::SetCgiStateDoneWithRequest(void)
0x1800047d0  xor     eax, eax
0x1800047d2  add     rsp, 48h
0x1800047d6  pop     rdi
0x1800047d7  pop     rsi
0x1800047d8  pop     rbp
0x1800047d9  pop     rbx
0x1800047da  retn
```
