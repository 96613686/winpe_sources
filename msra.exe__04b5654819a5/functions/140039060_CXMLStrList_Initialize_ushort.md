# CXMLStrList::Initialize(ushort *)

- ea: `0x140039060`
- end: `0x140039256`
- name: `?Initialize@CXMLStrList@@QEAAJPEAG@Z`
- size: `502`
- prototype: `__int64 __fastcall(LPVOID *ppv, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140026270`

## callees

- `0x140034ce4`
- `0x140039060`
- `0x14004d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140039089`
- `ole32!CoCreateInstance` at `0x140039089`
- `OLEAUT32!__imp_VariantClear` at `0x1400390f1`
- `OLEAUT32!__imp_VariantClear` at `0x14003914c`
- `OLEAUT32!__imp_VariantClear` at `0x1400391a7`
- `OLEAUT32!__imp_VariantClear` at `0x140039210`
- `OLEAUT32!__imp_VariantClear` at `0x1400390f1`
- `OLEAUT32!__imp_VariantClear` at `0x14003914c`
- `OLEAUT32!__imp_VariantClear` at `0x1400391a7`
- `OLEAUT32!__imp_VariantClear` at `0x140039210`

## string_xrefs

- `0x140039236`: `base\diagnosis\ra\racommon\src\xmlutils.cpp`
- `0x14003922a`: `CXMLStrList::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXMLStrList::Initialize(LPVOID *ppv, unsigned __int16 *a2)
{
  HRESULT Instance; // eax
  CEventLogger *v4; // rcx
  signed int v5; // ebx
  LPVOID v6; // rcx
  __int64 v7; // rax
  CEventLogger *v8; // rcx
  unsigned int v9; // r9d
  LPVOID v10; // rcx
  __int64 v11; // rax
  LPVOID v12; // rcx
  __int64 v13; // rax
  LPVOID v14; // rcx
  __int64 v15; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG v18; // [rsp+50h] [rbp-28h] BYREF

  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, ppv);
  v5 = Instance;
  if ( Instance >= 0 )
  {
    v6 = *ppv;
    v7 = *(_QWORD *)*ppv;
    pvarg.vt = 11;
    pvarg.iVal = -1;
    v18 = pvarg;
    v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v7 + 640))(v6, L"ProhibitDTD", &v18);
    VariantClear(&pvarg);
    if ( v5 >= 0 )
    {
      v10 = *ppv;
      v11 = *(_QWORD *)*ppv;
      pvarg.vt = 11;
      pvarg.iVal = 0;
      v18 = pvarg;
      v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v11 + 640))(v10, L"AllowXsltScript", &v18);
      VariantClear(&pvarg);
      if ( v5 >= 0 )
      {
        v12 = *ppv;
        v13 = *(_QWORD *)*ppv;
        pvarg.vt = 11;
        pvarg.iVal = 0;
        v18 = pvarg;
        v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v13 + 640))(
               v12,
               L"AllowDocumentFunction",
               &v18);
        VariantClear(&pvarg);
        if ( v5 >= 0 )
        {
          v14 = *ppv;
          v15 = *(_QWORD *)*ppv;
          pvarg.vt = 3;
          pvarg.lVal = 1;
          v18 = pvarg;
          v5 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, const wchar_t *, _QWORD, LPVOID *))(v15 + 448))(
                 v14,
                 &v18,
                 L"StringList",
                 0,
                 ppv + 1);
          VariantClear(&pvarg);
          if ( v5 >= 0 )
            return (unsigned int)v5;
          v9 = 174;
        }
        else
        {
          v9 = 168;
        }
      }
      else
      {
        v9 = 167;
      }
    }
    else
    {
      v9 = 166;
    }
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      v9,
      L"CXMLStrList::Initialize",
      v5);
    return (unsigned int)v5;
  }
  CEventLogger::LogError(
    v4,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
    0xA4u,
    L"CXMLStrList::Initialize",
    Instance);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140039060  push    rbp
0x140039062  push    rbx
0x140039063  push    rdi
0x140039064  push    r14
0x140039066  mov     rbp, rsp
0x140039069  sub     rsp, 78h
0x14003906d  mov     rdi, rcx
0x140039070  mov     [rsp+78h+ppv], rcx; ppv
0x140039075  lea     r9, IID_IXMLDOMDocument; riid
0x14003907c  xor     edx, edx; pUnkOuter
0x14003907e  lea     r8d, [rdx+1]; dwClsContext
0x140039082  lea     rcx, CLSID_DOMDocument60; rclsid
0x140039089  call    cs:__imp_CoCreateInstance
0x140039090  nop     dword ptr [rax+rax+00h]
0x140039095  mov     ebx, eax
0x140039097  test    eax, eax
0x140039099  jns     short loc_1400390AA
0x14003909b  mov     [rsp+78h+var_50], eax
0x14003909f  mov     r9d, 0A4h
0x1400390a5  jmp     loc_14003922A
0x1400390aa  mov     rcx, [rdi]
0x1400390ad  mov     rax, [rcx]
0x1400390b0  mov     r14d, 0Bh
0x1400390b6  mov     word ptr [rbp+pvarg], r14w
0x1400390bb  or      edx, 0FFFFFFFFh
0x1400390be  mov     word ptr [rbp+pvarg+8], dx
0x1400390c2  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400390c6  movaps  [rbp+var_28], xmm0
0x1400390ca  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400390cf  movsd   [rbp+var_18], xmm1
0x1400390d4  lea     r8, [rbp+var_28]
0x1400390d8  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x1400390df  mov     rax, [rax+280h]
0x1400390e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400390eb  mov     ebx, eax
0x1400390ed  lea     rcx, [rbp+pvarg]; pvarg
0x1400390f1  call    cs:__imp_VariantClear
0x1400390f8  nop     dword ptr [rax+rax+00h]
0x1400390fd  test    ebx, ebx
0x1400390ff  jns     short loc_14003910C
0x140039101  mov     r9d, 0A6h
0x140039107  jmp     loc_140039226
0x14003910c  mov     rcx, [rdi]
0x14003910f  mov     rax, [rcx]
0x140039112  mov     word ptr [rbp+pvarg], r14w
0x140039117  xor     edx, edx
0x140039119  mov     word ptr [rbp+pvarg+8], dx
0x14003911d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140039121  movaps  [rbp+var_28], xmm0
0x140039125  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x14003912a  movsd   [rbp+var_18], xmm1
0x14003912f  lea     r8, [rbp+var_28]
0x140039133  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x14003913a  mov     rax, [rax+280h]
0x140039141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039146  mov     ebx, eax
0x140039148  lea     rcx, [rbp+pvarg]; pvarg
0x14003914c  call    cs:__imp_VariantClear
0x140039153  nop     dword ptr [rax+rax+00h]
0x140039158  test    ebx, ebx
0x14003915a  jns     short loc_140039167
0x14003915c  mov     r9d, 0A7h
0x140039162  jmp     loc_140039226
0x140039167  mov     rcx, [rdi]
0x14003916a  mov     rax, [rcx]
0x14003916d  mov     word ptr [rbp+pvarg], r14w
0x140039172  xor     edx, edx
0x140039174  mov     word ptr [rbp+pvarg+8], dx
0x140039178  movups  xmm0, xmmword ptr [rbp+pvarg]
0x14003917c  movaps  [rbp+var_28], xmm0
0x140039180  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140039185  movsd   [rbp+var_18], xmm1
0x14003918a  lea     r8, [rbp+var_28]
0x14003918e  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x140039195  mov     rax, [rax+280h]
0x14003919c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400391a1  mov     ebx, eax
0x1400391a3  lea     rcx, [rbp+pvarg]; pvarg
0x1400391a7  call    cs:__imp_VariantClear
0x1400391ae  nop     dword ptr [rax+rax+00h]
0x1400391b3  test    ebx, ebx
0x1400391b5  jns     short loc_1400391BF
0x1400391b7  mov     r9d, 0A8h
0x1400391bd  jmp     short loc_140039226
0x1400391bf  mov     rcx, [rdi]
0x1400391c2  mov     rax, [rcx]
0x1400391c5  mov     edx, 3
0x1400391ca  mov     word ptr [rbp+pvarg], dx
0x1400391ce  mov     dword ptr [rbp+pvarg+8], 1
0x1400391d5  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400391d9  movaps  [rbp+var_28], xmm0
0x1400391dd  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400391e2  movsd   [rbp+var_18], xmm1
0x1400391e7  lea     rdx, [rdi+8]
0x1400391eb  mov     [rsp+78h+ppv], rdx
0x1400391f0  xor     r9d, r9d
0x1400391f3  lea     r8, aStringlist; "StringList"
0x1400391fa  lea     rdx, [rbp+var_28]
0x1400391fe  mov     rax, [rax+1C0h]
0x140039205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003920a  mov     ebx, eax
0x14003920c  lea     rcx, [rbp+pvarg]; pvarg
0x140039210  call    cs:__imp_VariantClear
0x140039217  nop     dword ptr [rax+rax+00h]
0x14003921c  test    ebx, ebx
0x14003921e  jns     short loc_140039249
0x140039220  mov     r9d, 0AEh; unsigned int
0x140039226  mov     [rsp+78h+var_50], ebx; unsigned int
0x14003922a  lea     rax, aCxmlstrlistIni; "CXMLStrList::Initialize"
0x140039231  mov     [rsp+78h+ppv], rax; unsigned __int16 *
0x140039236  lea     r8, aBaseDiagnosisR_25; "base\\diagnosis\\ra\\racommon\\src\\xml"...
0x14003923d  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140039244  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140039249  mov     eax, ebx
0x14003924b  add     rsp, 78h
0x14003924f  pop     r14
0x140039251  pop     rdi
0x140039252  pop     rbx
0x140039253  pop     rbp
0x140039254  retn
```
