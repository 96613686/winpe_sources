# DiagnosisTextParserImpl::SetXML(ushort const *)

- ea: `0x18001e244`
- end: `0x18001e353`
- name: `?SetXML@DiagnosisTextParserImpl@@QEAAJPEBG@Z`
- size: `271`
- prototype: `int(DiagnosisTextParserImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f1d0`
- `0x18001512c`
- `0x180016810`
- `0x18001a884`

## callees

- `0x18001d790`
- `0x18001df88`
- `0x18001e244`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e318`
- `KERNEL32!GetLastError` at `0x18001e318`
- `ole32!CoCreateInstance` at `0x18001e288`
- `ole32!CoCreateInstance` at `0x18001e288`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e2b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e2b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e2e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e2e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DiagnosisTextParserImpl::SetXML(void **this, const unsigned __int16 *a2)
{
  __int64 result; // rax
  int v5; // ebx
  OLECHAR *v6; // rsi
  signed int LastError; // eax
  __int16 v8; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  result = DiagnosisTextParserImpl::Clear((DiagnosisTextParserImpl *)this);
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
        if ( v5 >= 0 && v8 )
          v5 = RecoverComponents((__int64)ppv, (__int64)this, (__int64)(this + 1), (__int64)(this + 2), this + 4);
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18001e244  mov     [rsp+arg_0], rbx
0x18001e249  push    rbp
0x18001e24a  push    rsi
0x18001e24b  push    rdi
0x18001e24c  sub     rsp, 30h
0x18001e250  mov     rsi, rdx
0x18001e253  mov     rdi, rcx
0x18001e256  call    ?Clear@DiagnosisTextParserImpl@@AEAAJXZ; DiagnosisTextParserImpl::Clear(void)
0x18001e25b  xor     ebp, ebp
0x18001e25d  test    eax, eax
0x18001e25f  js      loc_18001E346
0x18001e265  mov     [rsp+48h+arg_18], rbp
0x18001e26a  lea     rax, [rsp+48h+arg_18]
0x18001e26f  mov     [rsp+48h+ppv], rax; ppv
0x18001e274  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18001e27b  xor     edx, edx; pUnkOuter
0x18001e27d  lea     r8d, [rbp+17h]; dwClsContext
0x18001e281  lea     rcx, CLSID_DOMDocument60; rclsid
0x18001e288  call    cs:__imp_CoCreateInstance
0x18001e28e  mov     ebx, eax
0x18001e290  test    eax, eax
0x18001e292  js      loc_18001E32D
0x18001e298  mov     rcx, [rsp+48h+arg_18]
0x18001e29d  mov     rax, [rcx]
0x18001e2a0  xor     edx, edx
0x18001e2a2  mov     rax, [rax+220h]
0x18001e2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2ae  mov     [rsp+48h+arg_10], bp
0x18001e2b3  mov     rcx, rsi; psz
0x18001e2b6  call    cs:__imp_SysAllocString
0x18001e2bc  mov     rsi, rax
0x18001e2bf  test    rax, rax
0x18001e2c2  jz      short loc_18001E318
0x18001e2c4  mov     rcx, [rsp+48h+arg_18]
0x18001e2c9  mov     rdx, [rcx]
0x18001e2cc  mov     rax, [rdx+208h]
0x18001e2d3  lea     r8, [rsp+48h+arg_10]
0x18001e2d8  mov     rdx, rsi
0x18001e2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2e0  mov     ebx, eax
0x18001e2e2  mov     rcx, rsi; bstrString
0x18001e2e5  call    cs:__imp_SysFreeString
0x18001e2eb  test    ebx, ebx
0x18001e2ed  js      short loc_18001E32D
0x18001e2ef  cmp     [rsp+48h+arg_10], bp
0x18001e2f4  jz      short loc_18001E32D
0x18001e2f6  lea     rax, [rdi+20h]
0x18001e2fa  lea     r9, [rdi+10h]
0x18001e2fe  lea     r8, [rdi+8]
0x18001e302  mov     [rsp+48h+ppv], rax
0x18001e307  mov     rdx, rdi
0x18001e30a  mov     rcx, [rsp+48h+arg_18]
0x18001e30f  call    ?RecoverComponents@@YAJPEAUIXMLDOMDocument@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAV?$multimap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@2@Z; RecoverComponents(IXMLDOMDocument *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &,std::multimap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> &)
0x18001e314  mov     ebx, eax
0x18001e316  jmp     short loc_18001E32D
0x18001e318  call    cs:__imp_GetLastError
0x18001e31e  mov     ebx, eax
0x18001e320  test    eax, eax
0x18001e322  jle     short loc_18001E32D
0x18001e324  movzx   ebx, ax
0x18001e327  or      ebx, 80070000h
0x18001e32d  mov     rcx, [rsp+48h+arg_18]
0x18001e332  test    rcx, rcx
0x18001e335  jz      short loc_18001E344
0x18001e337  mov     rax, [rcx]
0x18001e33a  mov     rax, [rax+10h]
0x18001e33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e343  nop
0x18001e344  mov     eax, ebx
0x18001e346  mov     rbx, [rsp+48h+arg_0]
0x18001e34b  add     rsp, 30h
0x18001e34f  pop     rdi
0x18001e350  pop     rsi
0x18001e351  pop     rbp
0x18001e352  retn
```
