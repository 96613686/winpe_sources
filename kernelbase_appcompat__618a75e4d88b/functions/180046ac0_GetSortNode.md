# GetSortNode

- ea: `0x180046ac0`
- end: `0x180048693`
- name: `GetSortNode`
- size: `7123`
- prototype: ``
- caller_count: `26`
- callee_count: `27`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001cd50`
- `0x1800202d0`
- `0x180020860`
- `0x180020b00`
- `0x180021b10`
- `0x180021ee0`
- `0x1800225d0`
- `0x180027400`
- `0x180034120`
- `0x1800418a0`
- `0x1800448f0`
- `0x1800468f0`
- `0x180046ac0`
- `0x180048920`
- `0x180096e80`
- `0x180097030`
- `0x1800b1340`
- `0x1800b1e10`
- `0x1800b2920`
- `0x1800b35a0`
- `0x1800b6b10`
- `0x1800c1870`
- `0x1800cb650`
- `0x1800fd238`
- `0x1800ffcd0`
- `0x180146e10`

## callees

- `0x18001cd34`
- `0x180020e60`
- `0x180024c80`
- `0x1800265f0`
- `0x180028360`
- `0x180028490`
- `0x1800285f0`
- `0x180029ec0`
- `0x18002aabc`
- `0x1800461b0`
- `0x180046520`
- `0x180046ac0`
- `0x1800486a0`
- `0x18004875c`
- `0x1800487a0`
- `0x180048800`
- `0x18004a310`
- `0x18004a820`
- `0x18004b408`
- `0x1800b283c`
- `0x18012c3ac`
- `0x1801369c9`
- `0x180142ba0`
- `0x180194ead`
- `0x180194eb9`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004836a`
- `ntdll!RtlInitUnicodeString` at `0x18004836a`
- `ntdll!RtlEqualSid` at `0x180048548`
- `ntdll!RtlEqualSid` at `0x180048548`
- `ntdll!NtOpenKey` at `0x1800483b1`
- `ntdll!NtOpenKey` at `0x1800483b1`
- `ntdll!NtCreateKey` at `0x1800483e8`
- `ntdll!NtCreateKey` at `0x1800483e8`
- `ntdll!RtlOpenCurrentUser` at `0x180047902`
- `ntdll!RtlOpenCurrentUser` at `0x180047902`
- `ntdll!NtQueryInformationToken` at `0x180048486`
- `ntdll!NtQueryInformationToken` at `0x180048527`
- `ntdll!NtQueryInformationToken` at `0x180048486`
- `ntdll!NtQueryInformationToken` at `0x180048527`
- `ntdll!CsrClientCallServer` at `0x180047821`
- `ntdll!CsrClientCallServer` at `0x180047821`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800477fb`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800477fb`
- `ntdll!CsrFreeCaptureBuffer` at `0x18004784d`
- `ntdll!CsrFreeCaptureBuffer` at `0x18004784d`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180047045`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180047045`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180046c06`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800473e3`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180047da5`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180046c06`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800473e3`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180047da5`
- `ntdll!NtClose` at `0x1800470bb`
- `ntdll!NtClose` at `0x1800479a0`
- `ntdll!NtClose` at `0x180048400`
- `ntdll!NtClose` at `0x180048442`
- `ntdll!NtClose` at `0x1800470bb`
- `ntdll!NtClose` at `0x1800479a0`
- `ntdll!NtClose` at `0x180048400`
- `ntdll!NtClose` at `0x180048442`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180046c44`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180046ffd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800471bd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800472b8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800474b4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180047c59`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180047e75`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180047ff8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180046c44`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180046ffd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800471bd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800472b8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800474b4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180047c59`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180047e75`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180047ff8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180046c98`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004721b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800473a4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800475a0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800475da`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180047b31`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180047d48`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180047ed3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180048055`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800481f7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180046c98`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004721b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800473a4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800475a0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800475da`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180047b31`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180047d48`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180047ed3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180048055`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800481f7`
- `ntdll!RtlFreeHeap` at `0x180047772`
- `ntdll!RtlFreeHeap` at `0x18004856c`
- `ntdll!RtlFreeHeap` at `0x180047772`
- `ntdll!RtlFreeHeap` at `0x18004856c`
- `ntdll!RtlAllocateHeap` at `0x180046da7`
- `ntdll!RtlAllocateHeap` at `0x180048228`
- `ntdll!RtlAllocateHeap` at `0x1800482ab`
- `ntdll!RtlAllocateHeap` at `0x1800484f2`
- `ntdll!RtlAllocateHeap` at `0x180046da7`
- `ntdll!RtlAllocateHeap` at `0x180048228`
- `ntdll!RtlAllocateHeap` at `0x1800482ab`
- `ntdll!RtlAllocateHeap` at `0x1800484f2`

## pseudocode

```c
__int64 __fastcall GetSortNode(__int16 *a1, __int64 a2, _QWORD *a3)
{
  __m128i *v3; // rdi
  int v5; // ebx
  __int64 *m128i_i64; // rax
  __int32 v7; // eax
  __int64 result; // rax
  __int64 v9; // r13
  int v10; // esi
  int v11; // r12d
  __int64 SortVersionDllTableEntry; // rbx
  __int64 v13; // r15
  int jj; // ecx
  __int64 v15; // rdx
  signed __int64 v16; // rbx
  signed __int64 v17; // rsi
  int v18; // ebx
  __int64 v19; // r13
  __int32 *v20; // r15
  __int64 v21; // rax
  unsigned int v22; // edx
  __int64 v23; // rsi
  char *v24; // rax
  __int64 v25; // rcx
  _WORD *v26; // rdx
  __int64 v27; // r8
  _WORD *v28; // rax
  _DWORD *v29; // rdi
  __int64 SortHashValue; // rdx
  int v31; // r10d
  volatile signed __int64 *v32; // rcx
  int v33; // r12d
  __int64 v34; // r15
  volatile signed __int64 *v35; // rcx
  int mm; // edx
  ULONG IsImpersonating; // ecx
  int v38; // ebx
  __int16 v39; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v41; // rbx
  NTSTATUS v42; // r14d
  HANDLE v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // rbx
  __int64 v46; // rax
  int v47; // edx
  int v48; // ecx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  int v53; // eax
  int v54; // r8d
  const wchar_t *v55; // r10
  __int16 *j; // r9
  int v57; // ecx
  __int64 v58; // r14
  DWORD v59; // ebx
  __int64 k; // rdx
  unsigned int *v61; // rax
  __int64 v62; // r8
  DWORD v63; // ebx
  _WORD *v64; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  __int64 (__fastcall *v66)(); // rdx
  __int64 *v67; // rcx
  __int64 v68; // rbx
  __int64 v69; // rax
  DWORD v70; // ebx
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v73; // r8
  DWORD v74; // ebx
  _WORD *v75; // rcx
  __int64 NamedLocaleHashNode; // rax
  HANDLE *NlsCache; // r14
  __int16 *v78; // rcx
  int n; // eax
  unsigned __int32 v80; // r11d
  __int64 v81; // rax
  unsigned int v82; // r11d
  int v83; // r10d
  __int16 *v84; // r9
  __int16 *ii; // r8
  __int16 v86; // dx
  __int16 v87; // cx
  signed int v88; // ebx
  int v89; // r10d
  unsigned int v90; // ecx
  int v91; // r10d
  int v92; // edx
  int v93; // eax
  int GlobalizationUserModelType; // eax
  int v95; // eax
  __int64 v96; // rcx
  WCHAR *v97; // rax
  __int64 v98; // rax
  __int64 v99; // rcx
  WCHAR *v100; // r8
  const WCHAR *v101; // rdx
  __int64 v102; // r9
  WCHAR *v103; // rax
  __int64 v104; // rdx
  ULONG v105; // ecx
  int v106; // r15d
  int v107; // r9d
  __int16 *v108; // r15
  __int16 *kk; // r14
  __int16 v110; // dx
  __int16 v111; // cx
  __int16 v112; // r8
  __int16 v113; // cx
  __int32 v114; // ecx
  __int64 v115; // rcx
  DWORD v116; // ebx
  __int64 m; // rdx
  unsigned int *v118; // rax
  __int64 v119; // r8
  DWORD v120; // ebx
  _WORD *v121; // rcx
  __int64 LocaleHashNode; // rax
  int v123; // eax
  int v124; // eax
  __int64 v125; // rdx
  __int64 v126; // rdx
  HANDLE *Heap; // rax
  HANDLE *v128; // rax
  __int128 v129; // xmm0
  __int64 v130; // rdx
  NTSTATUS v131; // ebx
  HANDLE v132; // rcx
  void *v133; // rbx
  PSID *v134; // r14
  int v135; // edx
  __int16 v136; // ax
  int v137; // eax
  int v138; // ebx
  unsigned int v139; // r15d
  _QWORD *v140; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v142; // [rsp+58h] [rbp-A8h]
  __int64 v143; // [rsp+60h] [rbp-A0h]
  int v144; // [rsp+68h] [rbp-98h]
  ULONG ReturnLength; // [rsp+6Ch] [rbp-94h] BYREF
  HANDLE KeyHandle; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  int v148; // [rsp+80h] [rbp-80h] BYREF
  __m128i v149; // [rsp+88h] [rbp-78h] BYREF
  __int128 v150; // [rsp+98h] [rbp-68h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v152; // [rsp+D8h] [rbp-28h]
  WCHAR ApiMessage[32]; // [rsp+E0h] [rbp-20h] BYREF
  PVOID CapturedData; // [rsp+120h] [rbp+20h] BYREF
  int v155; // [rsp+128h] [rbp+28h]

  v140 = a3;
  v3 = (__m128i *)a2;
  v149 = 0;
  v150 = 0;
  if ( a3 )
  {
    v44 = *a3;
    if ( *a3 )
    {
      if ( v44 == 0x4000 )
      {
        v45 = g_pOrdinalSort;
        v140 = (_QWORD *)g_pOrdinalSort;
        if ( g_pOrdinalSort )
          return v45;
        v66 = InitializeOrdinalSort;
        v67 = &g_pOrdinalSortInit;
      }
      else
      {
        if ( v44 != 16385 )
        {
          v45 = 0;
          if ( (int)v44 == v44 )
          {
            v46 = *a3 & 0xFFFLL;
            if ( (unsigned int)v46 < 0x80 )
            {
              v47 = (int)v44 >> 16;
              if ( (int)v44 >> 16 >= 1 )
              {
                v48 = v44 & 0x8000;
                v49 = 8 * v46;
                _mm_lfence();
                v50 = v48 ? v49 + 3848064 : v49 + 3847040;
                v51 = *(_QWORD *)((char *)&_ImageBase.unused + v50);
                if ( v51 )
                {
                  v45 = v51;
                  do
                  {
                    if ( v47 <= 1 )
                      break;
                    --v47;
                    v52 = 192;
                    if ( !v48 )
                      v52 = 8;
                    v45 = *(_QWORD *)(v52 + v45);
                  }
                  while ( v45 );
                }
              }
            }
          }
          return v45;
        }
        v45 = g_pInvariantSort;
        v140 = (_QWORD *)g_pInvariantSort;
        if ( g_pInvariantSort )
          return v45;
        v66 = InitializeInvariantSort;
        v67 = &g_pInvariantSortInit;
      }
      RtlRunOnceExecuteOnce(v67, v66, 0, &v140);
      return (__int64)v140;
    }
  }
  v5 = *(_DWORD *)(a2 + 4);
  if ( (v5 & 0xFFFFFF) == 0 )
  {
    if ( *(_DWORD *)a2 >= 0x20u )
    {
      v129 = *(_OWORD *)(a2 + 16);
      v149 = *(__m128i *)a2;
      v5 = _mm_cvtsi128_si32(_mm_srli_si128(v149, 4));
      v150 = v129;
    }
    else
    {
      v149.m128i_i32[0] = *(_DWORD *)a2;
      v149.m128i_i32[2] = *(_DWORD *)(a2 + 8);
      v149.m128i_i32[1] = v5;
    }
    v3 = &v149;
    if ( v5 )
    {
      if ( v5 != 0x1000000 )
        goto LABEL_3;
      v114 = `ResolveSortParadigm'::`2'::icuVersion;
    }
    else
    {
      v114 = `ResolveSortParadigm'::`2'::nlsVersion;
    }
    if ( !v114 )
    {
      v114 = *(_DWORD *)(DefaultSortVersion() + 4);
      if ( ((v114 ^ v5) & 0xFF000000) != 0 )
      {
        v114 = 16973824;
        if ( !v5 )
          v114 = 394497;
      }
      if ( v149.m128i_i32[1] )
        `ResolveSortParadigm'::`2'::icuVersion = v114;
      else
        `ResolveSortParadigm'::`2'::nlsVersion = v114;
    }
    v149.m128i_i32[1] = v114;
    v149.m128i_i32[2] = v114;
  }
LABEL_3:
  if ( v3->m128i_i32[0] < 0x20u )
    m128i_i64 = NLS_GUID_NULL;
  else
    m128i_i64 = v3[1].m128i_i64;
  if ( *m128i_i64 || m128i_i64[1] )
  {
    v7 = v3->m128i_i32[1];
    if ( (unsigned int)(v7 - 393728) > 0xFEF9FDFF && (v7 & 0xFFFFFF00) != 0x100 )
    {
      SetLastError_0(0x57u);
      return 0;
    }
    a1 = 0;
    v144 = 1;
    v18 = 1;
    goto LABEL_30;
  }
  v9 = 0;
  v144 = 1;
  v10 = 10;
  v11 = 256;
  if ( !a1 )
  {
    IsImpersonating = NtCurrentTeb()->IsImpersonating;
    if ( IsImpersonating )
    {
      NlsCache = 0;
      v105 = IsImpersonating - 1;
      if ( v105 )
      {
        if ( v105 == 1 )
        {
          if ( BasepIsSecureProcess )
            goto LABEL_161;
          v106 = 0;
          NlsCache = (HANDLE *)NtCurrentTeb()->NlsCache;
          if ( !NlsCache )
          {
            Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
            NlsCache = Heap;
            if ( Heap )
            {
              *Heap = 0;
              Heap[1] = 0;
              Heap[2] = 0;
              *((_WORD *)Heap + 842) = 3;
              *((_WORD *)Heap + 843) = 1;
              v106 = 1;
            }
            else
            {
              NlsCache = &gNlsProcessLocalCache;
            }
            NtCurrentTeb()->NlsCache = NlsCache;
          }
          if ( NlsCache != &gNlsProcessLocalCache && (v106 || *((_WORD *)NlsCache + 843) == 1) )
          {
            *((_WORD *)NlsCache + 843) = 1;
            UpdateNlsInfoCache(NlsCache, 0);
          }
        }
      }
      else
      {
        if ( BasepIsSecureProcess )
        {
          NlsCache = &gNlsProcessLocalCache;
        }
        else
        {
          NlsCache = (HANDLE *)NtCurrentTeb()->NlsCache;
          if ( !NlsCache )
          {
            v128 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
            NlsCache = v128;
            if ( v128 )
            {
              *v128 = 0;
              v128[1] = 0;
              v128[2] = 0;
              *((_WORD *)v128 + 842) = 3;
              *((_WORD *)v128 + 843) = 1;
            }
            else
            {
              NlsCache = &gNlsProcessLocalCache;
            }
            NtCurrentTeb()->NlsCache = NlsCache;
          }
          if ( NlsCache != &gNlsProcessLocalCache )
          {
            *((_WORD *)NlsCache + 843) = 1;
            UpdateNlsInfoCache(NlsCache, 0);
          }
        }
        NtCurrentTeb()->IsImpersonating = 2;
      }
LABEL_162:
      v58 = (__int64)NlsCache[2];
      if ( !v58 )
        return 0;
      goto LABEL_163;
    }
    v38 = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess == -1 )
    {
      ReturnLength = 0;
      v38 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      v152 = 0;
      if ( !BasepIsSecureProcess
        && NtQueryInformationToken(
             (HANDLE)0xFFFFFFFFFFFFFFFCLL,
             TokenStatistics,
             &ObjectAttributes,
             0x38u,
             &ReturnLength) >= 0 )
      {
        if ( *(HANDLE *)(gpServerNlsUserInfo + 1580) == ObjectAttributes.RootDirectory )
        {
          v38 = 1;
          gInteractiveLogonUserProcess = 1;
          word_1803AC294 = 1;
          goto LABEL_65;
        }
        v134 = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x54u);
        if ( v134 )
        {
          if ( NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, v134, 0x54u, &ReturnLength) >= 0 )
            v38 = RtlEqualSid(*v134, (PSID)(gpServerNlsUserInfo + 1588)) != 0;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v134);
        }
      }
      gInteractiveLogonUserProcess = v38;
      if ( v38 )
        word_1803AC294 = 1;
      else
        word_1803AC294 = 20;
    }
