# GlobalWndOnMethodCall(void)

- ea: `0x1804744f8`
- end: `0x180474d5b`
- name: `?GlobalWndOnMethodCall@@YAXXZ`
- size: `2147`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x180472e5c`

## callees

- `0x1803e817c`
- `0x180474378`
- `0x1804744f8`
- `0x180574704`
- `0x180626e88`
- `0x180b68094`
- `0x180b681b0`
- `0x181104010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1804745e4`
- `KERNEL32!QueryPerformanceCounter` at `0x1804745e4`
- `KERNEL32!QueryPerformanceFrequency` at `0x180474b94`
- `KERNEL32!QueryPerformanceFrequency` at `0x180474b94`
- `KERNEL32!LeaveCriticalSection` at `0x1804747ce`
- `KERNEL32!LeaveCriticalSection` at `0x1804749ff`
- `KERNEL32!LeaveCriticalSection` at `0x1804747ce`
- `KERNEL32!LeaveCriticalSection` at `0x1804749ff`
- `KERNEL32!LeaveCriticalSection` at `0x180474a66`
- `KERNEL32!EnterCriticalSection` at `0x180474548`
- `KERNEL32!EnterCriticalSection` at `0x1804748d5`
- `KERNEL32!EnterCriticalSection` at `0x180474977`
- `KERNEL32!EnterCriticalSection` at `0x180474548`
- `KERNEL32!EnterCriticalSection` at `0x1804748d5`
- `KERNEL32!EnterCriticalSection` at `0x180474977`
- `USER32!PostMessageW` at `0x180474d2d`
- `USER32!PostMessageW` at `0x180474d2d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474815`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474824`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474833`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474843`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474863`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474873`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474815`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474824`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474833`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474843`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474863`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180474873`
- `bcrypt!BCryptGenRandom` at `0x180474cc6`
- `bcrypt!BCryptGenRandom` at `0x180474cc6`

## pseudocode

