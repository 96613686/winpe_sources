# NtService::Stop(int const volatile &,_SERVICE_STATUS *)

- ea: `0x1402127a4`
- end: `0x140212972`
- name: `?Stop@NtService@@QEAAPEAVFrsStatus@@AEDHPEAU_SERVICE_STATUS@@@Z`
- size: `462`
- prototype: `struct FrsStatus *(NtService *__hidden this, const volatile int *, struct _SERVICE_STATUS *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1401f9e68`
- `0x1401fdf10`
- `0x140200460`

## callees

- `0x14000cb00`
- `0x14001c31c`
- `0x1401b9494`
- `0x1402127a4`
- `0x140212978`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140212836`
- `KERNEL32!GetLastError` at `0x1402128ab`
- `KERNEL32!GetLastError` at `0x140212836`
- `KERNEL32!GetLastError` at `0x1402128ab`
- `KERNEL32!GetCurrentThreadId` at `0x14021290e`
- `KERNEL32!GetCurrentThreadId` at `0x14021290e`
- `ADVAPI32!ControlService` at `0x140212822`
- `ADVAPI32!ControlService` at `0x14021289b`
- `ADVAPI32!ControlService` at `0x140212822`
- `ADVAPI32!ControlService` at `0x14021289b`

## string_xrefs

- `0x140212941`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x1402127c4`: `NtService::Stop`
- `0x1402128d9`: `[MIG] The second ControlService with SERVICE_CONTROL_STOP failed. Error: 0x%x`
- `0x14021292d`: `NtService::Stop`
- `0x140212800`: `Stop service %?`
- `0x140212864`: `The first ControlService with SERVICE_CONTROL_STOP failed. Error: 0x%x`

## pseudocode