LABEL_65:
    if ( !v38 )
    {
      NlsCheckStaleCache();
      goto LABEL_161;
    }
    if ( dword_1803AC290 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
      word_1803AC296 = 1;
    if ( !word_1803AC296 )
      goto LABEL_161;
    v39 = word_1803AC294;
    if ( word_1803AC294 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v39 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        if ( !word_1803AC296 )
          goto LABEL_160;
        v39 = word_1803AC294;
      }
    }
    word_1803AC296 = 2;
    if ( v39 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v41 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v155 = 1660;
        v42 = CsrClientCallServer(ApiMessage, v41, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v42 >= 0 )
          memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v41);
      }
      else
      {
        v42 = -1073741801;
      }
      if ( word_1803AC294 == 1 && v42 >= 0 )
      {
LABEL_80:
        if ( word_1803ABC18 == -1 )
        {
          qword_1803ABC10 = 0;
        }
        else
        {
          v68 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
          if ( !v68 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803ABC10 )
          {
LABEL_159:
            _InterlockedCompareExchange16(&word_1803AC296, 0, 2);
            if ( word_1803AC294 == 3 )
            {
LABEL_161:
              NlsCache = &gNlsProcessLocalCache;
              goto LABEL_162;
            }
LABEL_160:
            RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
            goto LABEL_161;
          }
        }
        v69 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_158:
          qword_1803ABC10 = v69;
          goto LABEL_159;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_157;
        v70 = gSystemLocale;
        for ( i = *((_QWORD *)P
                  + (((unsigned __int8)gSystemLocale
                    ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                   & 0x7F)); i; i = *(_QWORD *)(i + 88) )
        {
          if ( *(_DWORD *)i == gSystemLocale )
            break;
        }
        gpSysLocHashN = i;
        if ( i )
          goto LABEL_157;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_240;
        WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( WindowsLocaleData )
        {
          if ( (_WORD)v70 != 127 )
          {
            v74 = HIWORD(v70);
            if ( (v74 & 0xF) == 0 )
            {
              v75 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_153:
              NamedLocaleHashNode = MakeNamedLocaleHashNode(v75, 0);
              goto LABEL_154;
            }
            v104 = WindowsLocaleData[54];
            v75 = (_WORD *)qword_1803A6BD0;
            if ( (_DWORD)v104 )
              v75 = (_WORD *)(qword_1803A6BD0
                            + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v104 + 2LL * (v74 & 0xF)) - 2)
                            + 2);
            if ( v75 && *v75 )
              goto LABEL_153;
LABEL_240:
            gpSysLocHashN = 0;
LABEL_155:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_157;
          }
          NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v70, v73, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_240;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            NamedLocaleHashNode = FindLocaleHashNode(v70);
          }
          else
          {
            NamedLocaleHashNode = 0;
          }
        }
