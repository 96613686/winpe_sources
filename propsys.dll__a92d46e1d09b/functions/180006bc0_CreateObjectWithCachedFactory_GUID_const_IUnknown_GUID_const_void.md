# CreateObjectWithCachedFactory(_GUID const &,IUnknown *,_GUID const &,void * *)

- ea: `0x180006bc0`
- end: `0x1800070c5`
- name: `?CreateObjectWithCachedFactory@@YAJAEBU_GUID@@PEAUIUnknown@@0PEAPEAX@Z`
- size: `1285`
- prototype: `__int64 __fastcall(IID *rclsid, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `11`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180005240`
- `0x1800054d0`
- `0x1800055f0`
- `0x180005a38`
- `0x180005c30`
- `0x180005cf0`
- `0x180005d10`
- `0x180005e90`
- `0x180007190`
- `0x180065440`
- `0x180067430`

## callees

- `0x1800059cc`
- `0x180005bb0`
- `0x1800062b0`
- `0x18000681c`
- `0x180006bc0`
- `0x18001c4fc`
- `0x18005cc8c`
- `0x18006bb14`
- `0x18006ed20`
- `0x18006f1fc`
- `0x18006fb74`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180007038`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180007038`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006d43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007051`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007065`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006d43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007051`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007065`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006c83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006c83`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006fe7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006fe7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006cda`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006cda`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180006e3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180006e3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180006e20`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180006e20`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006c79`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006c79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006f55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006f55`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180006c99`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180006c99`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180006fc2`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180006fc2`

## pseudocode

```c
__int64 __fastcall CreateObjectWithCachedFactory(IID *rclsid, struct IUnknown *a2, const struct _GUID *a3, void **a4)
{
  IID v4; // xmm0
  void **v5; // r15
  const struct _GUID *v6; // r12
  unsigned int i; // ebx
  GUID v9; // xmm0
  __int64 *v10; // rdi
  HRESULT ApartmentType; // ebx
  DWORD v12; // r12d
  volatile signed __int32 *Value; // rax
  CCachedSTAObject *v14; // r14
  __int64 (__fastcall ***v15)(_QWORD, GUID *, void **); // rcx
  void *v16; // rcx
  unsigned int v18; // r14d
  LPVOID v19; // rcx
  DWORD v20; // ecx
  unsigned int v21; // ebx
  CCachedSTAObject *v22; // rax
  CCachedSTAObject *v23; // rax
  struct IUnknown *v24; // rcx
  const struct _GUID *v25; // r8
  APTTYPE pAptType; // [rsp+30h] [rbp-50h] BYREF
  void **v27; // [rsp+38h] [rbp-48h]
  const struct _GUID *v28; // [rsp+40h] [rbp-40h]
  void *v29; // [rsp+48h] [rbp-38h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+50h] [rbp-30h] BYREF
  IID Buf1; // [rsp+60h] [rbp-20h] BYREF

  v27 = a4;
  *a4 = 0;
  v4 = *rclsid;
  v5 = a4;
  v28 = a3;
  v6 = a3;
  Buf1 = v4;
  for ( i = 0; ; ++i )
  {
    if ( i >= 0xA )
      goto LABEL_36;
    if ( !memcmp_0(&Buf1, (char *)&xmmword_1800F0230 + 24 * i, 0x10u) )
      break;
  }
  if ( (__int128 *)((char *)&xmmword_1800F0230 + 24 * i) )
  {
    v9 = CLSID_PropSysBothClassFactory;
    v10 = g_aloBothClassFactory;
LABEL_7:
    v29 = 0;
    Buf1 = v9;
    InitOnceExecuteOnce(
      (PINIT_ONCE)v10 + 2,
      _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_,
      v10 + 3,
      0);
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 3));
    pAptType = APTTYPE_STA;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
    if ( ApartmentType >= 0 )
    {
      if ( pAptType == APTTYPE_STA )
        goto LABEL_9;
      if ( pAptType == APTTYPE_MTA )
      {
        v18 = *((_DWORD *)v10 + 1);
        ApartmentType = 1;
        v29 = 0;
        if ( !v18 )
          goto LABEL_18;
        v19 = g_pgit;
        if ( g_pgit )
          goto LABEL_27;
        goto LABEL_45;
      }
      if ( pAptType != APTTYPE_NA )
      {
        if ( pAptType != APTTYPE_MAINSTA )
        {
          ApartmentType = -2147221008;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 3));
          goto LABEL_19;
        }
