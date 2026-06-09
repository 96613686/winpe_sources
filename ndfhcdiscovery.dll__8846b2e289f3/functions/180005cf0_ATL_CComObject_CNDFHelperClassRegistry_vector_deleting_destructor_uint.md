# ATL::CComObject<CNDFHelperClassRegistry>::`vector deleting destructor'(uint)

- ea: `0x180005cf0`
- end: `0x180005d4e`
- name: `??_E?$CComObject@VCNDFHelperClassRegistry@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(CNDFHelperClassRegistry *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180005790`
- `0x180005cf0`
- `0x180015010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005d33`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005d33`

## pseudocode

```c
CNDFHelperClassRegistry *__fastcall ATL::CComObject<CNDFHelperClassRegistry>::`vector deleting destructor'(
        CNDFHelperClassRegistry *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CNDFHelperClassRegistry>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CNDFHelperClassRegistry::~CNDFHelperClassRegistry(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180005cf0  mov     [rsp+arg_0], rbx
0x180005cf5  push    rdi
0x180005cf6  sub     rsp, 20h
0x180005cfa  mov     dword ptr [rcx+8], 0C0000001h
0x180005d01  lea     rax, ??_7?$CComObject@VCNDFHelperClassRegistry@@@ATL@@6B@; const ATL::CComObject<CNDFHelperClassRegistry>::`vftable'
0x180005d08  mov     [rcx], rax
0x180005d0b  mov     rdi, rcx
0x180005d0e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005d15  mov     ebx, edx
0x180005d17  mov     rax, [rcx]
0x180005d1a  mov     rax, [rax+10h]
0x180005d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d23  mov     rcx, rdi; this
0x180005d26  call    ??1CNDFHelperClassRegistry@@QEAA@XZ; CNDFHelperClassRegistry::~CNDFHelperClassRegistry(void)
0x180005d2b  test    bl, 1
0x180005d2e  jz      short loc_180005D3F
0x180005d30  mov     rcx, rdi
0x180005d33  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005d3a  nop     dword ptr [rax+rax+00h]
0x180005d3f  mov     rbx, [rsp+28h+arg_0]
0x180005d44  mov     rax, rdi
0x180005d47  add     rsp, 20h
0x180005d4b  pop     rdi
0x180005d4c  retn
```
