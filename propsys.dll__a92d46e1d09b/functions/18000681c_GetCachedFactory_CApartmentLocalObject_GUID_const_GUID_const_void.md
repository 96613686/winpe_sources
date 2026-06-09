# _GetCachedFactory(CApartmentLocalObject *,_GUID const &,_GUID const &,void * *)

- ea: `0x18000681c`
- end: `0x180006b2b`
- name: `?_GetCachedFactory@@YAJPEAVCApartmentLocalObject@@AEBU_GUID@@1PEAPEAX@Z`
- size: `783`
- prototype: `__int64 __fastcall(struct CApartmentLocalObject *this, IID *rclsid, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800062e0`
- `0x180006bc0`
- `0x180007190`
- `0x180007fb0`

## callees

- `0x1800059cc`
- `0x180005bb0`
- `0x1800062b0`
- `0x18000681c`
- `0x1800070d0`
- `0x1800479d0`
- `0x18006bb14`
- `0x18006ed20`
- `0x18006f1fc`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180006aca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180006aca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006921`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006921`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000686b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000686b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006a7e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006a7e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800068c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800068c2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006862`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006862`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800069b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006b03`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800069b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006b03`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180006883`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180006883`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180006a5c`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180006a5c`

## pseudocode

```c
__int64 __fastcall _GetCachedFactory(
        struct CApartmentLocalObject *this,
        IID *rclsid,
        const struct _GUID *a3,
        void **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r12
  HRESULT ApartmentType; // ebx
  DWORD v9; // ebp
  volatile signed __int32 *Value; // rax
  volatile signed __int32 *v11; // rdi
  __int64 (__fastcall ***v12)(_QWORD, GUID *, void **); // rcx
  unsigned int v14; // edi
  LPVOID v15; // rcx
  CCachedSTAObject *v16; // rax
  CCachedSTAObject *v17; // rax
  CCachedSTAObject *v18; // rsi
  APTTYPE pAptType; // [rsp+30h] [rbp-58h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+38h] [rbp-50h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  *a4 = 0;
  InitOnceExecuteOnce(
    (PINIT_ONCE)this + 2,
    _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_,
    (char *)this + 24,
    0);
  EnterCriticalSection(v4);
  pAptType = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_11;
  if ( pAptType == APTTYPE_STA )
  {
LABEL_3:
    ApartmentType = CApartmentLocalObject::_DelayAllocateTLS(this);
    if ( ApartmentType < 0 )
      goto LABEL_11;
    v9 = *(_DWORD *)this;
    ApartmentType = 1;
    *a4 = 0;
    if ( v9 == -1 )
      goto LABEL_11;
    Value = (volatile signed __int32 *)TlsGetValue(v9);
    v11 = Value;
    if ( Value )
    {
      if ( *((_DWORD *)Value + 10) )
      {
        _InterlockedIncrement(Value + 2);
        *a4 = 0;
        v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)Value + 4);
        if ( v12 )
          ApartmentType = (**v12)(v12, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, a4);
        else
          ApartmentType = 1;
LABEL_9:
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          operator delete((void *)v11, (const struct std::nothrow_t *)0x30);
        goto LABEL_11;
      }
    }
    else
    {
      v11 = 0;
      v16 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
      if ( v16 && (v17 = CCachedSTAObject::CCachedSTAObject(v16), (v18 = v17) != 0) )
      {
        *((_DWORD *)v17 + 6) = v9;
        ApartmentType = CoRegisterInitializeSpy((IInitializeSpy *)v17, (ULARGE_INTEGER *)v17 + 2);
        if ( ApartmentType >= 0 )
        {
          ApartmentType = 1;
          *((_DWORD *)v18 + 10) = 1;
          if ( !*(_QWORD *)&CCachedSTAObject::s_hmod )
            GetModuleHandleExW(4u, &CCachedSTAObject::s_hmod, (HMODULE *)&CCachedSTAObject::s_hmod);
          TlsSetValue(v9, v18);
          v11 = (volatile signed __int32 *)v18;
          _InterlockedAdd((volatile signed __int32 *)v18 + 2, 1u);
        }
        CCachedSTAObject::Release(v18);
      }
      else
      {
        ApartmentType = -2147024882;
      }
      if ( ApartmentType >= 0 )
        goto LABEL_9;
    }
    ApartmentType = 1;
    goto LABEL_11;
  }
  if ( pAptType != APTTYPE_MTA )
  {
    if ( pAptType == APTTYPE_NA )
    {
      ApartmentType = CApartmentLocalObject::_GetInterfaceFromGIT(
                        (CApartmentLocalObject *)(unsigned int)(pAptType - 2),
                        *((_DWORD *)this + 2),
                        &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                        a4);
      goto LABEL_11;
    }
    if ( pAptType != APTTYPE_MAINSTA )
    {
      ApartmentType = -2147221008;
      goto LABEL_11;
    }
    goto LABEL_3;
  }
  v14 = *((_DWORD *)this + 1);
  ApartmentType = 1;
  *a4 = 0;
  if ( v14 )
  {
    v15 = g_pgit;
    if ( !g_pgit )
    {
      ApartmentType = CoCreateInstance(
                        &CLSID_StdGlobalInterfaceTable,
                        0,
                        1u,
                        &GUID_00000146_0000_0000_c000_000000000046,
                        &g_pgit);
      if ( ApartmentType < 0 )
        goto LABEL_11;
      v15 = g_pgit;
    }
    ApartmentType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)v15 + 40LL))(
                      v15,
                      v14,
                      &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                      a4);
    if ( ApartmentType < 0 )
      ApartmentType = 1;
  }
LABEL_11:
  LeaveCriticalSection(v4);
  if ( ApartmentType == 1 )
  {
    *(_QWORD *)pAptQualifier = 0;
    ApartmentType = CoCreateInstance(rclsid, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)pAptQualifier);
    if ( ApartmentType >= 0 )
    {
      ApartmentType = CApartmentLocalObject::TrySetApartmentObject(
                        this,
                        *(struct IUnknown **)pAptQualifier,
                        &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                        a4);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
    }
  }
  return (unsigned int)ApartmentType;
}

```

