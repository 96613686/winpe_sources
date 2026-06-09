# Rdp::Stack::Shim::CMonitorShim::CMonitorShim(Rdp::Stack::IMonitorConfig *,Rdp::Stack::Shim::CAdapterShim *)

- ea: `0x18001c914`
- end: `0x18001cab2`
- name: `??0CMonitorShim@Shim@Stack@Rdp@@QEAA@PEAUIMonitorConfig@23@PEAVCAdapterShim@123@@Z`
- size: `414`
- prototype: `Rdp::Stack::Shim::CMonitorShim *__fastcall(Rdp::Stack::Shim::CMonitorShim *this, struct Rdp::Stack::IMonitorConfig *, struct Rdp::Stack::Shim::CAdapterShim *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018afc`

## callees

- `0x180003714`
- `0x18000a0e4`
- `0x18000a4d8`
- `0x18000cea4`
- `0x18000d118`
- `0x18000d788`
- `0x18002a010`

## pseudocode

```c
Rdp::Stack::Shim::CMonitorShim *__fastcall Rdp::Stack::Shim::CMonitorShim::CMonitorShim(
        Rdp::Stack::Shim::CMonitorShim *this,
        struct Rdp::Stack::IMonitorConfig *a2,
        struct Rdp::Stack::Shim::CAdapterShim *a3)
{
  _QWORD *v6; // rax
  _BYTE *v7; // rax
  char *v9[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Rdp::Utils::Com::IUnknownBase::IUnknownBase(this);
  *(_QWORD *)this = &Rdp::Utils::Com::ComObject<Rdp::Stack::Shim::CMonitorShim,>::`vftable';
  *(_OWORD *)v9 = 0;
  std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::insert(
    (char *)this + 16,
    v9);
  *(_QWORD *)this = &Rdp::Stack::Shim::CMonitorShim::`vftable';
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  v6 = operator new(0x20u);
  *v6 = v6;
  v6[1] = v6;
  *((_QWORD *)this + 11) = v6;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 7;
  *((_QWORD *)this + 17) = 8;
  *((_DWORD *)this + 20) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(
    (char *)this + 104,
    16,
    *((_QWORD *)this + 11));
  *((_QWORD *)this + 18) = 2;
  *(_OWORD *)((char *)this + 168) = 0;
  *(_OWORD *)((char *)this + 184) = 0;
  *(_OWORD *)((char *)this + 200) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 54) = -1;
  *((_DWORD *)this + 55) = 0;
  *((_QWORD *)this + 28) = 0;
  wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
    (char *)this + 232,
    a3);
  wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
    (char *)this + 240,
    a2);
  *((_BYTE *)this + 248) = 0;
  v7 = (_BYTE *)(*(__int64 (__fastcall **)(struct Rdp::Stack::IMonitorConfig *))(*(_QWORD *)a2 + 32LL))(a2);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x3C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)0x80070057LL,
    (*v7 & 0xE) != 14,
    (bool)"At least valid display mode, scale factor and physical size structures should be present",
    v9[0]);
  return this;
}

```

## disassembly

