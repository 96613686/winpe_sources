# CConfigPolicy::CleanupAndCheckForUniquePolicyAndProfile(tagVARIANT,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,ulong,short &)

- ea: `0x180039a30`
- end: `0x180039e45`
- name: `?CleanupAndCheckForUniquePolicyAndProfile@CConfigPolicy@@AEAAJUtagVARIANT@@V?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@1KAEAF@Z`
- size: `1045`
- prototype: `__int64 __fastcall(__int64, VARIANTARG *, struct IUnknown **, struct IUnknown **, int, _WORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003bfb8`

## callees

- `0x180037d94`
- `0x180037e48`
- `0x180039a30`
- `0x18003cf38`
- `0x180050dbc`
- `0x180050e4c`
- `0x180050e60`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180039a7d`
- `OLEAUT32!__imp_VariantInit` at `0x180039ac4`
- `OLEAUT32!__imp_VariantInit` at `0x180039a7d`
- `OLEAUT32!__imp_VariantInit` at `0x180039ac4`
- `OLEAUT32!__imp_VariantClear` at `0x180039afe`
- `OLEAUT32!__imp_VariantClear` at `0x180039b11`
- `OLEAUT32!__imp_VariantClear` at `0x180039afe`
- `OLEAUT32!__imp_VariantClear` at `0x180039b11`
- `OLEAUT32!__imp_VariantCopy` at `0x180039a8b`
- `OLEAUT32!__imp_VariantCopy` at `0x180039a8b`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039adb`
- `OLEAUT32!__imp_VariantChangeType` at `0x180039adb`

## string_xrefs

