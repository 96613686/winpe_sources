# PerflibciLocalValidateCounters

- ea: `0x180005f20`
- end: `0x1800069a9`
- name: `PerflibciLocalValidateCounters`
- size: `2697`
- prototype: `__int64 __fastcall(struct _PERF_QUERY *, __int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015250`
- `0x180019060`

## callees

- `0x180002dd0`
- `0x180005f20`
- `0x1800069b0`
- `0x180006bc0`
- `0x180007740`
- `0x180008042`
- `0x180008050`
- `0x18000805c`
- `0x180015e20`
- `0x18001e431`
- `0x18001e43d`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800061a9`
- `ntdll!RtlNtStatusToDosError` at `0x18000655c`
- `ntdll!RtlNtStatusToDosError` at `0x18000660d`
- `ntdll!RtlNtStatusToDosError` at `0x1800066a1`
- `ntdll!RtlNtStatusToDosError` at `0x1800061a9`
- `ntdll!RtlNtStatusToDosError` at `0x18000655c`
- `ntdll!RtlNtStatusToDosError` at `0x18000660d`
- `ntdll!RtlNtStatusToDosError` at `0x1800066a1`
- `ntdll!RtlInitUnicodeString` at `0x180006187`
- `ntdll!RtlInitUnicodeString` at `0x18000662f`
- `ntdll!RtlInitUnicodeString` at `0x180006187`
- `ntdll!RtlInitUnicodeString` at `0x18000662f`
- `ntdll!NtClose` at `0x18000622e`
- `ntdll!NtClose` at `0x18000622e`
- `ntdll!RtlInitUnicodeStringEx` at `0x180006601`
- `ntdll!RtlInitUnicodeStringEx` at `0x180006601`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800066c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800066c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006073`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006073`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000630f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800065ea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000681c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000630f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800065ea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000681c`
- `api-ms-win-core-pcw-l1-1-0!PcwAddQueryItem` at `0x180006695`
- `api-ms-win-core-pcw-l1-1-0!PcwAddQueryItem` at `0x180006695`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateNotifier` at `0x18000619d`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateNotifier` at `0x18000619d`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateQuery` at `0x180006550`
- `api-ms-win-core-pcw-l1-1-0!PcwCreateQuery` at `0x180006550`
- `api-ms-win-core-pcw-l1-1-0!PcwRemoveQueryItem` at `0x18000650e`
- `api-ms-win-core-pcw-l1-1-0!PcwRemoveQueryItem` at `0x18000650e`

## pseudocode

```c
__int64 __fastcall PerflibciLocalValidateCounters(struct _PERF_QUERY *a1, __int64 a2, unsigned int a3, int a4)
{
  BOOL v4; // r12d
  struct PERFLIBCI_QUERY_PROVIDER_NODE *v5; // rbx
  __int64 v6; // r14
  struct _PERF_QUERY *v7; // rdi
  unsigned int updated; // ebp
  unsigned int v9; // edx
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rbx
  _QWORD *v13; // rbp
  struct _RTL_CRITICAL_SECTION *CounterSet; // rax
  struct _RTL_CRITICAL_SECTION *v15; // r13
  _OWORD *v16; // r14
  _QWORD *OwningThread; // rdx
  _QWORD *v18; // rcx
  _DWORD *v19; // rax
  NTSTATUS v20; // eax
  ULONG v21; // ebx
  _OWORD *v22; // rax
  int v23; // edx
  LONG LockCount; // ecx
  _DWORD *i; // rax
  unsigned int v26; // eax
  int v27; // eax
  unsigned int v28; // edi
  unsigned int *v29; // rsi
  __int64 v30; // rbx
  unsigned int v31; // eax
  unsigned int v32; // eax
  struct _PERF_QUERY *v33; // r15
  unsigned int v34; // edx
  int v35; // r8d
  unsigned int v36; // ecx
  unsigned int v37; // eax
  unsigned int v38; // esi
  unsigned int v39; // ebx
  void *v40; // rax
  void *v41; // rdi
  const void *v42; // rdx
  __int64 v43; // rdi
  unsigned int v44; // ecx
  __int64 v45; // rax
  bool v46; // zf
  int Query; // eax
  unsigned int v48; // ecx
  unsigned int v49; // r8d
  __int64 v50; // rbx
  unsigned int j; // edx
  __int64 v52; // rax
  __int64 v53; // r8
  int v54; // edx
  PWSTR Buffer; // rcx
  WCHAR v56; // ax
  unsigned int v57; // r14d
  __int64 v58; // rax
  _QWORD *v59; // rdi
  __int64 v60; // rax
  __int64 *v61; // rbx
  _QWORD *v62; // rdx
  _QWORD *v63; // rcx
  int v64; // eax
  unsigned int v65; // ebp
  __int64 v66; // rsi
  unsigned int v67; // eax
  int v68; // eax
  __int64 *v69; // r8
  unsigned int v70; // edx
  __int64 v71; // rax
  __int64 *k; // rdi
  unsigned int v73; // r8d
  __int64 v74; // r9
  __int64 v75; // rax
  int v76; // edx
  int v77; // edx
  __int64 v78; // r8
  __int64 result; // rax
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-148h]
  __int64 v81; // [rsp+28h] [rbp-140h]
  int v82[2]; // [rsp+30h] [rbp-138h]
  __int64 v83; // [rsp+38h] [rbp-130h]
  __int64 v84; // [rsp+40h] [rbp-128h]
  __int64 v85; // [rsp+48h] [rbp-120h]
  __int64 v86; // [rsp+50h] [rbp-118h]
  __int64 v87; // [rsp+58h] [rbp-110h]
  __int64 v88; // [rsp+60h] [rbp-108h]
  __int64 v89; // [rsp+68h] [rbp-100h]
  unsigned int v91; // [rsp+78h] [rbp-F0h]
  unsigned int v92; // [rsp+7Ch] [rbp-ECh]
  HANDLE Handle; // [rsp+88h] [rbp-E0h] BYREF
  __int64 v95; // [rsp+90h] [rbp-D8h]
  struct _UNICODE_STRING v96; // [rsp+98h] [rbp-D0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A8h] [rbp-C0h]
  __int64 v98; // [rsp+B0h] [rbp-B8h]
  _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-B0h] BYREF
  WCHAR SourceString[40]; // [rsp+D0h] [rbp-98h] BYREF

  v4 = a4 != 0;
  LODWORD(v5) = 0;
  v95 = a2;
  v6 = a2;
  v7 = a1;
  if ( !a1 || !a2 || a3 < 0x28 )
  {
    updated = 87;
    goto LABEL_176;
  }
  updated = 0;
  v9 = 0;
  do
  {
    if ( a3 - v9 < 0x28 )
      break;
    *(_DWORD *)(v9 + v6 + 36) = !v4 - 3;
    v10 = *(_DWORD *)(v9 + v6 + 20);
    if ( v10 < 0x28 )
      break;
    v9 += v10;
    if ( v9 < v10 )
    {
      updated = 87;
      break;
    }
  }
  while ( v9 < a3 );
  if ( v9 != a3 )
  {
    updated = 87;
    goto LABEL_176;
  }
  if ( (*((_BYTE *)a1 + 32) & 1) != 0 )
  {
    updated = 87;
    goto LABEL_176;
  }
  if ( !updated )
  {
    v91 = PerflibciEnsureCounterSetList();
    updated = v91;
    if ( !v91 )
    {
      v11 = 0;
      v92 = 0;
      while ( 1 )
      {
        v12 = v11;
        v13 = (_QWORD *)(v6 + v11);
        v98 = v11;
        CounterSet = (struct _RTL_CRITICAL_SECTION *)PerflibciCreateOrFindCounterSet(v13, 0, 0, 0);
        v15 = CounterSet;
        if ( !CounterSet )
        {
          *(_DWORD *)(v12 + v6 + 16) = 4200;
          goto LABEL_129;
        }
        lpCriticalSection = CounterSet + 1;
        EnterCriticalSection(CounterSet + 1);
        *(_DWORD *)(v12 + v6 + 16) = 0;
        v16 = (_OWORD *)*((_QWORD *)v7 + 3);
        if ( !v16 )
          break;
        OwningThread = v15->OwningThread;
        while ( 1 )
        {
          v18 = (_QWORD *)*((_QWORD *)v16 + 1);
          if ( *v18 == *OwningThread
            && v18[1] == OwningThread[1]
            && *((_QWORD *)v16 + 7) == *v13
            && *((_QWORD *)v16 + 8) == v13[1] )
          {
            break;
          }
          v16 = *(_OWORD **)v16;
          if ( !v16 )
            goto LABEL_27;
        }
LABEL_40:
        if ( *((_DWORD *)v13 + 4) )
          goto LABEL_128;
        v23 = *((_DWORD *)v13 + 6);
        if ( v23 != -1 )
        {
          LockCount = v15[3].LockCount;
          if ( LockCount )
          {
            for ( i = &v15[3].DebugInfo->Type; i; i += 14 )
            {
              if ( *i == v23 )
                goto LABEL_49;
              if ( !--LockCount )
                break;
            }
          }
          *((_DWORD *)v13 + 4) = 4202;
        }
LABEL_49:
        if ( *((_DWORD *)v13 + 4) )
          goto LABEL_128;
        v26 = *((_DWORD *)v13 + 5);
        if ( (v15[2].LockCount & 2) != 0 )
        {
          if ( v26 > 0x28 )
          {
            v27 = 0;
          }
          else
          {
            *((_DWORD *)v13 + 4) = 87;
            v27 = 87;
          }
          if ( v27 )
            goto LABEL_128;
        }
        else if ( v26 > 0x28 )
        {
          *((_DWORD *)v13 + 4) = 87;
          goto LABEL_128;
        }
        v28 = 0;
        v29 = (unsigned int *)v13 + 5;
        if ( !*((_DWORD *)v16 + 7) )
          goto LABEL_73;
        while ( 1 )
        {
          v30 = *((_QWORD *)v16 + 2) + v28;
          if ( *(_DWORD *)(v30 + 24) == *((_DWORD *)v13 + 6) )
          {
            v31 = *v29;
            if ( *(_DWORD *)(v30 + 20) <= 0x28u )
            {
              if ( v31 <= 0x28 )
                break;
              goto LABEL_72;
            }
            if ( v31 > 0x28
              && *(_DWORD *)(v30 + 28) == *((_DWORD *)v13 + 7)
              && CompareStringOrdinal((LPCWCH)(v30 + 40), -1, (LPCWCH)v13 + 20, -1, 1) == 2 )
            {
              break;
            }
          }
LABEL_72:
          v28 += *(_DWORD *)(v30 + 20);
          if ( v28 >= *((_DWORD *)v16 + 7) )
            goto LABEL_73;
        }
        v32 = *(_DWORD *)(v30 + 16);
        if ( !v4 )
        {
          if ( v32 != -2 )
          {
            v33 = a1;
            if ( v32 == 1223 )
            {
              if ( *(_DWORD *)(v30 + 36) == -2 )
              {
                *((_DWORD *)v13 + 4) = 1168;
                goto LABEL_74;
              }
            }
            else
            {
              if ( *(_DWORD *)(*((_QWORD *)v16 + 1) + 32LL) == 1 )
              {
                PcwRemoveQueryItem(*((_QWORD *)a1 + 9), *(unsigned int *)(v30 + 36));
                *(_DWORD *)(v30 + 16) = -2;
                *(_DWORD *)(v30 + 36) = 0;
                goto LABEL_74;
              }
              *(_DWORD *)(v30 + 16) = 1223;
            }
            *(_DWORD *)(v30 + 36) = -2;
            goto LABEL_74;
          }
          *((_DWORD *)v13 + 4) = 1168;
          goto LABEL_73;
        }
        if ( v32 > 0x1068 )
        {
          if ( v32 == 4201 )
          {
LABEL_89:
            *((_DWORD *)v13 + 4) = 183;
          }
          else
          {
LABEL_88:
            *(_DWORD *)(v30 + 16) = 1223;
            *(_DWORD *)(v30 + 36) = -3;
          }
LABEL_73:
          v33 = a1;
          goto LABEL_74;
        }
        if ( v32 == 4200 || !v32 || v32 == 3 )
          goto LABEL_89;
        if ( v32 != 1223 )
          goto LABEL_88;
        v33 = a1;
        if ( *(_DWORD *)(v30 + 36) == -3 )
          *((_DWORD *)v13 + 4) = 183;
        else
          *(_DWORD *)(v30 + 36) = -3;
LABEL_74:
        v34 = *((_DWORD *)v16 + 7);
        if ( v28 >= v34 )
        {
          if ( v4 )
          {
            v35 = *((_DWORD *)v16 + 6);
            v36 = (*v29 + 7) & 0xFFFFFFF8;
            if ( v35 - v34 >= v36 )
              goto LABEL_84;
            v37 = v35 + v36;
            if ( v35 + v36 >= v36
              && v37 < 0xFFFFDFFF
              && (v38 = *((_DWORD *)v33 + 23), v39 = (v37 + 0x1FFF) & (v38 - 0x2000), v39 >= v38)
              && (v40 = operator new(v39, (const struct std::nothrow_t *)&std::nothrow), (v41 = v40) != 0) )
            {
              memset_0(v40, 0, v39);
              v42 = (const void *)*((_QWORD *)v16 + 2);
              if ( v42 )
              {
                memcpy_0(v41, v42, *((unsigned int *)v16 + 7));
                operator delete(*((void **)v16 + 2));
              }
              *((_QWORD *)v16 + 2) = v41;
              *((_DWORD *)v16 + 6) = v39 - v38;
LABEL_84:
              v43 = *((unsigned int *)v16 + 7) + *((_QWORD *)v16 + 2);
              memcpy_0((void *)v43, v13, *((unsigned int *)v13 + 5));
              v44 = (*((_DWORD *)v13 + 5) + 7) & 0xFFFFFFF8;
              *(_DWORD *)(v43 + 20) = v44;
              v45 = *((_QWORD *)v16 + 1);
              *((_DWORD *)v16 + 7) += v44;
              if ( *(_DWORD *)(v45 + 32) != 1 )
              {
                *(_DWORD *)(v43 + 16) = 1223;
                goto LABEL_128;
              }
              v46 = *((_QWORD *)a1 + 9) == 0;
              v96 = 0;
              if ( v46 )
              {
                Query = PcwCreateQuery((char *)a1 + 72, 0);
                if ( Query < 0 )
                  goto LABEL_125;
              }
              v48 = *(_DWORD *)(v43 + 24);
              if ( v48 == -1 )
              {
                v49 = v15[3].LockCount;
                v50 = 0;
                if ( v49 )
                {
                  for ( j = 0; j < v49; ++j )
                  {
                    v52 = j;
                    v50 |= 1LL << *((_DWORD *)&v15[3].DebugInfo->Type + 14 * v52);
                  }
                }
                goto LABEL_111;
              }
              if ( v48 < 0x40 )
              {
                v50 = 1LL << v48;
LABEL_111:
                if ( *(_DWORD *)(v43 + 20) == 40
                  || v15[2].LockCount == 6 && CompareStringOrdinal((LPCWCH)(v43 + 40), -1, L"_Total", -1, 1) == 2 )
                {
                  RtlInitUnicodeString(&v96, L"*");
                  v54 = -1;
                }
                else
                {
                  Query = RtlInitUnicodeStringEx(&v96, (PCWSTR)(v43 + 40));
                  if ( Query < 0 )
                    goto LABEL_125;
                  v54 = *(_DWORD *)(v43 + 28);
                }
                Buffer = v96.Buffer;
                LOBYTE(v53) = 0;
                if ( v96.Buffer )
                {
                  v56 = *v96.Buffer;
                  if ( *v96.Buffer )
                  {
                    while ( v56 != 63 && v56 != 42 )
                    {
                      v56 = Buffer[1];
                      ++Buffer;
                      if ( !v56 )
                        goto LABEL_124;
                    }
                    LOBYTE(v53) = 1;
                  }
                }
LABEL_124:
                Query = PcwAddQueryItem(
                          v43 + 36,
                          *((_QWORD *)a1 + 9),
                          v53,
                          &v15[2].LockSemaphore,
                          &v96,
                          v54,
                          v50,
                          0xFFFFFFFFLL);
                if ( Query >= 0 )
                  *(_DWORD *)(v43 + 16) = 0;
                else
LABEL_125:
                  *(_DWORD *)(v43 + 16) = RtlNtStatusToDosError(Query);
              }
              else
              {
                *(_DWORD *)(v43 + 16) = 87;
              }
            }
            else
            {
              *((_DWORD *)v13 + 4) = 14;
            }
          }
          else
          {
            *((_DWORD *)v13 + 4) = 1168;
          }
        }
LABEL_128:
        LeaveCriticalSection(lpCriticalSection);
        v12 = v98;
        v7 = a1;
        v6 = v95;
LABEL_129:
        v11 = *(_DWORD *)(v6 + v12 + 20) + v92;
        v92 = v11;
        if ( v11 >= a3 )
        {
          v5 = (struct PERFLIBCI_QUERY_PROVIDER_NODE *)*((_QWORD *)v7 + 3);
          updated = 0;
          while ( v5 )
          {
            if ( *(_DWORD *)(*((_QWORD *)v5 + 1) + 32LL) != 1 )
            {
              updated = PerflibciSendCounterUpdateRequest(v7, v5, v4);
              v91 = updated;
            }
            v5 = *(struct PERFLIBCI_QUERY_PROVIDER_NODE **)v5;
            if ( updated )
            {
              LODWORD(v5) = 0;
              goto LABEL_176;
            }
          }
          v57 = 0;
          v58 = v95;
          while ( 1 )
          {
            v59 = (_QWORD *)(v58 + v57);
            v60 = PerflibciCreateOrFindCounterSet(v59, 0, 0, 0);
            if ( *((_DWORD *)v59 + 4) )
              goto LABEL_163;
            v61 = (__int64 *)*((_QWORD *)a1 + 3);
            if ( !v61 )
            {
LABEL_145:
              v64 = 87;
              if ( v4 )
                v64 = 14;
              *((_DWORD *)v59 + 4) = v64;
              goto LABEL_162;
            }
            v62 = *(_QWORD **)(v60 + 16);
            while ( 1 )
            {
              v63 = (_QWORD *)v61[1];
              if ( *v63 == *v62 && v63[1] == v62[1] && v61[7] == *v59 && v61[8] == v59[1] )
                break;
              v61 = (__int64 *)*v61;
              if ( !v61 )
                goto LABEL_145;
            }
            v65 = 0;
            if ( !*((_DWORD *)v61 + 7) )
              goto LABEL_156;
            while ( 1 )
            {
              v66 = v61[2] + v65;
              if ( *(_DWORD *)(v66 + 24) != *((_DWORD *)v59 + 6) )
                goto LABEL_160;
              v67 = *((_DWORD *)v59 + 5);
              if ( *(_DWORD *)(v66 + 20) > 0x28u )
                break;
              if ( v67 <= 0x28 )
                goto LABEL_154;
LABEL_160:
              v65 += *(_DWORD *)(v66 + 20);
              if ( v65 >= *((_DWORD *)v61 + 7) )
                goto LABEL_155;
            }
            if ( v67 <= 0x28
              || *(_DWORD *)(v66 + 28) != *((_DWORD *)v59 + 7)
              || CompareStringOrdinal((LPCWCH)(v66 + 40), -1, (LPCWCH)v59 + 20, -1, 1) != 2 )
            {
              goto LABEL_160;
            }
LABEL_154:
            *((_DWORD *)v59 + 4) = *(_DWORD *)(v66 + 16);
LABEL_155:
            if ( v65 >= *((_DWORD *)v61 + 7) )
            {
LABEL_156:
              v68 = 14;
              if ( !v4 )
                v68 = 87;
              *((_DWORD *)v59 + 4) = v68;
            }
LABEL_162:
            LODWORD(v5) = 0;
LABEL_163:
            v58 = v95;
            v57 += *(_DWORD *)(v57 + v95 + 20);
            if ( v57 >= a3 )
            {
              v69 = (__int64 *)*((_QWORD *)a1 + 3);
              v7 = a1;
              if ( v69 )
              {
                while ( 1 )
                {
                  if ( *(_DWORD *)(v69[1] + 32) != 1 )
                  {
                    v70 = 0;
                    if ( *((_DWORD *)v69 + 7) )
                      break;
                  }
LABEL_174:
                  v69 = (__int64 *)*v69;
                  if ( !v69 )
                    goto LABEL_175;
                }
                while ( 2 )
                {
                  v71 = v69[2];
                  if ( v4 )
                  {
                    if ( *(_DWORD *)(v70 + v71 + 36) == -3 )
                      goto LABEL_172;
                  }
                  else if ( *(_DWORD *)(v70 + v71 + 36) == -2 )
                  {
                    if ( !*(_DWORD *)(v70 + v71 + 16) )
                      *(_DWORD *)(v70 + v71 + 16) = -2;
LABEL_172:
                    *(_DWORD *)(v70 + v71 + 36) = 0;
                  }
                  v70 += *(_DWORD *)(v70 + v71 + 20);
                  if ( v70 >= *((_DWORD *)v69 + 7) )
                    goto LABEL_174;
                  continue;
                }
              }
LABEL_175:
              updated = v91;
              goto LABEL_176;
            }
          }
        }
      }
LABEL_27:
      if ( !v4 )
      {
        *((_DWORD *)v13 + 4) = 4200;
        goto LABEL_40;
      }
      v19 = v15->OwningThread;
      DestinationString = 0;
      Handle = 0;
      if ( v19[8] != 1 )
      {
        LODWORD(v89) = HIBYTE(v15->SpinCount);
        LODWORD(v88) = BYTE6(v15->SpinCount);
        LODWORD(v87) = BYTE5(v15->SpinCount);
        LODWORD(v86) = BYTE4(v15->SpinCount);
        LODWORD(v85) = BYTE3(v15->SpinCount);
        LODWORD(v84) = BYTE2(v15->SpinCount);
        LODWORD(v83) = BYTE1(v15->SpinCount);
        v82[0] = LOBYTE(v15->SpinCount);
        LODWORD(v81) = HIWORD(v15->LockSemaphore);
        bIgnoreCase[0] = WORD2(v15->LockSemaphore);
        StringCbPrintfW(
          SourceString,
          0x50u,
          L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
          LODWORD(v15->LockSemaphore),
          *(_QWORD *)bIgnoreCase,
          v81,
          *(_QWORD *)v82,
          v83,
          v84,
          v85,
          v86,
          v87,
          v88,
          v89);
        RtlInitUnicodeString(&DestinationString, SourceString);
        v20 = PcwCreateNotifier(&Handle, &DestinationString);
        if ( v20 < 0 )
        {
          v21 = RtlNtStatusToDosError(v20);
          if ( v21 )
          {
LABEL_37:
            if ( Handle )
              NtClose(Handle);
            goto LABEL_39;
          }
          goto LABEL_39;
        }
        v7 = a1;
      }
      v22 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v22 )
      {
        v21 = 14;
        goto LABEL_37;
      }
      *v22 = 0;
      v16 = v22;
      v21 = 0;
      v22[1] = 0;
      v22[2] = 0;
      v22[3] = 0;
      *((_QWORD *)v22 + 8) = 0;
      *((_QWORD *)v22 + 6) = Handle;
      *((_QWORD *)v22 + 1) = v15->OwningThread;
      *(_OWORD *)((char *)v22 + 56) = *(_OWORD *)&v15->LockSemaphore;
      *(_QWORD *)v22 = *((_QWORD *)v7 + 3);
      *((_QWORD *)v7 + 3) = v22;
LABEL_39:
      *((_DWORD *)v13 + 4) = v21;
      goto LABEL_40;
    }
  }
