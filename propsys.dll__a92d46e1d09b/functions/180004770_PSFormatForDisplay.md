# PSFormatForDisplay

- ea: `0x180004770`
- end: `0x180004c39`
- name: `PSFormatForDisplay`
- size: `1225`
- prototype: `HRESULT __stdcall(const PROPERTYKEY *const propkey, const PROPVARIANT *const propvar, PROPDESC_FORMAT_FLAGS pdfFlags, LPWSTR pwszText, DWORD cchText)`
- caller_count: `24`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180004280`
- `0x180004320`
- `0x1800043c0`
- `0x180004460`
- `0x180004690`
- `0x180067170`
- `0x18007e3e0`
- `0x18007e480`
- `0x18007e520`
- `0x18007e5c0`
- `0x18007e660`
- `0x18007e700`
- `0x18007e7a0`
- `0x18007e840`
- `0x18007e8e0`
- `0x18007e980`
- `0x18007ea20`
- `0x18007eac0`
- `0x18007eb60`
- `0x18007ec00`
- `0x18007eca0`
- `0x18007ed40`
- `0x18007ede0`
- `0x18007ee80`

## callees

- `0x180004770`
- `0x1800056c0`
- `0x1800059cc`
- `0x1800062b0`
- `0x18002e164`
- `0x18002e200`
- `0x18006bb14`
- `0x18006ed20`
- `0x18006f1fc`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004bde`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004bde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800048ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004b8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004ac4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180004ac4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004860`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004860`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800049cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800049cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800049aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800049aa`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800047ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800047ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004a2c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004b0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004a2c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004b0e`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180004813`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180004813`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180004a98`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180004a98`

## pseudocode