```asm
0x18001c914  mov     [rsp+arg_8], rbx
0x18001c919  mov     [rsp+arg_0], rcx
0x18001c91e  push    rsi
0x18001c91f  push    rdi
0x18001c920  push    r14
0x18001c922  sub     rsp, 40h
0x18001c926  mov     rdi, r8
0x18001c929  mov     rsi, rdx
0x18001c92c  mov     r14, rcx
0x18001c92f  call    ??0IUnknownBase@Com@Utils@Rdp@@IEAA@XZ; Rdp::Utils::Com::IUnknownBase::IUnknownBase(void)
0x18001c934  nop
0x18001c935  lea     rax, ??_7?$ComObject@VCMonitorShim@Shim@Stack@Rdp@@$$V@Com@Utils@Rdp@@6B@; const Rdp::Utils::Com::ComObject<Rdp::Stack::Shim::CMonitorShim,>::`vftable'
0x18001c93c  mov     [r14], rax
0x18001c93f  xorps   xmm0, xmm0
0x18001c942  movdqa  xmmword ptr [rsp+58h+var_28], xmm0; char *
0x18001c948  lea     rcx, [r14+10h]
0x18001c94c  lea     rdx, [rsp+58h+var_28]
0x18001c951  call    ?insert@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@QEAAXV?$initializer_list@U?$pair@$$CBU_GUID@@PEAX@std@@@2@@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::insert(std::initializer_list<std::pair<_GUID const,void *>>)
0x18001c956  nop
0x18001c957  lea     rax, ??_7CMonitorShim@Shim@Stack@Rdp@@6B@; const Rdp::Stack::Shim::CMonitorShim::`vftable'
0x18001c95e  mov     [r14], rax
0x18001c961  lea     rbx, [r14+50h]
0x18001c965  mov     [rsp+58h+arg_18], rbx
0x18001c96a  mov     dword ptr [rbx], 0
0x18001c970  mov     qword ptr [rbx+8], 0
0x18001c978  mov     qword ptr [rbx+10h], 0
0x18001c980  mov     ecx, 20h ; ' '; Size
0x18001c985  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c98a  mov     [rax], rax
0x18001c98d  mov     [rax+8], rax
0x18001c991  mov     [rbx+8], rax
0x18001c995  lea     rcx, [rbx+18h]
0x18001c999  mov     qword ptr [rcx], 0
0x18001c9a0  mov     qword ptr [rcx+8], 0
0x18001c9a8  mov     qword ptr [rcx+10h], 0
0x18001c9b0  mov     qword ptr [rbx+30h], 7
0x18001c9b8  mov     qword ptr [rbx+38h], 8
0x18001c9c0  mov     dword ptr [rbx], 3F800000h
0x18001c9c6  mov     r8, [rbx+8]
0x18001c9ca  mov     edx, 10h
0x18001c9cf  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>)
0x18001c9d4  nop
0x18001c9d5  mov     qword ptr [r14+90h], 2
0x18001c9e0  xorps   xmm0, xmm0
0x18001c9e3  movups  xmmword ptr [r14+0A8h], xmm0
0x18001c9eb  movups  xmmword ptr [r14+0B8h], xmm0
0x18001c9f3  movups  xmmword ptr [r14+0C8h], xmm0
0x18001c9fb  mov     qword ptr [r14+98h], 0
0x18001ca06  mov     qword ptr [r14+0A0h], 0
0x18001ca11  mov     dword ptr [r14+0D8h], 0FFFFFFFFh
0x18001ca1c  mov     dword ptr [r14+0DCh], 0
0x18001ca27  mov     qword ptr [r14+0E0h], 0
0x18001ca32  lea     rcx, [r14+0E8h]
0x18001ca39  mov     rdx, rdi
0x18001ca3c  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001ca41  nop
0x18001ca42  lea     rcx, [r14+0F0h]
0x18001ca49  mov     rdx, rsi
0x18001ca4c  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001ca51  nop
0x18001ca52  mov     byte ptr [r14+0F8h], 0
0x18001ca5a  mov     rax, [rsi]
0x18001ca5d  mov     rcx, rsi
0x18001ca60  mov     rax, [rax+20h]
0x18001ca64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca69  mov     cl, [rax]
0x18001ca6b  and     cl, 0Eh
0x18001ca6e  cmp     cl, 0Eh
0x18001ca71  setnz   al
0x18001ca74  mov     rcx, [rsp+58h]; this
0x18001ca79  lea     rdx, aAtLeastValidDi; "At least valid display mode, scale fact"...
0x18001ca80  mov     qword ptr [rsp+58h+var_30], rdx; bool
0x18001ca85  mov     [rsp+58h+var_38], al; char
0x18001ca89  mov     r9d, 80070057h; char *
0x18001ca8f  lea     r8, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001ca96  mov     edx, 3Ch ; '<'; void *
0x18001ca9b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001caa0  nop
0x18001caa1  mov     rax, r14
0x18001caa4  mov     rbx, [rsp+58h+arg_8]
0x18001caa9  add     rsp, 40h
0x18001caad  pop     r14
0x18001caaf  pop     rdi
0x18001cab0  pop     rsi
0x18001cab1  retn
```
