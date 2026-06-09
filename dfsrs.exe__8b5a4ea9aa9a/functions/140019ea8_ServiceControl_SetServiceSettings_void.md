# ServiceControl::SetServiceSettings(void)

- ea: `0x140019ea8`
- end: `0x14001a2d3`
- name: `?SetServiceSettings@ServiceControl@@IEAAPEAVFrsStatus@@XZ`
- size: `1067`
- prototype: `struct FrsStatus *__fastcall(ServiceControl *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140010518`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x14000cdc0`
- `0x1400191fc`
- `0x14001957c`
- `0x140019ea8`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140019fee`
- `KERNEL32!GetLastError` at `0x14001a186`
- `KERNEL32!GetLastError` at `0x140019fee`
- `KERNEL32!GetLastError` at `0x14001a186`
- `KERNEL32!GetCurrentThreadId` at `0x140019f6d`
- `KERNEL32!GetCurrentThreadId` at `0x14001a02e`
- `KERNEL32!GetCurrentThreadId` at `0x14001a178`
- `KERNEL32!GetCurrentThreadId` at `0x14001a1ae`
- `KERNEL32!GetCurrentThreadId` at `0x14001a264`
- `KERNEL32!GetCurrentThreadId` at `0x140019f6d`
- `KERNEL32!GetCurrentThreadId` at `0x14001a02e`
- `KERNEL32!GetCurrentThreadId` at `0x14001a178`
- `KERNEL32!GetCurrentThreadId` at `0x14001a1ae`
- `KERNEL32!GetCurrentThreadId` at `0x14001a264`
- `ADVAPI32!ChangeServiceConfig2W` at `0x14001a164`
- `ADVAPI32!ChangeServiceConfig2W` at `0x14001a164`
- `ADVAPI32!CloseServiceHandle` at `0x14001a1fa`
- `ADVAPI32!CloseServiceHandle` at `0x14001a20f`
- `ADVAPI32!CloseServiceHandle` at `0x14001a1fa`
- `ADVAPI32!CloseServiceHandle` at `0x14001a20f`
- `ADVAPI32!QueryServiceConfig2W` at `0x140019fda`
- `ADVAPI32!QueryServiceConfig2W` at `0x140019fda`

## string_xrefs

- `0x140019f7e`: `base\fs\remotefs\frs\src\main\servicecontrol.cpp`
- `0x14001a03f`: `base\fs\remotefs\frs\src\main\servicecontrol.cpp`
- `0x14001a1d0`: `base\fs\remotefs\frs\src\main\servicecontrol.cpp`
- `0x14001a283`: `base\fs\remotefs\frs\src\main\servicecontrol.cpp`
- `0x140019ee5`: `ServiceControl::SetServiceSettings`
- `0x140019f17`: `Setting failure action for service to be restarted`
- `0x140019f41`: `ServiceControl::SetServiceSettings`
- `0x14001a050`: `ServiceControl::SetServiceSettings`
- `0x14001a074`: `ServiceControl::SetServiceSettings`
- `0x14001a0c6`: `ServiceControl::SetServiceSettings`
- `0x14001a197`: `ServiceControl::SetServiceSettings`
- `0x14001a0a7`: `Restart actions for service are already set`
- `0x14001a12e`: `Setting service action restarts to %?`

## pseudocode

