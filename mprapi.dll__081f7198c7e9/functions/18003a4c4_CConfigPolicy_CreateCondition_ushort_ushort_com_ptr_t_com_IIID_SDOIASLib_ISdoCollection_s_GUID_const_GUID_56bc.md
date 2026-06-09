# CConfigPolicy::CreateCondition(ushort *,ushort *,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>)

- ea: `0x18003a4c4`
- end: `0x18003a6c0`
- name: `?CreateCondition@CConfigPolicy@@AEAAJPEAG0V?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, const OLECHAR *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003835c`

## callees

- `0x18003a4c4`
- `0x18003dfc4`
- `0x18003edbc`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003a50f`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a50f`
- `OLEAUT32!__imp_VariantClear` at `0x18003a649`
- `OLEAUT32!__imp_VariantClear` at `0x18003a649`

## string_xrefs

- `0x18003a5a1`: `CConfigPolicy::CreateCondition(): Error %lx Couldn't create a new SDO object for the Condition!`
- `0x18003a613`: `CConfigPolicy::CreateCondition(): Error %lx Couldn't set the Condition's value!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::CreateCondition(
        __int64 a1,
        unsigned __int16 *a2,
        const OLECHAR *a3,
        struct IUnknown **a4)
{
  IRecordInfo *v7; // rax
  struct IUnknown *v8; // rcx
  int v9; // eax
  int v10; // ebx
  __int128 v11; // xmm6
  __int64 v12; // xmm7_8
  HRESULT v13; // eax
  struct IUnknown *v15; // [rsp+28h] [rbp-E0h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-C0h]
  _QWORD v18[5]; // [rsp+50h] [rbp-B8h] BYREF
  int v19; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v20[2044]; // [rsp+7Ch] [rbp-8Ch] BYREF

  v18[0] = a4;
  *(_QWORD *)&pvarg.vt = 0;
  v7 = (IRecordInfo *)SysAllocString(a3);
  if ( !v7 && a3 )
    _com_issue_error(-2147024882);
  pvarg.iVal = 8;
  pvarg.pRecInfo = v7;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v8 = *a4;
  v15 = v8;
  if ( v8 )
    ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->AddRef)(v8);
  v9 = AddObjectToCollection(a2, &v15, &pvarg);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = *(_OWORD *)&pvarg.decVal.Lo32;
    v12 = v17;
    v15 = *(struct IUnknown **)&pvarg.vt;
    if ( *(_QWORD *)&pvarg.vt )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pvarg.vt + 8LL))(*(_QWORD *)&pvarg.vt);
    *(_OWORD *)&v18[1] = v11;
    v18[3] = v12;
    v10 = PutSdoProperty(&v15, 1024, &v18[1]);
    if ( v10 < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"CConfigPolicy::CreateCondition(): Error %lx Couldn't set the Condition's value!",
        (unsigned int)v10);
      goto LABEL_15;
    }
  }
  else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v19) = 0;
    FormatRRASErrorString(
      &v19,
      L"CConfigPolicy::CreateCondition(): Error %lx Couldn't create a new SDO object for the Condition!",
      (unsigned int)v9);
LABEL_15:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
      gSdoUtilEtwContext,
      xmmword_180078BA0,
      &v19);
  }
  v13 = VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v13 < 0 )
    _com_issue_error(v13);
  if ( *(_QWORD *)&pvarg.vt )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pvarg.vt + 16LL))(*(_QWORD *)&pvarg.vt);
  if ( *a4 )
    ((void (__fastcall *)(struct IUnknown *))(*a4)->lpVtbl->Release)(*a4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003a4c4  mov     rax, rsp
0x18003a4c7  mov     [rax+8], rbx
0x18003a4cb  push    rbp
0x18003a4cc  push    rsi
0x18003a4cd  push    rdi
0x18003a4ce  lea     rbp, [rax-7B8h]
0x18003a4d5  sub     rsp, 8A0h
0x18003a4dc  movaps  xmmword ptr [rax-28h], xmm6
0x18003a4e0  movaps  xmmword ptr [rax-38h], xmm7
0x18003a4e4  mov     rax, cs:__security_cookie
0x18003a4eb  xor     rax, rsp
0x18003a4ee  mov     [rbp+7B0h+var_40], rax
0x18003a4f5  mov     rdi, r9
0x18003a4f8  mov     rbx, r8
0x18003a4fb  mov     rsi, rdx
0x18003a4fe  mov     qword ptr [rsp+8B0h+var_868], r9
0x18003a503  mov     qword ptr [rsp+8B0h+pvarg], 0
0x18003a50c  mov     rcx, r8; psz
0x18003a50f  call    cs:__imp_SysAllocString
0x18003a515  test    rax, rax
0x18003a518  jnz     short loc_18003A523
0x18003a51a  test    rbx, rbx
0x18003a51d  jnz     loc_18003A6B5
0x18003a523  mov     ecx, 8
0x18003a528  mov     word ptr [rsp+8B0h+pvarg+8], cx
0x18003a52d  mov     qword ptr [rsp+8B0h+pvarg+10h], rax
0x18003a532  xor     eax, eax
0x18003a534  mov     [rsp+8B0h+var_840], eax
0x18003a538  xor     edx, edx; Val
0x18003a53a  mov     r8d, 7FCh; Size
0x18003a540  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18003a545  call    memset_0
0x18003a54a  mov     rcx, [rdi]
0x18003a54d  mov     [rsp+8B0h+var_890], rcx
0x18003a552  test    rcx, rcx
0x18003a555  jz      short loc_18003A564
0x18003a557  mov     rax, [rcx]
0x18003a55a  mov     rax, [rax+8]
0x18003a55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a563  nop
0x18003a564  lea     r8, [rsp+8B0h+pvarg]
0x18003a569  lea     rdx, [rsp+8B0h+var_890]
0x18003a56e  mov     rcx, rsi; unsigned __int16 *
0x18003a571  call    ?AddObjectToCollection@@YAJPEAGV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; AddObjectToCollection(ushort *,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &)
0x18003a576  mov     ebx, eax
0x18003a578  test    eax, eax
0x18003a57a  jns     short loc_18003A5AA
0x18003a57c  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003a583  jz      loc_18003A644
0x18003a589  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003a591  jz      loc_18003A644
0x18003a597  xor     ecx, ecx
0x18003a599  mov     word ptr [rsp+8B0h+var_840], cx
0x18003a59e  mov     r8d, eax
0x18003a5a1  lea     rdx, aCconfigpolicyC_5; "CConfigPolicy::CreateCondition(): Error"...
0x18003a5a8  jmp     short loc_18003A61A
0x18003a5aa  movups  xmm6, xmmword ptr [rsp+8B0h+pvarg+8]
0x18003a5af  movsd   xmm7, [rsp+8B0h+var_870]
0x18003a5b5  mov     rcx, qword ptr [rsp+8B0h+pvarg]
0x18003a5ba  mov     [rsp+8B0h+var_890], rcx
0x18003a5bf  test    rcx, rcx
0x18003a5c2  jz      short loc_18003A5D1
0x18003a5c4  mov     rax, [rcx]
0x18003a5c7  mov     rax, [rax+8]
0x18003a5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5d0  nop
0x18003a5d1  movaps  xmmword ptr [rsp+8B0h+var_868+8], xmm6
0x18003a5d6  movsd   [rsp+8B0h+var_850], xmm7
0x18003a5dc  lea     r8, [rsp+8B0h+var_868+8]
0x18003a5e1  mov     edx, 400h
0x18003a5e6  lea     rcx, [rsp+8B0h+var_890]
0x18003a5eb  call    ?PutSdoProperty@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JUtagVARIANT@@@Z; PutSdoProperty(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,tagVARIANT)
0x18003a5f0  mov     ebx, eax
0x18003a5f2  test    eax, eax
0x18003a5f4  jns     short loc_18003A644
0x18003a5f6  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003a5fd  jz      short loc_18003A644
0x18003a5ff  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003a607  jz      short loc_18003A644
0x18003a609  xor     eax, eax
0x18003a60b  mov     word ptr [rsp+8B0h+var_840], ax
0x18003a610  mov     r8d, ebx
0x18003a613  lea     rdx, aCconfigpolicyC_3; "CConfigPolicy::CreateCondition(): Error"...
0x18003a61a  lea     rcx, [rsp+8B0h+var_840]
0x18003a61f  call    FormatRRASErrorString
0x18003a624  lea     r8, [rsp+8B0h+var_840]
0x18003a629  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003a630  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003a637  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003a63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a643  nop
0x18003a644  lea     rcx, [rsp+8B0h+pvarg+8]; pvarg
0x18003a649  call    cs:__imp_VariantClear
0x18003a64f  test    eax, eax
0x18003a651  js      short loc_18003A6AD
0x18003a653  mov     rcx, qword ptr [rsp+8B0h+pvarg]
0x18003a658  test    rcx, rcx
0x18003a65b  jz      short loc_18003A66A
0x18003a65d  mov     rax, [rcx]
0x18003a660  mov     rax, [rax+10h]
0x18003a664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a669  nop
0x18003a66a  mov     rcx, [rdi]
0x18003a66d  test    rcx, rcx
0x18003a670  jz      short loc_18003A67F
0x18003a672  mov     rax, [rcx]
0x18003a675  mov     rax, [rax+10h]
0x18003a679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a67e  nop
0x18003a67f  mov     eax, ebx
0x18003a681  mov     rcx, [rbp+7B0h+var_40]
0x18003a688  xor     rcx, rsp; StackCookie
0x18003a68b  call    __security_check_cookie
0x18003a690  lea     r11, [rsp+8B0h+var_10]
0x18003a698  mov     rbx, [r11+20h]
0x18003a69c  movaps  xmm6, xmmword ptr [r11-10h]
0x18003a6a1  movaps  xmm7, xmmword ptr [r11-20h]
0x18003a6a6  mov     rsp, r11
0x18003a6a9  pop     rdi
0x18003a6aa  pop     rsi
0x18003a6ab  pop     rbp
0x18003a6ac  retn
0x18003a6ad  mov     ecx, eax; int
0x18003a6af  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003a6b5  mov     ecx, 8007000Eh; int
0x18003a6ba  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
