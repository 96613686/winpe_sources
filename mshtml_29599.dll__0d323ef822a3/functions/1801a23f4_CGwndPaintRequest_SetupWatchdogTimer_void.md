# CGwndPaintRequest::SetupWatchdogTimer(void)

- ea: `0x1801a23f4`
- end: `0x1801a2779`
- name: `?SetupWatchdogTimer@CGwndPaintRequest@@AEAAJXZ`
- size: `901`
- prototype: `__int64 __fastcall(CGwndPaintRequest *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801a194c`
- `0x1801a2094`
- `0x1807302dc`

## callees

- `0x1801a23f4`
- `0x1801cd074`
- `0x18079b8d4`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801a2669`
- `KERNEL32!GetCurrentThreadId` at `0x1801a26d1`
- `KERNEL32!GetCurrentThreadId` at `0x1801a2669`
- `KERNEL32!GetCurrentThreadId` at `0x1801a26d1`
- `USER32!GetWindowThreadProcessId` at `0x1801a2661`
- `USER32!GetWindowThreadProcessId` at `0x1801a26c9`
- `USER32!GetWindowThreadProcessId` at `0x1801a2661`
- `USER32!GetWindowThreadProcessId` at `0x1801a26c9`
- `USER32!SetTimer` at `0x1801a26b5`
- `USER32!SetTimer` at `0x1801a26f6`
- `USER32!SetTimer` at `0x1801a26b5`
- `USER32!SetTimer` at `0x1801a26f6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a256d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a257d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a25dd`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a25ed`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a26db`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a256d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a257d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a25dd`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a25ed`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a26db`

## pseudocode

