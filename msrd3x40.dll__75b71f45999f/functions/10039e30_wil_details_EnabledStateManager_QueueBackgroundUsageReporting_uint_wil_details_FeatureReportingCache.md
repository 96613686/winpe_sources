# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x10039e30`
- end: `0x1003a005`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QAEXIPAUwil_details_FeatureReportingCache@@@Z`
- size: `469`
- prototype: `void __thiscall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1003a060`

## callees

- `0x1000a900`
- `0x1000eb60`
- `0x10039e30`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f10c`
- `0x1005f180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x10039eed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x10039f19`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x10039eed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x10039f19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x10039e93`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x10039e93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x10039feb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x10039feb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10039f8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10039f9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10039f8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10039f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10039f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10039f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10039f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10039f62`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x10039f73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x10039fc4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x10039f73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x10039fc4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x10039f87`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x10039f87`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x10039f7e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x10039f7e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x10039f4f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x10039f4f`

## pseudocode

```c
void __thiscall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        unsigned int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  _DWORD *v4; // edx
  int v5; // ecx
  DWORD LastError; // esi
  struct _TP_TIMER *v7; // eax
  DWORD dwHighDateTime; // [esp-4h] [ebp-34h]
  struct _FILETIME pftDueTime; // [esp+14h] [ebp-1Ch] BYREF
  PTP_TIMER ThreadpoolTimer; // [esp+1Ch] [ebp-14h]
  PTP_TIMER pti; // [esp+20h] [ebp-10h]

  if ( !*(_DWORD *)pv
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress
    && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(wil::details::g_pfnDllShutdownInProgress) )
  {
    return;
  }
  AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
  if ( !*(_DWORD *)pv
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress
    && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(wil::details::g_pfnDllShutdownInProgress) )
  {
    if ( pv == (char *)-4 )
      return;
    goto LABEL_27;
  }
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 20), 8u) )
  {
    v4 = (_DWORD *)*((_DWORD *)pv + 6);
    v5 = *((_DWORD *)pv + 7) - (_DWORD)v4;
    if ( v4 )
    {
      if ( (v5 & (unsigned int)-((unsigned int)v4 < *((_DWORD *)pv + 7))) >= 8 )
      {
        *v4 = a2;
        v4[1] = a3;
LABEL_16:
        *((_DWORD *)pv + 6) += 8;
        goto LABEL_17;
      }
      memset(v4, 0, (unsigned int)v4 < *((_DWORD *)pv + 7) ? v5 : 0);
      *__errno() = 34;
    }
    else
    {
      *__errno() = 22;
    }
    _invalid_parameter_noinfo();
    goto LABEL_16;
  }
LABEL_17:
  if ( !pv[12] )
  {
    if ( !*((_DWORD *)pv + 2) )
    {
      pftDueTime.dwHighDateTime = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          _lambda_2661d55a252888999c40ae12ee6f1cd7_::_lambda_invoker_stdcall_,
                          pv,
                          0);
      pti = (PTP_TIMER)*((_DWORD *)pv + 2);
      if ( pti )
      {
        LastError = GetLastError();
        SetThreadpoolTimer(pti, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(pti, 1);
        CloseThreadpoolTimer(pti);
        SetLastError(LastError);
      }
      dwHighDateTime = pftDueTime.dwHighDateTime;
      *((_DWORD *)pv + 2) = ThreadpoolTimer;
      SetLastError(dwHighDateTime);
    }
    v7 = (struct _TP_TIMER *)*((_DWORD *)pv + 2);
    if ( v7 )
    {
      pftDueTime.dwLowDateTime = 1294967296;
      pftDueTime.dwHighDateTime = -1;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      pv[12] = 1;
    }
  }
  if ( pv != (char *)-4 )
LABEL_27:
    ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
}

