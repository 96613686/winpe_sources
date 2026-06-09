# ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x140005e30`
- end: `0x140005e97`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400058e4`
- `0x140005e30`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_1400160E8;
  result = 0;
  if ( !qword_1400160E8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_1400160E8;
  }
  *a4 = v6;
  if ( qword_1400160E8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1400160E8 + 8LL))(qword_1400160E8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005e30  push    rbx
0x140005e32  sub     rsp, 20h
0x140005e36  mov     rbx, r9
0x140005e39  test    edx, edx
0x140005e3b  jz      short loc_140005E44
0x140005e3d  mov     eax, 8002000Bh
0x140005e42  jmp     short loc_140005E91
0x140005e44  test    rbx, rbx
0x140005e47  jnz     short loc_140005E50
0x140005e49  mov     eax, 80004003h
0x140005e4e  jmp     short loc_140005E91
0x140005e50  mov     rcx, cs:qword_1400160E8
0x140005e57  xor     eax, eax
0x140005e59  test    rcx, rcx
0x140005e5c  jnz     short loc_140005E74
0x140005e5e  mov     edx, r8d; lcid
0x140005e61  lea     rcx, ?_tih@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140005e68  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140005e6d  mov     rcx, cs:qword_1400160E8
0x140005e74  mov     [rbx], rcx
0x140005e77  mov     rcx, cs:qword_1400160E8
0x140005e7e  test    rcx, rcx
0x140005e81  jz      short loc_140005E91
0x140005e83  mov     rax, [rcx]
0x140005e86  mov     rax, [rax+8]
0x140005e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e8f  xor     eax, eax
0x140005e91  add     rsp, 20h
0x140005e95  pop     rbx
0x140005e96  retn
```
