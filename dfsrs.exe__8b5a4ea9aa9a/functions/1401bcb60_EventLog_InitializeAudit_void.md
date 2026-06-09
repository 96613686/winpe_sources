# EventLog::InitializeAudit(void)

- ea: `0x1401bcb60`
- end: `0x1401bce32`
- name: `?InitializeAudit@EventLog@@AEAAPEAVFrsStatus@@XZ`
- size: `722`
- prototype: `struct FrsStatus *__fastcall(EventLog *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401ba3a4`

## callees

- `0x14000cdc0`
- `0x14000e34c`
- `0x14000ee94`
- `0x1400248ac`
- `0x1401b9494`
- `0x1401ba6f4`
- `0x1401ba8cc`
- `0x1401bcb60`
- `0x1401bed34`
- `0x140223010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1401bcbaa`
- `KERNEL32!LoadLibraryExW` at `0x1401bcbaa`
- `KERNEL32!GetProcAddress` at `0x1401bcbcd`
- `KERNEL32!GetProcAddress` at `0x1401bcbe8`
- `KERNEL32!GetProcAddress` at `0x1401bcc03`
- `KERNEL32!GetProcAddress` at `0x1401bcc21`
- `KERNEL32!GetProcAddress` at `0x1401bcc3f`
- `KERNEL32!GetProcAddress` at `0x1401bcbcd`
- `KERNEL32!GetProcAddress` at `0x1401bcbe8`
- `KERNEL32!GetProcAddress` at `0x1401bcc03`
- `KERNEL32!GetProcAddress` at `0x1401bcc21`
- `KERNEL32!GetProcAddress` at `0x1401bcc3f`
- `KERNEL32!GetLastError` at `0x1401bcd66`
- `KERNEL32!GetLastError` at `0x1401bcd66`
- `KERNEL32!GetCurrentThreadId` at `0x1401bccba`
- `KERNEL32!GetCurrentThreadId` at `0x1401bcd58`
- `KERNEL32!GetCurrentThreadId` at `0x1401bccba`
- `KERNEL32!GetCurrentThreadId` at `0x1401bcd58`

## string_xrefs

