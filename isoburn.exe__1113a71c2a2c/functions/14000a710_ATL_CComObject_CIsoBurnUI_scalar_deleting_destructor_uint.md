# ATL::CComObject<CIsoBurnUI>::`scalar deleting destructor'(uint)

- ea: `0x14000a710`
- end: `0x14000a776`
- name: `??_G?$CComObject@VCIsoBurnUI@@@ATL@@UEAAPEAXI@Z`
- size: `102`
- prototype: `__int64 __fastcall(CIsoBurnUI *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001c54`
- `0x14000a694`
- `0x14000a710`
- `0x140010010`

## pseudocode

```c
CIsoBurnUI *__fastcall ATL::CComObject<CIsoBurnUI>::`scalar deleting destructor'(CIsoBurnUI *this, char a2)
{
  *((_DWORD *)this + 18) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIsoBurnUI>::`vftable'{for `ATL::CDialogImpl<CIsoBurnUI,ATL::CWindow>'};
  *((_QWORD *)this + 8) = &ATL::CComObject<CIsoBurnUI>::`vftable'{for `IIsoBurnProgress'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIsoBurnUI::~CIsoBurnUI(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000a710  mov     [rsp+arg_0], rbx
0x14000a715  push    rdi
0x14000a716  sub     rsp, 20h
0x14000a71a  mov     dword ptr [rcx+48h], 0C0000001h
0x14000a721  lea     rax, ??_7?$CComObject@VCIsoBurnUI@@@ATL@@6B?$CDialogImpl@VCIsoBurnUI@@VCWindow@ATL@@@1@@; const ATL::CComObject<CIsoBurnUI>::`vftable'{for `ATL::CDialogImpl<CIsoBurnUI,ATL::CWindow>'}
0x14000a728  mov     [rcx], rax
0x14000a72b  mov     rdi, rcx
0x14000a72e  lea     rax, ??_7?$CComObject@VCIsoBurnUI@@@ATL@@6BIIsoBurnProgress@@@; const ATL::CComObject<CIsoBurnUI>::`vftable'{for `IIsoBurnProgress'}
0x14000a735  mov     ebx, edx
0x14000a737  mov     [rcx+40h], rax
0x14000a73b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000a742  mov     rax, [rcx]
0x14000a745  mov     rax, [rax+10h]
0x14000a749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a74e  mov     rcx, rdi; this
0x14000a751  call    ??1CIsoBurnUI@@UEAA@XZ; CIsoBurnUI::~CIsoBurnUI(void)
0x14000a756  test    bl, 1
0x14000a759  jz      short loc_14000A768
0x14000a75b  mov     edx, 0C0h
0x14000a760  mov     rcx, rdi; Block
0x14000a763  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000a768  mov     rbx, [rsp+28h+arg_0]
0x14000a76d  mov     rax, rdi
0x14000a770  add     rsp, 20h
0x14000a774  pop     rdi
0x14000a775  retn
```
