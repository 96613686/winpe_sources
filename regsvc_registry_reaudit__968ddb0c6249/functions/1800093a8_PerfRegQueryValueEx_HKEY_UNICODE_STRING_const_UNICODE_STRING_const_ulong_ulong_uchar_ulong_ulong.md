# PerfRegQueryValueEx(HKEY__ *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong *,ulong *,uchar *,ulong *,ulong *)

- ea: `0x1800093a8`
- end: `0x180009e41`
- name: `?PerfRegQueryValueEx@@YAJPEAUHKEY__@@PEBU_UNICODE_STRING@@1PEAK2PEAE22@Z`
- size: `2713`
- prototype: `__int64 __fastcall(HKEY, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008b58`
- `0x18000a638`
- `0x18001bedc`

## callees

- `0x180004f00`
- `0x180005da0`
- `0x180007740`
- `0x180008042`
- `0x180008050`
- `0x180008c30`
- `0x1800093a8`
- `0x180009ff0`
- `0x18000a0d4`
- `0x18000aaa0`
- `0x18000aac8`
- `0x18000abc4`
- `0x18000b508`
- `0x18000b7c8`
- `0x18000bef8`
- `0x18000c134`
- `0x1800102c0`
- `0x180010328`
- `0x180010430`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x180009446`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180009446`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800097a6`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800097f8`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800097a6`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800097f8`
- `ntdll!NtSetInformationThread` at `0x18000962d`
- `ntdll!NtSetInformationThread` at `0x180009de4`
- `ntdll!NtSetInformationThread` at `0x18000962d`
- `ntdll!NtSetInformationThread` at `0x180009de4`
- `ntdll!NtQueryInformationThread` at `0x1800095fe`
- `ntdll!NtQueryInformationThread` at `0x1800095fe`
- `ntdll!NtWaitForSingleObject` at `0x1800096cd`
- `ntdll!NtWaitForSingleObject` at `0x180009bfe`
- `ntdll!NtWaitForSingleObject` at `0x1800096cd`
- `ntdll!NtWaitForSingleObject` at `0x180009bfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009b9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009d25`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009b9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009d25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000956e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000956e`
- `SspiCli!GetUserNameExW` at `0x180009550`
- `SspiCli!GetUserNameExW` at `0x180009550`

## pseudocode

```c
__int64 __fastcall PerfRegQueryValueEx(
        HKEY a1,
        const struct _UNICODE_STRING *a2,
        const struct _UNICODE_STRING *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int8 *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  _QWORD *v10; // rcx
  wchar_t *Buffer; // rcx
  unsigned int QueryType; // eax
  int v13; // r12d
  unsigned int ExtensibleData; // ebx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  NTSTATUS InformationThread; // eax
  NTSTATUS v19; // eax
  unsigned int v20; // edi
  unsigned int v21; // eax
  _QWORD *v22; // rcx
  int Names; // ebx
  _WORD *v24; // rsi
  int ThreadPreferredUILanguages; // eax
  __int64 v26; // rax
  __int64 v27; // rax
  const unsigned __int16 *v28; // rax
  const unsigned __int16 *v29; // rdx
  __int64 v30; // rcx
  unsigned int LangIdFromSzLang; // eax
  __int16 v32; // r13
  int v33; // eax
  const unsigned __int16 *v34; // r13
  int v35; // eax
  int v36; // eax
  __int64 v37; // rax
  unsigned int v38; // eax
  unsigned int v39; // r8d
  unsigned int v40; // r9d
  unsigned int v41; // esi
  _QWORD *v42; // rcx
  struct _PERF_DATA_BLOCK *v43; // r13
  unsigned int v45; // [rsp+40h] [rbp-C0h]
  int v46; // [rsp+44h] [rbp-BCh] BYREF
  int v47; // [rsp+48h] [rbp-B8h] BYREF
  int v48; // [rsp+4Ch] [rbp-B4h] BYREF
  ULONG nSize; // [rsp+50h] [rbp-B0h] BYREF
  struct _PERF_DATA_BLOCK *v50; // [rsp+58h] [rbp-A8h]
  struct _UNICODE_STRING v51; // [rsp+60h] [rbp-A0h] BYREF
  void *v52; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v53; // [rsp+78h] [rbp-88h]
  union _LARGE_INTEGER Timeout; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v55; // [rsp+88h] [rbp-78h]
  __int64 v56; // [rsp+90h] [rbp-70h] BYREF
  __int128 v57; // [rsp+98h] [rbp-68h]
  __int128 v58; // [rsp+A8h] [rbp-58h]
  __int64 v59; // [rsp+B8h] [rbp-48h]
  __int64 v60; // [rsp+C0h] [rbp-40h]
  _OWORD ThreadInformation[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v62; // [rsp+E8h] [rbp-18h]
  WCHAR NameBuffer[128]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Filename[264]; // [rsp+200h] [rbp+100h] BYREF

  v55 = a5;
  v50 = (struct _PERF_DATA_BLOCK *)a6;
  v52 = 0;
  *(_QWORD *)&v51.Length = 0;
  v51.Buffer = 0;
  Timeout.QuadPart = 0;
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  v48 = 0;
  v47 = 0;
  v62 = 0;
  RtlRunOnceExecuteOnce(qword_18002B570, PerfpInitializeCallback, 0, 0);
  v10 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, a3);
    v10 = WPP_GLOBAL_Control;
  }
  v52 = 0;
  v47 = -1;
  v48 = -1;
  if ( !a3 || !a3->Buffer )
  {
    ExtensibleData = 87;
    goto LABEL_155;
  }
  Buffer = a3->Buffer;
  v51 = *a3;
  QueryType = GetQueryType(Buffer);
  v45 = QueryType;
  v13 = (unsigned __int16)QueryType;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
      (unsigned __int16)QueryType);
  ExtensibleData = PerfOpenKey((__int64)a1, (unsigned __int16)(v13 - 5) <= 3u);
  if ( ExtensibleData )
  {
    v10 = WPP_GLOBAL_Control;
    goto LABEL_155;
  }
  if ( !(unsigned int)TestClientForAccess() )
  {
    if ( PerfpThrottleError(0x3E8u, 0, &PerfpErrorLog) )
    {
      nSize = 128;
      if ( !GetUserNameExW((EXTENDED_NAME_FORMAT)65538, NameBuffer, &nSize) )
        NameBuffer[0] = 0;
      if ( !GetModuleFileNameW(0, Filename, 0x104u) )
        Filename[0] = 0;
      if ( (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
        McTemplateU0zz_EtwEventWriteTransfer(v15, PERFLIB_ACCESS_DENIED, NameBuffer, Filename);
    }
    ExtensibleData = 5;
    v10 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 20;
      v17 = 5;
LABEL_21:
      WPP_SF_d(v10[2], v16, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, v17);
LABEL_152:
      v10 = WPP_GLOBAL_Control;
      goto LABEL_155;
    }
    goto LABEL_155;
  }
  if ( dwBoostPriority )
  {
    InformationThread = NtQueryInformationThread(
                          (HANDLE)0xFFFFFFFFFFFFFFFELL,
                          ThreadBasicInformation,
                          ThreadInformation,
                          0x30u,
                          0);
    if ( InformationThread < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
          (unsigned int)InformationThread);
      v47 = 15;
    }
    else
    {
      v48 = DWORD2(v62);
      v47 = 15;
      if ( (unsigned int)(DWORD2(v62) - 1) <= 0xD )
      {
        v19 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &v47, 4u);
        if ( v19 >= 0 )
          goto LABEL_34;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
            (unsigned int)v19);
      }
    }
    v48 = -1;
  }
