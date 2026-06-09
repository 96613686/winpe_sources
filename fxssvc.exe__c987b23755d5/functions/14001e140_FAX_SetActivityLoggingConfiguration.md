# FAX_SetActivityLoggingConfiguration

- ea: `0x14001e140`
- end: `0x14001eab0`
- name: `FAX_SetActivityLoggingConfiguration`
- size: `2416`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x140014c24`
- `0x14001e140`
- `0x140027a58`
- `0x14002ce80`
- `0x1400452ac`
- `0x14004ec00`
- `0x14005549c`
- `0x140065dbc`
- `0x14006d8b0`
- `0x14006e160`
- `0x14006e54c`
- `0x1400755e0`
- `0x14007ee18`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001e5f4`
- `KERNEL32!GetLastError` at `0x14001e706`
- `KERNEL32!GetLastError` at `0x14001e763`
- `KERNEL32!GetLastError` at `0x14001e84d`
- `KERNEL32!GetLastError` at `0x14001e8f8`
- `KERNEL32!GetLastError` at `0x14001e942`
- `KERNEL32!GetLastError` at `0x14001ea06`
- `KERNEL32!GetLastError` at `0x14001e5f4`
- `KERNEL32!GetLastError` at `0x14001e706`
- `KERNEL32!GetLastError` at `0x14001e763`
- `KERNEL32!GetLastError` at `0x14001e84d`
- `KERNEL32!GetLastError` at `0x14001e8f8`
- `KERNEL32!GetLastError` at `0x14001e942`
- `KERNEL32!GetLastError` at `0x14001ea06`
- `KERNEL32!CloseHandle` at `0x14001e6dd`
- `KERNEL32!CloseHandle` at `0x14001e741`
- `KERNEL32!CloseHandle` at `0x14001e82b`
- `KERNEL32!CloseHandle` at `0x14001e920`
- `KERNEL32!CloseHandle` at `0x14001e6dd`
- `KERNEL32!CloseHandle` at `0x14001e741`
- `KERNEL32!CloseHandle` at `0x14001e82b`
- `KERNEL32!CloseHandle` at `0x14001e920`
- `KERNEL32!DeleteFileW` at `0x14001e8d6`
- `KERNEL32!DeleteFileW` at `0x14001e9d4`
- `KERNEL32!DeleteFileW` at `0x14001e8d6`
- `KERNEL32!DeleteFileW` at `0x14001e9d4`
- `KERNEL32!EnterCriticalSection` at `0x14001e35a`
- `KERNEL32!EnterCriticalSection` at `0x14001e367`
- `KERNEL32!EnterCriticalSection` at `0x14001e35a`
- `KERNEL32!EnterCriticalSection` at `0x14001e367`
- `KERNEL32!LeaveCriticalSection` at `0x14001e806`
- `KERNEL32!LeaveCriticalSection` at `0x14001e813`
- `KERNEL32!LeaveCriticalSection` at `0x14001e806`
- `KERNEL32!LeaveCriticalSection` at `0x14001e813`

## pseudocode

