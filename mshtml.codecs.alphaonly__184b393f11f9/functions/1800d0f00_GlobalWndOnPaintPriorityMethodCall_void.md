# GlobalWndOnPaintPriorityMethodCall(void)

- ea: `0x1800d0f00`
- end: `0x1800d189d`
- name: `?GlobalWndOnPaintPriorityMethodCall@@YAXXZ`
- size: `2461`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800d0380`
- `0x1800d04f4`

## callees

- `0x1800d0f00`
- `0x1800d18a4`
- `0x18011d7c8`
- `0x1801a2094`
- `0x18058a604`
- `0x18062a2c8`
- `0x1807302dc`
- `0x18079b8d4`
- `0x180b4f148`
- `0x180b4f264`
- `0x180b51434`
- `0x1810c2caa`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800d10ce`
- `KERNEL32!QueryPerformanceCounter` at `0x1800d10ce`
- `KERNEL32!GetTickCount` at `0x1800d107e`
- `KERNEL32!GetTickCount` at `0x1800d107e`
- `KERNEL32!GetTickCount64` at `0x1800d118f`
- `KERNEL32!GetTickCount64` at `0x1800d13ca`
- `KERNEL32!GetTickCount64` at `0x1800d13ef`
- `KERNEL32!GetTickCount64` at `0x1800d118f`
- `KERNEL32!GetTickCount64` at `0x1800d13ca`
- `KERNEL32!GetTickCount64` at `0x1800d13ef`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800d1617`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800d1617`
- `KERNEL32!LeaveCriticalSection` at `0x1800d129e`
- `KERNEL32!LeaveCriticalSection` at `0x1800d14b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800d14f3`
- `KERNEL32!LeaveCriticalSection` at `0x1800d181e`
- `KERNEL32!LeaveCriticalSection` at `0x1800d129e`
- `KERNEL32!LeaveCriticalSection` at `0x1800d14b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800d14f3`
- `KERNEL32!LeaveCriticalSection` at `0x1800d181e`
- `KERNEL32!EnterCriticalSection` at `0x1800d0f60`
- `KERNEL32!EnterCriticalSection` at `0x1800d1379`
- `KERNEL32!EnterCriticalSection` at `0x1800d1438`
- `KERNEL32!EnterCriticalSection` at `0x1800d185d`
- `KERNEL32!EnterCriticalSection` at `0x1800d0f60`
- `KERNEL32!EnterCriticalSection` at `0x1800d1379`
- `KERNEL32!EnterCriticalSection` at `0x1800d1438`
- `KERNEL32!EnterCriticalSection` at `0x1800d185d`
- `USER32!PostMessageW` at `0x1800d1529`
- `USER32!PostMessageW` at `0x1800d1529`
- `USER32!KillTimer` at `0x1800d1060`
- `USER32!KillTimer` at `0x1800d1060`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d12dc`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d12e5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d12ee`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d12f8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1312`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d131c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d12dc`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d12e5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d12ee`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d12f8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1312`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d131c`
- `bcrypt!BCryptGenRandom` at `0x1800d1766`
- `bcrypt!BCryptGenRandom` at `0x1800d1766`

## pseudocode

```c
void GlobalWndOnPaintPriorityMethodCall(void)
{
  __int64 v0; // r12
  __int64 v1; // rdi
  int v2; // r13d
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  __int64 v4; // r9
  __int64 v5; // rcx
  __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // r15
  __int64 v9; // rsi
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rsi
  UINT_PTR v13; // rsi
  __int64 v14; // r9
  int v15; // ecx
  __int64 v16; // rcx
  DWORD TickCount; // eax
  __int64 v18; // r8
  DWORD v19; // ebx
  HWND v20; // rcx
  __int64 v21; // rbx
  LARGE_INTEGER v22; // r9
  LARGE_INTEGER v23; // rsi
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // r8
  ULONGLONG TickCount64; // rax
  __int64 v27; // rdx
  __int64 v28; // rbx
  int v29; // r15d
  int v30; // r13d
  __int64 v31; // r14
  __int64 v32; // r14
  __int64 v33; // rsi
  unsigned __int64 v34; // r12
  __int128 v35; // xmm7
  int *i; // rdx
  int v37; // eax
  __int64 v38; // rcx
  int v39; // esi
  int j; // ebx
  __int64 v41; // rcx
  __int128 v42; // xmm6
  char v43; // bl
  struct IE_GLOBAL_THREAD_STATE *v44; // rax
  unsigned __int64 v45; // rdx
  int k; // ebx
  __int64 v47; // rax
  int v48; // eax
  __int64 v49; // rbx
  __int64 v50; // rbx
  __int64 v51; // rbx
  __int64 v52; // rax
  int v53; // esi
  _OWORD *v54; // r10
  int v55; // r11d
  __int64 v56; // r9
  __int64 v57; // rcx
  int *v58; // rdx
  int m; // ecx
  unsigned int v60; // r8d
  unsigned int v61; // r10d
  __int64 v62; // rdx
  unsigned int v63; // eax
  unsigned int v64; // eax
  unsigned int v65; // eax
  unsigned __int64 v66; // rbx
  void (__fastcall *v67)(__int64, __int64, _QWORD); // rax
  __int64 v68; // rcx
  __int64 v69; // rcx
  UCHAR pbBuffer[2]; // [rsp+38h] [rbp-79h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-71h] BYREF
  unsigned __int64 v72; // [rsp+48h] [rbp-69h] BYREF
  int v73; // [rsp+50h] [rbp-61h]
  unsigned int v74; // [rsp+54h] [rbp-5Dh]
  ULONGLONG v75; // [rsp+58h] [rbp-59h]
  __int64 v76; // [rsp+60h] [rbp-51h]

  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v76 = v0;
  v1 = *(_QWORD *)(v0 + 16);
  if ( v1 )
  {
    v2 = 0;
    v3 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v1 + 232) + 192LL);
    v73 = 0;
    EnterCriticalSection(v3);
    ++*(_WORD *)(*(_QWORD *)(v1 + 232) + 126LL);
    v4 = *(_QWORD *)(v1 + 232);
    LODWORD(v5) = *(_DWORD *)(v4 + 128);
    v74 = v5;
    *(_DWORD *)(v4 + 128) = v5 + 1;
    if ( !(_DWORD)v5 )
    {
      v60 = 0;
      v61 = *(_DWORD *)(*(_QWORD *)(v4 + 136) + 4LL);
      if ( v61 )
      {
        do
        {
          v62 = v60++;
          v5 = *(_QWORD *)(*(_QWORD *)(v4 + 136) + 8LL);
          *(_DWORD *)((v62 << 6) + v5 + 36) = 0;
        }
        while ( v60 < v61 );
      }
    }
    v6 = *(_QWORD *)(v1 + 232) + 304LL;
    if ( *(_BYTE *)(*(_QWORD *)(v1 + 232) + 321LL) )
    {
      v7 = *(_QWORD *)(v0 + 16);
      if ( v7 )
      {
        v8 = *(_QWORD *)(v7 + 232);
        if ( v8 )
        {
          v9 = *(_QWORD *)(v8 + 112);
          if ( v9 )
          {
            v10 = *(_DWORD *)(v9 + 4);
            v11 = 0;
            v12 = *(_QWORD *)(v9 + 8);
            while ( v10 > 0 )
            {
              if ( *(_QWORD *)v12 == v6 && *(_DWORD *)(v12 + 16) == 52737 )
              {
                if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
                  McTemplateU0pqpq_EventWriteTransfer(
                    v5,
                    (unsigned int)MSHTML_FORMSTIMER_KILL,
                    *(_QWORD *)v12,
                    52737,
                    *(_QWORD *)(v12 + 8),
                    *(_DWORD *)(v12 + 24));
                v13 = *(unsigned int *)(v12 + 20);
                if ( v11 >= 0 )
                {
                  v14 = *(_QWORD *)(v8 + 112);
                  v15 = *(_DWORD *)(v14 + 4);
                  if ( v11 < v15 )
                  {
                    *(_DWORD *)(v14 + 4) = v15 - 1;
                    if ( v11 < (unsigned int)(v15 - 1) )
                      memmove_0(
                        (void *)(*(_QWORD *)(v14 + 8) + 56LL * v11),
                        (const void *)(*(_QWORD *)(v14 + 8) + 56LL * (v11 + 1)),
                        56LL * (unsigned int)(v15 - v11 - 1));
                  }
                }
                KillTimer(*(HWND *)(v8 + 96), v13);
                break;
              }
              --v10;
              ++v11;
              v12 += 56;
            }
          }
        }
      }
      *(_BYTE *)(v6 + 17) = 0;
    }
    v16 = *(_QWORD *)(v1 + 232);
    if ( *(_QWORD *)(v16 + 136) )
    {
      TickCount = GetTickCount();
      v18 = *(_QWORD *)(v1 + 232);
      v19 = TickCount;
      v20 = *(HWND *)(v18 + 96);
      if ( v20 && TickCount - *(_DWORD *)(v18 + 328) > 0x1388 )
      {
        PostMessageW(v20, 0x113u, 0x2000u, 0);
        *(_DWORD *)(*(_QWORD *)(v1 + 232) + 328LL) = v19;
      }
      v21 = *(_QWORD *)(v1 + 232);
      if ( *(_DWORD *)(v21 + 60) )
      {
        if ( *(_DWORD *)(v21 + 60) == 2 )
        {
          PerformanceCount.QuadPart = 0;
          QueryPerformanceCounter(&PerformanceCount);
          v22 = CQPCTick::s_qpcFrequency;
          if ( CQPCTick::s_qpcFrequency.QuadPart
            || (QueryPerformanceFrequency(&CQPCTick::s_qpcFrequency),
                v22 = CQPCTick::s_qpcFrequency,
                CQPCTick::s_qpcFrequency.QuadPart) )
          {
            v23 = PerformanceCount;
            if ( PerformanceCount.QuadPart && v22.QuadPart && v22.QuadPart != 1000000 )
              v23.QuadPart = 1000000 * (PerformanceCount.QuadPart % (unsigned __int64)v22.QuadPart) / v22.QuadPart
                           + 1000000 * (PerformanceCount.QuadPart / (unsigned __int64)v22.QuadPart);
          }
          else
          {
            v23.QuadPart = 0;
          }
          LODWORD(v24) = -1;
          v25 = (v23.QuadPart - *(_QWORD *)(v21 + 24)) / 0x3E8uLL;
          if ( 1000 * (unsigned __int64)(unsigned int)(*(_DWORD *)(v21 + 16) + *(_DWORD *)(v21 + 32)) / v25 < 0xFFFFFFFF )
            v24 = 1000 * (unsigned __int64)(unsigned int)(*(_DWORD *)(v21 + 16) + *(_DWORD *)(v21 + 32)) / v25;
          if ( *(_BYTE *)(v21 + 56) )
          {
            v65 = *(_DWORD *)(v21 + 52);
            if ( v65 < *(_DWORD *)(v21 + 68) || (unsigned int)v24 >= *(_DWORD *)(v21 + 64) )
            {
              v72 = 0;
              CQPCTick::GetCurrentTimeInUs(&v72);
              CallRate::MarkCall((CallRate *)(v21 + 8), v72);
            }
            else
            {
              *(_BYTE *)(v21 + 56) = 0;
              CallRateManager::LogPauseTaskDisabled((CallRateManager *)v21, v65);
            }
          }
          else if ( (unsigned int)v24 >= *(_DWORD *)(v21 + 64) )
          {
            *(_BYTE *)(v21 + 56) = 1;
            CallRateManager::LogPauseTaskEnabled((CallRateManager *)v21, v24);
            if ( v23.QuadPart - *(_QWORD *)(v21 + 88) > *(_QWORD *)(v21 + 72) )
            {
              *(_DWORD *)(v21 + 80) = 2000;
              *(_DWORD *)(v21 + 84) = 1;
            }
            else
            {
              v63 = *(_DWORD *)(v21 + 80);
              if ( v63 < 0x4E20 )
              {
                *(_DWORD *)(v21 + 80) = v63 + 1000;
                v64 = *(_DWORD *)(v21 + 84);
                if ( v64 < 0xF )
                  *(_DWORD *)(v21 + 84) = v64 + 1;
              }
            }
            *(LARGE_INTEGER *)(v21 + 88) = v23;
            _InterlockedExchange64(
              (volatile __int64 *)StaticFrequency::GetInstance() + 5,
              COERCE__INT64((double)*(int *)(v21 + 84)));
          }
        }
        if ( *(_BYTE *)(v21 + 56) || *(_DWORD *)(v21 + 60) == 1 )
        {
          v72 = 0;
          CQPCTick::GetCurrentTimeInUs(&v72);
          *(_WORD *)pbBuffer = 0;
          BCryptGenRandom(0, pbBuffer, 2u, 2u);
          v66 = (unsigned int)((int)(float)((float)*(int *)(v21 + 80)
                                          * (float)((float)*(unsigned __int16 *)pbBuffer / 65535.0))
                             + 1000);
          do
          {
            PerformanceCount.QuadPart = 0;
            CQPCTick::GetCurrentTimeInUs((unsigned __int64 *)&PerformanceCount.QuadPart);
          }
          while ( PerformanceCount.QuadPart - v72 <= v66 );
        }
      }
      TickCount64 = GetTickCount64();
      v28 = *(_QWORD *)(v1 + 232);
      v29 = 0;
      v75 = TickCount64;
      v30 = *(_DWORD *)(*(_QWORD *)(v28 + 136) + 4LL);
      while ( v30 > 0 )
      {
        v28 = *(_QWORD *)(v1 + 232);
        v31 = *(_QWORD *)(v28 + 136);
        if ( v29 >= *(_DWORD *)(v31 + 4) )
          break;
        v32 = *(_QWORD *)(v31 + 8);
        v33 = (__int64)v29 << 6;
        if ( *(_DWORD *)(v33 + v32 + 36) > v74 )
          break;
        v34 = *(_QWORD *)(v33 + v32);
        if ( v34 )
        {
          if ( (*(_BYTE *)(v33 + v32 + 32) & 2) != 0 )
          {
            v35 = *(_OWORD *)(v33 + v32 + 40);
            PerformanceCount = *(LARGE_INTEGER *)(v33 + v32 + 8);
            v72 = *(_QWORD *)(v33 + v32 + 16);
            for ( i = (int *)(*(_QWORD *)(v28 + 144)
                            + 4 * (v34 % *((unsigned int *)qword_1813BF5B0 + *(int *)(v28 + 152))));
                  *i != v29;
                  i = (int *)(v32 + ((__int64)*i << 6) + 56) )
            {
              ;
            }
            v37 = *(_DWORD *)(v33 + v32 + 56);
            *(_QWORD *)(v33 + v32) = 0;
            *(_QWORD *)(v33 + v32 + 16) = 0;
            *(_QWORD *)(v33 + v32 + 24) = 0;
            *(_DWORD *)(v33 + v32 + 32) = 0;
            *(GUID *)(v33 + v32 + 40) = GUID_NULL;
            *i = v37;
            *(_DWORD *)(v33 + v32 + 56) = -1;
            v38 = *(_QWORD *)(v1 + 232);
            v39 = *(_DWORD *)(v38 + 296);
            LeaveCriticalSection((LPCRITICAL_SECTION)(v38 + 192));
            for ( j = 0; j < *(_DWORD *)(v1 + 516); ++j )
            {
              v41 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 520) + 8LL * j) + 5472LL);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 144LL))(v41);
            }
            v42 = *(_OWORD *)GlobalThreadState();
            v43 = *((_BYTE *)GlobalThreadState() + 16);
            *(_OWORD *)GlobalThreadState() = v35;
            v44 = GlobalThreadState();
            v45 = v72;
            *((_BYTE *)v44 + 16) = 1;
            ((void (__fastcall *)(unsigned __int64, unsigned __int64))PerformanceCount.QuadPart)(v34, v45);
            *(_OWORD *)GlobalThreadState() = v42;
            *((_BYTE *)GlobalThreadState() + 16) = v43;
            if ( !*(_WORD *)(*(_QWORD *)(v1 + 232) + 122LL) )
            {
              for ( k = 0; k < *(_DWORD *)(v1 + 516); ++k )
              {
                v47 = *(_QWORD *)(v1 + 520);
                if ( *(int *)(*(_QWORD *)(v47 + 8LL * k) + 6932LL) > 0 )
                  CObserverManager::InvokeObserversForCheckpoint((CObserverManager *)(*(_QWORD *)(v47 + 8LL * k) + 6928LL));
              }
            }
            EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v1 + 232) + 192LL));
            v28 = *(_QWORD *)(v1 + 232);
            if ( !*(_QWORD *)(v28 + 136) )
            {
              *(_WORD *)(v28 + 124) = 0;
              v2 = 0;
              goto LABEL_68;
            }
            --v30;
            v48 = 0;
            if ( ((*(_DWORD *)(v28 + 296) ^ v39) & 0xFFF00000) == 0 )
              v48 = v29;
            v29 = v48;
          }
        }
        else
        {
          v67 = *(void (__fastcall **)(__int64, __int64, _QWORD))(v33 + v32 + 24);
          if ( v67 )
          {
            v68 = *(_QWORD *)(v33 + v32 + 16);
            if ( v68 )
            {
              v67(v68, v27, 0);
              *(_QWORD *)(v33 + v32 + 24) = 0;
              *(_QWORD *)(v33 + v32 + 16) = 0;
              v28 = *(_QWORD *)(v1 + 232);
            }
          }
        }
        ++v29;
      }
      *(_DWORD *)(v28 + 316) += GetTickCount64() - v75;
      ++*(_DWORD *)(v28 + 312);
      v49 = *(_QWORD *)(v1 + 232);
      if ( !*(_BYTE *)(v49 + 322)
        || *(_QWORD *)(v49 + 304) + 600LL > GetTickCount64()
        || *(_DWORD *)(v49 + 312) < 4u && *(_DWORD *)(v49 + 316) < 0x258u
        || (LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v1 + 232) + 192LL)),
            CGwndPaintRequest::PostTimerYield(
              (CGwndPaintRequest *)(*(_QWORD *)(v1 + 232) + 304LL),
              *(struct GWND **)(v1 + 232)),
            CGwndPaintRequest::YieldToMessages((CGwndPaintRequest *)(*(_QWORD *)(v1 + 232) + 304LL), 0xFu),
            EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v1 + 232) + 192LL)),
            v69 = *(_QWORD *)(v1 + 232),
            *(_QWORD *)(v69 + 136)) )
      {
        v2 = 0;
        v50 = *(_QWORD *)(v76 + 16);
        if ( v50 )
          v51 = *(_QWORD *)(v50 + 232);
        else
          v51 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)(v51 + 192));
        v52 = *(_QWORD *)(v51 + 136);
        v53 = 0;
        if ( *(int *)(v52 + 4) > 0 )
        {
          v54 = *(_OWORD **)(v52 + 8);
          v55 = 0;
          do
          {
            v56 = *(_QWORD *)(v52 + 8) + ((__int64)v55 << 6);
            if ( *(_QWORD *)v56 || *(_QWORD *)(v56 + 24) && *(_QWORD *)(v56 + 16) )
            {
              if ( v54 != (_OWORD *)v56 )
              {
                *v54 = *(_OWORD *)v56;
                v54[1] = *(_OWORD *)(v56 + 16);
                v54[2] = *(_OWORD *)(v56 + 32);
                v54[3] = *(_OWORD *)(v56 + 48);
                if ( *(_QWORD *)v56 )
                {
                  v58 = (int *)(*(_QWORD *)(v51 + 144)
                              + 4
                              * (*(_QWORD *)v56
                               % (unsigned __int64)*((unsigned int *)qword_1813BF5B0 + *(int *)(v51 + 152))));
                  for ( m = *v58; *v58 != v55; m = *v58 )
                    v58 = (int *)(*(_QWORD *)(*(_QWORD *)(v51 + 136) + 8LL) + 56LL + ((__int64)m << 6));
                  *v58 = v53;
                }
              }
              v54 += 4;
              ++v53;
              if ( (*(_BYTE *)(v56 + 32) & 2) != 0 )
                ++v2;
            }
            v52 = *(_QWORD *)(v51 + 136);
            ++v55;
          }
          while ( v55 < *(_DWORD *)(v52 + 4) );
        }
        *(_DWORD *)(v52 + 4) = v53;
        *(_DWORD *)(v51 + 296) = (*(_DWORD *)(v51 + 296) + 0x100000)
                               ^ (*(_DWORD *)(v51 + 296)
                                ^ (*(_DWORD *)(v51 + 296) + 0x100000))
                               & 0xFFFFF;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v51 + 192));
      }
      else
      {
        v2 = v73;
        *(_WORD *)(v69 + 124) = 0;
      }
    }
    else
    {
      *(_WORD *)(v16 + 124) = 0;
    }