LABEL_154:
        gpSysLocHashN = NamedLocaleHashNode;
        if ( !NamedLocaleHashNode )
          goto LABEL_155;
LABEL_157:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v69 = gpSysLocHashN;
        goto LABEL_158;
      }
    }
    Handle = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_77:
      v43 = Handle;
      NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
      if ( word_1803AC294 == 3 && v43 )
        NtClose(v43);
      goto LABEL_80;
    }
    KeyHandle = 0;
    ReturnLength = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType();
    if ( GlobalizationUserModelType == 1 )
    {
      v95 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
    }
    else
    {
      v124 = GlobalizationUserModelType - 2;
      if ( v124 )
      {
        if ( v124 != 1 )
        {
LABEL_235:
          SetLastError_0(0x3F1u);
          goto LABEL_77;
        }
        v148 = 0;
        v95 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle, &v148);
      }
      else
      {
        v95 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
      }
    }
    if ( v95 >= 0 )
    {
      ApiMessage[0] = 0;
      v96 = 512;
      v97 = ApiMessage;
      do
      {
        if ( !*v97 )
          break;
        ++v97;
        --v96;
      }
      while ( v96 );
      v98 = 512 - v96;
      if ( !v96 )
        goto LABEL_233;
      v99 = 2147483646;
      v100 = &ApiMessage[v98];
      v101 = L"Control Panel\\International";
      v102 = 512 - v98;
      if ( 512 != v98 )
      {
        do
        {
          if ( !v99 )
            break;
          if ( !*v101 )
            break;
          *v100++ = *v101++;
          --v99;
          --v102;
        }
        while ( v102 );
      }
      v103 = v100 - 1;
      if ( v102 )
        v103 = v100;
      *v103 = 0;
      if ( v102 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ReturnLength = 0;
        v131 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v131 < 0 )
          v131 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &ReturnLength);
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v131 >= 0 )
        {
          v132 = Handle;
        }
        else
        {
          v132 = 0;
          Handle = 0;
        }
        if ( v131 >= 0 )
        {
          v133 = (void *)_InterlockedCompareExchange64(
                           (volatile signed __int64 *)&gNlsProcessLocalCache,
                           (signed __int64)v132,
                           0);
          if ( v133 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v133;
          }
          goto LABEL_77;
        }
      }
      else
      {
LABEL_233:
        if ( KeyHandle )
          NtClose(KeyHandle);
      }
    }
    goto LABEL_235;
  }
  if ( *a1 )
  {
    if ( *a1 != 33 )
      goto LABEL_164;
    v54 = 85;
    v55 = L"!x-sys-default-locale";
    for ( j = a1; v54 > 0; ++j )
    {
      v110 = *j;
      if ( !*j )
        break;
      v111 = *v55;
      if ( !*v55 )
        goto LABEL_217;
      if ( (unsigned __int16)(v110 - 65) <= 0x19u )
        v110 |= 0x20u;
      if ( (unsigned __int16)(v111 - 65) <= 0x19u )
        v111 |= 0x20u;
      if ( v110 == 95 )
        v110 = 45;
      if ( v111 == 95 )
        v111 = 45;
      if ( v110 != v111 )
        goto LABEL_217;
      --v54;
      ++v55;
    }
    if ( *j || *v55 )
      goto LABEL_217;
    v57 = g_definedDefaultSortVersion;
    if ( !g_definedDefaultSortVersion )
    {
      *(_QWORD *)&DestinationString.Length = 32;
      DestinationString.Buffer = 0;
      v142 = 0;
      v143 = 0;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( !g_definedDefaultSortVersion )
      {
        if ( (unsigned int)QueryRegDefaultSortingVersion(&DestinationString)
          && (unsigned int)QueryRegSortVersionDll(&DestinationString, 0, 0) )
        {
          v123 = *(_DWORD *)(&DestinationString.MaximumLength + 1);
        }
        else
        {
          v123 = 256;
        }
        dword_1803A52B4 = v123 | 0xFF;
        dword_1803A52B8 = v123 | 0xFF;
        _InterlockedExchange(&g_definedDefaultSortVersion, 1);
      }
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
      v57 = g_definedDefaultSortVersion;
    }
    if ( ((dword_1803A52B4 ^ v3->m128i_i32[1]) & 0xFFFFFF00) != 0 )
    {
      v58 = gpSysLocHashN;
      if ( gpSysLocHashN || BasepIsSecureProcess )
        goto LABEL_163;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_127;
      v59 = gSystemLocale;
      for ( k = *((_QWORD *)P
                + (((unsigned __int8)gSystemLocale
                  ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                 & 0x7F)); k; k = *(_QWORD *)(k + 88) )
      {
        if ( *(_DWORD *)k == gSystemLocale )
          break;
      }
      gpSysLocHashN = k;
      if ( k )
        goto LABEL_127;
      if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
        goto LABEL_359;
      v61 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( v61 )
      {
        if ( (_WORD)v59 != 127 )
        {
          v63 = HIWORD(v59);
          if ( (v63 & 0xF) == 0 )
          {
            v64 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v61);
LABEL_123:
            LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v64, 0);
            goto LABEL_124;
          }
          v125 = v61[54];
          v64 = (_WORD *)qword_1803A6BD0;
          if ( (_DWORD)v125 )
            v64 = (_WORD *)(qword_1803A6BD0
                          + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v125 + 2LL * (v63 & 0xF)) - 2)
                          + 2);
          if ( v64 && *v64 )
            goto LABEL_123;
LABEL_359:
          gpSysLocHashN = 0;
LABEL_125:
          gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
          if ( !gpSysLocHashN )
            gpSysLocHashN = gpInvLocHashN;
          goto LABEL_127;
        }
        LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v61, v59, v62, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_359;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          LocHashNodeFromSystemLocale = FindLocaleHashNode(v59);
        }
        else
        {
          LocHashNodeFromSystemLocale = 0;
        }
      }
