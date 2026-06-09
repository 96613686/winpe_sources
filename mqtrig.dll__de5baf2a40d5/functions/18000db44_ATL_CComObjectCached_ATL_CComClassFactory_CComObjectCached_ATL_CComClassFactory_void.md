# ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)

- ea: `0x18000db44`
- end: `0x18000db75`
- name: `??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dce4`

## callees

- `0x1800055fc`

## pseudocode

```c
void __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(a1 + 72));
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x18000db44  push    rbx
0x18000db46  sub     rsp, 20h
0x18000db4a  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000db51  mov     dword ptr [rcx+8], 1
0x18000db58  mov     [rcx], rax
0x18000db5b  mov     rbx, rcx
0x18000db5e  add     rcx, 48h ; 'H'; this
0x18000db62  call    ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
0x18000db67  lea     rcx, [rbx+10h]; this
0x18000db6b  add     rsp, 20h
0x18000db6f  pop     rbx
0x18000db70  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
