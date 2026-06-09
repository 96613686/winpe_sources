# CTimerMan::ThreadExec(void)

- ea: `0x1801a0fc0`
- end: `0x1801a126e`
- name: `?ThreadExec@CTimerMan@@MEAAXXZ`
- size: `686`
- prototype: `void __fastcall(CTimerMan *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1801a0fc0`
- `0x1801a194c`
- `0x180497b40`
- `0x1807b5a24`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1801a1076`
- `KERNEL32!QueryPerformanceCounter` at `0x1801a1076`
- `KERNEL32!QueryPerformanceFrequency` at `0x1801a1214`
- `KERNEL32!QueryPerformanceFrequency` at `0x1801a1214`
- `KERNEL32!LeaveCriticalSection` at `0x1801a1006`
- `KERNEL32!LeaveCriticalSection` at `0x1801a114f`
- `KERNEL32!LeaveCriticalSection` at `0x1801a1006`
- `KERNEL32!LeaveCriticalSection` at `0x1801a114f`
- `KERNEL32!EnterCriticalSection` at `0x1801a105d`
- `KERNEL32!EnterCriticalSection` at `0x1801a1137`
- `KERNEL32!EnterCriticalSection` at `0x1801a105d`
- `KERNEL32!EnterCriticalSection` at `0x1801a1137`
- `KERNEL32!WaitForSingleObject` at `0x1801a1023`
- `KERNEL32!WaitForSingleObject` at `0x1801a1023`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a115c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1165`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a116e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1177`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1181`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a11b2`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a11bc`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a115c`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1165`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a116e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1177`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1181`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a11b2`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a11bc`

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
  DWORD v9; // r12d
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
      McTemplateU0pq_EventWriteTransfer(&BERP_IE_Context, &MSHTML_CTIMERMAN_WAIT_START, this, v9);
    v6 = WaitForSingleObject(*((HANDLE *)this + 60), v9);
    v7 = v6;
    if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
      McTemplateU0pq_EventWriteTransfer(&BERP_IE_Context, &MSHTML_CTIMERMAN_WAIT_STOP, this, v6);
    v1 = v7 == 258;
  }
}

