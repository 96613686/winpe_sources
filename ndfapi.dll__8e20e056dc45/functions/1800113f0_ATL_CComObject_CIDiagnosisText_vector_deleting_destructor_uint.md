# ATL::CComObject<CIDiagnosisText>::`vector deleting destructor'(uint)

- ea: `0x1800113f0`
- end: `0x180011447`
- name: `??_E?$CComObject@VCIDiagnosisText@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CIDiagnosisText *__fastcall(CIDiagnosisText *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800110d4`
- `0x1800113f0`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011433`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011433`

## pseudocode

```c
CIDiagnosisText *__fastcall ATL::CComObject<CIDiagnosisText>::`vector deleting destructor'(
        CIDiagnosisText *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIDiagnosisText>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIDiagnosisText::~CIDiagnosisText(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800113f0  mov     [rsp+arg_0], rbx
0x1800113f5  push    rdi
0x1800113f6  sub     rsp, 20h
0x1800113fa  mov     dword ptr [rcx+8], 0C0000001h
0x180011401  lea     rax, ??_7?$CComObject@VCIDiagnosisText@@@ATL@@6B@; const ATL::CComObject<CIDiagnosisText>::`vftable'
0x180011408  mov     [rcx], rax
0x18001140b  mov     rdi, rcx
0x18001140e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011415  mov     ebx, edx
0x180011417  mov     rax, [rcx]
0x18001141a  mov     rax, [rax+10h]
0x18001141e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011423  mov     rcx, rdi; this
0x180011426  call    ??1CIDiagnosisText@@QEAA@XZ; CIDiagnosisText::~CIDiagnosisText(void)
0x18001142b  test    bl, 1
0x18001142e  jz      short loc_180011439
0x180011430  mov     rcx, rdi
0x180011433  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011439  mov     rbx, [rsp+28h+arg_0]
0x18001143e  mov     rax, rdi
0x180011441  add     rsp, 20h
0x180011445  pop     rdi
0x180011446  retn
```