LABEL_9:
        if ( *(_DWORD *)v10 == -1 )
        {
          v20 = TlsAlloc();
          if ( v20 == -1 )
          {
            ApartmentType = -2147024882;
            LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 3));
            v5 = v27;
            goto LABEL_19;
          }
          if ( _InterlockedCompareExchange((volatile signed __int32 *)v10, v20, -1) != -1 )
            TlsFree(v20);
        }
        v12 = *(_DWORD *)v10;
        ApartmentType = 1;
        v29 = 0;
        if ( v12 == -1 )
          goto LABEL_17;
        Value = (volatile signed __int32 *)TlsGetValue(v12);
        v14 = (CCachedSTAObject *)Value;
        if ( Value )
        {
          if ( *((_DWORD *)Value + 10) )
          {
            _InterlockedIncrement(Value + 2);
            v29 = 0;
            v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)Value + 4);
            if ( v15 )
              ApartmentType = (**v15)(v15, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, &v29);
            else
              ApartmentType = 1;
LABEL_15:
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 + 2, 0xFFFFFFFF) == 1 )
              operator delete(v14, (const struct std::nothrow_t *)0x30);
            goto LABEL_17;
          }
        }
        else
        {
          v22 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
          if ( v22 )
          {
            v23 = CCachedSTAObject::CCachedSTAObject(v22);
            *(_QWORD *)pAptQualifier = v23;
            v14 = v23;
            if ( v23 )
            {
              *((_DWORD *)v23 + 6) = v12;
              ApartmentType = CoRegisterInitializeSpy((IInitializeSpy *)v23, (ULARGE_INTEGER *)v23 + 2);
              if ( ApartmentType < 0 )
              {
                v24 = *(struct IUnknown **)pAptQualifier;
                v14 = 0;
              }
              else
              {
                ApartmentType = 1;
                *((_DWORD *)v14 + 10) = 1;
                if ( !*(_QWORD *)&CCachedSTAObject::s_hmod )
                  GetModuleHandleExW(4u, &CCachedSTAObject::s_hmod, (HMODULE *)&CCachedSTAObject::s_hmod);
                TlsSetValue(v12, v14);
                v24 = (struct IUnknown *)v14;
                _InterlockedIncrement((volatile signed __int32 *)v14 + 2);
              }
              CCachedSTAObject::Release((CCachedSTAObject *)v24);
              if ( ApartmentType >= 0 )
                goto LABEL_15;
            }
          }
        }
        ApartmentType = 1;
LABEL_17:
        v5 = v27;
        v6 = v28;
        goto LABEL_18;
      }
      v18 = *((_DWORD *)v10 + 2);
      ApartmentType = 1;
      v29 = 0;
      if ( v18 )
      {
        v19 = g_pgit;
        if ( g_pgit )
        {
LABEL_27:
          ApartmentType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)v19 + 40LL))(
                            v19,
                            v18,
                            &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                            &v29);
          if ( ApartmentType < 0 )
            ApartmentType = 1;
          goto LABEL_18;
        }
LABEL_45:
        ApartmentType = CoCreateInstance(
                          &CLSID_StdGlobalInterfaceTable,
                          0,
                          1u,
                          &GUID_00000146_0000_0000_c000_000000000046,
                          &g_pgit);
        if ( ApartmentType < 0 )
          goto LABEL_18;
        v19 = g_pgit;
        goto LABEL_27;
      }
    }
LABEL_18:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 3));
    if ( ApartmentType == 1 )
    {
      *(_QWORD *)pAptQualifier = 0;
      ApartmentType = CoCreateInstance(
                        &Buf1,
                        0,
                        1u,
                        &GUID_00000000_0000_0000_c000_000000000046,
                        (LPVOID *)pAptQualifier);
      if ( ApartmentType < 0 )
        return (unsigned int)ApartmentType;
      ApartmentType = CApartmentLocalObject::TrySetApartmentObject(
                        (CApartmentLocalObject *)v10,
                        *(struct IUnknown **)pAptQualifier,
                        &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                        &v29);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
    }
