# HlpGetCryptoProviders(IXMLDOMDocument2 *,ushort * * *,ulong *)

- ea: `0x18002a460`
- end: `0x18002ab99`
- name: `?HlpGetCryptoProviders@@YAJPEAUIXMLDOMDocument2@@PEAPEAPEAGPEAK@Z`
- size: `1849`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180028728`

## callees

- `0x18000b0f4`
- `0x1800141b0`
- `0x18002a460`
- `0x18002cf7c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002a6f5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002a6f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a5d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a75c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a5d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a75c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a8b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a8b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a745`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a8a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a745`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a8a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a69a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a69a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a6b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a6b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a6ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a7e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a895`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a92d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a9ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa28`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa83`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aaf7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a6ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a7e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a895`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a92d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a9ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa28`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aa83`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aaf7`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a715`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a715`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall HlpGetCryptoProviders(struct IXMLDOMDocument2 *a1, unsigned __int16 ***a2, unsigned int *a3)
{
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // eax
  __int64 v8; // r13
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v11; // r15
  void (*v12)(void); // rax
  unsigned int v13; // r14d
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, BSTR *); // r12
  OLECHAR *v18; // rdi
  DWORD LastError; // ebx
  int v20; // eax
  wchar_t *v21; // rax
  UINT v22; // eax
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rdi
  HANDLE v25; // rax
  void *v26; // rsi
  unsigned __int64 v27; // rdi
  __int64 v28; // rax
  BSTR v29; // rcx
  OLECHAR *v30; // rdx
  OLECHAR v31; // r8
  OLECHAR *v32; // rcx
  HANDLE v33; // rax
  void (*v34)(void); // rax
  __int64 *v35; // [rsp+20h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v37[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD *v38; // [rsp+40h] [rbp-28h] BYREF
  __int64 v39; // [rsp+48h] [rbp-20h]
  _QWORD v40[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  unsigned int v42; // [rsp+B0h] [rbp+48h] BYREF
  unsigned __int16 ***v43; // [rsp+B8h] [rbp+50h]
  unsigned int *v44; // [rsp+C0h] [rbp+58h]
  int v45; // [rsp+C8h] [rbp+60h] BYREF

  v44 = a3;
  v43 = a2;
  v42 = 0;
  v45 = 0;
  v38 = 0;
  v39 = 0;
  v40[0] = "HlpGetCryptoProviders";
  v40[1] = &v42;
  lpVtbl = a1->lpVtbl;
  v35 = 0;
  v4 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 **))lpVtbl->selectNodes)(
         a1,
         L"//p:GetPoliciesResponse//p:response//p:policies//p:policy//p:attributes//p:privateKeyAttributes//p:cryptoProviders//p:provider",
         &v35);
  v5 = v4;
  v42 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x471,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
      (const char *)(unsigned int)v4,
      (int)v35);
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
    wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    return v5;
  }
  if ( !v35 )
    goto LABEL_40;
  v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v35 + 64))(v35, &v45);
  v5 = v7;
  v42 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x476,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
      (const char *)(unsigned int)v7,
      (int)v35);
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
    wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    return v5;
  }
  if ( !v45 )
    goto LABEL_40;
  if ( 8 * (unsigned __int64)(unsigned int)v45 > 0xFFFFFFFF )
  {
    v5 = -2147024362;
    v42 = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
      (const char *)0x80070216LL,
      (int)v35);
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
    wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
    if ( !v35 )
      return v5;
    v34 = *(void (**)(void))(*v35 + 16);
LABEL_86:
    v34();
    return v5;
  }
  v42 = 0;
  v8 = v45;
  v9 = 8 * v45;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, v9);
  wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
  v38 = v11;
  v39 = v8;
  if ( v11 )
  {
    v13 = 0;
    if ( v45 > 0 )
    {
      while ( 1 )
      {
        v37[0] = 0;
        v37[1] = 0;
        bstrString = 0;
        v14 = *v35;
        v37[0] = 0;
        v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *))(v14 + 56))(v35, v13, v37);
        v5 = v15;
        v42 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x48C,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
            (const char *)(unsigned int)v15,
            (int)v35);
          if ( bstrString )
            SysFreeString(bstrString);
          if ( v37[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
          wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
          if ( v35 )
            (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
          return v5;
        }
        v16 = v37[0];
        v17 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v37[0] + 208LL);
        v18 = bstrString;
        if ( bstrString )
        {
          LastError = GetLastError();
          SysFreeString(v18);
          SetLastError(LastError);
        }
        bstrString = 0;
        v20 = v17(v16, &bstrString);
        v5 = v20;
        v42 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x48F,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
            (const char *)(unsigned int)v20,
            (int)v35);
          if ( bstrString )
            SysFreeString(bstrString);
          if ( v37[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
          wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
          if ( v35 )
            (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
          return v5;
        }
        v21 = wcsrchr(bstrString, 0x20u);
        if ( v21 && !v21[1] )
          *v21 = 0;
        v22 = SysStringLen(bstrString);
        if ( v22 + 1 < v22 )
          break;
        v23 = 2LL * (v22 + 1);
        if ( v23 > 0xFFFFFFFF )
        {
          v5 = -2147024362;
          v42 = -2147024362;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x49F,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
            (const char *)0x80070216LL,
            (int)v35);
          if ( bstrString )
            SysFreeString(bstrString);
          if ( v37[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
          goto LABEL_63;
        }
        v42 = 0;
        v24 = (unsigned int)v23;
        v25 = GetProcessHeap();
        v26 = HeapAlloc(v25, 8u, (unsigned int)v24);
        if ( !v26 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4A2,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
            (const char *)0x8007000ELL,
            (int)v35);
          if ( bstrString )
            SysFreeString(bstrString);
          if ( v37[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
          wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
          if ( v35 )
          {
            v12 = *(void (**)(void))(*v35 + 16);
            goto LABEL_57;
          }
          return 2147942414LL;
        }
        v27 = v24 >> 1;
        if ( !v27 )
        {
          v5 = -2147024809;
          v42 = -2147024809;
LABEL_44:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4A5,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
            (const char *)v5,
            (int)v35);
          if ( bstrString )
            SysFreeString(bstrString);
          v33 = GetProcessHeap();
          HeapFree(v33, 0, v26);
          if ( v37[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
          EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
          wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
          if ( v35 )
            (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
          return v5;
        }
        v28 = 2147483646;
        v29 = bstrString;
        v30 = (OLECHAR *)v26;
        do
        {
          if ( !v28 )
            break;
          v31 = *v29;
          if ( !*v29 )
            break;
          ++v29;
          *v30++ = v31;
          --v28;
          --v27;
        }
        while ( v27 );
        v5 = v27 == 0 ? 0x8007007A : 0;
        v32 = v30 - 1;
        if ( v27 )
          v32 = v30;
        *v32 = 0;
        v42 = v27 == 0 ? 0x8007007A : 0;
        if ( !v27 )
          goto LABEL_44;
        v11[v13] = v26;
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v37[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
        if ( (int)++v13 >= v45 )
          goto LABEL_39;
      }
      v5 = -2147024362;
      v42 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
        (const char *)0x80070216LL,
        (int)v35);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v37[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
LABEL_63:
      EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
      wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
      if ( !v35 )
        return v5;
      v34 = *(void (**)(void))(*v35 + 16);
      goto LABEL_86;
    }
LABEL_39:
    *v44 = v8;
    v38 = 0;
    v39 = 0;
    *v43 = (unsigned __int16 **)v11;
LABEL_40:
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
    wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x481,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\soapparser.cpp",
    (const char *)0x8007000ELL,
    (int)v35);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v40);
  wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v38);
  if ( v35 )
  {
    v12 = *(void (**)(void))(*v35 + 16);
LABEL_57:
    v12();
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002a460  mov     [rsp-40h+arg_10], r8
0x18002a465  mov     [rsp-40h+arg_8], rdx
0x18002a46a  push    rbp
0x18002a46b  push    rbx
0x18002a46c  push    rsi
0x18002a46d  push    rdi
0x18002a46e  push    r12
0x18002a470  push    r13
0x18002a472  push    r14
0x18002a474  push    r15
0x18002a476  mov     rbp, rsp
0x18002a479  sub     rsp, 68h
0x18002a47d  xor     r12d, r12d
0x18002a480  mov     [rbp+arg_0], r12d
0x18002a484  mov     [rbp+arg_18], r12d
0x18002a488  mov     [rbp+var_28], r12
0x18002a48c  mov     [rbp+var_20], r12
0x18002a490  lea     rax, aHlpgetcryptopr; "HlpGetCryptoProviders"
0x18002a497  mov     [rbp+var_18], rax
0x18002a49b  lea     rax, [rbp+arg_0]
0x18002a49f  mov     [rbp+var_10], rax
0x18002a4a3  mov     rax, [rcx]
0x18002a4a6  mov     [rbp+var_48], r12
0x18002a4aa  lea     r8, [rbp+var_48]
0x18002a4ae  lea     rdx, aPGetpoliciesre_10; "//p:GetPoliciesResponse//p:response//p:"...
0x18002a4b5  mov     rax, [rax+120h]
0x18002a4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4c1  mov     ebx, eax
0x18002a4c3  mov     [rbp+arg_0], eax
0x18002a4c6  test    eax, eax
0x18002a4c8  jns     short loc_18002A514
0x18002a4ca  mov     rcx, [rbp+40h]; this
0x18002a4ce  mov     r9d, eax; char *
0x18002a4d1  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002a4d8  mov     edx, 471h; void *
0x18002a4dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a4e2  nop
0x18002a4e3  lea     rcx, [rbp+var_18]; this
0x18002a4e7  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002a4ec  nop
0x18002a4ed  lea     rcx, [rbp+var_28]
0x18002a4f1  call    ?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)
0x18002a4f6  nop
0x18002a4f7  mov     rcx, [rbp+var_48]
0x18002a4fb  test    rcx, rcx
0x18002a4fe  jz      short loc_18002A50D
0x18002a500  mov     rax, [rcx]
0x18002a503  mov     rax, [rax+10h]
0x18002a507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a50c  nop
0x18002a50d  mov     eax, ebx
0x18002a50f  jmp     loc_18002A859
0x18002a514  mov     rcx, [rbp+var_48]
0x18002a518  test    rcx, rcx
0x18002a51b  jz      loc_18002A82D
0x18002a521  mov     rax, [rcx]
0x18002a524  lea     rdx, [rbp+arg_18]
0x18002a528  mov     rax, [rax+40h]
0x18002a52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a531  mov     ebx, eax
0x18002a533  mov     [rbp+arg_0], eax
0x18002a536  test    eax, eax
0x18002a538  jns     short loc_18002A57F
0x18002a53a  mov     rcx, [rbp+40h]; this
0x18002a53e  mov     r9d, eax; char *
0x18002a541  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002a548  mov     edx, 476h; void *
0x18002a54d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a552  nop
0x18002a553  lea     rcx, [rbp+var_18]; this
0x18002a557  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002a55c  nop
0x18002a55d  lea     rcx, [rbp+var_28]
0x18002a561  call    ?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)
0x18002a566  nop
0x18002a567  mov     rcx, [rbp+var_48]
0x18002a56b  test    rcx, rcx
0x18002a56e  jz      short loc_18002A57D
0x18002a570  mov     rax, [rcx]
0x18002a573  mov     rax, [rax+10h]
0x18002a577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a57c  nop
0x18002a57d  jmp     short loc_18002A50D
0x18002a57f  movsxd  rcx, [rbp+arg_18]
0x18002a583  test    ecx, ecx
0x18002a585  jnz     short loc_18002A5A0
0x18002a587  lea     rcx, [rbp+var_18]; this
0x18002a58b  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002a590  nop
0x18002a591  lea     rcx, [rbp+var_28]
0x18002a595  call    ?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)
0x18002a59a  nop
0x18002a59b  jmp     loc_18002A841
0x18002a5a0  mov     eax, ecx
0x18002a5a2  shl     rax, 3
0x18002a5a6  mov     edx, 0FFFFFFFFh
0x18002a5ab  cmp     rax, rdx
0x18002a5ae  ja      loc_18002AB49
0x18002a5b4  mov     [rbp+arg_0], r12d
0x18002a5b8  mov     r13, rcx
0x18002a5bb  mov     ebx, eax
0x18002a5bd  call    cs:__imp_GetProcessHeap
0x18002a5c4  nop     dword ptr [rax+rax+00h]
0x18002a5c9  mov     rcx, rax; hHeap
0x18002a5cc  mov     r8d, ebx; dwBytes
0x18002a5cf  mov     edx, 8; dwFlags
0x18002a5d4  call    cs:__imp_HeapAlloc
0x18002a5db  nop     dword ptr [rax+rax+00h]
0x18002a5e0  mov     r15, rax
0x18002a5e3  lea     rcx, [rbp+var_28]
0x18002a5e7  call    ?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)
0x18002a5ec  mov     [rbp+var_28], r15
0x18002a5f0  mov     [rbp+var_20], r13
0x18002a5f4  test    r15, r15
0x18002a5f7  jnz     short loc_18002A642
0x18002a5f9  mov     rcx, [rbp+40h]; this
0x18002a5fd  mov     r9d, 8007000Eh; char *
0x18002a603  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002a60a  mov     edx, 481h; void *
0x18002a60f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a614  nop
0x18002a615  lea     rcx, [rbp+var_18]; this
0x18002a619  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002a61e  nop
0x18002a61f  lea     rcx, [rbp+var_28]
0x18002a623  call    ?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)
0x18002a628  nop
0x18002a629  mov     rcx, [rbp+var_48]
0x18002a62d  test    rcx, rcx
0x18002a630  jz      loc_18002A97A
0x18002a636  mov     rax, [rcx]
0x18002a639  mov     rax, [rax+10h]
0x18002a63d  jmp     loc_18002A974
0x18002a642  mov     r14d, r12d
0x18002a645  cmp     [rbp+arg_18], r12d
0x18002a649  jle     loc_18002A817
0x18002a64f  mov     [rbp+var_38], r12
0x18002a653  mov     [rbp+var_30], r12
0x18002a657  mov     [rbp+bstrString], r12
0x18002a65b  mov     rcx, [rbp+var_48]
0x18002a65f  mov     rax, [rcx]
0x18002a662  mov     [rbp+var_38], r12
0x18002a666  lea     r8, [rbp+var_38]
0x18002a66a  mov     edx, r14d
0x18002a66d  mov     rax, [rax+38h]
0x18002a671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a676  mov     ebx, eax
0x18002a678  mov     [rbp+arg_0], eax
0x18002a67b  test    eax, eax
0x18002a67d  js      loc_18002AAD5
0x18002a683  mov     rsi, [rbp+var_38]
0x18002a687  mov     rax, [rsi]
0x18002a68a  mov     r12, [rax+0D0h]
0x18002a691  mov     rdi, [rbp+bstrString]
0x18002a695  test    rdi, rdi
0x18002a698  jz      short loc_18002A6C5
0x18002a69a  call    cs:__imp_GetLastError
0x18002a6a1  nop     dword ptr [rax+rax+00h]
0x18002a6a6  mov     ebx, eax
0x18002a6a8  mov     rcx, rdi; bstrString
0x18002a6ab  call    cs:__imp_SysFreeString
0x18002a6b2  nop     dword ptr [rax+rax+00h]
0x18002a6b7  mov     ecx, ebx; dwErrCode
0x18002a6b9  call    cs:__imp_SetLastError
0x18002a6c0  nop     dword ptr [rax+rax+00h]
0x18002a6c5  mov     [rbp+bstrString], 0
0x18002a6cd  lea     rdx, [rbp+bstrString]
0x18002a6d1  mov     rcx, rsi
0x18002a6d4  mov     rax, r12
0x18002a6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6dc  mov     ebx, eax
0x18002a6de  mov     [rbp+arg_0], eax
0x18002a6e1  xor     r12d, r12d
0x18002a6e4  test    eax, eax
0x18002a6e6  js      loc_18002AA61
0x18002a6ec  lea     edx, [r12+20h]; Ch
0x18002a6f1  mov     rcx, [rbp+bstrString]; Str
0x18002a6f5  call    cs:__imp_wcsrchr
0x18002a6fc  nop     dword ptr [rax+rax+00h]
0x18002a701  test    rax, rax
0x18002a704  jz      short loc_18002A711
0x18002a706  cmp     [rax+2], r12w
0x18002a70b  jnz     short loc_18002A711
0x18002a70d  mov     [rax], r12w
0x18002a711  mov     rcx, [rbp+bstrString]; pbstr
0x18002a715  call    cs:__imp_SysStringLen
0x18002a71c  nop     dword ptr [rax+rax+00h]
0x18002a721  lea     ecx, [rax+1]
0x18002a724  cmp     ecx, eax
0x18002a726  jb      loc_18002A9FE
0x18002a72c  mov     eax, ecx
0x18002a72e  add     rax, rax
0x18002a731  mov     ecx, 0FFFFFFFFh
0x18002a736  cmp     rax, rcx
0x18002a739  ja      loc_18002A984
0x18002a73f  mov     [rbp+arg_0], r12d
0x18002a743  mov     edi, eax
0x18002a745  call    cs:__imp_GetProcessHeap
0x18002a74c  nop     dword ptr [rax+rax+00h]
0x18002a751  mov     rcx, rax; hHeap
0x18002a754  mov     r8d, edi; dwBytes
0x18002a757  mov     edx, 8; dwFlags
0x18002a75c  call    cs:__imp_HeapAlloc
0x18002a763  nop     dword ptr [rax+rax+00h]
0x18002a768  mov     rsi, rax
0x18002a76b  test    rax, rax
0x18002a76e  jz      loc_18002A908
0x18002a774  shr     rdi, 1
0x18002a777  jz      loc_18002A86B
0x18002a77d  mov     eax, 7FFFFFFEh
0x18002a782  mov     rcx, [rbp+bstrString]
0x18002a786  mov     rdx, rsi
0x18002a789  test    rax, rax
0x18002a78c  jz      short loc_18002A7AD
0x18002a78e  movzx   r8d, word ptr [rcx]
0x18002a792  test    r8w, r8w
0x18002a796  jz      short loc_18002A7AD
0x18002a798  add     rcx, 2
0x18002a79c  mov     [rdx], r8w
0x18002a7a0  add     rdx, 2
0x18002a7a4  dec     rax
0x18002a7a7  sub     rdi, 1
0x18002a7ab  jnz     short loc_18002A789
0x18002a7ad  mov     rax, rdi
0x18002a7b0  neg     rax
0x18002a7b3  sbb     ebx, ebx
0x18002a7b5  not     ebx
0x18002a7b7  and     ebx, 8007007Ah
0x18002a7bd  lea     rcx, [rdx-2]
0x18002a7c1  test    rdi, rdi
0x18002a7c4  cmovnz  rcx, rdx
0x18002a7c8  mov     [rcx], r12w
0x18002a7cc  mov     [rbp+arg_0], ebx
0x18002a7cf  test    ebx, ebx
0x18002a7d1  js      loc_18002A873
0x18002a7d7  movsxd  rax, r14d
0x18002a7da  mov     [r15+rax*8], rsi
0x18002a7de  mov     rcx, [rbp+bstrString]; bstrString
0x18002a7e2  test    rcx, rcx
0x18002a7e5  jz      short loc_18002A7F4
0x18002a7e7  call    cs:__imp_SysFreeString
0x18002a7ee  nop     dword ptr [rax+rax+00h]
0x18002a7f3  nop
0x18002a7f4  mov     rcx, [rbp+var_38]
0x18002a7f8  test    rcx, rcx
0x18002a7fb  jz      short loc_18002A80A
0x18002a7fd  mov     rax, [rcx]
0x18002a800  mov     rax, [rax+10h]
0x18002a804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a809  nop
0x18002a80a  inc     r14d
0x18002a80d  cmp     r14d, [rbp+arg_18]
0x18002a811  jl      loc_18002A64F
0x18002a817  mov     rax, [rbp+arg_10]
0x18002a81b  mov     [rax], r13d
0x18002a81e  mov     [rbp+var_28], r12
0x18002a822  mov     [rbp+var_20], r12
0x18002a826  mov     rax, [rbp+arg_8]
0x18002a82a  mov     [rax], r15
0x18002a82d  lea     rcx, [rbp+var_18]; this
0x18002a831  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002a836  nop
0x18002a837  lea     rcx, [rbp+var_28]
0x18002a83b  call    ?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)
0x18002a840  nop
0x18002a841  mov     rcx, [rbp+var_48]
0x18002a845  test    rcx, rcx
0x18002a848  jz      short loc_18002A857
0x18002a84a  mov     rax, [rcx]
0x18002a84d  mov     rax, [rax+10h]
0x18002a851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a856  nop
0x18002a857  xor     eax, eax
0x18002a859  add     rsp, 68h
0x18002a85d  pop     r15
0x18002a85f  pop     r14
0x18002a861  pop     r13
0x18002a863  pop     r12
0x18002a865  pop     rdi
0x18002a866  pop     rsi
0x18002a867  pop     rbx
0x18002a868  pop     rbp
0x18002a869  retn
0x18002a86b  mov     ebx, 80070057h
0x18002a870  mov     [rbp+arg_0], ebx
0x18002a873  mov     rcx, [rbp+40h]; this
0x18002a877  mov     r9d, ebx; char *
0x18002a87a  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18002a881  mov     edx, 4A5h; void *
0x18002a886  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a88b  nop
0x18002a88c  mov     rcx, [rbp+bstrString]; bstrString
0x18002a890  test    rcx, rcx
0x18002a893  jz      short loc_18002A8A2
0x18002a895  call    cs:__imp_SysFreeString
0x18002a89c  nop     dword ptr [rax+rax+00h]
0x18002a8a1  nop
0x18002a8a2  call    cs:__imp_GetProcessHeap
0x18002a8a9  nop     dword ptr [rax+rax+00h]
0x18002a8ae  mov     rcx, rax; hHeap
  ... truncated ...
```