- `0x180039c4a`: `CConfigPolicy::CleanupAndCheckForUniquePolicyAndProfile(DELETE_OBJECT): The named Policy & Profile didn't exist!`
- `0x180039ca8`: `CConfigPolicy::CleanupAndCheckForUniquePolicyAndProfile(OPEN_OBJECT): The Policy & Profile Collections are out of sync -- the object exists in one, but not the other. (Policy: %d, Profile: %d)`
- `0x180039d62`: `CConfigPolicy::CleanupAndCheckForUniquePolicyAndProfile(): Error while trying to remove mismatched Policy/Profile object! %lx`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::CleanupAndCheckForUniquePolicyAndProfile(
        __int64 a1,
        VARIANTARG *a2,
        struct IUnknown **a3,
        struct IUnknown **a4,
        int a5,
        _WORD *a6)
{
  HRESULT v9; // eax
  HRESULT v10; // eax
  HRESULT v11; // eax
  HRESULT v12; // eax
  struct IUnknown *v13; // rdi
  struct IUnknown *v14; // rbx
  struct IUnknown *v15; // rax
  struct IUnknownVtbl *lpVtbl; // rdx
  int v17; // eax
  int v18; // edi
  struct IUnknown *v19; // rsi
  struct IUnknownVtbl *v20; // rdx
  int v21; // eax
  int v22; // ebx
  unsigned int v23; // ebx
  __int64 v24; // rdx
  const wchar_t *v25; // r8
  __int64 v26; // r9
  __int64 v27; // r8
  struct IUnknown *v28; // rcx
  struct IUnknown *v29; // rcx
  int v30; // eax
  __int16 v32; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v33; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvargDest; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  struct IUnknown **v38; // [rsp+88h] [rbp-78h]
  struct IUnknown **v39; // [rsp+90h] [rbp-70h]
  int v40; // [rsp+A0h] [rbp-60h] BYREF
  char v41[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v38 = a3;
  v39 = a4;
  VariantInit(&pvarg);
  v9 = VariantCopy(&pvarg, a2);
  if ( v9 < 0 )
    _com_issue_error(v9);
  v35 = 0;
  if ( pvarg.vt == 8 )
  {
    _bstr_t::operator=(&v35, pvarg.llVal);
  }
  else
  {
    VariantInit(&pvargDest);
    v10 = VariantChangeType(&pvargDest, &pvarg, 0, 8u);
    if ( v10 < 0 )
      _com_issue_error(v10);
    _bstr_t::operator=(&v35, pvargDest.llVal);
    v11 = VariantClear(&pvargDest);
    if ( v11 < 0 )
      _com_issue_error(v11);
  }
  v12 = VariantClear(&pvarg);
  if ( v12 < 0 )
    _com_issue_error(v12);
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v13 = *a3;
  if ( !*a3 )
    _com_issue_error(-2147467261);
  v14 = (struct IUnknown *)v35;
  v15 = (struct IUnknown *)v35;
  v33 = (struct IUnknown *)v35;
  if ( v35 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v35 + 16));
    v15 = v33;
  }
  v34 = (struct IUnknown *)&v33;
  v32 = 0;
  if ( v15 )
    lpVtbl = v15->lpVtbl;
  else
    lpVtbl = 0;
  v17 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknownVtbl *, __int16 *))v13->lpVtbl[4].QueryInterface)(
          v13,
          lpVtbl,
          &v32);
  if ( v17 < 0 )
    _com_issue_errorex(v17, v13, &GUID_56bc53e2_96db_11d1_bf3f_000000000000);
  v18 = v32;
  _bstr_t::~_bstr_t((_bstr_t *)&v33);
  v19 = *a4;
  if ( !*a4 )
    _com_issue_error(-2147467261);
  v33 = v14;
  if ( v14 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&v14[2]);
    v14 = v33;
  }
  v34 = (struct IUnknown *)&v33;
  v32 = 0;
  if ( v14 )
    v20 = v14->lpVtbl;
  else
    v20 = 0;
  v21 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknownVtbl *, __int16 *))v19->lpVtbl[4].QueryInterface)(
          v19,
          v20,
          &v32);
  if ( v21 < 0 )
    _com_issue_errorex(v21, v19, &GUID_56bc53e2_96db_11d1_bf3f_000000000000);
  v22 = v32;
  _bstr_t::~_bstr_t((_bstr_t *)&v33);
  if ( a5 == 5 && (_WORD)v18 )
  {
    if ( (_WORD)v22 )
    {
      v23 = -2147352573;
      if ( gIsSdoUtilEtwTracingAvailable )
      {
        v24 = xmmword_180078BA0;
        if ( (_QWORD)xmmword_180078BA0 )
        {
          v25 = L"CConfigPolicy::CleanupAndCheckForUniquePolicyAndProfile(DELETE_OBJECT): The named Policy & Profile didn't exist!";
LABEL_27:
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gSdoUtilTemplateFunc)(
            gSdoUtilEtwContext,
            v24,
            v25);
          goto LABEL_50;
        }
      }
      goto LABEL_50;
    }
  }
  else
  {
    if ( (_WORD)v18 == (_WORD)v22 && a5 != 5 )
    {
      v23 = 0;
LABEL_49:
      *a6 = v18;
      goto LABEL_50;
    }
    if ( a5 == 3 )
    {
      if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
      {
        LOWORD(v40) = 0;
        v26 = (unsigned int)-v22;
        if ( v22 > 0 )
          v26 = (unsigned int)v22;
        v27 = (unsigned int)-v18;
        if ( v18 > 0 )
          v27 = (unsigned int)v18;
        FormatRRASErrorString(
          &v40,
          L"CConfigPolicy::CleanupAndCheckForUniquePolicyAndProfile(OPEN_OBJECT): The Policy & Profile Collections are out"
           " of sync -- the object exists in one, but not the other. (Policy: %d, Profile: %d)",
          v27,
          v26);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
          gSdoUtilEtwContext,
          xmmword_180078BA0,
          &v40);
      }
      v23 = -2147024883;
      goto LABEL_50;
    }
  }
  v28 = *a4;
  v33 = v28;
  if ( v28 )
    ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->AddRef)(v28);
  v29 = *a3;
  v34 = v29;
  if ( v29 )
    ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->AddRef)(v29);
  pvargDest = *a2;
  v30 = CConfigPolicy::RemovePolicyAndProfile(
          (_DWORD)v29,
          (unsigned int)&pvargDest,
          (unsigned int)&v34,
          (unsigned int)&v33,
          v18);
  v23 = v30;
  if ( v30 >= 0 )
  {
    LOWORD(v18) = -1;
    goto LABEL_49;
  }
  if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v40) = 0;
    FormatRRASErrorString(
      &v40,
      L"CConfigPolicy::CleanupAndCheckForUniquePolicyAndProfile(): Error while trying to remove mismatched Policy/Profile object! %lx",
      (unsigned int)v30);
    v25 = (const wchar_t *)&v40;
    v24 = xmmword_180078BA0;
    goto LABEL_27;
  }
LABEL_50:
  _bstr_t::~_bstr_t((_bstr_t *)&v35);
  if ( *a3 )
    ((void (__fastcall *)(struct IUnknown *))(*a3)->lpVtbl->Release)(*a3);
  if ( *a4 )
    ((void (__fastcall *)(struct IUnknown *))(*a4)->lpVtbl->Release)(*a4);
  return v23;
}

