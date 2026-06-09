# ATL::CComObject<CIDiagnosisParameter>::`vector deleting destructor'(uint)

- ea: `0x180011330`
- end: `0x180011387`
- name: `??_E?$CComObject@VCIDiagnosisParameter@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CIDiagnosisParameter *__fastcall(CIDiagnosisParameter *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180010fe0`
- `0x180011330`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011373`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011373`

## pseudocode

```c
CIDiagnosisParameter *__fastcall ATL::CComObject<CIDiagnosisParameter>::`vector deleting destructor'(
        CIDiagnosisParameter *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIDiagnosisParameter>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIDiagnosisParameter::~CIDiagnosisParameter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011330  mov     [rsp+arg_0], rbx
0x180011335  push    rdi
0x180011336  sub     rsp, 20h
0x18001133a  mov     dword ptr [rcx+8], 0C0000001h
0x180011341  lea     rax, ??_7?$CComObject@VCIDiagnosisParameter@@@ATL@@6B@; const ATL::CComObject<CIDiagnosisParameter>::`vftable'
0x180011348  mov     [rcx], rax
0x18001134b  mov     rdi, rcx
0x18001134e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011355  mov     ebx, edx
0x180011357  mov     rax, [rcx]
0x18001135a  mov     rax, [rax+10h]
0x18001135e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011363  mov     rcx, rdi; this
0x180011366  call    ??1CIDiagnosisParameter@@QEAA@XZ; CIDiagnosisParameter::~CIDiagnosisParameter(void)
0x18001136b  test    bl, 1
0x18001136e  jz      short loc_180011379
0x180011370  mov     rcx, rdi
0x180011373  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011379  mov     rbx, [rsp+28h+arg_0]
0x18001137e  mov     rax, rdi
0x180011381  add     rsp, 20h
0x180011385  pop     rdi
0x180011386  retn
```
