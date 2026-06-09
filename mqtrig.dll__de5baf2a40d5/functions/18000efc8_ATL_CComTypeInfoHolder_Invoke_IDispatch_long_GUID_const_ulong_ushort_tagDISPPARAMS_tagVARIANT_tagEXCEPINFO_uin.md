# ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18000efc8`
- end: `0x18000f063`
- name: `?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *this, struct IDispatch *, unsigned int, const struct _GUID *, LCID lcid, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000eda0`
- `0x18000ee10`
- `0x18000ee80`
- `0x18000eef0`
- `0x18000ef60`

## callees

- `0x18000ea78`
- `0x18000efc8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::Invoke(
        ATL::CComTypeInfoHolder *this,
        struct IDispatch *a2,
        unsigned int a3,
        const struct _GUID *a4,
        LCID lcid,
        unsigned __int16 a6,
        struct tagDISPPARAMS *a7,
        struct tagVARIANT *a8,
        struct tagEXCEPINFO *a9,
        unsigned int *a10)
{
  __int64 result; // rax
  __int64 v14; // rcx

  if ( !*((_QWORD *)this + 3) || (result = 0, !*((_QWORD *)this + 5)) )
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  v14 = *((_QWORD *)this + 3);
  if ( v14 )
    return (*(__int64 (__fastcall **)(__int64, struct IDispatch *, _QWORD, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))(*(_QWORD *)v14 + 88LL))(
             v14,
             a2,
             a3,
             a6,
             a7,
             a8,
             a9,
             a10);
  return result;
}

```

## disassembly

```asm
0x18000efc8  mov     [rsp+arg_0], rbx
0x18000efcd  mov     [rsp+arg_8], rsi
0x18000efd2  push    rdi
0x18000efd3  sub     rsp, 50h
0x18000efd7  cmp     qword ptr [rcx+18h], 0
0x18000efdc  mov     edi, r8d
0x18000efdf  mov     rsi, rdx
0x18000efe2  mov     rbx, rcx
0x18000efe5  jz      short loc_18000EFEF
0x18000efe7  xor     eax, eax
0x18000efe9  cmp     [rcx+28h], rax
0x18000efed  jnz     short loc_18000EFFB
0x18000efef  mov     edx, [rsp+58h+lcid]; lcid
0x18000eff6  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000effb  mov     rcx, [rbx+18h]
0x18000efff  test    rcx, rcx
0x18000f002  jz      short loc_18000F053
0x18000f004  mov     rdx, [rsp+58h+arg_48]
0x18000f00c  mov     r8d, edi
0x18000f00f  mov     rax, [rcx]
0x18000f012  movzx   r9d, [rsp+58h+arg_28]
0x18000f01b  mov     [rsp+58h+var_20], rdx
0x18000f020  mov     rdx, [rsp+58h+arg_40]
0x18000f028  mov     rax, [rax+58h]
0x18000f02c  mov     [rsp+58h+var_28], rdx
0x18000f031  mov     rdx, [rsp+58h+arg_38]
0x18000f039  mov     [rsp+58h+var_30], rdx
0x18000f03e  mov     rdx, [rsp+58h+arg_30]
0x18000f046  mov     [rsp+58h+var_38], rdx
0x18000f04b  mov     rdx, rsi
0x18000f04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f053  mov     rbx, [rsp+58h+arg_0]
0x18000f058  mov     rsi, [rsp+58h+arg_8]
0x18000f05d  add     rsp, 50h
0x18000f061  pop     rdi
0x18000f062  retn
```
