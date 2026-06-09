# Dfdll::CSubscription::GetIconInformation(Dfdll::CString &,uint &)

- ea: `0x18000cac8`
- end: `0x18000d334`
- name: `?GetIconInformation@CSubscription@Dfdll@@QEAAJAEAVCString@2@AEAI@Z`
- size: `2156`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this, struct Dfdll::CString *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004bcc`

## callees

- `0x180002604`
- `0x180003530`
- `0x180009e0c`
- `0x18000a040`
- `0x18000cac8`
- `0x18000d9b8`
- `0x18001efd0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000cdef`
- `ole32!CoTaskMemFree` at `0x18000cf64`
- `ole32!CoTaskMemFree` at `0x18000cf8e`
- `ole32!CoTaskMemFree` at `0x18000d048`
- `ole32!CoTaskMemFree` at `0x18000d072`
- `ole32!CoTaskMemFree` at `0x18000d154`
- `ole32!CoTaskMemFree` at `0x18000d17e`
- `ole32!CoTaskMemFree` at `0x18000d217`
- `ole32!CoTaskMemFree` at `0x18000d244`
- `ole32!CoTaskMemFree` at `0x18000cdef`
- `ole32!CoTaskMemFree` at `0x18000cf64`
- `ole32!CoTaskMemFree` at `0x18000cf8e`
- `ole32!CoTaskMemFree` at `0x18000d048`
- `ole32!CoTaskMemFree` at `0x18000d072`
- `ole32!CoTaskMemFree` at `0x18000d154`
- `ole32!CoTaskMemFree` at `0x18000d17e`
- `ole32!CoTaskMemFree` at `0x18000d217`
- `ole32!CoTaskMemFree` at `0x18000d244`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Dfdll::CSubscription::GetIconInformation(
        Dfdll::CSubscription *this,
        struct Dfdll::CString *a2,
        unsigned int *a3)
{
  int ApplicationManifest; // esi
  __int64 (__fastcall ***v7)(__int64, __int64, __int64 *); // rsi
  __int64 v8; // rdx
  __int64 (__fastcall **v9)(__int64, __int64, __int64 *); // rbx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // r8
  unsigned __int16 *v13; // r14
  unsigned __int16 *v14; // rcx
  __int64 (__fastcall ***v15)(__int64, __int64, __int64 *); // rcx
  void **v17; // [rsp+30h] [rbp-39h] BYREF
  __int64 v18; // [rsp+38h] [rbp-31h] BYREF
  void **v19; // [rsp+40h] [rbp-29h]
  __int64 v20; // [rsp+48h] [rbp-21h] BYREF
  void **v21; // [rsp+50h] [rbp-19h]
  __int64 (__fastcall ***v22)(__int64, __int64, __int64 *); // [rsp+58h] [rbp-11h] BYREF
  void **v23; // [rsp+60h] [rbp-9h]
  LPVOID pv; // [rsp+68h] [rbp-1h] BYREF
  int v25; // [rsp+70h] [rbp+7h]
  char v26; // [rsp+74h] [rbp+Bh]
  void **v27; // [rsp+78h] [rbp+Fh]
  unsigned __int16 *v28; // [rsp+80h] [rbp+17h] BYREF
  int v29; // [rsp+88h] [rbp+1Fh]
  char v30; // [rsp+8Ch] [rbp+23h]
  int v31; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v32; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( !*((_QWORD *)this + 8) )
    return (unsigned int)-2147023893;
  ApplicationManifest = Dfdll::CSubscription::EnsureInitialization(this);
  if ( ApplicationManifest >= 0 )
  {
    v31 = 1;
    ApplicationManifest = Dfdll::CSubscription::CheckShellVisibility(this, &v31);
    if ( ApplicationManifest >= 0 )
    {
      if ( !v31 )
        return (unsigned int)-2147023893;
      if ( *((_QWORD *)this + 22)
        || (ApplicationManifest = Dfdll::CSubscription::LoadApplicationManifest(this), ApplicationManifest >= 0) )
      {
        v22 = 0;
        v21 = &Dfdll::CIUnknownBasedPointer<ISectionEntry>::`vftable';
        v18 = 0;
        v17 = &Dfdll::CIUnknownBasedPointer<IMetadataSectionEntry>::`vftable';
        ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(__int64, __int64, __int64 *)))(**((_QWORD **)this + 22) + 112LL))(
                                *((_QWORD *)this + 22),
                                &v22);
        if ( ApplicationManifest < 0 )
        {
          v18 = 0;
          v17 = &Dfdll::CObject::`vftable';
          v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
          if ( v22 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v22)[2])(v22);
          return (unsigned int)ApplicationManifest;
        }
        if ( !v22 )
        {
          ApplicationManifest = -2147024883;
          v18 = 0;
          v17 = &Dfdll::CObject::`vftable';
          v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
          return (unsigned int)ApplicationManifest;
        }
        v7 = v22;
        v8 = v18;
        v18 = 0;
        v9 = *v22;
        v10 = ((__int64 (__fastcall *)(void ***, __int64, _QWORD))v17[5])(&v17, v8, 0);
        v11 = (*v9)((__int64)v7, v10, &v18);
        ApplicationManifest = v11;
        v12 = v18;
        if ( v11 < 0 )
          v12 = 0;
        v18 = v12;
        if ( v11 < 0 )
        {
          v15 = v22;
          v17 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
          if ( v12 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            v15 = v22;
          }
          v18 = 0;
          v17 = &Dfdll::CObject::`vftable';
          v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
          if ( v15 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v15)[2])(v15);
        }
        else
        {
          v20 = 0;
          v19 = &Dfdll::CIUnknownBasedPointer<IDescriptionMetadataEntry>::`vftable';
          ApplicationManifest = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 112LL))(v12, &v20);
          if ( ApplicationManifest < 0 )
          {
            v19 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v20 = 0;
            v19 = &Dfdll::CObject::`vftable';
            v17 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v18 = 0;
            v17 = &Dfdll::CObject::`vftable';
            v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v22 )
              ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v22)[2])(v22);
            return (unsigned int)ApplicationManifest;
          }
          if ( !v20 )
          {
            ApplicationManifest = -2147024883;
            v20 = 0;
            v19 = &Dfdll::CObject::`vftable';
            v17 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v18 = 0;
            v17 = &Dfdll::CObject::`vftable';
            v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v22 )
              ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v22)[2])(v22);
            return (unsigned int)ApplicationManifest;
          }
          pv = 0;
          v26 = 0;
          v25 = 0;
          v23 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
          ApplicationManifest = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v20 + 56LL))(v20, &pv);
          if ( ApplicationManifest < 0 )
          {
            v23 = &Dfdll::CCOMPointerBase::`vftable';
            if ( pv )
              CoTaskMemFree(pv);
            pv = 0;
            v26 = 0;
            v25 = 0;
            v23 = &Dfdll::CObject::`vftable';
            v19 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v20 = 0;
            v19 = &Dfdll::CObject::`vftable';
            v17 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v18 = 0;
            v17 = &Dfdll::CObject::`vftable';
            v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v22 )
              ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v22)[2])(v22);
            return (unsigned int)ApplicationManifest;
          }
          if ( !pv )
          {
            ApplicationManifest = -2147024883;
            pv = 0;
            v26 = 0;
            v25 = 0;
            v23 = &Dfdll::CObject::`vftable';
            v19 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v20 = 0;
            v19 = &Dfdll::CObject::`vftable';
            v17 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v18 = 0;
            v17 = &Dfdll::CObject::`vftable';
            v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v22 )
              ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v22)[2])(v22);
            return (unsigned int)ApplicationManifest;
          }
          v32 = 0;
          v28 = 0;
          v30 = 0;
          v29 = 0;
          v27 = &Dfdll::CCOMPointer<unsigned short>::`vftable';
          ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *, unsigned __int16 **))(**((_QWORD **)this + 16) + 144LL))(
                                  *((_QWORD *)this + 16),
                                  0,
                                  *((_QWORD *)this + 10),
                                  &v32,
                                  &v28);
          if ( ApplicationManifest < 0 )
          {
            v27 = &Dfdll::CCOMPointerBase::`vftable';
            if ( v28 )
              CoTaskMemFree(v28);
            v28 = 0;
            v30 = 0;
            v29 = 0;
            v27 = &Dfdll::CObject::`vftable';
            v23 = &Dfdll::CCOMPointerBase::`vftable';
            if ( pv )
              CoTaskMemFree(pv);
            pv = 0;
            v26 = 0;
            v25 = 0;
            v23 = &Dfdll::CObject::`vftable';
            v19 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v20 = 0;
            v19 = &Dfdll::CObject::`vftable';
            v17 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v18 = 0;
            v17 = &Dfdll::CObject::`vftable';
            v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v22 )
              ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v22)[2])(v22);
            return (unsigned int)ApplicationManifest;
          }
          ApplicationManifest = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 16) + 152LL))(
                                  *((_QWORD *)this + 16),
                                  v32);
          if ( ApplicationManifest < 0 )
          {
            v27 = &Dfdll::CCOMPointerBase::`vftable';
            if ( v28 )
              CoTaskMemFree(v28);
            v28 = 0;
            v30 = 0;
            v29 = 0;
            v27 = &Dfdll::CObject::`vftable';
            v23 = &Dfdll::CCOMPointerBase::`vftable';
            if ( pv )
              CoTaskMemFree(pv);
            pv = 0;
            v26 = 0;
            v25 = 0;
            v23 = &Dfdll::CObject::`vftable';
            v19 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v20 = 0;
            v19 = &Dfdll::CObject::`vftable';
            v17 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v18 = 0;
            v17 = &Dfdll::CObject::`vftable';
            v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
            if ( v22 )
              ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v22)[2])(v22);
            return (unsigned int)ApplicationManifest;
          }
          v13 = (unsigned __int16 *)pv;
          v14 = v28;
          if ( v28 && pv )
          {
            ApplicationManifest = Dfdll::CString::Assign(a2, v28);
            if ( ApplicationManifest >= 0 )
            {
              ApplicationManifest = Dfdll::CPath::PathAddTail(a2, v13);
              if ( ApplicationManifest >= 0 )
              {
                *a3 = 0;
                ApplicationManifest = 0;
                v27 = &Dfdll::CCOMPointerBase::`vftable';
                if ( v28 )
                  CoTaskMemFree(v28);
                v28 = 0;
                v30 = 0;
                v29 = 0;
                v27 = &Dfdll::CObject::`vftable';
                v23 = &Dfdll::CCOMPointerBase::`vftable';
                if ( pv )
                  CoTaskMemFree(pv);
                pv = 0;
                v26 = 0;
                v25 = 0;
                v23 = &Dfdll::CObject::`vftable';
                v19 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                if ( v20 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                v20 = 0;
                v19 = &Dfdll::CObject::`vftable';
                v17 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                if ( v18 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                v18 = 0;
                v17 = &Dfdll::CObject::`vftable';
                v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
                if ( v22 )
                  ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v22)[2])(v22);
                return (unsigned int)ApplicationManifest;
              }
            }
            v13 = (unsigned __int16 *)pv;
            v14 = v28;
          }
          else
          {
            ApplicationManifest = -2147024809;
          }
          v27 = &Dfdll::CCOMPointerBase::`vftable';
          if ( v14 )
          {
            CoTaskMemFree(v14);
            v13 = (unsigned __int16 *)pv;
          }
          v28 = 0;
          v30 = 0;
          v29 = 0;
          v27 = &Dfdll::CObject::`vftable';
          v23 = &Dfdll::CCOMPointerBase::`vftable';
          if ( v13 )
            CoTaskMemFree(v13);
          pv = 0;
          v26 = 0;
          v25 = 0;
          v23 = &Dfdll::CObject::`vftable';
          v19 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          v20 = 0;
          v19 = &Dfdll::CObject::`vftable';
          v17 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v18 = 0;
          v17 = &Dfdll::CObject::`vftable';
          v21 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
          if ( v22 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, __int64, __int64 *)))(*v22)[2])(v22);
        }
      }
    }
  }
  return (unsigned int)ApplicationManifest;
}

```

## disassembly

```asm
0x18000cac8  mov     [rsp-8+arg_8], rbx
0x18000cacd  push    rbp
0x18000cace  push    rsi
0x18000cacf  push    rdi
0x18000cad0  push    r12
0x18000cad2  push    r13
0x18000cad4  push    r14
0x18000cad6  push    r15
0x18000cad8  lea     rbp, [rsp-27h]
0x18000cadd  sub     rsp, 90h
0x18000cae4  mov     r12, r8
0x18000cae7  mov     r15, rdx
0x18000caea  mov     rdi, rcx
0x18000caed  xor     r13d, r13d
0x18000caf0  cmp     [rcx+40h], r13
0x18000caf4  jnz     short loc_18000CB00
0x18000caf6  mov     esi, 800703EBh
0x18000cafb  jmp     loc_18000D317
0x18000cb00  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000cb05  mov     esi, eax
0x18000cb07  test    eax, eax
0x18000cb09  js      loc_18000D317
0x18000cb0f  mov     [rbp+57h+arg_0], 1
0x18000cb16  lea     rdx, [rbp+57h+arg_0]; int *
0x18000cb1a  mov     rcx, rdi; this
0x18000cb1d  call    ?CheckShellVisibility@CSubscription@Dfdll@@IEAAJAEAH@Z; Dfdll::CSubscription::CheckShellVisibility(int &)
0x18000cb22  mov     esi, eax
0x18000cb24  test    eax, eax
0x18000cb26  js      loc_18000D317
0x18000cb2c  cmp     [rbp+57h+arg_0], r13d
0x18000cb30  jz      short loc_18000CAF6
0x18000cb32  cmp     [rdi+0B0h], r13
0x18000cb39  jnz     short loc_18000CB4D
0x18000cb3b  mov     rcx, rdi; this
0x18000cb3e  call    ?LoadApplicationManifest@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::LoadApplicationManifest(void)
0x18000cb43  mov     esi, eax
0x18000cb45  test    eax, eax
0x18000cb47  js      loc_18000D317
0x18000cb4d  mov     [rbp+57h+var_68], r13
0x18000cb51  lea     rax, ??_7?$CIUnknownBasedPointer@UISectionEntry@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<ISectionEntry>::`vftable'
0x18000cb58  mov     [rbp+57h+var_70], rax
0x18000cb5c  mov     [rbp+57h+var_88], r13
0x18000cb60  lea     rax, ??_7?$CIUnknownBasedPointer@UIMetadataSectionEntry@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IMetadataSectionEntry>::`vftable'
0x18000cb67  mov     [rbp+57h+var_90], rax
0x18000cb6b  mov     rcx, [rdi+0B0h]
0x18000cb72  mov     rax, [rcx]
0x18000cb75  lea     rdx, [rbp+57h+var_68]
0x18000cb79  mov     rax, [rax+70h]
0x18000cb7d  call    cs:__guard_dispatch_icall_fptr
0x18000cb83  mov     esi, eax
0x18000cb85  test    eax, eax
0x18000cb87  jns     short loc_18000CBD9
0x18000cb89  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000cb90  mov     [rbp+57h+var_90], rdi
0x18000cb94  mov     rcx, [rbp+57h+var_88]
0x18000cb98  test    rcx, rcx
0x18000cb9b  jz      short loc_18000CBAA
0x18000cb9d  mov     rax, [rcx]
0x18000cba0  mov     rax, [rax+10h]
0x18000cba4  call    cs:__guard_dispatch_icall_fptr
0x18000cbaa  mov     [rbp+57h+var_88], r13
0x18000cbae  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000cbb5  mov     [rbp+57h+var_90], rbx
0x18000cbb9  mov     [rbp+57h+var_70], rdi
0x18000cbbd  mov     rcx, [rbp+57h+var_68]
0x18000cbc1  test    rcx, rcx
0x18000cbc4  jz      short loc_18000CBD4
0x18000cbc6  mov     rax, [rcx]
0x18000cbc9  mov     rax, [rax+10h]
0x18000cbcd  call    cs:__guard_dispatch_icall_fptr
0x18000cbd3  nop
0x18000cbd4  jmp     loc_18000D317
0x18000cbd9  mov     rcx, [rbp+57h+var_68]
0x18000cbdd  test    rcx, rcx
0x18000cbe0  jnz     short loc_18000CC3A
0x18000cbe2  mov     esi, 8007000Dh
0x18000cbe7  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000cbee  mov     [rbp+57h+var_90], rdi
0x18000cbf2  mov     rdx, [rbp+57h+var_88]
0x18000cbf6  test    rdx, rdx
0x18000cbf9  jz      short loc_18000CC0F
0x18000cbfb  mov     rax, [rdx]
0x18000cbfe  mov     rcx, rdx
0x18000cc01  mov     rax, [rax+10h]
0x18000cc05  call    cs:__guard_dispatch_icall_fptr
0x18000cc0b  mov     rcx, [rbp+57h+var_68]
0x18000cc0f  mov     [rbp+57h+var_88], r13
0x18000cc13  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000cc1a  mov     [rbp+57h+var_90], rbx
0x18000cc1e  mov     [rbp+57h+var_70], rdi
0x18000cc22  test    rcx, rcx
0x18000cc25  jz      short loc_18000CC35
0x18000cc27  mov     rax, [rcx]
0x18000cc2a  mov     rax, [rax+10h]
0x18000cc2e  call    cs:__guard_dispatch_icall_fptr
0x18000cc34  nop
0x18000cc35  jmp     loc_18000D317
0x18000cc3a  mov     rsi, rcx
0x18000cc3d  mov     rdx, [rbp+57h+var_88]
0x18000cc41  test    rdx, rdx
0x18000cc44  jz      short loc_18000CC5A
0x18000cc46  mov     rax, [rdx]
0x18000cc49  mov     rcx, rdx
0x18000cc4c  mov     rax, [rax+10h]
0x18000cc50  call    cs:__guard_dispatch_icall_fptr
0x18000cc56  mov     rcx, [rbp+57h+var_68]
0x18000cc5a  mov     r8, r13
0x18000cc5d  mov     [rbp+57h+var_88], r13
0x18000cc61  test    rsi, rsi
0x18000cc64  jz      loc_18000D2C8
0x18000cc6a  mov     rbx, [rsi]
0x18000cc6d  mov     rax, [rbp+57h+var_90]
0x18000cc71  lea     rcx, [rbp+57h+var_90]
0x18000cc75  mov     rax, [rax+28h]
0x18000cc79  call    cs:__guard_dispatch_icall_fptr
0x18000cc7f  mov     rdx, rax
0x18000cc82  lea     r8, [rbp+57h+var_88]
0x18000cc86  mov     rcx, rsi
0x18000cc89  mov     rax, [rbx]
0x18000cc8c  call    cs:__guard_dispatch_icall_fptr
0x18000cc92  mov     esi, eax
0x18000cc94  mov     r8, [rbp+57h+var_88]
0x18000cc98  test    eax, eax
0x18000cc9a  cmovs   r8, r13
0x18000cc9e  mov     [rbp+57h+var_88], r8
0x18000cca2  js      loc_18000D2C2
0x18000cca8  mov     [rbp+57h+var_78], r13
0x18000ccac  lea     rax, ??_7?$CIUnknownBasedPointer@UIDescriptionMetadataEntry@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IDescriptionMetadataEntry>::`vftable'
0x18000ccb3  mov     [rbp+57h+var_80], rax
0x18000ccb7  mov     rax, [r8]
0x18000ccba  lea     rdx, [rbp+57h+var_78]
0x18000ccbe  mov     rcx, r8
0x18000ccc1  mov     rax, [rax+70h]
0x18000ccc5  call    cs:__guard_dispatch_icall_fptr
0x18000cccb  mov     esi, eax
0x18000cccd  test    eax, eax
0x18000cccf  jns     short loc_18000CD43
0x18000ccd1  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000ccd8  mov     [rbp+57h+var_80], rdi
0x18000ccdc  mov     rcx, [rbp+57h+var_78]
0x18000cce0  test    rcx, rcx
0x18000cce3  jz      short loc_18000CCF2
0x18000cce5  mov     rax, [rcx]
0x18000cce8  mov     rax, [rax+10h]
0x18000ccec  call    cs:__guard_dispatch_icall_fptr
0x18000ccf2  mov     [rbp+57h+var_78], r13
0x18000ccf6  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000ccfd  mov     [rbp+57h+var_80], rbx
0x18000cd01  mov     [rbp+57h+var_90], rdi
0x18000cd05  mov     rcx, [rbp+57h+var_88]
0x18000cd09  test    rcx, rcx
0x18000cd0c  jz      short loc_18000CD1B
0x18000cd0e  mov     rax, [rcx]
0x18000cd11  mov     rax, [rax+10h]
0x18000cd15  call    cs:__guard_dispatch_icall_fptr
0x18000cd1b  mov     [rbp+57h+var_88], r13
0x18000cd1f  mov     [rbp+57h+var_90], rbx
0x18000cd23  mov     [rbp+57h+var_70], rdi
0x18000cd27  mov     rcx, [rbp+57h+var_68]
0x18000cd2b  test    rcx, rcx
0x18000cd2e  jz      short loc_18000CD3E
0x18000cd30  mov     rax, [rcx]
0x18000cd33  mov     rax, [rax+10h]
0x18000cd37  call    cs:__guard_dispatch_icall_fptr
0x18000cd3d  nop
0x18000cd3e  jmp     loc_18000D317
0x18000cd43  mov     rcx, [rbp+57h+var_78]
0x18000cd47  test    rcx, rcx
0x18000cd4a  jnz     short loc_18000CDA9
0x18000cd4c  mov     esi, 8007000Dh
0x18000cd51  mov     [rbp+57h+var_78], r13
0x18000cd55  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000cd5c  mov     [rbp+57h+var_80], rbx
0x18000cd60  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000cd67  mov     [rbp+57h+var_90], rdi
0x18000cd6b  mov     rcx, [rbp+57h+var_88]
0x18000cd6f  test    rcx, rcx
0x18000cd72  jz      short loc_18000CD81
0x18000cd74  mov     rax, [rcx]
0x18000cd77  mov     rax, [rax+10h]
0x18000cd7b  call    cs:__guard_dispatch_icall_fptr
0x18000cd81  mov     [rbp+57h+var_88], r13
0x18000cd85  mov     [rbp+57h+var_90], rbx
0x18000cd89  mov     [rbp+57h+var_70], rdi
0x18000cd8d  mov     rcx, [rbp+57h+var_68]
0x18000cd91  test    rcx, rcx
0x18000cd94  jz      short loc_18000CDA4
0x18000cd96  mov     rax, [rcx]
0x18000cd99  mov     rax, [rax+10h]
0x18000cd9d  call    cs:__guard_dispatch_icall_fptr
0x18000cda3  nop
0x18000cda4  jmp     loc_18000D317
0x18000cda9  mov     [rbp+57h+pv], r13
0x18000cdad  mov     [rbp+57h+var_4C], r13b
0x18000cdb1  mov     [rbp+57h+var_50], r13d
0x18000cdb5  lea     rbx, ??_7?$CCOMPointer@G@Dfdll@@6B@; const Dfdll::CCOMPointer<ushort>::`vftable'
0x18000cdbc  mov     [rbp+57h+var_60], rbx
0x18000cdc0  mov     rax, [rcx]
0x18000cdc3  lea     rdx, [rbp+57h+pv]
0x18000cdc7  mov     rax, [rax+38h]
0x18000cdcb  call    cs:__guard_dispatch_icall_fptr
0x18000cdd1  mov     esi, eax
0x18000cdd3  test    eax, eax
0x18000cdd5  jns     loc_18000CE77
0x18000cddb  lea     rdi, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000cde2  mov     [rbp+57h+var_60], rdi
0x18000cde6  mov     rcx, [rbp+57h+pv]; pv
0x18000cdea  test    rcx, rcx
0x18000cded  jz      short loc_18000CDF5
0x18000cdef  call    cs:__imp_CoTaskMemFree
0x18000cdf5  mov     [rbp+57h+pv], r13
0x18000cdf9  mov     [rbp+57h+var_4C], r13b
0x18000cdfd  mov     [rbp+57h+var_50], r13d
0x18000ce01  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000ce08  mov     [rbp+57h+var_60], rbx
0x18000ce0c  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000ce13  mov     [rbp+57h+var_80], rdi
0x18000ce17  mov     rcx, [rbp+57h+var_78]
0x18000ce1b  test    rcx, rcx
0x18000ce1e  jz      short loc_18000CE2D
0x18000ce20  mov     rax, [rcx]
0x18000ce23  mov     rax, [rax+10h]
0x18000ce27  call    cs:__guard_dispatch_icall_fptr
0x18000ce2d  mov     [rbp+57h+var_78], r13
0x18000ce31  mov     [rbp+57h+var_80], rbx
0x18000ce35  mov     [rbp+57h+var_90], rdi
0x18000ce39  mov     rcx, [rbp+57h+var_88]
0x18000ce3d  test    rcx, rcx
0x18000ce40  jz      short loc_18000CE4F
0x18000ce42  mov     rax, [rcx]
0x18000ce45  mov     rax, [rax+10h]
0x18000ce49  call    cs:__guard_dispatch_icall_fptr
0x18000ce4f  mov     [rbp+57h+var_88], r13
0x18000ce53  mov     [rbp+57h+var_90], rbx
0x18000ce57  mov     [rbp+57h+var_70], rdi
0x18000ce5b  mov     rcx, [rbp+57h+var_68]
0x18000ce5f  test    rcx, rcx
0x18000ce62  jz      short loc_18000CE72
0x18000ce64  mov     rax, [rcx]
0x18000ce67  mov     rax, [rax+10h]
0x18000ce6b  call    cs:__guard_dispatch_icall_fptr
0x18000ce71  nop
0x18000ce72  jmp     loc_18000D317
0x18000ce77  cmp     [rbp+57h+pv], r13
0x18000ce7b  jnz     loc_18000CF08
0x18000ce81  mov     esi, 8007000Dh
0x18000ce86  mov     [rbp+57h+pv], r13
0x18000ce8a  mov     [rbp+57h+var_4C], r13b
0x18000ce8e  mov     [rbp+57h+var_50], r13d
0x18000ce92  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000ce99  mov     [rbp+57h+var_60], rbx
0x18000ce9d  lea     rdi, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000cea4  mov     [rbp+57h+var_80], rdi
0x18000cea8  mov     rcx, [rbp+57h+var_78]
0x18000ceac  test    rcx, rcx
0x18000ceaf  jz      short loc_18000CEBE
0x18000ceb1  mov     rax, [rcx]
0x18000ceb4  mov     rax, [rax+10h]
0x18000ceb8  call    cs:__guard_dispatch_icall_fptr
0x18000cebe  mov     [rbp+57h+var_78], r13
0x18000cec2  mov     [rbp+57h+var_80], rbx
0x18000cec6  mov     [rbp+57h+var_90], rdi
0x18000ceca  mov     rcx, [rbp+57h+var_88]
0x18000cece  test    rcx, rcx
0x18000ced1  jz      short loc_18000CEE0
0x18000ced3  mov     rax, [rcx]
0x18000ced6  mov     rax, [rax+10h]
0x18000ceda  call    cs:__guard_dispatch_icall_fptr
0x18000cee0  mov     [rbp+57h+var_88], r13
0x18000cee4  mov     [rbp+57h+var_90], rbx
0x18000cee8  mov     [rbp+57h+var_70], rdi
0x18000ceec  mov     rcx, [rbp+57h+var_68]
0x18000cef0  test    rcx, rcx
0x18000cef3  jz      short loc_18000CF03
0x18000cef5  mov     rax, [rcx]
0x18000cef8  mov     rax, [rax+10h]
0x18000cefc  call    cs:__guard_dispatch_icall_fptr
0x18000cf02  nop
0x18000cf03  jmp     loc_18000D317
0x18000cf08  mov     [rbp+57h+arg_18], r13
0x18000cf0c  mov     [rbp+57h+var_40], r13
0x18000cf10  mov     [rbp+57h+var_34], r13b
0x18000cf14  mov     [rbp+57h+var_38], r13d
0x18000cf18  mov     [rbp+57h+var_48], rbx
0x18000cf1c  mov     rcx, [rdi+80h]
0x18000cf23  mov     rax, [rcx]
0x18000cf26  lea     rdx, [rbp+57h+var_40]
0x18000cf2a  mov     [rsp+0C0h+var_A0], rdx
0x18000cf2f  lea     r9, [rbp+57h+arg_18]
0x18000cf33  mov     r8, [rdi+50h]
0x18000cf37  xor     edx, edx
0x18000cf39  mov     rax, [rax+90h]
0x18000cf40  call    cs:__guard_dispatch_icall_fptr
0x18000cf46  mov     esi, eax
0x18000cf48  test    eax, eax
0x18000cf4a  jns     loc_18000D00F
0x18000cf50  lea     rdi, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000cf57  mov     [rbp+57h+var_48], rdi
0x18000cf5b  mov     rcx, [rbp+57h+var_40]; pv
0x18000cf5f  test    rcx, rcx
  ... truncated ...
```
