# ATL::CComObject<CEraseEvent>::~CComObject<CEraseEvent>(void)

- ea: `0x140003818`
- end: `0x14000387f`
- name: `??1?$CComObject@VCEraseEvent@@@ATL@@UEAA@XZ`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003d50`

## callees

- `0x140003818`
- `0x140010010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140003873`
- `KERNEL32!DeleteCriticalSection` at `0x140003873`

## pseudocode

```c
void __fastcall ATL::CComObject<CEraseEvent>::~CComObject<CEraseEvent>(__int64 a1)
{
  __int64 v2; // rcx

  *(_DWORD *)(a1 + 56) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CEraseEvent>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CEraseEvent>::`vftable'{for `ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v2 = *(_QWORD *)(a1 + 112);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *(_BYTE *)(a1 + 104) )
  {
    *(_BYTE *)(a1 + 104) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  }
}

```

## disassembly

```asm
0x140003818  push    rbx
0x14000381a  sub     rsp, 20h
0x14000381e  mov     dword ptr [rcx+38h], 0C0000001h
0x140003825  lea     rax, ??_7?$CComObject@VCEraseEvent@@@ATL@@6B?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CEraseEvent>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x14000382c  mov     [rcx], rax
0x14000382f  mov     rbx, rcx
0x140003832  lea     rax, ??_7?$CComObject@VCEraseEvent@@@ATL@@6B?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CEraseEvent>::`vftable'{for `ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x140003839  mov     [rcx+8], rax
0x14000383d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003844  mov     rax, [rcx]
0x140003847  mov     rax, [rax+10h]
0x14000384b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003850  mov     rcx, [rbx+70h]
0x140003854  test    rcx, rcx
0x140003857  jz      short loc_140003865
0x140003859  mov     rax, [rcx]
0x14000385c  mov     rax, [rax+10h]
0x140003860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003865  lea     rcx, [rbx+40h]; lpCriticalSection
0x140003869  cmp     byte ptr [rcx+28h], 0
0x14000386d  jz      short loc_140003879
0x14000386f  mov     byte ptr [rcx+28h], 0
0x140003873  call    cs:__imp_DeleteCriticalSection
0x140003879  add     rsp, 20h
0x14000387d  pop     rbx
0x14000387e  retn
```
