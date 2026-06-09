# ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180004f70`
- end: `0x18000501a`
- name: `?Invoke@?$IDispatchImpl@UILogScripting@@$1?IID_ILogScripting@@3U_GUID@@B$1?LIBID_IISLog@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002734`
- `0x180004f70`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x180004f85`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180004f85`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::Invoke(
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
  ITypeLib *v12; // rcx
  unsigned int TI; // eax
  struct ITypeInfo *v14; // rdi
  unsigned int v15; // ebx
  struct ITypeInfo *v17; // [rsp+50h] [rbp-38h] BYREF

  SetErrorInfo(0, 0);
  v17 = 0;
  TI = ATL::CComTypeInfoHolder::GetTI(v12, a4, &v17);
  v14 = v17;
  v15 = TI;
  if ( v17 )
  {
    v15 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, _QWORD, _QWORD, __int64, __int64, __int64, __int64))v17->lpVtbl->Invoke)(
            v17,
            a1,
            a2,
            a5,
            a6,
            a7,
            a8,
            a9);
    ((void (__fastcall *)(struct ITypeInfo *))v14->lpVtbl->Release)(v14);
  }
  return v15;
}

```

## disassembly

```asm
0x180004f70  push    rbx
0x180004f72  push    rbp
0x180004f73  push    rsi
0x180004f74  push    rdi
0x180004f75  sub     rsp, 68h
0x180004f79  mov     esi, edx
0x180004f7b  mov     rbp, rcx
0x180004f7e  xor     edx, edx; perrinfo
0x180004f80  xor     ecx, ecx; dwReserved
0x180004f82  mov     ebx, r9d
0x180004f85  call    cs:__imp_SetErrorInfo
0x180004f8b  lea     r8, [rsp+88h+var_38]; struct ITypeInfo **
0x180004f90  mov     [rsp+88h+var_38], 0
0x180004f99  mov     edx, ebx; unsigned int
0x180004f9b  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)
0x180004fa0  mov     rdi, [rsp+88h+var_38]
0x180004fa5  mov     ebx, eax
0x180004fa7  test    rdi, rdi
0x180004faa  jz      short loc_18000500F
0x180004fac  mov     rcx, [rsp+88h+arg_40]
0x180004fb4  mov     r8d, esi
0x180004fb7  mov     rdx, [rsp+88h+arg_30]
0x180004fbf  mov     rax, [rdi]
0x180004fc2  movzx   r9d, [rsp+88h+arg_20]
0x180004fcb  mov     [rsp+88h+var_50], rcx
0x180004fd0  mov     rcx, [rsp+88h+arg_38]
0x180004fd8  mov     rax, [rax+58h]
0x180004fdc  mov     [rsp+88h+var_58], rcx
0x180004fe1  mov     rcx, rdi
0x180004fe4  mov     [rsp+88h+var_60], rdx
0x180004fe9  mov     rdx, [rsp+88h+arg_28]
0x180004ff1  mov     [rsp+88h+var_68], rdx
0x180004ff6  mov     rdx, rbp
0x180004ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ffe  mov     rdx, [rdi]
0x180005001  mov     ebx, eax
0x180005003  mov     rcx, rdi
0x180005006  mov     rax, [rdx+10h]
0x18000500a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000500f  mov     eax, ebx
0x180005011  add     rsp, 68h
0x180005015  pop     rdi
0x180005016  pop     rsi
0x180005017  pop     rbp
0x180005018  pop     rbx
0x180005019  retn
```
