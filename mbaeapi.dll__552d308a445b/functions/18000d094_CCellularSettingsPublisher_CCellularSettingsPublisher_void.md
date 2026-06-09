# CCellularSettingsPublisher::~CCellularSettingsPublisher(void)

- ea: `0x18000d094`
- end: `0x18000d11f`
- name: `??1CCellularSettingsPublisher@@QEAA@XZ`
- size: `139`
- prototype: `void __fastcall(CCellularSettingsPublisher *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d430`
- `0x18000d640`

## callees

- `0x18000ccc8`
- `0x18000d094`
- `0x18000d3c0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d0a8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d10e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d0a8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d10e`

## pseudocode

```c
void __fastcall CCellularSettingsPublisher::~CCellularSettingsPublisher(CCellularSettingsPublisher *this)
{
  volatile signed __int32 *v2; // rbx

  DeleteCriticalSection((LPCRITICAL_SECTION)this + 10);
  WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue((CCellularSettingsPublisher *)((char *)this + 120));
  std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>((void **)this + 11);
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 10);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  if ( *((_BYTE *)this + 64) )
  {
    *((_BYTE *)this + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
}

```

## disassembly

```asm
0x18000d094  mov     [rsp+arg_0], rbx
0x18000d099  push    rdi
0x18000d09a  sub     rsp, 20h
0x18000d09e  mov     rdi, rcx
0x18000d0a1  add     rcx, 190h; lpCriticalSection
0x18000d0a8  call    cs:__imp_DeleteCriticalSection
0x18000d0ae  lea     rcx, [rdi+78h]; this
0x18000d0b2  call    ??1ThreadPoolWorkQueue@WcmCommon@@QEAA@XZ; WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(void)
0x18000d0b7  lea     rcx, [rdi+58h]
0x18000d0bb  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::~_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>(void)
0x18000d0c0  mov     rbx, [rdi+50h]
0x18000d0c4  test    rbx, rbx
0x18000d0c7  jz      short loc_18000D100
0x18000d0c9  or      eax, 0FFFFFFFFh
0x18000d0cc  lock xadd [rbx+8], eax
0x18000d0d1  cmp     eax, 1
0x18000d0d4  jnz     short loc_18000D100
0x18000d0d6  mov     rax, [rbx]
0x18000d0d9  mov     rcx, rbx
0x18000d0dc  mov     rax, [rax]
0x18000d0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0e4  or      eax, 0FFFFFFFFh
0x18000d0e7  lock xadd [rbx+0Ch], eax
0x18000d0ec  cmp     eax, 1
0x18000d0ef  jnz     short loc_18000D100
0x18000d0f1  mov     rax, [rbx]
0x18000d0f4  mov     rcx, rbx
0x18000d0f7  mov     rax, [rax+8]
0x18000d0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d100  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000d104  cmp     byte ptr [rcx+28h], 0
0x18000d108  jz      short loc_18000D114
0x18000d10a  mov     byte ptr [rcx+28h], 0
0x18000d10e  call    cs:__imp_DeleteCriticalSection
0x18000d114  mov     rbx, [rsp+28h+arg_0]
0x18000d119  add     rsp, 20h
0x18000d11d  pop     rdi
0x18000d11e  retn
```
