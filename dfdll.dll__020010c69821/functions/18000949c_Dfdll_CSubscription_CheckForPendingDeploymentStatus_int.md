# Dfdll::CSubscription::CheckForPendingDeploymentStatus(int &)

- ea: `0x18000949c`
- end: `0x18000972c`
- name: `?CheckForPendingDeploymentStatus@CSubscription@Dfdll@@IEAAJAEAH@Z`
- size: `656`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a2ac`

## callees

- `0x18000949c`
- `0x18000972c`
- `0x18000a040`
- `0x180012140`
- `0x180012b30`
- `0x180012bd0`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Dfdll::CSubscription::CheckForPendingDeploymentStatus(Dfdll::CSubscription *this, int *a2)
{
  int v4; // ebx
  const struct std::nothrow_t *v5; // rdx
  const struct std::nothrow_t *v7; // rdx
  void **v8; // [rsp+40h] [rbp-39h] BYREF
  __int64 v9; // [rsp+48h] [rbp-31h] BYREF
  int v10; // [rsp+50h] [rbp-29h] BYREF
  void **v11; // [rsp+58h] [rbp-21h] BYREF
  void **v12; // [rsp+60h] [rbp-19h]
  void *v13; // [rsp+68h] [rbp-11h]
  int v14; // [rsp+70h] [rbp-9h]
  int v15; // [rsp+78h] [rbp-1h]
  tagBLOB v16; // [rsp+80h] [rbp+7h] BYREF
  GUID v17; // [rsp+90h] [rbp+17h] BYREF

  v4 = Dfdll::CSubscription::EnsureInitialization(this);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v17 = CLSID_STORE_PROPSET;
  v11 = &Dfdll::CString::`vftable';
  v13 = 0;
  v14 = 0;
  v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v15 = 0;
  v9 = 0;
  v8 = &Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable';
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, GUID *, const wchar_t *, tagBLOB *))(**((_QWORD **)this + 16) + 136LL))(
         *((_QWORD *)this + 16),
         0,
         *((_QWORD *)this + 8),
         (char *)this + 200,
         &v17,
         L"PendingDeployment",
         &v16);
  if ( v4 < 0 )
  {
    v9 = 0;
    v8 = &Dfdll::CObject::`vftable';
    v11 = &Dfdll::CString::`vftable';
    v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
    return (unsigned int)v4;
  }
  v4 = Dfdll::CConvert::ToString(&v16, (struct Dfdll::CString *)&v11);
  if ( v4 < 0 )
  {
    v9 = 0;
    v8 = &Dfdll::CObject::`vftable';
    v11 = &Dfdll::CString::`vftable';
    v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v13 )
      operator delete(v13, v5);
    return (unsigned int)v4;
  }
  if ( !v15 )
  {
    v4 = -2147024809;
LABEL_10:
    v8 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
    v8 = &Dfdll::CObject::`vftable';
    v11 = &Dfdll::CString::`vftable';
    v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( v13 )
      operator delete(v13, v5);
    return (unsigned int)v4;
  }
  v4 = Dfdll::CSubscription::EnsureInitialization(this);
  if ( v4 < 0 )
    goto LABEL_10;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, __int64 *))(**((_QWORD **)this + 18) + 24LL))(
         *((_QWORD *)this + 18),
         0,
         v13,
         &v9);
  if ( v4 < 0 )
    goto LABEL_10;
  *a2 = 1;
  v10 = 1;
  if ( (int)Dfdll::CSubscription::CheckForSkippedDeploymentStatus(this, (__int64)&v8, &v10) >= 0 && v10 )
    *a2 = 0;
  v4 = 0;
  v8 = &Dfdll::CInterfacePointer<IUnknown>::`vftable';
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v9 = 0;
  v8 = &Dfdll::CObject::`vftable';
  v11 = &Dfdll::CString::`vftable';
  v12 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( v13 )
    operator delete(v13, v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000949c  mov     [rsp-8+arg_10], rbx
0x1800094a1  push    rbp
0x1800094a2  push    rsi
0x1800094a3  push    rdi
0x1800094a4  push    r12
0x1800094a6  push    r15
0x1800094a8  lea     rbp, [rsp-37h]
0x1800094ad  sub     rsp, 0B0h
0x1800094b4  mov     rax, cs:__security_cookie
0x1800094bb  xor     rax, rsp
0x1800094be  mov     [rbp+57h+var_30], rax
0x1800094c2  mov     rsi, rdx
0x1800094c5  mov     rdi, rcx
0x1800094c8  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x1800094cd  mov     ebx, eax
0x1800094cf  test    eax, eax
0x1800094d1  js      loc_18000965B
0x1800094d7  movups  xmm0, xmmword ptr cs:CLSID_STORE_PROPSET.Data1
0x1800094de  movdqu  [rbp+57h+var_40], xmm0
0x1800094e3  lea     r15, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x1800094ea  mov     [rbp+57h+var_78], r15
0x1800094ee  and     [rbp+57h+var_68], 0
0x1800094f3  and     [rbp+57h+var_60], 0
0x1800094f7  lea     r12, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x1800094fe  mov     [rbp+57h+var_70], r12
0x180009502  and     [rbp+57h+var_58], 0
0x180009506  and     [rbp+57h+var_88], 0
0x18000950b  lea     rax, ??_7?$CIUnknownBasedPointer@UIDefinitionIdentity@@@Dfdll@@6B@; const Dfdll::CIUnknownBasedPointer<IDefinitionIdentity>::`vftable'
0x180009512  mov     [rbp+57h+var_90], rax
0x180009516  mov     rcx, [rdi+80h]
0x18000951d  mov     rax, [rcx]
0x180009520  lea     r9, [rdi+0C8h]
0x180009527  lea     rdx, [rbp+57h+var_50]
0x18000952b  mov     [rsp+0D0h+var_A0], rdx
0x180009530  lea     rdx, aPendingdeploym; "PendingDeployment"
0x180009537  mov     [rsp+0D0h+var_A8], rdx
0x18000953c  lea     rdx, [rbp+57h+var_40]
0x180009540  mov     [rsp+0D0h+var_B0], rdx
0x180009545  mov     r8, [rdi+40h]
0x180009549  xor     edx, edx
0x18000954b  mov     rax, [rax+88h]
0x180009552  call    cs:__guard_dispatch_icall_fptr
0x180009558  mov     ebx, eax
0x18000955a  test    eax, eax
0x18000955c  jns     short loc_1800095AB
0x18000955e  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x180009565  mov     [rbp+57h+var_90], rax
0x180009569  mov     rcx, [rbp+57h+var_88]
0x18000956d  test    rcx, rcx
0x180009570  jz      short loc_18000957F
0x180009572  mov     rax, [rcx]
0x180009575  mov     rax, [rax+10h]
0x180009579  call    cs:__guard_dispatch_icall_fptr
0x18000957f  and     [rbp+57h+var_88], 0
0x180009584  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000958b  mov     [rbp+57h+var_90], rax
0x18000958f  mov     [rbp+57h+var_78], r15
0x180009593  mov     [rbp+57h+var_70], r12
0x180009597  mov     rcx, [rbp+57h+var_68]; void *
0x18000959b  test    rcx, rcx
0x18000959e  jz      short loc_1800095A6
0x1800095a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800095a5  nop
0x1800095a6  jmp     loc_18000965B
0x1800095ab  lea     rdx, [rbp+57h+var_78]; struct Dfdll::CString *
0x1800095af  lea     rcx, [rbp+57h+var_50]; struct tagBLOB *
0x1800095b3  call    ?ToString@CConvert@Dfdll@@SAJAEAUtagBLOB@@AEAVCString@2@@Z; Dfdll::CConvert::ToString(tagBLOB &,Dfdll::CString &)
0x1800095b8  mov     ebx, eax
0x1800095ba  test    eax, eax
0x1800095bc  jns     short loc_180009608
0x1800095be  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x1800095c5  mov     [rbp+57h+var_90], rax
0x1800095c9  mov     rcx, [rbp+57h+var_88]
0x1800095cd  test    rcx, rcx
0x1800095d0  jz      short loc_1800095DF
0x1800095d2  mov     rax, [rcx]
0x1800095d5  mov     rax, [rax+10h]
0x1800095d9  call    cs:__guard_dispatch_icall_fptr
0x1800095df  and     [rbp+57h+var_88], 0
0x1800095e4  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x1800095eb  mov     [rbp+57h+var_90], rax
0x1800095ef  mov     [rbp+57h+var_78], r15
0x1800095f3  mov     [rbp+57h+var_70], r12
0x1800095f7  mov     rcx, [rbp+57h+var_68]; void *
0x1800095fb  test    rcx, rcx
0x1800095fe  jz      short loc_180009606
0x180009600  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009605  nop
0x180009606  jmp     short loc_18000965B
0x180009608  cmp     [rbp+57h+var_58], 0
0x18000960c  jnz     short loc_180009680
0x18000960e  mov     ebx, 80070057h
0x180009613  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x18000961a  mov     [rbp+57h+var_90], rax
0x18000961e  mov     rcx, [rbp+57h+var_88]
0x180009622  test    rcx, rcx
0x180009625  jz      short loc_180009634
0x180009627  mov     rax, [rcx]
0x18000962a  mov     rax, [rax+10h]
0x18000962e  call    cs:__guard_dispatch_icall_fptr
0x180009634  and     [rbp+57h+var_88], 0
0x180009639  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180009640  mov     [rbp+57h+var_90], rax
0x180009644  mov     [rbp+57h+var_78], r15
0x180009648  mov     [rbp+57h+var_70], r12
0x18000964c  mov     rcx, [rbp+57h+var_68]; void *
0x180009650  test    rcx, rcx
0x180009653  jz      short loc_18000965B
0x180009655  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000965a  nop
0x18000965b  mov     eax, ebx
0x18000965d  mov     rcx, [rbp+57h+var_30]
0x180009661  xor     rcx, rsp; StackCookie
0x180009664  call    __security_check_cookie
0x180009669  mov     rbx, [rsp+0D0h+arg_10]
0x180009671  add     rsp, 0B0h
0x180009678  pop     r15
0x18000967a  pop     r12
0x18000967c  pop     rdi
0x18000967d  pop     rsi
0x18000967e  pop     rbp
0x18000967f  retn
0x180009680  mov     rcx, rdi; this
0x180009683  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x180009688  mov     ebx, eax
0x18000968a  test    eax, eax
0x18000968c  js      short loc_180009613
0x18000968e  mov     rcx, [rdi+90h]
0x180009695  mov     rax, [rcx]
0x180009698  lea     r9, [rbp+57h+var_88]
0x18000969c  mov     r8, [rbp+57h+var_68]
0x1800096a0  xor     edx, edx
0x1800096a2  mov     rax, [rax+18h]
0x1800096a6  call    cs:__guard_dispatch_icall_fptr
0x1800096ac  mov     ebx, eax
0x1800096ae  test    eax, eax
0x1800096b0  js      loc_180009613
0x1800096b6  mov     eax, 1
0x1800096bb  mov     [rsi], eax
0x1800096bd  mov     [rbp+57h+var_80], eax
0x1800096c0  lea     r8, [rbp+57h+var_80]
0x1800096c4  lea     rdx, [rbp+57h+var_90]
0x1800096c8  mov     rcx, rdi; this
0x1800096cb  call    ?CheckForSkippedDeploymentStatus@CSubscription@Dfdll@@IEAAJAEAV?$CIUnknownBasedPointer@UIDefinitionIdentity@@@2@AEAH@Z; Dfdll::CSubscription::CheckForSkippedDeploymentStatus(Dfdll::CIUnknownBasedPointer<IDefinitionIdentity> &,int &)
0x1800096d0  test    eax, eax
0x1800096d2  js      short loc_1800096DD
0x1800096d4  cmp     [rbp+57h+var_80], 0
0x1800096d8  jz      short loc_1800096DD
0x1800096da  and     dword ptr [rsi], 0
0x1800096dd  xor     ebx, ebx
0x1800096df  lea     rax, ??_7?$CInterfacePointer@UIUnknown@@@Dfdll@@6B@; const Dfdll::CInterfacePointer<IUnknown>::`vftable'
0x1800096e6  mov     [rbp+57h+var_90], rax
0x1800096ea  mov     rcx, [rbp+57h+var_88]
0x1800096ee  test    rcx, rcx
0x1800096f1  jz      short loc_180009700
0x1800096f3  mov     rax, [rcx]
0x1800096f6  mov     rax, [rax+10h]
0x1800096fa  call    cs:__guard_dispatch_icall_fptr
0x180009700  and     [rbp+57h+var_88], 0
0x180009705  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x18000970c  mov     [rbp+57h+var_90], rax
0x180009710  mov     [rbp+57h+var_78], r15
0x180009714  mov     [rbp+57h+var_70], r12
0x180009718  mov     rcx, [rbp+57h+var_68]; void *
0x18000971c  test    rcx, rcx
0x18000971f  jz      short loc_180009727
0x180009721  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009726  nop
0x180009727  jmp     loc_18000965B
```
