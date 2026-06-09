# ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140006800`
- end: `0x14000689b`
- name: `?Invoke@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400058e4`
- `0x140006800`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_140016068;
  if ( !qword_140016068 || (result = 0, !qword_140016078) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_140016068;
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
0x140006800  mov     [rsp+arg_0], rbx
0x140006805  push    rdi
0x140006806  sub     rsp, 50h
0x14000680a  mov     rdi, rcx
0x14000680d  mov     ebx, edx
0x14000680f  mov     rcx, cs:qword_140016068
0x140006816  test    rcx, rcx
0x140006819  jz      short loc_140006826
0x14000681b  xor     eax, eax
0x14000681d  cmp     cs:qword_140016078, rax
0x140006824  jnz     short loc_14000683C
0x140006826  mov     edx, r9d; lcid
0x140006829  lea     rcx, ?_tih@?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140006830  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140006835  mov     rcx, cs:qword_140016068
0x14000683c  test    rcx, rcx
0x14000683f  jz      short loc_140006890
0x140006841  mov     rdx, [rsp+58h+arg_40]
0x140006849  mov     r8d, ebx
0x14000684c  mov     rax, [rcx]
0x14000684f  movzx   r9d, [rsp+58h+arg_20]
0x140006858  mov     [rsp+58h+var_20], rdx
0x14000685d  mov     rdx, [rsp+58h+arg_38]
0x140006865  mov     rax, [rax+58h]
0x140006869  mov     [rsp+58h+var_28], rdx
0x14000686e  mov     rdx, [rsp+58h+arg_30]
0x140006876  mov     [rsp+58h+var_30], rdx
0x14000687b  mov     rdx, [rsp+58h+arg_28]
0x140006883  mov     [rsp+58h+var_38], rdx
0x140006888  mov     rdx, rdi
0x14000688b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006890  mov     rbx, [rsp+58h+arg_0]
0x140006895  add     rsp, 50h
0x140006899  pop     rdi
0x14000689a  retn
```
