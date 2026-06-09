# ATL::CComObject<CEnhancedStorageAct>::~CComObject<CEnhancedStorageAct>(void)

- ea: `0x180003e88`
- end: `0x180003ec7`
- name: `??1?$CComObject@VCEnhancedStorageAct@@@ATL@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(CEnhancedStorageAct *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004030`

## callees

- `0x18000215c`
- `0x1800025dc`
- `0x18000d010`

## pseudocode

```c
void __fastcall ATL::CComObject<CEnhancedStorageAct>::~CComObject<CEnhancedStorageAct>(CEnhancedStorageAct *this)
{
  *(_QWORD *)this = &ATL::CComObject<CEnhancedStorageAct>::`vftable';
  *((_DWORD *)this + 2) = -1073741823;
  CEnhancedStorageAct::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CEnhancedStorageAct::~CEnhancedStorageAct(this);
}

```

## disassembly

```asm
0x180003e88  push    rbx
0x180003e8a  sub     rsp, 20h
0x180003e8e  mov     rbx, rcx
0x180003e91  lea     rax, ??_7?$CComObject@VCEnhancedStorageAct@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageAct>::`vftable'
0x180003e98  mov     [rcx], rax
0x180003e9b  mov     dword ptr [rcx+8], 0C0000001h
0x180003ea2  call    ?FinalRelease@CEnhancedStorageAct@@QEAAXXZ; CEnhancedStorageAct::FinalRelease(void)
0x180003ea7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003eae  mov     rax, [rcx]
0x180003eb1  mov     rax, [rax+10h]
0x180003eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eba  mov     rcx, rbx; this
0x180003ebd  add     rsp, 20h
0x180003ec1  pop     rbx
0x180003ec2  jmp     ??1CEnhancedStorageAct@@UEAA@XZ; CEnhancedStorageAct::~CEnhancedStorageAct(void)
```