```

## disassembly

```asm
0x180039a30  mov     [rsp-8+arg_0], rbx
0x180039a35  push    rbp
0x180039a36  push    rsi
0x180039a37  push    rdi
0x180039a38  push    r12
0x180039a3a  push    r13
0x180039a3c  push    r14
0x180039a3e  push    r15
0x180039a40  lea     rbp, [rsp-7B0h]
0x180039a48  sub     rsp, 8B0h
0x180039a4f  mov     rax, cs:__security_cookie
0x180039a56  xor     rax, rsp
0x180039a59  mov     [rbp+7E0h+var_40], rax
0x180039a60  mov     r14, r9
0x180039a63  mov     r15, r8
0x180039a66  mov     r12, rdx
0x180039a69  mov     [rbp+7E0h+var_858], r8
0x180039a6d  mov     [rbp+7E0h+var_850], r9
0x180039a71  mov     r13, [rbp+7E0h+arg_28]
0x180039a78  lea     rcx, [rsp+8E0h+pvarg]; pvarg
0x180039a7d  call    cs:__imp_VariantInit
0x180039a83  mov     rdx, r12; pvargSrc
0x180039a86  lea     rcx, [rsp+8E0h+pvarg]; pvargDest
0x180039a8b  call    cs:__imp_VariantCopy
0x180039a91  test    eax, eax
0x180039a93  js      loc_180039DFD
0x180039a99  mov     [rsp+8E0h+var_898], 0
0x180039aa2  mov     ebx, 8
0x180039aa7  cmp     word ptr [rsp+8E0h+pvarg], bx
0x180039aac  jnz     short loc_180039ABF
0x180039aae  mov     rdx, qword ptr [rsp+8E0h+pvarg+8]
0x180039ab3  lea     rcx, [rsp+8E0h+var_898]
0x180039ab8  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180039abd  jmp     short loc_180039B0C
0x180039abf  lea     rcx, [rsp+8E0h+pvargDest]; pvarg
0x180039ac4  call    cs:__imp_VariantInit
0x180039aca  nop
0x180039acb  mov     r9d, ebx; vt
0x180039ace  xor     r8d, r8d; wFlags
0x180039ad1  lea     rdx, [rsp+8E0h+pvarg]; pvarSrc
0x180039ad6  lea     rcx, [rsp+8E0h+pvargDest]; pvargDest
0x180039adb  call    cs:__imp_VariantChangeType
0x180039ae1  test    eax, eax
0x180039ae3  js      loc_180039E05
0x180039ae9  mov     rdx, qword ptr [rsp+8E0h+pvargDest+8]
0x180039aee  lea     rcx, [rsp+8E0h+var_898]
0x180039af3  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180039af8  nop
0x180039af9  lea     rcx, [rsp+8E0h+pvargDest]; pvarg
0x180039afe  call    cs:__imp_VariantClear
0x180039b04  test    eax, eax
0x180039b06  js      loc_180039E0D
0x180039b0c  lea     rcx, [rsp+8E0h+pvarg]; pvarg
0x180039b11  call    cs:__imp_VariantClear
0x180039b17  test    eax, eax
0x180039b19  js      loc_180039E15
0x180039b1f  xor     eax, eax
0x180039b21  mov     [rbp+7E0h+var_840], eax
0x180039b24  xor     edx, edx; Val
0x180039b26  mov     r8d, 7FCh; Size
0x180039b2c  lea     rcx, [rbp+7E0h+var_83C]; void *
0x180039b30  call    memset_0
0x180039b35  mov     rdi, [r15]
0x180039b38  test    rdi, rdi
0x180039b3b  jz      loc_180039E1D
0x180039b41  mov     rbx, [rsp+8E0h+var_898]
0x180039b46  mov     rax, rbx
0x180039b49  mov     [rsp+8E0h+var_8A8], rbx
0x180039b4e  test    rbx, rbx
0x180039b51  jz      short loc_180039B5C
0x180039b53  lock inc dword ptr [rbx+10h]
0x180039b57  mov     rax, [rsp+8E0h+var_8A8]
0x180039b5c  lea     rcx, [rsp+8E0h+var_8A8]
0x180039b61  mov     [rsp+8E0h+var_8A0], rcx
0x180039b66  xor     ecx, ecx
0x180039b68  mov     [rsp+8E0h+var_8B0], cx
0x180039b6d  mov     rcx, [rdi]
0x180039b70  mov     r9, [rcx+60h]
0x180039b74  test    rax, rax
0x180039b77  jz      short loc_180039B7E
0x180039b79  mov     rdx, [rax]
0x180039b7c  jmp     short loc_180039B80
0x180039b7e  xor     edx, edx
0x180039b80  lea     r8, [rsp+8E0h+var_8B0]
0x180039b85  mov     rcx, rdi
0x180039b88  mov     rax, r9
0x180039b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b90  test    eax, eax
0x180039b92  js      loc_180039E28
0x180039b98  movsx   edi, [rsp+8E0h+var_8B0]
0x180039b9d  lea     rcx, [rsp+8E0h+var_8A8]; this
0x180039ba2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180039ba7  mov     rsi, [r14]
0x180039baa  test    rsi, rsi
0x180039bad  jz      loc_180039E3A
0x180039bb3  mov     [rsp+8E0h+var_8A8], rbx
0x180039bb8  test    rbx, rbx
0x180039bbb  jz      short loc_180039BC6
0x180039bbd  lock inc dword ptr [rbx+10h]
0x180039bc1  mov     rbx, [rsp+8E0h+var_8A8]
0x180039bc6  lea     rax, [rsp+8E0h+var_8A8]
0x180039bcb  mov     [rsp+8E0h+var_8A0], rax
0x180039bd0  xor     eax, eax
0x180039bd2  mov     [rsp+8E0h+var_8B0], ax
0x180039bd7  mov     rax, [rsi]
0x180039bda  test    rbx, rbx
0x180039bdd  jz      short loc_180039BE4
0x180039bdf  mov     rdx, [rbx]
0x180039be2  jmp     short loc_180039BE6
0x180039be4  xor     edx, edx
0x180039be6  lea     r8, [rsp+8E0h+var_8B0]
0x180039beb  mov     rcx, rsi
0x180039bee  mov     rax, [rax+60h]
0x180039bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bf7  test    eax, eax
0x180039bf9  js      loc_180039DEB
0x180039bff  movsx   ebx, [rsp+8E0h+var_8B0]
0x180039c04  lea     rcx, [rsp+8E0h+var_8A8]; this
0x180039c09  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180039c0e  mov     eax, [rbp+7E0h+arg_20]
0x180039c14  xor     esi, esi
0x180039c16  cmp     eax, 5
0x180039c19  jnz     short loc_180039C69
0x180039c1b  test    di, di
0x180039c1e  jz      short loc_180039C69
0x180039c20  test    bx, bx
0x180039c23  jz      loc_180039CE0
0x180039c29  mov     ebx, 80020003h
0x180039c2e  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, esi; int gIsSdoUtilEtwTracingAvailable
0x180039c34  jz      loc_180039D8A
0x180039c3a  mov     rdx, qword ptr cs:xmmword_180078BA0
0x180039c41  test    rdx, rdx
0x180039c44  jz      loc_180039D8A
0x180039c4a  lea     r8, aCconfigpolicyC_4; "CConfigPolicy::CleanupAndCheckForUnique"...
0x180039c51  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x180039c58  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180039c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c64  jmp     loc_180039D8A
0x180039c69  cmp     di, bx
0x180039c6c  jnz     short loc_180039C7A
0x180039c6e  cmp     eax, 5
0x180039c71  jz      short loc_180039C7A
0x180039c73  mov     ebx, esi
0x180039c75  jmp     loc_180039D85
0x180039c7a  cmp     eax, 3
0x180039c7d  jnz     short loc_180039CE0
0x180039c7f  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, esi; int gIsSdoUtilEtwTracingAvailable
0x180039c85  jz      short loc_180039CD6
0x180039c87  cmp     qword ptr cs:xmmword_180078BA0, rsi
0x180039c8e  jz      short loc_180039CD6
0x180039c90  mov     word ptr [rbp+7E0h+var_840], si
0x180039c94  mov     r9d, ebx
0x180039c97  neg     r9d
0x180039c9a  cmovs   r9d, ebx
0x180039c9e  mov     r8d, edi
0x180039ca1  neg     r8d
0x180039ca4  cmovs   r8d, edi
0x180039ca8  lea     rdx, aCconfigpolicyC_8; "CConfigPolicy::CleanupAndCheckForUnique"...
0x180039caf  lea     rcx, [rbp+7E0h+var_840]
0x180039cb3  call    FormatRRASErrorString
0x180039cb8  lea     r8, [rbp+7E0h+var_840]
0x180039cbc  mov     rdx, qword ptr cs:xmmword_180078BA0
0x180039cc3  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x180039cca  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180039cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cd6  mov     ebx, 8007000Dh
0x180039cdb  jmp     loc_180039D8A
0x180039ce0  mov     rcx, [r14]
0x180039ce3  mov     [rsp+8E0h+var_8A8], rcx
0x180039ce8  test    rcx, rcx
0x180039ceb  jz      short loc_180039CFA
0x180039ced  mov     rax, [rcx]
0x180039cf0  mov     rax, [rax+8]
0x180039cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cf9  nop
0x180039cfa  mov     rcx, [r15]
0x180039cfd  mov     [rsp+8E0h+var_8A0], rcx
0x180039d02  test    rcx, rcx
0x180039d05  jz      short loc_180039D14
0x180039d07  mov     rax, [rcx]
0x180039d0a  mov     rax, [rax+8]
0x180039d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d13  nop
0x180039d14  movaps  xmm0, xmmword ptr [r12]
0x180039d19  movaps  xmmword ptr [rsp+8E0h+pvargDest], xmm0
0x180039d1e  movsd   xmm1, qword ptr [r12+10h]
0x180039d25  movsd   qword ptr [rsp+8E0h+pvargDest+10h], xmm1
0x180039d2b  mov     [rsp+8E0h+var_8C0], di
0x180039d30  lea     r9, [rsp+8E0h+var_8A8]
0x180039d35  lea     r8, [rsp+8E0h+var_8A0]
0x180039d3a  lea     rdx, [rsp+8E0h+pvargDest]
0x180039d3f  call    ?RemovePolicyAndProfile@CConfigPolicy@@AEAAJUtagVARIANT@@V?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@1F@Z; CConfigPolicy::RemovePolicyAndProfile(tagVARIANT,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,short)
0x180039d44  mov     ebx, eax
0x180039d46  test    eax, eax
0x180039d48  jns     short loc_180039D82
0x180039d4a  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, esi; int gIsSdoUtilEtwTracingAvailable
0x180039d50  jz      short loc_180039D8A
0x180039d52  cmp     qword ptr cs:xmmword_180078BA0, rsi
0x180039d59  jz      short loc_180039D8A
0x180039d5b  mov     word ptr [rbp+7E0h+var_840], si
0x180039d5f  mov     r8d, eax
0x180039d62  lea     rdx, aCconfigpolicyC_2; "CConfigPolicy::CleanupAndCheckForUnique"...
0x180039d69  lea     rcx, [rbp+7E0h+var_840]
0x180039d6d  call    FormatRRASErrorString
0x180039d72  lea     r8, [rbp+7E0h+var_840]
0x180039d76  mov     rdx, qword ptr cs:xmmword_180078BA0
0x180039d7d  jmp     loc_180039C51
0x180039d82  or      edi, 0FFFFFFFFh
0x180039d85  mov     [r13+0], di
0x180039d8a  lea     rcx, [rsp+8E0h+var_898]; this
0x180039d8f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180039d94  nop
0x180039d95  mov     rcx, [r15]
0x180039d98  test    rcx, rcx
0x180039d9b  jz      short loc_180039DAA
0x180039d9d  mov     rax, [rcx]
0x180039da0  mov     rax, [rax+10h]
0x180039da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039da9  nop
0x180039daa  mov     rcx, [r14]
0x180039dad  test    rcx, rcx
0x180039db0  jz      short loc_180039DBF
0x180039db2  mov     rax, [rcx]
0x180039db5  mov     rax, [rax+10h]
0x180039db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039dbe  nop
0x180039dbf  mov     eax, ebx
0x180039dc1  mov     rcx, [rbp+7E0h+var_40]
0x180039dc8  xor     rcx, rsp; StackCookie
0x180039dcb  call    __security_check_cookie
0x180039dd0  mov     rbx, [rsp+8E0h+arg_0]
0x180039dd8  add     rsp, 8B0h
0x180039ddf  pop     r15
0x180039de1  pop     r14
0x180039de3  pop     r13
0x180039de5  pop     r12
0x180039de7  pop     rdi
0x180039de8  pop     rsi
0x180039de9  pop     rbp
0x180039dea  retn
0x180039deb  lea     r8, _GUID_56bc53e2_96db_11d1_bf3f_000000000000; struct _GUID *
0x180039df2  mov     rdx, rsi; struct IUnknown *
0x180039df5  mov     ecx, eax; int
0x180039df7  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180039dfd  mov     ecx, eax; int
0x180039dff  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180039e05  mov     ecx, eax; int
0x180039e07  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180039e0d  mov     ecx, eax; int
0x180039e0f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180039e15  mov     ecx, eax; int
0x180039e17  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180039e1d  mov     ecx, 80004003h; int
0x180039e22  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180039e28  lea     r8, _GUID_56bc53e2_96db_11d1_bf3f_000000000000; struct _GUID *
0x180039e2f  mov     rdx, rdi; struct IUnknown *
0x180039e32  mov     ecx, eax; int
0x180039e34  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180039e3a  mov     ecx, 80004003h; int
0x180039e3f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
