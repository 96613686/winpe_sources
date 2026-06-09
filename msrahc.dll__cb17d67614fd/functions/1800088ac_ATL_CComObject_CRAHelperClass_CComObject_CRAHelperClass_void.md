# ATL::CComObject<CRAHelperClass>::~CComObject<CRAHelperClass>(void)

- ea: `0x1800088ac`
- end: `0x1800088fc`
- name: `??1?$CComObject@VCRAHelperClass@@@ATL@@UEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CRAHelperClass *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008a70`

## callees

- `0x18000c920`
- `0x18001c010`

## pseudocode

```c
void __fastcall ATL::CComObject<CRAHelperClass>::~CComObject<CRAHelperClass>(CRAHelperClass *this)
{
  *((_DWORD *)this + 16) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CRAHelperClass>::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CRAHelperClass>::`vftable'{for `INetDiagHelperInfo'};
  *((_QWORD *)this + 7) = &ATL::CComObject<CRAHelperClass>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CRAHelperClass::~CRAHelperClass(this);
}

```

## disassembly

```asm
0x1800088ac  push    rbx
0x1800088ae  sub     rsp, 20h
0x1800088b2  mov     dword ptr [rcx+40h], 0C0000001h
0x1800088b9  lea     rax, ??_7?$CComObject@VCRAHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CRAHelperClass>::`vftable'{for `INetDiagHelper'}
0x1800088c0  mov     [rcx], rax
0x1800088c3  mov     rbx, rcx
0x1800088c6  lea     rax, ??_7?$CComObject@VCRAHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CRAHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x1800088cd  mov     [rcx+8], rax
0x1800088d1  lea     rax, ??_7?$CComObject@VCRAHelperClass@@@ATL@@6B@; const ATL::CComObject<CRAHelperClass>::`vftable'
0x1800088d8  mov     [rcx+38h], rax
0x1800088dc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800088e3  mov     rax, [rcx]
0x1800088e6  mov     rax, [rax+10h]
0x1800088ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ef  mov     rcx, rbx; this
0x1800088f2  add     rsp, 20h
0x1800088f6  pop     rbx
0x1800088f7  jmp     ??1CRAHelperClass@@QEAA@XZ; CRAHelperClass::~CRAHelperClass(void)
```
