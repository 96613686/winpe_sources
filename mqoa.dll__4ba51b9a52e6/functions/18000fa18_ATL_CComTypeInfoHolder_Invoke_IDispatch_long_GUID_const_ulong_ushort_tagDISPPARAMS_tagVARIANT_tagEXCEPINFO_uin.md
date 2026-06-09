# ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18000fa18`
- end: `0x18000fab3`
- name: `?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct IDispatch *, int, const struct _GUID *, LCID lcid, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `15`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f470`
- `0x18000f4e0`
- `0x18000f550`
- `0x18000f5c0`
- `0x18000f630`
- `0x18000f6a0`
- `0x18000f710`
- `0x18000f780`
- `0x18000f7f0`
- `0x18000f860`
- `0x18000f8d0`
- `0x18000f940`
- `0x18000f9b0`
- `0x180022ea0`
- `0x180025eb0`

## callees

- `0x18000ec10`
- `0x18000fa18`
- `0x180029010`

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
0x18000fa18  mov     [rsp+arg_0], rbx
0x18000fa1d  mov     [rsp+arg_8], rsi
0x18000fa22  push    rdi
0x18000fa23  sub     rsp, 50h
0x18000fa27  cmp     qword ptr [rcx+18h], 0
0x18000fa2c  mov     edi, r8d
0x18000fa2f  mov     rsi, rdx
0x18000fa32  mov     rbx, rcx
0x18000fa35  jz      short loc_18000FA3F
0x18000fa37  xor     eax, eax
0x18000fa39  cmp     [rcx+28h], rax
0x18000fa3d  jnz     short loc_18000FA4B
0x18000fa3f  mov     edx, [rsp+58h+lcid]; lcid
0x18000fa46  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000fa4b  mov     rcx, [rbx+18h]
0x18000fa4f  test    rcx, rcx
0x18000fa52  jz      short loc_18000FAA3
0x18000fa54  mov     rdx, [rsp+58h+arg_48]
0x18000fa5c  mov     r8d, edi
0x18000fa5f  mov     rax, [rcx]
0x18000fa62  movzx   r9d, [rsp+58h+arg_28]
0x18000fa6b  mov     [rsp+58h+var_20], rdx
0x18000fa70  mov     rdx, [rsp+58h+arg_40]
0x18000fa78  mov     rax, [rax+58h]
0x18000fa7c  mov     [rsp+58h+var_28], rdx
0x18000fa81  mov     rdx, [rsp+58h+arg_38]
0x18000fa89  mov     [rsp+58h+var_30], rdx
0x18000fa8e  mov     rdx, [rsp+58h+arg_30]
0x18000fa96  mov     [rsp+58h+var_38], rdx
0x18000fa9b  mov     rdx, rsi
0x18000fa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faa3  mov     rbx, [rsp+58h+arg_0]
0x18000faa8  mov     rsi, [rsp+58h+arg_8]
0x18000faad  add     rsp, 50h
0x18000fab1  pop     rdi
0x18000fab2  retn
```
