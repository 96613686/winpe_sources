# ATL::IDispatchImpl<INetworkDiagnostics,&_GUID const IID_INetworkDiagnostics,&_GUID const LIBID_ndfapiLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180013610`
- end: `0x180013677`
- name: `?GetTypeInfo@?$IDispatchImpl@UINetworkDiagnostics@@$1?IID_INetworkDiagnostics@@3U_GUID@@B$1?LIBID_ndfapiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800131d8`
- `0x180013610`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<INetworkDiagnostics,&_GUID const IID_INetworkDiagnostics,&_GUID const LIBID_ndfapiLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_18002F0E8;
  result = 0;
  if ( !qword_18002F0E8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<INetworkDiagnostics,&_GUID const IID_INetworkDiagnostics,&_GUID const LIBID_ndfapiLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_18002F0E8;
  }
  *a4 = v6;
  if ( qword_18002F0E8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002F0E8 + 8LL))(qword_18002F0E8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013610  push    rbx
0x180013612  sub     rsp, 20h
0x180013616  mov     rbx, r9
0x180013619  test    edx, edx
0x18001361b  jz      short loc_180013624
0x18001361d  mov     eax, 8002000Bh
0x180013622  jmp     short loc_180013671
0x180013624  test    rbx, rbx
0x180013627  jnz     short loc_180013630
0x180013629  mov     eax, 80004003h
0x18001362e  jmp     short loc_180013671
0x180013630  mov     rcx, cs:qword_18002F0E8
0x180013637  xor     eax, eax
0x180013639  test    rcx, rcx
0x18001363c  jnz     short loc_180013654
0x18001363e  mov     edx, r8d; lcid
0x180013641  lea     rcx, ?_tih@?$IDispatchImpl@UINetworkDiagnostics@@$1?IID_INetworkDiagnostics@@3U_GUID@@B$1?LIBID_ndfapiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180013648  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001364d  mov     rcx, cs:qword_18002F0E8
0x180013654  mov     [rbx], rcx
0x180013657  mov     rcx, cs:qword_18002F0E8
0x18001365e  test    rcx, rcx
0x180013661  jz      short loc_180013671
0x180013663  mov     rax, [rcx]
0x180013666  mov     rax, [rax+8]
0x18001366a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001366f  xor     eax, eax
0x180013671  add     rsp, 20h
0x180013675  pop     rbx
0x180013676  retn
```
