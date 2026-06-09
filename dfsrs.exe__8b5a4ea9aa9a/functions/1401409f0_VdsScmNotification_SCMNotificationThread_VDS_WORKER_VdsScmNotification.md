# VdsScmNotification::SCMNotificationThread(VDS_WORKER *,VdsScmNotification *)

- ea: `0x1401409f0`
- end: `0x140140f31`
- name: `?SCMNotificationThread@VdsScmNotification@@CAKPEAUVDS_WORKER@@PEAV1@@Z`
- size: `1345`
- prototype: `unsigned int __fastcall(struct VDS_WORKER *, struct VdsScmNotification *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000c910`
- `0x14000cb00`
- `0x14000d980`
- `0x14000dcc0`
- `0x1401409f0`
- `0x140140f38`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x140140ce8`
- `KERNEL32!WaitForSingleObjectEx` at `0x140140ce8`
- `KERNEL32!GetLastError` at `0x140140aca`
- `KERNEL32!GetLastError` at `0x140140b52`
- `KERNEL32!GetLastError` at `0x140140da5`
- `KERNEL32!GetLastError` at `0x140140aca`
- `KERNEL32!GetLastError` at `0x140140b52`
- `KERNEL32!GetLastError` at `0x140140da5`
- `ADVAPI32!OpenSCManagerW` at `0x140140ab6`
- `ADVAPI32!OpenSCManagerW` at `0x140140ab6`
- `ADVAPI32!OpenServiceW` at `0x140140b3e`
- `ADVAPI32!OpenServiceW` at `0x140140d8d`
- `ADVAPI32!OpenServiceW` at `0x140140b3e`
- `ADVAPI32!OpenServiceW` at `0x140140d8d`
- `ADVAPI32!CloseServiceHandle` at `0x140140d63`
- `ADVAPI32!CloseServiceHandle` at `0x140140e9a`
- `ADVAPI32!CloseServiceHandle` at `0x140140eae`
- `ADVAPI32!CloseServiceHandle` at `0x140140d63`
- `ADVAPI32!CloseServiceHandle` at `0x140140e9a`
- `ADVAPI32!CloseServiceHandle` at `0x140140eae`
- `ADVAPI32!NotifyServiceStatusChangeW` at `0x140140cc5`
- `ADVAPI32!NotifyServiceStatusChangeW` at `0x140140cc5`

## string_xrefs

- `0x140140a56`: `VdsScmNotification::SCMNotificationThread`
- `0x140140af1`: `VdsScmNotification::SCMNotificationThread`
- `0x140140b85`: `VdsScmNotification::SCMNotificationThread`
- `0x140140c32`: `VdsScmNotification::SCMNotificationThread`
- `0x140140c83`: `VdsScmNotification::SCMNotificationThread`
- `0x140140d1b`: `VdsScmNotification::SCMNotificationThread`
- `0x140140dcc`: `VdsScmNotification::SCMNotificationThread`
- `0x140140e38`: `VdsScmNotification::SCMNotificationThread`
- `0x140140e84`: `VdsScmNotification::SCMNotificationThread`
- `0x140140aad`: `ServicesActive`
- `0x140140a83`: `Starting VDS SCMNotificationThread`
- `0x140140b12`: `Failed to open handle to SCM. Error: %?`
- `0x140140c46`: `Calling NotificationServiceStatusChange on VDS Service`
- `0x140140df5`: `Failed to open handle to VDS Service. Error: %?`
- `0x140140e64`: `Failed to register to NotifyServiceStatusChange. Error: %?`
- `0x140140c97`: `Calling NotificationServiceStatusChange for VDS Service Install`
- `0x140140edc`: `Exiting SCMNotificationThread with status %?`
- `0x140140d2d`: `State of service has changed`

## pseudocode

```c
__int64 __fastcall VdsScmNotification::SCMNotificationThread(struct VDS_WORKER *a1, HANDLE *a2)
{
  SC_HANDLE v4; // rdi
  SC_HANDLE v5; // rsi
  const wchar_t **v6; // rcx
  int v7; // ebx
  DWORD v8; // edx
  SC_HANDLE v9; // rcx
  __int64 v11; // [rsp+28h] [rbp-E0h] BYREF
  const wchar_t *v12; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+38h] [rbp-D0h]
  const wchar_t *v14; // [rsp+40h] [rbp-C8h]
  const wchar_t *v15; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B8h]
  const wchar_t *v17; // [rsp+58h] [rbp-B0h]
  _QWORD v18[3]; // [rsp+60h] [rbp-A8h] BYREF
  const wchar_t *v19; // [rsp+78h] [rbp-90h] BYREF
  int v20; // [rsp+80h] [rbp-88h]
  int v21; // [rsp+84h] [rbp-84h]
  const wchar_t *v22; // [rsp+88h] [rbp-80h]
  const wchar_t *v23; // [rsp+90h] [rbp-78h] BYREF
  int v24; // [rsp+98h] [rbp-70h]
  int v25; // [rsp+9Ch] [rbp-6Ch]
  const wchar_t *v26; // [rsp+A0h] [rbp-68h]
  const wchar_t *v27; // [rsp+A8h] [rbp-60h] BYREF
  int v28; // [rsp+B0h] [rbp-58h]
  int v29; // [rsp+B4h] [rbp-54h]
  const wchar_t *v30; // [rsp+B8h] [rbp-50h]
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+C8h] [rbp-40h] BYREF

  LODWORD(v11) = 0;
  v4 = 0;
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v19 = L"VdsScmNotification::SCMNotificationThread";
    v22 = L"VDSN";
    v20 = 821;
    v21 = 4;
    dbgobj::DbgPrint<unsigned short>(&v19, L"Starting VDS SCMNotificationThread");
  }
  v5 = OpenSCManagerW(0, L"ServicesActive", 5u);
  if ( !v5 )
  {
    LODWORD(v11) = GetLastError();
    if ( g_DebugLog )
    {
      if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v24 = 833;
        v23 = L"VdsScmNotification::SCMNotificationThread";
        v25 = 2;
        v26 = L"VDSN";
        dbgobj::DbgPrint<unsigned short,unsigned int>(&v23, L"Failed to open handle to SCM. Error: %?", &v11);
      }
    }
  }
  if ( !(_DWORD)v11 )
  {
    v4 = OpenServiceW(v5, L"VDS", 4u);
    if ( v4 )
    {
      VdsScmNotification::SetVDSServiceInstallState(a2, 2);
      goto LABEL_17;
    }
    LODWORD(v11) = GetLastError();
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v18[1] = 0x20000034DLL;
      v18[0] = L"VdsScmNotification::SCMNotificationThread";
      v6 = (const wchar_t **)v18;
      v18[2] = L"VDSN";
LABEL_45:
      dbgobj::DbgPrint<unsigned short,unsigned int>(v6, L"Failed to open handle to VDS Service. Error: %?", &v11);
    }
