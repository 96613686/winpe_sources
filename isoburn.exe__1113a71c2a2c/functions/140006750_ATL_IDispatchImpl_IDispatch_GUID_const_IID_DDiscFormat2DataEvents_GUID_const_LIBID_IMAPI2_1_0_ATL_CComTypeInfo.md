# ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140006750`
- end: `0x1400067eb`
- name: `?Invoke@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400058e4`
- `0x140006750`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::Invoke(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        LCID a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v11; // rcx
  __int64 result; // rax

  v11 = qword_1400160E8;
  if ( !qword_1400160E8 || (result = 0, !qword_1400160F8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_1400160E8;
  }
  if ( v11 )
    return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)v11 + 88LL))(
             v11,
             a1,
             a2,
             a5,
             a6,
             a7,
             a8,
             a9);
  return result;
}

```

## disassembly

```asm
0x140006750  mov     [rsp+arg_0], rbx
0x140006755  push    rdi
0x140006756  sub     rsp, 50h
0x14000675a  mov     rdi, rcx
0x14000675d  mov     ebx, edx
0x14000675f  mov     rcx, cs:qword_1400160E8
0x140006766  test    rcx, rcx
0x140006769  jz      short loc_140006776
0x14000676b  xor     eax, eax
0x14000676d  cmp     cs:qword_1400160F8, rax
0x140006774  jnz     short loc_14000678C
0x140006776  mov     edx, r9d; lcid
0x140006779  lea     rcx, ?_tih@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140006780  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140006785  mov     rcx, cs:qword_1400160E8
0x14000678c  test    rcx, rcx
0x14000678f  jz      short loc_1400067E0
0x140006791  mov     rdx, [rsp+58h+arg_40]
0x140006799  mov     r8d, ebx
0x14000679c  mov     rax, [rcx]
0x14000679f  movzx   r9d, [rsp+58h+arg_20]
0x1400067a8  mov     [rsp+58h+var_20], rdx
0x1400067ad  mov     rdx, [rsp+58h+arg_38]
0x1400067b5  mov     rax, [rax+58h]
0x1400067b9  mov     [rsp+58h+var_28], rdx
0x1400067be  mov     rdx, [rsp+58h+arg_30]
0x1400067c6  mov     [rsp+58h+var_30], rdx
0x1400067cb  mov     rdx, [rsp+58h+arg_28]
0x1400067d3  mov     [rsp+58h+var_38], rdx
0x1400067d8  mov     rdx, rdi
0x1400067db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067e0  mov     rbx, [rsp+58h+arg_0]
0x1400067e5  add     rsp, 50h
0x1400067e9  pop     rdi
0x1400067ea  retn
```
