# ScheduleAlertTask(ushort const *,DMAlertType)

- ea: `0x180062ee0`
- end: `0x1800634ee`
- name: `?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z`
- size: `1550`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180065d70`

## callees

- `0x1800067a0`
- `0x18000de50`
- `0x18000efc4`
- `0x180019e8c`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18002e570`
- `0x18003708c`
- `0x1800434d0`
- `0x180043544`
- `0x180060894`
- `0x180060974`
- `0x180060998`
- `0x1800613ac`
- `0x180062ee0`
- `0x180065acc`
- `0x180072be0`
- `0x180074494`
- `0x180074524`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180063412`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180063412`
- `OLEAUT32!__imp_SysFreeString` at `0x180063195`
- `OLEAUT32!__imp_SysFreeString` at `0x180063362`
- `OLEAUT32!__imp_SysFreeString` at `0x180063195`
- `OLEAUT32!__imp_SysFreeString` at `0x180063362`
- `OLEAUT32!__imp_VariantInit` at `0x18006327b`
- `OLEAUT32!__imp_VariantInit` at `0x18006328e`
- `OLEAUT32!__imp_VariantInit` at `0x18006327b`
- `OLEAUT32!__imp_VariantInit` at `0x18006328e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180063431`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180063450`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180063431`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180063450`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180063424`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180063443`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180063424`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180063443`
- `RPCRT4!UuidFromStringW` at `0x180063014`
- `RPCRT4!UuidFromStringW` at `0x180063014`
- `DMCmnUtils!DmDisableTask` at `0x1800633c3`
- `DMCmnUtils!DmDisableTask` at `0x1800633c3`

## string_xrefs

- `0x1800630f8`: `%windir%\system32\deviceenroller.exe`
- `0x180062fdb`: `/s "%s" /c /Win10SModeAlert /SID "%s"`
- `0x180062ff2`: `/s "%s" /c /OsEditionUpgradeAlert /SID "%s"`
- `0x180062ff9`: `OS Edition Upgrade event listener created by enrollment client`
- `0x180062fe2`: `Win10 S Mode event listener created by enrollment client`
- `0x180062fc1`: `Wsc Startup event listener created by enrollment client`
- `0x1800633b2`: `Wsc Startup event listener created by enrollment client`

## pseudocode

```c
__int64 __fastcall ScheduleAlertTask(unsigned __int16 *a1, int a2)
{
  int v4; // edi
  const unsigned __int16 *v5; // r15
  unsigned int v6; // edx
  void *v7; // rax
  const unsigned __int16 *v8; // rbx
  RPC_STATUS v9; // edi
  int EnrollmentString; // eax
  unsigned __int16 *v11; // rax
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, __int64); // rdi
  _bstr_t *v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rbx
  void *v18; // rcx
  unsigned int i; // ebx
  struct IUnknown *v20; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // r12
  __int128 v22; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v24; // xmm8
  IRecordInfo *v25; // xmm9_8
  _variant_t *v26; // rax
  __int64 v27; // rdi
  __int128 v28; // xmm10
  __int64 v29; // xmm11_8
  _bstr_t *v30; // rax
  __int64 v31; // rdx
  int v32; // eax
  BSTR *v33; // rbx
  BSTR v34; // rcx
  int v35; // esi
  CEnrollmentLogger *Logger; // rax
  CEnrollmentLogger *v37; // rax
  CEnrollmentLogger *v38; // rax
  SAFEARRAY *v39; // rbx
  SAFEARRAY *v40; // rbx
  unsigned __int16 *v42; // [rsp+78h] [rbp-90h] BYREF
  void *v43; // [rsp+80h] [rbp-88h] BYREF
  int v44; // [rsp+88h] [rbp-80h] BYREF
  __int64 v45; // [rsp+90h] [rbp-78h] BYREF
  __int64 v46; // [rsp+98h] [rbp-70h] BYREF
  SAFEARRAY *v47; // [rsp+A0h] [rbp-68h] BYREF
  __int64 *v48; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-58h] BYREF
  struct IUnknown *v50; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v52[2]; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG Block; // [rsp+D8h] [rbp-30h] BYREF
  SAFEARRAY *psa; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v55; // [rsp+100h] [rbp-8h] BYREF
  __int64 v56; // [rsp+108h] [rbp+0h] BYREF
  VARIANTARG pvarg; // [rsp+110h] [rbp+8h] BYREF
  __int128 v58; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v59; // [rsp+138h] [rbp+30h]
  __int128 v60; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v61; // [rsp+158h] [rbp+50h]
  __int128 v62; // [rsp+168h] [rbp+60h] BYREF
  __int64 v63; // [rsp+178h] [rbp+70h]
  VARIANTARG v64; // [rsp+188h] [rbp+80h] BYREF
  UUID Uuid; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int16 v66[264]; // [rsp+1B8h] [rbp+B0h] BYREF

  v52[0] = 0;
  v50 = 0;
  v45 = 0;
  v49 = 0;
  v51 = 0;
  v46 = 0;
  v48 = 0;
  v56 = 0;
  v55 = 0;
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&v47, 8u);
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&psa, 0);
  v44 = 0;
  Uuid = 0;
  switch ( a2 )
  {
    case 0:
      v7 = (void *)WNF_OLIC_OS_EDITION_CHANGE;
      v8 = L"/s \"%s\" /c /OsEditionUpgradeAlert /SID \"%s\"";
      v5 = L"OS Edition Upgrade event listener created by enrollment client";
LABEL_8:
      v43 = v7;
      v42 = 0;
      v9 = UuidFromStringW(a1, &Uuid);
      if ( v9 )
      {
        v4 = v9 | 0x80010000;
        CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v42);
        goto LABEL_54;
      }
      *(UUID *)&Block.vt = Uuid;
      EnrollmentString = EEDBManager::GetEnrollmentString((struct _GUID *)&Block, L"SID", &v42);
      v4 = EnrollmentString;
      if ( EnrollmentString < 0 )
      {
        if ( EnrollmentString != -2147024894 )
        {
LABEL_15:
          CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v42);
LABEL_16:
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v44, v6);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = CreateTask(
                 v52,
                 &v50,
                 &v45,
                 &v49,
                 a1,
                 L"%windir%\\system32\\deviceenroller.exe",
                 v66,
                 L"S-1-5-18",
                 0,
                 1,
                 0,
                 0,
                 0);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 120LL))(v45, &v46);
          if ( v4 < 0 )
            goto LABEL_55;
          v12 = v46;
          v13 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 64LL);
          v14 = _bstr_t::_bstr_t((_bstr_t *)&Block, L"LocalSystem");
          if ( *(_QWORD *)v14 )
            v15 = **(_QWORD **)v14;
          else
            v15 = 0;
          v16 = v13(v12, v15);
          v17 = *(_QWORD *)&Block.vt;
          v4 = v16;
          if ( *(_QWORD *)&Block.vt
            && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&Block.vt + 16LL), 0xFFFFFFFF) == 1
            && v17 )
          {
            if ( *(_QWORD *)v17 )
            {
              SysFreeString(*(BSTR *)v17);
              *(_QWORD *)v17 = 0;
            }
            v18 = *(void **)(v17 + 8);
            if ( v18 )
            {
              operator delete(v18);
              *(_QWORD *)(v17 + 8) = 0;
            }
            operator delete((void *)v17);
          }
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 144LL))(v46, 1);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 208LL))(v49, 0xFFFFFFFFLL);
          if ( v4 < 0 )
            goto LABEL_55;
          v4 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v45 + 72LL))(v45, &v48);
          if ( v4 < 0 )
            goto LABEL_55;
          for ( i = 0; (unsigned __int64)(int)i < 8; ++i )
          {
            v4 = ATL::CComSafeArray<unsigned char,17>::SetAt(&v47, i, (char *)&v43 + (int)i);
            if ( v4 < 0 )
              goto LABEL_55;
          }
          v4 = AddTaskWNFTrigger(v48, &v47);
          if ( v4 < 0 )
            goto LABEL_55;
          v20 = v50;
          Release = v50->lpVtbl[5].Release;
          VariantInit(&pvarg);
          v22 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&Block);
          v24 = *(_OWORD *)&Block.vt;
          v25 = Block.pRecInfo;
          v26 = _variant_t::_variant_t((_variant_t *)&v64, L"S-1-5-18");
          v27 = v45;
          v28 = *(_OWORD *)v26;
          v29 = *((_QWORD *)v26 + 2);
          v30 = _bstr_t::_bstr_t((_bstr_t *)&v43, v5);
          if ( *(_QWORD *)v30 )
            v31 = **(_QWORD **)v30;
          else
            v31 = 0;
          v58 = v22;
          v59 = pRecInfo;
          v60 = v24;
          v61 = v25;
          v62 = v28;
          v63 = v29;
          v32 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))Release)(
                  v20,
                  v31,
                  v27,
                  6,
                  &v62,
                  &v60,
                  3,
                  &v58,
                  &v51);
          v33 = (BSTR *)v43;
          v4 = v32;
          if ( v43 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43 + 4, 0xFFFFFFFF) == 1 && v33 )
            {
              if ( *v33 )
              {
                SysFreeString(*v33);
                *v33 = 0;
              }
              v34 = v33[1];
              if ( v34 )
              {
                operator delete(v34);
                v33[1] = 0;
              }
              operator delete(v33);
            }
            v43 = 0;
          }
          _variant_t::~_variant_t(&v64);
          _variant_t::~_variant_t(&Block);
          _variant_t::~_variant_t(&pvarg);
          if ( a2 == 2 )
            DmDisableTask(
              L"\\Microsoft\\Windows\\EnterpriseMgmt",
              a1,
              L"Wsc Startup event listener created by enrollment client");
