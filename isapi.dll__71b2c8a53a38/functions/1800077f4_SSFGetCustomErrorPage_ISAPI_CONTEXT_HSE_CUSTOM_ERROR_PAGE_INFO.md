# SSFGetCustomErrorPage(ISAPI_CONTEXT *,_HSE_CUSTOM_ERROR_PAGE_INFO *)

- ea: `0x1800077f4`
- end: `0x180007a0f`
- name: `?SSFGetCustomErrorPage@@YAJPEAVISAPI_CONTEXT@@PEAU_HSE_CUSTOM_ERROR_PAGE_INFO@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, struct _HSE_CUSTOM_ERROR_PAGE_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x1800077f4`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007861`
- `iisutil!PuDbgPrint` at `0x1800078ba`
- `iisutil!PuDbgPrint` at `0x18000797b`
- `iisutil!PuDbgPrint` at `0x1800079f9`
- `iisutil!PuDbgPrint` at `0x180007861`
- `iisutil!PuDbgPrint` at `0x1800078ba`
- `iisutil!PuDbgPrint` at `0x18000797b`
- `iisutil!PuDbgPrint` at `0x1800079f9`

## string_xrefs

- `0x18000783f`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800078b3`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000795d`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x1800079d1`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFGetCustomErrorPage(struct ISAPI_CONTEXT *a1, struct _HSE_CUSTOM_ERROR_PAGE_INFO *a2)
{
  int v4; // edx
  int v5; // eax
  int v6; // ecx
  __int64 v7; // rcx
  __int64 result; // rax
  unsigned int v9; // ebx
  int v10; // eax
  const void *v11; // rcx
  const void *v12; // rdx
  const void *v13; // r8

  v4 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
  {
    if ( a2 )
    {
      v5 = *(_DWORD *)a2;
      v6 = *((_DWORD *)a2 + 1);
    }
    else
    {
      v5 = 0;
      v6 = 0;
    }
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      3295,
      "SSFGetCustomErrorPage",
      "\r\n  HSE_REQ_GET_CUSTOM_ERROR_PAGE[%p]: Function Entry\r\n    Error: %d\r\n    SubError: %d\r\n  <END>\r\n\r\n",
      a1,
      v5,
      v6);
    v4 = g_dwDebugFlags;
  }
  v7 = *((_QWORD *)a1 + 24);
  if ( !v7 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3308,
        "SSFGetCustomErrorPage",
        "\r\n  HSE_REQ_GET_CUSTOM_ERROR_PAGE[%p]: Failed to get interface to server core\r\n  <END>\r\n\r\n",
        a1);
    return 2147942487LL;
  }
  if ( !a2 || *((_DWORD *)a2 + 2) && !*((_QWORD *)a2 + 2) || !*((_QWORD *)a2 + 3) || !*((_QWORD *)a2 + 4) )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
    {
      if ( a2 )
      {
        v10 = *((_DWORD *)a2 + 2);
        v11 = (const void *)*((_QWORD *)a2 + 2);
        v12 = (const void *)*((_QWORD *)a2 + 3);
        v13 = (const void *)*((_QWORD *)a2 + 4);
      }
      else
      {
        v10 = 0;
        v11 = 0;
        v12 = 0;
        v13 = 0;
      }
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3339,
        "SSFGetCustomErrorPage",
        "\r\n"
        "  HSE_REQ_GET_CUSTOM_ERROR_PAGE[%p]: Parameter validation failure\r\n"
        "    Info Ptr: %p\r\n"
        "    Buffer Size: %d\r\n"
        "    Buffer Ptr: %p\r\n"
        "    Buffer Required Ptr: %p\r\n"
        "    IsFileError Ptr: %p\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a2,
        v10,
        v11,
        v12,
        v13);
    }
    return 2147942487LL;
  }
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v7 + 120LL))(
             v7,
             *(unsigned int *)a2,
             *((unsigned int *)a2 + 1));
  v9 = result;
  if ( (int)result < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
        3365,
        "SSFGetCustomErrorPage",
        "\r\n  HSE_REQ_GET_CUSTOM_ERROR_PAGE[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
        a1,
        result);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1800077f4  mov     [rsp+arg_0], rbx
