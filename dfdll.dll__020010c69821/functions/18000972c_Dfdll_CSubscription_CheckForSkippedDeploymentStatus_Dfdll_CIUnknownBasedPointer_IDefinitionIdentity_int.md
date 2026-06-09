# Dfdll::CSubscription::CheckForSkippedDeploymentStatus(Dfdll::CIUnknownBasedPointer<IDefinitionIdentity> &,int &)

- ea: `0x18000972c`
- end: `0x180009c44`
- name: `?CheckForSkippedDeploymentStatus@CSubscription@Dfdll@@IEAAJAEAV?$CIUnknownBasedPointer@UIDefinitionIdentity@@@2@AEAH@Z`
- size: `1304`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000949c`

## callees

- `0x18000972c`
- `0x18000a040`
- `0x180011ba8`
- `0x180012140`
- `0x180012b30`
- `0x180012bd0`
- `0x18001efd0`

## string_xrefs

- `0x1800097b9`: `UpdateSkippedDeployment`
- `0x180009a1e`: `UpdateSkipTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Dfdll::CSubscription::CheckForSkippedDeploymentStatus(
        Dfdll::CSubscription *this,
        __int64 a2,
        _DWORD *a3)
{
  int v6; // edi
  const struct std::nothrow_t *v7; // rdx
  const struct std::nothrow_t *v9; // rdx
  const struct std::nothrow_t *v10; // rdx
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // [rsp+48h] [rbp-71h] BYREF
  void **v13; // [rsp+50h] [rbp-69h] BYREF
  void **v14; // [rsp+58h] [rbp-61h]
  void *v15; // [rsp+60h] [rbp-59h]
  int v16; // [rsp+68h] [rbp-51h]
  int v17; // [rsp+70h] [rbp-49h]
  void **v18; // [rsp+78h] [rbp-41h] BYREF
  void **v19; // [rsp+80h] [rbp-39h]
  unsigned __int16 *v20; // [rsp+88h] [rbp-31h]
  int v21; // [rsp+90h] [rbp-29h]
  int v22; // [rsp+98h] [rbp-21h]
  int v23; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v24; // [rsp+A8h] [rbp-11h] BYREF
  struct tagBLOB v25; // [rsp+B0h] [rbp-9h] BYREF
  GUID v26; // [rsp+C0h] [rbp+7h] BYREF

  v26 = CLSID_STORE_PROPSET;
  v13 = &Dfdll::CString::`vftable';
  v15 = 0;
  v16 = 0;
  v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v17 = 0;
  v12 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, GUID *, const wchar_t *, struct tagBLOB *))(**((_QWORD **)this + 16) + 136LL))(
         *((_QWORD *)this + 16),
         0,
         *((_QWORD *)this + 8),
         (char *)this + 200,
         &v26,
         L"UpdateSkippedDeployment",
         &v25);
  if ( v6 < 0 )
  {
    v12 = 0;
    v13 = &Dfdll::CString::`vftable';
    v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
    return (unsigned int)v6;
  }
  v6 = Dfdll::CConvert::ToString(&v25, (struct Dfdll::CString *)&v13);
  if ( v6 < 0 )
  {
    v12 = 0;
    v13 = &Dfdll::CString::`vftable';
    v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v15 )
      operator delete(v15, v7);
    return (unsigned int)v6;
  }
  if ( !v17 )
  {
    v6 = -2147024809;
LABEL_9:
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
    v13 = &Dfdll::CString::`vftable';
    v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v15 )
      operator delete(v15, v7);
    return (unsigned int)v6;
  }
  v6 = Dfdll::CSubscription::EnsureInitialization(this);
  if ( v6 < 0 )
    goto LABEL_9;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, __int64 *))(**((_QWORD **)this + 18) + 24LL))(
         *((_QWORD *)this + 18),
         0,
         v15,
         &v12);
  if ( v6 < 0 )
    goto LABEL_9;
  v23 = 0;
  *a3 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int *))(**((_QWORD **)this + 18) + 72LL))(
         *((_QWORD *)this + 18),
         0,
         *(_QWORD *)(a2 + 8),
         v12,
         &v23);
  if ( v6 < 0 )
  {
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
    v13 = &Dfdll::CString::`vftable';
    v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v15 )
      operator delete(v15, v9);
    return (unsigned int)v6;
  }
  if ( v23 == 1 )
  {
    v18 = &Dfdll::CString::`vftable';
    v20 = 0;
    v21 = 0;
    v19 = &Dfdll::CBuffer<unsigned short>::`vftable';
    v22 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, GUID *, const wchar_t *, struct tagBLOB *))(**((_QWORD **)this + 16) + 136LL))(
           *((_QWORD *)this + 16),
           0,
           *((_QWORD *)this + 8),
           (char *)this + 200,
           &v26,
           L"UpdateSkipTime",
           &v25);
    if ( v6 < 0 )
    {
      v18 = &Dfdll::CString::`vftable';
      v19 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v20 )
        operator delete(v20, v10);
      v20 = 0;
      v21 = 0;
      v19 = &Dfdll::CObject::`vftable';
      v18 = &Dfdll::CObject::`vftable';
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v12 = 0;
      v13 = &Dfdll::CString::`vftable';
      v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v15 )
        operator delete(v15, v10);
      return (unsigned int)v6;
    }
    v6 = Dfdll::CConvert::ToString(&v25, (struct Dfdll::CString *)&v18);
    if ( v6 < 0 )
    {
      v18 = &Dfdll::CString::`vftable';
      v19 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v20 )
        operator delete(v20, v11);
      v20 = 0;
      v21 = 0;
      v19 = &Dfdll::CObject::`vftable';
      v18 = &Dfdll::CObject::`vftable';
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v12 = 0;
      v13 = &Dfdll::CString::`vftable';
      v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v15 )
        operator delete(v15, v11);
      return (unsigned int)v6;
    }
    v24 = 0;
    v6 = Dfdll::CSubscription::TimeElapsedSince(this, &v24, v20);
    if ( v6 < 0 )
    {
      v18 = &Dfdll::CString::`vftable';
      v19 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v20 )
        operator delete(v20, v9);
      v20 = 0;
      v21 = 0;
      v19 = &Dfdll::CObject::`vftable';
      v18 = &Dfdll::CObject::`vftable';
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v12 = 0;
      v13 = &Dfdll::CString::`vftable';
      v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v15 )
        operator delete(v15, v9);
      return (unsigned int)v6;
    }
    if ( v24 < 0 )
      *a3 = 1;
    v18 = &Dfdll::CString::`vftable';
    v19 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v20 )
      operator delete(v20, v9);
  }
  v6 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v12 = 0;
  v13 = &Dfdll::CString::`vftable';
  v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v15 )
    operator delete(v15, v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000972c  mov     [rsp-8+arg_18], rbx
0x180009731  push    rbp
0x180009732  push    rsi
0x180009733  push    rdi
0x180009734  push    r12
0x180009736  push    r13
0x180009738  push    r14
0x18000973a  push    r15
0x18000973c  lea     rbp, [rsp-27h]
0x180009741  sub     rsp, 0E0h
0x180009748  mov     rax, cs:__security_cookie
0x18000974f  xor     rax, rsp
0x180009752  mov     [rbp+57h+var_40], rax
0x180009756  mov     rsi, r8
0x180009759  mov     r14, rdx
0x18000975c  mov     rbx, rcx
0x18000975f  movups  xmm0, xmmword ptr cs:CLSID_STORE_PROPSET.Data1
0x180009766  movdqu  [rbp+57h+var_50], xmm0
0x18000976b  lea     r13, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x180009772  mov     [rbp+57h+var_C0], r13
0x180009776  xor     r12d, r12d
0x180009779  mov     [rbp+57h+var_B0], r12
0x18000977d  mov     [rbp+57h+var_A8], r12d
0x180009781  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180009788  mov     [rbp+57h+var_B8], rax
0x18000978c  mov     [rbp+57h+var_A0], r12d
0x180009790  mov     [rbp+57h+var_C8], r12
0x180009794  lea     rax, ??_7?$CIUnknownBasedPointer@UIDefinitionIdentity@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable'
0x18000979b  mov     [rbp+57h+var_D0], rax
0x18000979f  mov     rcx, [rcx+80h]
0x1800097a6  lea     r15, [rbx+0C8h]
0x1800097ad  mov     rax, [rcx]
0x1800097b0  lea     rdx, [rbp+57h+var_60]
0x1800097b4  mov     [rsp+110h+var_E0], rdx
0x1800097b9  lea     rdx, aUpdateskippedd; "UpdateSkippedDeployment"
0x1800097c0  mov     [rsp+110h+var_E8], rdx
0x1800097c5  lea     rdx, [rbp+57h+var_50]
0x1800097c9  mov     [rsp+110h+var_F0], rdx
0x1800097ce  mov     r9, r15
0x1800097d1  mov     r8, [rbx+40h]
0x1800097d5  xor     edx, edx
0x1800097d7  mov     rax, [rax+88h]
0x1800097de  call    cs:__guard_dispatch_icall_fptr
0x1800097e4  mov     edi, eax
0x1800097e6  test    eax, eax
0x1800097e8  jns     short loc_180009840
0x1800097ea  lea     rcx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x1800097f1  mov     [rbp+57h+var_D0], rcx
0x1800097f5  mov     rdx, [rbp+57h+var_C8]
0x1800097f9  test    rdx, rdx
0x1800097fc  jz      short loc_18000980E
0x1800097fe  mov     rcx, [rdx]
0x180009801  mov     rax, [rcx+10h]
0x180009805  mov     rcx, rdx
0x180009808  call    cs:__guard_dispatch_icall_fptr
0x18000980e  mov     [rbp+57h+var_C8], r12
0x180009812  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180009819  mov     [rbp+57h+var_D0], rbx
0x18000981d  mov     [rbp+57h+var_C0], r13
0x180009821  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x180009828  mov     [rbp+57h+var_B8], rax
0x18000982c  mov     rcx, [rbp+57h+var_B0]; void *
0x180009830  test    rcx, rcx
0x180009833  jz      short loc_18000983B
0x180009835  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000983a  nop
0x18000983b  jmp     loc_1800098FC
0x180009840  lea     rdx, [rbp+57h+var_C0]; struct Dfdll::CString *
0x180009844  lea     rcx, [rbp+57h+var_60]; struct tagBLOB *
0x180009848  call    ?ToString@CConvert@Dfdll@@SAJAEAUtagBLOB@@AEAVCString@2@@Z; Dfdll::CConvert::ToString(tagBLOB &,Dfdll::CString &)
0x18000984d  mov     edi, eax
0x18000984f  test    eax, eax
0x180009851  jns     short loc_1800098A3
0x180009853  lea     rcx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000985a  mov     [rbp+57h+var_D0], rcx
0x18000985e  mov     rcx, [rbp+57h+var_C8]
0x180009862  test    rcx, rcx
0x180009865  jz      short loc_180009874
0x180009867  mov     rax, [rcx]
0x18000986a  mov     rax, [rax+10h]
0x18000986e  call    cs:__guard_dispatch_icall_fptr
0x180009874  mov     [rbp+57h+var_C8], r12
0x180009878  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000987f  mov     [rbp+57h+var_D0], rbx
0x180009883  mov     [rbp+57h+var_C0], r13
0x180009887  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000988e  mov     [rbp+57h+var_B8], rax
0x180009892  mov     rcx, [rbp+57h+var_B0]; void *
0x180009896  test    rcx, rcx
0x180009899  jz      short loc_1800098A1
0x18000989b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800098a0  nop
0x1800098a1  jmp     short loc_1800098FC
0x1800098a3  cmp     [rbp+57h+var_A0], r12d
0x1800098a7  jnz     short loc_180009925
0x1800098a9  mov     edi, 80070057h
0x1800098ae  lea     rcx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x1800098b5  mov     [rbp+57h+var_D0], rcx
0x1800098b9  mov     rcx, [rbp+57h+var_C8]
0x1800098bd  test    rcx, rcx
0x1800098c0  jz      short loc_1800098CF
0x1800098c2  mov     rax, [rcx]
0x1800098c5  mov     rax, [rax+10h]
0x1800098c9  call    cs:__guard_dispatch_icall_fptr
0x1800098cf  mov     [rbp+57h+var_C8], r12
0x1800098d3  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800098da  mov     [rbp+57h+var_D0], rbx
0x1800098de  mov     [rbp+57h+var_C0], r13
0x1800098e2  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x1800098e9  mov     [rbp+57h+var_B8], rax
0x1800098ed  mov     rcx, [rbp+57h+var_B0]; void *
0x1800098f1  test    rcx, rcx
0x1800098f4  jz      short loc_1800098FC
0x1800098f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800098fb  nop
0x1800098fc  mov     eax, edi
0x1800098fe  mov     rcx, [rbp+57h+var_40]
0x180009902  xor     rcx, rsp; StackCookie
0x180009905  call    __security_check_cookie
0x18000990a  mov     rbx, [rsp+110h+arg_18]
0x180009912  add     rsp, 0E0h
0x180009919  pop     r15
0x18000991b  pop     r14
0x18000991d  pop     r13
0x18000991f  pop     r12
0x180009921  pop     rdi
0x180009922  pop     rsi
0x180009923  pop     rbp
0x180009924  retn
0x180009925  mov     rcx, rbx; this
0x180009928  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000992d  mov     edi, eax
0x18000992f  test    eax, eax
0x180009931  js      loc_1800098AE
0x180009937  mov     rcx, [rbx+90h]
0x18000993e  mov     rax, [rcx]
0x180009941  lea     r9, [rbp+57h+var_C8]
0x180009945  mov     r8, [rbp+57h+var_B0]
0x180009949  xor     edx, edx
0x18000994b  mov     rax, [rax+18h]
0x18000994f  call    cs:__guard_dispatch_icall_fptr
0x180009955  mov     edi, eax
0x180009957  test    eax, eax
0x180009959  js      loc_1800098AE
0x18000995f  mov     [rbp+57h+var_70], r12d
0x180009963  mov     [rsi], r12d
0x180009966  mov     rcx, [rbx+90h]
0x18000996d  mov     rax, [rcx]
0x180009970  lea     rdx, [rbp+57h+var_70]
0x180009974  mov     [rsp+110h+var_F0], rdx
0x180009979  mov     r9, [rbp+57h+var_C8]
0x18000997d  mov     r8, [r14+8]
0x180009981  xor     edx, edx
0x180009983  mov     rax, [rax+48h]
0x180009987  call    cs:__guard_dispatch_icall_fptr
0x18000998d  mov     edi, eax
0x18000998f  test    eax, eax
0x180009991  jns     short loc_1800099E6
0x180009993  lea     rcx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000999a  mov     [rbp+57h+var_D0], rcx
0x18000999e  mov     rcx, [rbp+57h+var_C8]
0x1800099a2  test    rcx, rcx
0x1800099a5  jz      short loc_1800099B4
0x1800099a7  mov     rax, [rcx]
0x1800099aa  mov     rax, [rax+10h]
0x1800099ae  call    cs:__guard_dispatch_icall_fptr
0x1800099b4  mov     [rbp+57h+var_C8], r12
0x1800099b8  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800099bf  mov     [rbp+57h+var_D0], rbx
0x1800099c3  mov     [rbp+57h+var_C0], r13
0x1800099c7  lea     rax, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x1800099ce  mov     [rbp+57h+var_B8], rax
0x1800099d2  mov     rcx, [rbp+57h+var_B0]; void *
0x1800099d6  test    rcx, rcx
0x1800099d9  jz      short loc_1800099E1
0x1800099db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800099e0  nop
0x1800099e1  jmp     loc_1800098FC
0x1800099e6  lea     r14, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x1800099ed  cmp     [rbp+57h+var_70], 1
0x1800099f1  jnz     loc_180009BF5
0x1800099f7  mov     [rbp+57h+var_98], r13
0x1800099fb  mov     [rbp+57h+var_88], r12
0x1800099ff  mov     [rbp+57h+var_80], r12d
0x180009a03  mov     [rbp+57h+var_90], r14
0x180009a07  mov     [rbp+57h+var_78], r12d
0x180009a0b  mov     rcx, [rbx+80h]
0x180009a12  mov     rax, [rcx]
0x180009a15  lea     rdx, [rbp+57h+var_60]
0x180009a19  mov     [rsp+110h+var_E0], rdx
0x180009a1e  lea     rdx, aUpdateskiptime; "UpdateSkipTime"
0x180009a25  mov     [rsp+110h+var_E8], rdx
0x180009a2a  lea     rdx, [rbp+57h+var_50]
0x180009a2e  mov     [rsp+110h+var_F0], rdx
0x180009a33  mov     r9, r15
0x180009a36  mov     r8, [rbx+40h]
0x180009a3a  xor     edx, edx
0x180009a3c  mov     rax, [rax+88h]
0x180009a43  call    cs:__guard_dispatch_icall_fptr
0x180009a49  mov     edi, eax
0x180009a4b  test    eax, eax
0x180009a4d  jns     short loc_180009AC1
0x180009a4f  mov     [rbp+57h+var_98], r13
0x180009a53  mov     [rbp+57h+var_90], r14
0x180009a57  mov     rcx, [rbp+57h+var_88]; void *
0x180009a5b  test    rcx, rcx
0x180009a5e  jz      short loc_180009A65
0x180009a60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009a65  mov     [rbp+57h+var_88], r12
0x180009a69  mov     [rbp+57h+var_80], r12d
0x180009a6d  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180009a74  mov     [rbp+57h+var_90], rbx
0x180009a78  mov     [rbp+57h+var_98], rbx
0x180009a7c  lea     rcx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180009a83  mov     [rbp+57h+var_D0], rcx
0x180009a87  mov     rcx, [rbp+57h+var_C8]
0x180009a8b  test    rcx, rcx
0x180009a8e  jz      short loc_180009A9D
0x180009a90  mov     rax, [rcx]
0x180009a93  mov     rax, [rax+10h]
0x180009a97  call    cs:__guard_dispatch_icall_fptr
0x180009a9d  mov     [rbp+57h+var_C8], r12
0x180009aa1  mov     [rbp+57h+var_D0], rbx
0x180009aa5  mov     [rbp+57h+var_C0], r13
0x180009aa9  mov     [rbp+57h+var_B8], r14
0x180009aad  mov     rcx, [rbp+57h+var_B0]; void *
0x180009ab1  test    rcx, rcx
0x180009ab4  jz      short loc_180009ABC
0x180009ab6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009abb  nop
0x180009abc  jmp     loc_1800098FC
0x180009ac1  lea     rdx, [rbp+57h+var_98]; struct Dfdll::CString *
0x180009ac5  lea     rcx, [rbp+57h+var_60]; struct tagBLOB *
0x180009ac9  call    ?ToString@CConvert@Dfdll@@SAJAEAUtagBLOB@@AEAVCString@2@@Z; Dfdll::CConvert::ToString(tagBLOB &,Dfdll::CString &)
0x180009ace  mov     edi, eax
0x180009ad0  test    eax, eax
0x180009ad2  jns     short loc_180009B46
0x180009ad4  mov     [rbp+57h+var_98], r13
0x180009ad8  mov     [rbp+57h+var_90], r14
0x180009adc  mov     rcx, [rbp+57h+var_88]; void *
0x180009ae0  test    rcx, rcx
0x180009ae3  jz      short loc_180009AEA
0x180009ae5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009aea  mov     [rbp+57h+var_88], r12
0x180009aee  mov     [rbp+57h+var_80], r12d
0x180009af2  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180009af9  mov     [rbp+57h+var_90], rbx
0x180009afd  mov     [rbp+57h+var_98], rbx
0x180009b01  lea     rcx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180009b08  mov     [rbp+57h+var_D0], rcx
0x180009b0c  mov     rcx, [rbp+57h+var_C8]
0x180009b10  test    rcx, rcx
0x180009b13  jz      short loc_180009B22
0x180009b15  mov     rax, [rcx]
0x180009b18  mov     rax, [rax+10h]
0x180009b1c  call    cs:__guard_dispatch_icall_fptr
0x180009b22  mov     [rbp+57h+var_C8], r12
0x180009b26  mov     [rbp+57h+var_D0], rbx
0x180009b2a  mov     [rbp+57h+var_C0], r13
0x180009b2e  mov     [rbp+57h+var_B8], r14
0x180009b32  mov     rcx, [rbp+57h+var_B0]; void *
0x180009b36  test    rcx, rcx
0x180009b39  jz      short loc_180009B41
0x180009b3b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009b40  nop
0x180009b41  jmp     loc_1800098FC
0x180009b46  mov     [rbp+57h+var_68], r12
0x180009b4a  mov     r8, [rbp+57h+var_88]; unsigned __int16 *
0x180009b4e  lea     rdx, [rbp+57h+var_68]; __int64 *
0x180009b52  mov     rcx, rbx; this
0x180009b55  call    ?TimeElapsedSince@CSubscription@Dfdll@@IEAAJAEA_JPEBG@Z; Dfdll::CSubscription::TimeElapsedSince(__int64 &,ushort const *)
0x180009b5a  mov     edi, eax
0x180009b5c  test    eax, eax
0x180009b5e  jns     short loc_180009BD2
0x180009b60  mov     [rbp+57h+var_98], r13
0x180009b64  mov     [rbp+57h+var_90], r14
0x180009b68  mov     rcx, [rbp+57h+var_88]; void *
0x180009b6c  test    rcx, rcx
0x180009b6f  jz      short loc_180009B76
0x180009b71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009b76  mov     [rbp+57h+var_88], r12
0x180009b7a  mov     [rbp+57h+var_80], r12d
0x180009b7e  lea     rbx, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180009b85  mov     [rbp+57h+var_90], rbx
0x180009b89  mov     [rbp+57h+var_98], rbx
0x180009b8d  lea     rcx, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180009b94  mov     [rbp+57h+var_D0], rcx
0x180009b98  mov     rcx, [rbp+57h+var_C8]
0x180009b9c  test    rcx, rcx
0x180009b9f  jz      short loc_180009BAE
0x180009ba1  mov     rax, [rcx]
0x180009ba4  mov     rax, [rax+10h]
0x180009ba8  call    cs:__guard_dispatch_icall_fptr
0x180009bae  mov     [rbp+57h+var_C8], r12
0x180009bb2  mov     [rbp+57h+var_D0], rbx
0x180009bb6  mov     [rbp+57h+var_C0], r13
0x180009bba  mov     [rbp+57h+var_B8], r14
0x180009bbe  mov     rcx, [rbp+57h+var_B0]; void *
0x180009bc2  test    rcx, rcx
0x180009bc5  jz      short loc_180009BCD
  ... truncated ...
```
