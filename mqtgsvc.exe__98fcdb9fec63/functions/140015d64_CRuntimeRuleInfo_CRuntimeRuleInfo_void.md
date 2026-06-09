# CRuntimeRuleInfo::~CRuntimeRuleInfo(void)

- ea: `0x140015d64`
- end: `0x140015dc1`
- name: `??1CRuntimeRuleInfo@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(CRuntimeRuleInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ae88`

## callees

- `0x140003868`
- `0x140004eb4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140015d74`
- `KERNEL32!DeleteCriticalSection` at `0x140015d74`

## pseudocode

```c
void __fastcall CRuntimeRuleInfo::~CRuntimeRuleInfo(CRuntimeRuleInfo *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1088));
  R<IObjectContext>::~R<IObjectContext>((__int64 *)this + 135);
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
0x140015d64  push    rbx
0x140015d66  sub     rsp, 20h
0x140015d6a  mov     rbx, rcx
0x140015d6d  add     rcx, 440h; lpCriticalSection
0x140015d74  call    cs:__imp_DeleteCriticalSection
0x140015d7a  nop
0x140015d7b  lea     rcx, [rbx+438h]
0x140015d82  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x140015d87  lea     rcx, [rbx+28h]; this
0x140015d8b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140015d90  lea     rcx, [rbx+20h]; this
0x140015d94  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140015d99  lea     rcx, [rbx+18h]; this
0x140015d9d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140015da2  lea     rcx, [rbx+10h]; this
0x140015da6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140015dab  lea     rcx, [rbx+8]; this
0x140015daf  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140015db4  mov     rcx, rbx; this
0x140015db7  add     rsp, 20h
0x140015dbb  pop     rbx
0x140015dbc  jmp     ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
```
