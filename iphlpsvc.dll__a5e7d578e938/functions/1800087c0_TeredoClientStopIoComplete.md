# TeredoClientStopIoComplete

- ea: `0x1800087c0`
- end: `0x180008aee`
- name: `TeredoClientStopIoComplete`
- size: `814`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800087c0`
- `0x180008af4`
- `0x180008b90`
- `0x180008c50`
- `0x18000d7c0`
- `0x180014180`
- `0x1800163e4`
- `0x1800190f0`
- `0x180051eec`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800087e9`
- `ntdll!EtwEventActivityIdControl` at `0x1800087e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a1f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008a67`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008a67`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008853`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008853`
- `WS2_32!__imp_htons` at `0x180008921`
- `WS2_32!__imp_htons` at `0x180008921`
- `WS2_32!__imp_ntohs` at `0x1800088e5`
- `WS2_32!__imp_ntohs` at `0x180008930`
- `WS2_32!__imp_ntohs` at `0x1800088e5`
- `WS2_32!__imp_ntohs` at `0x180008930`
- `FirewallAPI!FWIndicatePortInUse` at `0x1800088fa`
- `FirewallAPI!FWIndicatePortInUse` at `0x180008945`
- `FirewallAPI!FWIndicatePortInUse` at `0x1800088fa`
- `FirewallAPI!FWIndicatePortInUse` at `0x180008945`

## string_xrefs

- `0x18000881b`: `TeredoClientStopIoComplete`
- `0x18000888f`: `TeredoClientStopIoComplete`
- `0x180008a41`: `TeredoClientStopIoComplete`
- `0x1800087fc`: `Teredo client stop io complete: ClientState = %d, Client = 0x%p`
- `0x1800089f4`: `TeredoClientStopIoComplete setting Teredo timer to %u ms. Consecutive failures: %u`
- `0x180008828`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x18000886b`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x180008a2f`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x180008a76`: `onecoreuap\net\netio\iphlpsvc\service\client.c`

## pseudocode

