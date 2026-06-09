# ATL::IDispatchImpl<IRepairInfoEnum,&__s_GUID const _GUID_cbfdf96c_fb17_43dd_bc0f_03ca57914435,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1800136f0`
- end: `0x180013757`
- name: `?GetTypeInfo@?$IDispatchImpl@UIRepairInfoEnum@@$1?_GUID_cbfdf96c_fb17_43dd_bc0f_03ca57914435@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800131d8`
- `0x1800136f0`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IRepairInfoEnum,&__s_GUID const _GUID_cbfdf96c_fb17_43dd_bc0f_03ca57914435,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_18002F228;
  result = 0;
  if ( !qword_18002F228 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IRepairInfoEnum,&__s_GUID const _GUID_cbfdf96c_fb17_43dd_bc0f_03ca57914435,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_18002F228;
  }
  *a4 = v6;
  if ( qword_18002F228 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002F228 + 8LL))(qword_18002F228);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800136f0  push    rbx
0x1800136f2  sub     rsp, 20h
0x1800136f6  mov     rbx, r9
0x1800136f9  test    edx, edx
0x1800136fb  jz      short loc_180013704
0x1800136fd  mov     eax, 8002000Bh
0x180013702  jmp     short loc_180013751
0x180013704  test    rbx, rbx
0x180013707  jnz     short loc_180013710
0x180013709  mov     eax, 80004003h
0x18001370e  jmp     short loc_180013751
0x180013710  mov     rcx, cs:qword_18002F228
0x180013717  xor     eax, eax
0x180013719  test    rcx, rcx
0x18001371c  jnz     short loc_180013734
0x18001371e  mov     edx, r8d; lcid
0x180013721  lea     rcx, ?_tih@?$IDispatchImpl@UIRepairInfoEnum@@$1?_GUID_cbfdf96c_fb17_43dd_bc0f_03ca57914435@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180013728  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001372d  mov     rcx, cs:qword_18002F228
0x180013734  mov     [rbx], rcx
0x180013737  mov     rcx, cs:qword_18002F228
0x18001373e  test    rcx, rcx
0x180013741  jz      short loc_180013751
0x180013743  mov     rax, [rcx]
0x180013746  mov     rax, [rax+8]
0x18001374a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001374f  xor     eax, eax
0x180013751  add     rsp, 20h
0x180013755  pop     rbx
0x180013756  retn
```
