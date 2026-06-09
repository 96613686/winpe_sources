# DmDiagnosticsCollector::CreateLogFilteredByProviderId(_GUID,ushort const *,ushort const *)

- ea: `0x1800081e4`
- end: `0x180008399`
- name: `?CreateLogFilteredByProviderId@DmDiagnosticsCollector@@SAJU_GUID@@PEBG1@Z`
- size: `437`
- prototype: `static int(struct _GUID *__struct_ptr, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008064`

## callees

- `0x18000183c`
- `0x180005c14`
- `0x180007e18`
- `0x180007e30`
- `0x180007ea4`
- `0x1800081e4`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180008281`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082da`
- `OLEAUT32!__imp_SysFreeString` at `0x180008281`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000822a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000822a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DmDiagnosticsCollector::CreateLogFilteredByProviderId(
        struct _GUID *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, _QWORD, _QWORD, __int64 *); // rbx
  _QWORD *v12; // rax
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, _QWORD); // rbx
  _QWORD *v15; // rax
  OLECHAR *v16; // rax
  __int64 v17; // r8
  int v18; // eax
  int v19; // eax
  int ppv; // [rsp+20h] [rbp-38h]
  __int64 v22; // [rsp+30h] [rbp-28h] BYREF
  __int64 v23; // [rsp+38h] [rbp-20h] BYREF
  BSTR bstrString[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  LPVOID v26; // [rsp+A8h] [rbp+50h] BYREF

  v26 = 0;
  v22 = 0;
  v6 = CoCreateInstance(&CLSID_TraceRelogger, 0, 1u, &GUID_f754ad43_3bcc_4286_8009_9c5da214e84e, &v26);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (unsigned int)v6;
    v9 = 185;
    goto LABEL_6;
  }
  v23 = 0;
  v10 = v26;
  v11 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v26 + 24LL);
  v12 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a2);
  v7 = v11(v10, *v12, 0, &v23);
  SysFreeString(bstrString[0]);
  if ( v7 < 0 )
  {
    v9 = 188;
LABEL_5:
    v8 = (unsigned int)v7;
    goto LABEL_6;
  }
  v13 = v26;
  v14 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v26 + 72LL);
  v15 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a3);
  v7 = v14(v13, *v15);
  SysFreeString(bstrString[0]);
  if ( v7 < 0 )
  {
    v9 = 190;
    goto LABEL_5;
  }
  v16 = (OLECHAR *)operator new(0x38u);
  bstrString[0] = v16;
  *(_QWORD *)v16 = &TraceEventCallbackFilterByProvider::`vftable';
  *((_DWORD *)v16 + 2) = 1;
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(v16 + 8);
  *(struct _GUID *)(v17 + 40) = *a1;
  v22 = v17;
  v18 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v26 + 40LL))(v26, v17);
  v7 = v18;
  if ( v18 >= 0 )
  {
    v19 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 64LL))(v26);
    v7 = v19;
    if ( v19 >= 0 )
    {
      v7 = 0;
      goto LABEL_14;
    }
    v8 = (unsigned int)v19;
    v9 = 198;
  }
  else
  {
    v8 = (unsigned int)v18;
    v9 = 194;
  }
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\lib\\dmdiagnosticscollector.cpp",
    (const char *)v8,
    ppv);
LABEL_14:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800081e4  push    rbp
0x1800081e6  push    rbx
0x1800081e7  push    rsi
0x1800081e8  push    rdi
0x1800081e9  push    r14
0x1800081eb  push    r15
0x1800081ed  mov     rbp, rsp
0x1800081f0  sub     rsp, 58h
0x1800081f4  mov     rsi, r8
0x1800081f7  mov     r14, rdx
0x1800081fa  mov     r15, rcx
0x1800081fd  mov     [rbp+arg_18], 0
0x180008205  mov     [rbp+var_28], 0
0x18000820d  lea     rax, [rbp+arg_18]
0x180008211  mov     qword ptr [rsp+58h+ppv], rax; int
0x180008216  lea     r9, _GUID_f754ad43_3bcc_4286_8009_9c5da214e84e; riid
0x18000821d  xor     edx, edx; pUnkOuter
0x18000821f  lea     r8d, [rdx+1]; dwClsContext
0x180008223  lea     rcx, CLSID_TraceRelogger; rclsid
0x18000822a  call    cs:__imp_CoCreateInstance
0x180008231  nop     dword ptr [rax+rax+00h]
0x180008236  mov     ebx, eax
0x180008238  test    eax, eax
0x18000823a  jns     short loc_180008246
0x18000823c  mov     r9d, eax
0x18000823f  mov     edx, 0B9h
0x180008244  jmp     short loc_180008299
0x180008246  mov     [rbp+var_20], 0
0x18000824e  mov     rdi, [rbp+arg_18]
0x180008252  mov     rax, [rdi]
0x180008255  mov     rbx, [rax+18h]
0x180008259  mov     rdx, r14; unsigned __int16 *
0x18000825c  lea     rcx, [rbp+bstrString]; this
0x180008260  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180008265  nop
0x180008266  lea     r9, [rbp+var_20]
0x18000826a  xor     r8d, r8d
0x18000826d  mov     rdx, [rax]
0x180008270  mov     rcx, rdi
0x180008273  mov     rax, rbx
0x180008276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827b  mov     ebx, eax
0x18000827d  mov     rcx, [rbp+bstrString]; bstrString
0x180008281  call    cs:__imp_SysFreeString
0x180008288  nop     dword ptr [rax+rax+00h]
0x18000828d  test    ebx, ebx
0x18000828f  jns     short loc_1800082AE
0x180008291  mov     edx, 0BCh; void *
0x180008296  mov     r9d, ebx; char *
0x180008299  mov     rcx, [rbp+30h]; this
0x18000829d  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800082a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082a9  jmp     loc_180008376
0x1800082ae  mov     rdi, [rbp+arg_18]
0x1800082b2  mov     rax, [rdi]
0x1800082b5  mov     rbx, [rax+48h]
0x1800082b9  mov     rdx, rsi; unsigned __int16 *
0x1800082bc  lea     rcx, [rbp+bstrString]; this
0x1800082c0  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800082c5  nop
0x1800082c6  mov     rdx, [rax]
0x1800082c9  mov     rcx, rdi
0x1800082cc  mov     rax, rbx
0x1800082cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082d4  mov     ebx, eax
0x1800082d6  mov     rcx, [rbp+bstrString]; bstrString
0x1800082da  call    cs:__imp_SysFreeString
0x1800082e1  nop     dword ptr [rax+rax+00h]
0x1800082e6  test    ebx, ebx
0x1800082e8  jns     short loc_1800082F1
0x1800082ea  mov     edx, 0BEh
0x1800082ef  jmp     short loc_180008296
0x1800082f1  mov     ecx, 38h ; '8'; Size
0x1800082f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800082fb  mov     r8, rax
0x1800082fe  mov     [rbp+bstrString], rax
0x180008302  lea     rax, ??_7TraceEventCallbackFilterByProvider@@6B@; const TraceEventCallbackFilterByProvider::`vftable'
0x180008309  mov     [r8], rax
0x18000830c  mov     dword ptr [r8+8], 1
0x180008314  lea     rcx, [r8+10h]
0x180008318  call    ??0?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(void)
0x18000831d  movaps  xmm0, xmmword ptr [r15]
0x180008321  movdqu  xmmword ptr [r8+28h], xmm0
0x180008327  mov     [rbp+var_28], r8
0x18000832b  mov     rcx, [rbp+arg_18]
0x18000832f  mov     rdx, [rcx]
0x180008332  mov     rax, [rdx+28h]
0x180008336  mov     rdx, r8
0x180008339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000833e  mov     ebx, eax
0x180008340  test    eax, eax
0x180008342  jns     short loc_180008351
0x180008344  mov     r9d, eax
0x180008347  mov     edx, 0C2h
0x18000834c  jmp     loc_180008299
0x180008351  mov     rcx, [rbp+arg_18]
0x180008355  mov     rax, [rcx]
0x180008358  mov     rax, [rax+40h]
0x18000835c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008361  mov     ebx, eax
0x180008363  test    eax, eax
0x180008365  jns     short loc_180008374
0x180008367  mov     r9d, eax
0x18000836a  mov     edx, 0C6h
0x18000836f  jmp     loc_180008299
0x180008374  xor     ebx, ebx
0x180008376  lea     rcx, [rbp+var_28]
0x18000837a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000837f  nop
0x180008380  lea     rcx, [rbp+arg_18]
0x180008384  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008389  mov     eax, ebx
0x18000838b  add     rsp, 58h
0x18000838f  pop     r15
0x180008391  pop     r14
0x180008393  pop     rdi
0x180008394  pop     rsi
0x180008395  pop     rbx
0x180008396  pop     rbp
0x180008397  retn
```