```c
__int64 __fastcall FAX_SetActivityLoggingConfiguration(void *a1, int *a2)
{
  __int64 v2; // r12
  __int64 v3; // r13
  int v6; // esi
  CMapDeviceId *v7; // rcx
  int v8; // ebx
  __m128i v9; // xmm0
  const WCHAR *v10; // xmm1_8
  const WCHAR *v11; // rax
  __int64 v12; // r9
  __int64 v13; // r8
  unsigned int v14; // ebx
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int valid; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v22; // r15d
  __m128i *p_Mem; // r14
  unsigned int v24; // eax
  DWORD v25; // eax
  unsigned int ConfigEvent; // eax
  CMapDeviceId *v27; // rcx
  __int64 v28; // rdx
  DWORD v29; // eax
  DWORD v30; // eax
  DWORD LastError; // eax
  int v32; // eax
  DWORD v33; // eax
  DWORD v34; // eax
  int v35; // eax
  DWORD v36; // eax
  __m128i Mem; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpPathName; // [rsp+40h] [rbp-C0h]
  int v39; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+4Ch] [rbp-B4h]
  void *v41; // [rsp+50h] [rbp-B0h] BYREF
  void *v42; // [rsp+58h] [rbp-A8h] BYREF
  __m128i *v43; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v44[4]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v45; // [rsp+78h] [rbp-88h]
  WCHAR FileName[520]; // [rsp+80h] [rbp-80h] BYREF

  v2 = -1;
  v41 = (void *)-1LL;
  v3 = -1;
  v42 = (void *)-1LL;
  v39 = 0;
  lpPathName = 0;
  v40 = 0;
  v43 = 0;
  v6 = 0;
  Mem = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 305, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( *a2 != 24 )
  {
    v8 = *a2;
    if ( (unsigned int)GetWin32StructSize(&fax_activity_logging_config_fields) != v8 )
      return 87;
    v7 = WPP_GLOBAL_Control;
  }
  v9 = *(__m128i *)a2;
  v10 = (const WCHAR *)*((_QWORD *)a2 + 2);
  lpPathName = v10;
  Mem = v9;
  if ( !v9.m128i_i32[1] && !_mm_cvtsi128_si32(_mm_srli_si128(v9, 8)) )
    goto LABEL_18;
  if ( !v10 || !*v10 )
  {
    if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v7 + 2), 306, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    return 87;
  }
  v11 = v10;
  v12 = 249;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v12;
  }
  while ( v12 );
  v13 = (249 - v12) & -(__int64)(v12 != 0);
  if ( v12 )
  {
    if ( v10[v13 - 1] == 92 )
      v10[v13 - 1] = 0;
LABEL_18:
    v14 = FaxSvcAccessCheck(0x40u, &v39, 0, 1);
    if ( v14 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v16 = 308;
      v17 = v14;
      goto LABEL_23;
    }
    if ( !v39 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 309, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
      }
      return 5;
    }
    EnterCriticalSection(&g_CsInboundActivityLogging);
    EnterCriticalSection(&g_CsOutboundActivityLogging);
    if ( *(__int64 *)((char *)Mem.m128i_i64 + 4) )
    {
      if ( !(unsigned int)PathRepresentsFullPath((wchar_t *)lpPathName) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            310,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            lpPathName);
        }
        v14 = 87;
        goto LABEL_112;
      }
      valid = IsValidFaxFolder((unsigned __int16 *)lpPathName);
      v14 = valid;
      if ( valid )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            311,
            (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            (_DWORD)lpPathName,
            valid);
        }
        if ( v14 == 5 && FindClientAPIVersion(a1) >= 0x10000 )
          goto LABEL_48;
LABEL_112:
        LeaveCriticalSection(&g_CsOutboundActivityLogging);
        LeaveCriticalSection(&g_CsInboundActivityLogging);
        if ( v2 == -1 && v3 == -1 )
          goto LABEL_24;
        if ( !CloseHandle((HANDLE)v2)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            321,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            LastError);
        }
        v32 = StringCchPrintfW(FileName, 0x208u, L"%s\\%s", lpPathName, L"InboxLOG.txt");
        if ( v32 >= 0 )
        {
          if ( !DeleteFileW(FileName)
            && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v33 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 323, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v33);
          }
        }
        else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            322,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            (unsigned int)v32);
        }
        if ( !CloseHandle((HANDLE)v3)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v34 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v34);
        }
        v35 = StringCchPrintfW(FileName, 0x208u, L"%s\\%s", lpPathName, L"OutboxLOG.txt");
        if ( v35 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              325,
              &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
              (unsigned int)v35);
          }
          goto LABEL_24;
        }
        if ( DeleteFileW(FileName)
          || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_24:
          if ( v14 == 8 || v14 == 14 )
            return 7001;
          return v14;
        }
        v36 = GetLastError();
        v15 = WPP_GLOBAL_Control;
        v16 = 326;
        v17 = v36;
LABEL_23:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v17);
        goto LABEL_24;
      }
      v20 = CheckToSeeIfSameDir(lpPathName, *(wchar_t **)&fDesiredAccess);
      v14 = v20;
      if ( v20 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v20);
        }
        goto LABEL_61;
      }
      v6 = v40;
      if ( !v40 )
      {
        v21 = CreateLogDB(lpPathName, &v41, &v42);
        v14 = v21;
        if ( v21 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v21);
          }
          v3 = (__int64)v42;
          v2 = (__int64)v41;
LABEL_61:
          if ( v14 != 5 && v14 != 32 )
            goto LABEL_112;
LABEL_48:
          v14 = 7008;
          goto LABEL_112;
        }
        v2 = (__int64)v41;
        v3 = (__int64)v42;
      }
    }
    v22 = ContractConfigurationFolder(&Mem, &v43);
    if ( v22 )
    {
      p_Mem = v43;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
      }
      p_Mem = &Mem;
    }
    v24 = StoreActivityLoggingSettings(p_Mem);
    v14 = v24;
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 315, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v24);
      }
      v14 = 1015;
      goto LABEL_110;
    }
    if ( *(__int64 *)((char *)Mem.m128i_i64 + 4) )
    {
      if ( !ReplaceStringWithCopy((unsigned __int16 **)&fDesiredAccess, lpPathName) )
      {
        v25 = GetLastError();
        v14 = v25;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v25);
        }
        v44[1] = *(&g_ActivityLoggingConfig + 1);
        v44[2] = *(&g_ActivityLoggingConfig + 2);
        v45 = *(_QWORD *)&fDesiredAccess;
        v44[3] = 0;
        v44[0] = 24;
        ConfigEvent = StoreActivityLoggingSettings(v44);
        if ( !ConfigEvent )
          goto LABEL_110;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_110;
        }
        v28 = 317;
        goto LABEL_89;
      }
      if ( *(__int64 *)((char *)Mem.m128i_i64 + 4) && !v6 )
      {
        if ( g_hInboxActivityLogFile != (HANDLE)-1LL
          && !CloseHandle(g_hInboxActivityLogFile)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v29 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 318, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v29);
        }
        if ( g_hOutboxActivityLogFile != (HANDLE)-1LL
          && !CloseHandle(g_hOutboxActivityLogFile)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v30 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 319, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v30);
        }
        g_hInboxActivityLogFile = (HANDLE)v2;
        g_hOutboxActivityLogFile = (HANDLE)v3;
        v2 = -1;
        v3 = -1;
      }
    }
    *(_QWORD *)((char *)&g_ActivityLoggingConfig + 4) = *(__int64 *)((char *)Mem.m128i_i64 + 4);
    ConfigEvent = CreateConfigEvent(1);
    if ( !ConfigEvent
      || (v27 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control)
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_110:
      if ( v22 )
        pMemFree(p_Mem);
      goto LABEL_112;
    }
    v28 = 320;
LABEL_89:
    WPP_SF_d(*((_QWORD *)v27 + 2), v28, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, ConfigEvent);
    goto LABEL_110;
  }
  if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 2u )
    WPP_SF_(*((_QWORD *)v7 + 2), 307, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  return 111;
}

```

