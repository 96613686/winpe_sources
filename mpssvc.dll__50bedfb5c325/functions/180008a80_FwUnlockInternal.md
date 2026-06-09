# FwUnlockInternal

- ea: `0x180008a80`
- end: `0x180008d50`
- name: `FwUnlockInternal`
- size: `720`
- prototype: `__int64 __fastcall(void *, char *)`
- caller_count: `68`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800068fc`
- `0x180033840`
- `0x1800355c0`
- `0x180035c98`
- `0x180036ecc`
- `0x180037418`
- `0x180037aa0`
- `0x180039644`
- `0x18003d708`
- `0x180042754`
- `0x180042a4c`
- `0x180043758`
- `0x180047e34`
- `0x180054ea8`
- `0x180056310`
- `0x180057170`
- `0x180059320`
- `0x18005a810`
- `0x18005adb4`
- `0x18005d468`
- `0x18005d940`
- `0x180063a40`
- `0x180064e60`
- `0x180065050`
- `0x180065360`
- `0x180065c30`
- `0x18006d5f4`
- `0x18006e9f4`
- `0x1800782c0`
- `0x180078c1c`
- `0x180081250`
- `0x180084960`
- `0x180089090`
- `0x180089244`
- `0x18008ec20`
- `0x180095830`
- `0x180097e50`
- `0x18009b0f0`
- `0x18009b620`
- `0x18009bb44`
- `0x18009cea8`
- `0x18009d778`
- `0x18009dafc`
- `0x18009de48`
- `0x18009e1d8`
- `0x18009e51c`
- `0x18009e988`
- `0x18009edb8`
- `0x18009f98c`
- `0x18009fd80`

## callees

- `0x1800087cc`
- `0x180008a80`
- `0x180009e50`
- `0x18000a710`
- `0x18002fb84`
- `0x18002fdec`
- `0x18006781c`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008af7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008c3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008c3c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008ae4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008ae4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008ad3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008ad3`

## pseudocode

```c
void __fastcall FwUnlockInternal(void *a1, char *a2)
{
  struct _TP_TIMER *v2; // rbx
  __int64 v5; // r15
  wil::details *v6; // rcx
  unsigned __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // r13
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // r9d
  unsigned int v13; // r8d
  char v14; // r8
  unsigned __int64 v15; // r12
  signed __int64 v16; // rax
  signed __int64 v17; // rtt
  unsigned __int64 v18; // rdi
  signed int LastError; // eax
  unsigned int v20; // [rsp+30h] [rbp-68h]
  _DWORD v21[2]; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-58h]
  signed __int64 v23; // [rsp+48h] [rbp-50h]
  int v24; // [rsp+50h] [rbp-48h] BYREF

  v2 = pti;
  if ( pti )
  {
    _InterlockedCompareExchange(&gIsFwWatchDogCanceled, 1, 0);
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
  }
  v5 = qword_1801320B0;
  v7 = GetTickCount64() - qword_1801320B8;
  v8 = *Feature_WFDiagnosticTracing__descriptor;
  if ( (*(_BYTE *)Feature_WFDiagnosticTracing__descriptor & 0xC) == 0xC )
  {
    LODWORD(v15) = HIDWORD(*Feature_WFDiagnosticTracing__descriptor);
  }
  else
  {
    v9 = v8 >> 32;
    v24 = 0;
    v20 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(v6);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCurrentVariantState(v10, v21, &v24);
    if ( !v20 )
      v24 = 0;
    v11 = v21[0];
    while ( 1 )
    {
      if ( (v8 & 8) != 0 )
      {
        v12 = v9;
        v13 = v8;
      }
      else
      {
        v12 = v21[1];
        v13 = (v24 != 0 ? 8 : 0) | v11 & 0x800 | v8 & 0xFFFC07F7 | v11 & 0x3F000;
      }
      HIDWORD(v22) = v12;
      v23 = __PAIR64__(v9, v8);
      if ( (v8 & 4) == 0 )
        v13 = v11 & 0x400 | v13 & 0xFFFFFBFF | 4;
      LODWORD(v22) = v13;
      v14 = v23;
      v15 = HIDWORD(v22);
      v17 = v23;
      v16 = _InterlockedCompareExchange64(Feature_WFDiagnosticTracing__descriptor, v22, v23);
      if ( v17 == v16 )
        break;
      LODWORD(v8) = v16;
      LODWORD(v9) = HIDWORD(v16);
    }
    if ( (v14 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_WFDiagnosticTracing__descriptor,
        0,
        v20);
  }
  v18 = gFwLockSamplingCounter;
  if ( v7 >= (unsigned int)v15 )
    v18 = ++gFwLockSamplingCounter;
  if ( ReleaseMutex(hMutex) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        19,
        WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids,
        (unsigned int)dword_1801320A8);
  }
  else
  {
    LastError = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_dd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        18,
        WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids,
        (unsigned int)dword_1801320A8,
        LastError);
    }
  }
  FwTelemetryEventWriteFwLockTimeout(a1, a2, v5, v7, v18);
}

```

