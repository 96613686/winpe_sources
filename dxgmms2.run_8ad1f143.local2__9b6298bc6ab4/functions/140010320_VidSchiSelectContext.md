# VidSchiSelectContext

- ea: `0x140010320`
- end: `0x140010755`
- name: `VidSchiSelectContext`
- size: `1077`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400db54c`

## callees

- `0x14000a61c`
- `0x14000a7f8`
- `0x140010320`
- `0x140010760`
- `0x140011b70`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001035f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001035f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010744`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140010744`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400104c5`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400105b4`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400105e9`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400104c5`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400105b4`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400105e9`
- `ntoskrnl!RtlCopyBitMapEx` at `0x1400103b5`
- `ntoskrnl!RtlCopyBitMapEx` at `0x1400103fc`
- `ntoskrnl!RtlCopyBitMapEx` at `0x1400103b5`
- `ntoskrnl!RtlCopyBitMapEx` at `0x1400103fc`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x1400103cb`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x1400103cb`
- `ntoskrnl!RtlAreBitsClearEx` at `0x1400103df`
- `ntoskrnl!RtlAreBitsClearEx` at `0x1400103df`
- `ntoskrnl!RtlFindSetBitsEx` at `0x14001041a`
- `ntoskrnl!RtlFindSetBitsEx` at `0x14001041a`
- `watchdog!WdLogSingleEntry1` at `0x1400106fb`
- `watchdog!WdLogSingleEntry1` at `0x140010721`
- `watchdog!WdLogSingleEntry1` at `0x1400106fb`
- `watchdog!WdLogSingleEntry1` at `0x140010721`
- `dxgkrnl!DpSynchronizeExecution` at `0x1400104a3`
- `dxgkrnl!DpSynchronizeExecution` at `0x1400104a3`
- `HAL!KeQueryPerformanceCounter` at `0x14001061f`
- `HAL!KeQueryPerformanceCounter` at `0x1400106a6`
- `HAL!KeQueryPerformanceCounter` at `0x14001061f`
- `HAL!KeQueryPerformanceCounter` at `0x1400106a6`

## pseudocode

```c
struct _VIDSCH_CONTEXT *__fastcall VidSchiSelectContext(__int64 a1, int a2)
{
  struct _VIDSCH_CONTEXT *v4; // rdi
  __int64 v5; // rax
  __int64 SetBits; // rax
  __int64 *v7; // rbp
  __int64 v8; // rbp
  __int64 v9; // rcx
  __int64 v10; // rdx
  CCHAR v11; // al
  __int64 v13; // rax
  CCHAR MostSignificantBit; // al
  CCHAR v15; // al
  LARGE_INTEGER v16; // r14
  unsigned int v17; // edx
  __int64 v18; // rcx
  LARGE_INTEGER v19; // r14
  unsigned int v20; // edx
  __int64 v21; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-68h] BYREF
  __int64 v23; // [rsp+58h] [rbp-50h] BYREF
  __int128 v24; // [rsp+60h] [rbp-48h]
  __int64 v25; // [rsp+70h] [rbp-38h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+B0h] [rbp+8h] BYREF
  char v27; // [rsp+B8h] [rbp+10h] BYREF

  v4 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !a2 )
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 2096), &LockHandle);
  if ( *(_DWORD *)(a1 + 864) )
  {
    v5 = *(_QWORD *)(a1 + 272);
    if ( v5 && (*(_DWORD *)(v5 + 192) & 1) != 0 )
    {
      v4 = *(struct _VIDSCH_CONTEXT **)(a1 + 272);
    }
    else
    {
      RtlCopyBitMapEx(a1 + 584, a1 + 680, 0);
      RtlIntersectBitMapsEx(a1 + 680, a1 + 632);
      if ( (unsigned __int8)RtlAreBitsClearEx(a1 + 680, 0, *(_QWORD *)(a1 + 680)) )
        RtlCopyBitMapEx(a1 + 584, a1 + 680, 0);
      SetBits = RtlFindSetBitsEx(a1 + 680, 1, (unsigned int)(*(_DWORD *)(a1 + 856) + 1));
      if ( SetBits != -1 )
      {
        v7 = *(__int64 **)(a1 + 776);
        if ( (unsigned int)SetBits < *(_DWORD *)(a1 + 848) )
          v7 += (unsigned int)SetBits;
        v8 = *v7;
        *(_DWORD *)(a1 + 856) = SetBits;
        if ( v8 )
        {
          if ( *(_DWORD *)(v8 + 1900) )
          {
            v9 = *(_QWORD *)(v8 + 24);
            v27 = 0;
            v25 = 0;
            v23 = v8;
            v24 = 0;
            DpSynchronizeExecution(
              *(_QWORD *)(v9 + 32),
              VidSchiUpdateNodeRunningTimeAtISR,
              &v23,
              *(unsigned int *)(v9 + 40),
              &v27);
          }
          v10 = *(unsigned int *)(v8 + 1896);
          if ( *(_BYTE *)(v8 + 2152)
            && (v10 & 0xC0000000) == 0
            && (v13 = *(_QWORD *)(v8 + 24), (v10 & (0xFFFFFFFFuLL >> (31 - *(_BYTE *)(v13 + 224)))) != 0) )
          {
            MostSignificantBit = RtlFindMostSignificantBit(v10 & (0xFFFFFFFFuLL >> (31 - *(_BYTE *)(v13 + 224))));
            v4 = VidSchiSelectContextFromThisPriority((struct _VIDSCH_NODE *)v8, MostSignificantBit, 1);
            if ( v4 )
            {
              VidSchiUpdateNodeYieldStatus((struct _VIDSCH_NODE *)v8);
            }
            else
            {
              v15 = RtlFindMostSignificantBit(*(unsigned int *)(v8 + 1896));
              v4 = VidSchiSelectContextFromThisPriority((struct _VIDSCH_NODE *)v8, v15, 0);
              if ( !*(_QWORD *)(v8 + 2128) )
              {
                PerformanceFrequency.QuadPart = 0;
                v16 = KeQueryPerformanceCounter(&PerformanceFrequency);
                v17 = *(_DWORD *)(*((_QWORD *)v4 + 13) + 512LL);
                v18 = 0;
                if ( v17 <= *(_DWORD *)(a1 + 48) )
                  v18 = v17;
                if ( !*(_DWORD *)(*(_QWORD *)(a1 + 8 * v18 + 3528) + 83104LL) )
                {
                  WdLogSingleEntry1(3, (unsigned int)v18);
                  WdLogGlobalForLineNumber = 18980;
                }
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))VidSchiStartNodeYield)(
                  v8,
                  (LARGE_INTEGER)v16.QuadPart,
                  (union _LARGE_INTEGER)PerformanceFrequency.QuadPart);
              }
              VidSchiProfilePerformanceTick(20, a1, v8, 0, (__int64)v4, 0, 0, 1);
            }
          }
          else
          {
            v11 = RtlFindMostSignificantBit(*(unsigned int *)(v8 + 1896));
            v4 = VidSchiSelectContextFromThisPriority((struct _VIDSCH_NODE *)v8, v11, 0);
            if ( (*(_DWORD *)(a1 + 2904) & 8) != 0 && *(_BYTE *)(v8 + 2152) && !*(_QWORD *)(v8 + 2128) )
            {
              PerformanceFrequency.QuadPart = 0;
              v19 = KeQueryPerformanceCounter(&PerformanceFrequency);
              v20 = *(_DWORD *)(*((_QWORD *)v4 + 13) + 512LL);
              v21 = 0;
              if ( v20 <= *(_DWORD *)(a1 + 48) )
                v21 = v20;
              if ( !*(_DWORD *)(*(_QWORD *)(a1 + 8 * v21 + 3528) + 83104LL) )
              {
                WdLogSingleEntry1(3, (unsigned int)v21);
                WdLogGlobalForLineNumber = 18980;
              }
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))VidSchiStartNodeYield)(
                v8,
                (LARGE_INTEGER)v19.QuadPart,
                (union _LARGE_INTEGER)PerformanceFrequency.QuadPart);
            }
            VidSchiProfilePerformanceTick(20, a1, v8, 0, (__int64)v4, 0, 0, 0);
          }
        }
      }
    }
  }
  VidSchiProfilePerformanceTick(2, a1, 0, 0, (__int64)v4, 0, 0, 0);
  if ( !a2 )
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  return v4;
}

