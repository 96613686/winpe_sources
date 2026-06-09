# WebRuntimeDiagnostics::DiagnosticsTarget::CreateRemoteDiagnosticsSite(ulong,void * *,void * *)

- ea: `0x1800131c4`
- end: `0x180013537`
- name: `?CreateRemoteDiagnosticsSite@DiagnosticsTarget@WebRuntimeDiagnostics@@AEBAXKPEAPEAX0@Z`
- size: `883`
- prototype: `void __fastcall(WebRuntimeDiagnostics::DiagnosticsTarget *__hidden this, unsigned int, void **, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001dc30`
- `0x18001de38`
- `0x18001e1a0`

## callees

- `0x18000b0ec`
- `0x180012ed4`
- `0x1800131c4`
- `0x180018b30`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180013364`
- `OLEAUT32!__imp_VariantInit` at `0x180013364`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001329a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001329a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180013457`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180013457`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001342a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001342a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800132cd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800133ef`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800132cd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800133ef`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180013319`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800134e5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180013319`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800134e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WebRuntimeDiagnostics::DiagnosticsTarget::CreateRemoteDiagnosticsSite(
        WebRuntimeDiagnostics::DiagnosticsTarget *this,
        int a2,
        void **a3,
        void **a4)
{
  __int64 v8; // rax
  __int64 v9; // rbx
  struct IDispatch **v10; // r8
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, GUID *, __int64 *); // rbx
  int v13; // eax
  SAFEARRAY *v14; // rax
  const char *v15; // r9
  SAFEARRAY *v16; // rbx
  HRESULT v17; // eax
  HRESULT v18; // eax
  int v19; // eax
  const char *v20; // r9
  HRESULT v21; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  const char *v24; // r9
  _QWORD *v25; // rax
  void *v26; // rdx
  HRESULT v27; // eax
  int v28; // [rsp+20h] [rbp-49h]
  LONG plLbound; // [rsp+40h] [rbp-29h] BYREF
  void *ppvData; // [rsp+48h] [rbp-21h] BYREF
  __int64 v31; // [rsp+50h] [rbp-19h] BYREF
  struct HWND__ v32[2]; // [rsp+58h] [rbp-11h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-9h] BYREF
  void *v34; // [rsp+68h] [rbp-1h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp+7h] BYREF
  int v36[4]; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v37; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  LONG plUbound; // [rsp+D0h] [rbp+67h] BYREF

  v8 = *((_QWORD *)this + 16);
  if ( v8 )
  {
    *a3 = *(void **)(v8 + 40);
    *a4 = *(void **)(*((_QWORD *)this + 16) + 48LL);
  }
  else
  {
    *(_QWORD *)&v32[0].unused = 0;
    v9 = *((_QWORD *)this + 6);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v32);
    WebRuntimeDiagnostics::GetHtmlDocumentFromHwnd(*(HWND *)(v9 + 8), v32, v10);
    v31 = 0;
    v11 = *(_QWORD *)&v32[0].unused;
    v12 = ***(__int64 (__fastcall ****)(__int64, GUID *, __int64 *))&v32[0].unused;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v13 = v12(v11, &GUID_b722bccb_4e68_101b_a2bc_00aa00404770, &v31);
    if ( v13 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x236,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)v13,
        v28);
    rgsabound = (SAFEARRAYBOUND)2LL;
    v14 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v16 = v14;
    if ( !v14 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x23E,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        v15);
    ppvData = 0;
    v17 = SafeArrayAccessData(v14, &ppvData);
    if ( v17 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)v17,
        v28);
    *(_WORD *)ppvData = 19;
    *((_DWORD *)ppvData + 2) = a2;
    *((_WORD *)ppvData + 12) = 19;
    *((_DWORD *)ppvData + 8) = *((_DWORD *)this + 18);
    v18 = SafeArrayUnaccessData(v16);
    if ( v18 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x24B,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)v18,
        v28);
    *(_QWORD *)v36 = 8204;
    v37 = 0;
    *(_QWORD *)&v36[2] = v16;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v19 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, _QWORD))(*(_QWORD *)v31 + 32LL))(
            v31,
            &CGID_MSHTML,
            3802,
            0);
    if ( v19 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x253,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)v19,
        (int)v36);
    v34 = 0;
    if ( pvarg.vt != 8213 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x256,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        v20);
    v21 = SafeArrayAccessData(pvarg.parray, &v34);
    if ( v21 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x257,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)v21,
        (int)v36);
    plLbound = 0;
    plUbound = 0;
    LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
    if ( LBound < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x25B,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)LBound,
        (int)v36);
    UBound = SafeArrayGetUBound(pvarg.parray, 1u, &plUbound);
    if ( UBound < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x25C,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)UBound,
        (int)v36);
    if ( plUbound - plLbound != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        v24);
    v25 = v34;
    if ( !*(_QWORD *)v34 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x25F,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        v24);
    *a3 = *(void **)v34;
    v26 = (void *)v25[1];
    if ( !v26 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x260,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        v24);
    *a4 = v26;
    v27 = SafeArrayUnaccessData(pvarg.parray);
    if ( v27 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x262,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
        (const char *)(unsigned int)v27,
        (int)v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v32);
  }
}

```

