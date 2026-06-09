# PSCreateMultiplexPropertyStore

- ea: `0x1800062e0`
- end: `0x180006815`
- name: `PSCreateMultiplexPropertyStore`
- size: `1333`
- prototype: `HRESULT __stdcall(IUnknown **prgpunkStores, DWORD cStores, const IID *const riid, void **ppv)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007190`
- `0x180080af0`

## callees

- `0x1800059cc`
- `0x180005bb0`
- `0x1800062b0`
- `0x1800062e0`
- `0x18000681c`
- `0x1800070d0`
- `0x18001c4fc`
- `0x1800479d0`
- `0x18005cc8c`
- `0x18006ed20`
- `0x18006f1fc`
- `0x18006fb74`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000675a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000675a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000648f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000648f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006710`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180006710`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000642f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000642f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800063c6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800063c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800065f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006794`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800065f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006794`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800063eb`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800063eb`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x1800066ef`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x1800066ef`

## pseudocode

```c
HRESULT __stdcall PSCreateMultiplexPropertyStore(
        IUnknown **prgpunkStores,
        DWORD cStores,
        const IID *const riid,
        void **ppv)
{
  DWORD v5; // r15d
  IUnknown **v6; // rsi
  int ApartmentType; // ebx
  __int64 v8; // rbx
  GUID v9; // xmm0
  __int64 *v10; // r14
  DWORD v11; // r15d
  volatile signed __int32 *Value; // rax
  CCachedSTAObject *v13; // rsi
  __int64 (__fastcall ***v14)(_QWORD, GUID *, void **); // rcx
  void *v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  unsigned int v20; // edi
  LPVOID v21; // rcx
  __int64 i; // rbx
  CCachedSTAObject *v23; // rax
  CCachedSTAObject *v24; // rax
  CCachedSTAObject *v25; // rdi
  const struct _GUID *v26; // r8
  APTTYPE pAptType; // [rsp+38h] [rbp-39h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+3Ch] [rbp-35h] BYREF
  IUnknown **v29; // [rsp+40h] [rbp-31h]
  const IID *v30; // [rsp+48h] [rbp-29h]
  void *v31; // [rsp+50h] [rbp-21h] BYREF
  struct IUnknown *v32; // [rsp+58h] [rbp-19h] BYREF
  __int64 *v33; // [rsp+60h] [rbp-11h] BYREF
  IID Buf1; // [rsp+68h] [rbp-9h] BYREF

  v30 = riid;
  LODWORD(v32) = cStores;
  v5 = cStores;
  v29 = prgpunkStores;
  v6 = prgpunkStores;
  *ppv = 0;
  ApartmentType = -2147467261;
  if ( !prgpunkStores )
    return ApartmentType;
  v8 = 0;
  v33 = 0;
  Buf1 = CLSID_MultiplexPropertyStore;
  while ( 1 )
  {
    if ( (unsigned int)v8 >= 0xA )
      goto LABEL_40;
    if ( !memcmp_0(&Buf1, &_ImageBase + 6 * v8 + 245900, 0x10u) )
      break;
    v8 = (unsigned int)(v8 + 1);
  }
  if ( !(&_ImageBase + 6 * v8 + 245900) )
  {
LABEL_40:
    Buf1 = CLSID_MultiplexPropertyStore;
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      if ( !memcmp_0(&Buf1, &_ImageBase + 6 * i + 245888, 0x10u) )
      {
        if ( &_ImageBase + 6 * i + 245888 )
        {
          v9 = CLSID_PropSysApartmentClassFactory;
          v10 = g_aloApartmentClassFactory;
          goto LABEL_8;
        }
        return -2147221164;
      }
    }
    return -2147221164;
  }
  v9 = CLSID_PropSysBothClassFactory;
  v10 = g_aloBothClassFactory;
LABEL_8:
  v31 = 0;
  Buf1 = v9;
  InitOnceExecuteOnce(
    (PINIT_ONCE)v10 + 2,
    _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_,
    v10 + 3,
    0);
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 3));
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_19;
  if ( pAptType )
  {
    if ( pAptType == APTTYPE_MTA )
    {
      v20 = *((_DWORD *)v10 + 1);
      v31 = 0;
      ApartmentType = 1;
      if ( v20 )
      {
        v21 = g_pgit;
        if ( !g_pgit )
        {
          ApartmentType = CoCreateInstance(
                            &CLSID_StdGlobalInterfaceTable,
                            0,
                            1u,
                            &GUID_00000146_0000_0000_c000_000000000046,
                            &g_pgit);
          if ( ApartmentType < 0 )
            goto LABEL_19;
          v21 = g_pgit;
        }
        ApartmentType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)v21 + 40LL))(
                          v21,
                          v20,
                          &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                          &v31);
        if ( ApartmentType < 0 )
          ApartmentType = 1;
        goto LABEL_19;
      }
      goto LABEL_19;
    }
    if ( pAptType == APTTYPE_NA )
    {
      ApartmentType = CApartmentLocalObject::_GetInterfaceFromGIT(
                        0,
                        *((_DWORD *)v10 + 2),
                        &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                        &v31);
      goto LABEL_19;
    }
    if ( pAptType != APTTYPE_MAINSTA )
    {
      ApartmentType = -2147221008;
      goto LABEL_19;
    }
  }
  ApartmentType = CApartmentLocalObject::_DelayAllocateTLS((CApartmentLocalObject *)v10);
  if ( ApartmentType >= 0 )
  {
    v11 = *(_DWORD *)v10;
    v31 = 0;
    ApartmentType = 1;
    if ( v11 == -1 )
    {
LABEL_18:
      v5 = (unsigned int)v32;
      goto LABEL_19;
    }
    Value = (volatile signed __int32 *)TlsGetValue(v11);
    v13 = (CCachedSTAObject *)Value;
    if ( Value )
    {
      if ( *((_DWORD *)Value + 10) )
      {
        _InterlockedAdd(Value + 2, 1u);
        v31 = 0;
        v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)Value + 4);
        if ( v14 )
          ApartmentType = (**v14)(v14, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, &v31);
        else
          ApartmentType = 1;
LABEL_16:
        CCachedSTAObject::Release(v13);
LABEL_17:
        v6 = v29;
        goto LABEL_18;
      }
    }
    else
    {
      v13 = 0;
      v23 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
      if ( v23 && (v24 = CCachedSTAObject::CCachedSTAObject(v23), (v25 = v24) != 0) )
      {
        *((_DWORD *)v24 + 6) = v11;
        ApartmentType = CoRegisterInitializeSpy((IInitializeSpy *)v24, (ULARGE_INTEGER *)v24 + 2);
        if ( ApartmentType >= 0 )
        {
          ApartmentType = 1;
          *((_DWORD *)v25 + 10) = 1;
          if ( !*(_QWORD *)&CCachedSTAObject::s_hmod )
            GetModuleHandleExW(4u, &CCachedSTAObject::s_hmod, (HMODULE *)&CCachedSTAObject::s_hmod);
          TlsSetValue(v11, v25);
          v13 = v25;
          _InterlockedAdd((volatile signed __int32 *)v25 + 2, 1u);
        }
        CCachedSTAObject::Release(v25);
      }
      else
      {
        ApartmentType = -2147024882;
      }
      if ( ApartmentType >= 0 )
        goto LABEL_16;
    }
    ApartmentType = 1;
    goto LABEL_17;
  }
LABEL_19:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 3));
  if ( ApartmentType == 1 )
  {
    v32 = 0;
    ApartmentType = CoCreateInstance(&Buf1, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&v32);
    if ( ApartmentType < 0 )
      return ApartmentType;
    ApartmentType = CApartmentLocalObject::TrySetApartmentObject(
                      (CApartmentLocalObject *)v10,
                      v32,
                      &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                      &v31);
    ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
  }
  if ( ApartmentType >= 0 )
  {
    ApartmentType = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD, GUID *, __int64 **))(*(_QWORD *)v31 + 24LL))(
                      v31,
                      &CLSID_MultiplexPropertyStore,
                      0,
                      &GUID_b8158717_9161_46fd_b8d2_26d42185bc69,
                      &v33);
    if ( ApartmentType == -2147417848 )
    {
      CApartmentLocalObject::SetApartmentObject((CApartmentLocalObject *)v10, 0);
      SafeRelease<IShellFolder2>(&v31);
      ApartmentType = _GetCachedFactory((struct CApartmentLocalObject *)v10, &CLSID_MultiplexPropertyStore, v26, &v31);
      if ( ApartmentType >= 0 )
        ApartmentType = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD, GUID *, __int64 **))(*(_QWORD *)v31 + 24LL))(
                          v31,
                          &CLSID_MultiplexPropertyStore,
                          0,
                          &GUID_b8158717_9161_46fd_b8d2_26d42185bc69,
                          &v33);
    }
    v15 = v31;
    v31 = 0;
    if ( v15 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( ApartmentType >= 0 )
    {
      v16 = 0;
      while ( 1 )
      {
        v17 = *v33;
        if ( (unsigned int)v16 >= v5 )
          break;
        v18 = (*(__int64 (__fastcall **)(__int64 *, IUnknown *))(v17 + 24))(v33, v6[v16]);
        v16 = (unsigned int)(v16 + 1);
        ApartmentType = v18;
        if ( v18 < 0 )
          goto LABEL_30;
      }
      ApartmentType = (*(__int64 (__fastcall **)(__int64 *, const IID *, void **))v17)(v33, v30, ppv);
LABEL_30:
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    }
  }
  return ApartmentType;
}

```