LABEL_176:
  for ( k = (__int64 *)*((_QWORD *)v7 + 3); k; LODWORD(v5) = 0 )
  {
    v73 = *((_DWORD *)k + 7);
    if ( v73 )
    {
      do
      {
        v74 = k[2];
        v75 = v74 + (unsigned int)v5;
        v76 = *(_DWORD *)(v75 + 16);
        if ( v76 && (v77 = v76 - 3) != 0 && (unsigned int)(v77 - 4197) >= 2 )
        {
          v78 = v73 - *(_DWORD *)(v75 + 20);
          *((_DWORD *)k + 7) = v78;
          memmove_0(
            (void *)(v74 + (unsigned int)v5),
            (const void *)(v75 + *(unsigned int *)(v75 + 20)),
            v78 - (unsigned int)v5);
        }
        else
        {
          LODWORD(v5) = *(_DWORD *)(v75 + 20) + (_DWORD)v5;
        }
        v73 = *((_DWORD *)k + 7);
      }
      while ( (unsigned int)v5 < v73 );
    }
    k = (__int64 *)*k;
  }
  result = updated;
  *((_DWORD *)a1 + 8) |= 2u;
  return result;
}

```

## disassembly

```asm
0x180005f20  mov     r11, rsp
0x180005f23  push    rbx
0x180005f24  push    rbp
0x180005f25  push    rdi
0x180005f26  push    r13
0x180005f28  sub     rsp, 148h
0x180005f2f  mov     rax, cs:__security_cookie
0x180005f36  xor     rax, rsp
0x180005f39  mov     [rsp+168h+var_48], rax
0x180005f41  mov     [r11-28h], r12
0x180005f45  test    r9d, r9d
0x180005f48  mov     r12d, 1
0x180005f4e  mov     [r11-30h], r14
0x180005f52  cmovz   r12d, r9d
0x180005f56  mov     [rsp+168h+var_E8], r8d
0x180005f5e  xor     ebx, ebx
0x180005f60  mov     [rsp+168h+var_D8], rdx
0x180005f68  mov     [rsp+168h+var_F8], rcx
0x180005f6d  mov     r14, rdx
0x180005f70  mov     rdi, rcx
0x180005f73  test    rcx, rcx
0x180005f76  jz      loc_180006960
0x180005f7c  test    rdx, rdx
0x180005f7f  jz      loc_180006960
0x180005f85  cmp     r8d, 28h ; '('
0x180005f89  jb      loc_180006960
0x180005f8f  mov     [r11+18h], rsi
0x180005f93  mov     ebp, ebx
0x180005f95  mov     edx, ebx
0x180005f97  nop     word ptr [rax+rax+00000000h]
0x180005fa0  mov     eax, r8d
0x180005fa3  mov     esi, 57h ; 'W'
0x180005fa8  sub     eax, edx
0x180005faa  cmp     eax, 28h ; '('
0x180005fad  jb      short loc_180005FDB
0x180005faf  cmp     r12d, 1
0x180005fb3  mov     ecx, edx
0x180005fb5  mov     eax, ebx
0x180005fb7  setnz   al
0x180005fba  add     eax, 0FFFFFFFDh
0x180005fbd  mov     [rcx+r14+24h], eax
0x180005fc2  mov     eax, [rcx+r14+14h]
0x180005fc7  cmp     eax, 28h ; '('
0x180005fca  jb      short loc_180005FDB
0x180005fcc  add     edx, eax
0x180005fce  cmp     edx, eax
0x180005fd0  jb      short loc_180005FD9
0x180005fd2  cmp     edx, r8d
0x180005fd5  jb      short loc_180005FA0
0x180005fd7  jmp     short loc_180005FDB
0x180005fd9  mov     ebp, esi
0x180005fdb  cmp     edx, r8d
0x180005fde  jz      short loc_180005FE7
0x180005fe0  mov     ebp, esi
0x180005fe2  jmp     loc_1800068F2
0x180005fe7  test    byte ptr [rdi+20h], 1
0x180005feb  jz      short loc_180005FF4
0x180005fed  mov     ebp, esi
0x180005fef  jmp     loc_1800068F2
0x180005ff4  test    ebp, ebp
0x180005ff6  jnz     loc_1800068F2
0x180005ffc  call    ?PerflibciEnsureCounterSetList@@YAKXZ; PerflibciEnsureCounterSetList(void)
0x180006001  mov     [rsp+168h+var_F0], eax
0x180006005  mov     ebp, eax
0x180006007  test    eax, eax
0x180006009  jnz     loc_1800068F2
0x18000600f  mov     [rsp+168h+var_38], r15
0x180006017  mov     eax, ebx
0x180006019  mov     [rsp+168h+var_EC], ebx
0x18000601d  nop     dword ptr [rax]
0x180006020  xor     ecx, ecx
0x180006022  mov     ebx, eax
0x180006024  mov     [rsp+168h+var_138], ecx; int
0x180006028  xor     r9d, r9d
0x18000602b  mov     [rsp+168h+var_140], cx; __int16
0x180006030  xor     r8d, r8d
0x180006033  mov     qword ptr [rsp+168h+bIgnoreCase], rcx; void *
0x180006038  xor     edx, edx
0x18000603a  lea     rbp, [r14+rbx]
0x18000603e  mov     [rsp+168h+var_B8], rbx
0x180006046  mov     rcx, rbp; Buf1
0x180006049  call    PerflibciCreateOrFindCounterSet
0x18000604e  mov     r13, rax
0x180006051  test    rax, rax
0x180006054  jnz     short loc_180006064
0x180006056  mov     dword ptr [rbx+r14+10h], 1068h
0x18000605f  jmp     loc_1800066E2
0x180006064  add     rax, 28h ; '('
0x180006068  mov     rcx, rax; lpCriticalSection
0x18000606b  mov     [rsp+168h+lpCriticalSection], rax
0x180006073  call    cs:__imp_EnterCriticalSection
0x180006079  mov     dword ptr [rbx+r14+10h], 0
0x180006082  mov     r14, [rdi+18h]
0x180006086  test    r14, r14
0x180006089  jz      short loc_1800060C6
0x18000608b  mov     rdx, [r13+10h]
0x18000608f  nop
0x180006090  mov     rcx, [r14+8]
0x180006094  mov     rax, [rcx]
0x180006097  cmp     rax, [rdx]
0x18000609a  jnz     short loc_1800060BE
0x18000609c  mov     rax, [rcx+8]
0x1800060a0  cmp     rax, [rdx+8]
0x1800060a4  jnz     short loc_1800060BE
0x1800060a6  mov     rax, [r14+38h]
0x1800060aa  cmp     rax, [rbp+0]
0x1800060ae  jnz     short loc_1800060BE
0x1800060b0  mov     rax, [r14+40h]
0x1800060b4  cmp     rax, [rbp+8]
0x1800060b8  jz      loc_18000623C
0x1800060be  mov     r14, [r14]
0x1800060c1  test    r14, r14
0x1800060c4  jnz     short loc_180006090
0x1800060c6  test    r12d, r12d
0x1800060c9  jnz     short loc_1800060D7
0x1800060cb  mov     dword ptr [rbp+10h], 1068h
0x1800060d2  jmp     loc_18000623C
0x1800060d7  mov     rax, [r13+10h]
0x1800060db  xorps   xmm0, xmm0
0x1800060de  movups  xmmword ptr [rsp+168h+DestinationString.Length], xmm0
0x1800060e6  mov     [rsp+168h+Handle], 0
0x1800060f2  cmp     dword ptr [rax+20h], 1
0x1800060f6  jz      loc_1800061BC
0x1800060fc  movzx   ecx, byte ptr [r13+26h]
0x180006101  movzx   edx, byte ptr [r13+25h]
0x180006106  movzx   r8d, byte ptr [r13+24h]
0x18000610b  movzx   r9d, byte ptr [r13+23h]
0x180006110  movzx   eax, byte ptr [r13+27h]
0x180006115  movzx   r10d, byte ptr [r13+22h]
0x18000611a  movzx   r11d, byte ptr [r13+21h]
0x18000611f  movzx   ebx, byte ptr [r13+20h]
0x180006124  movzx   edi, word ptr [r13+1Eh]
0x180006129  movzx   esi, word ptr [r13+1Ch]
0x18000612e  mov     dword ptr [rsp+168h+var_100], eax
0x180006132  mov     dword ptr [rsp+168h+var_108], ecx
0x180006136  lea     rcx, [rsp+168h+SourceString]; unsigned __int16 *
0x18000613e  mov     dword ptr [rsp+168h+var_110], edx
0x180006142  mov     edx, 50h ; 'P'; unsigned __int64
0x180006147  mov     dword ptr [rsp+168h+var_118], r8d
0x18000614c  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180006153  mov     dword ptr [rsp+168h+var_120], r9d
0x180006158  mov     r9d, [r13+18h]
0x18000615c  mov     dword ptr [rsp+168h+var_128], r10d
0x180006161  mov     dword ptr [rsp+168h+var_130], r11d
0x180006166  mov     [rsp+168h+var_138], ebx
0x18000616a  mov     dword ptr [rsp+168h+var_140], edi
0x18000616e  mov     [rsp+168h+bIgnoreCase], esi
0x180006172  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006177  lea     rdx, [rsp+168h+SourceString]; SourceString
0x18000617f  lea     rcx, [rsp+168h+DestinationString]; DestinationString
0x180006187  call    cs:__imp_RtlInitUnicodeString
0x18000618d  lea     rdx, [rsp+168h+DestinationString]
0x180006195  lea     rcx, [rsp+168h+Handle]
0x18000619d  call    cs:__imp_PcwCreateNotifier
0x1800061a3  test    eax, eax
0x1800061a5  jns     short loc_1800061B7
0x1800061a7  mov     ecx, eax; Status
0x1800061a9  call    cs:__imp_RtlNtStatusToDosError
0x1800061af  mov     ebx, eax
0x1800061b1  test    eax, eax
0x1800061b3  jz      short loc_180006234
0x1800061b5  jmp     short loc_180006221
0x1800061b7  mov     rdi, [rsp+168h+var_F8]
0x1800061bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800061c3  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800061c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800061cd  mov     rdx, rax
0x1800061d0  test    rax, rax
0x1800061d3  jz      short loc_18000621C
0x1800061d5  xorps   xmm0, xmm0
0x1800061d8  xor     eax, eax
0x1800061da  movups  xmmword ptr [rdx], xmm0
0x1800061dd  mov     r14, rdx
0x1800061e0  xor     ebx, ebx
0x1800061e2  movups  xmmword ptr [rdx+10h], xmm0
0x1800061e6  movups  xmmword ptr [rdx+20h], xmm0
0x1800061ea  movups  xmmword ptr [rdx+30h], xmm0
0x1800061ee  mov     [rdx+40h], rax
0x1800061f2  mov     rcx, [rsp+168h+Handle]
0x1800061fa  mov     [rdx+30h], rcx
0x1800061fe  mov     rcx, [r13+10h]
0x180006202  mov     [rdx+8], rcx
0x180006206  movups  xmm0, xmmword ptr [r13+18h]
0x18000620b  movups  xmmword ptr [rdx+38h], xmm0
0x18000620f  mov     rax, [rdi+18h]
0x180006213  mov     [rdx], rax
0x180006216  mov     [rdi+18h], rdx
0x18000621a  jmp     short loc_180006234
0x18000621c  mov     ebx, 0Eh
0x180006221  mov     rcx, [rsp+168h+Handle]; Handle
0x180006229  test    rcx, rcx
0x18000622c  jz      short loc_180006234
0x18000622e  call    cs:__imp_NtClose
0x180006234  mov     [rbp+10h], ebx
0x180006237  mov     esi, 57h ; 'W'
0x18000623c  cmp     dword ptr [rbp+10h], 0
0x180006240  jnz     loc_1800066BA
0x180006246  mov     edx, [rbp+18h]
0x180006249  mov     r15d, 0FFFFFFFFh
0x18000624f  cmp     edx, r15d
0x180006252  jz      short loc_18000627E
0x180006254  mov     ecx, [r13+80h]
0x18000625b  test    ecx, ecx
0x18000625d  jz      short loc_180006277
0x18000625f  mov     rax, [r13+78h]
0x180006263  test    rax, rax
0x180006266  jz      short loc_180006277
0x180006268  cmp     [rax], edx
0x18000626a  jz      short loc_18000627E
0x18000626c  add     ecx, r15d
0x18000626f  jz      short loc_180006277
0x180006271  add     rax, 38h ; '8'
0x180006275  jmp     short loc_180006263
0x180006277  mov     dword ptr [rbp+10h], 106Ah
0x18000627e  cmp     dword ptr [rbp+10h], 0
0x180006282  jnz     loc_1800066BA
0x180006288  test    byte ptr [r13+58h], 2
0x18000628d  mov     eax, [rbp+14h]
0x180006290  jz      loc_18000636C
0x180006296  cmp     eax, 28h ; '('
0x180006299  ja      short loc_1800062A2
0x18000629b  mov     [rbp+10h], esi
0x18000629e  mov     eax, esi
0x1800062a0  jmp     short loc_1800062A4
0x1800062a2  xor     eax, eax
0x1800062a4  test    eax, eax
0x1800062a6  jnz     loc_1800066BA
0x1800062ac  mov     ecx, 14h
0x1800062b1  mov     rax, rbp
0x1800062b4  xor     edi, edi
0x1800062b6  lea     rsi, [rcx+rax]
0x1800062ba  cmp     [r14+1Ch], edi
0x1800062be  jbe     loc_18000638F
0x1800062c4  mov     eax, [rbp+18h]
0x1800062c7  mov     ebx, edi
0x1800062c9  add     rbx, [r14+10h]
0x1800062cd  cmp     [rbx+18h], eax
0x1800062d0  jnz     loc_180006382
0x1800062d6  cmp     dword ptr [rbx+14h], 28h ; '('
0x1800062da  mov     eax, [rsi]
0x1800062dc  jbe     loc_18000637D
0x1800062e2  cmp     eax, 28h ; '('
0x1800062e5  jbe     loc_180006382
0x1800062eb  mov     eax, [rbp+1Ch]
0x1800062ee  cmp     [rbx+1Ch], eax
0x1800062f1  jnz     loc_180006382
0x1800062f7  mov     edx, 0FFFFFFFFh; cchCount1
0x1800062fc  mov     [rsp+168h+bIgnoreCase], 1; bIgnoreCase
0x180006304  mov     r9d, edx; cchCount2
0x180006307  lea     r8, [rbp+28h]; lpString2
0x18000630b  lea     rcx, [rbx+28h]; lpString1
0x18000630f  call    cs:__imp_CompareStringOrdinal
0x180006315  cmp     eax, 2
0x180006318  jnz     short loc_180006382
0x18000631a  mov     eax, [rbx+10h]
0x18000631d  cmp     r12d, 1
0x180006321  jnz     loc_1800064BB
0x180006327  cmp     eax, 1068h
0x18000632c  ja      loc_180006495
0x180006332  jz      loc_1800064AF
0x180006338  test    eax, eax
0x18000633a  jz      loc_1800064AF
0x180006340  cmp     eax, 3
0x180006343  jz      loc_1800064AF
0x180006349  cmp     eax, 4C7h
0x18000634e  jnz     loc_18000649C
0x180006354  cmp     dword ptr [rbx+24h], 0FFFFFFFDh
0x180006358  mov     r15, [rsp+168h+var_F8]
0x18000635d  jnz     loc_180006489
0x180006363  mov     dword ptr [rbp+10h], 0B7h
0x18000636a  jmp     short loc_180006394
0x18000636c  cmp     eax, 28h ; '('
0x18000636f  jbe     loc_1800062AC
0x180006375  mov     [rbp+10h], esi
0x180006378  jmp     loc_1800066BA
0x18000637d  cmp     eax, 28h ; '('
0x180006380  jbe     short loc_18000631A
0x180006382  add     edi, [rbx+14h]
0x180006385  cmp     edi, [r14+1Ch]
0x180006389  jb      loc_1800062C4
0x18000638f  mov     r15, [rsp+168h+var_F8]
0x180006394  mov     edx, [r14+1Ch]
0x180006398  cmp     edi, edx
0x18000639a  jb      loc_1800066BA
0x1800063a0  cmp     r12d, 1
0x1800063a4  jnz     loc_1800066B3
0x1800063aa  mov     ecx, [rsi]
0x1800063ac  mov     r8d, [r14+18h]
0x1800063b0  add     ecx, 7
0x1800063b3  mov     eax, r8d
0x1800063b6  and     ecx, 0FFFFFFF8h
0x1800063b9  sub     eax, edx
0x1800063bb  cmp     eax, ecx
0x1800063bd  jnb     loc_180006445
0x1800063c3  lea     eax, [r8+rcx]
0x1800063c7  cmp     eax, ecx
0x1800063c9  jb      loc_180006527
0x1800063cf  cmp     eax, 0FFFFDFFFh
0x1800063d4  jnb     loc_180006527
0x1800063da  mov     esi, [r15+5Ch]
  ... truncated ...
```
