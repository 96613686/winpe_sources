# ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18001bf78`
- end: `0x18001c013`
- name: `?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct IDispatch *, int, const struct _GUID *, LCID lcid, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `17`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001bd50`
- `0x18001bdc0`
- `0x18001be30`
- `0x18001bea0`
- `0x18001bf10`
- `0x180026f80`
- `0x180028860`
- `0x18002ad30`
- `0x18002e760`
- `0x18002e7d0`
- `0x1800338f0`
- `0x180033960`
- `0x180038250`
- `0x1800382c0`
- `0x18003dad0`
- `0x18003db40`
- `0x180044d60`

## callees

- `0x18001b910`
- `0x18001bf78`
- `0x18004a010`

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
0x18001bf78  mov     [rsp+arg_0], rbx
0x18001bf7d  mov     [rsp+arg_8], rsi
0x18001bf82  push    rdi
0x18001bf83  sub     rsp, 50h
0x18001bf87  cmp     qword ptr [rcx+18h], 0
0x18001bf8c  mov     edi, r8d
0x18001bf8f  mov     rsi, rdx
0x18001bf92  mov     rbx, rcx
0x18001bf95  jz      short loc_18001BF9F
0x18001bf97  xor     eax, eax
0x18001bf99  cmp     [rcx+28h], rax
0x18001bf9d  jnz     short loc_18001BFAB
0x18001bf9f  mov     edx, [rsp+58h+lcid]; lcid
0x18001bfa6  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001bfab  mov     rcx, [rbx+18h]
0x18001bfaf  test    rcx, rcx
0x18001bfb2  jz      short loc_18001C003
0x18001bfb4  mov     rdx, [rsp+58h+arg_48]
0x18001bfbc  mov     r8d, edi
0x18001bfbf  mov     rax, [rcx]
0x18001bfc2  movzx   r9d, [rsp+58h+arg_28]
0x18001bfcb  mov     [rsp+58h+var_20], rdx
0x18001bfd0  mov     rdx, [rsp+58h+arg_40]
0x18001bfd8  mov     rax, [rax+58h]
0x18001bfdc  mov     [rsp+58h+var_28], rdx
0x18001bfe1  mov     rdx, [rsp+58h+arg_38]
0x18001bfe9  mov     [rsp+58h+var_30], rdx
0x18001bfee  mov     rdx, [rsp+58h+arg_30]
0x18001bff6  mov     [rsp+58h+var_38], rdx
0x18001bffb  mov     rdx, rsi
0x18001bffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c003  mov     rbx, [rsp+58h+arg_0]
0x18001c008  mov     rsi, [rsp+58h+arg_8]
0x18001c00d  add     rsp, 50h
0x18001c011  pop     rdi
0x18001c012  retn
```