```c
void GlobalWndOnMethodCall(void)
{
  __int64 v0; // rsi
  __int64 v1; // r9
  int v2; // ecx
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rdx
  int v6; // ecx
  int v7; // r15d
  LARGE_INTEGER v8; // r8
  LARGE_INTEGER v9; // rdi
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rcx
  int i; // r14d
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // r12
  unsigned int v18; // edx
  __int128 v19; // xmm7
  unsigned int v20; // r13d
  __int64 v21; // r9
  int *v22; // r8
  int j; // edx
  int v24; // eax
  int k; // ebx
  __int64 v26; // rcx
  __int128 v27; // xmm6
  char v28; // bl
  struct IE_GLOBAL_THREAD_STATE *v29; // rax
  unsigned __int64 v30; // rdx
  __int64 v31; // rdx
  void *v32; // r8
  int m; // ebx
  __int64 v34; // rax
  __int64 v35; // rcx
  int v36; // r14d
  __int64 v37; // rbx
  __int64 v38; // rbx
  struct _RTL_CRITICAL_SECTION *v39; // r15
  __int64 v40; // rax
  int v41; // edi
  _OWORD *v42; // r10
  int v43; // r11d
  __int64 v44; // r9
  __int64 v45; // rcx
  int *v46; // rdx
  int n; // ecx
  void (__fastcall *v48)(__int64, __int64, __int64 *); // rax
  __int64 v49; // rcx
  unsigned int v50; // r8d
  unsigned int v51; // r10d
  __int64 v52; // rdx
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  unsigned __int64 v56; // rbx
  __int64 v57; // rcx
  UCHAR pbBuffer[2]; // [rsp+28h] [rbp-69h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-61h] BYREF
  unsigned __int64 v60; // [rsp+38h] [rbp-59h] BYREF
  __int64 v61; // [rsp+40h] [rbp-51h]

  v61 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v0 = *(_QWORD *)(v61 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v0 + 232) + 192LL));
  ++*(_WORD *)(*(_QWORD *)(v0 + 232) + 122LL);
  v1 = *(_QWORD *)(v0 + 232);
  v2 = *(_DWORD *)(v1 + 128);
  *(_DWORD *)(v1 + 128) = v2 + 1;
  if ( !v2 )
  {
    v50 = 0;
    v51 = *(_DWORD *)(*(_QWORD *)(v1 + 136) + 4LL);
    if ( v51 )
    {
      do
      {
        v52 = v50++;
        *(_DWORD *)((v52 << 6) + *(_QWORD *)(*(_QWORD *)(v1 + 136) + 8LL) + 36) = 0;
      }
      while ( v50 < v51 );
    }
  }
  v3 = *(_QWORD *)(v0 + 232);
  v4 = *(_QWORD *)(v3 + 136);
  if ( v4 )
  {
    v5 = 0xFFFFFFFFLL;
    if ( (byte_1815BFC72 & 2) != 0 )
    {
      v7 = 1;
    }
    else
    {
      v6 = *(_DWORD *)(v4 + 4);
      v7 = -1;
      if ( v6 >= 0 && v6 + 1000 >= (unsigned int)v6 )
        v7 = v6 + 1000;
    }
    if ( *(_DWORD *)(v3 + 60) )
    {
      if ( *(_DWORD *)(v3 + 60) == 2 )
      {
        PerformanceCount.QuadPart = 0;
        QueryPerformanceCounter(&PerformanceCount);
        v8 = CQPCTick::s_qpcFrequency;
        if ( CQPCTick::s_qpcFrequency.QuadPart
          || (QueryPerformanceFrequency(&CQPCTick::s_qpcFrequency),
              v8 = CQPCTick::s_qpcFrequency,
              CQPCTick::s_qpcFrequency.QuadPart) )
        {
          v9 = PerformanceCount;
          if ( PerformanceCount.QuadPart && v8.QuadPart && v8.QuadPart != 1000000 )
            v9.QuadPart = 1000000 * (PerformanceCount.QuadPart % (unsigned __int64)v8.QuadPart) / v8.QuadPart
                        + 1000000 * (PerformanceCount.QuadPart / (unsigned __int64)v8.QuadPart);
        }
        else
        {
          v9.QuadPart = 0;
        }
        v10 = (v9.QuadPart - *(_QWORD *)(v3 + 24)) / 0x3E8uLL;
        v5 = 0xFFFFFFFFLL;
        LODWORD(v11) = -1;
        if ( 1000 * (unsigned __int64)(unsigned int)(*(_DWORD *)(v3 + 16) + *(_DWORD *)(v3 + 32)) / v10 < 0xFFFFFFFF )
          v11 = 1000 * (unsigned __int64)(unsigned int)(*(_DWORD *)(v3 + 16) + *(_DWORD *)(v3 + 32)) / v10;
        if ( *(_BYTE *)(v3 + 56) )
        {
          v55 = *(_DWORD *)(v3 + 52);
          if ( v55 < *(_DWORD *)(v3 + 68) || (unsigned int)v11 >= *(_DWORD *)(v3 + 64) )
          {
            v60 = 0;
            CQPCTick::GetCurrentTimeInUs((LARGE_INTEGER *)&v60);
            CallRate::MarkCall((CallRate *)(v3 + 8), v60);
          }
          else
          {
            *(_BYTE *)(v3 + 56) = 0;
            CallRateManager::LogPauseTaskDisabled((CallRateManager *)v3, v55);
          }
        }
        else if ( (unsigned int)v11 >= *(_DWORD *)(v3 + 64) )
        {
          *(_BYTE *)(v3 + 56) = 1;
          CallRateManager::LogPauseTaskEnabled((CallRateManager *)v3, v11);
          if ( v9.QuadPart - *(_QWORD *)(v3 + 88) > *(_QWORD *)(v3 + 72) )
          {
            *(_DWORD *)(v3 + 80) = 2000;
            *(_DWORD *)(v3 + 84) = 1;
          }
          else
          {
            v53 = *(_DWORD *)(v3 + 80);
            if ( v53 < 0x4E20 )
            {
              *(_DWORD *)(v3 + 80) = v53 + 1000;
              v54 = *(_DWORD *)(v3 + 84);
              if ( v54 < 0xF )
                *(_DWORD *)(v3 + 84) = v54 + 1;
            }
          }
          *(LARGE_INTEGER *)(v3 + 88) = v9;
          _InterlockedExchange64(
            (volatile __int64 *)StaticFrequency::GetInstance() + 5,
            COERCE__INT64((double)*(int *)(v3 + 84)));
        }
      }
      if ( *(_BYTE *)(v3 + 56) || *(_DWORD *)(v3 + 60) == 1 )
      {
        v60 = 0;
        CQPCTick::GetCurrentTimeInUs((LARGE_INTEGER *)&v60);
        *(_WORD *)pbBuffer = 0;
        BCryptGenRandom(0, pbBuffer, 2u, 2u);
        v56 = (unsigned int)((int)(float)((float)((float)*(unsigned __int16 *)pbBuffer / 65535.0)
                                        * (float)*(int *)(v3 + 80))
                           + 1000);
        do
        {
          PerformanceCount.QuadPart = 0;
          CQPCTick::GetCurrentTimeInUs(&PerformanceCount);
        }
        while ( PerformanceCount.QuadPart - v60 <= v56 );
      }
    }
    for ( i = 0; v7; ++i )
    {
      v13 = *(_QWORD *)(v0 + 232);
      v14 = *(_QWORD *)(v13 + 136);
      if ( i >= *(_DWORD *)(v14 + 4) )
        break;
      v15 = *(_QWORD *)(v14 + 8);
      v16 = (__int64)i << 6;
      v17 = *(_QWORD *)(v16 + v15);
      if ( v17 )
      {
        if ( (*(_BYTE *)(v16 + v15 + 32) & 2) == 0 )
        {
          v18 = *(_DWORD *)(v13 + 296);
          v19 = *(_OWORD *)(v16 + v15 + 40);
          PerformanceCount = *(LARGE_INTEGER *)(v16 + v15 + 8);
          v60 = *(_QWORD *)(v16 + v15 + 16);
          v20 = v18 >> 20;
          if ( *(_WORD *)(v13 + 122) == 1 )
          {
            *(_OWORD *)(v13 + 232) = *(_OWORD *)(v16 + v15);
            *(_OWORD *)(v13 + 248) = *(_OWORD *)(v16 + v15 + 16);
            *(_OWORD *)(v13 + 264) = *(_OWORD *)(v16 + v15 + 32);
            *(_OWORD *)(v13 + 280) = *(_OWORD *)(v16 + v15 + 48);
          }
          else
          {
            *(_DWORD *)(v13 + 296) = v18 ^ (v18 ^ (v18 + 1)) & 0xFFFFF;
          }
          v21 = *(_QWORD *)(v0 + 232);
          v22 = (int *)(*(_QWORD *)(v21 + 144)
                      + 4
                      * (*(_QWORD *)(v16 + v15)
                       % (unsigned __int64)*((unsigned int *)qword_1813F3260 + *(int *)(v21 + 152))));
          for ( j = *v22; *v22 != i; j = *v22 )
            v22 = (int *)(*(_QWORD *)(*(_QWORD *)(v21 + 136) + 8LL) + 56LL + ((__int64)j << 6));
          v24 = *(_DWORD *)(v16 + v15 + 56);
          *(_QWORD *)(v16 + v15) = 0;
          *(_QWORD *)(v16 + v15 + 16) = 0;
          *(_QWORD *)(v16 + v15 + 24) = 0;
          *(_DWORD *)(v16 + v15 + 32) = 0;
          *(GUID *)(v16 + v15 + 40) = GUID_NULL;
          *v22 = v24;
          *(_DWORD *)(v16 + v15 + 56) = -1;
          LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v0 + 232) + 192LL));
          for ( k = 0; k < *(_DWORD *)(v0 + 516); ++k )
          {
            v26 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v0 + 520) + 8LL * k) + 5472LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 144LL))(v26);
          }
          v27 = *(_OWORD *)GlobalThreadState();
          v28 = *((_BYTE *)GlobalThreadState() + 16);
          *(_OWORD *)GlobalThreadState() = v19;
          v29 = GlobalThreadState();
          v30 = v60;
          *((_BYTE *)v29 + 16) = 1;
          ((void (__fastcall *)(__int64, unsigned __int64))PerformanceCount.QuadPart)(v17, v30);
          *(_OWORD *)GlobalThreadState() = v27;
          *((_BYTE *)GlobalThreadState() + 16) = v28;
          if ( *(_WORD *)(*(_QWORD *)(v0 + 232) + 122LL) == 1 )
          {
            for ( m = 0; m < *(_DWORD *)(v0 + 516); ++m )
            {
              v34 = *(_QWORD *)(v0 + 520);
              if ( *(int *)(*(_QWORD *)(v34 + 8LL * m) + 6932LL) > 0 )
                CObserverManager::InvokeObserversForCheckpoint(
                  (CObserverManager *)(*(_QWORD *)(v34 + 8LL * m) + 6928LL),
                  v31,
                  v32);
            }
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v0 + 232) + 192LL));
          v35 = *(_QWORD *)(v0 + 232);
          if ( *(_DWORD *)(v35 + 296) >> 20 != v20 )
            i = -1;
          if ( !*(_QWORD *)(v35 + 136) )
          {
            *(_WORD *)(v35 + 120) = 0;
            goto LABEL_53;
          }
          --v7;
        }
      }
      else
      {
        v48 = *(void (__fastcall **)(__int64, __int64, __int64 *))(v16 + v15 + 24);
        if ( v48 )
        {
          v49 = *(_QWORD *)(v16 + v15 + 16);
          if ( v49 )
          {
            v48(v49, v5, qword_1813F3260);
            *(_QWORD *)(v16 + v15 + 24) = 0;
            *(_QWORD *)(v16 + v15 + 16) = 0;
          }
        }
      }
    }
    v36 = 0;
    v37 = *(_QWORD *)(v61 + 16);
    if ( v37 )
      v38 = *(_QWORD *)(v37 + 232);
    else
      v38 = 0;
    v39 = (struct _RTL_CRITICAL_SECTION *)(v38 + 192);
    EnterCriticalSection((LPCRITICAL_SECTION)(v38 + 192));
    v40 = *(_QWORD *)(v38 + 136);
    v41 = 0;
    if ( *(int *)(v40 + 4) > 0 )
    {
      v42 = *(_OWORD **)(v40 + 8);
      v43 = 0;
      do
      {
        v44 = *(_QWORD *)(v40 + 8) + ((__int64)v43 << 6);
        if ( *(_QWORD *)v44 || *(_QWORD *)(v44 + 24) && *(_QWORD *)(v44 + 16) )
        {
          if ( v42 != (_OWORD *)v44 )
          {
            *v42 = *(_OWORD *)v44;
            v42[1] = *(_OWORD *)(v44 + 16);
            v42[2] = *(_OWORD *)(v44 + 32);
            v42[3] = *(_OWORD *)(v44 + 48);
            if ( *(_QWORD *)v44 )
            {
              v46 = (int *)(*(_QWORD *)(v38 + 144)
                          + 4
                          * (*(_QWORD *)v44 % (unsigned __int64)*((unsigned int *)qword_1813F3260 + *(int *)(v38 + 152))));
              for ( n = *v46; *v46 != v43; n = *v46 )
                v46 = (int *)(*(_QWORD *)(*(_QWORD *)(v38 + 136) + 8LL) + 56LL + ((__int64)n << 6));
              *v46 = v41;
            }
          }
          v42 += 4;
          ++v41;
          if ( (*(_BYTE *)(v44 + 32) & 2) == 0 )
            ++v36;
        }
        v40 = *(_QWORD *)(v38 + 136);
        ++v43;
      }
      while ( v43 < *(_DWORD *)(v40 + 4) );
      v39 = (struct _RTL_CRITICAL_SECTION *)(v38 + 192);
    }
    *(_DWORD *)(v40 + 4) = v41;
    *(_DWORD *)(v38 + 296) = (*(_DWORD *)(v38 + 296) + 0x100000)
                           ^ (*(_DWORD *)(v38 + 296)
                            ^ (*(_DWORD *)(v38 + 296) + 0x100000))
                           & 0xFFFFF;
    LeaveCriticalSection(v39);
    v45 = *(_QWORD *)(v0 + 232);
    if ( v36 )
    {
      PostMessageW(*(HWND *)(v45 + 96), 0x8002u, 0, 0);
      v57 = *(_QWORD *)(v0 + 232);
      if ( !*(_WORD *)(v57 + 120) )
        ++*(_WORD *)(v57 + 120);
    }
    else if ( *(_WORD *)(v45 + 120) )
    {
      --*(_WORD *)(v45 + 120);
    }
  }
  else
  {
    *(_WORD *)(v3 + 120) = 0;
  }
LABEL_53:
  --*(_WORD *)(*(_QWORD *)(v0 + 232) + 122LL);
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v0 + 232) + 192LL));
}

```

