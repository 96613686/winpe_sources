# CDimInterfaceTable::InsertInterface(std::tr1::shared_ptr<CDimInterface> const &)

- ea: `0x1800076ac`
- end: `0x180007869`
- name: `?InsertInterface@CDimInterfaceTable@@QEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003f80`
- `0x1800057f0`
- `0x180006fac`
- `0x1800091dc`

## callees

- `0x180005670`
- `0x180006918`
- `0x1800076ac`
- `0x180007f70`
- `0x180008e70`
- `0x180009f64`
- `0x18000b534`
- `0x18001e508`
- `0x18001e53c`
- `0x180023318`
- `0x1800235cc`
- `0x180025c24`
- `0x18002d638`
- `0x180048010`

## import_xrefs

- `MPRDDM!TimerQInsert` at `0x180007849`
- `MPRDDM!TimerQInsert` at `0x180007849`
- `MPRDDM!ReConnectPersistentInterface` at `0x18000781b`
- `MPRDDM!ReConnectPersistentInterface` at `0x18000783a`
- `MPRDDM!TimerQRemove` at `0x180007825`
- `MPRDDM!TimerQRemove` at `0x180007825`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CDimInterfaceTable::InsertInterface(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  char result; // al
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // [rsp+20h] [rbp-38h] BYREF
  std::tr1::_Ref_count_base *v11; // [rsp+28h] [rbp-30h]
  __int128 v12; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-18h]

  v4 = std::map<std::wstring,std::set<std::tr1::shared_ptr<CDimInterface>,CDimInterfaceTable::_SHARED_PTR_COMP,std::allocator<std::tr1::shared_ptr<CDimInterface>>>,CDimInterfaceTable::_WSTRING_COMP,std::allocator<std::pair<std::wstring const,std::set<std::tr1::shared_ptr<CDimInterface>,CDimInterfaceTable::_SHARED_PTR_COMP,std::allocator<std::tr1::shared_ptr<CDimInterface>>>>>>::operator[](
         a1 + 120,
         *a2 + 8);
  std::_Tree<std::_Tset_traits<std::tr1::shared_ptr<CDimInterface>,CDimInterfaceTable::_SHARED_PTR_COMP,std::allocator<std::tr1::shared_ptr<CDimInterface>>,0>>::insert(
    v4,
    &v10,
    a2);
  v5 = std::map<void *,std::tr1::shared_ptr<CDimInterface>>::operator[](a1 + 216, *a2 + 96);
  std::tr1::shared_ptr<CDimInterface>::operator=(v5, a2);
  CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(a1, a2);
  CDimInterfaceTable::InsertInterfaceInHostNameMap(a1, a2);
  if ( *(_BYTE *)(a1 + 116) )
  {
    if ( CDimInterface::IsDimVsidInterface((CDimInterface *)*a2) )
    {
      std::tr1::static_pointer_cast<CDimVsidInterface,CDimInterface>(&v10, a2);
      v12 = *(_OWORD *)(*a2 + 3104);
      v13 = *(_QWORD *)(v10 + 3200);
      v6 = std::map<CDimInterfaceTable::_ROUTINGDOMAIN_LUID,std::tr1::shared_ptr<CDimVsidInterface>,CDimInterfaceTable::_ROUTINGDOMAIN_LUID_COMP,std::allocator<std::pair<CDimInterfaceTable::_ROUTINGDOMAIN_LUID const,std::tr1::shared_ptr<CDimVsidInterface>>>>::operator[](
             a1 + 248,
             &v12);
      std::tr1::shared_ptr<CDimVsidInterface>::operator=(v6, &v10);
      if ( v11 )
        std::tr1::_Ref_count_base::_Decref(v11);
    }
  }
  result = CDimInterface::IsDimS2SInterface((CDimInterface *)*a2);
  if ( result )
  {
    (**(void (__fastcall ***)(__int64))*a2)(*a2);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)*a2 + 456LL))(*a2) == 9
      && ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 104LL))(*a2) & 4) != 0
      && !_InterlockedCompareExchange(&dword_180070FC0, 0, 0)
      || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 104LL))(*a2) & 4) != 0
      && ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 104LL))(*a2) & 0x8000) != 0
      && !_InterlockedCompareExchange(&dword_180070FC0, 0, 0) )
    {
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 16LL))(*a2);
      TimerQRemove(v8, ReConnectPersistentInterface);
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 16LL))(*a2);
      TimerQInsert(v9, 1, ReConnectPersistentInterface);
    }
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)*a2 + 8LL))(*a2);
  }
  return result;
}

