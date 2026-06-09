# _GWPostMethodCallEx(GWND *,void *,void (CVoid::*)(unsigned __int64),unsigned __int64,ulong,void (*)(unsigned __int64))

- ea: `0x180265374`
- end: `0x18026587a`
- name: `?_GWPostMethodCallEx@@YAJPEAVGWND@@PEAXP8CVoid@@EAAX_K@Z2KP6AX2@Z@Z`
- size: `1286`
- prototype: `__int64 __usercall@<rax>(struct GWND *@<rcx>, int, __int64)`
- caller_count: `245`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001244c`
- `0x180050130`
- `0x18006a644`
- `0x1800fc860`
- `0x180100418`
- `0x18010df90`
- `0x18011403c`
- `0x1801147c0`
- `0x18011853c`
- `0x18011ac88`
- `0x1801583b0`
- `0x180158bd8`
- `0x180159590`
- `0x18015b784`
- `0x18015c1c8`
- `0x180161610`
- `0x1801ced64`
- `0x1801e452c`
- `0x1801f3d0c`
- `0x180262a14`
- `0x1802632f0`
- `0x180263960`
- `0x1802645c0`
- `0x1802647b8`
- `0x1802648b0`
- `0x180264950`
- `0x180264c5c`
- `0x180264df0`
- `0x1802650c0`
- `0x1802661d8`
- `0x180266364`
- `0x1802666f0`
- `0x180266810`
- `0x1802685b0`
- `0x18026d070`
- `0x18026e058`
- `0x18028ba68`
- `0x18028bffc`
- `0x180294190`
- `0x1802ce578`
- `0x1802cea10`
- `0x180307d20`
- `0x1803548cc`
- `0x18036b970`
- `0x18036f190`
- `0x180386684`
- `0x1803db91c`
- `0x1803e51b0`
- `0x1803f0ea0`
- `0x1803fc564`

## callees

- `0x18005e684`
- `0x18006b354`
- `0x18006b3c0`
- `0x180265374`
- `0x180265880`
- `0x180265be4`
- `0x1805cad98`
- `0x18077400c`
- `0x1807e1ba4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1802657c2`
- `msvcrt!memcpy_s` at `0x1802657c2`
- `KERNEL32!GetTickCount64` at `0x180265778`
- `KERNEL32!GetTickCount64` at `0x180265778`
- `KERNEL32!GetCurrentThreadId` at `0x1802655d2`
- `KERNEL32!GetCurrentThreadId` at `0x1802655d2`
- `KERNEL32!LeaveCriticalSection` at `0x18026559e`
- `KERNEL32!LeaveCriticalSection` at `0x18026559e`
- `KERNEL32!EnterCriticalSection` at `0x1802653ae`
- `KERNEL32!EnterCriticalSection` at `0x1802653ae`
- `USER32!PostMessageW` at `0x180265518`
- `USER32!PostMessageW` at `0x180265518`
- `USER32!GetWindowThreadProcessId` at `0x1802655c4`
- `USER32!GetWindowThreadProcessId` at `0x1802655c4`
- `USER32!RedrawWindow` at `0x180265584`
- `USER32!RedrawWindow` at `0x180265584`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265491`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802654a7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180265491`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802654a7`

## pseudocode

