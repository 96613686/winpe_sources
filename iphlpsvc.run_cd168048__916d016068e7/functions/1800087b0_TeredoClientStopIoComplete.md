# TeredoClientStopIoComplete

- ea: `0x1800087b0`
- end: `0x180008ade`
- name: `TeredoClientStopIoComplete`
- size: `814`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800087b0`
- `0x180008ae4`
- `0x180008b80`
- `0x180008c40`
- `0x18000d7b0`
- `0x180014170`
- `0x1800163d4`
- `0x1800190e0`
- `0x180051f2c`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800087d9`
- `ntdll!EtwEventActivityIdControl` at `0x1800087d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a0f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008a57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008a57`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008843`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008843`
- `WS2_32!__imp_htons` at `0x180008911`
- `WS2_32!__imp_htons` at `0x180008911`
- `WS2_32!__imp_ntohs` at `0x1800088d5`
- `WS2_32!__imp_ntohs` at `0x180008920`
- `WS2_32!__imp_ntohs` at `0x1800088d5`
- `WS2_32!__imp_ntohs` at `0x180008920`
- `FirewallAPI!FWIndicatePortInUse` at `0x1800088ea`
- `FirewallAPI!FWIndicatePortInUse` at `0x180008935`
- `FirewallAPI!FWIndicatePortInUse` at `0x1800088ea`
- `FirewallAPI!FWIndicatePortInUse` at `0x180008935`

## string_xrefs

