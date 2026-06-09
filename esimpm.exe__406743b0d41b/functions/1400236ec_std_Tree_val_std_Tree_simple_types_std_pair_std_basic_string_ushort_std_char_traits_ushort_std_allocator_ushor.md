# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord,std::default_delete<ESIMPM::LpaHelper::EsimRecord>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord,std::default_delete<ESIMPM::LpaHelper::EsimRecord>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord,std::default_delete<ESIMPM::LpaHelper::EsimRecord>>>,void *>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord,std::default_delete<ESIMPM::LpaHelper::EsimRecord>>>,void *> *)

- ea: `0x1400236ec`
- end: `0x140023773`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@PEAX@1@@Z`
- size: `135`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400236ec`
- `0x140023944`
- `0x140024004`
- `0x14002fb4c`

## callees

- `0x140003244`
- `0x140013df8`
- `0x1400236ec`
- `0x140023868`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rbx
  _QWORD *v6; // rsi
  void **v7; // rdi

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    v7 = (void **)v6[8];
    if ( v7 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::EsimProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::EsimProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>>,0>>(v7 + 1);
      if ( *v7 )
        operator delete(*v7);
      operator delete(v7);
    }
    std::wstring::_Tidy_deallocate(v6 + 4);
    operator delete(v6);
  }
}

```

## disassembly

```asm
0x1400236ec  push    rbx
0x1400236ee  push    rbp
0x1400236ef  push    rsi
0x1400236f0  push    rdi
0x1400236f1  push    r14
0x1400236f3  push    r15
0x1400236f5  sub     rsp, 28h
0x1400236f9  cmp     byte ptr [r8+19h], 0
0x1400236fe  mov     rbx, r8
0x140023701  mov     r14, rdx
0x140023704  mov     r15, rcx
0x140023707  jnz     short loc_140023766
0x140023709  mov     r8, [rbx+10h]
0x14002370d  mov     rdx, r14
0x140023710  mov     rcx, r15
0x140023713  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimRecord@LpaHelper@ESIMPM@@U?$default_delete@UEsimRecord@LpaHelper@ESIMPM@@@std@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ESIMPM::LpaHelper::EsimRecord>>,void *> *)
0x140023718  mov     rsi, rbx
0x14002371b  mov     rbx, [rbx]
0x14002371e  mov     rdi, [rsi+40h]
0x140023722  test    rdi, rdi
0x140023725  jz      short loc_14002374A
0x140023727  lea     rcx, [rdi+8]
0x14002372b  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VEsimProfile@ESIMPM@@U?$default_delete@VEsimProfile@ESIMPM@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VEsimProfile@ESIMPM@@U?$default_delete@VEsimProfile@ESIMPM@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::EsimProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::EsimProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>>,0>>(void)
0x140023730  mov     rcx, [rdi]; Block
0x140023733  test    rcx, rcx
0x140023736  jz      short loc_14002373D
0x140023738  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002373d  mov     edx, 18h
0x140023742  mov     rcx, rdi; Block
0x140023745  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002374a  lea     rcx, [rsi+20h]
0x14002374e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140023753  mov     edx, 48h ; 'H'
0x140023758  mov     rcx, rsi; Block
0x14002375b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140023760  cmp     byte ptr [rbx+19h], 0
0x140023764  jz      short loc_140023709
0x140023766  add     rsp, 28h
0x14002376a  pop     r15
0x14002376c  pop     r14
0x14002376e  pop     rdi
0x14002376f  pop     rsi
0x140023770  pop     rbp
0x140023771  pop     rbx
0x140023772  retn
```
