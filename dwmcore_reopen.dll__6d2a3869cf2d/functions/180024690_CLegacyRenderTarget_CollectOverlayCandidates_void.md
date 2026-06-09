# CLegacyRenderTarget::CollectOverlayCandidates(void)

- ea: `0x180024690`
- end: `0x180024896`
- name: `?CollectOverlayCandidates@CLegacyRenderTarget@@UEBAPEAVCOverlayContext@@XZ`
- size: `518`
- prototype: `struct COverlayContext *__fastcall(CLegacyRenderTarget *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180024690`
- `0x180024a98`
- `0x180050270`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800247ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800247ee`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800247fc`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800247fc`

## pseudocode

```c
struct COverlayContext *__fastcall CLegacyRenderTarget::CollectOverlayCandidates(CLegacyRenderTarget *this)
{
  __int64 v2; // rdx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  unsigned __int64 v9; // rcx
  HANDLE CurrentThread; // rax
  BOOL v11; // eax
  __int64 v12[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 CycleTime; // [rsp+60h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 5) )
    return 0;
  v2 = *((_QWORD *)this + 3);
  if ( !v2 )
    return 0;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)(v2 + 4112) - *(_QWORD *)(v2 + 4104)) >> 3) )
    *(_QWORD *)(v2 + 4112) += -8 * ((__int64)(*(_QWORD *)(v2 + 4112) - *(_QWORD *)(v2 + 4104)) >> 3);
  v4 = 0;
  if ( g_pComposition )
    v4 = *((_QWORD *)g_pComposition + 110);
  if ( *(_QWORD *)(v2 + 120) == v4 )
  {
    v5 = 0;
    if ( g_pComposition )
      v5 = *((_QWORD *)g_pComposition + 110);
    if ( *(_QWORD *)(v2 + 2664) != v5 )
    {
      v6 = *(_QWORD *)(v2 + 4040);
      v7 = (*(_QWORD *)(v2 + 4048) - v6) >> 3;
      v12[0] = v7;
      if ( v7 == -1 || (v12[1] = v6) == 0 && v7 )
      {
LABEL_25:
        ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
        __debugbreak();
      }
      if ( *(_BYTE *)(v2 + 2436) )
      {
        if ( v2 == -2420 )
          goto LABEL_25;
      }
      else if ( v2 == -132 && MEMORY[0xFFFFFFFFFFFFFFFC] )
      {
        goto LABEL_25;
      }
      v8 = COcclusionContext::Compute((COcclusionContext *)(v2 + 2648), (struct CVisualTree *)v2, (__int64)v12);
      if ( v8 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x9Au, 0);
    }
    v9 = 0;
    CycleTime = 0;
    if ( ::CycleTime )
    {
      CurrentThread = GetCurrentThread();
      v11 = QueryThreadCycleTime(CurrentThread, &CycleTime);
      v9 = CycleTime;
      if ( v11 )
        qword_1803BADD8 += CycleTime - ::CycleTime;
    }
    ::CycleTime = v9;
  }
  else
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2003292412, 0xA1u, 0);
  }
  return (CLegacyRenderTarget *)((char *)this + 56);
}

