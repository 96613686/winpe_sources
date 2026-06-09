# ProcessCommandForPropAnnounce(ushort *,ushort * *,ushort * *)

- ea: `0x1400482bc`
- end: `0x140048723`
- name: `?ProcessCommandForPropAnnounce@@YAHPEAGPEAPEAG1@Z`
- size: `1127`
- prototype: `_BOOL8 __fastcall(CEventLogger *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140047d10`

## callees

- `0x140034ce4`
- `0x140035600`
- `0x1400482bc`
- `0x14004d010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140048615`
- `KERNEL32!CompareStringW` at `0x140048615`
- `ole32!CoCreateInstance` at `0x140048394`
- `ole32!CoCreateInstance` at `0x140048394`
- `OLEAUT32!__imp_SysAllocString` at `0x14004834a`
- `OLEAUT32!__imp_SysAllocString` at `0x14004834a`
- `OLEAUT32!__imp_SysFreeString` at `0x140048596`
- `OLEAUT32!__imp_SysFreeString` at `0x140048683`
- `OLEAUT32!__imp_SysFreeString` at `0x14004869a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400486b1`
- `OLEAUT32!__imp_SysFreeString` at `0x140048596`
- `OLEAUT32!__imp_SysFreeString` at `0x140048683`
- `OLEAUT32!__imp_SysFreeString` at `0x14004869a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400486b1`
- `OLEAUT32!__imp_VariantClear` at `0x1400483f9`
- `OLEAUT32!__imp_VariantClear` at `0x14004845c`
- `OLEAUT32!__imp_VariantClear` at `0x1400484bf`
- `OLEAUT32!__imp_VariantClear` at `0x1400483f9`
- `OLEAUT32!__imp_VariantClear` at `0x14004845c`
- `OLEAUT32!__imp_VariantClear` at `0x1400484bf`

## string_xrefs

- `0x140048343`: `RCCOMMAND`
- `0x140048312`: `ProcessCommandForPropAnnounce`
- `0x1400485c4`: `ProcessCommandForPropAnnounce`

## pseudocode