## disassembly

```asm
0x14001e140  mov     [rsp-8+arg_10], rbx
0x14001e145  push    rbp
0x14001e146  push    rsi
0x14001e147  push    rdi
0x14001e148  push    r12
0x14001e14a  push    r13
0x14001e14c  push    r14
0x14001e14e  push    r15
0x14001e150  lea     rbp, [rsp-3A0h]
0x14001e158  sub     rsp, 4A0h
0x14001e15f  mov     rax, cs:__security_cookie
0x14001e166  xor     rax, rsp
0x14001e169  mov     [rbp+3D0h+var_40], rax
0x14001e170  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001e174  xor     r15d, r15d
0x14001e177  mov     r12, rax
0x14001e17a  mov     [rsp+4D0h+var_480], rax
0x14001e17f  mov     r13, rax
0x14001e182  mov     [rsp+4D0h+var_478], rax
0x14001e187  xor     eax, eax
0x14001e189  mov     [rsp+4D0h+var_488], r15d
0x14001e18e  xorps   xmm0, xmm0
0x14001e191  mov     [rsp+4D0h+lpPathName], rax
0x14001e196  mov     rdi, rdx
0x14001e199  mov     [rsp+4D0h+var_484], r15d
0x14001e19e  mov     r14, rcx
0x14001e1a1  mov     [rsp+4D0h+var_470], r15
0x14001e1a6  mov     esi, r15d
0x14001e1a9  movups  [rsp+4D0h+Mem], xmm0
0x14001e1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1b5  lea     rax, WPP_GLOBAL_Control
0x14001e1bc  cmp     rcx, rax
0x14001e1bf  jz      short loc_14001E1E9
0x14001e1c1  test    byte ptr [rcx+1Ch], 4
0x14001e1c5  jz      short loc_14001E1E9
0x14001e1c7  cmp     byte ptr [rcx+19h], 5
0x14001e1cb  jb      short loc_14001E1E9
0x14001e1cd  mov     rcx, [rcx+10h]
0x14001e1d1  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e1d8  mov     edx, 131h
0x14001e1dd  call    WPP_SF_
0x14001e1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1e9  mov     ebx, [rdi]
0x14001e1eb  cmp     ebx, 18h
0x14001e1ee  jz      short loc_14001E20B
0x14001e1f0  lea     rcx, ?fax_activity_logging_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_activity_logging_config_fields
0x14001e1f7  call    GetWin32StructSize
0x14001e1fc  cmp     eax, ebx
0x14001e1fe  jnz     loc_14001EA81
0x14001e204  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e20b  movups  xmm0, xmmword ptr [rdi]
0x14001e20e  movsd   xmm1, qword ptr [rdi+10h]
0x14001e213  mov     edi, 2
0x14001e218  movq    rax, xmm0
0x14001e21d  movsd   [rsp+4D0h+lpPathName], xmm1
0x14001e223  shr     rax, 20h
0x14001e227  movups  [rsp+4D0h+Mem], xmm0
0x14001e22c  test    eax, eax
0x14001e22e  jnz     short loc_14001E23D
0x14001e230  psrldq  xmm0, 8
0x14001e235  movd    eax, xmm0
0x14001e239  test    eax, eax
0x14001e23b  jz      short loc_14001E2A4
0x14001e23d  movq    rdx, xmm1
0x14001e242  test    rdx, rdx
0x14001e245  jz      loc_14001EA54
0x14001e24b  cmp     [rdx], r15w
0x14001e24f  jz      loc_14001EA54
0x14001e255  test    rdx, rdx
0x14001e258  jz      loc_14001EA20
0x14001e25e  mov     r10d, 0F9h
0x14001e264  mov     rax, rdx
0x14001e267  mov     r9d, r10d
0x14001e26a  cmp     [rax], r15w
0x14001e26e  jz      short loc_14001E279
0x14001e270  add     rax, rdi
0x14001e273  sub     r9, 1
0x14001e277  jnz     short loc_14001E26A
0x14001e279  sub     r10, r9
0x14001e27c  mov     rax, r9
0x14001e27f  neg     rax
0x14001e282  sbb     r8, r8
0x14001e285  and     r8, r10
0x14001e288  test    r9, r9
0x14001e28b  jz      loc_14001EA20
0x14001e291  mov     eax, 5Ch ; '\'
0x14001e296  cmp     ax, [rdx+r8*2-2]
0x14001e29c  jnz     short loc_14001E2A4
0x14001e29e  mov     [rdx+r8*2-2], r15w
0x14001e2a4  mov     r9d, 1; int
0x14001e2aa  lea     rdx, [rsp+4D0h+var_488]; int *
0x14001e2af  xor     r8d, r8d; unsigned int *
0x14001e2b2  lea     ecx, [r9+3Fh]; unsigned int
0x14001e2b6  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001e2bb  mov     ebx, eax
0x14001e2bd  test    eax, eax
0x14001e2bf  jz      short loc_14001E30E
0x14001e2c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e2c8  lea     rax, WPP_GLOBAL_Control
0x14001e2cf  cmp     rcx, rax
0x14001e2d2  jz      short loc_14001E2F8
0x14001e2d4  test    byte ptr [rcx+1Ch], 4
0x14001e2d8  jz      short loc_14001E2F8
0x14001e2da  cmp     [rcx+19h], dil
0x14001e2de  jb      short loc_14001E2F8
0x14001e2e0  mov     edx, 134h
0x14001e2e5  mov     r9d, ebx
0x14001e2e8  mov     rcx, [rcx+10h]
0x14001e2ec  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e2f3  call    WPP_SF_d
0x14001e2f8  cmp     ebx, 8
0x14001e2fb  jz      short loc_14001E302
0x14001e2fd  cmp     ebx, 0Eh
0x14001e300  jnz     short loc_14001E307
0x14001e302  mov     ebx, 1B59h
0x14001e307  mov     eax, ebx
0x14001e309  jmp     loc_14001EA86
0x14001e30e  cmp     [rsp+4D0h+var_488], r15d
0x14001e313  jnz     short loc_14001E353
0x14001e315  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e31c  lea     rax, WPP_GLOBAL_Control
0x14001e323  cmp     rcx, rax
0x14001e326  jz      short loc_14001E349
0x14001e328  test    byte ptr [rcx+1Ch], 4
0x14001e32c  jz      short loc_14001E349
0x14001e32e  cmp     [rcx+19h], dil
0x14001e332  jb      short loc_14001E349
0x14001e334  mov     rcx, [rcx+10h]
0x14001e338  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e33f  mov     edx, 135h
0x14001e344  call    WPP_SF_
0x14001e349  mov     eax, 5
0x14001e34e  jmp     loc_14001EA86
0x14001e353  lea     rcx, ?g_CsInboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001e35a  call    cs:__imp_EnterCriticalSection
0x14001e360  lea     rcx, ?g_CsOutboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001e367  call    cs:__imp_EnterCriticalSection
0x14001e36d  cmp     dword ptr [rsp+4D0h+Mem+4], r15d
0x14001e372  jnz     short loc_14001E37F
0x14001e374  cmp     dword ptr [rsp+4D0h+Mem+8], r15d
0x14001e379  jz      loc_14001E524
0x14001e37f  mov     rcx, [rsp+4D0h+lpPathName]; String1
0x14001e384  call    PathRepresentsFullPath
0x14001e389  test    eax, eax
0x14001e38b  jnz     short loc_14001E3D0
0x14001e38d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e394  lea     rsi, WPP_GLOBAL_Control
0x14001e39b  cmp     rcx, rsi
0x14001e39e  jz      short loc_14001E3C6
0x14001e3a0  test    byte ptr [rcx+1Ch], 4
0x14001e3a4  jz      short loc_14001E3C6
0x14001e3a6  cmp     [rcx+19h], dil
0x14001e3aa  jb      short loc_14001E3C6
0x14001e3ac  mov     r9, [rsp+4D0h+lpPathName]
0x14001e3b1  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e3b8  mov     rcx, [rcx+10h]
0x14001e3bc  mov     edx, 136h
0x14001e3c1  call    WPP_SF_S
0x14001e3c6  mov     ebx, 57h ; 'W'
0x14001e3cb  jmp     loc_14001E7FF
0x14001e3d0  mov     rcx, [rsp+4D0h+lpPathName]; unsigned __int16 *
0x14001e3d5  call    IsValidFaxFolder
0x14001e3da  mov     ebx, eax
0x14001e3dc  test    eax, eax
0x14001e3de  jz      short loc_14001E443
0x14001e3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e3e7  lea     rsi, WPP_GLOBAL_Control
0x14001e3ee  cmp     rcx, rsi
0x14001e3f1  jz      short loc_14001E41D
0x14001e3f3  test    byte ptr [rcx+1Ch], 4
0x14001e3f7  jz      short loc_14001E41D
0x14001e3f9  cmp     [rcx+19h], dil
0x14001e3fd  jb      short loc_14001E41D
0x14001e3ff  mov     r9, [rsp+4D0h+lpPathName]
0x14001e404  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e40b  mov     rcx, [rcx+10h]
0x14001e40f  mov     edx, 137h
0x14001e414  mov     dword ptr [rsp+4D0h+var_4B0], eax
0x14001e418  call    WPP_SF_Sd
0x14001e41d  cmp     ebx, 5
0x14001e420  jnz     loc_14001E7FF
0x14001e426  mov     rcx, r14; void *
0x14001e429  call    ?FindClientAPIVersion@@YAKPEAX@Z; FindClientAPIVersion(void *)
0x14001e42e  cmp     eax, 10000h
0x14001e433  jb      loc_14001E7FF
0x14001e439  mov     ebx, 1B60h
0x14001e43e  jmp     loc_14001E7FF
0x14001e443  mov     rdx, qword ptr cs:fDesiredAccess; String2
0x14001e44a  lea     r8, [rsp+4D0h+var_484]
0x14001e44f  mov     rcx, [rsp+4D0h+lpPathName]; lpPathName
0x14001e454  call    CheckToSeeIfSameDir
0x14001e459  mov     ebx, eax
0x14001e45b  test    eax, eax
0x14001e45d  jz      short loc_14001E4A0
0x14001e45f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e466  lea     rsi, WPP_GLOBAL_Control
0x14001e46d  cmp     rcx, rsi
0x14001e470  jz      loc_14001E503
0x14001e476  test    byte ptr [rcx+1Ch], 4
0x14001e47a  jz      loc_14001E503
0x14001e480  cmp     [rcx+19h], dil
0x14001e484  jb      short loc_14001E503
0x14001e486  mov     rcx, [rcx+10h]
0x14001e48a  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e491  mov     edx, 138h
0x14001e496  mov     r9d, eax
0x14001e499  call    WPP_SF_d
0x14001e49e  jmp     short loc_14001E503
0x14001e4a0  mov     esi, [rsp+4D0h+var_484]
0x14001e4a4  test    esi, esi
0x14001e4a6  jnz     short loc_14001E524
0x14001e4a8  mov     rcx, [rsp+4D0h+lpPathName]; unsigned __int16 *
0x14001e4ad  lea     r8, [rsp+4D0h+var_478]; void **
0x14001e4b2  lea     rdx, [rsp+4D0h+var_480]; void **
0x14001e4b7  call    ?CreateLogDB@@YAKPEBGPEAPEAX1@Z; CreateLogDB(ushort const *,void * *,void * *)
0x14001e4bc  mov     ebx, eax
0x14001e4be  test    eax, eax
0x14001e4c0  jz      short loc_14001E51A
0x14001e4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e4c9  lea     rsi, WPP_GLOBAL_Control
0x14001e4d0  cmp     rcx, rsi
0x14001e4d3  jz      short loc_14001E4F9
0x14001e4d5  test    byte ptr [rcx+1Ch], 4
0x14001e4d9  jz      short loc_14001E4F9
0x14001e4db  cmp     [rcx+19h], dil
0x14001e4df  jb      short loc_14001E4F9
0x14001e4e1  mov     rcx, [rcx+10h]
0x14001e4e5  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e4ec  mov     edx, 139h
0x14001e4f1  mov     r9d, eax
0x14001e4f4  call    WPP_SF_d
0x14001e4f9  mov     r13, [rsp+4D0h+var_478]
0x14001e4fe  mov     r12, [rsp+4D0h+var_480]
0x14001e503  cmp     ebx, 5
0x14001e506  jz      loc_14001E439
0x14001e50c  cmp     ebx, 20h ; ' '
0x14001e50f  jnz     loc_14001E7FF
0x14001e515  jmp     loc_14001E439
0x14001e51a  mov     r12, [rsp+4D0h+var_480]
0x14001e51f  mov     r13, [rsp+4D0h+var_478]
0x14001e524  lea     rdx, [rsp+4D0h+var_470]
0x14001e529  lea     rcx, [rsp+4D0h+Mem]
0x14001e52e  call    ?ContractConfigurationFolder@@YAHQEAXPEAPEAXW4FAX_ENUM_CONFIGURATION_TYPES@@@Z; ContractConfigurationFolder(void * const,void * *,FAX_ENUM_CONFIGURATION_TYPES)
0x14001e533  mov     r15d, eax
0x14001e536  test    eax, eax
0x14001e538  jnz     short loc_14001E575
0x14001e53a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e541  lea     rax, WPP_GLOBAL_Control
0x14001e548  cmp     rcx, rax
0x14001e54b  jz      short loc_14001E56E
0x14001e54d  test    byte ptr [rcx+1Ch], 4
0x14001e551  jz      short loc_14001E56E
0x14001e553  cmp     [rcx+19h], dil
0x14001e557  jb      short loc_14001E56E
0x14001e559  mov     rcx, [rcx+10h]
0x14001e55d  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e564  mov     edx, 13Ah
0x14001e569  call    WPP_SF_
0x14001e56e  lea     r14, [rsp+4D0h+Mem]
0x14001e573  jmp     short loc_14001E57A
0x14001e575  mov     r14, [rsp+4D0h+var_470]
0x14001e57a  mov     rcx, r14
0x14001e57d  call    StoreActivityLoggingSettings
0x14001e582  mov     ebx, eax
0x14001e584  test    eax, eax
0x14001e586  jz      short loc_14001E5C9
0x14001e588  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e58f  lea     rsi, WPP_GLOBAL_Control
0x14001e596  cmp     rcx, rsi
0x14001e599  jz      short loc_14001E5BF
0x14001e59b  test    byte ptr [rcx+1Ch], 4
0x14001e59f  jz      short loc_14001E5BF
0x14001e5a1  cmp     [rcx+19h], dil
0x14001e5a5  jb      short loc_14001E5BF
0x14001e5a7  mov     rcx, [rcx+10h]
0x14001e5ab  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e5b2  mov     edx, 13Bh
0x14001e5b7  mov     r9d, eax
0x14001e5ba  call    WPP_SF_d
0x14001e5bf  mov     ebx, 3F7h
0x14001e5c4  jmp     loc_14001E7F2
0x14001e5c9  cmp     dword ptr [rsp+4D0h+Mem+4], 0
0x14001e5ce  jnz     short loc_14001E5DB
0x14001e5d0  cmp     dword ptr [rsp+4D0h+Mem+8], 0
0x14001e5d5  jz      loc_14001E7A0
0x14001e5db  mov     rdx, [rsp+4D0h+lpPathName]; unsigned __int16 *
0x14001e5e0  lea     rcx, fDesiredAccess; unsigned __int16 **
0x14001e5e7  call    ?ReplaceStringWithCopy@@YAHPEAPEAGPEBG@Z; ReplaceStringWithCopy(ushort * *,ushort const *)
0x14001e5ec  test    eax, eax
0x14001e5ee  jnz     loc_14001E6B6
0x14001e5f4  call    cs:__imp_GetLastError
0x14001e5fa  mov     ebx, eax
0x14001e5fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e603  lea     rsi, WPP_GLOBAL_Control
0x14001e60a  cmp     rcx, rsi
0x14001e60d  jz      short loc_14001E633
0x14001e60f  test    byte ptr [rcx+1Ch], 4
0x14001e613  jz      short loc_14001E633
0x14001e615  cmp     [rcx+19h], dil
0x14001e619  jb      short loc_14001E633
  ... truncated ...
```