```

## disassembly

```asm
0x180024690  push    rbx
0x180024692  sub     rsp, 50h
0x180024696  cmp     qword ptr [rcx+28h], 0
0x18002469b  mov     rbx, rcx
0x18002469e  jz      short loc_1800246A9
0x1800246a0  mov     rdx, [rcx+18h]; struct CVisualTree *
0x1800246a4  test    rdx, rdx
0x1800246a7  jnz     short loc_1800246B1
0x1800246a9  xor     eax, eax
0x1800246ab  add     rsp, 50h
0x1800246af  pop     rbx
0x1800246b0  retn
0x1800246b1  mov     rax, [rdx+1010h]
0x1800246b8  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800246c2  sub     rax, [rdx+1008h]
0x1800246c9  sar     rax, 3
0x1800246cd  imul    rax, rcx
0x1800246d1  mov     [rsp+58h+arg_8], rdi
0x1800246d6  test    rax, rax
0x1800246d9  jz      short loc_1800246E6
0x1800246db  imul    rax, -28h
0x1800246df  add     [rdx+1010h], rax
0x1800246e6  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800246ed  xor     edi, edi
0x1800246ef  mov     ecx, edi
0x1800246f1  test    rax, rax
0x1800246f4  jz      short loc_1800246FD
0x1800246f6  mov     rcx, [rax+370h]
0x1800246fd  cmp     [rdx+78h], rcx
0x180024701  jnz     loc_180024831
0x180024707  mov     rcx, rdi
0x18002470a  test    rax, rax
0x18002470d  jz      short loc_180024716
0x18002470f  mov     rcx, [rax+370h]
0x180024716  cmp     [rdx+0A68h], rcx
0x18002471d  jz      loc_1800247DD
0x180024723  cmp     [rdx+984h], dil
0x18002472a  jnz     short loc_18002473D
0x18002472c  movss   xmm3, dword ptr [rdx+0A20h]
0x180024734  comiss  xmm3, cs:__real@3f800000
0x18002473b  ja      short loc_180024740
0x18002473d  xorps   xmm3, xmm3
0x180024740  mov     rcx, [rdx+0FC8h]
0x180024747  mov     rax, [rdx+0FD0h]
0x18002474e  sub     rax, rcx
0x180024751  sar     rax, 3
0x180024755  mov     [rsp+58h+var_18], rax
0x18002475a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002475e  jz      loc_180024873
0x180024764  mov     [rsp+58h+var_10], rcx
0x180024769  test    rcx, rcx
0x18002476c  jz      loc_18002488B
0x180024772  cmp     [rdx+984h], dil
0x180024779  jnz     loc_180024855
0x18002477f  mov     ecx, [rdx+80h]
0x180024785  lea     rax, [rdx+84h]
0x18002478c  mov     [rsp+58h+var_28], rcx
0x180024791  mov     [rsp+58h+var_20], rax
0x180024796  test    rax, rax
0x180024799  jz      loc_180024880
0x18002479f  lea     rax, [rsp+58h+var_18]
0x1800247a4  lea     rcx, [rdx+0A58h]; this
0x1800247ab  mov     qword ptr [rsp+58h+var_38], rax; __int64
0x1800247b0  lea     r8, [rsp+58h+var_28]
0x1800247b5  call    ?Compute@COcclusionContext@@IEAAJPEBVCVisualTree@@AEBV?$span@$$CBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@$0?0@gsl@@MAEBV?$span@PEAVCOverlayContext@@$0?0@4@@Z; COcclusionContext::Compute(CVisualTree const *,gsl::span<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const,-1> const &,float,gsl::span<COverlayContext *,-1> const &)
0x1800247ba  test    eax, eax
0x1800247bc  jns     short loc_1800247DD
0x1800247be  mov     [rsp+58h+var_30], rdi; void *
0x1800247c3  mov     r9d, eax; int
0x1800247c6  xor     r8d, r8d; unsigned int
0x1800247c9  mov     [rsp+58h+var_38], 9Ah; unsigned int
0x1800247d1  xor     edx, edx; int *
0x1800247d3  mov     ecx, 14h; unsigned int
0x1800247d8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800247dd  mov     rcx, rdi
0x1800247e0  cmp     cs:CycleTime, rcx
0x1800247e7  mov     [rsp+58h+CycleTime], rcx
0x1800247ec  jz      short loc_18002481C
0x1800247ee  call    cs:__imp_GetCurrentThread
0x1800247f4  mov     rcx, rax; ThreadHandle
0x1800247f7  lea     rdx, [rsp+58h+CycleTime]; CycleTime
0x1800247fc  call    cs:__imp_QueryThreadCycleTime
0x180024802  mov     rcx, [rsp+58h+CycleTime]
0x180024807  test    eax, eax
0x180024809  jz      short loc_18002481C
0x18002480b  mov     rax, rcx
0x18002480e  sub     rax, cs:CycleTime
0x180024815  add     cs:qword_1803BADD8, rax
0x18002481c  mov     cs:CycleTime, rcx
0x180024823  mov     rdi, [rsp+58h+arg_8]
0x180024828  lea     rax, [rbx+38h]
0x18002482c  jmp     loc_1800246AB
0x180024831  mov     [rsp+58h+var_30], rdi; void *
0x180024836  mov     r9d, 88982F04h; int
0x18002483c  xor     r8d, r8d; unsigned int
0x18002483f  mov     [rsp+58h+var_38], 0A1h; unsigned int
0x180024847  xor     edx, edx; int *
0x180024849  mov     ecx, 14h; unsigned int
0x18002484e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180024853  jmp     short loc_180024823
0x180024855  lea     rax, [rdx+974h]
0x18002485c  mov     [rsp+58h+var_28], 1
0x180024865  mov     [rsp+58h+var_20], rax
0x18002486a  test    rax, rax
0x18002486d  jnz     loc_18002479F
0x180024873  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x18002487a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002487f  int     3; Trap to Debugger
0x180024880  test    rcx, rcx
0x180024883  jz      loc_18002479F
0x180024889  jmp     short loc_180024873
0x18002488b  test    rax, rax
0x18002488e  jz      loc_180024772
0x180024894  jmp     short loc_180024873
```
