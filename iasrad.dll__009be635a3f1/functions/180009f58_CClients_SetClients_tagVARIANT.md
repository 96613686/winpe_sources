# CClients::SetClients(tagVARIANT *)

- ea: `0x180009f58`
- end: `0x18000a3f2`
- name: `?SetClients@CClients@@QEAAJPEAUtagVARIANT@@@Z`
- size: `1178`
- prototype: `__int64 __fastcall(CClients *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d1c0`

## callees

- `0x180009b10`
- `0x180009b24`
- `0x180009bd8`
- `0x180009c10`
- `0x180009c3c`
- `0x180009d2c`
- `0x180009f58`
- `0x18000a3f8`
- `0x18000a430`
- `0x18000a4d8`
- `0x18000a52c`
- `0x18001d31c`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscspn` at `0x18000a26a`
- `msvcrt!wcscspn` at `0x18000a26a`
- `iassvcs!IASRequestThread` at `0x18000a3a7`
- `iassvcs!IASRequestThread` at `0x18000a3a7`
- `iassvcs!IASReportLicenseViolation` at `0x18000a066`
- `iassvcs!IASReportLicenseViolation` at `0x18000a32d`
- `iassvcs!IASReportLicenseViolation` at `0x18000a066`
- `iassvcs!IASReportLicenseViolation` at `0x18000a32d`
- `KERNEL32!ResetEvent` at `0x18000a39e`
- `KERNEL32!ResetEvent` at `0x18000a39e`
- `OLEAUT32!__imp_VariantInit` at `0x18000a167`
- `OLEAUT32!__imp_VariantInit` at `0x18000a167`
- `OLEAUT32!__imp_VariantClear` at `0x18000a198`
- `OLEAUT32!__imp_VariantClear` at `0x18000a279`
- `OLEAUT32!__imp_VariantClear` at `0x18000a367`
- `OLEAUT32!__imp_VariantClear` at `0x18000a3bd`
- `OLEAUT32!__imp_VariantClear` at `0x18000a198`
- `OLEAUT32!__imp_VariantClear` at `0x18000a279`
- `OLEAUT32!__imp_VariantClear` at `0x18000a367`
- `OLEAUT32!__imp_VariantClear` at `0x18000a3bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a0d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a355`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a0d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a355`

## string_xrefs

- `0x18000a030`: `License Violation: %ld RADIUS Clients are configured, but only %lu are allowed for this product type.`

## pseudocode

