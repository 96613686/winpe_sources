# CESimSettingServer::~CESimSettingServer(void)

- ea: `0x18000d128`
- end: `0x18000d20a`
- name: `??1CESimSettingServer@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(CESimSettingServer *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18000d4a0`
- `0x18000d6b0`

## callees

- `0x1800028b0`
- `0x18000c160`
- `0x18000c1f4`
- `0x18000d128`
- `0x18000d2c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d1f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d1f4`
- `luiapi!LuiCloseHandle` at `0x18000d1bd`
- `luiapi!LuiCloseHandle` at `0x18000d1bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CESimSettingServer::~CESimSettingServer(CESimSettingServer *this)
{
  _QWORD *v2; // rbx
  void *v3; // rcx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CESimSettingServer::`vftable'{for `IESimSettingServer'};
  *((_QWORD *)this + 1) = &CESimSettingServer::`vftable'{for `IESimSettingEventHandler'};
  CSOperationDispatcher::~CSOperationDispatcher((CESimSettingServer *)((char *)this + 232));
  CSOperationDispatcher::~CSOperationDispatcher((CESimSettingServer *)((char *)this + 152));
  v2 = *(_QWORD **)(*((_QWORD *)this + 17) + 8LL);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<_GUID,enum SimSlot> const,bool>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::pair<_GUID,enum SimSlot> const,bool>,void *>>>(
      (char *)this + 136,
      (char *)this + 136,
      v2[2]);
    v3 = v2;
    v2 = (_QWORD *)*v2;
    operator delete(v3);
  }
  operator delete(*((void **)this + 17));
  if ( *((_QWORD *)this + 14) != -1 )
  {
    v4 = *((_QWORD *)this + 14);
    LuiCloseHandle(&v4);
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<_GUID,enum SimSlot> const,std::shared_ptr<AdapterSlotData>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::pair<_GUID,enum SimSlot> const,std::shared_ptr<AdapterSlotData>>,void *>>>(
    (char *)this + 88,
    (char *)this + 88,
    *(_QWORD *)(*((_QWORD *)this + 11) + 8LL));
  operator delete(*((void **)this + 11));
  if ( *((_BYTE *)this + 64) )
  {
    *((_BYTE *)this + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
}

```

## disassembly

```asm
0x18000d128  mov     [rsp+arg_8], rbx
0x18000d12d  mov     [rsp+arg_10], rsi
0x18000d132  push    rdi
0x18000d133  sub     rsp, 20h
0x18000d137  lea     rax, ??_7CESimSettingServer@@6BIESimSettingServer@@@; const CESimSettingServer::`vftable'{for `IESimSettingServer'}
0x18000d13e  mov     rdi, rcx
0x18000d141  mov     [rcx], rax
0x18000d144  lea     rax, ??_7CESimSettingServer@@6BIESimSettingEventHandler@@@; const CESimSettingServer::`vftable'{for `IESimSettingEventHandler'}
0x18000d14b  mov     [rcx+8], rax
0x18000d14f  add     rcx, 0E8h; this
0x18000d156  call    ??1CSOperationDispatcher@@QEAA@XZ; CSOperationDispatcher::~CSOperationDispatcher(void)
0x18000d15b  lea     rcx, [rdi+98h]; this
0x18000d162  call    ??1CSOperationDispatcher@@QEAA@XZ; CSOperationDispatcher::~CSOperationDispatcher(void)
0x18000d167  lea     rsi, [rdi+88h]
0x18000d16e  mov     rax, [rsi]
0x18000d171  mov     rbx, [rax+8]
0x18000d175  jmp     short loc_18000D196
0x18000d177  mov     r8, [rbx+10h]
0x18000d17b  mov     rdx, rsi
0x18000d17e  mov     rcx, rsi
0x18000d181  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@_N@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@_N@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@_N@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@_N@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<_GUID,SimSlot> const,bool>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::pair<_GUID,SimSlot> const,bool>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::pair<_GUID,SimSlot> const,bool>,void *>> &,std::_Tree_node<std::pair<std::pair<_GUID,SimSlot> const,bool>,void *> *)
0x18000d186  mov     rcx, rbx; Block
0x18000d189  mov     edx, 38h ; '8'
0x18000d18e  mov     rbx, [rbx]
0x18000d191  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d196  cmp     byte ptr [rbx+19h], 0
0x18000d19a  jz      short loc_18000D177
0x18000d19c  mov     rcx, [rsi]; Block
0x18000d19f  mov     edx, 38h ; '8'
0x18000d1a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d1a9  mov     rax, [rdi+70h]
0x18000d1ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d1b1  jz      short loc_18000D1C3
0x18000d1b3  lea     rcx, [rsp+28h+arg_0]
0x18000d1b8  mov     [rsp+28h+arg_0], rax
0x18000d1bd  call    cs:__imp_LuiCloseHandle
0x18000d1c3  lea     rbx, [rdi+58h]
0x18000d1c7  mov     r8, [rbx]
0x18000d1ca  mov     rdx, rbx
0x18000d1cd  mov     rcx, rbx
0x18000d1d0  mov     r8, [r8+8]
0x18000d1d4  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@V?$shared_ptr@UAdapterSlotData@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@V?$shared_ptr@UAdapterSlotData@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@V?$shared_ptr@UAdapterSlotData@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@V?$shared_ptr@UAdapterSlotData@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<_GUID,SimSlot> const,std::shared_ptr<AdapterSlotData>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::pair<_GUID,SimSlot> const,std::shared_ptr<AdapterSlotData>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::pair<_GUID,SimSlot> const,std::shared_ptr<AdapterSlotData>>,void *>> &,std::_Tree_node<std::pair<std::pair<_GUID,SimSlot> const,std::shared_ptr<AdapterSlotData>>,void *> *)
0x18000d1d9  mov     rcx, [rbx]; Block
0x18000d1dc  mov     edx, 48h ; 'H'
0x18000d1e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d1e6  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000d1ea  cmp     byte ptr [rcx+28h], 0
0x18000d1ee  jz      short loc_18000D1FA
0x18000d1f0  mov     byte ptr [rcx+28h], 0
0x18000d1f4  call    cs:__imp_DeleteCriticalSection
0x18000d1fa  mov     rbx, [rsp+28h+arg_8]
0x18000d1ff  mov     rsi, [rsp+28h+arg_10]
0x18000d204  add     rsp, 20h
0x18000d208  pop     rdi
0x18000d209  retn
```