LABEL_54:
          if ( v4 >= 0 )
            goto LABEL_61;
          goto LABEL_55;
        }
        v11 = L"S-1-1-0";
      }
      else
      {
        v11 = v42;
      }
      v4 = StringCchPrintfW(v66, 0x104u, v8, a1, v11);
      goto LABEL_15;
    case 1:
      v7 = (void *)WNF_CI_SMODE_CHANGE;
      v8 = L"/s \"%s\" /c /Win10SModeAlert /SID \"%s\"";
      v5 = L"Win10 S Mode event listener created by enrollment client";
      goto LABEL_8;
    case 2:
      v43 = (void *)WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION;
      v5 = L"Wsc Startup event listener created by enrollment client";
      v4 = StringCchPrintfW(v66, 0x104u, L"/s \"%s\" /c /WscStartupAlert", a1);
      goto LABEL_16;
  }
  v4 = -2147418113;
LABEL_55:
  if ( a2 )
  {
    v35 = a2 - 1;
    if ( v35 )
    {
      if ( v35 == 1 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogWscStartupAlertScheduleSetupFail(Logger, v4);
      }
    }
    else
    {
      v37 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogWin10SModeScheduleSetupFail(v37, v4);
    }
  }
  else
  {
    v38 = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogOsEditionUpgradeScheduleSetupFail(v38, v4);
  }
