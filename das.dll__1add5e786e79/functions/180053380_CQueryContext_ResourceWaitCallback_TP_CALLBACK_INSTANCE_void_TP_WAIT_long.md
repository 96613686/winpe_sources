# CQueryContext::ResourceWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180053380`
- end: `0x1800535bd`
- name: `?ResourceWaitCallback@CQueryContext@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `573`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180007500`
- `0x18003bc80`
- `0x1800529dc`
- `0x180053380`
- `0x1800535c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005345f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800534a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800534c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005345f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800534a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800534c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053448`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053448`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800533d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800533d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180053593`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180053593`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180053474`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180053512`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180053474`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180053512`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180053484`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180053484`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180053529`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180053529`
- `RMCLIENT!RmAcquireResources` at `0x180053572`
- `RMCLIENT!RmAcquireResources` at `0x180053572`
- `RMCLIENT!RmReleaseResources` at `0x1800534c9`
- `RMCLIENT!RmReleaseResources` at `0x1800534c9`
- `RMCLIENT!RmGetNotification` at `0x1800533f7`
- `RMCLIENT!RmGetNotification` at `0x1800533f7`

## pseudocode

```c
void __fastcall CQueryContext::ResourceWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  _QWORD *v5; // rdi
  int Notification; // eax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  RTL_SRWLOCK *v10; // rcx
  struct _TP_TIMER *v11; // rcx
  int v12; // [rsp+50h] [rbp+7h] BYREF
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+Fh] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp+17h] BYREF
  int v15; // [rsp+70h] [rbp+27h]
  int v16; // [rsp+74h] [rbp+2Bh]
  __int128 v17; // [rsp+78h] [rbp+2Fh] BYREF

  v12 = 0;
  v14[0] = 47;
  v14[1] = 1;
  v17 = 0;
  v16 = 1;
  v15 = 2;
  AcquireSRWLockShared((PSRWLOCK)Context);
  if ( *((_DWORD *)Context + 2) )
  {
    v5 = Context + 536;
    Notification = RmGetNotification(*((_QWORD *)Context + 67), &v17);
    if ( Notification < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
LABEL_17:
        OnQueryStateUpdateStub(2, 8, *((_QWORD *)Context + 49));
        goto LABEL_18;
      }
      v9 = 51;
LABEL_5:
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v7,
        v8,
        v9,
        &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
        Notification);
      goto LABEL_17;
    }
    AcquireSRWLockExclusive((PSRWLOCK)Context + 68);
    v10 = (RTL_SRWLOCK *)(Context + 544);
    if ( (_DWORD)v17 )
    {
      if ( (unsigned int)(v17 - 1) > 1 )
      {
        ReleaseSRWLockExclusive(v10);
        goto LABEL_17;
      }
      pftDueTime = 0;
      *((_DWORD *)Context + 138) = 0;
      ReleaseSRWLockExclusive(v10);
      Notification = RmReleaseResources(*v5);
      if ( Notification < 0 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_17;
        v9 = 52;
        goto LABEL_5;
      }
      v11 = (struct _TP_TIMER *)*((_QWORD *)Context + 66);
      *v5 = 0;
      pftDueTime = (struct _FILETIME)-300000000LL;
      SetThreadpoolTimer(v11, &pftDueTime, 0, 0);
    }
    else
    {
      *((_DWORD *)Context + 138) = 1;
      ReleaseSRWLockExclusive(v10);
      SetThreadpoolTimer(*((PTP_TIMER *)Context + 66), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)Context + 66), 1);
      if ( (int)CQueryContext::RestoreProviderQueries((CQueryContext *)Context) < 0 )
        goto LABEL_17;
    }
    SetThreadpoolWait(*((PTP_WAIT *)Context + 65), *((HANDLE *)Context + 64), 0);
    if ( !*v5
      && (int)((__int64 (__fastcall *)(__int64, _QWORD *, _QWORD, _QWORD, char *, _QWORD, int, int, int *, char *))RmAcquireResources)(
                1,
                v14,
                0,
                *((unsigned int *)Context + 100),
                Context,
                *((_QWORD *)Context + 64),
                1,
                2,
                &v12,
                Context + 536) < 0 )
    {
      goto LABEL_17;
    }
  }
LABEL_18:
  ReleaseSRWLockShared((PSRWLOCK)Context);
}

