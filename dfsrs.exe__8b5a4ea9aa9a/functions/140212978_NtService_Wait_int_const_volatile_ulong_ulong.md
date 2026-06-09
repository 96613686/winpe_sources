# NtService::Wait(int const volatile &,ulong,ulong)

- ea: `0x140212978`
- end: `0x140212c40`
- name: `?Wait@NtService@@QEAAPEAVFrsStatus@@AEDHKK@Z`
- size: `712`
- prototype: `struct FrsStatus *__fastcall(NtService *__hidden this, const volatile int *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1402127a4`

## callees

- `0x1400036a0`
- `0x14000c910`
- `0x1401b9494`
- `0x1401bd720`
- `0x140212978`

## import_xrefs

- `KERNEL32!Sleep` at `0x140212b5c`
- `KERNEL32!Sleep` at `0x140212b5c`
- `KERNEL32!GetLastError` at `0x140212a61`
- `KERNEL32!GetLastError` at `0x140212a61`
- `KERNEL32!GetCurrentThreadId` at `0x140212a53`
- `KERNEL32!GetCurrentThreadId` at `0x140212ac6`
- `KERNEL32!GetCurrentThreadId` at `0x140212b8b`
- `KERNEL32!GetCurrentThreadId` at `0x140212bd4`
- `KERNEL32!GetCurrentThreadId` at `0x140212a53`
- `KERNEL32!GetCurrentThreadId` at `0x140212ac6`
- `KERNEL32!GetCurrentThreadId` at `0x140212b8b`
- `KERNEL32!GetCurrentThreadId` at `0x140212bd4`
- `ADVAPI32!QueryServiceStatus` at `0x140212a43`
- `ADVAPI32!QueryServiceStatus` at `0x140212a43`

## string_xrefs

- `0x140212a20`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x140212a72`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x140212aab`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x140212b6b`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x140212b9c`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x140212bf3`: `base\fs\remotefs\frs\src\util\ntservice.cpp`
- `0x140212a19`: `NtService::Wait`
- `0x140212b35`: `Waiting for service ....`
- `0x1402129cd`: `NtService::Wait`
- `0x140212b23`: `NtService::Wait`
- `0x1402129f8`: `Wait for service %? finalState:%?`

## pseudocode

```c
struct FrsStatus *__fastcall NtService::Wait(SC_HANDLE *this, const volatile int *a2)
{
  __int64 v2; // rdi
  unsigned int v5; // esi
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  unsigned int *v8; // rbx
  DWORD v9; // eax
  __int64 v10; // rcx
  DWORD v11; // eax
  DWORD v12; // eax
  __int64 v13; // rcx
  int v15; // [rsp+50h] [rbp-19h] BYREF
  const wchar_t *v16; // [rsp+58h] [rbp-11h] BYREF
  int v17; // [rsp+60h] [rbp-9h]
  int v18; // [rsp+64h] [rbp-5h]
  const wchar_t *v19; // [rsp+68h] [rbp-1h]
  _SERVICE_STATUS ServiceStatus; // [rsp+70h] [rbp+7h] BYREF

  v15 = 1;
  v2 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v16 = L"NtService::Wait";
    v19 = L"SRVC";
    v17 = 121;
    v18 = 4;
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,unsigned long>(
      &v16,
      L"Wait for service %? finalState:%?",
      this + 1,
      &v15);
  }
  if ( !*a2 )
  {
    v5 = 120000;
    while ( v5 )
    {
      if ( !QueryServiceStatus(*this, &ServiceStatus) )
      {
        CurrentThreadId = GetCurrentThreadId();
        LastError = GetLastError();
        v8 = (unsigned int *)FrsStatusList::PushNewError(
                               "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                               LastError,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                               "NtService::Wait",
                               136,
                               CurrentThreadId,
                               0);
        if ( v8 )
          goto LABEL_20;
      }
      if ( ServiceStatus.dwCurrentState == v15 )
        break;
      if ( v5 < 0x3E8 )
      {
        v9 = GetCurrentThreadId();
        v8 = (unsigned int *)FrsStatusList::PushNewError(
                               v10,
                               995,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                               "NtService::Wait",
                               153,
                               v9,
                               0);
        if ( v8 )
          goto LABEL_20;
      }
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v17 = 164;
        v16 = L"NtService::Wait";
        v18 = 4;
        v19 = L"SRVC";
        dbgobj::DbgPrint<unsigned short>(&v16, L"Waiting for service ....");
      }
      Sleep(0x3E8u);
      v5 -= 1000;
      if ( *a2 )
        break;
    }
  }
  if ( *a2 )
  {
    v11 = GetCurrentThreadId();
    v8 = (unsigned int *)FrsStatusList::PushNewError(
                           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                           9033,
                           0,
                           3,
                           "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                           "NtService::Wait",
                           170,
                           v11,
                           0);
    if ( v8 )
    {
LABEL_20:
      v12 = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v13,
                                   v8[1],
                                   v8[2],
                                   *v8,
                                   "base\\fs\\remotefs\\frs\\src\\util\\ntservice.cpp",
                                   "NtService::Wait",
                                   173,
                                   v12,
                                   v8);
    }
  }
  return (struct FrsStatus *)v2;
}

