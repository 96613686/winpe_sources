# ATL::CComObject<CEnhancedStorageSilo>::~CComObject<CEnhancedStorageSilo>(void)

- ea: `0x1800020e8`
- end: `0x180002122`
- name: `??1?$CComObject@VCEnhancedStorageSilo@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(CEnhancedStorageSilo *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800021c0`

## callees

- `0x180006400`
- `0x18000d010`

## pseudocode

```c
void __fastcall ATL::CComObject<CEnhancedStorageSilo>::~CComObject<CEnhancedStorageSilo>(CEnhancedStorageSilo *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CEnhancedStorageSilo>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CEnhancedStorageSilo::~CEnhancedStorageSilo(this);
}

```

## disassembly

```asm
0x1800020e8  push    rbx
0x1800020ea  sub     rsp, 20h
0x1800020ee  mov     dword ptr [rcx+8], 0C0000001h
0x1800020f5  lea     rax, ??_7?$CComObject@VCEnhancedStorageSilo@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageSilo>::`vftable'
0x1800020fc  mov     [rcx], rax
0x1800020ff  mov     rbx, rcx
0x180002102  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002109  mov     rax, [rcx]
0x18000210c  mov     rax, [rax+10h]
0x180002110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002115  mov     rcx, rbx; this
0x180002118  add     rsp, 20h
0x18000211c  pop     rbx
0x18000211d  jmp     ??1CEnhancedStorageSilo@@UEAA@XZ; CEnhancedStorageSilo::~CEnhancedStorageSilo(void)
```
