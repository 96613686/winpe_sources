# CTimerMan::ThreadExec(void)

- ea: `0x180264950`
- end: `0x180264c53`
- name: `?ThreadExec@CTimerMan@@MEAAXXZ`
- size: `771`
- prototype: `void __fastcall(CTimerMan *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180157d3c`
- `0x180264950`
- `0x180265374`
- `0x1807c1510`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180264a18`
- `KERNEL32!QueryPerformanceCounter` at `0x180264a18`
- `KERNEL32!QueryPerformanceFrequency` at `0x180264bf3`
- `KERNEL32!QueryPerformanceFrequency` at `0x180264bf3`
- `KERNEL32!LeaveCriticalSection` at `0x180264996`
- `KERNEL32!LeaveCriticalSection` at `0x180264afd`
- `KERNEL32!LeaveCriticalSection` at `0x180264996`
- `KERNEL32!LeaveCriticalSection` at `0x180264afd`
- `KERNEL32!EnterCriticalSection` at `0x1802649f9`
- `KERNEL32!EnterCriticalSection` at `0x180264adf`
- `KERNEL32!EnterCriticalSection` at `0x1802649f9`
- `KERNEL32!EnterCriticalSection` at `0x180264adf`
- `KERNEL32!WaitForSingleObject` at `0x1802649b9`
- `KERNEL32!WaitForSingleObject` at `0x1802649b9`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b10`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b1f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b2e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b3d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b4d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b84`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b94`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b10`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b1f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b2e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b3d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b4d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b84`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180264b94`

## pseudocode

```c
void __fastcall CTimerMan::ThreadExec(CTimerMan *this)
{
  bool v1; // r13
  __int64 i; // r14
  int v4; // r15d
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  DWORD v6; // eax
  DWORD v7; // ebx
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  unsigned int v9; // r12d
  LARGE_INTEGER v10; // r8
  unsigned __int64 v11; // rdi
  unsigned int v12; // edi
  unsigned __int64 v13; // rbp
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  __int128 v16; // xmm6
  __int128 v17; // xmm7
  char v18; // bl
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-78h] BYREF

  v1 = 0;
  while ( !*((_DWORD *)this + 118) )
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
    v9 = -1;
    if ( v8 )
      EnterCriticalSection(v8);
    if ( *((int *)this + 17) > 0 )
    {
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v10 = CQPCTick::s_qpcFrequency;
      if ( CQPCTick::s_qpcFrequency.QuadPart
        || (QueryPerformanceFrequency(&CQPCTick::s_qpcFrequency),
            v10 = CQPCTick::s_qpcFrequency,
            CQPCTick::s_qpcFrequency.QuadPart) )
      {
        LODWORD(v11) = PerformanceCount.LowPart;
        if ( PerformanceCount.QuadPart && v10.QuadPart && v10.QuadPart != 1000 )
          v11 = 1000 * (PerformanceCount.QuadPart % (unsigned __int64)v10.QuadPart) / v10.QuadPart
              + 1000 * (PerformanceCount.QuadPart / (unsigned __int64)v10.QuadPart);
      }
      else
      {
        LODWORD(v11) = 0;
      }
      v12 = v11 - *((_DWORD *)this + 134);
      v4 = *((_DWORD *)this + 17);
      for ( i = *((_QWORD *)this + 9); v4; --v4 )
      {
        if ( !*(_DWORD *)(i + 24) )
        {
          if ( *(_DWORD *)i > v12 )
          {
            if ( !v1 || !*(_DWORD *)(i + 4) )
            {
              if ( *(_DWORD *)i - v12 < v9 )
                v9 = *(_DWORD *)i - v12;
              goto LABEL_3;
            }
            *(_DWORD *)i = v12;
          }
          v13 = *(_QWORD *)(i + 16);
          *(_DWORD *)(i + 4) = 0;
          if ( !*(_DWORD *)(v13 + 80) && *(int *)(v13 + 68) <= 0 && !*(_DWORD *)(v13 + 84) )
          {
            v14 = *(struct _RTL_CRITICAL_SECTION **)(v13 + 8);
            if ( v14 )
              EnterCriticalSection(v14);
            if ( *(_DWORD *)(v13 + 72) )
            {
              *(_DWORD *)(v13 + 84) = 1;
              CBaseFT::LeaveCriticalSection((CBaseFT *)v13);
            }
            else
            {
              v15 = *(struct _RTL_CRITICAL_SECTION **)(v13 + 8);
              if ( v15 )
                LeaveCriticalSection(v15);
              *(_DWORD *)(v13 + 80) = 1;
              v16 = *(_OWORD *)GlobalThreadState();
              v17 = *(_OWORD *)GlobalThreadState();
              v18 = *((_BYTE *)GlobalThreadState() + 16);
              *(_OWORD *)GlobalThreadState() = v16;
              *((_BYTE *)GlobalThreadState() + 16) = 1;
              _GWPostMethodCallEx(*(struct GWND **)(v13 + 56), v13, (__int64)CTimerCtx::OnMethodCall, 0, 1, 0);
              *(_OWORD *)GlobalThreadState() = v17;
              *((_BYTE *)GlobalThreadState() + 16) = v18;
            }
          }
        }
LABEL_3:
        i += 32;
      }
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
    if ( v5 )
      LeaveCriticalSection(v5);
    if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
      McTemplateU0pq_EventWriteTransfer(
        (REGHANDLE *)&BERP_IE_Context,
        (const EVENT_DESCRIPTOR *)MSHTML_CTIMERMAN_WAIT_START,
        (__int64)this,
        v9);
    v6 = WaitForSingleObject(*((HANDLE *)this + 60), v9);
    v7 = v6;
    if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
      McTemplateU0pq_EventWriteTransfer(
        (REGHANDLE *)&BERP_IE_Context,
        (const EVENT_DESCRIPTOR *)MSHTML_CTIMERMAN_WAIT_STOP,
        (__int64)this,
        v6);
    v1 = v7 == 258;
  }
}

