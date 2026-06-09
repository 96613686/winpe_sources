# CITransaction::EnlistKtm(void)

- ea: `0x18002847c`
- end: `0x180028a7c`
- name: `?EnlistKtm@CITransaction@@AEAAJXZ`
- size: `1536`
- prototype: `__int64 __fastcall(CITransaction *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800440e0`
- `0x180044170`

## callees

- `0x180003cf0`
- `0x1800104c0`
- `0x180011ac0`
- `0x18002847c`
- `0x180028d40`
- `0x180029434`
- `0x1800729ec`
- `0x18007f82c`
- `0x18007f8a0`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `ntdll!NtSetInformationTransaction` at `0x1800286b0`
- `ntdll!NtSetInformationTransaction` at `0x180028731`
- `ntdll!NtSetInformationTransaction` at `0x1800286b0`
- `ntdll!NtSetInformationTransaction` at `0x180028731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028789`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800285f2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800285f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002864a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002864a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028678`
- `ktmw32!RollbackTransactionAsync` at `0x1800289ef`
- `ktmw32!RollbackTransactionAsync` at `0x1800289ef`
- `ktmw32!OpenTransaction` at `0x1800284e3`
- `ktmw32!OpenTransaction` at `0x180028661`
- `ktmw32!OpenTransaction` at `0x1800284e3`
- `ktmw32!OpenTransaction` at `0x180028661`
- `ktmw32!PrivCreateTransaction` at `0x180028634`
- `ktmw32!PrivCreateTransaction` at `0x180028634`

## string_xrefs

- `0x18002855b`: `com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp`
- `0x1800286ce`: `com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp`
- `0x180028882`: `com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp`
- `0x180028544`: `CITransaction::EnlistKtm - error from StartKtmRmService`
- `0x1800289d6`: `com\complus\dtc\dtc\msdtcprx\src\dtcprxtx.cpp`
- `0x18002876f`: `CITransaction::GetKtmHandle - error from GetPropagationTokenSize`
- `0x18002879c`: `CITransaction::EnlistKtm - can't allocate propagation token buffer`
- `0x1800287de`: `CITransaction::GetKtmHandle - error from GetPropagationToken`

## pseudocode