- `0x18000880b`: `TeredoClientStopIoComplete`
- `0x18000887f`: `TeredoClientStopIoComplete`
- `0x180008a31`: `TeredoClientStopIoComplete`
- `0x1800087ec`: `Teredo client stop io complete: ClientState = %d, Client = 0x%p`
- `0x1800089e4`: `TeredoClientStopIoComplete setting Teredo timer to %u ms. Consecutive failures: %u`
- `0x180008818`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x18000885b`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x180008a1f`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x180008a66`: `onecoreuap\net\netio\iphlpsvc\service\client.c`

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
0x1800087b0  push    rbx
0x1800087b2  push    rbp
0x1800087b3  push    rsi
0x1800087b4  push    rdi
0x1800087b5  push    r12
0x1800087b7  push    r13
0x1800087b9  push    r14
0x1800087bb  sub     rsp, 40h
0x1800087bf  mov     rbp, [rcx+1EE0h]
0x1800087c6  lea     rdx, g_TeredoActivityId
0x1800087cd  mov     rsi, rcx
0x1800087d0  mov     r13d, 2
0x1800087d6  mov     ecx, r13d
0x1800087d9  call    cs:__imp_EtwEventActivityIdControl
0x1800087e0  nop     dword ptr [rax+rax+00h]
0x1800087e5  mov     r8d, [rsi+2188h]
0x1800087ec  lea     rdx, aTeredoClientSt; "Teredo client stop io complete: ClientS"...
0x1800087f3  mov     r12d, 100000h
0x1800087f9  mov     r9, rsi
0x1800087fc  mov     ecx, r12d
0x1800087ff  call    EventWrite0
0x180008804  mov     rdi, cs:g_TeredoLock
0x18000880b  lea     rax, aTeredoclientst_0; "TeredoClientStopIoComplete"
0x180008812  mov     r14d, 0C2Eh
0x180008818  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000881f  mov     dword ptr [rsp+78h+var_50], r14d
0x180008824  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x18000882b  mov     r8, rdi
0x18000882e  mov     [rsp+78h+var_58], rax
0x180008833  mov     ecx, 800000h
0x180008838  call    EventWrite0
0x18000883d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008840  mov     rcx, rdi; hHandle
0x180008843  call    cs:__imp_WaitForSingleObject
0x18000884a  nop     dword ptr [rax+rax+00h]
0x18000884f  mov     r8, rdi
0x180008852  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180008859  mov     ebx, eax
0x18000885b  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180008862  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180008869  mov     dword ptr [rsp+78h+var_48], ebx
0x18000886d  test    ebx, ebx
0x18000886f  mov     dword ptr [rsp+78h+var_50], r14d
0x180008874  mov     edi, 800000h
0x180008879  cmovnz  rdx, rax
0x18000887d  mov     ecx, edi
0x18000887f  lea     rax, aTeredoclientst_0; "TeredoClientStopIoComplete"
0x180008886  mov     [rsp+78h+var_58], rax
0x18000888b  call    EventWrite0
0x180008890  lea     r14d, [r13-1]
0x180008894  test    ebx, ebx
0x180008896  jz      short loc_1800088BC
0x180008898  cmp     dword ptr [rsi+2188h], 0
0x18000889f  jz      loc_180008A4B
0x1800088a5  xor     edx, edx
0x1800088a7  mov     rcx, rsi
0x1800088aa  call    TeredoClientChangeStateAndLog
0x1800088af  mov     rcx, rsi
0x1800088b2  call    TeredoClientUpdateStateInNsi
0x1800088b7  jmp     loc_180008A4B
0x1800088bc  movzx   ebx, word ptr [rsi+1E7Eh]
0x1800088c3  lea     rdx, aTeredoDeregist_1; "Teredo deregister firewall exceptions"
0x1800088ca  mov     ecx, r12d
0x1800088cd  call    EventWrite0
0x1800088d2  movzx   ecx, bx; netshort
0x1800088d5  call    cs:__imp_ntohs
0x1800088dc  nop     dword ptr [rax+rax+00h]
0x1800088e1  xor     r8d, r8d
0x1800088e4  mov     ecx, r14d
0x1800088e7  movzx   edx, ax
0x1800088ea  call    cs:__imp_FWIndicatePortInUse
0x1800088f1  nop     dword ptr [rax+rax+00h]
0x1800088f6  test    eax, eax
0x1800088f8  jz      short loc_18000890C
0x1800088fa  mov     r8d, eax
0x1800088fd  lea     rdx, aFailedToUnregi; "Failed to unregister random port except"...
0x180008904  mov     ecx, r12d
0x180008907  call    EventWriteError0
0x18000890c  mov     ecx, 0DD8h; hostshort
0x180008911  call    cs:__imp_htons
0x180008918  nop     dword ptr [rax+rax+00h]
0x18000891d  movzx   ecx, ax; netshort
0x180008920  call    cs:__imp_ntohs
0x180008927  nop     dword ptr [rax+rax+00h]
0x18000892c  xor     r8d, r8d
0x18000892f  mov     ecx, r14d
0x180008932  movzx   edx, ax
0x180008935  call    cs:__imp_FWIndicatePortInUse
0x18000893c  nop     dword ptr [rax+rax+00h]
0x180008941  test    eax, eax
0x180008943  jz      short loc_180008957
0x180008945  mov     r8d, eax
0x180008948  lea     rdx, aFailedToUnregi_0; "Failed to unregister port 3544 exceptio"...
0x18000894f  mov     ecx, r12d
0x180008952  call    EventWriteError0
0x180008957  xor     eax, eax
0x180008959  mov     [rsi+1E7Ch], r13
0x180008960  mov     [rsi+1E84h], rax
0x180008967  mov     ecx, [rsi+2188h]
0x18000896d  sub     ecx, r14d
0x180008970  jz      short loc_180008997
0x180008972  cmp     ecx, r14d
0x180008975  jnz     loc_180008A05
0x18000897b  xor     edx, edx
0x18000897d  mov     rcx, rsi
0x180008980  call    TeredoClientChangeStateAndLog
0x180008985  mov     rcx, rsi
0x180008988  call    TeredoClientUpdateStateInNsi
0x18000898d  mov     rcx, rsi; pv
0x180008990  call    TeredoStartClient
0x180008995  jmp     short loc_180008A05
0x180008997  xor     edx, edx
0x180008999  mov     rcx, rsi
0x18000899c  call    TeredoClientChangeStateAndLog
0x1800089a1  mov     rcx, rsi
0x1800089a4  call    TeredoClientUpdateStateInNsi
0x1800089a9  cmp     dword ptr [rbp+18h], 0
0x1800089ad  jnz     short loc_180008A05
0x1800089af  add     [rsi+3820h], r14d
0x1800089b6  mov     r8d, 5
0x1800089bc  mov     eax, [rsi+3820h]
0x1800089c2  cmp     eax, r8d
0x1800089c5  jbe     short loc_1800089D0
0x1800089c7  mov     [rsi+3820h], r8d
0x1800089ce  jmp     short loc_1800089D3
0x1800089d0  mov     r8d, eax
0x1800089d3  xor     edx, edx
0x1800089d5  mov     rcx, rbp
0x1800089d8  call    TeredoResolveInterval
0x1800089dd  mov     r9d, [rsi+3820h]
0x1800089e4  lea     rdx, aTeredoclientst; "TeredoClientStopIoComplete setting Tere"...
0x1800089eb  mov     r8d, eax
0x1800089ee  mov     ecx, r12d
0x1800089f1  mov     ebx, eax
0x1800089f3  call    EventWrite0
0x1800089f8  mov     r8d, r14d
0x1800089fb  mov     edx, ebx
0x1800089fd  mov     rcx, rbp
0x180008a00  call    TeredoSetTimer
0x180008a05  mov     rbx, cs:g_TeredoLock
0x180008a0c  mov     rcx, rbx; hMutex
0x180008a0f  call    cs:__imp_ReleaseMutex
0x180008a16  nop     dword ptr [rax+rax+00h]
0x180008a1b  mov     dword ptr [rsp+78h+var_48], eax
0x180008a1f  lea     r9, aOnecoreuapNetN_29; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180008a26  mov     dword ptr [rsp+78h+var_50], 0C82h
0x180008a2e  mov     r8, rbx
0x180008a31  lea     rax, aTeredoclientst_0; "TeredoClientStopIoComplete"
0x180008a38  mov     ecx, edi
0x180008a3a  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180008a41  mov     [rsp+78h+var_58], rax
0x180008a46  call    EventWrite0
0x180008a4b  mov     rcx, [rsi+2170h]; hEvent
0x180008a52  test    rcx, rcx
0x180008a55  jz      short loc_180008A63
0x180008a57  call    cs:__imp_SetEvent
0x180008a5e  nop     dword ptr [rax+rax+00h]
0x180008a63  mov     r8d, [rsi]
0x180008a66  lea     rdi, aOnecoreuapNetN_27; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180008a6d  mov     ebx, 0C88h
0x180008a72  lea     rdx, aTeredoderefere; "TeredoDereferenceClient: --%d @ %ls:%u"
0x180008a79  mov     r9, rdi
0x180008a7c  mov     dword ptr [rsp+78h+var_58], ebx
0x180008a80  mov     ecx, r12d
0x180008a83  call    EventWrite0
0x180008a88  mov     edx, [rsi]
0x180008a8a  mov     eax, r14d
0x180008a8d  lock xadd [rsi+8], eax
0x180008a92  add     eax, r14d
0x180008a95  sub     eax, r14d
0x180008a98  and     eax, 3Fh
0x180008a9b  lea     rcx, [rax+rax*4]
0x180008a9f  or      eax, 0FFFFFFFFh
0x180008aa2  mov     [rsi+rcx*8+10h], edx
0x180008aa6  mov     [rsi+rcx*8+20h], ebx
0x180008aaa  mov     [rsi+rcx*8+18h], rdi
0x180008aaf  mov     [rsi+rcx*8+30h], r14d
0x180008ab4  mov     qword ptr [rsi+rcx*8+28h], 0
0x180008abd  lock xadd [rsi], eax
0x180008ac1  cmp     eax, r14d
0x180008ac4  jnz     short loc_180008ACE
0x180008ac6  mov     rcx, rsi
0x180008ac9  call    TeredoCleanupClient
0x180008ace  add     rsp, 40h
0x180008ad2  pop     r14
0x180008ad4  pop     r13
0x180008ad6  pop     r12
0x180008ad8  pop     rdi
0x180008ad9  pop     rsi
0x180008ada  pop     rbp
0x180008adb  pop     rbx
0x180008adc  retn
```
