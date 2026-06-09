# ATL::CComObject<CPPTPDiagHelper>::`scalar deleting destructor'(uint)

- ea: `0x180009ad0`
- end: `0x180009b39`
- name: `??_G?$CComObject@VCPPTPDiagHelper@@@ATL@@UEAAPEAXI@Z`
- size: `105`
- prototype: `CPPTPDiagHelper *__fastcall(CPPTPDiagHelper *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009a6c`
- `0x180009ad0`
- `0x18000f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009b1e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009b1e`

## pseudocode

```c
CPPTPDiagHelper *__fastcall ATL::CComObject<CPPTPDiagHelper>::`scalar deleting destructor'(
        CPPTPDiagHelper *this,
        char a2)
{
  *((_DWORD *)this + 14) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CPPTPDiagHelper>::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CPPTPDiagHelper>::`vftable'{for `INetDiagHelperInfo'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CPPTPDiagHelper::~CPPTPDiagHelper(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009ad0  mov     [rsp+arg_0], rbx
0x180009ad5  push    rdi
0x180009ad6  sub     rsp, 20h
0x180009ada  mov     dword ptr [rcx+38h], 0C0000001h
0x180009ae1  lea     rax, ??_7?$CComObject@VCPPTPDiagHelper@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CPPTPDiagHelper>::`vftable'{for `INetDiagHelper'}
0x180009ae8  mov     [rcx], rax
0x180009aeb  mov     rdi, rcx
0x180009aee  lea     rax, ??_7?$CComObject@VCPPTPDiagHelper@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CPPTPDiagHelper>::`vftable'{for `INetDiagHelperInfo'}
0x180009af5  mov     ebx, edx
0x180009af7  mov     [rcx+8], rax
0x180009afb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009b02  mov     rax, [rcx]
0x180009b05  mov     rax, [rax+10h]
0x180009b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b0e  mov     rcx, rdi; this
0x180009b11  call    ??1CPPTPDiagHelper@@QEAA@XZ; CPPTPDiagHelper::~CPPTPDiagHelper(void)
0x180009b16  test    bl, 1
0x180009b19  jz      short loc_180009B2A
0x180009b1b  mov     rcx, rdi
0x180009b1e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009b25  nop     dword ptr [rax+rax+00h]
0x180009b2a  mov     rbx, [rsp+28h+arg_0]
0x180009b2f  mov     rax, rdi
0x180009b32  add     rsp, 20h
0x180009b36  pop     rdi
0x180009b37  retn
```