## disassembly

```asm
0x1800062e0  mov     rax, rsp
0x1800062e3  mov     [rax+10h], rbx
0x1800062e7  push    rbp
0x1800062e8  push    rsi
0x1800062e9  push    rdi
0x1800062ea  push    r12
0x1800062ec  push    r13
0x1800062ee  push    r14
0x1800062f0  push    r15
0x1800062f2  lea     rbp, [rax-5Fh]
0x1800062f6  sub     rsp, 90h
0x1800062fd  movaps  xmmword ptr [rax-48h], xmm6
0x180006301  mov     rax, cs:__security_cookie
0x180006308  xor     rax, rsp
0x18000630b  mov     [rbp+57h+var_50], rax
0x18000630f  mov     [rbp+57h+var_80], r8
0x180006313  mov     r13, r9
0x180006316  mov     dword ptr [rbp+57h+var_70], edx
0x180006319  mov     r15d, edx
0x18000631c  mov     [rbp+57h+var_88], rcx
0x180006320  mov     rsi, rcx
0x180006323  mov     qword ptr [r9], 0
0x18000632a  mov     ebx, 80004003h
0x18000632f  test    rcx, rcx
0x180006332  jz      loc_18000654E
0x180006338  movups  xmm6, xmmword ptr cs:CLSID_MultiplexPropertyStore.Data1
0x18000633f  xor     ebx, ebx
0x180006341  mov     [rbp+57h+var_68], 0
0x180006349  movdqa  [rbp+57h+Buf1], xmm6
0x18000634e  lea     r12d, [rbx+10h]
0x180006352  lea     r14d, [rbx+1]
0x180006356  lea     rdx, __ImageBase
0x18000635d  cmp     ebx, 0Ah
0x180006360  jnb     loc_18000663E
0x180006366  lea     rcx, [rbx+rbx*2]
0x18000636a  mov     r8, r12; Size
0x18000636d  lea     rdi, ds:0F0230h[rcx*8]
0x180006375  add     rdi, rdx
0x180006378  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000637c  mov     rdx, rdi; Buf2
0x18000637f  call    memcmp_0
0x180006384  test    eax, eax
0x180006386  jz      short loc_18000638D
0x180006388  add     ebx, r14d
0x18000638b  jmp     short loc_180006356
0x18000638d  test    rdi, rdi
0x180006390  jz      loc_180006637
0x180006396  movups  xmm0, xmmword ptr cs:CLSID_PropSysBothClassFactory.Data1
0x18000639d  lea     r14, ?g_aloBothClassFactory@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloBothClassFactory
0x1800063a4  lea     r12, [r14+18h]
0x1800063a8  mov     [rbp+57h+var_78], 0
0x1800063b0  mov     r8, r12; Parameter
0x1800063b3  lea     rcx, [r14+10h]; InitOnce
0x1800063b7  xor     r9d, r9d; Context
0x1800063ba  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800063c1  movdqu  [rbp+57h+Buf1], xmm0
0x1800063c6  call    cs:__imp_InitOnceExecuteOnce
0x1800063cc  mov     rcx, r12; lpCriticalSection
0x1800063cf  call    cs:__imp_EnterCriticalSection
0x1800063d5  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800063d9  mov     [rbp+57h+pAptType], 0
0x1800063e0  lea     rcx, [rbp+57h+pAptType]; pAptType
0x1800063e4  mov     [rbp+57h+pAptQualifier], 0
0x1800063eb  call    cs:__imp_CoGetApartmentType
0x1800063f1  mov     ebx, eax
0x1800063f3  test    eax, eax
0x1800063f5  js      loc_18000648C
0x1800063fb  mov     ecx, [rbp+57h+pAptType]
0x1800063fe  test    ecx, ecx
0x180006400  jnz     loc_18000657C
0x180006406  mov     rcx, r14; this
0x180006409  call    ?_DelayAllocateTLS@CApartmentLocalObject@@AEAAJXZ; CApartmentLocalObject::_DelayAllocateTLS(void)
0x18000640e  mov     ebx, eax
0x180006410  test    eax, eax
0x180006412  js      short loc_18000648C
0x180006414  mov     r15d, [r14]
0x180006417  mov     edi, 1
0x18000641c  mov     [rbp+57h+var_78], 0
0x180006424  mov     ebx, edi
0x180006426  cmp     r15d, 0FFFFFFFFh
0x18000642a  jz      short loc_180006488
0x18000642c  mov     ecx, r15d; dwTlsIndex
0x18000642f  call    cs:__imp_TlsGetValue
0x180006435  mov     rsi, rax
0x180006438  test    rax, rax
0x18000643b  jz      loc_1800066BE
0x180006441  cmp     dword ptr [rax+28h], 0
0x180006445  jz      loc_1800067B5
0x18000644b  lock add [rax+8], edi
0x18000644f  mov     [rbp+57h+var_78], 0
0x180006457  mov     rcx, [rsi+20h]
0x18000645b  test    rcx, rcx
0x18000645e  jz      loc_18000673D
0x180006464  mov     rax, [rcx]
0x180006467  lea     r8, [rbp+57h+var_78]
0x18000646b  lea     rdx, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x180006472  mov     rax, [rax]
0x180006475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000647a  mov     ebx, eax
0x18000647c  mov     rcx, rsi; this
0x18000647f  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x180006484  mov     rsi, [rbp+57h+var_88]
0x180006488  mov     r15d, dword ptr [rbp+57h+var_70]
0x18000648c  mov     rcx, r12; lpCriticalSection
0x18000648f  call    cs:__imp_LeaveCriticalSection
0x180006495  mov     r12d, 1
0x18000649b  cmp     ebx, r12d
0x18000649e  jz      loc_1800065D8
0x1800064a4  test    ebx, ebx
0x1800064a6  js      loc_18000654E
0x1800064ac  mov     rcx, [rbp+57h+var_78]
0x1800064b0  lea     rdx, [rbp+57h+var_68]
0x1800064b4  mov     [rsp+0C0h+ppv], rdx
0x1800064b9  lea     rdi, CLSID_MultiplexPropertyStore
0x1800064c0  lea     r9, _GUID_b8158717_9161_46fd_b8d2_26d42185bc69
0x1800064c7  xor     r8d, r8d
0x1800064ca  mov     rdx, rdi
0x1800064cd  mov     rax, [rcx]
0x1800064d0  mov     rax, [rax+18h]
0x1800064d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d9  mov     ebx, eax
0x1800064db  cmp     eax, 80010108h
0x1800064e0  jz      loc_1800067BC
0x1800064e6  mov     rcx, [rbp+57h+var_78]
0x1800064ea  mov     [rbp+57h+var_78], 0
0x1800064f2  test    rcx, rcx
0x1800064f5  jz      short loc_180006503
0x1800064f7  mov     rax, [rcx]
0x1800064fa  mov     rax, [rax+10h]
0x1800064fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006503  test    ebx, ebx
0x180006505  js      short loc_18000654E
0x180006507  xor     edi, edi
0x180006509  mov     rcx, [rbp+57h+var_68]
0x18000650d  mov     rax, [rcx]
0x180006510  cmp     edi, r15d
0x180006513  jnb     short loc_18000652D
0x180006515  mov     rdx, [rsi+rdi*8]
0x180006519  mov     rax, [rax+18h]
0x18000651d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006522  add     edi, r12d
0x180006525  mov     ebx, eax
0x180006527  test    eax, eax
0x180006529  jns     short loc_180006509
0x18000652b  jmp     short loc_18000653E
0x18000652d  mov     rdx, [rbp+57h+var_80]
0x180006531  mov     r8, r13
0x180006534  mov     rax, [rax]
0x180006537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000653c  mov     ebx, eax
0x18000653e  mov     rcx, [rbp+57h+var_68]
0x180006542  mov     rax, [rcx]
0x180006545  mov     rax, [rax+10h]
0x180006549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654e  mov     eax, ebx
0x180006550  mov     rcx, [rbp+57h+var_50]
0x180006554  xor     rcx, rsp; StackCookie
0x180006557  call    __security_check_cookie
0x18000655c  lea     r11, [rsp+0C0h+var_30]
0x180006564  mov     rbx, [r11+48h]
0x180006568  movaps  xmm6, xmmword ptr [r11-10h]
0x18000656d  mov     rsp, r11
0x180006570  pop     r15
0x180006572  pop     r14
0x180006574  pop     r13
0x180006576  pop     r12
0x180006578  pop     rdi
0x180006579  pop     rsi
0x18000657a  pop     rbp
0x18000657b  retn
0x18000657c  sub     ecx, 1
0x18000657f  jnz     loc_180006690
0x180006585  mov     edi, [r14+4]
0x180006589  lea     edx, [rcx+1]
0x18000658c  mov     [rbp+57h+var_78], 0
0x180006594  mov     ebx, edx
0x180006596  test    edi, edi
0x180006598  jz      loc_18000648C
0x18000659e  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x1800065a5  test    rcx, rcx
0x1800065a8  jz      loc_180006775
0x1800065ae  mov     rax, [rcx]
0x1800065b1  lea     r9, [rbp+57h+var_78]
0x1800065b5  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x1800065bc  mov     edx, edi
0x1800065be  mov     rax, [rax+28h]
0x1800065c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065c7  mov     ebx, eax
0x1800065c9  test    eax, eax
0x1800065cb  mov     eax, 1
0x1800065d0  cmovs   ebx, eax
0x1800065d3  jmp     loc_18000648C
0x1800065d8  lea     rax, [rbp+57h+var_70]
0x1800065dc  mov     [rbp+57h+var_70], 0
0x1800065e4  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800065eb  mov     [rsp+0C0h+ppv], rax; ppv
0x1800065f0  mov     r8d, r12d; dwClsContext
0x1800065f3  lea     rcx, [rbp+57h+Buf1]; rclsid
0x1800065f7  xor     edx, edx; pUnkOuter
0x1800065f9  call    cs:__imp_CoCreateInstance
0x1800065ff  mov     ebx, eax
0x180006601  test    eax, eax
0x180006603  js      loc_18000654E
0x180006609  mov     rdx, [rbp+57h+var_70]; struct IUnknown *
0x18000660d  lea     r9, [rbp+57h+var_78]; void **
0x180006611  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; struct _GUID *
0x180006618  mov     rcx, r14; this
0x18000661b  call    ?TrySetApartmentObject@CApartmentLocalObject@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::TrySetApartmentObject(IUnknown *,_GUID const &,void * *)
0x180006620  mov     rcx, [rbp+57h+var_70]
0x180006624  mov     ebx, eax
0x180006626  mov     rax, [rcx]
0x180006629  mov     rax, [rax+10h]
0x18000662d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006632  jmp     loc_1800064A4
0x180006637  lea     rdx, __ImageBase
0x18000663e  movdqa  [rbp+57h+Buf1], xmm6
0x180006643  xor     ebx, ebx
0x180006645  cmp     ebx, 2
0x180006648  jnb     short loc_1800066B4
0x18000664a  lea     rcx, [rbx+rbx*2]
0x18000664e  mov     r8, r12; Size
0x180006651  lea     rdi, ds:0F0200h[rcx*8]
0x180006659  add     rdi, rdx
0x18000665c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180006660  mov     rdx, rdi; Buf2
0x180006663  call    memcmp_0
0x180006668  test    eax, eax
0x18000666a  jz      short loc_180006678
0x18000666c  add     ebx, r14d
0x18000666f  lea     rdx, __ImageBase
0x180006676  jmp     short loc_180006645
0x180006678  test    rdi, rdi
0x18000667b  jz      short loc_1800066B4
0x18000667d  movups  xmm0, xmmword ptr cs:CLSID_PropSysApartmentClassFactory.Data1
0x180006684  lea     r14, ?g_aloApartmentClassFactory@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloApartmentClassFactory
0x18000668b  jmp     loc_1800063A4
0x180006690  sub     ecx, 1; this
0x180006693  jnz     loc_180006762
0x180006699  mov     edx, [r14+8]; unsigned int
0x18000669d  lea     r9, [rbp+57h+var_78]; void **
0x1800066a1  lea     r8, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; struct _GUID *
0x1800066a8  call    ?_GetInterfaceFromGIT@CApartmentLocalObject@@AEAAJKAEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::_GetInterfaceFromGIT(ulong,_GUID const &,void * *)
0x1800066ad  mov     ebx, eax
0x1800066af  jmp     loc_18000648C
0x1800066b4  mov     ebx, 80040154h
0x1800066b9  jmp     loc_18000654E
0x1800066be  xor     esi, esi
0x1800066c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800066c7  lea     ecx, [rsi+30h]; unsigned __int64
0x1800066ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800066cf  test    rax, rax
0x1800066d2  jz      short loc_180006744
0x1800066d4  mov     rcx, rax; this
0x1800066d7  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x1800066dc  mov     rdi, rax
0x1800066df  test    rax, rax
0x1800066e2  jz      short loc_180006744
0x1800066e4  lea     rdx, [rax+10h]; puliCookie
0x1800066e8  mov     [rax+18h], r15d
0x1800066ec  mov     rcx, rax; pSpy
0x1800066ef  call    cs:__imp_CoRegisterInitializeSpy
0x1800066f5  mov     ebx, eax
0x1800066f7  test    eax, eax
0x1800066f9  js      short loc_18000671D
0x1800066fb  lea     ebx, [rsi+1]
0x1800066fe  mov     [rdi+28h], ebx
0x180006701  cmp     cs:?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * CCachedSTAObject::s_hmod
0x180006708  jz      short loc_18000674B
0x18000670a  mov     rdx, rdi; lpTlsValue
0x18000670d  mov     ecx, r15d; dwTlsIndex
0x180006710  call    cs:__imp_TlsSetValue
0x180006716  mov     rsi, rdi
0x180006719  lock add [rdi+8], ebx
0x18000671d  mov     rcx, rdi; this
0x180006720  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x180006725  test    ebx, ebx
0x180006727  js      loc_1800067B0
0x18000672d  jnz     loc_18000647C
0x180006733  mov     edi, 1
0x180006738  jmp     loc_18000644F
0x18000673d  mov     ebx, edi
0x18000673f  jmp     loc_18000647C
0x180006744  mov     ebx, 8007000Eh
0x180006749  jmp     short loc_180006725
0x18000674b  lea     rdx, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; lpModuleName
0x180006752  mov     ecx, 4; dwFlags
0x180006757  mov     r8, rdx; phModule
0x18000675a  call    cs:__imp_GetModuleHandleExW
0x180006760  jmp     short loc_18000670A
0x180006762  cmp     ecx, 1
0x180006765  jz      loc_180006406
0x18000676b  mov     ebx, 800401F0h
0x180006770  jmp     loc_18000648C
0x180006775  lea     rax, ?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x18000677c  mov     r8d, edx; dwClsContext
0x18000677f  xor     edx, edx; pUnkOuter
0x180006781  mov     [rsp+0C0h+ppv], rax; ppv
0x180006786  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000678d  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006794  call    cs:__imp_CoCreateInstance
  ... truncated ...
```