```c
__int64 __fastcall CClients::SetClients(HANDLE *this, struct tagVARIANT *a2)
{
  __int64 result; // rax
  int v5; // ebx
  __int64 v6; // rdx
  PVOID v7; // rcx
  LPVOID v8; // rax
  __int64 v9; // rax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rax
  unsigned int v11; // esi
  const wchar_t *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  _QWORD *v15; // rbx
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  signed int v21; // [rsp+A8h] [rbp+38h] BYREF
  int v22; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+48h] BYREF

  if ( !a2 || a2->vt != 9 || !a2->llVal )
    return 2147942487LL;
  result = CClients::StopResolvingClients((CClients *)this);
  if ( (int)result < 0 )
    return result;
  ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(&v19);
  v5 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))a2->llVal)(
         a2->llVal,
         &GUID_56bc53e2_96db_11d1_bf3f_000000000000,
         &v19);
  if ( v5 < 0 )
    goto LABEL_6;
  v21 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, signed int *))(*(_QWORD *)v19 + 56LL))(v19, &v21);
  if ( v5 < 0 )
    goto LABEL_6;
  v6 = v21;
  if ( !v21 )
  {
    CClients::DeleteObjects((CClients *)this);
    v5 = 0;
LABEL_6:
    ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v19);
    return (unsigned int)v5;
  }
  if ( v21 > *((_DWORD *)this + 20) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("License Violation: %ld RADIUS Clients are configured, but only %lu are allowed for this product type.");
      WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_d3f61b2c9f4a322e61c9452f1dbab538_Traceguids);
    }
    IASReportLicenseViolation(v7, v6);
    v5 = -2147023501;
    goto LABEL_6;
  }
  if ( (unsigned __int64)v21 > 0x1FFFFFFF )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Integer overflow with %ld RADIUS Clients.");
      WPP_SF_sl(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    v5 = -2147024362;
    goto LABEL_6;
  }
  v8 = CoTaskMemAlloc(8LL * v21);
  this[6] = v8;
  if ( !v8 )
  {
LABEL_49:
    v5 = -2147024882;
    goto LABEL_6;
  }
  ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(v17);
  v9 = ATL::CComPtrBase<IUnknown>::operator->(&v19);
  v5 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v9 + 112LL))(v9, v17);
  if ( v5 < 0 )
  {
LABEL_24:
    ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(v17);
    goto LABEL_6;
  }
  ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(&v16);
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))ATL::CComPtrBase<IUnknown>::operator->(v17);
  v5 = (**v10)(v10, &GUID_00020404_0000_0000_c000_000000000046, &v16);
  if ( v5 < 0 )
  {
LABEL_26:
    ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v16);
    goto LABEL_24;
  }
  VariantInit(&pvarg);
  v22 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v16 + 24LL))(v16, 1, &pvarg, &v22);
  if ( v5 < 0 )
  {
LABEL_28:
    VariantClear(&pvarg);
    goto LABEL_26;
  }
  v11 = 0;
  while ( v22 && v11 < v21 )
  {
    ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(&v23);
    v5 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
           pvarg.llVal,
           &GUID_56bc53de_96db_11d1_bf3f_000000000000,
           &v23);
    if ( v5 < 0 )
      goto LABEL_46;
    v18 = 0;
    v5 = (*(__int64 (__fastcall **)(HANDLE, _QWORD, GUID *, __int64 *))(*(_QWORD *)this[5] + 24LL))(
           this[5],
           0,
           &GUID_6bc096da_0ce6_11d1_baae_00c04fc2e20d,
           &v18);
    if ( v5 < 0 )
      goto LABEL_46;
    *((_QWORD *)this[6] + v11++) = v18;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 80LL))(v18, v23);
    if ( v5 < 0 )
      goto LABEL_46;
    if ( !*((_BYTE *)this + 84) )
    {
      v12 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 64LL))(v18);
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      if ( wcscspn(v12, L"/") != v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 56LL))(v18);
          WppDbgPrint("License Violation: RADIUS Client '%S' uses sub-net syntax, which is not allowed for this product type.");
          v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 56LL))(v18);
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)&WPP_d3f61b2c9f4a322e61c9452f1dbab538_Traceguids,
            (unsigned int)"NPSRAD",
            v14);
        }
        ((void (*)(void))IASReportLicenseViolation)();
        v5 = -2147023501;
LABEL_46:
        ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v23);
        CClients::FreeClientArray((CClients *)this, v11);
        goto LABEL_28;
      }
    }
    VariantClear(&pvarg);
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v16 + 24LL))(
           v16,
           1,
           &pvarg,
           &v22);
    if ( v5 < 0 )
      goto LABEL_46;
    ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v23);
  }
  v15 = CoTaskMemAlloc(0x18u);
  if ( !v15 )
  {
    VariantClear(&pvarg);
    ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v16);
    ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(v17);
    goto LABEL_49;
  }
  *v15 = CClients::CallbackRoutine;
  v15[1] = this;
  *((_DWORD *)v15 + 4) = v11;
  ResetEvent(this[9]);
  if ( !(unsigned int)IASRequestThread(v15) )
    CClients::CallbackRoutine((struct IAS_CALLBACK *)v15);
  VariantClear(&pvarg);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v16);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(v17);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v19);
  return 0;
}

```

## disassembly

