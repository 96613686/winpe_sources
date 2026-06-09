# Notifier::NotifyThread::FireNotification(__MIDL_IEventObjectChange_0001,ushort const *,__MIDL___MIDL_itf_esstruct_0000_0000_0001,ushort const *)

- ea: `0x18000f3d8`
- end: `0x18000f80b`
- name: `?FireNotification@NotifyThread@Notifier@@QEAAXW4__MIDL_IEventObjectChange_0001@@PEBGW4__MIDL___MIDL_itf_esstruct_0000_0000_0001@@1@Z`
- size: `1075`
- prototype: `void __fastcall(__int64, int, const OLECHAR *, int, OLECHAR *psz)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e170`
- `0x180034bf0`

## callees

- `0x180003d54`
- `0x180009034`
- `0x18000f3d8`
- `0x180010410`
- `0x180012654`
- `0x1800234f4`
- `0x1800355e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f441`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f589`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f441`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f589`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f509`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f509`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f5cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f5cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f4ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f519`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f532`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f4ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f519`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f532`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000f764`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000f764`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f594`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f626`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f735`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f594`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f626`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f735`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f60a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f60a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f489`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f49f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f489`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f49f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000f4ad`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000f4ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f465`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f465`

## string_xrefs

- `0x18000f55e`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f5b1`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f64b`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f67d`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f693`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f6d7`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f71b`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f79c`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f7ce`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f7fa`: `com\complus\src\events\tier2\notify.cpp`
- `0x18000f6b5`: `com\complus\src\events\Shared\UTSem.h`
- `0x18000f7ee`: `CreateEvent`
- `0x18000f790`: `CreateThread`

## pseudocode

```c
void __fastcall Notifier::NotifyThread::FireNotification(__int64 a1, int a2, const OLECHAR *a3, int a4, OLECHAR *psz)
{
  HANDLE EventW; // r14
  _DWORD *v10; // rax
  _DWORD *v11; // rsi
  HANDLE v12; // rbx
  BSTR v13; // rax
  OLECHAR *v14; // rcx
  DWORD v15; // ebx
  HANDLE CurrentProcess; // rbx
  HANDLE v17; // rax
  void *v18; // rcx
  HANDLE v19; // rax
  int v20; // [rsp+40h] [rbp-10h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-8h]
  HANDLE TargetHandle; // [rsp+90h] [rbp+40h] BYREF
  DWORD ThreadId; // [rsp+98h] [rbp+48h] BYREF

  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 144);
  v20 = 1;
  if ( a1 == -144 )
    InternalError(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x154u, 0x80001203, 0x10u);
  CSemExclusiveES::Lock((CSemExclusiveES *)lpCriticalSection);
  if ( *(_DWORD *)(a1 + 200) == 1 )
  {
    CLockES::UnLock((CLockES *)&v20);
    if ( *(_DWORD *)(a1 + 200) == 1 )
      InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x313u, 0x14u, L"EventsystemShuttingDown");
  }
  if ( *(_DWORD *)(a1 + 192) )
  {
    v18 = *(void **)(a1 + 48);
    if ( v18 )
    {
      CloseHandle(v18);
      *(_QWORD *)(a1 + 48) = 0;
    }
    _InterlockedAdd((volatile signed __int32 *)(a1 + 196), 1u);
    ThreadId = 0;
    v19 = CreateThread(0, 0, Notifier::NotifyThread::ThreadMain, (LPVOID)a1, 0, &ThreadId);
    *(_QWORD *)(a1 + 48) = v19;
    if ( !v19 )
    {
      CLockES::UnLock((CLockES *)&v20);
      Notifier::NotifyThread::Release((Notifier::NotifyThread *)a1);
      if ( !*(_QWORD *)(a1 + 48) )
        InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x324u, 0x14u, L"CreateThread");
    }
    *(_DWORD *)(a1 + 192) = 0;
  }
  if ( WaitForSingleObject(*(HANDLE *)(a1 + 56), 0xFFFFFFFF) )
  {
    CLockES::UnLock((CLockES *)&v20);
    InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x32Eu, 0x14u, L"WaitForSingleObject");
  }
  TargetHandle = 0;
  EventW = 0;
  if ( a2 == 2 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      CLockES::UnLock((CLockES *)&v20);
      InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x33Cu, 0x14u, L"CreateEvent");
    }
    CurrentProcess = GetCurrentProcess();
    v17 = GetCurrentProcess();
    DuplicateHandle(v17, EventW, CurrentProcess, &TargetHandle, 0, 0, 2u);
    if ( !TargetHandle )
    {
      CLockES::UnLock((CLockES *)&v20);
      CloseHandle(EventW);
      EventW = 0;
      if ( !TargetHandle )
        InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x34Cu, 0x14u, L"DuplicateHandle");
    }
  }
  v10 = CoTaskMemAlloc(0x40u);
  v11 = v10;
  if ( v10 )
  {
    v12 = TargetHandle;
    *(_QWORD *)v10 = 0;
    v10[2] = a2;
    v13 = SysAllocString(a3);
    v14 = psz;
    *((_QWORD *)v11 + 2) = v13;
    v11[6] = a4;
    *((_QWORD *)v11 + 4) = v12;
    *((_QWORD *)v11 + 5) = SysAllocString(v14);
    CoCreateGuid((GUID *)v11 + 3);
    if ( !*((_QWORD *)v11 + 2) )
      InternalError(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x13Au, 0xC0001204, 0x14u);
    if ( !*((_QWORD *)v11 + 5) )
      InternalError(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x13Bu, 0xC0001204, 0x14u);
  }
  else
  {
    CLockES::UnLock((CLockES *)&v20);
    InternalError(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x357u, 0xC0001204, 0x14u);
    v11 = 0;
  }
  CSemExclusiveES::Lock((CSemExclusiveES *)(a1 + 72));
  if ( *(_QWORD *)(a1 + 128) )
  {
    **(_QWORD **)(a1 + 136) = v11;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 136) )
      InternalAssert(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x293u, 0x14u, L"m_pLastNotify == 0");
    *(_QWORD *)(a1 + 128) = v11;
  }
  *(_QWORD *)(a1 + 136) = v11;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  SetEvent(*(HANDLE *)(a1 + 120));
  if ( v20 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v20 = 0;
  }
  if ( EventW )
  {
    v15 = WaitForSingleObject(EventW, 0x1D4C0u);
    CloseHandle(EventW);
    if ( v15 == -1 )
      InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x368u, 0x14u, L"WaitForSingleObject");
  }
  if ( v20 )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000f3d8  mov     [rsp-38h+arg_10], rbx