```c
__int64 __fastcall _GWPostMethodCallEx(
        struct GWND *a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  signed int LastWin32Error; // esi
  __int64 v8; // r9
  __int64 v9; // r8
  unsigned __int64 v10; // r12
  int v11; // r13d
  __int64 v12; // rbx
  __int64 v13; // r14
  unsigned int v14; // ebp
  unsigned int v15; // r15d
  __int64 v16; // r14
  __int64 v17; // rbp
  GUID v18; // xmm0
  unsigned __int64 v19; // rax
  __int64 v20; // r12
  unsigned __int64 v21; // r15
  int v22; // r13d
  DWORD WindowThreadProcessId; // ebx
  unsigned int v25; // ecx
  unsigned int v26; // ebx
  unsigned __int64 v27; // rcx
  unsigned int v28; // edx
  const void *v29; // r13
  rsize_t v30; // r12
  __int64 v31; // rax
  int i; // edx
  __int64 v33; // rcx
  __int64 v34; // rax
  unsigned int v35; // ecx
  void *v36; // rax
  int v37; // [rsp+30h] [rbp-58h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+38h] [rbp-50h]

  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 192);
  LastWin32Error = -2147467259;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 192));
  v9 = *((_QWORD *)a1 + 17);
  if ( v9 && *((_QWORD *)a1 + 12) )
  {
    v10 = a2;
    if ( !a2 && !a6 )
    {
LABEL_61:
      LastWin32Error = 0;
      goto LABEL_19;
    }
    if ( (a5 & 1) == 0 )
    {
      v8 = a4;
      for ( i = *(_DWORD *)(*((_QWORD *)a1 + 18) + 4 * (a2 % *((unsigned int *)qword_1813F3260 + *((int *)a1 + 38))));
            i >= 0;
            i = *(_DWORD *)(v34 + v33 + 56) )
      {
        v33 = *(_QWORD *)(v9 + 8);
        v34 = (__int64)i << 6;
        if ( *(_QWORD *)(v34 + v33) == a2 && *(_QWORD *)(v34 + v33 + 8) == a3 && *(_QWORD *)(v34 + v33 + 16) == a4 )
          goto LABEL_61;
      }
    }
    v11 = *(_DWORD *)(v9 + 4);
    v12 = *((int *)a1 + 38);
    v37 = v11;
    if ( v11 == *((_DWORD *)qword_1813F3260 + v12) )
    {
      MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *((void **)a1 + 18), (void *)v9);
      *((_QWORD *)a1 + 18) = 0;
      *((_DWORD *)a1 + 38) = 0;
      LastWin32Error = AllocateMethodCallBuckets(a1, (int)v12 + 1);
      if ( LastWin32Error )
        goto LABEL_19;
      RehashMethodCalls(a1);
    }
    v13 = *((_QWORD *)a1 + 17);
    v14 = v11 + 1;
    v15 = *(_DWORD *)v13 >> 2;
    if ( v11 + 1 <= v15 )
    {
      LastWin32Error = 0;
      goto LABEL_8;
    }
    if ( (v14 & 0x80000000) != 0 )
    {
      LastWin32Error = -2147024809;
      goto LABEL_19;
    }
    v26 = 4;
    if ( v14 >= 4 )
    {
      if ( v14 <= 4 )
        goto LABEL_28;
      v26 = v15 + (*(_DWORD *)v13 >> 3);
      if ( v26 < v15 )
      {
        LastWin32Error = -2147024362;
        goto LABEL_37;
      }
      if ( v14 > v26 )
LABEL_28:
        v26 = v11 + 1;
    }
    v27 = (unsigned __int64)v26 << 6;
    v28 = v26 << 6;
    if ( v27 > 0xFFFFFFFF )
      v28 = -1;
    LastWin32Error = v27 > 0xFFFFFFFF ? 0x80070216 : 0;
    if ( v27 <= 0xFFFFFFFF )
    {
      v29 = *(const void **)(v13 + 8);
      v30 = v28;
      if ( (*(_BYTE *)v13 & 2) != 0 )
      {
        v36 = (void *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, v28, 0xFFFFFFFFLL, v8);
        *(_QWORD *)(v13 + 8) = v36;
        if ( !v36 )
        {
          *(_QWORD *)(v13 + 8) = v29;
LABEL_58:
          LastWin32Error = -2147024882;
          goto LABEL_36;
        }
        memcpy_s(v36, v30, v29, v15 << 6);
      }
      else
      {
        v31 = MemoryProtection::HeapReAlloc<1>(v27, *(_QWORD *)(v13 + 8), v28);
        if ( !v31 && v30 )
          goto LABEL_58;
        *(_QWORD *)(v13 + 8) = v31;
        LastWin32Error = 0;
      }
      *(_DWORD *)v13 &= 1u;
      *(_DWORD *)v13 |= 4 * v26;
LABEL_36:
      v11 = v37;
      v10 = a2;
    }
LABEL_37:
    if ( LastWin32Error )
      goto LABEL_19;
LABEL_8:
    v16 = (__int64)v11 << 6;
    *(_DWORD *)(*((_QWORD *)a1 + 17) + 4LL) = v14;
    v17 = *(_QWORD *)(*((_QWORD *)a1 + 17) + 8LL);
    *(_QWORD *)(v16 + v17 + 8) = a3;
    *(_QWORD *)(v16 + v17 + 16) = a4;
    *(_QWORD *)(v16 + v17 + 24) = a6;
    *(_DWORD *)(v16 + v17 + 32) = a5;
    *(_QWORD *)(v16 + v17) = v10;
    *(_DWORD *)(v16 + v17 + 36) = *((_DWORD *)a1 + 32);
    if ( *((_BYTE *)GlobalThreadState() + 16)
      || (WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)a1 + 12), 0),
          WindowThreadProcessId == GetCurrentThreadId()) )
    {
      v18 = *(GUID *)GlobalThreadState();
    }
    else
    {
      v18 = GUID_NULL;
    }
    *(GUID *)(v16 + v17 + 40) = v18;
    v19 = v10;
    v20 = *((_QWORD *)a1 + 18);
    v21 = v19 % *((unsigned int *)qword_1813F3260 + *((int *)a1 + 38));
    v22 = *(_DWORD *)(v20 + 4 * v21);
    *(_DWORD *)(v16 + v17 + 56) = v22;
    *(_DWORD *)(v20 + 4 * v21) = v37;
    if ( (a5 & 2) == 0 )
    {
      if ( (unsigned __int16)*((_DWORD *)a1 + 30) )
      {
        v25 = *((unsigned __int16 *)a1 + 61);
        if ( v25 >= *((_DWORD *)a1 + 33) || (unsigned __int16)*((_DWORD *)a1 + 30) > v25 )
          goto LABEL_19;
      }
      if ( PostMessageW(*((HWND *)a1 + 12), 0x8002u, 0, 0) )
      {
        ++*((_WORD *)a1 + 60);
        goto LABEL_19;
      }
      LastWin32Error = GetLastWin32Error();
      *(_DWORD *)(*((_QWORD *)a1 + 17) + 4LL) = v37;
LABEL_63:
      *(_DWORD *)(v20 + 4 * v21) = v22;
      goto LABEL_19;
    }
    if ( *((_BYTE *)a1 + 320) )
    {
      if ( (unsigned __int16)*((_DWORD *)a1 + 31) )
      {
        v35 = *((unsigned __int16 *)a1 + 63);
        if ( (unsigned __int16)*((_DWORD *)a1 + 31) > v35 || v35 >= *((_DWORD *)a1 + 33) )
        {
          LastWin32Error = 0;
          goto LABEL_19;
        }
      }
      LastWin32Error = CGwndPaintRequest::SetupWatchdogTimer((struct GWND *)((char *)a1 + 304));
      if ( LastWin32Error >= 0 )
      {
        if ( *((_BYTE *)a1 + 322) )
        {
LABEL_18:
          RedrawWindow(*((HWND *)a1 + 12), 0, 0, 2u);
          ++*((_WORD *)a1 + 62);
          goto LABEL_19;
        }
        LastWin32Error = FormsSetCoalescableTimer(
                           (__int64)a1 + 304,
                           (__int64)CGwndPaintRequest::OnStarveCheckTimer,
                           52738,
                           300,
                           0,
                           1);
        if ( LastWin32Error >= 0 )
        {
          *((_BYTE *)a1 + 322) = 1;
          *((_QWORD *)a1 + 38) = GetTickCount64();
          *((_QWORD *)a1 + 39) = 0;
          goto LABEL_18;
        }
      }
    }
    else
    {
      LastWin32Error = -2147418113;
    }
    *(_DWORD *)(*((_QWORD *)a1 + 17) + 4LL) = v37;
    goto LABEL_63;
  }
LABEL_19:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)LastWin32Error;
}

```

