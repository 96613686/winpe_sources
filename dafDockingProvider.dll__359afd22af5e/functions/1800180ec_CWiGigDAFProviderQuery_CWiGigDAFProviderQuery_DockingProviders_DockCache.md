# CWiGigDAFProviderQuery::CWiGigDAFProviderQuery(DockingProviders *,DockCache *)

- ea: `0x1800180ec`
- end: `0x180018216`
- name: `??0CWiGigDAFProviderQuery@@QEAA@PEAVDockingProviders@@PEAVDockCache@@@Z`
- size: `298`
- prototype: `CWiGigDAFProviderQuery *__fastcall(CWiGigDAFProviderQuery *__hidden this, struct DockingProviders *, struct DockCache *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ce20`

## callees

- `0x180001484`
- `0x1800020bd`
- `0x18001117c`
- `0x1800180ec`
- `0x180019e70`
- `0x18001a24c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001813e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001813e`

## pseudocode

```c
CWiGigDAFProviderQuery *__fastcall CWiGigDAFProviderQuery::CWiGigDAFProviderQuery(
        CWiGigDAFProviderQuery *this,
        struct DockingProviders *a2,
        struct DockCache *a3)
{
  _QWORD *v4; // rax
  const char *v5; // rdx
  __int64 v6; // rdx
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF
  __int16 v9; // [rsp+60h] [rbp+8h]
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF
  char *v11; // [rsp+70h] [rbp+18h]

  v9 = (__int16)this;
  *(_QWORD *)this = &CWiGigDAFProviderQuery::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 16) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = a2;
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)this + 6) = a3;
  if ( a3 )
    _InterlockedIncrement((volatile signed __int32 *)a3 + 24);
  *((_DWORD *)this + 14) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *((_BYTE *)this + 104) = 0;
  v11 = (char *)this + 112;
  *((_WORD *)this + 56) = v9;
  *((_QWORD *)this + 16) = 0;
  v4 = operator new(0x4A8u);
  if ( !v4 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, v5);
    throw (std::bad_alloc *)pExceptionObject;
  }
  *((_QWORD *)this + 15) = v4;
  *v4 = v4;
  *(_QWORD *)(*((_QWORD *)this + 15) + 8LL) = *((_QWORD *)this + 15);
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 48) = 1065353216;
  std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::reserve(
    (char *)this + 144,
    16);
  v10 = *((_QWORD *)this + 15);
  v6 = *((_QWORD *)this + 18);
  if ( v6 != *((_QWORD *)this + 19) )
    *((_QWORD *)this + 19) = v6;
  std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Insert_n(
    (char *)this + 144,
    v6,
    16,
    &v10);
  *((_QWORD *)this + 22) = 7;
  *((_QWORD *)this + 23) = 8;
  *((_QWORD *)this + 25) = 0;
  _InterlockedIncrement((volatile signed __int32 *)&g_cLockCount);
  return this;
}

```

## disassembly

```asm
0x1800180ec  mov     [rsp+arg_18], rbx
0x1800180f1  mov     [rsp+arg_0], rcx
0x1800180f6  push    rbp
0x1800180f7  push    rsi
0x1800180f8  push    rdi
0x1800180f9  sub     rsp, 40h
0x1800180fd  mov     rbx, rcx
0x180018100  lea     rax, ??_7CWiGigDAFProviderQuery@@6B@; const CWiGigDAFProviderQuery::`vftable'
0x180018107  mov     [rcx], rax
0x18001810a  xor     ebp, ebp
0x18001810c  mov     [rcx+8], rbp
0x180018110  mov     [rcx+10h], bpl
0x180018114  mov     [rcx+18h], rbp
0x180018118  mov     [rcx+20h], rbp
0x18001811c  mov     [rcx+28h], rdx
0x180018120  test    rdx, rdx
0x180018123  jz      short loc_180018129
0x180018125  lock inc dword ptr [rdx+8]
0x180018129  mov     [rcx+30h], r8
0x18001812d  test    r8, r8
0x180018130  jz      short loc_180018137
0x180018132  lock inc dword ptr [r8+60h]
0x180018137  mov     [rcx+38h], ebp
0x18001813a  add     rcx, 40h ; '@'; lpCriticalSection
0x18001813e  call    cs:__imp_InitializeCriticalSection
0x180018144  nop
0x180018145  mov     [rbx+68h], bpl
0x180018149  lea     rdi, [rbx+70h]
0x18001814d  mov     [rsp+58h+arg_10], rdi
0x180018152  movzx   eax, word ptr [rsp+58h+arg_0]
0x180018157  mov     [rdi], ax
0x18001815a  mov     [rdi+10h], rbp
0x18001815e  mov     ecx, 4A8h; Size
0x180018163  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018168  test    rax, rax
0x18001816b  jz      loc_1800181FA
0x180018171  mov     [rdi+8], rax
0x180018175  mov     [rax], rax
0x180018178  mov     rax, [rdi+8]
0x18001817c  mov     [rax+8], rax
0x180018180  lea     rsi, [rdi+20h]
0x180018184  mov     [rsi], rbp
0x180018187  mov     [rsi+8], rbp
0x18001818b  mov     [rsi+10h], rbp
0x18001818f  mov     dword ptr [rdi+50h], 3F800000h
0x180018196  mov     edx, 10h
0x18001819b  mov     rcx, rsi
0x18001819e  call    ?reserve@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::reserve(unsigned __int64)
0x1800181a3  mov     rax, [rdi+8]
0x1800181a7  mov     [rsp+58h+arg_8], rax
0x1800181ac  mov     rdx, [rsi]
0x1800181af  cmp     rdx, [rsi+8]
0x1800181b3  jz      short loc_1800181B9
0x1800181b5  mov     [rsi+8], rdx
0x1800181b9  lea     r9, [rsp+58h+arg_8]
0x1800181be  mov     r8d, 10h
0x1800181c4  mov     rcx, rsi
0x1800181c7  call    ?_Insert_n@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@IEAAXV?$_Vector_const_iterator@V?$_Vector_val@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@@2@_KAEBV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@@Z; std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>>,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> const &)
0x1800181cc  mov     qword ptr [rdi+40h], 7
0x1800181d4  mov     qword ptr [rdi+48h], 8
0x1800181dc  mov     [rbx+0C8h], rbp
0x1800181e3  lock inc cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x1800181ea  mov     rax, rbx
0x1800181ed  mov     rbx, [rsp+58h+arg_18]
0x1800181f2  add     rsp, 40h
0x1800181f6  pop     rdi
0x1800181f7  pop     rsi
0x1800181f8  pop     rbp
0x1800181f9  retn
0x1800181fa  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800181ff  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180018204  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001820b  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180018210  call    _CxxThrowException_0
```