```c
__int64 __fastcall CGwndPaintRequest::SetupWatchdogTimer(CGwndPaintRequest *this)
{
  unsigned int v1; // edi
  __int64 v3; // r15
  __int64 v4; // rax
  __int64 v5; // r14
  __int64 v6; // rbx
  __int64 v7; // rax
  int v8; // ecx
  __int64 i; // rdi
  CImplAry *v10; // rcx
  int v11; // r8d
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned int v14; // eax
  int v15; // edx
  __int64 v16; // r8
  __int64 v17; // rax
  unsigned int v18; // ebx
  int v19; // r15d
  HWND v20; // rcx
  UINT_PTR v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rbp
  __int64 v24; // rsi
  int v25; // ecx
  GUID v26; // xmm0
  HWND *v28; // rsi
  __int128 v29; // xmm0
  __int64 (__fastcall *v30)(HWND, UINT_PTR, __int64, _QWORD, _DWORD); // rax
  UINT_PTR v31; // rdx
  HWND v32; // rcx
  DWORD v34; // ebx
  DWORD WindowThreadProcessId; // ebx

  v1 = 0;
  if ( !*((_BYTE *)this + 17) )
  {
    v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v4 = *(_QWORD *)(v3 + 16);
    if ( v4 )
      v5 = *(_QWORD *)(v4 + 232);
    else
      v5 = 0;
    if ( !*(_QWORD *)(v5 + 96) )
      return (unsigned int)-2147467259;
    if ( v4 )
      v6 = *(_QWORD *)(v4 + 232);
    else
      v6 = 0;
    v7 = *(_QWORD *)(v6 + 112);
    v8 = *(_DWORD *)(v7 + 4);
    for ( i = *(_QWORD *)(v7 + 8); ; i += 56 )
    {
      if ( v8 <= 0 )
        goto LABEL_11;
      if ( *(CGwndPaintRequest **)i == this && *(_DWORD *)(i + 16) == 52737 )
        break;
      --v8;
    }
    if ( *(_DWORD *)(i + 24) != 10 )
      *(_DWORD *)(i + 24) = 10;
    if ( *(_DWORD *)(i + 32) )
      goto LABEL_40;
    if ( *((_BYTE *)GlobalThreadState() + 16) )
    {
      v28 = (HWND *)(v6 + 96);
      v29 = *(_OWORD *)GlobalThreadState();
    }
    else
    {
      v28 = (HWND *)(v6 + 96);
      WindowThreadProcessId = GetWindowThreadProcessId(*(HWND *)(v6 + 96), 0);
      v29 = WindowThreadProcessId == GetCurrentThreadId() ? *(_OWORD *)GlobalThreadState() : *(_OWORD *)&GUID_NULL;
    }
    v30 = (__int64 (__fastcall *)(HWND, UINT_PTR, __int64, _QWORD, _DWORD))qword_181591D28;
    v31 = *(unsigned int *)(i + 20);
    *(_OWORD *)(i + 40) = v29;
    v32 = *v28;
    if ( v30 ? v30(v32, v31, 10, 0, *(_DWORD *)(i + 28)) : SetTimer(v32, v31, 0xAu, 0) )
    {
LABEL_40:
      if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
        McTemplateU0pqpq_EventWriteTransfer(
          v8,
          (unsigned int)&MSHTML_FORMSTIMER_RESET,
          *(_QWORD *)i,
          *(_DWORD *)(i + 16),
          *(_QWORD *)(i + 8),
          *(_DWORD *)(i + 24));
      v1 = 0;
LABEL_29:
      *((_BYTE *)this + 17) = 1;
      return v1;
    }
LABEL_11:
    v10 = *(CImplAry **)(v5 + 112);
    v11 = *((_DWORD *)v10 + 1) + 1;
    if ( (unsigned int)v11 <= *(_DWORD *)v10 >> 2 )
    {
      v1 = 0;
      goto LABEL_13;
    }
    if ( v11 >= 0 )
    {
      v1 = CImplAry::EnsureSizeWorker(v10, 0x38u, v11);
      if ( v1 )
        goto LABEL_28;
LABEL_13:
      v12 = *(_QWORD *)(v3 + 16);
      if ( v12 )
        v12 = *(_QWORD *)(v12 + 232);
      v13 = *(_QWORD *)(v12 + 112);
LABEL_16:
      v14 = *(_DWORD *)(v12 + 104) + 1;
      *(_DWORD *)(v12 + 104) = v14;
      if ( v14 < 0x2002 )
      {
        *(_DWORD *)(v12 + 104) = 8194;
        v14 = 8194;
      }
      v15 = *(_DWORD *)(v13 + 4);
      v16 = *(_QWORD *)(v13 + 8);
      while ( v15 > 0 )
      {
        if ( v14 == *(_DWORD *)(v16 + 20) )
          goto LABEL_16;
        --v15;
        v16 += 56;
      }
      v17 = *(_QWORD *)(v3 + 16);
      v18 = *(_DWORD *)(v12 + 104);
      v19 = *(unsigned __int8 *)(v17 + 583);
      if ( *(_BYTE *)(v17 + 583)
        || ((v20 = *(HWND *)(v5 + 96), !qword_181591D28)
          ? (v21 = SetTimer(v20, v18, 0xAu, 0))
          : (v21 = ((__int64 (__fastcall *)(HWND, _QWORD, __int64))qword_181591D28)(v20, v18, 10)),
            v21) )
      {
        v22 = *(_QWORD *)(v5 + 112);
        v23 = *(_QWORD *)(v22 + 8);
        v24 = 56LL * *(int *)(v22 + 4);
        *(_QWORD *)(v24 + v23) = this;
        *(_QWORD *)(v24 + v23 + 8) = CGwndPaintRequest::OnWatchdogTimer;
        *(_DWORD *)(v24 + v23 + 20) = v18;
        *(_DWORD *)(v24 + v23 + 16) = 52737;
        *(_QWORD *)(v24 + v23 + 24) = 10;
        *(_DWORD *)(v24 + v23 + 36) = 1;
        *(_DWORD *)(v24 + v23 + 32) = v19;
        if ( *((_BYTE *)GlobalThreadState() + 16)
          || (v34 = GetWindowThreadProcessId(*(HWND *)(v5 + 96), 0), v34 == GetCurrentThreadId()) )
        {
          v26 = *(GUID *)GlobalThreadState();
        }
        else
        {
          v26 = GUID_NULL;
        }
        *(GUID *)(v24 + v23 + 40) = v26;
        ++*(_DWORD *)(*(_QWORD *)(v5 + 112) + 4LL);
        if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
          McTemplateU0pqpq_EventWriteTransfer(
            v25,
            (unsigned int)&MSHTML_FORMSTIMER_SET,
            (_DWORD)this,
            52737,
            (char)CGwndPaintRequest::OnWatchdogTimer,
            10);
LABEL_28:
        if ( (v1 & 0x80000000) != 0 )
          return v1;
        goto LABEL_29;
      }
      return (unsigned int)-2147467259;
    }
    return (unsigned int)-2147024809;
  }
  return v1;
}

```

