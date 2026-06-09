# DXGSWAPCHAINLOCKWITHDEVICE::Acquire(DXGDEVICE * *,bool,bool)

- ea: `0x1403a2584`
- end: `0x1403a2a63`
- name: `?Acquire@DXGSWAPCHAINLOCKWITHDEVICE@@QEAAJPEAPEAVDXGDEVICE@@_N1@Z`
- size: `1247`
- prototype: `__int64 __fastcall(DXGSWAPCHAINLOCKWITHDEVICE *__hidden this, struct DXGDEVICE **, bool, bool)`
- caller_count: `7`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401b0150`
- `0x1401c5580`
- `0x1401d5f80`
- `0x1401dd060`
- `0x14026d810`
- `0x1403a1da0`
- `0x1403a1ef0`

## callees

- `0x1400146ac`
- `0x1400148d4`
- `0x140015b60`
- `0x1400162a4`
- `0x14001b9c0`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001f8cc`
- `0x140042cc0`
- `0x140047d74`
- `0x1400a0bd0`
- `0x140328500`
- `0x14032a5c4`
- `0x14032a964`
- `0x1403672dc`
- `0x1403a2584`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a27b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a28b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a27b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1403a28b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403a26d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403a26d9`
- `ntoskrnl!KeReadStateEvent` at `0x1403a2779`
- `ntoskrnl!KeReadStateEvent` at `0x1403a2779`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403a26cd`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403a26cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403a285f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403a285f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1403a27cb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1403a2935`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1403a27cb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1403a2935`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403a28cc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403a28ff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403a28cc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1403a28ff`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1403a2874`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1403a2874`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403a279d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1403a279d`
- `watchdog!WdLogSingleEntry2` at `0x1403a26a8`
- `watchdog!WdLogSingleEntry2` at `0x1403a2706`
- `watchdog!WdLogSingleEntry2` at `0x1403a288c`
- `watchdog!WdLogSingleEntry2` at `0x1403a26a8`
- `watchdog!WdLogSingleEntry2` at `0x1403a2706`
- `watchdog!WdLogSingleEntry2` at `0x1403a288c`
- `watchdog!WdLogSingleEntry0` at `0x1403a29ec`
- `watchdog!WdLogSingleEntry0` at `0x1403a29ec`
- `watchdog!WdLogSingleEntry1` at `0x1403a29c7`
- `watchdog!WdLogSingleEntry1` at `0x1403a2a3c`
- `watchdog!WdLogSingleEntry1` at `0x1403a29c7`
- `watchdog!WdLogSingleEntry1` at `0x1403a2a3c`

## pseudocode