## disassembly

```asm
0x1804744f8  mov     rax, rsp
0x1804744fb  push    rbp
0x1804744fc  push    rbx
0x1804744fd  push    rsi
0x1804744fe  push    rdi
0x1804744ff  push    r12
0x180474501  push    r13
0x180474503  push    r14
0x180474505  push    r15
0x180474507  lea     rbp, [rax-5Fh]
0x18047450b  sub     rsp, 0A8h
0x180474512  mov     ecx, cs:_tls_index
0x180474518  movaps  xmmword ptr [rax-58h], xmm6
0x18047451c  movaps  xmmword ptr [rax-68h], xmm7
0x180474520  mov     rax, gs:58h
0x180474529  mov     edx, 10h
0x18047452e  mov     r12, [rax+rcx*8]
0x180474532  mov     [rbp+57h+var_A8], r12
0x180474536  mov     rsi, [r12+rdx]
0x18047453a  mov     rcx, [rsi+0E8h]
0x180474541  add     rcx, 0C0h; lpCriticalSection
0x180474548  call    cs:__imp_EnterCriticalSection
0x18047454f  nop     dword ptr [rax+rax+00h]
0x180474554  mov     rax, [rsi+0E8h]
0x18047455b  mov     r13d, 1
0x180474561  xor     r12d, r12d
0x180474564  add     [rax+7Ah], r13w
0x180474569  mov     r9, [rsi+0E8h]
0x180474570  mov     ecx, [r9+80h]
0x180474577  lea     eax, [rcx+1]
0x18047457a  mov     [r9+80h], eax
0x180474581  test    ecx, ecx
0x180474583  jz      loc_180474BC2
0x180474589  mov     rbx, [rsi+0E8h]
0x180474590  mov     rcx, [rbx+88h]
0x180474597  test    rcx, rcx
0x18047459a  jz      loc_180474BB8
0x1804745a0  test    cs:byte_1815BFC72, 2
0x1804745a7  mov     edx, 0FFFFFFFFh
0x1804745ac  jnz     loc_180474B37
0x1804745b2  mov     ecx, [rcx+4]
0x1804745b5  mov     r15d, edx
0x1804745b8  test    ecx, ecx
0x1804745ba  js      short loc_1804745C8
0x1804745bc  lea     eax, [rcx+3E8h]
0x1804745c2  cmp     eax, ecx
0x1804745c4  cmovnb  r15d, eax
0x1804745c8  cmp     [rbx+3Ch], r12d
0x1804745cc  jz      loc_1804746AA
0x1804745d2  cmp     dword ptr [rbx+3Ch], 2
0x1804745d6  jnz     loc_180474696
0x1804745dc  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1804745e0  mov     qword ptr [rbp+57h+PerformanceCount], r12
0x1804745e4  call    cs:__imp_QueryPerformanceCounter
0x1804745eb  nop     dword ptr [rax+rax+00h]
0x1804745f0  mov     r8, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x1804745f7  test    r8, r8
0x1804745fa  jz      loc_180474B8D
0x180474600  mov     rdi, qword ptr [rbp+57h+PerformanceCount]
0x180474604  test    rdi, rdi
0x180474607  jz      short loc_18047463F
0x180474609  test    r8, r8
0x18047460c  jz      short loc_18047463F
0x18047460e  cmp     r8, 0F4240h
0x180474615  jz      short loc_18047463F
0x180474617  xor     edx, edx
0x180474619  mov     rax, rdi
0x18047461c  div     r8
0x18047461f  xor     edx, edx
0x180474621  mov     rcx, rax
0x180474624  imul    rax, r8
0x180474628  sub     rdi, rax
0x18047462b  imul    rax, rdi, 0F4240h
0x180474632  imul    rdi, rcx, 0F4240h
0x180474639  div     r8
0x18047463c  add     rdi, rax
0x18047463f  mov     eax, [rbx+20h]
0x180474642  mov     r8, rdi
0x180474645  add     eax, [rbx+10h]
0x180474648  sub     r8, [rbx+18h]
0x18047464c  imul    rcx, rax, 3E8h
0x180474653  mov     rax, 624DD2F1A9FBE77h
0x18047465d  mul     r8
0x180474660  mov     rax, rcx
0x180474663  sub     r8, rdx
0x180474666  shr     r8, 1
0x180474669  add     r8, rdx
0x18047466c  xor     edx, edx
0x18047466e  shr     r8, 9
0x180474672  div     r8
0x180474675  mov     edx, 0FFFFFFFFh
0x18047467a  cmp     rax, rdx
0x18047467d  mov     ecx, edx
0x18047467f  cmovb   rcx, rax
0x180474683  cmp     [rbx+38h], r12b
0x180474687  jnz     loc_180474C66
0x18047468d  cmp     ecx, [rbx+40h]
0x180474690  jnb     loc_180474BFD
0x180474696  cmp     [rbx+38h], r12b
0x18047469a  jnz     loc_180474CA5
0x1804746a0  cmp     [rbx+3Ch], r13d
0x1804746a4  jz      loc_180474CA5
0x1804746aa  mov     r14d, r12d
0x1804746ad  lea     r8, qword_1813F3260
0x1804746b4  or      r11d, 0FFFFFFFFh
0x1804746b8  test    r15d, r15d
0x1804746bb  jz      loc_18047494D
0x1804746c1  mov     rcx, [rsi+0E8h]
0x1804746c8  mov     rdi, [rcx+88h]
0x1804746cf  cmp     r14d, [rdi+4]
0x1804746d3  jge     loc_18047494D
0x1804746d9  mov     rdi, [rdi+8]
0x1804746dd  xor     r10d, r10d
0x1804746e0  movsxd  rbx, r14d
0x1804746e3  shl     rbx, 6
0x1804746e7  mov     r12, [rbx+rdi]
0x1804746eb  test    r12, r12
0x1804746ee  jz      loc_180474B56
0x1804746f4  test    byte ptr [rbx+rdi+20h], 2
0x1804746f9  jnz     loc_180474B2F
0x1804746ff  mov     rax, [rbx+rdi+8]
0x180474704  mov     edx, [rcx+128h]
0x18047470a  mov     r13d, edx
0x18047470d  movups  xmm7, xmmword ptr [rbx+rdi+28h]
0x180474712  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x180474716  mov     rax, [rbx+rdi+10h]
0x18047471b  mov     [rbp+57h+var_B0], rax
0x18047471f  lea     eax, [r10+1]
0x180474723  shr     r13d, 14h
0x180474727  cmp     [rcx+7Ah], ax
0x18047472b  jnz     loc_180474B3F
0x180474731  movups  xmm0, xmmword ptr [rbx+rdi]
0x180474735  movups  xmmword ptr [rcx+0E8h], xmm0
0x18047473c  movups  xmm1, xmmword ptr [rbx+rdi+10h]
0x180474741  movups  xmmword ptr [rcx+0F8h], xmm1
0x180474748  movups  xmm0, xmmword ptr [rbx+rdi+20h]
0x18047474d  movups  xmmword ptr [rcx+108h], xmm0
0x180474754  movups  xmm1, xmmword ptr [rbx+rdi+30h]
0x180474759  movups  xmmword ptr [rcx+118h], xmm1
0x180474760  mov     r9, [rsi+0E8h]
0x180474767  xor     edx, edx
0x180474769  movsxd  rax, dword ptr [r9+98h]
0x180474770  mov     ecx, [r8+rax*4]
0x180474774  mov     rax, [rbx+rdi]
0x180474778  div     rcx
0x18047477b  mov     rax, [r9+90h]
0x180474782  mov     ecx, edx
0x180474784  lea     r8, [rax+rcx*4]
0x180474788  mov     edx, [r8]
0x18047478b  cmp     edx, r14d
0x18047478e  jnz     loc_180474926
0x180474794  mov     eax, [rbx+rdi+38h]
0x180474798  mov     [rbx+rdi], r10
0x18047479c  mov     [rbx+rdi+10h], r10
0x1804747a1  mov     [rbx+rdi+18h], r10
0x1804747a6  mov     [rbx+rdi+20h], r10d
0x1804747ab  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1804747b2  movdqu  xmmword ptr [rbx+rdi+28h], xmm0
0x1804747b8  mov     [r8], eax
0x1804747bb  mov     [rbx+rdi+38h], r11d
0x1804747c0  mov     rcx, [rsi+0E8h]
0x1804747c7  add     rcx, 0C0h; lpCriticalSection
0x1804747ce  call    cs:__imp_LeaveCriticalSection
0x1804747d5  nop     dword ptr [rax+rax+00h]
0x1804747da  xor     ebx, ebx
0x1804747dc  lea     edi, [rbx+1]
0x1804747df  cmp     [rsi+204h], ebx
0x1804747e5  jle     short loc_180474815
0x1804747e7  mov     rax, [rsi+208h]
0x1804747ee  movsxd  rcx, ebx
0x1804747f1  mov     rcx, [rax+rcx*8]
0x1804747f5  mov     rcx, [rcx+1560h]
0x1804747fc  mov     rax, [rcx]
0x1804747ff  mov     rax, [rax+90h]
0x180474806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047480b  add     ebx, edi
0x18047480d  cmp     ebx, [rsi+204h]
0x180474813  jl      short loc_1804747E7
0x180474815  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18047481c  nop     dword ptr [rax+rax+00h]
0x180474821  movups  xmm6, xmmword ptr [rax]
0x180474824  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18047482b  nop     dword ptr [rax+rax+00h]
0x180474830  mov     bl, [rax+10h]
0x180474833  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18047483a  nop     dword ptr [rax+rax+00h]
0x18047483f  movdqu  xmmword ptr [rax], xmm7
0x180474843  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18047484a  nop     dword ptr [rax+rax+00h]
0x18047484f  mov     rdx, [rbp+57h+var_B0]
0x180474853  mov     rcx, r12
0x180474856  mov     [rax+10h], dil
0x18047485a  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x18047485e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180474863  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18047486a  nop     dword ptr [rax+rax+00h]
0x18047486f  movdqu  xmmword ptr [rax], xmm6
0x180474873  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18047487a  nop     dword ptr [rax+rax+00h]
0x18047487f  xor     r12d, r12d
0x180474882  mov     [rax+10h], bl
0x180474885  mov     rax, [rsi+0E8h]
0x18047488c  cmp     [rax+7Ah], di
0x180474890  jnz     short loc_1804748C7
0x180474892  mov     ebx, r12d
0x180474895  cmp     [rsi+204h], r12d
0x18047489c  jle     short loc_1804748C7
0x18047489e  mov     rax, [rsi+208h]
0x1804748a5  movsxd  rcx, ebx
0x1804748a8  mov     rcx, [rax+rcx*8]
0x1804748ac  add     rcx, 1B10h; this
0x1804748b3  cmp     [rcx+4], r12d
0x1804748b7  jg      loc_180474B03
0x1804748bd  add     ebx, edi
0x1804748bf  cmp     ebx, [rsi+204h]
0x1804748c5  jl      short loc_18047489E
0x1804748c7  mov     rcx, [rsi+0E8h]
0x1804748ce  add     rcx, 0C0h; lpCriticalSection
0x1804748d5  call    cs:__imp_EnterCriticalSection
0x1804748dc  nop     dword ptr [rax+rax+00h]
0x1804748e1  mov     rcx, [rsi+0E8h]
0x1804748e8  mov     r11d, 0FFFFFFFFh
0x1804748ee  mov     eax, [rcx+128h]
0x1804748f4  shr     eax, 14h
0x1804748f7  cmp     eax, r13d
0x1804748fa  cmovnz  r14d, r11d
0x1804748fe  cmp     [rcx+88h], r12
0x180474905  jz      loc_180474A72
0x18047490b  mov     eax, 0FFFFFFFFh
0x180474910  lea     r13d, [r11+2]
0x180474914  add     r15d, eax
0x180474917  lea     r8, qword_1813F3260
0x18047491e  add     r14d, r13d
0x180474921  jmp     loc_1804746B8
0x180474926  mov     rax, [r9+88h]
0x18047492d  mov     rcx, [rax+8]
0x180474931  add     rcx, 38h ; '8'
0x180474935  movsxd  r8, edx
0x180474938  shl     r8, 6
0x18047493c  add     r8, rcx
0x18047493f  mov     edx, [r8]
0x180474942  cmp     edx, r14d
0x180474945  jz      loc_180474794
0x18047494b  jmp     short loc_180474935
0x18047494d  mov     rbx, [rbp+57h+var_A8]
0x180474951  mov     r14d, r12d
0x180474954  mov     eax, 10h
0x180474959  mov     rbx, [rbx+rax]
0x18047495d  test    rbx, rbx
0x180474960  jz      loc_180474AFB
0x180474966  mov     rbx, [rbx+0E8h]
0x18047496d  lea     r15, [rbx+0C0h]
0x180474974  mov     rcx, r15; lpCriticalSection
0x180474977  call    cs:__imp_EnterCriticalSection
0x18047497e  nop     dword ptr [rax+rax+00h]
0x180474983  mov     rax, [rbx+88h]
0x18047498a  mov     edi, r12d
0x18047498d  cmp     [rax+4], r12d
0x180474991  jle     short loc_1804749D6
0x180474993  mov     r10, [rax+8]
0x180474997  lea     r15, qword_1813F3260
0x18047499e  mov     r11d, r12d
0x1804749a1  movsxd  r9, r11d
0x1804749a4  shl     r9, 6
0x1804749a8  add     r9, [rax+8]
0x1804749ac  cmp     [r9], r12
0x1804749af  jnz     loc_180474A88
0x1804749b5  cmp     [r9+18h], r12
0x1804749b9  jnz     loc_180474A7E
0x1804749bf  mov     rax, [rbx+88h]
0x1804749c6  add     r11d, r13d
0x1804749c9  cmp     r11d, [rax+4]
0x1804749cd  jl      short loc_1804749A1
0x1804749cf  lea     r15, [rbx+0C0h]
0x1804749d6  mov     [rax+4], edi
0x1804749d9  mov     rcx, r15; lpCriticalSection
0x1804749dc  mov     eax, [rbx+128h]
0x1804749e2  lea     edx, [rax+100000h]
0x1804749e8  mov     r8d, edx
0x1804749eb  xor     r8d, eax
0x1804749ee  and     r8d, 0FFFFFh
0x1804749f5  xor     r8d, edx
0x1804749f8  mov     [rbx+128h], r8d
0x1804749ff  call    cs:__imp_LeaveCriticalSection
0x180474a06  nop     dword ptr [rax+rax+00h]
0x180474a0b  mov     rcx, [rsi+0E8h]
0x180474a12  test    r14d, r14d
0x180474a15  jnz     loc_180474D1E
0x180474a1b  movzx   eax, word ptr [rcx+78h]
0x180474a1f  test    eax, eax
0x180474a21  jz      short loc_180474A77
0x180474a23  mov     edx, 0FFFFh
0x180474a28  add     [rcx+78h], dx
0x180474a2c  mov     rax, [rsi+0E8h]
0x180474a33  add     [rax+7Ah], dx
0x180474a37  mov     rcx, [rsi+0E8h]
0x180474a3e  add     rcx, 0C0h
0x180474a45  lea     r11, [rsp+0E0h+var_38]
0x180474a4d  movaps  xmm6, xmmword ptr [r11-18h]
0x180474a52  movaps  xmm7, xmmword ptr [r11-28h]
  ... truncated ...
```