0x1800077f9  push    rdi
0x1800077fa  sub     rsp, 60h
0x1800077fe  mov     rbx, rdx
0x180007801  mov     rdi, rcx
0x180007804  mov     edx, cs:g_dwDebugFlags
0x18000780a  test    dl, 3
0x18000780d  setnz   r8b
0x180007811  bt      edx, 1Ah
0x180007815  setb    al
0x180007818  test    al, r8b
0x18000781b  jz      short loc_18000786D
0x18000781d  test    rbx, rbx
0x180007820  jz      short loc_180007829
0x180007822  mov     eax, [rbx]
0x180007824  mov     ecx, [rbx+4]
0x180007827  jmp     short loc_18000782D
0x180007829  xor     eax, eax
0x18000782b  xor     ecx, ecx
0x18000782d  mov     dword ptr [rsp+68h+var_30], ecx
0x180007831  lea     r9, aSsfgetcustomer; "SSFGetCustomErrorPage"
0x180007838  mov     rcx, cs:g_pDebug
0x18000783f  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007846  mov     dword ptr [rsp+68h+var_38], eax
0x18000784a  mov     r8d, 0CDFh
0x180007850  lea     rax, aHseReqGetCusto_2; "\r\n  HSE_REQ_GET_CUSTOM_ERROR_PAGE[%p]"...
0x180007857  mov     [rsp+68h+var_40], rdi
0x18000785c  mov     [rsp+68h+var_48], rax
0x180007861  call    cs:__imp_PuDbgPrint
0x180007867  mov     edx, cs:g_dwDebugFlags
0x18000786d  mov     rcx, [rdi+0C0h]
0x180007874  test    rcx, rcx
0x180007877  jnz     short loc_1800078C5
0x180007879  test    dl, 3
0x18000787c  setnz   cl
0x18000787f  bt      edx, 14h
0x180007883  setb    al
0x180007886  test    al, cl
0x180007888  jz      loc_1800079FF
0x18000788e  mov     rcx, cs:g_pDebug
0x180007895  lea     rax, aHseReqGetCusto_3; "\r\n  HSE_REQ_GET_CUSTOM_ERROR_PAGE[%p]"...
0x18000789c  mov     [rsp+68h+var_40], rdi
0x1800078a1  lea     r9, aSsfgetcustomer; "SSFGetCustomErrorPage"
0x1800078a8  mov     r8d, 0CECh
0x1800078ae  mov     [rsp+68h+var_48], rax
0x1800078b3  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800078ba  call    cs:__imp_PuDbgPrint
0x1800078c0  jmp     loc_1800079FF
0x1800078c5  test    rbx, rbx
0x1800078c8  jz      loc_180007985
0x1800078ce  mov     r9d, [rbx+8]
0x1800078d2  test    r9d, r9d
0x1800078d5  jz      short loc_1800078E2
0x1800078d7  cmp     qword ptr [rbx+10h], 0
0x1800078dc  jz      loc_180007985
0x1800078e2  mov     r8, [rbx+18h]
0x1800078e6  test    r8, r8
0x1800078e9  jz      loc_180007985
0x1800078ef  mov     r10, [rbx+20h]
0x1800078f3  test    r10, r10
0x1800078f6  jz      loc_180007985
0x1800078fc  mov     rdx, [rbx+28h]
0x180007900  mov     rax, [rcx]
0x180007903  mov     [rsp+68h+var_30], rdx
0x180007908  mov     rdx, [rbx+10h]
0x18000790c  mov     [rsp+68h+var_38], r10
0x180007911  mov     rax, [rax+78h]
0x180007915  mov     [rsp+68h+var_40], r8
0x18000791a  mov     r8d, [rbx+4]
0x18000791e  mov     [rsp+68h+var_48], rdx
0x180007923  mov     edx, [rbx]
0x180007925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000792a  mov     ebx, eax
0x18000792c  test    eax, eax
0x18000792e  jns     loc_180007A04
0x180007934  mov     ecx, cs:g_dwDebugFlags
0x18000793a  test    cl, 3
0x18000793d  setnz   dl
0x180007940  bt      ecx, 14h
0x180007944  setb    cl
0x180007947  test    cl, dl
0x180007949  jz      short loc_180007981
0x18000794b  mov     rcx, cs:g_pDebug
0x180007952  lea     r9, aSsfgetcustomer; "SSFGetCustomErrorPage"
0x180007959  mov     dword ptr [rsp+68h+var_38], eax
0x18000795d  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007964  lea     rax, aHseReqGetCusto_0; "\r\n  HSE_REQ_GET_CUSTOM_ERROR_PAGE[%p]"...
0x18000796b  mov     [rsp+68h+var_40], rdi
0x180007970  mov     r8d, 0D25h
0x180007976  mov     [rsp+68h+var_48], rax
0x18000797b  call    cs:__imp_PuDbgPrint
0x180007981  mov     eax, ebx
0x180007983  jmp     short loc_180007A04
0x180007985  test    dl, 3
0x180007988  setnz   cl
0x18000798b  bt      edx, 14h
0x18000798f  setb    al
0x180007992  test    al, cl
0x180007994  jz      short loc_1800079FF
0x180007996  test    rbx, rbx
0x180007999  jz      short loc_1800079AC
0x18000799b  mov     eax, [rbx+8]
0x18000799e  mov     rcx, [rbx+10h]
0x1800079a2  mov     rdx, [rbx+18h]
0x1800079a6  mov     r8, [rbx+20h]
0x1800079aa  jmp     short loc_1800079B5
0x1800079ac  xor     eax, eax
0x1800079ae  xor     ecx, ecx
0x1800079b0  xor     edx, edx
0x1800079b2  xor     r8d, r8d
0x1800079b5  mov     [rsp+68h+var_18], r8
0x1800079ba  lea     r9, aSsfgetcustomer; "SSFGetCustomErrorPage"
0x1800079c1  mov     [rsp+68h+var_20], rdx
0x1800079c6  mov     r8d, 0D0Bh
0x1800079cc  mov     [rsp+68h+var_28], rcx
0x1800079d1  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800079d8  mov     rcx, cs:g_pDebug
0x1800079df  mov     dword ptr [rsp+68h+var_30], eax
0x1800079e3  lea     rax, aHseReqGetCusto; "\r\n  HSE_REQ_GET_CUSTOM_ERROR_PAGE[%p]"...
0x1800079ea  mov     [rsp+68h+var_38], rbx
0x1800079ef  mov     [rsp+68h+var_40], rdi
0x1800079f4  mov     [rsp+68h+var_48], rax
0x1800079f9  call    cs:__imp_PuDbgPrint
0x1800079ff  mov     eax, 80070057h
0x180007a04  mov     rbx, [rsp+68h+arg_0]
0x180007a09  add     rsp, 60h
0x180007a0d  pop     rdi
0x180007a0e  retn
```
