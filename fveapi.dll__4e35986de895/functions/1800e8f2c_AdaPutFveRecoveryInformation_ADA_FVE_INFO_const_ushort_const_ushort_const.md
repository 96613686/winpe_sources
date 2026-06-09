# AdaPutFveRecoveryInformation(_ADA_FVE_INFO const *,ushort const *,ushort const *)

- ea: `0x1800e8f2c`
- end: `0x1800e97fb`
- name: `?AdaPutFveRecoveryInformation@@YAJPEBU_ADA_FVE_INFO@@PEBG1@Z`
- size: `2255`
- prototype: `__int64 __fastcall(const struct _ADA_FVE_INFO *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800caf70`

## callees

- `0x1800090c0`
- `0x18000aae0`
- `0x180023800`
- `0x1800600c0`
- `0x1800e88d4`
- `0x1800e8f2c`
- `0x1800ea0bc`
- `0x1800ea100`
- `0x1800ea16c`
- `0x180129010`

## import_xrefs

- `msvcrt!_scwprintf` at `0x1800e9668`
- `msvcrt!_scwprintf` at `0x1800e9668`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800e9048`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800e905c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800e9048`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800e905c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e93ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e93ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9410`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e938b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e938b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e93aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e93aa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e9084`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e9084`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e97c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e97c1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e9400`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e9400`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e97d8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e97d8`
- `RPCRT4!RpcImpersonateClient` at `0x1800e97a7`
- `RPCRT4!RpcImpersonateClient` at `0x1800e97a7`
- `RPCRT4!RpcRevertToSelf` at `0x1800e944c`
- `RPCRT4!RpcRevertToSelf` at `0x1800e944c`

## pseudocode

