# ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180004a10`
- end: `0x180004a32`
- name: `?GetTypeInfo@?$IDispatchImpl@UILogScripting@@$1?IID_ILogScripting@@3U_GUID@@B$1?LIBID_IISLog@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002734`
- `0x180004a10`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        ITypeLib *a1,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  if ( !a4 )
    return 2147500035LL;
  if ( a2 )
    return 2147614731LL;
  return ATL::CComTypeInfoHolder::GetTI(a1, a3, a4);
}

```

## disassembly

```asm
0x180004a10  mov     eax, r8d
0x180004a13  test    r9, r9
0x180004a16  jnz     short loc_180004A1E
0x180004a18  mov     eax, 80004003h
0x180004a1d  retn
0x180004a1e  test    edx, edx
0x180004a20  jz      short loc_180004A28
0x180004a22  mov     eax, 8002000Bh
0x180004a27  retn
0x180004a28  mov     r8, r9; struct ITypeInfo **
0x180004a2b  mov     edx, eax; unsigned int
0x180004a2d  jmp     ?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)
```
