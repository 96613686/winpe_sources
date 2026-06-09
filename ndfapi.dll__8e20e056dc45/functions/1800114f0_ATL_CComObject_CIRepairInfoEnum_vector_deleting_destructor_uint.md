# ATL::CComObject<CIRepairInfoEnum>::`vector deleting destructor'(uint)

- ea: `0x1800114f0`
- end: `0x180011547`
- name: `??_E?$CComObject@VCIRepairInfoEnum@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CIRepairInfoEnum *__fastcall(CIRepairInfoEnum *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180011188`
- `0x1800114f0`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011533`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011533`

## pseudocode

```c
CIRepairInfoEnum *__fastcall ATL::CComObject<CIRepairInfoEnum>::`vector deleting destructor'(
        CIRepairInfoEnum *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIRepairInfoEnum>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIRepairInfoEnum::~CIRepairInfoEnum(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800114f0  mov     [rsp+arg_0], rbx
0x1800114f5  push    rdi
0x1800114f6  sub     rsp, 20h
0x1800114fa  mov     dword ptr [rcx+8], 0C0000001h
0x180011501  lea     rax, ??_7?$CComObject@VCIRepairInfoEnum@@@ATL@@6B@; const ATL::CComObject<CIRepairInfoEnum>::`vftable'
0x180011508  mov     [rcx], rax
0x18001150b  mov     rdi, rcx
0x18001150e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011515  mov     ebx, edx
0x180011517  mov     rax, [rcx]
0x18001151a  mov     rax, [rax+10h]
0x18001151e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011523  mov     rcx, rdi; this
0x180011526  call    ??1CIRepairInfoEnum@@QEAA@XZ; CIRepairInfoEnum::~CIRepairInfoEnum(void)
0x18001152b  test    bl, 1
0x18001152e  jz      short loc_180011539
0x180011530  mov     rcx, rdi
0x180011533  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011539  mov     rbx, [rsp+28h+arg_0]
0x18001153e  mov     rax, rdi
0x180011541  add     rsp, 20h
0x180011545  pop     rdi
0x180011546  retn
```
