# ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180013e38`
- end: `0x180013ed3`
- name: `?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *this, struct IDispatch *, unsigned int, const struct _GUID *, LCID lcid, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `10`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800139e0`
- `0x180013a50`
- `0x180013ac0`
- `0x180013b30`
- `0x180013ba0`
- `0x180013c10`
- `0x180013c80`
- `0x180013cf0`
- `0x180013d60`
- `0x180013dd0`

## callees

- `0x1800131d8`
- `0x180013e38`
- `0x180021010`

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
0x180013e38  mov     [rsp+arg_0], rbx
0x180013e3d  mov     [rsp+arg_8], rsi
0x180013e42  push    rdi
0x180013e43  sub     rsp, 50h
0x180013e47  cmp     qword ptr [rcx+18h], 0
0x180013e4c  mov     edi, r8d
0x180013e4f  mov     rsi, rdx
0x180013e52  mov     rbx, rcx
0x180013e55  jz      short loc_180013E5F
0x180013e57  xor     eax, eax
0x180013e59  cmp     [rcx+28h], rax
0x180013e5d  jnz     short loc_180013E6B
0x180013e5f  mov     edx, [rsp+58h+lcid]; lcid
0x180013e66  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180013e6b  mov     rcx, [rbx+18h]
0x180013e6f  test    rcx, rcx
0x180013e72  jz      short loc_180013EC3
0x180013e74  mov     rdx, [rsp+58h+arg_48]
0x180013e7c  mov     r8d, edi
0x180013e7f  mov     rax, [rcx]
0x180013e82  movzx   r9d, [rsp+58h+arg_28]
0x180013e8b  mov     [rsp+58h+var_20], rdx
0x180013e90  mov     rdx, [rsp+58h+arg_40]
0x180013e98  mov     rax, [rax+58h]
0x180013e9c  mov     [rsp+58h+var_28], rdx
0x180013ea1  mov     rdx, [rsp+58h+arg_38]
0x180013ea9  mov     [rsp+58h+var_30], rdx
0x180013eae  mov     rdx, [rsp+58h+arg_30]
0x180013eb6  mov     [rsp+58h+var_38], rdx
0x180013ebb  mov     rdx, rsi
0x180013ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ec3  mov     rbx, [rsp+58h+arg_0]
0x180013ec8  mov     rsi, [rsp+58h+arg_8]
0x180013ecd  add     rsp, 50h
0x180013ed1  pop     rdi
0x180013ed2  retn
```
