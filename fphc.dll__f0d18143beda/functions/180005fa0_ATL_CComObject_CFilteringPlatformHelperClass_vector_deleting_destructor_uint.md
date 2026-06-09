# ATL::CComObject<CFilteringPlatformHelperClass>::`vector deleting destructor'(uint)

- ea: `0x180005fa0`
- end: `0x18000600d`
- name: `??_E?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@UEAAPEAXI@Z`
- size: `109`
- prototype: `__int64 __fastcall(CFilteringPlatformHelperClass *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005e60`
- `0x180005fa0`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005ff9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005ff9`

## pseudocode

```c
CFilteringPlatformHelperClass *__fastcall ATL::CComObject<CFilteringPlatformHelperClass>::`vector deleting destructor'(
        CFilteringPlatformHelperClass *this,
        char a2)
{
  *((_DWORD *)this + 16) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'{for `INetDiagHelperInfo'};
  *((_QWORD *)this + 7) = &ATL::CComObject<CFilteringPlatformHelperClass>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CFilteringPlatformHelperClass::~CFilteringPlatformHelperClass(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005fa0  mov     [rsp+arg_0], rbx
0x180005fa5  push    rdi
0x180005fa6  sub     rsp, 20h
0x180005faa  mov     dword ptr [rcx+40h], 0C0000001h
0x180005fb1  lea     rax, ??_7?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'{for `INetDiagHelper'}
0x180005fb8  mov     [rcx], rax
0x180005fbb  mov     rdi, rcx
0x180005fbe  lea     rax, ??_7?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x180005fc5  mov     ebx, edx
0x180005fc7  mov     [rcx+8], rax
0x180005fcb  lea     rax, ??_7?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@6B@; const ATL::CComObject<CFilteringPlatformHelperClass>::`vftable'
0x180005fd2  mov     [rcx+38h], rax
0x180005fd6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005fdd  mov     rax, [rcx]
0x180005fe0  mov     rax, [rax+10h]
0x180005fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fe9  mov     rcx, rdi; this
0x180005fec  call    ??1CFilteringPlatformHelperClass@@QEAA@XZ; CFilteringPlatformHelperClass::~CFilteringPlatformHelperClass(void)
0x180005ff1  test    bl, 1
0x180005ff4  jz      short loc_180005FFF
0x180005ff6  mov     rcx, rdi
0x180005ff9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005fff  mov     rbx, [rsp+28h+arg_0]
0x180006004  mov     rax, rdi
0x180006007  add     rsp, 20h
0x18000600b  pop     rdi
0x18000600c  retn
```
