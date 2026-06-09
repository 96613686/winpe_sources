# Config::AdConfig::TranslateDn(ushort const *,ulong,FrsStringImpl<ushort,char> &)

- ea: `0x1401f3590`
- end: `0x1401f3c0d`
- name: `?TranslateDn@AdConfig@Config@@IEAAPEAVFrsStatus@@PEBGKAEAV?$FrsStringImpl@GD@@@Z`
- size: `1661`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1401ee0a0`
- `0x1401f3590`

## callees

- `0x14000c910`
- `0x14000cd1c`
- `0x14000e34c`
- `0x14000ee94`
- `0x140010680`
- `0x140022ce4`
- `0x140029390`
- `0x14004a5b8`
- `0x1401b9494`
- `0x1401de5cc`
- `0x1401e335c`
- `0x1401e3e58`
- `0x1401e52e8`
- `0x1401eab98`
- `0x1401f1be4`
- `0x1401f3590`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401f367d`
- `KERNEL32!GetCurrentThreadId` at `0x1401f37c6`
- `KERNEL32!GetCurrentThreadId` at `0x1401f37ee`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3855`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3a4a`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3acb`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3b4c`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3b80`
- `KERNEL32!GetCurrentThreadId` at `0x1401f367d`
- `KERNEL32!GetCurrentThreadId` at `0x1401f37c6`
- `KERNEL32!GetCurrentThreadId` at `0x1401f37ee`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3855`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3a4a`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3acb`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3b4c`
- `KERNEL32!GetCurrentThreadId` at `0x1401f3b80`

## string_xrefs

- `0x1401f3ba7`: `Config::AdConfig::TranslateDn`
- `0x1401f3649`: `Config::AdConfig::TranslateDn`
- `0x1401f36d5`: `Config::AdConfig::TranslateDn`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Config::AdConfig::TranslateDn(
        Config::AdConfig *a1,
        const unsigned __int16 *a2,
        enum DS_NAME_FORMAT a3,
        __int64 a4)
{
  const unsigned __int16 *v5; // r14
  __int64 v7; // rbx
  char v8; // al
  char *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rdx
  enum DS_NAME_FORMAT v14; // eax
  __int64 v15; // rcx
  struct FrsStatus *v16; // rdi
  const wchar_t *v17; // rax
  enum DS_NAME_FORMAT v18; // r9d
  __int64 v19; // rcx
  struct DS_NAME_RESULTW *v20; // rax
  PDS_NAME_RESULT_ITEMW v21; // r9
  LPCRITICAL_SECTION v22; // rcx
  const wchar_t *pDomain; // rax
  PDS_NAME_RESULT_ITEMW rItems; // rcx
  const wchar_t *pName; // rax
  int v27; // [rsp+38h] [rbp-49h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-41h]
  struct FrsStatus *v29; // [rsp+48h] [rbp-39h]
  const wchar_t *v30; // [rsp+58h] [rbp-29h] BYREF
  int v31; // [rsp+60h] [rbp-21h]
  int v32; // [rsp+64h] [rbp-1Dh]
  const wchar_t *v33; // [rsp+68h] [rbp-19h]
  unsigned __int16 *v34; // [rsp+70h] [rbp-11h] BYREF
  struct DS_NAME_RESULTW *v35; // [rsp+78h] [rbp-9h] BYREF
  enum DS_NAME_FORMAT v36; // [rsp+80h] [rbp-1h]
  struct FrsStatus *v37; // [rsp+88h] [rbp+7h] BYREF
  unsigned __int16 *v38; // [rsp+90h] [rbp+Fh] BYREF
  const wchar_t *v39; // [rsp+98h] [rbp+17h] BYREF
  unsigned __int16 *v40; // [rsp+A0h] [rbp+1Fh] BYREF
  const wchar_t *v41; // [rsp+E8h] [rbp+67h] BYREF
  const unsigned __int16 *v42; // [rsp+F0h] [rbp+6Fh] BYREF
  __int64 v43; // [rsp+100h] [rbp+7Fh]

  v43 = a4;
  v42 = a2;
  v5 = a2;
  v7 = 0;
  v35 = 0;
  v34 = &FrsStringImpl<unsigned short,char>::s_Empty;
  v8 = byte_140315A80;
  if ( !byte_140315A80 )
  {
    _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
    v5 = v42;
    v8 = 0;
  }
  v38 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v8 )
  {
    _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
    v5 = v42;
    v8 = byte_140315A80;
  }
  v40 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v8 )
  {
    _InterlockedAdd((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty, 1u);
    v5 = v42;
  }
  v9 = *(char **)(*((_QWORD *)a1 + 5) + 8LL);
  if ( (unsigned __int64)(v9 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v30 = L"Config::AdConfig::TranslateDn";
      v31 = 7313;
      v32 = 3;
      v33 = L"CFAD";
      dbgobj::DbgPrint<unsigned short>(&v30, L"Bind to DS is invalid");
    }
    v29 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v27 = 7314;
    v11 = 1;
    goto LABEL_13;
  }
  v14 = DS_NT4_ACCOUNT_NAME;
  if ( a3 != DS_USER_PRINCIPAL_NAME )
    v14 = a3;
  v36 = v14;
  v16 = Config::DsSession::CrackNames((Config::DsSession *)&v35, v9, v5, (enum DS_NAME_FORMAT)a4, v14, &v35);
  v37 = v16;
  if ( !v16 )
    goto LABEL_35;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
  {
    v30 = L"Config::AdConfig::TranslateDn";
    v31 = 7342;
    v32 = 2;
    v33 = L"CFAD";
    LODWORD(v41) = a3;
    v17 = L"<null>";
    if ( v5 )
      v17 = v5;
    v39 = v17;
    dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned long,FrsStatus>(
      (unsigned int)&v30,
      (unsigned int)L"Failed to CrackNames(). dn:%ws desiredFormat:%d Error:%?",
      (unsigned int)&v39,
      (unsigned int)&v41,
      (__int64)v16);
  }
  CLEAR_ERROR(&v37);
  v16 = Config::DsSession::Rebind((HANDLE *)(*((_QWORD *)a1 + 5) + 8LL), 0);
  if ( v16 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v30 = L"Config::AdConfig::TranslateDn";
      v31 = 7374;
      v32 = 3;
      v33 = L"CFAD";
      dbgobj::DbgPrint<unsigned short>(&v30, L"Failed to rebind to DS. Invalidating the connection to AD,DS");
    }
    Config::AdConfig::Disconnect(a1);
    v29 = v16;
    CurrentThreadId = GetCurrentThreadId();
    v27 = 7376;
    goto LABEL_82;
  }
  v16 = Config::DsSession::CrackNames(
          (Config::DsSession *)(unsigned int)v36,
          *(void **)(*((_QWORD *)a1 + 5) + 8LL),
          v5,
          v18,
          v36,
          &v35);
  v37 = v16;
  if ( !v16 )
  {
LABEL_35:
    v20 = v35;
    if ( v35 && v35->cItems && (v21 = v35->rItems) != 0 )
    {
      if ( v21->status )
      {
        if ( v21->status == 5 )
        {
          v16 = Config::DsSession::Rebind((HANDLE *)(*((_QWORD *)a1 + 5) + 8LL), v21->pDomain);
          if ( v16 )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
            {
              v30 = L"Config::AdConfig::TranslateDn";
              v31 = 7405;
              v32 = 3;
              v33 = L"CFAD";
              dbgobj::DbgPrint<unsigned short>(&v30, L"Failed to rebind to DS. Invalidating the connection to AD,DS");
            }
            Config::AdConfig::Disconnect(a1);
            v29 = v16;
            CurrentThreadId = GetCurrentThreadId();
            v27 = 7407;
            goto LABEL_82;
          }
          v16 = (struct FrsStatus *)Config::AdConfig::TranslateDn(a1, v5, (unsigned int)a3, &v34);
        }
        else
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v30 = L"Config::AdConfig::TranslateDn";
            v31 = 7412;
            v32 = 4;
            v33 = L"CFAD";
            dbgobj::DbgPrint<unsigned short,unsigned short const *,unsigned long>(
              &v30,
              L"CrackNames() dn:%ws status:%d",
              &v42);
          }
          if ( a3 == DS_NT4_ACCOUNT_NAME && !(unsigned int)Config::DsSession::GuessNt4Name(v15, v5, &v34) )
          {
            v29 = 0;
            CurrentThreadId = GetCurrentThreadId();
            v27 = 7415;
            goto LABEL_28;
          }
        }
      }
      else
      {
        v22 = g_DebugLog;
        if ( g_DebugLog )
        {
          if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v30 = L"Config::AdConfig::TranslateDn";
            v31 = 7390;
            v32 = 4;
            v33 = L"CFAD";
            pDomain = L"<null>";
            if ( v21->pDomain )
              pDomain = v21->pDomain;
            v41 = pDomain;
            dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v30, L"Cracked Domain:%ws", &v41);
            v20 = v35;
            v22 = g_DebugLog;
          }
          if ( v22 && LODWORD(v22[1].LockSemaphore) && SLODWORD(v22[1].OwningThread) >= 4 )
          {
            v30 = L"Config::AdConfig::TranslateDn";
            v31 = 7391;
            v32 = 4;
            v33 = L"CFAD";
            rItems = v20->rItems;
            pName = L"<null>";
            if ( rItems->pName )
              pName = rItems->pName;
            v41 = pName;
            dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v30, L"Cracked Name  :%ws", &v41);
            v20 = v35;
          }
        }
        FrsStringImpl<unsigned short,char>::Set(&v38, v20->rItems->pDomain);
        FrsStringImpl<unsigned short,char>::Set(&v34, v35->rItems->pName);
      }
    }
    else
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v30 = L"Config::AdConfig::TranslateDn";
        v31 = 7423;
        v32 = 4;
        v33 = L"CFAD";
        dbgobj::DbgPrint<unsigned short,unsigned short const *>(&v30, L"CrackNames() dn:%ws no status", &v42);
      }
      if ( a3 == DS_NT4_ACCOUNT_NAME && !(unsigned int)Config::DsSession::GuessNt4Name(v15, v5, &v34) )
      {
        v29 = 0;
        CurrentThreadId = GetCurrentThreadId();
        v27 = 7426;
        goto LABEL_28;
      }
    }
    if ( !v16 )
    {
      if ( a3 == DS_USER_PRINCIPAL_NAME && *((_QWORD *)v34 + 1) && *((_QWORD *)v38 + 1) )
        v16 = (struct FrsStatus *)Config::DsSession::FormUpn(v38, v34 + 9, v38 + 9, v43);
      else
        FrsStringImpl<unsigned short,char>::Set(v43, &v34);
      if ( !v16 )
        goto LABEL_84;
    }
    v29 = v16;
    CurrentThreadId = GetCurrentThreadId();
    v27 = 7440;
LABEL_82:
    v13 = *((unsigned int *)v16 + 1);
    v12 = *((unsigned int *)v16 + 2);
    v11 = *(unsigned int *)v16;
    goto LABEL_83;
  }
  if ( a3 != DS_NT4_ACCOUNT_NAME )
  {
    v29 = v16;
    CurrentThreadId = GetCurrentThreadId();
    v27 = 7370;
    goto LABEL_82;
  }
  CLEAR_ERROR(&v37);
  if ( !(unsigned int)Config::DsSession::GuessNt4Name(v19, v5, v43) )
  {
    v29 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v27 = 7368;
LABEL_28:
    v11 = 1;
LABEL_13:
    v12 = 0;
    v13 = 87;
LABEL_83:
    v7 = FrsStatusList::PushNewError(
           v10,
           v13,
           v12,
           v11,
           "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
           "Config::AdConfig::TranslateDn",
           v27,
           CurrentThreadId,
           v29);
  }
LABEL_84:
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v40);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v38);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v34);
  scoped_any<DS_NAME_RESULTW *,close_fun<void (*)(DS_NAME_RESULTW *),&void DsFreeNameResultW(DS_NAME_RESULTW *)>,null_t,0>::~scoped_any<DS_NAME_RESULTW *,close_fun<void (*)(DS_NAME_RESULTW *),&void DsFreeNameResultW(DS_NAME_RESULTW *)>,null_t,0>(&v35);
  return v7;
}

```