```c
__int64 __fastcall AdaPutFveRecoveryInformation(
        const struct _ADA_FVE_INFO *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void *v3; // r12
  _DWORD *v4; // r14
  bool v5; // r13
  __int64 v7; // r9
  signed int v8; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  unsigned __int16 *v11; // r15
  unsigned __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned __int64 v14; // rdx
  unsigned int v15; // eax
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // eax
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // rcx
  const struct _GUID *v21; // r8
  BOOL IsComImpersonating; // eax
  bool v23; // zf
  signed int LastError; // eax
  signed int v25; // eax
  RPC_STATUS v26; // eax
  unsigned int v27; // eax
  unsigned __int64 v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rax
  char *v34; // rax
  char *v35; // rcx
  char *v36; // r15
  unsigned __int64 v37; // rbx
  unsigned __int64 v38; // rax
  unsigned __int16 *v39; // rax
  unsigned int v40; // eax
  signed int v41; // eax
  unsigned __int16 *v43; // [rsp+30h] [rbp-99h]
  void *v44; // [rsp+38h] [rbp-91h] BYREF
  HANDLE Token; // [rsp+40h] [rbp-89h] BYREF
  __int64 v46; // [rsp+48h] [rbp-81h] BYREF
  void *Thread; // [rsp+50h] [rbp-79h] BYREF
  __int64 v48; // [rsp+58h] [rbp-71h] BYREF
  __int128 v49; // [rsp+60h] [rbp-69h]
  __int64 v50; // [rsp+70h] [rbp-59h] BYREF
  __int128 v51; // [rsp+78h] [rbp-51h]
  __int64 v52; // [rsp+88h] [rbp-41h] BYREF
  __int128 v53; // [rsp+90h] [rbp-39h]
  char *v54; // [rsp+A0h] [rbp-29h]
  __int64 v55; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-19h]
  __int64 v57; // [rsp+C0h] [rbp-9h] BYREF
  __int128 v58; // [rsp+C8h] [rbp-1h]
  unsigned __int64 v59; // [rsp+130h] [rbp+67h] BYREF
  const unsigned __int16 *v60; // [rsp+138h] [rbp+6Fh] BYREF
  const unsigned __int16 *v61; // [rsp+140h] [rbp+77h]
  int v62; // [rsp+148h] [rbp+7Fh] BYREF

  v61 = a3;
  v60 = a2;
  v3 = 0;
  v55 = 0;
  v50 = 0;
  v4 = 0;
  Thread = 0;
  v5 = 0;
  Token = (HANDLE)-1LL;
  v52 = 0;
  v57 = 0;
  v44 = 0;
  v46 = 0;
  v43 = 0;
  LOBYTE(v60) = 0;
  v62 = 0;
  LOBYTE(v61) = 0;
  v48 = 0;
  v56 = 0;
  v51 = 0;
  v53 = 0;
  v58 = 0;
  v49 = 0;
  if ( !a1 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return (unsigned int)v8;
    v10 = 10;
    goto LABEL_5;
  }
  if ( !*(_DWORD *)a1 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return (unsigned int)v8;
    v10 = 11;
    goto LABEL_5;
  }
  if ( (*(_BYTE *)a1 & 1) == 0 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return (unsigned int)v8;
    v10 = 12;
    goto LABEL_5;
  }
  if ( (*(_BYTE *)a1 & 4) == 0 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return (unsigned int)v8;
    v10 = 13;
    goto LABEL_5;
  }
  if ( (*(_BYTE *)a1 & 8) == 0 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return (unsigned int)v8;
    v10 = 14;
    goto LABEL_5;
  }
  v12 = *((_QWORD *)a1 + 22);
  v54 = (char *)a1 + 40;
  if ( v12 > 0x40 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return (unsigned int)v8;
    v10 = 15;
    goto LABEL_5;
  }
  v13 = StringCchLengthW((const unsigned __int16 *)a1 + 20, v12 + 1, &v59);
  v8 = v13;
  if ( v13 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v13);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 < 0 )
      goto LABEL_6;
  }
  else
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v14 = *((_QWORD *)a1 + 39);
  if ( v14 <= 0x3F )
  {
    v15 = StringCchLengthW((const unsigned __int16 *)a1 + 92, v14 + 1, &v59);
    v8 = v15;
    if ( v15 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v15);
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 < 0 )
        goto LABEL_6;
    }
    else
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v16 = 3;
    if ( (*(_BYTE *)a1 & 0x10) != 0 )
    {
      if ( *((_QWORD *)a1 + 552) > 0x1000u )
      {
        v7 = 2147942487LL;
        v8 = -2147024809;
        if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 0x40) == 0 )
          goto LABEL_6;
        v10 = 19;
        goto LABEL_5;
      }
      v16 = 4;
    }
    v17 = v16 + 1;
    if ( (*(_BYTE *)a1 & 2) == 0 )
      v17 = v16;
    LODWORD(v59) = v17;
    v18 = AdapInitializeCOM((bool *)&v60);
    v8 = v18;
    if ( v18 )
    {
      v20 = (const unsigned __int16 *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v18);
      if ( v8 < 0 )
        goto LABEL_6;
    }
    if ( NtCurrentTeb()->IsImpersonating )
    {
      IsComImpersonating = AdapIsComImpersonating();
      v8 = IsComImpersonating;
      if ( IsComImpersonating )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
            IsComImpersonating);
        v23 = v8 == 0;
        if ( v8 < 0 )
          goto LABEL_6;
      }
      else
      {
        v23 = 1;
      }
      v5 = v23;
      Thread = GetCurrentThread();
      if ( !OpenThreadToken(Thread, 4u, 0, &Token) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_6;
        v10 = 22;
        goto LABEL_83;
      }
      if ( v8 )
      {
        v26 = RpcRevertToSelf();
        v8 = v26;
        if ( v26 )
        {
          if ( v26 > 0 )
            v8 = (unsigned __int16)v26 | 0x80070000;
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
            goto LABEL_6;
          v10 = 24;
LABEL_83:
          v7 = (unsigned int)v8;
          goto LABEL_5;
        }
      }
      else if ( !RevertToSelf() )
      {
        v25 = GetLastError();
        v8 = v25;
        if ( v25 > 0 )
          v8 = (unsigned __int16)v25 | 0x80070000;
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_6;
        v10 = 23;
        goto LABEL_83;
      }
      LOBYTE(v61) = 1;
    }
    v27 = AdapOpenComputerObject(v20, v19, v21, &v44);
    v8 = v27;
    if ( !v27 )
      goto LABEL_103;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v27);
    if ( v8 >= 0 )
    {
LABEL_103:
      v28 = 32LL * (unsigned int)v59;
      if ( !is_mul_ok((unsigned int)v59, 0x20u) )
        v28 = -1;
      v29 = operator new[](v28, (const struct std::nothrow_t *)&std::nothrow);
      v4 = v29;
      if ( !v29 )
      {
        v8 = -2147024882;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_110;
        v31 = 26;
        goto LABEL_109;
      }
      *v29 = L"objectClass";
      v29[2] = &v55;
      *((_DWORD *)v29 + 2) = 2;
      *((_DWORD *)v29 + 6) = 1;
      *((_DWORD *)v29 + 3) = 3;
      v29[4] = L"msFVE-RecoveryPassword";
      *((_DWORD *)v29 + 10) = 2;
      v29[6] = &v57;
      *((_DWORD *)v29 + 11) = 5;
      *((_DWORD *)v29 + 14) = 1;
      v29[8] = L"msFVE-RecoveryGuid";
      v29[10] = &v52;
      v32 = 2;
      v4[18] = 2;
      v4[19] = 8;
      v4[22] = 1;
      if ( (*(_BYTE *)a1 & 2) != 0 )
      {
        v4[26] = 2;
        *((_QWORD *)v4 + 12) = L"msFVE-VolumeGuid";
        *((_QWORD *)v4 + 14) = &v48;
        v4[27] = 8;
        v4[30] = 1;
        *((_QWORD *)&v49 + 1) = (char *)a1 + 20;
        v32 = 3;
        LODWORD(v48) = 8;
        LODWORD(v49) = 16;
      }
      if ( (*(_BYTE *)a1 & 0x10) != 0 )
      {
        v33 = 8 * (v32 + 1);
        *(_QWORD *)&v4[v33] = L"msFVE-KeyPackage";
        *(_QWORD *)&v4[v33 + 4] = &v50;
        v4[v33 + 2] = 2;
        v4[v33 + 3] = 8;
        v4[v33 + 6] = 1;
        LODWORD(v51) = *((_DWORD *)a1 + 1104);
        LODWORD(v50) = 8;
        *((_QWORD *)&v51 + 1) = (char *)a1 + 320;
      }
      v34 = (char *)a1 + 4;
      LODWORD(v57) = 5;
      LODWORD(v55) = 3;
      *(_QWORD *)&v56 = L"msFVE-RecoveryInformation";
      v35 = (char *)a1 + 184;
      v36 = v54;
      *(_QWORD *)&v58 = v35;
      LODWORD(v52) = 8;
      LODWORD(v53) = 16;
      *((_QWORD *)&v53 + 1) = v34;
      v37 = _scwprintf(L"CN=%s", v54) + 1;
      v38 = 2 * v37;
      if ( !is_mul_ok(v37, 2u) )
        v38 = -1;
      v39 = (unsigned __int16 *)operator new[](v38, (const struct std::nothrow_t *)&std::nothrow);
      v43 = v39;
      if ( v39 )
      {
        v40 = StringCchPrintfW(v39, v37, L"CN=%s", v36);
        v8 = v40;
        if ( !v40 )
          goto LABEL_126;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v40);
        if ( v8 >= 0 )
        {
LABEL_126:
          v3 = v44;
          v11 = v43;
          v41 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, _DWORD *, _QWORD, __int64 *))(*(_QWORD *)v44 + 48LL))(
                  v44,
                  v43,
                  v4,
                  (unsigned int)v59,
                  &v46);
          v8 = v41;
          if ( v41 == -2147016694 )
          {
            if ( (int)AdaIsSchemaExtInstalled(&v62) >= 0 && !v62 )
              v8 = -2144272374;
          }
          else if ( !v41 )
          {
            goto LABEL_7;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
              (unsigned int)v8);
          goto LABEL_7;
        }
        goto LABEL_110;
      }
      v8 = -2147024882;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v31 = 27;
LABEL_109:
        WPP_SF_d(v30[2], v31, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, 2147942414LL);
      }
    }
LABEL_110:
    v3 = v44;
    v11 = v43;
    goto LABEL_7;
  }
  v7 = 2147942487LL;
  v8 = -2147024809;
  if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 0x40) == 0 )
    goto LABEL_6;
  v10 = 17;
LABEL_5:
  WPP_SF_d(v9[2], v10, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v7);
LABEL_6:
  v11 = 0;
LABEL_7:
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v3 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v11 )
    operator delete[](v11);
  if ( v4 )
    operator delete[](v4);
  if ( (_BYTE)v61 )
  {
    if ( v5 )
      SetThreadToken(&Thread, Token);
    else
      RpcImpersonateClient(0);
  }
  if ( Token != (HANDLE)-1LL )
  {
    CloseHandle(Token);
    Token = (HANDLE)-1LL;
  }
  if ( (_BYTE)v60 )
    CoUninitialize();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800e8f2c  mov     [rsp-8+arg_10], r8
0x1800e8f31  mov     [rsp-8+arg_8], rdx
0x1800e8f36  push    rbp
0x1800e8f37  push    rbx
0x1800e8f38  push    rsi
0x1800e8f39  push    rdi
0x1800e8f3a  push    r12
0x1800e8f3c  push    r13
0x1800e8f3e  push    r14
0x1800e8f40  push    r15
0x1800e8f42  lea     rbp, [rsp-1Fh]
0x1800e8f47  sub     rsp, 0E8h
0x1800e8f4e  xor     r12d, r12d
0x1800e8f51  mov     [rbp+57h+var_78], 0
0x1800e8f59  xorps   xmm0, xmm0
0x1800e8f5c  mov     [rbp+57h+var_B0], 0
0x1800e8f64  xor     r14d, r14d
0x1800e8f67  mov     [rbp+57h+Thread], 0
0x1800e8f6f  xor     r13b, r13b
0x1800e8f72  mov     [rsp+120h+Token], 0FFFFFFFFFFFFFFFFh
0x1800e8f7b  mov     [rbp+57h+var_98], 0
0x1800e8f83  mov     r15, rcx
0x1800e8f86  mov     [rbp+57h+var_60], r14
0x1800e8f8a  mov     [rsp+120h+var_E8], r12
0x1800e8f8f  mov     [rsp+120h+var_D8], r12
0x1800e8f94  mov     [rsp+120h+var_F0], r12
0x1800e8f99  mov     byte ptr [rbp+57h+arg_8], r12b
0x1800e8f9d  mov     [rbp+57h+arg_18], r12d
0x1800e8fa1  mov     byte ptr [rbp+57h+arg_10], r12b
0x1800e8fa5  mov     [rbp+57h+var_C8], r12
0x1800e8fa9  movdqu  [rbp+57h+var_70], xmm0
0x1800e8fae  movdqu  [rbp+57h+var_A8], xmm0
0x1800e8fb3  movdqu  [rbp+57h+var_90], xmm0
0x1800e8fb8  movdqu  [rbp+57h+var_58], xmm0
0x1800e8fbd  movdqu  [rbp+57h+var_C0], xmm0
0x1800e8fc2  test    rcx, rcx
0x1800e8fc5  jnz     loc_1800E9095
0x1800e8fcb  mov     r9d, 80070057h
0x1800e8fd1  mov     ebx, r9d
0x1800e8fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8fdb  lea     rdi, WPP_GLOBAL_Control
0x1800e8fe2  cmp     rcx, rdi
0x1800e8fe5  jz      loc_1800E97E4
0x1800e8feb  test    byte ptr [rcx+1Ch], 40h
0x1800e8fef  jz      loc_1800E97E4
0x1800e8ff5  lea     edx, [r15+0Ah]
0x1800e8ff9  lea     r8, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e9000  mov     rcx, [rcx+10h]
0x1800e9004  call    WPP_SF_d
0x1800e9009  mov     r15, r12
0x1800e900c  mov     rcx, [rsp+120h+var_D8]
0x1800e9011  test    rcx, rcx
0x1800e9014  jz      short loc_1800E902B
0x1800e9016  mov     rax, [rcx]
0x1800e9019  mov     rax, [rax+10h]
0x1800e901d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9022  mov     [rsp+120h+var_D8], 0
0x1800e902b  test    r12, r12
0x1800e902e  jz      short loc_1800E9040
0x1800e9030  mov     rax, [r12]
0x1800e9034  mov     rcx, r12
0x1800e9037  mov     rax, [rax+10h]
0x1800e903b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9040  test    r15, r15
0x1800e9043  jz      short loc_1800E9054
0x1800e9045  mov     rcx, r15
0x1800e9048  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800e904f  nop     dword ptr [rax+rax+00h]
0x1800e9054  test    r14, r14
0x1800e9057  jz      short loc_1800E9068
0x1800e9059  mov     rcx, r14
0x1800e905c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800e9063  nop     dword ptr [rax+rax+00h]
0x1800e9068  cmp     byte ptr [rbp+57h+arg_10], 0
0x1800e906c  jz      loc_1800E97B3
0x1800e9072  test    r13b, r13b
0x1800e9075  jz      loc_1800E97A5
0x1800e907b  mov     rdx, [rsp+120h+Token]; Token
0x1800e9080  lea     rcx, [rbp+57h+Thread]; Thread
0x1800e9084  call    cs:__imp_SetThreadToken
0x1800e908b  nop     dword ptr [rax+rax+00h]
0x1800e9090  jmp     loc_1800E97B3
0x1800e9095  cmp     [rcx], r12d
0x1800e9098  jnz     short loc_1800E90CE
0x1800e909a  mov     r9d, 80070057h
0x1800e90a0  mov     ebx, r9d
0x1800e90a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e90aa  lea     rdi, WPP_GLOBAL_Control
0x1800e90b1  cmp     rcx, rdi
0x1800e90b4  jz      loc_1800E97E4
0x1800e90ba  test    byte ptr [rcx+1Ch], 40h
0x1800e90be  jz      loc_1800E97E4
0x1800e90c4  mov     edx, 0Bh
0x1800e90c9  jmp     loc_1800E8FF9
0x1800e90ce  test    byte ptr [rcx], 1
0x1800e90d1  jnz     short loc_1800E9107
0x1800e90d3  mov     r9d, 80070057h
0x1800e90d9  mov     ebx, r9d
0x1800e90dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e90e3  lea     rdi, WPP_GLOBAL_Control
0x1800e90ea  cmp     rcx, rdi
0x1800e90ed  jz      loc_1800E97E4
0x1800e90f3  test    byte ptr [rcx+1Ch], 40h
0x1800e90f7  jz      loc_1800E97E4
0x1800e90fd  mov     edx, 0Ch
0x1800e9102  jmp     loc_1800E8FF9
0x1800e9107  test    byte ptr [rcx], 4
0x1800e910a  jnz     short loc_1800E9140
0x1800e910c  mov     r9d, 80070057h
0x1800e9112  mov     ebx, r9d
0x1800e9115  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e911c  lea     rdi, WPP_GLOBAL_Control
0x1800e9123  cmp     rcx, rdi
0x1800e9126  jz      loc_1800E97E4
0x1800e912c  test    byte ptr [rcx+1Ch], 40h
0x1800e9130  jz      loc_1800E97E4
0x1800e9136  mov     edx, 0Dh
0x1800e913b  jmp     loc_1800E8FF9
0x1800e9140  test    byte ptr [rcx], 8
0x1800e9143  jnz     short loc_1800E9179
0x1800e9145  mov     r9d, 80070057h
0x1800e914b  mov     ebx, r9d
0x1800e914e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9155  lea     rdi, WPP_GLOBAL_Control
0x1800e915c  cmp     rcx, rdi
0x1800e915f  jz      loc_1800E97E4
0x1800e9165  test    byte ptr [rcx+1Ch], 40h
0x1800e9169  jz      loc_1800E97E4
0x1800e916f  mov     edx, 0Eh
0x1800e9174  jmp     loc_1800E8FF9
0x1800e9179  lea     rax, [rcx+28h]
0x1800e917d  mov     rdx, [rax+88h]
0x1800e9184  mov     [rbp+57h+var_80], rax
0x1800e9188  cmp     rdx, 40h ; '@'
0x1800e918c  jbe     short loc_1800E91C2
0x1800e918e  mov     r9d, 80070057h
0x1800e9194  mov     ebx, r9d
0x1800e9197  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e919e  lea     rdi, WPP_GLOBAL_Control
0x1800e91a5  cmp     rcx, rdi
0x1800e91a8  jz      loc_1800E97E4
0x1800e91ae  test    byte ptr [rcx+1Ch], 40h
0x1800e91b2  jz      loc_1800E97E4
0x1800e91b8  mov     edx, 0Fh
0x1800e91bd  jmp     loc_1800E8FF9
0x1800e91c2  inc     rdx; unsigned __int64
0x1800e91c5  lea     r8, [rbp+57h+arg_0]; unsigned __int64 *
0x1800e91c9  mov     rcx, rax; unsigned __int16 *
0x1800e91cc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800e91d1  lea     rdi, WPP_GLOBAL_Control
0x1800e91d8  mov     ebx, eax
0x1800e91da  lea     rsi, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e91e1  test    eax, eax
0x1800e91e3  jz      short loc_1800E921C
0x1800e91e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e91ec  cmp     rcx, rdi
0x1800e91ef  jz      short loc_1800E9212
0x1800e91f1  test    byte ptr [rcx+1Ch], 40h
0x1800e91f5  jz      short loc_1800E9212
0x1800e91f7  mov     rcx, [rcx+10h]
0x1800e91fb  mov     edx, 10h
0x1800e9200  mov     r9d, eax
0x1800e9203  mov     r8, rsi
0x1800e9206  call    WPP_SF_d
0x1800e920b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9212  test    ebx, ebx
0x1800e9214  js      loc_1800E9009
0x1800e921a  jmp     short loc_1800E9223
0x1800e921c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9223  mov     rdx, [r15+138h]
0x1800e922a  cmp     rdx, 3Fh ; '?'
0x1800e922e  jbe     short loc_1800E9259
0x1800e9230  mov     r9d, 80070057h
0x1800e9236  mov     ebx, r9d
0x1800e9239  cmp     rcx, rdi
0x1800e923c  jz      loc_1800E9009
0x1800e9242  test    byte ptr [rcx+1Ch], 40h
0x1800e9246  jz      loc_1800E9009
0x1800e924c  mov     edx, 11h
0x1800e9251  mov     r8, rsi
0x1800e9254  jmp     loc_1800E9000
0x1800e9259  inc     rdx; unsigned __int64
0x1800e925c  lea     r8, [rbp+57h+arg_0]; unsigned __int64 *
0x1800e9260  lea     rcx, [r15+0B8h]; unsigned __int16 *
0x1800e9267  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800e926c  mov     ebx, eax
0x1800e926e  test    eax, eax
0x1800e9270  jz      short loc_1800E92A9
0x1800e9272  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9279  cmp     rcx, rdi
0x1800e927c  jz      short loc_1800E929F
0x1800e927e  test    byte ptr [rcx+1Ch], 40h
0x1800e9282  jz      short loc_1800E929F
0x1800e9284  mov     rcx, [rcx+10h]
0x1800e9288  mov     edx, 12h
0x1800e928d  mov     r9d, eax
0x1800e9290  mov     r8, rsi
0x1800e9293  call    WPP_SF_d
0x1800e9298  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e929f  test    ebx, ebx
0x1800e92a1  js      loc_1800E9009
0x1800e92a7  jmp     short loc_1800E92B0
0x1800e92a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e92b0  test    byte ptr [r15], 10h
0x1800e92b4  mov     eax, 3
0x1800e92b9  jz      short loc_1800E92F1
0x1800e92bb  cmp     qword ptr [r15+1140h], 1000h
0x1800e92c6  jbe     short loc_1800E92EC
0x1800e92c8  mov     r9d, 80070057h
0x1800e92ce  mov     ebx, r9d
0x1800e92d1  cmp     rcx, rdi
0x1800e92d4  jz      loc_1800E9009
0x1800e92da  test    byte ptr [rcx+1Ch], 40h
0x1800e92de  jz      loc_1800E9009
0x1800e92e4  lea     edx, [rax+10h]
0x1800e92e7  jmp     loc_1800E9251
0x1800e92ec  mov     eax, 4
0x1800e92f1  test    byte ptr [r15], 2
0x1800e92f5  lea     ecx, [rax+1]
0x1800e92f8  cmovz   ecx, eax
0x1800e92fb  mov     dword ptr [rbp+57h+arg_0], ecx
0x1800e92fe  lea     rcx, [rbp+57h+arg_8]; bool *
0x1800e9302  call    ?AdapInitializeCOM@@YAJPEA_N@Z; AdapInitializeCOM(bool *)
0x1800e9307  mov     ebx, eax
0x1800e9309  test    eax, eax
0x1800e930b  jz      short loc_1800E933B
0x1800e930d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9314  cmp     rcx, rdi
0x1800e9317  jz      short loc_1800E9333
0x1800e9319  test    byte ptr [rcx+1Ch], 40h
0x1800e931d  jz      short loc_1800E9333
0x1800e931f  mov     rcx, [rcx+10h]
0x1800e9323  mov     edx, 14h
0x1800e9328  mov     r9d, eax
0x1800e932b  mov     r8, rsi
0x1800e932e  call    WPP_SF_d
0x1800e9333  test    ebx, ebx
0x1800e9335  js      loc_1800E9009
0x1800e933b  mov     eax, gs:179Ch
0x1800e9343  test    eax, eax
0x1800e9345  jz      loc_1800E9491
0x1800e934b  call    ?AdapIsComImpersonating@@YAJXZ; AdapIsComImpersonating(void)
0x1800e9350  mov     ebx, eax
0x1800e9352  test    eax, eax
0x1800e9354  jz      short loc_1800E9385
0x1800e9356  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e935d  cmp     rcx, rdi
0x1800e9360  jz      short loc_1800E937C
0x1800e9362  test    byte ptr [rcx+1Ch], 40h
0x1800e9366  jz      short loc_1800E937C
0x1800e9368  mov     rcx, [rcx+10h]
0x1800e936c  mov     edx, 15h
0x1800e9371  mov     r9d, eax
0x1800e9374  mov     r8, rsi
0x1800e9377  call    WPP_SF_d
0x1800e937c  test    ebx, ebx
0x1800e937e  jns     short loc_1800E9387
0x1800e9380  jmp     loc_1800E9009
0x1800e9385  test    ebx, ebx
0x1800e9387  setz    r13b
0x1800e938b  call    cs:__imp_GetCurrentThread
0x1800e9392  nop     dword ptr [rax+rax+00h]
0x1800e9397  xor     r8d, r8d; OpenAsSelf
0x1800e939a  lea     r9, [rsp+120h+Token]; TokenHandle
0x1800e939f  mov     rcx, rax; ThreadHandle
0x1800e93a2  mov     [rbp+57h+Thread], rax
0x1800e93a6  lea     edx, [r8+4]; DesiredAccess
0x1800e93aa  call    cs:__imp_OpenThreadToken
0x1800e93b1  nop     dword ptr [rax+rax+00h]
0x1800e93b6  test    eax, eax
0x1800e93b8  jnz     short loc_1800E93FC
0x1800e93ba  call    cs:__imp_GetLastError
0x1800e93c1  nop     dword ptr [rax+rax+00h]
0x1800e93c6  mov     ebx, eax
0x1800e93c8  test    eax, eax
0x1800e93ca  jle     short loc_1800E93D5
0x1800e93cc  movzx   ebx, ax
0x1800e93cf  or      ebx, 80070000h
0x1800e93d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e93dc  cmp     rcx, rdi
0x1800e93df  jz      loc_1800E9009
0x1800e93e5  test    byte ptr [rcx+1Ch], 40h
0x1800e93e9  jz      loc_1800E9009
0x1800e93ef  mov     edx, 16h
0x1800e93f4  mov     r9d, ebx
0x1800e93f7  jmp     loc_1800E9251
0x1800e93fc  test    ebx, ebx
0x1800e93fe  jnz     short loc_1800E944C
0x1800e9400  call    cs:__imp_RevertToSelf
0x1800e9407  nop     dword ptr [rax+rax+00h]
0x1800e940c  test    eax, eax
0x1800e940e  jnz     short loc_1800E948D
0x1800e9410  call    cs:__imp_GetLastError
0x1800e9417  nop     dword ptr [rax+rax+00h]
0x1800e941c  mov     ebx, eax
0x1800e941e  test    eax, eax
0x1800e9420  jle     short loc_1800E942B
0x1800e9422  movzx   ebx, ax
0x1800e9425  or      ebx, 80070000h
0x1800e942b  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