- `0x1401bcb81`: `%SystemRoot%\System32\dfsrresS.dll`
- `0x1401bcba3`: `authz.dll`
- `0x1401bcbf8`: `AuthzEnumerateSecurityEventSources`
- `0x1401bcc16`: `AuthzInstallSecurityEventSource`
- `0x1401bcbc3`: `AuthzRegisterSecurityEventSource`
- `0x1401bcbdd`: `AuthzUnregisterSecurityEventSource`
- `0x1401bcc34`: `AuthzReportSecurityEventFromParams`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall EventLog::InitializeAudit(EventLog *this)
{
  HMODULE Library; // rax
  const unsigned __int16 *v3; // rdx
  EventLog *v4; // rcx
  struct FrsStatus *v5; // rax
  DWORD CurrentThreadId; // ebx
  unsigned int v7; // eax
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rdx
  unsigned int (__fastcall *v10)(_QWORD, const wchar_t *, char *); // rax
  DWORD v11; // ebx
  DWORD LastError; // eax
  __int64 v13; // rcx
  void **v15; // [rsp+50h] [rbp-30h] BYREF
  __int64 v16; // [rsp+58h] [rbp-28h] BYREF
  const wchar_t *v17; // [rsp+60h] [rbp-20h] BYREF
  int v18; // [rsp+68h] [rbp-18h]
  int v19; // [rsp+6Ch] [rbp-14h]
  const wchar_t *v20; // [rsp+70h] [rbp-10h]
  struct FrsStatus *v21; // [rsp+A0h] [rbp+20h] BYREF

  v21 = 0;
  FilePath::FilePath((FilePath *)&v15, L"%SystemRoot%\\System32\\dfsrresS.dll");
  Library = (HMODULE)*((_QWORD *)this + 11);
  if ( Library || (Library = LoadLibraryExW(L"authz.dll", 0, 0x800u), (*((_QWORD *)this + 11) = Library) != 0) )
  {
    *((_QWORD *)this + 15) = GetProcAddress(Library, "AuthzRegisterSecurityEventSource");
    *((_QWORD *)this + 14) = GetProcAddress(*((HMODULE *)this + 11), "AuthzUnregisterSecurityEventSource");
    *((_QWORD *)this + 16) = GetProcAddress(*((HMODULE *)this + 11), "AuthzEnumerateSecurityEventSources");
    *((_QWORD *)this + 17) = GetProcAddress(*((HMODULE *)this + 11), "AuthzInstallSecurityEventSource");
    *((_QWORD *)this + 18) = GetProcAddress(*((HMODULE *)this + 11), "AuthzReportSecurityEventFromParams");
  }
  if ( *((_QWORD *)this + 11) )
  {
    if ( !*((_QWORD *)this + 13) )
    {
      if ( *((_QWORD *)this + 15) )
      {
        if ( *((_QWORD *)this + 14) )
        {
          if ( *((_QWORD *)this + 16) )
          {
            if ( *((_QWORD *)this + 17) )
            {
              if ( *((_QWORD *)this + 18) )
              {
                v5 = EventLog::AuditEnableSinglePrivilege(v4, v3);
                v21 = v5;
                if ( v5 )
                  goto LABEL_19;
                CurrentThreadId = GetCurrentThreadId();
                v7 = FilePath::Expand((FilePath *)&v15);
                v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                           v8,
                                           v7,
                                           0,
                                           1,
                                           &PreviousState,
                                           "EventLog::InitializeAudit",
                                           1432,
                                           CurrentThreadId,
                                           0);
                v21 = v5;
                if ( v5
                  || (v5 = EventLog::AuditInstall(this, v9, (const unsigned __int16 *)(v16 + 18)), (v21 = v5) != 0)
                  || (v10 = (unsigned int (__fastcall *)(_QWORD, const wchar_t *, char *))*((_QWORD *)this + 15)) != 0
                  && !v10(0, L"DFSR Audit", (char *)this + 104)
                  && (v11 = GetCurrentThreadId(),
                      LastError = GetLastError(),
                      v5 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                 v13,
                                                 LastError,
                                                 0,
                                                 1,
                                                 &PreviousState,
                                                 "EventLog::InitializeAudit",
                                                 1444,
                                                 v11,
                                                 0),
                      (v21 = v5) != 0) )
                {
LABEL_19:
                  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                  {
                    v17 = L"EventLog::InitializeAudit";
                    v18 = 1449;
                    v19 = 3;
                    v20 = L"EVNT";
                    dbgobj::DbgPrint<unsigned short,FrsStatus>(&v17, L"(Ignored) %?", v5);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  CLEAR_ERROR(&v21);
  v15 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v16);
  return v21;
}

```

## disassembly

```asm
0x1401bcb60  mov     [rsp-18h+arg_8], rbx
0x1401bcb65  mov     [rsp-18h+arg_10], rdi
0x1401bcb6a  push    rbp
0x1401bcb6b  push    r12
0x1401bcb6d  push    r15
0x1401bcb6f  mov     rbp, rsp
0x1401bcb72  sub     rsp, 80h
0x1401bcb79  mov     rdi, rcx
0x1401bcb7c  and     [rbp+arg_0], 0
0x1401bcb81  lea     rdx, Src; "%SystemRoot%\\System32\\dfsrresS.dll"
0x1401bcb88  lea     rcx, [rbp+var_30]; this
0x1401bcb8c  call    ??0FilePath@@QEAA@PEBG@Z; FilePath::FilePath(ushort const *)
0x1401bcb91  nop
0x1401bcb92  mov     rax, [rdi+58h]
0x1401bcb96  test    rax, rax
0x1401bcb99  jnz     short loc_1401BCBC3
0x1401bcb9b  xor     edx, edx; hFile
0x1401bcb9d  mov     r8d, 800h; dwFlags
0x1401bcba3  lea     rcx, aAuthzDll; "authz.dll"
0x1401bcbaa  call    cs:__imp_LoadLibraryExW
0x1401bcbb1  nop     dword ptr [rax+rax+00h]
0x1401bcbb6  mov     [rdi+58h], rax
0x1401bcbba  test    rax, rax
0x1401bcbbd  jz      loc_1401BCC52
0x1401bcbc3  lea     rdx, aAuthzregisters; "AuthzRegisterSecurityEventSource"
0x1401bcbca  mov     rcx, rax; hModule
0x1401bcbcd  call    cs:__imp_GetProcAddress
0x1401bcbd4  nop     dword ptr [rax+rax+00h]
0x1401bcbd9  mov     [rdi+78h], rax
0x1401bcbdd  lea     rdx, aAuthzunregiste; "AuthzUnregisterSecurityEventSource"
0x1401bcbe4  mov     rcx, [rdi+58h]; hModule
0x1401bcbe8  call    cs:__imp_GetProcAddress
0x1401bcbef  nop     dword ptr [rax+rax+00h]
0x1401bcbf4  mov     [rdi+70h], rax
0x1401bcbf8  lea     rdx, aAuthzenumerate; "AuthzEnumerateSecurityEventSources"
0x1401bcbff  mov     rcx, [rdi+58h]; hModule
0x1401bcc03  call    cs:__imp_GetProcAddress
0x1401bcc0a  nop     dword ptr [rax+rax+00h]
0x1401bcc0f  mov     [rdi+80h], rax
0x1401bcc16  lea     rdx, aAuthzinstallse; "AuthzInstallSecurityEventSource"
0x1401bcc1d  mov     rcx, [rdi+58h]; hModule
0x1401bcc21  call    cs:__imp_GetProcAddress
0x1401bcc28  nop     dword ptr [rax+rax+00h]
0x1401bcc2d  mov     [rdi+88h], rax
0x1401bcc34  lea     rdx, aAuthzreportsec; "AuthzReportSecurityEventFromParams"
0x1401bcc3b  mov     rcx, [rdi+58h]; hModule
0x1401bcc3f  call    cs:__imp_GetProcAddress
0x1401bcc46  nop     dword ptr [rax+rax+00h]
0x1401bcc4b  mov     [rdi+90h], rax
0x1401bcc52  cmp     qword ptr [rdi+58h], 0
0x1401bcc57  jz      loc_1401BCDF6
0x1401bcc5d  cmp     qword ptr [rdi+68h], 0
0x1401bcc62  jnz     loc_1401BCDF6
0x1401bcc68  cmp     qword ptr [rdi+78h], 0
0x1401bcc6d  jz      loc_1401BCDF6
0x1401bcc73  cmp     qword ptr [rdi+70h], 0
0x1401bcc78  jz      loc_1401BCDF6
0x1401bcc7e  cmp     qword ptr [rdi+80h], 0
0x1401bcc86  jz      loc_1401BCDF6
0x1401bcc8c  cmp     qword ptr [rdi+88h], 0
0x1401bcc94  jz      loc_1401BCDF6
0x1401bcc9a  cmp     qword ptr [rdi+90h], 0
0x1401bcca2  jz      loc_1401BCDF6
0x1401bcca8  call    ?AuditEnableSinglePrivilege@EventLog@@AEAAPEAVFrsStatus@@PEBG@Z; EventLog::AuditEnableSinglePrivilege(ushort const *)
0x1401bccad  mov     [rbp+arg_0], rax
0x1401bccb1  test    rax, rax
0x1401bccb4  jnz     loc_1401BCDA7
0x1401bccba  call    cs:__imp_GetCurrentThreadId
0x1401bccc1  nop     dword ptr [rax+rax+00h]
0x1401bccc6  mov     ebx, eax
0x1401bccc8  lea     rcx, [rbp+var_30]; this
0x1401bcccc  call    ?Expand@FilePath@@QEAAKXZ; FilePath::Expand(void)
0x1401bccd1  and     [rsp+80h+var_40], 0
0x1401bccd7  mov     [rsp+80h+var_48], ebx
0x1401bccdb  mov     [rsp+80h+var_50], 598h
0x1401bcce3  lea     r15, aEventlogInitia; "EventLog::InitializeAudit"
0x1401bccea  mov     [rsp+80h+var_58], r15
0x1401bccef  lea     r12, PreviousState
0x1401bccf6  mov     [rsp+80h+var_60], r12
0x1401bccfb  mov     r9d, 1
0x1401bcd01  xor     r8d, r8d
0x1401bcd04  mov     edx, eax
0x1401bcd06  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401bcd0b  mov     [rbp+arg_0], rax
0x1401bcd0f  test    rax, rax
0x1401bcd12  jnz     loc_1401BCDA7
0x1401bcd18  mov     r8, [rbp+var_28]
0x1401bcd1c  add     r8, 12h; unsigned __int16 *
0x1401bcd20  mov     rcx, rdi; this
0x1401bcd23  call    ?AuditInstall@EventLog@@AEAAPEAVFrsStatus@@PEBG0@Z; EventLog::AuditInstall(ushort const *,ushort const *)
0x1401bcd28  mov     [rbp+arg_0], rax
0x1401bcd2c  test    rax, rax
0x1401bcd2f  jnz     short loc_1401BCDA7
0x1401bcd31  mov     rax, [rdi+78h]
0x1401bcd35  test    rax, rax
0x1401bcd38  jz      loc_1401BCDF6
0x1401bcd3e  lea     r8, [rdi+68h]
0x1401bcd42  lea     rdx, aDfsrAudit; "DFSR Audit"
0x1401bcd49  xor     ecx, ecx
0x1401bcd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401bcd50  test    eax, eax
0x1401bcd52  jnz     loc_1401BCDF6
0x1401bcd58  call    cs:__imp_GetCurrentThreadId
0x1401bcd5f  nop     dword ptr [rax+rax+00h]
0x1401bcd64  mov     ebx, eax
0x1401bcd66  call    cs:__imp_GetLastError
0x1401bcd6d  nop     dword ptr [rax+rax+00h]
0x1401bcd72  and     [rsp+80h+var_40], 0
0x1401bcd78  mov     [rsp+80h+var_48], ebx
0x1401bcd7c  mov     [rsp+80h+var_50], 5A4h
0x1401bcd84  mov     [rsp+80h+var_58], r15
0x1401bcd89  mov     [rsp+80h+var_60], r12
0x1401bcd8e  mov     r9d, 1
0x1401bcd94  xor     r8d, r8d
0x1401bcd97  mov     edx, eax
0x1401bcd99  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401bcd9e  mov     [rbp+arg_0], rax
0x1401bcda2  test    rax, rax
0x1401bcda5  jz      short loc_1401BCDF6
0x1401bcda7  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401bcdae  test    rcx, rcx
0x1401bcdb1  jz      short loc_1401BCDF6
0x1401bcdb3  cmp     dword ptr [rcx+40h], 0
0x1401bcdb7  jz      short loc_1401BCDF6
0x1401bcdb9  cmp     dword ptr [rcx+38h], 3
0x1401bcdbd  jl      short loc_1401BCDF6
0x1401bcdbf  lea     rcx, aEventlogInitia_0; "EventLog::InitializeAudit"
0x1401bcdc6  mov     [rbp+var_20], rcx
0x1401bcdca  mov     [rbp+var_18], 5A9h
0x1401bcdd1  mov     [rbp+var_14], 3
0x1401bcdd8  lea     rcx, aEvnt; "EVNT"
0x1401bcddf  mov     [rbp+var_10], rcx
0x1401bcde3  mov     r8, rax
0x1401bcde6  lea     rdx, aIgnored_0; "(Ignored) %?"
0x1401bcded  lea     rcx, [rbp+var_20]
0x1401bcdf1  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1401bcdf6  lea     rcx, [rbp+arg_0]; struct FrsStatus **
0x1401bcdfa  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401bcdff  nop
0x1401bce00  lea     rax, ??_7FilePath@@6B@; const FilePath::`vftable'
0x1401bce07  mov     [rbp+var_30], rax
0x1401bce0b  lea     rcx, [rbp+var_28]
0x1401bce0f  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401bce14  mov     rax, [rbp+arg_0]
0x1401bce18  lea     r11, [rsp+80h+var_s0]
0x1401bce20  mov     rbx, [r11+28h]
0x1401bce24  mov     rdi, [r11+30h]
0x1401bce28  mov     rsp, r11
0x1401bce2b  pop     r15
0x1401bce2d  pop     r12
0x1401bce2f  pop     rbp
0x1401bce30  retn
```
