# PSCreatePropertyProvider

- ea: `0x180007fb0`
- end: `0x1800084d7`
- name: `PSCreatePropertyProvider`
- size: `1319`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180007190`
- `0x180073e60`

## callees

- `0x1800059cc`
- `0x180005bb0`
- `0x1800062b0`
- `0x18000681c`
- `0x1800070d0`
- `0x180007fb0`
- `0x18001c4fc`
- `0x1800479d0`
- `0x18005cc8c`
- `0x18006bb14`
- `0x18006ed20`
- `0x18006f1fc`
- `0x18006fb74`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180008416`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180008416`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000813c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008430`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000813c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008430`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000807f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000807f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800083bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800083bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800080d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800080d3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008075`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008075`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008299`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000845a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008299`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000845a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180008095`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180008095`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180008398`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180008398`

## pseudocode

```c
__int64 __fastcall PSCreatePropertyProvider(__int64 a1, __int64 a2, void *a3)
{
  LPVOID v3; // r13
  __int64 v4; // r15
  unsigned int i; // ebx
  GUID v7; // xmm0
  __int64 *v8; // rdi
  HRESULT ApartmentType; // ebx
  DWORD v10; // r15d
  volatile signed __int32 *Value; // rax
  volatile signed __int32 *v12; // r14
  __int64 (__fastcall ***v13)(_QWORD, GUID *, void **); // rcx
  void *v14; // rcx
  unsigned int v16; // r14d
  LPVOID v17; // rcx
  unsigned int j; // ebx
  CCachedSTAObject *v19; // rax
  CCachedSTAObject *v20; // rax
  CCachedSTAObject *v21; // r13
  const struct _GUID *v22; // r8
  APTTYPE pAptType; // [rsp+38h] [rbp-39h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+3Ch] [rbp-35h] BYREF
  __int64 v25; // [rsp+40h] [rbp-31h]
  void *v26; // [rsp+48h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-21h] BYREF
  _QWORD v28[2]; // [rsp+58h] [rbp-19h] BYREF
  IID Buf1; // [rsp+68h] [rbp-9h] BYREF

  ppv = a3;
  v3 = a3;
  v25 = a2;
  Buf1 = CLSID_PropertyProvider;
  v4 = a2;
  v28[0] = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 0xA )
      goto LABEL_36;
    if ( !memcmp_0(&Buf1, (char *)&xmmword_1800F0230 + 24 * i, 0x10u) )
      break;
  }
  if ( (__int128 *)((char *)&xmmword_1800F0230 + 24 * i) )
  {
    v7 = CLSID_PropSysBothClassFactory;
    v8 = g_aloBothClassFactory;
LABEL_7:
    v26 = 0;
    Buf1 = v7;
    InitOnceExecuteOnce(
      (PINIT_ONCE)v8 + 2,
      _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_,
      v8 + 3,
      0);
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 3));
    pAptType = APTTYPE_STA;
    pAptQualifier = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
    if ( ApartmentType >= 0 )
    {
      switch ( pAptType )
      {
        case APTTYPE_STA:
          goto LABEL_9;
        case APTTYPE_MTA:
          v16 = *((_DWORD *)v8 + 1);
          ApartmentType = 1;
          v26 = 0;
          if ( !v16 )
            break;
          v17 = g_pgit;
          if ( !g_pgit )
          {
            ApartmentType = CoCreateInstance(
                              &CLSID_StdGlobalInterfaceTable,
                              0,
                              1u,
                              &GUID_00000146_0000_0000_c000_000000000046,
                              &g_pgit);
            if ( ApartmentType < 0 )
              break;
            v17 = g_pgit;
          }
          ApartmentType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)v17 + 40LL))(
                            v17,
                            v16,
                            &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                            &v26);
          if ( ApartmentType < 0 )
            ApartmentType = 1;
          break;
        case APTTYPE_NA:
          ApartmentType = CApartmentLocalObject::_GetInterfaceFromGIT(
                            0,
                            *((_DWORD *)v8 + 2),
                            &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                            &v26);
          break;
        case APTTYPE_MAINSTA:
