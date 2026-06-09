# DriverEntry

- ea: `0x1400291a8`
- end: `0x1400294ab`
- name: `DriverEntry`
- size: `771`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028b80`

## callees

- `0x140005f30`
- `0x140006380`
- `0x140014970`
- `0x140016670`
- `0x14001686c`
- `0x140022d88`
- `0x140028714`
- `0x140028ac8`
- `0x140029088`
- `0x1400291a8`
- `0x1400294b4`
- `0x14002965c`
- `0x14002a15c`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x14002923c`
- `ntoskrnl!EtwRegister` at `0x14002923c`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400292c6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400292c6`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140029208`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140029208`
- `ntoskrnl!SeRegisterLogonSessionTerminatedRoutineEx` at `0x1400292b3`
- `ntoskrnl!SeRegisterLogonSessionTerminatedRoutineEx` at `0x1400292b3`
- `ntoskrnl!EtwWrite` at `0x140029475`
- `ntoskrnl!EtwWrite` at `0x140029475`
- `FLTMGR!FltStartFiltering` at `0x14002940a`
- `FLTMGR!FltStartFiltering` at `0x14002940a`
- `FLTMGR!FltRegisterFilter` at `0x1400293e6`
- `FLTMGR!FltRegisterFilter` at `0x1400293e6`
- `FLTMGR!FltInitializePushLock` at `0x140029289`
- `FLTMGR!FltInitializePushLock` at `0x140029392`
- `FLTMGR!FltInitializePushLock` at `0x140029289`
- `FLTMGR!FltInitializePushLock` at `0x140029392`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v5; // ebx
  __int64 *v6; // rcx
  int v7; // edx
  char v8; // al
  __int64 *v9; // rdx
  char v10; // al
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rbx
  int Settings; // eax
  __int64 *v16; // rdx
  int v17; // [rsp+30h] [rbp-20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-18h] BYREF

  if ( SkipDriverLoad )
    return -1073741823;
  if ( (unsigned __int8)LuafvSkipDriverLoad() )
    return -1073740948;
  wil_InitializeFeatureStaging();
  qword_14000F308 = (__int64)DriverObject;
  ExInitializeRundownProtection(&RunRef);
  qword_14000F290 = (__int64)&qword_14000F288;
  qword_14000F288 = (__int64)&qword_14000F288;
  v5 = EtwRegister(&LuafvEventProviderId, 0, 0, &qword_14000F120);
  if ( v5 >= 0 )
  {
    LuafvInitializePool();
    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
    LuafvInitializeSdTable();
    LuafvInitializeFileTable();
    qword_14000F2E0 = 0;
    qword_14000F2F0 = 0;
    FltInitializePushLock(&UserListLock);
    qword_14000E878 = (__int64)&UserList;
    UserList = (__int64)&UserList;
    SeRegisterLogonSessionTerminatedRoutineEx(UserLogoffCallback, 0);
    KeInitializeSpinLock(&ScavengerSpinLock);
    ScavengerWorkItem.Parameter = 0;
    ScavengerWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)ScavengerThreadRoutine;
    ScavengerWorkItem.List.Flink = 0;
    ScavengerInitialized = 1;
    memset(LuafvOperationRegistration, 0, 0x620u);
    v6 = LuafvOperationRegistration;
    v7 = 0;
    do
    {
      v8 = v7++ - 20;
      *(_BYTE *)v6 = v8;
      v6[1] = (__int64)LuafvPreRedirect;
      v6 += 4;
    }
    while ( v7 < 48 );
    *(_BYTE *)v6 = 0x80;
    v9 = &LuafvOperationRegistrationOverrides;
    v10 = 0;
    do
    {
      v11 = v10;
      v12 = *((_DWORD *)v9 + 1);
      v9 += 4;
      v11 *= 32;
      *(_DWORD *)((char *)&LuafvOperationRegistration[80] + v11 + 4) = v12;
      *(__int64 *)((char *)&LuafvOperationRegistration[81] + v11) = *(v9 - 3);
      *(__int64 *)((char *)&LuafvOperationRegistration[82] + v11) = *(v9 - 2);
      v10 = *(_BYTE *)v9;
    }
    while ( *(_BYTE *)v9 != 0x80 );
    v13 = 0;
    v14 = 0;
    do
    {
      LuafvDvfcbHashTable[v14 + 1] = (__int64)&LuafvDvfcbHashTable[v14];
      LuafvDvfcbHashTable[v14] = (__int64)&LuafvDvfcbHashTable[v14];
      FltInitializePushLock((PULONG_PTR)&qword_14000E310[v14]);
      ++v13;
      v14 += 3;
    }
    while ( v13 != 16 );
    Settings = LuafvReadSettings(RegistryPath);
    v5 = Settings;
    if ( Settings < 0 )
    {
      v16 = (__int64 *)&LuafvReadSettingsFailed;
    }
    else
    {
      if ( (dword_14000F114 & 1) != 0 )
        LuafvFilterRegistration.FilterUnloadCallback = (PFLT_FILTER_UNLOAD_CALLBACK)LuafvUnload;
      Settings = FltRegisterFilter(DriverObject, &LuafvFilterRegistration, &LuafvDriverData);
      v5 = Settings;
      if ( Settings < 0 )
      {
        LuafvDriverData = 0;
        v16 = LuafvFilterRegistrationFailed;
      }
      else
      {
        Settings = LuafvInitializeSecurity();
        v5 = Settings;
        if ( Settings < 0 )
        {
          v16 = LuafvInitializeSecurityFailed;
        }
        else
        {
          Settings = FltStartFiltering(LuafvDriverData);
          v5 = Settings;
          if ( Settings >= 0 )
            return v5;
          v16 = LuafvStartFilteringFailed;
        }
      }
    }
    v17 = Settings;
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (ULONGLONG)&v17;
    EtwWrite(qword_14000F120, (PCEVENT_DESCRIPTOR)v16, 0, 1u, &UserData);
    LuafvUnload(0);
    return v5;
  }
  wil_UninitializeFeatureStaging();
  return v5;
}

```

