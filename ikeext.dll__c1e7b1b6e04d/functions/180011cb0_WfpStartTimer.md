# WfpStartTimer

- ea: `0x180011cb0`
- end: `0x180011f6c`
- name: `WfpStartTimer`
- size: `700`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003c468`
- `0x18003d320`
- `0x18003e7e0`
- `0x180065190`
- `0x18006572c`
- `0x180069884`
- `0x18006a7a0`
- `0x1800cb790`
- `0x1800cc0b0`
- `0x1800ccb80`
- `0x1800cd260`
- `0x1800ce2d0`

## callees

- `0x180010db0`
- `0x180011680`
- `0x180011cb0`
- `0x180016534`
- `0x18004890c`
- `0x180050850`
- `0x1800528e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ee7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ee7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011cf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011dfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011cf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011dfc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011d86`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011d86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011d3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011df3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011d3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011df3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011d55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011d55`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011d4c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011d4c`

## string_xrefs

- `0x180011e5d`: `CreateThreadpoolTimer`

## pseudocode

```c
__int64 __fastcall WfpStartTimer(__int64 a1, unsigned int a2, __int64 a3, struct _RTL_CRITICAL_SECTION *a4, _DWORD *pv)
{
  __int64 v9; // rdi
  struct _TP_TIMER *ThreadpoolTimer; // rax
  unsigned int v11; // edx
  signed int LastError; // ebx
  int v14; // r8d
  __int64 v15; // rcx
  __int64 v16; // rax
  int TlsPeerAddr; // eax
  int v18; // edx
  int v19; // r8d
  signed int v20; // [rsp+30h] [rbp-78h] BYREF
  _FILETIME pftDueTime; // [rsp+38h] [rbp-70h] BYREF
  char v22[16]; // [rsp+40h] [rbp-68h] BYREF
  const char *v23; // [rsp+50h] [rbp-58h]
  __int64 v24; // [rsp+58h] [rbp-50h]
  signed int *v25; // [rsp+60h] [rbp-48h]
  __int64 v26; // [rsp+68h] [rbp-40h]

  pftDueTime = 0;
  EnterCriticalSection(a4);
  if ( pv[6] == 1 )
  {
    LeaveCriticalSection(a4);
    EnterCriticalSection(a4);
    if ( (unsigned int)(pv[6] - 2) <= 1 )
    {
      LeaveCriticalSection(a4);
      v16 = WfpReportSysErrorAsNtStatus(v15, "WfpStopTimer", 259);
      v9 = v16;
      if ( v16 )
      {
        WfpReportError(v16, "WfpStopTimer");
LABEL_22:
        WfpReportError(v9, "WfpStartTimer");
        return v9;
      }
    }
    else
    {
      pv[6] = 2;
      LeaveCriticalSection(a4);
      SetThreadpoolTimer(*(PTP_TIMER *)pv, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)pv, 1);
      CloseThreadpoolTimer(*(PTP_TIMER *)pv);
      v9 = 0;
    }
  }
  else
  {
    v9 = 0;
    LeaveCriticalSection(a4);
  }
  *(_OWORD *)pv = 0;
  *((_OWORD *)pv + 1) = 0;
  *((_QWORD *)pv + 4) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(WfpUserModeTimerInternalCallback, pv, 0);
  *(_QWORD *)pv = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    *((_QWORD *)pv + 1) = a1;
    *((_QWORD *)pv + 2) = a3;
    *((_QWORD *)pv + 4) = a4;
    if ( a2 <= 1 )
      v11 = 1;
    else
      v11 = 95 * a2 / 0x64;
    pftDueTime = (_FILETIME)(-10000000LL * v11);
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 1000 * a2 / 0x14);
    EnterCriticalSection(a4);
    pv[6] = 1;
    LeaveCriticalSection(a4);
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      TlsPeerAddr = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
      WPP_SF_SsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        v19,
        TlsPeerAddr,
        (__int64)"CreateThreadpoolTimer",
        LastError);
    }
    if ( gWfpLogUserModeErrors && (byte_180178161 & 1) != 0 )
    {
      v20 = LastError;
      v25 = &v20;
      v23 = "CreateThreadpoolTimer";
      v24 = 22;
      v26 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v14,
        3,
        (__int64)v22);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = LastError;
  }
  if ( v9 )
    goto LABEL_22;
  return v9;
}

