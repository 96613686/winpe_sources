# CWapDPU::RemoveNonSupportedNode(ATL::CComPtr<IDomNode>,ATL::CComPtr<IDomNode>)

- ea: `0x18002aadc`
- end: `0x18002abce`
- name: `?RemoveNonSupportedNode@CWapDPU@@CAJV?$CComPtr@UIDomNode@@@ATL@@0@Z`
- size: `242`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029240`

## callees

- `0x180001878`
- `0x1800110bc`
- `0x18001e1a8`
- `0x18002aadc`
- `0x18002b33c`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002aba5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aba5`

## string_xrefs

- `0x18002ab3f`: `Removed non-supported node`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWapDPU::RemoveNonSupportedNode(const char *a1, OLECHAR *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  const char *v11; // [rsp+50h] [rbp+8h] BYREF
  BSTR v12; // [rsp+58h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+18h] BYREF

  v12 = a2;
  v11 = a1;
  bstrString = 0;
  (*(void (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)a2 + 80LL))(*(_QWORD *)a2, &bstrString);
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)a1 + 232LL))(*(_QWORD *)a1, *(_QWORD *)a2);
  v9 = v4;
  if ( v4 < 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      McTemplateU0d_EventWriteTransfer(v6, v5, (unsigned int)v4);
  }
  else
  {
    if ( (unsigned int)dword_18003E080 > 4 )
    {
      v12 = bstrString;
      v11 = "Removed non-supported node";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)bstrString,
        (unsigned int)word_180037A12,
        v7,
        v8,
        (__int64)&v11,
        (__int64)&v12);
    }
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MDM_ENTERPRISE_DIAGNOSTICS_Context,
        EnterpriseDiagnosticsEnrollProvisioningWapNodeFiltering,
        bstrString);
  }
  SysFreeString(bstrString);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a1);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a2);
  return v9;
}

```

## disassembly

```asm
0x18002aadc  mov     r11, rsp
0x18002aadf  mov     [r11+10h], rdx
0x18002aae3  mov     [r11+8], rcx
0x18002aae7  push    rbx
0x18002aae8  push    rsi
0x18002aae9  push    rdi
0x18002aaea  sub     rsp, 30h
0x18002aaee  mov     rdi, rdx
0x18002aaf1  mov     rsi, rcx
0x18002aaf4  mov     qword ptr [r11+18h], 0
0x18002aafc  mov     rcx, [rdx]
0x18002aaff  mov     rax, [rcx]
0x18002ab02  lea     rdx, [r11+18h]
0x18002ab06  mov     rax, [rax+50h]
0x18002ab0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab0f  mov     rcx, [rsi]
0x18002ab12  mov     rax, [rcx]
0x18002ab15  mov     rdx, [rdi]
0x18002ab18  mov     rax, [rax+0E8h]
0x18002ab1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab24  mov     ebx, eax
0x18002ab26  test    eax, eax
0x18002ab28  js      short loc_18002AB8E
0x18002ab2a  mov     ecx, cs:dword_18003E080
0x18002ab30  cmp     ecx, 4
0x18002ab33  jbe     short loc_18002AB6B
0x18002ab35  mov     rcx, [rsp+48h+bstrString]
0x18002ab3a  mov     [rsp+48h+arg_8], rcx
0x18002ab3f  lea     rax, aRemovedNonSupp; "Removed non-supported node"
0x18002ab46  mov     [rsp+48h+arg_0], rax
0x18002ab4b  lea     rax, [rsp+48h+arg_8]
0x18002ab50  mov     [rsp+48h+var_20], rax
0x18002ab55  lea     rax, [rsp+48h+arg_0]
0x18002ab5a  mov     [rsp+48h+var_28], rax
0x18002ab5f  lea     rdx, word_180037A12
0x18002ab66  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002ab6b  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x18002ab72  jz      short loc_18002ABA0
0x18002ab74  mov     r8, [rsp+48h+bstrString]
0x18002ab79  lea     rdx, EnterpriseDiagnosticsEnrollProvisioningWapNodeFiltering
0x18002ab80  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18002ab87  call    McTemplateU0z_EventWriteTransfer
0x18002ab8c  jmp     short loc_18002ABA0
0x18002ab8e  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x18002ab95  jz      short loc_18002ABA0
0x18002ab97  mov     r8d, ebx
0x18002ab9a  call    McTemplateU0d_EventWriteTransfer
0x18002ab9f  nop
0x18002aba0  mov     rcx, [rsp+48h+bstrString]; bstrString
0x18002aba5  call    cs:__imp_SysFreeString
0x18002abac  nop     dword ptr [rax+rax+00h]
0x18002abb1  nop
0x18002abb2  mov     rcx, rsi
0x18002abb5  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002abba  nop
0x18002abbb  mov     rcx, rdi
0x18002abbe  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002abc3  mov     eax, ebx
0x18002abc5  add     rsp, 30h
0x18002abc9  pop     rdi
0x18002abca  pop     rsi
0x18002abcb  pop     rbx
0x18002abcc  retn
```
