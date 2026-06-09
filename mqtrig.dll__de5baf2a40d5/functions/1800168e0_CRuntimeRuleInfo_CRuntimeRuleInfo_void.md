# CRuntimeRuleInfo::~CRuntimeRuleInfo(void)

- ea: `0x1800168e0`
- end: `0x18001693d`
- name: `??1CRuntimeRuleInfo@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(CRuntimeRuleInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a2d8`

## callees

- `0x1800030d8`
- `0x180009ab0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800168f0`
- `KERNEL32!DeleteCriticalSection` at `0x1800168f0`

## pseudocode

```c
void __fastcall CRuntimeRuleInfo::~CRuntimeRuleInfo(CRuntimeRuleInfo *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1088));
  ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>((__int64 *)this + 135);
  _bstr_t::_Free((CRuntimeRuleInfo *)((char *)this + 40));
  _bstr_t::_Free((CRuntimeRuleInfo *)((char *)this + 32));
  _bstr_t::_Free((CRuntimeRuleInfo *)((char *)this + 24));
  _bstr_t::_Free((CRuntimeRuleInfo *)((char *)this + 16));
  _bstr_t::_Free((CRuntimeRuleInfo *)((char *)this + 8));
  _bstr_t::_Free(this);
}

```

## disassembly

```asm
0x1800168e0  push    rbx
0x1800168e2  sub     rsp, 20h
0x1800168e6  mov     rbx, rcx
0x1800168e9  add     rcx, 440h; lpCriticalSection
0x1800168f0  call    cs:__imp_DeleteCriticalSection
0x1800168f6  nop
0x1800168f7  lea     rcx, [rbx+438h]
0x1800168fe  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x180016903  lea     rcx, [rbx+28h]; this
0x180016907  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001690c  lea     rcx, [rbx+20h]; this
0x180016910  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180016915  lea     rcx, [rbx+18h]; this
0x180016919  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001691e  lea     rcx, [rbx+10h]; this
0x180016922  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180016927  lea     rcx, [rbx+8]; this
0x18001692b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180016930  mov     rcx, rbx; this
0x180016933  add     rsp, 20h
0x180016937  pop     rbx
0x180016938  jmp     ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
```
