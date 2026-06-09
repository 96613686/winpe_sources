# TeredoRegisterWithSCWorker

- ea: `0x180007880`
- end: `0x180007d8f`
- name: `TeredoRegisterWithSCWorker`
- size: `1295`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004c54`
- `0x180004f50`
- `0x1800077d8`
- `0x180007880`
- `0x180008c40`
- `0x18000ce90`
- `0x18000d7b0`
- `0x180012dbc`
- `0x1800190e0`
- `0x180022b30`
- `0x180041a00`
- `0x18005f2d8`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180007c6e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180007c6e`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180007c85`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180007c85`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007abf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007abf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007a7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b36`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007a7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800078cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007c04`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800078cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007c04`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800079e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800079e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000794d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000794d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000797d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000797d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800079ac`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800079ac`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007ca2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007cc1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007ca2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007cc1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180007935`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180007935`

## string_xrefs

- `0x180007d60`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007d72`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x1800078a0`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x1800078e7`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007a8a`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007aeb`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007b46`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007bd6`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007c10`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007d26`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007c4f`: `Teredo registering with SC in a worker: Unable to grab config lock`
- `0x180007d46`: `Teredo registering with SC in a worker: Unable to grab config lock`
- `0x180007ad8`: `Teredo registering with SC in a worker: Wait completed by apc.`
- `0x180007bb2`: `Teredo registering with SC in a worker: Wait completed by event.`
- `0x180007bc3`: `Teredo registering with SC in a worker: Unexpected Wait completion. Error (%d)`
- `0x180007b9e`: `Teredo registering with SC in a worker: Unable to grab config lock.`
- `0x180007959`: `Teredo registering with SC in a worker: Unable to open handle to SCM. Error (%d)`
- `0x1800079d0`: `Teredo registering with SC in a worker: Unable to open handle to BFE. Error (%d)`
- `0x1800079fe`: `Teredo registering with SC in a worker: Unable to create event to stop BFE thread.Error (%d)`
- `0x180007b84`: `Teredo registering with SC in a worker: Service lags SCM. Error (%d). Re-register.`

## pseudocode

```c
void __fastcall TeredoRegisterWithSCWorker(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  HANDLE v2; // rdi
  const wchar_t *v4; // r14
  DWORD v5; // ebx
  const wchar_t *v6; // rdx
  SC_HANDLE v7; // rax
  DWORD LastError; // eax
  const wchar_t *v9; // rdx
  void *v10; // rcx
  SC_HANDLE v11; // rax
  HANDLE EventW; // rax
  __int64 v13; // rax
  HANDLE v14; // rbx
  DWORD v15; // eax
  HANDLE v16; // rbx
  HANDLE v17; // rdi
  DWORD v18; // ebx
  unsigned int v19; // ebx
  __int64 v20; // r8
  PSLIST_ENTRY v21; // rax
  SC_HANDLE v22; // rcx
  SC_HANDLE v23; // rcx
  __int64 v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // [rsp+28h] [rbp-50h]
  __int64 v27; // [rsp+28h] [rbp-50h]
  __int64 v28; // [rsp+28h] [rbp-50h]
  __int64 v29; // [rsp+28h] [rbp-50h]
  __int64 v30; // [rsp+30h] [rbp-48h]
  __int64 v31; // [rsp+30h] [rbp-48h]

  v2 = g_TeredoLock;
  EventWrite0(
    0x800000,
    L"Get lock (%p) invoked at %S : %S : %u",
    g_TeredoLock,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
    "TeredoRegisterWithSCWorker",
    2428);
  v4 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
  v5 = WaitForSingleObject(v2, 0xFFFFFFFF);
  LODWORD(v26) = 2428;
  v6 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
  if ( v5 )
    v6 = L"Lock (%p) failed at %S : %S : %u. Return %d";
  EventWrite0(
    0x800000,
    v6,
    v2,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
    "TeredoRegisterWithSCWorker",
    v26,
    v5);
  if ( v5 )
  {
    EventWriteError0(0x100000, L"Teredo registering with SC in a worker: Unable to grab config lock");
    v19 = 2434;
    v20 = 2433;
    goto LABEL_49;
  }
  if ( *((_DWORD *)Context + 6) )
    goto LABEL_8;
  v7 = OpenSCManagerW(0, 0, 0x80000000);
  *((_QWORD *)Context + 351) = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    v9 = L"Teredo registering with SC in a worker: Unable to open handle to SCM. Error (%d)";
LABEL_7:
    EventWriteError0(0x100000, v9, LastError);
    goto LABEL_8;
  }
  v11 = OpenServiceW(v7, L"BFE", 4u);
  *((_QWORD *)Context + 352) = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    v9 = L"Teredo registering with SC in a worker: Unable to open handle to BFE. Error (%d)";
    goto LABEL_7;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)Context + 357) = EventW;
  if ( !EventW )
  {
    EventWriteError0(
      0x100000,
      L"Teredo registering with SC in a worker: Unable to create event to stop BFE thread.Error (%d)",
      0);
    goto LABEL_8;
  }
  v13 = MALLOC(0x50u);
  *((_QWORD *)Context + 353) = v13;
  if ( !v13 )
  {
    EventWrite0(
      0x100000,
      L"Teredo registering with SC in a worker: Unable to allocate buffers for SCM primary notifications.Error (%d)",
      8);
    goto LABEL_8;
  }
  dword_1800C92E0 = 1;
  if ( (unsigned int)TeredoRegisterForSCNotification(Context) )
  {
    LastError = GetLastError();
    v9 = L"Teredo registering with SC in a worker: Unable to register for BFE notifications with SCM.Error (%d)";
    goto LABEL_7;
  }
  *((_DWORD *)Context + 695) = 3;
  v14 = g_TeredoLock;
  LODWORD(v30) = ReleaseMutex(g_TeredoLock);
  LODWORD(v27) = 2533;
  EventWrite0(
    0x800000,
    L"Lock (%p) released at %S : %S : %u. Return %d",
    v14,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
    "TeredoRegisterWithSCWorker",
    v27,
    v30);
  while ( 1 )
  {
    v15 = WaitForSingleObjectEx(*((HANDLE *)Context + 357), 0xFFFFFFFF, 1);
    if ( v15 != 192 )
      break;
    EventWrite0(0x100000, L"Teredo registering with SC in a worker: Wait completed by apc.");
    if ( !(unsigned int)GetAndTraceLock(
                          "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
                          "TeredoRegisterWithSCWorker",
                          2571,
                          g_TeredoLock) )
    {
      EventWriteError0(0x100000, L"Teredo registering with SC in a worker: Unable to grab config lock.");
      goto LABEL_30;
    }
    if ( *((_DWORD *)Context + 6) || !dword_1800C92E0 )
      goto LABEL_8;
    TeredoSetTimer(Context, 0, 0);
    v16 = g_TeredoLock;
    LODWORD(v31) = ReleaseMutex(g_TeredoLock);
    LODWORD(v28) = 2599;
    EventWrite0(
      0x800000,
      L"Lock (%p) released at %S : %S : %u. Return %d",
      v16,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
      "TeredoRegisterWithSCWorker",
      v28,
      v31);
    if ( (unsigned int)TeredoRegisterForSCNotification(Context) == 1294 )
    {
      EventWriteError0(
        0x100000,
        L"Teredo registering with SC in a worker: Service lags SCM. Error (%d). Re-register.",
        1294);
      *((_DWORD *)Context + 695) = 2;
      goto LABEL_30;
    }
  }
  if ( v15 )
    EventWriteError0(0x100000, L"Teredo registering with SC in a worker: Unexpected Wait completion. Error (%d)", v15);
  else
    EventWrite0(0x100000, L"Teredo registering with SC in a worker: Wait completed by event.");