LABEL_9:
          ApartmentType = CApartmentLocalObject::_DelayAllocateTLS((CApartmentLocalObject *)v8);
          if ( ApartmentType < 0 )
            break;
          v10 = *(_DWORD *)v8;
          ApartmentType = 1;
          v26 = 0;
          if ( v10 == -1 )
            goto LABEL_17;
          Value = (volatile signed __int32 *)TlsGetValue(v10);
          v12 = Value;
          if ( Value )
          {
            if ( *((_DWORD *)Value + 10) )
            {
              _InterlockedIncrement(Value + 2);
              v26 = 0;
              v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)Value + 4);
              if ( v13 )
                ApartmentType = (**v13)(v13, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, &v26);
              else
                ApartmentType = 1;
LABEL_15:
              if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
                operator delete((void *)v12, (const struct std::nothrow_t *)0x30);
              goto LABEL_17;
            }
          }
          else
          {
            v19 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
            if ( v19 )
            {
              v20 = CCachedSTAObject::CCachedSTAObject(v19);
              v21 = v20;
              if ( v20 )
              {
                *((_DWORD *)v20 + 6) = v10;
                ApartmentType = CoRegisterInitializeSpy((IInitializeSpy *)v20, (ULARGE_INTEGER *)v20 + 2);
                if ( ApartmentType < 0 )
                {
                  v12 = 0;
                }
                else
                {
                  ApartmentType = 1;
                  *((_DWORD *)v21 + 10) = 1;
                  if ( !*(_QWORD *)&CCachedSTAObject::s_hmod )
                    GetModuleHandleExW(4u, &CCachedSTAObject::s_hmod, (HMODULE *)&CCachedSTAObject::s_hmod);
                  TlsSetValue(v10, v21);
                  v12 = (volatile signed __int32 *)v21;
                  _InterlockedIncrement((volatile signed __int32 *)v21 + 2);
                }
                CCachedSTAObject::Release(v21);
                v3 = ppv;
                if ( ApartmentType >= 0 )
                  goto LABEL_15;
              }
              else
              {
                v3 = ppv;
              }
            }
          }
          ApartmentType = 1;
LABEL_17:
          v4 = v25;
          break;
        default:
          ApartmentType = -2147221008;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 3));
LABEL_19:
          if ( ApartmentType >= 0 )
          {
            ApartmentType = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD, GUID *, _QWORD *))(*(_QWORD *)v26 + 24LL))(
                              v26,
                              &CLSID_PropertyProvider,
                              0,
                              &GUID_465a756d_45ad_4305_85fd_d3321650f3b7,
                              v28);
            if ( ApartmentType == -2147417848 )
            {
              CApartmentLocalObject::SetApartmentObject((CApartmentLocalObject *)v8, 0);
              SafeRelease<IShellFolder2>(&v26);
              ApartmentType = _GetCachedFactory((struct CApartmentLocalObject *)v8, &CLSID_PropertyProvider, v22, &v26);
              if ( ApartmentType >= 0 )
                ApartmentType = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD, GUID *, _QWORD *))(*(_QWORD *)v26 + 24LL))(
                                  v26,
                                  &CLSID_PropertyProvider,
                                  0,
                                  &GUID_465a756d_45ad_4305_85fd_d3321650f3b7,
                                  v28);
            }
            v14 = v26;
            v26 = 0;
            if ( v14 )
              (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
            if ( ApartmentType >= 0 )
            {
              ApartmentType = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v28[0] + 24LL))(v28[0], a1);
              if ( ApartmentType >= 0 )
                ApartmentType = (**(__int64 (__fastcall ***)(_QWORD, __int64, LPVOID))v28[0])(v28[0], v4, v3);
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28[0] + 16LL))(v28[0]);
            }
          }
          return (unsigned int)ApartmentType;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 3));
    if ( ApartmentType == 1 )
    {
      ppv = 0;
      ApartmentType = CoCreateInstance(&Buf1, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
      if ( ApartmentType < 0 )
        return (unsigned int)ApartmentType;
      ApartmentType = CApartmentLocalObject::TrySetApartmentObject(
                        (CApartmentLocalObject *)v8,
                        (struct IUnknown *)ppv,
                        &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                        &v26);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    goto LABEL_19;
  }
LABEL_36:
  Buf1 = CLSID_PropertyProvider;
  for ( j = 0; j < 2; ++j )
  {
    if ( !memcmp_0(&Buf1, (char *)&xmmword_1800F0200 + 24 * j, 0x10u) )
    {
      if ( (__int128 *)((char *)&xmmword_1800F0200 + 24 * j) )
      {
        v7 = CLSID_PropSysApartmentClassFactory;
        v8 = g_aloApartmentClassFactory;
        goto LABEL_7;
      }
      break;
    }
  }
  return (unsigned int)-2147221164;
}