```

## disassembly

```asm
0x1801a0fc0  mov     rax, rsp
0x1801a0fc3  mov     [rax+8], rcx
0x1801a0fc7  push    rbx
0x1801a0fc8  push    rbp
0x1801a0fc9  push    rsi
0x1801a0fca  push    rdi
0x1801a0fcb  push    r12
0x1801a0fcd  push    r13
0x1801a0fcf  push    r14
0x1801a0fd1  push    r15
0x1801a0fd3  sub     rsp, 68h
0x1801a0fd7  xor     ebx, ebx
0x1801a0fd9  movaps  xmmword ptr [rax-58h], xmm6
0x1801a0fdd  mov     r13b, bl
0x1801a0fe0  movaps  xmmword ptr [rax-68h], xmm7
0x1801a0fe4  mov     rsi, rcx
0x1801a0fe7  jmp     short loc_1801A1044
0x1801a0fe9  cmp     [r14+18h], ebx
0x1801a0fed  jz      loc_1801A10E8
0x1801a0ff3  add     r14, 20h ; ' '
0x1801a0ff7  sub     r15d, 1
0x1801a0ffb  jnz     short loc_1801A0FE9
0x1801a0ffd  mov     rcx, [rsi+8]; lpCriticalSection
0x1801a1001  test    rcx, rcx
0x1801a1004  jz      short loc_1801A100C
0x1801a1006  call    cs:__imp_LeaveCriticalSection
0x1801a100c  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1801a1013  jnz     loc_1801A1232
0x1801a1019  mov     rcx, [rsi+1E0h]; hHandle
0x1801a1020  mov     edx, r12d; dwMilliseconds
0x1801a1023  call    cs:__imp_WaitForSingleObject
0x1801a1029  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1801a1030  mov     ebx, eax
0x1801a1032  jnz     loc_1801A1250
0x1801a1038  cmp     ebx, 102h
0x1801a103e  setz    r13b
0x1801a1042  xor     ebx, ebx
0x1801a1044  cmp     [rsi+1D8h], ebx
0x1801a104a  jnz     loc_1801A11CC
0x1801a1050  mov     rcx, [rsi+8]; lpCriticalSection
0x1801a1054  or      r12d, 0FFFFFFFFh
0x1801a1058  test    rcx, rcx
0x1801a105b  jz      short loc_1801A1063
0x1801a105d  call    cs:__imp_EnterCriticalSection
0x1801a1063  cmp     [rsi+44h], ebx
0x1801a1066  jle     short loc_1801A0FFD
0x1801a1068  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x1801a106d  mov     qword ptr [rsp+0A8h+PerformanceCount], 0
0x1801a1076  call    cs:__imp_QueryPerformanceCounter
0x1801a107c  mov     r8, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x1801a1083  test    r8, r8
0x1801a1086  jz      loc_1801A120D
0x1801a108c  mov     rdi, qword ptr [rsp+0A8h+PerformanceCount]
0x1801a1091  test    rdi, rdi
0x1801a1094  jz      short loc_1801A10CC
0x1801a1096  test    r8, r8
0x1801a1099  jz      short loc_1801A10CC
0x1801a109b  cmp     r8, 3E8h
0x1801a10a2  jz      short loc_1801A10CC
0x1801a10a4  xor     edx, edx
0x1801a10a6  mov     rax, rdi
0x1801a10a9  div     r8
0x1801a10ac  xor     edx, edx
0x1801a10ae  mov     rcx, rax
0x1801a10b1  imul    rax, r8
0x1801a10b5  sub     rdi, rax
0x1801a10b8  imul    rax, rdi, 3E8h
0x1801a10bf  imul    rdi, rcx, 3E8h
0x1801a10c6  div     r8
0x1801a10c9  add     rdi, rax
0x1801a10cc  sub     edi, [rsi+218h]
0x1801a10d2  mov     r15d, [rsi+44h]
0x1801a10d6  mov     r14, [rsi+48h]
0x1801a10da  test    r15d, r15d
0x1801a10dd  jnz     loc_1801A0FE9
0x1801a10e3  jmp     loc_1801A0FFD
0x1801a10e8  mov     eax, [r14]
0x1801a10eb  cmp     eax, edi
0x1801a10ed  jbe     short loc_1801A110B
0x1801a10ef  test    r13b, r13b
0x1801a10f2  jnz     loc_1801A11E7
0x1801a10f8  sub     eax, edi
0x1801a10fa  cmp     eax, r12d
0x1801a10fd  jnb     loc_1801A0FF3
0x1801a1103  mov     r12d, eax
0x1801a1106  jmp     loc_1801A0FF3
0x1801a110b  mov     rbp, [r14+10h]
0x1801a110f  mov     [r14+4], ebx
0x1801a1113  cmp     [rbp+50h], ebx
0x1801a1116  jnz     loc_1801A0FF3
0x1801a111c  cmp     [rbp+44h], ebx
0x1801a111f  jg      loc_1801A0FF3
0x1801a1125  cmp     [rbp+54h], ebx
0x1801a1128  jnz     loc_1801A0FF3
0x1801a112e  mov     rcx, [rbp+8]; lpCriticalSection
0x1801a1132  test    rcx, rcx
0x1801a1135  jz      short loc_1801A113D
0x1801a1137  call    cs:__imp_EnterCriticalSection
0x1801a113d  cmp     [rbp+48h], ebx
0x1801a1140  jnz     loc_1801A11F9
0x1801a1146  mov     rcx, [rbp+8]; lpCriticalSection
0x1801a114a  test    rcx, rcx
0x1801a114d  jz      short loc_1801A1155
0x1801a114f  call    cs:__imp_LeaveCriticalSection
0x1801a1155  mov     dword ptr [rbp+50h], 1
0x1801a115c  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a1162  movups  xmm6, xmmword ptr [rax]
0x1801a1165  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a116b  movups  xmm7, xmmword ptr [rax]
0x1801a116e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a1174  mov     bl, [rax+10h]
0x1801a1177  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a117d  movdqu  xmmword ptr [rax], xmm6
0x1801a1181  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a1187  mov     [rsp+0A8h+var_80], 0; __int64
0x1801a1190  lea     r8, ?OnMethodCall@CTimerCtx@@QEAAX_K@Z; CTimerCtx::OnMethodCall(unsigned __int64)
0x1801a1197  xor     r9d, r9d
0x1801a119a  mov     [rsp+0A8h+var_88], 1; int
0x1801a11a2  mov     rdx, rbp
0x1801a11a5  mov     byte ptr [rax+10h], 1
0x1801a11a9  mov     rcx, [rbp+38h]; struct GWND *
0x1801a11ad  call    ?_GWPostMethodCallEx@@YAJPEAVGWND@@PEAXP8CVoid@@EAAX_K@Z2KP6AX2@Z@Z; _GWPostMethodCallEx(GWND *,void *,void (CVoid::*)(unsigned __int64),unsigned __int64,ulong,void (*)(unsigned __int64))
0x1801a11b2  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a11b8  movdqu  xmmword ptr [rax], xmm7
0x1801a11bc  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a11c2  mov     [rax+10h], bl
0x1801a11c5  xor     ebx, ebx
0x1801a11c7  jmp     loc_1801A0FF3
0x1801a11cc  movaps  xmm6, [rsp+0A8h+var_58]
0x1801a11d1  movaps  xmm7, [rsp+0A8h+var_68]
0x1801a11d6  add     rsp, 68h
0x1801a11da  pop     r15
0x1801a11dc  pop     r14
0x1801a11de  pop     r13
0x1801a11e0  pop     r12
0x1801a11e2  pop     rdi
0x1801a11e3  pop     rsi
0x1801a11e4  pop     rbp
0x1801a11e5  pop     rbx
0x1801a11e6  retn
0x1801a11e7  cmp     [r14+4], ebx
0x1801a11eb  jz      loc_1801A10F8
0x1801a11f1  mov     [r14], edi
0x1801a11f4  jmp     loc_1801A110B
0x1801a11f9  mov     rcx, rbp; this
0x1801a11fc  mov     dword ptr [rbp+54h], 1
0x1801a1203  call    ?LeaveCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::LeaveCriticalSection(void)
0x1801a1208  jmp     loc_1801A0FF3
0x1801a120d  lea     rcx, ?s_qpcFrequency@CQPCTick@@0_KA; lpFrequency
0x1801a1214  call    cs:__imp_QueryPerformanceFrequency
0x1801a121a  mov     r8, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x1801a1221  test    r8, r8
0x1801a1224  jnz     loc_1801A108C
0x1801a122a  mov     rdi, rbx
0x1801a122d  jmp     loc_1801A10CC
0x1801a1232  mov     r9d, r12d
0x1801a1235  lea     rdx, MSHTML_CTIMERMAN_WAIT_START
0x1801a123c  mov     r8, rsi
0x1801a123f  lea     rcx, BERP_IE_Context
0x1801a1246  call    McTemplateU0pq_EventWriteTransfer
0x1801a124b  jmp     loc_1801A1019
0x1801a1250  mov     r9d, ebx
0x1801a1253  lea     rdx, MSHTML_CTIMERMAN_WAIT_STOP
0x1801a125a  mov     r8, rsi
0x1801a125d  lea     rcx, BERP_IE_Context
0x1801a1264  call    McTemplateU0pq_EventWriteTransfer
0x1801a1269  jmp     loc_1801A1038
```