LABEL_30:
  v17 = g_TeredoLock;
  LODWORD(v28) = 2627;
  EventWrite0(
    0x800000,
    L"Get lock (%p) invoked at %S : %S : %u",
    g_TeredoLock,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
    "TeredoRegisterWithSCWorker",
    v28);
  v18 = WaitForSingleObject(v17, 0xFFFFFFFF);
  LODWORD(v31) = v18;
  if ( v18 )
    v4 = L"Lock (%p) failed at %S : %S : %u. Return %d";
  LODWORD(v29) = 2627;
  EventWrite0(
    0x800000,
    v4,
    v17,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
    "TeredoRegisterWithSCWorker",
    v29,
    v31);
  if ( !v18 )
  {
LABEL_8:
    v10 = (void *)*((_QWORD *)Context + 357);
    *((_DWORD *)Context + 696) = 0;
    if ( v10 )
    {
      CloseHandle(v10);
      *((_QWORD *)Context + 357) = 0;
    }
    while ( QueryDepthSList((PSLIST_HEADER)Context + 177) )
    {
      v21 = InterlockedPopEntrySList((PSLIST_HEADER)Context + 177);
      FREE(v21);
    }
    v22 = (SC_HANDLE)*((_QWORD *)Context + 352);
    if ( v22 )
    {
      CloseServiceHandle(v22);
      *((_QWORD *)Context + 352) = 0;
    }
    v23 = (SC_HANDLE)*((_QWORD *)Context + 351);
    if ( v23 )
    {
      CloseServiceHandle(v23);
      *((_QWORD *)Context + 351) = 0;
    }
    v24 = *((_QWORD *)Context + 353);
    if ( v24 )
    {
      FREE(v24);
      *((_QWORD *)Context + 353) = 0;
    }
    if ( *((_DWORD *)Context + 695) == 2 && !*((_DWORD *)Context + 6) )
    {
      v25 = TeredoRegisterWithSC(Context);
      if ( !v25 )
      {
LABEL_47:
        ReleaseAndTraceLock(
          "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
          "TeredoRegisterWithSCWorker",
          2701,
          g_TeredoLock);
        v19 = 2705;
        v20 = 2703;
        goto LABEL_49;
      }
      EventWriteError0(
        0x100000,
        L"Teredo registering with SC in a worker: Unable to re-register with SCM for BFE notifications.Error (%d)",
        v25);
    }
    *((_DWORD *)Context + 695) = 0;
    goto LABEL_47;
  }
  EventWriteError0(0x100000, L"Teredo registering with SC in a worker: Unable to grab config lock");
  v19 = 2633;
  v20 = 2632;