```c
struct FrsStatus *__fastcall ServiceControl::SetServiceSettings(
        ServiceControl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int64 v3; // rbp
  LPCRITICAL_SECTION v4; // rax
  __int64 v5; // rdi
  unsigned int *v7; // rbx
  SC_HANDLE v8; // rsi
  unsigned int v9; // esi
  DWORD v10; // eax
  __int64 v11; // rax
  DWORD v12; // r14d
  DWORD v13; // eax
  __int64 i; // rax
  DWORD v15; // ebx
  __int64 LastError; // rdx
  DWORD CurrentThreadId; // eax
  SC_HANDLE v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  SC_HANDLE hService; // [rsp+90h] [rbp+0h] BYREF

  v3 = (unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL;
  v4 = g_DebugLog;
  v5 = 0;
  *(_DWORD *)(v3 + 32) = 0;
  *(_QWORD *)(v3 + 64) = 0;
  v7 = 0;
  *(_QWORD *)v3 = 0;
  v8 = 0;
  if ( v4 && LODWORD(v4[1].LockSemaphore) && SLODWORD(v4[1].OwningThread) >= 5 )
  {
    *(_QWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 8) = L"ServiceControl::SetServiceSettings";
    *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = 371;
    *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = 5;
    *(_QWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = L"SCNT";
    dbgobj::DbgPrint<unsigned short>(v3 + 8, L"Setting failure action for service to be restarted");
  }
  if ( (unsigned __int64)(*((_QWORD *)this + 4) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = FrsStatusList::PushNewError(
            "base\\fs\\remotefs\\frs\\src\\main\\servicecontrol.cpp",
            6,
            0,
            1,
            "base\\fs\\remotefs\\frs\\src\\main\\servicecontrol.cpp",
            "ServiceControl::SetServiceSettings",
            374,
            CurrentThreadId,
            0);
    goto LABEL_31;
  }
  v9 = ServiceControl::OpenServiceHandles(
         this,
         a2,
         a3,
         (struct SC_HANDLE__ **)(v3 + 64),
         (struct SC_HANDLE__ **)((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL));
  if ( v9 )
  {
    v10 = GetCurrentThreadId();
    v11 = FrsStatusList::PushNewError(
            "base\\fs\\remotefs\\frs\\src\\main\\servicecontrol.cpp",
            v9,
            0,
            1,
            "base\\fs\\remotefs\\frs\\src\\main\\servicecontrol.cpp",
            "ServiceControl::SetServiceSettings",
            381,
            v10,
            0);
    v8 = *(SC_HANDLE *)v3;
LABEL_31:
    v7 = (unsigned int *)v11;
    goto LABEL_32;
  }
  v8 = *(SC_HANDLE *)v3;
  if ( QueryServiceConfig2W(*(SC_HANDLE *)v3, 2u, (LPBYTE)(v3 + 128), 0x128u, (LPDWORD)(v3 + 32)) )
  {
    if ( *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) == 32 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = 408;
        goto LABEL_20;
      }
    }
    else
    {
      for ( i = 0; i < 32; ++i )
      {
        *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8 + 8 * i) = 1;
        *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0xAC + 8 * i) = 1800000;
      }
      *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 32;
      *(_QWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = ((unsigned __int64)&hService
                                                                                 & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                + 168;
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        *(_QWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = L"ServiceControl::SetServiceSettings";
        *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 426;
        *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x34) = 4;
        *(_QWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = L"SCNT";
        *(_DWORD *)v3 = 32;
        dbgobj::DbgPrint<unsigned short,int>(
          v3 + 40,
          L"Setting service action restarts to %?",
          (unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL);
      }
      if ( !ChangeServiceConfig2W(v8, 2u, (LPVOID)(v3 + 128)) )
      {
        v15 = GetCurrentThreadId();
        LastError = GetLastError();
        v11 = FrsStatusList::PushNewError(
                "base\\fs\\remotefs\\frs\\src\\main\\servicecontrol.cpp",
                LastError,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\main\\servicecontrol.cpp",
                "ServiceControl::SetServiceSettings",
                432,
                v15,
                0);
        goto LABEL_31;
      }
    }
  }
  else
  {
    v12 = GetLastError();
    if ( v12 != 122 )
    {
      v13 = GetCurrentThreadId();
      v11 = FrsStatusList::PushNewError(
              "base\\fs\\remotefs\\frs\\src\\main\\servicecontrol.cpp",
              v12,
              0,
              1,
              "base\\fs\\remotefs\\frs\\src\\main\\servicecontrol.cpp",
              "ServiceControl::SetServiceSettings",
              398,
              v13,
              0);
      goto LABEL_31;
    }
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = 396;
LABEL_20:
      *(_QWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 8) = L"ServiceControl::SetServiceSettings";
      *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = 4;
      *(_QWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = L"SCNT";
      dbgobj::DbgPrint<unsigned short>(v3 + 8, L"Restart actions for service are already set");
    }
  }
LABEL_32:
  if ( v8 )
    CloseServiceHandle(v8);
  v18 = *(SC_HANDLE *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
  if ( v18 )
    CloseServiceHandle(v18);
  if ( v7 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      *(_QWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = L"ServiceControl::SetServiceSettings";
      *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 445;
      *(_DWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x34) = 3;
      *(_QWORD *)(((unsigned __int64)&hService & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = L"SCNT";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(v3 + 40, L"Failed to set failure action to restart.  Error:%?", v7);
    }
    v19 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v20,
                                 v7[1],
                                 v7[2],
                                 *v7,
                                 "base\\fs\\remotefs\\frs\\src\\main\\servicecontrol.cpp",
                                 "ServiceControl::SetServiceSettings",
                                 448,
                                 v19,
                                 v7);
  }
  return (struct FrsStatus *)v5;
}

```

