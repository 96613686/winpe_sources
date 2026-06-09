# ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetFuncInfoFromId(_GUID const &,long,ulong,ATL::_ATL_FUNC_INFO &)

- ea: `0x1400052e0`
- end: `0x1400053df`
- name: `?GetFuncInfoFromId@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@JKAEAU_ATL_FUNC_INFO@2@@Z`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140004300`
- `0x1400052e0`
- `0x1400058e4`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::GetFuncInfoFromId(
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

  if ( off_140016098->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&off_140016098->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)off_140016098->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&off_140016098->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid = *(GUID *)(a1 + 8);
    v6 = *(GUID *)(a1 + 24);
    off_140016098 = &ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid;
    ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih = &ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid;
    ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid = v6;
    word_1400160A0 = *(_WORD *)(a1 + 40);
    word_1400160A2 = *(_WORD *)(a1 + 42);
  }
  v7 = qword_1400160A8;
  if ( qword_1400160A8
    || (result = ATL::CComTypeInfoHolder::GetTI(
                   (ATL::CComTypeInfoHolder *)&ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
                   a4),
        (v7 = qword_1400160A8) != 0) )
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
0x1400052e0  mov     [rsp+arg_0], rbx
0x1400052e5  push    rdi
0x1400052e6  sub     rsp, 30h
0x1400052ea  mov     rdx, cs:off_140016098
0x1400052f1  mov     edi, r8d
0x1400052f4  mov     eax, cs:GUID_NULL.Data1
0x1400052fa  cmp     [rdx], eax
0x1400052fc  jnz     short loc_140005369
0x1400052fe  mov     eax, dword ptr cs:GUID_NULL.Data2
0x140005304  cmp     [rdx+4], eax
0x140005307  jnz     short loc_140005369
0x140005309  mov     eax, dword ptr cs:GUID_NULL.Data4
0x14000530f  cmp     [rdx+8], eax
0x140005312  jnz     short loc_140005369
0x140005314  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x14000531a  cmp     [rdx+0Ch], eax
0x14000531d  jnz     short loc_140005369
0x14000531f  movups  xmm0, xmmword ptr [rcx+8]
0x140005323  lea     rax, ?m_InnerLibid@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A; _GUID ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid
0x14000532a  movdqu  xmmword ptr cs:?m_InnerLibid@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A.Data1, xmm0; _GUID ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerLibid ...
0x140005332  movups  xmm1, xmmword ptr [rcx+18h]
0x140005336  mov     cs:off_140016098, rax
0x14000533d  lea     rax, ?m_InnerIid@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A; _GUID ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid
0x140005344  mov     cs:?_tih@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A, rax; ATL::CComTypeInfoHolder ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih
0x14000534b  movdqu  xmmword ptr cs:?m_InnerIid@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1U_GUID@@A.Data1, xmm1; _GUID ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::m_InnerIid ...
0x140005353  movzx   eax, word ptr [rcx+28h]
0x140005357  mov     cs:word_1400160A0, ax
0x14000535e  movzx   eax, word ptr [rcx+2Ah]
0x140005362  mov     cs:word_1400160A2, ax
0x140005369  mov     rbx, cs:qword_1400160A8
0x140005370  xor     eax, eax
0x140005372  test    rbx, rbx
0x140005375  jnz     short loc_140005392
0x140005377  mov     edx, r9d; lcid
0x14000537a  lea     rcx, ?_tih@?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140005381  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140005386  mov     rbx, cs:qword_1400160A8
0x14000538d  test    rbx, rbx
0x140005390  jz      short loc_1400053A3
0x140005392  mov     rax, [rbx]
0x140005395  mov     rcx, rbx
0x140005398  mov     rax, [rax+8]
0x14000539c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053a1  jmp     short loc_1400053A7
0x1400053a3  test    eax, eax
0x1400053a5  js      short loc_1400053D4
0x1400053a7  mov     rax, [rsp+38h+arg_20]
0x1400053ac  mov     r8d, edi; int
0x1400053af  mov     rcx, rbx; struct ITypeInfo *
0x1400053b2  mov     [rsp+38h+var_18], rax; struct ATL::_ATL_FUNC_INFO *
0x1400053b7  call    ?AtlGetFuncInfoFromId@ATL@@YAJPEAUITypeInfo@@AEBU_GUID@@JKAEAU_ATL_FUNC_INFO@1@@Z; ATL::AtlGetFuncInfoFromId(ITypeInfo *,_GUID const &,long,ulong,ATL::_ATL_FUNC_INFO &)
0x1400053bc  mov     edi, eax
0x1400053be  test    rbx, rbx
0x1400053c1  jz      short loc_1400053D2
0x1400053c3  mov     rcx, [rbx]
0x1400053c6  mov     rax, [rcx+10h]
0x1400053ca  mov     rcx, rbx
0x1400053cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053d2  mov     eax, edi
0x1400053d4  mov     rbx, [rsp+38h+arg_0]
0x1400053d9  add     rsp, 30h
0x1400053dd  pop     rdi
0x1400053de  retn
```