```

## disassembly

```asm
0x180264950  mov     rax, rsp
0x180264953  mov     [rax+8], rcx
0x180264957  push    rbx
0x180264958  push    rbp
0x180264959  push    rsi
0x18026495a  push    rdi
0x18026495b  push    r12
0x18026495d  push    r13
0x18026495f  push    r14
0x180264961  push    r15
0x180264963  sub     rsp, 68h
0x180264967  xor     ebx, ebx
0x180264969  movaps  xmmword ptr [rax-58h], xmm6
0x18026496d  mov     r13b, bl
0x180264970  movaps  xmmword ptr [rax-68h], xmm7
0x180264974  mov     rsi, rcx
0x180264977  jmp     short loc_1802649E0
0x180264979  cmp     [r14+18h], ebx
0x18026497d  jz      loc_180264A90
0x180264983  add     r14, 20h ; ' '
0x180264987  sub     r15d, 1
0x18026498b  jnz     short loc_180264979
0x18026498d  mov     rcx, [rsi+8]; lpCriticalSection
0x180264991  test    rcx, rcx
0x180264994  jz      short loc_1802649A2
0x180264996  call    cs:__imp_LeaveCriticalSection
0x18026499d  nop     dword ptr [rax+rax+00h]
0x1802649a2  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1802649a9  jnz     loc_180264C17
0x1802649af  mov     rcx, [rsi+1E0h]; hHandle
0x1802649b6  mov     edx, r12d; dwMilliseconds
0x1802649b9  call    cs:__imp_WaitForSingleObject
0x1802649c0  nop     dword ptr [rax+rax+00h]
0x1802649c5  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1802649cc  mov     ebx, eax
0x1802649ce  jnz     loc_180264C35
0x1802649d4  cmp     ebx, 102h
0x1802649da  setz    r13b
0x1802649de  xor     ebx, ebx
0x1802649e0  cmp     [rsi+1D8h], ebx
0x1802649e6  jnz     loc_180264BAA
0x1802649ec  mov     rcx, [rsi+8]; lpCriticalSection
0x1802649f0  or      r12d, 0FFFFFFFFh
0x1802649f4  test    rcx, rcx
0x1802649f7  jz      short loc_180264A05
0x1802649f9  call    cs:__imp_EnterCriticalSection
0x180264a00  nop     dword ptr [rax+rax+00h]
0x180264a05  cmp     [rsi+44h], ebx
0x180264a08  jle     short loc_18026498D
0x180264a0a  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x180264a0f  mov     qword ptr [rsp+0A8h+PerformanceCount], 0
0x180264a18  call    cs:__imp_QueryPerformanceCounter
0x180264a1f  nop     dword ptr [rax+rax+00h]
0x180264a24  mov     r8, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x180264a2b  test    r8, r8
0x180264a2e  jz      loc_180264BEC
0x180264a34  mov     rdi, qword ptr [rsp+0A8h+PerformanceCount]
0x180264a39  test    rdi, rdi
0x180264a3c  jz      short loc_180264A74
0x180264a3e  test    r8, r8
0x180264a41  jz      short loc_180264A74
0x180264a43  cmp     r8, 3E8h
0x180264a4a  jz      short loc_180264A74
0x180264a4c  xor     edx, edx
0x180264a4e  mov     rax, rdi
0x180264a51  div     r8
0x180264a54  xor     edx, edx
0x180264a56  mov     rcx, rax
0x180264a59  imul    rax, r8
0x180264a5d  sub     rdi, rax
0x180264a60  imul    rax, rdi, 3E8h
0x180264a67  imul    rdi, rcx, 3E8h
0x180264a6e  div     r8
0x180264a71  add     rdi, rax
0x180264a74  sub     edi, [rsi+218h]
0x180264a7a  mov     r15d, [rsi+44h]
0x180264a7e  mov     r14, [rsi+48h]
0x180264a82  test    r15d, r15d
0x180264a85  jnz     loc_180264979
0x180264a8b  jmp     loc_18026498D
0x180264a90  mov     eax, [r14]
0x180264a93  cmp     eax, edi
0x180264a95  jbe     short loc_180264AB3
0x180264a97  test    r13b, r13b
0x180264a9a  jnz     loc_180264BC6
0x180264aa0  sub     eax, edi
0x180264aa2  cmp     eax, r12d
0x180264aa5  jnb     loc_180264983
0x180264aab  mov     r12d, eax
0x180264aae  jmp     loc_180264983
0x180264ab3  mov     rbp, [r14+10h]
0x180264ab7  mov     [r14+4], ebx
0x180264abb  cmp     [rbp+50h], ebx
0x180264abe  jnz     loc_180264983
0x180264ac4  cmp     [rbp+44h], ebx
0x180264ac7  jg      loc_180264983
0x180264acd  cmp     [rbp+54h], ebx
0x180264ad0  jnz     loc_180264983
0x180264ad6  mov     rcx, [rbp+8]; lpCriticalSection
0x180264ada  test    rcx, rcx
0x180264add  jz      short loc_180264AEB
0x180264adf  call    cs:__imp_EnterCriticalSection
0x180264ae6  nop     dword ptr [rax+rax+00h]
0x180264aeb  cmp     [rbp+48h], ebx
0x180264aee  jnz     loc_180264BD8
0x180264af4  mov     rcx, [rbp+8]; lpCriticalSection
0x180264af8  test    rcx, rcx
0x180264afb  jz      short loc_180264B09
0x180264afd  call    cs:__imp_LeaveCriticalSection
0x180264b04  nop     dword ptr [rax+rax+00h]
0x180264b09  mov     dword ptr [rbp+50h], 1
0x180264b10  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180264b17  nop     dword ptr [rax+rax+00h]
0x180264b1c  movups  xmm6, xmmword ptr [rax]
0x180264b1f  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180264b26  nop     dword ptr [rax+rax+00h]
0x180264b2b  movups  xmm7, xmmword ptr [rax]
0x180264b2e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180264b35  nop     dword ptr [rax+rax+00h]
0x180264b3a  mov     bl, [rax+10h]
0x180264b3d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180264b44  nop     dword ptr [rax+rax+00h]
0x180264b49  movdqu  xmmword ptr [rax], xmm6
0x180264b4d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180264b54  nop     dword ptr [rax+rax+00h]
0x180264b59  mov     [rsp+0A8h+var_80], 0; __int64
0x180264b62  lea     r8, ?OnMethodCall@CTimerCtx@@QEAAX_K@Z; CTimerCtx::OnMethodCall(unsigned __int64)
0x180264b69  xor     r9d, r9d
0x180264b6c  mov     [rsp+0A8h+var_88], 1; int
0x180264b74  mov     rdx, rbp
0x180264b77  mov     byte ptr [rax+10h], 1
0x180264b7b  mov     rcx, [rbp+38h]; struct GWND *
0x180264b7f  call    ?_GWPostMethodCallEx@@YAJPEAVGWND@@PEAXP8CVoid@@EAAX_K@Z2KP6AX2@Z@Z; _GWPostMethodCallEx(GWND *,void *,void (CVoid::*)(unsigned __int64),unsigned __int64,ulong,void (*)(unsigned __int64))
0x180264b84  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180264b8b  nop     dword ptr [rax+rax+00h]
0x180264b90  movdqu  xmmword ptr [rax], xmm7
0x180264b94  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180264b9b  nop     dword ptr [rax+rax+00h]
0x180264ba0  mov     [rax+10h], bl
0x180264ba3  xor     ebx, ebx
0x180264ba5  jmp     loc_180264983
0x180264baa  movaps  xmm6, [rsp+0A8h+var_58]
0x180264baf  movaps  xmm7, [rsp+0A8h+var_68]
0x180264bb4  add     rsp, 68h
0x180264bb8  pop     r15
0x180264bba  pop     r14
0x180264bbc  pop     r13
0x180264bbe  pop     r12
0x180264bc0  pop     rdi
0x180264bc1  pop     rsi
0x180264bc2  pop     rbp
0x180264bc3  pop     rbx
0x180264bc4  retn
0x180264bc6  cmp     [r14+4], ebx
0x180264bca  jz      loc_180264AA0
0x180264bd0  mov     [r14], edi
0x180264bd3  jmp     loc_180264AB3
0x180264bd8  mov     rcx, rbp; this
0x180264bdb  mov     dword ptr [rbp+54h], 1
0x180264be2  call    ?LeaveCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::LeaveCriticalSection(void)
0x180264be7  jmp     loc_180264983
0x180264bec  lea     rcx, ?s_qpcFrequency@CQPCTick@@0_KA; lpFrequency
0x180264bf3  call    cs:__imp_QueryPerformanceFrequency
0x180264bfa  nop     dword ptr [rax+rax+00h]
0x180264bff  mov     r8, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x180264c06  test    r8, r8
0x180264c09  jnz     loc_180264A34
0x180264c0f  mov     rdi, rbx
0x180264c12  jmp     loc_180264A74
0x180264c17  mov     r9d, r12d
0x180264c1a  lea     rdx, MSHTML_CTIMERMAN_WAIT_START
0x180264c21  mov     r8, rsi
0x180264c24  lea     rcx, BERP_IE_Context
0x180264c2b  call    McTemplateU0pq_EventWriteTransfer
0x180264c30  jmp     loc_1802649AF
0x180264c35  mov     r9d, ebx
0x180264c38  lea     rdx, MSHTML_CTIMERMAN_WAIT_STOP
0x180264c3f  mov     r8, rsi
0x180264c42  lea     rcx, BERP_IE_Context
0x180264c49  call    McTemplateU0pq_EventWriteTransfer
0x180264c4e  jmp     loc_1802649D4
```
