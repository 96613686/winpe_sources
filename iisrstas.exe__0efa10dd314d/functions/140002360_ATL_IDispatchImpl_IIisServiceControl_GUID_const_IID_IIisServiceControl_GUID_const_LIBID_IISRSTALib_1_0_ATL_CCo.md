# ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140002360`
- end: `0x1400023f4`
- name: `?Invoke@?$IDispatchImpl@UIIisServiceControl@@$1?IID_IIisServiceControl@@3U_GUID@@B$1?LIBID_IISRSTALib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400020ec`
- `0x140002360`
- `0x140006010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IIisServiceControl,&_GUID const IID_IIisServiceControl,&_GUID const LIBID_IISRSTALib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_14000A0A8;
  if ( !qword_14000A0A8 || (result = 0, !qword_14000A0B8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(qword_14000A0A8, a4);
    v11 = qword_14000A0A8;
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
0x140002360  mov     [rsp+arg_0], rbx
0x140002365  push    rdi
0x140002366  sub     rsp, 50h
0x14000236a  mov     rdi, rcx
0x14000236d  mov     ebx, edx
0x14000236f  mov     rcx, cs:qword_14000A0A8; this
0x140002376  test    rcx, rcx
0x140002379  jz      short loc_140002386
0x14000237b  xor     eax, eax
0x14000237d  cmp     cs:qword_14000A0B8, rax
0x140002384  jnz     short loc_140002395
0x140002386  mov     edx, r9d; unsigned int
0x140002389  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x14000238e  mov     rcx, cs:qword_14000A0A8
0x140002395  test    rcx, rcx
0x140002398  jz      short loc_1400023E9
0x14000239a  mov     rdx, [rsp+58h+arg_40]
0x1400023a2  mov     r8d, ebx
0x1400023a5  mov     rax, [rcx]
0x1400023a8  movzx   r9d, [rsp+58h+arg_20]
0x1400023b1  mov     [rsp+58h+var_20], rdx
0x1400023b6  mov     rdx, [rsp+58h+arg_38]
0x1400023be  mov     rax, [rax+58h]
0x1400023c2  mov     [rsp+58h+var_28], rdx
0x1400023c7  mov     rdx, [rsp+58h+arg_30]
0x1400023cf  mov     [rsp+58h+var_30], rdx
0x1400023d4  mov     rdx, [rsp+58h+arg_28]
0x1400023dc  mov     [rsp+58h+var_38], rdx
0x1400023e1  mov     rdx, rdi
0x1400023e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023e9  mov     rbx, [rsp+58h+arg_0]
0x1400023ee  add     rsp, 50h
0x1400023f2  pop     rdi
0x1400023f3  retn
```
