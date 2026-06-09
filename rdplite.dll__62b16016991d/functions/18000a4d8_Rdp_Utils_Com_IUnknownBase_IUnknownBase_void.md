# Rdp::Utils::Com::IUnknownBase::IUnknownBase(void)

- ea: `0x18000a4d8`
- end: `0x18000a5cd`
- name: `??0IUnknownBase@Com@Utils@Rdp@@IEAA@XZ`
- size: `245`
- prototype: `__int64 __fastcall(Rdp::Utils::Com::IUnknownBase *__hidden this)`
- caller_count: `11`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a00c`
- `0x18000a3f4`
- `0x18000f39c`
- `0x18000f908`
- `0x18001339c`
- `0x180016a90`
- `0x1800182b4`
- `0x18001c6d4`
- `0x18001c914`
- `0x1800200d8`
- `0x1800231d4`

## callees

- `0x1800036f0`
- `0x180003714`
- `0x18000d118`
- `0x18000d788`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Rdp::Utils::Com::IUnknownBase *__fastcall Rdp::Utils::Com::IUnknownBase::IUnknownBase(
        Rdp::Utils::Com::IUnknownBase *this)
{
  char *v2; // rbx
  _QWORD *v3; // rax
  _QWORD v5[2]; // [rsp+30h] [rbp-38h] BYREF
  GUID v6; // [rsp+40h] [rbp-28h] BYREF
  Rdp::Utils::Com::IUnknownBase *v7; // [rsp+50h] [rbp-18h]
  __int64 v8; // [rsp+58h] [rbp-10h] BYREF

  *(_QWORD *)this = &Rdp::Utils::Com::IUnknownBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  v2 = (char *)this + 16;
  v6 = GUID_00000000_0000_0000_c000_000000000046;
  v7 = this;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  v3 = operator new(0x28u);
  *v3 = v3;
  v3[1] = v3;
  *((_QWORD *)v2 + 1) = v3;
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 4) = 0;
  *((_QWORD *)v2 + 5) = 0;
  *((_QWORD *)v2 + 6) = 7;
  *((_QWORD *)v2 + 7) = 8;
  *(_DWORD *)v2 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(
    v2 + 24,
    16,
    *((_QWORD *)v2 + 1));
  v5[0] = &v6;
  v5[1] = &v8;
  std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::insert(
    v2,
    v5);
  return this;
}

```

## disassembly

```asm
0x18000a4d8  mov     [rsp+arg_8], rbx
0x18000a4dd  push    rdi
0x18000a4de  sub     rsp, 60h
0x18000a4e2  mov     rax, cs:__security_cookie
0x18000a4e9  xor     rax, rsp
0x18000a4ec  mov     [rsp+68h+var_10], rax
0x18000a4f1  mov     rdi, rcx
0x18000a4f4  mov     [rsp+68h+var_48], rcx
0x18000a4f9  lea     rax, ??_7IUnknownBase@Com@Utils@Rdp@@6B@; const Rdp::Utils::Com::IUnknownBase::`vftable'
0x18000a500  mov     [rcx], rax
0x18000a503  mov     dword ptr [rcx+8], 0
0x18000a50a  lea     rbx, [rcx+10h]
0x18000a50e  mov     [rsp+68h+var_48], rbx
0x18000a513  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x18000a51a  movdqu  [rsp+68h+var_28], xmm0
0x18000a520  mov     [rsp+68h+var_18], rcx
0x18000a525  mov     dword ptr [rbx], 0
0x18000a52b  mov     qword ptr [rbx+8], 0
0x18000a533  mov     qword ptr [rbx+10h], 0
0x18000a53b  mov     ecx, 28h ; '('; Size
0x18000a540  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a545  mov     [rax], rax
0x18000a548  mov     [rax+8], rax
0x18000a54c  mov     [rbx+8], rax
0x18000a550  lea     rcx, [rbx+18h]
0x18000a554  mov     qword ptr [rcx], 0
0x18000a55b  mov     qword ptr [rcx+8], 0
0x18000a563  mov     qword ptr [rcx+10h], 0
0x18000a56b  mov     qword ptr [rbx+30h], 7
0x18000a573  mov     qword ptr [rbx+38h], 8
0x18000a57b  mov     dword ptr [rbx], 3F800000h
0x18000a581  mov     r8, [rbx+8]
0x18000a585  mov     edx, 10h
0x18000a58a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>)
0x18000a58f  nop
0x18000a590  lea     rax, [rsp+68h+var_28]
0x18000a595  mov     [rsp+68h+var_38], rax
0x18000a59a  lea     rax, [rsp+68h+var_10]
0x18000a59f  mov     [rsp+68h+var_30], rax
0x18000a5a4  lea     rdx, [rsp+68h+var_38]
0x18000a5a9  mov     rcx, rbx
0x18000a5ac  call    ?insert@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@QEAAXV?$initializer_list@U?$pair@$$CBU_GUID@@PEAX@std@@@2@@Z; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::insert(std::initializer_list<std::pair<_GUID const,void *>>)
0x18000a5b1  nop
0x18000a5b2  mov     rax, rdi
0x18000a5b5  mov     rcx, [rsp+68h+var_10]
0x18000a5ba  xor     rcx, rsp; StackCookie
0x18000a5bd  call    __security_check_cookie
0x18000a5c2  mov     rbx, [rsp+68h+arg_8]
0x18000a5c7  add     rsp, 60h
0x18000a5cb  pop     rdi
0x18000a5cc  retn
```
