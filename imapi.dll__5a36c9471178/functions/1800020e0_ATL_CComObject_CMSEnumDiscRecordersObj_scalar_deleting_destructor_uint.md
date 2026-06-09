# ATL::CComObject<CMSEnumDiscRecordersObj>::`scalar deleting destructor'(uint)

- ea: `0x1800020e0`
- end: `0x180002136`
- name: `??_G?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@UEAAPEAXI@Z`
- size: `86`
- prototype: `__int64 __fastcall(CMSEnumDiscRecordersObj *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001144`
- `0x1800020e0`
- `0x18000aa40`
- `0x180019010`

## pseudocode

```c
CMSEnumDiscRecordersObj *__fastcall ATL::CComObject<CMSEnumDiscRecordersObj>::`scalar deleting destructor'(
        CMSEnumDiscRecordersObj *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CMSEnumDiscRecordersObj>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CMSEnumDiscRecordersObj::~CMSEnumDiscRecordersObj(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800020e0  mov     [rsp+arg_0], rbx
0x1800020e5  push    rdi
0x1800020e6  sub     rsp, 20h
0x1800020ea  mov     dword ptr [rcx+8], 0C0000001h
0x1800020f1  lea     rax, ??_7?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@6B@; const ATL::CComObject<CMSEnumDiscRecordersObj>::`vftable'
0x1800020f8  mov     [rcx], rax
0x1800020fb  mov     rdi, rcx
0x1800020fe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002105  mov     ebx, edx
0x180002107  mov     rax, [rcx]
0x18000210a  mov     rax, [rax+10h]
0x18000210e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002113  mov     rcx, rdi; this
0x180002116  call    ??1CMSEnumDiscRecordersObj@@QEAA@XZ; CMSEnumDiscRecordersObj::~CMSEnumDiscRecordersObj(void)
0x18000211b  test    bl, 1
0x18000211e  jz      short loc_180002128
0x180002120  mov     rcx, rdi; Block
0x180002123  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002128  mov     rbx, [rsp+28h+arg_0]
0x18000212d  mov     rax, rdi
0x180002130  add     rsp, 20h
0x180002134  pop     rdi
0x180002135  retn
```
