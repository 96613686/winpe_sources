# EapHost::BaseXmlHelper::Document2String(IXMLDOMDocument2 &)

- ea: `0x1800160ac`
- end: `0x180016176`
- name: `?Document2String@BaseXmlHelper@EapHost@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAUIXMLDOMDocument2@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d200`
- `0x18001eb30`
- `0x18001ede0`

## callees

- `0x180004ec0`
- `0x18000d098`
- `0x18000d0e8`
- `0x1800160ac`
- `0x18001617c`
- `0x180034010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016157`
- `OLEAUT32!__imp_SysFreeString` at `0x180016157`

## pseudocode

```c
__int64 __fastcall EapHost::BaseXmlHelper::Document2String(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // eax
  BSTR bstrString; // [rsp+48h] [rbp+10h] BYREF
  __int64 v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_1dc4107c12973fe87cbae404ee4330ac_Traceguids);
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 360LL))(a2, &v8);
  if ( v4 )
    EapHost::BaseXmlHelper::GetXmlErrorAndThrow(v4);
  bstrString = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 272LL))(v8, &bstrString);
  if ( v5 )
    EapHost::BaseXmlHelper::GetXmlErrorAndThrow(v5);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    a1,
    (__int64)bstrString);
  SysFreeString(bstrString);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v8);
  return a1;
}

```

## disassembly

```asm
0x1800160ac  mov     [rsp+arg_0], rbx
0x1800160b1  push    rdi
0x1800160b2  sub     rsp, 30h
0x1800160b6  mov     rdi, rdx
0x1800160b9  mov     rbx, rcx
0x1800160bc  mov     [rsp+38h+arg_10], 0
0x1800160c5  lea     rax, WPP_GLOBAL_Control
0x1800160cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160d3  cmp     rcx, rax
0x1800160d6  jz      short loc_1800160F3
0x1800160d8  test    byte ptr [rcx+1Ch], 4
0x1800160dc  jz      short loc_1800160F3
0x1800160de  mov     edx, 10h
0x1800160e3  lea     r8, WPP_1dc4107c12973fe87cbae404ee4330ac_Traceguids
0x1800160ea  mov     rcx, [rcx+10h]
0x1800160ee  call    WPP_SF_
0x1800160f3  mov     rax, [rdi]
0x1800160f6  lea     rdx, [rsp+38h+arg_10]
0x1800160fb  mov     rcx, rdi
0x1800160fe  mov     rax, [rax+168h]
0x180016105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001610a  test    eax, eax
0x18001610c  jz      short loc_180016116
0x18001610e  mov     ecx, eax; unsigned int
0x180016110  call    ?GetXmlErrorAndThrow@BaseXmlHelper@EapHost@@SAXJ@Z; EapHost::BaseXmlHelper::GetXmlErrorAndThrow(long)
0x180016116  mov     [rsp+38h+bstrString], 0
0x18001611f  mov     rcx, [rsp+38h+arg_10]
0x180016124  mov     rax, [rcx]
0x180016127  lea     rdx, [rsp+38h+bstrString]
0x18001612c  mov     rax, [rax+110h]
0x180016133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016138  test    eax, eax
0x18001613a  jz      short loc_180016144
0x18001613c  mov     ecx, eax; unsigned int
0x18001613e  call    ?GetXmlErrorAndThrow@BaseXmlHelper@EapHost@@SAXJ@Z; EapHost::BaseXmlHelper::GetXmlErrorAndThrow(long)
0x180016144  mov     rdx, [rsp+38h+bstrString]
0x180016149  mov     rcx, rbx
0x18001614c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180016151  nop
0x180016152  mov     rcx, [rsp+38h+bstrString]; bstrString
0x180016157  call    cs:__imp_SysFreeString
0x18001615d  nop
0x18001615e  lea     rcx, [rsp+38h+arg_10]
0x180016163  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180016168  mov     rax, rbx
0x18001616b  mov     rbx, [rsp+38h+arg_0]
0x180016170  add     rsp, 30h
0x180016174  pop     rdi
0x180016175  retn
```