```c
HRESULT __stdcall PSFormatForDisplay(
        const PROPERTYKEY *const propkey,
        const PROPVARIANT *const propvar,
        PROPDESC_FORMAT_FLAGS pdfFlags,
        LPWSTR pwszText,
        DWORD cchText)
{
  PROPDESC_FORMAT_FLAGS v6; // r14d
  int ApartmentType; // ebx
  DWORD v10; // r15d
  volatile signed __int32 *Value; // rax
  CCachedSTAObject *v12; // rbp
  __int64 (__fastcall ***v13)(_QWORD, GUID *, void **); // rcx
  unsigned int v15; // ebp
  LPVOID v16; // rcx
  DWORD v17; // ecx
  CCachedSTAObject *v18; // rax
  CCachedSTAObject *v19; // rax
  CCachedSTAObject *v20; // rcx
  struct IUnknown *v21; // r15
  APTTYPE pAptType; // [rsp+40h] [rbp-68h] BYREF
  PROPDESC_FORMAT_FLAGS v23; // [rsp+44h] [rbp-64h]
  void *v24; // [rsp+48h] [rbp-60h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+50h] [rbp-58h] BYREF

  v23 = pdfFlags;
  v6 = pdfFlags;
  if ( !pwszText )
    return -2147467261;
  if ( cchText )
  {
    *pwszText = 0;
    v24 = 0;
    InitOnceExecuteOnce(
      &InitOnce,
      _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_,
      &CriticalSection,
      0);
    EnterCriticalSection(&CriticalSection);
    pAptType = APTTYPE_STA;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
    if ( ApartmentType < 0 )
      goto LABEL_14;
    switch ( pAptType )
    {
      case APTTYPE_STA:
LABEL_5:
        if ( g_aloPropertySystem == -1 )
        {
          v17 = TlsAlloc();
          if ( v17 == -1 )
          {
            ApartmentType = -2147024882;
            LeaveCriticalSection(&CriticalSection);
            v6 = v23;
            goto LABEL_15;
          }
          if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_aloPropertySystem, v17, -1) != -1 )
            TlsFree(v17);
        }
        v10 = g_aloPropertySystem;
        ApartmentType = 1;
        v24 = 0;
        if ( g_aloPropertySystem == -1 )
          goto LABEL_13;
        Value = (volatile signed __int32 *)TlsGetValue(g_aloPropertySystem);
        v12 = (CCachedSTAObject *)Value;
        if ( Value )
        {
          if ( *((_DWORD *)Value + 10) )
          {
            _InterlockedIncrement(Value + 2);
            v24 = 0;
            v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)Value + 4);
            if ( v13 )
              ApartmentType = (**v13)(v13, &GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3, &v24);
            else
              ApartmentType = 1;
LABEL_11:
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 2, 0xFFFFFFFF) == 1 )
              operator delete(v12, (const struct std::nothrow_t *)0x30);
            goto LABEL_13;
          }
        }
        else
        {
          v18 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
          if ( v18 )
          {
            v19 = CCachedSTAObject::CCachedSTAObject(v18);
            *(_QWORD *)pAptQualifier = v19;
            v12 = v19;
            if ( v19 )
            {
              *((_DWORD *)v19 + 6) = v10;
              ApartmentType = CoRegisterInitializeSpy((IInitializeSpy *)v19, (ULARGE_INTEGER *)v19 + 2);
              if ( ApartmentType < 0 )
              {
                v20 = *(CCachedSTAObject **)pAptQualifier;
                v12 = 0;
              }
              else
              {
                ApartmentType = 1;
                *((_DWORD *)v12 + 10) = 1;
                if ( !*(_QWORD *)&CCachedSTAObject::s_hmod )
                  GetModuleHandleExW(4u, &CCachedSTAObject::s_hmod, (HMODULE *)&CCachedSTAObject::s_hmod);
                TlsSetValue(v10, v12);
                v20 = v12;
                _InterlockedIncrement((volatile signed __int32 *)v12 + 2);
              }
              CCachedSTAObject::Release(v20);
              if ( ApartmentType >= 0 )
                goto LABEL_11;
            }
          }
        }
        ApartmentType = 1;
LABEL_13:
        v6 = v23;
        goto LABEL_14;
      case APTTYPE_MTA:
        v15 = dword_1800F0E24;
        v24 = 0;
        ApartmentType = 1;
        if ( !dword_1800F0E24 )
          goto LABEL_14;
        v16 = g_pgit;
        if ( g_pgit )
          goto LABEL_21;
        break;
      case APTTYPE_NA:
        v15 = dword_1800F0E28;
        v24 = 0;
        ApartmentType = 1;
        if ( !dword_1800F0E28 )
        {
LABEL_14:
          LeaveCriticalSection(&CriticalSection);
          if ( ApartmentType == 1 )
          {
            *(_QWORD *)pAptQualifier = 0;
            ApartmentType = CoCreateInstance(
                              &CLSID_PropertySystem,
                              0,
                              1u,
                              &GUID_00000000_0000_0000_c000_000000000046,
                              (LPVOID *)pAptQualifier);
            if ( ApartmentType < 0 )
              return ApartmentType;
            v21 = *(struct IUnknown **)pAptQualifier;
            v24 = 0;
            CApartmentLocalObject::_EnterCriticalSection((CApartmentLocalObject *)&g_aloPropertySystem);
            ApartmentType = CApartmentLocalObject::_GetApartmentObject(
                              (CApartmentLocalObject *)&g_aloPropertySystem,
                              &GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3,
                              &v24);
            if ( ApartmentType == 1 )
            {
              ApartmentType = CApartmentLocalObject::_SetApartmentObject(
                                (CApartmentLocalObject *)&g_aloPropertySystem,
                                v21);
              if ( ApartmentType >= 0 )
                ApartmentType = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, void **))v21->lpVtbl->QueryInterface)(
                                  v21,
                                  &GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3,
                                  &v24);
            }
            LeaveCriticalSection(&CriticalSection);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
          }
LABEL_15:
          if ( ApartmentType >= 0 )
          {
            ApartmentType = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *const, const PROPVARIANT *const, _QWORD, LPWSTR, DWORD))(*(_QWORD *)v24 + 56LL))(
                              v24,
                              propkey,
                              propvar,
                              (unsigned int)v6,
                              pwszText,
                              cchText);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
          }
          return ApartmentType;
        }
        v16 = g_pgit;
        if ( g_pgit )
        {
LABEL_21:
          ApartmentType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)v16 + 40LL))(
                            v16,
                            v15,
                            &GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3,
                            &v24);
          if ( ApartmentType < 0 )
            ApartmentType = 1;
          goto LABEL_14;
        }
        break;
      case APTTYPE_MAINSTA:
        goto LABEL_5;
      default:
        ApartmentType = -2147221008;
        LeaveCriticalSection(&CriticalSection);
        goto LABEL_15;
    }
    ApartmentType = CoCreateInstance(
                      &CLSID_StdGlobalInterfaceTable,
                      0,
                      1u,
                      &GUID_00000146_0000_0000_c000_000000000046,
                      &g_pgit);
    if ( ApartmentType < 0 )
      goto LABEL_14;
    v16 = g_pgit;
    goto LABEL_21;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180004770  mov     r11, rsp
0x180004773  push    rsi
0x180004774  push    r12
0x180004776  push    r13
0x180004778  push    r14
0x18000477a  sub     rsp, 88h
0x180004781  mov     rax, cs:__security_cookie
0x180004788  xor     rax, rsp
0x18000478b  mov     [rsp+0A8h+var_50], rax
0x180004790  mov     [rsp+0A8h+var_64], r8d
0x180004795  mov     rsi, r9
0x180004798  mov     r14d, r8d
0x18000479b  mov     r13, rdx
0x18000479e  mov     r12, rcx
0x1800047a1  test    r9, r9
0x1800047a4  jz      loc_180004C2F
0x1800047aa  mov     [r11-38h], rdi
0x1800047ae  mov     edi, [rsp+0A8h+cchText]
0x1800047b5  test    edi, edi
0x1800047b7  jz      loc_180004BE9
0x1800047bd  mov     [r11-28h], rbx
0x1800047c1  lea     r8, CriticalSection; Parameter
0x1800047c8  mov     [r11-40h], r15
0x1800047cc  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800047d3  xor     r15d, r15d
0x1800047d6  mov     [r11-30h], rbp
0x1800047da  mov     [r9], r15w
0x1800047de  lea     rcx, InitOnce; InitOnce
0x1800047e5  xor     r9d, r9d; Context
0x1800047e8  mov     [r11-60h], r15
0x1800047ec  call    cs:__imp_InitOnceExecuteOnce
0x1800047f2  lea     rcx, CriticalSection; lpCriticalSection
0x1800047f9  call    cs:__imp_EnterCriticalSection
0x1800047ff  lea     rdx, [rsp+0A8h+pAptQualifier]; pAptQualifier
0x180004804  mov     [rsp+0A8h+pAptType], r15d
0x180004809  lea     rcx, [rsp+0A8h+pAptType]; pAptType
0x18000480e  mov     [rsp+0A8h+pAptQualifier], r15d
0x180004813  call    cs:__imp_CoGetApartmentType
0x180004819  mov     ebx, eax
0x18000481b  test    eax, eax
0x18000481d  js      loc_1800048C7
0x180004823  mov     edx, [rsp+0A8h+pAptType]
0x180004827  test    edx, edx
0x180004829  jnz     loc_18000494C
0x18000482f  cmp     cs:?g_aloPropertySystem@@3VCApartmentLocalObject@@A, 0FFFFFFFFh; CApartmentLocalObject g_aloPropertySystem
0x180004836  mov     r14d, 0FFFFFFFFh
0x18000483c  jz      loc_1800049AA
0x180004842  mov     r15d, cs:?g_aloPropertySystem@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloPropertySystem
0x180004849  mov     ebx, 1
0x18000484e  mov     [rsp+0A8h+var_60], 0
0x180004857  cmp     r15d, 0FFFFFFFFh
0x18000485b  jz      short loc_1800048BF
0x18000485d  mov     ecx, r15d; dwTlsIndex
0x180004860  call    cs:__imp_TlsGetValue
0x180004866  mov     rbp, rax
0x180004869  test    rax, rax
0x18000486c  jz      loc_180004A5A
0x180004872  cmp     dword ptr [rax+28h], 0
0x180004876  jz      loc_180004BC1
0x18000487c  lock inc dword ptr [rax+8]
0x180004880  mov     [rsp+0A8h+var_60], 0
0x180004889  mov     rcx, [rbp+20h]
0x18000488d  test    rcx, rcx
0x180004890  jz      loc_180004BAB
0x180004896  mov     rax, [rcx]
0x180004899  lea     r8, [rsp+0A8h+var_60]
0x18000489e  lea     rdx, _GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3
0x1800048a5  mov     rax, [rax]
0x1800048a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ad  mov     ebx, eax
0x1800048af  lock xadd [rbp+8], r14d
0x1800048b5  cmp     r14d, 1
0x1800048b9  jz      loc_180004A48
0x1800048bf  mov     r14d, [rsp+0A8h+var_64]
0x1800048c4  xor     r15d, r15d
0x1800048c7  lea     rcx, CriticalSection; lpCriticalSection
0x1800048ce  call    cs:__imp_LeaveCriticalSection
0x1800048d4  cmp     ebx, 1
0x1800048d7  jz      loc_180004AE9
0x1800048dd  test    ebx, ebx
0x1800048df  js      short loc_180004917
0x1800048e1  mov     rcx, [rsp+0A8h+var_60]
0x1800048e6  mov     r9d, r14d
0x1800048e9  mov     [rsp+0A8h+var_80], edi
0x1800048ed  mov     r8, r13
0x1800048f0  mov     rdx, r12
0x1800048f3  mov     [rsp+0A8h+ppv], rsi
0x1800048f8  mov     rax, [rcx]
0x1800048fb  mov     rax, [rax+38h]
0x1800048ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004904  mov     rcx, [rsp+0A8h+var_60]
0x180004909  mov     ebx, eax
0x18000490b  mov     rax, [rcx]
0x18000490e  mov     rax, [rax+10h]
0x180004912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004917  mov     rbp, [rsp+0A8h+var_30]
0x18000491c  mov     eax, ebx
0x18000491e  mov     rbx, [rsp+0A8h+var_28]
0x180004926  mov     r15, [rsp+0A8h+var_40]
0x18000492b  mov     rdi, [rsp+0A8h+var_38]
0x180004930  mov     rcx, [rsp+0A8h+var_50]
0x180004935  xor     rcx, rsp; StackCookie
0x180004938  call    __security_check_cookie
0x18000493d  add     rsp, 88h
0x180004944  pop     r14
0x180004946  pop     r13
0x180004948  pop     r12
0x18000494a  pop     rsi
0x18000494b  retn
0x18000494c  sub     edx, 1
0x18000494f  jnz     loc_1800049DA
0x180004955  mov     ebp, cs:dword_1800F0E24
0x18000495b  mov     edx, 1
0x180004960  mov     [rsp+0A8h+var_60], r15
0x180004965  mov     ebx, edx
0x180004967  test    ebp, ebp
0x180004969  jz      loc_1800048C7
0x18000496f  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180004976  test    rcx, rcx
0x180004979  jz      loc_180004A0D
0x18000497f  mov     rax, [rcx]
0x180004982  lea     r9, [rsp+0A8h+var_60]
0x180004987  lea     r8, _GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3
0x18000498e  mov     edx, ebp
0x180004990  mov     rax, [rax+28h]
0x180004994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004999  mov     ebx, eax
0x18000499b  test    eax, eax
0x18000499d  mov     eax, 1
0x1800049a2  cmovs   ebx, eax
0x1800049a5  jmp     loc_1800048C7
0x1800049aa  call    cs:__imp_TlsAlloc
0x1800049b0  mov     ecx, eax; dwTlsIndex
0x1800049b2  cmp     eax, 0FFFFFFFFh
0x1800049b5  jz      loc_180004C13
0x1800049bb  mov     eax, r14d
0x1800049be  lock cmpxchg cs:?g_aloPropertySystem@@3VCApartmentLocalObject@@A, ecx; CApartmentLocalObject g_aloPropertySystem
0x1800049c6  cmp     eax, 0FFFFFFFFh
0x1800049c9  jz      loc_180004842
0x1800049cf  call    cs:__imp_TlsFree
0x1800049d5  jmp     loc_180004842
0x1800049da  sub     edx, 1
0x1800049dd  jnz     loc_180004BF3
0x1800049e3  mov     ebp, cs:dword_1800F0E28
0x1800049e9  mov     edx, 1
0x1800049ee  mov     [rsp+0A8h+var_60], r15
0x1800049f3  mov     ebx, edx
0x1800049f5  test    ebp, ebp
0x1800049f7  jz      loc_1800048C7
0x1800049fd  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180004a04  test    rcx, rcx
0x180004a07  jnz     loc_18000497F
0x180004a0d  lea     rax, ?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180004a14  mov     r8d, edx; dwClsContext
0x180004a17  xor     edx, edx; pUnkOuter
0x180004a19  mov     [rsp+0A8h+ppv], rax; ppv
0x180004a1e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180004a25  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004a2c  call    cs:__imp_CoCreateInstance
0x180004a32  mov     ebx, eax
0x180004a34  test    eax, eax
0x180004a36  js      loc_1800048C7
0x180004a3c  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180004a43  jmp     loc_18000497F
0x180004a48  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180004a4d  mov     rcx, rbp; void *
0x180004a50  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004a55  jmp     loc_1800048BF
0x180004a5a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004a61  mov     ecx, 30h ; '0'; unsigned __int64
0x180004a66  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004a6b  test    rax, rax
0x180004a6e  jz      loc_180004BC1
0x180004a74  mov     rcx, rax; this
0x180004a77  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x180004a7c  mov     qword ptr [rsp+0A8h+pAptQualifier], rax
0x180004a81  mov     rbp, rax
0x180004a84  test    rax, rax
0x180004a87  jz      loc_180004BC1
0x180004a8d  lea     rdx, [rax+10h]; puliCookie
0x180004a91  mov     [rax+18h], r15d
0x180004a95  mov     rcx, rax; pSpy
0x180004a98  call    cs:__imp_CoRegisterInitializeSpy
0x180004a9e  mov     ebx, eax
0x180004aa0  test    eax, eax
0x180004aa2  js      loc_180004BB5
0x180004aa8  mov     ebx, 1
0x180004aad  mov     [rbp+28h], ebx
0x180004ab0  cmp     cs:?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CCachedSTAObject::s_hmod
0x180004ab8  jz      loc_180004BCB
0x180004abe  mov     rdx, rbp; lpTlsValue
0x180004ac1  mov     ecx, r15d; dwTlsIndex
0x180004ac4  call    cs:__imp_TlsSetValue
0x180004aca  mov     rcx, rbp; this
0x180004acd  lock inc dword ptr [rcx+8]
0x180004ad1  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x180004ad6  test    ebx, ebx
0x180004ad8  js      loc_180004BC1
0x180004ade  jz      loc_180004880
0x180004ae4  jmp     loc_1800048AF
0x180004ae9  lea     rax, [rsp+0A8h+pAptQualifier]
0x180004aee  mov     qword ptr [rsp+0A8h+pAptQualifier], r15
0x180004af3  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180004afa  mov     [rsp+0A8h+ppv], rax; ppv
0x180004aff  xor     edx, edx; pUnkOuter
0x180004b01  lea     rcx, CLSID_PropertySystem; rclsid
0x180004b08  mov     r8d, 1; dwClsContext
0x180004b0e  call    cs:__imp_CoCreateInstance
0x180004b14  mov     ebx, eax
0x180004b16  test    eax, eax
0x180004b18  js      loc_180004917
0x180004b1e  mov     r15, qword ptr [rsp+0A8h+pAptQualifier]
0x180004b23  lea     rcx, ?g_aloPropertySystem@@3VCApartmentLocalObject@@A; this
0x180004b2a  mov     [rsp+0A8h+var_60], 0
0x180004b33  call    ?_EnterCriticalSection@CApartmentLocalObject@@AEAAXXZ; CApartmentLocalObject::_EnterCriticalSection(void)
0x180004b38  lea     r8, [rsp+0A8h+var_60]; void **
0x180004b3d  lea     rdx, _GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3; struct _GUID *
0x180004b44  lea     rcx, ?g_aloPropertySystem@@3VCApartmentLocalObject@@A; this
0x180004b4b  call    ?_GetApartmentObject@CApartmentLocalObject@@AEAAJAEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::_GetApartmentObject(_GUID const &,void * *)
0x180004b50  mov     ebx, eax
0x180004b52  cmp     eax, 1
0x180004b55  jnz     short loc_180004B88
0x180004b57  mov     rdx, r15; struct IUnknown *
0x180004b5a  lea     rcx, ?g_aloPropertySystem@@3VCApartmentLocalObject@@A; this
0x180004b61  call    ?_SetApartmentObject@CApartmentLocalObject@@AEAAJPEAUIUnknown@@@Z; CApartmentLocalObject::_SetApartmentObject(IUnknown *)
0x180004b66  mov     ebx, eax
0x180004b68  test    eax, eax
0x180004b6a  js      short loc_180004B88
0x180004b6c  mov     rax, [r15]
0x180004b6f  lea     r8, [rsp+0A8h+var_60]
0x180004b74  lea     rdx, _GUID_ca724e8a_c3e6_442b_88a4_6fb0db8035a3
0x180004b7b  mov     rcx, r15
0x180004b7e  mov     rax, [rax]
0x180004b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b86  mov     ebx, eax
0x180004b88  lea     rcx, CriticalSection; lpCriticalSection
0x180004b8f  call    cs:__imp_LeaveCriticalSection
0x180004b95  mov     rcx, qword ptr [rsp+0A8h+pAptQualifier]
0x180004b9a  mov     rax, [rcx]
0x180004b9d  mov     rax, [rax+10h]
0x180004ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ba6  jmp     loc_1800048DD
0x180004bab  mov     ebx, 1
0x180004bb0  jmp     loc_1800048AF
0x180004bb5  mov     rcx, qword ptr [rsp+0A8h+pAptQualifier]
0x180004bba  xor     ebp, ebp
0x180004bbc  jmp     loc_180004AD1
0x180004bc1  mov     ebx, 1
0x180004bc6  jmp     loc_1800048BF
0x180004bcb  lea     r8, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; phModule
0x180004bd2  mov     ecx, 4; dwFlags
0x180004bd7  lea     rdx, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; lpModuleName
0x180004bde  call    cs:__imp_GetModuleHandleExW
0x180004be4  jmp     loc_180004ABE
0x180004be9  mov     eax, 80070057h
0x180004bee  jmp     loc_18000492B
0x180004bf3  cmp     edx, 1
0x180004bf6  jz      loc_18000482F
0x180004bfc  lea     rcx, CriticalSection; lpCriticalSection
0x180004c03  mov     ebx, 800401F0h
0x180004c08  call    cs:__imp_LeaveCriticalSection
0x180004c0e  jmp     loc_1800048DD
0x180004c13  lea     rcx, CriticalSection; lpCriticalSection
0x180004c1a  mov     ebx, 8007000Eh
0x180004c1f  call    cs:__imp_LeaveCriticalSection
0x180004c25  mov     r14d, [rsp+0A8h+var_64]
0x180004c2a  jmp     loc_1800048DD
0x180004c2f  mov     eax, 80004003h
0x180004c34  jmp     loc_180004930
```
