# ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x140005d50`
- end: `0x140005db7`
- name: `?GetTypeInfo@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400058e4`
- `0x140005d50`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_1400160A8;
  result = 0;
  if ( !qword_1400160A8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)&ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_1400160A8;
  }
  *a4 = v6;
  if ( qword_1400160A8 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))qword_1400160A8->lpVtbl->AddRef)(qword_1400160A8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005d50  push    rbx
0x140005d52  sub     rsp, 20h
0x140005d56  mov     rbx, r9
0x140005d59  test    edx, edx
0x140005d5b  jz      short loc_140005D64
0x140005d5d  mov     eax, 8002000Bh
0x140005d62  jmp     short loc_140005DB1
0x140005d64  test    rbx, rbx
0x140005d67  jnz     short loc_140005D70
0x140005d69  mov     eax, 80004003h
0x140005d6e  jmp     short loc_140005DB1
0x140005d70  mov     rcx, cs:qword_1400160A8
0x140005d77  xor     eax, eax
0x140005d79  test    rcx, rcx
0x140005d7c  jnz     short loc_140005D94
0x140005d7e  mov     edx, r8d; lcid
0x140005d81  lea     rcx, ?_tih@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140005d88  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140005d8d  mov     rcx, cs:qword_1400160A8
0x140005d94  mov     [rbx], rcx
0x140005d97  mov     rcx, cs:qword_1400160A8
0x140005d9e  test    rcx, rcx
0x140005da1  jz      short loc_140005DB1
0x140005da3  mov     rax, [rcx]
0x140005da6  mov     rax, [rax+8]
0x140005daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005daf  xor     eax, eax
0x140005db1  add     rsp, 20h
0x140005db5  pop     rbx
0x140005db6  retn
```
