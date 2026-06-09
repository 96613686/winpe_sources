# ATL::CComObject<CBindingCallback>::~CComObject<CBindingCallback>(void)

- ea: `0x1800216a0`
- end: `0x1800216cd`
- name: `??1?$CComObject@VCBindingCallback@@@ATL@@QEAA@XZ`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180021844`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x1800216c6`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CBindingCallback>::~CComObject<CBindingCallback>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &ATL::CComObject<CBindingCallback>::`vftable';
  _InterlockedDecrement(&dword_1800464E8);
  *(_QWORD *)a1 = &CBindingCallback::`vftable';
  return MPDeleteCriticalSection(a1 + 16);
}

```

## disassembly

```asm
0x1800216a0  mov     dword ptr [rcx+8], 1
0x1800216a7  lea     rax, ??_7?$CComObject@VCBindingCallback@@@ATL@@6B@; const ATL::CComObject<CBindingCallback>::`vftable'
0x1800216ae  mov     [rcx], rax
0x1800216b1  lea     rax, ??_7CBindingCallback@@6B@; const CBindingCallback::`vftable'
0x1800216b8  lock dec cs:dword_1800464E8
0x1800216bf  mov     [rcx], rax
0x1800216c2  add     rcx, 10h
0x1800216c6  jmp     cs:__imp_MPDeleteCriticalSection
```