## disassembly

```asm
0x18000681c  mov     [rsp+arg_10], rbx
0x180006821  push    rbp
0x180006822  push    rsi
0x180006823  push    rdi
0x180006824  push    r12
0x180006826  push    r13
0x180006828  push    r14
0x18000682a  push    r15
0x18000682c  sub     rsp, 50h
0x180006830  mov     rax, cs:__security_cookie
0x180006837  xor     rax, rsp
0x18000683a  mov     [rsp+88h+var_48], rax
0x18000683f  lea     r12, [rcx+18h]
0x180006843  mov     r14, r9
0x180006846  mov     r13, rdx
0x180006849  mov     r15, rcx
0x18000684c  xor     esi, esi
0x18000684e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180006855  mov     [r9], rsi
0x180006858  add     rcx, 10h; InitOnce
0x18000685c  xor     r9d, r9d; Context
0x18000685f  mov     r8, r12; Parameter
0x180006862  call    cs:__imp_InitOnceExecuteOnce
0x180006868  mov     rcx, r12; lpCriticalSection
0x18000686b  call    cs:__imp_EnterCriticalSection
0x180006871  lea     rdx, [rsp+88h+pAptQualifier]; pAptQualifier
0x180006876  mov     [rsp+88h+pAptType], esi
0x18000687a  lea     rcx, [rsp+88h+pAptType]; pAptType
0x18000687f  mov     [rsp+88h+pAptQualifier], esi
0x180006883  call    cs:__imp_CoGetApartmentType
0x180006889  lea     ebp, [rsi+1]
0x18000688c  mov     ebx, eax
0x18000688e  test    eax, eax
0x180006890  js      loc_18000691E
0x180006896  mov     ecx, [rsp+88h+pAptType]
0x18000689a  test    ecx, ecx
0x18000689c  jnz     loc_180006952
0x1800068a2  mov     rcx, r15; this
0x1800068a5  call    ?_DelayAllocateTLS@CApartmentLocalObject@@AEAAJXZ; CApartmentLocalObject::_DelayAllocateTLS(void)
0x1800068aa  mov     ebx, eax
0x1800068ac  test    eax, eax
0x1800068ae  js      short loc_18000691E
0x1800068b0  mov     ebp, [r15]
0x1800068b3  mov     ebx, 1
0x1800068b8  mov     [r14], rsi
0x1800068bb  cmp     ebp, 0FFFFFFFFh
0x1800068be  jz      short loc_180006919
0x1800068c0  mov     ecx, ebp; dwTlsIndex
0x1800068c2  call    cs:__imp_TlsGetValue
0x1800068c8  mov     rdi, rax
0x1800068cb  test    rax, rax
0x1800068ce  jz      loc_180006A29
0x1800068d4  cmp     [rax+28h], esi
0x1800068d7  jz      loc_180006B1F
0x1800068dd  lock inc dword ptr [rax+8]
0x1800068e1  mov     [r14], rsi
0x1800068e4  mov     rcx, [rdi+20h]
0x1800068e8  test    rcx, rcx
0x1800068eb  jz      loc_180006AA8
0x1800068f1  mov     rax, [rcx]
0x1800068f4  lea     rdx, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x1800068fb  mov     r8, r14
0x1800068fe  mov     rax, [rax]
0x180006901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006906  mov     ebx, eax
0x180006908  or      eax, 0FFFFFFFFh
0x18000690b  lock xadd [rdi+8], eax
0x180006910  cmp     eax, 1
0x180006913  jz      loc_180006A17
0x180006919  mov     ebp, 1
0x18000691e  mov     rcx, r12; lpCriticalSection
0x180006921  call    cs:__imp_LeaveCriticalSection
0x180006927  cmp     ebx, ebp
0x180006929  jz      short loc_180006998
0x18000692b  mov     eax, ebx
0x18000692d  mov     rcx, [rsp+88h+var_48]
0x180006932  xor     rcx, rsp; StackCookie
0x180006935  call    __security_check_cookie
0x18000693a  mov     rbx, [rsp+88h+arg_10]
0x180006942  add     rsp, 50h
0x180006946  pop     r15
0x180006948  pop     r14
0x18000694a  pop     r13
0x18000694c  pop     r12
0x18000694e  pop     rdi
0x18000694f  pop     rsi
0x180006950  pop     rbp
0x180006951  retn
0x180006952  sub     ecx, ebp
0x180006954  jnz     loc_1800069F5
0x18000695a  mov     edi, [r15+4]
0x18000695e  mov     ebx, ebp
0x180006960  mov     [r14], rsi
0x180006963  test    edi, edi
0x180006965  jz      short loc_18000691E
0x180006967  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x18000696e  test    rcx, rcx
0x180006971  jz      loc_180006AE4
0x180006977  mov     rax, [rcx]
0x18000697a  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x180006981  mov     r9, r14
0x180006984  mov     edx, edi
0x180006986  mov     rax, [rax+28h]
0x18000698a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000698f  test    eax, eax
0x180006991  mov     ebx, eax
0x180006993  cmovs   ebx, ebp
0x180006996  jmp     short loc_18000691E
0x180006998  lea     rax, [rsp+88h+pAptQualifier]
0x18000699d  mov     qword ptr [rsp+88h+pAptQualifier], rsi
0x1800069a2  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800069a9  mov     [rsp+88h+ppv], rax; ppv
0x1800069ae  mov     r8d, ebp; dwClsContext
0x1800069b1  xor     edx, edx; pUnkOuter
0x1800069b3  mov     rcx, r13; rclsid
0x1800069b6  call    cs:__imp_CoCreateInstance
0x1800069bc  mov     ebx, eax
0x1800069be  test    eax, eax
0x1800069c0  js      loc_18000692B
0x1800069c6  mov     rdx, qword ptr [rsp+88h+pAptQualifier]; struct IUnknown *
0x1800069cb  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; struct _GUID *
0x1800069d2  mov     r9, r14; void **
0x1800069d5  mov     rcx, r15; this
0x1800069d8  call    ?TrySetApartmentObject@CApartmentLocalObject@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::TrySetApartmentObject(IUnknown *,_GUID const &,void * *)
0x1800069dd  mov     rcx, qword ptr [rsp+88h+pAptQualifier]
0x1800069e2  mov     ebx, eax
0x1800069e4  mov     rax, [rcx]
0x1800069e7  mov     rax, [rax+10h]
0x1800069eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f0  jmp     loc_18000692B
0x1800069f5  sub     ecx, ebp; this
0x1800069f7  jnz     loc_180006AD2
0x1800069fd  mov     edx, [r15+8]; unsigned int
0x180006a01  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; struct _GUID *
0x180006a08  mov     r9, r14; void **
0x180006a0b  call    ?_GetInterfaceFromGIT@CApartmentLocalObject@@AEAAJKAEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::_GetInterfaceFromGIT(ulong,_GUID const &,void * *)
0x180006a10  mov     ebx, eax
0x180006a12  jmp     loc_18000691E
0x180006a17  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180006a1c  mov     rcx, rdi; void *
0x180006a1f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006a24  jmp     loc_180006919
0x180006a29  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006a30  mov     ecx, 30h ; '0'; unsigned __int64
0x180006a35  mov     rdi, rsi
0x180006a38  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006a3d  test    rax, rax
0x180006a40  jz      short loc_180006AB4
0x180006a42  mov     rcx, rax; this
0x180006a45  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x180006a4a  mov     rsi, rax
0x180006a4d  test    rax, rax
0x180006a50  jz      short loc_180006AB2
0x180006a52  lea     rdx, [rax+10h]; puliCookie
0x180006a56  mov     [rax+18h], ebp
0x180006a59  mov     rcx, rax; pSpy
0x180006a5c  call    cs:__imp_CoRegisterInitializeSpy
0x180006a62  mov     ebx, eax
0x180006a64  test    eax, eax
0x180006a66  js      short loc_180006A8B
0x180006a68  mov     ebx, 1
0x180006a6d  mov     [rsi+28h], ebx
0x180006a70  cmp     cs:?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * CCachedSTAObject::s_hmod
0x180006a77  jz      short loc_180006ABB
0x180006a79  mov     rdx, rsi; lpTlsValue
0x180006a7c  mov     ecx, ebp; dwTlsIndex
0x180006a7e  call    cs:__imp_TlsSetValue
0x180006a84  mov     rdi, rsi
0x180006a87  lock add [rsi+8], ebx
0x180006a8b  mov     rcx, rsi; this
0x180006a8e  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x180006a93  xor     esi, esi
0x180006a95  test    ebx, ebx
0x180006a97  js      loc_180006B1F
0x180006a9d  jz      loc_1800068E1
0x180006aa3  jmp     loc_180006908
0x180006aa8  mov     ebx, 1
0x180006aad  jmp     loc_180006908
0x180006ab2  xor     esi, esi
0x180006ab4  mov     ebx, 8007000Eh
0x180006ab9  jmp     short loc_180006A95
0x180006abb  lea     rdx, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; lpModuleName
0x180006ac2  mov     ecx, 4; dwFlags
0x180006ac7  mov     r8, rdx; phModule
0x180006aca  call    cs:__imp_GetModuleHandleExW
0x180006ad0  jmp     short loc_180006A79
0x180006ad2  cmp     ecx, ebp
0x180006ad4  jz      loc_1800068A2
0x180006ada  mov     ebx, 800401F0h
0x180006adf  jmp     loc_18000691E
0x180006ae4  lea     rax, ?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180006aeb  mov     r8d, ebp; dwClsContext
0x180006aee  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180006af5  mov     [rsp+88h+ppv], rax; ppv
0x180006afa  xor     edx, edx; pUnkOuter
0x180006afc  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006b03  call    cs:__imp_CoCreateInstance
0x180006b09  mov     ebx, eax
0x180006b0b  test    eax, eax
0x180006b0d  js      loc_18000691E
0x180006b13  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180006b1a  jmp     loc_180006977
0x180006b1f  mov     ebp, 1
0x180006b24  mov     ebx, ebp
0x180006b26  jmp     loc_18000691E
```
