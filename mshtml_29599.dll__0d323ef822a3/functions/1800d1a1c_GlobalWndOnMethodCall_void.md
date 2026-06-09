# GlobalWndOnMethodCall(void)

- ea: `0x1800d1a1c`
- end: `0x1800d2220`
- name: `?GlobalWndOnMethodCall@@YAXXZ`
- size: `2052`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x1800d04f4`

## callees

- `0x1800d18a4`
- `0x1800d1a1c`
- `0x18011d7c8`
- `0x18058a604`
- `0x18062a2c8`
- `0x180b4f148`
- `0x180b4f264`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800d1b02`
- `KERNEL32!QueryPerformanceCounter` at `0x1800d1b02`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800d206b`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800d206b`
- `KERNEL32!LeaveCriticalSection` at `0x1800d1ce6`
- `KERNEL32!LeaveCriticalSection` at `0x1800d1ee1`
- `KERNEL32!LeaveCriticalSection` at `0x1800d1ce6`
- `KERNEL32!LeaveCriticalSection` at `0x1800d1ee1`
- `KERNEL32!LeaveCriticalSection` at `0x1800d1f42`
- `KERNEL32!EnterCriticalSection` at `0x1800d1a6c`
- `KERNEL32!EnterCriticalSection` at `0x1800d1dc3`
- `KERNEL32!EnterCriticalSection` at `0x1800d1e5f`
- `KERNEL32!EnterCriticalSection` at `0x1800d1a6c`
- `KERNEL32!EnterCriticalSection` at `0x1800d1dc3`
- `KERNEL32!EnterCriticalSection` at `0x1800d1e5f`
- `USER32!PostMessageW` at `0x1800d21f8`
- `USER32!PostMessageW` at `0x1800d21f8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d27`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d30`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d39`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d43`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d5d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d67`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d27`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d30`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d39`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d43`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d5d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d1d67`
- `bcrypt!BCryptGenRandom` at `0x1800d2197`
- `bcrypt!BCryptGenRandom` at `0x1800d2197`

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
  int m; // ebx
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // r14d
  __int64 v35; // rbx
  __int64 v36; // rbx
  struct _RTL_CRITICAL_SECTION *v37; // r15
  __int64 v38; // rax
  int v39; // edi
  _OWORD *v40; // r10
  int v41; // r11d
  __int64 v42; // r9
  __int64 v43; // rcx
  int *v44; // rdx
  int n; // ecx
  void (__fastcall *v46)(__int64, __int64, unsigned int *); // rax
  __int64 v47; // rcx
  unsigned int v48; // r8d
  unsigned int v49; // r10d
  __int64 v50; // rdx
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned __int64 v54; // rbx
  __int64 v55; // rcx
  UCHAR pbBuffer[2]; // [rsp+28h] [rbp-69h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-61h] BYREF
  unsigned __int64 v58; // [rsp+38h] [rbp-59h] BYREF
  __int64 v59; // [rsp+40h] [rbp-51h]

  v59 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v0 = *(_QWORD *)(v59 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v0 + 232) + 192LL));
  ++*(_WORD *)(*(_QWORD *)(v0 + 232) + 122LL);
  v1 = *(_QWORD *)(v0 + 232);
  v2 = *(_DWORD *)(v1 + 128);
  *(_DWORD *)(v1 + 128) = v2 + 1;
  if ( !v2 )
  {
    v48 = 0;
    v49 = *(_DWORD *)(*(_QWORD *)(v1 + 136) + 4LL);
    if ( v49 )
    {
      do
      {
        v50 = v48++;
        *(_DWORD *)((v50 << 6) + *(_QWORD *)(*(_QWORD *)(v1 + 136) + 8LL) + 36) = 0;
      }
      while ( v48 < v49 );
    }
  }
  v3 = *(_QWORD *)(v0 + 232);
  v4 = *(_QWORD *)(v3 + 136);
  if ( v4 )
  {
    v5 = 0xFFFFFFFFLL;
    if ( (byte_18158CB72 & 2) != 0 )
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
          v53 = *(_DWORD *)(v3 + 52);
          if ( v53 < *(_DWORD *)(v3 + 68) || (unsigned int)v11 >= *(_DWORD *)(v3 + 64) )
          {
            v58 = 0;
            CQPCTick::GetCurrentTimeInUs(&v58);
            CallRate::MarkCall((CallRate *)(v3 + 8), v58);
          }
          else
          {
            *(_BYTE *)(v3 + 56) = 0;
            CallRateManager::LogPauseTaskDisabled((CallRateManager *)v3, v53);
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
            v51 = *(_DWORD *)(v3 + 80);
            if ( v51 < 0x4E20 )
            {
              *(_DWORD *)(v3 + 80) = v51 + 1000;
              v52 = *(_DWORD *)(v3 + 84);
              if ( v52 < 0xF )
                *(_DWORD *)(v3 + 84) = v52 + 1;
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
        v58 = 0;
        CQPCTick::GetCurrentTimeInUs(&v58);
        *(_WORD *)pbBuffer = 0;
        BCryptGenRandom(0, pbBuffer, 2u, 2u);
        v54 = (unsigned int)((int)(float)((float)((float)*(unsigned __int16 *)pbBuffer / 65535.0)
                                        * (float)*(int *)(v3 + 80))
                           + 1000);
        do
        {
          PerformanceCount.QuadPart = 0;
          CQPCTick::GetCurrentTimeInUs((unsigned __int64 *)&PerformanceCount.QuadPart);
        }
        while ( PerformanceCount.QuadPart - v58 <= v54 );
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
          v58 = *(_QWORD *)(v16 + v15 + 16);
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
                      + 4 * (*(_QWORD *)(v16 + v15) % (unsigned __int64)dword_1813BF5B0[*(int *)(v21 + 152)]));
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
          v30 = v58;
          *((_BYTE *)v29 + 16) = 1;
          ((void (__fastcall *)(__int64, unsigned __int64))PerformanceCount.QuadPart)(v17, v30);
          *(_OWORD *)GlobalThreadState() = v27;
          *((_BYTE *)GlobalThreadState() + 16) = v28;
          if ( *(_WORD *)(*(_QWORD *)(v0 + 232) + 122LL) == 1 )
          {
            for ( m = 0; m < *(_DWORD *)(v0 + 516); ++m )
            {
              v32 = *(_QWORD *)(v0 + 520);
              if ( *(int *)(*(_QWORD *)(v32 + 8LL * m) + 6932LL) > 0 )
                CObserverManager::InvokeObserversForCheckpoint((CObserverManager *)(*(_QWORD *)(v32 + 8LL * m) + 6928LL));
            }
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v0 + 232) + 192LL));
          v33 = *(_QWORD *)(v0 + 232);
          if ( *(_DWORD *)(v33 + 296) >> 20 != v20 )
            i = -1;
          if ( !*(_QWORD *)(v33 + 136) )
          {
            *(_WORD *)(v33 + 120) = 0;
            goto LABEL_53;
          }
          --v7;
        }
      }
      else
      {
        v46 = *(void (__fastcall **)(__int64, __int64, unsigned int *))(v16 + v15 + 24);
        if ( v46 )
        {
          v47 = *(_QWORD *)(v16 + v15 + 16);
          if ( v47 )
          {
            v46(v47, v5, dword_1813BF5B0);
            *(_QWORD *)(v16 + v15 + 24) = 0;
            *(_QWORD *)(v16 + v15 + 16) = 0;
          }
        }
      }
    }
    v34 = 0;
    v35 = *(_QWORD *)(v59 + 16);
    if ( v35 )
      v36 = *(_QWORD *)(v35 + 232);
    else
      v36 = 0;
    v37 = (struct _RTL_CRITICAL_SECTION *)(v36 + 192);
    EnterCriticalSection((LPCRITICAL_SECTION)(v36 + 192));
    v38 = *(_QWORD *)(v36 + 136);
    v39 = 0;
    if ( *(int *)(v38 + 4) > 0 )
    {
      v40 = *(_OWORD **)(v38 + 8);
      v41 = 0;
      do
      {
        v42 = *(_QWORD *)(v38 + 8) + ((__int64)v41 << 6);
        if ( *(_QWORD *)v42 || *(_QWORD *)(v42 + 24) && *(_QWORD *)(v42 + 16) )
        {
          if ( v40 != (_OWORD *)v42 )
          {
            *v40 = *(_OWORD *)v42;
            v40[1] = *(_OWORD *)(v42 + 16);
            v40[2] = *(_OWORD *)(v42 + 32);
            v40[3] = *(_OWORD *)(v42 + 48);
            if ( *(_QWORD *)v42 )
            {
              v44 = (int *)(*(_QWORD *)(v36 + 144)
                          + 4 * (*(_QWORD *)v42 % (unsigned __int64)dword_1813BF5B0[*(int *)(v36 + 152)]));
              for ( n = *v44; *v44 != v41; n = *v44 )
                v44 = (int *)(*(_QWORD *)(*(_QWORD *)(v36 + 136) + 8LL) + 56LL + ((__int64)n << 6));
              *v44 = v39;
            }
          }
          v40 += 4;
          ++v39;
          if ( (*(_BYTE *)(v42 + 32) & 2) == 0 )
            ++v34;
        }
        v38 = *(_QWORD *)(v36 + 136);
        ++v41;
      }
      while ( v41 < *(_DWORD *)(v38 + 4) );
      v37 = (struct _RTL_CRITICAL_SECTION *)(v36 + 192);
    }
    *(_DWORD *)(v38 + 4) = v39;
    *(_DWORD *)(v36 + 296) = (*(_DWORD *)(v36 + 296) + 0x100000)
                           ^ (*(_DWORD *)(v36 + 296)
                            ^ (*(_DWORD *)(v36 + 296) + 0x100000))
                           & 0xFFFFF;
    LeaveCriticalSection(v37);
    v43 = *(_QWORD *)(v0 + 232);
    if ( v34 )
    {
      PostMessageW(*(HWND *)(v43 + 96), 0x8002u, 0, 0);
      v55 = *(_QWORD *)(v0 + 232);
      if ( !*(_WORD *)(v55 + 120) )
        ++*(_WORD *)(v55 + 120);
    }
    else if ( *(_WORD *)(v43 + 120) )
    {
      --*(_WORD *)(v43 + 120);
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
0x1800d1a1c  mov     rax, rsp
0x1800d1a1f  push    rbp
0x1800d1a20  push    rbx
0x1800d1a21  push    rsi
0x1800d1a22  push    rdi
0x1800d1a23  push    r12
0x1800d1a25  push    r13
0x1800d1a27  push    r14
0x1800d1a29  push    r15
0x1800d1a2b  lea     rbp, [rax-5Fh]
0x1800d1a2f  sub     rsp, 0A8h
0x1800d1a36  mov     ecx, cs:_tls_index
0x1800d1a3c  movaps  xmmword ptr [rax-58h], xmm6
0x1800d1a40  movaps  xmmword ptr [rax-68h], xmm7
0x1800d1a44  mov     rax, gs:58h
0x1800d1a4d  mov     edx, 10h
0x1800d1a52  mov     r12, [rax+rcx*8]
0x1800d1a56  mov     [rbp+57h+var_A8], r12
0x1800d1a5a  mov     rsi, [r12+rdx]
0x1800d1a5e  mov     rcx, [rsi+0E8h]
0x1800d1a65  add     rcx, 0C0h; lpCriticalSection
0x1800d1a6c  call    cs:__imp_EnterCriticalSection
0x1800d1a72  mov     rax, [rsi+0E8h]
0x1800d1a79  mov     r13d, 1
0x1800d1a7f  xor     r12d, r12d
0x1800d1a82  add     [rax+7Ah], r13w
0x1800d1a87  mov     r9, [rsi+0E8h]
0x1800d1a8e  mov     ecx, [r9+80h]
0x1800d1a95  lea     eax, [rcx+1]
0x1800d1a98  mov     [r9+80h], eax
0x1800d1a9f  test    ecx, ecx
0x1800d1aa1  jz      loc_1800D2093
0x1800d1aa7  mov     rbx, [rsi+0E8h]
0x1800d1aae  mov     rcx, [rbx+88h]
0x1800d1ab5  test    rcx, rcx
0x1800d1ab8  jz      loc_1800D2089
0x1800d1abe  test    cs:byte_18158CB72, 2
0x1800d1ac5  mov     edx, 0FFFFFFFFh
0x1800d1aca  jnz     loc_1800D200E
0x1800d1ad0  mov     ecx, [rcx+4]
0x1800d1ad3  mov     r15d, edx
0x1800d1ad6  test    ecx, ecx
0x1800d1ad8  js      short loc_1800D1AE6
0x1800d1ada  lea     eax, [rcx+3E8h]
0x1800d1ae0  cmp     eax, ecx
0x1800d1ae2  cmovnb  r15d, eax
0x1800d1ae6  cmp     [rbx+3Ch], r12d
0x1800d1aea  jz      loc_1800D1BC2
0x1800d1af0  cmp     dword ptr [rbx+3Ch], 2
0x1800d1af4  jnz     loc_1800D1BAE
0x1800d1afa  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800d1afe  mov     qword ptr [rbp+57h+PerformanceCount], r12
0x1800d1b02  call    cs:__imp_QueryPerformanceCounter
0x1800d1b08  mov     r8, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x1800d1b0f  test    r8, r8
0x1800d1b12  jz      loc_1800D2064
0x1800d1b18  mov     rdi, qword ptr [rbp+57h+PerformanceCount]
0x1800d1b1c  test    rdi, rdi
0x1800d1b1f  jz      short loc_1800D1B57
0x1800d1b21  test    r8, r8
0x1800d1b24  jz      short loc_1800D1B57
0x1800d1b26  cmp     r8, 0F4240h
0x1800d1b2d  jz      short loc_1800D1B57
0x1800d1b2f  xor     edx, edx
0x1800d1b31  mov     rax, rdi
0x1800d1b34  div     r8
0x1800d1b37  xor     edx, edx
0x1800d1b39  mov     rcx, rax
0x1800d1b3c  imul    rax, r8
0x1800d1b40  sub     rdi, rax
0x1800d1b43  imul    rax, rdi, 0F4240h
0x1800d1b4a  imul    rdi, rcx, 0F4240h
0x1800d1b51  div     r8
0x1800d1b54  add     rdi, rax
0x1800d1b57  mov     eax, [rbx+20h]
0x1800d1b5a  mov     r8, rdi
0x1800d1b5d  add     eax, [rbx+10h]
0x1800d1b60  sub     r8, [rbx+18h]
0x1800d1b64  imul    rcx, rax, 3E8h
0x1800d1b6b  mov     rax, 624DD2F1A9FBE77h
0x1800d1b75  mul     r8
0x1800d1b78  mov     rax, rcx
0x1800d1b7b  sub     r8, rdx
0x1800d1b7e  shr     r8, 1
0x1800d1b81  add     r8, rdx
0x1800d1b84  xor     edx, edx
0x1800d1b86  shr     r8, 9
0x1800d1b8a  div     r8
0x1800d1b8d  mov     edx, 0FFFFFFFFh
0x1800d1b92  cmp     rax, rdx
0x1800d1b95  mov     ecx, edx
0x1800d1b97  cmovb   rcx, rax
0x1800d1b9b  cmp     [rbx+38h], r12b
0x1800d1b9f  jnz     loc_1800D2137
0x1800d1ba5  cmp     ecx, [rbx+40h]
0x1800d1ba8  jnb     loc_1800D20CE
0x1800d1bae  cmp     [rbx+38h], r12b
0x1800d1bb2  jnz     loc_1800D2176
0x1800d1bb8  cmp     [rbx+3Ch], r13d
0x1800d1bbc  jz      loc_1800D2176
0x1800d1bc2  mov     r14d, r12d
0x1800d1bc5  lea     r8, dword_1813BF5B0
0x1800d1bcc  or      r11d, 0FFFFFFFFh
0x1800d1bd0  test    r15d, r15d
0x1800d1bd3  jz      loc_1800D1E35
0x1800d1bd9  mov     rcx, [rsi+0E8h]
0x1800d1be0  mov     rdi, [rcx+88h]
0x1800d1be7  cmp     r14d, [rdi+4]
0x1800d1beb  jge     loc_1800D1E35
0x1800d1bf1  mov     rdi, [rdi+8]
0x1800d1bf5  xor     r10d, r10d
0x1800d1bf8  movsxd  rbx, r14d
0x1800d1bfb  shl     rbx, 6
0x1800d1bff  mov     r12, [rbx+rdi]
0x1800d1c03  test    r12, r12
0x1800d1c06  jz      loc_1800D202D
0x1800d1c0c  test    byte ptr [rbx+rdi+20h], 2
0x1800d1c11  jnz     loc_1800D2006
0x1800d1c17  mov     rax, [rbx+rdi+8]
0x1800d1c1c  mov     edx, [rcx+128h]
0x1800d1c22  mov     r13d, edx
0x1800d1c25  movups  xmm7, xmmword ptr [rbx+rdi+28h]
0x1800d1c2a  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x1800d1c2e  mov     rax, [rbx+rdi+10h]
0x1800d1c33  mov     [rbp+57h+var_B0], rax
0x1800d1c37  lea     eax, [r10+1]
0x1800d1c3b  shr     r13d, 14h
0x1800d1c3f  cmp     [rcx+7Ah], ax
0x1800d1c43  jnz     loc_1800D2016
0x1800d1c49  movups  xmm0, xmmword ptr [rbx+rdi]
0x1800d1c4d  movups  xmmword ptr [rcx+0E8h], xmm0
0x1800d1c54  movups  xmm1, xmmword ptr [rbx+rdi+10h]
0x1800d1c59  movups  xmmword ptr [rcx+0F8h], xmm1
0x1800d1c60  movups  xmm0, xmmword ptr [rbx+rdi+20h]
0x1800d1c65  movups  xmmword ptr [rcx+108h], xmm0
0x1800d1c6c  movups  xmm1, xmmword ptr [rbx+rdi+30h]
0x1800d1c71  movups  xmmword ptr [rcx+118h], xmm1
0x1800d1c78  mov     r9, [rsi+0E8h]
0x1800d1c7f  xor     edx, edx
0x1800d1c81  movsxd  rax, dword ptr [r9+98h]
0x1800d1c88  mov     ecx, [r8+rax*4]
0x1800d1c8c  mov     rax, [rbx+rdi]
0x1800d1c90  div     rcx
0x1800d1c93  mov     rax, [r9+90h]
0x1800d1c9a  mov     ecx, edx
0x1800d1c9c  lea     r8, [rax+rcx*4]
0x1800d1ca0  mov     edx, [r8]
0x1800d1ca3  cmp     edx, r14d
0x1800d1ca6  jnz     loc_1800D1E0E
0x1800d1cac  mov     eax, [rbx+rdi+38h]
0x1800d1cb0  mov     [rbx+rdi], r10
0x1800d1cb4  mov     [rbx+rdi+10h], r10
0x1800d1cb9  mov     [rbx+rdi+18h], r10
0x1800d1cbe  mov     [rbx+rdi+20h], r10d
0x1800d1cc3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800d1cca  movdqu  xmmword ptr [rbx+rdi+28h], xmm0
0x1800d1cd0  mov     [r8], eax
0x1800d1cd3  mov     [rbx+rdi+38h], r11d
0x1800d1cd8  mov     rcx, [rsi+0E8h]
0x1800d1cdf  add     rcx, 0C0h; lpCriticalSection
0x1800d1ce6  call    cs:__imp_LeaveCriticalSection
0x1800d1cec  xor     ebx, ebx
0x1800d1cee  lea     edi, [rbx+1]
0x1800d1cf1  cmp     [rsi+204h], ebx
0x1800d1cf7  jle     short loc_1800D1D27
0x1800d1cf9  mov     rax, [rsi+208h]
0x1800d1d00  movsxd  rcx, ebx
0x1800d1d03  mov     rcx, [rax+rcx*8]
0x1800d1d07  mov     rcx, [rcx+1560h]
0x1800d1d0e  mov     rax, [rcx]
0x1800d1d11  mov     rax, [rax+90h]
0x1800d1d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d1d  add     ebx, edi
0x1800d1d1f  cmp     ebx, [rsi+204h]
0x1800d1d25  jl      short loc_1800D1CF9
0x1800d1d27  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d1d2d  movups  xmm6, xmmword ptr [rax]
0x1800d1d30  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d1d36  mov     bl, [rax+10h]
0x1800d1d39  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d1d3f  movdqu  xmmword ptr [rax], xmm7
0x1800d1d43  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d1d49  mov     rdx, [rbp+57h+var_B0]
0x1800d1d4d  mov     rcx, r12
0x1800d1d50  mov     [rax+10h], dil
0x1800d1d54  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x1800d1d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d5d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d1d63  movdqu  xmmword ptr [rax], xmm6
0x1800d1d67  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d1d6d  xor     r12d, r12d
0x1800d1d70  mov     [rax+10h], bl
0x1800d1d73  mov     rax, [rsi+0E8h]
0x1800d1d7a  cmp     [rax+7Ah], di
0x1800d1d7e  jnz     short loc_1800D1DB5
0x1800d1d80  mov     ebx, r12d
0x1800d1d83  cmp     [rsi+204h], r12d
0x1800d1d8a  jle     short loc_1800D1DB5
0x1800d1d8c  mov     rax, [rsi+208h]
0x1800d1d93  movsxd  rcx, ebx
0x1800d1d96  mov     rcx, [rax+rcx*8]
0x1800d1d9a  add     rcx, 1B10h; this
0x1800d1da1  cmp     [rcx+4], r12d
0x1800d1da5  jg      loc_1800D1FDA
0x1800d1dab  add     ebx, edi
0x1800d1dad  cmp     ebx, [rsi+204h]
0x1800d1db3  jl      short loc_1800D1D8C
0x1800d1db5  mov     rcx, [rsi+0E8h]
0x1800d1dbc  add     rcx, 0C0h; lpCriticalSection
0x1800d1dc3  call    cs:__imp_EnterCriticalSection
0x1800d1dc9  mov     rcx, [rsi+0E8h]
0x1800d1dd0  mov     r11d, 0FFFFFFFFh
0x1800d1dd6  mov     eax, [rcx+128h]
0x1800d1ddc  shr     eax, 14h
0x1800d1ddf  cmp     eax, r13d
0x1800d1de2  cmovnz  r14d, r11d
0x1800d1de6  cmp     [rcx+88h], r12
0x1800d1ded  jz      loc_1800D1F49
0x1800d1df3  mov     eax, 0FFFFFFFFh
0x1800d1df8  lea     r13d, [r11+2]
0x1800d1dfc  add     r15d, eax
0x1800d1dff  lea     r8, dword_1813BF5B0
0x1800d1e06  add     r14d, r13d
0x1800d1e09  jmp     loc_1800D1BD0
0x1800d1e0e  mov     rax, [r9+88h]
0x1800d1e15  mov     rcx, [rax+8]
0x1800d1e19  add     rcx, 38h ; '8'
0x1800d1e1d  movsxd  r8, edx
0x1800d1e20  shl     r8, 6
0x1800d1e24  add     r8, rcx
0x1800d1e27  mov     edx, [r8]
0x1800d1e2a  cmp     edx, r14d
0x1800d1e2d  jz      loc_1800D1CAC
0x1800d1e33  jmp     short loc_1800D1E1D
0x1800d1e35  mov     rbx, [rbp+57h+var_A8]
0x1800d1e39  mov     r14d, r12d
0x1800d1e3c  mov     eax, 10h
0x1800d1e41  mov     rbx, [rbx+rax]
0x1800d1e45  test    rbx, rbx
0x1800d1e48  jz      loc_1800D1FD2
0x1800d1e4e  mov     rbx, [rbx+0E8h]
0x1800d1e55  lea     r15, [rbx+0C0h]
0x1800d1e5c  mov     rcx, r15; lpCriticalSection
0x1800d1e5f  call    cs:__imp_EnterCriticalSection
0x1800d1e65  mov     rax, [rbx+88h]
0x1800d1e6c  mov     edi, r12d
0x1800d1e6f  cmp     [rax+4], r12d
0x1800d1e73  jle     short loc_1800D1EB8
0x1800d1e75  mov     r10, [rax+8]
0x1800d1e79  lea     r15, dword_1813BF5B0
0x1800d1e80  mov     r11d, r12d
0x1800d1e83  movsxd  r9, r11d
0x1800d1e86  shl     r9, 6
0x1800d1e8a  add     r9, [rax+8]
0x1800d1e8e  cmp     [r9], r12
0x1800d1e91  jnz     loc_1800D1F5F
0x1800d1e97  cmp     [r9+18h], r12
0x1800d1e9b  jnz     loc_1800D1F55
0x1800d1ea1  mov     rax, [rbx+88h]
0x1800d1ea8  add     r11d, r13d
0x1800d1eab  cmp     r11d, [rax+4]
0x1800d1eaf  jl      short loc_1800D1E83
0x1800d1eb1  lea     r15, [rbx+0C0h]
0x1800d1eb8  mov     [rax+4], edi
0x1800d1ebb  mov     rcx, r15; lpCriticalSection
0x1800d1ebe  mov     eax, [rbx+128h]
0x1800d1ec4  lea     edx, [rax+100000h]
0x1800d1eca  mov     r8d, edx
0x1800d1ecd  xor     r8d, eax
0x1800d1ed0  and     r8d, 0FFFFFh
0x1800d1ed7  xor     r8d, edx
0x1800d1eda  mov     [rbx+128h], r8d
0x1800d1ee1  call    cs:__imp_LeaveCriticalSection
0x1800d1ee7  mov     rcx, [rsi+0E8h]
0x1800d1eee  test    r14d, r14d
0x1800d1ef1  jnz     loc_1800D21E9
0x1800d1ef7  movzx   eax, word ptr [rcx+78h]
0x1800d1efb  test    eax, eax
0x1800d1efd  jz      short loc_1800D1F4E
0x1800d1eff  mov     edx, 0FFFFh
0x1800d1f04  add     [rcx+78h], dx
0x1800d1f08  mov     rax, [rsi+0E8h]
0x1800d1f0f  add     [rax+7Ah], dx
0x1800d1f13  mov     rcx, [rsi+0E8h]
0x1800d1f1a  add     rcx, 0C0h
0x1800d1f21  lea     r11, [rsp+0E0h+var_38]
0x1800d1f29  movaps  xmm6, xmmword ptr [r11-18h]
0x1800d1f2e  movaps  xmm7, xmmword ptr [r11-28h]
0x1800d1f33  mov     rsp, r11
0x1800d1f36  pop     r15
0x1800d1f38  pop     r14
0x1800d1f3a  pop     r13
0x1800d1f3c  pop     r12
0x1800d1f3e  pop     rdi
0x1800d1f3f  pop     rsi
0x1800d1f40  pop     rbx
0x1800d1f41  pop     rbp
0x1800d1f42  jmp     cs:__imp_LeaveCriticalSection
0x1800d1f49  mov     [rcx+78h], r12w
0x1800d1f4e  mov     edx, 0FFFFh
  ... truncated ...
```
