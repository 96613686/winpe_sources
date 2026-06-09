# CWapNodeValidator::ReadCspNameFromFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002d6bc`
- end: `0x18002d7ab`
- name: `?ReadCspNameFromFile@CWapNodeValidator@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ce00`

## callees

- `0x1800110bc`
- `0x180011d9c`
- `0x18001d87c`
- `0x18002c344`
- `0x18002d6bc`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002d780`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d780`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWapNodeValidator::ReadCspNameFromFile(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int16 *v4; // rax
  int XmlDocumentFromDdf; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  BSTR bstrString; // [rsp+40h] [rbp+20h] BYREF
  __int64 v12; // [rsp+48h] [rbp+28h] BYREF
  LPVOID v13; // [rsp+58h] [rbp+38h] BYREF

  v4 = (unsigned __int16 *)a2;
  v13 = 0;
  v12 = 0;
  bstrString = 0;
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v4 = *(unsigned __int16 **)a2;
  XmlDocumentFromDdf = GetXmlDocumentFromDdf(v4, &v13);
  v6 = XmlDocumentFromDdf;
  if ( XmlDocumentFromDdf >= 0 )
  {
    XmlDocumentFromDdf = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v13 + 296LL))(
                           v13,
                           L"MgmtTree/Node/NodeName",
                           &v12);
    v6 = XmlDocumentFromDdf;
    if ( XmlDocumentFromDdf >= 0 )
    {
      XmlDocumentFromDdf = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 208LL))(v12, &bstrString);
      v6 = XmlDocumentFromDdf;
      if ( XmlDocumentFromDdf >= 0 )
      {
        std::wstring::assign(a3);
        v6 = 0;
        goto LABEL_11;
      }
      v7 = 479;
    }
    else
    {
      v7 = 478;
    }
  }
  else
  {
    v7 = 477;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
    (const char *)(unsigned int)XmlDocumentFromDdf,
    savedregs);
LABEL_11:
  SysFreeString(bstrString);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v12);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v13);
  return v6;
}

```

## disassembly

```asm
0x18002d6bc  mov     [rsp-18h+bstrString], rcx
0x18002d6c1  push    rbp
0x18002d6c2  push    rbx
0x18002d6c3  push    rdi; int
0x18002d6c4  mov     rbp, rsp
0x18002d6c7  sub     rsp, 20h
0x18002d6cb  mov     rdi, r8
0x18002d6ce  mov     rax, rdx
0x18002d6d1  mov     [rbp+arg_18], 0
0x18002d6d9  mov     [rbp+arg_8], 0
0x18002d6e1  mov     [rbp+bstrString], 0
0x18002d6e9  cmp     qword ptr [rdx+18h], 7
0x18002d6ee  jbe     short loc_18002D6F3
0x18002d6f0  mov     rax, [rdx]
0x18002d6f3  lea     rdx, [rbp+arg_18]; int
0x18002d6f7  mov     rcx, rax; unsigned __int16 *
0x18002d6fa  call    ?GetXmlDocumentFromDdf@@YAJPEBGAEAV?$CComPtr@UIXMLDOMDocument3@@@ATL@@@Z; GetXmlDocumentFromDdf(ushort const *,ATL::CComPtr<IXMLDOMDocument3> &)
0x18002d6ff  mov     ebx, eax
0x18002d701  test    eax, eax
0x18002d703  jns     short loc_18002D70C
0x18002d705  mov     edx, 1DDh
0x18002d70a  jmp     short loc_18002D735
0x18002d70c  mov     rcx, [rbp+arg_18]
0x18002d710  mov     rax, [rcx]
0x18002d713  lea     r8, [rbp+arg_8]
0x18002d717  lea     rdx, aMgmttreeNodeNo; "MgmtTree/Node/NodeName"
0x18002d71e  mov     rax, [rax+128h]
0x18002d725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d72a  mov     ebx, eax
0x18002d72c  test    eax, eax
0x18002d72e  jns     short loc_18002D74A
0x18002d730  mov     edx, 1DEh; void *
0x18002d735  mov     rcx, [rbp+18h]; this
0x18002d739  mov     r9d, eax; char *
0x18002d73c  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002d743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d748  jmp     short loc_18002D77C
0x18002d74a  mov     rcx, [rbp+arg_8]
0x18002d74e  mov     rax, [rcx]
0x18002d751  lea     rdx, [rbp+bstrString]
0x18002d755  mov     rax, [rax+0D0h]
0x18002d75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d761  mov     ebx, eax
0x18002d763  test    eax, eax
0x18002d765  jns     short loc_18002D76E
0x18002d767  mov     edx, 1DFh
0x18002d76c  jmp     short loc_18002D735
0x18002d76e  mov     rdx, [rbp+bstrString]
0x18002d772  mov     rcx, rdi
0x18002d775  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18002d77a  xor     ebx, ebx
0x18002d77c  mov     rcx, [rbp+bstrString]; bstrString
0x18002d780  call    cs:__imp_SysFreeString
0x18002d787  nop     dword ptr [rax+rax+00h]
0x18002d78c  nop
0x18002d78d  lea     rcx, [rbp+arg_8]
0x18002d791  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d796  nop
0x18002d797  lea     rcx, [rbp+arg_18]
0x18002d79b  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d7a0  mov     eax, ebx
0x18002d7a2  add     rsp, 20h
0x18002d7a6  pop     rdi
0x18002d7a7  pop     rbx
0x18002d7a8  pop     rbp
0x18002d7a9  retn
```
