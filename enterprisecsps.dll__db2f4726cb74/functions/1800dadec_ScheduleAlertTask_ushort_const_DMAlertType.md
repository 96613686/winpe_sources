# ScheduleAlertTask(ushort const *,DMAlertType)

- ea: `0x1800dadec`
- end: `0x1800db30e`
- name: `?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z`
- size: `1314`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a27c0`
- `0x1800a3bc0`

## callees

- `0x180008de0`
- `0x1800091b0`
- `0x18000db4c`
- `0x18001a4fc`
- `0x1800637f4`
- `0x180063870`
- `0x1800639d0`
- `0x1800c18f0`
- `0x1800ca7a8`
- `0x1800d11a4`
- `0x1800d19fc`
- `0x1800d7720`
- `0x1800d7e58`
- `0x1800d820c`
- `0x1800dadec`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800dafae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800db18f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dafae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800db18f`
- `OLEAUT32!__imp_VariantInit` at `0x1800db099`
- `OLEAUT32!__imp_VariantInit` at `0x1800db0b2`
- `OLEAUT32!__imp_VariantInit` at `0x1800db099`
- `OLEAUT32!__imp_VariantInit` at `0x1800db0b2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800db241`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800db26c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800db241`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800db26c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800db22e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800db259`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800db22e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800db259`
- `DMCmnUtils!DmDisableTask` at `0x1800db1f0`
- `DMCmnUtils!DmDisableTask` at `0x1800db1f0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800db216`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800db216`

## string_xrefs

- `0x1800daf03`: `%windir%\system32\deviceenroller.exe`
- `0x1800db0eb`: `Wsc Startup event listener created by enrollment client`
- `0x1800db1df`: `Wsc Startup event listener created by enrollment client`

## pseudocode

