# ATL::IDispatchImpl<IRepairInfo,&__s_GUID const _GUID_53f9a461_08a2_4203_9ea5_db567ab2e3ba,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180013680`
- end: `0x1800136e7`
- name: `?GetTypeInfo@?$IDispatchImpl@UIRepairInfo@@$1?_GUID_53f9a461_08a2_4203_9ea5_db567ab2e3ba@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800131d8`
- `0x180013680`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IRepairInfo,&__s_GUID const _GUID_53f9a461_08a2_4203_9ea5_db567ab2e3ba,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_18002F1E8;
  result = 0;
  if ( !qword_18002F1E8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IRepairInfo,&__s_GUID const _GUID_53f9a461_08a2_4203_9ea5_db567ab2e3ba,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_18002F1E8;
  }
  *a4 = v6;
  if ( qword_18002F1E8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002F1E8 + 8LL))(qword_18002F1E8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013680  push    rbx
0x180013682  sub     rsp, 20h
0x180013686  mov     rbx, r9
0x180013689  test    edx, edx
0x18001368b  jz      short loc_180013694
0x18001368d  mov     eax, 8002000Bh
0x180013692  jmp     short loc_1800136E1
0x180013694  test    rbx, rbx
0x180013697  jnz     short loc_1800136A0
0x180013699  mov     eax, 80004003h
0x18001369e  jmp     short loc_1800136E1
0x1800136a0  mov     rcx, cs:qword_18002F1E8
0x1800136a7  xor     eax, eax
0x1800136a9  test    rcx, rcx
0x1800136ac  jnz     short loc_1800136C4
0x1800136ae  mov     edx, r8d; lcid
0x1800136b1  lea     rcx, ?_tih@?$IDispatchImpl@UIRepairInfo@@$1?_GUID_53f9a461_08a2_4203_9ea5_db567ab2e3ba@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800136b8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800136bd  mov     rcx, cs:qword_18002F1E8
0x1800136c4  mov     [rbx], rcx
0x1800136c7  mov     rcx, cs:qword_18002F1E8
0x1800136ce  test    rcx, rcx
0x1800136d1  jz      short loc_1800136E1
0x1800136d3  mov     rax, [rcx]
0x1800136d6  mov     rax, [rax+8]
0x1800136da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136df  xor     eax, eax
0x1800136e1  add     rsp, 20h
0x1800136e5  pop     rbx
0x1800136e6  retn
```
