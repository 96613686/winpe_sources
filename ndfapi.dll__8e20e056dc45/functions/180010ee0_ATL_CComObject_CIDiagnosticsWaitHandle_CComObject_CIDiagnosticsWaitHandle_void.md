# ATL::CComObject<CIDiagnosticsWaitHandle>::~CComObject<CIDiagnosticsWaitHandle>(void)

- ea: `0x180010ee0`
- end: `0x180010f47`
- name: `??1?$CComObject@VCIDiagnosticsWaitHandle@@@ATL@@UEAA@XZ`
- size: `103`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011450`

## callees

- `0x180010ee0`
- `0x180021010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180010f3b`
- `KERNEL32!DeleteCriticalSection` at `0x180010f3b`

## pseudocode

```c
void __fastcall ATL::CComObject<CIDiagnosticsWaitHandle>::~CComObject<CIDiagnosticsWaitHandle>(__int64 a1)
{
  *(_DWORD *)(a1 + 16) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CIDiagnosticsWaitHandle>::`vftable'{for `ATL::IDispatchImpl<IDiagnosticsWaitHandle,&__s_GUID const _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CIDiagnosticsWaitHandle>::`vftable'{for `ISynchronize'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)a1 = &CIDiagnosticsWaitHandle::`vftable'{for `ATL::IDispatchImpl<IDiagnosticsWaitHandle,&__s_GUID const _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 8) = &CIDiagnosticsWaitHandle::`vftable'{for `ISynchronize'};
  if ( *(_BYTE *)(a1 + 64) )
  {
    *(_BYTE *)(a1 + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  }
}

```

## disassembly

```asm
0x180010ee0  push    rbx
0x180010ee2  sub     rsp, 20h
0x180010ee6  mov     dword ptr [rcx+10h], 0C0000001h
0x180010eed  lea     rax, ??_7?$CComObject@VCIDiagnosticsWaitHandle@@@ATL@@6B?$IDispatchImpl@UIDiagnosticsWaitHandle@@$1?_GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CIDiagnosticsWaitHandle>::`vftable'{for `ATL::IDispatchImpl<IDiagnosticsWaitHandle,&__s_GUID const _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x180010ef4  mov     [rcx], rax
0x180010ef7  mov     rbx, rcx
0x180010efa  lea     rax, ??_7?$CComObject@VCIDiagnosticsWaitHandle@@@ATL@@6BISynchronize@@@; const ATL::CComObject<CIDiagnosticsWaitHandle>::`vftable'{for `ISynchronize'}
0x180010f01  mov     [rcx+8], rax
0x180010f05  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180010f0c  mov     rax, [rcx]
0x180010f0f  mov     rax, [rax+10h]
0x180010f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f18  lea     rax, ??_7CIDiagnosticsWaitHandle@@6B?$IDispatchImpl@UIDiagnosticsWaitHandle@@$1?_GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CIDiagnosticsWaitHandle::`vftable'{for `ATL::IDispatchImpl<IDiagnosticsWaitHandle,&__s_GUID const _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x180010f1f  mov     [rbx], rax
0x180010f22  lea     rcx, [rbx+18h]; lpCriticalSection
0x180010f26  lea     rax, ??_7CIDiagnosticsWaitHandle@@6BISynchronize@@@; const CIDiagnosticsWaitHandle::`vftable'{for `ISynchronize'}
0x180010f2d  mov     [rbx+8], rax
0x180010f31  cmp     byte ptr [rcx+28h], 0
0x180010f35  jz      short loc_180010F41
0x180010f37  mov     byte ptr [rcx+28h], 0
0x180010f3b  call    cs:__imp_DeleteCriticalSection
0x180010f41  add     rsp, 20h
0x180010f45  pop     rbx
0x180010f46  retn
```
