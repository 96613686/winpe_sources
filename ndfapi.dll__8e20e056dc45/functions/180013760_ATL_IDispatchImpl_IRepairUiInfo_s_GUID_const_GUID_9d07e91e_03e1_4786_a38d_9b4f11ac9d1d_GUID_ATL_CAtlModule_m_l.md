# ATL::IDispatchImpl<IRepairUiInfo,&__s_GUID const _GUID_9d07e91e_03e1_4786_a38d_9b4f11ac9d1d,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180013760`
- end: `0x1800137c7`
- name: `?GetTypeInfo@?$IDispatchImpl@UIRepairUiInfo@@$1?_GUID_9d07e91e_03e1_4786_a38d_9b4f11ac9d1d@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800131d8`
- `0x180013760`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IRepairUiInfo,&__s_GUID const _GUID_9d07e91e_03e1_4786_a38d_9b4f11ac9d1d,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_18002F1A8;
  result = 0;
  if ( !qword_18002F1A8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IRepairUiInfo,&__s_GUID const _GUID_9d07e91e_03e1_4786_a38d_9b4f11ac9d1d,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_18002F1A8;
  }
  *a4 = v6;
  if ( qword_18002F1A8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002F1A8 + 8LL))(qword_18002F1A8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013760  push    rbx
0x180013762  sub     rsp, 20h
0x180013766  mov     rbx, r9
0x180013769  test    edx, edx
0x18001376b  jz      short loc_180013774
0x18001376d  mov     eax, 8002000Bh
0x180013772  jmp     short loc_1800137C1
0x180013774  test    rbx, rbx
0x180013777  jnz     short loc_180013780
0x180013779  mov     eax, 80004003h
0x18001377e  jmp     short loc_1800137C1
0x180013780  mov     rcx, cs:qword_18002F1A8
0x180013787  xor     eax, eax
0x180013789  test    rcx, rcx
0x18001378c  jnz     short loc_1800137A4
0x18001378e  mov     edx, r8d; lcid
0x180013791  lea     rcx, ?_tih@?$IDispatchImpl@UIRepairUiInfo@@$1?_GUID_9d07e91e_03e1_4786_a38d_9b4f11ac9d1d@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180013798  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001379d  mov     rcx, cs:qword_18002F1A8
0x1800137a4  mov     [rbx], rcx
0x1800137a7  mov     rcx, cs:qword_18002F1A8
0x1800137ae  test    rcx, rcx
0x1800137b1  jz      short loc_1800137C1
0x1800137b3  mov     rax, [rcx]
0x1800137b6  mov     rax, [rax+8]
0x1800137ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137bf  xor     eax, eax
0x1800137c1  add     rsp, 20h
0x1800137c5  pop     rbx
0x1800137c6  retn
```
