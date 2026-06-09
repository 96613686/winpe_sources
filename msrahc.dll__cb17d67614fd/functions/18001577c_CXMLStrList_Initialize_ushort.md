# CXMLStrList::Initialize(ushort *)

- ea: `0x18001577c`
- end: `0x1800159aa`
- name: `?Initialize@CXMLStrList@@QEAAJPEAG@Z`
- size: `558`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 **this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010184`

## callees

- `0x180014660`
- `0x180015510`
- `0x18001577c`
- `0x18001c010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180015865`
- `OLEAUT32!__imp_VariantClear` at `0x1800158ba`
- `OLEAUT32!__imp_VariantClear` at `0x18001590f`
- `OLEAUT32!__imp_VariantClear` at `0x180015972`
- `OLEAUT32!__imp_VariantClear` at `0x180015865`
- `OLEAUT32!__imp_VariantClear` at `0x1800158ba`
- `OLEAUT32!__imp_VariantClear` at `0x18001590f`
- `OLEAUT32!__imp_VariantClear` at `0x180015972`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015803`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015803`

## string_xrefs

- `0x180015992`: `base\diagnosis\ra\racommon\src\xmlutils.cpp`
- `0x180015986`: `CXMLStrList::Initialize`

## pseudocode

```c
__int64 __fastcall CXMLStrList::Initialize(struct IXMLDOMDocument2 **this, unsigned __int16 *a2)
{
  signed int inited; // eax
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  signed int v6; // ebx
  signed int v7; // eax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  HRESULT Instance; // eax
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  CEventLogger *v12; // rcx
  struct IXMLDOMDocument2 *v13; // rcx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  unsigned int v17; // r9d
  struct IXMLDOMDocument2 *v18; // rcx
  struct IXMLDOMDocument2Vtbl *v19; // rax
  struct IXMLDOMDocument2 *v20; // rcx
  struct IXMLDOMDocument2Vtbl *v21; // rax
  struct IXMLDOMDocument2 *v22; // rcx
  struct IXMLDOMDocument2Vtbl *v23; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG v26; // [rsp+50h] [rbp-28h] BYREF

  if ( a2 )
  {
    inited = InitXMLDocWithString(a2, this);
    v6 = inited;
    if ( inited >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, struct IXMLDOMDocument2 **))(*this)->lpVtbl->selectSingleNode)(
             *this,
             L"StringList",
             this + 1);
      v6 = v7;
      if ( v7 < 0 )
        CEventLogger::LogError(
          v9,
          v8,
          L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
          0x99u,
          L"CXMLStrList::Initialize",
          v7);
    }
    else
    {
      CEventLogger::LogError(
        v5,
        v4,
        L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
        0x95u,
        L"CXMLStrList::Initialize",
        inited);
    }
  }
  else
  {
    Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, (LPVOID *)this);
    v6 = Instance;
    if ( Instance >= 0 )
    {
      v13 = *this;
      lpVtbl = (*this)->lpVtbl;
      pvarg.vt = 11;
      pvarg.iVal = -1;
      v26 = pvarg;
      v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, VARIANTARG *))lpVtbl->setProperty)(
             v13,
             L"ProhibitDTD",
             &v26);
      VariantClear(&pvarg);
      if ( v6 >= 0 )
      {
        v18 = *this;
        v19 = (*this)->lpVtbl;
        pvarg.vt = 11;
        pvarg.iVal = 0;
        v26 = pvarg;
        v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, VARIANTARG *))v19->setProperty)(
               v18,
               L"AllowXsltScript",
               &v26);
        VariantClear(&pvarg);
        if ( v6 >= 0 )
        {
          v20 = *this;
          v21 = (*this)->lpVtbl;
          pvarg.vt = 11;
          pvarg.iVal = 0;
          v26 = pvarg;
          v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, VARIANTARG *))v21->setProperty)(
                 v20,
                 L"AllowDocumentFunction",
                 &v26);
          VariantClear(&pvarg);
          if ( v6 >= 0 )
          {
            v22 = *this;
            v23 = (*this)->lpVtbl;
            pvarg.vt = 3;
            pvarg.lVal = 1;
            v26 = pvarg;
            v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, const wchar_t *, _QWORD, struct IXMLDOMDocument2 **))v23->createNode)(
                   v22,
                   &v26,
                   L"StringList",
                   0,
                   this + 1);
            VariantClear(&pvarg);
            if ( v6 >= 0 )
              return (unsigned int)v6;
            v17 = 174;
          }
          else
          {
            v17 = 168;
          }
        }
        else
        {
          v17 = 167;
        }
      }
      else
      {
        v17 = 166;
      }
      CEventLogger::LogError(
        v16,
        v15,
        L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
        v17,
        L"CXMLStrList::Initialize",
        v6);
      return (unsigned int)v6;
    }
    CEventLogger::LogError(
      v12,
      v11,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      0xA4u,
      L"CXMLStrList::Initialize",
      Instance);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001577c  push    rbp
