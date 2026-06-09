# TeredoTimerCallback

- ea: `0x18002e8a0`
- end: `0x18002ec09`
- name: `TeredoTimerCallback`
- size: `873`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180013f64`
- `0x1800190e0`
- `0x18001caf0`
- `0x18002e8a0`
- `0x18002ec10`
- `0x18005f2d8`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18002e971`
- `ntdll!EtwEventActivityIdControl` at `0x18002e971`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002e9d0`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002e9d0`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18002e9b8`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x18002e9b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ebbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ebbf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ea7c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ea7c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002e90a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002e90a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eb6f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002eb6f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18002eb17`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18002eb17`

## string_xrefs

- `0x18002e8dc`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18002e922`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18002ebcf`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`

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
0x18002e8a0  push    rbx
0x18002e8a2  push    rbp
0x18002e8a3  push    rsi
0x18002e8a4  push    rdi
0x18002e8a5  push    r12
0x18002e8a7  push    r13
0x18002e8a9  push    r14
0x18002e8ab  push    r15
0x18002e8ad  sub     rsp, 48h
0x18002e8b1  mov     rsi, rdx
0x18002e8b4  mov     r12d, 100000h
0x18002e8ba  mov     ecx, r12d
0x18002e8bd  lea     rdx, aTeredotimercal_1; "TeredoTimerCallback invoked."
0x18002e8c4  call    EventWrite0
0x18002e8c9  mov     rdi, cs:g_TeredoLock
0x18002e8d0  lea     r13, aTeredotimercal_0; "TeredoTimerCallback"
0x18002e8d7  mov     ebp, 517h
0x18002e8dc  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002e8e3  mov     r15d, 800000h
0x18002e8e9  mov     dword ptr [rsp+88h+var_60], ebp
0x18002e8ed  mov     r8, rdi
0x18002e8f0  mov     [rsp+88h+var_68], r13
0x18002e8f5  mov     ecx, r15d
0x18002e8f8  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x18002e8ff  call    EventWrite0
0x18002e904  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002e907  mov     rcx, rdi; hHandle
0x18002e90a  call    cs:__imp_WaitForSingleObject
0x18002e911  nop     dword ptr [rax+rax+00h]
0x18002e916  xor     r14d, r14d
0x18002e919  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x18002e920  mov     ebx, eax
0x18002e922  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002e929  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x18002e930  mov     dword ptr [rsp+88h+var_58], ebx
0x18002e934  test    ebx, ebx
0x18002e936  mov     dword ptr [rsp+88h+var_60], ebp
0x18002e93a  mov     r8, rdi
0x18002e93d  mov     [rsp+88h+var_68], r13
0x18002e942  cmovnz  rdx, rax
0x18002e946  mov     ecx, r15d
0x18002e949  call    EventWrite0
0x18002e94e  test    ebx, ebx
0x18002e950  jnz     loc_18002EBF7
0x18002e956  lea     r15d, [r14+1]
0x18002e95a  cmp     [rsi+18h], r14d
0x18002e95e  jnz     loc_18002EBA7
0x18002e964  lea     rdx, g_TeredoActivityId
0x18002e96b  mov     edi, r14d
0x18002e96e  lea     ecx, [rbx+2]
0x18002e971  call    cs:__imp_EtwEventActivityIdControl
0x18002e978  nop     dword ptr [rax+rax+00h]
0x18002e97d  cmp     [rsi+0ADCh], r14d
0x18002e984  jnz     short loc_18002E9A7
0x18002e986  mov     rcx, rsi; pv
0x18002e989  call    TeredoRegisterWithSC
0x18002e98e  test    eax, eax
0x18002e990  jz      short loc_18002E9A7
0x18002e992  mov     r8d, eax
0x18002e995  lea     rdx, aUnableToRegist_0; "Unable to register with the SCM. Error "...
0x18002e99c  mov     ecx, r12d
0x18002e99f  call    EventWriteError0
0x18002e9a4  mov     edi, r15d
0x18002e9a7  lea     rbp, [rsi+0B10h]
0x18002e9ae  lea     r13, aBfeIsNotRunnin; "BFE is not running."
0x18002e9b5  mov     rcx, rbp; ListHead
0x18002e9b8  call    cs:__imp_QueryDepthSList
0x18002e9bf  nop     dword ptr [rax+rax+00h]
0x18002e9c4  test    ax, ax
0x18002e9c7  jz      loc_18002EAA7
0x18002e9cd  mov     rcx, rbp; ListHead
0x18002e9d0  call    cs:__imp_InterlockedPopEntrySList
0x18002e9d7  nop     dword ptr [rax+rax+00h]
0x18002e9dc  mov     rbx, rax
0x18002e9df  mov     r8d, [rax+28h]
0x18002e9e3  test    r8d, r8d
0x18002e9e6  jnz     short loc_18002EA3A
0x18002e9e8  lea     rdx, aValidScmNotifi; "Valid SCM Notification received"
0x18002e9ef  mov     ecx, r12d
0x18002e9f2  call    EventWrite0
0x18002e9f7  mov     eax, [rbx+30h]
0x18002e9fa  cmp     eax, 4
0x18002e9fd  jnz     short loc_18002EA08
0x18002e9ff  mov     [rsi+0AE0h], r15d
0x18002ea06  jmp     short loc_18002EA2D
0x18002ea08  dec     eax
0x18002ea0a  test    eax, 0FFFFFFFDh
0x18002ea0f  jnz     short loc_18002EA2D
0x18002ea11  mov     rdx, r13
0x18002ea14  mov     [rsi+0AE0h], r14d
0x18002ea1b  mov     ecx, r12d
0x18002ea1e  call    EventWriteError0
0x18002ea23  mov     dword ptr [rsi+0B34h], 12h
0x18002ea2d  mov     rcx, rbx
0x18002ea30  call    FREE
0x18002ea35  jmp     loc_18002E9B5
0x18002ea3a  cmp     r8d, 50Eh
0x18002ea41  jnz     short loc_18002EA57
0x18002ea43  mov     rcx, rbx
0x18002ea46  call    FREE
0x18002ea4b  mov     dword ptr [rsi+0ADCh], 2
0x18002ea55  jmp     short loc_18002EA75
0x18002ea57  lea     rdx, aNotificationSt; "Notification Status of SCM callback is "...
0x18002ea5e  mov     ecx, r12d
0x18002ea61  call    EventWrite0
0x18002ea66  mov     rcx, rbx
0x18002ea69  call    FREE
0x18002ea6e  mov     [rsi+0ADCh], r15d
0x18002ea75  mov     rcx, [rsi+0B28h]; hEvent
0x18002ea7c  call    cs:__imp_SetEvent
0x18002ea83  nop     dword ptr [rax+rax+00h]
0x18002ea88  mov     rdx, r13
0x18002ea8b  mov     [rsi+0AE0h], r14d
0x18002ea92  mov     ecx, r12d
0x18002ea95  call    EventWriteError0
0x18002ea9a  mov     edi, r15d
0x18002ea9d  mov     dword ptr [rsi+0B34h], 12h
0x18002eaa7  mov     rcx, rsi
0x18002eaaa  call    TeredoCompartmentUpdateWFPRegistration
0x18002eaaf  test    edi, edi
0x18002eab1  jz      short loc_18002EAC0
0x18002eab3  mov     edx, 0Fh
0x18002eab8  mov     cs:dword_1800C92A8, edx
0x18002eabe  jmp     short loc_18002EAD9
0x18002eac0  mov     eax, cs:dword_1800C92A8
0x18002eac6  mov     edx, 12Ch
0x18002eacb  add     eax, eax
0x18002eacd  mov     cs:dword_1800C92A8, eax
0x18002ead3  cmp     eax, edx
0x18002ead5  ja      short loc_18002EAB8
0x18002ead7  mov     edx, eax
0x18002ead9  mov     rcx, rsi
0x18002eadc  call    TeredoTypeClient
0x18002eae1  test    eax, eax
0x18002eae3  jnz     short loc_18002EAF5
0x18002eae5  call    TeredoTypeServer
0x18002eaea  test    eax, eax
0x18002eaec  jnz     short loc_18002EAF5
0x18002eaee  mov     edi, 7FFFFFFFh
0x18002eaf3  jmp     short loc_18002EB34
0x18002eaf5  mov     rcx, cs:hProv; hProv
0x18002eafc  lea     r8, [rsp+88h+pbBuffer]; pbBuffer
0x18002eb04  imul    ebx, edx, 3E8h
0x18002eb0a  mov     edx, 4; dwLen
0x18002eb0f  mov     dword ptr [rsp+88h+pbBuffer], r14d
0x18002eb17  call    cs:__imp_CryptGenRandom
0x18002eb1e  nop     dword ptr [rax+rax+00h]
0x18002eb23  mov     eax, dword ptr [rsp+88h+pbBuffer]
0x18002eb2a  xor     edx, edx
0x18002eb2c  div     ebx
0x18002eb2e  mov     edi, edx
0x18002eb30  shr     edi, 1
0x18002eb32  add     edi, ebx
0x18002eb34  mov     r8d, edi
0x18002eb37  lea     rdx, aTeredotimercal; "TeredoTimerCallback setting Teredo time"...
0x18002eb3e  mov     ecx, r12d
0x18002eb41  call    EventWrite0
0x18002eb46  mov     rbx, [rsi+4BF8h]
0x18002eb4d  lea     rdx, [rsp+88h+pbBuffer]; pftDueTime
0x18002eb55  mov     eax, edi
0x18002eb57  xor     r9d, r9d; msWindowLength
0x18002eb5a  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18002eb61  xor     r8d, r8d; msPeriod
0x18002eb64  mov     [rsp+88h+pbBuffer], rcx
0x18002eb6c  mov     rcx, rbx; pti
0x18002eb6f  call    cs:__imp_SetThreadpoolTimer
0x18002eb76  nop     dword ptr [rax+rax+00h]
0x18002eb7b  mov     r9d, edi
0x18002eb7e  mov     [rsp+88h+var_60], rbx
0x18002eb83  lea     r8, aTeredoTimer; "Teredo Timer"
0x18002eb8a  mov     dword ptr [rsp+88h+var_68], r14d
0x18002eb8f  lea     rdx, aSHasBeenSetToT; "%s has been set to: timeout = %d ms, pe"...
0x18002eb96  mov     ecx, 8000000h
0x18002eb9b  call    EventWrite0
0x18002eba0  lea     r13, aTeredotimercal_0; "TeredoTimerCallback"
0x18002eba7  mov     [rsi+4B84h], r14d
0x18002ebae  mov     [rsi+4B88h], r15d
0x18002ebb5  mov     rbx, cs:g_TeredoLock
0x18002ebbc  mov     rcx, rbx; hMutex
0x18002ebbf  call    cs:__imp_ReleaseMutex
0x18002ebc6  nop     dword ptr [rax+rax+00h]
0x18002ebcb  mov     dword ptr [rsp+88h+var_58], eax
0x18002ebcf  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18002ebd6  mov     dword ptr [rsp+88h+var_60], 582h
0x18002ebde  mov     r8, rbx
0x18002ebe1  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x18002ebe8  mov     [rsp+88h+var_68], r13
0x18002ebed  mov     ecx, 800000h
0x18002ebf2  call    EventWrite0
0x18002ebf7  add     rsp, 48h
0x18002ebfb  pop     r15
0x18002ebfd  pop     r14
0x18002ebff  pop     r13
0x18002ec01  pop     r12
0x18002ec03  pop     rdi
0x18002ec04  pop     rsi
0x18002ec05  pop     rbp
0x18002ec06  pop     rbx
0x18002ec07  retn
```
