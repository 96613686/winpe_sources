# ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180004790`
- end: `0x1800047fe`
- name: `?GetIDsOfNames@?$IDispatchImpl@UILogScripting@@$1?IID_ILogScripting@@3U_GUID@@B$1?LIBID_IISLog@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002734`
- `0x180004790`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        ITypeLib *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        LCID a5,
        __int64 a6)
{
  unsigned int TI; // eax
  struct ITypeInfo *v9; // rbx
  unsigned int v10; // edi
  struct ITypeInfo *v12; // [rsp+30h] [rbp-38h] BYREF

  v12 = 0;
  TI = ATL::CComTypeInfoHolder::GetTI(a1, a5, &v12);
  v9 = v12;
  v10 = TI;
  if ( v12 )
  {
    v10 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, _QWORD, __int64))v12->lpVtbl->GetIDsOfNames)(
            v12,
            a3,
            a4,
            a6);
    ((void (__fastcall *)(struct ITypeInfo *))v9->lpVtbl->Release)(v9);
  }
  return v10;
}

```

## disassembly

```asm
0x180004790  push    rbx
0x180004792  push    rbp
0x180004793  push    rsi
0x180004794  push    rdi
0x180004795  sub     rsp, 48h
0x180004799  mov     edx, [rsp+68h+arg_20]; unsigned int
0x1800047a0  mov     rbp, r8
0x1800047a3  lea     r8, [rsp+68h+var_38]; struct ITypeInfo **
0x1800047a8  mov     [rsp+68h+var_38], 0
0x1800047b1  mov     esi, r9d
0x1800047b4  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)
0x1800047b9  mov     rbx, [rsp+68h+var_38]
0x1800047be  mov     edi, eax
0x1800047c0  test    rbx, rbx
0x1800047c3  jz      short loc_1800047F3
0x1800047c5  mov     rax, [rbx]
0x1800047c8  mov     r8d, esi
0x1800047cb  mov     r9, [rsp+68h+arg_28]
0x1800047d3  mov     rdx, rbp
0x1800047d6  mov     rcx, rbx
0x1800047d9  mov     rax, [rax+50h]
0x1800047dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047e2  mov     rdx, [rbx]
0x1800047e5  mov     edi, eax
0x1800047e7  mov     rcx, rbx
0x1800047ea  mov     rax, [rdx+10h]
0x1800047ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f3  mov     eax, edi
0x1800047f5  add     rsp, 48h
0x1800047f9  pop     rdi
0x1800047fa  pop     rsi
0x1800047fb  pop     rbp
0x1800047fc  pop     rbx
0x1800047fd  retn
```
