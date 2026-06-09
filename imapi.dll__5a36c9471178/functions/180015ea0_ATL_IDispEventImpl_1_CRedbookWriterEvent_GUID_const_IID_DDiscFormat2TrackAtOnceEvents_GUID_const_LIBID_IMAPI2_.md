# ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180015ea0`
- end: `0x180015f07`
- name: `?GetTypeInfo@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180015bd8`
- `0x180015ea0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  __int64 result; // rax
  struct ITypeInfo *v6; // rcx

  if ( a2 )
    return 2147614731LL;
  if ( !a4 )
    return 2147500035LL;
  v6 = qword_1800212E8;
  result = 0;
  if ( !qword_1800212E8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)&ATL::IDispEventImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_1800212E8;
  }
  *a4 = v6;
  if ( qword_1800212E8 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))qword_1800212E8->lpVtbl->AddRef)(qword_1800212E8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015ea0  push    rbx
0x180015ea2  sub     rsp, 20h
0x180015ea6  mov     rbx, r9
0x180015ea9  test    edx, edx
0x180015eab  jz      short loc_180015EB4
0x180015ead  mov     eax, 8002000Bh
0x180015eb2  jmp     short loc_180015F01
0x180015eb4  test    rbx, rbx
0x180015eb7  jnz     short loc_180015EC0
0x180015eb9  mov     eax, 80004003h
0x180015ebe  jmp     short loc_180015F01
0x180015ec0  mov     rcx, cs:qword_1800212E8
0x180015ec7  xor     eax, eax
0x180015ec9  test    rcx, rcx
0x180015ecc  jnz     short loc_180015EE4
0x180015ece  mov     edx, r8d; lcid
0x180015ed1  lea     rcx, ?_tih@?$IDispEventImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180015ed8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180015edd  mov     rcx, cs:qword_1800212E8
0x180015ee4  mov     [rbx], rcx
0x180015ee7  mov     rcx, cs:qword_1800212E8
0x180015eee  test    rcx, rcx
0x180015ef1  jz      short loc_180015F01
0x180015ef3  mov     rax, [rcx]
0x180015ef6  mov     rax, [rax+8]
0x180015efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eff  xor     eax, eax
0x180015f01  add     rsp, 20h
0x180015f05  pop     rbx
0x180015f06  retn
```
