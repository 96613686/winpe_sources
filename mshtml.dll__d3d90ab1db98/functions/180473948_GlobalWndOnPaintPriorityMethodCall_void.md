# GlobalWndOnPaintPriorityMethodCall(void)

- ea: `0x180473948`
- end: `0x180474370`
- name: `?GlobalWndOnPaintPriorityMethodCall@@YAXXZ`
- size: `2600`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180472cc0`
- `0x180472e5c`

## callees

- `0x180266858`
- `0x1803e817c`
- `0x180473948`
- `0x180474378`
- `0x180574704`
- `0x180626e88`
- `0x180738758`
- `0x1807a7ab4`
- `0x180b68094`
- `0x180b681b0`
- `0x180b6a564`
- `0x1810f650a`
- `0x181104010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180473b28`
- `KERNEL32!QueryPerformanceCounter` at `0x180473b28`
- `KERNEL32!GetTickCount` at `0x180473ad2`
- `KERNEL32!GetTickCount` at `0x180473ad2`
- `KERNEL32!GetTickCount64` at `0x180473bef`
- `KERNEL32!GetTickCount64` at `0x180473e60`
- `KERNEL32!GetTickCount64` at `0x180473e8b`
- `KERNEL32!GetTickCount64` at `0x180473bef`
- `KERNEL32!GetTickCount64` at `0x180473e60`
- `KERNEL32!GetTickCount64` at `0x180473e8b`
- `KERNEL32!QueryPerformanceFrequency` at `0x1804740d2`
- `KERNEL32!QueryPerformanceFrequency` at `0x1804740d2`
- `KERNEL32!LeaveCriticalSection` at `0x180473d04`
- `KERNEL32!LeaveCriticalSection` at `0x180473f5b`
- `KERNEL32!LeaveCriticalSection` at `0x180473fa1`
- `KERNEL32!LeaveCriticalSection` at `0x1804742e5`
- `KERNEL32!LeaveCriticalSection` at `0x180473d04`
- `KERNEL32!LeaveCriticalSection` at `0x180473f5b`
- `KERNEL32!LeaveCriticalSection` at `0x180473fa1`
- `KERNEL32!LeaveCriticalSection` at `0x1804742e5`
- `KERNEL32!EnterCriticalSection` at `0x1804739a8`
- `KERNEL32!EnterCriticalSection` at `0x180473e09`
- `KERNEL32!EnterCriticalSection` at `0x180473eda`
- `KERNEL32!EnterCriticalSection` at `0x18047432a`
- `KERNEL32!EnterCriticalSection` at `0x1804739a8`
- `KERNEL32!EnterCriticalSection` at `0x180473e09`
- `KERNEL32!EnterCriticalSection` at `0x180473eda`
- `KERNEL32!EnterCriticalSection` at `0x18047432a`
- `USER32!PostMessageW` at `0x180473fde`
- `USER32!PostMessageW` at `0x180473fde`
- `USER32!KillTimer` at `0x180473aae`
- `USER32!KillTimer` at `0x180473aae`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d48`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d57`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d66`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d76`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d96`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473da6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d48`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d57`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d66`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d76`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473d96`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180473da6`
- `bcrypt!BCryptGenRandom` at `0x180474227`
- `bcrypt!BCryptGenRandom` at `0x180474227`

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
                            + 4 * (v34 % *((unsigned int *)qword_1813F3260 + *(int *)(v28 + 152))));
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
                               % (unsigned __int64)*((unsigned int *)qword_1813F3260 + *(int *)(v51 + 152))));
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
0x180473948  mov     rax, rsp
0x18047394b  push    rbp
0x18047394c  push    rbx
0x18047394d  push    rsi
0x18047394e  push    rdi
0x18047394f  push    r12
0x180473951  push    r13
0x180473953  push    r14
0x180473955  push    r15
0x180473957  lea     rbp, [rax-5Fh]
0x18047395b  sub     rsp, 0C8h
0x180473962  mov     ecx, cs:_tls_index
0x180473968  movaps  xmmword ptr [rax-58h], xmm6
0x18047396c  movaps  xmmword ptr [rax-68h], xmm7
0x180473970  mov     rax, gs:58h
0x180473979  mov     ebx, 10h
0x18047397e  mov     r12, [rax+rcx*8]
0x180473982  mov     [rbp+57h+var_A8], r12
0x180473986  mov     rdi, [r12+rbx]
0x18047398a  test    rdi, rdi
0x18047398d  jz      loc_180473FAD
0x180473993  mov     rcx, [rdi+0E8h]
0x18047399a  xor     r13d, r13d
0x18047399d  add     rcx, 0C0h; lpCriticalSection
0x1804739a4  mov     [rbp+57h+var_B8], r13d
0x1804739a8  call    cs:__imp_EnterCriticalSection
0x1804739af  nop     dword ptr [rax+rax+00h]
0x1804739b4  mov     rax, [rdi+0E8h]
0x1804739bb  lea     r11d, [r13+1]
0x1804739bf  add     [rax+7Eh], r11w
0x1804739c4  mov     r9, [rdi+0E8h]
0x1804739cb  mov     ecx, [r9+80h]
0x1804739d2  mov     [rbp+57h+var_B4], ecx
0x1804739d5  lea     eax, [rcx+1]
0x1804739d8  mov     [r9+80h], eax
0x1804739df  test    ecx, ecx
0x1804739e1  jz      loc_180474120
0x1804739e7  mov     r14, [rdi+0E8h]
0x1804739ee  add     r14, 130h
0x1804739f5  cmp     [r14+11h], r13b
0x1804739f9  jz      loc_1804740B9
0x1804739ff  mov     r15, [r12+rbx]
0x180473a03  xor     r12d, r12d
0x180473a06  test    r15, r15
0x180473a09  jz      loc_180473ABA
0x180473a0f  mov     r15, [r15+0E8h]
0x180473a16  test    r15, r15
0x180473a19  jz      loc_180473ABA
0x180473a1f  mov     rsi, [r15+70h]
0x180473a23  test    rsi, rsi
0x180473a26  jz      loc_180473ABA
0x180473a2c  mov     eax, [rsi+4]
0x180473a2f  mov     ebx, r12d
0x180473a32  mov     rsi, [rsi+8]
0x180473a36  mov     r9d, 0CE01h
0x180473a3c  test    eax, eax
0x180473a3e  jle     short loc_180473ABA
0x180473a40  cmp     [rsi], r14
0x180473a43  jnz     loc_180473E51
0x180473a49  cmp     [rsi+10h], r9d
0x180473a4d  jnz     loc_180473E51
0x180473a53  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x180473a5a  jnz     loc_1804740F6
0x180473a60  mov     esi, [rsi+14h]
0x180473a63  test    ebx, ebx
0x180473a65  js      short loc_180473AA7
0x180473a67  mov     r9, [r15+70h]
0x180473a6b  mov     ecx, [r9+4]
0x180473a6f  cmp     ebx, ecx
0x180473a71  jge     short loc_180473AA7
0x180473a73  lea     eax, [rcx-1]
0x180473a76  mov     [r9+4], eax
0x180473a7a  cmp     ebx, eax
0x180473a7c  jnb     short loc_180473AA7
0x180473a7e  sub     ecx, ebx
0x180473a80  sub     ecx, r11d
0x180473a83  mov     eax, ecx
0x180473a85  imul    r8, rax, 38h ; '8'; Size
0x180473a89  lea     eax, [rbx+1]
0x180473a8c  movsxd  rdx, eax
0x180473a8f  movsxd  rax, ebx
0x180473a92  imul    rcx, rax, 38h ; '8'
0x180473a96  imul    rdx, 38h ; '8'
0x180473a9a  add     rcx, [r9+8]; void *
0x180473a9e  add     rdx, [r9+8]; Src
0x180473aa2  call    memmove_0
0x180473aa7  mov     rcx, [r15+60h]; hWnd
0x180473aab  mov     rdx, rsi; uIDEvent
0x180473aae  call    cs:__imp_KillTimer
0x180473ab5  nop     dword ptr [rax+rax+00h]
0x180473aba  mov     [r14+11h], r12b
0x180473abe  mov     rcx, [rdi+0E8h]
0x180473ac5  cmp     [rcx+88h], r12
0x180473acc  jz      loc_1804740C1
0x180473ad2  call    cs:__imp_GetTickCount
0x180473ad9  nop     dword ptr [rax+rax+00h]
0x180473ade  mov     r8, [rdi+0E8h]
0x180473ae5  mov     ebx, eax
0x180473ae7  mov     rcx, [r8+60h]; hWnd
0x180473aeb  test    rcx, rcx
0x180473aee  jz      short loc_180473B05
0x180473af0  mov     edx, eax
0x180473af2  sub     edx, [r8+148h]
0x180473af9  cmp     edx, 1388h
0x180473aff  ja      loc_180473FD0
0x180473b05  mov     rbx, [rdi+0E8h]
0x180473b0c  cmp     [rbx+3Ch], r12d
0x180473b10  jz      loc_180473BEF
0x180473b16  cmp     dword ptr [rbx+3Ch], 2
0x180473b1a  jnz     loc_180473BDB
0x180473b20  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180473b24  mov     qword ptr [rbp+57h+PerformanceCount], r13
0x180473b28  call    cs:__imp_QueryPerformanceCounter
0x180473b2f  nop     dword ptr [rax+rax+00h]
0x180473b34  mov     r9, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x180473b3b  test    r9, r9
0x180473b3e  jz      loc_1804740CB
0x180473b44  mov     rsi, qword ptr [rbp+57h+PerformanceCount]
0x180473b48  test    rsi, rsi
0x180473b4b  jz      short loc_180473B86
0x180473b4d  test    r9, r9
0x180473b50  jz      short loc_180473B86
0x180473b52  cmp     r9, 0F4240h
0x180473b59  jz      short loc_180473B86
0x180473b5b  xor     edx, edx
0x180473b5d  mov     rax, rsi
0x180473b60  div     r9
0x180473b63  xor     edx, edx
0x180473b65  mov     rcx, rax
0x180473b68  mov     r8, rax
0x180473b6b  imul    rcx, r9
0x180473b6f  sub     rsi, rcx
0x180473b72  imul    rax, rsi, 0F4240h
0x180473b79  imul    rsi, r8, 0F4240h
0x180473b80  div     r9
0x180473b83  add     rsi, rax
0x180473b86  mov     eax, [rbx+20h]
0x180473b89  mov     r8, rsi
0x180473b8c  add     eax, [rbx+10h]
0x180473b8f  sub     r8, [rbx+18h]
0x180473b93  imul    rcx, rax, 3E8h
0x180473b9a  mov     rax, 624DD2F1A9FBE77h
0x180473ba4  mul     r8
0x180473ba7  mov     rax, rcx
0x180473baa  mov     ecx, 0FFFFFFFFh
0x180473baf  sub     r8, rdx
0x180473bb2  shr     r8, 1
0x180473bb5  add     r8, rdx
0x180473bb8  xor     edx, edx
0x180473bba  shr     r8, 9
0x180473bbe  div     r8
0x180473bc1  cmp     rax, rcx
0x180473bc4  cmovb   rcx, rax
0x180473bc8  cmp     [rbx+38h], r12b
0x180473bcc  jnz     loc_1804741C7
0x180473bd2  cmp     ecx, [rbx+40h]
0x180473bd5  jnb     loc_18047415B
0x180473bdb  cmp     [rbx+38h], r12b
0x180473bdf  jnz     loc_180474206
0x180473be5  cmp     dword ptr [rbx+3Ch], 1
0x180473be9  jz      loc_180474206
0x180473bef  call    cs:__imp_GetTickCount64
0x180473bf6  nop     dword ptr [rax+rax+00h]
0x180473bfb  mov     rbx, [rdi+0E8h]
0x180473c02  mov     r15d, r12d
0x180473c05  mov     [rbp+57h+var_B0], rax
0x180473c09  mov     rcx, [rbx+88h]
0x180473c10  mov     r13d, [rcx+4]
0x180473c14  lea     rcx, qword_1813F3260
0x180473c1b  test    r13d, r13d
0x180473c1e  jle     loc_180473E60
0x180473c24  mov     rbx, [rdi+0E8h]
0x180473c2b  mov     r14, [rbx+88h]
0x180473c32  cmp     r15d, [r14+4]
0x180473c36  jge     loc_180473E60
0x180473c3c  mov     r14, [r14+8]
0x180473c40  mov     eax, [rbp+57h+var_B4]
0x180473c43  movsxd  rsi, r15d
0x180473c46  shl     rsi, 6
0x180473c4a  cmp     [rsi+r14+24h], eax
0x180473c4f  ja      loc_180473E60
0x180473c55  mov     r12, [rsi+r14]
0x180473c59  xor     r8d, r8d
0x180473c5c  test    r12, r12
0x180473c5f  jz      loc_180474287
0x180473c65  test    byte ptr [rsi+r14+20h], 2
0x180473c6b  jz      loc_18047427F
0x180473c71  mov     rax, [rsi+r14+8]
0x180473c76  xor     edx, edx
0x180473c78  movups  xmm7, xmmword ptr [rsi+r14+28h]
0x180473c7e  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x180473c82  mov     rax, [rsi+r14+10h]
0x180473c87  mov     [rbp+57h+var_C0], rax
0x180473c8b  movsxd  rax, dword ptr [rbx+98h]
0x180473c92  mov     ecx, [rcx+rax*4]
0x180473c95  mov     rax, r12
0x180473c98  div     rcx
0x180473c9b  mov     rax, [rbx+90h]
0x180473ca2  mov     ecx, edx
0x180473ca4  lea     rdx, [rax+rcx*4]
0x180473ca8  jmp     short loc_180473CB8
0x180473caa  movsxd  rdx, eax
0x180473cad  shl     rdx, 6
0x180473cb1  add     rdx, 38h ; '8'
0x180473cb5  add     rdx, r14
0x180473cb8  mov     eax, [rdx]
0x180473cba  cmp     eax, r15d
0x180473cbd  jnz     short loc_180473CAA
0x180473cbf  mov     eax, [rsi+r14+38h]
0x180473cc4  mov     [rsi+r14], r8
0x180473cc8  mov     [rsi+r14+10h], r8
0x180473ccd  mov     [rsi+r14+18h], r8
0x180473cd2  mov     [rsi+r14+20h], r8d
0x180473cd7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180473cde  movdqu  xmmword ptr [rsi+r14+28h], xmm0
0x180473ce5  mov     [rdx], eax
0x180473ce7  mov     dword ptr [rsi+r14+38h], 0FFFFFFFFh
0x180473cf0  mov     rcx, [rdi+0E8h]
0x180473cf7  mov     esi, [rcx+128h]
0x180473cfd  add     rcx, 0C0h; lpCriticalSection
0x180473d04  call    cs:__imp_LeaveCriticalSection
0x180473d0b  nop     dword ptr [rax+rax+00h]
0x180473d10  xor     ebx, ebx
0x180473d12  cmp     [rdi+204h], ebx
0x180473d18  jle     short loc_180473D48
0x180473d1a  mov     rax, [rdi+208h]
0x180473d21  movsxd  rcx, ebx
0x180473d24  mov     rcx, [rax+rcx*8]
0x180473d28  mov     rcx, [rcx+1560h]
0x180473d2f  mov     rax, [rcx]
0x180473d32  mov     rax, [rax+90h]
0x180473d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180473d3e  inc     ebx
0x180473d40  cmp     ebx, [rdi+204h]
0x180473d46  jl      short loc_180473D1A
0x180473d48  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180473d4f  nop     dword ptr [rax+rax+00h]
0x180473d54  movups  xmm6, xmmword ptr [rax]
0x180473d57  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180473d5e  nop     dword ptr [rax+rax+00h]
0x180473d63  mov     bl, [rax+10h]
0x180473d66  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180473d6d  nop     dword ptr [rax+rax+00h]
0x180473d72  movdqu  xmmword ptr [rax], xmm7
0x180473d76  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180473d7d  nop     dword ptr [rax+rax+00h]
0x180473d82  mov     rdx, [rbp+57h+var_C0]
0x180473d86  mov     rcx, r12
0x180473d89  mov     byte ptr [rax+10h], 1
0x180473d8d  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x180473d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180473d96  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180473d9d  nop     dword ptr [rax+rax+00h]
0x180473da2  movdqu  xmmword ptr [rax], xmm6
0x180473da6  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180473dad  nop     dword ptr [rax+rax+00h]
0x180473db2  xor     r12d, r12d
0x180473db5  mov     [rax+10h], bl
0x180473db8  mov     rax, [rdi+0E8h]
0x180473dbf  cmp     [rax+7Ah], r12w
0x180473dc4  jnz     short loc_180473DFB
0x180473dc6  mov     ebx, r12d
0x180473dc9  cmp     [rdi+204h], r12d
0x180473dd0  jle     short loc_180473DFB
0x180473dd2  mov     rax, [rdi+208h]
0x180473dd9  movsxd  rcx, ebx
0x180473ddc  mov     rcx, [rax+rcx*8]
0x180473de0  add     rcx, 1B10h; this
0x180473de7  cmp     [rcx+4], r12d
0x180473deb  jg      loc_1804740AF
0x180473df1  inc     ebx
0x180473df3  cmp     ebx, [rdi+204h]
0x180473df9  jl      short loc_180473DD2
0x180473dfb  mov     rcx, [rdi+0E8h]
0x180473e02  add     rcx, 0C0h; lpCriticalSection
0x180473e09  call    cs:__imp_EnterCriticalSection
0x180473e10  nop     dword ptr [rax+rax+00h]
0x180473e15  mov     rbx, [rdi+0E8h]
0x180473e1c  cmp     [rbx+88h], r12
0x180473e23  jz      loc_180474080
0x180473e29  xor     esi, [rbx+128h]
0x180473e2f  dec     r13d
0x180473e32  test    esi, 0FFF00000h
0x180473e38  mov     eax, r12d
0x180473e3b  cmovz   eax, r15d
0x180473e3f  mov     r15d, eax
0x180473e42  lea     rcx, qword_1813F3260
0x180473e49  inc     r15d
0x180473e4c  jmp     loc_180473C1B
0x180473e51  sub     eax, r11d
0x180473e54  add     ebx, r11d
0x180473e57  add     rsi, 38h ; '8'
0x180473e5b  jmp     loc_180473A3C
0x180473e60  call    cs:__imp_GetTickCount64
0x180473e67  nop     dword ptr [rax+rax+00h]
0x180473e6c  sub     eax, dword ptr [rbp+57h+var_B0]
0x180473e6f  add     [rbx+13Ch], eax
0x180473e75  inc     dword ptr [rbx+138h]
0x180473e7b  mov     rbx, [rdi+0E8h]
0x180473e82  cmp     [rbx+142h], r12b
  ... truncated ...
```