## disassembly

```asm
0x180265374  mov     rax, rsp
0x180265377  mov     [rax+20h], r9
0x18026537b  mov     [rax+18h], r8
0x18026537f  mov     [rax+10h], rdx
0x180265383  mov     [rax+8], rcx
0x180265387  push    rbx
0x180265388  push    rbp
0x180265389  push    rsi
0x18026538a  push    rdi
0x18026538b  push    r12
0x18026538d  push    r13
0x18026538f  push    r14
0x180265391  push    r15
0x180265393  sub     rsp, 48h
0x180265397  lea     rax, [rcx+0C0h]
0x18026539e  mov     rdi, rcx
0x1802653a1  mov     rcx, rax; lpCriticalSection
0x1802653a4  mov     [rsp+88h+lpCriticalSection], rax
0x1802653a9  mov     esi, 80004005h
0x1802653ae  call    cs:__imp_EnterCriticalSection
0x1802653b5  nop     dword ptr [rax+rax+00h]
0x1802653ba  mov     r8, [rdi+88h]; void *
0x1802653c1  xor     ebp, ebp
0x1802653c3  test    r8, r8
0x1802653c6  jz      loc_180265599
0x1802653cc  cmp     [rdi+60h], rbp
0x1802653d0  jz      loc_180265599
0x1802653d6  mov     r12, [rsp+88h+arg_8]
0x1802653de  test    r12, r12
0x1802653e1  jz      loc_180265859
0x1802653e7  test    byte ptr [rsp+88h+arg_20], 1
0x1802653ef  lea     r11, qword_1813F3260
0x1802653f6  jz      loc_18026569C
0x1802653fc  mov     r13d, [r8+4]
0x180265400  movsxd  rbx, dword ptr [rdi+98h]
0x180265407  mov     [rsp+88h+var_58], r13d
0x18026540c  cmp     r13d, [r11+rbx*4]
0x180265410  jz      loc_180265817
0x180265416  mov     r14, [rdi+88h]
0x18026541d  lea     ebp, [r13+1]
0x180265421  mov     r15d, [r14]
0x180265424  shr     r15d, 2
0x180265428  cmp     ebp, r15d
0x18026542b  ja      loc_180265608
0x180265431  xor     esi, esi
0x180265433  mov     rax, [rdi+88h]
0x18026543a  movsxd  r14, r13d
0x18026543d  shl     r14, 6
0x180265441  mov     [rax+4], ebp
0x180265444  mov     rax, [rdi+88h]
0x18026544b  mov     rbp, [rax+8]
0x18026544f  mov     rax, [rsp+88h+arg_10]
0x180265457  mov     [r14+rbp+8], rax
0x18026545c  mov     rax, [rsp+88h+arg_18]
0x180265464  mov     [r14+rbp+10h], rax
0x180265469  mov     rax, [rsp+88h+arg_28]
0x180265471  mov     [r14+rbp+18h], rax
0x180265476  mov     eax, [rsp+88h+arg_20]
0x18026547d  mov     [r14+rbp+20h], eax
0x180265482  mov     [r14+rbp], r12
0x180265486  mov     eax, [rdi+80h]
0x18026548c  mov     [r14+rbp+24h], eax
0x180265491  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180265498  nop     dword ptr [rax+rax+00h]
0x18026549d  cmp     byte ptr [rax+10h], 0
0x1802654a1  jz      loc_1802655BE
0x1802654a7  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1802654ae  nop     dword ptr [rax+rax+00h]
0x1802654b3  movups  xmm0, xmmword ptr [rax]
0x1802654b6  movdqu  xmmword ptr [r14+rbp+28h], xmm0
0x1802654bd  movsxd  rax, dword ptr [rdi+98h]
0x1802654c4  lea     rcx, qword_1813F3260
0x1802654cb  xor     edx, edx
0x1802654cd  mov     ecx, [rcx+rax*4]
0x1802654d0  mov     rax, r12
0x1802654d3  mov     r12, [rdi+90h]
0x1802654da  div     rcx
0x1802654dd  test    byte ptr [rsp+88h+arg_20], 2
0x1802654e5  mov     r15d, edx
0x1802654e8  mov     r13d, [r12+r15*4]
0x1802654ec  mov     [r14+rbp+38h], r13d
0x1802654f1  mov     ebp, [rsp+88h+var_58]
0x1802654f5  mov     [r12+r15*4], ebp
0x1802654f9  jnz     short loc_180265537
0x1802654fb  mov     eax, [rdi+78h]
0x1802654fe  and     eax, 0FFFFh
0x180265503  jnz     loc_1802655F2
0x180265509  mov     rcx, [rdi+60h]; hWnd
0x18026550d  xor     r9d, r9d; lParam
0x180265510  xor     r8d, r8d; wParam
0x180265513  mov     edx, 8002h; Msg
0x180265518  call    cs:__imp_PostMessageW
0x18026551f  nop     dword ptr [rax+rax+00h]
0x180265524  test    eax, eax
0x180265526  jz      loc_1802657FD
0x18026552c  mov     eax, 1
0x180265531  add     [rdi+78h], ax
0x180265535  jmp     short loc_180265599
0x180265537  lea     rbx, [rdi+130h]
0x18026553e  xor     r14d, r14d
0x180265541  cmp     [rbx+10h], r14b
0x180265545  jz      loc_180265869
0x18026554b  mov     eax, [rdi+7Ch]
0x18026554e  and     eax, 0FFFFh
0x180265553  jnz     loc_1802656FD
0x180265559  mov     rcx, rbx; this
0x18026555c  call    ?SetupWatchdogTimer@CGwndPaintRequest@@AEAAJXZ; CGwndPaintRequest::SetupWatchdogTimer(void)
0x180265561  mov     esi, eax
0x180265563  test    eax, eax
0x180265565  js      loc_18026586E
0x18026556b  cmp     [rbx+12h], r14b
0x18026556f  jz      loc_180265742
0x180265575  mov     rcx, [rdi+60h]; hWnd
0x180265579  mov     r9d, 2; flags
0x18026557f  xor     r8d, r8d; hrgnUpdate
0x180265582  xor     edx, edx; lprcUpdate
0x180265584  call    cs:__imp_RedrawWindow
0x18026558b  nop     dword ptr [rax+rax+00h]
0x180265590  mov     eax, 1
0x180265595  add     [rdi+7Ch], ax
0x180265599  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x18026559e  call    cs:__imp_LeaveCriticalSection
0x1802655a5  nop     dword ptr [rax+rax+00h]
0x1802655aa  mov     eax, esi
0x1802655ac  add     rsp, 48h
0x1802655b0  pop     r15
0x1802655b2  pop     r14
0x1802655b4  pop     r13
0x1802655b6  pop     r12
0x1802655b8  pop     rdi
0x1802655b9  pop     rsi
0x1802655ba  pop     rbp
0x1802655bb  pop     rbx
0x1802655bc  retn
0x1802655be  mov     rcx, [rdi+60h]; hWnd
0x1802655c2  xor     edx, edx; lpdwProcessId
0x1802655c4  call    cs:__imp_GetWindowThreadProcessId
0x1802655cb  nop     dword ptr [rax+rax+00h]
0x1802655d0  mov     ebx, eax
0x1802655d2  call    cs:__imp_GetCurrentThreadId
0x1802655d9  nop     dword ptr [rax+rax+00h]
0x1802655de  cmp     ebx, eax
0x1802655e0  jz      loc_1802654A7
0x1802655e6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1802655ed  jmp     loc_1802654B6
0x1802655f2  movzx   ecx, word ptr [rdi+7Ah]
0x1802655f6  cmp     ecx, [rdi+84h]
0x1802655fc  jnb     short loc_180265599
0x1802655fe  cmp     eax, ecx
0x180265600  jbe     loc_180265509
0x180265606  jmp     short loc_180265599
0x180265608  test    ebp, ebp
0x18026560a  js      loc_1802657E1
0x180265610  mov     ebx, 4
0x180265615  cmp     ebp, ebx
0x180265617  jb      short loc_180265621
0x180265619  ja      loc_180265719
0x18026561f  mov     ebx, ebp
0x180265621  mov     ecx, ebx
0x180265623  mov     r8d, 0FFFFFFFFh
0x180265629  shl     rcx, 6
0x18026562d  mov     edx, ecx
0x18026562f  cmp     rcx, r8
0x180265632  ja      loc_1802656F5
0x180265638  cmp     r8, rcx
0x18026563b  mov     esi, 80070216h
0x180265640  sbb     eax, eax
0x180265642  and     esi, eax
0x180265644  cmp     rcx, r8
0x180265647  ja      short loc_18026568F
0x180265649  test    byte ptr [r14], 2
0x18026564d  mov     r13, [r14+8]
0x180265651  mov     r12d, edx
0x180265654  jnz     loc_18026579A
0x18026565a  mov     r8d, r12d
0x18026565d  mov     rdx, r13
0x180265660  call    ??$HeapReAlloc@$00@MemoryProtection@@YAPEAXPEAX0_K@Z; MemoryProtection::HeapReAlloc<1>(void *,void *,unsigned __int64)
0x180265665  test    rax, rax
0x180265668  jz      loc_180265734
0x18026566e  mov     [r14+8], rax
0x180265672  xor     esi, esi
0x180265674  and     dword ptr [r14], 1
0x180265678  lea     eax, ds:0[rbx*4]
0x18026567f  or      [r14], eax
0x180265682  mov     r13d, [rsp+88h+var_58]
0x180265687  mov     r12, [rsp+88h+arg_8]
0x18026568f  test    esi, esi
0x180265691  jz      loc_180265433
0x180265697  jmp     loc_180265599
0x18026569c  movsxd  rax, dword ptr [rdi+98h]
0x1802656a3  xor     edx, edx
0x1802656a5  mov     r9, [rsp+88h+arg_18]
0x1802656ad  mov     r10, [rsp+88h+arg_10]
0x1802656b5  mov     ecx, [r11+rax*4]
0x1802656b9  mov     rax, r12
0x1802656bc  div     rcx
0x1802656bf  mov     rax, [rdi+90h]
0x1802656c6  mov     ecx, edx
0x1802656c8  mov     edx, [rax+rcx*4]
0x1802656cb  test    edx, edx
0x1802656cd  js      loc_1802653FC
0x1802656d3  mov     rcx, [r8+8]
0x1802656d7  movsxd  rax, edx
0x1802656da  shl     rax, 6
0x1802656de  cmp     [rax+rcx], r12
0x1802656e2  jnz     short loc_1802656EF
0x1802656e4  cmp     [rax+rcx+8], r10
0x1802656e9  jz      loc_1802657EB
0x1802656ef  mov     edx, [rax+rcx+38h]
0x1802656f3  jmp     short loc_1802656CB
0x1802656f5  mov     edx, r8d
0x1802656f8  jmp     loc_180265638
0x1802656fd  movzx   ecx, word ptr [rdi+7Eh]
0x180265701  cmp     eax, ecx
0x180265703  ja      short loc_180265711
0x180265705  cmp     ecx, [rdi+84h]
0x18026570b  jb      loc_180265559
0x180265711  mov     esi, r14d
0x180265714  jmp     loc_180265599
0x180265719  mov     ebx, [r14]
0x18026571c  shr     ebx, 3
0x18026571f  add     ebx, r15d
0x180265722  cmp     ebx, r15d
0x180265725  jb      short loc_180265790
0x180265727  cmp     ebp, ebx
0x180265729  jbe     loc_180265621
0x18026572f  jmp     loc_18026561F
0x180265734  test    r12, r12
0x180265737  jz      loc_18026566E
0x18026573d  jmp     loc_1802657D7
0x180265742  mov     [rsp+88h+var_60], 1
0x18026574a  lea     rdx, ?OnStarveCheckTimer@CGwndPaintRequest@@QEAAJI@Z; CGwndPaintRequest::OnStarveCheckTimer(uint)
0x180265751  mov     r9d, 12Ch
0x180265757  mov     [rsp+88h+var_68], r14d
0x18026575c  mov     r8d, 0CE02h
0x180265762  mov     rcx, rbx
0x180265765  call    ?FormsSetCoalescableTimer@@YAJPEAXP8CVoid@@EAAJI@ZIIKW4FORMS_TIMER_SUSPEND_FLAG@@@Z; FormsSetCoalescableTimer(void *,long (CVoid::*)(uint),uint,uint,ulong,FORMS_TIMER_SUSPEND_FLAG)
0x18026576a  mov     esi, eax
0x18026576c  test    eax, eax
0x18026576e  js      loc_18026586E
0x180265774  mov     byte ptr [rbx+12h], 1
0x180265778  call    cs:__imp_GetTickCount64
0x18026577f  nop     dword ptr [rax+rax+00h]
0x180265784  mov     [rbx], rax
0x180265787  mov     [rbx+8], r14
0x18026578b  jmp     loc_180265575
0x180265790  mov     esi, 80070216h
0x180265795  jmp     loc_18026568F
0x18026579a  mov     rcx, cs:g_hProcessHeap
0x1802657a1  mov     rdx, r12
0x1802657a4  call    ??$HeapAlloc@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<1>(void *,unsigned __int64)
0x1802657a9  mov     [r14+8], rax
0x1802657ad  test    rax, rax
0x1802657b0  jz      short loc_1802657D3
0x1802657b2  shl     r15d, 6
0x1802657b6  mov     r8, r13; Source
0x1802657b9  mov     r9d, r15d; SourceSize
0x1802657bc  mov     rdx, r12; DestinationSize
0x1802657bf  mov     rcx, rax; Destination
0x1802657c2  call    cs:__imp_memcpy_s
0x1802657c9  nop     dword ptr [rax+rax+00h]
0x1802657ce  jmp     loc_180265674
0x1802657d3  mov     [r14+8], r13
0x1802657d7  mov     esi, 8007000Eh
0x1802657dc  jmp     loc_180265682
0x1802657e1  mov     esi, 80070057h
0x1802657e6  jmp     loc_180265599
0x1802657eb  cmp     [rax+rcx+10h], r9
0x1802657f0  jnz     loc_1802656EF
0x1802657f6  mov     esi, ebp
0x1802657f8  jmp     loc_180265599
0x1802657fd  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180265802  mov     rcx, [rdi+88h]
0x180265809  mov     esi, eax
0x18026580b  mov     [rcx+4], ebp
0x18026580e  mov     [r12+r15*4], r13d
0x180265812  jmp     loc_180265599
0x180265817  mov     rdx, [rdi+90h]; void *
0x18026581e  mov     rcx, cs:g_hProcessHeap; this
0x180265825  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18026582a  lea     edx, [rbx+1]; int
0x18026582d  mov     [rdi+90h], rbp
0x180265834  mov     rcx, rdi; struct GWND *
0x180265837  mov     [rdi+98h], ebp
0x18026583d  call    ?AllocateMethodCallBuckets@@YAJPEAVGWND@@H@Z; AllocateMethodCallBuckets(GWND *,int)
0x180265842  mov     esi, eax
0x180265844  test    eax, eax
0x180265846  jnz     loc_180265599
0x18026584c  mov     rcx, rdi; struct GWND *
0x18026584f  call    ?RehashMethodCalls@@YAXPEAVGWND@@@Z; RehashMethodCalls(GWND *)
0x180265854  jmp     loc_180265416
0x180265859  cmp     [rsp+88h+arg_28], rbp
0x180265861  jnz     loc_1802653E7
0x180265867  jmp     short loc_1802657F6
0x180265869  mov     esi, 8000FFFFh
0x18026586e  mov     rax, [rdi+88h]
0x180265875  mov     [rax+4], ebp
0x180265878  jmp     short loc_18026580E
```