```

## disassembly

```asm
0x10039e30  mov     edi, edi
0x10039e32  push    ebp
0x10039e33  mov     ebp, esp
0x10039e35  push    0FFFFFFFFh
0x10039e37  push    offset ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QAEXIPAUwil_details_FeatureReportingCache@@@Z_SEH
0x10039e3c  mov     eax, large fs:0
0x10039e42  push    eax
0x10039e43  sub     esp, 14h
0x10039e46  push    ebx
0x10039e47  push    esi
0x10039e48  push    edi; unsigned int
0x10039e49  mov     eax, ___security_cookie
0x10039e4e  xor     eax, ebp
0x10039e50  push    eax; void *
0x10039e51  lea     eax, [ebp+var_C]
0x10039e54  mov     large fs:0, eax
0x10039e5a  mov     edi, ecx
0x10039e5c  mov     eax, [edi]
0x10039e5e  test    eax, eax
0x10039e60  jz      loc_10039FF1
0x10039e66  cmp     ?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x10039e6d  jnz     loc_10039FF1
0x10039e73  mov     esi, ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x10039e79  test    esi, esi
0x10039e7b  jz      short loc_10039E8F
0x10039e7d  mov     ecx, esi
0x10039e7f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10039e85  call    esi ; ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x10039e87  test    al, al
0x10039e89  jnz     loc_10039FF1
0x10039e8f  lea     ebx, [edi+4]
0x10039e92  push    ebx; SRWLock
0x10039e93  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x10039e99  mov     eax, [edi]
0x10039e9b  test    eax, eax
0x10039e9d  jz      loc_10039FE6
0x10039ea3  cmp     ?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x10039eaa  jnz     loc_10039FE6
0x10039eb0  mov     esi, ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x10039eb6  test    esi, esi
0x10039eb8  jz      short loc_10039ECC
0x10039eba  mov     ecx, esi
0x10039ebc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10039ec2  call    esi ; ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x10039ec4  test    al, al
0x10039ec6  jnz     loc_10039FE6
0x10039ecc  push    8; unsigned int
0x10039ece  lea     ecx, [edi+14h]; this
0x10039ed1  call    ?ensure@heap_buffer@details_abi@wil@@QAE_NI@Z; wil::details_abi::heap_buffer::ensure(uint)
0x10039ed6  test    al, al
0x10039ed8  jz      short loc_10039F2E
0x10039eda  mov     edx, [edi+18h]
0x10039edd  mov     ecx, [edi+1Ch]
0x10039ee0  sub     ecx, edx
0x10039ee2  cmp     edx, [edi+1Ch]
0x10039ee5  sbb     eax, eax
0x10039ee7  and     eax, ecx
0x10039ee9  test    edx, edx
0x10039eeb  jnz     short loc_10039EFB
0x10039eed  call    ds:__imp___errno
0x10039ef3  mov     dword ptr [eax], 16h
0x10039ef9  jmp     short loc_10039F25
0x10039efb  cmp     eax, 8
0x10039efe  jb      short loc_10039F0D
0x10039f00  mov     eax, [ebp+arg_0]
0x10039f03  mov     [edx], eax
0x10039f05  mov     eax, [ebp+arg_4]
0x10039f08  mov     [edx+4], eax
0x10039f0b  jmp     short loc_10039F2A
0x10039f0d  push    eax; Size
0x10039f0e  push    0; Val
0x10039f10  push    edx; void *
0x10039f11  call    _memset
0x10039f16  add     esp, 0Ch
0x10039f19  call    ds:__imp___errno
0x10039f1f  mov     dword ptr [eax], 22h ; '"'
0x10039f25  call    __invalid_parameter_noinfo
0x10039f2a  add     dword ptr [edi+18h], 8
0x10039f2e  cmp     byte ptr [edi+0Ch], 0
0x10039f32  jnz     loc_10039FCE
0x10039f38  cmp     dword ptr [edi+8], 0
0x10039f3c  jnz     short loc_10039FA3
0x10039f3e  call    ds:__imp__GetLastError@0; GetLastError()
0x10039f44  push    0; pcbe
0x10039f46  push    edi; pv
0x10039f47  push    offset ?_lambda_invoker_stdcall_@_lambda_2661d55a252888999c40ae12ee6f1cd7_@@CG@PAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_TIMER@@@Z; pfnti
0x10039f4c  mov     [ebp+pftDueTime.dwHighDateTime], eax
0x10039f4f  call    ds:__imp__CreateThreadpoolTimer@12; CreateThreadpoolTimer(x,x,x)
0x10039f55  mov     [ebp+var_14], eax
0x10039f58  mov     eax, [edi+8]
0x10039f5b  mov     [ebp+pti], eax
0x10039f5e  test    eax, eax
0x10039f60  jz      short loc_10039F94
0x10039f62  call    ds:__imp__GetLastError@0; GetLastError()
0x10039f68  push    0; msWindowLength
0x10039f6a  push    0; msPeriod
0x10039f6c  push    0; pftDueTime
0x10039f6e  push    [ebp+pti]; pti
0x10039f71  mov     esi, eax
0x10039f73  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x10039f79  push    1; fCancelPendingCallbacks
0x10039f7b  push    [ebp+pti]; pti
0x10039f7e  call    ds:__imp__WaitForThreadpoolTimerCallbacks@8; WaitForThreadpoolTimerCallbacks(x,x)
0x10039f84  push    [ebp+pti]; pti
0x10039f87  call    ds:__imp__CloseThreadpoolTimer@4; CloseThreadpoolTimer(x)
0x10039f8d  push    esi; dwErrCode
0x10039f8e  call    ds:__imp__SetLastError@4; SetLastError(x)
0x10039f94  mov     eax, [ebp+var_14]
0x10039f97  push    [ebp+pftDueTime.dwHighDateTime]; dwErrCode
0x10039f9a  mov     [edi+8], eax
0x10039f9d  call    ds:__imp__SetLastError@4; SetLastError(x)
0x10039fa3  mov     eax, [edi+8]
0x10039fa6  test    eax, eax
0x10039fa8  jz      short loc_10039FCE
0x10039faa  push    124F8h; msWindowLength
0x10039faf  push    0; msPeriod
0x10039fb1  lea     ecx, [ebp+pftDueTime]
0x10039fb4  mov     [ebp+pftDueTime.dwLowDateTime], 4D2FA200h
0x10039fbb  push    ecx; pftDueTime
0x10039fbc  push    eax; pti
0x10039fbd  mov     [ebp+pftDueTime.dwHighDateTime], 0FFFFFFFFh
0x10039fc4  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x10039fca  mov     byte ptr [edi+0Ch], 1
0x10039fce  test    ebx, ebx
0x10039fd0  jnz     short loc_10039FEA
0x10039fd2  mov     ecx, [ebp+var_C]
0x10039fd5  mov     large fs:0, ecx
0x10039fdc  pop     ecx
0x10039fdd  pop     edi
0x10039fde  pop     esi
0x10039fdf  pop     ebx
0x10039fe0  mov     esp, ebp
0x10039fe2  pop     ebp
0x10039fe3  retn    8
0x10039fe6  test    ebx, ebx
0x10039fe8  jz      short loc_10039FF1
0x10039fea  push    ebx; SRWLock
0x10039feb  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x10039ff1  mov     ecx, [ebp+var_C]
0x10039ff4  mov     large fs:0, ecx
0x10039ffb  pop     ecx
0x10039ffc  pop     edi
0x10039ffd  pop     esi
0x10039ffe  pop     ebx
0x10039fff  mov     esp, ebp
0x1003a001  pop     ebp
0x1003a002  retn    8
0x10060de0  nop
0x10060de1  nop
0x10060de2  mov     edx, [esp-4+arg_4]
0x10060de6  lea     eax, [edx+0Ch]
0x10060de9  mov     ecx, [edx-24h]
0x10060dec  xor     ecx, eax; StackCookie
0x10060dee  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060df3  mov     eax, offset stru_10062AB0
0x10060df8  jmp     ___CxxFrameHandler3
```
