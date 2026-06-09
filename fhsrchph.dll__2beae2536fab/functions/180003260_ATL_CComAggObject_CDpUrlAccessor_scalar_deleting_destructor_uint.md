# ATL::CComAggObject<CDpUrlAccessor>::`scalar deleting destructor'(uint)

- ea: `0x180003260`
- end: `0x1800032b8`
- name: `??_G?$CComAggObject@VCDpUrlAccessor@@@ATL@@UEAAPEAXI@Z`
- size: `88`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003034`
- `0x180003260`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800032a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800032a4`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CDpUrlAccessor>::`scalar deleting destructor'(_DWORD *a1, char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CDpUrlAccessor>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CDpUrlAccessor::~CDpUrlAccessor((CDpUrlAccessor *)(a1 + 6));
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003260  mov     [rsp+arg_0], rbx
0x180003265  push    rdi
0x180003266  sub     rsp, 20h
0x18000326a  mov     dword ptr [rcx+8], 0C0000001h
0x180003271  lea     rax, ??_7?$CComAggObject@VCDpUrlAccessor@@@ATL@@6B@; const ATL::CComAggObject<CDpUrlAccessor>::`vftable'
0x180003278  mov     [rcx], rax
0x18000327b  mov     rdi, rcx
0x18000327e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003285  mov     ebx, edx
0x180003287  mov     rax, [rcx]
0x18000328a  mov     rax, [rax+10h]
0x18000328e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003293  lea     rcx, [rdi+18h]; this
0x180003297  call    ??1CDpUrlAccessor@@QEAA@XZ; CDpUrlAccessor::~CDpUrlAccessor(void)
0x18000329c  test    bl, 1
0x18000329f  jz      short loc_1800032AA
0x1800032a1  mov     rcx, rdi
0x1800032a4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800032aa  mov     rbx, [rsp+28h+arg_0]
0x1800032af  mov     rax, rdi
0x1800032b2  add     rsp, 20h
0x1800032b6  pop     rdi
0x1800032b7  retn
```