## disassembly

```asm
0x1801a23f4  mov     rax, rsp
0x1801a23f7  mov     [rax+10h], rbx
0x1801a23fb  mov     [rax+18h], rbp
0x1801a23ff  mov     [rax+8], rcx
0x1801a2403  push    rsi
0x1801a2404  push    rdi
0x1801a2405  push    r13
0x1801a2407  push    r14
0x1801a2409  push    r15
0x1801a240b  sub     rsp, 30h
0x1801a240f  xor     edi, edi
0x1801a2411  mov     r13, rcx
0x1801a2414  cmp     [rcx+11h], dil
0x1801a2418  jnz     loc_1801A25A9
0x1801a241e  mov     rax, gs:58h
0x1801a2427  mov     ecx, cs:_tls_index
0x1801a242d  mov     esi, 10h
0x1801a2432  mov     r15, [rax+rcx*8]
0x1801a2436  mov     rax, [r15+rsi]
0x1801a243a  test    rax, rax
0x1801a243d  jz      loc_1801A2683
0x1801a2443  mov     r14, [rax+0E8h]
0x1801a244a  cmp     [r14+60h], rdi
0x1801a244e  jz      loc_1801A272F
0x1801a2454  test    rax, rax
0x1801a2457  jz      loc_1801A268B
0x1801a245d  mov     rbx, [rax+0E8h]
0x1801a2464  mov     rax, [rbx+70h]
0x1801a2468  mov     ecx, [rax+4]
0x1801a246b  mov     rdi, [rax+8]
0x1801a246f  mov     ebp, 0Ah
0x1801a2474  test    ecx, ecx
0x1801a2476  jle     short loc_1801A248E
0x1801a2478  cmp     [rdi], r13
0x1801a247b  jz      loc_1801A25C2
0x1801a2481  dec     ecx
0x1801a2483  add     rdi, 38h ; '8'
0x1801a2487  jmp     short loc_1801A246F
0x1801a2489  mov     esi, 10h
0x1801a248e  mov     rcx, [r14+70h]; this
0x1801a2492  mov     r8d, [rcx+4]
0x1801a2496  mov     eax, [rcx]
0x1801a2498  inc     r8d; int
0x1801a249b  shr     eax, 2
0x1801a249e  cmp     r8d, eax
0x1801a24a1  ja      loc_1801A2697
0x1801a24a7  xor     edi, edi
0x1801a24a9  mov     rcx, [r15+rsi]
0x1801a24ad  test    rcx, rcx
0x1801a24b0  jz      loc_1801A2692
0x1801a24b6  mov     rcx, [rcx+0E8h]
0x1801a24bd  mov     r9, [rcx+70h]
0x1801a24c1  mov     r10d, 2002h
0x1801a24c7  mov     eax, [rcx+68h]
0x1801a24ca  inc     eax
0x1801a24cc  mov     [rcx+68h], eax
0x1801a24cf  cmp     eax, r10d
0x1801a24d2  jb      loc_1801A276D
0x1801a24d8  mov     edx, [r9+4]
0x1801a24dc  mov     r8, [r9+8]
0x1801a24e0  test    edx, edx
0x1801a24e2  jg      loc_1801A2646
0x1801a24e8  mov     rax, [r15+rsi]
0x1801a24ec  mov     ebx, [rcx+68h]
0x1801a24ef  movzx   r15d, byte ptr [rax+247h]
0x1801a24f7  test    r15d, r15d
0x1801a24fa  jnz     short loc_1801A252B
0x1801a24fc  mov     rax, cs:qword_181591D28
0x1801a2503  xor     r9d, r9d; lpTimerFunc
0x1801a2506  mov     rcx, [r14+60h]; hWnd
0x1801a250a  mov     edx, ebx; nIDEvent
0x1801a250c  mov     r8d, ebp; uElapse
0x1801a250f  test    rax, rax
0x1801a2512  jz      loc_1801A26B5
0x1801a2518  mov     dword ptr [rsp+58h+var_38], r9d
0x1801a251d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a2522  test    rax, rax
0x1801a2525  jz      loc_1801A272F
0x1801a252b  mov     rcx, [r14+70h]
0x1801a252f  movsxd  rax, dword ptr [rcx+4]
0x1801a2533  mov     rbp, [rcx+8]
0x1801a2537  imul    rsi, rax, 38h ; '8'
0x1801a253b  lea     rax, ?OnWatchdogTimer@CGwndPaintRequest@@QEAAJI@Z; CGwndPaintRequest::OnWatchdogTimer(uint)
0x1801a2542  mov     [rsi+rbp], r13
0x1801a2546  mov     [rsi+rbp+8], rax
0x1801a254b  mov     [rsi+rbp+14h], ebx
0x1801a254f  mov     dword ptr [rsi+rbp+10h], 0CE01h
0x1801a2557  mov     qword ptr [rsi+rbp+18h], 0Ah
0x1801a2560  mov     dword ptr [rsi+rbp+24h], 1
0x1801a2568  mov     [rsi+rbp+20h], r15d
0x1801a256d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a2573  cmp     byte ptr [rax+10h], 0
0x1801a2577  jz      loc_1801A265B
0x1801a257d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a2583  movups  xmm0, xmmword ptr [rax]
0x1801a2586  movdqu  xmmword ptr [rsi+rbp+28h], xmm0
0x1801a258c  mov     rax, [r14+70h]
0x1801a2590  inc     dword ptr [rax+4]
0x1801a2593  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1801a259a  jnz     loc_1801A2701
0x1801a25a0  test    edi, edi
0x1801a25a2  js      short loc_1801A25A9
0x1801a25a4  mov     byte ptr [r13+11h], 1
0x1801a25a9  mov     rbx, [rsp+58h+arg_8]
0x1801a25ae  mov     eax, edi
0x1801a25b0  mov     rbp, [rsp+58h+arg_10]
0x1801a25b5  add     rsp, 30h
0x1801a25b9  pop     r15
0x1801a25bb  pop     r14
0x1801a25bd  pop     r13
0x1801a25bf  pop     rdi
0x1801a25c0  pop     rsi
0x1801a25c1  retn
0x1801a25c2  cmp     dword ptr [rdi+10h], 0CE01h
0x1801a25c9  jnz     loc_1801A2481
0x1801a25cf  cmp     [rdi+18h], ebp
0x1801a25d2  jz      short loc_1801A25D7
0x1801a25d4  mov     [rdi+18h], ebp
0x1801a25d7  cmp     dword ptr [rdi+20h], 0
0x1801a25db  jnz     short loc_1801A2632
0x1801a25dd  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a25e3  cmp     byte ptr [rax+10h], 0
0x1801a25e7  jz      loc_1801A26C0
0x1801a25ed  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a25f3  lea     rsi, [rbx+60h]
0x1801a25f7  movups  xmm0, xmmword ptr [rax]
0x1801a25fa  mov     rax, cs:qword_181591D28
0x1801a2601  xor     r9d, r9d; lpTimerFunc
0x1801a2604  mov     edx, [rdi+14h]; nIDEvent
0x1801a2607  movdqu  xmmword ptr [rdi+28h], xmm0
0x1801a260c  mov     rcx, [rsi]; hWnd
0x1801a260f  test    rax, rax
0x1801a2612  jz      loc_1801A26F3
0x1801a2618  mov     r8d, [rdi+1Ch]
0x1801a261c  mov     dword ptr [rsp+58h+var_38], r8d
0x1801a2621  mov     r8d, ebp
0x1801a2624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a2629  test    rax, rax
0x1801a262c  jz      loc_1801A2489
0x1801a2632  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1801a2639  jnz     loc_1801A2745
0x1801a263f  xor     edi, edi
0x1801a2641  jmp     loc_1801A25A4
0x1801a2646  cmp     eax, [r8+14h]
0x1801a264a  jz      loc_1801A24C7
0x1801a2650  dec     edx
0x1801a2652  add     r8, 38h ; '8'
0x1801a2656  jmp     loc_1801A24E0
0x1801a265b  mov     rcx, [r14+60h]; hWnd
0x1801a265f  xor     edx, edx; lpdwProcessId
0x1801a2661  call    cs:__imp_GetWindowThreadProcessId
0x1801a2667  mov     ebx, eax
0x1801a2669  call    cs:__imp_GetCurrentThreadId
0x1801a266f  cmp     ebx, eax
0x1801a2671  jz      loc_1801A257D
0x1801a2677  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801a267e  jmp     loc_1801A2586
0x1801a2683  xor     r14d, r14d
0x1801a2686  jmp     loc_1801A244A
0x1801a268b  xor     ebx, ebx
0x1801a268d  jmp     loc_1801A2464
0x1801a2692  jmp     loc_1801A24BD
0x1801a2697  test    r8d, r8d
0x1801a269a  js      short loc_1801A26E9
0x1801a269c  mov     edx, 38h ; '8'; unsigned __int64
0x1801a26a1  call    ?EnsureSizeWorker@CImplAry@@AEAAJ_KJ@Z; CImplAry::EnsureSizeWorker(unsigned __int64,long)
0x1801a26a6  mov     edi, eax
0x1801a26a8  test    eax, eax
0x1801a26aa  jz      loc_1801A24A9
0x1801a26b0  jmp     loc_1801A25A0
0x1801a26b5  call    cs:__imp_SetTimer
0x1801a26bb  jmp     loc_1801A2522
0x1801a26c0  lea     rsi, [rbx+60h]
0x1801a26c4  xor     edx, edx; lpdwProcessId
0x1801a26c6  mov     rcx, [rsi]; hWnd
0x1801a26c9  call    cs:__imp_GetWindowThreadProcessId
0x1801a26cf  mov     ebx, eax
0x1801a26d1  call    cs:__imp_GetCurrentThreadId
0x1801a26d7  cmp     ebx, eax
0x1801a26d9  jnz     short loc_1801A2739
0x1801a26db  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a26e1  movups  xmm0, xmmword ptr [rax]
0x1801a26e4  jmp     loc_1801A25FA
0x1801a26e9  mov     edi, 80070057h
0x1801a26ee  jmp     loc_1801A25A9
0x1801a26f3  mov     r8d, ebp; uElapse
0x1801a26f6  call    cs:__imp_SetTimer
0x1801a26fc  jmp     loc_1801A2629
0x1801a2701  lea     rax, ?OnWatchdogTimer@CGwndPaintRequest@@QEAAJI@Z; CGwndPaintRequest::OnWatchdogTimer(uint)
0x1801a2708  mov     [rsp+58h+var_30], 0Ah
0x1801a2710  mov     r9d, 0CE01h
0x1801a2716  mov     [rsp+58h+var_38], rax
0x1801a271b  mov     r8, r13
0x1801a271e  lea     rdx, MSHTML_FORMSTIMER_SET
0x1801a2725  call    McTemplateU0pqpq_EventWriteTransfer
0x1801a272a  jmp     loc_1801A25A0
0x1801a272f  mov     edi, 80004005h
0x1801a2734  jmp     loc_1801A25A9
0x1801a2739  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801a2740  jmp     loc_1801A25FA
0x1801a2745  mov     eax, [rdi+18h]
0x1801a2748  lea     rdx, MSHTML_FORMSTIMER_RESET
0x1801a274f  mov     r9d, [rdi+10h]
0x1801a2753  mov     r8, [rdi]
0x1801a2756  mov     [rsp+58h+var_30], eax
0x1801a275a  mov     rax, [rdi+8]
0x1801a275e  mov     [rsp+58h+var_38], rax
0x1801a2763  call    McTemplateU0pqpq_EventWriteTransfer
0x1801a2768  jmp     loc_1801A263F
0x1801a276d  mov     [rcx+68h], r10d
0x1801a2771  mov     eax, r10d
0x1801a2774  jmp     loc_1801A24D8
```
