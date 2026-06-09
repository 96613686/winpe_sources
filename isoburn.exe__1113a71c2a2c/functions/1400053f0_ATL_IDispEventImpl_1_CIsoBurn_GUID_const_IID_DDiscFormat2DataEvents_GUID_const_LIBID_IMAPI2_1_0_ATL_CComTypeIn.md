# ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetFuncInfoFromId(_GUID const &,long,ulong,ATL::_ATL_FUNC_INFO &)

- ea: `0x1400053f0`
- end: `0x1400054ef`
- name: `?GetFuncInfoFromId@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@JKAEAU_ATL_FUNC_INFO@2@@Z`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140004300`
- `0x1400053f0`
- `0x1400058e4`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetFuncInfoFromId(
        __int64 a1,
        __int64 a2,
        int a3,
        LCID a4,
        struct ATL::_ATL_FUNC_INFO *a5)
{
  GUID v6; // xmm1
  struct ITypeInfo *v7; // rbx
  __int64 result; // rax
  const struct _GUID *v9; // rdx
  unsigned int v10; // r9d
  unsigned int FuncInfoFromId; // edi

  if ( off_140016118->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&off_140016118->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)off_140016118->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&off_140016118->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid = *(GUID *)(a1 + 8);
    v6 = *(GUID *)(a1 + 24);
    off_140016118 = &ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid;
    ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih = &ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid;
    ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid = v6;
    word_140016120 = *(_WORD *)(a1 + 40);
    word_140016122 = *(_WORD *)(a1 + 42);
  }
  v7 = qword_140016128;
  if ( qword_140016128
    || (result = ATL::CComTypeInfoHolder::GetTI(
                   (ATL::CComTypeInfoHolder *)&ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
                   a4),
        (v7 = qword_140016128) != 0) )
  {
    ((void (__fastcall *)(struct ITypeInfo *))v7->lpVtbl->AddRef)(v7);
  }
  else if ( (int)result < 0 )
  {
    return result;
  }
  FuncInfoFromId = ATL::AtlGetFuncInfoFromId(v7, v9, a3, v10, a5);
  if ( v7 )
    ((void (__fastcall *)(struct ITypeInfo *))v7->lpVtbl->Release)(v7);
  return FuncInfoFromId;
}

```

## disassembly

```asm
0x1400053f0  mov     [rsp+arg_0], rbx
0x1400053f5  push    rdi
0x1400053f6  sub     rsp, 30h
0x1400053fa  mov     rdx, cs:off_140016118
0x140005401  mov     edi, r8d
0x140005404  mov     eax, cs:GUID_NULL.Data1
0x14000540a  cmp     [rdx], eax
0x14000540c  jnz     short loc_140005479
0x14000540e  mov     eax, dword ptr cs:GUID_NULL.Data2
0x140005414  cmp     [rdx+4], eax
0x140005417  jnz     short loc_140005479
0x140005419  mov     eax, dword ptr cs:GUID_NULL.Data4
0x14000541f  cmp     [rdx+8], eax
0x140005422  jnz     short loc_140005479
0x140005424  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x14000542a  cmp     [rdx+0Ch], eax
0x14000542d  jnz     short loc_140005479
0x14000542f  movups  xmm0, xmmword ptr [rcx+8]
0x140005433  lea     rax, ?m_InnerLibid@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A; _GUID ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid
0x14000543a  movdqu  xmmword ptr cs:?m_InnerLibid@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A.Data1, xmm0; _GUID ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid ...
0x140005442  movups  xmm1, xmmword ptr [rcx+18h]
0x140005446  mov     cs:off_140016118, rax
0x14000544d  lea     rax, ?m_InnerIid@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A; _GUID ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid
0x140005454  mov     cs:?_tih@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A, rax; ATL::CComTypeInfoHolder ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih
0x14000545b  movdqu  xmmword ptr cs:?m_InnerIid@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A.Data1, xmm1; _GUID ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid ...
0x140005463  movzx   eax, word ptr [rcx+28h]
0x140005467  mov     cs:word_140016120, ax
0x14000546e  movzx   eax, word ptr [rcx+2Ah]
0x140005472  mov     cs:word_140016122, ax
0x140005479  mov     rbx, cs:qword_140016128
0x140005480  xor     eax, eax
0x140005482  test    rbx, rbx
0x140005485  jnz     short loc_1400054A2
0x140005487  mov     edx, r9d; lcid
0x14000548a  lea     rcx, ?_tih@?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140005491  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140005496  mov     rbx, cs:qword_140016128
0x14000549d  test    rbx, rbx
0x1400054a0  jz      short loc_1400054B3
0x1400054a2  mov     rax, [rbx]
0x1400054a5  mov     rcx, rbx
0x1400054a8  mov     rax, [rax+8]
0x1400054ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054b1  jmp     short loc_1400054B7
0x1400054b3  test    eax, eax
0x1400054b5  js      short loc_1400054E4
0x1400054b7  mov     rax, [rsp+38h+arg_20]
0x1400054bc  mov     r8d, edi; int
0x1400054bf  mov     rcx, rbx; struct ITypeInfo *
0x1400054c2  mov     [rsp+38h+var_18], rax; struct ATL::_ATL_FUNC_INFO *
0x1400054c7  call    ?AtlGetFuncInfoFromId@ATL@@YAJPEAUITypeInfo@@AEBU_GUID@@JKAEAU_ATL_FUNC_INFO@1@@Z; ATL::AtlGetFuncInfoFromId(ITypeInfo *,_GUID const &,long,ulong,ATL::_ATL_FUNC_INFO &)
0x1400054cc  mov     edi, eax
0x1400054ce  test    rbx, rbx
0x1400054d1  jz      short loc_1400054E2
0x1400054d3  mov     rcx, [rbx]
0x1400054d6  mov     rax, [rcx+10h]
0x1400054da  mov     rcx, rbx
0x1400054dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054e2  mov     eax, edi
0x1400054e4  mov     rbx, [rsp+38h+arg_0]
0x1400054e9  add     rsp, 30h
0x1400054ed  pop     rdi
0x1400054ee  retn
```