```c
__int64 __fastcall TeredoClientStopIoComplete(unsigned int *pv)
{
  __int64 v1; // rbp
  HANDLE v3; // rdi
  DWORD v4; // eax
  const wchar_t *v5; // rdx
  DWORD v6; // ebx
  u_short v7; // bx
  u_short v8; // ax
  unsigned int v9; // eax
  u_short v10; // ax
  u_short v11; // ax
  unsigned int v12; // eax
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rbx
  HANDLE v16; // rbx
  void *v17; // rcx
  unsigned int v18; // edx
  __int64 v19; // rcx
  __int64 result; // rax
  __int64 v21; // [rsp+20h] [rbp-58h]
  __int64 v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+28h] [rbp-50h]
  __int64 v24; // [rsp+30h] [rbp-48h]

  v1 = *((_QWORD *)pv + 988);
  EtwEventActivityIdControl(2, g_TeredoActivityId);
  EventWrite0(0x100000, L"Teredo client stop io complete: ClientState = %d, Client = 0x%p", pv[2146], pv);
  v3 = g_TeredoLock;
  EventWrite0(
    0x800000,
    L"Get lock (%p) invoked at %S : %S : %u",
    g_TeredoLock,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
    "TeredoClientStopIoComplete",
    3118);
  v4 = WaitForSingleObject(v3, 0xFFFFFFFF);
  v5 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
  v6 = v4;
  LODWORD(v22) = 3118;
  if ( v4 )
    v5 = L"Lock (%p) failed at %S : %S : %u. Return %d";
  EventWrite0(
    0x800000,
    v5,
    v3,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
    "TeredoClientStopIoComplete",
    v22,
    v4);
  if ( v6 )
  {
    if ( pv[2146] )
    {
      TeredoClientChangeStateAndLog(pv, 0);
      TeredoClientUpdateStateInNsi(pv);
    }
  }
  else
  {
    v7 = *((_WORD *)pv + 3903);
    EventWrite0(0x100000, L"Teredo deregister firewall exceptions");
    v8 = ntohs(v7);
    v9 = FWIndicatePortInUse(1, v8, 0);
    if ( v9 )
      EventWriteError0(0x100000, L"Failed to unregister random port exception in the firewall (%d)", v9);
    v10 = htons(0xDD8u);
    v11 = ntohs(v10);
    v12 = FWIndicatePortInUse(1, v11, 0);
    if ( v12 )
      EventWriteError0(0x100000, L"Failed to unregister port 3544 exception in the firewall (%d)", v12);
    *(_QWORD *)(pv + 1951) = 2;
    *(_QWORD *)(pv + 1953) = 0;
    if ( pv[2146] == 1 )
    {
      TeredoClientChangeStateAndLog(pv, 0);
      TeredoClientUpdateStateInNsi(pv);
      if ( !*(_DWORD *)(v1 + 24) )
      {
        ++pv[3592];
        v13 = 5;
        v14 = pv[3592];
        if ( v14 <= 5 )
          v13 = v14;
        else
          pv[3592] = 5;
        v15 = (unsigned int)TeredoResolveInterval(v1, 0, v13);
        EventWrite0(
          0x100000,
          L"TeredoClientStopIoComplete setting Teredo timer to %u ms. Consecutive failures: %u",
          v15,
          pv[3592]);
        TeredoSetTimer(v1, (unsigned int)v15, 1);
      }
    }
    else if ( pv[2146] == 2 )
    {
      TeredoClientChangeStateAndLog(pv, 0);
      TeredoClientUpdateStateInNsi(pv);
      TeredoStartClient(pv);
    }
    v16 = g_TeredoLock;
    LODWORD(v24) = ReleaseMutex(g_TeredoLock);
    LODWORD(v23) = 3202;
    EventWrite0(
      0x800000,
      L"Lock (%p) released at %S : %S : %u. Return %d",
      v16,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
      "TeredoClientStopIoComplete",
      v23,
      v24);
  }
  v17 = (void *)*((_QWORD *)pv + 1070);
  if ( v17 )
    SetEvent(v17);
  LODWORD(v21) = 3208;
  EventWrite0(
    0x100000,
    L"TeredoDereferenceClient: --%d @ %ls:%u",
    *pv,
    L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
    v21);
  v18 = *pv;
  v19 = 5LL * (_InterlockedExchangeAdd((volatile signed __int32 *)pv + 2, 1u) & 0x3F);
  pv[2 * v19 + 4] = v18;
  pv[2 * v19 + 8] = 3208;
  *(_QWORD *)&pv[2 * v19 + 6] = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c";
  pv[2 * v19 + 12] = 1;
  *(_QWORD *)&pv[2 * v19 + 10] = 0;
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)pv, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return TeredoCleanupClient(pv);
  return result;
}

```

## disassembly

