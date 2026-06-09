# DmDiagnosticsCollector::CreateLogFilteredByProviderId(_GUID,ushort const *,ushort const *)

- ea: `0x180007e58`
- end: `0x180007ffa`
- name: `?CreateLogFilteredByProviderId@DmDiagnosticsCollector@@SAJU_GUID@@PEBG1@Z`
- size: `418`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007ce4`

## callees

- `0x18000181c`
- `0x180005a14`
- `0x180007ab0`
- `0x180007ac8`
- `0x180007b34`
- `0x180007e58`
- `0x180026010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007eef`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f42`
- `OLEAUT32!__imp_SysFreeString` at `0x180007eef`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f42`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007e9e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007e9e`

## pseudocode

```c
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
0x180007e58  push    rbp
0x180007e5a  push    rbx
0x180007e5b  push    rsi
0x180007e5c  push    rdi
0x180007e5d  push    r14
0x180007e5f  push    r15
0x180007e61  mov     rbp, rsp
0x180007e64  sub     rsp, 58h
0x180007e68  mov     rsi, r8
0x180007e6b  mov     r14, rdx
0x180007e6e  mov     r15, rcx
0x180007e71  mov     [rbp+arg_18], 0
0x180007e79  mov     [rbp+var_28], 0
0x180007e81  lea     rax, [rbp+arg_18]
0x180007e85  mov     qword ptr [rsp+58h+ppv], rax; int
0x180007e8a  lea     r9, _GUID_f754ad43_3bcc_4286_8009_9c5da214e84e; riid
0x180007e91  xor     edx, edx; pUnkOuter
0x180007e93  lea     r8d, [rdx+1]; dwClsContext
0x180007e97  lea     rcx, CLSID_TraceRelogger; rclsid
0x180007e9e  call    cs:__imp_CoCreateInstance
0x180007ea4  mov     ebx, eax
0x180007ea6  test    eax, eax
0x180007ea8  jns     short loc_180007EB4
0x180007eaa  mov     r9d, eax
0x180007ead  mov     edx, 0B9h
0x180007eb2  jmp     short loc_180007F01
0x180007eb4  mov     [rbp+var_20], 0
0x180007ebc  mov     rdi, [rbp+arg_18]
0x180007ec0  mov     rax, [rdi]
0x180007ec3  mov     rbx, [rax+18h]
0x180007ec7  mov     rdx, r14; unsigned __int16 *
0x180007eca  lea     rcx, [rbp+bstrString]; this
0x180007ece  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180007ed3  nop
0x180007ed4  lea     r9, [rbp+var_20]
0x180007ed8  xor     r8d, r8d
0x180007edb  mov     rdx, [rax]
0x180007ede  mov     rcx, rdi
0x180007ee1  mov     rax, rbx
0x180007ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ee9  mov     ebx, eax
0x180007eeb  mov     rcx, [rbp+bstrString]; bstrString
0x180007eef  call    cs:__imp_SysFreeString
0x180007ef5  test    ebx, ebx
0x180007ef7  jns     short loc_180007F16
0x180007ef9  mov     edx, 0BCh; void *
0x180007efe  mov     r9d, ebx; char *
0x180007f01  mov     rcx, [rbp+30h]; this
0x180007f05  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180007f0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f11  jmp     loc_180007FD8
0x180007f16  mov     rdi, [rbp+arg_18]
0x180007f1a  mov     rax, [rdi]
0x180007f1d  mov     rbx, [rax+48h]
0x180007f21  mov     rdx, rsi; unsigned __int16 *
0x180007f24  lea     rcx, [rbp+bstrString]; this
0x180007f28  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180007f2d  nop
0x180007f2e  mov     rdx, [rax]
0x180007f31  mov     rcx, rdi
0x180007f34  mov     rax, rbx
0x180007f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f3c  mov     ebx, eax
0x180007f3e  mov     rcx, [rbp+bstrString]; bstrString
0x180007f42  call    cs:__imp_SysFreeString
0x180007f48  test    ebx, ebx
0x180007f4a  jns     short loc_180007F53
0x180007f4c  mov     edx, 0BEh
0x180007f51  jmp     short loc_180007EFE
0x180007f53  mov     ecx, 38h ; '8'; Size
0x180007f58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007f5d  mov     r8, rax
0x180007f60  mov     [rbp+bstrString], rax
0x180007f64  lea     rax, ??_7TraceEventCallbackFilterByProvider@@6B@; const TraceEventCallbackFilterByProvider::`vftable'
0x180007f6b  mov     [r8], rax
0x180007f6e  mov     dword ptr [r8+8], 1
0x180007f76  lea     rcx, [r8+10h]
0x180007f7a  call    ??0?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(void)
0x180007f7f  movaps  xmm0, xmmword ptr [r15]
0x180007f83  movdqu  xmmword ptr [r8+28h], xmm0
0x180007f89  mov     [rbp+var_28], r8
0x180007f8d  mov     rcx, [rbp+arg_18]
0x180007f91  mov     rdx, [rcx]
0x180007f94  mov     rax, [rdx+28h]
0x180007f98  mov     rdx, r8
0x180007f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fa0  mov     ebx, eax
0x180007fa2  test    eax, eax
0x180007fa4  jns     short loc_180007FB3
0x180007fa6  mov     r9d, eax
0x180007fa9  mov     edx, 0C2h
0x180007fae  jmp     loc_180007F01
0x180007fb3  mov     rcx, [rbp+arg_18]
0x180007fb7  mov     rax, [rcx]
0x180007fba  mov     rax, [rax+40h]
0x180007fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc3  mov     ebx, eax
0x180007fc5  test    eax, eax
0x180007fc7  jns     short loc_180007FD6
0x180007fc9  mov     r9d, eax
0x180007fcc  mov     edx, 0C6h
0x180007fd1  jmp     loc_180007F01
0x180007fd6  xor     ebx, ebx
0x180007fd8  lea     rcx, [rbp+var_28]
0x180007fdc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007fe1  nop
0x180007fe2  lea     rcx, [rbp+arg_18]
0x180007fe6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007feb  mov     eax, ebx
0x180007fed  add     rsp, 58h
0x180007ff1  pop     r15
0x180007ff3  pop     r14
0x180007ff5  pop     rdi
0x180007ff6  pop     rsi
0x180007ff7  pop     rbx
0x180007ff8  pop     rbp
0x180007ff9  retn
```