LABEL_49:
  DereferenceCompartmentEx(Context, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c", v20);
  DereferenceServiceEx("TeredoRegisterWithSCWorker", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c", v19);
}

```

## disassembly

```asm
0x180007880  push    rbx
0x180007882  push    rbp
0x180007883  push    rsi
0x180007884  push    rdi
0x180007885  push    r12
0x180007887  push    r13
0x180007889  push    r14
0x18000788b  sub     rsp, 40h
0x18000788f  mov     rdi, cs:g_TeredoLock
0x180007896  lea     r13, aTeredoregister; "TeredoRegisterWithSCWorker"
0x18000789d  mov     rsi, rdx
0x1800078a0  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800078a7  mov     ebp, 97Ch
0x1800078ac  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x1800078b3  mov     dword ptr [rsp+78h+var_50], ebp
0x1800078b7  mov     r8, rdi
0x1800078ba  mov     ecx, 800000h
0x1800078bf  mov     [rsp+78h+var_58], r13
0x1800078c4  call    EventWrite0
0x1800078c9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800078cc  mov     rcx, rdi; hHandle
0x1800078cf  call    cs:__imp_WaitForSingleObject
0x1800078d6  nop     dword ptr [rax+rax+00h]
0x1800078db  xor     r12d, r12d
0x1800078de  lea     r14, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x1800078e5  mov     ebx, eax
0x1800078e7  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800078ee  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x1800078f5  mov     dword ptr [rsp+78h+var_48], ebx
0x1800078f9  test    ebx, ebx
0x1800078fb  mov     dword ptr [rsp+78h+var_50], ebp
0x1800078ff  mov     rdx, r14
0x180007902  mov     [rsp+78h+var_58], r13
0x180007907  cmovnz  rdx, rax
0x18000790b  mov     r8, rdi
0x18000790e  mov     ecx, 800000h
0x180007913  call    EventWrite0
0x180007918  test    ebx, ebx
0x18000791a  jnz     loc_180007D46
0x180007920  mov     ebp, 100000h
0x180007925  cmp     [rsi+18h], r12d
0x180007929  jnz     short loc_18000796A
0x18000792b  xor     edx, edx; lpDatabaseName
0x18000792d  xor     ecx, ecx; lpMachineName
0x18000792f  mov     r8d, 80000000h; dwDesiredAccess
0x180007935  call    cs:__imp_OpenSCManagerW
0x18000793c  nop     dword ptr [rax+rax+00h]
0x180007941  mov     [rsi+0AF8h], rax
0x180007948  test    rax, rax
0x18000794b  jnz     short loc_18000799C
0x18000794d  call    cs:__imp_GetLastError
0x180007954  nop     dword ptr [rax+rax+00h]
0x180007959  lea     rdx, aTeredoRegister_14; "Teredo registering with SC in a worker:"...
0x180007960  mov     r8d, eax
0x180007963  mov     ecx, ebp
0x180007965  call    EventWriteError0
0x18000796a  mov     rcx, [rsi+0B28h]; hObject
0x180007971  mov     [rsi+0AE0h], r12d
0x180007978  test    rcx, rcx
0x18000797b  jz      short loc_180007990
0x18000797d  call    cs:__imp_CloseHandle
0x180007984  nop     dword ptr [rax+rax+00h]
0x180007989  mov     [rsi+0B28h], r12
0x180007990  lea     rbx, [rsi+0B10h]
0x180007997  jmp     loc_180007C82
0x18000799c  mov     r8d, 4; dwDesiredAccess
0x1800079a2  lea     rdx, ServiceName; "BFE"
0x1800079a9  mov     rcx, rax; hSCManager
0x1800079ac  call    cs:__imp_OpenServiceW
0x1800079b3  nop     dword ptr [rax+rax+00h]
0x1800079b8  mov     [rsi+0B00h], rax
0x1800079bf  test    rax, rax
0x1800079c2  jnz     short loc_1800079D9
0x1800079c4  call    cs:__imp_GetLastError
0x1800079cb  nop     dword ptr [rax+rax+00h]
0x1800079d0  lea     rdx, aTeredoRegister_8; "Teredo registering with SC in a worker:"...
0x1800079d7  jmp     short loc_180007960
0x1800079d9  xor     r9d, r9d; lpName
0x1800079dc  xor     r8d, r8d; bInitialState
0x1800079df  xor     edx, edx; bManualReset
0x1800079e1  xor     ecx, ecx; lpEventAttributes
0x1800079e3  call    cs:__imp_CreateEventW
0x1800079ea  nop     dword ptr [rax+rax+00h]
0x1800079ef  mov     [rsi+0B28h], rax
0x1800079f6  test    rax, rax
0x1800079f9  jnz     short loc_180007A0A
0x1800079fb  xor     r8d, r8d
0x1800079fe  lea     rdx, aTeredoRegister_17; "Teredo registering with SC in a worker:"...
0x180007a05  jmp     loc_180007963
0x180007a0a  mov     ecx, 50h ; 'P'; dwBytes
0x180007a0f  call    MALLOC
0x180007a14  mov     [rsi+0B08h], rax
0x180007a1b  test    rax, rax
0x180007a1e  jnz     short loc_180007A37
0x180007a20  lea     r8d, [rax+8]
0x180007a24  mov     ecx, ebp
0x180007a26  lea     rdx, aTeredoRegister_2; "Teredo registering with SC in a worker:"...
0x180007a2d  call    EventWrite0
0x180007a32  jmp     loc_18000796A
0x180007a37  mov     edi, 1
0x180007a3c  mov     rcx, rsi
0x180007a3f  mov     cs:dword_1800C92E0, edi
0x180007a45  call    TeredoRegisterForSCNotification
0x180007a4a  test    eax, eax
0x180007a4c  jz      short loc_180007A66
0x180007a4e  call    cs:__imp_GetLastError
0x180007a55  nop     dword ptr [rax+rax+00h]
0x180007a5a  lea     rdx, aTeredoRegister_20; "Teredo registering with SC in a worker:"...
0x180007a61  jmp     loc_180007960
0x180007a66  mov     dword ptr [rsi+0ADCh], 3
0x180007a70  mov     rbx, cs:g_TeredoLock
0x180007a77  mov     rcx, rbx; hMutex
0x180007a7a  call    cs:__imp_ReleaseMutex
0x180007a81  nop     dword ptr [rax+rax+00h]
0x180007a86  mov     dword ptr [rsp+78h+var_48], eax
0x180007a8a  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007a91  mov     dword ptr [rsp+78h+var_50], 9E5h
0x180007a99  mov     r8, rbx
0x180007a9c  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180007aa3  mov     [rsp+78h+var_58], r13
0x180007aa8  mov     ecx, 800000h
0x180007aad  call    EventWrite0
0x180007ab2  mov     rcx, [rsi+0B28h]; hHandle
0x180007ab9  mov     r8d, edi; bAlertable
0x180007abc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007abf  call    cs:__imp_WaitForSingleObjectEx
0x180007ac6  nop     dword ptr [rax+rax+00h]
0x180007acb  mov     ecx, ebp
0x180007acd  cmp     eax, 0C0h
0x180007ad2  jnz     loc_180007BAE
0x180007ad8  lea     rdx, aTeredoRegister_10; "Teredo registering with SC in a worker:"...
0x180007adf  call    EventWrite0
0x180007ae4  mov     r9, cs:g_TeredoLock
0x180007aeb  lea     rcx, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007af2  mov     r8d, 0A0Bh
0x180007af8  mov     rdx, r13
0x180007afb  call    GetAndTraceLock
0x180007b00  test    eax, eax
0x180007b02  jz      loc_180007B9E
0x180007b08  cmp     [rsi+18h], r12d
0x180007b0c  jnz     loc_18000796A
0x180007b12  cmp     cs:dword_1800C92E0, r12d
0x180007b19  jz      loc_18000796A
0x180007b1f  xor     r8d, r8d
0x180007b22  xor     edx, edx
0x180007b24  mov     rcx, rsi
0x180007b27  call    TeredoSetTimer
0x180007b2c  mov     rbx, cs:g_TeredoLock
0x180007b33  mov     rcx, rbx; hMutex
0x180007b36  call    cs:__imp_ReleaseMutex
0x180007b3d  nop     dword ptr [rax+rax+00h]
0x180007b42  mov     dword ptr [rsp+78h+var_48], eax
0x180007b46  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007b4d  mov     dword ptr [rsp+78h+var_50], 0A27h
0x180007b55  mov     r8, rbx
0x180007b58  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180007b5f  mov     [rsp+78h+var_58], r13
0x180007b64  mov     ecx, 800000h
0x180007b69  call    EventWrite0
0x180007b6e  mov     rcx, rsi
0x180007b71  call    TeredoRegisterForSCNotification
0x180007b76  cmp     eax, 50Eh
0x180007b7b  jnz     loc_180007AB2
0x180007b81  mov     r8d, eax
0x180007b84  lea     rdx, aTeredoRegister_5; "Teredo registering with SC in a worker:"...
0x180007b8b  mov     ecx, ebp
0x180007b8d  call    EventWriteError0
0x180007b92  mov     dword ptr [rsi+0ADCh], 2
0x180007b9c  jmp     short loc_180007BCF
0x180007b9e  lea     rdx, aTeredoRegister_3; "Teredo registering with SC in a worker:"...
0x180007ba5  mov     ecx, ebp
0x180007ba7  call    EventWriteError0
0x180007bac  jmp     short loc_180007BCF
0x180007bae  test    eax, eax
0x180007bb0  jnz     short loc_180007BC0
0x180007bb2  lea     rdx, aTeredoRegister_0; "Teredo registering with SC in a worker:"...
0x180007bb9  call    EventWrite0
0x180007bbe  jmp     short loc_180007BCF
0x180007bc0  mov     r8d, eax
0x180007bc3  lea     rdx, aTeredoRegister_16; "Teredo registering with SC in a worker:"...
0x180007bca  call    EventWriteError0
0x180007bcf  mov     rdi, cs:g_TeredoLock
0x180007bd6  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007bdd  mov     r8, rdi
0x180007be0  mov     dword ptr [rsp+78h+var_50], 0A43h
0x180007be8  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x180007bef  mov     [rsp+78h+var_58], r13
0x180007bf4  mov     ecx, 800000h
0x180007bf9  call    EventWrite0
0x180007bfe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007c01  mov     rcx, rdi; hHandle
0x180007c04  call    cs:__imp_WaitForSingleObject
0x180007c0b  nop     dword ptr [rax+rax+00h]
0x180007c10  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007c17  mov     r8, rdi
0x180007c1a  mov     ebx, eax
0x180007c1c  test    eax, eax
0x180007c1e  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180007c25  mov     dword ptr [rsp+78h+var_48], ebx
0x180007c29  cmovnz  r14, rax
0x180007c2d  mov     dword ptr [rsp+78h+var_50], 0A43h
0x180007c35  mov     rdx, r14
0x180007c38  mov     [rsp+78h+var_58], r13
0x180007c3d  mov     ecx, 800000h
0x180007c42  call    EventWrite0
0x180007c47  test    ebx, ebx
0x180007c49  jz      loc_18000796A
0x180007c4f  lea     rdx, aTeredoRegister_6; "Teredo registering with SC in a worker:"...
0x180007c56  mov     ecx, ebp
0x180007c58  call    EventWriteError0
0x180007c5d  mov     ebx, 0A49h
0x180007c62  lea     r8d, [rbx-1]
0x180007c66  jmp     loc_180007D60
0x180007c6b  mov     rcx, rbx; ListHead
0x180007c6e  call    cs:__imp_InterlockedPopEntrySList
0x180007c75  nop     dword ptr [rax+rax+00h]
0x180007c7a  mov     rcx, rax
0x180007c7d  call    FREE
0x180007c82  mov     rcx, rbx; ListHead
0x180007c85  call    cs:__imp_QueryDepthSList
0x180007c8c  nop     dword ptr [rax+rax+00h]
0x180007c91  test    ax, ax
0x180007c94  jnz     short loc_180007C6B
0x180007c96  mov     rcx, [rsi+0B00h]; hSCObject
0x180007c9d  test    rcx, rcx
0x180007ca0  jz      short loc_180007CB5
0x180007ca2  call    cs:__imp_CloseServiceHandle
0x180007ca9  nop     dword ptr [rax+rax+00h]
0x180007cae  mov     [rsi+0B00h], r12
0x180007cb5  mov     rcx, [rsi+0AF8h]; hSCObject
0x180007cbc  test    rcx, rcx
0x180007cbf  jz      short loc_180007CD4
0x180007cc1  call    cs:__imp_CloseServiceHandle
0x180007cc8  nop     dword ptr [rax+rax+00h]
0x180007ccd  mov     [rsi+0AF8h], r12
0x180007cd4  mov     rcx, [rsi+0B08h]
0x180007cdb  test    rcx, rcx
0x180007cde  jz      short loc_180007CEC
0x180007ce0  call    FREE
0x180007ce5  mov     [rsi+0B08h], r12
0x180007cec  cmp     dword ptr [rsi+0ADCh], 2
0x180007cf3  jnz     short loc_180007D18
0x180007cf5  cmp     [rsi+18h], r12d
0x180007cf9  jnz     short loc_180007D18
0x180007cfb  mov     rcx, rsi; pv
0x180007cfe  call    TeredoRegisterWithSC
0x180007d03  test    eax, eax
0x180007d05  jz      short loc_180007D1F
0x180007d07  mov     r8d, eax
0x180007d0a  lea     rdx, aTeredoRegister_15; "Teredo registering with SC in a worker:"...
0x180007d11  mov     ecx, ebp
0x180007d13  call    EventWriteError0
0x180007d18  mov     [rsi+0ADCh], r12d
0x180007d1f  mov     r9, cs:g_TeredoLock
0x180007d26  lea     rcx, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007d2d  mov     r8d, 0A8Dh
0x180007d33  mov     rdx, r13
0x180007d36  call    ReleaseAndTraceLock
0x180007d3b  mov     ebx, 0A91h
0x180007d40  lea     r8d, [rbx-2]
0x180007d44  jmp     short loc_180007D60
0x180007d46  lea     rdx, aTeredoRegister_6; "Teredo registering with SC in a worker:"...
0x180007d4d  mov     ecx, 100000h
0x180007d52  call    EventWriteError0
0x180007d57  mov     ebx, 982h
0x180007d5c  lea     r8d, [rbx-1]
0x180007d60  lea     rdx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007d67  mov     rcx, rsi
0x180007d6a  call    DereferenceCompartmentEx
0x180007d6f  mov     r8d, ebx
0x180007d72  lea     rdx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007d79  mov     rcx, r13
0x180007d7c  add     rsp, 40h
0x180007d80  pop     r14
0x180007d82  pop     r13
0x180007d84  pop     r12
0x180007d86  pop     rdi
0x180007d87  pop     rsi
0x180007d88  pop     rbp
0x180007d89  pop     rbx
0x180007d8a  jmp     DereferenceServiceEx
```
