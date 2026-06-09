# DiagnosisTextParserImpl::SetXML(ushort const *)

- ea: `0x18002c314`
- end: `0x18002c416`
- name: `?SetXML@DiagnosisTextParserImpl@@QEAAJPEBG@Z`
- size: `258`
- prototype: `int(DiagnosisTextParserImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c2fc`

## callees

- `0x180008c84`
- `0x18002ba6c`
- `0x18002be68`
- `0x18002c314`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002c3e8`
- `KERNEL32!GetLastError` at `0x18002c3e8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c386`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c386`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c3b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c3b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c358`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c358`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagnosisTextParserImpl::SetXML(DiagnosisTextParserImpl *this, const unsigned __int16 *a2)
{
  __int64 result; // rax
  int v5; // ebx
  OLECHAR *v6; // rsi
  signed int LastError; // eax
  __int16 v8; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  result = DiagnosisTextParserImpl::Clear(this);
  if ( (int)result >= 0 )
  {
    ppv = 0;
    v5 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &ppv);
    if ( v5 >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
      v8 = 0;
      v6 = SysAllocString(a2);
      if ( v6 )
      {
        v5 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, v6, &v8);
        SysFreeString(v6);
        if ( v5 >= 0 )
        {
          if ( v8 )
            v5 = RecoverComponents((_DWORD)ppv, (_DWORD)this, (int)this + 8, (int)this + 16, (__int64)this + 32);
        }
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&ppv);
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002c314  mov     [rsp+arg_0], rbx
0x18002c319  push    rbp
0x18002c31a  push    rsi
0x18002c31b  push    rdi
0x18002c31c  sub     rsp, 30h
0x18002c320  mov     rsi, rdx
0x18002c323  mov     rdi, rcx
0x18002c326  call    ?Clear@DiagnosisTextParserImpl@@AEAAJXZ; DiagnosisTextParserImpl::Clear(void)
0x18002c32b  xor     ebp, ebp
0x18002c32d  test    eax, eax
0x18002c32f  js      loc_18002C409
0x18002c335  mov     [rsp+48h+arg_18], rbp
0x18002c33a  lea     rax, [rsp+48h+arg_18]
0x18002c33f  mov     [rsp+48h+ppv], rax; ppv
0x18002c344  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18002c34b  xor     edx, edx; pUnkOuter
0x18002c34d  lea     r8d, [rbp+17h]; dwClsContext
0x18002c351  lea     rcx, CLSID_DOMDocument60; rclsid
0x18002c358  call    cs:__imp_CoCreateInstance
0x18002c35e  mov     ebx, eax
0x18002c360  test    eax, eax
0x18002c362  js      loc_18002C3FD
0x18002c368  mov     rcx, [rsp+48h+arg_18]
0x18002c36d  mov     rax, [rcx]
0x18002c370  xor     edx, edx
0x18002c372  mov     rax, [rax+220h]
0x18002c379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c37e  mov     [rsp+48h+arg_10], bp
0x18002c383  mov     rcx, rsi; psz
0x18002c386  call    cs:__imp_SysAllocString
0x18002c38c  mov     rsi, rax
0x18002c38f  test    rax, rax
0x18002c392  jz      short loc_18002C3E8
0x18002c394  mov     rcx, [rsp+48h+arg_18]
0x18002c399  mov     rdx, [rcx]
0x18002c39c  mov     rax, [rdx+208h]
0x18002c3a3  lea     r8, [rsp+48h+arg_10]
0x18002c3a8  mov     rdx, rsi
0x18002c3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3b0  mov     ebx, eax
0x18002c3b2  mov     rcx, rsi; bstrString
0x18002c3b5  call    cs:__imp_SysFreeString
0x18002c3bb  test    ebx, ebx
0x18002c3bd  js      short loc_18002C3FD
0x18002c3bf  cmp     [rsp+48h+arg_10], bp
0x18002c3c4  jz      short loc_18002C3FD
0x18002c3c6  lea     rax, [rdi+20h]
0x18002c3ca  lea     r9, [rdi+10h]
0x18002c3ce  lea     r8, [rdi+8]
0x18002c3d2  mov     [rsp+48h+ppv], rax
0x18002c3d7  mov     rdx, rdi
0x18002c3da  mov     rcx, [rsp+48h+arg_18]
0x18002c3df  call    ?RecoverComponents@@YAJPEAUIXMLDOMDocument@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@2@Z; RecoverComponents(IXMLDOMDocument *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x18002c3e4  mov     ebx, eax
0x18002c3e6  jmp     short loc_18002C3FD
0x18002c3e8  call    cs:__imp_GetLastError
0x18002c3ee  mov     ebx, eax
0x18002c3f0  test    eax, eax
0x18002c3f2  jle     short loc_18002C3FD
0x18002c3f4  movzx   ebx, ax
0x18002c3f7  or      ebx, 80070000h
0x18002c3fd  lea     rcx, [rsp+48h+arg_18]
0x18002c402  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18002c407  mov     eax, ebx
0x18002c409  mov     rbx, [rsp+48h+arg_0]
0x18002c40e  add     rsp, 30h
0x18002c412  pop     rdi
0x18002c413  pop     rsi
0x18002c414  pop     rbp
0x18002c415  retn
```