```

## disassembly

```asm
0x140010320  mov     r11, rsp
0x140010323  push    rdi
0x140010324  sub     rsp, 0A0h
0x14001032b  mov     [r11+18h], rbx
0x14001032f  xor     eax, eax
0x140010331  mov     [r11-18h], rsi
0x140010335  xorps   xmm0, xmm0
0x140010338  mov     [r11-28h], r15
0x14001033c  mov     esi, edx
0x14001033e  xor     r15d, r15d
0x140010341  mov     rbx, rcx
0x140010344  mov     edi, r15d
0x140010347  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14001034c  mov     [r11-58h], rax
0x140010350  test    edx, edx
0x140010352  jnz     short loc_14001036B
0x140010354  add     rcx, 830h; SpinLock
0x14001035b  lea     rdx, [r11-68h]; LockHandle
0x14001035f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140010366  nop     dword ptr [rax+rax+00h]
0x14001036b  cmp     [rbx+360h], edi
0x140010371  jz      loc_140010527
0x140010377  mov     rax, [rbx+110h]
0x14001037e  test    rax, rax
0x140010381  jz      short loc_140010391
0x140010383  mov     eax, [rax+0C0h]
0x140010389  test    al, 1
0x14001038b  jnz     loc_14001057B
0x140010391  mov     [rsp+0A8h+var_10], rbp
0x140010399  lea     rcx, [rbx+248h]
0x1400103a0  mov     [rsp+0A8h+var_20], r14
0x1400103a8  xor     r8d, r8d
0x1400103ab  lea     r14, [rbx+2A8h]
0x1400103b2  mov     rdx, r14
0x1400103b5  call    cs:__imp_RtlCopyBitMapEx
0x1400103bc  nop     dword ptr [rax+rax+00h]
0x1400103c1  lea     rdx, [rbx+278h]
0x1400103c8  mov     rcx, r14
0x1400103cb  call    cs:__imp_RtlIntersectBitMapsEx
0x1400103d2  nop     dword ptr [rax+rax+00h]
0x1400103d7  mov     r8, [r14]
0x1400103da  xor     edx, edx
0x1400103dc  mov     rcx, r14
0x1400103df  call    cs:__imp_RtlAreBitsClearEx
0x1400103e6  nop     dword ptr [rax+rax+00h]
0x1400103eb  test    al, al
0x1400103ed  jz      short loc_140010408
0x1400103ef  xor     r8d, r8d
0x1400103f2  lea     rcx, [rbx+248h]
0x1400103f9  mov     rdx, r14
0x1400103fc  call    cs:__imp_RtlCopyBitMapEx
0x140010403  nop     dword ptr [rax+rax+00h]
0x140010408  mov     r8d, [rbx+358h]
0x14001040f  mov     edx, 1
0x140010414  inc     r8d
0x140010417  mov     rcx, r14
0x14001041a  call    cs:__imp_RtlFindSetBitsEx
0x140010421  nop     dword ptr [rax+rax+00h]
0x140010426  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001042a  jz      loc_140010517
0x140010430  mov     rbp, [rbx+308h]
0x140010437  cmp     eax, [rbx+350h]
0x14001043d  jnb     short loc_140010446
0x14001043f  mov     ecx, eax
0x140010441  lea     rbp, [rbp+rcx*8+0]
0x140010446  mov     rbp, [rbp+0]
0x14001044a  mov     [rbx+358h], eax
0x140010450  test    rbp, rbp
0x140010453  jz      loc_140010517
0x140010459  mov     eax, [rbp+76Ch]
0x14001045f  test    eax, eax
0x140010461  jz      short loc_1400104AF
0x140010463  mov     rcx, [rbp+18h]
0x140010467  lea     rax, [rsp+0A8h+arg_8]
0x14001046f  mov     [rsp+0A8h+arg_8], dil
0x140010477  lea     r8, [rsp+0A8h+var_50]
0x14001047c  mov     [rsp+0A8h+var_38], r15
0x140010481  lea     rdx, VidSchiUpdateNodeRunningTimeAtISR
0x140010488  mov     [rsp+0A8h+var_50], rbp
0x14001048d  xorps   xmm0, xmm0
0x140010490  movdqu  [rsp+0A8h+var_48], xmm0
0x140010496  mov     r9d, [rcx+28h]
0x14001049a  mov     rcx, [rcx+20h]
0x14001049e  mov     [rsp+0A8h+var_88], rax
0x1400104a3  call    cs:__imp_DpSynchronizeExecution
0x1400104aa  nop     dword ptr [rax+rax+00h]
0x1400104af  mov     edx, [rbp+768h]
0x1400104b5  cmp     [rbp+868h], dil
0x1400104bc  jnz     loc_140010584
0x1400104c2  mov     rcx, rdx; Set
0x1400104c5  call    cs:__imp_RtlFindMostSignificantBit
0x1400104cc  nop     dword ptr [rax+rax+00h]
0x1400104d1  movsx   edx, al; unsigned int
0x1400104d4  xor     r8d, r8d; bool
0x1400104d7  mov     rcx, rbp; struct _VIDSCH_NODE *
0x1400104da  call    ?VidSchiSelectContextFromThisPriority@@YAPEAU_VIDSCH_CONTEXT@@PEAU_VIDSCH_NODE@@K_N@Z; VidSchiSelectContextFromThisPriority(_VIDSCH_NODE *,ulong,bool)
0x1400104df  mov     rdi, rax
0x1400104e2  mov     eax, [rbx+0B58h]
0x1400104e8  test    al, 8
0x1400104ea  jnz     loc_14001067C
0x1400104f0  mov     [rsp+0A8h+var_70], r15
0x1400104f5  mov     [rsp+0A8h+var_78], r15
0x1400104fa  xor     r9d, r9d
0x1400104fd  mov     [rsp+0A8h+var_80], r15
0x140010502  mov     r8, rbp
0x140010505  mov     rdx, rbx
0x140010508  mov     [rsp+0A8h+var_88], rdi
0x14001050d  mov     ecx, 14h
0x140010512  call    VidSchiProfilePerformanceTick
0x140010517  mov     rbp, [rsp+0A8h+var_10]
0x14001051f  mov     r14, [rsp+0A8h+var_20]
0x140010527  mov     [rsp+0A8h+var_70], r15
0x14001052c  xor     r9d, r9d
0x14001052f  mov     [rsp+0A8h+var_78], r15
0x140010534  xor     r8d, r8d
0x140010537  mov     [rsp+0A8h+var_80], r15
0x14001053c  mov     rdx, rbx
0x14001053f  mov     ecx, 2
0x140010544  mov     [rsp+0A8h+var_88], rdi
0x140010549  call    VidSchiProfilePerformanceTick
0x14001054e  mov     r15, [rsp+0A8h+var_28]
0x140010556  test    esi, esi
0x140010558  mov     rsi, [rsp+0A8h+var_18]
0x140010560  mov     rbx, [rsp+0A8h+arg_10]
0x140010568  jz      loc_14001073F
0x14001056e  mov     rax, rdi
0x140010571  add     rsp, 0A0h
0x140010578  pop     rdi
0x140010579  retn
0x14001057b  mov     rdi, [rbx+110h]
0x140010582  jmp     short loc_140010527
0x140010584  test    edx, 0C0000000h
0x14001058a  jnz     loc_1400104C2
0x140010590  mov     rax, [rbp+18h]
0x140010594  mov     ecx, 1Fh
0x140010599  mov     r8d, 0FFFFFFFFh
0x14001059f  sub     ecx, [rax+0E0h]
0x1400105a5  shr     r8, cl
0x1400105a8  and     r8, rdx
0x1400105ab  jz      loc_1400104C2
0x1400105b1  mov     rcx, r8; Set
0x1400105b4  call    cs:__imp_RtlFindMostSignificantBit
0x1400105bb  nop     dword ptr [rax+rax+00h]
0x1400105c0  movsx   edx, al; unsigned int
0x1400105c3  mov     r8b, 1; bool
0x1400105c6  mov     rcx, rbp; struct _VIDSCH_NODE *
0x1400105c9  call    ?VidSchiSelectContextFromThisPriority@@YAPEAU_VIDSCH_CONTEXT@@PEAU_VIDSCH_NODE@@K_N@Z; VidSchiSelectContextFromThisPriority(_VIDSCH_NODE *,ulong,bool)
0x1400105ce  mov     rdi, rax
0x1400105d1  test    rax, rax
0x1400105d4  jz      short loc_1400105E3
0x1400105d6  mov     rcx, rbp; struct _VIDSCH_NODE *
0x1400105d9  call    ?VidSchiUpdateNodeYieldStatus@@YAXPEAU_VIDSCH_NODE@@@Z; VidSchiUpdateNodeYieldStatus(_VIDSCH_NODE *)
0x1400105de  jmp     loc_140010517
0x1400105e3  mov     ecx, [rbp+768h]; Set
0x1400105e9  call    cs:__imp_RtlFindMostSignificantBit
0x1400105f0  nop     dword ptr [rax+rax+00h]
0x1400105f5  movsx   edx, al; unsigned int
0x1400105f8  xor     r8d, r8d; bool
0x1400105fb  mov     rcx, rbp; struct _VIDSCH_NODE *
0x1400105fe  call    ?VidSchiSelectContextFromThisPriority@@YAPEAU_VIDSCH_CONTEXT@@PEAU_VIDSCH_NODE@@K_N@Z; VidSchiSelectContextFromThisPriority(_VIDSCH_NODE *,ulong,bool)
0x140010603  mov     rdi, rax
0x140010606  cmp     [rbp+850h], r15
0x14001060d  jnz     short loc_14001066E
0x14001060f  lea     rcx, [rsp+0A8h+PerformanceFrequency]; PerformanceFrequency
0x140010617  mov     qword ptr [rsp+0A8h+PerformanceFrequency], r15
0x14001061f  call    cs:__imp_KeQueryPerformanceCounter
0x140010626  nop     dword ptr [rax+rax+00h]
0x14001062b  mov     rcx, [rdi+68h]
0x14001062f  mov     r14, rax
0x140010632  mov     edx, [rcx+200h]
0x140010638  mov     ecx, r15d
0x14001063b  cmp     edx, [rbx+30h]
0x14001063e  cmovbe  ecx, edx
0x140010641  mov     edx, ecx
0x140010643  mov     rcx, [rbx+rcx*8+0DC8h]
0x14001064b  mov     r9d, [rcx+144A0h]
0x140010652  test    r9d, r9d
0x140010655  jz      loc_1400106F6
0x14001065b  mov     r8, qword ptr [rsp+0A8h+PerformanceFrequency]
0x140010663  mov     rdx, r14
0x140010666  mov     rcx, rbp
0x140010669  call    VidSchiStartNodeYield
0x14001066e  mov     [rsp+0A8h+var_70], 1
0x140010677  jmp     loc_1400104F5
0x14001067c  cmp     [rbp+868h], r15b
0x140010683  jz      loc_1400104F0
0x140010689  cmp     [rbp+850h], r15
0x140010690  jnz     loc_1400104F0
0x140010696  lea     rcx, [rsp+0A8h+PerformanceFrequency]; PerformanceFrequency
0x14001069e  mov     qword ptr [rsp+0A8h+PerformanceFrequency], r15
0x1400106a6  call    cs:__imp_KeQueryPerformanceCounter
0x1400106ad  nop     dword ptr [rax+rax+00h]
0x1400106b2  mov     rcx, [rdi+68h]
0x1400106b6  mov     r14, rax
0x1400106b9  mov     edx, [rcx+200h]
0x1400106bf  mov     ecx, r15d
0x1400106c2  cmp     edx, [rbx+30h]
0x1400106c5  cmovbe  ecx, edx
0x1400106c8  mov     edx, ecx
0x1400106ca  mov     rcx, [rbx+rcx*8+0DC8h]
0x1400106d2  mov     r9d, [rcx+144A0h]
0x1400106d9  test    r9d, r9d
0x1400106dc  jz      short loc_14001071C
0x1400106de  mov     r8, qword ptr [rsp+0A8h+PerformanceFrequency]
0x1400106e6  mov     rdx, r14
0x1400106e9  mov     rcx, rbp
0x1400106ec  call    VidSchiStartNodeYield
0x1400106f1  jmp     loc_1400104F0
0x1400106f6  mov     ecx, 3
0x1400106fb  call    cs:__imp_WdLogSingleEntry1
0x140010702  nop     dword ptr [rax+rax+00h]
0x140010707  mov     r9d, 10h
0x14001070d  mov     cs:WdLogGlobalForLineNumber, 4A24h
0x140010717  jmp     loc_14001065B
0x14001071c  mov     ecx, 3
0x140010721  call    cs:__imp_WdLogSingleEntry1
0x140010728  nop     dword ptr [rax+rax+00h]
0x14001072d  mov     r9d, 10h
0x140010733  mov     cs:WdLogGlobalForLineNumber, 4A24h
0x14001073d  jmp     short loc_1400106DE
0x14001073f  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140010744  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001074b  nop     dword ptr [rax+rax+00h]
0x140010750  jmp     loc_14001056E
```