```c
_BOOL8 __fastcall ProcessCommandForPropAnnounce(CEventLogger *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  WCHAR *v6; // rdi
  unsigned int v7; // r9d
  signed int v8; // ebx
  CEventLogger *v9; // rcx
  HRESULT v10; // eax
  CEventLogger *v11; // rcx
  __int64 v12; // rax
  CEventLogger *v13; // rcx
  __int64 v14; // rax
  CEventLogger *v15; // rcx
  __int64 v16; // rax
  CEventLogger *v17; // rcx
  signed int v18; // eax
  CEventLogger *v19; // rcx
  signed int AttributeFromAttributeList; // eax
  CEventLogger *v21; // rcx
  signed int v22; // eax
  CEventLogger *v23; // rcx
  signed int v24; // eax
  CEventLogger *v25; // rcx
  BOOL v26; // ebx
  struct IXMLDOMNamedNodeMap *v28; // [rsp+30h] [rbp-50h] BYREF
  PCNZWCH lpString1; // [rsp+38h] [rbp-48h] BYREF
  __int64 v30; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v32; // [rsp+60h] [rbp-20h] BYREF
  __int16 v33; // [rsp+C8h] [rbp+48h] BYREF
  LPVOID ppv; // [rsp+D8h] [rbp+58h] BYREF

  ppv = 0;
  v33 = -1;
  v30 = 0;
  v28 = 0;
  v6 = 0;
  if ( !a2 )
  {
    v7 = 1548;
LABEL_3:
    v8 = -2147467261;
    CEventLogger::LogError(
      a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
      v7,
      L"ProcessCommandForPropAnnounce",
      0x80004003);
    goto LABEL_32;
  }
  if ( !a3 )
  {
    v7 = 1549;
    goto LABEL_3;
  }
  v6 = SysAllocString(L"RCCOMMAND");
  lpString1 = v6;
  if ( v6 )
  {
    v10 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &ppv);
    v8 = v10;
    if ( v10 >= 0 )
    {
      v12 = *(_QWORD *)ppv;
      pvarg.vt = 11;
      pvarg.iVal = -1;
      v32 = pvarg;
      v8 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v12 + 640))(ppv, L"ProhibitDTD", &v32);
      VariantClear(&pvarg);
      if ( v8 >= 0 )
      {
        v14 = *(_QWORD *)ppv;
        pvarg.vt = 11;
        pvarg.iVal = 0;
        v32 = pvarg;
        v8 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v14 + 640))(
               ppv,
               L"AllowXsltScript",
               &v32);
        VariantClear(&pvarg);
        if ( v8 >= 0 )
        {
          v16 = *(_QWORD *)ppv;
          pvarg.vt = 11;
          pvarg.iVal = 0;
          v32 = pvarg;
          v8 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v16 + 640))(
                 ppv,
                 L"AllowDocumentFunction",
                 &v32);
          VariantClear(&pvarg);
          if ( v8 >= 0 )
          {
            v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
            v8 = v18;
            if ( v18 >= 0 )
            {
              if ( (*(int (__fastcall **)(LPVOID, CEventLogger *, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, a1, &v33) < 0
                || !v33
                || (*(int (__fastcall **)(LPVOID, WCHAR *, __int64 *))(*(_QWORD *)ppv + 296LL))(ppv, v6, &v30) < 0
                || !v30
                || (*(int (__fastcall **)(__int64, struct IXMLDOMNamedNodeMap **))(*(_QWORD *)v30 + 136LL))(v30, &v28) < 0
                || !v28 )
              {
                goto LABEL_31;
              }
              SysFreeString(v6);
              lpString1 = 0;
              AttributeFromAttributeList = GetAttributeFromAttributeList(v28, L"NAME", (unsigned __int16 **)&lpString1);
              v8 = AttributeFromAttributeList;
              if ( AttributeFromAttributeList < 0 )
              {
                CEventLogger::LogError(
                  v21,
                  &Recoverable_Error,
                  L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
                  0x636u,
                  L"ProcessCommandForPropAnnounce",
                  AttributeFromAttributeList);
                v6 = (WCHAR *)lpString1;
                goto LABEL_32;
              }
              v6 = (WCHAR *)lpString1;
              if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"SETTINGANNOUNCE", -1) != 2 )
              {
LABEL_31:
                v8 = -2147467259;
                goto LABEL_32;
              }
              v22 = GetAttributeFromAttributeList(v28, L"PROPERTY", a2);
              v8 = v22;
              if ( v22 >= 0 )
              {
                v24 = GetAttributeFromAttributeList(v28, L"VALUE", a3);
                v8 = v24;
                if ( v24 >= 0 )
                  goto LABEL_36;
                CEventLogger::LogError(
                  v25,
                  &Recoverable_Error,
                  L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
                  0x651u,
                  L"ProcessCommandForPropAnnounce",
                  v24);
              }
              else
              {
                CEventLogger::LogError(
                  v23,
                  &Recoverable_Error,
                  L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
                  0x64Cu,
                  L"ProcessCommandForPropAnnounce",
                  v22);
              }
            }
            else
            {
              CEventLogger::LogError(
                v19,
                &Recoverable_Error,
                L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
                0x61Du,
                L"ProcessCommandForPropAnnounce",
                v18);
            }
          }
          else
          {
            CEventLogger::LogError(
              v17,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
              0x61Bu,
              L"ProcessCommandForPropAnnounce",
              v8);
          }
        }
        else
        {
          CEventLogger::LogError(
            v15,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
            0x61Au,
            L"ProcessCommandForPropAnnounce",
            v8);
        }
      }
      else
      {
        CEventLogger::LogError(
          v13,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
          0x619u,
          L"ProcessCommandForPropAnnounce",
          v8);
      }
    }
    else
    {
      CEventLogger::LogError(
        v11,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
        0x617u,
        L"ProcessCommandForPropAnnounce",
        v10);
    }
  }
  else
  {
    v8 = -2147024882;
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
      0x610u,
      L"ProcessCommandForPropAnnounce",
      0x8007000E);
  }
LABEL_32:
  if ( *a2 )
  {
    SysFreeString(*a2);
    *a2 = 0;
  }
  if ( *a3 )
  {
    SysFreeString(*a3);
    *a3 = 0;
  }
LABEL_36:
  if ( v6 )
    SysFreeString(v6);
  v26 = v8 >= 0;
  if ( v28 )
    ((void (__fastcall *)(struct IXMLDOMNamedNodeMap *))v28->lpVtbl->Release)(v28);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v26;
}

```

## disassembly