LABEL_19:
    if ( ApartmentType >= 0 )
    {
      ApartmentType = (*(__int64 (__fastcall **)(void *, IID *, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v29 + 24LL))(
                        v29,
                        rclsid,
                        0,
                        v6,
                        v5);
      if ( ApartmentType == -2147417848 )
      {
        CApartmentLocalObject::SetApartmentObject((CApartmentLocalObject *)v10, 0);
        SafeRelease<IShellFolder2>(&v29);
        ApartmentType = _GetCachedFactory((struct CApartmentLocalObject *)v10, rclsid, v25, &v29);
        if ( ApartmentType >= 0 )
          ApartmentType = (*(__int64 (__fastcall **)(void *, IID *, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v29 + 24LL))(
                            v29,
                            rclsid,
                            0,
                            v6,
                            v5);
      }
      v16 = v29;
      v29 = 0;
      if ( v16 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return (unsigned int)ApartmentType;
  }
LABEL_36:
  v21 = 0;
  Buf1 = *rclsid;
  while ( v21 < 2 )
  {
    if ( !memcmp_0(&Buf1, (char *)&xmmword_1800F0200 + 24 * v21, 0x10u) )
    {
      if ( (__int128 *)((char *)&xmmword_1800F0200 + 24 * v21) )
      {
        v9 = CLSID_PropSysApartmentClassFactory;
        v10 = g_aloApartmentClassFactory;
        goto LABEL_7;
      }
      return 2147746132LL;
    }
    ++v21;
  }
  return 2147746132LL;
}

```

## disassembly

```asm
0x180006bc0  push    rbp
0x180006bc2  push    rbx
0x180006bc3  push    rsi
0x180006bc4  push    r12
0x180006bc6  push    r13
0x180006bc8  push    r14
0x180006bca  push    r15
0x180006bcc  mov     rbp, rsp
0x180006bcf  sub     rsp, 80h
0x180006bd6  mov     rax, cs:__security_cookie
0x180006bdd  xor     rax, rsp
0x180006be0  mov     [rbp+var_10], rax
0x180006be4  xor     r14d, r14d
0x180006be7  mov     [rbp+var_48], r9
0x180006beb  mov     [r9], r14
0x180006bee  lea     rsi, __ImageBase
0x180006bf5  movups  xmm0, xmmword ptr [rcx]
0x180006bf8  mov     r15, r9
0x180006bfb  mov     [rbp+var_40], r8
0x180006bff  mov     r12, r8
0x180006c02  mov     [rsp+80h+arg_8], rdi
0x180006c0a  movaps  [rbp+Buf1], xmm0
0x180006c0e  mov     r13, rcx
0x180006c11  mov     ebx, r14d
0x180006c14  cmp     ebx, 0Ah
0x180006c17  jnb     loc_180006EAB
0x180006c1d  mov     eax, ebx
0x180006c1f  lea     rdi, rva xmmword_1800F0230[rsi]
0x180006c26  mov     r8d, 10h; Size
0x180006c2c  lea     rcx, [rax+rax*2]
0x180006c30  lea     rdi, [rdi+rcx*8]
0x180006c34  mov     rdx, rdi; Buf2
0x180006c37  lea     rcx, [rbp+Buf1]; Buf1
0x180006c3b  call    memcmp_0
0x180006c40  test    eax, eax
0x180006c42  jz      short loc_180006C48
0x180006c44  inc     ebx
0x180006c46  jmp     short loc_180006C14
0x180006c48  test    rdi, rdi
0x180006c4b  jz      loc_180006EAB
0x180006c51  movups  xmm0, xmmword ptr cs:CLSID_PropSysBothClassFactory.Data1
0x180006c58  lea     rdi, ?g_aloBothClassFactory@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloBothClassFactory
0x180006c5f  lea     rcx, [rdi+10h]; InitOnce
0x180006c63  mov     [rbp+var_38], r14
0x180006c67  xor     r9d, r9d; Context
0x180006c6a  lea     r8, [rdi+18h]; Parameter
0x180006c6e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180006c75  movups  [rbp+Buf1], xmm0
0x180006c79  call    cs:__imp_InitOnceExecuteOnce
0x180006c7f  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006c83  call    cs:__imp_EnterCriticalSection
0x180006c89  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x180006c8d  mov     [rbp+pAptType], r14d
0x180006c91  lea     rcx, [rbp+pAptType]; pAptType
0x180006c95  mov     [rbp+pAptQualifier], r14d
0x180006c99  call    cs:__imp_CoGetApartmentType
0x180006c9f  mov     ebx, eax
0x180006ca1  mov     edx, 1
0x180006ca6  test    eax, eax
0x180006ca8  js      loc_180006D3F
0x180006cae  mov     ecx, [rbp+pAptType]
0x180006cb1  test    ecx, ecx
0x180006cb3  jnz     loc_180006DC6
0x180006cb9  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180006cbc  mov     r15d, 0FFFFFFFFh
0x180006cc2  jz      loc_180006E20
0x180006cc8  mov     r12d, [rdi]
0x180006ccb  mov     ebx, edx
0x180006ccd  mov     [rbp+var_38], r14
0x180006cd1  cmp     r12d, 0FFFFFFFFh
0x180006cd5  jz      short loc_180006D37
0x180006cd7  mov     ecx, r12d; dwTlsIndex
0x180006cda  call    cs:__imp_TlsGetValue
0x180006ce0  mov     r14, rax
0x180006ce3  test    rax, rax
0x180006ce6  jz      loc_180006F8D
0x180006cec  cmp     dword ptr [rax+28h], 0
0x180006cf0  jz      loc_18000701B
0x180006cf6  lock inc dword ptr [rax+8]
0x180006cfa  mov     [rbp+var_38], 0
0x180006d02  mov     rcx, [r14+20h]
0x180006d06  test    rcx, rcx
0x180006d09  jz      loc_180007008
0x180006d0f  mov     rax, [rcx]
0x180006d12  lea     r8, [rbp+var_38]
0x180006d16  lea     rdx, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x180006d1d  mov     rax, [rax]
0x180006d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d25  mov     ebx, eax
0x180006d27  lock xadd [r14+8], r15d
0x180006d2d  cmp     r15d, 1
0x180006d31  jz      loc_180006F71
0x180006d37  mov     r15, [rbp+var_48]
0x180006d3b  mov     r12, [rbp+var_40]
0x180006d3f  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006d43  call    cs:__imp_LeaveCriticalSection
0x180006d49  xor     r14d, r14d
0x180006d4c  cmp     ebx, 1
0x180006d4f  jz      loc_180006E4D
0x180006d55  test    ebx, ebx
0x180006d57  js      short loc_180006D9D
0x180006d59  mov     rcx, [rbp+var_38]
0x180006d5d  mov     r9, r12
0x180006d60  xor     r8d, r8d
0x180006d63  mov     [rsp+80h+ppv], r15
0x180006d68  mov     rdx, r13
0x180006d6b  mov     rax, [rcx]
0x180006d6e  mov     rax, [rax+18h]
0x180006d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d77  mov     ebx, eax
0x180006d79  cmp     eax, 80010108h
0x180006d7e  jz      loc_180007074
0x180006d84  mov     rcx, [rbp+var_38]
0x180006d88  mov     [rbp+var_38], r14
0x180006d8c  test    rcx, rcx
0x180006d8f  jz      short loc_180006D9D
0x180006d91  mov     rax, [rcx]
0x180006d94  mov     rax, [rax+10h]
0x180006d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d9d  mov     eax, ebx
0x180006d9f  mov     rdi, [rsp+80h+arg_8]
0x180006da7  mov     rcx, [rbp+var_10]
0x180006dab  xor     rcx, rsp; StackCookie
0x180006dae  call    __security_check_cookie
0x180006db3  add     rsp, 80h
0x180006dba  pop     r15
0x180006dbc  pop     r14
0x180006dbe  pop     r13
0x180006dc0  pop     r12
0x180006dc2  pop     rsi
0x180006dc3  pop     rbx
0x180006dc4  pop     rbp
0x180006dc5  retn
0x180006dc6  sub     ecx, edx
0x180006dc8  jnz     loc_180006F07
0x180006dce  mov     r14d, [rdi+4]
0x180006dd2  mov     ebx, edx
0x180006dd4  mov     [rbp+var_38], 0
0x180006ddc  test    r14d, r14d
0x180006ddf  jz      loc_180006D3F
0x180006de5  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180006dec  test    rcx, rcx
0x180006def  jz      loc_180006F36
0x180006df5  mov     rax, [rcx]
0x180006df8  lea     r9, [rbp+var_38]
0x180006dfc  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x180006e03  mov     edx, r14d
0x180006e06  mov     rax, [rax+28h]
0x180006e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e0f  mov     ebx, eax
0x180006e11  test    eax, eax
0x180006e13  mov     eax, 1
0x180006e18  cmovs   ebx, eax
0x180006e1b  jmp     loc_180006D3F
0x180006e20  call    cs:__imp_TlsAlloc
0x180006e26  mov     ecx, eax; dwTlsIndex
0x180006e28  cmp     eax, 0FFFFFFFFh
0x180006e2b  jz      loc_18000705C
0x180006e31  mov     eax, r15d
0x180006e34  lock cmpxchg [rdi], ecx
0x180006e38  cmp     eax, 0FFFFFFFFh
0x180006e3b  jz      short loc_180006E43
0x180006e3d  call    cs:__imp_TlsFree
0x180006e43  mov     edx, 1
0x180006e48  jmp     loc_180006CC8
0x180006e4d  lea     rax, [rbp+pAptQualifier]
0x180006e51  mov     qword ptr [rbp+pAptQualifier], r14
0x180006e55  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180006e5c  mov     [rsp+80h+ppv], rax; ppv
0x180006e61  xor     edx, edx; pUnkOuter
0x180006e63  lea     rcx, [rbp+Buf1]; rclsid
0x180006e67  mov     r8d, 1; dwClsContext
0x180006e6d  call    cs:__imp_CoCreateInstance
0x180006e73  mov     ebx, eax
0x180006e75  test    eax, eax
0x180006e77  js      loc_180006D9D
0x180006e7d  mov     rdx, qword ptr [rbp+pAptQualifier]; struct IUnknown *
0x180006e81  lea     r9, [rbp+var_38]; void **
0x180006e85  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; struct _GUID *
0x180006e8c  mov     rcx, rdi; this
0x180006e8f  call    ?TrySetApartmentObject@CApartmentLocalObject@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::TrySetApartmentObject(IUnknown *,_GUID const &,void * *)
0x180006e94  mov     rcx, qword ptr [rbp+pAptQualifier]
0x180006e98  mov     ebx, eax
0x180006e9a  mov     rax, [rcx]
0x180006e9d  mov     rax, [rax+10h]
0x180006ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea6  jmp     loc_180006D55
0x180006eab  movups  xmm0, xmmword ptr [r13+0]
0x180006eb0  mov     ebx, r14d
0x180006eb3  movaps  [rbp+Buf1], xmm0
0x180006eb7  cmp     ebx, 2
0x180006eba  jnb     loc_180006F83
0x180006ec0  mov     eax, ebx
0x180006ec2  lea     rdi, rva xmmword_1800F0200[rsi]
0x180006ec9  mov     r8d, 10h; Size
0x180006ecf  lea     rcx, [rax+rax*2]
0x180006ed3  lea     rdi, [rdi+rcx*8]
0x180006ed7  mov     rdx, rdi; Buf2
0x180006eda  lea     rcx, [rbp+Buf1]; Buf1
0x180006ede  call    memcmp_0
0x180006ee3  test    eax, eax
0x180006ee5  jz      short loc_180006EEB
0x180006ee7  inc     ebx
0x180006ee9  jmp     short loc_180006EB7
0x180006eeb  test    rdi, rdi
0x180006eee  jz      loc_180006F83
0x180006ef4  movups  xmm0, xmmword ptr cs:CLSID_PropSysApartmentClassFactory.Data1
0x180006efb  lea     rdi, ?g_aloApartmentClassFactory@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloApartmentClassFactory
0x180006f02  jmp     loc_180006C5F
0x180006f07  sub     ecx, edx
0x180006f09  jnz     loc_180007040
0x180006f0f  mov     r14d, [rdi+8]
0x180006f13  mov     ebx, edx
0x180006f15  mov     [rbp+var_38], 0
0x180006f1d  test    r14d, r14d
0x180006f20  jz      loc_180006D3F
0x180006f26  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180006f2d  test    rcx, rcx
0x180006f30  jnz     loc_180006DF5
0x180006f36  lea     rax, ?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180006f3d  mov     r8d, edx; dwClsContext
0x180006f40  xor     edx, edx; pUnkOuter
0x180006f42  mov     [rsp+80h+ppv], rax; ppv
0x180006f47  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180006f4e  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006f55  call    cs:__imp_CoCreateInstance
0x180006f5b  mov     ebx, eax
0x180006f5d  test    eax, eax
0x180006f5f  js      loc_180006D3F
0x180006f65  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180006f6c  jmp     loc_180006DF5
0x180006f71  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180006f76  mov     rcx, r14; void *
0x180006f79  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006f7e  jmp     loc_180006D37
0x180006f83  mov     eax, 80040154h
0x180006f88  jmp     loc_180006D9F
0x180006f8d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006f94  mov     ecx, 30h ; '0'; unsigned __int64
0x180006f99  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006f9e  test    rax, rax
0x180006fa1  jz      short loc_18000701B
0x180006fa3  mov     rcx, rax; this
0x180006fa6  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x180006fab  mov     qword ptr [rbp+pAptQualifier], rax
0x180006faf  mov     r14, rax
0x180006fb2  test    rax, rax
0x180006fb5  jz      short loc_18000701B
0x180006fb7  lea     rdx, [rax+10h]; puliCookie
0x180006fbb  mov     [rax+18h], r12d
0x180006fbf  mov     rcx, rax; pSpy
0x180006fc2  call    cs:__imp_CoRegisterInitializeSpy
0x180006fc8  mov     ebx, eax
0x180006fca  test    eax, eax
0x180006fcc  js      short loc_180007012
0x180006fce  mov     ebx, 1
0x180006fd3  mov     [r14+28h], ebx
0x180006fd7  cmp     cs:?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CCachedSTAObject::s_hmod
0x180006fdf  jz      short loc_180007025
0x180006fe1  mov     rdx, r14; lpTlsValue
0x180006fe4  mov     ecx, r12d; dwTlsIndex
0x180006fe7  call    cs:__imp_TlsSetValue
0x180006fed  mov     rcx, r14; this
0x180006ff0  lock inc dword ptr [rcx+8]
0x180006ff4  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x180006ff9  test    ebx, ebx
0x180006ffb  js      short loc_18000701B
0x180006ffd  jz      loc_180006CFA
0x180007003  jmp     loc_180006D27
0x180007008  mov     ebx, 1
0x18000700d  jmp     loc_180006D27
0x180007012  mov     rcx, qword ptr [rbp+pAptQualifier]
0x180007016  xor     r14d, r14d
0x180007019  jmp     short loc_180006FF4
0x18000701b  mov     ebx, 1
0x180007020  jmp     loc_180006D37
0x180007025  lea     r8, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; phModule
0x18000702c  mov     ecx, 4; dwFlags
0x180007031  lea     rdx, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; lpModuleName
0x180007038  call    cs:__imp_GetModuleHandleExW
0x18000703e  jmp     short loc_180006FE1
0x180007040  cmp     ecx, edx
0x180007042  jz      loc_180006CB9
0x180007048  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000704c  mov     ebx, 800401F0h
0x180007051  call    cs:__imp_LeaveCriticalSection
0x180007057  jmp     loc_180006D55
0x18000705c  lea     rcx, [rdi+18h]; lpCriticalSection
0x180007060  mov     ebx, 8007000Eh
0x180007065  call    cs:__imp_LeaveCriticalSection
0x18000706b  mov     r15, [rbp+var_48]
0x18000706f  jmp     loc_180006D55
0x180007074  xor     edx, edx; struct IUnknown *
0x180007076  mov     rcx, rdi; this
0x180007079  call    ?SetApartmentObject@CApartmentLocalObject@@QEAAJPEAUIUnknown@@@Z; CApartmentLocalObject::SetApartmentObject(IUnknown *)
0x18000707e  lea     rcx, [rbp+var_38]
0x180007082  call    ??$SafeRelease@UIShellFolder2@@@@YAXPEAPEAUIShellFolder2@@@Z; SafeRelease<IShellFolder2>(IShellFolder2 * *)
0x180007087  lea     r9, [rbp+var_38]; void **
0x18000708b  mov     rdx, r13; rclsid
0x18000708e  mov     rcx, rdi; this
  ... truncated ...
```
