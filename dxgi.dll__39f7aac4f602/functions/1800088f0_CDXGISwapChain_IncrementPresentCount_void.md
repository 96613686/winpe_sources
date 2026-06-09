# CDXGISwapChain::IncrementPresentCount(void)

- ea: `0x1800088f0`
- end: `0x180008d35`
- name: `?IncrementPresentCount@CDXGISwapChain@@QEAAXXZ`
- size: `1093`
- prototype: `void __fastcall(CDXGISwapChain *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180008d40`
- `0x18000ec08`

## callees

- `0x1800084f8`
- `0x180008680`
- `0x180008730`
- `0x1800088f0`
- `0x180011db0`
- `0x180071814`
- `0x180075fa0`
- `0x180076f20`
- `0x1800a3a70`
- `0x1800a3ebc`

## import_xrefs

- `win32u!NtQueryCompositionSurfaceStatistics` at `0x180008a19`
- `win32u!NtQueryCompositionSurfaceStatistics` at `0x180008a19`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008b02`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008b02`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x180008c6b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x180008c6b`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180008bba`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x180008bba`

## pseudocode

```c
void __fastcall CDXGISwapChain::IncrementPresentCount(CDXGISwapChain *this, const struct _tlgProvider_t *a2)
{
  _DWORD *v3; // rsi
  unsigned __int64 v4; // rcx
  _DWORD *v5; // rdi
  int v6; // eax
  char v7; // al
  __int128 v8; // xmm0
  char v9; // al
  char v10; // al
  CDXGITelemetryHelper *v11; // rcx
  int v12; // edx
  int v13; // r14d
  int v14; // r15d
  int v15; // r14d
  int v16; // eax
  int v17; // r8d
  int v18; // edx
  __int64 v19; // r12
  bool v20; // zf
  int *v21; // rax
  HWND v22; // rcx
  LARGE_INTEGER PerformanceCount[2]; // [rsp+28h] [rbp-39h] BYREF
  __int64 v24; // [rsp+38h] [rbp-29h] BYREF
  int v25; // [rsp+40h] [rbp-21h]
  int v26; // [rsp+44h] [rbp-1Dh]
  int v27; // [rsp+48h] [rbp-19h]
  char v28; // [rsp+4Ch] [rbp-15h]
  char v29; // [rsp+4Dh] [rbp-14h]
  char v30; // [rsp+4Eh] [rbp-13h]
  char v31; // [rsp+4Fh] [rbp-12h]
  int v32; // [rsp+50h] [rbp-11h]
  bool v33; // [rsp+54h] [rbp-Dh]
  char v34; // [rsp+55h] [rbp-Ch]
  __int16 v35; // [rsp+56h] [rbp-Bh]
  __int128 v36; // [rsp+58h] [rbp-9h]
  int v37; // [rsp+70h] [rbp+Fh]

  ++*((_DWORD *)this + 393);
  if ( byte_180109BBC || (qword_180109BB0 & 3) == 1 )
    GPMHelper::NotifyPerformanceMonitor(
      (GPMHelper *)qword_180109A90,
      a2,
      *((_DWORD *)this + 393),
      *(struct _LUID *)((char *)this + 920));
  v3 = 0;
  v4 = *((unsigned int *)this + 393);
  if ( (_DWORD)v4 == *((_DWORD *)this + 1183) + 1000 && *((_BYTE *)this + 2530) && *((_BYTE *)this + 2121) )
  {
    *((_BYTE *)this + 4736) = 1;
    if ( *((_BYTE *)this + 2531) )
      v3 = (_DWORD *)((char *)this + 4740);
    else
      v3 = (_DWORD *)((char *)this + 4756);
  }
  v5 = (_DWORD *)((char *)this + 4716);
  if ( (_DWORD)v4 != 1000 * ((unsigned int)v4 / 0x3E8) )
    v5 = 0;
  if ( v3 || v5 )
  {
    memset_0(&v24, 0, 0x50u);
    v6 = NtQueryCompositionSurfaceStatistics(*((_QWORD *)this + 153), &v24);
    if ( (int)HRESULTFromNTSTATUS(v6) >= 0 )
    {
      if ( *((_DWORD *)this + 111) == 1 )
      {
        v19 = 3744;
        if ( !CDXGISwapChain::UseProxyFlip(this) )
          v19 = 1944;
        v20 = !CDXGISwapChain::UseProxyFlip(this);
        v21 = (int *)((char *)this + 3780);
        if ( v20 )
          v21 = (int *)((char *)this + 2020);
        v12 = v21[6];
        v13 = v21[1];
        if ( v12 == 2 || (v14 = *v21, v12 == 4) )
        {
          v14 = v21[1];
          v13 = *v21;
        }
        if ( *(_DWORD *)((char *)this + v19) == v14 && *(_DWORD *)((char *)this + v19 + 4) == v13 )
        {
          v7 = 1;
          if ( *((_DWORD *)this + 82) != 2 )
            goto LABEL_29;
          v22 = (HWND)*((_QWORD *)this + 42);
          *(_OWORD *)&PerformanceCount[0].LowPart = 0;
          if ( GetWindowRect(v22, (LPRECT)PerformanceCount)
            && PerformanceCount[1].LowPart - PerformanceCount[0].LowPart == v14
            && PerformanceCount[1].HighPart - PerformanceCount[0].HighPart == v13 )
          {
            v7 = 1;
            goto LABEL_29;
          }
        }
        v7 = 0;
      }
      else
      {
        v7 = 1;
      }
LABEL_29:
      v15 = 0;
      if ( v37 )
      {
        v17 = 0;
        if ( v7 )
        {
          v16 = 1;
          v18 = 0;
        }
        else
        {
          v16 = 0;
          v18 = 1;
        }
        v4 = 0;
      }
      else
      {
        if ( v7 )
        {
          v4 = 0;
          v15 = 1;
        }
        else
        {
          v4 = GetForegroundWindow() == *((HWND *)this + 42);
        }
        v16 = 0;
        v17 = v4;
        v18 = 0;
      }
      if ( v3 )
      {
        *v3 += v16;
        v3[1] += v15;
        v3[2] += v18;
        v3[3] += v4;
      }
      if ( v5 )
      {
        *v5 += v16;
        v5[1] += v15;
        v5[2] += v18;
        v5[3] += v17;
      }
    }
  }
  if ( *((_DWORD *)this + 393) == 1000 )
  {
    v8 = *(_OWORD *)((char *)this + 4716);
    v25 = 1000;
    v31 = 0;
    v34 = 0;
    v26 = *((_DWORD *)this + 394);
    v27 = *((_DWORD *)this + 1145);
    v24 = *((_QWORD *)this + 115);
    v9 = *((_BYTE *)this + 3920) & 1;
    v28 = 0;
    v29 = v9;
    v10 = *((_BYTE *)this + 3944);
    v33 = dword_180109B8C != 0;
    v30 = v10;
    v32 = *((_DWORD *)this + 1011);
    v35 = dword_180109BA6;
    v36 = v8;
    CDXGITelemetryHelper::LogSwapChainStatus(
      (CDXGITelemetryHelper *)v4,
      (const struct CDXGITelemetryHelper::SwapChainStatus *)&v24);
    if ( *((_DWORD *)this + 82) == 2 && *((_DWORD *)this + 1145) )
    {
      PerformanceCount[0] = *(LARGE_INTEGER *)((char *)this + 920);
      CDXGITelemetryHelper::LogFullscreenPresentInfo(
        v11,
        (const struct _LUID *)PerformanceCount,
        (CDXGISwapChain *)((char *)this + 4584));
    }
    if ( *((_BYTE *)this + 4736) )
    {
      PerformanceCount[0] = *(LARGE_INTEGER *)((char *)this + 920);
      CDXGITelemetryHelper::LogHybridScanOutInfo(
        v11,
        (const struct _LUID *)PerformanceCount,
        (CDXGISwapChain *)((char *)this + 4736));
    }
  }
  if ( *((_DWORD *)this + 1112) )
  {
    PerformanceCount[0].QuadPart = 0;
    QueryPerformanceCounter(PerformanceCount);
    if ( (double)(PerformanceCount[0].LowPart - *((_DWORD *)this + 1114))
       / (double)(int)*((_QWORD *)this + 281)
       * 1000.0 >= 2000.0 )
    {
      CDXGISwapChain::ShowNotification(this, *((_DWORD *)this + 1112));
      *((_DWORD *)this + 1112) = 0;
    }
  }
}