```c
__int64 __fastcall DXGSWAPCHAINLOCKWITHDEVICE::Acquire(
        DXGSWAPCHAINLOCKWITHDEVICE *this,
        struct DXGDEVICE **a2,
        char a3,
        char a4)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  _BYTE *v9; // r15
  struct DXGPROCESS *Current; // rax
  struct DXGPROCESS *v11; // rbp
  volatile signed __int32 *v12; // r14
  __int64 v13; // rdx
  __int64 v14; // r12
  unsigned int v15; // eax
  __int64 v16; // r8
  int v17; // edx
  __int64 v18; // rbx
  signed __int64 v19; // rax
  signed __int64 v20; // rtt
  int v21; // ebp
  __int64 result; // rax
  struct _KEVENT *v23; // r14
  __int64 v24; // rcx
  __int64 *v25; // rbx
  __int64 v26; // rbx
  HANDLE CurrentProcessId; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rdx
  char v35[8]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v36; // [rsp+68h] [rbp-80h]
  __int64 v37; // [rsp+70h] [rbp-78h]
  char v38; // [rsp+78h] [rbp-70h]
  __int64 v39; // [rsp+80h] [rbp-68h]

  DXGAUTOMUTEX::Acquire((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 24));
  v8 = *((_QWORD *)this + 1);
  *((_BYTE *)this + 40) = 1;
  if ( *(_DWORD *)(v8 + 48) )
  {
    WdLogSingleEntry1(3, v8);
    result = 3221225558LL;
    WdLogGlobalForLineNumber = 4332;
  }
  else
  {
    v9 = (char *)this + 16;
    if ( *(_BYTE *)this == 1 )
    {
      v25 = (__int64 *)(v8 + 160);
      if ( !*v9 )
        v25 = (__int64 *)(v8 + 112);
      v26 = *v25;
      if ( PsGetCurrentProcess(v7) != v26 )
      {
        CurrentProcessId = PsGetCurrentProcessId();
        WdLogSingleEntry2(3, *((_QWORD *)this + 1), CurrentProcessId);
        result = 3221225506LL;
        WdLogGlobalForLineNumber = 4341;
        return result;
      }
    }
    Current = DXGPROCESS::GetCurrent();
    v11 = Current;
    if ( a2 )
    {
      *a2 = 0;
      v12 = (volatile signed __int32 *)((char *)Current + 248);
      DXGPUSHLOCK::AcquireShared((struct DXGPROCESS *)((char *)Current + 248));
      v13 = *v9 != 0 ? 0x30 : 0;
      v14 = *(unsigned int *)(v13 + *((_QWORD *)this + 1) + 96);
      v15 = (*(_DWORD *)(v13 + *((_QWORD *)this + 1) + 96) >> 6) & 0xFFFFFF;
      if ( v15 < *((_DWORD *)v11 + 74) )
      {
        v16 = *((_QWORD *)v11 + 35);
        if ( (((unsigned int)v14 >> 25) & 0x60) == (*(_BYTE *)(v16 + 16LL * v15 + 8) & 0x60)
          && (*(_DWORD *)(v16 + 16LL * v15 + 8) & 0x2000) == 0 )
        {
          v17 = *(_DWORD *)(v16 + 16LL * v15 + 8) & 0x1F;
          if ( v17 )
          {
            if ( v17 != 3 )
            {
              WdLogSingleEntry0(2);
              v18 = 0;
              WdLogGlobalForLineNumber = 318;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
              goto LABEL_15;
            }
            v18 = *(_QWORD *)(v16 + 16LL * v15);
            if ( !v18 )
            {
LABEL_15:
              WdLogSingleEntry2(3, v14, v11);
              WdLogGlobalForLineNumber = 4381;
              v21 = -1073741811;
LABEL_16:
              _InterlockedDecrement(v12 + 4);
              ExReleasePushLockSharedEx(v12, 0);
              KeLeaveCriticalRegion();
              if ( !v18 || !a3 )
              {
LABEL_20:
                if ( v21 >= 0 )
                {
                  v32 = *((_QWORD *)this + 1);
                  if ( !*(_DWORD *)(v32 + 48) )
                  {
                    *(_QWORD *)((*v9 != 0 ? 0x30 : 0) + v32 + 104) = v18;
                    *a2 = (struct DXGDEVICE *)v18;
                    return (unsigned int)v21;
                  }
                  WdLogSingleEntry1(3, v32);
                  WdLogGlobalForLineNumber = 4438;
                  v21 = -1073741738;
                }
                DXGSWAPCHAINLOCKWITHDEVICE::Release(this);
                return (unsigned int)v21;
              }
              DXGAUTOMUTEX::Release((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 24));
              v23 = *(struct _KEVENT **)(v18 + 16);
              if ( !KeReadStateEvent(v23 + 4) )
                KeWaitForSingleObject(&v23[4], Executive, 0, 0, 0);
              if ( (unsigned int)Feature_IdSwapChainUserModeSync__private_IsEnabledDeviceUsageNoInline() && a4 )
              {
                KeEnterCriticalRegion();
                if ( !ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v18 + 136), 0) )
                {
                  DXGADAPTER::TryWakeUpFromD3State(*(DXGADAPTER **)(*(_QWORD *)(v18 + 16) + 16LL));
                  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                    McTemplateK0q_EtwWriteTransfer(v28, EventBlockThread, v29, 40);
                  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v18 + 136), 1u);
LABEL_42:
                  DXGADAPTER::EnableD3Requests(*(DXGADAPTER **)(*(_QWORD *)(v18 + 16) + 16LL));
                }
              }
              else
              {
                KeEnterCriticalRegion();
                if ( !ExAcquireResourceSharedLite(*(PERESOURCE *)(v18 + 136), 0) )
                {
                  DXGADAPTER::TryWakeUpFromD3State(*(DXGADAPTER **)(*(_QWORD *)(v18 + 16) + 16LL));
                  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
                    McTemplateK0q_EtwWriteTransfer(v30, EventBlockThread, v31, 40);
                  ExAcquireResourceSharedLite(*(PERESOURCE *)(v18 + 136), 1u);
                  goto LABEL_42;
                }
              }
              *((_BYTE *)this + 41) = 1;
              v24 = *(_QWORD *)(*(_QWORD *)(v18 + 16) + 16LL);
              v37 = v24;
              v38 = 0;
              v39 = 0;
              if ( v24 )
              {
                _InterlockedIncrement64((volatile signed __int64 *)(v24 + 24));
                v36 = -1;
              }
              COREACCESS::operator=((char *)this + 56, v35);
              COREACCESS::~COREACCESS((COREACCESS *)v35);
              COREACCESS::AcquireShared((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 56), 0);
              if ( *(_DWORD *)(v18 + 608) == 1 )
              {
                *((_BYTE *)this + 43) = 1;
              }
              else
              {
                COREACCESS::Release((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 56));
                v21 = -1073741130;
                WdLogSingleEntry2(3, v18, -1073741130);
                WdLogGlobalForLineNumber = 4422;
              }
              DXGAUTOMUTEX::Acquire((DXGSWAPCHAINLOCKWITHDEVICE *)((char *)this + 24));
              goto LABEL_20;
            }
            _m_prefetchw((const void *)(v18 + 64));
            v19 = *(_QWORD *)(v18 + 64);
            while ( v19 )
            {
              v20 = v19;
              v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v18 + 64), v19 + 1, v19);
              if ( v20 == v19 )
              {
                v21 = 0;
                *((_BYTE *)this + 42) = 1;
                *((_QWORD *)this + 6) = v18;
                goto LABEL_16;
              }
            }
          }
        }
      }
      v18 = 0;
      goto LABEL_15;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1403a2584  mov     [rsp+arg_10], rbx
0x1403a2589  push    rbp
0x1403a258a  push    rsi
0x1403a258b  push    rdi
0x1403a258c  push    r12
0x1403a258e  push    r13
0x1403a2590  push    r14
0x1403a2592  push    r15
0x1403a2594  sub     rsp, 0B0h
0x1403a259b  mov     rax, cs:__security_cookie
0x1403a25a2  xor     rax, rsp
0x1403a25a5  mov     [rsp+0E8h+var_48], rax
0x1403a25ad  mov     rdi, rcx
0x1403a25b0  mov     [rsp+0E8h+var_98], r9b
0x1403a25b5  add     rcx, 18h; this
0x1403a25b9  mov     [rsp+0E8h+var_90], rdx
0x1403a25be  mov     r13b, r8b
0x1403a25c1  mov     rsi, rdx
0x1403a25c4  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1403a25c9  mov     rax, [rdi+8]
0x1403a25cd  xor     r14d, r14d
0x1403a25d0  mov     byte ptr [rdi+28h], 1
0x1403a25d4  cmp     [rax+30h], r14d
0x1403a25d8  jnz     loc_1403A29BF
0x1403a25de  cmp     byte ptr [rdi], 1
0x1403a25e1  lea     r15, [rdi+10h]
0x1403a25e5  jz      loc_1403A284C
0x1403a25eb  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1403a25f0  mov     rbp, rax
0x1403a25f3  test    rsi, rsi
0x1403a25f6  jz      loc_1403A2A5C
0x1403a25fc  mov     [rsi], r14
0x1403a25ff  lea     r14, [rax+0F8h]
0x1403a2606  mov     rcx, r14; this
0x1403a2609  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x1403a260e  mov     rax, [rdi+8]
0x1403a2612  mov     esi, 3
0x1403a2617  mov     cl, [r15]
0x1403a261a  neg     cl
0x1403a261c  sbb     rdx, rdx
0x1403a261f  and     edx, 30h
0x1403a2622  mov     r12d, [rdx+rax+60h]
0x1403a2627  mov     eax, r12d
0x1403a262a  shr     eax, 6
0x1403a262d  and     eax, 0FFFFFFh
0x1403a2632  cmp     eax, [rbp+128h]
0x1403a2638  jnb     short loc_1403A269E
0x1403a263a  mov     r8, [rbp+118h]
0x1403a2641  mov     ecx, r12d
0x1403a2644  mov     ebx, eax
0x1403a2646  add     rbx, rbx
0x1403a2649  shr     ecx, 19h
0x1403a264c  and     ecx, 60h
0x1403a264f  mov     edx, [r8+rbx*8+8]
0x1403a2654  mov     eax, edx
0x1403a2656  and     eax, 60h
0x1403a2659  cmp     cl, al
0x1403a265b  jnz     short loc_1403A269E
0x1403a265d  bt      edx, 0Dh
0x1403a2661  jb      short loc_1403A269E
0x1403a2663  and     edx, 1Fh
0x1403a2666  jz      short loc_1403A269E
0x1403a2668  cmp     edx, esi
0x1403a266a  jnz     loc_1403A29E7
0x1403a2670  mov     rbx, [r8+rbx*8]
0x1403a2674  test    rbx, rbx
0x1403a2677  jz      short loc_1403A26A0
0x1403a2679  prefetchw byte ptr [rbx+40h]
0x1403a267d  mov     rax, [rbx+40h]
0x1403a2681  test    rax, rax
0x1403a2684  jz      short loc_1403A269E
0x1403a2686  lea     rcx, [rax+1]
0x1403a268a  lock cmpxchg [rbx+40h], rcx
0x1403a2690  jnz     short loc_1403A2681
0x1403a2692  xor     ebp, ebp
0x1403a2694  mov     byte ptr [rdi+2Ah], 1
0x1403a2698  mov     [rdi+30h], rbx
0x1403a269c  jmp     short loc_1403A26C3
0x1403a269e  xor     ebx, ebx
0x1403a26a0  mov     rdx, r12
0x1403a26a3  mov     r8, rbp
0x1403a26a6  mov     ecx, esi
0x1403a26a8  call    cs:__imp_WdLogSingleEntry2
0x1403a26af  nop     dword ptr [rax+rax+00h]
0x1403a26b4  mov     cs:WdLogGlobalForLineNumber, 111Dh
0x1403a26be  mov     ebp, 0C000000Dh
0x1403a26c3  lock dec dword ptr [r14+10h]
0x1403a26c8  xor     edx, edx
0x1403a26ca  mov     rcx, r14
0x1403a26cd  call    cs:__imp_ExReleasePushLockSharedEx
0x1403a26d4  nop     dword ptr [rax+rax+00h]
0x1403a26d9  call    cs:__imp_KeLeaveCriticalRegion
0x1403a26e0  nop     dword ptr [rax+rax+00h]
0x1403a26e5  test    rbx, rbx
0x1403a26e8  jnz     short loc_1403A2763
0x1403a26ea  xor     r13d, r13d
0x1403a26ed  jmp     short loc_1403A2725
0x1403a26ef  mov     rcx, r14; this
0x1403a26f2  call    ?Release@COREACCESS@@QEAAXXZ; COREACCESS::Release(void)
0x1403a26f7  mov     rbp, 0FFFFFFFFC00002B6h
0x1403a26fe  mov     r8, rbp
0x1403a2701  mov     rdx, rbx
0x1403a2704  mov     ecx, esi
0x1403a2706  call    cs:__imp_WdLogSingleEntry2
0x1403a270d  nop     dword ptr [rax+rax+00h]
0x1403a2712  mov     cs:WdLogGlobalForLineNumber, 1146h
0x1403a271c  lea     rcx, [rdi+18h]; this
0x1403a2720  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1403a2725  test    ebp, ebp
0x1403a2727  jns     loc_1403A2994
0x1403a272d  mov     rcx, rdi; this
0x1403a2730  call    ?Release@DXGSWAPCHAINLOCKWITHDEVICE@@QEAAXXZ; DXGSWAPCHAINLOCKWITHDEVICE::Release(void)
0x1403a2735  mov     eax, ebp
0x1403a2737  mov     rcx, [rsp+0E8h+var_48]
0x1403a273f  xor     rcx, rsp; StackCookie
0x1403a2742  call    __security_check_cookie
0x1403a2747  mov     rbx, [rsp+0E8h+arg_10]
0x1403a274f  add     rsp, 0B0h
0x1403a2756  pop     r15
0x1403a2758  pop     r14
0x1403a275a  pop     r13
0x1403a275c  pop     r12
0x1403a275e  pop     rdi
0x1403a275f  pop     rsi
0x1403a2760  pop     rbp
0x1403a2761  retn
0x1403a2763  test    r13b, r13b
0x1403a2766  jz      short loc_1403A26EA
0x1403a2768  lea     rcx, [rdi+18h]; this
0x1403a276c  call    ?Release@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Release(void)
0x1403a2771  mov     r14, [rbx+10h]
0x1403a2775  lea     rcx, [r14+60h]; Event
0x1403a2779  call    cs:__imp_KeReadStateEvent
0x1403a2780  nop     dword ptr [rax+rax+00h]
0x1403a2785  xor     r13d, r13d
0x1403a2788  test    eax, eax
0x1403a278a  jnz     short loc_1403A27A9
0x1403a278c  xor     r9d, r9d; Alertable
0x1403a278f  mov     [rsp+0E8h+Timeout], r13; Timeout
0x1403a2794  xor     r8d, r8d; WaitMode
0x1403a2797  lea     rcx, [r14+60h]; Object
0x1403a279b  xor     edx, edx; WaitReason
0x1403a279d  call    cs:__imp_KeWaitForSingleObject
0x1403a27a4  nop     dword ptr [rax+rax+00h]
0x1403a27a9  call    Feature_IdSwapChainUserModeSync__private_IsEnabledDeviceUsageNoInline
0x1403a27ae  test    eax, eax
0x1403a27b0  jnz     loc_1403A28AC
0x1403a27b6  call    cs:__imp_KeEnterCriticalRegion
0x1403a27bd  nop     dword ptr [rax+rax+00h]
0x1403a27c2  mov     rcx, [rbx+88h]; Resource
0x1403a27c9  xor     edx, edx; Wait
0x1403a27cb  call    cs:__imp_ExAcquireResourceSharedLite
0x1403a27d2  nop     dword ptr [rax+rax+00h]
0x1403a27d7  test    al, al
0x1403a27d9  jz      loc_1403A2916
0x1403a27df  mov     byte ptr [rdi+29h], 1
0x1403a27e3  mov     rax, [rbx+10h]
0x1403a27e7  mov     rcx, [rax+10h]
0x1403a27eb  mov     [rsp+0E8h+var_78], rcx
0x1403a27f0  mov     [rsp+0E8h+var_70], r13b
0x1403a27f5  mov     [rsp+0E8h+var_68], r13
0x1403a27fd  test    rcx, rcx
0x1403a2800  jz      short loc_1403A2810
0x1403a2802  lock inc qword ptr [rcx+18h]
0x1403a2807  mov     [rsp+0E8h+var_80], 0FFFFFFFFFFFFFFFFh
0x1403a2810  lea     r14, [rdi+38h]
0x1403a2814  mov     rcx, r14
0x1403a2817  lea     rdx, [rsp+0E8h+var_88]
0x1403a281c  call    ??4COREACCESS@@QEAAAEAV0@$$QEAV0@@Z; COREACCESS::operator=(COREACCESS &&)
0x1403a2821  lea     rcx, [rsp+0E8h+var_88]; this
0x1403a2826  call    ??1COREACCESS@@QEAA@XZ; COREACCESS::~COREACCESS(void)
0x1403a282b  xor     edx, edx; char *
0x1403a282d  mov     rcx, r14; this
0x1403a2830  call    ?AcquireShared@COREACCESS@@QEAAXPEBD@Z; COREACCESS::AcquireShared(char const *)
0x1403a2835  mov     eax, [rbx+260h]
0x1403a283b  cmp     eax, 1
0x1403a283e  jnz     loc_1403A26EF
0x1403a2844  mov     [rdi+2Bh], al
0x1403a2847  jmp     loc_1403A271C
0x1403a284c  lea     rbx, [rax+0A0h]
0x1403a2853  cmp     [r15], r14b
0x1403a2856  jz      loc_1403A290D
0x1403a285c  mov     rbx, [rbx]
0x1403a285f  call    cs:__imp_PsGetCurrentProcess
0x1403a2866  nop     dword ptr [rax+rax+00h]
0x1403a286b  cmp     rax, rbx
0x1403a286e  jz      loc_1403A25EB
0x1403a2874  call    cs:__imp_PsGetCurrentProcessId
0x1403a287b  nop     dword ptr [rax+rax+00h]
0x1403a2880  mov     rdx, [rdi+8]
0x1403a2884  mov     ecx, 3
0x1403a2889  mov     r8, rax
0x1403a288c  call    cs:__imp_WdLogSingleEntry2
0x1403a2893  nop     dword ptr [rax+rax+00h]
0x1403a2898  mov     eax, 0C0000022h
0x1403a289d  mov     cs:WdLogGlobalForLineNumber, 10F5h
0x1403a28a7  jmp     loc_1403A2737
0x1403a28ac  cmp     [rsp+0E8h+var_98], r13b
0x1403a28b1  jz      loc_1403A27B6
0x1403a28b7  call    cs:__imp_KeEnterCriticalRegion
0x1403a28be  nop     dword ptr [rax+rax+00h]
0x1403a28c3  mov     rcx, [rbx+88h]; Resource
0x1403a28ca  xor     edx, edx; Wait
0x1403a28cc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403a28d3  nop     dword ptr [rax+rax+00h]
0x1403a28d8  test    al, al
0x1403a28da  jnz     loc_1403A27DF
0x1403a28e0  mov     rcx, [rbx+10h]
0x1403a28e4  mov     rcx, [rcx+10h]; this
0x1403a28e8  call    ?TryWakeUpFromD3State@DXGADAPTER@@QEAAEXZ; DXGADAPTER::TryWakeUpFromD3State(void)
0x1403a28ed  cmp     cs:bTracingEnabled, r13b
0x1403a28f4  jnz     short loc_1403A2970
0x1403a28f6  mov     rcx, [rbx+88h]; Resource
0x1403a28fd  mov     dl, 1; Wait
0x1403a28ff  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1403a2906  nop     dword ptr [rax+rax+00h]
0x1403a290b  jmp     short loc_1403A2941
0x1403a290d  lea     rbx, [rax+70h]
0x1403a2911  jmp     loc_1403A285C
0x1403a2916  mov     rcx, [rbx+10h]
0x1403a291a  mov     rcx, [rcx+10h]; this
0x1403a291e  call    ?TryWakeUpFromD3State@DXGADAPTER@@QEAAEXZ; DXGADAPTER::TryWakeUpFromD3State(void)
0x1403a2923  cmp     cs:bTracingEnabled, r13b
0x1403a292a  jnz     short loc_1403A2953
0x1403a292c  mov     rcx, [rbx+88h]; Resource
0x1403a2933  mov     dl, 1; Wait
0x1403a2935  call    cs:__imp_ExAcquireResourceSharedLite
0x1403a293c  nop     dword ptr [rax+rax+00h]
0x1403a2941  mov     rcx, [rbx+10h]
0x1403a2945  mov     rcx, [rcx+10h]; this
0x1403a2949  call    ?EnableD3Requests@DXGADAPTER@@QEAAXXZ; DXGADAPTER::EnableD3Requests(void)
0x1403a294e  jmp     loc_1403A27DF
0x1403a2953  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403a295a  jz      short loc_1403A292C
0x1403a295c  mov     r9d, 28h ; '('
0x1403a2962  lea     rdx, EventBlockThread
0x1403a2969  call    McTemplateK0q_EtwWriteTransfer
0x1403a296e  jmp     short loc_1403A292C
0x1403a2970  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1403a2977  jz      loc_1403A28F6
0x1403a297d  mov     r9d, 28h ; '('
0x1403a2983  lea     rdx, EventBlockThread
0x1403a298a  call    McTemplateK0q_EtwWriteTransfer
0x1403a298f  jmp     loc_1403A28F6
0x1403a2994  mov     rdx, [rdi+8]
0x1403a2998  cmp     [rdx+30h], r13d
0x1403a299c  jnz     loc_1403A2A3A
0x1403a29a2  mov     al, [r15]
0x1403a29a5  neg     al
0x1403a29a7  mov     rax, [rsp+0E8h+var_90]
0x1403a29ac  sbb     rcx, rcx
0x1403a29af  and     ecx, 30h
0x1403a29b2  mov     [rcx+rdx+68h], rbx
0x1403a29b7  mov     [rax], rbx
0x1403a29ba  jmp     loc_1403A2735
0x1403a29bf  mov     rdx, rax
0x1403a29c2  mov     ecx, 3
0x1403a29c7  call    cs:__imp_WdLogSingleEntry1
0x1403a29ce  nop     dword ptr [rax+rax+00h]
0x1403a29d3  mov     eax, 0C0000056h
0x1403a29d8  mov     cs:WdLogGlobalForLineNumber, 10ECh
0x1403a29e2  jmp     loc_1403A2737
0x1403a29e7  mov     ecx, 2
0x1403a29ec  call    cs:__imp_WdLogSingleEntry0
0x1403a29f3  nop     dword ptr [rax+rax+00h]
0x1403a29f8  xor     ebx, ebx
0x1403a29fa  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x1403a2a01  mov     [rsp+0E8h+var_A8], rbx
0x1403a2a06  mov     eax, 13Eh
0x1403a2a0b  mov     [rsp+0E8h+var_B0], rbx
0x1403a2a10  or      r8d, 0FFFFFFFFh
0x1403a2a14  mov     [rsp+0E8h+var_B8], rbx
0x1403a2a19  mov     edx, 40000h
0x1403a2a1e  mov     [rsp+0E8h+var_C0], rbx
0x1403a2a23  xor     ecx, ecx
0x1403a2a25  mov     [rsp+0E8h+Timeout], rax
0x1403a2a2a  mov     cs:WdLogGlobalForLineNumber, eax
0x1403a2a30  call    DxgkLogInternalTriageEvent
0x1403a2a35  jmp     loc_1403A26A0
0x1403a2a3a  mov     ecx, esi
0x1403a2a3c  call    cs:__imp_WdLogSingleEntry1
0x1403a2a43  nop     dword ptr [rax+rax+00h]
0x1403a2a48  mov     cs:WdLogGlobalForLineNumber, 1156h
0x1403a2a52  mov     ebp, 0C0000056h
0x1403a2a57  jmp     loc_1403A272D
0x1403a2a5c  xor     eax, eax
0x1403a2a5e  jmp     loc_1403A2737
```
