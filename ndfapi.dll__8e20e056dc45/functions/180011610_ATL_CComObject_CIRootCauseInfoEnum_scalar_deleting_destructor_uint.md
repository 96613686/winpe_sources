# ATL::CComObject<CIRootCauseInfoEnum>::`scalar deleting destructor'(uint)

- ea: `0x180011610`
- end: `0x180011667`
- name: `??_G?$CComObject@VCIRootCauseInfoEnum@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CIRootCauseInfoEnum *__fastcall(CIRootCauseInfoEnum *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180011274`
- `0x180011610`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011653`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011653`

## pseudocode

```c
CIRootCauseInfoEnum *__fastcall ATL::CComObject<CIRootCauseInfoEnum>::`scalar deleting destructor'(
        CIRootCauseInfoEnum *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIRootCauseInfoEnum>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIRootCauseInfoEnum::~CIRootCauseInfoEnum(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011610  mov     [rsp+arg_0], rbx
0x180011615  push    rdi
0x180011616  sub     rsp, 20h
0x18001161a  mov     dword ptr [rcx+8], 0C0000001h
0x180011621  lea     rax, ??_7?$CComObject@VCIRootCauseInfoEnum@@@ATL@@6B@; const ATL::CComObject<CIRootCauseInfoEnum>::`vftable'
0x180011628  mov     [rcx], rax
0x18001162b  mov     rdi, rcx
0x18001162e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011635  mov     ebx, edx
0x180011637  mov     rax, [rcx]
0x18001163a  mov     rax, [rax+10h]
0x18001163e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011643  mov     rcx, rdi; this
0x180011646  call    ??1CIRootCauseInfoEnum@@QEAA@XZ; CIRootCauseInfoEnum::~CIRootCauseInfoEnum(void)
0x18001164b  test    bl, 1
0x18001164e  jz      short loc_180011659
0x180011650  mov     rcx, rdi
0x180011653  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011659  mov     rbx, [rsp+28h+arg_0]
0x18001165e  mov     rax, rdi
0x180011661  add     rsp, 20h
0x180011665  pop     rdi
0x180011666  retn
```