```

## disassembly

```asm
0x1800088f0  mov     r11, rsp
0x1800088f3  push    rbp
0x1800088f4  push    rbx
0x1800088f5  lea     rbp, [r11-5Fh]
0x1800088f9  sub     rsp, 0A8h
0x180008900  mov     rax, cs:__security_cookie
0x180008907  xor     rax, rsp
0x18000890a  mov     [rbp+57h+var_30], rax
0x18000890e  inc     dword ptr [rcx+624h]
0x180008914  mov     rbx, rcx
0x180008917  mov     eax, dword ptr cs:qword_180109BB0
0x18000891d  and     al, 3
0x18000891f  mov     [r11+10h], rsi
0x180008923  cmp     cs:byte_180109BBC, 0
0x18000892a  mov     [r11+18h], rdi
0x18000892e  jz      loc_180008B5E
0x180008934  mov     r9, [rcx+398h]; struct _LUID
0x18000893b  mov     r8d, [rcx+624h]; unsigned int
0x180008942  lea     rcx, qword_180109A90; this
0x180008949  call    ?NotifyPerformanceMonitor@GPMHelper@@QEAAXPEBU_tlgProvider_t@@IU_LUID@@@Z; GPMHelper::NotifyPerformanceMonitor(_tlgProvider_t const *,uint,_LUID)
0x18000894e  mov     eax, [rbx+127Ch]
0x180008954  xor     esi, esi
0x180008956  mov     ecx, [rbx+624h]; this
0x18000895c  add     eax, 3E8h
0x180008961  cmp     ecx, eax
0x180008963  jnz     short loc_180008992
0x180008965  cmp     [rbx+9E2h], sil
0x18000896c  jz      short loc_180008992
0x18000896e  cmp     [rbx+849h], sil
0x180008975  jz      short loc_180008992
0x180008977  mov     byte ptr [rbx+1280h], 1
0x18000897e  cmp     [rbx+9E3h], sil
0x180008985  jz      loc_180008C9E
0x18000898b  lea     rsi, [rbx+1284h]
0x180008992  mov     eax, 10624DD3h
0x180008997  lea     rdi, [rbx+126Ch]
0x18000899e  mul     ecx
0x1800089a0  shr     edx, 6
0x1800089a3  imul    eax, edx, 3E8h
0x1800089a9  cmp     ecx, eax
0x1800089ab  mov     eax, 0
0x1800089b0  cmovnz  rdi, rax
0x1800089b4  test    rsi, rsi
0x1800089b7  jnz     short loc_1800089FD
0x1800089b9  test    rdi, rdi
0x1800089bc  jnz     short loc_1800089FD
0x1800089be  cmp     dword ptr [rbx+624h], 3E8h
0x1800089c8  mov     rdi, [rsp+0B0h+arg_10]
0x1800089d0  mov     rsi, [rsp+0B0h+arg_8]
0x1800089d8  jz      short loc_180008A46
0x1800089da  cmp     dword ptr [rbx+1160h], 0
0x1800089e1  jnz     loc_180008AF6
0x1800089e7  mov     rcx, [rbp+57h+var_30]
0x1800089eb  xor     rcx, rsp; StackCookie
0x1800089ee  call    __security_check_cookie
0x1800089f3  add     rsp, 0A8h
0x1800089fa  pop     rbx
0x1800089fb  pop     rbp
0x1800089fc  retn
0x1800089fd  xor     edx, edx; Val
0x1800089ff  lea     rcx, [rbp+57h+var_80]; void *
0x180008a03  mov     r8d, 50h ; 'P'; Size
0x180008a09  call    memset_0
0x180008a0e  mov     rcx, [rbx+4C8h]
0x180008a15  lea     rdx, [rbp+57h+var_80]
0x180008a19  call    cs:__imp_NtQueryCompositionSurfaceStatistics
0x180008a1f  mov     ecx, eax; int
0x180008a21  call    ?HRESULTFromNTSTATUS@@YAJJ@Z; HRESULTFromNTSTATUS(long)
0x180008a26  test    eax, eax
0x180008a28  js      short loc_1800089BE
0x180008a2a  cmp     dword ptr [rbx+1BCh], 1
0x180008a31  mov     [rsp+0B0h+var_18], r14
0x180008a39  jz      loc_180008BFE
0x180008a3f  mov     al, 1
0x180008a41  jmp     loc_180008BA5
0x180008a46  movups  xmm0, xmmword ptr [rbx+126Ch]
0x180008a4d  xor     eax, eax
0x180008a4f  mov     [rbp+57h+var_78], 3E8h
0x180008a56  mov     [rbp+57h+var_69], al
0x180008a59  lea     rdx, [rbp+57h+var_80]; struct CDXGITelemetryHelper::SwapChainStatus *
0x180008a5d  mov     [rbp+57h+var_63], al
0x180008a60  mov     eax, [rbx+628h]
0x180008a66  mov     [rbp+57h+var_74], eax
0x180008a69  mov     eax, [rbx+11E4h]
0x180008a6f  mov     [rbp+57h+var_70], eax
0x180008a72  mov     rax, [rbx+398h]
0x180008a79  mov     [rbp+57h+var_80], rax
0x180008a7d  movzx   eax, byte ptr [rbx+0F50h]
0x180008a84  and     al, 1
0x180008a86  mov     [rbp+57h+var_6C], 0
0x180008a8a  cmp     cs:dword_180109B8C, 0
0x180008a91  mov     [rbp+57h+var_6B], al
0x180008a94  movzx   eax, byte ptr [rbx+0F68h]
0x180008a9b  setnz   [rbp+57h+var_64]
0x180008a9f  mov     [rbp+57h+var_6A], al
0x180008aa2  mov     eax, [rbx+0FCCh]
0x180008aa8  mov     [rbp+57h+var_68], eax
0x180008aab  movzx   eax, word ptr cs:dword_180109BA6
0x180008ab2  mov     [rbp+57h+var_62], ax
0x180008ab6  movups  [rbp+57h+var_60], xmm0
0x180008aba  call    ?LogSwapChainStatus@CDXGITelemetryHelper@@QEAAXAEBUSwapChainStatus@1@@Z; CDXGITelemetryHelper::LogSwapChainStatus(CDXGITelemetryHelper::SwapChainStatus const &)
0x180008abf  cmp     dword ptr [rbx+148h], 2
0x180008ac6  jz      loc_180008D08
0x180008acc  lea     r8, [rbx+1280h]; struct HybridScanOutTelemetryInfo *
0x180008ad3  cmp     byte ptr [r8], 0
0x180008ad7  jz      loc_1800089DA
0x180008add  mov     rax, [rbx+398h]
0x180008ae4  lea     rdx, [rbp+57h+PerformanceCount]; struct _LUID *
0x180008ae8  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x180008aec  call    ?LogHybridScanOutInfo@CDXGITelemetryHelper@@QEAAXAEBU_LUID@@AEBUHybridScanOutTelemetryInfo@@@Z; CDXGITelemetryHelper::LogHybridScanOutInfo(_LUID const &,HybridScanOutTelemetryInfo const &)
0x180008af1  jmp     loc_1800089DA
0x180008af6  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180008afa  mov     qword ptr [rbp+57h+PerformanceCount], 0
0x180008b02  call    cs:__imp_QueryPerformanceCounter
0x180008b08  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x180008b0c  xorps   xmm1, xmm1
0x180008b0f  sub     rax, [rbx+1168h]
0x180008b16  xorps   xmm0, xmm0
0x180008b19  cvtsi2sd xmm0, qword ptr [rbx+8C8h]
0x180008b22  cvtsi2sd xmm1, rax
0x180008b27  divsd   xmm1, xmm0
0x180008b2b  mulsd   xmm1, cs:__real@408f400000000000
0x180008b33  comisd  xmm1, cs:__real@409f400000000000
0x180008b3b  jb      loc_1800089E7
0x180008b41  mov     edx, [rbx+1160h]; unsigned int
0x180008b47  mov     rcx, rbx; this
0x180008b4a  call    ?ShowNotification@CDXGISwapChain@@AEAAXK@Z; CDXGISwapChain::ShowNotification(ulong)
0x180008b4f  mov     dword ptr [rbx+1160h], 0
0x180008b59  jmp     loc_1800089E7
0x180008b5e  cmp     al, 1
0x180008b60  jz      loc_180008934
0x180008b66  jmp     loc_18000894E
0x180008b6b  mov     edx, [rax+18h]
0x180008b6e  mov     ecx, [rax]
0x180008b70  mov     r14d, [rax+4]
0x180008b74  cmp     edx, 2
0x180008b77  jz      loc_180008CAA
0x180008b7d  mov     r15d, ecx
0x180008b80  cmp     edx, 4
0x180008b83  jz      loc_180008CAA
0x180008b89  cmp     [r12+rbx], r15d
0x180008b8d  jz      loc_180008CB5
0x180008b93  xor     al, al
0x180008b95  mov     r12, [rsp+0A0h]
0x180008b9d  mov     r15, [rsp+0B0h+var_20]
0x180008ba5  xor     r14d, r14d
0x180008ba8  cmp     [rbp+57h+var_48], r14d
0x180008bac  jnz     loc_180008CD9
0x180008bb2  test    al, al
0x180008bb4  jnz     loc_180008CC2
0x180008bba  call    cs:__imp_GetForegroundWindow
0x180008bc0  xor     ecx, ecx
0x180008bc2  cmp     rax, [rbx+150h]
0x180008bc9  jz      loc_180008CCF
0x180008bcf  xor     eax, eax
0x180008bd1  mov     r8d, ecx
0x180008bd4  xor     edx, edx
0x180008bd6  test    rsi, rsi
0x180008bd9  jnz     loc_180008CF7
0x180008bdf  test    rdi, rdi
0x180008be2  jz      short loc_180008BF1
0x180008be4  add     [rdi], eax
0x180008be6  add     [rdi+4], r14d
0x180008bea  add     [rdi+8], edx
0x180008bed  add     [rdi+0Ch], r8d
0x180008bf1  mov     r14, [rsp+0B0h+var_18]
0x180008bf9  jmp     loc_1800089BE
0x180008bfe  mov     [rsp+0A0h], r12
0x180008c06  mov     rcx, rbx; this
0x180008c09  mov     [rsp+0B0h+var_20], r15
0x180008c11  call    ?UseProxyFlip@CDXGISwapChain@@AEBA_NXZ; CDXGISwapChain::UseProxyFlip(void)
0x180008c16  test    al, al
0x180008c18  mov     ecx, 798h
0x180008c1d  mov     r12d, 0EA0h
0x180008c23  cmovz   r12d, ecx
0x180008c27  mov     rcx, rbx; this
0x180008c2a  call    ?UseProxyFlip@CDXGISwapChain@@AEBA_NXZ; CDXGISwapChain::UseProxyFlip(void)
0x180008c2f  test    al, al
0x180008c31  lea     rax, [rbx+0EC4h]
0x180008c38  jnz     loc_180008B6B
0x180008c3e  lea     rax, [rbx+7E4h]
0x180008c45  jmp     loc_180008B6B
0x180008c4a  cmp     dword ptr [rbx+148h], 2
0x180008c51  mov     al, 1
0x180008c53  jnz     loc_180008B95
0x180008c59  mov     rcx, [rbx+150h]; hWnd
0x180008c60  lea     rdx, [rbp+57h+PerformanceCount]; lpRect
0x180008c64  xorps   xmm0, xmm0
0x180008c67  movups  xmmword ptr [rbp+57h+PerformanceCount], xmm0
0x180008c6b  call    cs:__imp_GetWindowRect
0x180008c71  test    eax, eax
0x180008c73  jz      loc_180008B93
0x180008c79  mov     eax, dword ptr [rbp+57h+PerformanceCount+8]
0x180008c7c  sub     eax, dword ptr [rbp+57h+PerformanceCount]
0x180008c7f  cmp     eax, r15d
0x180008c82  jnz     loc_180008B93
0x180008c88  mov     eax, dword ptr [rbp+57h+PerformanceCount+0Ch]
0x180008c8b  sub     eax, dword ptr [rbp+57h+PerformanceCount+4]
0x180008c8e  cmp     eax, r14d
0x180008c91  jnz     loc_180008B93
0x180008c97  mov     al, 1
0x180008c99  jmp     loc_180008B95
0x180008c9e  lea     rsi, [rbx+1294h]
0x180008ca5  jmp     loc_180008992
0x180008caa  mov     r15d, r14d
0x180008cad  mov     r14d, ecx
0x180008cb0  jmp     loc_180008B89
0x180008cb5  cmp     [r12+rbx+4], r14d
0x180008cba  jnz     loc_180008B93
0x180008cc0  jmp     short loc_180008C4A
0x180008cc2  xor     ecx, ecx
0x180008cc4  mov     r14d, 1
0x180008cca  jmp     loc_180008BCF
0x180008ccf  mov     ecx, 1
0x180008cd4  jmp     loc_180008BCF
0x180008cd9  xor     r8d, r8d
0x180008cdc  test    al, al
0x180008cde  jz      short loc_180008CE9
0x180008ce0  mov     eax, 1
0x180008ce5  xor     edx, edx
0x180008ce7  jmp     short loc_180008CF0
0x180008ce9  xor     eax, eax
0x180008ceb  mov     edx, 1
0x180008cf0  xor     ecx, ecx
0x180008cf2  jmp     loc_180008BD6
0x180008cf7  add     [rsi], eax
0x180008cf9  add     [rsi+4], r14d
0x180008cfd  add     [rsi+8], edx
0x180008d00  add     [rsi+0Ch], ecx
0x180008d03  jmp     loc_180008BDF
0x180008d08  cmp     dword ptr [rbx+11E4h], 0
0x180008d0f  jbe     loc_180008ACC
0x180008d15  mov     rax, [rbx+398h]
0x180008d1c  lea     r8, [rbx+11E8h]; struct FullscreenPresentInfo *
0x180008d23  lea     rdx, [rbp+57h+PerformanceCount]; struct _LUID *
0x180008d27  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x180008d2b  call    ?LogFullscreenPresentInfo@CDXGITelemetryHelper@@QEAAXAEBU_LUID@@AEBUFullscreenPresentInfo@@@Z; CDXGITelemetryHelper::LogFullscreenPresentInfo(_LUID const &,FullscreenPresentInfo const &)
0x180008d30  jmp     loc_180008ACC
```
