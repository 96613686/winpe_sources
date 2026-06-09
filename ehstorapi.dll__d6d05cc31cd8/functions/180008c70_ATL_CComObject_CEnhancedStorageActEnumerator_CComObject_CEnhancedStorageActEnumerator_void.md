# ATL::CComObject<CEnhancedStorageActEnumerator>::~CComObject<CEnhancedStorageActEnumerator>(void)

- ea: `0x180008c70`
- end: `0x180008caa`
- name: `??1?$CComObject@VCEnhancedStorageActEnumerator@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `__int64 __fastcall(CEnhancedStorageActEnumerator *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008d80`

## callees

- `0x180003f64`
- `0x18000d010`

## pseudocode

```c
void __fastcall ATL::CComObject<CEnhancedStorageActEnumerator>::~CComObject<CEnhancedStorageActEnumerator>(
        CEnhancedStorageActEnumerator *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CEnhancedStorageActEnumerator>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CEnhancedStorageActEnumerator::~CEnhancedStorageActEnumerator(this);
}

```

## disassembly

```asm
0x180008c70  push    rbx
0x180008c72  sub     rsp, 20h
0x180008c76  mov     dword ptr [rcx+8], 0C0000001h
0x180008c7d  lea     rax, ??_7?$CComObject@VCEnhancedStorageActEnumerator@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageActEnumerator>::`vftable'
0x180008c84  mov     [rcx], rax
0x180008c87  mov     rbx, rcx
0x180008c8a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008c91  mov     rax, [rcx]
0x180008c94  mov     rax, [rax+10h]
0x180008c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9d  mov     rcx, rbx; this
0x180008ca0  add     rsp, 20h
0x180008ca4  pop     rbx
0x180008ca5  jmp     ??1CEnhancedStorageActEnumerator@@UEAA@XZ; CEnhancedStorageActEnumerator::~CEnhancedStorageActEnumerator(void)
```
