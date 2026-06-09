# CNetDiagClient::~CNetDiagClient(void)

- ea: `0x180008304`
- end: `0x1800083ca`
- name: `??1CNetDiagClient@@QEAA@XZ`
- size: `198`
- prototype: `void __fastcall(void **this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000a160`
- `0x18000a9e0`
- `0x180014340`

## callees

- `0x180002044`
- `0x180008144`
- `0x1800081c4`
- `0x180008304`
- `0x1800086cc`
- `0x1800089b4`
- `0x180009fcc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008333`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800083b0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008333`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800083b0`
- `ole32!CoTaskMemFree` at `0x180008321`
- `ole32!CoTaskMemFree` at `0x180008321`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CNetDiagClient::~CNetDiagClient(void **this)
{
  void *v2; // rcx
  void *v3; // rcx

  CNetDiagClient::CleanupDiagnosis((CNetDiagClient *)this);
  v2 = this[3];
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = this[385];
  if ( v3 )
  {
    operator delete(v3);
    this[385] = 0;
    this[386] = 0;
    this[387] = 0;
  }
  `eh vector destructor iterator'(this + 247, 0x58u, 0xCu, (void (*)(void *))CRootCauseInfo::~CRootCauseInfo);
  `eh vector destructor iterator'(this + 18, 0x98u, 0xCu, (void (*)(void *))CRepairInfo::~CRepairInfo);
  std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::~_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>(this + 14);
  std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::~_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>(this + 12);
  std::_Tree<std::_Tmap_traits<_GUID,std::wstring,GuidLessThan,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::wstring,GuidLessThan,std::allocator<std::pair<_GUID const,std::wstring>>,0>>(this + 10);
  std::_Tree<std::_Tmap_traits<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::clear(this + 8);
  operator delete(this[8]);
  _attributes_array_t::FreeAll((_attributes_array_t *)(this + 4));
}

```

## disassembly

```asm
0x180008304  mov     [rsp+arg_0], rbx
0x180008309  push    rdi
0x18000830a  sub     rsp, 20h
0x18000830e  mov     rdi, rcx
0x180008311  call    ?CleanupDiagnosis@CNetDiagClient@@IEAAJXZ; CNetDiagClient::CleanupDiagnosis(void)
0x180008316  mov     rcx, [rdi+18h]; pv
0x18000831a  xor     ebx, ebx
0x18000831c  test    rcx, rcx
0x18000831f  jz      short loc_180008327
0x180008321  call    cs:__imp_CoTaskMemFree
0x180008327  mov     rcx, [rdi+0C08h]
0x18000832e  test    rcx, rcx
0x180008331  jz      short loc_18000834E
0x180008333  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008339  mov     [rdi+0C08h], rbx
0x180008340  mov     [rdi+0C10h], rbx
0x180008347  mov     [rdi+0C18h], rbx
0x18000834e  lea     rcx, [rdi+7B8h]; void *
0x180008355  lea     r9, ??1CRootCauseInfo@@UEAA@XZ; void (*)(void *)
0x18000835c  mov     ebx, 0Ch
0x180008361  mov     r8d, ebx; unsigned __int64
0x180008364  lea     edx, [rbx+4Ch]; unsigned __int64
0x180008367  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000836c  lea     rcx, [rdi+90h]; void *
0x180008373  lea     r9, ??1CRepairInfo@@UEAA@XZ; void (*)(void *)
0x18000837a  mov     r8d, ebx; unsigned __int64
0x18000837d  mov     edx, 98h; unsigned __int64
0x180008382  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180008387  lea     rcx, [rdi+70h]
0x18000838b  call    ??1?$_Tree@V?$_Tset_traits@U_GUID@@UGuidLessThan@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::~_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>(void)
0x180008390  lea     rcx, [rdi+60h]
0x180008394  call    ??1?$_Tree@V?$_Tset_traits@U_GUID@@UGuidLessThan@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::~_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>(void)
0x180008399  lea     rcx, [rdi+50h]
0x18000839d  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGuidLessThan@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::wstring,GuidLessThan,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::wstring,GuidLessThan,std::allocator<std::pair<_GUID const,std::wstring>>,0>>(void)
0x1800083a2  nop
0x1800083a3  lea     rcx, [rdi+40h]
0x1800083a7  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@UWstringLessThan@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::clear(void)
0x1800083ac  mov     rcx, [rdi+40h]
0x1800083b0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800083b6  nop
0x1800083b7  lea     rcx, [rdi+20h]; this
0x1800083bb  mov     rbx, [rsp+28h+arg_0]
0x1800083c0  add     rsp, 20h
0x1800083c4  pop     rdi
0x1800083c5  jmp     ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
```
