# PublicNetworkListManager::RetrieveGITEntry(std::map<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>> const *,_RTL_CRITICAL_SECTION *,ulong,ATL::CComPtr<IGlobalInterfaceTable> const &,_GUID const &,void * *)

- ea: `0x1800295c8`
- end: `0x18002966f`
- name: `?RetrieveGITEntry@PublicNetworkListManager@@CAJPEBV?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@PEAU_RTL_CRITICAL_SECTION@@KAEBV?$CComPtr@UIGlobalInterfaceTable@@@ATL@@AEBU_GUID@@PEAPEAX@Z`
- size: `167`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023228`
- `0x180023388`
- `0x1800234e4`
- `0x1800236a0`
- `0x18002382c`

## callees

- `0x180009184`
- `0x180009d08`
- `0x18000a45c`
- `0x18000c5d4`
- `0x1800295c8`
- `0x180043010`

## string_xrefs

- `0x18002964c`: `onecore\net\netprofiles\service\src\public\lib\networklistmanagerimpl.cpp`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::RetrieveGITEntry(
        _QWORD *a1,
        struct _RTL_CRITICAL_SECTION *a2,
        int a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v8; // rax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-48h]
  int v14; // [rsp+30h] [rbp-38h] BYREF
  struct _RTL_CRITICAL_SECTION *v15[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v14 = a3;
  v15[0] = 0;
  wil::EnterCriticalSection(v15, a2);
  v8 = std::_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>::_Find<unsigned long>(
         a1,
         &v14);
  if ( v8 == *a1 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v15);
    return 2147745796LL;
  }
  else
  {
    v10 = *(_DWORD *)(v8 + 48);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v15);
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(*(_QWORD *)*a4 + 40LL))(*a4, v10, a5, a6);
    v12 = v11;
    if ( v11 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x871,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\public\\lib\\networklistmanagerimpl.cpp",
        (const char *)(unsigned int)v11,
        v13);
      return v12;
    }
  }
}

```

## disassembly

```asm
0x1800295c8  push    rbx
0x1800295ca  push    rbp
0x1800295cb  push    rsi
0x1800295cc  push    rdi
0x1800295cd  sub     rsp, 48h
0x1800295d1  mov     rsi, [rsp+68h+arg_20]
0x1800295d9  mov     rbx, rcx
0x1800295dc  mov     rbp, [rsp+68h+arg_28]
0x1800295e4  lea     rcx, [rsp+68h+var_30]
0x1800295e9  mov     rdi, r9
0x1800295ec  mov     [rsp+68h+var_38], r8d
0x1800295f1  mov     [rsp+68h+var_30], 0
0x1800295fa  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800295ff  lea     rdx, [rsp+68h+var_38]
0x180029604  mov     rcx, rbx
0x180029607  call    ??$_Find@K@?$_Tree@V?$_Tmap_traits@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@PEAX@1@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>::_Find<ulong>(ulong const &)
0x18002960c  lea     rcx, [rsp+68h+var_30]
0x180029611  cmp     rax, [rbx]
0x180029614  jnz     short loc_180029622
0x180029616  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18002961b  mov     eax, 80040004h
0x180029620  jmp     short loc_180029666
0x180029622  mov     ebx, [rax+30h]
0x180029625  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18002962a  mov     rcx, [rdi]
0x18002962d  mov     r9, rbp
0x180029630  mov     r8, rsi
0x180029633  mov     edx, ebx
0x180029635  mov     rax, [rcx]
0x180029638  mov     rax, [rax+28h]
0x18002963c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029641  mov     ebx, eax
0x180029643  test    eax, eax
0x180029645  jns     short loc_180029664
0x180029647  mov     rcx, [rsp+68h]; this
0x18002964c  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x180029653  mov     r9d, eax; char *
0x180029656  mov     edx, 871h; void *
0x18002965b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029660  mov     eax, ebx
0x180029662  jmp     short loc_180029666
0x180029664  xor     eax, eax
0x180029666  add     rsp, 48h
0x18002966a  pop     rdi
0x18002966b  pop     rsi
0x18002966c  pop     rbp
0x18002966d  pop     rbx
0x18002966e  retn
```