```c
__int64 __fastcall ScheduleAlertTask(const unsigned __int16 *a1)
{
  unsigned int v2; // edx
  int v3; // edi
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, __int64); // rdi
  _bstr_t *v6; // rax
  __int64 v7; // rdx
  BSTR *v8; // rbx
  BSTR v9; // rcx
  unsigned int i; // ebx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r14
  __int128 v13; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  __int128 v15; // xmm8
  IRecordInfo *v16; // xmm9_8
  _variant_t *v17; // rax
  __int128 v18; // xmm10
  __int64 v19; // xmm11_8
  __int64 v20; // rdi
  _bstr_t *v21; // rax
  __int64 v22; // rdx
  BSTR *v23; // rbx
  BSTR v24; // rcx
  CEnrollmentLogger *Logger; // rax
  SAFEARRAY *v26; // rbx
  SAFEARRAY *v27; // rbx
  __int64 v29; // [rsp+78h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-88h] BYREF
  __int64 v31; // [rsp+88h] [rbp-80h] BYREF
  void *Block[2]; // [rsp+90h] [rbp-78h] BYREF
  SAFEARRAY *v33; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v39; // [rsp+D0h] [rbp-38h] BYREF
  SAFEARRAY *psa; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v41; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v42; // [rsp+E8h] [rbp-20h] BYREF
  VARIANTARG v43; // [rsp+F0h] [rbp-18h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+0h] BYREF
  __int128 v45; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v46; // [rsp+138h] [rbp+30h]
  __int128 v47; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v48; // [rsp+158h] [rbp+50h]
  __int128 v49; // [rsp+168h] [rbp+60h] BYREF
  __int64 v50; // [rsp+178h] [rbp+70h]
  _BYTE v51[24]; // [rsp+188h] [rbp+80h] BYREF
  __int128 v52; // [rsp+1A0h] [rbp+98h]
  unsigned __int16 v53[264]; // [rsp+1B8h] [rbp+B0h] BYREF

  v38 = 0;
  v36 = 0;
  v30 = 0;
  v35 = 0;
  v37 = 0;
  v31 = 0;
  v34 = 0;
  v42 = 0;
  v41 = 0;
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&v33, 8);
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&psa, 0);
  LODWORD(v29) = 0;
  v52 = 0;
  v39 = WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION;
  v3 = StringCchPrintfW(v53, 0x104u, L"/s \"%s\" /c /WscStartupAlert", a1);
  if ( v3 < 0 )
    goto LABEL_38;
  v3 = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v29, v2);
  if ( v3 < 0 )
    goto LABEL_38;
  v3 = CreateTask(
         &v38,
         &v36,
         &v30,
         &v35,
         a1,
         L"%windir%\\system32\\deviceenroller.exe",
         v53,
         L"S-1-5-18",
         0,
         1,
         0,
         0,
         0);
  if ( v3 < 0 )
    goto LABEL_38;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 120LL))(v30, &v31);
  if ( v3 < 0 )
    goto LABEL_38;
  v4 = v31;
  v5 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 64LL);
  v6 = _bstr_t::_bstr_t((_bstr_t *)Block, L"LocalSystem");
  if ( *(_QWORD *)v6 )
    v7 = **(_QWORD **)v6;
  else
    v7 = 0;
  v3 = v5(v4, v7);
  v8 = (BSTR *)Block[0];
  if ( Block[0] && _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v8 )
  {
    if ( *v8 )
    {
      SysFreeString(*v8);
      *v8 = 0;
    }
    v9 = v8[1];
    if ( v9 )
    {
      operator delete(v9);
      v8[1] = 0;
    }
    operator delete(v8);
  }
  if ( v3 < 0 )
    goto LABEL_38;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 144LL))(v31, 1);
  if ( v3 < 0 )
    goto LABEL_38;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 208LL))(v35, 0xFFFFFFFFLL);
  if ( v3 < 0 )
    goto LABEL_38;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 72LL))(v30, &v34);
  if ( v3 < 0 )
    goto LABEL_38;
  for ( i = 0; (unsigned __int64)(int)i < 8; ++i )
  {
    v3 = ATL::CComSafeArray<unsigned char,17>::SetAt(&v33, i, (char *)&v39 + (int)i);
    if ( v3 < 0 )
      goto LABEL_38;
  }
  v3 = AddTaskWNFTrigger(v34, &v33);
  if ( v3 < 0 )
    goto LABEL_38;
  v11 = v36;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(*(_QWORD *)v36 + 136LL);
  VariantInit(&pvarg);
  v13 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v43);
  v15 = *(_OWORD *)&v43.vt;
  v16 = v43.pRecInfo;
  v17 = _variant_t::_variant_t((_variant_t *)v51, L"S-1-5-18");
  v18 = *(_OWORD *)v17;
  v19 = *((_QWORD *)v17 + 2);
  v20 = v30;
  v21 = _bstr_t::_bstr_t((_bstr_t *)Block, L"Wsc Startup event listener created by enrollment client");
  if ( *(_QWORD *)v21 )
    v22 = **(_QWORD **)v21;
  else
    v22 = 0;
  v45 = v13;
  v46 = pRecInfo;
  v47 = v15;
  v48 = v16;
  v49 = v18;
  v50 = v19;
  v3 = v12(v11, v22, v20, 6, &v49, &v47, 3, &v45, &v37);
  v23 = (BSTR *)Block[0];
  if ( Block[0] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Block[0] + 4, 0xFFFFFFFF) == 1 && v23 )
    {
      if ( *v23 )
      {
        SysFreeString(*v23);
        *v23 = 0;
      }
      v24 = v23[1];
      if ( v24 )
      {
        operator delete(v24);
        v23[1] = 0;
      }
      operator delete(v23);
    }
    Block[0] = 0;
  }
  _variant_t::~_variant_t((_variant_t *)v51);
  _variant_t::~_variant_t((_variant_t *)&v43);
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  DmDisableTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", a1, L"Wsc Startup event listener created by enrollment client");
  if ( v3 < 0 )
  {
LABEL_38:
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogWscStartupAlertScheduleSetupFail(Logger, v3);
  }
  if ( (_DWORD)v29 )
    CoUninitialize();
  v26 = psa;
  if ( psa && SafeArrayUnlock(psa) >= 0 )
    SafeArrayDestroy(v26);
  v27 = v33;
  if ( v33 && SafeArrayUnlock(v33) >= 0 )
    SafeArrayDestroy(v27);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v41);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v42);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v34);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v31);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v37);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v35);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v30);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v36);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v38);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800dadec  mov     rax, rsp
0x1800dadef  push    rbp
0x1800dadf0  push    rbx
0x1800dadf1  push    rsi
0x1800dadf2  push    rdi
0x1800dadf3  push    r14
0x1800dadf5  push    r15
0x1800dadf7  lea     rbp, [rax-368h]
0x1800dadfe  sub     rsp, 438h
0x1800dae05  movaps  xmmword ptr [rax-48h], xmm6
0x1800dae09  movaps  xmmword ptr [rax-58h], xmm7
0x1800dae0d  movaps  xmmword ptr [rax-68h], xmm8
0x1800dae12  movaps  xmmword ptr [rax-78h], xmm9
0x1800dae17  movaps  xmmword ptr [rax-88h], xmm10
0x1800dae1f  movaps  xmmword ptr [rax-98h], xmm11
0x1800dae27  mov     rax, cs:__security_cookie
0x1800dae2e  xor     rax, rsp
0x1800dae31  mov     [rbp+360h+var_A0], rax
0x1800dae38  mov     rsi, rcx
0x1800dae3b  xor     r15d, r15d
0x1800dae3e  mov     [rbp+360h+var_3A0], r15
0x1800dae42  mov     [rbp+360h+var_3B0], r15
0x1800dae46  mov     [rsp+460h+var_3E8], r15
0x1800dae4b  mov     [rbp+360h+var_3B8], r15
0x1800dae4f  mov     [rbp+360h+var_3A8], r15
0x1800dae53  mov     [rbp+360h+var_3E0], r15
0x1800dae57  mov     [rbp+360h+var_3C0], r15
0x1800dae5b  mov     [rbp+360h+var_380], r15
0x1800dae5f  mov     [rbp+360h+var_388], r15
0x1800dae63  lea     edx, [r15+8]
0x1800dae67  lea     rcx, [rbp+360h+var_3C8]
0x1800dae6b  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x1800dae70  xor     edx, edx
0x1800dae72  lea     rcx, [rbp+360h+psa]
0x1800dae76  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x1800dae7b  mov     dword ptr [rsp+460h+var_3F0], r15d
0x1800dae80  xorps   xmm0, xmm0
0x1800dae83  movups  [rbp+360h+var_2C8], xmm0
0x1800dae8a  mov     rax, cs:WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION
0x1800dae91  mov     [rbp+360h+var_398], rax
0x1800dae95  mov     r9, rsi
0x1800dae98  lea     r8, aSSCWscstartupa; "/s \"%s\" /c /WscStartupAlert"
0x1800dae9f  mov     edx, 104h; unsigned __int64
0x1800daea4  lea     rcx, [rbp+360h+var_2B0]; unsigned __int16 *
0x1800daeab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800daeb0  mov     edi, eax
0x1800daeb2  test    eax, eax
0x1800daeb4  js      loc_1800DB200
0x1800daeba  lea     rcx, [rsp+460h+var_3F0]; this
0x1800daebf  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800daec4  mov     edi, eax
0x1800daec6  test    eax, eax
0x1800daec8  js      loc_1800DB200
0x1800daece  mov     [rsp+460h+var_400], r15d
0x1800daed3  mov     [rsp+460h+var_408], r15d
0x1800daed8  mov     [rsp+460h+var_410], r15d
0x1800daedd  lea     r14d, [r15+1]
0x1800daee1  mov     [rsp+460h+var_418], r14d
0x1800daee6  mov     [rsp+460h+var_420], r15d
0x1800daeeb  lea     rax, aS1518; "S-1-5-18"
0x1800daef2  mov     [rsp+460h+var_428], rax
0x1800daef7  lea     rax, [rbp+360h+var_2B0]
0x1800daefe  mov     [rsp+460h+var_430], rax
0x1800daf03  lea     rax, Src; "%windir%\\system32\\deviceenroller.exe"
0x1800daf0a  mov     [rsp+460h+var_438], rax
0x1800daf0f  mov     [rsp+460h+var_440], rsi
0x1800daf14  lea     r9, [rbp+360h+var_3B8]
0x1800daf18  lea     r8, [rsp+460h+var_3E8]
0x1800daf1d  lea     rdx, [rbp+360h+var_3B0]
0x1800daf21  lea     rcx, [rbp+360h+var_3A0]
0x1800daf25  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x1800daf2a  mov     edi, eax
0x1800daf2c  test    eax, eax
0x1800daf2e  js      loc_1800DB200
0x1800daf34  mov     rcx, [rsp+460h+var_3E8]
0x1800daf39  mov     rax, [rcx]
0x1800daf3c  lea     rdx, [rbp+360h+var_3E0]
0x1800daf40  mov     rax, [rax+78h]
0x1800daf44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daf49  mov     edi, eax
0x1800daf4b  test    eax, eax
0x1800daf4d  js      loc_1800DB200
0x1800daf53  mov     rbx, [rbp+360h+var_3E0]
0x1800daf57  mov     rax, [rbx]
0x1800daf5a  mov     rdi, [rax+40h]
0x1800daf5e  lea     rdx, aLocalsystem; "LocalSystem"
0x1800daf65  lea     rcx, [rbp+360h+Block]; this
0x1800daf69  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800daf6e  mov     rcx, [rax]
0x1800daf71  test    rcx, rcx
0x1800daf74  jz      short loc_1800DAF7B
0x1800daf76  mov     rdx, [rcx]
0x1800daf79  jmp     short loc_1800DAF7E
0x1800daf7b  mov     rdx, r15
0x1800daf7e  mov     rcx, rbx
0x1800daf81  mov     rax, rdi
0x1800daf84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daf89  mov     edi, eax
0x1800daf8b  mov     rbx, [rbp+360h+Block]
0x1800daf8f  test    rbx, rbx
0x1800daf92  jz      short loc_1800DAFDC
0x1800daf94  or      eax, 0FFFFFFFFh
0x1800daf97  lock xadd [rbx+10h], eax
0x1800daf9c  cmp     eax, r14d
0x1800daf9f  jnz     short loc_1800DAFDC
0x1800dafa1  test    rbx, rbx
0x1800dafa4  jz      short loc_1800DAFDC
0x1800dafa6  mov     rcx, [rbx]; bstrString
0x1800dafa9  test    rcx, rcx
0x1800dafac  jz      short loc_1800DAFBD
0x1800dafae  call    cs:__imp_SysFreeString
0x1800dafb5  nop     dword ptr [rax+rax+00h]
0x1800dafba  mov     [rbx], r15
0x1800dafbd  mov     rcx, [rbx+8]; Block
0x1800dafc1  test    rcx, rcx
0x1800dafc4  jz      short loc_1800DAFCF
0x1800dafc6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dafcb  mov     [rbx+8], r15
0x1800dafcf  mov     edx, 18h
0x1800dafd4  mov     rcx, rbx; Block
0x1800dafd7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dafdc  test    edi, edi
0x1800dafde  js      loc_1800DB200
0x1800dafe4  mov     rcx, [rbp+360h+var_3E0]
0x1800dafe8  mov     rax, [rcx]
0x1800dafeb  mov     edx, r14d
0x1800dafee  mov     rax, [rax+90h]
0x1800daff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daffa  mov     edi, eax
0x1800daffc  test    eax, eax
0x1800daffe  js      loc_1800DB200
0x1800db004  mov     rcx, [rbp+360h+var_3B8]
0x1800db008  mov     rax, [rcx]
0x1800db00b  or      edx, 0FFFFFFFFh
0x1800db00e  mov     rax, [rax+0D0h]
0x1800db015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db01a  mov     edi, eax
0x1800db01c  test    eax, eax
0x1800db01e  js      loc_1800DB200
0x1800db024  mov     rcx, [rsp+460h+var_3E8]
0x1800db029  mov     rax, [rcx]
0x1800db02c  lea     rdx, [rbp+360h+var_3C0]
0x1800db030  mov     rax, [rax+48h]
0x1800db034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db039  mov     edi, eax
0x1800db03b  test    eax, eax
0x1800db03d  js      loc_1800DB200
0x1800db043  mov     ebx, r15d
0x1800db046  movsxd  rax, ebx
0x1800db049  cmp     rax, 8
0x1800db04d  jnb     short loc_1800DB070
0x1800db04f  lea     r8, [rbp+360h+var_398]
0x1800db053  add     r8, rax
0x1800db056  mov     edx, ebx
0x1800db058  lea     rcx, [rbp+360h+var_3C8]
0x1800db05c  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x1800db061  mov     edi, eax
0x1800db063  test    eax, eax
0x1800db065  js      loc_1800DB200
0x1800db06b  add     ebx, r14d
0x1800db06e  jmp     short loc_1800DB046
0x1800db070  lea     rdx, [rbp+360h+var_3C8]
0x1800db074  mov     rcx, [rbp+360h+var_3C0]
0x1800db078  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x1800db07d  mov     edi, eax
0x1800db07f  test    eax, eax
0x1800db081  js      loc_1800DB200
0x1800db087  mov     rbx, [rbp+360h+var_3B0]
0x1800db08b  mov     rax, [rbx]
0x1800db08e  mov     r14, [rax+88h]
0x1800db095  lea     rcx, [rbp+360h+pvarg]; pvarg
0x1800db099  call    cs:__imp_VariantInit
0x1800db0a0  nop     dword ptr [rax+rax+00h]
0x1800db0a5  movups  xmm6, xmmword ptr [rbp+360h+pvarg]
0x1800db0a9  movsd   xmm7, qword ptr [rbp+360h+pvarg+10h]
0x1800db0ae  lea     rcx, [rbp+360h+var_378]; pvarg
0x1800db0b2  call    cs:__imp_VariantInit
0x1800db0b9  nop     dword ptr [rax+rax+00h]
0x1800db0be  movups  xmm8, xmmword ptr [rbp+360h+var_378]
0x1800db0c3  movsd   xmm9, qword ptr [rbp+360h+var_378+10h]
0x1800db0c9  lea     rdx, aS1518; "S-1-5-18"
0x1800db0d0  lea     rcx, [rbp+360h+var_2E0]; this
0x1800db0d7  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x1800db0dc  movups  xmm10, xmmword ptr [rax]
0x1800db0e0  movsd   xmm11, qword ptr [rax+10h]
0x1800db0e6  mov     rdi, [rsp+460h+var_3E8]
0x1800db0eb  lea     rdx, aWscStartupEven; "Wsc Startup event listener created by e"...
0x1800db0f2  lea     rcx, [rbp+360h+Block]; this
0x1800db0f6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800db0fb  mov     rdx, [rax]
0x1800db0fe  test    rdx, rdx
0x1800db101  jz      short loc_1800DB108
0x1800db103  mov     rdx, [rdx]
0x1800db106  jmp     short loc_1800DB10B
0x1800db108  mov     rdx, r15
0x1800db10b  movaps  [rbp+360h+var_340], xmm6
0x1800db10f  movsd   [rbp+360h+var_330], xmm7
0x1800db114  movaps  [rbp+360h+var_320], xmm8
0x1800db119  movsd   [rbp+360h+var_310], xmm9
0x1800db11f  movaps  [rbp+360h+var_300], xmm10
0x1800db124  movsd   [rbp+360h+var_2F0], xmm11
0x1800db12a  lea     rax, [rbp+360h+var_3A8]
0x1800db12e  mov     qword ptr [rsp+460h+var_420], rax
0x1800db133  lea     rax, [rbp+360h+var_340]
0x1800db137  mov     [rsp+460h+var_428], rax
0x1800db13c  mov     dword ptr [rsp+460h+var_430], 3
0x1800db144  lea     rax, [rbp+360h+var_320]
0x1800db148  mov     [rsp+460h+var_438], rax
0x1800db14d  lea     rax, [rbp+360h+var_300]
0x1800db151  mov     [rsp+460h+var_440], rax
0x1800db156  mov     r9d, 6
0x1800db15c  mov     r8, rdi
0x1800db15f  mov     rcx, rbx
0x1800db162  mov     rax, r14
0x1800db165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db16a  mov     edi, eax
0x1800db16c  mov     rbx, [rbp+360h+Block]
0x1800db170  test    rbx, rbx
0x1800db173  jz      short loc_1800DB1C1
0x1800db175  or      eax, 0FFFFFFFFh
0x1800db178  lock xadd [rbx+10h], eax
0x1800db17d  cmp     eax, 1
0x1800db180  jnz     short loc_1800DB1BD
0x1800db182  test    rbx, rbx
0x1800db185  jz      short loc_1800DB1BD
0x1800db187  mov     rcx, [rbx]; bstrString
0x1800db18a  test    rcx, rcx
0x1800db18d  jz      short loc_1800DB19E
0x1800db18f  call    cs:__imp_SysFreeString
0x1800db196  nop     dword ptr [rax+rax+00h]
0x1800db19b  mov     [rbx], r15
0x1800db19e  mov     rcx, [rbx+8]; Block
0x1800db1a2  test    rcx, rcx
0x1800db1a5  jz      short loc_1800DB1B0
0x1800db1a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db1ac  mov     [rbx+8], r15
0x1800db1b0  mov     edx, 18h
0x1800db1b5  mov     rcx, rbx; Block
0x1800db1b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db1bd  mov     [rbp+360h+Block], r15
0x1800db1c1  lea     rcx, [rbp+360h+var_2E0]; this
0x1800db1c8  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800db1cd  lea     rcx, [rbp+360h+var_378]; this
0x1800db1d1  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800db1d6  lea     rcx, [rbp+360h+pvarg]; this
0x1800db1da  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800db1df  lea     r8, aWscStartupEven; "Wsc Startup event listener created by e"...
0x1800db1e6  mov     rdx, rsi
0x1800db1e9  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x1800db1f0  call    cs:__imp_?DmDisableTask@@YAJPEBG00@Z; DmDisableTask(ushort const *,ushort const *,ushort const *)
0x1800db1f7  nop     dword ptr [rax+rax+00h]
0x1800db1fc  test    edi, edi
0x1800db1fe  jns     short loc_1800DB20F
0x1800db200  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800db205  mov     edx, edi; int
0x1800db207  mov     rcx, rax; this
0x1800db20a  call    ?LogWscStartupAlertScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogWscStartupAlertScheduleSetupFail(long)
0x1800db20f  cmp     dword ptr [rsp+460h+var_3F0], r15d
0x1800db214  jz      short loc_1800DB222
0x1800db216  call    cs:__imp_CoUninitialize
0x1800db21d  nop     dword ptr [rax+rax+00h]
0x1800db222  mov     rbx, [rbp+360h+psa]
0x1800db226  test    rbx, rbx
0x1800db229  jz      short loc_1800DB24D
0x1800db22b  mov     rcx, rbx; psa
0x1800db22e  call    cs:__imp_SafeArrayUnlock
0x1800db235  nop     dword ptr [rax+rax+00h]
0x1800db23a  test    eax, eax
0x1800db23c  js      short loc_1800DB24D
0x1800db23e  mov     rcx, rbx; psa
0x1800db241  call    cs:__imp_SafeArrayDestroy
0x1800db248  nop     dword ptr [rax+rax+00h]
0x1800db24d  mov     rbx, [rbp+360h+var_3C8]
0x1800db251  test    rbx, rbx
0x1800db254  jz      short loc_1800DB278
0x1800db256  mov     rcx, rbx; psa
0x1800db259  call    cs:__imp_SafeArrayUnlock
0x1800db260  nop     dword ptr [rax+rax+00h]
0x1800db265  test    eax, eax
0x1800db267  js      short loc_1800DB278
0x1800db269  mov     rcx, rbx; psa
0x1800db26c  call    cs:__imp_SafeArrayDestroy
0x1800db273  nop     dword ptr [rax+rax+00h]
0x1800db278  lea     rcx, [rbp+360h+var_388]
0x1800db27c  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800db281  lea     rcx, [rbp+360h+var_380]
0x1800db285  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800db28a  lea     rcx, [rbp+360h+var_3C0]
0x1800db28e  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800db293  lea     rcx, [rbp+360h+var_3E0]
0x1800db297  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800db29c  lea     rcx, [rbp+360h+var_3A8]
0x1800db2a0  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800db2a5  lea     rcx, [rbp+360h+var_3B8]
0x1800db2a9  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800db2ae  lea     rcx, [rsp+460h+var_3E8]
0x1800db2b3  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800db2b8  lea     rcx, [rbp+360h+var_3B0]
0x1800db2bc  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x1800db2c1  lea     rcx, [rbp+360h+var_3A0]
  ... truncated ...
```