```c
int __fastcall CITransaction::EnlistKtm(CITransaction *this)
{
  GUID *v1; // r13
  HANDLE v3; // rax
  int result; // eax
  char *v5; // r15
  void *v6; // r12
  CIConnSink *v7; // rsi
  int started; // ebx
  const wchar_t *v9; // rax
  __int64 v10; // r9
  __int64 Transaction; // rax
  signed int LastError; // eax
  HANDLE v13; // rax
  bool v14; // zf
  int v15; // ebx
  const wchar_t *v16; // rax
  __int64 v17; // r9
  int v18; // eax
  unsigned int v19; // r9d
  char *v20; // rdx
  int v21; // ecx
  unsigned int v22; // r13d
  _DWORD *v23; // rax
  struct CSendReceive *Instance; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  void *v27; // rcx
  int cchWideChar[2]; // [rsp+28h] [rbp-B1h]
  unsigned int v29; // [rsp+50h] [rbp-89h] BYREF
  int v30; // [rsp+54h] [rbp-85h] BYREF
  unsigned int v31; // [rsp+58h] [rbp-81h] BYREF
  int *v32; // [rsp+60h] [rbp-79h] BYREF
  void *v33; // [rsp+68h] [rbp-71h] BYREF
  int v34; // [rsp+70h] [rbp-69h] BYREF
  struct _SECURITY_ATTRIBUTES *v35; // [rsp+78h] [rbp-61h] BYREF
  struct _GUID v36; // [rsp+80h] [rbp-59h] BYREF
  WCHAR WideCharStr[40]; // [rsp+90h] [rbp-49h] BYREF

  v33 = (void *)-1LL;
  v1 = (GUID *)((char *)this + 1112);
  v29 = 0;
  v34 = 0;
  v30 = 0;
  v32 = 0;
  v36 = GUID_NULL;
  v31 = 0;
  v3 = OpenTransaction(0x120037u, (LPGUID)((char *)this + 1112));
  *((_QWORD *)this + 128) = v3;
  if ( v3 != (HANDLE)-1LL )
    return 0;
  v35 = 0;
  result = CITransaction::GetTransactionSecurityAttributes(&v35);
  if ( !result )
  {
    v5 = (char *)this + 96;
    v6 = 0;
    v7 = 0;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 12) + 8LL))((char *)this + 96);
    started = StartKtmRmService();
    (**((void (__fastcall ***)(char *))this + 12))((char *)this + 96);
    if ( started < 0 )
    {
      v9 = L"CITransaction::EnlistKtm - error from StartKtmRmService";
      v10 = 3395;
LABEL_6:
      cchWideChar[0] = started;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp",
        v10,
        L"CITransaction::EnlistKtm",
        *(_QWORD *)cchWideChar,
        v9);
      goto LABEL_57;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))((char *)this + 96);
    started = CTmProxyCore::GetKtmRmTmHandle(*((CTmProxyCore **)this + 29), 1, &v33);
    (**(void (__fastcall ***)(char *))v5)((char *)this + 96);
    if ( started < 0 )
    {
      v9 = L"CITransaction::EnlistKtm - error from GetKtmRmTmHandle";
      v10 = 3404;
      goto LABEL_6;
    }
    WideCharStr[0] = 0;
    MultiByteToWideChar(0, 0, (LPCCH)this + 188, 40, WideCharStr, 40);
    v14 = *((_QWORD *)this + 128) == -1;
    WideCharStr[39] = 0;
    if ( v14 )
    {
      Transaction = PrivCreateTransaction(
                      v35,
                      v1,
                      0,
                      *((unsigned int *)this + 44),
                      *((_DWORD *)this + 45),
                      0,
                      WideCharStr);
      *((_QWORD *)this + 128) = Transaction;
      if ( Transaction != -1 )
      {
        v15 = NtSetInformationTransaction(Transaction, 4, &v33);
        if ( v15 )
        {
          v16 = L"CITransaction::EnlistKtm - error from NtSetInformationTransaction";
          v17 = 3468;
        }
        else
        {
          started = CITransaction::GetKtmCookie(this, &v36);
          if ( started < 0 )
          {
            v9 = L"error from GetKtmCookie";
            v10 = 3477;
            goto LABEL_6;
          }
          v15 = NtSetInformationTransaction(*((_QWORD *)this + 128), 5, &v36);
          if ( !v15 )
            goto LABEL_26;
          v16 = L"error from NtSetInformationTransaction - Setting TM Id!";
          v17 = 3491;
        }
        started = v15 | 0x10000000;
        cchWideChar[0] = started;
        TraceStringInline(
          15,
          1,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp",
          v17,
          L"CITransaction::EnlistKtm",
          *(_QWORD *)cchWideChar,
          v16);
LABEL_16:
        v14 = started == 0;
        goto LABEL_17;
      }
      LastError = GetLastError();
      started = LastError;
      if ( LastError != 6800 )
        goto LABEL_14;
      v13 = OpenTransaction(0x120037u, v1);
      *((_QWORD *)this + 128) = v13;
      if ( v13 == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        started = LastError;
LABEL_14:
        if ( LastError > 0 )
          started = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_16;
      }
    }
LABEL_26:
    v18 = (*(__int64 (__fastcall **)(CITransaction *, unsigned int *))(*(_QWORD *)this + 64LL))(this, &v29);
    started = v18;
    if ( v18 < 0 )
    {
      v19 = 3501;
      v20 = "CITransaction::GetKtmHandle - error from GetPropagationTokenSize";
LABEL_28:
      v21 = v18;
LABEL_56:
      TraceFile(v21, v20, "com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp", v19);
      goto LABEL_57;
    }
    v22 = v29 + 8;
    v23 = CoTaskMemAlloc(v29 + 8);
    v6 = v23;
    if ( !v23 )
    {
      v21 = -2147024882;
      v20 = "CITransaction::EnlistKtm - can't allocate propagation token buffer";
      v19 = 3510;
LABEL_55:
      started = v21;
      goto LABEL_56;
    }
    *v23 = v29;
    v18 = (*(__int64 (__fastcall **)(CITransaction *, _QWORD, _DWORD *, int *))(*(_QWORD *)this + 72LL))(
            this,
            v29,
            v23 + 1,
            &v34);
    started = v18;
    if ( v18 < 0 )
    {
      v19 = 3523;
      v20 = "CITransaction::GetKtmHandle - error from GetPropagationToken";
      goto LABEL_28;
    }
    Instance = CSendReceive::CreateInstance();
    v7 = Instance;
    if ( !Instance )
    {
      v21 = -2147024882;
      v20 = "CITransaction::EnlistKtm - can't allocate CSendReceive";
      v19 = 3533;
      goto LABEL_55;
    }
    if ( !(*(unsigned int (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance + 32LL))(Instance) )
    {
      CIConnSink::DeleteObject(v7);
      v21 = -2147024882;
      v20 = "CITransaction::GetKtmHandle - can't initialize CSendReceive";
      v7 = 0;
      v19 = 3542;
      goto LABEL_55;
    }
    (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v7 + 160LL))(v7);
    v25 = *((_QWORD *)this + 29);
    v26 = *(_QWORD *)(v25 + 3520);
    if ( !v26 )
    {
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcprxtx.cpp",
        3550,
        L"CITransaction::EnlistKtm",
        0,
        L"CITransaction::GetKtmHandle - m_pCTmProxyCore->m_pINameObjKtmRm is NULL, check KTMRM CIDs");
      started = -2147168217;
      goto LABEL_57;
    }
    v18 = (*(__int64 (__fastcall **)(CIConnSink *, _QWORD, __int64, __int64, int))(*(_QWORD *)v7 + 248LL))(
            v7,
            *(_QWORD *)(v25 + 3544),
            v26,
            1,
            4097);
    started = v18;
    if ( v18 < 0 )
    {
      v19 = 3563;
      v20 = "CITransaction::EnlistKtm - error from CSendReceive::Connect";
      goto LABEL_28;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))((char *)this + 96);
    started = (*(__int64 (__fastcall **)(CIConnSink *, __int64, _QWORD, void *, int *, int **, _DWORD, unsigned int *))(*(_QWORD *)v7 + 96LL))(
                v7,
                1073741825,
                v22,
                v6,
                &v30,
                &v32,
                0,
                &v31);
    (**(void (__fastcall ***)(char *))v5)((char *)this + 96);
    if ( started )
    {
      v19 = 3580;
      v20 = "CITransaction::EnlistKtm - error from CSendReceive::SendReceive";
LABEL_43:
      v21 = started;
      goto LABEL_56;
    }
    if ( v30 == 1073741826 )
    {
      if ( v31 >= 4 )
      {
        if ( v32 )
        {
          started = *v32;
          v14 = *v32 == 0;
          if ( *v32 >= 0 )
          {
LABEL_17:
            if ( v14 )
            {
LABEL_60:
              if ( v32 )
                (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v7 + 120LL))(v7);
              if ( v7 )
              {
                (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v7 + 272LL))(v7);
                (*(void (__fastcall **)(CIConnSink *))(*(_QWORD *)v7 + 168LL))(v7);
              }
              if ( v6 )
                CoTaskMemFree(v6);
              return started;
            }
LABEL_57:
            v27 = (void *)*((_QWORD *)this + 128);
            if ( v27 != (void *)-1LL )
              RollbackTransactionAsync(v27);
            (*(void (__fastcall **)(_QWORD, CITransaction *, _QWORD))(**((_QWORD **)this + 9) + 16LL))(
              *((_QWORD *)this + 9),
              this,
              0);
            goto LABEL_60;
          }
          v19 = 3602;
          v20 = "CITransaction::EnlistKtm - error from enlistment";
          goto LABEL_43;
        }
        v19 = 3595;
        v20 = "CITransaction::EnlistKtm - null result message";
      }
      else
      {
        v19 = 3589;
        v20 = "CITransaction::EnlistKtm - bad result message length";
      }
    }
    else
    {
      if ( v30 == 9 )
      {
        started = -2147168228;
        v20 = "CITransaction::EnlistKtm - connection to KtmRm went down";
        v19 = 3609;
        goto LABEL_43;
      }
      v19 = 3615;
      v20 = "CITransaction::EnlistKtm - unexpected return MTAG for KtmRm";
    }
    v21 = -2147418113;
    goto LABEL_55;
  }
  return result;
}

```

