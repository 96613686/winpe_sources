# BthServGlobals::~BthServGlobals(void)

- ea: `0x18000b214`
- end: `0x18000b30e`
- name: `??1BthServGlobals@@QEAA@XZ`
- size: `250`
- prototype: `void __fastcall(BthServGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180035c00`

## callees

- `0x180001b94`
- `0x18000ab98`
- `0x18000b194`
- `0x18000b214`
- `0x18001414c`
- `0x18001eb6c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b280`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b280`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2af`

## pseudocode

```c
void __fastcall BthServGlobals::~BthServGlobals(BthServGlobals *this)
{
  void *v2; // rbx
  HMODULE v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  volatile signed __int32 *v5; // rbx

  std::unique_ptr<LocalCorePerformanceTelemetryCollector>::~unique_ptr<LocalCorePerformanceTelemetryCollector>((struct _TP_TIMER ***)this + 48);
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>,void *>>>(
    (char *)this + 368,
    (char *)this + 368,
    *(_QWORD *)(*((_QWORD *)this + 46) + 8LL));
  operator delete(*((void **)this + 46), (const struct std::nothrow_t *)0x38);
  v2 = (void *)*((_QWORD *)this + 44);
  if ( v2 )
  {
    Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(*((Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher **)this
                                                                                             + 44));
    operator delete(v2, (const struct std::nothrow_t *)0x28);
  }
  v3 = (HMODULE)*((_QWORD *)this + 42);
  if ( v3 )
    FreeLibrary(v3);
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 41);
  if ( v4 )
    (**v4)(v4, 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 14);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  BthServRadioInterfaceWatcher::~BthServRadioInterfaceWatcher((BthServGlobals *)((char *)this + 64));
}

```

## disassembly

```asm
0x18000b214  mov     [rsp+arg_0], rbx
0x18000b219  push    rdi
0x18000b21a  sub     rsp, 20h
0x18000b21e  mov     rdi, rcx
0x18000b221  add     rcx, 180h
0x18000b228  call    ??1?$unique_ptr@VLocalCorePerformanceTelemetryCollector@@U?$default_delete@VLocalCorePerformanceTelemetryCollector@@@std@@@std@@QEAA@XZ; std::unique_ptr<LocalCorePerformanceTelemetryCollector>::~unique_ptr<LocalCorePerformanceTelemetryCollector>(void)
0x18000b22d  lea     rbx, [rdi+170h]
0x18000b234  mov     r8, [rbx]
0x18000b237  mov     rdx, rbx
0x18000b23a  mov     rcx, rbx
0x18000b23d  mov     r8, [r8+8]
0x18000b241  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@VFingerprintCollectorTimer@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@VFingerprintCollectorTimer@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@VFingerprintCollectorTimer@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@VFingerprintCollectorTimer@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<FingerprintCollectorTimer>>,void *> *)
0x18000b246  mov     rcx, [rbx]; void *
0x18000b249  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x18000b24e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b253  mov     rbx, [rdi+160h]
0x18000b25a  test    rbx, rbx
0x18000b25d  jz      short loc_18000B274
0x18000b25f  mov     rcx, rbx; this
0x18000b262  call    ??1BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(void)
0x18000b267  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18000b26c  mov     rcx, rbx; void *
0x18000b26f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b274  mov     rcx, [rdi+150h]; hLibModule
0x18000b27b  test    rcx, rcx
0x18000b27e  jz      short loc_18000B28C
0x18000b280  call    cs:__imp_FreeLibrary
0x18000b287  nop     dword ptr [rax+rax+00h]
0x18000b28c  mov     rcx, [rdi+148h]
0x18000b293  test    rcx, rcx
0x18000b296  jz      short loc_18000B2A8
0x18000b298  mov     rax, [rcx]
0x18000b29b  mov     edx, 1
0x18000b2a0  mov     rax, [rax]
0x18000b2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2a8  lea     rcx, [rdi+100h]; lpCriticalSection
0x18000b2af  call    cs:__imp_DeleteCriticalSection
0x18000b2b6  nop     dword ptr [rax+rax+00h]
0x18000b2bb  mov     rbx, [rdi+70h]
0x18000b2bf  test    rbx, rbx
0x18000b2c2  jz      short loc_18000B2FB
0x18000b2c4  or      eax, 0FFFFFFFFh
0x18000b2c7  lock xadd [rbx+8], eax
0x18000b2cc  cmp     eax, 1
0x18000b2cf  jnz     short loc_18000B2FB
0x18000b2d1  mov     rax, [rbx]
0x18000b2d4  mov     rcx, rbx
0x18000b2d7  mov     rax, [rax]
0x18000b2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2df  or      eax, 0FFFFFFFFh
0x18000b2e2  lock xadd [rbx+0Ch], eax
0x18000b2e7  cmp     eax, 1
0x18000b2ea  jnz     short loc_18000B2FB
0x18000b2ec  mov     rax, [rbx]
0x18000b2ef  mov     rcx, rbx
0x18000b2f2  mov     rax, [rax+8]
0x18000b2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2fb  lea     rcx, [rdi+40h]; this
0x18000b2ff  mov     rbx, [rsp+28h+arg_0]
0x18000b304  add     rsp, 20h
0x18000b308  pop     rdi
0x18000b309  jmp     ??1BthServRadioInterfaceWatcher@@QEAA@XZ; BthServRadioInterfaceWatcher::~BthServRadioInterfaceWatcher(void)
```