```

## disassembly

```asm
0x180007fb0  mov     r11, rsp
0x180007fb3  push    rbp
0x180007fb4  push    rbx
0x180007fb5  push    rsi
0x180007fb6  push    r12
0x180007fb8  push    r13
0x180007fba  push    r14
0x180007fbc  push    r15
0x180007fbe  lea     rbp, [r11-5Fh]
0x180007fc2  sub     rsp, 90h
0x180007fc9  movaps  xmmword ptr [r11-48h], xmm6
0x180007fce  mov     rax, cs:__security_cookie
0x180007fd5  xor     rax, rsp
0x180007fd8  mov     [rbp+57h+var_50], rax
0x180007fdc  movups  xmm6, xmmword ptr cs:CLSID_PropertyProvider.Data1
0x180007fe3  xor     r14d, r14d
0x180007fe6  mov     [rbp+57h+ppv], r8
0x180007fea  mov     r13, r8
0x180007fed  mov     [rbp+57h+var_88], rdx
0x180007ff1  movdqa  [rbp+57h+Buf1], xmm6
0x180007ff6  lea     rsi, __ImageBase
0x180007ffd  mov     r15, rdx
0x180008000  mov     [rbp+57h+var_70], r14
0x180008004  mov     r12, rcx
0x180008007  mov     [r11+20h], rdi
0x18000800b  mov     ebx, r14d
0x18000800e  xchg    ax, ax
0x180008010  cmp     ebx, 0Ah
0x180008013  jnb     loc_1800082D7
0x180008019  mov     eax, ebx
0x18000801b  lea     rdi, rva xmmword_1800F0230[rsi]
0x180008022  mov     r8d, 10h; Size
0x180008028  lea     rcx, [rax+rax*2]
0x18000802c  lea     rdi, [rdi+rcx*8]
0x180008030  mov     rdx, rdi; Buf2
0x180008033  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180008037  call    memcmp_0
0x18000803c  test    eax, eax
0x18000803e  jz      short loc_180008044
0x180008040  inc     ebx
0x180008042  jmp     short loc_180008010
0x180008044  test    rdi, rdi
0x180008047  jz      loc_1800082D7
0x18000804d  movups  xmm0, xmmword ptr cs:CLSID_PropSysBothClassFactory.Data1
0x180008054  lea     rdi, ?g_aloBothClassFactory@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloBothClassFactory
0x18000805b  lea     rcx, [rdi+10h]; InitOnce
0x18000805f  mov     [rbp+57h+var_80], r14
0x180008063  xor     r9d, r9d; Context
0x180008066  lea     r8, [rdi+18h]; Parameter
0x18000806a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180008071  movups  [rbp+57h+Buf1], xmm0
0x180008075  call    cs:__imp_InitOnceExecuteOnce
0x18000807b  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000807f  call    cs:__imp_EnterCriticalSection
0x180008085  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x180008089  mov     [rbp+57h+pAptType], r14d
0x18000808d  lea     rcx, [rbp+57h+pAptType]; pAptType
0x180008091  mov     [rbp+57h+pAptQualifier], r14d
0x180008095  call    cs:__imp_CoGetApartmentType
0x18000809b  mov     ebx, eax
0x18000809d  test    eax, eax
0x18000809f  js      loc_180008138
0x1800080a5  mov     ecx, [rbp+57h+pAptType]
0x1800080a8  test    ecx, ecx
0x1800080aa  jnz     loc_18000821B
0x1800080b0  mov     rcx, rdi; this
0x1800080b3  call    ?_DelayAllocateTLS@CApartmentLocalObject@@AEAAJXZ; CApartmentLocalObject::_DelayAllocateTLS(void)
0x1800080b8  mov     ebx, eax
0x1800080ba  test    eax, eax
0x1800080bc  js      short loc_180008138
0x1800080be  mov     r15d, [rdi]
0x1800080c1  mov     ebx, 1
0x1800080c6  mov     [rbp+57h+var_80], r14
0x1800080ca  cmp     r15d, 0FFFFFFFFh
0x1800080ce  jz      short loc_180008134
0x1800080d0  mov     ecx, r15d; dwTlsIndex
0x1800080d3  call    cs:__imp_TlsGetValue
0x1800080d9  mov     r14, rax
0x1800080dc  test    rax, rax
0x1800080df  jz      loc_180008367
0x1800080e5  cmp     dword ptr [rax+28h], 0
0x1800080e9  jz      loc_1800083F9
0x1800080ef  lock inc dword ptr [rax+8]
0x1800080f3  mov     [rbp+57h+var_80], 0
0x1800080fb  mov     rcx, [r14+20h]
0x1800080ff  test    rcx, rcx
0x180008102  jz      loc_1800083E6
0x180008108  mov     rax, [rcx]
0x18000810b  lea     r8, [rbp+57h+var_80]
0x18000810f  lea     rdx, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x180008116  mov     rax, [rax]
0x180008119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000811e  mov     ebx, eax
0x180008120  mov     eax, 0FFFFFFFFh
0x180008125  lock xadd [r14+8], eax
0x18000812b  cmp     eax, 1
0x18000812e  jz      loc_18000834B
0x180008134  mov     r15, [rbp+57h+var_88]
0x180008138  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000813c  call    cs:__imp_LeaveCriticalSection
0x180008142  xor     r14d, r14d
0x180008145  cmp     ebx, 1
0x180008148  jz      loc_180008279
0x18000814e  test    ebx, ebx
0x180008150  js      loc_1800081EA
0x180008156  mov     rcx, [rbp+57h+var_80]
0x18000815a  lea     rdx, [rbp+57h+var_70]
0x18000815e  mov     [rsp+20h], rdx
0x180008163  lea     r9, _GUID_465a756d_45ad_4305_85fd_d3321650f3b7
0x18000816a  xor     r8d, r8d
0x18000816d  lea     rdx, CLSID_PropertyProvider
0x180008174  mov     rax, [rcx]
0x180008177  mov     rax, [rax+18h]
0x18000817b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008180  mov     ebx, eax
0x180008182  cmp     eax, 80010108h
0x180008187  jz      loc_180008476
0x18000818d  mov     rcx, [rbp+57h+var_80]
0x180008191  mov     [rbp+57h+var_80], r14
0x180008195  test    rcx, rcx
0x180008198  jz      short loc_1800081A6
0x18000819a  mov     rax, [rcx]
0x18000819d  mov     rax, [rax+10h]
0x1800081a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081a6  test    ebx, ebx
0x1800081a8  js      short loc_1800081EA
0x1800081aa  mov     rcx, [rbp+57h+var_70]
0x1800081ae  mov     rdx, r12
0x1800081b1  mov     rax, [rcx]
0x1800081b4  mov     rax, [rax+18h]
0x1800081b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081bd  mov     ebx, eax
0x1800081bf  test    eax, eax
0x1800081c1  js      short loc_1800081DA
0x1800081c3  mov     rcx, [rbp+57h+var_70]
0x1800081c7  mov     r8, r13
0x1800081ca  mov     rdx, r15
0x1800081cd  mov     rax, [rcx]
0x1800081d0  mov     rax, [rax]
0x1800081d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081d8  mov     ebx, eax
0x1800081da  mov     rcx, [rbp+57h+var_70]
0x1800081de  mov     rax, [rcx]
0x1800081e1  mov     rax, [rax+10h]
0x1800081e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ea  mov     rdi, [rsp+0C0h+arg_18]
0x1800081f2  mov     eax, ebx
0x1800081f4  mov     rcx, [rbp+57h+var_50]
0x1800081f8  xor     rcx, rsp; StackCookie
0x1800081fb  call    __security_check_cookie
0x180008200  movaps  xmm6, [rsp+0C0h+var_48+8]
0x180008208  add     rsp, 90h
0x18000820f  pop     r15
0x180008211  pop     r14
0x180008213  pop     r13
0x180008215  pop     r12
0x180008217  pop     rsi
0x180008218  pop     rbx
0x180008219  pop     rbp
0x18000821a  retn
0x18000821b  sub     ecx, 1
0x18000821e  jnz     loc_180008328
0x180008224  mov     r14d, [rdi+4]
0x180008228  mov     ebx, 1
0x18000822d  mov     [rbp+57h+var_80], 0
0x180008235  test    r14d, r14d
0x180008238  jz      loc_180008138
0x18000823e  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180008245  test    rcx, rcx
0x180008248  jz      loc_18000843B
0x18000824e  mov     rax, [rcx]
0x180008251  lea     r9, [rbp+57h+var_80]
0x180008255  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x18000825c  mov     edx, r14d
0x18000825f  mov     rax, [rax+28h]
0x180008263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008268  mov     ebx, eax
0x18000826a  test    eax, eax
0x18000826c  mov     eax, 1
0x180008271  cmovs   ebx, eax
0x180008274  jmp     loc_180008138
0x180008279  lea     rax, [rbp+57h+ppv]
0x18000827d  mov     [rbp+57h+ppv], r14
0x180008281  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180008288  mov     [rsp+20h], rax; ppv
0x18000828d  xor     edx, edx; pUnkOuter
0x18000828f  lea     rcx, [rbp+57h+Buf1]; rclsid
0x180008293  mov     r8d, 1; dwClsContext
0x180008299  call    cs:__imp_CoCreateInstance
0x18000829f  mov     ebx, eax
0x1800082a1  test    eax, eax
0x1800082a3  js      loc_1800081EA
0x1800082a9  mov     rdx, [rbp+57h+ppv]; struct IUnknown *
0x1800082ad  lea     r9, [rbp+57h+var_80]; void **
0x1800082b1  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; struct _GUID *
0x1800082b8  mov     rcx, rdi; this
0x1800082bb  call    ?TrySetApartmentObject@CApartmentLocalObject@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::TrySetApartmentObject(IUnknown *,_GUID const &,void * *)
0x1800082c0  mov     rcx, [rbp+57h+ppv]
0x1800082c4  mov     ebx, eax
0x1800082c6  mov     rax, [rcx]
0x1800082c9  mov     rax, [rax+10h]
0x1800082cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082d2  jmp     loc_18000814E
0x1800082d7  movdqa  [rbp+57h+Buf1], xmm6
0x1800082dc  mov     ebx, r14d
0x1800082df  nop
0x1800082e0  cmp     ebx, 2
0x1800082e3  jnb     short loc_18000835D
0x1800082e5  mov     eax, ebx
0x1800082e7  lea     rdi, rva xmmword_1800F0200[rsi]
0x1800082ee  mov     r8d, 10h; Size
0x1800082f4  lea     rcx, [rax+rax*2]
0x1800082f8  lea     rdi, [rdi+rcx*8]
0x1800082fc  mov     rdx, rdi; Buf2
0x1800082ff  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180008303  call    memcmp_0
0x180008308  test    eax, eax
0x18000830a  jz      short loc_180008310
0x18000830c  inc     ebx
0x18000830e  jmp     short loc_1800082E0
0x180008310  test    rdi, rdi
0x180008313  jz      short loc_18000835D
0x180008315  movups  xmm0, xmmword ptr cs:CLSID_PropSysApartmentClassFactory.Data1
0x18000831c  lea     rdi, ?g_aloApartmentClassFactory@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloApartmentClassFactory
0x180008323  jmp     loc_18000805B
0x180008328  sub     ecx, 1; this
0x18000832b  jnz     loc_18000841E
0x180008331  mov     edx, [rdi+8]; unsigned int
0x180008334  lea     r9, [rbp+57h+var_80]; void **
0x180008338  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; struct _GUID *
0x18000833f  call    ?_GetInterfaceFromGIT@CApartmentLocalObject@@AEAAJKAEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::_GetInterfaceFromGIT(ulong,_GUID const &,void * *)
0x180008344  mov     ebx, eax
0x180008346  jmp     loc_180008138
0x18000834b  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180008350  mov     rcx, r14; void *
0x180008353  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008358  jmp     loc_180008134
0x18000835d  mov     ebx, 80040154h
0x180008362  jmp     loc_1800081EA
0x180008367  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000836e  mov     ecx, 30h ; '0'; unsigned __int64
0x180008373  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008378  test    rax, rax
0x18000837b  jz      short loc_1800083F9
0x18000837d  mov     rcx, rax; this
0x180008380  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x180008385  mov     r13, rax
0x180008388  test    rax, rax
0x18000838b  jz      short loc_1800083F5
0x18000838d  lea     rdx, [rax+10h]; puliCookie
0x180008391  mov     [rax+18h], r15d
0x180008395  mov     rcx, rax; pSpy
0x180008398  call    cs:__imp_CoRegisterInitializeSpy
0x18000839e  mov     ebx, eax
0x1800083a0  test    eax, eax
0x1800083a2  js      short loc_1800083F0
0x1800083a4  mov     ebx, 1
0x1800083a9  mov     [r13+28h], ebx
0x1800083ad  cmp     cs:?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CCachedSTAObject::s_hmod
0x1800083b5  jz      short loc_180008403
0x1800083b7  mov     rdx, r13; lpTlsValue
0x1800083ba  mov     ecx, r15d; dwTlsIndex
0x1800083bd  call    cs:__imp_TlsSetValue
0x1800083c3  mov     r14, r13
0x1800083c6  lock inc dword ptr [r13+8]
0x1800083cb  mov     rcx, r13; this
0x1800083ce  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x1800083d3  mov     r13, [rbp+57h+ppv]
0x1800083d7  test    ebx, ebx
0x1800083d9  js      short loc_1800083F9
0x1800083db  jz      loc_1800080F3
0x1800083e1  jmp     loc_180008120
0x1800083e6  mov     ebx, 1
0x1800083eb  jmp     loc_180008120
0x1800083f0  xor     r14d, r14d
0x1800083f3  jmp     short loc_1800083CB
0x1800083f5  mov     r13, [rbp+57h+ppv]
0x1800083f9  mov     ebx, 1
0x1800083fe  jmp     loc_180008134
0x180008403  lea     r8, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; phModule
0x18000840a  mov     ecx, 4; dwFlags
0x18000840f  lea     rdx, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; lpModuleName
0x180008416  call    cs:__imp_GetModuleHandleExW
0x18000841c  jmp     short loc_1800083B7
0x18000841e  cmp     ecx, 1
0x180008421  jz      loc_1800080B0
0x180008427  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000842b  mov     ebx, 800401F0h
0x180008430  call    cs:__imp_LeaveCriticalSection
0x180008436  jmp     loc_18000814E
0x18000843b  lea     rax, ?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180008442  xor     edx, edx; pUnkOuter
0x180008444  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000844b  mov     [rsp+20h], rax; ppv
0x180008450  mov     r8d, ebx; dwClsContext
0x180008453  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000845a  call    cs:__imp_CoCreateInstance
0x180008460  mov     ebx, eax
0x180008462  test    eax, eax
0x180008464  js      loc_180008138
  ... truncated ...
```
