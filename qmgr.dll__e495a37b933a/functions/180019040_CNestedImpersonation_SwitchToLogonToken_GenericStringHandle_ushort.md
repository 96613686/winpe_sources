# CNestedImpersonation::SwitchToLogonToken(GenericStringHandle<ushort>)

- ea: `0x180019040`
- end: `0x18001950e`
- name: `?SwitchToLogonToken@CNestedImpersonation@@QEAAXV?$GenericStringHandle@G@@@Z`
- size: `1230`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180059860`
- `0x180068880`
- `0x18008a9a0`
- `0x18008abdc`
- `0x18008b030`
- `0x18008b230`
- `0x18008b6b0`
- `0x18008bd40`
- `0x18008c040`
- `0x18009651c`
- `0x1800a1930`
- `0x1800ce1a0`
- `0x1800d4390`
- `0x1800d46d0`
- `0x1800d77ac`

## callees

- `0x180018d00`
- `0x180019040`
- `0x180019514`
- `0x180019690`
- `0x180019a30`
- `0x180019d90`
- `0x18001a6fc`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800acacc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800190a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001914e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800190a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001914e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019410`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800193b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800194af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800193b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800194af`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180019299`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180019299`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180019278`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001928b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180019278`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001928b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180019406`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180019406`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800191fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800191fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CNestedImpersonation::SwitchToLogonToken(__int64 a1, void **a2)
{
  _DWORD *v4; // rax
  AppPackageInfo *v5; // r12
  AppPackageInfo *v6; // rax
  AppPackageInfo *v7; // r14
  unsigned int LastError; // eax
  PSID v9; // rbx
  DWORD v10; // r13d
  PUCHAR SidSubAuthorityCount; // rax
  void *v12; // rcx
  AppPackageInfo *v13; // rbx
  int v14; // eax
  __int64 v15; // rdx
  char *v16; // rcx
  volatile signed __int32 *v17; // rax
  volatile signed __int32 *v18; // rax
  __int64 v19; // rcx
  signed int v20; // eax
  void *v21; // rcx
  void *v22; // [rsp+40h] [rbp-89h] BYREF
  void *v23; // [rsp+48h] [rbp-81h] BYREF
  PSID pSid; // [rsp+50h] [rbp-79h] BYREF
  void *v25; // [rsp+58h] [rbp-71h]
  void **pExceptionObject; // [rsp+60h] [rbp-69h] BYREF
  __int128 v27; // [rsp+68h] [rbp-61h]
  int v28; // [rsp+78h] [rbp-51h]
  int v29; // [rsp+7Ch] [rbp-4Dh]
  int v30; // [rsp+80h] [rbp-49h]
  unsigned __int64 UserContextToken; // [rsp+C0h] [rbp-9h] BYREF
  AppPackageInfo *v32[11]; // [rsp+C8h] [rbp-1h] BYREF
  int TokenInformation; // [rsp+140h] [rbp+77h] BYREF
  void *ReturnLength; // [rsp+148h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids);
  v4 = HeapAlloc(hBitsHeap, 8u, 0x10u);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
    v27 = 0;
    pExceptionObject = &ComError::`vftable';
    v28 = -2147024882;
    v29 = 0;
    v30 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v22 = v4;
  v4[2] = 1;
  *(_QWORD *)v22 = 0;
  v5 = (AppPackageInfo *)CopyTokenSid(**(HANDLE **)(a1 + 16));
  v32[2] = v5;
  v6 = (AppPackageInfo *)HeapAlloc(hBitsHeap, 8u, 4u);
  v7 = v6;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
    v27 = 0;
    pExceptionObject = &ComError::`vftable';
    v28 = -2147024882;
    v29 = 0;
    v30 = 1;
    throw (ComError *)&pExceptionObject;
  }
  *(_DWORD *)v6 = 1;
  v32[3] = v6;
  GetPackageInfoFromToken(v32, **(_QWORD **)(a1 + 16));
  LODWORD(ReturnLength) = 0;
  TokenInformation = 0;
  if ( !GetTokenInformation(**(HANDLE **)(a1 + 16), TokenElevation, &TokenInformation, 4u, (PDWORD)&ReturnLength) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v27 = 0;
    pExceptionObject = &ComError::`vftable';
    v28 = LastError;
    v29 = 437;
    v30 = 1;
    throw (ComError *)&pExceptionObject;
  }
  GetTokenIntegrityLevelSid(&pSid, **(_QWORD **)(a1 + 16));
  v9 = pSid;
  if ( *GetSidSubAuthorityCount(pSid) )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(v9);
    v10 = *GetSidSubAuthority(v9, (unsigned int)*SidSubAuthorityCount - 1);
  }
  else
  {
    v10 = 0;
  }
  v12 = v25;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25, 0xFFFFFFFF) == 1 )
  {
    operator delete(v12, 4u);
    operator delete(v9, 0);
  }
  UserContextToken = QueryUserContextToken(**(void ***)(a1 + 16));
  _InterlockedIncrement((volatile signed __int32 *)*a2 + 2);
  ReturnLength = *a2;
  CNestedImpersonation::UpdateServiceName(a1, &ReturnLength);
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 48) + 8LL));
  v23 = *(void **)(a1 + 48);
  pSid = v5;
  v25 = v7;
  _InterlockedIncrement((volatile signed __int32 *)v7);
  v13 = v32[0];
  v14 = CJobManager::CloneUserToken(
          (__int64)g_Manager,
          (SidHandle *)&pSid,
          v32[0],
          TokenInformation,
          v10,
          (__int64 *)&UserContextToken,
          &v23,
          (TokenHandle *)&v22);
  if ( v14 < 0 )
  {
    v27 = 0;
    pExceptionObject = &ComError::`vftable';
    v28 = v14;
    v29 = 452;
    v30 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v15 = *(_QWORD *)(a1 + 16);
  if ( *(_QWORD *)v15 != *(_QWORD *)v22 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 8), 0xFFFFFFFF) == 1 )
    {
      v16 = **(char ***)(a1 + 16);
      if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(v16);
        **(_QWORD **)(a1 + 16) = 0;
      }
      operator delete(*(void **)(a1 + 16), 0x10u);
      v17 = (volatile signed __int32 *)v22;
      *(_QWORD *)(a1 + 16) = v22;
      _InterlockedIncrement(v17 + 2);
    }
    else
    {
      v18 = (volatile signed __int32 *)v22;
      *(_QWORD *)(a1 + 16) = v22;
      _InterlockedIncrement(v18 + 2);
    }
  }
  *(_BYTE *)(a1 + 8) = 0;
  if ( !ImpersonateLoggedOnUser(**(HANDLE **)(a1 + 16)) )
  {
    v20 = GetLastError();
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    v27 = 0;
    pExceptionObject = &ComError::`vftable';
    v28 = v20;
    v29 = 0;
    v30 = 1;
    throw (ComError *)&pExceptionObject;
  }
  *(_BYTE *)(a1 + 8) = 1;
  if ( v13 )
    std::default_delete<AppPackageInfo>::operator()(v19, v13);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
  {
    operator delete(v7, 4u);
    operator delete(v5, 0);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22 + 2, 0xFFFFFFFF) == 1 )
  {
    v21 = v22;
    if ( (unsigned __int64)(*(_QWORD *)v22 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v22);
      *(_QWORD *)v22 = 0;
      v21 = v22;
    }
    operator delete(v21, 0x10u);
    v22 = 0;
  }
  if ( *a2 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a2 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a2, 0x10u);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x180019040  mov     [rsp-8+arg_0], rbx
