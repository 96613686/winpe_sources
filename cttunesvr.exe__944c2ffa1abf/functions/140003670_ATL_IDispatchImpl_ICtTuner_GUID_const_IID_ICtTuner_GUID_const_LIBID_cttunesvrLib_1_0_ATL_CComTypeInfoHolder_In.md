# ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140003670`
- end: `0x140003704`
- name: `?Invoke@?$IDispatchImpl@UICtTuner@@$1?IID_ICtTuner@@3U_GUID@@B$1?LIBID_cttunesvrLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400031f4`
- `0x140003670`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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
  struct ITypeInfo *v11; // rcx
  __int64 result; // rax

  v11 = qword_14000B068;
  if ( !qword_14000B068 || (result = 0, !qword_14000B078) )
  {
    result = ATL::CComTypeInfoHolder::GetTI((ATL::CComTypeInfoHolder *)qword_14000B068, a4);
    v11 = qword_14000B068;
  }
  if ( v11 )
    return ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, _QWORD, _QWORD, __int64, __int64, __int64, __int64))v11->lpVtbl->Invoke)(
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
0x140003670  mov     [rsp+arg_0], rbx
0x140003675  push    rdi
0x140003676  sub     rsp, 50h
0x14000367a  mov     rdi, rcx
0x14000367d  mov     ebx, edx
0x14000367f  mov     rcx, cs:qword_14000B068; this
0x140003686  test    rcx, rcx
0x140003689  jz      short loc_140003696
0x14000368b  xor     eax, eax
0x14000368d  cmp     cs:qword_14000B078, rax
0x140003694  jnz     short loc_1400036A5
0x140003696  mov     edx, r9d; unsigned int
0x140003699  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x14000369e  mov     rcx, cs:qword_14000B068
0x1400036a5  test    rcx, rcx
0x1400036a8  jz      short loc_1400036F9
0x1400036aa  mov     rdx, [rsp+58h+arg_40]
0x1400036b2  mov     r8d, ebx
0x1400036b5  mov     rax, [rcx]
0x1400036b8  movzx   r9d, [rsp+58h+arg_20]
0x1400036c1  mov     [rsp+58h+var_20], rdx
0x1400036c6  mov     rdx, [rsp+58h+arg_38]
0x1400036ce  mov     rax, [rax+58h]
0x1400036d2  mov     [rsp+58h+var_28], rdx
0x1400036d7  mov     rdx, [rsp+58h+arg_30]
0x1400036df  mov     [rsp+58h+var_30], rdx
0x1400036e4  mov     rdx, [rsp+58h+arg_28]
0x1400036ec  mov     [rsp+58h+var_38], rdx
0x1400036f1  mov     rdx, rdi
0x1400036f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036f9  mov     rbx, [rsp+58h+arg_0]
0x1400036fe  add     rsp, 50h
0x140003702  pop     rdi
0x140003703  retn
```