0x18001577e  push    rbx
0x18001577f  push    rdi
0x180015780  push    r14
0x180015782  mov     rbp, rsp
0x180015785  sub     rsp, 78h
0x180015789  mov     rax, rdx
0x18001578c  mov     rdi, rcx
0x18001578f  test    rdx, rdx
0x180015792  jz      short loc_1800157EA
0x180015794  mov     rdx, rcx; struct IXMLDOMDocument2 **
0x180015797  mov     rcx, rax; unsigned __int16 *
0x18001579a  call    ?InitXMLDocWithString@@YAJQEAGPEAPEAUIXMLDOMDocument2@@@Z; InitXMLDocWithString(ushort * const,IXMLDOMDocument2 * *)
0x18001579f  mov     ebx, eax
0x1800157a1  test    eax, eax
0x1800157a3  jns     short loc_1800157B4
0x1800157a5  mov     [rsp+78h+var_50], eax
0x1800157a9  mov     r9d, 95h
0x1800157af  jmp     loc_180015986
0x1800157b4  mov     rcx, [rdi]
0x1800157b7  mov     rax, [rcx]
0x1800157ba  lea     r8, [rdi+8]
0x1800157be  lea     rdx, aStringlist; "StringList"
0x1800157c5  mov     rax, [rax+128h]
0x1800157cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157d1  mov     ebx, eax
0x1800157d3  test    eax, eax
0x1800157d5  jns     loc_18001599E
0x1800157db  mov     [rsp+78h+var_50], eax
0x1800157df  mov     r9d, 99h
0x1800157e5  jmp     loc_180015986
0x1800157ea  mov     [rsp+78h+ppv], rdi; ppv
0x1800157ef  lea     r9, IID_IXMLDOMDocument; riid
0x1800157f6  xor     edx, edx; pUnkOuter
0x1800157f8  lea     r8d, [rdx+1]; dwClsContext
0x1800157fc  lea     rcx, CLSID_DOMDocument60; rclsid
0x180015803  call    cs:__imp_CoCreateInstance
0x180015809  mov     ebx, eax
0x18001580b  test    eax, eax
0x18001580d  jns     short loc_18001581E
0x18001580f  mov     [rsp+78h+var_50], eax
0x180015813  mov     r9d, 0A4h
0x180015819  jmp     loc_180015986
0x18001581e  mov     rcx, [rdi]
0x180015821  mov     rax, [rcx]
0x180015824  mov     r14d, 0Bh
0x18001582a  mov     word ptr [rbp+pvarg], r14w
0x18001582f  or      edx, 0FFFFFFFFh
0x180015832  mov     word ptr [rbp+pvarg+8], dx
0x180015836  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001583a  movaps  [rbp+var_28], xmm0
0x18001583e  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180015843  movsd   [rbp+var_18], xmm1
0x180015848  lea     r8, [rbp+var_28]
0x18001584c  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x180015853  mov     rax, [rax+280h]
0x18001585a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001585f  mov     ebx, eax
0x180015861  lea     rcx, [rbp+pvarg]; pvarg
0x180015865  call    cs:__imp_VariantClear
0x18001586b  test    ebx, ebx
0x18001586d  jns     short loc_18001587A
0x18001586f  mov     r9d, 0A6h
0x180015875  jmp     loc_180015982
0x18001587a  mov     rcx, [rdi]
0x18001587d  mov     rax, [rcx]
0x180015880  mov     word ptr [rbp+pvarg], r14w
0x180015885  xor     edx, edx
0x180015887  mov     word ptr [rbp+pvarg+8], dx
0x18001588b  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001588f  movaps  [rbp+var_28], xmm0
0x180015893  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180015898  movsd   [rbp+var_18], xmm1
0x18001589d  lea     r8, [rbp+var_28]
0x1800158a1  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x1800158a8  mov     rax, [rax+280h]
0x1800158af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158b4  mov     ebx, eax
0x1800158b6  lea     rcx, [rbp+pvarg]; pvarg
0x1800158ba  call    cs:__imp_VariantClear
0x1800158c0  test    ebx, ebx
0x1800158c2  jns     short loc_1800158CF
0x1800158c4  mov     r9d, 0A7h
0x1800158ca  jmp     loc_180015982
0x1800158cf  mov     rcx, [rdi]
0x1800158d2  mov     rax, [rcx]
0x1800158d5  mov     word ptr [rbp+pvarg], r14w
0x1800158da  xor     edx, edx
0x1800158dc  mov     word ptr [rbp+pvarg+8], dx
0x1800158e0  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800158e4  movaps  [rbp+var_28], xmm0
0x1800158e8  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800158ed  movsd   [rbp+var_18], xmm1
0x1800158f2  lea     r8, [rbp+var_28]
0x1800158f6  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x1800158fd  mov     rax, [rax+280h]
0x180015904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015909  mov     ebx, eax
0x18001590b  lea     rcx, [rbp+pvarg]; pvarg
0x18001590f  call    cs:__imp_VariantClear
0x180015915  test    ebx, ebx
0x180015917  jns     short loc_180015921
0x180015919  mov     r9d, 0A8h
0x18001591f  jmp     short loc_180015982
0x180015921  mov     rcx, [rdi]
0x180015924  mov     rax, [rcx]
0x180015927  mov     edx, 3
0x18001592c  mov     word ptr [rbp+pvarg], dx
0x180015930  mov     dword ptr [rbp+pvarg+8], 1
0x180015937  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001593b  movaps  [rbp+var_28], xmm0
0x18001593f  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180015944  movsd   [rbp+var_18], xmm1
0x180015949  lea     rdx, [rdi+8]
0x18001594d  mov     [rsp+78h+ppv], rdx
0x180015952  xor     r9d, r9d
0x180015955  lea     r8, aStringlist; "StringList"
0x18001595c  lea     rdx, [rbp+var_28]
0x180015960  mov     rax, [rax+1C0h]
0x180015967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001596c  mov     ebx, eax
0x18001596e  lea     rcx, [rbp+pvarg]; pvarg
0x180015972  call    cs:__imp_VariantClear
0x180015978  test    ebx, ebx
0x18001597a  jns     short loc_18001599E
0x18001597c  mov     r9d, 0AEh; unsigned int
0x180015982  mov     [rsp+78h+var_50], ebx; unsigned int
0x180015986  lea     rax, aCxmlstrlistIni; "CXMLStrList::Initialize"
0x18001598d  mov     [rsp+78h+ppv], rax; unsigned __int16 *
0x180015992  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\racommon\\src\\xml"...
0x180015999  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18001599e  mov     eax, ebx
0x1800159a0  add     rsp, 78h
0x1800159a4  pop     r14
0x1800159a6  pop     rdi
0x1800159a7  pop     rbx
0x1800159a8  pop     rbp
0x1800159a9  retn
```