LABEL_46:
    VdsScmNotification::SetVDSServiceInstallState(a2, 1);
    if ( (_DWORD)v11 == 123 || (_DWORD)v11 == 1060 )
      LODWORD(v11) = 0;
LABEL_17:
    while ( !(_DWORD)v11 )
    {
      ScopedLock::ScopedLock((ScopedLock *)v18, (struct ScopedCS *)VdsScmNotification::workerCS);
      v7 = *((_DWORD *)a1 + 2);
      ScopedLock::~ScopedLock((ScopedLock *)v18);
      if ( v7 )
        break;
      memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
      pNotifyBuffer.pContext = a2;
      pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)VdsScmNotification::SCMEventCallback;
      pNotifyBuffer.dwVersion = 2;
      if ( v4 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v13 = 0x400000367LL;
          v12 = L"VdsScmNotification::SCMNotificationThread";
          v14 = L"VDSN";
          dbgobj::DbgPrint<unsigned short>(&v12, L"Calling NotificationServiceStatusChange on VDS Service");
        }
        v8 = 525;
        v9 = v4;
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v13 = 0x400000374LL;
          v12 = L"VdsScmNotification::SCMNotificationThread";
          v14 = L"VDSN";
          dbgobj::DbgPrint<unsigned short>(&v12, L"Calling NotificationServiceStatusChange for VDS Service Install");
        }
        v8 = 384;
        v9 = v5;
      }
      LODWORD(v11) = NotifyServiceStatusChangeW(v9, v8, &pNotifyBuffer);
      if ( (_DWORD)v11 )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v15 = L"VdsScmNotification::SCMNotificationThread";
          v17 = L"VDSN";
          v16 = 0x20000037CLL;
          dbgobj::DbgPrint<unsigned short,unsigned int>(
            &v15,
            L"Failed to register to NotifyServiceStatusChange. Error: %?",
            &v11);
        }
        break;
      }
      LODWORD(v11) = WaitForSingleObjectEx(a2[1], 0xFFFFFFFF, 1);
      if ( (_DWORD)v11 != 192 )
        break;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v28 = 906;
        v27 = L"VdsScmNotification::SCMNotificationThread";
        v29 = 4;
        v30 = L"VDSN";
        dbgobj::DbgPrint<unsigned short>(&v27, L"State of service has changed");
      }
      LODWORD(v11) = 0;
      if ( *((_DWORD *)a2 + 8) == 2 )
      {
        if ( !v4 )
        {
          v4 = OpenServiceW(v5, L"VDS", 4u);
          if ( !v4 )
          {
            LODWORD(v11) = GetLastError();
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
            {
              v13 = 0x2000003A6LL;
              v12 = L"VdsScmNotification::SCMNotificationThread";
              v6 = &v12;
              v14 = L"VDSN";
              goto LABEL_45;
            }
            goto LABEL_46;
          }
        }
      }
      else if ( v4 )
      {
        CloseServiceHandle(v4);
        v4 = 0;
      }
    }
  }
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v5 )
    CloseServiceHandle(v5);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v15 = L"VdsScmNotification::SCMNotificationThread";
    v16 = 0x4000003BELL;
    v17 = L"VDSN";
    dbgobj::DbgPrint<unsigned short,unsigned int>(&v15, L"Exiting SCMNotificationThread with status %?", &v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1401409f0  mov     rax, rsp
0x1401409f3  mov     [rax+8], rbx
0x1401409f7  mov     [rax+18h], rsi
0x1401409fb  mov     [rax+20h], rdi
0x1401409ff  push    rbp
0x140140a00  push    r12
0x140140a02  push    r13
0x140140a04  push    r14
0x140140a06  push    r15
0x140140a08  lea     rbp, [rax-48h]
0x140140a0c  sub     rsp, 120h
0x140140a13  mov     rax, cs:__security_cookie
0x140140a1a  xor     rax, rsp
0x140140a1d  mov     [rbp+40h+var_30], rax
0x140140a21  xor     r12d, r12d
0x140140a24  mov     r14, rdx
0x140140a27  mov     r15, rcx
0x140140a2a  mov     dword ptr [rsp+140h+var_120], r12d
0x140140a2f  xor     edx, edx; Val
0x140140a31  lea     rcx, [rbp+40h+pNotifyBuffer]; void *
0x140140a35  mov     esi, r12d
0x140140a38  mov     edi, r12d
0x140140a3b  lea     r8d, [r12+50h]; Size
0x140140a40  call    memset_0
0x140140a45  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140140a4c  lea     ebx, [r12+2]
0x140140a51  lea     r13d, [r12+4]
0x140140a56  lea     rcx, aVdsscmnotifica_3; "VdsScmNotification::SCMNotificationThre"...
0x140140a5d  lea     rdx, aVdsn; "VDSN"
0x140140a64  test    rax, rax
0x140140a67  jz      short loc_140140AA7
0x140140a69  cmp     [rax+40h], r12d
0x140140a6d  jz      short loc_140140AA7
0x140140a6f  cmp     [rax+38h], r13d
0x140140a73  jl      short loc_140140AA7
0x140140a75  mov     [rsp+140h+var_D0], rcx
0x140140a7a  lea     rcx, [rsp+140h+var_D0]
0x140140a7f  mov     [rbp+40h+var_C0], rdx
0x140140a83  lea     rdx, aStartingVdsScm; "Starting VDS SCMNotificationThread"
0x140140a8a  mov     [rsp+140h+var_C8], 335h
0x140140a92  mov     [rsp+140h+var_C4], r13d
0x140140a97  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140140a9c  cmp     dword ptr [rsp+140h+var_120], r12d
0x140140aa1  jnz     loc_140140E84
0x140140aa7  mov     r8d, 5; dwDesiredAccess
0x140140aad  lea     rdx, DatabaseName; "ServicesActive"
0x140140ab4  xor     ecx, ecx; lpMachineName
0x140140ab6  call    cs:__imp_OpenSCManagerW
0x140140abd  nop     dword ptr [rax+rax+00h]
0x140140ac2  mov     rsi, rax
0x140140ac5  test    rax, rax
0x140140ac8  jnz     short loc_140140B26
0x140140aca  call    cs:__imp_GetLastError
0x140140ad1  nop     dword ptr [rax+rax+00h]
0x140140ad6  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140140add  mov     dword ptr [rsp+140h+var_120], eax
0x140140ae1  test    rcx, rcx
0x140140ae4  jz      short loc_140140B26
0x140140ae6  cmp     [rcx+40h], r12d
0x140140aea  jz      short loc_140140B26
0x140140aec  cmp     [rcx+38h], ebx
0x140140aef  jl      short loc_140140B26
0x140140af1  lea     rax, aVdsscmnotifica_3; "VdsScmNotification::SCMNotificationThre"...
0x140140af8  mov     [rbp+40h+var_B0], 341h
0x140140aff  mov     [rbp+40h+var_B8], rax
0x140140b03  lea     r8, [rsp+140h+var_120]
0x140140b08  lea     rax, aVdsn; "VDSN"
0x140140b0f  mov     [rbp+40h+var_AC], ebx
0x140140b12  lea     rdx, aFailedToOpenHa_0; "Failed to open handle to SCM. Error: %?"
0x140140b19  mov     [rbp+40h+var_A8], rax
0x140140b1d  lea     rcx, [rbp+40h+var_B8]
0x140140b21  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140140b26  cmp     dword ptr [rsp+140h+var_120], r12d
0x140140b2b  jnz     loc_140140E84
0x140140b31  mov     r8d, r13d; dwDesiredAccess
0x140140b34  lea     rdx, aVds; "VDS"
0x140140b3b  mov     rcx, rsi; hSCManager
0x140140b3e  call    cs:__imp_OpenServiceW
0x140140b45  nop     dword ptr [rax+rax+00h]
0x140140b4a  mov     rdi, rax
0x140140b4d  test    rax, rax
0x140140b50  jnz     short loc_140140BB3
0x140140b52  call    cs:__imp_GetLastError
0x140140b59  nop     dword ptr [rax+rax+00h]
0x140140b5e  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140140b65  mov     dword ptr [rsp+140h+var_120], eax
0x140140b69  test    rcx, rcx
0x140140b6c  jz      loc_140140E06
0x140140b72  cmp     [rcx+40h], r12d
0x140140b76  jz      loc_140140E06
0x140140b7c  cmp     [rcx+38h], ebx
0x140140b7f  jl      loc_140140E06
0x140140b85  lea     rax, aVdsscmnotifica_3; "VdsScmNotification::SCMNotificationThre"...
0x140140b8c  mov     dword ptr [rsp+140h+var_E0], 34Dh
0x140140b94  mov     qword ptr [rsp+140h+var_E8], rax
0x140140b99  lea     rcx, [rsp+140h+var_E8]
0x140140b9e  lea     rax, aVdsn; "VDSN"
0x140140ba5  mov     dword ptr [rsp+140h+var_E0+4], ebx
0x140140ba9  mov     [rsp+140h+var_D8], rax
0x140140bae  jmp     loc_140140DF5
0x140140bb3  mov     edx, ebx
0x140140bb5  mov     rcx, r14
0x140140bb8  call    ?SetVDSServiceInstallState@VdsScmNotification@@AEAAXW4SvcInstallState@1@@Z; VdsScmNotification::SetVDSServiceInstallState(VdsScmNotification::SvcInstallState)
0x140140bbd  cmp     dword ptr [rsp+140h+var_120], r12d
0x140140bc2  jnz     loc_140140E84
0x140140bc8  lea     rdx, ?workerCS@VdsScmNotification@@0VScopedCS@@A; struct ScopedCS *
0x140140bcf  lea     rcx, [rsp+140h+var_E8]; this
0x140140bd4  call    ??0ScopedLock@@QEAA@AEAVScopedCS@@@Z; ScopedLock::ScopedLock(ScopedCS &)
0x140140bd9  mov     ebx, [r15+8]
0x140140bdd  lea     rcx, [rsp+140h+var_E8]; this
0x140140be2  call    ??1ScopedLock@@QEAA@XZ; ScopedLock::~ScopedLock(void)
0x140140be7  test    ebx, ebx
0x140140be9  jnz     loc_140140E84
0x140140bef  xor     edx, edx; Val
0x140140bf1  lea     r8d, [rbx+50h]; Size
0x140140bf5  lea     rcx, [rbp+40h+pNotifyBuffer]; void *
0x140140bf9  call    memset_0
0x140140bfe  mov     [rbp+40h+pNotifyBuffer.pContext], r14
0x140140c02  lea     rax, ?SCMEventCallback@VdsScmNotification@@CAXPEAX@Z; VdsScmNotification::SCMEventCallback(void *)
0x140140c09  mov     [rbp+40h+pNotifyBuffer.pfnNotifyCallback], rax
0x140140c0d  mov     ebx, 2
0x140140c12  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140140c19  mov     [rbp+40h+pNotifyBuffer.dwVersion], ebx
0x140140c1c  test    rdi, rdi
0x140140c1f  jz      short loc_140140C72
0x140140c21  test    rax, rax
0x140140c24  jz      short loc_140140C68
0x140140c26  cmp     [rax+40h], r12d
0x140140c2a  jz      short loc_140140C68
0x140140c2c  cmp     [rax+38h], r13d
0x140140c30  jl      short loc_140140C68
0x140140c32  lea     rax, aVdsscmnotifica_3; "VdsScmNotification::SCMNotificationThre"...
0x140140c39  mov     dword ptr [rsp+140h+var_110], 367h
0x140140c41  mov     [rsp+140h+var_118], rax
0x140140c46  lea     rdx, aCallingNotific_0; "Calling NotificationServiceStatusChange"...
0x140140c4d  lea     rax, aVdsn; "VDSN"
0x140140c54  mov     dword ptr [rsp+140h+var_110+4], r13d
0x140140c59  lea     rcx, [rsp+140h+var_118]
0x140140c5e  mov     [rsp+140h+var_108], rax
0x140140c63  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140140c68  mov     edx, 20Dh
0x140140c6d  mov     rcx, rdi
0x140140c70  jmp     short loc_140140CC1
0x140140c72  test    rax, rax
0x140140c75  jz      short loc_140140CB9
0x140140c77  cmp     [rax+40h], r12d
0x140140c7b  jz      short loc_140140CB9
0x140140c7d  cmp     [rax+38h], r13d
0x140140c81  jl      short loc_140140CB9
0x140140c83  lea     rax, aVdsscmnotifica_3; "VdsScmNotification::SCMNotificationThre"...
0x140140c8a  mov     dword ptr [rsp+140h+var_110], 374h
0x140140c92  mov     [rsp+140h+var_118], rax
0x140140c97  lea     rdx, aCallingNotific; "Calling NotificationServiceStatusChange"...
0x140140c9e  lea     rax, aVdsn; "VDSN"
0x140140ca5  mov     dword ptr [rsp+140h+var_110+4], r13d
0x140140caa  lea     rcx, [rsp+140h+var_118]
0x140140caf  mov     [rsp+140h+var_108], rax
0x140140cb4  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140140cb9  mov     edx, 180h; dwNotifyMask
0x140140cbe  mov     rcx, rsi; hService
0x140140cc1  lea     r8, [rbp+40h+pNotifyBuffer]; pNotifyBuffer
0x140140cc5  call    cs:__imp_NotifyServiceStatusChangeW
0x140140ccc  nop     dword ptr [rax+rax+00h]
0x140140cd1  mov     dword ptr [rsp+140h+var_120], eax
0x140140cd5  test    eax, eax
0x140140cd7  jnz     loc_140140E31
0x140140cdd  mov     rcx, [r14+8]; hHandle
0x140140ce1  lea     r8d, [rax+1]; bAlertable
0x140140ce5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140140ce8  call    cs:__imp_WaitForSingleObjectEx
0x140140cef  nop     dword ptr [rax+rax+00h]
0x140140cf4  mov     dword ptr [rsp+140h+var_120], eax
0x140140cf8  cmp     eax, 0C0h
0x140140cfd  jnz     loc_140140E84
0x140140d03  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140140d0a  test    rcx, rcx
0x140140d0d  jz      short loc_140140D4C
0x140140d0f  cmp     [rcx+40h], r12d
0x140140d13  jz      short loc_140140D4C
0x140140d15  cmp     [rcx+38h], r13d
0x140140d19  jl      short loc_140140D4C
0x140140d1b  lea     rax, aVdsscmnotifica_3; "VdsScmNotification::SCMNotificationThre"...
0x140140d22  mov     [rbp+40h+var_98], 38Ah
0x140140d29  mov     [rbp+40h+var_A0], rax
0x140140d2d  lea     rdx, aStateOfService; "State of service has changed"
0x140140d34  lea     rax, aVdsn; "VDSN"
0x140140d3b  mov     [rbp+40h+var_94], r13d
0x140140d3f  lea     rcx, [rbp+40h+var_A0]
0x140140d43  mov     [rbp+40h+var_90], rax
0x140140d47  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140140d4c  mov     dword ptr [rsp+140h+var_120], r12d
0x140140d51  cmp     [r14+20h], ebx
0x140140d55  jz      short loc_140140D77
0x140140d57  test    rdi, rdi
0x140140d5a  jz      loc_140140BBD
0x140140d60  mov     rcx, rdi; hSCObject
0x140140d63  call    cs:__imp_CloseServiceHandle
0x140140d6a  nop     dword ptr [rax+rax+00h]
0x140140d6f  mov     rdi, r12
0x140140d72  jmp     loc_140140BBD
0x140140d77  test    rdi, rdi
0x140140d7a  jnz     loc_140140BBD
0x140140d80  mov     r8d, r13d; dwDesiredAccess
0x140140d83  lea     rdx, aVds; "VDS"
0x140140d8a  mov     rcx, rsi; hSCManager
0x140140d8d  call    cs:__imp_OpenServiceW
0x140140d94  nop     dword ptr [rax+rax+00h]
0x140140d99  mov     rdi, rax
0x140140d9c  test    rax, rax
0x140140d9f  jnz     loc_140140BBD
0x140140da5  call    cs:__imp_GetLastError
0x140140dac  nop     dword ptr [rax+rax+00h]
0x140140db1  mov     dword ptr [rsp+140h+var_120], eax
0x140140db5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140140dbc  test    rax, rax
0x140140dbf  jz      short loc_140140E06
0x140140dc1  cmp     [rax+40h], r12d
0x140140dc5  jz      short loc_140140E06
0x140140dc7  cmp     [rax+38h], ebx
0x140140dca  jl      short loc_140140E06
0x140140dcc  lea     rax, aVdsscmnotifica_3; "VdsScmNotification::SCMNotificationThre"...
0x140140dd3  mov     dword ptr [rsp+140h+var_110], 3A6h
0x140140ddb  mov     [rsp+140h+var_118], rax
0x140140de0  lea     rcx, [rsp+140h+var_118]
0x140140de5  lea     rax, aVdsn; "VDSN"
0x140140dec  mov     dword ptr [rsp+140h+var_110+4], ebx
0x140140df0  mov     [rsp+140h+var_108], rax
0x140140df5  lea     rdx, aFailedToOpenHa; "Failed to open handle to VDS Service. E"...
0x140140dfc  lea     r8, [rsp+140h+var_120]
0x140140e01  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140140e06  mov     edx, 1
0x140140e0b  mov     rcx, r14
0x140140e0e  call    ?SetVDSServiceInstallState@VdsScmNotification@@AEAAXW4SvcInstallState@1@@Z; VdsScmNotification::SetVDSServiceInstallState(VdsScmNotification::SvcInstallState)
0x140140e13  mov     eax, dword ptr [rsp+140h+var_120]
0x140140e17  cmp     eax, 7Bh ; '{'
0x140140e1a  jz      short loc_140140E27
0x140140e1c  cmp     eax, 424h
0x140140e21  jnz     loc_140140BBD
0x140140e27  mov     dword ptr [rsp+140h+var_120], r12d
0x140140e2c  jmp     loc_140140BBD
0x140140e31  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140140e38  lea     r14, aVdsscmnotifica_3; "VdsScmNotification::SCMNotificationThre"...
0x140140e3f  test    rcx, rcx
0x140140e42  jz      short loc_140140E8B
0x140140e44  cmp     [rcx+40h], r12d
0x140140e48  jz      short loc_140140E8B
0x140140e4a  cmp     [rcx+38h], ebx
0x140140e4d  jl      short loc_140140E8B
0x140140e4f  mov     dword ptr [rsp+140h+var_F8+4], ebx
0x140140e53  lea     r8, [rsp+140h+var_120]
0x140140e58  lea     rbx, aVdsn; "VDSN"
0x140140e5f  mov     [rsp+140h+var_100], r14
0x140140e64  lea     rdx, aFailedToRegist_3; "Failed to register to NotifyServiceStat"...
0x140140e6b  mov     [rsp+140h+var_F0], rbx
0x140140e70  lea     rcx, [rsp+140h+var_100]
0x140140e75  mov     dword ptr [rsp+140h+var_F8], 37Ch
0x140140e7d  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140140e82  jmp     short loc_140140E92
0x140140e84  lea     r14, aVdsscmnotifica_3; "VdsScmNotification::SCMNotificationThre"...
0x140140e8b  lea     rbx, aVdsn; "VDSN"
0x140140e92  test    rdi, rdi
0x140140e95  jz      short loc_140140EA6
0x140140e97  mov     rcx, rdi; hSCObject
0x140140e9a  call    cs:__imp_CloseServiceHandle
0x140140ea1  nop     dword ptr [rax+rax+00h]
0x140140ea6  test    rsi, rsi
0x140140ea9  jz      short loc_140140EBA
0x140140eab  mov     rcx, rsi; hSCObject
0x140140eae  call    cs:__imp_CloseServiceHandle
0x140140eb5  nop     dword ptr [rax+rax+00h]
0x140140eba  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140140ec1  test    rcx, rcx
0x140140ec4  jz      short loc_140140EFF
0x140140ec6  cmp     [rcx+40h], r12d
0x140140eca  jz      short loc_140140EFF
0x140140ecc  cmp     [rcx+38h], r13d
0x140140ed0  jl      short loc_140140EFF
0x140140ed2  lea     r8, [rsp+140h+var_120]
0x140140ed7  mov     [rsp+140h+var_100], r14
0x140140edc  lea     rdx, aExitingScmnoti; "Exiting SCMNotificationThread with stat"...
0x140140ee3  mov     dword ptr [rsp+140h+var_F8], 3BEh
0x140140eeb  lea     rcx, [rsp+140h+var_100]
0x140140ef0  mov     dword ptr [rsp+140h+var_F8+4], r13d
0x140140ef5  mov     [rsp+140h+var_F0], rbx
0x140140efa  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140140eff  mov     eax, dword ptr [rsp+140h+var_120]
0x140140f03  mov     rcx, [rbp+40h+var_30]
0x140140f07  xor     rcx, rsp; StackCookie
0x140140f0a  call    __security_check_cookie
0x140140f0f  lea     r11, [rsp+140h+var_20]
0x140140f17  mov     rbx, [r11+30h]
0x140140f1b  mov     rsi, [r11+40h]
0x140140f1f  mov     rdi, [r11+48h]
0x140140f23  mov     rsp, r11
0x140140f26  pop     r15
0x140140f28  pop     r14
0x140140f2a  pop     r13
0x140140f2c  pop     r12
0x140140f2e  pop     rbp
0x140140f2f  retn
  ... truncated ...
```
