# ATL::CComObject<CIRepairInfo>::`scalar deleting destructor'(uint)

- ea: `0x180011490`
- end: `0x1800114e7`
- name: `??_G?$CComObject@VCIRepairInfo@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CIRepairInfo *__fastcall(CIRepairInfo *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180011134`
- `0x180011490`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800114d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800114d3`

## pseudocode

```c
CIRepairInfo *__fastcall ATL::CComObject<CIRepairInfo>::`scalar deleting destructor'(CIRepairInfo *this, char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIRepairInfo>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIRepairInfo::~CIRepairInfo(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180011490  mov     [rsp+arg_0], rbx
0x180011495  push    rdi
0x180011496  sub     rsp, 20h
0x18001149a  mov     dword ptr [rcx+8], 0C0000001h
0x1800114a1  lea     rax, ??_7?$CComObject@VCIRepairInfo@@@ATL@@6B@; const ATL::CComObject<CIRepairInfo>::`vftable'
0x1800114a8  mov     [rcx], rax
0x1800114ab  mov     rdi, rcx
0x1800114ae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800114b5  mov     ebx, edx
0x1800114b7  mov     rax, [rcx]
0x1800114ba  mov     rax, [rax+10h]
0x1800114be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114c3  mov     rcx, rdi; this
0x1800114c6  call    ??1CIRepairInfo@@QEAA@XZ; CIRepairInfo::~CIRepairInfo(void)
0x1800114cb  test    bl, 1
0x1800114ce  jz      short loc_1800114D9
0x1800114d0  mov     rcx, rdi
0x1800114d3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800114d9  mov     rbx, [rsp+28h+arg_0]
0x1800114de  mov     rax, rdi
0x1800114e1  add     rsp, 20h
0x1800114e5  pop     rdi
0x1800114e6  retn
```