LABEL_124:
      gpSysLocHashN = LocHashNodeFromSystemLocale;
      if ( !LocHashNodeFromSystemLocale )
        goto LABEL_125;
LABEL_127:
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
      v58 = gpSysLocHashN;
LABEL_163:
      a1 = *(__int16 **)(v58 + 32);
LABEL_164:
      v18 = 1;
      if ( a1 )
        goto LABEL_165;
LABEL_30:
      v19 = (v3[1].m128i_i32[0] ^ ((unsigned __int32)v3->m128i_i32[1] >> 8)) & 0x7F;
      v17 = g_pSortGuidHash[v19];
      if ( v17 )
      {
        v139 = v3->m128i_i32[1] & 0xFFFFFF00;
        do
        {
          if ( v139 == (*(_DWORD *)(v17 + 216) & 0xFFFFFF00) && !memcmp_0(&v3[1], (const void *)(v17 + 200), 0x10u) )
          {
            if ( v140 )
            {
              if ( v18 > 0xFFFF )
                v138 = 0;
              else
                v138 = v19 | (v18 << 16) | 0x8000;
              *v140 = v138;
            }
            return v17;
          }
          v17 = *(_QWORD *)(v17 + 192);
          ++v18;
        }
        while ( v17 );
      }
      LODWORD(v9) = 0;
      v20 = &v3->m128i_i32[1];
      goto LABEL_32;
    }
    result = g_pSystemDefaultSort;
    if ( g_pSystemDefaultSort )
      return result;
    if ( !v57 )
    {
      *(_QWORD *)&DestinationString.Length = 32;
      DestinationString.Buffer = 0;
      v142 = 0;
      v143 = 0;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( !g_definedDefaultSortVersion )
      {
        if ( (unsigned int)QueryRegDefaultSortingVersion(&DestinationString)
          && (unsigned int)QueryRegSortVersionDll(&DestinationString, 0, 0) )
        {
          v11 = *(_DWORD *)(&DestinationString.MaximumLength + 1);
        }
        dword_1803A52B4 = v11 | 0xFF;
        dword_1803A52B8 = v11 | 0xFF;
        _InterlockedExchange(&g_definedDefaultSortVersion, 1);
      }
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    }
    v115 = gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_313:
      result = GetSortNode(*(_QWORD *)(v115 + 32), g_defaultSortVersion, 0);
      g_pSystemDefaultSort = result;
      if ( !result )
      {
        result = g_pInvariantSort;
        v140 = (_QWORD *)g_pInvariantSort;
        if ( !g_pInvariantSort )
        {
          RtlRunOnceExecuteOnce(&g_pInvariantSortInit, InitializeInvariantSort, 0, &v140);
          result = (__int64)v140;
        }
        g_pSystemDefaultSort = result;
      }
      return result;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_312;
    v116 = gSystemLocale;
    for ( m = *((_QWORD *)P
              + (((unsigned __int8)gSystemLocale
                ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
               & 0x7F)); m; m = *(_QWORD *)(m + 88) )
    {
      if ( *(_DWORD *)m == gSystemLocale )
        break;
    }
    gpSysLocHashN = m;
    if ( m )
      goto LABEL_312;
    if ( (gSystemLocale & 0xFFF00000) == 0 && !BasepIsSecureProcess )
    {
      v118 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( v118 )
      {
        if ( (_WORD)v116 == 127 )
        {
          LocaleHashNode = MakeLocHashNodeFromSystemLocale(v118, v116, v119, 0);
          goto LABEL_308;
        }
        v120 = HIWORD(v116);
        if ( (v120 & 0xF) == 0 )
        {
          v121 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v118);
LABEL_307:
          LocaleHashNode = MakeNamedLocaleHashNode(v121, 0);
          goto LABEL_308;
        }
        v126 = v118[54];
        v121 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v126 )
          v121 = (_WORD *)(qword_1803A6BD0
                         + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v126 + 2LL * (v120 & 0xF)) - 2)
                         + 2);
        if ( v121 && *v121 )
          goto LABEL_307;
      }
      else if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          && !(unsigned int)CreateTransientLocales() )
        {
LABEL_309:
          gpSysLocHashN = v9;
          if ( !v9 )
            goto LABEL_310;
LABEL_312:
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          v115 = gpSysLocHashN;
          goto LABEL_313;
        }
        LocaleHashNode = FindLocaleHashNode(v116);
