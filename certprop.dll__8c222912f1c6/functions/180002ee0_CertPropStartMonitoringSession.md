# CertPropStartMonitoringSession

- ea: `0x180002ee0`
- end: `0x18000305b`
- name: `CertPropStartMonitoringSession`
- size: `379`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800061c0`

## callees

- `0x180002560`
- `0x180002610`
- `0x180002ee0`
- `0x180004600`
- `0x180018bb4`
- `0x180018d78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ff8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ff8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f51`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002f60`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180002f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f6a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002feb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002feb`
- `WINSTA!WinStationQueryInformationW` at `0x180002fb8`
- `WINSTA!WinStationQueryInformationW` at `0x180002fb8`

## pseudocode

```c
__int64 __fastcall CertPropStartMonitoringSession(__int64 a1)
{
  int v2; // r9d
  __int64 v3; // rcx
  DWORD ThreadpoolWait; // edi
  int v5; // eax
  __int64 v6; // rcx
  int v8; // [rsp+50h] [rbp+8h] BYREF
  int v9; // [rsp+58h] [rbp+10h] BYREF

  v8 = 0;
  v9 = 0;
  WppTraceIndent(a1, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      v2,
      *(_DWORD *)(a1 + 8));
  }
  EnterCriticalSection(&g_csSessionList);
  if ( SetThreadToken(0, *(HANDLE *)(a1 + 416)) )
  {
    ThreadpoolWait = CertPropCreateThreadpoolWait(
                       v3,
                       (void *)a1,
                       *(void **)(a1 + 112),
                       (struct _TP_CALLBACK_ENVIRON_V3 *)(a1 + 424),
                       (PTP_WAIT *)(a1 + 16));
    if ( !ThreadpoolWait )
    {
      WinStationQueryInformationW(0, *(unsigned int *)(a1 + 8), 28, &v8, 4, &v9);
      if ( v8 )
      {
        *(_QWORD *)(a1 + 28) = 0;
        v5 = 0;
      }
      else
      {
        v5 = 1;
      }
      *(_DWORD *)(a1 + 564) = v5;
      *(_DWORD *)(a1 + 280) = *(_DWORD *)(a1 + 8);
      ThreadpoolWait = ReaderMonitorStartThread((LPVOID)(a1 + 24));
    }
    RevertToSelf();
  }
  else
  {
    ThreadpoolWait = GetLastError();
  }
  LeaveCriticalSection(&g_csSessionList);
  WppTraceIndent(v6, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      ThreadpoolWait);
  }
  return ThreadpoolWait;
}

```

## disassembly

```asm
0x180002ee0  sub     rsp, 48h
0x180002ee4  mov     [rsp+48h+arg_10], rbx
0x180002ee9  mov     edx, 2
0x180002eee  mov     [rsp+48h+var_8], rbp
0x180002ef3  mov     rbx, rcx
0x180002ef6  mov     [rsp+48h+var_10], rsi
0x180002efb  xor     esi, esi
0x180002efd  mov     [rsp+48h+arg_0], esi
0x180002f01  mov     [rsp+48h+arg_8], esi
0x180002f05  call    WppTraceIndent
0x180002f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f11  lea     rbp, WPP_GLOBAL_Control
0x180002f18  cmp     rcx, rbp
0x180002f1b  jz      short loc_180002F45
0x180002f1d  test    byte ptr [rcx+1Ch], 1
0x180002f21  jz      short loc_180002F45
0x180002f23  cmp     byte ptr [rcx+19h], 4
0x180002f27  jb      short loc_180002F45
0x180002f29  mov     eax, [rbx+8]
0x180002f2c  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180002f33  mov     rcx, [rcx+10h]
0x180002f37  mov     edx, 29h ; ')'
0x180002f3c  mov     dword ptr [rsp+48h+var_28], eax
0x180002f40  call    WPP_SF_sd
0x180002f45  lea     rcx, g_csSessionList; lpCriticalSection
0x180002f4c  mov     [rsp+48h+var_18], rdi
0x180002f51  call    cs:__imp_EnterCriticalSection
0x180002f57  mov     rdx, [rbx+1A0h]; Token
0x180002f5e  xor     ecx, ecx; Thread
0x180002f60  call    cs:__imp_SetThreadToken
0x180002f66  test    eax, eax
0x180002f68  jnz     short loc_180002F74
0x180002f6a  call    cs:__imp_GetLastError
0x180002f70  mov     edi, eax
0x180002f72  jmp     short loc_180002FF1
0x180002f74  mov     r8, [rbx+70h]
0x180002f78  lea     rax, [rbx+10h]
0x180002f7c  lea     r9, [rbx+1A8h]
0x180002f83  mov     [rsp+48h+var_28], rax
0x180002f88  mov     rdx, rbx
0x180002f8b  call    CertPropCreateThreadpoolWait
0x180002f90  mov     edi, eax
0x180002f92  test    eax, eax
0x180002f94  jnz     short loc_180002FEB
0x180002f96  mov     edx, [rbx+8]
0x180002f99  lea     rax, [rsp+48h+arg_8]
0x180002f9e  mov     [rsp+48h+var_20], rax
0x180002fa3  lea     r9, [rsp+48h+arg_0]
0x180002fa8  mov     r8d, 1Ch
0x180002fae  mov     dword ptr [rsp+48h+var_28], 4
0x180002fb6  xor     ecx, ecx
0x180002fb8  call    cs:__imp_WinStationQueryInformationW
0x180002fbe  cmp     [rsp+48h+arg_0], esi
0x180002fc2  jz      short loc_180002FCC
0x180002fc4  mov     [rbx+1Ch], rsi
0x180002fc8  mov     eax, esi
0x180002fca  jmp     short loc_180002FD1
0x180002fcc  mov     eax, 1
0x180002fd1  mov     [rbx+234h], eax
0x180002fd7  lea     rcx, [rbx+18h]; lpParameter
0x180002fdb  mov     eax, [rbx+8]
0x180002fde  mov     [rbx+118h], eax
0x180002fe4  call    ReaderMonitorStartThread
0x180002fe9  mov     edi, eax
0x180002feb  call    cs:__imp_RevertToSelf
0x180002ff1  lea     rcx, g_csSessionList; lpCriticalSection
0x180002ff8  call    cs:__imp_LeaveCriticalSection
0x180002ffe  mov     edx, 2
0x180003003  call    WppTraceIndent
0x180003008  mov     rcx, cs:WPP_GLOBAL_Control
0x18000300f  mov     rsi, [rsp+48h+var_10]
0x180003014  cmp     rcx, rbp
0x180003017  mov     rbp, [rsp+48h+var_8]
0x18000301c  mov     rbx, [rsp+48h+arg_10]
0x180003021  jz      short loc_18000304F
0x180003023  test    byte ptr [rcx+1Ch], 1
0x180003027  jz      short loc_18000304F
0x180003029  cmp     byte ptr [rcx+19h], 4
0x18000302d  jb      short loc_18000304F
0x18000302f  mov     r9, cs:WPP_pszIndent
0x180003036  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000303d  mov     rcx, [rcx+10h]
0x180003041  mov     edx, 2Ah ; '*'
0x180003046  mov     dword ptr [rsp+48h+var_28], edi
0x18000304a  call    WPP_SF_sD
0x18000304f  mov     eax, edi
0x180003051  mov     rdi, [rsp+48h+var_18]
0x180003056  add     rsp, 48h
0x18000305a  retn
```
