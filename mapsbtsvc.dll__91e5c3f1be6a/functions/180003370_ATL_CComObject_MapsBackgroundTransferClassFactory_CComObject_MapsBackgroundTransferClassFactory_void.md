# ATL::CComObject<MapsBackgroundTransferClassFactory>::~CComObject<MapsBackgroundTransferClassFactory>(void)

- ea: `0x180003370`
- end: `0x1800033b5`
- name: `??1?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@UEAA@XZ`
- size: `69`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003420`

## callees

- `0x180002ac4`
- `0x180015010`

## pseudocode

```c
void __fastcall ATL::CComObject<MapsBackgroundTransferClassFactory>::~CComObject<MapsBackgroundTransferClassFactory>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<MapsBackgroundTransferClassFactory>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x180003370  push    rbx
0x180003372  sub     rsp, 20h
0x180003376  mov     dword ptr [rcx+8], 0C0000001h
0x18000337d  lea     rax, ??_7?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@6B@; const ATL::CComObject<MapsBackgroundTransferClassFactory>::`vftable'
0x180003384  mov     [rcx], rax
0x180003387  mov     rbx, rcx
0x18000338a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003391  mov     rax, [rcx]
0x180003394  mov     rax, [rax+10h]
0x180003398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000339d  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800033a4  lea     rcx, [rbx+10h]; this
0x1800033a8  mov     [rbx], rax
0x1800033ab  add     rsp, 20h
0x1800033af  pop     rbx
0x1800033b0  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