LABEL_68:
    v57 = *(_QWORD *)(v1 + 232);
    if ( *(_WORD *)(v57 + 124) )
      --*(_WORD *)(v57 + 124);
    --*(_WORD *)(*(_QWORD *)(v1 + 232) + 126LL);
    if ( v2 )
      CGwndPaintRequest::MakeRequest((CGwndPaintRequest *)(*(_QWORD *)(v1 + 232) + 304LL), *(struct GWND **)(v1 + 232));
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v1 + 232) + 192LL));
  }
}

```

## disassembly

```asm
0x1800d0f00  mov     rax, rsp
0x1800d0f03  push    rbp
0x1800d0f04  push    rbx
0x1800d0f05  push    rsi
0x1800d0f06  push    rdi
0x1800d0f07  push    r12
0x1800d0f09  push    r13
0x1800d0f0b  push    r14
0x1800d0f0d  push    r15
0x1800d0f0f  lea     rbp, [rax-5Fh]
0x1800d0f13  sub     rsp, 0C8h
0x1800d0f1a  mov     ecx, cs:_tls_index
0x1800d0f20  movaps  xmmword ptr [rax-58h], xmm6
0x1800d0f24  movaps  xmmword ptr [rax-68h], xmm7
0x1800d0f28  mov     rax, gs:58h
0x1800d0f31  mov     ebx, 10h
0x1800d0f36  mov     r12, [rax+rcx*8]
0x1800d0f3a  mov     [rbp+57h+var_A8], r12
0x1800d0f3e  mov     rdi, [r12+rbx]
0x1800d0f42  test    rdi, rdi
0x1800d0f45  jz      loc_1800D14F9
0x1800d0f4b  mov     rcx, [rdi+0E8h]
0x1800d0f52  xor     r13d, r13d
0x1800d0f55  add     rcx, 0C0h; lpCriticalSection
0x1800d0f5c  mov     [rbp+57h+var_B8], r13d
0x1800d0f60  call    cs:__imp_EnterCriticalSection
0x1800d0f66  mov     rax, [rdi+0E8h]
0x1800d0f6d  lea     r11d, [r13+1]
0x1800d0f71  add     [rax+7Eh], r11w
0x1800d0f76  mov     r9, [rdi+0E8h]
0x1800d0f7d  mov     ecx, [r9+80h]
0x1800d0f84  mov     [rbp+57h+var_B4], ecx
0x1800d0f87  lea     eax, [rcx+1]
0x1800d0f8a  mov     [r9+80h], eax
0x1800d0f91  test    ecx, ecx
0x1800d0f93  jz      loc_1800D165F
0x1800d0f99  mov     r14, [rdi+0E8h]
0x1800d0fa0  add     r14, 130h
0x1800d0fa7  cmp     [r14+11h], r13b
0x1800d0fab  jz      loc_1800D15FE
0x1800d0fb1  mov     r15, [r12+rbx]
0x1800d0fb5  xor     r12d, r12d
0x1800d0fb8  test    r15, r15
0x1800d0fbb  jz      loc_1800D1066
0x1800d0fc1  mov     r15, [r15+0E8h]
0x1800d0fc8  test    r15, r15
0x1800d0fcb  jz      loc_1800D1066
0x1800d0fd1  mov     rsi, [r15+70h]
0x1800d0fd5  test    rsi, rsi
0x1800d0fd8  jz      loc_1800D1066
0x1800d0fde  mov     eax, [rsi+4]
0x1800d0fe1  mov     ebx, r12d
0x1800d0fe4  mov     rsi, [rsi+8]
0x1800d0fe8  mov     r9d, 0CE01h
0x1800d0fee  test    eax, eax
0x1800d0ff0  jle     short loc_1800D1066
0x1800d0ff2  cmp     [rsi], r14
0x1800d0ff5  jnz     loc_1800D13BB
0x1800d0ffb  cmp     [rsi+10h], r9d
0x1800d0fff  jnz     loc_1800D13BB
0x1800d1005  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1800d100c  jnz     loc_1800D1635
0x1800d1012  mov     esi, [rsi+14h]
0x1800d1015  test    ebx, ebx
0x1800d1017  js      short loc_1800D1059
0x1800d1019  mov     r9, [r15+70h]
0x1800d101d  mov     ecx, [r9+4]
0x1800d1021  cmp     ebx, ecx
0x1800d1023  jge     short loc_1800D1059
0x1800d1025  lea     eax, [rcx-1]
0x1800d1028  mov     [r9+4], eax
0x1800d102c  cmp     ebx, eax
0x1800d102e  jnb     short loc_1800D1059
0x1800d1030  sub     ecx, ebx
0x1800d1032  sub     ecx, r11d
0x1800d1035  mov     eax, ecx
0x1800d1037  imul    r8, rax, 38h ; '8'; Size
0x1800d103b  lea     eax, [rbx+1]
0x1800d103e  movsxd  rdx, eax
0x1800d1041  movsxd  rax, ebx
0x1800d1044  imul    rcx, rax, 38h ; '8'
0x1800d1048  imul    rdx, 38h ; '8'
0x1800d104c  add     rcx, [r9+8]; void *
0x1800d1050  add     rdx, [r9+8]; Src
0x1800d1054  call    memmove_0
0x1800d1059  mov     rcx, [r15+60h]; hWnd
0x1800d105d  mov     rdx, rsi; uIDEvent
0x1800d1060  call    cs:__imp_KillTimer
0x1800d1066  mov     [r14+11h], r12b
0x1800d106a  mov     rcx, [rdi+0E8h]
0x1800d1071  cmp     [rcx+88h], r12
0x1800d1078  jz      loc_1800D1606
0x1800d107e  call    cs:__imp_GetTickCount
0x1800d1084  mov     r8, [rdi+0E8h]
0x1800d108b  mov     ebx, eax
0x1800d108d  mov     rcx, [r8+60h]; hWnd
0x1800d1091  test    rcx, rcx
0x1800d1094  jz      short loc_1800D10AB
0x1800d1096  mov     edx, eax
0x1800d1098  sub     edx, [r8+148h]
0x1800d109f  cmp     edx, 1388h
0x1800d10a5  ja      loc_1800D151B
0x1800d10ab  mov     rbx, [rdi+0E8h]
0x1800d10b2  cmp     [rbx+3Ch], r12d
0x1800d10b6  jz      loc_1800D118F
0x1800d10bc  cmp     dword ptr [rbx+3Ch], 2
0x1800d10c0  jnz     loc_1800D117B
0x1800d10c6  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800d10ca  mov     qword ptr [rbp+57h+PerformanceCount], r13
0x1800d10ce  call    cs:__imp_QueryPerformanceCounter
0x1800d10d4  mov     r9, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x1800d10db  test    r9, r9
0x1800d10de  jz      loc_1800D1610
0x1800d10e4  mov     rsi, qword ptr [rbp+57h+PerformanceCount]
0x1800d10e8  test    rsi, rsi
0x1800d10eb  jz      short loc_1800D1126
0x1800d10ed  test    r9, r9
0x1800d10f0  jz      short loc_1800D1126
0x1800d10f2  cmp     r9, 0F4240h
0x1800d10f9  jz      short loc_1800D1126
0x1800d10fb  xor     edx, edx
0x1800d10fd  mov     rax, rsi
0x1800d1100  div     r9
0x1800d1103  xor     edx, edx
0x1800d1105  mov     rcx, rax
0x1800d1108  mov     r8, rax
0x1800d110b  imul    rcx, r9
0x1800d110f  sub     rsi, rcx
0x1800d1112  imul    rax, rsi, 0F4240h
0x1800d1119  imul    rsi, r8, 0F4240h
0x1800d1120  div     r9
0x1800d1123  add     rsi, rax
0x1800d1126  mov     eax, [rbx+20h]
0x1800d1129  mov     r8, rsi
0x1800d112c  add     eax, [rbx+10h]
0x1800d112f  sub     r8, [rbx+18h]
0x1800d1133  imul    rcx, rax, 3E8h
0x1800d113a  mov     rax, 624DD2F1A9FBE77h
0x1800d1144  mul     r8
0x1800d1147  mov     rax, rcx
0x1800d114a  mov     ecx, 0FFFFFFFFh
0x1800d114f  sub     r8, rdx
0x1800d1152  shr     r8, 1
0x1800d1155  add     r8, rdx
0x1800d1158  xor     edx, edx
0x1800d115a  shr     r8, 9
0x1800d115e  div     r8
0x1800d1161  cmp     rax, rcx
0x1800d1164  cmovb   rcx, rax
0x1800d1168  cmp     [rbx+38h], r12b
0x1800d116c  jnz     loc_1800D1706
0x1800d1172  cmp     ecx, [rbx+40h]
0x1800d1175  jnb     loc_1800D169A
0x1800d117b  cmp     [rbx+38h], r12b
0x1800d117f  jnz     loc_1800D1745
0x1800d1185  cmp     dword ptr [rbx+3Ch], 1
0x1800d1189  jz      loc_1800D1745
0x1800d118f  call    cs:__imp_GetTickCount64
0x1800d1195  mov     rbx, [rdi+0E8h]
0x1800d119c  mov     r15d, r12d
0x1800d119f  mov     [rbp+57h+var_B0], rax
0x1800d11a3  mov     rcx, [rbx+88h]
0x1800d11aa  mov     r13d, [rcx+4]
0x1800d11ae  lea     rcx, qword_1813BF5B0
0x1800d11b5  test    r13d, r13d
0x1800d11b8  jle     loc_1800D13CA
0x1800d11be  mov     rbx, [rdi+0E8h]
0x1800d11c5  mov     r14, [rbx+88h]
0x1800d11cc  cmp     r15d, [r14+4]
0x1800d11d0  jge     loc_1800D13CA
0x1800d11d6  mov     r14, [r14+8]
0x1800d11da  mov     eax, [rbp+57h+var_B4]
0x1800d11dd  movsxd  rsi, r15d
0x1800d11e0  shl     rsi, 6
0x1800d11e4  cmp     [rsi+r14+24h], eax
0x1800d11e9  ja      loc_1800D13CA
0x1800d11ef  mov     r12, [rsi+r14]
0x1800d11f3  xor     r8d, r8d
0x1800d11f6  test    r12, r12
0x1800d11f9  jz      loc_1800D17C0
0x1800d11ff  test    byte ptr [rsi+r14+20h], 2
0x1800d1205  jz      loc_1800D17B8
0x1800d120b  mov     rax, [rsi+r14+8]
0x1800d1210  xor     edx, edx
0x1800d1212  movups  xmm7, xmmword ptr [rsi+r14+28h]
0x1800d1218  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x1800d121c  mov     rax, [rsi+r14+10h]
0x1800d1221  mov     [rbp+57h+var_C0], rax
0x1800d1225  movsxd  rax, dword ptr [rbx+98h]
0x1800d122c  mov     ecx, [rcx+rax*4]
0x1800d122f  mov     rax, r12
0x1800d1232  div     rcx
0x1800d1235  mov     rax, [rbx+90h]
0x1800d123c  mov     ecx, edx
0x1800d123e  lea     rdx, [rax+rcx*4]
0x1800d1242  jmp     short loc_1800D1252
0x1800d1244  movsxd  rdx, eax
0x1800d1247  shl     rdx, 6
0x1800d124b  add     rdx, 38h ; '8'
0x1800d124f  add     rdx, r14
0x1800d1252  mov     eax, [rdx]
0x1800d1254  cmp     eax, r15d
0x1800d1257  jnz     short loc_1800D1244
0x1800d1259  mov     eax, [rsi+r14+38h]
0x1800d125e  mov     [rsi+r14], r8
0x1800d1262  mov     [rsi+r14+10h], r8
0x1800d1267  mov     [rsi+r14+18h], r8
0x1800d126c  mov     [rsi+r14+20h], r8d
0x1800d1271  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800d1278  movdqu  xmmword ptr [rsi+r14+28h], xmm0
0x1800d127f  mov     [rdx], eax
0x1800d1281  mov     dword ptr [rsi+r14+38h], 0FFFFFFFFh
0x1800d128a  mov     rcx, [rdi+0E8h]
0x1800d1291  mov     esi, [rcx+128h]
0x1800d1297  add     rcx, 0C0h; lpCriticalSection
0x1800d129e  call    cs:__imp_LeaveCriticalSection
0x1800d12a4  xor     ebx, ebx
0x1800d12a6  cmp     [rdi+204h], ebx
0x1800d12ac  jle     short loc_1800D12DC
0x1800d12ae  mov     rax, [rdi+208h]
0x1800d12b5  movsxd  rcx, ebx
0x1800d12b8  mov     rcx, [rax+rcx*8]
0x1800d12bc  mov     rcx, [rcx+1560h]
0x1800d12c3  mov     rax, [rcx]
0x1800d12c6  mov     rax, [rax+90h]
0x1800d12cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d12d2  inc     ebx
0x1800d12d4  cmp     ebx, [rdi+204h]
0x1800d12da  jl      short loc_1800D12AE
0x1800d12dc  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d12e2  movups  xmm6, xmmword ptr [rax]
0x1800d12e5  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d12eb  mov     bl, [rax+10h]
0x1800d12ee  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d12f4  movdqu  xmmword ptr [rax], xmm7
0x1800d12f8  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d12fe  mov     rdx, [rbp+57h+var_C0]
0x1800d1302  mov     rcx, r12
0x1800d1305  mov     byte ptr [rax+10h], 1
0x1800d1309  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x1800d130d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1312  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d1318  movdqu  xmmword ptr [rax], xmm6
0x1800d131c  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d1322  xor     r12d, r12d
0x1800d1325  mov     [rax+10h], bl
0x1800d1328  mov     rax, [rdi+0E8h]
0x1800d132f  cmp     [rax+7Ah], r12w
0x1800d1334  jnz     short loc_1800D136B
0x1800d1336  mov     ebx, r12d
0x1800d1339  cmp     [rdi+204h], r12d
0x1800d1340  jle     short loc_1800D136B
0x1800d1342  mov     rax, [rdi+208h]
0x1800d1349  movsxd  rcx, ebx
0x1800d134c  mov     rcx, [rax+rcx*8]
0x1800d1350  add     rcx, 1B10h; this
0x1800d1357  cmp     [rcx+4], r12d
0x1800d135b  jg      loc_1800D15F4
0x1800d1361  inc     ebx
0x1800d1363  cmp     ebx, [rdi+204h]
0x1800d1369  jl      short loc_1800D1342
0x1800d136b  mov     rcx, [rdi+0E8h]
0x1800d1372  add     rcx, 0C0h; lpCriticalSection
0x1800d1379  call    cs:__imp_EnterCriticalSection
0x1800d137f  mov     rbx, [rdi+0E8h]
0x1800d1386  cmp     [rbx+88h], r12
0x1800d138d  jz      loc_1800D15C5
0x1800d1393  xor     esi, [rbx+128h]
0x1800d1399  dec     r13d
0x1800d139c  test    esi, 0FFF00000h
0x1800d13a2  mov     eax, r12d
0x1800d13a5  cmovz   eax, r15d
0x1800d13a9  mov     r15d, eax
0x1800d13ac  lea     rcx, qword_1813BF5B0
0x1800d13b3  inc     r15d
0x1800d13b6  jmp     loc_1800D11B5
0x1800d13bb  sub     eax, r11d
0x1800d13be  add     ebx, r11d
0x1800d13c1  add     rsi, 38h ; '8'
0x1800d13c5  jmp     loc_1800D0FEE
0x1800d13ca  call    cs:__imp_GetTickCount64
0x1800d13d0  sub     eax, dword ptr [rbp+57h+var_B0]
0x1800d13d3  add     [rbx+13Ch], eax
0x1800d13d9  inc     dword ptr [rbx+138h]
0x1800d13df  mov     rbx, [rdi+0E8h]
0x1800d13e6  cmp     [rbx+142h], r12b
0x1800d13ed  jz      short loc_1800D140E
0x1800d13ef  call    cs:__imp_GetTickCount64
0x1800d13f5  mov     rcx, [rbx+130h]
0x1800d13fc  mov     r8d, 258h
0x1800d1402  add     rcx, r8
0x1800d1405  cmp     rcx, rax
0x1800d1408  jbe     loc_1800D17FA
0x1800d140e  mov     rbx, [rbp+57h+var_A8]
0x1800d1412  mov     r13d, r12d
0x1800d1415  mov     eax, 10h
0x1800d141a  mov     rbx, [rbx+rax]
0x1800d141e  test    rbx, rbx
0x1800d1421  jz      loc_1800D15BD
0x1800d1427  mov     rbx, [rbx+0E8h]
  ... truncated ...
```