LABEL_308:
        v9 = LocaleHashNode;
        goto LABEL_309;
      }
    }
    gpSysLocHashN = 0;
LABEL_310:
    gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
    if ( !gpSysLocHashN )
      gpSysLocHashN = gpInvLocHashN;
    goto LABEL_312;
  }
  v144 = 1;
  if ( !g_definedDefaultSortVersion )
  {
    *(_QWORD *)&DestinationString.Length = 32;
    DestinationString.Buffer = 0;
    v142 = 0;
    v143 = 0;
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( !g_definedDefaultSortVersion )
    {
      if ( (unsigned int)QueryRegDefaultSortingVersion(&DestinationString)
        && (unsigned int)QueryRegSortVersionDll(&DestinationString, 0, 0) )
      {
        v53 = *(_DWORD *)(&DestinationString.MaximumLength + 1);
      }
      else
      {
        v53 = 256;
      }
      dword_1803A52B4 = v53 | 0xFF;
      dword_1803A52B8 = v53 | 0xFF;
      _InterlockedExchange(&g_definedDefaultSortVersion, 1);
    }
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
  }
  if ( ((dword_1803A52B4 ^ v3->m128i_i32[1]) & 0xFFFFFF00) == 0 )
  {
    result = g_pInvariantSort;
    v140 = (_QWORD *)g_pInvariantSort;
    if ( !g_pInvariantSort )
    {
      RtlRunOnceExecuteOnce(&g_pInvariantSortInit, InitializeInvariantSort, 0, &v140);
      return (__int64)v140;
    }
    return result;
  }
LABEL_217:
  v18 = 1;
LABEL_165:
  v78 = a1;
  for ( n = 12; *v78; --v10 )
  {
    if ( !v10 )
      break;
    v135 = 2 * n;
    v136 = *v78;
    if ( *v78 == 45 || v136 == 95 )
      v137 = v10;
    else
      v137 = v136 & 0xDF;
    ++v78;
    n = v135 ^ v137;
  }
  v80 = v3->m128i_u32[1];
  v20 = &v3->m128i_i32[1];
  v81 = (((unsigned __int8)n ^ BYTE1(v80)) + ((unsigned __int16)(n ^ (v80 >> 8)) >> 8)) & 0x7F;
  KeyHandle = (HANDLE)(unsigned int)v81;
  v17 = g_pSortHash[v81];
  if ( v17 )
  {
    v82 = v80 & 0xFFFFFF00;
    while ( 1 )
    {
      if ( v82 == (*(_DWORD *)(v17 + 216) & 0xFFFFFF00) )
      {
        v83 = 85;
        v84 = (__int16 *)(v17 + 16);
        for ( ii = a1; v83 > 0; ++ii )
        {
          v86 = *ii;
          if ( !*ii )
            break;
          v87 = *v84;
          if ( !*v84 )
            goto LABEL_173;
          if ( (unsigned __int16)(v86 - 65) <= 0x19u )
            v86 |= 0x20u;
          if ( (unsigned __int16)(v87 - 65) <= 0x19u )
            v87 |= 0x20u;
          if ( v86 == 95 )
            v86 = 45;
          if ( v87 == 95 )
            v87 = 45;
          if ( v86 != v87 )
            goto LABEL_173;
          --v83;
          ++v84;
        }
        if ( !*ii && !*v84 )
        {
          if ( v140 )
          {
            if ( v18 > 0xFFFF )
              v88 = 0;
            else
              v88 = (unsigned int)KeyHandle | (v18 << 16);
            *v140 = v88;
          }
          return v17;
        }
      }
LABEL_173:
      v17 = *(_QWORD *)(v17 + 8);
      if ( !v17 )
        break;
      ++v18;
    }
    KeyHandle = (char *)v3->m128i_i64 + 4;
    goto LABEL_33;
  }
LABEL_32:
  KeyHandle = v20;
  v21 = 0;
  if ( a1 )
LABEL_33:
    v21 = GetNamedLocaleHashNode(a1, 0);
  v22 = *v20 & 0xFFFFFF00;
  if ( v22 == 256 || (unsigned int)(*v20 - 393728) <= 0xFEF9FDFF )
  {
    if ( v21 )
      v23 = *(_QWORD *)(v21 + 32);
    else
      v23 = 0;
    if ( v22 == 256 )
    {
      v24 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x110u);
      v16 = (signed __int64)v24;
      if ( v24 )
      {
        *(_DWORD *)v24 = 2;
        *((_QWORD *)v24 + 1) = 0;
        *(GUID *)(v24 + 200) = GUID_DEFAULT;
        *((_QWORD *)v24 + 24) = 0;
        *((_DWORD *)v24 + 54) = 256;
        *((_QWORD *)v24 + 28) = MinSortGetSortKey;
        *((_QWORD *)v24 + 29) = MinSortChangeCase;
        *((_QWORD *)v24 + 30) = &MinSortCompareString;
        *((_QWORD *)v24 + 31) = &MinSortFindString;
        *((_QWORD *)v24 + 32) = MinSortIsDefinedString;
        *((_WORD *)v24 + 8) = 0;
        goto LABEL_25;
      }
      goto LABEL_386;
    }
  }
  else
  {
    if ( !v21 )
      return 0;
    v23 = *(_QWORD *)(*(_QWORD *)(v21 + 104) + 32LL);
  }
  SortVersionDllTableEntry = GetSortVersionDllTableEntry(v3);
  if ( !SortVersionDllTableEntry )
  {
    v13 = CreateSortVersionDllTableEntry();
    if ( v13 )
    {
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      SortVersionDllTableEntry = GetSortVersionDllTableEntry(v3);
      if ( !SortVersionDllTableEntry )
      {
        for ( jj = 0; jj < 10; ++jj )
        {
          v15 = 8LL * jj + 3849088;
          if ( !*(_QWORD *)((char *)&_ImageBase.unused + v15) )
          {
            *(_QWORD *)((char *)&_ImageBase.unused + v15) = v13;
LABEL_23:
            RtlReleaseSRWLockExclusive(&gTblPtrsLock);
            SortVersionDllTableEntry = v13;
            goto LABEL_24;
          }
        }
        if ( jj != 10 )
          goto LABEL_23;
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        CleanupSortVersionDllTableEntry(v13);
        goto LABEL_386;
      }
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
      CleanupSortVersionDllTableEntry(v13);
      goto LABEL_24;
    }
LABEL_386:
    v16 = 0;
    goto LABEL_25;
  }
