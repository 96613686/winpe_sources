# ATL::CComObject<CVPNDiagHelper>::`vector deleting destructor'(uint)

- ea: `0x1800082e0`
- end: `0x180008349`
- name: `??_E?$CComObject@VCVPNDiagHelper@@@ATL@@UEAAPEAXI@Z`
- size: `105`
- prototype: `CVPNDiagHelper *__fastcall(CVPNDiagHelper *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180008280`
- `0x1800082e0`
- `0x18000f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000832e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000832e`

## pseudocode

```c
CVPNDiagHelper *__fastcall ATL::CComObject<CVPNDiagHelper>::`vector deleting destructor'(CVPNDiagHelper *this, char a2)
{
  *((_DWORD *)this + 14) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CVPNDiagHelper>::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CVPNDiagHelper>::`vftable'{for `INetDiagHelperInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CVPNDiagHelper::~CVPNDiagHelper(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800082e0  mov     [rsp+arg_0], rbx
0x1800082e5  push    rdi
0x1800082e6  sub     rsp, 20h
0x1800082ea  mov     dword ptr [rcx+38h], 0C0000001h
0x1800082f1  lea     rax, ??_7?$CComObject@VCVPNDiagHelper@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CVPNDiagHelper>::`vftable'{for `INetDiagHelper'}
0x1800082f8  mov     [rcx], rax
0x1800082fb  mov     rdi, rcx
0x1800082fe  lea     rax, ??_7?$CComObject@VCVPNDiagHelper@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CVPNDiagHelper>::`vftable'{for `INetDiagHelperInfo'}
0x180008305  mov     ebx, edx
0x180008307  mov     [rcx+8], rax
0x18000830b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008312  mov     rax, [rcx]
0x180008315  mov     rax, [rax+10h]
0x180008319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000831e  mov     rcx, rdi; this
0x180008321  call    ??1CVPNDiagHelper@@QEAA@XZ; CVPNDiagHelper::~CVPNDiagHelper(void)
0x180008326  test    bl, 1
0x180008329  jz      short loc_18000833A
0x18000832b  mov     rcx, rdi
0x18000832e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008335  nop     dword ptr [rax+rax+00h]
0x18000833a  mov     rbx, [rsp+28h+arg_0]
0x18000833f  mov     rax, rdi
0x180008342  add     rsp, 20h
0x180008346  pop     rdi
0x180008347  retn
```
