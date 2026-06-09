# ATL::IDispatchImpl<IDiagnosisText,&__s_GUID const _GUID_f7c33982_17fe_4472_ac19_8113f5a9cf78,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180013530`
- end: `0x180013597`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDiagnosisText@@$1?_GUID_f7c33982_17fe_4472_ac19_8113f5a9cf78@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800131d8`
- `0x180013530`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDiagnosisText,&__s_GUID const _GUID_f7c33982_17fe_4472_ac19_8113f5a9cf78,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_18002F2E8;
  result = 0;
  if ( !qword_18002F2E8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDiagnosisText,&__s_GUID const _GUID_f7c33982_17fe_4472_ac19_8113f5a9cf78,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_18002F2E8;
  }
  *a4 = v6;
  if ( qword_18002F2E8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002F2E8 + 8LL))(qword_18002F2E8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013530  push    rbx
0x180013532  sub     rsp, 20h
0x180013536  mov     rbx, r9
0x180013539  test    edx, edx
0x18001353b  jz      short loc_180013544
0x18001353d  mov     eax, 8002000Bh
0x180013542  jmp     short loc_180013591
0x180013544  test    rbx, rbx
0x180013547  jnz     short loc_180013550
0x180013549  mov     eax, 80004003h
0x18001354e  jmp     short loc_180013591
0x180013550  mov     rcx, cs:qword_18002F2E8
0x180013557  xor     eax, eax
0x180013559  test    rcx, rcx
0x18001355c  jnz     short loc_180013574
0x18001355e  mov     edx, r8d; lcid
0x180013561  lea     rcx, ?_tih@?$IDispatchImpl@UIDiagnosisText@@$1?_GUID_f7c33982_17fe_4472_ac19_8113f5a9cf78@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180013568  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001356d  mov     rcx, cs:qword_18002F2E8
0x180013574  mov     [rbx], rcx
0x180013577  mov     rcx, cs:qword_18002F2E8
0x18001357e  test    rcx, rcx
0x180013581  jz      short loc_180013591
0x180013583  mov     rax, [rcx]
0x180013586  mov     rax, [rax+8]
0x18001358a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001358f  xor     eax, eax
0x180013591  add     rsp, 20h
0x180013595  pop     rbx
0x180013596  retn
```
