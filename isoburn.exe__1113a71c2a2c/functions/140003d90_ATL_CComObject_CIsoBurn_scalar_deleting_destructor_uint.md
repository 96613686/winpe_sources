# ATL::CComObject<CIsoBurn>::`scalar deleting destructor'(uint)

- ea: `0x140003d90`
- end: `0x140003e01`
- name: `??_G?$CComObject@VCIsoBurn@@@ATL@@UEAAPEAXI@Z`
- size: `113`
- prototype: `__int64 __fastcall(CIsoBurn *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140001c54`
- `0x140003a78`
- `0x140003d90`
- `0x140010010`

## pseudocode

```c
CIsoBurn *__fastcall ATL::CComObject<CIsoBurn>::`scalar deleting destructor'(CIsoBurn *this, char a2)
{
  *((_DWORD *)this + 16) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIsoBurn>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CIsoBurn>::`vftable'{for `ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 7) = &ATL::CComObject<CIsoBurn>::`vftable'{for `IIsoBurn'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIsoBurn::~CIsoBurn(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140003d90  mov     [rsp+arg_0], rbx
0x140003d95  push    rdi
0x140003d96  sub     rsp, 20h
0x140003d9a  mov     dword ptr [rcx+40h], 0C0000001h
0x140003da1  lea     rax, ??_7?$CComObject@VCIsoBurn@@@ATL@@6B?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CIsoBurn>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x140003da8  mov     [rcx], rax
0x140003dab  mov     rdi, rcx
0x140003dae  lea     rax, ??_7?$CComObject@VCIsoBurn@@@ATL@@6B?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CIsoBurn>::`vftable'{for `ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x140003db5  mov     ebx, edx
0x140003db7  mov     [rcx+8], rax
0x140003dbb  lea     rax, ??_7?$CComObject@VCIsoBurn@@@ATL@@6BIIsoBurn@@@; const ATL::CComObject<CIsoBurn>::`vftable'{for `IIsoBurn'}
0x140003dc2  mov     [rcx+38h], rax
0x140003dc6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003dcd  mov     rax, [rcx]
0x140003dd0  mov     rax, [rax+10h]
0x140003dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dd9  mov     rcx, rdi; this
0x140003ddc  call    ??1CIsoBurn@@QEAA@XZ; CIsoBurn::~CIsoBurn(void)
0x140003de1  test    bl, 1
0x140003de4  jz      short loc_140003DF3
0x140003de6  mov     edx, 0A8h
0x140003deb  mov     rcx, rdi; Block
0x140003dee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003df3  mov     rbx, [rsp+28h+arg_0]
0x140003df8  mov     rax, rdi
0x140003dfb  add     rsp, 20h
0x140003dff  pop     rdi
0x140003e00  retn
```