## disassembly

```asm
0x180008a80  push    rbx
0x180008a82  push    rbp
0x180008a83  push    rsi
0x180008a84  push    rdi
0x180008a85  push    r15
0x180008a87  sub     rsp, 70h
0x180008a8b  mov     rax, cs:__security_cookie
0x180008a92  xor     rax, rsp
0x180008a95  mov     [rsp+98h+var_40], rax
0x180008a9a  mov     rbx, cs:pti
0x180008aa1  mov     rbp, rdx
0x180008aa4  mov     [rsp+98h+arg_10], r12
0x180008aac  mov     rsi, rcx
0x180008aaf  mov     [rsp+98h+var_38], r14
0x180008ab4  test    rbx, rbx
0x180008ab7  jz      short loc_180008AF0
0x180008ab9  mov     edi, 1
0x180008abe  xor     eax, eax
0x180008ac0  lock cmpxchg cs:?gIsFwWatchDogCanceled@@3HC, edi; int volatile gIsFwWatchDogCanceled
0x180008ac8  xor     r9d, r9d; msWindowLength
0x180008acb  xor     r8d, r8d; msPeriod
0x180008ace  xor     edx, edx; pftDueTime
0x180008ad0  mov     rcx, rbx; pti
0x180008ad3  call    cs:__imp_SetThreadpoolTimer
0x180008ada  nop     dword ptr [rax+rax+00h]
0x180008adf  mov     edx, edi; fCancelPendingCallbacks
0x180008ae1  mov     rcx, rbx; pti
0x180008ae4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008aeb  nop     dword ptr [rax+rax+00h]
0x180008af0  mov     r15, cs:qword_1801320B0
0x180008af7  call    cs:__imp_GetTickCount64
0x180008afe  nop     dword ptr [rax+rax+00h]
0x180008b03  mov     rbx, rax
0x180008b06  mov     rax, cs:qword_1801320B8
0x180008b0d  mov     r14, cs:Feature_WFDiagnosticTracing__descriptor
0x180008b14  sub     rbx, rax
0x180008b17  mov     rdi, [r14]
0x180008b1a  mov     eax, edi
0x180008b1c  and     eax, 0Ch
0x180008b1f  cmp     al, 0Ch
0x180008b21  jz      loc_180008CA6
0x180008b27  mov     [rsp+98h+var_30], r13
0x180008b2c  mov     r13, rdi
0x180008b2f  sar     r13, 20h
0x180008b33  mov     [rsp+98h+var_48], 0
0x180008b3b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008b40  lea     r8, [rsp+98h+var_48]
0x180008b45  mov     [rsp+98h+var_68], eax
0x180008b49  lea     rdx, [rsp+98h+var_60]
0x180008b4e  mov     r12d, eax
0x180008b51  call    ?GetCurrentVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCurrentVariantState(int *)
0x180008b56  test    r12d, r12d
0x180008b59  jz      loc_180008D08
0x180008b5f  mov     rcx, [rsp+98h+var_60]
0x180008b64  test    dil, 8
0x180008b68  jnz     loc_180008D15
0x180008b6e  mov     r9d, dword ptr [rsp+98h+var_60+4]
0x180008b73  mov     r8d, ecx
0x180008b76  and     r8d, 3F000h
0x180008b7d  mov     eax, edi
0x180008b7f  and     eax, 0FFFC0FFFh
0x180008b84  or      r8d, eax
0x180008b87  mov     eax, [rsp+98h+var_48]
0x180008b8b  neg     eax
0x180008b8d  mov     eax, ecx
0x180008b8f  sbb     edx, edx
0x180008b91  and     r8d, 0FFFFF7F7h
0x180008b98  and     eax, 800h
0x180008b9d  and     edx, 8
0x180008ba0  or      r8d, eax
0x180008ba3  or      r8d, edx
0x180008ba6  mov     edx, r8d
0x180008ba9  mov     dword ptr [rsp+98h+var_58+4], r9d
0x180008bae  btr     edx, 0Ah
0x180008bb2  mov     dword ptr [rsp+98h+var_50], edi
0x180008bb6  mov     eax, ecx
0x180008bb8  mov     dword ptr [rsp+98h+var_50+4], r13d
0x180008bbd  and     eax, 400h
0x180008bc2  or      edx, eax
0x180008bc4  or      edx, 4
0x180008bc7  test    dil, 4
0x180008bcb  cmovz   r8d, edx
0x180008bcf  mov     dword ptr [rsp+98h+var_58], r8d
0x180008bd4  mov     rdx, [rsp+98h+var_58]
0x180008bd9  mov     r8, [rsp+98h+var_50]
0x180008bde  mov     r12, rdx
0x180008be1  shr     r12, 20h
0x180008be5  mov     rax, r8
0x180008be8  lock cmpxchg [r14], rdx
0x180008bed  jnz     loc_180008C98
0x180008bf3  mov     r13, [rsp+98h+var_30]
0x180008bf8  test    r8b, 4
0x180008bfc  jnz     short loc_180008C15
0x180008bfe  mov     r9d, [rsp+98h+var_68]
0x180008c03  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008c0a  xor     r8d, r8d
0x180008c0d  mov     rdx, r14
0x180008c10  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008c15  mov     r14, [rsp+98h+var_38]
0x180008c1a  mov     rdi, cs:?gFwLockSamplingCounter@@3_KA; unsigned __int64 gFwLockSamplingCounter
0x180008c21  mov     eax, r12d
0x180008c24  mov     r12, [rsp+98h+arg_10]
0x180008c2c  cmp     rbx, rax
0x180008c2f  jnb     loc_180008D20
0x180008c35  mov     rcx, cs:hMutex; hMutex
0x180008c3c  call    cs:__imp_ReleaseMutex
0x180008c43  nop     dword ptr [rax+rax+00h]
0x180008c48  test    eax, eax
0x180008c4a  jz      short loc_180008CB2
0x180008c4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c53  lea     rdx, WPP_GLOBAL_Control
0x180008c5a  cmp     rcx, rdx
0x180008c5d  jz      short loc_180008C69
0x180008c5f  test    byte ptr [rcx+1Ch], 4
0x180008c63  jnz     loc_180008D2F
0x180008c69  mov     r9, rbx; unsigned __int64
0x180008c6c  mov     [rsp+98h+var_78], rdi; unsigned __int64
0x180008c71  mov     r8, r15; unsigned __int64
0x180008c74  mov     rdx, rbp; char *
0x180008c77  mov     rcx, rsi; void *
0x180008c7a  call    ?FwTelemetryEventWriteFwLockTimeout@@YAXPEAXPEBD_K22@Z; FwTelemetryEventWriteFwLockTimeout(void *,char const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x180008c7f  mov     rcx, [rsp+98h+var_40]
0x180008c84  xor     rcx, rsp; StackCookie
0x180008c87  call    __security_check_cookie
0x180008c8c  add     rsp, 70h
0x180008c90  pop     r15
0x180008c92  pop     rdi
0x180008c93  pop     rsi
0x180008c94  pop     rbp
0x180008c95  pop     rbx
0x180008c96  retn
0x180008c98  mov     edi, eax
0x180008c9a  shr     rax, 20h
0x180008c9e  mov     r13d, eax
0x180008ca1  jmp     loc_180008B64
0x180008ca6  shr     rdi, 20h
0x180008caa  mov     r12d, edi
0x180008cad  jmp     loc_180008C15
0x180008cb2  call    cs:__imp_GetLastError
0x180008cb9  nop     dword ptr [rax+rax+00h]
0x180008cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cc5  lea     rdx, WPP_GLOBAL_Control
0x180008ccc  cmp     rcx, rdx
0x180008ccf  jz      short loc_180008C69
0x180008cd1  test    byte ptr [rcx+1Ch], 4
0x180008cd5  jz      short loc_180008C69
0x180008cd7  test    eax, eax
0x180008cd9  jle     short loc_180008CE3
0x180008cdb  movzx   eax, ax
0x180008cde  or      eax, 80070000h
0x180008ce3  mov     r9d, cs:dword_1801320A8
0x180008cea  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x180008cf1  mov     rcx, [rcx+10h]
0x180008cf5  mov     edx, 12h
0x180008cfa  mov     dword ptr [rsp+98h+var_78], eax
0x180008cfe  call    WPP_SF_dd
0x180008d03  jmp     loc_180008C69
0x180008d08  mov     [rsp+98h+var_48], 0
0x180008d10  jmp     loc_180008B5F
0x180008d15  mov     r9d, r13d
0x180008d18  mov     r8d, edi
0x180008d1b  jmp     loc_180008BA6
0x180008d20  inc     rdi
0x180008d23  mov     cs:?gFwLockSamplingCounter@@3_KA, rdi; unsigned __int64 gFwLockSamplingCounter
0x180008d2a  jmp     loc_180008C35
0x180008d2f  mov     r9d, cs:dword_1801320A8
0x180008d36  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x180008d3d  mov     rcx, [rcx+10h]
0x180008d41  mov     edx, 13h
0x180008d46  call    WPP_SF_d
0x180008d4b  jmp     loc_180008C69
```