LABEL_34:
  v20 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a7 )
    v20 = *a7;
  Timeout.QuadPart = -20000000;
  if ( (unsigned __int16)(v13 - 5) > 3u )
  {
    v56 = 0;
    v59 = 0;
    v57 = 0;
    v60 = 0;
    v58 = 0;
    v38 = NtWaitForSingleObject(hGlobalDataMutex, 0, &Timeout);
    if ( v38 )
    {
      ExtensibleData = 170;
      v41 = v20;
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, v38);
        v10 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v42 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
        v42 = WPP_GLOBAL_Control;
      }
      v41 = 122;
      if ( v20 >= 0x7A )
      {
        v43 = v50;
        if ( v50 )
        {
          if ( v13 == 3 )
          {
            v52 = v50;
            memset_0(v50, 0, sizeof(struct _PERF_DATA_BLOCK));
          }
          else
          {
            MonBuildPerfDataBlock(v50, &v52, v39, v40);
          }
        }
        LODWORD(v56) = v45;
        *(_QWORD *)&v57 = v51.Buffer;
        *((_QWORD *)&v58 + 1) = &v52;
        *((_QWORD *)&v57 + 1) = v43;
        *(_QWORD *)&v58 = a7;
        v59 = 0;
        v60 = 0;
        ExtensibleData = QueryExtensibleData((struct COLLECT_THREAD_DATA *)&v56);
      }
      else
      {
        if ( (*((_BYTE *)v42 + 28) & 2) != 0 && *((_BYTE *)v42 + 25) >= 2u )
          WPP_SF_d(v42[2], 29, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, v20);
        v43 = v50;
        ExtensibleData = 234;
      }
      ReleaseMutex(hGlobalDataMutex);
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
        v10 = WPP_GLOBAL_Control;
      }
      if ( !ExtensibleData )
      {
        ExtensibleData = 0;
        v20 = (_DWORD)v52 - (_DWORD)v43;
        if ( a7 )
          *a7 = v20;
        v43->TotalByteLength = v20;
        v10 = WPP_GLOBAL_Control;
LABEL_148:
        if ( a8 )
        {
          *a8 = v20;
          v10 = WPP_GLOBAL_Control;
        }
        if ( v55 )
        {
          *v55 = 3;
          goto LABEL_152;
        }
        goto LABEL_155;
      }
    }
    if ( v20 >= v41 )
      v20 = v41;
    goto LABEL_148;
  }
  v21 = NtWaitForSingleObject(hGlobalDataMutex, 0, &Timeout);
  if ( !v21 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
      v22 = WPP_GLOBAL_Control;
    }
    if ( a1 == HKEY_PERFORMANCE_DATA )
    {
      Names = PerfGetNames(v45, &stru_1800206B8, &v51, (unsigned __int8 *)v50, a7, a8, 0);
LABEL_110:
      if ( Names >= 0 )
        goto LABEL_115;
      v22 = WPP_GLOBAL_Control;
LABEL_112:
      if ( (*((_BYTE *)v22 + 28) & 2) != 0 && *((_BYTE *)v22 + 25) >= 2u )
        WPP_SF_d(v22[2], 25, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, (unsigned int)Names);
LABEL_115:
      ExtensibleData = PerfpDosError(Names);
      if ( v55 )
        *v55 = 7;
      ReleaseMutex(hGlobalDataMutex);
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
        goto LABEL_152;
      }
      goto LABEL_155;
    }
    if ( ((unsigned __int64)(a1 + 536870892) & 0xFFFFFFFFFFFFFFEFuLL) != 0 )
    {
      Names = -1073741811;
      goto LABEL_112;
    }
    nSize = 0;
    v46 = 0;
    v24 = 0;
    ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(36, &v46, 0, &nSize);
    Names = ThreadPreferredUILanguages;
    if ( (!ThreadPreferredUILanguages || ThreadPreferredUILanguages == -1073741789) && nSize )
    {
      v26 = operator new(saturated_mul(nSize, 2u));
      v24 = (_WORD *)v26;
      if ( v26 )
      {
        Names = RtlGetThreadPreferredUILanguages(36, &v46, v26, &nSize);
        if ( !v46 )
        {
          operator delete(v24);
          v24 = 0;
        }
      }
      else
      {
        v46 = 0;
        Names = -1073741801;
      }
    }
    if ( a1 == HKEY_PERFORMANCE_TEXT )
    {
      Names = PerfGetNames(v45, &stru_1800206B8, &v51, (unsigned __int8 *)v50, a7, a8, L"009");
      if ( (int)(Names + 0x80000000) < 0 || Names == -2147483643 || !v24 || !*v24 )
        goto LABEL_108;
      v27 = -1;
      do
        ++v27;
      while ( v24[v27] );
      v28 = &v24[v27 + 1];
      if ( *v28 )
      {
        do
        {
          v29 = v28;
          v30 = -1;
          do
            ++v30;
          while ( v28[v30] );
          v28 += v30 + 1;
        }
        while ( *v28 );
      }
      else
      {
        v29 = v24;
      }
      LangIdFromSzLang = GetLangIdFromSzLang(v29);
      v32 = LangIdFromSzLang;
      *(_OWORD *)&NativeLangId = 0;
      PerfGetLangId(LangIdFromSzLang, 0, &NativeLangId, 8u);
      if ( a7 )
        *a7 = v20;
      if ( a8 )
        *a8 = 0;
      Names = PerfGetNames(v45, &stru_1800206B8, &v51, (unsigned __int8 *)v50, a7, a8, &NativeLangId);
      if ( (int)(Names + 0x80000000) < 0 || Names == -2147483643 )
        goto LABEL_108;
      *(_OWORD *)&NativeLangId = 0;
      PerfGetLangId(v32 & 0x3FF, 1u, &NativeLangId, 8u);
      if ( a7 )
        *a7 = v20;
      if ( a8 )
        *a8 = 0;
      v33 = PerfGetNames(v45, &stru_1800206B8, &v51, (unsigned __int8 *)v50, a7, a8, &NativeLangId);
    }
    else
    {
      if ( a1 != HKEY_PERFORMANCE_NLSTEXT )
        goto LABEL_108;
      if ( v24 && *v24 )
      {
        v34 = v24;
        do
        {
          v53 = GetLangIdFromSzLang(v34);
          *(_OWORD *)&NativeLangId = 0;
          PerfGetLangId(v53, 0, &NativeLangId, 8u);
          if ( a7 )
            *a7 = v20;
          if ( a8 )
            *a8 = 0;
          v35 = PerfGetNames(v45, &stru_1800206B8, &v51, (unsigned __int8 *)v50, a7, a8, &NativeLangId);
          Names = v35;
          if ( v35 >= 0 )
            break;
          if ( v35 == -2147483643 )
            goto LABEL_108;
          *(_OWORD *)&NativeLangId = 0;
          PerfGetLangId(v53 & 0x3FF, 1u, &NativeLangId, 8u);
          if ( a7 )
            *a7 = v20;
          if ( a8 )
            *a8 = 0;
          v36 = PerfGetNames(v45, &stru_1800206B8, &v51, (unsigned __int8 *)v50, a7, a8, &NativeLangId);
          Names = v36;
          if ( v36 >= 0 )
            break;
          if ( v36 == -2147483643 )
            goto LABEL_108;
          v37 = -1;
          do
            ++v37;
          while ( v34[v37] );
          v34 += v37 + 1;
        }
        while ( *v34 );
        if ( Names == -2147483643 || Names >= 0 )
          goto LABEL_108;
      }
      if ( a7 )
        *a7 = v20;
      if ( a8 )
        *a8 = 0;
      v33 = PerfGetNames(v45, &stru_1800206B8, &v51, (unsigned __int8 *)v50, a7, a8, L"009");
    }
    Names = v33;
