# GetAuthorizedSharingToken

- ea: `0x18000da68`
- end: `0x18000dcf7`
- name: `GetAuthorizedSharingToken`
- size: `655`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, FILETIME **)`
- caller_count: `6`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ca4c`
- `0x18000ceb4`
- `0x18000cfcc`
- `0x18000d0d0`
- `0x18000d3e4`
- `0x18000d7b8`

## callees

- `0x1800041a0`
- `0x180006cb0`
- `0x180006f78`
- `0x18000bf80`
- `0x18000da68`
- `0x18000dd00`
- `0x18000dee8`
- `0x18000e020`
- `0x18000e674`
- `0x18000f2b0`
- `0x18000f384`
- `0x18000f674`
- `0x180011a78`
- `0x1800124b0`
- `0x1800129fc`
- `0x180017140`
- `0x180019720`
- `0x18001b340`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000db47`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000db47`

## string_xrefs

- `0x18000db56`: `Token %s is already expired`
- `0x18000db68`: `GetAuthorizedSharingToken`
- `0x18000dcae`: `GetAuthorizedSharingToken`
- `0x18000dc9c`: `Unable to authorize access to token %s`
- `0x18000daeb`: `SharingTokenManager::GetSharingToken`

## pseudocode

```c
__int64 __fastcall GetAuthorizedSharingToken(unsigned __int16 *a1, int a2, FILETIME **a3)
{
  struct _FILETIME *v6; // rdx
  FILETIME v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int Token; // ebx
  _DWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  DSLogger *v16; // rax
  FILETIME *v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  DSLogger *v22; // rax
  SqmHelper *v23; // r14
  FILETIME *v24; // rsi
  FILETIME *v25; // rbx
  FILETIME *i; // r11
  __int64 v27; // r9
  FILETIME **v28; // r11
  FILETIME *v29; // rcx
  DSLogger *v30; // rax
  FILETIME FileTime1; // [rsp+30h] [rbp-50h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-48h] BYREF
  SqmHelper *v34[4]; // [rsp+40h] [rbp-40h] BYREF
  struct _GUID v35; // [rsp+60h] [rbp-20h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v34);
  v35 = 0;
  if ( SharingToken::ConvertStringToTokenId(a1, &v35) < 0 )
    goto LABEL_2;
  v11 = (_DWORD *)tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get();
  if ( !*v11 )
  {
    v16 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v13,
                        v12,
                        v14,
                        v15);
    Token = -1055719422;
    DSLogger::LogError(v16, L"SharingTokenManager::GetSharingToken", 0x97u, L"hr=0x%x.", -1055719422);
    goto LABEL_29;
  }
  Token = SharingTokenDatabase::GetToken((SharingTokenDatabase *)(v11 + 2));
  if ( Token < 0 )
    goto LABEL_29;
  v17 = *a3;
  FileTime2 = 0;
  FileTime1 = 0;
  Token = DSUtils::GetCurrentTimeAsFileTime(&FileTime2, v6);
  if ( Token < 0 )
    goto LABEL_29;
  FileTime1 = v17[12];
  if ( CompareFileTime(&FileTime1, &FileTime2) < 0 )
  {
    v22 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v19,
                        v18,
                        v20,
                        v21);
    DSLogger::LogError(v22, L"GetAuthorizedSharingToken", 0x8Fu, L"Token %s is already expired", a1);
LABEL_2:
    Token = -1055719418;
LABEL_29:
    v30 = (DSLogger *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get)(
                        v7,
                        v6,
                        v8,
                        v9);
    DSLogger::LogError(v30, L"GetAuthorizedSharingToken", 0xD2u, L"Unable to authorize access to token %s", a1);
    tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&void tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(a3);
    goto LABEL_30;
  }
  Token = PolicyChecker::GetClientSid(v34);
  if ( Token < 0 )
    goto LABEL_29;
  v23 = v34[0];
  if ( !a2
    || (unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(
                       v34[0],
                       (v34[1] - v34[0]) >> 1,
                       *(_QWORD *)&(*a3)[4],
                       (__int64)(*(_QWORD *)&(*a3)[5] - *(_QWORD *)&(*a3)[4]) >> 1) )
  {
    v24 = *a3 + 16;
    v25 = (FILETIME *)*v24;
    for ( i = (FILETIME *)*v24; ; i = *v28 )
    {
      if ( i == v24 )
      {
        while ( v25 != v24 )
        {
          v7 = v25[2];
          if ( *(_DWORD *)(*(_QWORD *)&v7 + 40LL) == 2
            && (unsigned int)PolicyChecker::CheckCapability(*(const unsigned __int16 **)(*(_QWORD *)&v7 + 8LL)) )
          {
            goto LABEL_12;
          }
          v25 = (FILETIME *)*v25;
        }
        Token = -1055719414;
        goto LABEL_29;
      }
      v27 = -1;
      do
        ++v27;
      while ( *((_WORD *)v23 + v27) );
      if ( !(unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(
                            *(_QWORD *)(*(_QWORD *)&i[2] + 8LL),
                            (__int64)(*(_QWORD *)(*(_QWORD *)&i[2] + 16LL) - *(_QWORD *)(*(_QWORD *)&i[2] + 8LL)) >> 1,
                            v23,
                            v27) )
        break;
    }
    FileTime1.dwLowDateTime = 0;
    AutoImpersonate<1>::ImpersonateClient(&FileTime1);
    v29 = *a3;
    FileTime2.dwLowDateTime = 1;
    Token = (*(__int64 (__fastcall **)(FILETIME *, FILETIME *))(*(_QWORD *)v29 + 32LL))(v29, &FileTime2);
    if ( Token < 0 )
    {
LABEL_22:
      AutoImpersonate<1>::RevertToSelf(&FileTime1);
      goto LABEL_29;
    }
    if ( !FileTime2.dwLowDateTime )
    {
      Token = -1055719414;
      DataSharingServiceTelemetry::GetAuthorizedSharingTokenEDPCheckFailed();
      goto LABEL_22;
    }
    AutoImpersonate<1>::RevertToSelf(&FileTime1);
    LogTokenRedemtionStats(v34[0]);
  }
  else
  {
LABEL_12:
    Token = 0;
  }
LABEL_30:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v34);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x18000da68  mov     [rsp-38h+arg_8], rbx
0x18000da6d  push    rbp
0x18000da6e  push    rsi
0x18000da6f  push    rdi
0x18000da70  push    r12
0x18000da72  push    r13
0x18000da74  push    r14
0x18000da76  push    r15
0x18000da78  mov     rbp, rsp
0x18000da7b  sub     rsp, 80h
0x18000da82  mov     rax, cs:__security_cookie
0x18000da89  xor     rax, rsp
0x18000da8c  mov     [rbp+var_10], rax
0x18000da90  mov     r12, rcx
0x18000da93  mov     rdi, r8
0x18000da96  lea     rcx, [rbp+var_40]
0x18000da9a  mov     r15d, edx
0x18000da9d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000daa2  xorps   xmm0, xmm0
0x18000daa5  lea     rdx, [rbp+var_20]; struct _GUID *
0x18000daa9  mov     rcx, r12; unsigned __int16 *
0x18000daac  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x18000dab0  call    ?ConvertStringToTokenId@SharingToken@@SAJPEBGAEAU_GUID@@@Z; SharingToken::ConvertStringToTokenId(ushort const *,_GUID &)
0x18000dab5  xor     r13d, r13d
0x18000dab8  test    eax, eax
0x18000daba  jns     short loc_18000DAC6
0x18000dabc  mov     ebx, 0C1130006h
0x18000dac1  jmp     loc_18000DC97
0x18000dac6  call    ?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)
0x18000dacb  cmp     [rax], r13d
0x18000dace  jnz     short loc_18000DAFF
0x18000dad0  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000dad5  mov     ebx, 0C1130002h
0x18000dada  lea     r9, aHr0xX; "hr=0x%x."
0x18000dae1  mov     r8d, 97h; unsigned int
0x18000dae7  mov     dword ptr [rsp+80h+var_60], ebx
0x18000daeb  lea     rdx, aSharingtokenma_1; "SharingTokenManager::GetSharingToken"
0x18000daf2  mov     rcx, rax; this
0x18000daf5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000dafa  jmp     loc_18000DC97
0x18000daff  lea     rcx, [rax+8]; this
0x18000db03  mov     r8, rdi
0x18000db06  lea     rdx, [rbp+var_20]
0x18000db0a  call    ?GetToken@SharingTokenDatabase@@QEAAJAEBU_GUID@@AEAV?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; SharingTokenDatabase::GetToken(_GUID const &,tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>> &)
0x18000db0f  mov     ebx, eax
0x18000db11  test    eax, eax
0x18000db13  js      loc_18000DC97
0x18000db19  mov     rsi, [rdi]
0x18000db1c  lea     rcx, [rbp+FileTime2]; lpFileTime
0x18000db20  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r13
0x18000db24  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r13
0x18000db28  call    ?GetCurrentTimeAsFileTime@DSUtils@@YAJPEAU_FILETIME@@@Z; DSUtils::GetCurrentTimeAsFileTime(_FILETIME *)
0x18000db2d  mov     ebx, eax
0x18000db2f  test    eax, eax
0x18000db31  js      loc_18000DC97
0x18000db37  mov     rax, [rsi+60h]
0x18000db3b  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18000db3f  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18000db43  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18000db47  call    cs:__imp_CompareFileTime
0x18000db4d  test    eax, eax
0x18000db4f  jns     short loc_18000DB7C
0x18000db51  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000db56  lea     r9, aTokenSIsAlread; "Token %s is already expired"
0x18000db5d  mov     [rsp+80h+var_60], r12
0x18000db62  mov     r8d, 8Fh; unsigned int
0x18000db68  lea     rdx, aGetauthorizeds; "GetAuthorizedSharingToken"
0x18000db6f  mov     rcx, rax; this
0x18000db72  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000db77  jmp     loc_18000DABC
0x18000db7c  lea     rcx, [rbp+var_40]
0x18000db80  call    ?GetClientSid@PolicyChecker@@SAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; PolicyChecker::GetClientSid(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18000db85  mov     ebx, eax
0x18000db87  test    eax, eax
0x18000db89  js      loc_18000DC97
0x18000db8f  mov     r14, [rbp+var_40]
0x18000db93  test    r15d, r15d
0x18000db96  jz      short loc_18000DBC7
0x18000db98  mov     rax, [rdi]
0x18000db9b  mov     rcx, r14
0x18000db9e  mov     rdx, [rbp+var_38]
0x18000dba2  sub     rdx, r14
0x18000dba5  sar     rdx, 1
0x18000dba8  mov     r8, [rax+20h]
0x18000dbac  mov     r9, [rax+28h]
0x18000dbb0  sub     r9, r8
0x18000dbb3  sar     r9, 1
0x18000dbb6  call    ?compare@?$_StringTraits@U?$char_traits@G@utl@@@utl@@SAHPEBG_K01@Z; utl::_StringTraits<utl::char_traits<ushort>>::compare(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x18000dbbb  test    eax, eax
0x18000dbbd  jnz     short loc_18000DBC7
0x18000dbbf  mov     ebx, r13d
0x18000dbc2  jmp     loc_18000DCC5
0x18000dbc7  mov     rsi, [rdi]
0x18000dbca  sub     rsi, 0FFFFFFFFFFFFFF80h
0x18000dbce  mov     rbx, [rsi]
0x18000dbd1  mov     r11, rbx
0x18000dbd4  cmp     r11, rsi
0x18000dbd7  jz      loc_18000DC6D
0x18000dbdd  mov     rdx, [r11+10h]
0x18000dbe1  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000dbe5  inc     r9
0x18000dbe8  cmp     [r14+r9*2], r13w
0x18000dbed  jnz     short loc_18000DBE5
0x18000dbef  mov     rcx, [rdx+8]
0x18000dbf3  mov     r8, r14
0x18000dbf6  mov     rdx, [rdx+10h]
0x18000dbfa  sub     rdx, rcx
0x18000dbfd  sar     rdx, 1
0x18000dc00  call    ?compare@?$_StringTraits@U?$char_traits@G@utl@@@utl@@SAHPEBG_K01@Z; utl::_StringTraits<utl::char_traits<ushort>>::compare(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x18000dc05  test    eax, eax
0x18000dc07  jz      short loc_18000DC0E
0x18000dc09  mov     r11, [r11]
0x18000dc0c  jmp     short loc_18000DBD4
0x18000dc0e  lea     rcx, [rbp+FileTime1]
0x18000dc12  mov     [rbp+FileTime1.dwLowDateTime], r13d
0x18000dc16  call    ?ImpersonateClient@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::ImpersonateClient(void)
0x18000dc1b  mov     rcx, [rdi]
0x18000dc1e  lea     rdx, [rbp+FileTime2]
0x18000dc22  mov     [rbp+FileTime2.dwLowDateTime], 1
0x18000dc29  mov     rax, [rcx]
0x18000dc2c  mov     rax, [rax+20h]
0x18000dc30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc35  mov     ebx, eax
0x18000dc37  test    eax, eax
0x18000dc39  js      short loc_18000DC4B
0x18000dc3b  cmp     [rbp+FileTime2.dwLowDateTime], r13d
0x18000dc3f  jnz     short loc_18000DC56
0x18000dc41  mov     ebx, 0C113000Ah
0x18000dc46  call    ?GetAuthorizedSharingTokenEDPCheckFailed@DataSharingServiceTelemetry@@SAXXZ; DataSharingServiceTelemetry::GetAuthorizedSharingTokenEDPCheckFailed(void)
0x18000dc4b  lea     rcx, [rbp+FileTime1]
0x18000dc4f  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18000dc54  jmp     short loc_18000DC97
0x18000dc56  lea     rcx, [rbp+FileTime1]
0x18000dc5a  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18000dc5f  mov     rdx, [rdi]
0x18000dc62  mov     rcx, [rbp+var_40]; this
0x18000dc66  call    LogTokenRedemtionStats
0x18000dc6b  jmp     short loc_18000DCC5
0x18000dc6d  cmp     rbx, rsi
0x18000dc70  jz      short loc_18000DC92
0x18000dc72  mov     rcx, [rbx+10h]
0x18000dc76  cmp     dword ptr [rcx+28h], 2
0x18000dc7a  jnz     short loc_18000DC8D
0x18000dc7c  mov     rcx, [rcx+8]; unsigned __int16 *
0x18000dc80  call    ?CheckCapability@PolicyChecker@@SAHPEBG@Z; PolicyChecker::CheckCapability(ushort const *)
0x18000dc85  test    eax, eax
0x18000dc87  jnz     loc_18000DBBF
0x18000dc8d  mov     rbx, [rbx]
0x18000dc90  jmp     short loc_18000DC6D
0x18000dc92  mov     ebx, 0C113000Ah
0x18000dc97  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000dc9c  lea     r9, aUnableToAuthor; "Unable to authorize access to token %s"
0x18000dca3  mov     [rsp+80h+var_60], r12
0x18000dca8  mov     r8d, 0D2h; unsigned int
0x18000dcae  lea     rdx, aGetauthorizeds; "GetAuthorizedSharingToken"
0x18000dcb5  mov     rcx, rax; this
0x18000dcb8  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000dcbd  mov     rcx, rdi
0x18000dcc0  call    ?reset@?$smart_xxx@PEAVSharingToken@@P6AXPEAV1@@Z$1??$_delete@VSharingToken@@@tlx@@YAX0@Z$0A@V?$allocator@H@utl@@@tlx@@QEAAXXZ; tlx::smart_xxx<SharingToken *,void (*)(SharingToken *),&tlx::_delete<SharingToken>(SharingToken *),0,utl::allocator<int>>::reset(void)
0x18000dcc5  lea     rcx, [rbp+var_40]
0x18000dcc9  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000dcce  mov     eax, ebx
0x18000dcd0  mov     rcx, [rbp+var_10]
0x18000dcd4  xor     rcx, rsp; StackCookie
0x18000dcd7  call    __security_check_cookie
0x18000dcdc  mov     rbx, [rsp+80h+arg_8]
0x18000dce4  add     rsp, 80h
0x18000dceb  pop     r15
0x18000dced  pop     r14
0x18000dcef  pop     r13
0x18000dcf1  pop     r12
0x18000dcf3  pop     rdi
0x18000dcf4  pop     rsi
0x18000dcf5  pop     rbp
0x18000dcf6  retn
```
