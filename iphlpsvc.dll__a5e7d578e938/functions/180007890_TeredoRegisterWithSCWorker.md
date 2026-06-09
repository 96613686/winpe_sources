# TeredoRegisterWithSCWorker

- ea: `0x180007890`
- end: `0x180007d9f`
- name: `TeredoRegisterWithSCWorker`
- size: `1295`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004c64`
- `0x180004f60`
- `0x1800077e8`
- `0x180007890`
- `0x180008c50`
- `0x18000cea0`
- `0x18000d7c0`
- `0x180012dcc`
- `0x1800190f0`
- `0x180022b40`
- `0x1800419c0`
- `0x18005f2f8`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180007c7e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180007c7e`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180007c95`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180007c95`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007acf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007acf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007a8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b46`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007a8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b46`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800078df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007c14`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800078df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007c14`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800079f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800079f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000795d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000795d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000798d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000798d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800079bc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800079bc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007cb2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007cd1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007cb2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007cd1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180007945`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180007945`

## string_xrefs

- `0x180007d70`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007d82`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x1800078b0`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x1800078f7`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007a9a`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007afb`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007b56`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007be6`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007c20`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007d36`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180007c5f`: `Teredo registering with SC in a worker: Unable to grab config lock`
- `0x180007d56`: `Teredo registering with SC in a worker: Unable to grab config lock`
- `0x180007ae8`: `Teredo registering with SC in a worker: Wait completed by apc.`
- `0x180007bc2`: `Teredo registering with SC in a worker: Wait completed by event.`
- `0x180007bd3`: `Teredo registering with SC in a worker: Unexpected Wait completion. Error (%d)`
- `0x180007bae`: `Teredo registering with SC in a worker: Unable to grab config lock.`
- `0x180007969`: `Teredo registering with SC in a worker: Unable to open handle to SCM. Error (%d)`
- `0x1800079e0`: `Teredo registering with SC in a worker: Unable to open handle to BFE. Error (%d)`
- `0x180007a0e`: `Teredo registering with SC in a worker: Unable to create event to stop BFE thread.Error (%d)`
- `0x180007b94`: `Teredo registering with SC in a worker: Service lags SCM. Error (%d). Re-register.`

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
0x180007890  push    rbx
0x180007892  push    rbp
0x180007893  push    rsi
0x180007894  push    rdi
0x180007895  push    r12
0x180007897  push    r13
0x180007899  push    r14
0x18000789b  sub     rsp, 40h
0x18000789f  mov     rdi, cs:g_TeredoLock
0x1800078a6  lea     r13, aTeredoregister; "TeredoRegisterWithSCWorker"
0x1800078ad  mov     rsi, rdx
0x1800078b0  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800078b7  mov     ebp, 97Ch
0x1800078bc  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x1800078c3  mov     dword ptr [rsp+78h+var_50], ebp
0x1800078c7  mov     r8, rdi
0x1800078ca  mov     ecx, 800000h
0x1800078cf  mov     [rsp+78h+var_58], r13
0x1800078d4  call    EventWrite0
0x1800078d9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800078dc  mov     rcx, rdi; hHandle
0x1800078df  call    cs:__imp_WaitForSingleObject
0x1800078e6  nop     dword ptr [rax+rax+00h]
0x1800078eb  xor     r12d, r12d
0x1800078ee  lea     r14, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x1800078f5  mov     ebx, eax
0x1800078f7  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800078fe  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180007905  mov     dword ptr [rsp+78h+var_48], ebx
0x180007909  test    ebx, ebx
0x18000790b  mov     dword ptr [rsp+78h+var_50], ebp
0x18000790f  mov     rdx, r14
0x180007912  mov     [rsp+78h+var_58], r13
0x180007917  cmovnz  rdx, rax
0x18000791b  mov     r8, rdi
0x18000791e  mov     ecx, 800000h
0x180007923  call    EventWrite0
0x180007928  test    ebx, ebx
0x18000792a  jnz     loc_180007D56
0x180007930  mov     ebp, 100000h
0x180007935  cmp     [rsi+18h], r12d
0x180007939  jnz     short loc_18000797A
0x18000793b  xor     edx, edx; lpDatabaseName
0x18000793d  xor     ecx, ecx; lpMachineName
0x18000793f  mov     r8d, 80000000h; dwDesiredAccess
0x180007945  call    cs:__imp_OpenSCManagerW
0x18000794c  nop     dword ptr [rax+rax+00h]
0x180007951  mov     [rsi+0AF8h], rax
0x180007958  test    rax, rax
0x18000795b  jnz     short loc_1800079AC
0x18000795d  call    cs:__imp_GetLastError
0x180007964  nop     dword ptr [rax+rax+00h]
0x180007969  lea     rdx, aTeredoRegister_14; "Teredo registering with SC in a worker:"...
0x180007970  mov     r8d, eax
0x180007973  mov     ecx, ebp
0x180007975  call    EventWriteError0
0x18000797a  mov     rcx, [rsi+0B28h]; hObject
0x180007981  mov     [rsi+0AE0h], r12d
0x180007988  test    rcx, rcx
0x18000798b  jz      short loc_1800079A0
0x18000798d  call    cs:__imp_CloseHandle
0x180007994  nop     dword ptr [rax+rax+00h]
0x180007999  mov     [rsi+0B28h], r12
0x1800079a0  lea     rbx, [rsi+0B10h]
0x1800079a7  jmp     loc_180007C92
0x1800079ac  mov     r8d, 4; dwDesiredAccess
0x1800079b2  lea     rdx, ServiceName; "BFE"
0x1800079b9  mov     rcx, rax; hSCManager
0x1800079bc  call    cs:__imp_OpenServiceW
0x1800079c3  nop     dword ptr [rax+rax+00h]
0x1800079c8  mov     [rsi+0B00h], rax
0x1800079cf  test    rax, rax
0x1800079d2  jnz     short loc_1800079E9
0x1800079d4  call    cs:__imp_GetLastError
0x1800079db  nop     dword ptr [rax+rax+00h]
0x1800079e0  lea     rdx, aTeredoRegister_8; "Teredo registering with SC in a worker:"...
0x1800079e7  jmp     short loc_180007970
0x1800079e9  xor     r9d, r9d; lpName
0x1800079ec  xor     r8d, r8d; bInitialState
0x1800079ef  xor     edx, edx; bManualReset
0x1800079f1  xor     ecx, ecx; lpEventAttributes
0x1800079f3  call    cs:__imp_CreateEventW
0x1800079fa  nop     dword ptr [rax+rax+00h]
0x1800079ff  mov     [rsi+0B28h], rax
0x180007a06  test    rax, rax
0x180007a09  jnz     short loc_180007A1A
0x180007a0b  xor     r8d, r8d
0x180007a0e  lea     rdx, aTeredoRegister_17; "Teredo registering with SC in a worker:"...
0x180007a15  jmp     loc_180007973
0x180007a1a  mov     ecx, 50h ; 'P'; dwBytes
0x180007a1f  call    MALLOC
0x180007a24  mov     [rsi+0B08h], rax
0x180007a2b  test    rax, rax
0x180007a2e  jnz     short loc_180007A47
0x180007a30  lea     r8d, [rax+8]
0x180007a34  mov     ecx, ebp
0x180007a36  lea     rdx, aTeredoRegister_2; "Teredo registering with SC in a worker:"...
0x180007a3d  call    EventWrite0
0x180007a42  jmp     loc_18000797A
0x180007a47  mov     edi, 1
0x180007a4c  mov     rcx, rsi
0x180007a4f  mov     cs:dword_1800C92E0, edi
0x180007a55  call    TeredoRegisterForSCNotification
0x180007a5a  test    eax, eax
0x180007a5c  jz      short loc_180007A76
0x180007a5e  call    cs:__imp_GetLastError
0x180007a65  nop     dword ptr [rax+rax+00h]
0x180007a6a  lea     rdx, aTeredoRegister_20; "Teredo registering with SC in a worker:"...
0x180007a71  jmp     loc_180007970
0x180007a76  mov     dword ptr [rsi+0ADCh], 3
0x180007a80  mov     rbx, cs:g_TeredoLock
0x180007a87  mov     rcx, rbx; hMutex
0x180007a8a  call    cs:__imp_ReleaseMutex
0x180007a91  nop     dword ptr [rax+rax+00h]
0x180007a96  mov     dword ptr [rsp+78h+var_48], eax
0x180007a9a  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007aa1  mov     dword ptr [rsp+78h+var_50], 9E5h
0x180007aa9  mov     r8, rbx
0x180007aac  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180007ab3  mov     [rsp+78h+var_58], r13
0x180007ab8  mov     ecx, 800000h
0x180007abd  call    EventWrite0
0x180007ac2  mov     rcx, [rsi+0B28h]; hHandle
0x180007ac9  mov     r8d, edi; bAlertable
0x180007acc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007acf  call    cs:__imp_WaitForSingleObjectEx
0x180007ad6  nop     dword ptr [rax+rax+00h]
0x180007adb  mov     ecx, ebp
0x180007add  cmp     eax, 0C0h
0x180007ae2  jnz     loc_180007BBE
0x180007ae8  lea     rdx, aTeredoRegister_10; "Teredo registering with SC in a worker:"...
0x180007aef  call    EventWrite0
0x180007af4  mov     r9, cs:g_TeredoLock
0x180007afb  lea     rcx, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007b02  mov     r8d, 0A0Bh
0x180007b08  mov     rdx, r13
0x180007b0b  call    GetAndTraceLock
0x180007b10  test    eax, eax
0x180007b12  jz      loc_180007BAE
0x180007b18  cmp     [rsi+18h], r12d
0x180007b1c  jnz     loc_18000797A
0x180007b22  cmp     cs:dword_1800C92E0, r12d
0x180007b29  jz      loc_18000797A
0x180007b2f  xor     r8d, r8d
0x180007b32  xor     edx, edx
0x180007b34  mov     rcx, rsi
0x180007b37  call    TeredoSetTimer
0x180007b3c  mov     rbx, cs:g_TeredoLock
0x180007b43  mov     rcx, rbx; hMutex
0x180007b46  call    cs:__imp_ReleaseMutex
0x180007b4d  nop     dword ptr [rax+rax+00h]
0x180007b52  mov     dword ptr [rsp+78h+var_48], eax
0x180007b56  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007b5d  mov     dword ptr [rsp+78h+var_50], 0A27h
0x180007b65  mov     r8, rbx
0x180007b68  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180007b6f  mov     [rsp+78h+var_58], r13
0x180007b74  mov     ecx, 800000h
0x180007b79  call    EventWrite0
0x180007b7e  mov     rcx, rsi
0x180007b81  call    TeredoRegisterForSCNotification
0x180007b86  cmp     eax, 50Eh
0x180007b8b  jnz     loc_180007AC2
0x180007b91  mov     r8d, eax
0x180007b94  lea     rdx, aTeredoRegister_5; "Teredo registering with SC in a worker:"...
0x180007b9b  mov     ecx, ebp
0x180007b9d  call    EventWriteError0
0x180007ba2  mov     dword ptr [rsi+0ADCh], 2
0x180007bac  jmp     short loc_180007BDF
0x180007bae  lea     rdx, aTeredoRegister_3; "Teredo registering with SC in a worker:"...
0x180007bb5  mov     ecx, ebp
0x180007bb7  call    EventWriteError0
0x180007bbc  jmp     short loc_180007BDF
0x180007bbe  test    eax, eax
0x180007bc0  jnz     short loc_180007BD0
0x180007bc2  lea     rdx, aTeredoRegister_0; "Teredo registering with SC in a worker:"...
0x180007bc9  call    EventWrite0
0x180007bce  jmp     short loc_180007BDF
0x180007bd0  mov     r8d, eax
0x180007bd3  lea     rdx, aTeredoRegister_16; "Teredo registering with SC in a worker:"...
0x180007bda  call    EventWriteError0
0x180007bdf  mov     rdi, cs:g_TeredoLock
0x180007be6  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007bed  mov     r8, rdi
0x180007bf0  mov     dword ptr [rsp+78h+var_50], 0A43h
0x180007bf8  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x180007bff  mov     [rsp+78h+var_58], r13
0x180007c04  mov     ecx, 800000h
0x180007c09  call    EventWrite0
0x180007c0e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007c11  mov     rcx, rdi; hHandle
0x180007c14  call    cs:__imp_WaitForSingleObject
0x180007c1b  nop     dword ptr [rax+rax+00h]
0x180007c20  lea     r9, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007c27  mov     r8, rdi
0x180007c2a  mov     ebx, eax
0x180007c2c  test    eax, eax
0x180007c2e  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x180007c35  mov     dword ptr [rsp+78h+var_48], ebx
0x180007c39  cmovnz  r14, rax
0x180007c3d  mov     dword ptr [rsp+78h+var_50], 0A43h
0x180007c45  mov     rdx, r14
0x180007c48  mov     [rsp+78h+var_58], r13
0x180007c4d  mov     ecx, 800000h
0x180007c52  call    EventWrite0
0x180007c57  test    ebx, ebx
0x180007c59  jz      loc_18000797A
0x180007c5f  lea     rdx, aTeredoRegister_6; "Teredo registering with SC in a worker:"...
0x180007c66  mov     ecx, ebp
0x180007c68  call    EventWriteError0
0x180007c6d  mov     ebx, 0A49h
0x180007c72  lea     r8d, [rbx-1]
0x180007c76  jmp     loc_180007D70
0x180007c7b  mov     rcx, rbx; ListHead
0x180007c7e  call    cs:__imp_InterlockedPopEntrySList
0x180007c85  nop     dword ptr [rax+rax+00h]
0x180007c8a  mov     rcx, rax
0x180007c8d  call    FREE
0x180007c92  mov     rcx, rbx; ListHead
0x180007c95  call    cs:__imp_QueryDepthSList
0x180007c9c  nop     dword ptr [rax+rax+00h]
0x180007ca1  test    ax, ax
0x180007ca4  jnz     short loc_180007C7B
0x180007ca6  mov     rcx, [rsi+0B00h]; hSCObject
0x180007cad  test    rcx, rcx
0x180007cb0  jz      short loc_180007CC5
0x180007cb2  call    cs:__imp_CloseServiceHandle
0x180007cb9  nop     dword ptr [rax+rax+00h]
0x180007cbe  mov     [rsi+0B00h], r12
0x180007cc5  mov     rcx, [rsi+0AF8h]; hSCObject
0x180007ccc  test    rcx, rcx
0x180007ccf  jz      short loc_180007CE4
0x180007cd1  call    cs:__imp_CloseServiceHandle
0x180007cd8  nop     dword ptr [rax+rax+00h]
0x180007cdd  mov     [rsi+0AF8h], r12
0x180007ce4  mov     rcx, [rsi+0B08h]
0x180007ceb  test    rcx, rcx
0x180007cee  jz      short loc_180007CFC
0x180007cf0  call    FREE
0x180007cf5  mov     [rsi+0B08h], r12
0x180007cfc  cmp     dword ptr [rsi+0ADCh], 2
0x180007d03  jnz     short loc_180007D28
0x180007d05  cmp     [rsi+18h], r12d
0x180007d09  jnz     short loc_180007D28
0x180007d0b  mov     rcx, rsi; pv
0x180007d0e  call    TeredoRegisterWithSC
0x180007d13  test    eax, eax
0x180007d15  jz      short loc_180007D2F
0x180007d17  mov     r8d, eax
0x180007d1a  lea     rdx, aTeredoRegister_15; "Teredo registering with SC in a worker:"...
0x180007d21  mov     ecx, ebp
0x180007d23  call    EventWriteError0
0x180007d28  mov     [rsi+0ADCh], r12d
0x180007d2f  mov     r9, cs:g_TeredoLock
0x180007d36  lea     rcx, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007d3d  mov     r8d, 0A8Dh
0x180007d43  mov     rdx, r13
0x180007d46  call    ReleaseAndTraceLock
0x180007d4b  mov     ebx, 0A91h
0x180007d50  lea     r8d, [rbx-2]
0x180007d54  jmp     short loc_180007D70
0x180007d56  lea     rdx, aTeredoRegister_6; "Teredo registering with SC in a worker:"...
0x180007d5d  mov     ecx, 100000h
0x180007d62  call    EventWriteError0
0x180007d67  mov     ebx, 982h
0x180007d6c  lea     r8d, [rbx-1]
0x180007d70  lea     rdx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007d77  mov     rcx, rsi
0x180007d7a  call    DereferenceCompartmentEx
0x180007d7f  mov     r8d, ebx
0x180007d82  lea     rdx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180007d89  mov     rcx, r13
0x180007d8c  add     rsp, 40h
0x180007d90  pop     r14
0x180007d92  pop     r13
0x180007d94  pop     r12
0x180007d96  pop     rdi
0x180007d97  pop     rsi
0x180007d98  pop     rbp
0x180007d99  pop     rbx
0x180007d9a  jmp     DereferenceServiceEx
```