LABEL_61:
  if ( v44 )
    CoUninitialize();
  v39 = psa;
  if ( psa && SafeArrayUnlock(psa) >= 0 )
    SafeArrayDestroy(v39);
  v40 = v47;
  if ( v47 && SafeArrayUnlock(v47) >= 0 )
    SafeArrayDestroy(v40);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v55);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v56);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v48);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v46);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v51);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v49);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(&v45);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>((__int64 *)&v50);
  ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(v52);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180062ee0  mov     rax, rsp
0x180062ee3  push    rbp
0x180062ee4  push    rbx
0x180062ee5  push    rsi
0x180062ee6  push    rdi
0x180062ee7  push    r12
0x180062ee9  push    r13
0x180062eeb  push    r14
0x180062eed  push    r15
0x180062eef  lea     rbp, [rax-378h]
0x180062ef6  sub     rsp, 438h
0x180062efd  movaps  xmmword ptr [rax-58h], xmm6
0x180062f01  movaps  xmmword ptr [rax-68h], xmm7
0x180062f05  movaps  xmmword ptr [rax-78h], xmm8
0x180062f0a  movaps  xmmword ptr [rax-88h], xmm9
0x180062f12  movaps  xmmword ptr [rax-98h], xmm10
0x180062f1a  movaps  xmmword ptr [rax-0A8h], xmm11
0x180062f22  mov     rax, cs:__security_cookie
0x180062f29  xor     rax, rsp
0x180062f2c  mov     [rbp+370h+var_B0], rax
0x180062f33  xor     r13d, r13d
0x180062f36  mov     esi, edx
0x180062f38  mov     r14, rcx
0x180062f3b  mov     [rbp+370h+var_3B0], r13
0x180062f3f  lea     rcx, [rbp+370h+var_3D8]
0x180062f43  mov     [rbp+370h+var_3C0], r13
0x180062f47  mov     [rbp+370h+var_3E8], r13
0x180062f4b  lea     edx, [r13+8]
0x180062f4f  mov     [rbp+370h+var_3C8], r13
0x180062f53  mov     [rbp+370h+var_3B8], r13
0x180062f57  mov     [rbp+370h+var_3E0], r13
0x180062f5b  mov     [rbp+370h+var_3D0], r13
0x180062f5f  mov     [rbp+370h+var_370], r13
0x180062f63  mov     [rbp+370h+var_378], r13
0x180062f67  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x180062f6c  xor     edx, edx
0x180062f6e  lea     rcx, [rbp+370h+psa]
0x180062f72  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x180062f77  mov     [rbp+370h+var_3F0], r13d
0x180062f7b  xorps   xmm0, xmm0
0x180062f7e  mov     ecx, esi
0x180062f80  movups  xmmword ptr [rbp+370h+Uuid.Data1], xmm0
0x180062f87  test    esi, esi
0x180062f89  jz      short loc_180062FEB
0x180062f8b  sub     ecx, 1
0x180062f8e  jz      short loc_180062FD4
0x180062f90  cmp     ecx, 1
0x180062f93  jz      short loc_180062F9F
0x180062f95  mov     edi, 8000FFFFh
0x180062f9a  jmp     loc_1800633CD
0x180062f9f  mov     rax, cs:WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION
0x180062fa6  lea     r8, aSSCWscstartupa; "/s \"%s\" /c /WscStartupAlert"
0x180062fad  mov     r9, r14
0x180062fb0  mov     [rsp+470h+var_3F8], rax
0x180062fb5  mov     edx, 104h; unsigned __int64
0x180062fba  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x180062fc1  lea     r15, aWscStartupEven; "Wsc Startup event listener created by e"...
0x180062fc8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180062fcd  mov     edi, eax
0x180062fcf  jmp     loc_180063099
0x180062fd4  mov     rax, cs:WNF_CI_SMODE_CHANGE
0x180062fdb  lea     rbx, aSSCWin10smodea; "/s \"%s\" /c /Win10SModeAlert /SID \"%s"...
0x180062fe2  lea     r15, aWin10SModeEven; "Win10 S Mode event listener created by "...
0x180062fe9  jmp     short loc_180063000
0x180062feb  mov     rax, cs:WNF_OLIC_OS_EDITION_CHANGE
0x180062ff2  lea     rbx, aSSCOseditionup; "/s \"%s\" /c /OsEditionUpgradeAlert /SI"...
0x180062ff9  lea     r15, aOsEditionUpgra; "OS Edition Upgrade event listener creat"...
0x180063000  lea     rdx, [rbp+370h+Uuid]; Uuid
0x180063007  mov     [rsp+470h+var_3F8], rax
0x18006300c  mov     rcx, r14; StringUuid
0x18006300f  mov     [rsp+470h+var_400], r13
0x180063014  call    cs:__imp_UuidFromStringW
0x18006301a  mov     edi, eax
0x18006301c  test    eax, eax
0x18006301e  jz      short loc_180063035
0x180063020  or      edi, 80010000h
0x180063026  lea     rcx, [rsp+470h+var_400]
0x18006302b  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180063030  jmp     loc_1800633C9
0x180063035  movaps  xmm0, xmmword ptr [rbp+370h+Uuid.Data1]
0x18006303c  lea     r8, [rsp+470h+var_400]; unsigned __int16 **
0x180063041  lea     rdx, aSid; "SID"
0x180063048  movdqa  xmmword ptr [rbp+370h+Block], xmm0
0x18006304d  lea     rcx, [rbp+370h+Block]; struct _GUID
0x180063051  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x180063056  mov     edi, eax
0x180063058  test    eax, eax
0x18006305a  js      short loc_180063063
0x18006305c  mov     rax, [rsp+470h+var_400]
0x180063061  jmp     short loc_180063071
0x180063063  cmp     eax, 80070002h
0x180063068  jnz     short loc_18006308F
0x18006306a  lea     rax, aS110; "S-1-1-0"
0x180063071  mov     r9, r14
0x180063074  mov     [rsp+470h+var_450], rax
0x180063079  mov     r8, rbx; unsigned __int16 *
0x18006307c  lea     rcx, [rbp+370h+var_2C0]; unsigned __int16 *
0x180063083  mov     edx, 104h; unsigned __int64
0x180063088  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006308d  mov     edi, eax
0x18006308f  lea     rcx, [rsp+470h+var_400]
0x180063094  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180063099  test    edi, edi
0x18006309b  js      loc_1800633CD
0x1800630a1  lea     rcx, [rbp+370h+var_3F0]; this
0x1800630a5  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800630aa  mov     edi, eax
0x1800630ac  test    eax, eax
0x1800630ae  js      loc_1800633CD
0x1800630b4  mov     [rsp+470h+var_410], r13d
0x1800630b9  lea     rax, aS1518; "S-1-5-18"
0x1800630c0  mov     [rsp+470h+var_418], r13d
0x1800630c5  lea     r9, [rbp+370h+var_3C8]
0x1800630c9  mov     [rsp+470h+var_420], r13d
0x1800630ce  lea     r8, [rbp+370h+var_3E8]
0x1800630d2  mov     [rsp+470h+var_428], 1
0x1800630da  lea     rdx, [rbp+370h+var_3C0]
0x1800630de  mov     [rsp+470h+var_430], r13d
0x1800630e3  lea     rcx, [rbp+370h+var_3B0]
0x1800630e7  mov     [rsp+470h+var_438], rax
0x1800630ec  lea     rax, [rbp+370h+var_2C0]
0x1800630f3  mov     [rsp+470h+var_440], rax
0x1800630f8  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x1800630ff  mov     [rsp+470h+var_448], rax
0x180063104  mov     [rsp+470h+var_450], r14
0x180063109  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x18006310e  mov     edi, eax
0x180063110  test    eax, eax
0x180063112  js      loc_1800633CD
0x180063118  mov     rcx, [rbp+370h+var_3E8]
0x18006311c  lea     rdx, [rbp+370h+var_3E0]
0x180063120  mov     rax, [rcx]
0x180063123  mov     rax, [rax+78h]
0x180063127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006312c  mov     edi, eax
0x18006312e  test    eax, eax
0x180063130  js      loc_1800633CD
0x180063136  mov     rbx, [rbp+370h+var_3E0]
0x18006313a  lea     rdx, aLocalsystem; "LocalSystem"
0x180063141  lea     rcx, [rbp+370h+Block]; this
0x180063145  mov     rax, [rbx]
0x180063148  mov     rdi, [rax+40h]
0x18006314c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180063151  mov     rcx, [rax]
0x180063154  test    rcx, rcx
0x180063157  jz      short loc_18006315E
0x180063159  mov     rdx, [rcx]
0x18006315c  jmp     short loc_180063161
0x18006315e  mov     rdx, r13
0x180063161  mov     rcx, rbx
0x180063164  mov     rax, rdi
0x180063167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006316c  mov     rbx, [rbp+370h+Block]
0x180063170  or      r12d, 0FFFFFFFFh
0x180063174  mov     edi, eax
0x180063176  test    rbx, rbx
0x180063179  jz      short loc_1800631BD
0x18006317b  mov     eax, r12d
0x18006317e  lock xadd [rbx+10h], eax
0x180063183  add     eax, r12d
0x180063186  jnz     short loc_1800631BD
0x180063188  test    rbx, rbx
0x18006318b  jz      short loc_1800631BD
0x18006318d  mov     rcx, [rbx]; bstrString
0x180063190  test    rcx, rcx
0x180063193  jz      short loc_18006319E
0x180063195  call    cs:__imp_SysFreeString
0x18006319b  mov     [rbx], r13
0x18006319e  mov     rcx, [rbx+8]; Block
0x1800631a2  test    rcx, rcx
0x1800631a5  jz      short loc_1800631B0
0x1800631a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800631ac  mov     [rbx+8], r13
0x1800631b0  mov     edx, 18h
0x1800631b5  mov     rcx, rbx; Block
0x1800631b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800631bd  test    edi, edi
0x1800631bf  js      loc_1800633CD
0x1800631c5  mov     rcx, [rbp+370h+var_3E0]
0x1800631c9  mov     edx, 1
0x1800631ce  mov     rax, [rcx]
0x1800631d1  mov     rax, [rax+90h]
0x1800631d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631dd  mov     edi, eax
0x1800631df  test    eax, eax
0x1800631e1  js      loc_1800633CD
0x1800631e7  mov     rcx, [rbp+370h+var_3C8]
0x1800631eb  mov     edx, r12d
0x1800631ee  mov     rax, [rcx]
0x1800631f1  mov     rax, [rax+0D0h]
0x1800631f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631fd  mov     edi, eax
0x1800631ff  test    eax, eax
0x180063201  js      loc_1800633CD
0x180063207  mov     rcx, [rbp+370h+var_3E8]
0x18006320b  lea     rdx, [rbp+370h+var_3D0]
0x18006320f  mov     rax, [rcx]
0x180063212  mov     rax, [rax+48h]
0x180063216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006321b  mov     edi, eax
0x18006321d  test    eax, eax
0x18006321f  js      loc_1800633CD
0x180063225  mov     ebx, r13d
0x180063228  movsxd  rax, ebx
0x18006322b  cmp     rax, 8
0x18006322f  jnb     short loc_180063252
0x180063231  lea     r8, [rsp+470h+var_3F8]
0x180063236  mov     edx, ebx
0x180063238  add     r8, rax
0x18006323b  lea     rcx, [rbp+370h+var_3D8]
0x18006323f  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x180063244  mov     edi, eax
0x180063246  test    eax, eax
0x180063248  js      loc_1800633CD
0x18006324e  inc     ebx
0x180063250  jmp     short loc_180063228
0x180063252  mov     rcx, [rbp+370h+var_3D0]
0x180063256  lea     rdx, [rbp+370h+var_3D8]
0x18006325a  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x18006325f  mov     edi, eax
0x180063261  test    eax, eax
0x180063263  js      loc_1800633CD
0x180063269  mov     rbx, [rbp+370h+var_3C0]
0x18006326d  lea     rcx, [rbp+370h+pvarg]; pvarg
0x180063271  mov     rax, [rbx]
0x180063274  mov     r12, [rax+88h]
0x18006327b  call    cs:__imp_VariantInit
0x180063281  movups  xmm6, xmmword ptr [rbp+370h+pvarg]
0x180063285  lea     rcx, [rbp+370h+Block]; pvarg
0x180063289  movsd   xmm7, qword ptr [rbp+370h+pvarg+10h]
0x18006328e  call    cs:__imp_VariantInit
0x180063294  movups  xmm8, xmmword ptr [rbp+370h+Block]
0x180063299  lea     rdx, aS1518; "S-1-5-18"
0x1800632a0  movsd   xmm9, [rbp+370h+var_390]
0x1800632a6  lea     rcx, [rbp+370h+var_2F0]; this
0x1800632ad  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x1800632b2  mov     rdi, [rbp+370h+var_3E8]
0x1800632b6  lea     rcx, [rsp+470h+var_3F8]; this
0x1800632bb  mov     rdx, r15; unsigned __int16 *
0x1800632be  movups  xmm10, xmmword ptr [rax]
0x1800632c2  movsd   xmm11, qword ptr [rax+10h]
0x1800632c8  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800632cd  mov     rdx, [rax]
0x1800632d0  test    rdx, rdx
0x1800632d3  jz      short loc_1800632DA
0x1800632d5  mov     rdx, [rdx]
0x1800632d8  jmp     short loc_1800632DD
0x1800632da  mov     rdx, r13
0x1800632dd  lea     rax, [rbp+370h+var_3B8]
0x1800632e1  movaps  [rbp+370h+var_350], xmm6
0x1800632e5  mov     qword ptr [rsp+470h+var_430], rax
0x1800632ea  mov     r9d, 6
0x1800632f0  lea     rax, [rbp+370h+var_350]
0x1800632f4  movsd   [rbp+370h+var_340], xmm7
0x1800632f9  mov     [rsp+470h+var_438], rax
0x1800632fe  mov     r8, rdi
0x180063301  lea     rax, [rbp+370h+var_330]
0x180063305  mov     dword ptr [rsp+470h+var_440], 3
0x18006330d  mov     [rsp+470h+var_448], rax
0x180063312  mov     rcx, rbx
0x180063315  lea     rax, [rbp+370h+var_310]
0x180063319  movaps  [rbp+370h+var_330], xmm8
0x18006331e  mov     [rsp+470h+var_450], rax
0x180063323  mov     rax, r12
0x180063326  movsd   [rbp+370h+var_320], xmm9
0x18006332c  movaps  [rbp+370h+var_310], xmm10
0x180063331  movsd   [rbp+370h+var_300], xmm11
0x180063337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006333c  mov     rbx, [rsp+470h+var_3F8]
0x180063341  mov     edi, eax
0x180063343  test    rbx, rbx
0x180063346  jz      short loc_18006338F
0x180063348  or      eax, 0FFFFFFFFh
0x18006334b  lock xadd [rbx+10h], eax
0x180063350  cmp     eax, 1
0x180063353  jnz     short loc_18006338A
0x180063355  test    rbx, rbx
0x180063358  jz      short loc_18006338A
0x18006335a  mov     rcx, [rbx]; bstrString
0x18006335d  test    rcx, rcx
0x180063360  jz      short loc_18006336B
0x180063362  call    cs:__imp_SysFreeString
0x180063368  mov     [rbx], r13
0x18006336b  mov     rcx, [rbx+8]; Block
0x18006336f  test    rcx, rcx
0x180063372  jz      short loc_18006337D
0x180063374  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063379  mov     [rbx+8], r13
0x18006337d  mov     edx, 18h
0x180063382  mov     rcx, rbx; Block
0x180063385  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006338a  mov     [rsp+470h+var_3F8], r13
0x18006338f  lea     rcx, [rbp+370h+var_2F0]; this
0x180063396  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18006339b  lea     rcx, [rbp+370h+Block]; this
0x18006339f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800633a4  lea     rcx, [rbp+370h+pvarg]; this
0x1800633a8  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800633ad  cmp     esi, 2
0x1800633b0  jnz     short loc_1800633C9
  ... truncated ...
```