0x18000f3dd  push    rbp
0x18000f3de  push    rsi
0x18000f3df  push    rdi
0x18000f3e0  push    r12
0x18000f3e2  push    r13
0x18000f3e4  push    r14
0x18000f3e6  push    r15
0x18000f3e8  mov     rbp, rsp
0x18000f3eb  sub     rsp, 50h
0x18000f3ef  lea     rax, [rcx+90h]
0x18000f3f6  xor     esi, esi
0x18000f3f8  mov     [rbp+lpCriticalSection], rax
0x18000f3fc  mov     ebx, 1
0x18000f401  mov     [rbp+var_10], ebx
0x18000f404  mov     r12d, r9d
0x18000f407  mov     r13, r8
0x18000f40a  mov     r15d, edx
0x18000f40d  mov     rdi, rcx
0x18000f410  test    rax, rax
0x18000f413  jz      loc_18000F6B0
0x18000f419  mov     rcx, [rbp+lpCriticalSection]; this
0x18000f41d  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18000f422  cmp     [rdi+0C8h], ebx
0x18000f428  jz      loc_18000F6F4
0x18000f42e  cmp     [rdi+0C0h], esi
0x18000f434  jnz     loc_18000F72C
0x18000f43a  mov     rcx, [rdi+38h]; hHandle
0x18000f43e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f441  call    cs:__imp_WaitForSingleObject
0x18000f447  test    eax, eax
0x18000f449  jnz     loc_18000F7B3
0x18000f44f  mov     [rbp+TargetHandle], rsi
0x18000f453  mov     r14, rsi
0x18000f456  cmp     r15d, 2
0x18000f45a  jz      loc_18000F5C2
0x18000f460  mov     ecx, 40h ; '@'; cb
0x18000f465  call    cs:__imp_CoTaskMemAlloc
0x18000f46b  mov     rsi, rax
0x18000f46e  test    rax, rax
0x18000f471  jz      loc_18000F550
0x18000f477  mov     rbx, [rbp+TargetHandle]
0x18000f47b  mov     rcx, r13; psz
0x18000f47e  mov     qword ptr [rax], 0
0x18000f485  mov     [rax+8], r15d
0x18000f489  call    cs:__imp_SysAllocString
0x18000f48f  mov     rcx, [rbp+psz]; psz
0x18000f493  mov     [rsi+10h], rax
0x18000f497  mov     [rsi+18h], r12d
0x18000f49b  mov     [rsi+20h], rbx
0x18000f49f  call    cs:__imp_SysAllocString
0x18000f4a5  lea     rcx, [rsi+30h]; pguid
0x18000f4a9  mov     [rsi+28h], rax
0x18000f4ad  call    cs:__imp_CoCreateGuid
0x18000f4b3  xor     r15d, r15d
0x18000f4b6  cmp     [rsi+10h], r15
0x18000f4ba  jz      loc_18000F68E
0x18000f4c0  cmp     [rsi+28h], r15
0x18000f4c4  jz      loc_18000F6D2
0x18000f4ca  lea     rcx, [rdi+48h]; this
0x18000f4ce  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x18000f4d3  cmp     [rdi+80h], r15
0x18000f4da  jnz     loc_18000F65C
0x18000f4e0  cmp     [rdi+88h], r15
0x18000f4e7  jnz     loc_18000F66B
0x18000f4ed  mov     [rdi+80h], rsi
0x18000f4f4  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000f4f8  mov     [rdi+88h], rsi
0x18000f4ff  call    cs:__imp_LeaveCriticalSection
0x18000f505  mov     rcx, [rdi+78h]; hEvent
0x18000f509  call    cs:__imp_SetEvent
0x18000f50f  cmp     [rbp+var_10], r15d
0x18000f513  jz      short loc_18000F523
0x18000f515  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18000f519  call    cs:__imp_LeaveCriticalSection
0x18000f51f  mov     [rbp+var_10], r15d
0x18000f523  test    r14, r14
0x18000f526  jnz     short loc_18000F581
0x18000f528  cmp     [rbp+var_10], r15d
0x18000f52c  jz      short loc_18000F538
0x18000f52e  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18000f532  call    cs:__imp_LeaveCriticalSection
0x18000f538  mov     rbx, [rsp+50h+arg_10]
0x18000f540  add     rsp, 50h
0x18000f544  pop     r15
0x18000f546  pop     r14
0x18000f548  pop     r13
0x18000f54a  pop     r12
0x18000f54c  pop     rdi
0x18000f54d  pop     rsi
0x18000f54e  pop     rbp
0x18000f54f  retn
0x18000f550  lea     rcx, [rbp+var_10]; this
0x18000f554  call    ?UnLock@CLockES@@QEAAXXZ; CLockES::UnLock(void)
0x18000f559  mov     edx, 357h; unsigned int
0x18000f55e  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f565  mov     r9d, 14h; unsigned __int16
0x18000f56b  mov     r8d, 0C0001204h; unsigned int
0x18000f571  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000f576  xor     r15d, r15d
0x18000f579  mov     esi, r15d
0x18000f57c  jmp     loc_18000F4CA
0x18000f581  mov     edx, 1D4C0h; dwMilliseconds
0x18000f586  mov     rcx, r14; hHandle
0x18000f589  call    cs:__imp_WaitForSingleObject
0x18000f58f  mov     rcx, r14; hObject
0x18000f592  mov     ebx, eax
0x18000f594  call    cs:__imp_CloseHandle
0x18000f59a  cmp     ebx, 0FFFFFFFFh
0x18000f59d  jnz     short loc_18000F528
0x18000f59f  mov     r8d, 14h; unsigned __int16
0x18000f5a5  lea     r9, aWaitforsingleo; "WaitForSingleObject"
0x18000f5ac  mov     edx, 368h; unsigned int
0x18000f5b1  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f5b8  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18000f5bd  jmp     loc_18000F528
0x18000f5c2  xor     r9d, r9d; lpName
0x18000f5c5  xor     r8d, r8d; bInitialState
0x18000f5c8  xor     edx, edx; bManualReset
0x18000f5ca  xor     ecx, ecx; lpEventAttributes
0x18000f5cc  call    cs:__imp_CreateEventW
0x18000f5d2  mov     r14, rax
0x18000f5d5  test    rax, rax
0x18000f5d8  jz      loc_18000F7DF
0x18000f5de  call    cs:__imp_GetCurrentProcess
0x18000f5e4  mov     rbx, rax
0x18000f5e7  call    cs:__imp_GetCurrentProcess
0x18000f5ed  mov     [rsp+50h+dwOptions], 2; dwOptions
0x18000f5f5  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18000f5f9  mov     rcx, rax; hSourceProcessHandle
0x18000f5fc  mov     [rsp+50h+bInheritHandle], esi; bInheritHandle
0x18000f600  mov     r8, rbx; hTargetProcessHandle
0x18000f603  mov     [rsp+50h+dwDesiredAccess], esi; dwDesiredAccess
0x18000f607  mov     rdx, r14; hSourceHandle
0x18000f60a  call    cs:__imp_DuplicateHandle
0x18000f610  cmp     [rbp+TargetHandle], rsi
0x18000f614  jnz     loc_18000F460
0x18000f61a  lea     rcx, [rbp+var_10]; this
0x18000f61e  call    ?UnLock@CLockES@@QEAAXXZ; CLockES::UnLock(void)
0x18000f623  mov     rcx, r14; hObject
0x18000f626  call    cs:__imp_CloseHandle
0x18000f62c  mov     r14, rsi
0x18000f62f  cmp     [rbp+TargetHandle], rsi
0x18000f633  jnz     loc_18000F460
0x18000f639  mov     r8d, 14h; unsigned __int16
0x18000f63f  lea     r9, aDuplicatehandl; "DuplicateHandle"
0x18000f646  mov     edx, 34Ch; unsigned int
0x18000f64b  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f652  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18000f657  jmp     loc_18000F460
0x18000f65c  mov     rax, [rdi+88h]
0x18000f663  mov     [rax], rsi
0x18000f666  jmp     loc_18000F4F4
0x18000f66b  mov     r8d, 14h; unsigned __int16
0x18000f671  lea     r9, aMPlastnotify0; "m_pLastNotify == 0"
0x18000f678  mov     edx, 293h; unsigned int
0x18000f67d  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f684  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000f689  jmp     loc_18000F4ED
0x18000f68e  mov     edx, 13Ah; unsigned int
0x18000f693  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f69a  mov     r9d, 14h; unsigned __int16
0x18000f6a0  mov     r8d, 0C0001204h; unsigned int
0x18000f6a6  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000f6ab  jmp     loc_18000F4C0
0x18000f6b0  mov     edx, 154h; unsigned int
0x18000f6b5  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x18000f6bc  mov     r9d, 10h; unsigned __int16
0x18000f6c2  mov     r8d, 80001203h; unsigned int
0x18000f6c8  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000f6cd  jmp     loc_18000F419
0x18000f6d2  mov     edx, 13Bh; unsigned int
0x18000f6d7  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f6de  mov     r9d, 14h; unsigned __int16
0x18000f6e4  mov     r8d, 0C0001204h; unsigned int
0x18000f6ea  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000f6ef  jmp     loc_18000F4CA
0x18000f6f4  lea     rcx, [rbp+var_10]; this
0x18000f6f8  call    ?UnLock@CLockES@@QEAAXXZ; CLockES::UnLock(void)
0x18000f6fd  cmp     [rdi+0C8h], ebx
0x18000f703  jnz     loc_18000F42E
0x18000f709  mov     r8d, 14h; unsigned __int16
0x18000f70f  lea     r9, aEventsystemshu; "EventsystemShuttingDown"
0x18000f716  mov     edx, 313h; unsigned int
0x18000f71b  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f722  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18000f727  jmp     loc_18000F42E
0x18000f72c  mov     rcx, [rdi+30h]; hObject
0x18000f730  test    rcx, rcx
0x18000f733  jz      short loc_18000F73F
0x18000f735  call    cs:__imp_CloseHandle
0x18000f73b  mov     [rdi+30h], rsi
0x18000f73f  lock add [rdi+0C4h], ebx
0x18000f746  lea     rax, [rbp+ThreadId]
0x18000f74a  mov     [rbp+ThreadId], esi
0x18000f74d  mov     qword ptr [rsp+50h+bInheritHandle], rax; lpThreadId
0x18000f752  lea     r8, ?ThreadMain@NotifyThread@Notifier@@CAKPEAX@Z; lpStartAddress
0x18000f759  mov     r9, rdi; lpParameter
0x18000f75c  mov     [rsp+50h+dwDesiredAccess], esi; dwCreationFlags
0x18000f760  xor     edx, edx; dwStackSize
0x18000f762  xor     ecx, ecx; lpThreadAttributes
0x18000f764  call    cs:__imp_CreateThread
0x18000f76a  mov     [rdi+30h], rax
0x18000f76e  test    rax, rax
0x18000f771  jnz     short loc_18000F7A8
0x18000f773  lea     rcx, [rbp+var_10]; this
0x18000f777  call    ?UnLock@CLockES@@QEAAXXZ; CLockES::UnLock(void)
0x18000f77c  mov     rcx, rdi; this
0x18000f77f  call    ?Release@NotifyThread@Notifier@@QEAAKXZ; Notifier::NotifyThread::Release(void)
0x18000f784  cmp     [rdi+30h], rsi
0x18000f788  jnz     short loc_18000F7A8
0x18000f78a  mov     r8d, 14h; unsigned __int16
0x18000f790  lea     r9, aCreatethread; "CreateThread"
0x18000f797  mov     edx, 324h; unsigned int
0x18000f79c  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f7a3  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18000f7a8  mov     [rdi+0C0h], esi
0x18000f7ae  jmp     loc_18000F43A
0x18000f7b3  lea     rcx, [rbp+var_10]; this
0x18000f7b7  call    ?UnLock@CLockES@@QEAAXXZ; CLockES::UnLock(void)
0x18000f7bc  mov     r8d, 14h; unsigned __int16
0x18000f7c2  lea     r9, aWaitforsingleo; "WaitForSingleObject"
0x18000f7c9  mov     edx, 32Eh; unsigned int
0x18000f7ce  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f7d5  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18000f7da  jmp     loc_18000F44F
0x18000f7df  lea     rcx, [rbp+var_10]; this
0x18000f7e3  call    ?UnLock@CLockES@@QEAAXXZ; CLockES::UnLock(void)
0x18000f7e8  mov     r8d, 14h; unsigned __int16
0x18000f7ee  lea     r9, aCreateevent; "CreateEvent"
0x18000f7f5  mov     edx, 33Ch; unsigned int
0x18000f7fa  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000f801  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x18000f806  jmp     loc_18000F5DE
```