```

## disassembly

```asm
0x140212978  mov     [rsp-8+arg_8], rbx
0x14021297d  mov     [rsp-8+arg_10], rsi
0x140212982  push    rbp
0x140212983  push    rdi
0x140212984  push    r13
0x140212986  push    r14
0x140212988  push    r15
0x14021298a  lea     rbp, [rsp-37h]
0x14021298f  sub     rsp, 0A0h
0x140212996  mov     rax, cs:__security_cookie
0x14021299d  xor     rax, rsp
0x1402129a0  mov     [rbp+57h+var_30], rax
0x1402129a4  xor     eax, eax
0x1402129a6  mov     [rbp+57h+var_70], 1
0x1402129ad  mov     qword ptr [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], rax
0x1402129b1  xor     edi, edi
0x1402129b3  mov     [rbp+57h+ServiceStatus.dwWaitHint], eax
0x1402129b6  xorps   xmm0, xmm0
0x1402129b9  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1402129c0  mov     r14, rdx
0x1402129c3  lea     rdx, aSrvc; "SRVC"
0x1402129ca  mov     r15, rcx
0x1402129cd  lea     rcx, aNtserviceWait_0; "NtService::Wait"
0x1402129d4  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x1402129d8  test    rax, rax
0x1402129db  jz      short loc_140212A16
0x1402129dd  cmp     [rax+40h], edi
0x1402129e0  jz      short loc_140212A16
0x1402129e2  cmp     dword ptr [rax+38h], 4
0x1402129e6  jl      short loc_140212A16
0x1402129e8  mov     [rbp+57h+var_68], rcx
0x1402129ec  lea     r8, [r15+8]
0x1402129f0  mov     [rbp+57h+var_58], rdx
0x1402129f4  lea     rcx, [rbp+57h+var_68]
0x1402129f8  lea     rdx, aWaitForService; "Wait for service %? finalState:%?"
0x1402129ff  mov     [rbp+57h+var_60], 79h ; 'y'
0x140212a06  lea     r9, [rbp+57h+var_70]
0x140212a0a  mov     [rbp+57h+var_5C], 4
0x140212a11  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@K@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBK@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,ulong>(ushort const *,FrsStringImpl<ushort,char> const &,ulong const &)
0x140212a16  mov     eax, [r14]
0x140212a19  lea     r13, aNtserviceWait; "NtService::Wait"
0x140212a20  lea     rbx, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140212a27  test    eax, eax
0x140212a29  jnz     loc_140212B80
0x140212a2f  mov     esi, 1D4C0h
0x140212a34  test    esi, esi
0x140212a36  jz      loc_140212B80
0x140212a3c  mov     rcx, [r15]; hService
0x140212a3f  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x140212a43  call    cs:__imp_QueryServiceStatus
0x140212a4a  nop     dword ptr [rax+rax+00h]
0x140212a4f  test    eax, eax
0x140212a51  jnz     short loc_140212AB2
0x140212a53  call    cs:__imp_GetCurrentThreadId
0x140212a5a  nop     dword ptr [rax+rax+00h]
0x140212a5f  mov     ebx, eax
0x140212a61  call    cs:__imp_GetLastError
0x140212a68  nop     dword ptr [rax+rax+00h]
0x140212a6d  mov     [rsp+0C0h+var_80], rdi
0x140212a72  lea     rcx, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140212a79  mov     [rsp+0C0h+var_88], ebx
0x140212a7d  mov     r9d, 1
0x140212a83  mov     [rsp+0C0h+var_90], 88h
0x140212a8b  xor     r8d, r8d
0x140212a8e  mov     [rsp+0C0h+var_98], r13
0x140212a93  mov     edx, eax
0x140212a95  mov     [rsp+0C0h+var_A0], rcx
0x140212a9a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140212a9f  mov     rbx, rax
0x140212aa2  test    rax, rax
0x140212aa5  jnz     loc_140212BD4
0x140212aab  lea     rbx, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140212ab2  mov     eax, [rbp+57h+var_70]
0x140212ab5  cmp     [rbp+57h+ServiceStatus.dwCurrentState], eax
0x140212ab8  jz      loc_140212B80
0x140212abe  cmp     esi, 3E8h
0x140212ac4  jnb     short loc_140212B0C
0x140212ac6  call    cs:__imp_GetCurrentThreadId
0x140212acd  nop     dword ptr [rax+rax+00h]
0x140212ad2  mov     [rsp+0C0h+var_80], rdi
0x140212ad7  mov     r9d, 1
0x140212add  mov     [rsp+0C0h+var_88], eax
0x140212ae1  xor     r8d, r8d
0x140212ae4  mov     [rsp+0C0h+var_90], 99h
0x140212aec  mov     edx, 3E3h
0x140212af1  mov     [rsp+0C0h+var_98], r13
0x140212af6  mov     [rsp+0C0h+var_A0], rbx
0x140212afb  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140212b00  mov     rbx, rax
0x140212b03  test    rax, rax
0x140212b06  jnz     loc_140212BD4
0x140212b0c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140212b13  test    rax, rax
0x140212b16  jz      short loc_140212B57
0x140212b18  cmp     [rax+40h], edi
0x140212b1b  jz      short loc_140212B57
0x140212b1d  cmp     dword ptr [rax+38h], 4
0x140212b21  jl      short loc_140212B57
0x140212b23  lea     rax, aNtserviceWait_0; "NtService::Wait"
0x140212b2a  mov     [rbp+57h+var_60], 0A4h
0x140212b31  mov     [rbp+57h+var_68], rax
0x140212b35  lea     rdx, aWaitingForServ; "Waiting for service ...."
0x140212b3c  lea     rax, aSrvc; "SRVC"
0x140212b43  mov     [rbp+57h+var_5C], 4
0x140212b4a  lea     rcx, [rbp+57h+var_68]
0x140212b4e  mov     [rbp+57h+var_58], rax
0x140212b52  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140212b57  mov     ecx, 3E8h; dwMilliseconds
0x140212b5c  call    cs:__imp_Sleep
0x140212b63  nop     dword ptr [rax+rax+00h]
0x140212b68  mov     eax, [r14]
0x140212b6b  lea     rbx, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140212b72  add     esi, 0FFFFFC18h
0x140212b78  test    eax, eax
0x140212b7a  jz      loc_140212A34
0x140212b80  mov     eax, [r14]
0x140212b83  test    eax, eax
0x140212b85  jz      loc_140212C14
0x140212b8b  call    cs:__imp_GetCurrentThreadId
0x140212b92  nop     dword ptr [rax+rax+00h]
0x140212b97  mov     [rsp+0C0h+var_80], rdi
0x140212b9c  lea     rcx, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140212ba3  mov     [rsp+0C0h+var_88], eax
0x140212ba7  mov     r9d, 3
0x140212bad  mov     [rsp+0C0h+var_90], 0AAh
0x140212bb5  xor     r8d, r8d
0x140212bb8  mov     [rsp+0C0h+var_98], r13
0x140212bbd  mov     edx, 2349h
0x140212bc2  mov     [rsp+0C0h+var_A0], rcx
0x140212bc7  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140212bcc  mov     rbx, rax
0x140212bcf  test    rax, rax
0x140212bd2  jz      short loc_140212C14
0x140212bd4  call    cs:__imp_GetCurrentThreadId
0x140212bdb  nop     dword ptr [rax+rax+00h]
0x140212be0  mov     r9d, [rbx]
0x140212be3  mov     r8d, [rbx+8]
0x140212be7  mov     edx, [rbx+4]
0x140212bea  mov     [rsp+0C0h+var_80], rbx
0x140212bef  mov     [rsp+0C0h+var_88], eax
0x140212bf3  lea     rax, aBaseFsRemotefs; "base\\fs\\remotefs\\frs\\src\\util\\nts"...
0x140212bfa  mov     [rsp+0C0h+var_90], 0ADh
0x140212c02  mov     [rsp+0C0h+var_98], r13
0x140212c07  mov     [rsp+0C0h+var_A0], rax
0x140212c0c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140212c11  mov     rdi, rax
0x140212c14  mov     rax, rdi
0x140212c17  mov     rcx, [rbp+57h+var_30]
0x140212c1b  xor     rcx, rsp; StackCookie
0x140212c1e  call    __security_check_cookie
0x140212c23  lea     r11, [rsp+0C0h+var_20]
0x140212c2b  mov     rbx, [r11+38h]
0x140212c2f  mov     rsi, [r11+40h]
0x140212c33  mov     rsp, r11
0x140212c36  pop     r15
0x140212c38  pop     r14
0x140212c3a  pop     r13
0x140212c3c  pop     rdi
0x140212c3d  pop     rbp
0x140212c3e  retn
```
