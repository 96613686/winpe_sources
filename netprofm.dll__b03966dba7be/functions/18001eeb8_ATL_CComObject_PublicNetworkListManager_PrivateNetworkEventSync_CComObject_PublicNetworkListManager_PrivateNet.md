# ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::~CComObject<PublicNetworkListManager::PrivateNetworkEventSync>(void)

- ea: `0x18001eeb8`
- end: `0x18001ef20`
- name: `??1?$CComObject@VPrivateNetworkEventSync@PublicNetworkListManager@@@ATL@@UEAA@XZ`
- size: `104`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f2c0`

## callees

- `0x180008020`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eefa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001eefa`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::~CComObject<PublicNetworkListManager::PrivateNetworkEventSync>(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = a1 + 32;
  *(_DWORD *)(a1 + 32) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::`vftable'{for `INotifyNetworkListManagerEventsPrivate'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::`vftable'{for `INotifyNetworkEventsPrivate'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::`vftable'{for `INotifyNetworkInterfaceEventsPrivate'};
  *(_QWORD *)(a1 + 24) = &ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::`vftable'{for `INotifyNetworkGlobalCostEventsPrivate'};
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 608));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  return ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(v1);
}

```

## disassembly

```asm
0x18001eeb8  push    rbx
0x18001eeba  sub     rsp, 20h
0x18001eebe  lea     rbx, [rcx+20h]
0x18001eec2  lea     rax, ??_7?$CComObject@VPrivateNetworkEventSync@PublicNetworkListManager@@@ATL@@6BINotifyNetworkListManagerEventsPrivate@@@; const ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::`vftable'{for `INotifyNetworkListManagerEventsPrivate'}
0x18001eec9  mov     dword ptr [rbx], 0C0000001h
0x18001eecf  mov     [rcx], rax
0x18001eed2  lea     rax, ??_7?$CComObject@VPrivateNetworkEventSync@PublicNetworkListManager@@@ATL@@6BINotifyNetworkEventsPrivate@@@; const ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::`vftable'{for `INotifyNetworkEventsPrivate'}
0x18001eed9  mov     [rcx+8], rax
0x18001eedd  lea     rax, ??_7?$CComObject@VPrivateNetworkEventSync@PublicNetworkListManager@@@ATL@@6BINotifyNetworkInterfaceEventsPrivate@@@; const ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::`vftable'{for `INotifyNetworkInterfaceEventsPrivate'}
0x18001eee4  mov     [rcx+10h], rax
0x18001eee8  lea     rax, ??_7?$CComObject@VPrivateNetworkEventSync@PublicNetworkListManager@@@ATL@@6BINotifyNetworkGlobalCostEventsPrivate@@@; const ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::`vftable'{for `INotifyNetworkGlobalCostEventsPrivate'}
0x18001eeef  mov     [rcx+18h], rax
0x18001eef3  add     rcx, 260h; lpCriticalSection
0x18001eefa  call    cs:__imp_DeleteCriticalSection
0x18001ef00  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001ef07  mov     rax, [rcx]
0x18001ef0a  mov     rax, [rax+10h]
0x18001ef0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef13  mov     rcx, rbx
0x18001ef16  add     rsp, 20h
0x18001ef1a  pop     rbx
0x18001ef1b  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