## disassembly

```asm
0x18002847c  push    rbp
0x18002847e  push    rbx
0x18002847f  push    rsi
0x180028480  push    rdi
0x180028481  push    r12
0x180028483  push    r13
0x180028485  push    r14
0x180028487  push    r15
0x180028489  lea     rbp, [rsp-1Fh]
0x18002848e  sub     rsp, 0F8h
0x180028495  mov     rax, cs:__security_cookie
0x18002849c  xor     rax, rsp
0x18002849f  mov     [rbp+57h+var_50], rax
0x1800284a3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800284aa  xor     r14d, r14d
0x1800284ad  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFFh
0x1800284b5  lea     r13, [rcx+458h]
0x1800284bc  mov     [rsp+130h+var_E0], r14d
0x1800284c1  mov     rdi, rcx
0x1800284c4  mov     [rbp+57h+var_C0], r14d
0x1800284c8  mov     rdx, r13; TransactionId
0x1800284cb  mov     [rsp+130h+var_DC], r14d
0x1800284d0  mov     ecx, 120037h; dwDesiredAccess
0x1800284d5  mov     [rbp+57h+var_D0], r14
0x1800284d9  movdqu  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x1800284de  mov     [rsp+130h+var_D8], r14d
0x1800284e3  call    cs:__imp_OpenTransaction
0x1800284e9  mov     [rdi+400h], rax
0x1800284f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800284f4  jz      short loc_1800284FD
0x1800284f6  xor     eax, eax
0x1800284f8  jmp     loc_180028A5C
0x1800284fd  lea     rcx, [rbp+57h+var_B8]; struct _SECURITY_ATTRIBUTES **
0x180028501  mov     [rbp+57h+var_B8], r14
0x180028505  call    ?GetTransactionSecurityAttributes@CITransaction@@SAJPEAPEAU_SECURITY_ATTRIBUTES@@@Z; CITransaction::GetTransactionSecurityAttributes(_SECURITY_ATTRIBUTES * *)
0x18002850a  test    eax, eax
0x18002850c  jnz     loc_180028A5C
0x180028512  lea     r15, [rdi+60h]
0x180028516  mov     r12, r14
0x180028519  mov     rax, [r15]
0x18002851c  mov     rcx, r15
0x18002851f  mov     rsi, r14
0x180028522  mov     rax, [rax+8]
0x180028526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002852b  call    ?StartKtmRmService@@YAJXZ; StartKtmRmService(void)
0x180028530  mov     rcx, [r15]
0x180028533  mov     ebx, eax
0x180028535  mov     rax, [rcx]
0x180028538  mov     rcx, r15
0x18002853b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028540  test    ebx, ebx
0x180028542  jns     short loc_180028581
0x180028544  lea     rax, aCitransactionE_11; "CITransaction::EnlistKtm - error from S"...
0x18002854b  mov     r9d, 0D43h
0x180028551  mov     edx, 1
0x180028556  mov     [rsp+130h+var_100], rax
0x18002855b  lea     r8, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180028562  lea     rax, aCitransactionE_5; "CITransaction::EnlistKtm"
0x180028569  mov     [rsp+130h+cchWideChar], ebx
0x18002856d  mov     ecx, 0Fh
0x180028572  mov     [rsp+130h+lpWideCharStr], rax
0x180028577  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002857c  jmp     loc_1800289E2
0x180028581  mov     rax, [r15]
0x180028584  mov     rcx, r15
0x180028587  mov     rax, [rax+8]
0x18002858b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028590  mov     rcx, [rdi+0E8h]; this
0x180028597  lea     r8, [rbp+57h+var_C8]; void **
0x18002859b  mov     r14d, 1
0x1800285a1  mov     edx, r14d; int
0x1800285a4  call    ?GetKtmRmTmHandle@CTmProxyCore@@QEAAJHPEAPEAX@Z; CTmProxyCore::GetKtmRmTmHandle(int,void * *)
0x1800285a9  mov     ebx, eax
0x1800285ab  mov     rcx, r15
0x1800285ae  mov     rax, [r15]
0x1800285b1  mov     rax, [rax]
0x1800285b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285b9  test    ebx, ebx
0x1800285bb  jns     short loc_1800285CF
0x1800285bd  lea     rax, aCitransactionE_2; "CITransaction::EnlistKtm - error from G"...
0x1800285c4  mov     r9d, 0D4Ch
0x1800285ca  mov     edx, r14d
0x1800285cd  jmp     short loc_180028556
0x1800285cf  xor     eax, eax
0x1800285d1  lea     r8, [rdi+0BCh]; lpMultiByteStr
0x1800285d8  mov     [rbp+57h+WideCharStr], ax
0x1800285dc  xor     edx, edx; dwFlags
0x1800285de  xor     ecx, ecx; CodePage
0x1800285e0  lea     r9d, [rax+28h]; cbMultiByte
0x1800285e4  lea     rax, [rbp+57h+WideCharStr]
0x1800285e8  mov     [rsp+130h+cchWideChar], r9d; cchWideChar
0x1800285ed  mov     [rsp+130h+lpWideCharStr], rax; lpWideCharStr
0x1800285f2  call    cs:__imp_MultiByteToWideChar
0x1800285f8  xor     eax, eax
0x1800285fa  cmp     qword ptr [rdi+400h], 0FFFFFFFFFFFFFFFFh
0x180028602  mov     [rbp+57h+var_52], ax
0x180028606  jnz     loc_18002874F
0x18002860c  mov     r9d, [rdi+0B0h]
0x180028613  lea     rax, [rbp+57h+WideCharStr]
0x180028617  mov     rcx, [rbp+57h+var_B8]
0x18002861b  xor     r8d, r8d
0x18002861e  mov     [rsp+130h+var_100], rax
0x180028623  mov     rdx, r13
0x180028626  mov     eax, [rdi+0B4h]
0x18002862c  mov     [rsp+130h+cchWideChar], esi
0x180028630  mov     dword ptr [rsp+130h+lpWideCharStr], eax
0x180028634  call    cs:__imp_PrivCreateTransaction
0x18002863a  mov     [rdi+400h], rax
0x180028641  mov     rcx, rax
0x180028644  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028648  jnz     short loc_18002869A
0x18002864a  call    cs:__imp_GetLastError
0x180028650  mov     ebx, eax
0x180028652  cmp     eax, 1A90h
0x180028657  jnz     short loc_180028680
0x180028659  mov     rdx, r13; TransactionId
0x18002865c  mov     ecx, 120037h; dwDesiredAccess
0x180028661  call    cs:__imp_OpenTransaction
0x180028667  mov     [rdi+400h], rax
0x18002866e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028672  jnz     loc_18002874F
0x180028678  call    cs:__imp_GetLastError
0x18002867e  mov     ebx, eax
0x180028680  test    eax, eax
0x180028682  jle     short loc_18002868D
0x180028684  movzx   ebx, ax
0x180028687  or      ebx, 80070000h
0x18002868d  test    ebx, ebx
0x18002868f  jz      loc_180028A0B
0x180028695  jmp     loc_1800289E2
0x18002869a  mov     rax, [rbp+57h+var_C8]
0x18002869e  lea     r8, [rbp+57h+var_C8]
0x1800286a2  mov     r9d, 8
0x1800286a8  mov     [rbp+57h+var_C8], rax
0x1800286ac  lea     edx, [r9-4]
0x1800286b0  call    cs:__imp_NtSetInformationTransaction
0x1800286b6  mov     ebx, eax
0x1800286b8  test    eax, eax
0x1800286ba  jz      short loc_1800286F8
0x1800286bc  lea     rax, aCitransactionE_9; "CITransaction::EnlistKtm - error from N"...
0x1800286c3  mov     r9d, 0D8Ch
0x1800286c9  mov     [rsp+130h+var_100], rax
0x1800286ce  lea     r8, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x1800286d5  bts     ebx, 1Ch
0x1800286d9  lea     rax, aCitransactionE_5; "CITransaction::EnlistKtm"
0x1800286e0  mov     [rsp+130h+cchWideChar], ebx
0x1800286e4  mov     edx, r14d
0x1800286e7  mov     ecx, 0Fh
0x1800286ec  mov     [rsp+130h+lpWideCharStr], rax
0x1800286f1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800286f6  jmp     short loc_18002868D
0x1800286f8  lea     rdx, [rbp+57h+var_B0]; struct _GUID *
0x1800286fc  mov     rcx, rdi; this
0x1800286ff  call    ?GetKtmCookie@CITransaction@@AEAAJPEAU_GUID@@@Z; CITransaction::GetKtmCookie(_GUID *)
0x180028704  mov     ebx, eax
0x180028706  test    eax, eax
0x180028708  jns     short loc_18002871C
0x18002870a  lea     rax, aErrorFromGetkt; "error from GetKtmCookie"
0x180028711  mov     r9d, 0D95h
0x180028717  jmp     loc_1800285CA
0x18002871c  mov     rcx, [rdi+400h]
0x180028723  lea     r8, [rbp+57h+var_B0]
0x180028727  mov     r9d, 10h
0x18002872d  lea     edx, [r9-0Bh]
0x180028731  call    cs:__imp_NtSetInformationTransaction
0x180028737  mov     ebx, eax
0x180028739  test    eax, eax
0x18002873b  jz      short loc_18002874F
0x18002873d  lea     rax, aErrorFromNtset; "error from NtSetInformationTransaction "...
0x180028744  mov     r9d, 0DA3h
0x18002874a  jmp     loc_1800286C9
0x18002874f  mov     rax, [rdi]
0x180028752  lea     rdx, [rsp+130h+var_E0]
0x180028757  mov     rcx, rdi
0x18002875a  mov     rax, [rax+40h]
0x18002875e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028763  mov     ebx, eax
0x180028765  test    eax, eax
0x180028767  jns     short loc_18002877D
0x180028769  mov     r9d, 0DADh
0x18002876f  lea     rdx, aCitransactionG; "CITransaction::GetKtmHandle - error fro"...
0x180028776  mov     ecx, eax
0x180028778  jmp     loc_1800289D6
0x18002877d  mov     r13d, [rsp+130h+var_E0]
0x180028782  add     r13d, 8
0x180028786  mov     ecx, r13d; cb
0x180028789  call    cs:__imp_CoTaskMemAlloc
0x18002878f  mov     r12, rax
0x180028792  test    rax, rax
0x180028795  jnz     short loc_1800287AE
0x180028797  mov     ecx, 8007000Eh
0x18002879c  lea     rdx, aCitransactionE_4; "CITransaction::EnlistKtm - can't alloca"...
0x1800287a3  mov     r9d, 0DB6h
0x1800287a9  jmp     loc_1800289D4
0x1800287ae  mov     eax, [rsp+130h+var_E0]
0x1800287b2  lea     r8, [r12+4]
0x1800287b7  mov     [r12], eax
0x1800287bb  lea     r9, [rbp+57h+var_C0]
0x1800287bf  mov     rax, [rdi]
0x1800287c2  mov     rcx, rdi
0x1800287c5  mov     edx, [rsp+130h+var_E0]
0x1800287c9  mov     rax, [rax+48h]
0x1800287cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287d2  mov     ebx, eax
0x1800287d4  test    eax, eax
0x1800287d6  jns     short loc_1800287E7
0x1800287d8  mov     r9d, 0DC3h
0x1800287de  lea     rdx, aCitransactionG_7; "CITransaction::GetKtmHandle - error fro"...
0x1800287e5  jmp     short loc_180028776
0x1800287e7  call    ?CreateInstance@CSendReceive@@SAPEAV1@XZ; CSendReceive::CreateInstance(void)
0x1800287ec  mov     rsi, rax
0x1800287ef  test    rax, rax
0x1800287f2  jnz     short loc_18002880B
0x1800287f4  mov     ecx, 8007000Eh
0x1800287f9  lea     rdx, aCitransactionE_10; "CITransaction::EnlistKtm - can't alloca"...
0x180028800  mov     r9d, 0DCDh
0x180028806  jmp     loc_1800289D4
0x18002880b  mov     rax, [rax]
0x18002880e  mov     rcx, rsi
0x180028811  mov     rax, [rax+20h]
0x180028815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002881a  mov     rcx, rsi; this
0x18002881d  test    eax, eax
0x18002881f  jnz     short loc_18002883F
0x180028821  call    ?DeleteObject@CIConnSink@@UEAAXXZ; CIConnSink::DeleteObject(void)
0x180028826  mov     ecx, 8007000Eh
0x18002882b  lea     rdx, aCitransactionG_0; "CITransaction::GetKtmHandle - can't ini"...
0x180028832  xor     esi, esi
0x180028834  mov     r9d, 0DD6h
0x18002883a  jmp     loc_1800289D4
0x18002883f  mov     rax, [rsi]
0x180028842  mov     rax, [rax+0A0h]
0x180028849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002884e  mov     rdx, [rdi+0E8h]
0x180028855  mov     r8, [rdx+0DC0h]
0x18002885c  test    r8, r8
0x18002885f  jnz     short loc_1800288A2
0x180028861  lea     rax, aCitransactionG_5; "CITransaction::GetKtmHandle - m_pCTmPro"...
0x180028868  mov     r9d, 0DDEh
0x18002886e  mov     [rsp+130h+var_100], rax
0x180028873  mov     edx, r14d
0x180028876  mov     qword ptr [rsp+130h+cchWideChar], r8
0x18002887b  lea     rax, aCitransactionE_5; "CITransaction::EnlistKtm"
0x180028882  lea     r8, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180028889  mov     [rsp+130h+lpWideCharStr], rax
0x18002888e  mov     ecx, 0Fh
0x180028893  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180028898  mov     ebx, 8004D027h
0x18002889d  jmp     loc_1800289E2
0x1800288a2  mov     rax, [rsi]
0x1800288a5  mov     r9d, r14d
0x1800288a8  mov     rdx, [rdx+0DD8h]
0x1800288af  mov     rcx, rsi
0x1800288b2  mov     dword ptr [rsp+130h+lpWideCharStr], 1001h
0x1800288ba  mov     rax, [rax+0F8h]
0x1800288c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288c6  mov     ebx, eax
0x1800288c8  test    eax, eax
0x1800288ca  jns     short loc_1800288DE
0x1800288cc  mov     r9d, 0DEBh
0x1800288d2  lea     rdx, aCitransactionE; "CITransaction::EnlistKtm - error from C"...
0x1800288d9  jmp     loc_180028776
0x1800288de  mov     rax, [r15]
0x1800288e1  mov     rcx, r15
0x1800288e4  mov     rax, [rax+8]
0x1800288e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288ed  mov     rax, [rsi]
0x1800288f0  lea     rcx, [rsp+130h+var_D8]
0x1800288f5  mov     [rsp+130h+var_F8], rcx
0x1800288fa  mov     r9, r12
0x1800288fd  lea     rcx, [rbp+57h+var_D0]
0x180028901  mov     dword ptr [rsp+130h+var_100], 0
0x180028909  mov     qword ptr [rsp+130h+cchWideChar], rcx
0x18002890e  mov     r8d, r13d
0x180028911  mov     rax, [rax+60h]
0x180028915  lea     rcx, [rsp+130h+var_DC]
0x18002891a  mov     [rsp+130h+lpWideCharStr], rcx
0x18002891f  mov     edx, 40000001h
0x180028924  mov     rcx, rsi
0x180028927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002892c  mov     ebx, eax
0x18002892e  mov     rcx, r15
0x180028931  mov     rax, [r15]
0x180028934  mov     rax, [rax]
0x180028937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002893c  test    ebx, ebx
0x18002893e  jz      short loc_180028954
0x180028940  mov     r9d, 0DFCh
0x180028946  lea     rdx, aCitransactionE_6; "CITransaction::EnlistKtm - error from C"...
0x18002894d  mov     ecx, ebx
0x18002894f  jmp     loc_1800289D6
0x180028954  cmp     [rsp+130h+var_DC], 40000002h
0x18002895c  jnz     short loc_1800289A7
0x18002895e  cmp     [rsp+130h+var_D8], 4
0x180028963  jnb     short loc_180028974
0x180028965  mov     r9d, 0E05h
0x18002896b  lea     rdx, aCitransactionE_0; "CITransaction::EnlistKtm - bad result m"...
0x180028972  jmp     short loc_1800289CF
0x180028974  cmp     [rbp+57h+var_D0], 0
0x180028979  jnz     short loc_18002898A
  ... truncated ...
```
