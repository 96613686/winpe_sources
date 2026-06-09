# SSFGetCertInfoEx(ISAPI_CONTEXT *,_CERT_CONTEXT_EX *)

- ea: `0x18000750c`
- end: `0x180007678`
- name: `?SSFGetCertInfoEx@@YAJPEAVISAPI_CONTEXT@@PEAU_CERT_CONTEXT_EX@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct _CERT_CONTEXT_EX *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x18000750c`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007564`
- `iisutil!PuDbgPrint` at `0x1800075e3`
- `iisutil!PuDbgPrint` at `0x180007665`
- `iisutil!PuDbgPrint` at `0x180007564`
- `iisutil!PuDbgPrint` at `0x1800075e3`
- `iisutil!PuDbgPrint` at `0x180007665`

## string_xrefs

- `0x18000755d`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800075d7`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x180007647`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFGetCertInfoEx(struct ISAPI_CONTEXT *a1, struct _CERT_CONTEXT_EX *a2)
{
  int v2; // r9d
  __int64 v5; // rcx
  int v7; // eax
  unsigned int v8; // edi

  v2 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      1003,
      "SSFGetCertInfoEx",
      "\r\n  HSE_REQ_GET_CERT_INFO_EX[%p]: Function Entry\r\n  <END>\r\n\r\n",
      a1);
    v2 = g_dwDebugFlags;
  }
  v5 = *((_QWORD *)a1 + 24);
  if ( !v5 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1016,
        "SSFGetCertInfoEx",
        "\r\n  HSE_REQ_GET_CERT_INFO_EX[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    if ( (v2 & 3) != 0 && (v2 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        1035,
        "SSFGetCertInfoEx",
        "\r\n"
        "  HSE_REQ_GET_CERT_INFO_EX[%p]: Parameter validation failure\r\n"
        "    CertContext Ptr: NULL\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
    return 2147942487LL;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _CERT_CONTEXT_EX *, BYTE *, DWORD *, DWORD *))(*(_QWORD *)v5 + 72LL))(
         v5,
         a2->cbAllocated,
         a2,
         a2->CertContext.pbCertEncoded,
         &a2->CertContext.cbCertEncoded,
         &a2->dwCertificateFlags);
  v8 = v7;
  if ( v7 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      1058,
      "SSFGetCertInfoEx",
      "\r\n  HSE_REQ_GET_CERT_INFO_EX[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v7);
  return v8;
}

```

## disassembly

```asm
0x18000750c  mov     [rsp+arg_0], rbx
0x180007511  push    rdi
0x180007512  sub     rsp, 40h
0x180007516  mov     r9d, cs:g_dwDebugFlags
0x18000751d  mov     rdi, rdx
0x180007520  test    r9b, 3
0x180007524  mov     rbx, rcx
0x180007527  setnz   r8b
0x18000752b  bt      r9d, 1Ah
0x180007530  setb    al
0x180007533  test    al, r8b
0x180007536  jz      short loc_180007571
0x180007538  mov     [rsp+48h+var_20], rcx
0x18000753d  lea     rax, aHseReqGetCertI_1; "\r\n  HSE_REQ_GET_CERT_INFO_EX[%p]: Fun"...
0x180007544  mov     rcx, cs:g_pDebug
0x18000754b  lea     r9, aSsfgetcertinfo; "SSFGetCertInfoEx"
0x180007552  mov     r8d, 3EBh
0x180007558  mov     [rsp+48h+var_28], rax
0x18000755d  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007564  call    cs:__imp_PuDbgPrint
0x18000756a  mov     r9d, cs:g_dwDebugFlags
0x180007571  mov     rcx, [rbx+0C0h]
0x180007578  test    rcx, rcx
0x18000757b  jnz     short loc_18000759F
0x18000757d  test    r9b, 3
0x180007581  setnz   cl
0x180007584  bt      r9d, 14h
0x180007589  setb    al
0x18000758c  test    al, cl
0x18000758e  jz      short loc_1800075E9
0x180007590  lea     rax, aHseReqGetCertI; "\r\n  HSE_REQ_GET_CERT_INFO_EX[%p]: Fai"...
0x180007597  mov     r8d, 3F8h
0x18000759d  jmp     short loc_1800075C4
0x18000759f  test    rdi, rdi
0x1800075a2  jnz     short loc_1800075F0
0x1800075a4  test    r9b, 3
0x1800075a8  setnz   cl
0x1800075ab  bt      r9d, 14h
0x1800075b0  setb    al
0x1800075b3  test    al, cl
0x1800075b5  jz      short loc_1800075E9
0x1800075b7  lea     rax, aHseReqGetCertI_3; "\r\n  HSE_REQ_GET_CERT_INFO_EX[%p]: Par"...
0x1800075be  mov     r8d, 40Bh
0x1800075c4  mov     rcx, cs:g_pDebug
0x1800075cb  lea     r9, aSsfgetcertinfo; "SSFGetCertInfoEx"
0x1800075d2  mov     [rsp+48h+var_20], rbx
0x1800075d7  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800075de  mov     [rsp+48h+var_28], rax
0x1800075e3  call    cs:__imp_PuDbgPrint
0x1800075e9  mov     eax, 80070057h
0x1800075ee  jmp     short loc_18000766D
0x1800075f0  mov     rax, [rcx]
0x1800075f3  lea     rdx, [rdi+2Ch]
0x1800075f7  mov     r9, [rdi+8]
0x1800075fb  lea     r8, [rdi+10h]
0x1800075ff  mov     [rsp+48h+var_20], rdx
0x180007604  mov     edx, [rdi+28h]
0x180007607  mov     rax, [rax+48h]
0x18000760b  mov     [rsp+48h+var_28], r8
0x180007610  mov     r8, rdi
0x180007613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007618  mov     edi, eax
0x18000761a  test    eax, eax
0x18000761c  jns     short loc_18000766B
0x18000761e  mov     ecx, cs:g_dwDebugFlags
0x180007624  test    cl, 3
0x180007627  setnz   dl
0x18000762a  bt      ecx, 14h
0x18000762e  setb    cl
0x180007631  test    cl, dl
0x180007633  jz      short loc_18000766B
0x180007635  mov     rcx, cs:g_pDebug
0x18000763c  lea     r9, aSsfgetcertinfo; "SSFGetCertInfoEx"
0x180007643  mov     [rsp+48h+var_18], eax
0x180007647  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000764e  lea     rax, aHseReqGetCertI_2; "\r\n  HSE_REQ_GET_CERT_INFO_EX[%p]: Fai"...
0x180007655  mov     [rsp+48h+var_20], rbx
0x18000765a  mov     r8d, 422h
0x180007660  mov     [rsp+48h+var_28], rax
0x180007665  call    cs:__imp_PuDbgPrint
0x18000766b  mov     eax, edi
0x18000766d  mov     rbx, [rsp+48h+arg_0]
0x180007672  add     rsp, 40h
0x180007676  pop     rdi
0x180007677  retn
```
