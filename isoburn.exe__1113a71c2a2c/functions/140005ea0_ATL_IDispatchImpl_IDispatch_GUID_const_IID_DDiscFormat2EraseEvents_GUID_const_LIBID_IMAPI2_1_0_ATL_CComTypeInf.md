# ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x140005ea0`
- end: `0x140005f07`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400058e4`
- `0x140005ea0`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_140016068;
  result = 0;
  if ( !qword_140016068 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_140016068;
  }
  *a4 = v6;
  if ( qword_140016068 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140016068 + 8LL))(qword_140016068);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005ea0  push    rbx
0x140005ea2  sub     rsp, 20h
0x140005ea6  mov     rbx, r9
0x140005ea9  test    edx, edx
0x140005eab  jz      short loc_140005EB4
0x140005ead  mov     eax, 8002000Bh
0x140005eb2  jmp     short loc_140005F01
0x140005eb4  test    rbx, rbx
0x140005eb7  jnz     short loc_140005EC0
0x140005eb9  mov     eax, 80004003h
0x140005ebe  jmp     short loc_140005F01
0x140005ec0  mov     rcx, cs:qword_140016068
0x140005ec7  xor     eax, eax
0x140005ec9  test    rcx, rcx
0x140005ecc  jnz     short loc_140005EE4
0x140005ece  mov     edx, r8d; lcid
0x140005ed1  lea     rcx, ?_tih@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140005ed8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140005edd  mov     rcx, cs:qword_140016068
0x140005ee4  mov     [rbx], rcx
0x140005ee7  mov     rcx, cs:qword_140016068
0x140005eee  test    rcx, rcx
0x140005ef1  jz      short loc_140005F01
0x140005ef3  mov     rax, [rcx]
0x140005ef6  mov     rax, [rax+8]
0x140005efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eff  xor     eax, eax
0x140005f01  add     rsp, 20h
0x140005f05  pop     rbx
0x140005f06  retn
```
