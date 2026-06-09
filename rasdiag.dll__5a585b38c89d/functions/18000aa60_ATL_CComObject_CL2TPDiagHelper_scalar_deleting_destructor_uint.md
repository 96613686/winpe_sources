# ATL::CComObject<CL2TPDiagHelper>::`scalar deleting destructor'(uint)

- ea: `0x18000aa60`
- end: `0x18000aac9`
- name: `??_G?$CComObject@VCL2TPDiagHelper@@@ATL@@UEAAPEAXI@Z`
- size: `105`
- prototype: `CL2TPDiagHelper *__fastcall(CL2TPDiagHelper *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000aa20`
- `0x18000aa60`
- `0x18000f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aaae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aaae`

## pseudocode

```c
CL2TPDiagHelper *__fastcall ATL::CComObject<CL2TPDiagHelper>::`scalar deleting destructor'(
        CL2TPDiagHelper *this,
        char a2)
{
  *((_DWORD *)this + 14) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CL2TPDiagHelper>::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CL2TPDiagHelper>::`vftable'{for `INetDiagHelperInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CL2TPDiagHelper::~CL2TPDiagHelper(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000aa60  mov     [rsp+arg_0], rbx
0x18000aa65  push    rdi
0x18000aa66  sub     rsp, 20h
0x18000aa6a  mov     dword ptr [rcx+38h], 0C0000001h
0x18000aa71  lea     rax, ??_7?$CComObject@VCL2TPDiagHelper@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CL2TPDiagHelper>::`vftable'{for `INetDiagHelper'}
0x18000aa78  mov     [rcx], rax
0x18000aa7b  mov     rdi, rcx
0x18000aa7e  lea     rax, ??_7?$CComObject@VCL2TPDiagHelper@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CL2TPDiagHelper>::`vftable'{for `INetDiagHelperInfo'}
0x18000aa85  mov     ebx, edx
0x18000aa87  mov     [rcx+8], rax
0x18000aa8b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000aa92  mov     rax, [rcx]
0x18000aa95  mov     rax, [rax+10h]
0x18000aa99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa9e  mov     rcx, rdi; this
0x18000aaa1  call    ??1CL2TPDiagHelper@@QEAA@XZ; CL2TPDiagHelper::~CL2TPDiagHelper(void)
0x18000aaa6  test    bl, 1
0x18000aaa9  jz      short loc_18000AABA
0x18000aaab  mov     rcx, rdi
0x18000aaae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000aab5  nop     dword ptr [rax+rax+00h]
0x18000aaba  mov     rbx, [rsp+28h+arg_0]
0x18000aabf  mov     rax, rdi
0x18000aac2  add     rsp, 20h
0x18000aac6  pop     rdi
0x18000aac7  retn
```