```asm
0x180009f58  push    rbp
0x180009f5a  push    rbx
0x180009f5b  push    rsi
0x180009f5c  push    rdi
0x180009f5d  push    r14
0x180009f5f  mov     rbp, rsp
0x180009f62  sub     rsp, 70h
0x180009f66  mov     rbx, rdx
0x180009f69  mov     rdi, rcx
0x180009f6c  xor     r14d, r14d
0x180009f6f  test    rdx, rdx
0x180009f72  jz      loc_18000A3E2
0x180009f78  cmp     word ptr [rdx], 9
0x180009f7c  jnz     loc_18000A3E2
0x180009f82  cmp     [rdx+8], r14
0x180009f86  jz      loc_18000A3E2
0x180009f8c  call    ?StopResolvingClients@CClients@@AEAAJXZ; CClients::StopResolvingClients(void)
0x180009f91  test    eax, eax
0x180009f93  js      loc_18000A3E7
0x180009f99  lea     rcx, [rbp+var_28]; void *
0x180009f9d  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x180009fa2  mov     rcx, [rbx+8]
0x180009fa6  mov     rax, [rcx]
0x180009fa9  lea     r8, [rbp+var_28]
0x180009fad  lea     rdx, _GUID_56bc53e2_96db_11d1_bf3f_000000000000
0x180009fb4  mov     rax, [rax]
0x180009fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fbc  mov     ebx, eax
0x180009fbe  test    eax, eax
0x180009fc0  jns     short loc_180009FD2
0x180009fc2  lea     rcx, [rbp+var_28]
0x180009fc6  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180009fcb  mov     eax, ebx
0x180009fcd  jmp     loc_18000A3E7
0x180009fd2  mov     [rbp+arg_8], r14d
0x180009fd6  mov     rcx, [rbp+var_28]
0x180009fda  mov     rax, [rcx]
0x180009fdd  lea     rdx, [rbp+arg_8]
0x180009fe1  mov     rax, [rax+38h]
0x180009fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fea  mov     ebx, eax
0x180009fec  test    eax, eax
0x180009fee  js      short loc_180009FC2
0x180009ff0  movsxd  rdx, [rbp+arg_8]
0x180009ff4  test    edx, edx
0x180009ff6  jnz     short loc_18000A005
0x180009ff8  mov     rcx, rdi; this
0x180009ffb  call    ?DeleteObjects@CClients@@QEAAXXZ; CClients::DeleteObjects(void)
0x18000a000  mov     ebx, r14d
0x18000a003  jmp     short loc_180009FC2
0x18000a005  mov     r8d, [rdi+50h]
0x18000a009  cmp     edx, r8d
0x18000a00c  jle     short loc_18000A076
0x18000a00e  lea     rax, WPP_GLOBAL_Control
0x18000a015  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a01c  cmp     rcx, rax
0x18000a01f  jz      short loc_18000A066
0x18000a021  cmp     byte ptr [rcx+19h], 2
0x18000a025  jb      short loc_18000A066
0x18000a027  test    dword ptr [rcx+1Ch], 100h
0x18000a02e  jz      short loc_18000A066
0x18000a030  lea     rcx, aLicenseViolati_1; "License Violation: %ld RADIUS Clients a"...
0x18000a037  call    WppDbgPrint
0x18000a03c  mov     edx, 0Ah
0x18000a041  mov     eax, [rdi+50h]
0x18000a044  mov     [rsp+70h+var_48], eax
0x18000a048  mov     eax, [rbp+arg_8]
0x18000a04b  mov     dword ptr [rsp+70h+var_50], eax
0x18000a04f  lea     r8, WPP_d3f61b2c9f4a322e61c9452f1dbab538_Traceguids
0x18000a056  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a05d  mov     rcx, [rcx+10h]
0x18000a061  call    WPP_SF_sdd
0x18000a066  call    cs:__imp_IASReportLicenseViolation
0x18000a06c  mov     ebx, 80070573h
0x18000a071  jmp     loc_180009FC2
0x18000a076  mov     rcx, rdx
0x18000a079  cmp     rdx, 1FFFFFFFh
0x18000a080  jbe     short loc_18000A0D1
0x18000a082  lea     rax, WPP_GLOBAL_Control
0x18000a089  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a090  cmp     rcx, rax
0x18000a093  jz      short loc_18000A0C7
0x18000a095  cmp     byte ptr [rcx+19h], 2
0x18000a099  jb      short loc_18000A0C7
0x18000a09b  test    dword ptr [rcx+1Ch], 100h
0x18000a0a2  jz      short loc_18000A0C7
0x18000a0a4  lea     rcx, aIntegerOverflo; "Integer overflow with %ld RADIUS Client"...
0x18000a0ab  call    WppDbgPrint
0x18000a0b0  mov     eax, [rbp+arg_8]
0x18000a0b3  mov     dword ptr [rsp+70h+var_50], eax
0x18000a0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0be  mov     rcx, [rcx+10h]
0x18000a0c2  call    WPP_SF_sl
0x18000a0c7  mov     ebx, 80070216h
0x18000a0cc  jmp     loc_180009FC2
0x18000a0d1  shl     rcx, 3; cb
0x18000a0d5  call    cs:__imp_CoTaskMemAlloc
0x18000a0db  mov     [rdi+30h], rax
0x18000a0df  test    rax, rax
0x18000a0e2  jz      loc_18000A37F
0x18000a0e8  lea     rcx, [rbp+var_38]; void *
0x18000a0ec  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x18000a0f1  lea     rcx, [rbp+var_28]
0x18000a0f5  call    ??C?$CComPtrBase@UIUnknown@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIUnknown@@@1@XZ; ATL::CComPtrBase<IUnknown>::operator->(void)
0x18000a0fa  mov     r8, rax
0x18000a0fd  mov     rcx, [rax]
0x18000a100  mov     rax, [rcx+70h]
0x18000a104  lea     rdx, [rbp+var_38]
0x18000a108  mov     rcx, r8
0x18000a10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a110  mov     ebx, eax
0x18000a112  test    eax, eax
0x18000a114  jns     short loc_18000A124
0x18000a116  lea     rcx, [rbp+var_38]
0x18000a11a  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000a11f  jmp     loc_180009FC2
0x18000a124  lea     rcx, [rbp+var_40]; void *
0x18000a128  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x18000a12d  lea     rcx, [rbp+var_38]
0x18000a131  call    ??C?$CComPtrBase@UIUnknown@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIUnknown@@@1@XZ; ATL::CComPtrBase<IUnknown>::operator->(void)
0x18000a136  mov     r9, rax
0x18000a139  mov     rcx, [rax]
0x18000a13c  mov     rax, [rcx]
0x18000a13f  lea     r8, [rbp+var_40]
0x18000a143  lea     rdx, _GUID_00020404_0000_0000_c000_000000000046
0x18000a14a  mov     rcx, r9
0x18000a14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a152  mov     ebx, eax
0x18000a154  test    eax, eax
0x18000a156  jns     short loc_18000A163
0x18000a158  lea     rcx, [rbp+var_40]
0x18000a15c  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000a161  jmp     short loc_18000A116
0x18000a163  lea     rcx, [rbp+pvarg]; pvarg
0x18000a167  call    cs:__imp_VariantInit
0x18000a16d  mov     [rbp+arg_10], r14d
0x18000a171  mov     rcx, [rbp+var_40]
0x18000a175  mov     rax, [rcx]
0x18000a178  lea     r9, [rbp+arg_10]
0x18000a17c  lea     r8, [rbp+pvarg]
0x18000a180  mov     edx, 1
0x18000a185  mov     rax, [rax+18h]
0x18000a189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a18e  mov     ebx, eax
0x18000a190  test    eax, eax
0x18000a192  jns     short loc_18000A1A0
0x18000a194  lea     rcx, [rbp+pvarg]; pvarg
0x18000a198  call    cs:__imp_VariantClear
0x18000a19e  jmp     short loc_18000A158
0x18000a1a0  mov     esi, r14d
0x18000a1a3  cmp     [rbp+arg_10], r14d
0x18000a1a7  jbe     loc_18000A350
0x18000a1ad  cmp     esi, [rbp+arg_8]
0x18000a1b0  jnb     loc_18000A350
0x18000a1b6  lea     rcx, [rbp+arg_18]; void *
0x18000a1ba  call    ??0?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::CComPtr<IClassFactory>(void)
0x18000a1bf  mov     rcx, qword ptr [rbp+pvarg+8]
0x18000a1c3  mov     rax, [rcx]
0x18000a1c6  lea     r8, [rbp+arg_18]
0x18000a1ca  lea     rdx, _GUID_56bc53de_96db_11d1_bf3f_000000000000
0x18000a1d1  mov     rax, [rax]
0x18000a1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d9  mov     ebx, eax
0x18000a1db  test    eax, eax
0x18000a1dd  js      loc_18000A338
0x18000a1e3  mov     [rbp+var_30], r14
0x18000a1e7  mov     rcx, [rdi+28h]
0x18000a1eb  mov     rax, [rcx]
0x18000a1ee  lea     r9, [rbp+var_30]
0x18000a1f2  lea     r8, _GUID_6bc096da_0ce6_11d1_baae_00c04fc2e20d
0x18000a1f9  xor     edx, edx
0x18000a1fb  mov     rax, [rax+18h]
0x18000a1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a204  mov     ebx, eax
0x18000a206  test    eax, eax
0x18000a208  js      loc_18000A338
0x18000a20e  mov     edx, esi
0x18000a210  mov     rcx, [rdi+30h]
0x18000a214  mov     rax, [rbp+var_30]
0x18000a218  mov     [rcx+rdx*8], rax
0x18000a21c  inc     esi
0x18000a21e  mov     rcx, [rbp+var_30]
0x18000a222  mov     rax, [rcx]
0x18000a225  mov     rdx, [rbp+arg_18]
0x18000a229  mov     rax, [rax+50h]
0x18000a22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a232  mov     ebx, eax
0x18000a234  test    eax, eax
0x18000a236  js      loc_18000A338
0x18000a23c  cmp     [rdi+54h], r14b
0x18000a240  jnz     short loc_18000A275
0x18000a242  mov     rcx, [rbp+var_30]
0x18000a246  mov     rax, [rcx]
0x18000a249  mov     rax, [rax+40h]
0x18000a24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a252  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a256  inc     rbx
0x18000a259  cmp     [rax+rbx*2], r14w
0x18000a25e  jnz     short loc_18000A256
0x18000a260  lea     rdx, asc_180034878; "/"
0x18000a267  mov     rcx, rax; String
0x18000a26a  call    cs:__imp_wcscspn
0x18000a270  cmp     rax, rbx
0x18000a273  jnz     short loc_18000A2B4
0x18000a275  lea     rcx, [rbp+pvarg]; pvarg
0x18000a279  call    cs:__imp_VariantClear
0x18000a27f  mov     rcx, [rbp+var_40]
0x18000a283  mov     rax, [rcx]
0x18000a286  lea     r9, [rbp+arg_10]
0x18000a28a  lea     r8, [rbp+pvarg]
0x18000a28e  mov     edx, 1
0x18000a293  mov     rax, [rax+18h]
0x18000a297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29c  mov     ebx, eax
0x18000a29e  lea     rcx, [rbp+arg_18]
0x18000a2a2  test    eax, eax
0x18000a2a4  js      loc_18000A33C
0x18000a2aa  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000a2af  jmp     loc_18000A1A3
0x18000a2b4  lea     rax, WPP_GLOBAL_Control
0x18000a2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2c2  cmp     rcx, rax
0x18000a2c5  jz      short loc_18000A32D
0x18000a2c7  cmp     byte ptr [rcx+19h], 2
0x18000a2cb  jb      short loc_18000A32D
0x18000a2cd  test    dword ptr [rcx+1Ch], 100h
0x18000a2d4  jz      short loc_18000A32D
0x18000a2d6  mov     rcx, [rbp+var_30]
0x18000a2da  mov     rax, [rcx]
0x18000a2dd  mov     rax, [rax+38h]
0x18000a2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2e6  mov     rdx, rax
0x18000a2e9  lea     rcx, aLicenseViolati; "License Violation: RADIUS Client '%S' u"...
0x18000a2f0  call    WppDbgPrint
0x18000a2f5  mov     rcx, [rbp+var_30]
0x18000a2f9  mov     rax, [rcx]
0x18000a2fc  mov     rax, [rax+38h]
0x18000a300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a305  mov     edx, 0Ch
0x18000a30a  mov     [rsp+70h+var_50], rax
0x18000a30f  lea     r9, aNpsrad; "NPSRAD"
0x18000a316  lea     r8, WPP_d3f61b2c9f4a322e61c9452f1dbab538_Traceguids
0x18000a31d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a324  mov     rcx, [rcx+10h]
0x18000a328  call    WPP_SF_sS
0x18000a32d  call    cs:__imp_IASReportLicenseViolation
0x18000a333  mov     ebx, 80070573h
0x18000a338  lea     rcx, [rbp+arg_18]
0x18000a33c  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000a341  mov     edx, esi; unsigned int
0x18000a343  mov     rcx, rdi; this
0x18000a346  call    ?FreeClientArray@CClients@@AEAAXK@Z; CClients::FreeClientArray(ulong)
0x18000a34b  jmp     loc_18000A194
0x18000a350  mov     ecx, 18h; cb
0x18000a355  call    cs:__imp_CoTaskMemAlloc
0x18000a35b  mov     rbx, rax
0x18000a35e  test    rax, rax
0x18000a361  jnz     short loc_18000A389
0x18000a363  lea     rcx, [rbp+pvarg]; pvarg
0x18000a367  call    cs:__imp_VariantClear
0x18000a36d  lea     rcx, [rbp+var_40]
0x18000a371  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000a376  lea     rcx, [rbp+var_38]
0x18000a37a  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000a37f  mov     ebx, 8007000Eh
0x18000a384  jmp     loc_180009FC2
0x18000a389  lea     rax, ?CallbackRoutine@CClients@@CAXPEAUIAS_CALLBACK@@@Z; CClients::CallbackRoutine(IAS_CALLBACK *)
0x18000a390  mov     [rbx], rax
0x18000a393  mov     [rbx+8], rdi
0x18000a397  mov     [rbx+10h], esi
0x18000a39a  mov     rcx, [rdi+48h]; hEvent
0x18000a39e  call    cs:__imp_ResetEvent
0x18000a3a4  mov     rcx, rbx
0x18000a3a7  call    cs:__imp_IASRequestThread
0x18000a3ad  test    eax, eax
0x18000a3af  jnz     short loc_18000A3B9
0x18000a3b1  mov     rcx, rbx; struct IAS_CALLBACK *
0x18000a3b4  call    ?CallbackRoutine@CClients@@CAXPEAUIAS_CALLBACK@@@Z; CClients::CallbackRoutine(IAS_CALLBACK *)
0x18000a3b9  lea     rcx, [rbp+pvarg]; pvarg
0x18000a3bd  call    cs:__imp_VariantClear
0x18000a3c3  lea     rcx, [rbp+var_40]
0x18000a3c7  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000a3cc  lea     rcx, [rbp+var_38]
0x18000a3d0  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000a3d5  lea     rcx, [rbp+var_28]
0x18000a3d9  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000a3de  xor     eax, eax
0x18000a3e0  jmp     short loc_18000A3E7
0x18000a3e2  mov     eax, 80070057h
0x18000a3e7  add     rsp, 70h
0x18000a3eb  pop     r14
0x18000a3ed  pop     rdi
0x18000a3ee  pop     rsi
0x18000a3ef  pop     rbx
0x18000a3f0  pop     rbp
0x18000a3f1  retn
```
