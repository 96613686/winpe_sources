# ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180004488`
- end: `0x180004548`
- name: `?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `192`
- prototype: `__int64 __usercall@<rax>(ATL::CComTypeInfoHolder *__hidden this@<rcx>, struct IDispatch *@<rdx>, int@<r8d>, const struct _GUID *@<r9>, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002920`
- `0x1800031d0`
- `0x180003e20`
- `0x180005310`
- `0x180007120`

## callees

- `0x1800043a0`
- `0x180004488`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x1800044a2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800044a2`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::Invoke(
        ATL::CComTypeInfoHolder *this,
        struct IDispatch *a2,
        unsigned int a3,
        struct ITypeInfo *a4,
        LCID a5,
        unsigned __int16 a6,
        struct tagDISPPARAMS *a7,
        struct tagVARIANT *a8,
        struct tagEXCEPINFO *a9,
        unsigned int *a10)
{
  unsigned int TI; // eax
  struct ITypeInfo *v14; // rdi
  unsigned int v15; // ebx
  struct ITypeInfo *v17; // [rsp+98h] [rbp+20h] BYREF

  v17 = a4;
  SetErrorInfo(0, 0);
  v17 = 0;
  TI = ATL::CComTypeInfoHolder::GetTI(this, a5, &v17);
  v14 = v17;
  v15 = TI;
  if ( v17 )
  {
    v15 = ((__int64 (__fastcall *)(struct ITypeInfo *, struct IDispatch *, _QWORD, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))v17->lpVtbl->Invoke)(
            v17,
            a2,
            a3,
            a6,
            a7,
            a8,
            a9,
            a10);
    ((void (__fastcall *)(struct ITypeInfo *))v14->lpVtbl->Release)(v14);
  }
  return v15;
}

```

## disassembly

```asm
0x180004488  mov     [rsp+arg_18], r9
0x18000448d  push    rbx
0x18000448e  push    rbp
0x18000448f  push    rsi
0x180004490  push    rdi
0x180004491  sub     rsp, 58h
0x180004495  mov     rbp, rdx
0x180004498  mov     rbx, rcx
0x18000449b  xor     edx, edx; perrinfo
0x18000449d  xor     ecx, ecx; dwReserved
0x18000449f  mov     esi, r8d
0x1800044a2  call    cs:__imp_SetErrorInfo
0x1800044a8  mov     edx, [rsp+78h+arg_20]; unsigned int
0x1800044af  lea     r8, [rsp+78h+arg_18]; struct ITypeInfo **
0x1800044b7  mov     rcx, rbx; this
0x1800044ba  mov     [rsp+78h+arg_18], 0
0x1800044c6  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)
0x1800044cb  mov     rdi, [rsp+78h+arg_18]
0x1800044d3  mov     ebx, eax
0x1800044d5  test    rdi, rdi
0x1800044d8  jz      short loc_18000453D
0x1800044da  mov     rcx, [rsp+78h+arg_48]
0x1800044e2  mov     r8d, esi
0x1800044e5  mov     rdx, [rsp+78h+arg_38]
0x1800044ed  mov     rax, [rdi]
0x1800044f0  movzx   r9d, [rsp+78h+arg_28]
0x1800044f9  mov     [rsp+78h+var_40], rcx
0x1800044fe  mov     rcx, [rsp+78h+arg_40]
0x180004506  mov     rax, [rax+58h]
0x18000450a  mov     [rsp+78h+var_48], rcx
0x18000450f  mov     rcx, rdi
0x180004512  mov     [rsp+78h+var_50], rdx
0x180004517  mov     rdx, [rsp+78h+arg_30]
0x18000451f  mov     [rsp+78h+var_58], rdx
0x180004524  mov     rdx, rbp
0x180004527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000452c  mov     rdx, [rdi]
0x18000452f  mov     ebx, eax
0x180004531  mov     rcx, rdi
0x180004534  mov     rax, [rdx+10h]
0x180004538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000453d  mov     eax, ebx
0x18000453f  add     rsp, 58h
0x180004543  pop     rdi
0x180004544  pop     rsi
0x180004545  pop     rbp
0x180004546  pop     rbx
0x180004547  retn
```