LABEL_108:
    if ( v46 )
      operator delete(v24);
    goto LABEL_110;
  }
  ExtensibleData = 170;
  v10 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 23;
    v17 = v21;
    goto LABEL_21;
  }
LABEL_155:
  if ( dwBoostPriority && v48 > 0 && v48 != v47 )
  {
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &v48, 4u);
    v10 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_d(v10[2], 31, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, ExtensibleData);
  return ExtensibleData;
}

```

## disassembly

```asm
0x1800093a8  mov     [rsp-8+arg_8], rbx
0x1800093ad  push    rbp
0x1800093ae  push    rsi
0x1800093af  push    rdi
0x1800093b0  push    r12
0x1800093b2  push    r13
0x1800093b4  push    r14
0x1800093b6  push    r15
0x1800093b8  lea     rbp, [rsp-320h]
0x1800093c0  sub     rsp, 420h
0x1800093c7  mov     rax, cs:__security_cookie
0x1800093ce  xor     rax, rsp
0x1800093d1  mov     [rbp+350h+var_40], rax
0x1800093d8  mov     rax, [rbp+350h+arg_20]
0x1800093df  lea     rdx, PerfpInitializeCallback
0x1800093e6  mov     r15, [rbp+350h+arg_30]
0x1800093ed  xor     r12d, r12d
0x1800093f0  mov     r14, [rbp+350h+arg_38]
0x1800093f7  xorps   xmm0, xmm0
0x1800093fa  mov     [rbp+350h+var_3C8], rax
0x1800093fe  mov     rbx, r8
0x180009401  mov     rax, [rbp+350h+arg_28]
0x180009408  mov     r13, rcx
0x18000940b  xor     r9d, r9d
0x18000940e  mov     [rsp+450h+var_3F8], rax
0x180009413  xor     r8d, r8d
0x180009416  mov     [rsp+450h+var_3E0], r12
0x18000941b  lea     rcx, qword_18002B570
0x180009422  mov     qword ptr [rsp+450h+var_3F0.Length], r12
0x180009427  mov     [rsp+450h+var_3F0.Buffer], r12
0x18000942c  mov     qword ptr [rbp+350h+Timeout], r12
0x180009430  movups  [rbp+350h+ThreadInformation], xmm0
0x180009434  mov     [rsp+450h+var_404], r12d
0x180009439  movups  [rbp+350h+var_378], xmm0
0x18000943d  mov     [rsp+450h+var_408], r12d
0x180009442  movups  [rbp+350h+var_368], xmm0
0x180009446  call    cs:__imp_RtlRunOnceExecuteOnce
0x18000944c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009453  test    byte ptr [rcx+1Ch], 1
0x180009457  jz      short loc_18000947E
0x180009459  cmp     byte ptr [rcx+19h], 4
0x18000945d  jb      short loc_18000947E
0x18000945f  mov     rcx, [rcx+10h]
0x180009463  lea     edx, [r12+12h]
0x180009468  mov     r9, rbx
0x18000946b  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180009472  call    WPP_SF_Z
0x180009477  mov     rcx, cs:WPP_GLOBAL_Control
0x18000947e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009482  mov     [rsp+450h+var_3E0], r12
0x180009487  mov     [rsp+450h+var_408], eax
0x18000948b  mov     [rsp+450h+var_404], eax
0x18000948f  test    rbx, rbx
0x180009492  jz      loc_180009DB2
0x180009498  cmp     [rbx+8], r12
0x18000949c  jz      loc_180009DB2
0x1800094a2  movups  xmm0, xmmword ptr [rbx]
0x1800094a5  mov     rcx, [rbx+8]; String1
0x1800094a9  movups  xmmword ptr [rsp+450h+var_3F0.Length], xmm0
0x1800094ae  call    ?GetQueryType@@YAKPEAG@Z; GetQueryType(ushort *)
0x1800094b3  mov     [rsp+450h+var_410], eax
0x1800094b7  movzx   r12d, ax
0x1800094bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094c2  test    byte ptr [rcx+1Ch], 2
0x1800094c6  jz      short loc_1800094E6
0x1800094c8  cmp     byte ptr [rcx+19h], 4
0x1800094cc  jb      short loc_1800094E6
0x1800094ce  mov     rcx, [rcx+10h]
0x1800094d2  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x1800094d9  mov     edx, 13h
0x1800094de  mov     r9d, r12d
0x1800094e1  call    WPP_SF_d
0x1800094e6  mov     edi, 5
0x1800094eb  movzx   eax, r12w
0x1800094ef  sub     ax, di
0x1800094f2  lea     ecx, [rdi-2]
0x1800094f5  cmp     ax, cx
0x1800094f8  mov     rcx, r13
0x1800094fb  setbe   sil
0x1800094ff  mov     dl, sil
0x180009502  call    PerfOpenKey
0x180009507  mov     ebx, eax
0x180009509  test    eax, eax
0x18000950b  jnz     loc_180009DA6
0x180009511  call    TestClientForAccess
0x180009516  xor     ebx, ebx
0x180009518  test    eax, eax
0x18000951a  jnz     loc_1800095DA
0x180009520  lea     r8, ?PerfpErrorLog@@3UERROR_LOG@@A; struct ERROR_LOG *
0x180009527  xor     edx, edx; HKEY
0x180009529  mov     ecx, 3E8h; unsigned int
0x18000952e  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x180009533  xor     r12d, r12d
0x180009536  test    eax, eax
0x180009538  jz      short loc_1800095A0
0x18000953a  lea     r8, [rsp+450h+nSize]; nSize
0x18000953f  mov     [rsp+450h+nSize], 80h
0x180009547  lea     rdx, [rbp+350h+NameBuffer]; lpNameBuffer
0x18000954b  mov     ecx, 10002h; NameFormat
0x180009550  call    cs:__imp_GetUserNameExW
0x180009556  test    al, al
0x180009558  jnz     short loc_18000955F
0x18000955a  mov     [rbp+350h+NameBuffer], r12w
0x18000955f  mov     r8d, 104h; nSize
0x180009565  lea     rdx, [rbp+350h+Filename]; lpFilename
0x18000956c  xor     ecx, ecx; hModule
0x18000956e  call    cs:__imp_GetModuleFileNameW
0x180009574  test    eax, eax
0x180009576  jnz     short loc_180009580
0x180009578  mov     [rbp+350h+Filename], r12w
0x180009580  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x180009587  jz      short loc_1800095A0
0x180009589  lea     r9, [rbp+350h+Filename]
0x180009590  lea     r8, [rbp+350h+NameBuffer]
0x180009594  lea     rdx, PERFLIB_ACCESS_DENIED
0x18000959b  call    McTemplateU0zz_EtwEventWriteTransfer
0x1800095a0  mov     ebx, edi
0x1800095a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095a9  test    byte ptr [rcx+1Ch], 2
0x1800095ad  jz      loc_180009DB7
0x1800095b3  cmp     byte ptr [rcx+19h], 2
0x1800095b7  jb      loc_180009DB7
0x1800095bd  mov     edx, 14h
0x1800095c2  mov     r9d, edi
0x1800095c5  mov     rcx, [rcx+10h]
0x1800095c9  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x1800095d0  call    WPP_SF_d
0x1800095d5  jmp     loc_180009D9D
0x1800095da  cmp     cs:?dwBoostPriority@@3KA, ebx; ulong dwBoostPriority
0x1800095e0  jz      loc_18000969D
0x1800095e6  xor     edx, edx; ThreadInformationClass
0x1800095e8  mov     [rsp+450h+ReturnLength], rbx; ReturnLength
0x1800095ed  mov     r9d, 30h ; '0'; ThreadInformationLength
0x1800095f3  lea     r8, [rbp+350h+ThreadInformation]; ThreadInformation
0x1800095f7  lea     rdi, [rdx-2]
0x1800095fb  mov     rcx, rdi; ThreadHandle
0x1800095fe  call    cs:__imp_NtQueryInformationThread
0x180009604  test    eax, eax
0x180009606  js      short loc_180009662
0x180009608  mov     eax, dword ptr [rbp+350h+var_368+8]
0x18000960b  mov     [rsp+450h+var_404], eax
0x18000960f  dec     eax
0x180009611  mov     [rsp+450h+var_408], 0Fh
0x180009619  cmp     eax, 0Dh
0x18000961c  ja      short loc_180009695
0x18000961e  lea     r9d, [rdi+6]; ThreadInformationLength
0x180009622  mov     rcx, rdi; ThreadHandle
0x180009625  lea     r8, [rsp+450h+var_408]; ThreadInformation
0x18000962a  lea     edx, [rdi+4]; ThreadInformationClass
0x18000962d  call    cs:__imp_NtSetInformationThread
0x180009633  test    eax, eax
0x180009635  jns     short loc_18000969D
0x180009637  mov     rcx, cs:WPP_GLOBAL_Control
0x18000963e  test    byte ptr [rcx+1Ch], 2
0x180009642  jz      short loc_180009695
0x180009644  cmp     byte ptr [rcx+19h], 2
0x180009648  jb      short loc_180009695
0x18000964a  mov     rcx, [rcx+10h]
0x18000964e  lea     edx, [rdi+18h]
0x180009651  mov     r9d, eax
0x180009654  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18000965b  call    WPP_SF_d
0x180009660  jmp     short loc_180009695
0x180009662  mov     rcx, cs:WPP_GLOBAL_Control
0x180009669  test    byte ptr [rcx+1Ch], 2
0x18000966d  jz      short loc_18000968D
0x18000966f  cmp     byte ptr [rcx+19h], 2
0x180009673  jb      short loc_18000968D
0x180009675  mov     rcx, [rcx+10h]
0x180009679  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180009680  mov     edx, 15h
0x180009685  mov     r9d, eax
0x180009688  call    WPP_SF_d
0x18000968d  mov     [rsp+450h+var_408], 0Fh
0x180009695  mov     [rsp+450h+var_404], 0FFFFFFFFh
0x18000969d  mov     edi, ebx
0x18000969f  test    r14, r14
0x1800096a2  jz      short loc_1800096A7
0x1800096a4  mov     [r14], ebx
0x1800096a7  test    r15, r15
0x1800096aa  jz      short loc_1800096AF
0x1800096ac  mov     edi, [r15]
0x1800096af  mov     rcx, cs:?hGlobalDataMutex@@3PEAXEA; Handle
0x1800096b6  lea     r8, [rbp+350h+Timeout]; Timeout
0x1800096ba  xor     edx, edx; Alertable
0x1800096bc  mov     qword ptr [rbp+350h+Timeout], 0FFFFFFFFFECED300h
0x1800096c4  test    sil, sil
0x1800096c7  jz      loc_180009BE2
0x1800096cd  call    cs:__imp_NtWaitForSingleObject
0x1800096d3  xor     r12d, r12d
0x1800096d6  test    eax, eax
0x1800096d8  jz      short loc_180009707
0x1800096da  mov     ebx, 0AAh
0x1800096df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096e6  test    byte ptr [rcx+1Ch], 2
0x1800096ea  jz      loc_180009DB7
0x1800096f0  cmp     byte ptr [rcx+19h], 2
0x1800096f4  jb      loc_180009DB7
0x1800096fa  lea     edx, [r12+17h]
0x1800096ff  mov     r9d, eax
0x180009702  jmp     loc_1800095C5
0x180009707  mov     rcx, cs:WPP_GLOBAL_Control
0x18000970e  test    byte ptr [rcx+1Ch], 2
0x180009712  jz      short loc_180009736
0x180009714  cmp     byte ptr [rcx+19h], 4
0x180009718  jb      short loc_180009736
0x18000971a  mov     rcx, [rcx+10h]
0x18000971e  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180009725  mov     edx, 18h
0x18000972a  call    WPP_SF_
0x18000972f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009736  cmp     r13, 0FFFFFFFF80000004h
0x18000973d  jnz     short loc_18000976F
0x18000973f  mov     r9, [rsp+450h+var_3F8]; unsigned __int8 *
0x180009744  lea     r8, [rsp+450h+var_3F0]; struct _UNICODE_STRING *
0x180009749  mov     ecx, [rsp+450h+var_410]; unsigned int
0x18000974d  lea     rdx, stru_1800206B8; struct _UNICODE_STRING *
0x180009754  mov     [rsp+450h+var_420], r12; unsigned __int16 *
0x180009759  mov     [rsp+450h+var_428], r14; unsigned int *
0x18000975e  mov     [rsp+450h+ReturnLength], r15; unsigned int *
0x180009763  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x180009768  mov     ebx, eax
0x18000976a  jmp     loc_180009B51
0x18000976f  lea     rax, [r13+7FFFFFB0h]
0x180009776  test    rax, 0FFFFFFFFFFFFFFEFh
0x18000977c  jz      short loc_180009788
0x18000977e  mov     ebx, 0C000000Dh
0x180009783  jmp     loc_180009B5C
0x180009788  xor     r8d, r8d
0x18000978b  mov     [rsp+450h+nSize], r12d
0x180009790  lea     r9, [rsp+450h+nSize]
0x180009795  mov     [rsp+450h+var_40C], r12d
0x18000979a  lea     rdx, [rsp+450h+var_40C]
0x18000979f  mov     rsi, r12
0x1800097a2  lea     ecx, [r8+24h]
0x1800097a6  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x1800097ac  mov     ebx, eax
0x1800097ae  test    eax, eax
0x1800097b0  jz      short loc_1800097B9
0x1800097b2  cmp     eax, 0C0000023h
0x1800097b7  jnz     short loc_18000981E
0x1800097b9  mov     eax, [rsp+450h+nSize]
0x1800097bd  test    eax, eax
0x1800097bf  jz      short loc_18000981E
0x1800097c1  mov     edx, eax
0x1800097c3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800097ca  mov     eax, 2
0x1800097cf  mul     rdx
0x1800097d2  cmovb   rax, rcx
0x1800097d6  mov     rcx, rax
0x1800097d9  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800097de  mov     rsi, rax
0x1800097e1  test    rax, rax
0x1800097e4  jz      short loc_180009814
0x1800097e6  lea     r9, [rsp+450h+nSize]
0x1800097eb  mov     r8, rax
0x1800097ee  lea     rdx, [rsp+450h+var_40C]
0x1800097f3  mov     ecx, 24h ; '$'
0x1800097f8  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x1800097fe  mov     ebx, eax
0x180009800  cmp     [rsp+450h+var_40C], r12d
0x180009805  jnz     short loc_18000981E
0x180009807  mov     rcx, rsi; Block
0x18000980a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000980f  mov     rsi, r12
0x180009812  jmp     short loc_18000981E
0x180009814  mov     [rsp+450h+var_40C], r12d
0x180009819  mov     ebx, 0C0000017h
0x18000981e  cmp     r13, 0FFFFFFFF80000050h
0x180009825  jnz     loc_1800099B7
0x18000982b  mov     r9, [rsp+450h+var_3F8]; unsigned __int8 *
0x180009830  lea     rax, ?DefaultLangId@@3QBGB; "009"
0x180009837  mov     ecx, [rsp+450h+var_410]; unsigned int
0x18000983b  lea     r8, [rsp+450h+var_3F0]; struct _UNICODE_STRING *
0x180009840  mov     [rsp+450h+var_420], rax; unsigned __int16 *
0x180009845  lea     rdx, stru_1800206B8; struct _UNICODE_STRING *
0x18000984c  mov     [rsp+450h+var_428], r14; unsigned int *
0x180009851  mov     [rsp+450h+ReturnLength], r15; unsigned int *
0x180009856  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x18000985b  mov     ecx, 80000000h
0x180009860  mov     ebx, eax
0x180009862  add     eax, ecx
0x180009864  test    ecx, eax
0x180009866  jnz     loc_180009B42
0x18000986c  cmp     ebx, 80000005h
0x180009872  jz      loc_180009B42
0x180009878  test    rsi, rsi
0x18000987b  jz      loc_180009B42
0x180009881  cmp     [rsi], r12w
0x180009885  jz      loc_180009B42
0x18000988b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000988f  inc     rax
0x180009892  cmp     [rsi+rax*2], r12w
0x180009897  jnz     short loc_18000988F
0x180009899  inc     rax
0x18000989c  lea     rax, [rsi+rax*2]
0x1800098a0  cmp     [rax], r12w
0x1800098a4  jz      short loc_1800098C7
0x1800098a6  mov     rdx, rax
0x1800098a9  or      rcx, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