```

## disassembly

```asm
0x180053380  mov     [rsp-8+arg_0], rbx
0x180053385  mov     [rsp-8+arg_10], rsi
0x18005338a  push    rbp
0x18005338b  push    rdi
0x18005338c  push    r15
0x18005338e  lea     rbp, [rsp-47h]
0x180053393  sub     rsp, 90h
0x18005339a  mov     rax, cs:__security_cookie
0x1800533a1  xor     rax, rsp
0x1800533a4  mov     [rbp+57h+var_18], rax
0x1800533a8  xorps   xmm0, xmm0
0x1800533ab  mov     [rbp+57h+var_50], 0
0x1800533b2  mov     r15d, 1
0x1800533b8  mov     [rbp+57h+var_40], 2Fh ; '/'
0x1800533c0  mov     rcx, rdx; SRWLock
0x1800533c3  mov     [rbp+57h+var_38], r15
0x1800533c7  movups  [rbp+57h+var_28], xmm0
0x1800533cb  mov     [rbp+57h+var_2C], r15d
0x1800533cf  mov     rbx, rdx
0x1800533d2  mov     [rbp+57h+var_30], 2
0x1800533d9  call    cs:__imp_AcquireSRWLockShared
0x1800533df  cmp     dword ptr [rbx+8], 0
0x1800533e3  jz      loc_180053590
0x1800533e9  lea     rdi, [rbx+218h]
0x1800533f0  mov     rcx, [rdi]
0x1800533f3  lea     rdx, [rbp+57h+var_28]
0x1800533f7  call    cs:__imp_RmGetNotification
0x1800533fd  test    eax, eax
0x1800533ff  jns     short loc_18005343E
0x180053401  lea     rcx, WPP_RECORDER_INITIALIZED
0x180053408  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005340f  jz      loc_18005357C
0x180053415  lea     r9d, [r15+32h]; int
0x180053419  mov     rcx, cs:WPP_GLOBAL_Control
0x180053420  mov     dword ptr [rsp+0A0h+var_78], eax; char
0x180053424  lea     rax, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x18005342b  mov     [rsp+0A0h+MessageGuid], rax; MessageGuid
0x180053430  mov     rcx, [rcx+28h]; int
0x180053434  call    WPP_RECORDER_SF_D
0x180053439  jmp     loc_18005357C
0x18005343e  lea     rsi, [rbx+220h]
0x180053445  mov     rcx, rsi; SRWLock
0x180053448  call    cs:__imp_AcquireSRWLockExclusive
0x18005344e  mov     eax, dword ptr [rbp+57h+var_28]
0x180053451  mov     rcx, rsi; SRWLock
0x180053454  test    eax, eax
0x180053456  jnz     short loc_18005349C
0x180053458  mov     [rbx+228h], r15d
0x18005345f  call    cs:__imp_ReleaseSRWLockExclusive
0x180053465  mov     rcx, [rbx+210h]; pti
0x18005346c  xor     r9d, r9d; msWindowLength
0x18005346f  xor     r8d, r8d; msPeriod
0x180053472  xor     edx, edx; pftDueTime
0x180053474  call    cs:__imp_SetThreadpoolTimer
0x18005347a  mov     rcx, [rbx+210h]; pti
0x180053481  mov     edx, r15d; fCancelPendingCallbacks
0x180053484  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005348a  mov     rcx, rbx; this
0x18005348d  call    ?RestoreProviderQueries@CQueryContext@@IEAAJXZ; CQueryContext::RestoreProviderQueries(void)
0x180053492  test    eax, eax
0x180053494  js      loc_18005357C
0x18005349a  jmp     short loc_180053518
0x18005349c  dec     eax
0x18005349e  cmp     eax, r15d
0x1800534a1  jbe     short loc_1800534AE
0x1800534a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800534a9  jmp     loc_18005357C
0x1800534ae  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], 0
0x1800534b6  mov     dword ptr [rbx+228h], 0
0x1800534c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800534c6  mov     rcx, [rdi]
0x1800534c9  call    cs:__imp_RmReleaseResources
0x1800534cf  test    eax, eax
0x1800534d1  jns     short loc_1800534F2
0x1800534d3  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800534da  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800534e1  jz      loc_18005357C
0x1800534e7  mov     r9d, 34h ; '4'
0x1800534ed  jmp     loc_180053419
0x1800534f2  mov     rcx, [rbx+210h]; pti
0x1800534f9  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x1800534fd  xor     r9d, r9d; msWindowLength
0x180053500  mov     qword ptr [rdi], 0
0x180053507  xor     r8d, r8d; msPeriod
0x18005350a  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x180053512  call    cs:__imp_SetThreadpoolTimer
0x180053518  mov     rdx, [rbx+200h]; h
0x18005351f  xor     r8d, r8d; pftTimeout
0x180053522  mov     rcx, [rbx+208h]; pwa
0x180053529  call    cs:__imp_SetThreadpoolWait
0x18005352f  cmp     qword ptr [rdi], 0
0x180053533  jnz     short loc_180053590
0x180053535  mov     r9d, [rbx+190h]
0x18005353c  lea     rax, [rbp+57h+var_50]
0x180053540  mov     [rsp+0A0h+var_58], rdi
0x180053545  lea     rdx, [rbp+57h+var_40]
0x180053549  mov     [rsp+0A0h+var_60], rax
0x18005354e  xor     r8d, r8d
0x180053551  mov     rax, [rbx+200h]
0x180053558  mov     ecx, r15d
0x18005355b  mov     [rsp+0A0h+var_68], 2
0x180053563  mov     [rsp+0A0h+var_70], r15d
0x180053568  mov     qword ptr [rsp+0A0h+var_78], rax
0x18005356d  mov     [rsp+0A0h+MessageGuid], rbx
0x180053572  call    cs:__imp_RmAcquireResources
0x180053578  test    eax, eax
0x18005357a  jns     short loc_180053590
0x18005357c  mov     r8, [rbx+188h]
0x180053583  mov     edx, 8
0x180053588  lea     ecx, [rdx-6]
0x18005358b  call    ?OnQueryStateUpdateStub@@YAJW4_DEV_QUERY_STATE@@W4_DAF_SECONDARY_QUERY_STATE@@PEAX@Z; OnQueryStateUpdateStub(_DEV_QUERY_STATE,_DAF_SECONDARY_QUERY_STATE,void *)
0x180053590  mov     rcx, rbx; SRWLock
0x180053593  call    cs:__imp_ReleaseSRWLockShared
0x180053599  mov     rcx, [rbp+57h+var_18]
0x18005359d  xor     rcx, rsp; StackCookie
0x1800535a0  call    __security_check_cookie
0x1800535a5  lea     r11, [rsp+0A0h+var_10]
0x1800535ad  mov     rbx, [r11+20h]
0x1800535b1  mov     rsi, [r11+30h]
0x1800535b5  mov     rsp, r11
0x1800535b8  pop     r15
0x1800535ba  pop     rdi
0x1800535bb  pop     rbp
0x1800535bc  retn
```
