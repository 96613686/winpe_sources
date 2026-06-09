# ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x140005dc0`
- end: `0x140005e27`
- name: `?GetTypeInfo@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400058e4`
- `0x140005dc0`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_140016128;
  result = 0;
  if ( !qword_140016128 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)&ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_140016128;
  }
  *a4 = v6;
  if ( qword_140016128 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))qword_140016128->lpVtbl->AddRef)(qword_140016128);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005dc0  push    rbx
0x140005dc2  sub     rsp, 20h
0x140005dc6  mov     rbx, r9
0x140005dc9  test    edx, edx
0x140005dcb  jz      short loc_140005DD4
0x140005dcd  mov     eax, 8002000Bh
0x140005dd2  jmp     short loc_140005E21
0x140005dd4  test    rbx, rbx
0x140005dd7  jnz     short loc_140005DE0
0x140005dd9  mov     eax, 80004003h
0x140005dde  jmp     short loc_140005E21
0x140005de0  mov     rcx, cs:qword_140016128
0x140005de7  xor     eax, eax
0x140005de9  test    rcx, rcx
0x140005dec  jnz     short loc_140005E04
0x140005dee  mov     edx, r8d; lcid
0x140005df1  lea     rcx, ?_tih@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140005df8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140005dfd  mov     rcx, cs:qword_140016128
0x140005e04  mov     [rbx], rcx
0x140005e07  mov     rcx, cs:qword_140016128
0x140005e0e  test    rcx, rcx
0x140005e11  jz      short loc_140005E21
0x140005e13  mov     rax, [rcx]
0x140005e16  mov     rax, [rax+8]
0x140005e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e1f  xor     eax, eax
0x140005e21  add     rsp, 20h
0x140005e25  pop     rbx
0x140005e26  retn
```
