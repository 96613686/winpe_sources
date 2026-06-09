# ATL::IDispatchImpl<IDiagnosisParameter,&__s_GUID const _GUID_5b8fe18c_02a2_4364_9ff6_3415cefaf70b,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180013450`
- end: `0x1800134b7`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDiagnosisParameter@@$1?_GUID_5b8fe18c_02a2_4364_9ff6_3415cefaf70b@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800131d8`
- `0x180013450`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDiagnosisParameter,&__s_GUID const _GUID_5b8fe18c_02a2_4364_9ff6_3415cefaf70b,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_18002F268;
  result = 0;
  if ( !qword_18002F268 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDiagnosisParameter,&__s_GUID const _GUID_5b8fe18c_02a2_4364_9ff6_3415cefaf70b,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_18002F268;
  }
  *a4 = v6;
  if ( qword_18002F268 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002F268 + 8LL))(qword_18002F268);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013450  push    rbx
0x180013452  sub     rsp, 20h
0x180013456  mov     rbx, r9
0x180013459  test    edx, edx
0x18001345b  jz      short loc_180013464
0x18001345d  mov     eax, 8002000Bh
0x180013462  jmp     short loc_1800134B1
0x180013464  test    rbx, rbx
0x180013467  jnz     short loc_180013470
0x180013469  mov     eax, 80004003h
0x18001346e  jmp     short loc_1800134B1
0x180013470  mov     rcx, cs:qword_18002F268
0x180013477  xor     eax, eax
0x180013479  test    rcx, rcx
0x18001347c  jnz     short loc_180013494
0x18001347e  mov     edx, r8d; lcid
0x180013481  lea     rcx, ?_tih@?$IDispatchImpl@UIDiagnosisParameter@@$1?_GUID_5b8fe18c_02a2_4364_9ff6_3415cefaf70b@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180013488  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001348d  mov     rcx, cs:qword_18002F268
0x180013494  mov     [rbx], rcx
0x180013497  mov     rcx, cs:qword_18002F268
0x18001349e  test    rcx, rcx
0x1800134a1  jz      short loc_1800134B1
0x1800134a3  mov     rax, [rcx]
0x1800134a6  mov     rax, [rax+8]
0x1800134aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134af  xor     eax, eax
0x1800134b1  add     rsp, 20h
0x1800134b5  pop     rbx
0x1800134b6  retn
```