## disassembly

```asm
0x1400291a8  mov     [rsp-28h+arg_10], rbx
0x1400291ad  push    rbp
0x1400291ae  push    rsi
0x1400291af  push    rdi
0x1400291b0  push    r13
0x1400291b2  push    r14
0x1400291b4  mov     rbp, rsp
0x1400291b7  sub     rsp, 50h
0x1400291bb  mov     rax, cs:__security_cookie
0x1400291c2  xor     rax, rsp
0x1400291c5  mov     [rbp+var_8], rax
0x1400291c9  cmp     cs:SkipDriverLoad, 0
0x1400291d0  mov     r14, rdx
0x1400291d3  mov     rsi, rcx
0x1400291d6  jz      short loc_1400291E2
0x1400291d8  mov     eax, 0C0000001h
0x1400291dd  jmp     loc_14002948A
0x1400291e2  call    LuafvSkipDriverLoad
0x1400291e7  test    al, al
0x1400291e9  jz      short loc_1400291F5
0x1400291eb  mov     eax, 0C000036Ch
0x1400291f0  jmp     loc_14002948A
0x1400291f5  call    wil_InitializeFeatureStaging
0x1400291fa  lea     rcx, RunRef; RunRef
0x140029201  mov     cs:qword_14000F308, rsi
0x140029208  call    cs:__imp_ExInitializeRundownProtection
0x14002920f  nop     dword ptr [rax+rax+00h]
0x140029214  lea     rax, qword_14000F288
0x14002921b  xor     r8d, r8d; CallbackContext
0x14002921e  lea     r9, qword_14000F120; RegHandle
0x140029225  mov     cs:qword_14000F290, rax
0x14002922c  xor     edx, edx; EnableCallback
0x14002922e  mov     cs:qword_14000F288, rax
0x140029235  lea     rcx, LuafvEventProviderId; ProviderId
0x14002923c  call    cs:__imp_EtwRegister
0x140029243  nop     dword ptr [rax+rax+00h]
0x140029248  mov     ebx, eax
0x14002924a  test    eax, eax
0x14002924c  jns     short loc_140029258
0x14002924e  call    wil_UninitializeFeatureStaging
0x140029253  jmp     loc_140029488
0x140029258  call    LuafvInitializePool
0x14002925d  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140029262  call    LuafvInitializeSdTable
0x140029267  call    LuafvInitializeFileTable
0x14002926c  lea     rcx, UserListLock; PushLock
0x140029273  mov     cs:qword_14000F2E0, 0
0x14002927e  mov     cs:qword_14000F2F0, 0
0x140029289  call    cs:__imp_FltInitializePushLock
0x140029290  nop     dword ptr [rax+rax+00h]
0x140029295  lea     rax, UserList
0x14002929c  xor     edx, edx
0x14002929e  lea     rcx, UserLogoffCallback
0x1400292a5  mov     cs:qword_14000E878, rax
0x1400292ac  mov     cs:UserList, rax
0x1400292b3  call    cs:__imp_SeRegisterLogonSessionTerminatedRoutineEx
0x1400292ba  nop     dword ptr [rax+rax+00h]
0x1400292bf  lea     rcx, ScavengerSpinLock; SpinLock
0x1400292c6  call    cs:__imp_KeInitializeSpinLock
0x1400292cd  nop     dword ptr [rax+rax+00h]
0x1400292d2  lea     rax, ScavengerThreadRoutine
0x1400292d9  mov     cs:ScavengerWorkItem.Parameter, 0
0x1400292e4  lea     rbx, LuafvOperationRegistration
0x1400292eb  mov     cs:ScavengerWorkItem.WorkerRoutine, rax
0x1400292f2  mov     rcx, rbx; void *
0x1400292f5  mov     cs:ScavengerWorkItem.List.Flink, 0
0x140029300  xor     edx, edx; Val
0x140029302  mov     cs:ScavengerInitialized, 1
0x140029309  mov     r8d, 620h; Size
0x14002930f  call    memset
0x140029314  mov     rcx, rbx
0x140029317  xor     edx, edx
0x140029319  lea     eax, [rdx-14h]
0x14002931c  inc     edx
0x14002931e  mov     [rcx], al
0x140029320  lea     rax, LuafvPreRedirect
0x140029327  mov     [rcx+8], rax
0x14002932b  lea     rcx, [rcx+20h]
0x14002932f  cmp     edx, 30h ; '0'
0x140029332  jl      short loc_140029319
0x140029334  mov     byte ptr [rcx], 80h
0x140029337  lea     rdx, LuafvOperationRegistrationOverrides
0x14002933e  xor     al, al
0x140029340  movsx   rcx, al
0x140029344  mov     eax, [rdx+4]
0x140029347  lea     rdx, [rdx+20h]
0x14002934b  shl     rcx, 5
0x14002934f  mov     [rcx+rbx+284h], eax
0x140029356  mov     rax, [rdx-18h]
0x14002935a  mov     [rcx+rbx+288h], rax
0x140029362  mov     rax, [rdx-10h]
0x140029366  mov     [rcx+rbx+290h], rax
0x14002936e  mov     al, [rdx]
0x140029370  cmp     al, 80h
0x140029372  jnz     short loc_140029340
0x140029374  xor     edi, edi
0x140029376  lea     r13, LuafvDvfcbHashTable
0x14002937d  xor     ebx, ebx
0x14002937f  lea     rax, [rbx+r13]
0x140029383  lea     rcx, [r13+10h]
0x140029387  mov     [rbx+r13+8], rax
0x14002938c  add     rcx, rbx; PushLock
0x14002938f  mov     [rax], rax
0x140029392  call    cs:__imp_FltInitializePushLock
0x140029399  nop     dword ptr [rax+rax+00h]
0x14002939e  inc     rdi
0x1400293a1  add     rbx, 18h
0x1400293a5  cmp     rdi, 10h
0x1400293a9  jnz     short loc_14002937F
0x1400293ab  mov     rcx, r14
0x1400293ae  call    LuafvReadSettings
0x1400293b3  mov     ebx, eax
0x1400293b5  test    eax, eax
0x1400293b7  js      loc_140029442
0x1400293bd  mov     eax, cs:dword_14000F114
0x1400293c3  test    al, 1
0x1400293c5  jz      short loc_1400293D5
0x1400293c7  lea     rax, LuafvUnload
0x1400293ce  mov     cs:LuafvFilterRegistration.FilterUnloadCallback, rax
0x1400293d5  lea     r8, LuafvDriverData; RetFilter
0x1400293dc  mov     rcx, rsi; Driver
0x1400293df  lea     rdx, LuafvFilterRegistration; Registration
0x1400293e6  call    cs:__imp_FltRegisterFilter
0x1400293ed  nop     dword ptr [rax+rax+00h]
0x1400293f2  mov     ebx, eax
0x1400293f4  test    eax, eax
0x1400293f6  js      short loc_14002942E
0x1400293f8  call    LuafvInitializeSecurity
0x1400293fd  mov     ebx, eax
0x1400293ff  test    eax, eax
0x140029401  js      short loc_140029425
0x140029403  mov     rcx, cs:LuafvDriverData; Filter
0x14002940a  call    cs:__imp_FltStartFiltering
0x140029411  nop     dword ptr [rax+rax+00h]
0x140029416  mov     ebx, eax
0x140029418  test    eax, eax
0x14002941a  jns     short loc_140029488
0x14002941c  lea     rdx, LuafvStartFilteringFailed
0x140029423  jmp     short loc_140029449
0x140029425  lea     rdx, LuafvInitializeSecurityFailed
0x14002942c  jmp     short loc_140029449
0x14002942e  mov     cs:LuafvDriverData, 0
0x140029439  lea     rdx, LuafvFilterRegistrationFailed
0x140029440  jmp     short loc_140029449
0x140029442  lea     rdx, LuafvReadSettingsFailed; EventDescriptor
0x140029449  mov     rcx, cs:qword_14000F120; RegHandle
0x140029450  mov     r9d, 1; UserDataCount
0x140029456  mov     [rbp+var_20], eax
0x140029459  xor     r8d, r8d; ActivityId
0x14002945c  lea     rax, [rbp+var_20]
0x140029460  mov     qword ptr [rbp+var_18.Size], 4
0x140029468  mov     [rbp+var_18.Ptr], rax
0x14002946c  lea     rax, [rbp+var_18]
0x140029470  mov     [rsp+50h+UserData], rax; UserData
0x140029475  call    cs:__imp_EtwWrite
0x14002947c  nop     dword ptr [rax+rax+00h]
0x140029481  xor     ecx, ecx
0x140029483  call    LuafvUnload
0x140029488  mov     eax, ebx
0x14002948a  mov     rcx, [rbp+var_8]
0x14002948e  xor     rcx, rsp; StackCookie
0x140029491  call    __security_check_cookie
0x140029496  mov     rbx, [rsp+50h+arg_10]
0x14002949e  add     rsp, 50h
0x1400294a2  pop     r14
0x1400294a4  pop     r13
0x1400294a6  pop     rdi
0x1400294a7  pop     rsi
0x1400294a8  pop     rbp
0x1400294a9  retn
```
