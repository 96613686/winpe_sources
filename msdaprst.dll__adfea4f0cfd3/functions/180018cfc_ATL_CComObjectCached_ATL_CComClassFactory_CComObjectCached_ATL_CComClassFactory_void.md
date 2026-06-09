# ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)

- ea: `0x180018cfc`
- end: `0x180018d18`
- name: `??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018ed8`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x180018d11`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  return MPDeleteCriticalSection(a1 + 16);
}

```

## disassembly

```asm
0x180018cfc  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180018d03  mov     dword ptr [rcx+8], 1
0x180018d0a  mov     [rcx], rax
0x180018d0d  add     rcx, 10h
0x180018d11  jmp     cs:__imp_MPDeleteCriticalSection
```