LABEL_24:
  v16 = (*(__int64 (__fastcall **)(__int64, __m128i *, _QWORD))(SortVersionDllTableEntry + 16))(v23, v3, 0);
LABEL_25:
  if ( !v16 )
    return 0;
  if ( a1 )
  {
    v25 = 85;
    v26 = (_WORD *)(v16 + 16);
    v27 = 2147483646;
    do
    {
      if ( !v27 )
        break;
      if ( !*a1 )
        break;
      *v26++ = *a1++;
      --v27;
      --v25;
    }
    while ( v25 );
    v28 = v26 - 1;
    if ( v25 )
      v28 = v26;
    *v28 = 0;
    if ( !v25 )
      return 0;
    v29 = (_DWORD *)(v16 + 216);
    SortHashValue = (unsigned int)GetSortHashValue(v16 + 16, *(unsigned int *)(v16 + 216), v27);
    v17 = g_pSortHash[SortHashValue];
    v32 = &g_pSortHash[SortHashValue];
    *(_QWORD *)(v16 + 8) = 0;
    do
    {
      while ( v17 )
      {
        if ( ((*v29 ^ *(_DWORD *)(v17 + 216)) & 0xFFFFFF00) == 0 )
        {
          v107 = 85;
          v108 = (__int16 *)(v16 + 16);
          for ( kk = (__int16 *)(v17 + 16); v107 > 0; ++kk )
          {
            v112 = *kk;
            if ( !*kk )
              break;
            v113 = *v108;
            if ( !*v108 )
              goto LABEL_318;
            if ( (unsigned __int16)(v112 - 65) <= 0x19u )
              v112 |= 0x20u;
            if ( (unsigned __int16)(v113 - 65) <= 0x19u )
              v113 |= 0x20u;
            if ( v112 == 95 )
              v112 = 45;
            if ( v113 == 95 )
              v113 = 45;
            if ( v112 != v113 )
              goto LABEL_318;
            --v107;
            ++v108;
          }
          if ( !*kk && !*v108 )
          {
            if ( v140 )
            {
              if ( v31 > 0xFFFF || (int)SortHashValue > 4095 )
                v89 = 0;
              else
                v89 = SortHashValue | (v31 << 16);
              *v140 = v89;
            }
            goto LABEL_195;
          }
        }
LABEL_318:
        v32 = (volatile signed __int64 *)(v17 + 8);
        ++v31;
        v17 = *(_QWORD *)(v17 + 8);
      }
      v17 = _InterlockedCompareExchange64(v32, v16, 0);
    }
    while ( v17 );
    v33 = 1;
    if ( v140 )
    {
      if ( v31 > 0xFFFF || (int)SortHashValue > 4095 )
        v91 = 0;
      else
        v91 = SortHashValue | (v31 << 16);
      *v140 = v91;
    }
  }
  else
  {
    v33 = 0;
    v29 = (_DWORD *)(v16 + 216);
  }
  if ( !memcmp_0((const void *)(v16 + 200), NLS_GUID_NULL, 0x10u) )
    return v16;
  v34 = (*(_DWORD *)(v16 + 200) ^ (*v29 >> 8)) & 0x7F;
  v17 = g_pSortGuidHash[v34];
  v35 = &g_pSortGuidHash[v34];
  *(_QWORD *)(v16 + 192) = 0;
LABEL_54:
  for ( mm = v144; ; v144 = mm )
  {
    if ( !v17 )
    {
      v17 = _InterlockedCompareExchange64(v35, v16, 0);
      if ( v17 )
        goto LABEL_54;
      if ( v140 )
      {
        if ( mm > 0xFFFF )
          v92 = 0;
        else
          v92 = v34 | (mm << 16) | 0x8000;
        *v140 = v92;
      }
      return v16;
    }
    if ( ((*v29 ^ *(_DWORD *)(v17 + 216)) & 0xFFFFFF00) == 0 )
      break;
LABEL_446:
    v35 = (volatile signed __int64 *)(v17 + 192);
    ++mm;
    v17 = *(_QWORD *)(v17 + 192);
  }
  if ( memcmp_0((const void *)(v17 + 200), (const void *)(v16 + 200), 0x10u) )
  {
    mm = v144;
    goto LABEL_446;
  }
  if ( v140 )
  {
    if ( v144 > 0xFFFF )
      v93 = 0;
    else
      v93 = v34 | (v144 << 16) | 0x8000;
    *v140 = v93;
  }
  if ( v33 )
    return v16;
LABEL_195:
  if ( v17 != v16 )
  {
    v90 = *(_DWORD *)KeyHandle & 0xFFFFFF00;
    if ( v90 == 256 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v16);
    }
    else
    {
      while ( (int)v9 < 10 )
      {
        v130 = g_pSortVersionDlls[(int)v9];
        if ( !v130 )
          break;
        if ( (*(_DWORD *)v130 & 0xFFFFFF00) == v90 )
        {
          (*(void (__fastcall **)(signed __int64, __int64, struct HINSTANCE__ *))(v130 + 24))(v16, v130, &_ImageBase);
          return v17;
        }
        LODWORD(v9) = v9 + 1;
      }
    }
  }
  return v17;
}