```c
struct FrsStatus *__fastcall NtService::Stop(SC_HANDLE *this, const volatile int *a2, struct _SERVICE_STATUS *a3)
{
  __int64 v3; // rbx
  DWORD LastError; // eax
  struct FrsStatus *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  const wchar_t *v12; // [rsp+50h] [rbp-20h] BYREF
  int v13; // [rsp+58h] [rbp-18h]
  int v14; // [rsp+5Ch] [rbp-14h]
  const wchar_t *v15; // [rsp+60h] [rbp-10h]
  DWORD v16; // [rsp+A0h] [rbp+30h] BYREF

  v3 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v12 = L"NtService::Stop";
    v13 = 226;
    v14 = 4;
    v15 = L"SRVC";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>>(&v12, L"Stop service %?", this + 1);
  }
  if ( !ControlService(*this, 1u, a3) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v12 = L"NtService::Stop";
      v13 = 236;
      v14 = 3;
      v15 = L"SRVC";
      dbgobj::DbgPrint<unsigned short,unsigned int>(
        &v12,
        L"The first ControlService with SERVICE_CONTROL_STOP failed. Error: 0x%x",
        &v16);
      LastError = v16;
    }
    if ( LastError == 1053 && !ControlService(*this, 1u, a3) )
    {
      v16 = GetLastError();
      if ( g_DebugLog )
      {
        if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v12 = L"NtService::Stop";
          v13 = 244;
          v14 = 3;
          v15 = L"SRVC";
          dbgobj::DbgPrint<unsigned short,unsigned int>(
            &v12,
            L"[MIG] The second ControlService with SERVICE_CONTROL_STOP failed. Error: 0x%x",
            &v16);
        }
      }
    }
  }
  v8 = NtService::Wait(this, a2);
  if ( v8 )
  {
    CurrentThreadId = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v10,
                                 *((unsigned int *)v8 + 1),
                                 *((unsigned int *)v8 + 2),
                                 *(unsigned int *)v8,
                                 "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                                 "NtService::Stop",
                                 253,
                                 CurrentThreadId,
                                 v8);
  }
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x1402127a4  mov     [rsp-28h+arg_8], rbx
0x1402127a9  mov     [rsp-28h+arg_10], rsi
0x1402127ae  push    rbp
0x1402127af  push    rdi
0x1402127b0  push    r12
0x1402127b2  push    r13
0x1402127b4  push    r14
0x1402127b6  mov     rbp, rsp
0x1402127b9  sub     rsp, 70h
0x1402127bd  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1402127c4  lea     r12, aNtserviceStop; "NtService::Stop"
0x1402127cb  xor     ebx, ebx
0x1402127cd  lea     r13, aSrvc; "SRVC"
0x1402127d4  mov     rsi, r8
0x1402127d7  mov     r14, rdx
0x1402127da  mov     rdi, rcx
0x1402127dd  test    rax, rax
0x1402127e0  jz      short loc_140212817
0x1402127e2  cmp     [rax+40h], ebx
0x1402127e5  jz      short loc_140212817
0x1402127e7  cmp     dword ptr [rax+38h], 4
0x1402127eb  jl      short loc_140212817
0x1402127ed  lea     r8, [rcx+8]
0x1402127f1  mov     [rbp+var_20], r12
0x1402127f5  lea     rcx, [rbp+var_20]
0x1402127f9  mov     [rbp+var_18], 0E2h
0x140212800  lea     rdx, aStopService; "Stop service %?"
0x140212807  mov     [rbp+var_14], 4
0x14021280e  mov     [rbp+var_10], r13
0x140212812  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>>(ushort const *,FrsStringImpl<ushort,char> const &)
0x140212817  mov     rcx, [rdi]; hService
0x14021281a  mov     r8, rsi; lpServiceStatus
0x14021281d  mov     edx, 1; dwControl
0x140212822  call    cs:__imp_ControlService
0x140212829  nop     dword ptr [rax+rax+00h]
0x14021282e  test    eax, eax
0x140212830  jnz     loc_1402128FB
0x140212836  call    cs:__imp_GetLastError
0x14021283d  nop     dword ptr [rax+rax+00h]
0x140212842  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140212849  mov     [rbp+arg_0], eax
0x14021284c  test    rcx, rcx
0x14021284f  jz      short loc_140212889
0x140212851  cmp     [rcx+40h], ebx
0x140212854  jz      short loc_140212889
0x140212856  cmp     dword ptr [rcx+38h], 3
0x14021285a  jl      short loc_140212889
0x14021285c  lea     r8, [rbp+arg_0]
0x140212860  mov     [rbp+var_20], r12
0x140212864  lea     rdx, aTheFirstContro; "The first ControlService with SERVICE_C"...
0x14021286b  mov     [rbp+var_18], 0ECh
0x140212872  lea     rcx, [rbp+var_20]
0x140212876  mov     [rbp+var_14], 3
0x14021287d  mov     [rbp+var_10], r13
0x140212881  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140212886  mov     eax, [rbp+arg_0]
0x140212889  cmp     eax, 41Dh
0x14021288e  jnz     short loc_1402128FB
0x140212890  mov     rcx, [rdi]; hService
0x140212893  mov     r8, rsi; lpServiceStatus
0x140212896  mov     edx, 1; dwControl
0x14021289b  call    cs:__imp_ControlService
0x1402128a2  nop     dword ptr [rax+rax+00h]
0x1402128a7  test    eax, eax
0x1402128a9  jnz     short loc_1402128FB
0x1402128ab  call    cs:__imp_GetLastError
0x1402128b2  nop     dword ptr [rax+rax+00h]
0x1402128b7  mov     [rbp+arg_0], eax
0x1402128ba  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1402128c1  test    rax, rax
0x1402128c4  jz      short loc_1402128FB
0x1402128c6  cmp     [rax+40h], ebx
0x1402128c9  jz      short loc_1402128FB
0x1402128cb  cmp     dword ptr [rax+38h], 3
0x1402128cf  jl      short loc_1402128FB
0x1402128d1  lea     r8, [rbp+arg_0]
0x1402128d5  mov     [rbp+var_20], r12
0x1402128d9  lea     rdx, aMigTheSecondCo; "[MIG] The second ControlService with SE"...
0x1402128e0  mov     [rbp+var_18], 0F4h
0x1402128e7  lea     rcx, [rbp+var_20]
0x1402128eb  mov     [rbp+var_14], 3
0x1402128f2  mov     [rbp+var_10], r13
0x1402128f6  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x1402128fb  mov     rdx, r14; volatile int *
0x1402128fe  mov     rcx, rdi; this
0x140212901  call    ?Wait@NtService@@QEAAPEAVFrsStatus@@AEDHKK@Z; NtService::Wait(int const volatile &,ulong,ulong)
0x140212906  mov     rdi, rax
0x140212909  test    rax, rax
0x14021290c  jz      short loc_140212955
0x14021290e  call    cs:__imp_GetCurrentThreadId
0x140212915  nop     dword ptr [rax+rax+00h]
0x14021291a  mov     r9d, [rdi]
0x14021291d  mov     r8d, [rdi+8]
0x140212921  mov     edx, [rdi+4]
0x140212924  mov     [rsp+70h+var_30], rdi
0x140212929  mov     [rsp+70h+var_38], eax
0x14021292d  lea     rax, aNtserviceStop_0; "NtService::Stop"
0x140212934  mov     [rsp+70h+var_40], 0FDh
0x14021293c  mov     [rsp+70h+var_48], rax
0x140212941  lea     rax, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140212948  mov     [rsp+70h+var_50], rax
0x14021294d  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140212952  mov     rbx, rax
0x140212955  lea     r11, [rsp+70h+var_s0]
0x14021295a  mov     rax, rbx
0x14021295d  mov     rbx, [r11+38h]
0x140212961  mov     rsi, [r11+40h]
0x140212965  mov     rsp, r11
0x140212968  pop     r14
0x14021296a  pop     r13
0x14021296c  pop     r12
0x14021296e  pop     rdi
0x14021296f  pop     rbp
0x140212970  retn
```