```asm
0x1400482bc  mov     [rsp-38h+arg_0], rbx
0x1400482c1  push    rbp
0x1400482c2  push    rsi
0x1400482c3  push    rdi
0x1400482c4  push    r12
0x1400482c6  push    r13
0x1400482c8  push    r14
0x1400482ca  push    r15
0x1400482cc  mov     rbp, rsp
0x1400482cf  sub     rsp, 80h
0x1400482d6  mov     rsi, r8
0x1400482d9  mov     r14, rdx
0x1400482dc  mov     r15, rcx
0x1400482df  xor     r12d, r12d
0x1400482e2  mov     [rbp+arg_18], r12
0x1400482e6  or      r13d, 0FFFFFFFFh
0x1400482ea  mov     [rbp+arg_8], r13w
0x1400482ef  mov     [rbp+var_40], r12
0x1400482f3  mov     [rbp+var_50], r12
0x1400482f7  mov     edi, r12d
0x1400482fa  test    rdx, rdx
0x1400482fd  jnz     short loc_140048336
0x1400482ff  mov     r9d, 60Ch; unsigned int
0x140048305  mov     [rsp+80h+cchCount2], 80004003h; unsigned int
0x14004830d  mov     ebx, 80004003h
0x140048312  lea     rax, aProcesscommand; "ProcessCommandForPropAnnounce"
0x140048319  mov     [rsp+80h+ppv], rax; unsigned __int16 *
0x14004831e  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\core\\lib\\rarecv."...
0x140048325  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14004832c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140048331  jmp     loc_14004867B
0x140048336  test    rsi, rsi
0x140048339  jnz     short loc_140048343
0x14004833b  mov     r9d, 60Dh
0x140048341  jmp     short loc_140048305
0x140048343  lea     rcx, aRccommand; "RCCOMMAND"
0x14004834a  call    cs:__imp_SysAllocString
0x140048351  nop     dword ptr [rax+rax+00h]
0x140048356  mov     rdi, rax
0x140048359  mov     [rbp+lpString1], rax
0x14004835d  test    rax, rax
0x140048360  jnz     short loc_140048377
0x140048362  mov     ebx, 8007000Eh
0x140048367  mov     [rsp+80h+cchCount2], 8007000Eh
0x14004836f  mov     r9d, 610h
0x140048375  jmp     short loc_140048312
0x140048377  lea     rax, [rbp+arg_18]
0x14004837b  mov     [rsp+80h+ppv], rax; ppv
0x140048380  lea     r9, IID_IXMLDOMDocument; riid
0x140048387  xor     edx, edx; pUnkOuter
0x140048389  lea     r8d, [rdx+1]; dwClsContext
0x14004838d  lea     rcx, CLSID_DOMDocument60; rclsid
0x140048394  call    cs:__imp_CoCreateInstance
0x14004839b  nop     dword ptr [rax+rax+00h]
0x1400483a0  mov     ebx, eax
0x1400483a2  test    eax, eax
0x1400483a4  jns     short loc_1400483B5
0x1400483a6  mov     [rsp+80h+cchCount2], eax
0x1400483aa  mov     r9d, 617h
0x1400483b0  jmp     loc_140048312
0x1400483b5  mov     rcx, [rbp+arg_18]
0x1400483b9  mov     rax, [rcx]
0x1400483bc  mov     edx, 0Bh
0x1400483c1  mov     word ptr [rbp+pvarg], dx
0x1400483c5  mov     word ptr [rbp+pvarg+8], r13w
0x1400483ca  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400483ce  movaps  [rbp+var_20], xmm0
0x1400483d2  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400483d7  movsd   [rbp+var_10], xmm1
0x1400483dc  lea     r8, [rbp+var_20]
0x1400483e0  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x1400483e7  mov     rax, [rax+280h]
0x1400483ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400483f3  mov     ebx, eax
0x1400483f5  lea     rcx, [rbp+pvarg]; pvarg
0x1400483f9  call    cs:__imp_VariantClear
0x140048400  nop     dword ptr [rax+rax+00h]
0x140048405  test    ebx, ebx
0x140048407  jns     short loc_140048418
0x140048409  mov     [rsp+80h+cchCount2], ebx
0x14004840d  mov     r9d, 619h
0x140048413  jmp     loc_140048312
0x140048418  mov     rcx, [rbp+arg_18]
0x14004841c  mov     rax, [rcx]
0x14004841f  mov     edx, 0Bh
0x140048424  mov     word ptr [rbp+pvarg], dx
0x140048428  mov     word ptr [rbp+pvarg+8], r12w
0x14004842d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140048431  movaps  [rbp+var_20], xmm0
0x140048435  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x14004843a  movsd   [rbp+var_10], xmm1
0x14004843f  lea     r8, [rbp+var_20]
0x140048443  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x14004844a  mov     rax, [rax+280h]
0x140048451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048456  mov     ebx, eax
0x140048458  lea     rcx, [rbp+pvarg]; pvarg
0x14004845c  call    cs:__imp_VariantClear
0x140048463  nop     dword ptr [rax+rax+00h]
0x140048468  test    ebx, ebx
0x14004846a  jns     short loc_14004847B
0x14004846c  mov     [rsp+80h+cchCount2], ebx
0x140048470  mov     r9d, 61Ah
0x140048476  jmp     loc_140048312
0x14004847b  mov     rcx, [rbp+arg_18]
0x14004847f  mov     rax, [rcx]
0x140048482  mov     edx, 0Bh
0x140048487  mov     word ptr [rbp+pvarg], dx
0x14004848b  mov     word ptr [rbp+pvarg+8], r12w
0x140048490  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140048494  movaps  [rbp+var_20], xmm0
0x140048498  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x14004849d  movsd   [rbp+var_10], xmm1
0x1400484a2  lea     r8, [rbp+var_20]
0x1400484a6  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x1400484ad  mov     rax, [rax+280h]
0x1400484b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400484b9  mov     ebx, eax
0x1400484bb  lea     rcx, [rbp+pvarg]; pvarg
0x1400484bf  call    cs:__imp_VariantClear
0x1400484c6  nop     dword ptr [rax+rax+00h]
0x1400484cb  test    ebx, ebx
0x1400484cd  jns     short loc_1400484DE
0x1400484cf  mov     [rsp+80h+cchCount2], ebx
0x1400484d3  mov     r9d, 61Bh
0x1400484d9  jmp     loc_140048312
0x1400484de  mov     rcx, [rbp+arg_18]
0x1400484e2  mov     rax, [rcx]
0x1400484e5  xor     edx, edx
0x1400484e7  mov     rax, [rax+1F8h]
0x1400484ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400484f3  mov     ebx, eax
0x1400484f5  test    eax, eax
0x1400484f7  jns     short loc_140048508
0x1400484f9  mov     [rsp+80h+cchCount2], eax
0x1400484fd  mov     r9d, 61Dh
0x140048503  jmp     loc_140048312
0x140048508  mov     rcx, [rbp+arg_18]
0x14004850c  mov     rax, [rcx]
0x14004850f  lea     r8, [rbp+arg_8]
0x140048513  mov     rdx, r15
0x140048516  mov     rax, [rax+208h]
0x14004851d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048522  test    eax, eax
0x140048524  js      loc_140048676
0x14004852a  cmp     [rbp+arg_8], r12w
0x14004852f  jz      loc_140048676
0x140048535  mov     rcx, [rbp+arg_18]
0x140048539  mov     rax, [rcx]
0x14004853c  lea     r8, [rbp+var_40]
0x140048540  mov     rdx, rdi
0x140048543  mov     rax, [rax+128h]
0x14004854a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004854f  test    eax, eax
0x140048551  js      loc_140048676
0x140048557  mov     rcx, [rbp+var_40]
0x14004855b  test    rcx, rcx
0x14004855e  jz      loc_140048676
0x140048564  mov     rax, [rcx]
0x140048567  lea     rdx, [rbp+var_50]
0x14004856b  mov     rax, [rax+88h]
0x140048572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048577  test    eax, eax
0x140048579  js      loc_140048676
0x14004857f  cmp     [rbp+var_50], r12
0x140048583  setz    al
0x140048586  test    al, al
0x140048588  jnz     loc_140048676
0x14004858e  test    rdi, rdi
0x140048591  jz      short loc_1400485A6
0x140048593  mov     rcx, rdi; bstrString
0x140048596  call    cs:__imp_SysFreeString
0x14004859d  nop     dword ptr [rax+rax+00h]
0x1400485a2  mov     [rbp+lpString1], r12
0x1400485a6  lea     r8, [rbp+lpString1]; unsigned __int16 **
0x1400485aa  lea     rdx, aName; "NAME"
0x1400485b1  mov     rcx, [rbp+var_50]; struct IXMLDOMNamedNodeMap *
0x1400485b5  call    ?GetAttributeFromAttributeList@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeList(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x1400485ba  mov     ebx, eax
0x1400485bc  test    eax, eax
0x1400485be  jns     short loc_1400485F2
0x1400485c0  mov     [rsp+80h+cchCount2], eax; unsigned int
0x1400485c4  lea     rax, aProcesscommand; "ProcessCommandForPropAnnounce"
0x1400485cb  mov     [rsp+80h+ppv], rax; unsigned __int16 *
0x1400485d0  mov     r9d, 636h; unsigned int
0x1400485d6  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\core\\lib\\rarecv."...
0x1400485dd  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400485e4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400485e9  mov     rdi, [rbp+lpString1]
0x1400485ed  jmp     loc_14004867B
0x1400485f2  mov     [rsp+80h+cchCount2], r13d; cchCount2
0x1400485f7  lea     rax, aSettingannounc; "SETTINGANNOUNCE"
0x1400485fe  mov     [rsp+80h+ppv], rax; lpString2
0x140048603  mov     r9d, r13d; cchCount1
0x140048606  mov     rdi, [rbp+lpString1]
0x14004860a  mov     r8, rdi; lpString1
0x14004860d  mov     edx, 1; dwCmpFlags
0x140048612  lea     ecx, [rdx+7Eh]; Locale
0x140048615  call    cs:__imp_CompareStringW
0x14004861c  nop     dword ptr [rax+rax+00h]
0x140048621  cmp     eax, 2
0x140048624  jnz     short loc_140048676
0x140048626  mov     r8, r14; unsigned __int16 **
0x140048629  lea     rdx, aProperty; "PROPERTY"
0x140048630  mov     rcx, [rbp+var_50]; struct IXMLDOMNamedNodeMap *
0x140048634  call    ?GetAttributeFromAttributeList@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeList(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x140048639  mov     ebx, eax
0x14004863b  test    eax, eax
0x14004863d  jns     short loc_14004864E
0x14004863f  mov     [rsp+80h+cchCount2], eax
0x140048643  mov     r9d, 64Ch
0x140048649  jmp     loc_140048312
0x14004864e  mov     r8, rsi; unsigned __int16 **
0x140048651  lea     rdx, aValue; "VALUE"
0x140048658  mov     rcx, [rbp+var_50]; struct IXMLDOMNamedNodeMap *
0x14004865c  call    ?GetAttributeFromAttributeList@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z; GetAttributeFromAttributeList(IXMLDOMNamedNodeMap *,ushort *,ushort * *)
0x140048661  mov     ebx, eax
0x140048663  test    eax, eax
0x140048665  jns     short loc_1400486A9
0x140048667  mov     [rsp+80h+cchCount2], eax
0x14004866b  mov     r9d, 651h
0x140048671  jmp     loc_140048312
0x140048676  mov     ebx, 80004005h
0x14004867b  mov     rcx, [r14]; bstrString
0x14004867e  test    rcx, rcx
0x140048681  jz      short loc_140048692
0x140048683  call    cs:__imp_SysFreeString
0x14004868a  nop     dword ptr [rax+rax+00h]
0x14004868f  mov     [r14], r12
0x140048692  mov     rcx, [rsi]; bstrString
0x140048695  test    rcx, rcx
0x140048698  jz      short loc_1400486A9
0x14004869a  call    cs:__imp_SysFreeString
0x1400486a1  nop     dword ptr [rax+rax+00h]
0x1400486a6  mov     [rsi], r12
0x1400486a9  test    rdi, rdi
0x1400486ac  jz      short loc_1400486BE
0x1400486ae  mov     rcx, rdi; bstrString
0x1400486b1  call    cs:__imp_SysFreeString
0x1400486b8  nop     dword ptr [rax+rax+00h]
0x1400486bd  nop
0x1400486be  not     ebx
0x1400486c0  shr     ebx, 1Fh
0x1400486c3  mov     rcx, [rbp+var_50]
0x1400486c7  test    rcx, rcx
0x1400486ca  jz      short loc_1400486D9
0x1400486cc  mov     rax, [rcx]
0x1400486cf  mov     rax, [rax+10h]
0x1400486d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400486d8  nop
0x1400486d9  mov     rcx, [rbp+var_40]
0x1400486dd  test    rcx, rcx
0x1400486e0  jz      short loc_1400486EF
0x1400486e2  mov     rax, [rcx]
0x1400486e5  mov     rax, [rax+10h]
0x1400486e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400486ee  nop
0x1400486ef  mov     rcx, [rbp+arg_18]
0x1400486f3  test    rcx, rcx
0x1400486f6  jz      short loc_140048705
0x1400486f8  mov     rax, [rcx]
0x1400486fb  mov     rax, [rax+10h]
0x1400486ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048704  nop
0x140048705  mov     eax, ebx
0x140048707  mov     rbx, [rsp+80h+arg_0]
0x14004870f  add     rsp, 80h
0x140048716  pop     r15
0x140048718  pop     r14
0x14004871a  pop     r13
0x14004871c  pop     r12
0x14004871e  pop     rdi
0x14004871f  pop     rsi
0x140048720  pop     rbp
0x140048721  retn
```
