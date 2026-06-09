# ATL::IDispatchImpl<IDiagnosticsWaitHandle,&__s_GUID const _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1800135a0`
- end: `0x180013607`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDiagnosticsWaitHandle@@$1?_GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800131d8`
- `0x1800135a0`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDiagnosticsWaitHandle,&__s_GUID const _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_18002F328;
  result = 0;
  if ( !qword_18002F328 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDiagnosticsWaitHandle,&__s_GUID const _GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_18002F328;
  }
  *a4 = v6;
  if ( qword_18002F328 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002F328 + 8LL))(qword_18002F328);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800135a0  push    rbx
0x1800135a2  sub     rsp, 20h
0x1800135a6  mov     rbx, r9
0x1800135a9  test    edx, edx
0x1800135ab  jz      short loc_1800135B4
0x1800135ad  mov     eax, 8002000Bh
0x1800135b2  jmp     short loc_180013601
0x1800135b4  test    rbx, rbx
0x1800135b7  jnz     short loc_1800135C0
0x1800135b9  mov     eax, 80004003h
0x1800135be  jmp     short loc_180013601
0x1800135c0  mov     rcx, cs:qword_18002F328
0x1800135c7  xor     eax, eax
0x1800135c9  test    rcx, rcx
0x1800135cc  jnz     short loc_1800135E4
0x1800135ce  mov     edx, r8d; lcid
0x1800135d1  lea     rcx, ?_tih@?$IDispatchImpl@UIDiagnosticsWaitHandle@@$1?_GUID_4758e4a5_6f20_4615_bc2c_27580cc00e67@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800135d8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800135dd  mov     rcx, cs:qword_18002F328
0x1800135e4  mov     [rbx], rcx
0x1800135e7  mov     rcx, cs:qword_18002F328
0x1800135ee  test    rcx, rcx
0x1800135f1  jz      short loc_180013601
0x1800135f3  mov     rax, [rcx]
0x1800135f6  mov     rax, [rax+8]
0x1800135fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135ff  xor     eax, eax
0x180013601  add     rsp, 20h
0x180013605  pop     rbx
0x180013606  retn
```
