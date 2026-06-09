# ATL::CComObject<CIRepairUiInfo>::`scalar deleting destructor'(uint)

- ea: `0x180011550`
- end: `0x1800115a7`
- name: `??_G?$CComObject@VCIRepairUiInfo@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CIRepairUiInfo *__fastcall(CIRepairUiInfo *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1800111d4`
- `0x180011550`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011593`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011593`

## pseudocode

```c
CIRepairUiInfo *__fastcall ATL::CComObject<CIRepairUiInfo>::`scalar deleting destructor'(CIRepairUiInfo *this, char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIRepairUiInfo>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIRepairUiInfo::~CIRepairUiInfo(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011550  mov     [rsp+arg_0], rbx
0x180011555  push    rdi
0x180011556  sub     rsp, 20h
0x18001155a  mov     dword ptr [rcx+8], 0C0000001h
0x180011561  lea     rax, ??_7?$CComObject@VCIRepairUiInfo@@@ATL@@6B@; const ATL::CComObject<CIRepairUiInfo>::`vftable'
0x180011568  mov     [rcx], rax
0x18001156b  mov     rdi, rcx
0x18001156e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011575  mov     ebx, edx
0x180011577  mov     rax, [rcx]
0x18001157a  mov     rax, [rax+10h]
0x18001157e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011583  mov     rcx, rdi; this
0x180011586  call    ??1CIRepairUiInfo@@QEAA@XZ; CIRepairUiInfo::~CIRepairUiInfo(void)
0x18001158b  test    bl, 1
0x18001158e  jz      short loc_180011599
0x180011590  mov     rcx, rdi
0x180011593  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011599  mov     rbx, [rsp+28h+arg_0]
0x18001159e  mov     rax, rdi
0x1800115a1  add     rsp, 20h
0x1800115a5  pop     rdi
0x1800115a6  retn
```
