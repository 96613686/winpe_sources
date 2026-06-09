# ATL::CComObject<CRasDiagHelper>::`vector deleting destructor'(uint)

- ea: `0x180006170`
- end: `0x1800061d9`
- name: `??_E?$CComObject@VCRasDiagHelper@@@ATL@@UEAAPEAXI@Z`
- size: `105`
- prototype: `CRasDiagHelper *__fastcall(CRasDiagHelper *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800060b0`
- `0x180006170`
- `0x18000f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800061be`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800061be`

## pseudocode

```c
CRasDiagHelper *__fastcall ATL::CComObject<CRasDiagHelper>::`vector deleting destructor'(CRasDiagHelper *this, char a2)
{
  *((_DWORD *)this + 14) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CRasDiagHelper>::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CRasDiagHelper>::`vftable'{for `INetDiagHelperInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CRasDiagHelper::~CRasDiagHelper(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006170  mov     [rsp+arg_0], rbx
0x180006175  push    rdi
0x180006176  sub     rsp, 20h
0x18000617a  mov     dword ptr [rcx+38h], 0C0000001h
0x180006181  lea     rax, ??_7?$CComObject@VCRasDiagHelper@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CRasDiagHelper>::`vftable'{for `INetDiagHelper'}
0x180006188  mov     [rcx], rax
0x18000618b  mov     rdi, rcx
0x18000618e  lea     rax, ??_7?$CComObject@VCRasDiagHelper@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CRasDiagHelper>::`vftable'{for `INetDiagHelperInfo'}
0x180006195  mov     ebx, edx
0x180006197  mov     [rcx+8], rax
0x18000619b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800061a2  mov     rax, [rcx]
0x1800061a5  mov     rax, [rax+10h]
0x1800061a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ae  mov     rcx, rdi; this
0x1800061b1  call    ??1CRasDiagHelper@@QEAA@XZ; CRasDiagHelper::~CRasDiagHelper(void)
0x1800061b6  test    bl, 1
0x1800061b9  jz      short loc_1800061CA
0x1800061bb  mov     rcx, rdi
0x1800061be  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800061c5  nop     dword ptr [rax+rax+00h]
0x1800061ca  mov     rbx, [rsp+28h+arg_0]
0x1800061cf  mov     rax, rdi
0x1800061d2  add     rsp, 20h
0x1800061d6  pop     rdi
0x1800061d7  retn
```
