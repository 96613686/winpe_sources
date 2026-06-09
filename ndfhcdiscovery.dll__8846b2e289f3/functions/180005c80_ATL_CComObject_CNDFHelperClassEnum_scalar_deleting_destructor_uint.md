# ATL::CComObject<CNDFHelperClassEnum>::`scalar deleting destructor'(uint)

- ea: `0x180005c80`
- end: `0x180005cde`
- name: `??_G?$CComObject@VCNDFHelperClassEnum@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(CNDFHelperClassEnum *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005c80`
- `0x18000b2bc`
- `0x180015010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005cc3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005cc3`

## pseudocode

```c
CNDFHelperClassEnum *__fastcall ATL::CComObject<CNDFHelperClassEnum>::`scalar deleting destructor'(
        CNDFHelperClassEnum *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CNDFHelperClassEnum>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CNDFHelperClassEnum::~CNDFHelperClassEnum(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005c80  mov     [rsp+arg_0], rbx
0x180005c85  push    rdi
0x180005c86  sub     rsp, 20h
0x180005c8a  mov     dword ptr [rcx+8], 0C0000001h
0x180005c91  lea     rax, ??_7?$CComObject@VCNDFHelperClassEnum@@@ATL@@6B@; const ATL::CComObject<CNDFHelperClassEnum>::`vftable'
0x180005c98  mov     [rcx], rax
0x180005c9b  mov     rdi, rcx
0x180005c9e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005ca5  mov     ebx, edx
0x180005ca7  mov     rax, [rcx]
0x180005caa  mov     rax, [rax+10h]
0x180005cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cb3  mov     rcx, rdi; this
0x180005cb6  call    ??1CNDFHelperClassEnum@@QEAA@XZ; CNDFHelperClassEnum::~CNDFHelperClassEnum(void)
0x180005cbb  test    bl, 1
0x180005cbe  jz      short loc_180005CCF
0x180005cc0  mov     rcx, rdi
0x180005cc3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005cca  nop     dword ptr [rax+rax+00h]
0x180005ccf  mov     rbx, [rsp+28h+arg_0]
0x180005cd4  mov     rax, rdi
0x180005cd7  add     rsp, 20h
0x180005cdb  pop     rdi
0x180005cdc  retn
```
