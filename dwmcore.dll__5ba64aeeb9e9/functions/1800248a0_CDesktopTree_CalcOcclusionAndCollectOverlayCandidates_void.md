# CDesktopTree::CalcOcclusionAndCollectOverlayCandidates(void)

- ea: `0x1800248a0`
- end: `0x180024a91`
- name: `?CalcOcclusionAndCollectOverlayCandidates@CDesktopTree@@QEAAJXZ`
- size: `497`
- prototype: `__int64 __fastcall(CDesktopTree *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024650`

## callees

- `0x1800248a0`
- `0x180024a98`
- `0x180050270`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800249e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800249e8`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800249f6`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800249f6`

## pseudocode

```c
__int64 __fastcall CDesktopTree::CalcOcclusionAndCollectOverlayCandidates(CDesktopTree *this)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  HANDLE CurrentThread; // rax
  BOOL v10; // eax
  __int64 v12[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 CycleTime; // [rsp+60h] [rbp+8h] BYREF

  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 514) - *((_QWORD *)this + 513)) >> 3) )
    *((_QWORD *)this + 514) += -8 * ((__int64)(*((_QWORD *)this + 514) - *((_QWORD *)this + 513)) >> 3);
  v2 = 0;
  if ( g_pComposition )
    v2 = *((_QWORD *)g_pComposition + 110);
  if ( *((_QWORD *)this + 15) == v2 )
  {
    v3 = 0;
    v4 = 0;
    if ( g_pComposition )
      v4 = *((_QWORD *)g_pComposition + 110);
    if ( *((_QWORD *)this + 333) != v4 )
    {
      v5 = *((_QWORD *)this + 505);
      v6 = (*((_QWORD *)this + 506) - v5) >> 3;
      v12[0] = v6;
      if ( v6 == -1 || (v12[1] = v5) == 0 && v6 )
      {
LABEL_22:
        ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
        __debugbreak();
      }
      if ( *((_BYTE *)this + 2436) )
      {
        if ( this == (CDesktopTree *)-2420LL )
          goto LABEL_22;
      }
      else if ( this == (CDesktopTree *)-132LL && MEMORY[0xFFFFFFFFFFFFFFFC] )
      {
        goto LABEL_22;
      }
      v7 = COcclusionContext::Compute((CDesktopTree *)((char *)this + 2648), this, (__int64)v12);
      v3 = v7;
      if ( v7 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, 0x9Au, 0);
    }
    v8 = 0;
    CycleTime = 0;
    if ( ::CycleTime )
    {
      CurrentThread = GetCurrentThread();
      v10 = QueryThreadCycleTime(CurrentThread, &CycleTime);
      v8 = CycleTime;
      if ( v10 )
        qword_1803BADD8 += CycleTime - ::CycleTime;
    }
    ::CycleTime = v8;
  }
  else
  {
    v3 = -2003292412;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2003292412, 0xA1u, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x1800248a0  push    rdi
0x1800248a2  sub     rsp, 50h
0x1800248a6  mov     rax, [rcx+1010h]
0x1800248ad  mov     rdx, rcx; struct CVisualTree *
0x1800248b0  sub     rax, [rcx+1008h]
0x1800248b7  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800248c1  sar     rax, 3
0x1800248c5  imul    rax, rcx
0x1800248c9  test    rax, rax
0x1800248cc  jz      short loc_1800248D9
0x1800248ce  imul    rax, -28h
0x1800248d2  add     [rdx+1010h], rax
0x1800248d9  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800248e0  xor     edi, edi
0x1800248e2  mov     ecx, edi
0x1800248e4  test    rax, rax
0x1800248e7  jz      short loc_1800248F0
0x1800248e9  mov     rcx, [rax+370h]
0x1800248f0  mov     [rsp+58h+arg_8], rbx
0x1800248f5  cmp     [rdx+78h], rcx
0x1800248f9  jnz     loc_180024A2A
0x1800248ff  mov     ebx, edi
0x180024901  mov     rcx, rdi
0x180024904  test    rax, rax
0x180024907  jz      short loc_180024910
0x180024909  mov     rcx, [rax+370h]
0x180024910  cmp     [rdx+0A68h], rcx
0x180024917  jz      loc_1800249D7
0x18002491d  cmp     [rdx+984h], bl
0x180024923  jnz     short loc_180024936
0x180024925  movss   xmm3, dword ptr [rdx+0A20h]
0x18002492d  comiss  xmm3, cs:__real@3f800000
0x180024934  ja      short loc_180024939
0x180024936  xorps   xmm3, xmm3
0x180024939  mov     rcx, [rdx+0FC8h]
0x180024940  mov     rax, [rdx+0FD0h]
0x180024947  sub     rax, rcx
0x18002494a  sar     rax, 3
0x18002494e  mov     [rsp+58h+var_18], rax
0x180024953  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024957  jz      loc_180024A6E
0x18002495d  mov     [rsp+58h+var_10], rcx
0x180024962  test    rcx, rcx
0x180024965  jz      loc_180024A86
0x18002496b  cmp     [rdx+984h], bl
0x180024971  jnz     loc_180024A50
0x180024977  mov     ecx, [rdx+80h]
0x18002497d  lea     rax, [rdx+84h]
0x180024984  mov     [rsp+58h+var_28], rcx
0x180024989  mov     [rsp+58h+var_20], rax
0x18002498e  test    rax, rax
0x180024991  jz      loc_180024A7B
0x180024997  lea     rax, [rsp+58h+var_18]
0x18002499c  lea     rcx, [rdx+0A58h]; this
0x1800249a3  mov     qword ptr [rsp+58h+var_38], rax; __int64
0x1800249a8  lea     r8, [rsp+58h+var_28]
0x1800249ad  call    ?Compute@COcclusionContext@@IEAAJPEBVCVisualTree@@AEBV?$span@$$CBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@$0?0@gsl@@MAEBV?$span@PEAVCOverlayContext@@$0?0@4@@Z; COcclusionContext::Compute(CVisualTree const *,gsl::span<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const,-1> const &,float,gsl::span<COverlayContext *,-1> const &)
0x1800249b2  mov     ebx, eax
0x1800249b4  test    eax, eax
0x1800249b6  jns     short loc_1800249D7
0x1800249b8  mov     [rsp+58h+var_30], rdi; void *
0x1800249bd  mov     r9d, eax; int
0x1800249c0  xor     r8d, r8d; unsigned int
0x1800249c3  mov     [rsp+58h+var_38], 9Ah; unsigned int
0x1800249cb  xor     edx, edx; int *
0x1800249cd  mov     ecx, 14h; unsigned int
0x1800249d2  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800249d7  mov     rcx, rdi
0x1800249da  cmp     cs:CycleTime, rcx
0x1800249e1  mov     [rsp+58h+CycleTime], rcx
0x1800249e6  jz      short loc_180024A16
0x1800249e8  call    cs:__imp_GetCurrentThread
0x1800249ee  mov     rcx, rax; ThreadHandle
0x1800249f1  lea     rdx, [rsp+58h+CycleTime]; CycleTime
0x1800249f6  call    cs:__imp_QueryThreadCycleTime
0x1800249fc  mov     rcx, [rsp+58h+CycleTime]
0x180024a01  test    eax, eax
0x180024a03  jz      short loc_180024A16
0x180024a05  mov     rax, rcx
0x180024a08  sub     rax, cs:CycleTime
0x180024a0f  add     cs:qword_1803BADD8, rax
0x180024a16  mov     cs:CycleTime, rcx
0x180024a1d  mov     eax, ebx
0x180024a1f  mov     rbx, [rsp+58h+arg_8]
0x180024a24  add     rsp, 50h
0x180024a28  pop     rdi
0x180024a29  retn
0x180024a2a  mov     ebx, 88982F04h
0x180024a2f  mov     [rsp+58h+var_30], rdi; void *
0x180024a34  mov     r9d, ebx; int
0x180024a37  mov     [rsp+58h+var_38], 0A1h; unsigned int
0x180024a3f  xor     r8d, r8d; unsigned int
0x180024a42  xor     edx, edx; int *
0x180024a44  mov     ecx, 14h; unsigned int
0x180024a49  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180024a4e  jmp     short loc_180024A1D
0x180024a50  lea     rax, [rdx+974h]
0x180024a57  mov     [rsp+58h+var_28], 1
0x180024a60  mov     [rsp+58h+var_20], rax
0x180024a65  test    rax, rax
0x180024a68  jnz     loc_180024997
0x180024a6e  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x180024a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a7a  int     3; Trap to Debugger
0x180024a7b  test    rcx, rcx
0x180024a7e  jz      loc_180024997
0x180024a84  jmp     short loc_180024A6E
0x180024a86  test    rax, rax
0x180024a89  jz      loc_18002496B
0x180024a8f  jmp     short loc_180024A6E
```