0x180019045  mov     [rsp-8+arg_8], rdx
0x18001904a  push    rbp
0x18001904b  push    rsi
0x18001904c  push    rdi
0x18001904d  push    r12
0x18001904f  push    r13
0x180019051  push    r14
0x180019053  push    r15
0x180019055  lea     rbp, [rsp-27h]
0x18001905a  sub     rsp, 0F0h
0x180019061  mov     r15, rdx
0x180019064  mov     rsi, rcx
0x180019067  xor     edi, edi
0x180019069  lea     rbx, WPP_GLOBAL_Control
0x180019070  mov     rcx, cs:WPP_GLOBAL_Control
0x180019077  cmp     rcx, rbx
0x18001907a  jz      short loc_180019097
0x18001907c  test    byte ptr [rcx+1Ch], 1
0x180019080  jz      short loc_180019097
0x180019082  mov     edx, 13h
0x180019087  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18001908e  mov     rcx, [rcx+10h]
0x180019092  call    WPP_SF_
0x180019097  mov     edx, 8; dwFlags
0x18001909c  mov     r8d, 10h; dwBytes
0x1800190a2  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800190a9  call    cs:__imp_HeapAlloc
0x1800190af  test    rax, rax
0x1800190b2  jnz     short loc_180019115
0x1800190b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190bb  cmp     rcx, rbx
0x1800190be  jz      short loc_1800190E1
0x1800190c0  test    byte ptr [rcx+1Ch], 4
0x1800190c4  jz      short loc_1800190E1
0x1800190c6  mov     edx, 0Ah
0x1800190cb  mov     r9d, 10h
0x1800190d1  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800190d8  mov     rcx, [rcx+10h]
0x1800190dc  call    WPP_SF_d
0x1800190e1  xorps   xmm0, xmm0
0x1800190e4  movups  [rbp+57h+var_B8], xmm0
0x1800190e8  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800190ef  mov     [rbp+57h+pExceptionObject], rcx
0x1800190f3  mov     [rbp+57h+var_A8], 8007000Eh
0x1800190fa  mov     [rbp+57h+var_A4], edi
0x1800190fd  mov     [rbp+57h+var_A0], 1
0x180019104  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001910b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001910f  call    _CxxThrowException_0
0x180019115  mov     [rsp+120h+var_E0], rax
0x18001911a  mov     dword ptr [rax+8], 1
0x180019121  mov     rax, [rsp+120h+var_E0]
0x180019126  mov     [rax], rdi
0x180019129  mov     rcx, [rsi+10h]
0x18001912d  mov     rcx, [rcx]; TokenHandle
0x180019130  call    ?CopyTokenSid@@YAPEAXPEAX@Z; CopyTokenSid(void *)
0x180019135  mov     r12, rax
0x180019138  mov     [rbp+57h+var_48], rax
0x18001913c  mov     edx, 8; dwFlags
0x180019141  mov     r8d, 4; dwBytes
0x180019147  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18001914e  call    cs:__imp_HeapAlloc
0x180019154  mov     r14, rax
0x180019157  test    rax, rax
0x18001915a  jnz     short loc_1800191BD
0x18001915c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019163  cmp     rcx, rbx
0x180019166  jz      short loc_180019189
0x180019168  test    byte ptr [rcx+1Ch], 4
0x18001916c  jz      short loc_180019189
0x18001916e  mov     edx, 0Ah
0x180019173  mov     r9d, 4
0x180019179  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180019180  mov     rcx, [rcx+10h]
0x180019184  call    WPP_SF_d
0x180019189  xorps   xmm0, xmm0
0x18001918c  movups  [rbp+57h+var_B8], xmm0
0x180019190  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180019197  mov     [rbp+57h+pExceptionObject], rcx
0x18001919b  mov     [rbp+57h+var_A8], 8007000Eh
0x1800191a2  mov     [rbp+57h+var_A4], edi
0x1800191a5  mov     [rbp+57h+var_A0], 1
0x1800191ac  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800191b3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800191b7  call    _CxxThrowException_0
0x1800191bd  mov     dword ptr [rax], 1
0x1800191c3  mov     [rbp+57h+var_40], r14
0x1800191c7  mov     rdx, [rsi+10h]
0x1800191cb  mov     rdx, [rdx]
0x1800191ce  lea     rcx, [rbp+57h+var_58]
0x1800191d2  call    ?GetPackageInfoFromToken@@YA?AV?$unique_ptr@UAppPackageInfo@@U?$default_delete@UAppPackageInfo@@@std@@@std@@PEAX@Z; GetPackageInfoFromToken(void *)
0x1800191d7  nop
0x1800191d8  mov     dword ptr [rbp+57h+arg_18], edi
0x1800191db  mov     [rbp+57h+TokenInformation], edi
0x1800191de  mov     rcx, [rsi+10h]
0x1800191e2  lea     rax, [rbp+57h+arg_18]
0x1800191e6  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1800191eb  mov     r9d, 4; TokenInformationLength
0x1800191f1  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800191f5  mov     edx, 14h; TokenInformationClass
0x1800191fa  mov     rcx, [rcx]; TokenHandle
0x1800191fd  call    cs:__imp_GetTokenInformation
0x180019203  test    eax, eax
0x180019205  jnz     short loc_18001925B
0x180019207  call    cs:__imp_GetLastError
0x18001920d  test    eax, eax
0x18001920f  jg      short loc_180019219
0x180019211  call    cs:__imp_GetLastError
0x180019217  jmp     short loc_180019227
0x180019219  call    cs:__imp_GetLastError
0x18001921f  movzx   eax, ax
0x180019222  or      eax, 80070000h
0x180019227  xorps   xmm0, xmm0
0x18001922a  movups  [rbp+57h+var_B8], xmm0
0x18001922e  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180019235  mov     [rbp+57h+pExceptionObject], rcx
0x180019239  mov     [rbp+57h+var_A8], eax
0x18001923c  mov     [rbp+57h+var_A4], 1B5h
0x180019243  mov     [rbp+57h+var_A0], 1
0x18001924a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180019251  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019255  call    _CxxThrowException_0
0x18001925b  mov     eax, [rbp+57h+TokenInformation]
0x18001925e  mov     [rbp+57h+TokenInformation], eax
0x180019261  mov     rdx, [rsi+10h]
0x180019265  mov     rdx, [rdx]
0x180019268  lea     rcx, [rbp+57h+pSid]
0x18001926c  call    ?GetTokenIntegrityLevelSid@@YA?AVSidHandle@@PEAX@Z; GetTokenIntegrityLevelSid(void *)
0x180019271  mov     rbx, [rbp+57h+pSid]
0x180019275  mov     rcx, rbx; pSid
0x180019278  call    cs:__imp_GetSidSubAuthorityCount
0x18001927e  cmp     byte ptr [rax], 0
0x180019281  jnz     short loc_180019288
0x180019283  mov     r13d, edi
0x180019286  jmp     short loc_1800192A2
0x180019288  mov     rcx, rbx; pSid
0x18001928b  call    cs:__imp_GetSidSubAuthorityCount
0x180019291  movzx   edx, byte ptr [rax]
0x180019294  dec     edx; nSubAuthority
0x180019296  mov     rcx, rbx; pSid
0x180019299  call    cs:__imp_GetSidSubAuthority
0x18001929f  mov     r13d, [rax]
0x1800192a2  mov     rcx, [rbp+57h+var_C8]; void *
0x1800192a6  mov     edi, 0FFFFFFFFh
0x1800192ab  mov     eax, edi
0x1800192ad  lock xadd [rcx], eax
0x1800192b1  cmp     eax, 1
0x1800192b4  jnz     short loc_1800192CA
0x1800192b6  mov     edx, 4; unsigned __int64
0x1800192bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800192c0  xor     edx, edx; unsigned __int64
0x1800192c2  mov     rcx, rbx; void *
0x1800192c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800192ca  mov     rcx, [rsi+10h]
0x1800192ce  mov     rcx, [rcx]; void *
0x1800192d1  call    ?QueryUserContextToken@@YA_KPEAX@Z; QueryUserContextToken(void *)
0x1800192d6  mov     [rbp+57h+var_60], rax
0x1800192da  mov     rax, [r15]
0x1800192dd  lock inc dword ptr [rax+8]
0x1800192e1  mov     rax, [r15]
0x1800192e4  mov     [rbp+57h+arg_18], rax
0x1800192e8  lea     rdx, [rbp+57h+arg_18]
0x1800192ec  mov     rcx, rsi
0x1800192ef  call    ?UpdateServiceName@CNestedImpersonation@@AEAAXV?$GenericStringHandle@G@@@Z; CNestedImpersonation::UpdateServiceName(GenericStringHandle<ushort>)
0x1800192f4  mov     rax, [rsi+30h]
0x1800192f8  lock inc dword ptr [rax+8]
0x1800192fc  mov     rax, [rsi+30h]
0x180019300  mov     [rsp+120h+var_D8], rax
0x180019305  mov     [rbp+57h+pSid], r12
0x180019309  mov     [rbp+57h+var_C8], r14
0x18001930d  lock inc dword ptr [r14]
0x180019311  lea     rax, [rsp+120h+var_E0]
0x180019316  mov     [rsp+120h+var_E8], rax
0x18001931b  lea     rax, [rsp+120h+var_D8]
0x180019320  mov     [rsp+120h+var_F0], rax
0x180019325  lea     rax, [rbp+57h+var_60]
0x180019329  mov     [rsp+120h+var_F8], rax
0x18001932e  mov     dword ptr [rsp+120h+ReturnLength], r13d
0x180019333  mov     r9d, [rbp+57h+TokenInformation]
0x180019337  mov     rbx, [rbp+57h+var_58]
0x18001933b  mov     r8, rbx
0x18001933e  lea     rdx, [rbp+57h+pSid]
0x180019342  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180019349  call    ?CloneUserToken@CJobManager@@QEAAJVSidHandle@@PEAUAppPackageInfo@@HKPEA_KV?$GenericStringHandle@G@@PEAVTokenHandle@@@Z; CJobManager::CloneUserToken(SidHandle,AppPackageInfo *,int,ulong,unsigned __int64 *,GenericStringHandle<ushort>,TokenHandle *)
0x18001934e  test    eax, eax
0x180019350  jns     short loc_180019386
0x180019352  xorps   xmm0, xmm0
0x180019355  movups  [rbp+57h+var_B8], xmm0
0x180019359  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180019360  mov     [rbp+57h+pExceptionObject], rcx
0x180019364  mov     [rbp+57h+var_A8], eax
0x180019367  mov     [rbp+57h+var_A4], 1C4h
0x18001936e  mov     [rbp+57h+var_A0], 1
0x180019375  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001937c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019380  call    _CxxThrowException_0
0x180019386  mov     rdx, [rsi+10h]
0x18001938a  mov     rax, [rsp+120h+var_E0]
0x18001938f  mov     rcx, [rax]
0x180019392  cmp     [rdx], rcx
0x180019395  jz      short loc_1800193F8
0x180019397  mov     eax, edi
0x180019399  lock xadd [rdx+8], eax
0x18001939e  cmp     eax, 1
0x1800193a1  jnz     short loc_1800193E6
0x1800193a3  mov     rax, [rsi+10h]
0x1800193a7  mov     rcx, [rax]; hObject
0x1800193aa  lea     rax, [rcx-1]
0x1800193ae  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800193b2  ja      short loc_1800193C6
0x1800193b4  call    cs:__imp_CloseHandle
0x1800193ba  mov     rax, [rsi+10h]
0x1800193be  xor     r13d, r13d
0x1800193c1  mov     [rax], r13
0x1800193c4  jmp     short loc_1800193C9
0x1800193c6  xor     r13d, r13d
0x1800193c9  mov     edx, 10h; unsigned __int64
0x1800193ce  mov     rcx, [rsi+10h]; void *
0x1800193d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800193d7  mov     rax, [rsp+120h+var_E0]
0x1800193dc  mov     [rsi+10h], rax
0x1800193e0  lock inc dword ptr [rax+8]
0x1800193e4  jmp     short loc_1800193FB
0x1800193e6  xor     r13d, r13d
0x1800193e9  mov     rax, [rsp+120h+var_E0]
0x1800193ee  mov     [rsi+10h], rax
0x1800193f2  lock inc dword ptr [rax+8]
0x1800193f6  jmp     short loc_1800193FB
0x1800193f8  xor     r13d, r13d
0x1800193fb  mov     byte ptr [rsi+8], 0
0x1800193ff  mov     rcx, [rsi+10h]
0x180019403  mov     rcx, [rcx]; hToken
0x180019406  call    cs:__imp_ImpersonateLoggedOnUser
0x18001940c  test    eax, eax
0x18001940e  jnz     short loc_180019453
0x180019410  call    cs:__imp_GetLastError
0x180019416  test    eax, eax
0x180019418  jle     short loc_180019422
0x18001941a  movzx   eax, ax
0x18001941d  or      eax, 80070000h
0x180019422  xorps   xmm0, xmm0
0x180019425  movups  [rbp+57h+var_B8], xmm0
0x180019429  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180019430  mov     [rbp+57h+pExceptionObject], rcx
0x180019434  mov     [rbp+57h+var_A8], eax
0x180019437  mov     [rbp+57h+var_A4], r13d
0x18001943b  mov     [rbp+57h+var_A0], 1
0x180019442  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180019449  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001944d  call    _CxxThrowException_0
0x180019453  mov     byte ptr [rsi+8], 1
0x180019457  test    rbx, rbx
0x18001945a  jz      short loc_180019465
0x18001945c  mov     rdx, rbx
0x18001945f  call    ??R?$default_delete@UAppPackageInfo@@@std@@QEBAXPEAUAppPackageInfo@@@Z; std::default_delete<AppPackageInfo>::operator()(AppPackageInfo *)
0x180019464  nop
0x180019465  mov     eax, edi
0x180019467  lock xadd [r14], eax
0x18001946c  cmp     eax, 1
0x18001946f  jnz     short loc_180019489
0x180019471  mov     edx, 4; unsigned __int64
0x180019476  mov     rcx, r14; void *
0x180019479  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001947e  xor     edx, edx; unsigned __int64
0x180019480  mov     rcx, r12; void *
0x180019483  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019488  nop
0x180019489  mov     rcx, [rsp+120h+var_E0]
0x18001948e  mov     eax, edi
0x180019490  lock xadd [rcx+8], eax
0x180019495  cmp     eax, 1
0x180019498  jnz     short loc_1800194D1
0x18001949a  mov     rcx, [rsp+120h+var_E0]
0x18001949f  mov     rdx, [rcx]
0x1800194a2  lea     rax, [rdx-1]
0x1800194a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800194aa  ja      short loc_1800194C2
0x1800194ac  mov     rcx, rdx; hObject
0x1800194af  call    cs:__imp_CloseHandle
0x1800194b5  mov     rax, [rsp+120h+var_E0]
0x1800194ba  mov     [rax], r13
0x1800194bd  mov     rcx, [rsp+120h+var_E0]; void *
0x1800194c2  mov     edx, 10h; unsigned __int64
0x1800194c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800194cc  mov     [rsp+120h+var_E0], r13
0x1800194d1  mov     rax, [r15]
0x1800194d4  test    rax, rax
0x1800194d7  jz      short loc_1800194F3
0x1800194d9  lock xadd [rax+8], edi
0x1800194de  cmp     edi, 1
0x1800194e1  jnz     short loc_1800194F0
0x1800194e3  mov     edx, 10h; unsigned __int64
0x1800194e8  mov     rcx, [r15]; void *
0x1800194eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800194f0  mov     [r15], r13
0x1800194f3  mov     rbx, [rsp+120h+arg_0]
0x1800194fb  add     rsp, 0F0h
0x180019502  pop     r15
0x180019504  pop     r14
  ... truncated ...
```
