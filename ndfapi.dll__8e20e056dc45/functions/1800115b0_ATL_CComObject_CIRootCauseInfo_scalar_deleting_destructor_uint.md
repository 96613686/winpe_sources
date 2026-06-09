# ATL::CComObject<CIRootCauseInfo>::`scalar deleting destructor'(uint)

- ea: `0x1800115b0`
- end: `0x180011607`
- name: `??_G?$CComObject@VCIRootCauseInfo@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CIRootCauseInfo *__fastcall(CIRootCauseInfo *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180011220`
- `0x1800115b0`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800115f3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800115f3`

## pseudocode

```c
CIRootCauseInfo *__fastcall ATL::CComObject<CIRootCauseInfo>::`scalar deleting destructor'(
        CIRootCauseInfo *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIRootCauseInfo>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIRootCauseInfo::~CIRootCauseInfo(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800115b0  mov     [rsp+arg_0], rbx
0x1800115b5  push    rdi
0x1800115b6  sub     rsp, 20h
0x1800115ba  mov     dword ptr [rcx+8], 0C0000001h
0x1800115c1  lea     rax, ??_7?$CComObject@VCIRootCauseInfo@@@ATL@@6B@; const ATL::CComObject<CIRootCauseInfo>::`vftable'
0x1800115c8  mov     [rcx], rax
0x1800115cb  mov     rdi, rcx
0x1800115ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800115d5  mov     ebx, edx
0x1800115d7  mov     rax, [rcx]
0x1800115da  mov     rax, [rax+10h]
0x1800115de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115e3  mov     rcx, rdi; this
0x1800115e6  call    ??1CIRootCauseInfo@@QEAA@XZ; CIRootCauseInfo::~CIRootCauseInfo(void)
0x1800115eb  test    bl, 1
0x1800115ee  jz      short loc_1800115F9
0x1800115f0  mov     rcx, rdi
0x1800115f3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800115f9  mov     rbx, [rsp+28h+arg_0]
0x1800115fe  mov     rax, rdi
0x180011601  add     rsp, 20h
0x180011605  pop     rdi
0x180011606  retn
```
