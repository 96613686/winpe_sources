# ATL::CComObject<CIDiagnosisParameterEnum>::`scalar deleting destructor'(uint)

- ea: `0x180011390`
- end: `0x1800113e7`
- name: `??_G?$CComObject@VCIDiagnosisParameterEnum@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CIDiagnosisParameterEnum *__fastcall(CIDiagnosisParameterEnum *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001105c`
- `0x180011390`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800113d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800113d3`

## pseudocode

```c
CIDiagnosisParameterEnum *__fastcall ATL::CComObject<CIDiagnosisParameterEnum>::`scalar deleting destructor'(
        CIDiagnosisParameterEnum *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIDiagnosisParameterEnum>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIDiagnosisParameterEnum::~CIDiagnosisParameterEnum(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011390  mov     [rsp+arg_0], rbx
0x180011395  push    rdi
0x180011396  sub     rsp, 20h
0x18001139a  mov     dword ptr [rcx+8], 0C0000001h
0x1800113a1  lea     rax, ??_7?$CComObject@VCIDiagnosisParameterEnum@@@ATL@@6B@; const ATL::CComObject<CIDiagnosisParameterEnum>::`vftable'
0x1800113a8  mov     [rcx], rax
0x1800113ab  mov     rdi, rcx
0x1800113ae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800113b5  mov     ebx, edx
0x1800113b7  mov     rax, [rcx]
0x1800113ba  mov     rax, [rax+10h]
0x1800113be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113c3  mov     rcx, rdi; this
0x1800113c6  call    ??1CIDiagnosisParameterEnum@@QEAA@XZ; CIDiagnosisParameterEnum::~CIDiagnosisParameterEnum(void)
0x1800113cb  test    bl, 1
0x1800113ce  jz      short loc_1800113D9
0x1800113d0  mov     rcx, rdi
0x1800113d3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800113d9  mov     rbx, [rsp+28h+arg_0]
0x1800113de  mov     rax, rdi
0x1800113e1  add     rsp, 20h
0x1800113e5  pop     rdi
0x1800113e6  retn
```
