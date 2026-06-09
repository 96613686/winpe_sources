# ATL::IDispatchImpl<IDiagnosisParameterEnum,&__s_GUID const _GUID_d30a82ff_2f37_40c0_a24d_2a8ca90321eb,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1800134c0`
- end: `0x180013527`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDiagnosisParameterEnum@@$1?_GUID_d30a82ff_2f37_40c0_a24d_2a8ca90321eb@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800131d8`
- `0x1800134c0`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDiagnosisParameterEnum,&__s_GUID const _GUID_d30a82ff_2f37_40c0_a24d_2a8ca90321eb,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_18002F2A8;
  result = 0;
  if ( !qword_18002F2A8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDiagnosisParameterEnum,&__s_GUID const _GUID_d30a82ff_2f37_40c0_a24d_2a8ca90321eb,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_18002F2A8;
  }
  *a4 = v6;
  if ( qword_18002F2A8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002F2A8 + 8LL))(qword_18002F2A8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800134c0  push    rbx
0x1800134c2  sub     rsp, 20h
0x1800134c6  mov     rbx, r9
0x1800134c9  test    edx, edx
0x1800134cb  jz      short loc_1800134D4
0x1800134cd  mov     eax, 8002000Bh
0x1800134d2  jmp     short loc_180013521
0x1800134d4  test    rbx, rbx
0x1800134d7  jnz     short loc_1800134E0
0x1800134d9  mov     eax, 80004003h
0x1800134de  jmp     short loc_180013521
0x1800134e0  mov     rcx, cs:qword_18002F2A8
0x1800134e7  xor     eax, eax
0x1800134e9  test    rcx, rcx
0x1800134ec  jnz     short loc_180013504
0x1800134ee  mov     edx, r8d; lcid
0x1800134f1  lea     rcx, ?_tih@?$IDispatchImpl@UIDiagnosisParameterEnum@@$1?_GUID_d30a82ff_2f37_40c0_a24d_2a8ca90321eb@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800134f8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800134fd  mov     rcx, cs:qword_18002F2A8
0x180013504  mov     [rbx], rcx
0x180013507  mov     rcx, cs:qword_18002F2A8
0x18001350e  test    rcx, rcx
0x180013511  jz      short loc_180013521
0x180013513  mov     rax, [rcx]
0x180013516  mov     rax, [rax+8]
0x18001351a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001351f  xor     eax, eax
0x180013521  add     rsp, 20h
0x180013525  pop     rbx
0x180013526  retn
```
