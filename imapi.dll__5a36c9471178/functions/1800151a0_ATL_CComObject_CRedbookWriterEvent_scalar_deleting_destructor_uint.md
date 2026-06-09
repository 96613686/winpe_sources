# ATL::CComObject<CRedbookWriterEvent>::`scalar deleting destructor'(uint)

- ea: `0x1800151a0`
- end: `0x18001520e`
- name: `??_G?$CComObject@VCRedbookWriterEvent@@@ATL@@UEAAPEAXI@Z`
- size: `110`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001144`
- `0x1800151a0`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800151ec`
- `KERNEL32!DeleteCriticalSection` at `0x1800151ec`

## pseudocode

```c
char *__fastcall ATL::CComObject<CRedbookWriterEvent>::`scalar deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 14) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CRedbookWriterEvent>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)Block + 1) = &ATL::CComObject<CRedbookWriterEvent>::`vftable'{for `ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( Block[104] )
  {
    Block[104] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 64));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800151a0  mov     [rsp+arg_0], rbx
0x1800151a5  push    rdi
0x1800151a6  sub     rsp, 20h
0x1800151aa  mov     dword ptr [rcx+38h], 0C0000001h
0x1800151b1  lea     rax, ??_7?$CComObject@VCRedbookWriterEvent@@@ATL@@6B?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CRedbookWriterEvent>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x1800151b8  mov     [rcx], rax
0x1800151bb  mov     rbx, rcx
0x1800151be  lea     rax, ??_7?$CComObject@VCRedbookWriterEvent@@@ATL@@6B?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CRedbookWriterEvent>::`vftable'{for `ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x1800151c5  mov     edi, edx
0x1800151c7  mov     [rcx+8], rax
0x1800151cb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800151d2  mov     rax, [rcx]
0x1800151d5  mov     rax, [rax+10h]
0x1800151d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151de  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800151e2  cmp     byte ptr [rcx+28h], 0
0x1800151e6  jz      short loc_1800151F2
0x1800151e8  mov     byte ptr [rcx+28h], 0
0x1800151ec  call    cs:__imp_DeleteCriticalSection
0x1800151f2  test    dil, 1
0x1800151f6  jz      short loc_180015200
0x1800151f8  mov     rcx, rbx; Block
0x1800151fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015200  mov     rax, rbx
0x180015203  mov     rbx, [rsp+28h+arg_0]
0x180015208  add     rsp, 20h
0x18001520c  pop     rdi
0x18001520d  retn
```
