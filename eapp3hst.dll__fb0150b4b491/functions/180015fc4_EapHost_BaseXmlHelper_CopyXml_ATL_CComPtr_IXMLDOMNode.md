# EapHost::BaseXmlHelper::CopyXml(ATL::CComPtr<IXMLDOMNode>)

- ea: `0x180015fc4`
- end: `0x1800160a4`
- name: `?CopyXml@BaseXmlHelper@EapHost@@SA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@V?$CComPtr@UIXMLDOMNode@@@4@@Z`
- size: `224`
- prototype: `struct IUnknown **__fastcall(struct IUnknown **, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015f10`

## callees

- `0x1800017a0`
- `0x18000d098`
- `0x18000d0e8`
- `0x18000d184`
- `0x18000eb94`
- `0x180015fc4`
- `0x18001617c`
- `0x1800162d4`
- `0x180034010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016073`
- `OLEAUT32!__imp_SysFreeString` at `0x180016073`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct IUnknown **__fastcall EapHost::BaseXmlHelper::CopyXml(struct IUnknown **a1, _QWORD *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rax
  struct IUnknown **v6; // rax
  BSTR bstrString; // [rsp+28h] [rbp-48h] BYREF
  LPVOID ppv[3]; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v10[32]; // [rsp+48h] [rbp-28h] BYREF

  ppv[1] = a1;
  ppv[2] = a2;
  *a1 = 0;
  bstrString = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)*a2 + 272LL))(*a2, &bstrString);
  if ( v4 )
    EapHost::BaseXmlHelper::GetXmlErrorAndThrow(v4);
  v5 = std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
         (__int64)v10,
         (__int64)bstrString);
  v6 = (struct IUnknown **)EapHost::BaseXmlHelper::String2Document(ppv, v5);
  if ( *a1 != *v6 )
    ATL::AtlComPtrAssign(a1, *v6);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)ppv);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)v10);
  SysFreeString(bstrString);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(a2);
  return a1;
}

```

## disassembly

```asm
0x180015fc4  mov     [rsp-8+arg_10], rbx
0x180015fc9  mov     [rsp-8+arg_18], rdi
0x180015fce  push    rbp
0x180015fcf  mov     rbp, rsp
0x180015fd2  sub     rsp, 70h
0x180015fd6  mov     rax, cs:__security_cookie
0x180015fdd  xor     rax, rsp
0x180015fe0  mov     [rbp+var_8], rax
0x180015fe4  mov     rdi, rdx
0x180015fe7  mov     rbx, rcx
0x180015fea  mov     [rbp+var_38], rcx
0x180015fee  mov     [rbp+var_30], rdx
0x180015ff2  mov     [rbp+var_50], 0
0x180015ff9  mov     qword ptr [rcx], 0
0x180016000  mov     [rbp+var_50], 1
0x180016007  mov     [rbp+bstrString], 0
0x18001600f  mov     rcx, [rdx]
0x180016012  mov     rax, [rcx]
0x180016015  lea     rdx, [rbp+bstrString]
0x180016019  mov     rax, [rax+110h]
0x180016020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016025  test    eax, eax
0x180016027  jz      short loc_180016031
0x180016029  mov     ecx, eax; unsigned int
0x18001602b  call    ?GetXmlErrorAndThrow@BaseXmlHelper@EapHost@@SAXJ@Z; EapHost::BaseXmlHelper::GetXmlErrorAndThrow(long)
0x180016031  mov     rdx, [rbp+bstrString]
0x180016035  lea     rcx, [rbp+var_28]
0x180016039  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18001603e  nop
0x18001603f  mov     rdx, rax
0x180016042  lea     rcx, [rbp+ppv]; ppv
0x180016046  call    ?String2Document@BaseXmlHelper@EapHost@@SA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapHost::BaseXmlHelper::String2Document(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18001604b  mov     rdx, [rax]; struct IUnknown *
0x18001604e  cmp     [rbx], rdx
0x180016051  jz      short loc_18001605B
0x180016053  mov     rcx, rbx; struct IUnknown **
0x180016056  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001605b  lea     rcx, [rbp+ppv]
0x18001605f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180016064  nop
0x180016065  lea     rcx, [rbp+var_28]
0x180016069  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001606e  nop
0x18001606f  mov     rcx, [rbp+bstrString]; bstrString
0x180016073  call    cs:__imp_SysFreeString
0x180016079  nop
0x18001607a  mov     rcx, rdi
0x18001607d  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180016082  mov     rax, rbx
0x180016085  mov     rcx, [rbp+var_8]
0x180016089  xor     rcx, rsp; StackCookie
0x18001608c  call    __security_check_cookie
0x180016091  lea     r11, [rsp+70h+var_s0]
0x180016096  mov     rbx, [r11+20h]
0x18001609a  mov     rdi, [r11+28h]
0x18001609e  mov     rsp, r11
0x1800160a1  pop     rbp
0x1800160a2  retn
```
