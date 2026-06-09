# TeredoTimerCallback

- ea: `0x18002e8b0`
- end: `0x18002ec19`
- name: `TeredoTimerCallback`
- size: `873`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180013f74`
- `0x1800190f0`
- `0x18001cb00`
- `0x18002e8b0`
- `0x18002ec20`
- `0x18005f2f8`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18002e981`
- `ntdll!EtwEventActivityIdControl` at `0x18002e981`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002e9e0`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002e9e0`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18002e9c8`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18002e9c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ebcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ebcf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ea8c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ea8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002e91a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002e91a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eb7f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eb7f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18002eb27`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18002eb27`

## string_xrefs

- `0x18002e8ec`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18002e932`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18002ebdf`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`

## pseudocode

```c
__int64 __fastcall TeredoTimerCallback(__int64 a1, __int64 a2)
{
  HANDLE v3; // rdi
  DWORD v4; // eax
  const wchar_t *v5; // rdx
  DWORD v6; // ebx
  __int64 result; // rax
  int v8; // edi
  unsigned int v9; // eax
  PSLIST_ENTRY v10; // rax
  PSLIST_ENTRY v11; // rbx
  int v12; // r8d
  int Next; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  int v16; // edx
  __int64 v17; // rcx
  unsigned int v18; // edi
  unsigned int v19; // ebx
  struct _TP_TIMER *v20; // rbx
  HANDLE v21; // rbx
  __int64 v22; // [rsp+20h] [rbp-68h]
  __int64 v23; // [rsp+28h] [rbp-60h]
  __int64 v24; // [rsp+28h] [rbp-60h]
  __int64 v25; // [rsp+30h] [rbp-58h]
  __int64 pbBuffer; // [rsp+98h] [rbp+10h] BYREF

  EventWrite0(0x100000, L"TeredoTimerCallback invoked.");
  v3 = g_TeredoLock;
  EventWrite0(
    0x800000,
    L"Get lock (%p) invoked at %S : %S : %u",
    g_TeredoLock,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c",
    "TeredoTimerCallback",
    1303);
  v4 = WaitForSingleObject(v3, 0xFFFFFFFF);
  v5 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
  v6 = v4;
  LODWORD(v23) = 1303;
  if ( v4 )
    v5 = L"Lock (%p) failed at %S : %S : %u. Return %d";
  result = EventWrite0(
             0x800000,
             v5,
             v3,
             "onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c",
             "TeredoTimerCallback",
             v23,
             v4);
  if ( !v6 )
  {
    if ( *(_DWORD *)(a2 + 24) )
    {
LABEL_29:
      *(_DWORD *)(a2 + 19332) = 0;
      *(_DWORD *)(a2 + 19336) = 1;
      v21 = g_TeredoLock;
      LODWORD(v25) = ReleaseMutex(g_TeredoLock);
      LODWORD(v24) = 1410;
      return EventWrite0(
               0x800000,
               L"Lock (%p) released at %S : %S : %u. Return %d",
               v21,
               "onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c",
               "TeredoTimerCallback",
               v24,
               v25);
    }
    v8 = 0;
    EtwEventActivityIdControl(2, g_TeredoActivityId);
    if ( !*(_DWORD *)(a2 + 2780) )
    {
      v9 = TeredoRegisterWithSC((PVOID)a2);
      if ( v9 )
      {
        EventWriteError0(0x100000, L"Unable to register with the SCM. Error %d", v9);
        v8 = 1;
      }
    }
    while ( QueryDepthSList((PSLIST_HEADER)(a2 + 2832)) )
    {
      v10 = InterlockedPopEntrySList((PSLIST_HEADER)(a2 + 2832));
      v11 = v10;
      v12 = *((_DWORD *)&v10[2].Next + 2);
      if ( v12 )
      {
        if ( v12 == 1294 )
        {
          FREE(v10);
          *(_DWORD *)(a2 + 2780) = 2;
        }
        else
        {
          EventWrite0(0x100000, L"Notification Status of SCM callback is %d");
          FREE(v11);
          *(_DWORD *)(a2 + 2780) = 1;
        }
        SetEvent(*(HANDLE *)(a2 + 2856));
        *(_DWORD *)(a2 + 2784) = 0;
        EventWriteError0(0x100000, L"BFE is not running.");
        v8 = 1;
        *(_DWORD *)(a2 + 2868) = 18;
        break;
      }
      EventWrite0(0x100000, L"Valid SCM Notification received");
      Next = (int)v11[3].Next;
      if ( Next == 4 )
      {
        *(_DWORD *)(a2 + 2784) = 1;
      }
      else if ( ((Next - 1) & 0xFFFFFFFD) == 0 )
      {
        *(_DWORD *)(a2 + 2784) = 0;
        EventWriteError0(0x100000, L"BFE is not running.");
        *(_DWORD *)(a2 + 2868) = 18;
      }
      FREE(v11);
    }
    TeredoCompartmentUpdateWFPRegistration((PVOID)a2);
    if ( v8 )
    {
      v14 = 15;
    }
    else
    {
      v14 = 300;
      v15 = 2 * dword_1800C92A8;
      dword_1800C92A8 = v15;
      if ( v15 <= 0x12C )
      {
        v14 = v15;
LABEL_24:
        if ( (unsigned int)TeredoTypeClient(a2, v14) || (unsigned int)TeredoTypeServer(v17) )
        {
          v19 = 1000 * v16;
          LODWORD(pbBuffer) = 0;
          CryptGenRandom(hProv, 4u, (BYTE *)&pbBuffer);
          v18 = v19 + (((unsigned int)pbBuffer % v19) >> 1);
        }
        else
        {
          v18 = 0x7FFFFFFF;
        }
        EventWrite0(0x100000, L"TeredoTimerCallback setting Teredo timer to %u ms", v18);
        v20 = *(struct _TP_TIMER **)(a2 + 19448);
        pbBuffer = -10000LL * v18;
        SetThreadpoolTimer(v20, (PFILETIME)&pbBuffer, 0, 0);
        LODWORD(v22) = 0;
        EventWrite0(
          0x8000000,
          L"%s has been set to: timeout = %d ms, period = %d ms, timer memory pointer = %p",
          L"Teredo Timer",
          v18,
          v22,
          v20);
        goto LABEL_29;
      }
    }
    dword_1800C92A8 = v14;
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x18002e8b0  push    rbx
0x18002e8b2  push    rbp
0x18002e8b3  push    rsi
0x18002e8b4  push    rdi
0x18002e8b5  push    r12
0x18002e8b7  push    r13
0x18002e8b9  push    r14
0x18002e8bb  push    r15
0x18002e8bd  sub     rsp, 48h
0x18002e8c1  mov     rsi, rdx
0x18002e8c4  mov     r12d, 100000h
0x18002e8ca  mov     ecx, r12d
0x18002e8cd  lea     rdx, aTeredotimercal_1; "TeredoTimerCallback invoked."
0x18002e8d4  call    EventWrite0
0x18002e8d9  mov     rdi, cs:g_TeredoLock
0x18002e8e0  lea     r13, aTeredotimercal_0; "TeredoTimerCallback"
0x18002e8e7  mov     ebp, 517h
0x18002e8ec  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002e8f3  mov     r15d, 800000h
0x18002e8f9  mov     dword ptr [rsp+88h+var_60], ebp
0x18002e8fd  mov     r8, rdi
0x18002e900  mov     [rsp+88h+var_68], r13
0x18002e905  mov     ecx, r15d
0x18002e908  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x18002e90f  call    EventWrite0
0x18002e914  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002e917  mov     rcx, rdi; hHandle
0x18002e91a  call    cs:__imp_WaitForSingleObject
0x18002e921  nop     dword ptr [rax+rax+00h]
0x18002e926  xor     r14d, r14d
0x18002e929  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x18002e930  mov     ebx, eax
0x18002e932  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002e939  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x18002e940  mov     dword ptr [rsp+88h+var_58], ebx
0x18002e944  test    ebx, ebx
0x18002e946  mov     dword ptr [rsp+88h+var_60], ebp
0x18002e94a  mov     r8, rdi
0x18002e94d  mov     [rsp+88h+var_68], r13
0x18002e952  cmovnz  rdx, rax
0x18002e956  mov     ecx, r15d
0x18002e959  call    EventWrite0
0x18002e95e  test    ebx, ebx
0x18002e960  jnz     loc_18002EC07
0x18002e966  lea     r15d, [r14+1]
0x18002e96a  cmp     [rsi+18h], r14d
0x18002e96e  jnz     loc_18002EBB7
0x18002e974  lea     rdx, g_TeredoActivityId
0x18002e97b  mov     edi, r14d
0x18002e97e  lea     ecx, [rbx+2]
0x18002e981  call    cs:__imp_EtwEventActivityIdControl
0x18002e988  nop     dword ptr [rax+rax+00h]
0x18002e98d  cmp     [rsi+0ADCh], r14d
0x18002e994  jnz     short loc_18002E9B7
0x18002e996  mov     rcx, rsi; pv
0x18002e999  call    TeredoRegisterWithSC
0x18002e99e  test    eax, eax
0x18002e9a0  jz      short loc_18002E9B7
0x18002e9a2  mov     r8d, eax
0x18002e9a5  lea     rdx, aUnableToRegist_0; "Unable to register with the SCM. Error "...
0x18002e9ac  mov     ecx, r12d
0x18002e9af  call    EventWriteError0
0x18002e9b4  mov     edi, r15d
0x18002e9b7  lea     rbp, [rsi+0B10h]
0x18002e9be  lea     r13, aBfeIsNotRunnin; "BFE is not running."
0x18002e9c5  mov     rcx, rbp; ListHead
0x18002e9c8  call    cs:__imp_QueryDepthSList
0x18002e9cf  nop     dword ptr [rax+rax+00h]
0x18002e9d4  test    ax, ax
0x18002e9d7  jz      loc_18002EAB7
0x18002e9dd  mov     rcx, rbp; ListHead
0x18002e9e0  call    cs:__imp_InterlockedPopEntrySList
0x18002e9e7  nop     dword ptr [rax+rax+00h]
0x18002e9ec  mov     rbx, rax
0x18002e9ef  mov     r8d, [rax+28h]
0x18002e9f3  test    r8d, r8d
0x18002e9f6  jnz     short loc_18002EA4A
0x18002e9f8  lea     rdx, aValidScmNotifi; "Valid SCM Notification received"
0x18002e9ff  mov     ecx, r12d
0x18002ea02  call    EventWrite0
0x18002ea07  mov     eax, [rbx+30h]
0x18002ea0a  cmp     eax, 4
0x18002ea0d  jnz     short loc_18002EA18
0x18002ea0f  mov     [rsi+0AE0h], r15d
0x18002ea16  jmp     short loc_18002EA3D
0x18002ea18  dec     eax
0x18002ea1a  test    eax, 0FFFFFFFDh
0x18002ea1f  jnz     short loc_18002EA3D
0x18002ea21  mov     rdx, r13
0x18002ea24  mov     [rsi+0AE0h], r14d
0x18002ea2b  mov     ecx, r12d
0x18002ea2e  call    EventWriteError0
0x18002ea33  mov     dword ptr [rsi+0B34h], 12h
0x18002ea3d  mov     rcx, rbx
0x18002ea40  call    FREE
0x18002ea45  jmp     loc_18002E9C5
0x18002ea4a  cmp     r8d, 50Eh
0x18002ea51  jnz     short loc_18002EA67
0x18002ea53  mov     rcx, rbx
0x18002ea56  call    FREE
0x18002ea5b  mov     dword ptr [rsi+0ADCh], 2
0x18002ea65  jmp     short loc_18002EA85
0x18002ea67  lea     rdx, aNotificationSt; "Notification Status of SCM callback is "...
0x18002ea6e  mov     ecx, r12d
0x18002ea71  call    EventWrite0
0x18002ea76  mov     rcx, rbx
0x18002ea79  call    FREE
0x18002ea7e  mov     [rsi+0ADCh], r15d
0x18002ea85  mov     rcx, [rsi+0B28h]; hEvent
0x18002ea8c  call    cs:__imp_SetEvent
0x18002ea93  nop     dword ptr [rax+rax+00h]
0x18002ea98  mov     rdx, r13
0x18002ea9b  mov     [rsi+0AE0h], r14d
0x18002eaa2  mov     ecx, r12d
0x18002eaa5  call    EventWriteError0
0x18002eaaa  mov     edi, r15d
0x18002eaad  mov     dword ptr [rsi+0B34h], 12h
0x18002eab7  mov     rcx, rsi
0x18002eaba  call    TeredoCompartmentUpdateWFPRegistration
0x18002eabf  test    edi, edi
0x18002eac1  jz      short loc_18002EAD0
0x18002eac3  mov     edx, 0Fh
0x18002eac8  mov     cs:dword_1800C92A8, edx
0x18002eace  jmp     short loc_18002EAE9
0x18002ead0  mov     eax, cs:dword_1800C92A8
0x18002ead6  mov     edx, 12Ch
0x18002eadb  add     eax, eax
0x18002eadd  mov     cs:dword_1800C92A8, eax
0x18002eae3  cmp     eax, edx
0x18002eae5  ja      short loc_18002EAC8
0x18002eae7  mov     edx, eax
0x18002eae9  mov     rcx, rsi
0x18002eaec  call    TeredoTypeClient
0x18002eaf1  test    eax, eax
0x18002eaf3  jnz     short loc_18002EB05
0x18002eaf5  call    TeredoTypeServer
0x18002eafa  test    eax, eax
0x18002eafc  jnz     short loc_18002EB05
0x18002eafe  mov     edi, 7FFFFFFFh
0x18002eb03  jmp     short loc_18002EB44
0x18002eb05  mov     rcx, cs:hProv; hProv
0x18002eb0c  lea     r8, [rsp+88h+pbBuffer]; pbBuffer
0x18002eb14  imul    ebx, edx, 3E8h
0x18002eb1a  mov     edx, 4; dwLen
0x18002eb1f  mov     dword ptr [rsp+88h+pbBuffer], r14d
0x18002eb27  call    cs:__imp_CryptGenRandom
0x18002eb2e  nop     dword ptr [rax+rax+00h]
0x18002eb33  mov     eax, dword ptr [rsp+88h+pbBuffer]
0x18002eb3a  xor     edx, edx
0x18002eb3c  div     ebx
0x18002eb3e  mov     edi, edx
0x18002eb40  shr     edi, 1
0x18002eb42  add     edi, ebx
0x18002eb44  mov     r8d, edi
0x18002eb47  lea     rdx, aTeredotimercal; "TeredoTimerCallback setting Teredo time"...
0x18002eb4e  mov     ecx, r12d
0x18002eb51  call    EventWrite0
0x18002eb56  mov     rbx, [rsi+4BF8h]
0x18002eb5d  lea     rdx, [rsp+88h+pbBuffer]; pftDueTime
0x18002eb65  mov     eax, edi
0x18002eb67  xor     r9d, r9d; msWindowLength
0x18002eb6a  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18002eb71  xor     r8d, r8d; msPeriod
0x18002eb74  mov     [rsp+88h+pbBuffer], rcx
0x18002eb7c  mov     rcx, rbx; pti
0x18002eb7f  call    cs:__imp_SetThreadpoolTimer
0x18002eb86  nop     dword ptr [rax+rax+00h]
0x18002eb8b  mov     r9d, edi
0x18002eb8e  mov     [rsp+88h+var_60], rbx
0x18002eb93  lea     r8, aTeredoTimer; "Teredo Timer"
0x18002eb9a  mov     dword ptr [rsp+88h+var_68], r14d
0x18002eb9f  lea     rdx, aSHasBeenSetToT; "%s has been set to: timeout = %d ms, pe"...
0x18002eba6  mov     ecx, 8000000h
0x18002ebab  call    EventWrite0
0x18002ebb0  lea     r13, aTeredotimercal_0; "TeredoTimerCallback"
0x18002ebb7  mov     [rsi+4B84h], r14d
0x18002ebbe  mov     [rsi+4B88h], r15d
0x18002ebc5  mov     rbx, cs:g_TeredoLock
0x18002ebcc  mov     rcx, rbx; hMutex
0x18002ebcf  call    cs:__imp_ReleaseMutex
0x18002ebd6  nop     dword ptr [rax+rax+00h]
0x18002ebdb  mov     dword ptr [rsp+88h+var_58], eax
0x18002ebdf  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002ebe6  mov     dword ptr [rsp+88h+var_60], 582h
0x18002ebee  mov     r8, rbx
0x18002ebf1  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x18002ebf8  mov     [rsp+88h+var_68], r13
0x18002ebfd  mov     ecx, 800000h
0x18002ec02  call    EventWrite0
0x18002ec07  add     rsp, 48h
0x18002ec0b  pop     r15
0x18002ec0d  pop     r14
0x18002ec0f  pop     r13
0x18002ec11  pop     r12
0x18002ec13  pop     rdi
0x18002ec14  pop     rsi
0x18002ec15  pop     rbp
0x18002ec16  pop     rbx
0x18002ec17  retn
```
