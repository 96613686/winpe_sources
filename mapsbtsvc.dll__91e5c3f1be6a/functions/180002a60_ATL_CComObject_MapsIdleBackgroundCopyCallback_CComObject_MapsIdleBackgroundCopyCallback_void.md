# ATL::CComObject<MapsIdleBackgroundCopyCallback>::~CComObject<MapsIdleBackgroundCopyCallback>(void)

- ea: `0x180002a60`
- end: `0x180002a9b`
- name: `??1?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002af0`

## callees

- `0x180002ac4`
- `0x180015010`

## pseudocode

```c
void __fastcall ATL::CComObject<MapsIdleBackgroundCopyCallback>::~CComObject<MapsIdleBackgroundCopyCallback>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<MapsIdleBackgroundCopyCallback>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x180002a60  push    rbx
0x180002a62  sub     rsp, 20h
0x180002a66  mov     dword ptr [rcx+8], 0C0000001h
0x180002a6d  lea     rax, ??_7?$CComObject@VMapsIdleBackgroundCopyCallback@@@ATL@@6B@; const ATL::CComObject<MapsIdleBackgroundCopyCallback>::`vftable'
0x180002a74  mov     [rcx], rax
0x180002a77  mov     rbx, rcx
0x180002a7a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002a81  mov     rax, [rcx]
0x180002a84  mov     rax, [rax+10h]
0x180002a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a8d  lea     rcx, [rbx+10h]; this
0x180002a91  add     rsp, 20h
0x180002a95  pop     rbx
0x180002a96  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