```

## disassembly

```asm
0x180011cb0  mov     [rsp+arg_0], rbx
0x180011cb5  mov     [rsp+arg_10], rbp
0x180011cba  push    rsi
0x180011cbb  push    rdi
0x180011cbc  push    r12
0x180011cbe  push    r14
0x180011cc0  push    r15
0x180011cc2  sub     rsp, 80h
0x180011cc9  mov     rax, cs:__security_cookie
0x180011cd0  xor     rax, rsp
0x180011cd3  mov     [rsp+0A8h+var_38], rax
0x180011cd8  mov     rbx, [rsp+0A8h+pv]
0x180011ce0  mov     r15, rcx
0x180011ce3  xor     r12d, r12d
0x180011ce6  mov     rcx, r9; lpCriticalSection
0x180011ce9  mov     qword ptr [rsp+0A8h+pftDueTime.dwLowDateTime], r12
0x180011cee  mov     rsi, r9
0x180011cf1  mov     r14, r8
0x180011cf4  mov     ebp, edx
0x180011cf6  call    cs:__imp_EnterCriticalSection
0x180011cfc  cmp     dword ptr [rbx+18h], 1
0x180011d00  mov     rcx, rsi; lpCriticalSection
0x180011d03  jnz     short loc_180011D60
0x180011d05  call    cs:__imp_LeaveCriticalSection
0x180011d0b  mov     rcx, rsi; lpCriticalSection
0x180011d0e  call    cs:__imp_EnterCriticalSection
0x180011d14  mov     eax, [rbx+18h]
0x180011d17  mov     rcx, rsi; lpCriticalSection
0x180011d1a  sub     eax, 2
0x180011d1d  cmp     eax, 1
0x180011d20  jbe     loc_180011EE7
0x180011d26  mov     dword ptr [rbx+18h], 2
0x180011d2d  call    cs:__imp_LeaveCriticalSection
0x180011d33  mov     rcx, [rbx]; pti
0x180011d36  xor     r9d, r9d; msWindowLength
0x180011d39  xor     r8d, r8d; msPeriod
0x180011d3c  xor     edx, edx; pftDueTime
0x180011d3e  call    cs:__imp_SetThreadpoolTimer
0x180011d44  mov     rcx, [rbx]; pti
0x180011d47  mov     edx, 1; fCancelPendingCallbacks
0x180011d4c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011d52  mov     rcx, [rbx]; pti
0x180011d55  call    cs:__imp_CloseThreadpoolTimer
0x180011d5b  mov     edi, r12d
0x180011d5e  jmp     short loc_180011D69
0x180011d60  mov     rdi, r12
0x180011d63  call    cs:__imp_LeaveCriticalSection
0x180011d69  xorps   xmm0, xmm0
0x180011d6c  lea     rcx, WfpUserModeTimerInternalCallback; pfnti
0x180011d73  movups  xmmword ptr [rbx], xmm0
0x180011d76  xor     eax, eax
0x180011d78  xor     r8d, r8d; pcbe
0x180011d7b  movups  xmmword ptr [rbx+10h], xmm0
0x180011d7f  mov     rdx, rbx; pv
0x180011d82  mov     [rbx+20h], rax
0x180011d86  call    cs:__imp_CreateThreadpoolTimer
0x180011d8c  mov     [rbx], rax
0x180011d8f  mov     r10, rax
0x180011d92  test    rax, rax
0x180011d95  jz      loc_180011E47
0x180011d9b  mov     [rbx+8], r15
0x180011d9f  mov     [rbx+10h], r14
0x180011da3  mov     [rbx+20h], rsi
0x180011da7  cmp     ebp, 1
0x180011daa  jbe     loc_180011EDD
0x180011db0  imul    ecx, ebp, 5Fh ; '_'
0x180011db3  mov     eax, 51EB851Fh
0x180011db8  mul     ecx
0x180011dba  shr     edx, 5
0x180011dbd  mov     eax, edx
0x180011dbf  xor     r8d, r8d; msPeriod
0x180011dc2  imul    rax, 0FFFFFFFFFF676980h
0x180011dc9  imul    edx, ebp, 3E8h
0x180011dcf  mov     rcx, rax
0x180011dd2  mov     [rsp+0A8h+pftDueTime.dwLowDateTime], eax
0x180011dd6  shr     rcx, 20h
0x180011dda  mov     eax, 0CCCCCCCDh
0x180011ddf  mov     [rsp+0A8h+pftDueTime.dwHighDateTime], ecx
0x180011de3  mov     rcx, r10; pti
0x180011de6  mul     edx
0x180011de8  shr     edx, 4
0x180011deb  mov     r9d, edx; msWindowLength
0x180011dee  lea     rdx, [rsp+0A8h+pftDueTime]; pftDueTime
0x180011df3  call    cs:__imp_SetThreadpoolTimer
0x180011df9  mov     rcx, rsi; lpCriticalSection
0x180011dfc  call    cs:__imp_EnterCriticalSection
0x180011e02  mov     rcx, rsi; lpCriticalSection
0x180011e05  mov     dword ptr [rbx+18h], 1
0x180011e0c  call    cs:__imp_LeaveCriticalSection
0x180011e12  test    rdi, rdi
0x180011e15  jnz     loc_180011F1A
0x180011e1b  mov     rax, rdi
0x180011e1e  mov     rcx, [rsp+0A8h+var_38]
0x180011e23  xor     rcx, rsp; StackCookie
0x180011e26  call    __security_check_cookie
0x180011e2b  lea     r11, [rsp+0A8h+var_28]
0x180011e33  mov     rbx, [r11+30h]
0x180011e37  mov     rbp, [r11+40h]
0x180011e3b  mov     rsp, r11
0x180011e3e  pop     r15
0x180011e40  pop     r14
0x180011e42  pop     r12
0x180011e44  pop     rdi
0x180011e45  pop     rsi
0x180011e46  retn
0x180011e47  call    cs:__imp_GetLastError
0x180011e4d  mov     ebx, eax
0x180011e4f  mov     rax, cs:WPP_GLOBAL_Control
0x180011e56  lea     rcx, WPP_GLOBAL_Control
0x180011e5d  lea     rdi, aCreatethreadpo_0; "CreateThreadpoolTimer"
0x180011e64  cmp     rax, rcx
0x180011e67  jz      short loc_180011E73
0x180011e69  cmp     byte ptr [rax+19h], 2
0x180011e6d  jnb     loc_180011F2E
0x180011e73  cmp     cs:gWfpLogUserModeErrors, r12d
0x180011e7a  jz      short loc_180011ECD
0x180011e7c  test    cs:byte_180178161, 1
0x180011e83  jz      short loc_180011ECD
0x180011e85  lea     rax, [rsp+0A8h+var_78]
0x180011e8a  mov     [rsp+0A8h+var_78], ebx
0x180011e8e  mov     [rsp+0A8h+var_48], rax
0x180011e93  lea     rdx, WFP_USERMODE_ERROR
0x180011e9a  lea     rax, [rsp+0A8h+var_68]
0x180011e9f  mov     [rsp+0A8h+var_58], rdi
0x180011ea4  mov     r9d, 3
0x180011eaa  mov     [rsp+0A8h+var_88], rax
0x180011eaf  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180011eb6  mov     [rsp+0A8h+var_50], 16h
0x180011ebf  mov     [rsp+0A8h+var_40], 4
0x180011ec8  call    McGenEventWrite_EtwEventWriteTransfer
0x180011ecd  test    ebx, ebx
0x180011ecf  jg      loc_180011F5E
0x180011ed5  movsxd  rdi, ebx
0x180011ed8  jmp     loc_180011E12
0x180011edd  mov     edx, 1
0x180011ee2  jmp     loc_180011DBD
0x180011ee7  call    cs:__imp_LeaveCriticalSection
0x180011eed  mov     r8d, 103h
0x180011ef3  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x180011efa  call    WfpReportSysErrorAsNtStatus
0x180011eff  mov     rdi, rax
0x180011f02  test    rax, rax
0x180011f05  jz      loc_180011D69
0x180011f0b  lea     rdx, aWfpstoptimer; "WfpStopTimer"
0x180011f12  mov     rcx, rax
0x180011f15  call    WfpReportError
0x180011f1a  lea     rdx, aWfpstarttimer; "WfpStartTimer"
0x180011f21  mov     rcx, rdi
0x180011f24  call    WfpReportError
0x180011f29  jmp     loc_180011E1B
0x180011f2e  test    byte ptr [rax+1Ch], 1
0x180011f32  jz      loc_180011E73
0x180011f38  call    IkeGetTlsPeerAddr
0x180011f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f44  mov     r9, rax
0x180011f47  mov     [rsp+0A8h+var_80], ebx
0x180011f4b  mov     [rsp+0A8h+var_88], rdi
0x180011f50  mov     rcx, [rcx+10h]
0x180011f54  call    WPP_SF_SsD
0x180011f59  jmp     loc_180011E73
0x180011f5e  movzx   ebx, bx
0x180011f61  or      ebx, 80070000h
0x180011f67  jmp     loc_180011ED5
```
