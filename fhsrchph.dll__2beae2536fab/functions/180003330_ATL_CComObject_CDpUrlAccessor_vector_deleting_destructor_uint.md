# ATL::CComObject<CDpUrlAccessor>::`vector deleting destructor'(uint)

- ea: `0x180003330`
- end: `0x180003387`
- name: `??_E?$CComObject@VCDpUrlAccessor@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `CDpUrlAccessor *__fastcall(CDpUrlAccessor *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003034`
- `0x180003330`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003373`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003373`

## pseudocode

```c
CDpUrlAccessor *__fastcall ATL::CComObject<CDpUrlAccessor>::`vector deleting destructor'(CDpUrlAccessor *this, char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CDpUrlAccessor>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CDpUrlAccessor::~CDpUrlAccessor(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003330  mov     [rsp+arg_0], rbx
0x180003335  push    rdi
0x180003336  sub     rsp, 20h
0x18000333a  mov     dword ptr [rcx+8], 0C0000001h
0x180003341  lea     rax, ??_7?$CComObject@VCDpUrlAccessor@@@ATL@@6B@; const ATL::CComObject<CDpUrlAccessor>::`vftable'
0x180003348  mov     [rcx], rax
0x18000334b  mov     rdi, rcx
0x18000334e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003355  mov     ebx, edx
0x180003357  mov     rax, [rcx]
0x18000335a  mov     rax, [rax+10h]
0x18000335e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003363  mov     rcx, rdi; this
0x180003366  call    ??1CDpUrlAccessor@@QEAA@XZ; CDpUrlAccessor::~CDpUrlAccessor(void)
0x18000336b  test    bl, 1
0x18000336e  jz      short loc_180003379
0x180003370  mov     rcx, rdi
0x180003373  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003379  mov     rbx, [rsp+28h+arg_0]
0x18000337e  mov     rax, rdi
0x180003381  add     rsp, 20h
0x180003385  pop     rdi
0x180003386  retn
```