## disassembly

```asm
0x1401f3590  mov     rax, rsp
0x1401f3593  mov     [rax+18h], rbx
0x1401f3597  mov     [rax+20h], r9
0x1401f359b  mov     [rax+10h], rdx
0x1401f359f  push    rbp
0x1401f35a0  push    rsi
0x1401f35a1  push    rdi
0x1401f35a2  push    r12
0x1401f35a4  push    r13
0x1401f35a6  push    r14
0x1401f35a8  push    r15
0x1401f35aa  lea     rbp, [rax-5Fh]
0x1401f35ae  sub     rsp, 0A0h
0x1401f35b5  mov     r13d, r8d
0x1401f35b8  mov     r14, rdx
0x1401f35bb  mov     rsi, rcx
0x1401f35be  xor     ebx, ebx
0x1401f35c0  mov     [rbp+57h+var_60], rbx
0x1401f35c4  lea     rcx, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401f35cb  mov     [rbp+57h+var_68], rcx
0x1401f35cf  lea     edi, [rbx+1]
0x1401f35d2  mov     al, cs:byte_140315A80
0x1401f35d8  test    al, al
0x1401f35da  jnz     short loc_1401F35ED
0x1401f35dc  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, edi; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401f35e3  mov     r14, [rbp+57h+arg_8]
0x1401f35e7  mov     al, cs:byte_140315A80
0x1401f35ed  mov     [rbp+57h+var_48], rcx
0x1401f35f1  test    al, al
0x1401f35f3  jnz     short loc_1401F3606
0x1401f35f5  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, edi; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401f35fc  mov     r14, [rbp+57h+arg_8]
0x1401f3600  mov     al, cs:byte_140315A80
0x1401f3606  mov     [rbp+57h+var_38], rcx
0x1401f360a  test    al, al
0x1401f360c  jnz     short loc_1401F3619
0x1401f360e  lock add cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A, edi; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401f3615  mov     r14, [rbp+57h+arg_8]
0x1401f3619  mov     rax, [rsi+28h]
0x1401f361d  mov     rdx, [rax+8]; void *
0x1401f3621  lea     rax, [rdx-1]
0x1401f3625  mov     ecx, ebx
0x1401f3627  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401f362b  setbe   cl
0x1401f362e  test    ecx, ecx
0x1401f3630  jnz     short loc_1401F36A9
0x1401f3632  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f3639  test    rax, rax
0x1401f363c  jz      short loc_1401F367D
0x1401f363e  cmp     [rax+40h], ebx
0x1401f3641  jz      short loc_1401F367D
0x1401f3643  cmp     dword ptr [rax+38h], 3
0x1401f3647  jl      short loc_1401F367D
0x1401f3649  lea     r15, aConfigAdconfig_25; "Config::AdConfig::TranslateDn"
0x1401f3650  mov     [rbp+57h+var_80], r15
0x1401f3654  mov     [rbp+57h+var_78], 1C91h
0x1401f365b  mov     [rbp+57h+var_74], 3
0x1401f3662  lea     r12, aCfad; "CFAD"
0x1401f3669  mov     [rbp+57h+var_70], r12
0x1401f366d  lea     rdx, aBindToDsIsInva; "Bind to DS is invalid"
0x1401f3674  lea     rcx, [rbp+57h+var_80]
0x1401f3678  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401f367d  call    cs:__imp_GetCurrentThreadId
0x1401f3684  nop     dword ptr [rax+rax+00h]
0x1401f3689  mov     [rsp+40h], rbx
0x1401f368e  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401f3692  mov     [rsp+0D0h+var_A0], 1C92h
0x1401f369a  mov     r9d, edi
0x1401f369d  xor     r8d, r8d
0x1401f36a0  lea     edx, [r8+57h]
0x1401f36a4  jmp     loc_1401F3BA7
0x1401f36a9  mov     eax, 2
0x1401f36ae  cmp     r13d, 8
0x1401f36b2  cmovnz  eax, r13d
0x1401f36b6  mov     [rbp+57h+var_58], eax
0x1401f36b9  lea     rcx, [rbp+57h+var_60]; this
0x1401f36bd  mov     [rsp+0D0h+var_A8], rcx; struct DS_NAME_RESULTW **
0x1401f36c2  mov     [rsp+0D0h+var_B0], eax; enum DS_NAME_FORMAT
0x1401f36c6  mov     r8, r14; unsigned __int16 *
0x1401f36c9  call    ?CrackNames@DsSession@Config@@IEAAPEAVFrsStatus@@PEAXPEBGW4DS_NAME_FORMAT@@2PEAPEAUDS_NAME_RESULTW@@@Z; Config::DsSession::CrackNames(void *,ushort const *,DS_NAME_FORMAT,DS_NAME_FORMAT,DS_NAME_RESULTW * *)
0x1401f36ce  mov     rdi, rax
0x1401f36d1  mov     [rbp+57h+var_50], rax
0x1401f36d5  lea     r15, aConfigAdconfig_25; "Config::AdConfig::TranslateDn"
0x1401f36dc  lea     r12, aCfad; "CFAD"
0x1401f36e3  lea     rdx, aNull; "<null>"
0x1401f36ea  test    rax, rax
0x1401f36ed  jz      loc_1401F387E
0x1401f36f3  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f36fa  test    rax, rax
0x1401f36fd  jz      short loc_1401F374F
0x1401f36ff  cmp     [rax+40h], ebx
0x1401f3702  jz      short loc_1401F374F
0x1401f3704  cmp     dword ptr [rax+38h], 2
0x1401f3708  jl      short loc_1401F374F
0x1401f370a  mov     [rbp+57h+var_80], r15
0x1401f370e  mov     [rbp+57h+var_78], 1CAEh
0x1401f3715  mov     [rbp+57h+var_74], 2
0x1401f371c  mov     [rbp+57h+var_70], r12
0x1401f3720  mov     dword ptr [rbp+57h+arg_0], r13d
0x1401f3724  mov     rax, rdx
0x1401f3727  test    r14, r14
0x1401f372a  cmovnz  rax, r14
0x1401f372e  mov     [rbp+57h+var_40], rax
0x1401f3732  mov     qword ptr [rsp+0D0h+var_B0], rdi
0x1401f3737  lea     r9, [rbp+57h+arg_0]
0x1401f373b  lea     r8, [rbp+57h+var_40]
0x1401f373f  lea     rdx, aFailedToCrackn; "Failed to CrackNames(). dn:%ws desiredF"...
0x1401f3746  lea     rcx, [rbp+57h+var_80]
0x1401f374a  call    ??$DbgPrint@GPEBGKVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBKAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,ulong,FrsStatus>(ushort const *,ushort const * const &,ulong const &,FrsStatus const &)
0x1401f374f  lea     rcx, [rbp+57h+var_50]; struct FrsStatus **
0x1401f3753  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401f3758  mov     rcx, [rsi+28h]
0x1401f375c  add     rcx, 8; phDS
0x1401f3760  xor     edx, edx; DnsDomainName
0x1401f3762  call    ?Rebind@DsSession@Config@@QEAAPEAVFrsStatus@@PEBG@Z; Config::DsSession::Rebind(ushort const *)
0x1401f3767  mov     rdi, rax
0x1401f376a  test    rax, rax
0x1401f376d  jnz     loc_1401F3810
0x1401f3773  mov     rax, [rsi+28h]
0x1401f3777  lea     rcx, [rbp+57h+var_60]
0x1401f377b  mov     [rsp+0D0h+var_A8], rcx; struct DS_NAME_RESULTW **
0x1401f3780  mov     ecx, [rbp+57h+var_58]; this
0x1401f3783  mov     [rsp+0D0h+var_B0], ecx; enum DS_NAME_FORMAT
0x1401f3787  mov     r8, r14; unsigned __int16 *
0x1401f378a  mov     rdx, [rax+8]; void *
0x1401f378e  call    ?CrackNames@DsSession@Config@@IEAAPEAVFrsStatus@@PEAXPEBGW4DS_NAME_FORMAT@@2PEAPEAUDS_NAME_RESULTW@@@Z; Config::DsSession::CrackNames(void *,ushort const *,DS_NAME_FORMAT,DS_NAME_FORMAT,DS_NAME_RESULTW * *)
0x1401f3793  mov     rdi, rax
0x1401f3796  mov     [rbp+57h+var_50], rax
0x1401f379a  test    rax, rax
0x1401f379d  jz      loc_1401F3877
0x1401f37a3  cmp     r13d, 2
0x1401f37a7  jnz     short loc_1401F37EE
0x1401f37a9  lea     rcx, [rbp+57h+var_50]; struct FrsStatus **
0x1401f37ad  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401f37b2  mov     r8, [rbp+57h+arg_18]
0x1401f37b6  mov     rdx, r14
0x1401f37b9  call    ?GuessNt4Name@DsSession@Config@@QEBAHPEBGAEAV?$FrsStringImpl@GD@@@Z; Config::DsSession::GuessNt4Name(ushort const *,FrsStringImpl<ushort,char> &)
0x1401f37be  test    eax, eax
0x1401f37c0  jnz     loc_1401F3BC7
0x1401f37c6  call    cs:__imp_GetCurrentThreadId
0x1401f37cd  nop     dword ptr [rax+rax+00h]
0x1401f37d2  mov     [rsp+40h], rbx
0x1401f37d7  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401f37db  mov     [rsp+0D0h+var_A0], 1CC8h
0x1401f37e3  mov     r9d, 1
0x1401f37e9  jmp     loc_1401F369D
0x1401f37ee  call    cs:__imp_GetCurrentThreadId
0x1401f37f5  nop     dword ptr [rax+rax+00h]
0x1401f37fa  mov     [rsp+40h], rdi
0x1401f37ff  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401f3803  mov     [rsp+0D0h+var_A0], 1CCAh
0x1401f380b  jmp     loc_1401F3B9D
0x1401f3810  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f3817  test    rax, rax
0x1401f381a  jz      short loc_1401F384D
0x1401f381c  cmp     [rax+40h], ebx
0x1401f381f  jz      short loc_1401F384D
0x1401f3821  cmp     dword ptr [rax+38h], 3
0x1401f3825  jl      short loc_1401F384D
0x1401f3827  mov     [rbp+57h+var_80], r15
0x1401f382b  mov     [rbp+57h+var_78], 1CCEh
0x1401f3832  mov     [rbp+57h+var_74], 3
0x1401f3839  mov     [rbp+57h+var_70], r12
0x1401f383d  lea     rdx, aFailedToRebind; "Failed to rebind to DS. Invalidating th"...
0x1401f3844  lea     rcx, [rbp+57h+var_80]
0x1401f3848  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401f384d  mov     rcx, rsi; this
0x1401f3850  call    ?Disconnect@AdConfig@Config@@QEAAXXZ; Config::AdConfig::Disconnect(void)
0x1401f3855  call    cs:__imp_GetCurrentThreadId
0x1401f385c  nop     dword ptr [rax+rax+00h]
0x1401f3861  mov     [rsp+40h], rdi
0x1401f3866  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401f386a  mov     [rsp+0D0h+var_A0], 1CD0h
0x1401f3872  jmp     loc_1401F3B9D
0x1401f3877  lea     rdx, aNull; "<null>"
0x1401f387e  mov     rax, [rbp+57h+var_60]
0x1401f3882  test    rax, rax
0x1401f3885  jz      loc_1401F3AED
0x1401f388b  cmp     [rax], ebx
0x1401f388d  jz      loc_1401F3AED
0x1401f3893  mov     r9, [rax+8]
0x1401f3897  test    r9, r9
0x1401f389a  jz      loc_1401F3AED
0x1401f38a0  cmp     [r9], ebx
0x1401f38a3  jnz     loc_1401F39C8
0x1401f38a9  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f38b0  test    rcx, rcx
0x1401f38b3  jz      loc_1401F395A
0x1401f38b9  mov     esi, 4
0x1401f38be  cmp     [rcx+40h], ebx
0x1401f38c1  jz      short loc_1401F3909
0x1401f38c3  cmp     [rcx+38h], esi
0x1401f38c6  jl      short loc_1401F3909
0x1401f38c8  mov     [rbp+57h+var_80], r15
0x1401f38cc  mov     [rbp+57h+var_78], 1CDEh
0x1401f38d3  mov     [rbp+57h+var_74], esi
0x1401f38d6  mov     [rbp+57h+var_70], r12
0x1401f38da  mov     rax, rdx
0x1401f38dd  cmp     [r9+8], rbx
0x1401f38e1  cmovnz  rax, [r9+8]
0x1401f38e6  mov     [rbp+57h+arg_0], rax
0x1401f38ea  lea     r8, [rbp+57h+arg_0]
0x1401f38ee  lea     rdx, aCrackedDomainW; "Cracked Domain:%ws"
0x1401f38f5  lea     rcx, [rbp+57h+var_80]
0x1401f38f9  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401f38fe  mov     rax, [rbp+57h+var_60]
0x1401f3902  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f3909  test    rcx, rcx
0x1401f390c  jz      short loc_1401F395A
0x1401f390e  cmp     [rcx+40h], ebx
0x1401f3911  jz      short loc_1401F395A
0x1401f3913  cmp     [rcx+38h], esi
0x1401f3916  jl      short loc_1401F395A
0x1401f3918  mov     [rbp+57h+var_80], r15
0x1401f391c  mov     [rbp+57h+var_78], 1CDFh
0x1401f3923  mov     [rbp+57h+var_74], esi
0x1401f3926  mov     [rbp+57h+var_70], r12
0x1401f392a  mov     rcx, [rax+8]
0x1401f392e  cmp     [rcx+10h], rbx
0x1401f3932  lea     rax, aNull; "<null>"
0x1401f3939  cmovnz  rax, [rcx+10h]
0x1401f393e  mov     [rbp+57h+arg_0], rax
0x1401f3942  lea     r8, [rbp+57h+arg_0]
0x1401f3946  lea     rdx, aCrackedNameWs; "Cracked Name  :%ws"
0x1401f394d  lea     rcx, [rbp+57h+var_80]
0x1401f3951  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401f3956  mov     rax, [rbp+57h+var_60]
0x1401f395a  mov     rcx, [rax+8]
0x1401f395e  mov     rdx, [rcx+8]
0x1401f3962  lea     rcx, [rbp+57h+var_48]
0x1401f3966  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401f396b  mov     rax, [rbp+57h+var_60]
0x1401f396f  mov     rcx, [rax+8]
0x1401f3973  mov     rdx, [rcx+10h]
0x1401f3977  lea     rcx, [rbp+57h+var_68]
0x1401f397b  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401f3980  test    rdi, rdi
0x1401f3983  jnz     loc_1401F3B80
0x1401f3989  cmp     r13d, 8
0x1401f398d  jnz     loc_1401F3B6E
0x1401f3993  mov     rax, [rbp+57h+var_68]
0x1401f3997  cmp     [rax+8], rbx
0x1401f399b  jz      loc_1401F3B6E
0x1401f39a1  mov     rcx, [rbp+57h+var_48]
0x1401f39a5  cmp     [rcx+8], rbx
0x1401f39a9  jz      loc_1401F3B6E
0x1401f39af  lea     r8, [rcx+12h]
0x1401f39b3  lea     rdx, [rax+12h]
0x1401f39b7  mov     r9, [rbp+57h+arg_18]
0x1401f39bb  call    ?FormUpn@DsSession@Config@@IEAAPEAVFrsStatus@@PEBG0AEAV?$FrsStringImpl@GD@@@Z; Config::DsSession::FormUpn(ushort const *,ushort const *,FrsStringImpl<ushort,char> &)
0x1401f39c0  mov     rdi, rax
0x1401f39c3  jmp     loc_1401F3B7B
0x1401f39c8  cmp     dword ptr [r9], 5
0x1401f39cc  jnz     loc_1401F3A6C
0x1401f39d2  mov     rcx, [rsi+28h]
0x1401f39d6  add     rcx, 8; phDS
0x1401f39da  mov     rdx, [r9+8]; DnsDomainName
0x1401f39de  call    ?Rebind@DsSession@Config@@QEAAPEAVFrsStatus@@PEBG@Z; Config::DsSession::Rebind(ushort const *)
0x1401f39e3  mov     rdi, rax
0x1401f39e6  test    rax, rax
0x1401f39e9  jnz     short loc_1401F3A05
0x1401f39eb  lea     r9, [rbp+57h+var_68]
0x1401f39ef  mov     r8d, r13d
0x1401f39f2  mov     rdx, r14
0x1401f39f5  mov     rcx, rsi
0x1401f39f8  call    ?TranslateDn@AdConfig@Config@@IEAAPEAVFrsStatus@@PEBGKAEAV?$FrsStringImpl@GD@@@Z; Config::AdConfig::TranslateDn(ushort const *,ulong,FrsStringImpl<ushort,char> &)
0x1401f39fd  mov     rdi, rax
0x1401f3a00  jmp     loc_1401F3980
0x1401f3a05  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f3a0c  test    rax, rax
0x1401f3a0f  jz      short loc_1401F3A42
0x1401f3a11  cmp     [rax+40h], ebx
0x1401f3a14  jz      short loc_1401F3A42
0x1401f3a16  cmp     dword ptr [rax+38h], 3
0x1401f3a1a  jl      short loc_1401F3A42
0x1401f3a1c  mov     [rbp+57h+var_80], r15
0x1401f3a20  mov     [rbp+57h+var_78], 1CEDh
0x1401f3a27  mov     [rbp+57h+var_74], 3
0x1401f3a2e  mov     [rbp+57h+var_70], r12
0x1401f3a32  lea     rdx, aFailedToRebind; "Failed to rebind to DS. Invalidating th"...
0x1401f3a39  lea     rcx, [rbp+57h+var_80]
0x1401f3a3d  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401f3a42  mov     rcx, rsi; this
0x1401f3a45  call    ?Disconnect@AdConfig@Config@@QEAAXXZ; Config::AdConfig::Disconnect(void)
0x1401f3a4a  call    cs:__imp_GetCurrentThreadId
0x1401f3a51  nop     dword ptr [rax+rax+00h]
0x1401f3a56  mov     [rsp+40h], rdi
0x1401f3a5b  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401f3a5f  mov     [rsp+0D0h+var_A0], 1CEFh
0x1401f3a67  jmp     loc_1401F3B9D
0x1401f3a6c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401f3a73  test    rax, rax
0x1401f3a76  jz      short loc_1401F3AAD
0x1401f3a78  cmp     [rax+40h], ebx
0x1401f3a7b  jz      short loc_1401F3AAD
0x1401f3a7d  mov     esi, 4
0x1401f3a82  cmp     [rax+38h], esi
0x1401f3a85  jl      short loc_1401F3AAD
0x1401f3a87  mov     [rbp+57h+var_80], r15
0x1401f3a8b  mov     [rbp+57h+var_78], 1CF4h
  ... truncated ...
```