```asm
0x1800087c0  push    rbx
0x1800087c2  push    rbp
0x1800087c3  push    rsi
0x1800087c4  push    rdi
0x1800087c5  push    r12
0x1800087c7  push    r13
0x1800087c9  push    r14
0x1800087cb  sub     rsp, 40h
0x1800087cf  mov     rbp, [rcx+1EE0h]
0x1800087d6  lea     rdx, g_TeredoActivityId
0x1800087dd  mov     rsi, rcx
0x1800087e0  mov     r13d, 2
0x1800087e6  mov     ecx, r13d
0x1800087e9  call    cs:__imp_EtwEventActivityIdControl
0x1800087f0  nop     dword ptr [rax+rax+00h]
0x1800087f5  mov     r8d, [rsi+2188h]
0x1800087fc  lea     rdx, aTeredoClientSt; "Teredo client stop io complete: ClientS"...
0x180008803  mov     r12d, 100000h
0x180008809  mov     r9, rsi
0x18000880c  mov     ecx, r12d
0x18000880f  call    EventWrite0
0x180008814  mov     rdi, cs:g_TeredoLock
0x18000881b  lea     rax, aTeredoclientst_0; "TeredoClientStopIoComplete"
0x180008822  mov     r14d, 0C2Eh
0x180008828  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000882f  mov     dword ptr [rsp+78h+var_50], r14d
0x180008834  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x18000883b  mov     r8, rdi
0x18000883e  mov     [rsp+78h+var_58], rax
0x180008843  mov     ecx, 800000h
0x180008848  call    EventWrite0
0x18000884d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008850  mov     rcx, rdi; hHandle
0x180008853  call    cs:__imp_WaitForSingleObject
0x18000885a  nop     dword ptr [rax+rax+00h]
0x18000885f  mov     r8, rdi
0x180008862  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180008869  mov     ebx, eax
0x18000886b  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180008872  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180008879  mov     dword ptr [rsp+78h+var_48], ebx
0x18000887d  test    ebx, ebx
0x18000887f  mov     dword ptr [rsp+78h+var_50], r14d
0x180008884  mov     edi, 800000h
0x180008889  cmovnz  rdx, rax
0x18000888d  mov     ecx, edi
0x18000888f  lea     rax, aTeredoclientst_0; "TeredoClientStopIoComplete"
0x180008896  mov     [rsp+78h+var_58], rax
0x18000889b  call    EventWrite0
0x1800088a0  lea     r14d, [r13-1]
0x1800088a4  test    ebx, ebx
0x1800088a6  jz      short loc_1800088CC
0x1800088a8  cmp     dword ptr [rsi+2188h], 0
0x1800088af  jz      loc_180008A5B
0x1800088b5  xor     edx, edx
0x1800088b7  mov     rcx, rsi
0x1800088ba  call    TeredoClientChangeStateAndLog
0x1800088bf  mov     rcx, rsi
0x1800088c2  call    TeredoClientUpdateStateInNsi
0x1800088c7  jmp     loc_180008A5B
0x1800088cc  movzx   ebx, word ptr [rsi+1E7Eh]
0x1800088d3  lea     rdx, aTeredoDeregist_1; "Teredo deregister firewall exceptions"
0x1800088da  mov     ecx, r12d
0x1800088dd  call    EventWrite0
0x1800088e2  movzx   ecx, bx; netshort
0x1800088e5  call    cs:__imp_ntohs
0x1800088ec  nop     dword ptr [rax+rax+00h]
0x1800088f1  xor     r8d, r8d
0x1800088f4  mov     ecx, r14d
0x1800088f7  movzx   edx, ax
0x1800088fa  call    cs:__imp_FWIndicatePortInUse
0x180008901  nop     dword ptr [rax+rax+00h]
0x180008906  test    eax, eax
0x180008908  jz      short loc_18000891C
0x18000890a  mov     r8d, eax
0x18000890d  lea     rdx, aFailedToUnregi; "Failed to unregister random port except"...
0x180008914  mov     ecx, r12d
0x180008917  call    EventWriteError0
0x18000891c  mov     ecx, 0DD8h; hostshort
0x180008921  call    cs:__imp_htons
0x180008928  nop     dword ptr [rax+rax+00h]
0x18000892d  movzx   ecx, ax; netshort
0x180008930  call    cs:__imp_ntohs
0x180008937  nop     dword ptr [rax+rax+00h]
0x18000893c  xor     r8d, r8d
0x18000893f  mov     ecx, r14d
0x180008942  movzx   edx, ax
0x180008945  call    cs:__imp_FWIndicatePortInUse
0x18000894c  nop     dword ptr [rax+rax+00h]
0x180008951  test    eax, eax
0x180008953  jz      short loc_180008967
0x180008955  mov     r8d, eax
0x180008958  lea     rdx, aFailedToUnregi_0; "Failed to unregister port 3544 exceptio"...
0x18000895f  mov     ecx, r12d
0x180008962  call    EventWriteError0
0x180008967  xor     eax, eax
0x180008969  mov     [rsi+1E7Ch], r13
0x180008970  mov     [rsi+1E84h], rax
0x180008977  mov     ecx, [rsi+2188h]
0x18000897d  sub     ecx, r14d
0x180008980  jz      short loc_1800089A7
0x180008982  cmp     ecx, r14d
0x180008985  jnz     loc_180008A15
0x18000898b  xor     edx, edx
0x18000898d  mov     rcx, rsi
0x180008990  call    TeredoClientChangeStateAndLog
0x180008995  mov     rcx, rsi
0x180008998  call    TeredoClientUpdateStateInNsi
0x18000899d  mov     rcx, rsi; pv
0x1800089a0  call    TeredoStartClient
0x1800089a5  jmp     short loc_180008A15
0x1800089a7  xor     edx, edx
0x1800089a9  mov     rcx, rsi
0x1800089ac  call    TeredoClientChangeStateAndLog
0x1800089b1  mov     rcx, rsi
0x1800089b4  call    TeredoClientUpdateStateInNsi
0x1800089b9  cmp     dword ptr [rbp+18h], 0
0x1800089bd  jnz     short loc_180008A15
0x1800089bf  add     [rsi+3820h], r14d
0x1800089c6  mov     r8d, 5
0x1800089cc  mov     eax, [rsi+3820h]
0x1800089d2  cmp     eax, r8d
0x1800089d5  jbe     short loc_1800089E0
0x1800089d7  mov     [rsi+3820h], r8d
0x1800089de  jmp     short loc_1800089E3
0x1800089e0  mov     r8d, eax
0x1800089e3  xor     edx, edx
0x1800089e5  mov     rcx, rbp
0x1800089e8  call    TeredoResolveInterval
0x1800089ed  mov     r9d, [rsi+3820h]
0x1800089f4  lea     rdx, aTeredoclientst; "TeredoClientStopIoComplete setting Tere"...
0x1800089fb  mov     r8d, eax
0x1800089fe  mov     ecx, r12d
0x180008a01  mov     ebx, eax
0x180008a03  call    EventWrite0
0x180008a08  mov     r8d, r14d
0x180008a0b  mov     edx, ebx
0x180008a0d  mov     rcx, rbp
0x180008a10  call    TeredoSetTimer
0x180008a15  mov     rbx, cs:g_TeredoLock
0x180008a1c  mov     rcx, rbx; hMutex
0x180008a1f  call    cs:__imp_ReleaseMutex
0x180008a26  nop     dword ptr [rax+rax+00h]
0x180008a2b  mov     dword ptr [rsp+78h+var_48], eax
0x180008a2f  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180008a36  mov     dword ptr [rsp+78h+var_50], 0C82h
0x180008a3e  mov     r8, rbx
0x180008a41  lea     rax, aTeredoclientst_0; "TeredoClientStopIoComplete"
0x180008a48  mov     ecx, edi
0x180008a4a  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180008a51  mov     [rsp+78h+var_58], rax
0x180008a56  call    EventWrite0
0x180008a5b  mov     rcx, [rsi+2170h]; hEvent
0x180008a62  test    rcx, rcx
0x180008a65  jz      short loc_180008A73
0x180008a67  call    cs:__imp_SetEvent
0x180008a6e  nop     dword ptr [rax+rax+00h]
0x180008a73  mov     r8d, [rsi]
0x180008a76  lea     rdi, aOnecoreuapNetN_27; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180008a7d  mov     ebx, 0C88h
0x180008a82  lea     rdx, aTeredoderefere; "TeredoDereferenceClient: --%d @ %ls:%u"
0x180008a89  mov     r9, rdi
0x180008a8c  mov     dword ptr [rsp+78h+var_58], ebx
0x180008a90  mov     ecx, r12d
0x180008a93  call    EventWrite0
0x180008a98  mov     edx, [rsi]
0x180008a9a  mov     eax, r14d
0x180008a9d  lock xadd [rsi+8], eax
0x180008aa2  add     eax, r14d
0x180008aa5  sub     eax, r14d
0x180008aa8  and     eax, 3Fh
0x180008aab  lea     rcx, [rax+rax*4]
0x180008aaf  or      eax, 0FFFFFFFFh
0x180008ab2  mov     [rsi+rcx*8+10h], edx
0x180008ab6  mov     [rsi+rcx*8+20h], ebx
0x180008aba  mov     [rsi+rcx*8+18h], rdi
0x180008abf  mov     [rsi+rcx*8+30h], r14d
0x180008ac4  mov     qword ptr [rsi+rcx*8+28h], 0
0x180008acd  lock xadd [rsi], eax
0x180008ad1  cmp     eax, r14d
0x180008ad4  jnz     short loc_180008ADE
0x180008ad6  mov     rcx, rsi
0x180008ad9  call    TeredoCleanupClient
0x180008ade  add     rsp, 40h
0x180008ae2  pop     r14
0x180008ae4  pop     r13
0x180008ae6  pop     r12
0x180008ae8  pop     rdi
0x180008ae9  pop     rsi
0x180008aea  pop     rbp
0x180008aeb  pop     rbx
0x180008aec  retn
```