## disassembly

```asm
0x1800131c4  mov     [rsp-8+arg_8], rbx
0x1800131c9  mov     [rsp-8+arg_10], rsi
0x1800131ce  push    rbp
0x1800131cf  push    rdi
0x1800131d0  push    r12
0x1800131d2  push    r14
0x1800131d4  push    r15
0x1800131d6  lea     rbp, [rsp-37h]
0x1800131db  sub     rsp, 0A0h
0x1800131e2  mov     r15, r9
0x1800131e5  mov     r14, r8
0x1800131e8  mov     r12d, edx
0x1800131eb  mov     rsi, rcx
0x1800131ee  mov     rax, [rcx+80h]
0x1800131f5  test    rax, rax
0x1800131f8  jz      short loc_180013214
0x1800131fa  mov     rax, [rax+28h]
0x1800131fe  mov     [r8], rax
0x180013201  mov     rax, [rcx+80h]
0x180013208  mov     rcx, [rax+30h]
0x18001320c  mov     [r9], rcx
0x18001320f  jmp     loc_18001351B
0x180013214  mov     qword ptr [rbp+57h+var_68.unused], 0
0x18001321c  mov     rbx, [rcx+30h]
0x180013220  lea     rcx, [rbp+57h+var_68]
0x180013224  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013229  lea     rdx, [rbp+57h+var_68]; HWND
0x18001322d  mov     rcx, [rbx+8]; hWnd
0x180013231  call    ?GetHtmlDocumentFromHwnd@WebRuntimeDiagnostics@@YAXQEAUHWND__@@PEAPEAUIDispatch@@@Z; WebRuntimeDiagnostics::GetHtmlDocumentFromHwnd(HWND__ * const,IDispatch * *)
0x180013236  mov     [rbp+57h+var_70], 0
0x18001323e  mov     rdi, qword ptr [rbp+57h+var_68.unused]
0x180013242  mov     rax, [rdi]
0x180013245  mov     rbx, [rax]
0x180013248  lea     rcx, [rbp+57h+var_70]
0x18001324c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013251  lea     r8, [rbp+57h+var_70]
0x180013255  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x18001325c  mov     rcx, rdi
0x18001325f  mov     rax, rbx
0x180013262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013267  mov     rcx, [rbp+5Fh]; this
0x18001326b  test    eax, eax
0x18001326d  jns     short loc_180013284
0x18001326f  mov     r9d, eax; char *
0x180013272  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180013279  mov     edx, 236h; void *
0x18001327e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180013284  mov     qword ptr [rbp+57h+rgsabound.cElements], 2
0x18001328c  mov     ecx, 0Ch; vt
0x180013291  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180013295  lea     edi, [rcx-0Bh]
0x180013298  mov     edx, edi; cDims
0x18001329a  call    cs:__imp_SafeArrayCreate
0x1800132a0  mov     rbx, rax
0x1800132a3  mov     rcx, [rbp+5Fh]; this
0x1800132a7  test    rax, rax
0x1800132aa  jnz     short loc_1800132BE
0x1800132ac  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800132b3  mov     edx, 23Eh; void *
0x1800132b8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800132be  mov     [rbp+57h+ppvData], 0
0x1800132c6  lea     rdx, [rbp+57h+ppvData]; ppvData
0x1800132ca  mov     rcx, rbx; psa
0x1800132cd  call    cs:__imp_SafeArrayAccessData
0x1800132d3  mov     rcx, [rbp+5Fh]; this
0x1800132d7  test    eax, eax
0x1800132d9  jns     short loc_1800132F0
0x1800132db  mov     r9d, eax; char *
0x1800132de  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800132e5  mov     edx, 241h; void *
0x1800132ea  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800132f0  mov     ecx, 13h
0x1800132f5  mov     rax, [rbp+57h+ppvData]
0x1800132f9  mov     [rax], cx
0x1800132fc  mov     rax, [rbp+57h+ppvData]
0x180013300  mov     [rax+8], r12d
0x180013304  mov     rax, [rbp+57h+ppvData]
0x180013308  mov     [rax+18h], cx
0x18001330c  mov     ecx, [rsi+48h]
0x18001330f  mov     rax, [rbp+57h+ppvData]
0x180013313  mov     [rax+20h], ecx
0x180013316  mov     rcx, rbx; psa
0x180013319  call    cs:__imp_SafeArrayUnaccessData
0x18001331f  mov     rcx, [rbp+5Fh]; this
0x180013323  test    eax, eax
0x180013325  jns     short loc_18001333C
0x180013327  mov     r9d, eax; char *
0x18001332a  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180013331  mov     edx, 24Bh; void *
0x180013336  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001333c  xorps   xmm0, xmm0
0x18001333f  xor     eax, eax
0x180013341  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x180013345  mov     [rbp+57h+var_28], rax
0x180013349  mov     eax, 200Ch
0x18001334e  mov     word ptr [rbp+57h+var_38], ax
0x180013352  mov     qword ptr [rbp+57h+var_38+8], rbx
0x180013356  xor     eax, eax
0x180013358  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001335c  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180013360  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180013364  call    cs:__imp_VariantInit
0x18001336a  mov     rcx, [rbp+57h+var_70]
0x18001336e  mov     rax, [rcx]
0x180013371  lea     rdx, [rbp+57h+pvarg]
0x180013375  mov     [rsp+0C0h+var_98], rdx
0x18001337a  lea     rdx, [rbp+57h+var_38]
0x18001337e  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x180013383  xor     r9d, r9d
0x180013386  mov     r8d, 0EDAh
0x18001338c  lea     rdx, CGID_MSHTML
0x180013393  mov     rax, [rax+20h]
0x180013397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001339c  mov     rcx, [rbp+5Fh]; this
0x1800133a0  test    eax, eax
0x1800133a2  jns     short loc_1800133B9
0x1800133a4  mov     r9d, eax; char *
0x1800133a7  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800133ae  mov     edx, 253h; void *
0x1800133b3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800133b9  mov     [rbp+57h+var_58], 0
0x1800133c1  mov     eax, 2015h
0x1800133c6  cmp     word ptr [rbp+57h+pvarg], ax
0x1800133ca  setz    al
0x1800133cd  mov     rcx, [rbp+5Fh]; this
0x1800133d1  test    al, al
0x1800133d3  jnz     short loc_1800133E7
0x1800133d5  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800133dc  mov     edx, 256h; void *
0x1800133e1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800133e7  lea     rdx, [rbp+57h+var_58]; ppvData
0x1800133eb  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x1800133ef  call    cs:__imp_SafeArrayAccessData
0x1800133f5  mov     rcx, [rbp+5Fh]; this
0x1800133f9  test    eax, eax
0x1800133fb  jns     short loc_180013412
0x1800133fd  mov     r9d, eax; char *
0x180013400  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180013407  mov     edx, 257h; void *
0x18001340c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180013412  mov     [rbp+57h+plLbound], 0
0x180013419  mov     [rbp+57h+plUbound], 0
0x180013420  lea     r8, [rbp+57h+plLbound]; plLbound
0x180013424  mov     edx, edi; nDim
0x180013426  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x18001342a  call    cs:__imp_SafeArrayGetLBound
0x180013430  mov     rcx, [rbp+5Fh]; this
0x180013434  test    eax, eax
0x180013436  jns     short loc_18001344D
0x180013438  mov     r9d, eax; char *
0x18001343b  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180013442  mov     edx, 25Bh; void *
0x180013447  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001344d  lea     r8, [rbp+57h+plUbound]; plUbound
0x180013451  mov     edx, edi; nDim
0x180013453  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x180013457  call    cs:__imp_SafeArrayGetUBound
0x18001345d  mov     rcx, [rbp+5Fh]; this
0x180013461  test    eax, eax
0x180013463  jns     short loc_18001347A
0x180013465  mov     r9d, eax; char *
0x180013468  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001346f  mov     edx, 25Ch; void *
0x180013474  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001347a  mov     rcx, [rbp+5Fh]; this
0x18001347e  mov     eax, [rbp+57h+plUbound]
0x180013481  sub     eax, [rbp+57h+plLbound]
0x180013484  cmp     eax, edi
0x180013486  jz      short loc_18001349A
0x180013488  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001348f  mov     edx, 25Dh; void *
0x180013494  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001349a  mov     rax, [rbp+57h+var_58]
0x18001349e  mov     rdx, [rax]
0x1800134a1  mov     rcx, [rbp+5Fh]; this
0x1800134a5  test    rdx, rdx
0x1800134a8  jnz     short loc_1800134BC
0x1800134aa  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800134b1  mov     edx, 25Fh; void *
0x1800134b6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800134bc  mov     [r14], rdx
0x1800134bf  mov     rdx, [rax+8]
0x1800134c3  mov     rcx, [rbp+5Fh]; this
0x1800134c7  test    rdx, rdx
0x1800134ca  jnz     short loc_1800134DE
0x1800134cc  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800134d3  mov     edx, 260h; void *
0x1800134d8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800134de  mov     [r15], rdx
0x1800134e1  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x1800134e5  call    cs:__imp_SafeArrayUnaccessData
0x1800134eb  mov     rcx, [rbp+5Fh]; this
0x1800134ef  test    eax, eax
0x1800134f1  jns     short loc_180013508
0x1800134f3  mov     r9d, eax; char *
0x1800134f6  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800134fd  mov     edx, 262h; void *
0x180013502  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180013508  lea     rcx, [rbp+57h+var_70]
0x18001350c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013511  nop
0x180013512  lea     rcx, [rbp+57h+var_68]
0x180013516  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001351b  lea     r11, [rsp+0C0h+var_20]
0x180013523  mov     rbx, [r11+38h]
0x180013527  mov     rsi, [r11+40h]
0x18001352b  mov     rsp, r11
0x18001352e  pop     r15
0x180013530  pop     r14
0x180013532  pop     r12
0x180013534  pop     rdi
0x180013535  pop     rbp
0x180013536  retn
```