## disassembly

```asm
0x140019ea8  mov     [rsp-8+arg_8], rbx
0x140019ead  mov     [rsp-8+arg_10], rsi
0x140019eb2  push    rbp
0x140019eb3  push    rdi
0x140019eb4  push    r12
0x140019eb6  push    r13
0x140019eb8  push    r14
0x140019eba  sub     rsp, 260h
0x140019ec1  lea     rbp, [rsp+90h]
0x140019ec9  and     rbp, 0FFFFFFFFFFFFFFC0h
0x140019ecd  mov     rax, cs:__security_cookie
0x140019ed4  xor     rax, rsp
0x140019ed7  mov     [rbp+1F0h+var_30], rax
0x140019ede  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140019ee5  lea     r12, aServicecontrol_11; "ServiceControl::SetServiceSettings"
0x140019eec  xor     edi, edi
0x140019eee  lea     r13, aScnt; "SCNT"
0x140019ef5  mov     [rbp+1F0h+var_1D0], edi
0x140019ef8  mov     r14, rcx
0x140019efb  mov     [rbp+1F0h+hSCObject], rdi
0x140019eff  mov     ebx, edi
0x140019f01  mov     [rbp+1F0h+hService], rdi
0x140019f05  mov     esi, edi
0x140019f07  test    rax, rax
0x140019f0a  jz      short loc_140019F3D
0x140019f0c  cmp     [rax+40h], edi
0x140019f0f  jz      short loc_140019F3D
0x140019f11  cmp     dword ptr [rax+38h], 5
0x140019f15  jl      short loc_140019F3D
0x140019f17  lea     rdx, aSettingFailure; "Setting failure action for service to b"...
0x140019f1e  mov     [rbp+1F0h+var_1E8], r12
0x140019f22  lea     rcx, [rbp+1F0h+var_1E8]
0x140019f26  mov     [rbp+1F0h+var_1E0], 173h
0x140019f2d  mov     [rbp+1F0h+var_1DC], 5
0x140019f34  mov     [rbp+1F0h+var_1D8], r13
0x140019f38  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140019f3d  mov     rax, [r14+20h]
0x140019f41  lea     r14, aServicecontrol_4; "ServiceControl::SetServiceSettings"
0x140019f48  dec     rax
0x140019f4b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019f4f  ja      loc_14001A1AE
0x140019f55  lea     rax, [rbp+1F0h+hService]
0x140019f59  lea     r9, [rbp+1F0h+hSCObject]; struct SC_HANDLE__ **
0x140019f5d  mov     [rsp+280h+pcbBytesNeeded], rax; struct SC_HANDLE__ **
0x140019f62  call    ?OpenServiceHandles@ServiceControl@@IEAAKPEBG0AEAPEAUSC_HANDLE__@@1@Z; ServiceControl::OpenServiceHandles(ushort const *,ushort const *,SC_HANDLE__ * &,SC_HANDLE__ * &)
0x140019f67  mov     esi, eax
0x140019f69  test    eax, eax
0x140019f6b  jz      short loc_140019FB4
0x140019f6d  call    cs:__imp_GetCurrentThreadId
0x140019f74  nop     dword ptr [rax+rax+00h]
0x140019f79  mov     [rsp+280h+var_240], rdi
0x140019f7e  lea     rcx, aBaseFsRemotefs_81; "base\\fs\\remotefs\\frs\\src\\main\\ser"...
0x140019f85  mov     [rsp+280h+var_248], eax
0x140019f89  mov     r9d, 1
0x140019f8f  mov     [rsp+280h+var_250], 17Dh
0x140019f97  xor     r8d, r8d
0x140019f9a  mov     [rsp+280h+var_258], r14
0x140019f9f  mov     edx, esi
0x140019fa1  mov     [rsp+280h+pcbBytesNeeded], rcx
0x140019fa6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140019fab  mov     rsi, [rbp+1F0h+hService]
0x140019faf  jmp     loc_14001A1EF
0x140019fb4  mov     rsi, [rbp+1F0h+hService]
0x140019fb8  lea     rax, [rbp+1F0h+var_1D0]
0x140019fbc  mov     r14d, 2
0x140019fc2  mov     [rsp+280h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140019fc7  mov     edx, r14d; dwInfoLevel
0x140019fca  lea     r8, [rbp+1F0h+Buffer]; lpBuffer
0x140019fd1  mov     rcx, rsi; hService
0x140019fd4  mov     r9d, 128h; cbBufSize
0x140019fda  call    cs:__imp_QueryServiceConfig2W
0x140019fe1  nop     dword ptr [rax+rax+00h]
0x140019fe6  test    eax, eax
0x140019fe8  jnz     loc_14001A080
0x140019fee  call    cs:__imp_GetLastError
0x140019ff5  nop     dword ptr [rax+rax+00h]
0x140019ffa  mov     r14d, eax
0x140019ffd  cmp     eax, 7Ah ; 'z'
0x14001a000  jnz     short loc_14001A02E
0x14001a002  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001a009  test    rax, rax
0x14001a00c  jz      loc_14001A0C6
0x14001a012  cmp     [rax+40h], edi
0x14001a015  jz      loc_14001A0C6
0x14001a01b  cmp     dword ptr [rax+38h], 4
0x14001a01f  jl      loc_14001A0C6
0x14001a025  mov     [rbp+1F0h+var_1E0], 18Ch
0x14001a02c  jmp     short loc_14001A0A7
0x14001a02e  call    cs:__imp_GetCurrentThreadId
0x14001a035  nop     dword ptr [rax+rax+00h]
0x14001a03a  mov     [rsp+280h+var_240], rdi
0x14001a03f  lea     rcx, aBaseFsRemotefs_81; "base\\fs\\remotefs\\frs\\src\\main\\ser"...
0x14001a046  mov     [rsp+280h+var_248], eax
0x14001a04a  mov     r9d, 1
0x14001a050  lea     rax, aServicecontrol_4; "ServiceControl::SetServiceSettings"
0x14001a057  mov     [rsp+280h+var_250], 18Eh
0x14001a05f  mov     [rsp+280h+var_258], rax
0x14001a064  xor     r8d, r8d
0x14001a067  mov     edx, r14d
0x14001a06a  mov     [rsp+280h+pcbBytesNeeded], rcx
0x14001a06f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14001a074  lea     r14, aServicecontrol_4; "ServiceControl::SetServiceSettings"
0x14001a07b  jmp     loc_14001A1EF
0x14001a080  cmp     [rbp+1F0h+var_158], 20h ; ' '
0x14001a087  jnz     short loc_14001A0D2
0x14001a089  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001a090  test    rax, rax
0x14001a093  jz      short loc_14001A0C6
0x14001a095  cmp     [rax+40h], edi
0x14001a098  jz      short loc_14001A0C6
0x14001a09a  cmp     dword ptr [rax+38h], 4
0x14001a09e  jl      short loc_14001A0C6
0x14001a0a0  mov     [rbp+1F0h+var_1E0], 198h
0x14001a0a7  lea     rdx, aRestartActions; "Restart actions for service are already"...
0x14001a0ae  mov     [rbp+1F0h+var_1E8], r12
0x14001a0b2  lea     rcx, [rbp+1F0h+var_1E8]
0x14001a0b6  mov     [rbp+1F0h+var_1DC], 4
0x14001a0bd  mov     [rbp+1F0h+var_1D8], r13
0x14001a0c1  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14001a0c6  lea     r14, aServicecontrol_4; "ServiceControl::SetServiceSettings"
0x14001a0cd  jmp     loc_14001A1F2
0x14001a0d2  mov     rax, rdi
0x14001a0d5  lea     rcx, [rbp+1F0h+var_148]
0x14001a0dc  mov     dword ptr [rcx+rax*8], 1
0x14001a0e3  mov     [rbp+rax*8+1F0h+var_144], 1B7740h
0x14001a0ee  inc     rax
0x14001a0f1  cmp     rax, 20h ; ' '
0x14001a0f5  jl      short loc_14001A0DC
0x14001a0f7  lea     rax, [rbp+1F0h+var_148]
0x14001a0fe  mov     [rbp+1F0h+var_158], 20h ; ' '
0x14001a108  mov     [rbp+1F0h+var_150], rax
0x14001a10f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001a116  test    rax, rax
0x14001a119  jz      short loc_14001A157
0x14001a11b  cmp     [rax+40h], edi
0x14001a11e  jz      short loc_14001A157
0x14001a120  cmp     dword ptr [rax+38h], 4
0x14001a124  jl      short loc_14001A157
0x14001a126  lea     r8, [rbp+1F0h+hService]
0x14001a12a  mov     [rbp+1F0h+var_1C8], r12
0x14001a12e  lea     rdx, aSettingService; "Setting service action restarts to %?"
0x14001a135  mov     [rbp+1F0h+var_1C0], 1AAh
0x14001a13c  lea     rcx, [rbp+1F0h+var_1C8]
0x14001a140  mov     [rbp+1F0h+var_1BC], 4
0x14001a147  mov     [rbp+1F0h+var_1B8], r13
0x14001a14b  mov     dword ptr [rbp+1F0h+hService], 20h ; ' '
0x14001a152  call    ??$DbgPrint@GH@dbgobj@@QEAA_KPEBGAEBH@Z; dbgobj::DbgPrint<ushort,int>(ushort const *,int const &)
0x14001a157  lea     r8, [rbp+1F0h+Buffer]; lpInfo
0x14001a15e  mov     edx, r14d; dwInfoLevel
0x14001a161  mov     rcx, rsi; hService
0x14001a164  call    cs:__imp_ChangeServiceConfig2W
0x14001a16b  nop     dword ptr [rax+rax+00h]
0x14001a170  test    eax, eax
0x14001a172  jnz     loc_14001A0C6
0x14001a178  call    cs:__imp_GetCurrentThreadId
0x14001a17f  nop     dword ptr [rax+rax+00h]
0x14001a184  mov     ebx, eax
0x14001a186  call    cs:__imp_GetLastError
0x14001a18d  nop     dword ptr [rax+rax+00h]
0x14001a192  mov     [rsp+280h+var_240], rdi
0x14001a197  lea     r14, aServicecontrol_4; "ServiceControl::SetServiceSettings"
0x14001a19e  mov     [rsp+280h+var_248], ebx
0x14001a1a2  mov     edx, eax
0x14001a1a4  mov     [rsp+280h+var_250], 1B0h
0x14001a1ac  jmp     short loc_14001A1D0
0x14001a1ae  call    cs:__imp_GetCurrentThreadId
0x14001a1b5  nop     dword ptr [rax+rax+00h]
0x14001a1ba  mov     [rsp+280h+var_240], rdi
0x14001a1bf  mov     edx, 6
0x14001a1c4  mov     [rsp+280h+var_248], eax
0x14001a1c8  mov     [rsp+280h+var_250], 176h
0x14001a1d0  lea     rcx, aBaseFsRemotefs_81; "base\\fs\\remotefs\\frs\\src\\main\\ser"...
0x14001a1d7  mov     [rsp+280h+var_258], r14
0x14001a1dc  mov     r9d, 1
0x14001a1e2  mov     [rsp+280h+pcbBytesNeeded], rcx
0x14001a1e7  xor     r8d, r8d
0x14001a1ea  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14001a1ef  mov     rbx, rax
0x14001a1f2  test    rsi, rsi
0x14001a1f5  jz      short loc_14001A206
0x14001a1f7  mov     rcx, rsi; hSCObject
0x14001a1fa  call    cs:__imp_CloseServiceHandle
0x14001a201  nop     dword ptr [rax+rax+00h]
0x14001a206  mov     rcx, [rbp+1F0h+hSCObject]; hSCObject
0x14001a20a  test    rcx, rcx
0x14001a20d  jz      short loc_14001A21B
0x14001a20f  call    cs:__imp_CloseServiceHandle
0x14001a216  nop     dword ptr [rax+rax+00h]
0x14001a21b  test    rbx, rbx
0x14001a21e  jz      loc_14001A2A4
0x14001a224  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14001a22b  test    rax, rax
0x14001a22e  jz      short loc_14001A264
0x14001a230  cmp     [rax+40h], edi
0x14001a233  jz      short loc_14001A264
0x14001a235  cmp     dword ptr [rax+38h], 3
0x14001a239  jl      short loc_14001A264
0x14001a23b  mov     r8, rbx
0x14001a23e  mov     [rbp+1F0h+var_1C8], r12
0x14001a242  lea     rdx, aFailedToSetFai; "Failed to set failure action to restart"...
0x14001a249  mov     [rbp+1F0h+var_1C0], 1BDh
0x14001a250  lea     rcx, [rbp+1F0h+var_1C8]
0x14001a254  mov     [rbp+1F0h+var_1BC], 3
0x14001a25b  mov     [rbp+1F0h+var_1B8], r13
0x14001a25f  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14001a264  call    cs:__imp_GetCurrentThreadId
0x14001a26b  nop     dword ptr [rax+rax+00h]
0x14001a270  mov     r9d, [rbx]
0x14001a273  mov     r8d, [rbx+8]
0x14001a277  mov     edx, [rbx+4]
0x14001a27a  mov     [rsp+280h+var_240], rbx
0x14001a27f  mov     [rsp+280h+var_248], eax
0x14001a283  lea     rax, aBaseFsRemotefs_81; "base\\fs\\remotefs\\frs\\src\\main\\ser"...
0x14001a28a  mov     [rsp+280h+var_250], 1C0h
0x14001a292  mov     [rsp+280h+var_258], r14
0x14001a297  mov     [rsp+280h+pcbBytesNeeded], rax
0x14001a29c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14001a2a1  mov     rdi, rax
0x14001a2a4  mov     rax, rdi
0x14001a2a7  mov     rcx, [rbp+1F0h+var_30]
0x14001a2ae  xor     rcx, rsp; StackCookie
0x14001a2b1  call    __security_check_cookie
0x14001a2b6  lea     r11, [rsp+280h+var_20]
0x14001a2be  mov     rbx, [r11+38h]
0x14001a2c2  mov     rsi, [r11+40h]
0x14001a2c6  mov     rsp, r11
0x14001a2c9  pop     r14
0x14001a2cb  pop     r13
0x14001a2cd  pop     r12
0x14001a2cf  pop     rdi
0x14001a2d0  pop     rbp
0x14001a2d1  retn
```
