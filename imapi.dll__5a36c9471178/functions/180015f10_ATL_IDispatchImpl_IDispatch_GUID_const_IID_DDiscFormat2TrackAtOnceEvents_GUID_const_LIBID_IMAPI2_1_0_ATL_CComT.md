# ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180015f10`
- end: `0x180015f77`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015bd8`
- `0x180015f10`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        int a2,
        LCID a3,
        __int64 *a4)
{
  __int64 result; // rax
  __int64 v6; // rcx

  if ( a2 )
    return 2147614731LL;
  if ( !a4 )
    return 2147500035LL;
  v6 = qword_1800212A8;
  result = 0;
  if ( !qword_1800212A8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_1800212A8;
  }
  *a4 = v6;
  if ( qword_1800212A8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800212A8 + 8LL))(qword_1800212A8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015f10  push    rbx
0x180015f12  sub     rsp, 20h
0x180015f16  mov     rbx, r9
0x180015f19  test    edx, edx
0x180015f1b  jz      short loc_180015F24
0x180015f1d  mov     eax, 8002000Bh
0x180015f22  jmp     short loc_180015F71
0x180015f24  test    rbx, rbx
0x180015f27  jnz     short loc_180015F30
0x180015f29  mov     eax, 80004003h
0x180015f2e  jmp     short loc_180015F71
0x180015f30  mov     rcx, cs:qword_1800212A8
0x180015f37  xor     eax, eax
0x180015f39  test    rcx, rcx
0x180015f3c  jnz     short loc_180015F54
0x180015f3e  mov     edx, r8d; lcid
0x180015f41  lea     rcx, ?_tih@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180015f48  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180015f4d  mov     rcx, cs:qword_1800212A8
0x180015f54  mov     [rbx], rcx
0x180015f57  mov     rcx, cs:qword_1800212A8
0x180015f5e  test    rcx, rcx
0x180015f61  jz      short loc_180015F71
0x180015f63  mov     rax, [rcx]
0x180015f66  mov     rax, [rax+8]
0x180015f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f6f  xor     eax, eax
0x180015f71  add     rsp, 20h
0x180015f75  pop     rbx
0x180015f76  retn
```