```

## disassembly

```asm
0x180046ac0  push    rbp
0x180046ac2  push    rbx
0x180046ac3  push    rdi
0x180046ac4  push    r14
0x180046ac6  lea     rbp, [rsp-408h]
0x180046ace  sub     rsp, 508h
0x180046ad5  mov     rax, cs:__security_cookie
0x180046adc  xor     rax, rsp
0x180046adf  mov     [rbp+420h+var_40], rax
0x180046ae6  mov     [rsp+520h+var_4E0], r8
0x180046aeb  xorps   xmm0, xmm0
0x180046aee  mov     rdi, rdx
0x180046af1  mov     r14, rcx
0x180046af4  movups  [rbp+420h+var_498], xmm0
0x180046af8  movups  [rbp+420h+var_488], xmm0
0x180046afc  test    r8, r8
0x180046aff  jnz     loc_1800470E5
0x180046b05  mov     ebx, [rdx+4]
0x180046b08  test    ebx, 0FFFFFFh
0x180046b0e  jz      loc_180047BB3
0x180046b14  cmp     dword ptr [rdi], 20h ; ' '
0x180046b17  jb      loc_1800477BF
0x180046b1d  lea     rax, [rdi+10h]
0x180046b21  cmp     qword ptr [rax], 0
0x180046b25  mov     [rsp+520h+arg_18], rsi
0x180046b2d  mov     [rsp+520h+var_20], r12
0x180046b35  mov     [rsp+520h+var_28], r13
0x180046b3d  mov     [rsp+520h+var_30], r15
0x180046b45  jz      short loc_180046B7F
0x180046b47  mov     eax, [rdi+4]
0x180046b4a  lea     ecx, [rax-60200h]
0x180046b50  cmp     ecx, 0FEF9FDFFh
0x180046b56  jbe     loc_180046D08
0x180046b5c  and     eax, 0FFFFFF00h
0x180046b61  mov     ecx, 100h
0x180046b66  cmp     eax, ecx
0x180046b68  jz      loc_180046D08
0x180046b6e  mov     ecx, 57h ; 'W'; dwErrCode
0x180046b73  call    SetLastError_0
0x180046b78  xor     eax, eax
0x180046b7a  jmp     loc_180046CCB
0x180046b7f  cmp     qword ptr [rax+8], 0
0x180046b84  jnz     short loc_180046B47
0x180046b86  xor     r13d, r13d
0x180046b89  mov     r15d, 1
0x180046b8f  mov     [rsp+520h+var_4B8], r15d
0x180046b94  mov     esi, 0Ah
0x180046b99  mov     r12d, 100h
0x180046b9f  test    r14, r14
0x180046ba2  jz      loc_180046F8C
0x180046ba8  movzx   eax, word ptr [r14]
0x180046bac  test    ax, ax
0x180046baf  jnz     loc_18004723B
0x180046bb5  cmp     cs:g_definedDefaultSortVersion, r13d
0x180046bbc  mov     [rsp+520h+var_4B8], r15d
0x180046bc1  jz      loc_18004719E
0x180046bc7  mov     eax, [rdi+4]
0x180046bca  xor     eax, cs:dword_1803A52B4
0x180046bd0  test    eax, 0FFFFFF00h
0x180046bd5  jnz     loc_1800478AB
0x180046bdb  mov     rax, cs:g_pInvariantSort
0x180046be2  mov     [rsp+520h+var_4E0], rax
0x180046be7  test    rax, rax
0x180046bea  jnz     loc_180046CCB
0x180046bf0  lea     r9, [rsp+520h+var_4E0]
0x180046bf5  xor     r8d, r8d
0x180046bf8  lea     rdx, InitializeInvariantSort
0x180046bff  lea     rcx, g_pInvariantSortInit
0x180046c06  call    cs:__imp_RtlRunOnceExecuteOnce
0x180046c0d  nop     dword ptr [rax+rax+00h]
0x180046c12  mov     rax, [rsp+520h+var_4E0]
0x180046c17  jmp     loc_180046CCB
0x180046c1c  mov     rcx, rdi
0x180046c1f  call    GetSortVersionDllTableEntry
0x180046c24  mov     rbx, rax
0x180046c27  test    rax, rax
0x180046c2a  jnz     short loc_180046CA7
0x180046c2c  call    CreateSortVersionDllTableEntry
0x180046c31  mov     r15, rax
0x180046c34  test    rax, rax
0x180046c37  jz      loc_18004820B
0x180046c3d  lea     rcx, gTblPtrsLock
0x180046c44  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180046c4b  nop     dword ptr [rax+rax+00h]
0x180046c50  mov     rcx, rdi
0x180046c53  call    GetSortVersionDllTableEntry
0x180046c58  mov     rbx, rax
0x180046c5b  test    rax, rax
0x180046c5e  jnz     loc_180047B2A
0x180046c64  mov     ecx, r13d
0x180046c67  lea     r8, __ImageBase
0x180046c6e  cmp     ecx, 0Ah
0x180046c71  jge     loc_1800481EA
0x180046c77  movsxd  rax, ecx
0x180046c7a  lea     rdx, ds:3ABB80h[rax*8]
0x180046c82  cmp     qword ptr [rdx+r8], 0
0x180046c87  jnz     loc_180048673
0x180046c8d  mov     [rdx+r8], r15
0x180046c91  lea     rcx, gTblPtrsLock
0x180046c98  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180046c9f  nop     dword ptr [rax+rax+00h]
0x180046ca4  mov     rbx, r15
0x180046ca7  mov     rax, [rbx+10h]
0x180046cab  xor     r8d, r8d
0x180046cae  mov     rdx, rdi
0x180046cb1  mov     rcx, rsi
0x180046cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cb9  mov     rbx, rax
0x180046cbc  test    rbx, rbx
0x180046cbf  jnz     loc_180046E35
0x180046cc5  mov     rsi, r13
0x180046cc8  mov     rax, rsi
0x180046ccb  mov     r13, [rsp+520h+var_28]
0x180046cd3  mov     r12, [rsp+520h+var_20]
0x180046cdb  mov     rsi, [rsp+520h+arg_18]
0x180046ce3  mov     r15, [rsp+520h+var_30]
0x180046ceb  mov     rcx, [rbp+420h+var_40]
0x180046cf2  xor     rcx, rsp; StackCookie
0x180046cf5  call    __security_check_cookie
0x180046cfa  add     rsp, 508h
0x180046d01  pop     r14
0x180046d03  pop     rdi
0x180046d04  pop     rbx
0x180046d05  pop     rbp
0x180046d06  retn
0x180046d08  mov     eax, 1
0x180046d0d  xor     r14d, r14d
0x180046d10  mov     [rsp+520h+var_4B8], eax
0x180046d14  mov     ebx, eax
0x180046d16  mov     r15d, [rdi+4]
0x180046d1a  lea     rax, __ImageBase
0x180046d21  mov     r13d, r15d
0x180046d24  shr     r13d, 8
0x180046d28  xor     r13d, [rdi+10h]
0x180046d2c  and     r13d, 7Fh
0x180046d30  mov     rsi, rva g_pSortGuidHash[rax+r13*8]
0x180046d38  test    rsi, rsi
0x180046d3b  jnz     loc_180048667
0x180046d41  xor     r13d, r13d
0x180046d44  lea     r15, [rdi+4]
0x180046d48  mov     r12d, 100h
0x180046d4e  mov     [rsp+520h+KeyHandle], r15
0x180046d53  mov     rax, r13
0x180046d56  test    r14, r14
0x180046d59  jz      short loc_180046D65
0x180046d5b  xor     edx, edx
0x180046d5d  mov     rcx, r14
0x180046d60  call    GetNamedLocaleHashNode
0x180046d65  mov     ecx, [r15]
0x180046d68  mov     edx, ecx
0x180046d6a  and     edx, 0FFFFFF00h
0x180046d70  cmp     edx, r12d
0x180046d73  jnz     loc_180046F5C
0x180046d79  test    rax, rax
0x180046d7c  jz      loc_180046F84
0x180046d82  mov     rsi, [rax+20h]
0x180046d86  cmp     edx, r12d
0x180046d89  jnz     loc_180046C1C
0x180046d8f  mov     rcx, gs:60h
0x180046d98  mov     edx, 8; Flags
0x180046d9d  mov     r8d, 110h; Size
0x180046da3  mov     rcx, [rcx+30h]; HeapHandle
0x180046da7  call    cs:__imp_RtlAllocateHeap
0x180046dae  nop     dword ptr [rax+rax+00h]
0x180046db3  mov     rbx, rax
0x180046db6  test    rax, rax
0x180046db9  jz      loc_18004820B
0x180046dbf  movups  xmm0, xmmword ptr cs:GUID_DEFAULT.Data1
0x180046dc6  mov     dword ptr [rax], 2
0x180046dcc  mov     [rax+8], r13
0x180046dd0  movups  xmmword ptr [rax+0C8h], xmm0
0x180046dd7  mov     [rax+0C0h], r13
0x180046dde  mov     [rax+0D8h], r12d
0x180046de5  lea     rax, MinSortGetSortKey
0x180046dec  mov     [rbx+0E0h], rax
0x180046df3  lea     rax, MinSortChangeCase
0x180046dfa  mov     [rbx+0E8h], rax
0x180046e01  lea     rax, MinSortCompareString
0x180046e08  mov     [rbx+0F0h], rax
0x180046e0f  lea     rax, MinSortFindString
0x180046e16  mov     [rbx+0F8h], rax
0x180046e1d  lea     rax, MinSortIsDefinedString
0x180046e24  mov     [rbx+100h], rax
0x180046e2b  mov     [rbx+10h], r13w
0x180046e30  jmp     loc_180046CBC
0x180046e35  test    r14, r14
0x180046e38  jz      loc_18004722C
0x180046e3e  mov     ecx, 55h ; 'U'
0x180046e43  lea     rdx, [rbx+10h]
0x180046e47  mov     r8d, 7FFFFFFEh
0x180046e4d  test    r8, r8
0x180046e50  jz      short loc_180046E6F
0x180046e52  movzx   eax, word ptr [r14]
0x180046e56  test    ax, ax
0x180046e59  jz      short loc_180046E6F
0x180046e5b  mov     [rdx], ax
0x180046e5e  add     r14, 2
0x180046e62  add     rdx, 2
0x180046e66  dec     r8
0x180046e69  sub     rcx, 1
0x180046e6d  jnz     short loc_180046E4D
0x180046e6f  test    rcx, rcx
0x180046e72  lea     rax, [rdx-2]
0x180046e76  cmovnz  rax, rdx
0x180046e7a  mov     [rax], r13w
0x180046e7e  jz      loc_180046CC5
0x180046e84  lea     rdi, [rbx+0D8h]
0x180046e8b  mov     r10d, 1
0x180046e91  mov     edx, [rdi]
0x180046e93  lea     rcx, [rbx+10h]
0x180046e97  call    GetSortHashValue
0x180046e9c  mov     edx, eax
0x180046e9e  lea     rax, __ImageBase
0x180046ea5  lea     rcx, rva g_pSortHash[rax]
0x180046eac  mov     rsi, [rcx+rdx*8]
0x180046eb0  lea     rcx, [rcx+rdx*8]
0x180046eb4  mov     [rbx+8], r13
0x180046eb8  test    rsi, rsi
0x180046ebb  jnz     loc_180047A74
0x180046ec1  xor     eax, eax
0x180046ec3  lock cmpxchg [rcx], rbx
0x180046ec8  mov     rsi, rax
0x180046ecb  jnz     short loc_180046EB8
0x180046ecd  mov     rcx, [rsp+520h+var_4E0]
0x180046ed2  mov     r12d, 1
0x180046ed8  test    rcx, rcx
0x180046edb  jnz     loc_180047794
0x180046ee1  mov     r8d, 10h; Size
0x180046ee7  lea     rdx, NLS_GUID_NULL; Buf2
0x180046eee  lea     rcx, [rbx+0C8h]; Buf1
0x180046ef5  call    memcmp_0
0x180046efa  test    eax, eax
0x180046efc  jz      short loc_180046F54
0x180046efe  mov     r15d, [rdi]
0x180046f01  lea     rax, __ImageBase
0x180046f08  shr     r15d, 8
0x180046f0c  lea     rcx, rva g_pSortGuidHash[rax]
0x180046f13  xor     r15d, [rbx+0C8h]
0x180046f1a  and     r15d, 7Fh
0x180046f1e  mov     rsi, [rcx+r15*8]
0x180046f22  lea     rcx, [rcx+r15*8]
0x180046f26  mov     [rbx+0C0h], r13
0x180046f2d  mov     edx, [rsp+520h+var_4B8]
0x180046f31  test    rsi, rsi
0x180046f34  jnz     loc_1800473FC
0x180046f3a  xor     eax, eax
0x180046f3c  lock cmpxchg [rcx], rbx
0x180046f41  mov     rsi, rax
0x180046f44  jnz     short loc_180046F2D
0x180046f46  mov     rcx, [rsp+520h+var_4E0]
0x180046f4b  test    rcx, rcx
0x180046f4e  jnz     loc_1800477CB
0x180046f54  mov     rsi, rbx
0x180046f57  jmp     loc_180046CC8
0x180046f5c  add     ecx, 0FFF9FE00h
0x180046f62  cmp     ecx, 0FEF9FDFFh
0x180046f68  jbe     loc_180046D79
0x180046f6e  test    rax, rax
0x180046f71  jz      loc_180046CC5
0x180046f77  mov     rax, [rax+68h]
0x180046f7b  mov     rsi, [rax+20h]
0x180046f7f  jmp     loc_180046C1C
0x180046f84  mov     rsi, r13
0x180046f87  jmp     loc_180046D86
0x180046f8c  mov     rax, gs:30h
0x180046f95  mov     ecx, [rax+179Ch]
0x180046f9b  test    ecx, ecx
0x180046f9d  jnz     loc_180047A04
0x180046fa3  mov     ebx, cs:gInteractiveLogonUserProcess
0x180046fa9  cmp     ebx, 0FFFFFFFFh
0x180046fac  jz      loc_180047EF2
0x180046fb2  test    ebx, ebx
0x180046fb4  jz      loc_1800479FA
0x180046fba  mov     rax, cs:gpServerNlsUserInfo
0x180046fc1  mov     ecx, [rax+678h]
0x180046fc7  mov     eax, cs:dword_1803AC290
0x180046fcd  cmp     eax, ecx
0x180046fcf  jz      short loc_180046FD9
0x180046fd1  mov     cs:word_1803AC296, r15w
0x180046fd9  movzx   eax, cs:word_1803AC296
0x180046fe0  test    ax, ax
0x180046fe3  jz      loc_1800475E6
0x180046fe9  movzx   eax, cs:word_1803AC294
0x180046ff0  cmp     ax, 3
0x180046ff4  jz      short loc_18004701A
0x180046ff6  lea     rcx, gNlsProcessCacheLock
0x180046ffd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180047004  nop     dword ptr [rax+rax+00h]
0x180047009  movzx   eax, cs:word_1803AC294
0x180047010  cmp     ax, 3
0x180047014  jnz     loc_18004786C
0x18004701a  mov     ecx, 2
0x18004701f  mov     cs:word_1803AC296, cx
0x180047026  cmp     ax, r15w
0x18004702a  jnz     short loc_180047071
0x18004702c  xor     edx, edx; Val
0x18004702e  lea     rcx, [rbp+420h+ApiMessage]; void *
0x180047032  mov     r8d, 3B8h; Size
0x180047038  call    memset_0
0x18004703d  mov     edx, 67Ch; BufferSize
  ... truncated ...
```