```

## disassembly

```asm
0x1800076ac  mov     [rsp+arg_8], rbx
0x1800076b1  push    rdi
0x1800076b2  sub     rsp, 50h
0x1800076b6  mov     rbx, rdx
0x1800076b9  mov     rdi, rcx
0x1800076bc  mov     rdx, [rdx]
0x1800076bf  add     rdx, 8
0x1800076c3  add     rcx, 78h ; 'x'
0x1800076c7  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$shared_ptr@VCDimInterface@@@tr1@std@@U_SHARED_PTR_COMP@CDimInterfaceTable@@V?$allocator@V?$shared_ptr@VCDimInterface@@@tr1@std@@@3@@2@U_WSTRING_COMP@CDimInterfaceTable@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$shared_ptr@VCDimInterface@@@tr1@std@@U_SHARED_PTR_COMP@CDimInterfaceTable@@V?$allocator@V?$shared_ptr@VCDimInterface@@@tr1@std@@@3@@2@@std@@@2@@std@@QEAAAEAV?$set@V?$shared_ptr@VCDimInterface@@@tr1@std@@U_SHARED_PTR_COMP@CDimInterfaceTable@@V?$allocator@V?$shared_ptr@VCDimInterface@@@tr1@std@@@3@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::set<std::tr1::shared_ptr<CDimInterface>,CDimInterfaceTable::_SHARED_PTR_COMP,std::allocator<std::tr1::shared_ptr<CDimInterface>>>,CDimInterfaceTable::_WSTRING_COMP,std::allocator<std::pair<std::wstring const,std::set<std::tr1::shared_ptr<CDimInterface>,CDimInterfaceTable::_SHARED_PTR_COMP,std::allocator<std::tr1::shared_ptr<CDimInterface>>>>>>::operator[](std::wstring const &)
0x1800076cc  mov     r8, rbx
0x1800076cf  lea     rdx, [rsp+58h+var_38]
0x1800076d4  mov     rcx, rax
0x1800076d7  call    ?insert@?$_Tree@V?$_Tset_traits@V?$shared_ptr@VCDimInterface@@@tr1@std@@U_SHARED_PTR_COMP@CDimInterfaceTable@@V?$allocator@V?$shared_ptr@VCDimInterface@@@tr1@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$shared_ptr@VCDimInterface@@@tr1@std@@U_SHARED_PTR_COMP@CDimInterfaceTable@@V?$allocator@V?$shared_ptr@VCDimInterface@@@tr1@std@@@3@$0A@@std@@@std@@@std@@_N@2@AEBV?$shared_ptr@VCDimInterface@@@tr1@2@_N@Z; std::_Tree<std::_Tset_traits<std::tr1::shared_ptr<CDimInterface>,CDimInterfaceTable::_SHARED_PTR_COMP,std::allocator<std::tr1::shared_ptr<CDimInterface>>,0>>::insert(std::tr1::shared_ptr<CDimInterface> const &,bool)
0x1800076dc  mov     rdx, [rbx]
0x1800076df  add     rdx, 60h ; '`'
0x1800076e3  lea     rcx, [rdi+0D8h]
0x1800076ea  call    ??A?$map@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@VCDimInterface@@@tr1@1@AEBQEAX@Z; std::map<void *,std::tr1::shared_ptr<CDimInterface>>::operator[](void * const &)
0x1800076ef  mov     rcx, rax
0x1800076f2  mov     rdx, rbx
0x1800076f5  call    ??4?$shared_ptr@VCDimInterface@@@tr1@std@@QEAAAEAV012@AEBV012@@Z; std::tr1::shared_ptr<CDimInterface>::operator=(std::tr1::shared_ptr<CDimInterface> const &)
0x1800076fa  mov     rdx, rbx
0x1800076fd  mov     rcx, rdi
0x180007700  call    ?InsertInterfaceInRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x180007705  mov     rdx, rbx
0x180007708  mov     rcx, rdi
0x18000770b  call    ?InsertInterfaceInHostNameMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInHostNameMap(std::tr1::shared_ptr<CDimInterface> const &)
0x180007710  cmp     byte ptr [rdi+74h], 0
0x180007714  jz      short loc_180007780
0x180007716  mov     rcx, [rbx]; this
0x180007719  call    ?IsDimVsidInterface@CDimInterface@@QEBA_NXZ; CDimInterface::IsDimVsidInterface(void)
0x18000771e  test    al, al
0x180007720  jz      short loc_180007780
0x180007722  mov     rdx, rbx
0x180007725  lea     rcx, [rsp+58h+var_38]
0x18000772a  call    ??$static_pointer_cast@VCDimVsidInterface@@VCDimInterface@@@tr1@std@@YA?AV?$shared_ptr@VCDimVsidInterface@@@01@AEBV?$shared_ptr@VCDimInterface@@@01@@Z; std::tr1::static_pointer_cast<CDimVsidInterface,CDimInterface>(std::tr1::shared_ptr<CDimInterface> const &)
0x18000772f  nop
0x180007730  mov     rax, [rbx]
0x180007733  movups  xmm0, xmmword ptr [rax+0C20h]
0x18000773a  movdqu  [rsp+58h+var_28], xmm0
0x180007740  mov     rax, [rsp+58h+var_38]
0x180007745  mov     rcx, [rax+0C80h]
0x18000774c  mov     [rsp+58h+var_18], rcx
0x180007751  lea     rcx, [rdi+0F8h]
0x180007758  lea     rdx, [rsp+58h+var_28]
0x18000775d  call    ??A?$map@U_ROUTINGDOMAIN_LUID@CDimInterfaceTable@@V?$shared_ptr@VCDimVsidInterface@@@tr1@std@@U_ROUTINGDOMAIN_LUID_COMP@2@V?$allocator@U?$pair@$$CBU_ROUTINGDOMAIN_LUID@CDimInterfaceTable@@V?$shared_ptr@VCDimVsidInterface@@@tr1@std@@@std@@@5@@std@@QEAAAEAV?$shared_ptr@VCDimVsidInterface@@@tr1@1@AEBU_ROUTINGDOMAIN_LUID@CDimInterfaceTable@@@Z; std::map<CDimInterfaceTable::_ROUTINGDOMAIN_LUID,std::tr1::shared_ptr<CDimVsidInterface>,CDimInterfaceTable::_ROUTINGDOMAIN_LUID_COMP,std::allocator<std::pair<CDimInterfaceTable::_ROUTINGDOMAIN_LUID const,std::tr1::shared_ptr<CDimVsidInterface>>>>::operator[](CDimInterfaceTable::_ROUTINGDOMAIN_LUID const &)
0x180007762  mov     rcx, rax
0x180007765  lea     rdx, [rsp+58h+var_38]
0x18000776a  call    ??4?$shared_ptr@VCDimVsidInterface@@@tr1@std@@QEAAAEAV012@AEBV012@@Z; std::tr1::shared_ptr<CDimVsidInterface>::operator=(std::tr1::shared_ptr<CDimVsidInterface> const &)
0x18000776f  nop
0x180007770  mov     rcx, [rsp+58h+var_30]; this
0x180007775  test    rcx, rcx
0x180007778  jz      short loc_180007780
0x18000777a  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x18000777f  nop
0x180007780  mov     rcx, [rbx]; this
0x180007783  call    ?IsDimS2SInterface@CDimInterface@@QEBA_NXZ; CDimInterface::IsDimS2SInterface(void)
0x180007788  test    al, al
0x18000778a  jz      loc_18000785E
0x180007790  mov     rcx, [rbx]
0x180007793  mov     rax, [rcx]
0x180007796  mov     rax, [rax]
0x180007799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000779e  mov     rcx, [rbx]
0x1800077a1  mov     rax, [rcx]
0x1800077a4  mov     rax, [rax+1C8h]
0x1800077ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b0  cmp     eax, 9
0x1800077b3  jnz     short loc_1800077D6
0x1800077b5  mov     rcx, [rbx]
0x1800077b8  mov     rax, [rcx]
0x1800077bb  mov     rax, [rax+68h]
0x1800077bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077c4  test    al, 4
0x1800077c6  jz      short loc_1800077D6
0x1800077c8  xor     ecx, ecx
0x1800077ca  xor     eax, eax
0x1800077cc  lock cmpxchg cs:dword_180070FC0, ecx
0x1800077d4  jz      short loc_18000780C
0x1800077d6  mov     rcx, [rbx]
0x1800077d9  mov     rax, [rcx]
0x1800077dc  mov     rax, [rax+68h]
0x1800077e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e5  test    al, 4
0x1800077e7  jz      short loc_18000784F
0x1800077e9  mov     rcx, [rbx]
0x1800077ec  mov     rax, [rcx]
0x1800077ef  mov     rax, [rax+68h]
0x1800077f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f8  bt      eax, 0Fh
0x1800077fc  jnb     short loc_18000784F
0x1800077fe  xor     ecx, ecx
0x180007800  xor     eax, eax
0x180007802  lock cmpxchg cs:dword_180070FC0, ecx
0x18000780a  jnz     short loc_18000784F
0x18000780c  mov     rcx, [rbx]
0x18000780f  mov     rax, [rcx]
0x180007812  mov     rax, [rax+10h]
0x180007816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000781b  mov     rdx, cs:__imp_ReConnectPersistentInterface
0x180007822  mov     rcx, rax
0x180007825  call    cs:__imp_TimerQRemove
0x18000782b  mov     rcx, [rbx]
0x18000782e  mov     rax, [rcx]
0x180007831  mov     rax, [rax+10h]
0x180007835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000783a  mov     r8, cs:__imp_ReConnectPersistentInterface
0x180007841  mov     edx, 1
0x180007846  mov     rcx, rax
0x180007849  call    cs:__imp_TimerQInsert
0x18000784f  mov     rcx, [rbx]
0x180007852  mov     rax, [rcx]
0x180007855  mov     rax, [rax+8]
0x180007859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785e  mov     rbx, [rsp+58h+arg_8]
0x180007863  add     rsp, 50h
0x180007867  pop     rdi
0x180007868  retn
```
