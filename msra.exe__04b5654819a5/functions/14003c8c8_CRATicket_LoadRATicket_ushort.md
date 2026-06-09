# CRATicket::LoadRATicket(ushort *)

- ea: `0x14003c8c8`
- end: `0x14003d081`
- name: `?LoadRATicket@CRATicket@@QEAAJPEAG@Z`
- size: `1977`
- prototype: `__int64 __fastcall(OLECHAR **this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140014574`
- `0x140032274`

## callees

- `0x1400044f8`
- `0x14000a0e4`
- `0x140034ce4`
- `0x14003c8c8`
- `0x14003ff50`
- `0x14004d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14003c9c4`
- `ole32!CoCreateInstance` at `0x14003c9c4`
- `OLEAUT32!__imp_SysAllocString` at `0x14003cdb9`
- `OLEAUT32!__imp_SysAllocString` at `0x14003ce91`
- `OLEAUT32!__imp_SysAllocString` at `0x14003cdb9`
- `OLEAUT32!__imp_SysAllocString` at `0x14003ce91`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cda5`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ce7d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cecd`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cedc`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ceeb`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cefa`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf09`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf18`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf27`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf37`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf47`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf57`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf66`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf76`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf85`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cda5`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ce7d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cecd`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cedc`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ceeb`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cefa`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf09`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf18`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf27`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf37`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf47`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf57`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf66`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf76`
- `OLEAUT32!__imp_SysFreeString` at `0x14003cf85`
- `OLEAUT32!__imp_SysStringLen` at `0x14003ce60`
- `OLEAUT32!__imp_SysStringLen` at `0x14003ce60`
- `OLEAUT32!__imp_VariantInit` at `0x14003c91d`
- `OLEAUT32!__imp_VariantInit` at `0x14003cb71`
- `OLEAUT32!__imp_VariantInit` at `0x14003c91d`
- `OLEAUT32!__imp_VariantInit` at `0x14003cb71`
- `OLEAUT32!__imp_VariantClear` at `0x14003ca53`
- `OLEAUT32!__imp_VariantClear` at `0x14003cab4`
- `OLEAUT32!__imp_VariantClear` at `0x14003cb16`
- `OLEAUT32!__imp_VariantClear` at `0x14003cd63`
- `OLEAUT32!__imp_VariantClear` at `0x14003ce2f`
- `OLEAUT32!__imp_VariantClear` at `0x14003cf96`
- `OLEAUT32!__imp_VariantClear` at `0x14003ca53`
- `OLEAUT32!__imp_VariantClear` at `0x14003cab4`
- `OLEAUT32!__imp_VariantClear` at `0x14003cb16`
- `OLEAUT32!__imp_VariantClear` at `0x14003cd63`
- `OLEAUT32!__imp_VariantClear` at `0x14003ce2f`
- `OLEAUT32!__imp_VariantClear` at `0x14003cf96`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRATicket::LoadRATicket(OLECHAR **this, unsigned __int16 *a2)
{
  OLECHAR *v4; // rdi
  OLECHAR *v5; // rbx
  OLECHAR *v6; // rsi
  OLECHAR *v7; // r14
  HRESULT v8; // eax
  CEventLogger *v9; // rcx
  int v10; // r15d
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // eax
  int v15; // eax
  const OLECHAR *bstrVal; // rbx
  OLECHAR *v17; // rcx
  BSTR v18; // rax
  const OLECHAR *v19; // r12
  OLECHAR *v20; // rcx
  BSTR v21; // rax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v27; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *v28; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR *v29; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR *v30; // [rsp+78h] [rbp-88h] BYREF
  OLECHAR *v31; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h] BYREF
  __int64 v33; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG v35; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v37; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  __int64 v40; // [rsp+100h] [rbp+0h]
  __int64 v41; // [rsp+108h] [rbp+8h]
  __int64 v42; // [rsp+110h] [rbp+10h]
  __int64 v43; // [rsp+118h] [rbp+18h]
  __int64 v44; // [rsp+120h] [rbp+20h]
  __int64 v45; // [rsp+128h] [rbp+28h]
  __int64 v46; // [rsp+130h] [rbp+30h]
  __int64 v47; // [rsp+138h] [rbp+38h]
  __int16 v48; // [rsp+190h] [rbp+90h] BYREF
  int v49; // [rsp+198h] [rbp+98h] BYREF

  ppv = 0;
  v34 = 0;
  v24 = 0;
  v33 = 0;
  v32 = 0;
  v26 = 0;
  v25 = 0;
  v38 = 0;
  v48 = 0;
  VariantInit(&pvarg);
  memset(&v37, 0, sizeof(v37));
  v39 = 0;
  v49 = 0;
  v4 = 0;
  v30 = 0;
  v40 = 0;
  v5 = 0;
  v28 = 0;
  v6 = 0;
  v31 = 0;
  v7 = 0;
  v29 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = -1;
  v8 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &ppv);
  v10 = v8;
  if ( v8 < 0 )
  {
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      0xDEDu,
      L"CRATicket::LoadRATicket",
      v8);
    goto LABEL_46;
  }
  v11 = *(_QWORD *)ppv;
  v27.vt = 11;
  v27.iVal = 0;
  v35 = v27;
  v10 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v11 + 640))(
          ppv,
          L"AllowDocumentFunction",
          &v35);
  VariantClear(&v27);
  if ( v10 >= 0 )
  {
    v12 = *(_QWORD *)ppv;
    v27.vt = 11;
    v27.iVal = 0;
    v35 = v27;
    v10 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v12 + 640))(ppv, L"AllowXsltScript", &v35);
    VariantClear(&v27);
    if ( v10 >= 0 )
    {
      v13 = *(_QWORD *)ppv;
      v27.vt = 11;
      v27.iVal = -1;
      v35 = v27;
      v10 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v13 + 640))(ppv, L"ProhibitDTD", &v35);
      VariantClear(&v27);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
          if ( v10 >= 0 )
          {
            VariantInit(&v37);
            v37.vt = 8;
            v37.llVal = (LONGLONG)a2;
            v35 = v37;
            if ( (*(int (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)ppv + 464LL))(ppv, &v35, &v48) < 0 )
              goto LABEL_45;
            if ( !v48 )
              goto LABEL_45;
            (*(void (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 480LL))(ppv, &v34);
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 56LL))(v34, &v49);
            if ( v49 )
              goto LABEL_45;
            v10 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v31, L"UPLOADINFO/UPLOADDATA");
            v6 = v31;
            if ( v10 < 0 )
              goto LABEL_46;
            if ( (*(int (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)ppv + 296LL))(ppv, v31, &v33) < 0
              || !v33 )
            {
              goto LABEL_45;
            }
            v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 136LL))(v33, &v24);
            if ( v10 < 0 )
              goto LABEL_46;
            if ( !v24 )
              goto LABEL_46;
            v10 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v30, L"USERNAME");
            v4 = v30;
            if ( v10 < 0 )
              goto LABEL_46;
            if ( (*(int (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v24 + 56LL))(v24, v30, &v32) < 0
              || !v32 )
            {
              goto LABEL_45;
            }
            v14 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v32 + 64LL))(v32, &pvarg);
            v10 = v14;
            if ( v14 < 0 )
              goto LABEL_46;
            if ( v14 == 1 )
              goto LABEL_46;
            v10 = CRATicket::put_NoviceName((CRATicket *)this, pvarg.bstrVal);
            if ( v10 < 0 )
              goto LABEL_46;
            v10 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v29, L"PassStub");
            v7 = v29;
            if ( v10 < 0 )
              goto LABEL_46;
            if ( (*(int (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v24 + 56LL))(v24, v29, &v26) < 0 )
              goto LABEL_45;
            if ( !v26 )
              goto LABEL_45;
            VariantClear(&pvarg);
            v15 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v26 + 64LL))(v26, &pvarg);
            if ( v15 < 0 || v15 == 1 )
              goto LABEL_45;
            bstrVal = pvarg.bstrVal;
            v17 = this[21];
            if ( pvarg.bstrVal != v17 )
            {
              SysFreeString(v17);
              if ( bstrVal )
              {
                v18 = SysAllocString(bstrVal);
                this[21] = v18;
                if ( !v18 )
                  goto LABEL_63;
              }
              else
              {
                this[21] = 0;
              }
            }
            v10 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v28, L"LHTICKET");
            v5 = v28;
            if ( v10 < 0 )
              goto LABEL_46;
            if ( (*(int (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v24 + 56LL))(v24, v28, &v25) < 0
              || !v25 )
            {
LABEL_45:
              v10 = -2147467259;
              goto LABEL_46;
            }
            VariantClear(&pvarg);
            v10 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v25 + 64LL))(v25, &pvarg);
            if ( v10 < 0 )
              goto LABEL_46;
            if ( pvarg.llVal && SysStringLen(pvarg.bstrVal) )
            {
              v19 = pvarg.bstrVal;
              v20 = this[5];
              if ( pvarg.bstrVal != v20 )
              {
                SysFreeString(v20);
                if ( v19 )
                {
                  v21 = SysAllocString(v19);
                  this[5] = v21;
                  if ( v21 )
                    goto LABEL_43;
LABEL_63:
                  ATL::AtlThrowImpl(-2147024882);
                }
                this[5] = 0;
              }
LABEL_43:
              *((_DWORD *)this + 38) = 2;
              goto LABEL_46;
            }
            v10 = -2147024809;
          }
        }
      }
    }
  }
LABEL_46:
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(0);
  SysFreeString(v7);
  SysFreeString(v6);
  SysFreeString(v5);
  SysFreeString(0);
  SysFreeString(v4);
  SysFreeString(0);
  VariantClear(&pvarg);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003c8c8  mov     [rsp-8+arg_0], rbx
0x14003c8cd  push    rbp
0x14003c8ce  push    rsi
0x14003c8cf  push    rdi
0x14003c8d0  push    r12
0x14003c8d2  push    r13
0x14003c8d4  push    r14
0x14003c8d6  push    r15
0x14003c8d8  lea     rbp, [rsp-40h]
0x14003c8dd  sub     rsp, 140h
0x14003c8e4  mov     r12, rdx
0x14003c8e7  mov     r13, rcx
0x14003c8ea  xor     r15d, r15d
0x14003c8ed  mov     [rsp+170h+var_140], r15
0x14003c8f2  mov     [rbp+70h+var_D8], r15
0x14003c8f6  mov     [rsp+170h+var_138], r15
0x14003c8fb  mov     [rbp+70h+var_E0], r15
0x14003c8ff  mov     [rbp+70h+var_E8], r15
0x14003c903  mov     [rsp+170h+var_128], r15
0x14003c908  mov     [rsp+170h+var_130], r15
0x14003c90d  mov     [rbp+70h+var_80], r15
0x14003c911  mov     [rbp+70h+arg_10], r15w
0x14003c919  lea     rcx, [rbp+70h+pvarg]; pvarg
0x14003c91d  call    cs:__imp_VariantInit
0x14003c924  nop     dword ptr [rax+rax+00h]
0x14003c929  nop
0x14003c92a  xorps   xmm0, xmm0
0x14003c92d  xor     eax, eax
0x14003c92f  movups  xmmword ptr [rbp+70h+var_98], xmm0
0x14003c933  mov     qword ptr [rbp+70h+var_98+10h], rax
0x14003c937  mov     [rbp+70h+var_78], r15
0x14003c93b  mov     [rbp+70h+arg_18], r15d
0x14003c942  mov     edi, r15d
0x14003c945  mov     [rsp+170h+var_F8], r15
0x14003c94a  mov     [rbp+70h+var_70], r15
0x14003c94e  mov     ebx, r15d
0x14003c951  mov     [rsp+170h+var_108], rbx
0x14003c956  mov     esi, r15d
0x14003c959  mov     [rbp+70h+var_F0], r15
0x14003c95d  mov     r14d, r15d
0x14003c960  mov     [rsp+170h+var_100], r15
0x14003c965  mov     [rbp+70h+var_68], r15
0x14003c969  mov     [rbp+70h+var_60], r15
0x14003c96d  mov     [rbp+70h+var_58], r15
0x14003c971  mov     [rbp+70h+var_50], r15
0x14003c975  mov     [rbp+70h+var_48], r15
0x14003c979  mov     [rbp+70h+var_40], r15
0x14003c97d  mov     [rbp+70h+var_38], r15
0x14003c981  or      eax, 0FFFFFFFFh
0x14003c984  mov     [rbp+70h+arg_10], ax
0x14003c98b  mov     rcx, [rsp+170h+var_138]
0x14003c990  test    rcx, rcx
0x14003c993  jz      short loc_14003C9A6
0x14003c995  mov     rax, [rcx]
0x14003c998  mov     rax, [rax+10h]
0x14003c99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c9a1  mov     [rsp+170h+var_138], r15
0x14003c9a6  lea     rax, [rsp+170h+var_140]
0x14003c9ab  mov     [rsp+170h+ppv], rax; ppv
0x14003c9b0  lea     r9, IID_IXMLDOMDocument; riid
0x14003c9b7  xor     edx, edx; pUnkOuter
0x14003c9b9  lea     r8d, [rdx+1]; dwClsContext
0x14003c9bd  lea     rcx, CLSID_DOMDocument60; rclsid
0x14003c9c4  call    cs:__imp_CoCreateInstance
0x14003c9cb  nop     dword ptr [rax+rax+00h]
0x14003c9d0  mov     r15d, eax
0x14003c9d3  xor     edx, edx
0x14003c9d5  test    eax, eax
0x14003c9d7  jns     short loc_14003CA07
0x14003c9d9  mov     [rsp+170h+var_148], eax; unsigned int
0x14003c9dd  lea     rax, aCraticketLoadr; "CRATicket::LoadRATicket"
0x14003c9e4  mov     [rsp+170h+ppv], rax; unsigned __int16 *
0x14003c9e9  mov     r9d, 0DEDh; unsigned int
0x14003c9ef  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003c9f6  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003c9fd  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003ca02  jmp     loc_14003CECB
0x14003ca07  mov     rcx, [rsp+170h+var_140]
0x14003ca0c  mov     rax, [rcx]
0x14003ca0f  mov     r8d, 0Bh
0x14003ca15  mov     word ptr [rsp+170h+var_120], r8w
0x14003ca1b  mov     word ptr [rsp+170h+var_120+8], dx
0x14003ca20  movups  xmm0, xmmword ptr [rsp+170h+var_120]
0x14003ca25  movaps  [rbp+70h+var_D0], xmm0
0x14003ca29  movsd   xmm1, qword ptr [rsp+170h+var_120+10h]
0x14003ca2f  movsd   [rbp+70h+var_C0], xmm1
0x14003ca34  lea     r8, [rbp+70h+var_D0]
0x14003ca38  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x14003ca3f  mov     rax, [rax+280h]
0x14003ca46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ca4b  mov     r15d, eax
0x14003ca4e  lea     rcx, [rsp+170h+var_120]; pvarg
0x14003ca53  call    cs:__imp_VariantClear
0x14003ca5a  nop     dword ptr [rax+rax+00h]
0x14003ca5f  xor     edx, edx
0x14003ca61  test    r15d, r15d
0x14003ca64  js      loc_14003CECB
0x14003ca6a  mov     rcx, [rsp+170h+var_140]
0x14003ca6f  mov     rax, [rcx]
0x14003ca72  lea     r8d, [rdx+0Bh]
0x14003ca76  mov     word ptr [rsp+170h+var_120], r8w
0x14003ca7c  mov     word ptr [rsp+170h+var_120+8], dx
0x14003ca81  movups  xmm0, xmmword ptr [rsp+170h+var_120]
0x14003ca86  movaps  [rbp+70h+var_D0], xmm0
0x14003ca8a  movsd   xmm1, qword ptr [rsp+170h+var_120+10h]
0x14003ca90  movsd   [rbp+70h+var_C0], xmm1
0x14003ca95  lea     r8, [rbp+70h+var_D0]
0x14003ca99  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x14003caa0  mov     rax, [rax+280h]
0x14003caa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003caac  mov     r15d, eax
0x14003caaf  lea     rcx, [rsp+170h+var_120]; pvarg
0x14003cab4  call    cs:__imp_VariantClear
0x14003cabb  nop     dword ptr [rax+rax+00h]
0x14003cac0  test    r15d, r15d
0x14003cac3  js      loc_14003CECB
0x14003cac9  mov     rcx, [rsp+170h+var_140]
0x14003cace  mov     rax, [rcx]
0x14003cad1  mov     edx, 0Bh
0x14003cad6  mov     word ptr [rsp+170h+var_120], dx
0x14003cadb  or      edx, 0FFFFFFFFh
0x14003cade  mov     word ptr [rsp+170h+var_120+8], dx
0x14003cae3  movups  xmm0, xmmword ptr [rsp+170h+var_120]
0x14003cae8  movaps  [rbp+70h+var_D0], xmm0
0x14003caec  movsd   xmm1, qword ptr [rsp+170h+var_120+10h]
0x14003caf2  movsd   [rbp+70h+var_C0], xmm1
0x14003caf7  lea     r8, [rbp+70h+var_D0]
0x14003cafb  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x14003cb02  mov     rax, [rax+280h]
0x14003cb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cb0e  mov     r15d, eax
0x14003cb11  lea     rcx, [rsp+170h+var_120]; pvarg
0x14003cb16  call    cs:__imp_VariantClear
0x14003cb1d  nop     dword ptr [rax+rax+00h]
0x14003cb22  test    r15d, r15d
0x14003cb25  js      loc_14003CECB
0x14003cb2b  mov     rcx, [rsp+170h+var_140]
0x14003cb30  mov     rax, [rcx]
0x14003cb33  xor     edx, edx
0x14003cb35  mov     rax, [rax+230h]
0x14003cb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cb41  mov     r15d, eax
0x14003cb44  test    eax, eax
0x14003cb46  js      loc_14003CECB
0x14003cb4c  mov     rcx, [rsp+170h+var_140]
0x14003cb51  mov     rax, [rcx]
0x14003cb54  xor     edx, edx
0x14003cb56  mov     rax, [rax+1F8h]
0x14003cb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cb62  mov     r15d, eax
0x14003cb65  test    eax, eax
0x14003cb67  js      loc_14003CECB
0x14003cb6d  lea     rcx, [rbp+70h+var_98]; pvarg
0x14003cb71  call    cs:__imp_VariantInit
0x14003cb78  nop     dword ptr [rax+rax+00h]
0x14003cb7d  mov     eax, 8
0x14003cb82  mov     word ptr [rbp+70h+var_98], ax
0x14003cb86  mov     qword ptr [rbp+70h+var_98+8], r12
0x14003cb8a  mov     rcx, [rsp+170h+var_140]
0x14003cb8f  movups  xmm0, xmmword ptr [rbp+70h+var_98]
0x14003cb93  movaps  [rbp+70h+var_D0], xmm0
0x14003cb97  movsd   xmm1, qword ptr [rbp+70h+var_98+10h]
0x14003cb9c  movsd   [rbp+70h+var_C0], xmm1
0x14003cba1  mov     rax, [rcx]
0x14003cba4  lea     r8, [rbp+70h+arg_10]
0x14003cbab  lea     rdx, [rbp+70h+var_D0]
0x14003cbaf  mov     rax, [rax+1D0h]
0x14003cbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cbbb  xor     r12d, r12d
0x14003cbbe  test    eax, eax
0x14003cbc0  js      loc_14003CEC5
0x14003cbc6  cmp     [rbp+70h+arg_10], r12w
0x14003cbce  jz      loc_14003CEC5
0x14003cbd4  mov     rcx, [rsp+170h+var_140]
0x14003cbd9  mov     rax, [rcx]
0x14003cbdc  lea     rdx, [rbp+70h+var_D8]
0x14003cbe0  mov     rax, [rax+1E0h]
0x14003cbe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cbec  mov     rcx, [rbp+70h+var_D8]
0x14003cbf0  mov     rax, [rcx]
0x14003cbf3  lea     rdx, [rbp+70h+arg_18]
0x14003cbfa  mov     rax, [rax+38h]
0x14003cbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cc03  cmp     [rbp+70h+arg_18], r12d
0x14003cc0a  jnz     loc_14003CEC5
0x14003cc10  lea     rdx, aUploadinfoUplo; "UPLOADINFO/UPLOADDATA"
0x14003cc17  lea     rcx, [rbp+70h+var_F0]; this
0x14003cc1b  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14003cc20  mov     r15d, eax
0x14003cc23  mov     rsi, [rbp+70h+var_F0]
0x14003cc27  test    eax, eax
0x14003cc29  js      loc_14003CECB
0x14003cc2f  mov     rcx, [rsp+170h+var_140]
0x14003cc34  mov     rax, [rcx]
0x14003cc37  lea     r8, [rbp+70h+var_E0]
0x14003cc3b  mov     rdx, rsi
0x14003cc3e  mov     rax, [rax+128h]
0x14003cc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cc4a  test    eax, eax
0x14003cc4c  js      loc_14003CEC5
0x14003cc52  mov     rcx, [rbp+70h+var_E0]
0x14003cc56  test    rcx, rcx
0x14003cc59  jz      loc_14003CEC5
0x14003cc5f  mov     rax, [rcx]
0x14003cc62  lea     rdx, [rsp+170h+var_138]
0x14003cc67  mov     rax, [rax+88h]
0x14003cc6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cc73  mov     r15d, eax
0x14003cc76  test    eax, eax
0x14003cc78  js      loc_14003CECB
0x14003cc7e  cmp     [rsp+170h+var_138], r12
0x14003cc83  jz      loc_14003CECB
0x14003cc89  lea     rdx, aUsername; "USERNAME"
0x14003cc90  lea     rcx, [rsp+170h+var_F8]; this
0x14003cc95  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14003cc9a  mov     r15d, eax
0x14003cc9d  mov     rdi, [rsp+170h+var_F8]
0x14003cca2  test    eax, eax
0x14003cca4  js      loc_14003CECB
0x14003ccaa  mov     rcx, [rsp+170h+var_138]
0x14003ccaf  mov     rax, [rcx]
0x14003ccb2  lea     r8, [rbp+70h+var_E8]
0x14003ccb6  mov     rdx, rdi
0x14003ccb9  mov     rax, [rax+38h]
0x14003ccbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ccc2  test    eax, eax
0x14003ccc4  js      loc_14003CEC5
0x14003ccca  mov     rcx, [rbp+70h+var_E8]
0x14003ccce  test    rcx, rcx
0x14003ccd1  jz      loc_14003CEC5
0x14003ccd7  mov     rax, [rcx]
0x14003ccda  lea     rdx, [rbp+70h+pvarg]
0x14003ccde  mov     rax, [rax+40h]
0x14003cce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cce7  mov     r15d, eax
0x14003ccea  test    eax, eax
0x14003ccec  js      loc_14003CECB
0x14003ccf2  cmp     eax, 1
0x14003ccf5  jz      loc_14003CECB
0x14003ccfb  mov     rdx, qword ptr [rbp+70h+pvarg+8]; unsigned __int16 *
0x14003ccff  mov     rcx, r13; this
0x14003cd02  call    ?put_NoviceName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_NoviceName(ushort *)
0x14003cd07  mov     r15d, eax
0x14003cd0a  test    eax, eax
0x14003cd0c  js      loc_14003CECB
0x14003cd12  lea     rdx, aPassstub; "PassStub"
0x14003cd19  lea     rcx, [rsp+170h+var_100]; this
0x14003cd1e  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14003cd23  mov     r15d, eax
0x14003cd26  mov     r14, [rsp+170h+var_100]
0x14003cd2b  test    eax, eax
0x14003cd2d  js      loc_14003CECB
0x14003cd33  mov     rcx, [rsp+170h+var_138]
0x14003cd38  mov     rax, [rcx]
0x14003cd3b  lea     r8, [rsp+170h+var_128]
0x14003cd40  mov     rdx, r14
0x14003cd43  mov     rax, [rax+38h]
0x14003cd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cd4c  test    eax, eax
0x14003cd4e  js      loc_14003CEC5
0x14003cd54  cmp     [rsp+170h+var_128], r12
0x14003cd59  jz      loc_14003CEC5
0x14003cd5f  lea     rcx, [rbp+70h+pvarg]; pvarg
0x14003cd63  call    cs:__imp_VariantClear
0x14003cd6a  nop     dword ptr [rax+rax+00h]
0x14003cd6f  mov     rcx, [rsp+170h+var_128]
0x14003cd74  mov     rax, [rcx]
0x14003cd77  lea     rdx, [rbp+70h+pvarg]
0x14003cd7b  mov     rax, [rax+40h]
0x14003cd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003cd84  test    eax, eax
0x14003cd86  js      loc_14003CEC5
0x14003cd8c  cmp     eax, 1
0x14003cd8f  jz      loc_14003CEC5
0x14003cd95  mov     rbx, qword ptr [rbp+70h+pvarg+8]
0x14003cd99  mov     rcx, [r13+0A8h]; bstrString
0x14003cda0  cmp     rbx, rcx
0x14003cda3  jz      short loc_14003CDDE
0x14003cda5  call    cs:__imp_SysFreeString
0x14003cdac  nop     dword ptr [rax+rax+00h]
0x14003cdb1  test    rbx, rbx
0x14003cdb4  jz      short loc_14003CDD7
0x14003cdb6  mov     rcx, rbx; psz
0x14003cdb9  call    cs:__imp_SysAllocString
0x14003cdc0  nop     dword ptr [rax+rax+00h]
0x14003cdc5  mov     [r13+0A8h], rax
0x14003cdcc  test    rax, rax
0x14003cdcf  jz      loc_14003D076
0x14003cdd5  jmp     short loc_14003CDDE
0x14003cdd7  mov     [r13+0A8h], r12
0x14003cdde  lea     rdx, aLhticket; "LHTICKET"
0x14003cde5  lea     rcx, [rsp+170h+var_108]; this
0x14003cdea  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14003cdef  mov     r15d, eax
0x14003cdf2  mov     rbx, [rsp+170h+var_108]
0x14003cdf7  test    eax, eax
0x14003cdf9  js      loc_14003CECB
0x14003cdff  mov     rcx, [rsp+170h+var_138]
0x14003ce04  mov     rax, [rcx]
0x14003ce07  lea     r8, [rsp+170h+var_130]
  ... truncated ...
```
