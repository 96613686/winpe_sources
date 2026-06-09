# ATL::CComObject<CEnhancedStorageSiloAction>::~CComObject<CEnhancedStorageSiloAction>(void)

- ea: `0x18000637c`
- end: `0x1800063d3`
- name: `??1?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@UEAA@XZ`
- size: `87`
- prototype: `__int64 __fastcall(CEnhancedStorageSiloAction *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800064f0`

## callees

- `0x18000637c`
- `0x18000649c`
- `0x18000d010`

## pseudocode

```c
void __fastcall ATL::CComObject<CEnhancedStorageSiloAction>::~CComObject<CEnhancedStorageSiloAction>(
        CEnhancedStorageSiloAction *this)
{
  __int64 v2; // rcx

  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CEnhancedStorageSiloAction>::`vftable';
  v2 = *((_QWORD *)this + 12);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 12) = 0;
  }
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CEnhancedStorageSiloAction::~CEnhancedStorageSiloAction(this);
}

```

## disassembly

```asm
0x18000637c  push    rbx
0x18000637e  sub     rsp, 20h
0x180006382  lea     rax, ??_7?$CComObject@VCEnhancedStorageSiloAction@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageSiloAction>::`vftable'
0x180006389  mov     dword ptr [rcx+8], 0C0000001h
0x180006390  mov     [rcx], rax
0x180006393  mov     rbx, rcx
0x180006396  mov     rcx, [rcx+60h]
0x18000639a  test    rcx, rcx
0x18000639d  jz      short loc_1800063B3
0x18000639f  mov     rax, [rcx]
0x1800063a2  mov     rax, [rax+10h]
0x1800063a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ab  mov     qword ptr [rbx+60h], 0
0x1800063b3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800063ba  mov     rax, [rcx]
0x1800063bd  mov     rax, [rax+10h]
0x1800063c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c6  mov     rcx, rbx; this
0x1800063c9  add     rsp, 20h
0x1800063cd  pop     rbx
0x1800063ce  jmp     ??1CEnhancedStorageSiloAction@@QEAA@XZ; CEnhancedStorageSiloAction::~CEnhancedStorageSiloAction(void)
```
