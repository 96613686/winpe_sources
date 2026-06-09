# FrsService::RemoveDisabledPrivileges(void)

- ea: `0x14000eec4`
- end: `0x14000f338`
- name: `?RemoveDisabledPrivileges@FrsService@@KAPEAVFrsStatus@@XZ`
- size: `1140`
- prototype: `struct FrsStatus *(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x140011254`

## callees

- `0x1400036a0`
- `0x14000c870`
- `0x14000c910`
- `0x14000ca4c`
- `0x14000cb00`
- `0x14000eec4`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000f2b2`
- `KERNEL32!CloseHandle` at `0x14000f2b2`
- `KERNEL32!GetLastError` at `0x14000f002`
- `KERNEL32!GetLastError` at `0x14000f15b`
- `KERNEL32!GetLastError` at `0x14000f002`
- `KERNEL32!GetLastError` at `0x14000f15b`
- `KERNEL32!GetCurrentThreadId` at `0x14000ef40`
- `KERNEL32!GetCurrentThreadId` at `0x14000eff4`
- `KERNEL32!GetCurrentThreadId` at `0x14000f14d`
- `KERNEL32!GetCurrentThreadId` at `0x14000f2cb`
- `KERNEL32!GetCurrentThreadId` at `0x14000ef40`
- `KERNEL32!GetCurrentThreadId` at `0x14000eff4`
- `KERNEL32!GetCurrentThreadId` at `0x14000f14d`
- `KERNEL32!GetCurrentThreadId` at `0x14000f2cb`
- `ntdll!RtlNtStatusToDosError` at `0x14000ef51`
- `ntdll!RtlNtStatusToDosError` at `0x14000ef51`
- `ntdll!NtOpenProcessToken` at `0x14000ef1b`
- `ntdll!NtOpenProcessToken` at `0x14000ef1b`
- `ADVAPI32!GetTokenInformation` at `0x14000efb2`
- `ADVAPI32!GetTokenInformation` at `0x14000efe4`
- `ADVAPI32!GetTokenInformation` at `0x14000efb2`
- `ADVAPI32!GetTokenInformation` at `0x14000efe4`
- `ADVAPI32!LookupPrivilegeNameW` at `0x14000f0a1`
- `ADVAPI32!LookupPrivilegeNameW` at `0x14000f0a1`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14000f139`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14000f139`

## string_xrefs

- `0x14000ef31`: `base\fs\remotefs\frs\src\main\frsservice.cpp`
- `0x14000f177`: `base\fs\remotefs\frs\src\main\frsservice.cpp`
- `0x14000f295`: `base\fs\remotefs\frs\src\main\frsservice.cpp`
- `0x14000ef27`: `FrsService::RemoveDisabledPrivileges`
- `0x14000f16c`: `FrsService::RemoveDisabledPrivileges`
- `0x14000f29c`: `FrsService::RemoveDisabledPrivileges`
- `0x14000f047`: `FrsService::RemoveDisabledPrivileges`
- `0x14000f066`: `FrsService::RemoveDisabledPrivileges`
- `0x14000f119`: `FrsService::RemoveDisabledPrivileges`
- `0x14000f22e`: `Privilege %s set for removal`
- `0x14000f1ce`: `Failed to remove privileges. Error:%d`
- `0x14000f26d`: `Privileges removed successfully`

## pseudocode

```c
struct FrsStatus *FrsService::RemoveDisabledPrivileges(void)
{
  __int64 v0; // rdi
  unsigned int *v1; // rbx
  struct _TOKEN_PRIVILEGES *v2; // rsi
  int v3; // r14d
  DWORD v4; // ebx
  ULONG v5; // eax
  __int64 v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  __int64 v9; // rcx
  DWORD v10; // r14d
  char *v11; // r12
  __int64 v12; // rdx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  DWORD v15; // eax
  __int64 v16; // rcx
  DWORD TokenInformationLength[2]; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v19; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+68h] [rbp-A0h]
  const wchar_t *v21; // [rsp+70h] [rbp-98h]
  void *TokenHandle; // [rsp+78h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-88h]
  WCHAR Name[264]; // [rsp+88h] [rbp-80h] BYREF

  v0 = 0;
  TokenInformationLength[0] = 0;
  v1 = 0;
  TokenHandle = (void *)-1LL;
  v23 = 0;
  v2 = 0;
  v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, &TokenHandle);
  if ( v3 >= 0
    || (v4 = GetCurrentThreadId(),
        v5 = RtlNtStatusToDosError(v3),
        v23 = FrsStatusList::PushNewError(
                v6,
                v5,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\main\\frsservice.cpp",
                "FrsService::RemoveDisabledPrivileges",
                743,
                v4,
                0),
        (v1 = (unsigned int *)v23) == 0) )
  {
    GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, TokenInformationLength);
    v2 = (struct _TOKEN_PRIVILEGES *)operator_new(TokenInformationLength[0]);
    if ( GetTokenInformation(TokenHandle, TokenPrivileges, v2, TokenInformationLength[0], TokenInformationLength)
      || (v7 = GetCurrentThreadId(),
          v8 = GetLastError(),
          v23 = FrsStatusList::PushNewError(
                  v9,
                  v8,
                  0,
                  1,
                  "base\\fs\\remotefs\\frs\\src\\main\\frsservice.cpp",
                  "FrsService::RemoveDisabledPrivileges",
                  769,
                  v7,
                  0),
          (v1 = (unsigned int *)v23) == 0) )
    {
      v10 = 0;
      if ( v2->PrivilegeCount )
      {
        do
        {
          if ( (v2->Privileges[v10].Attributes & 2) == 0 )
          {
            v11 = (char *)v2 + 12 * v10;
            TokenInformationLength[1] = 260;
            *((_DWORD *)v11 + 3) = 4;
            if ( LookupPrivilegeNameW(0, (PLUID)(v11 + 4), Name, &TokenInformationLength[1]) )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
              {
                v19 = L"FrsService::RemoveDisabledPrivileges";
                v20 = 0x40000031FLL;
                v21 = L"FSVC";
                dbgobj::DbgPrint<unsigned short,unsigned short [39]>(&v19, L"Privilege %s set for removal", Name);
              }
            }
            else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v19 = L"FrsService::RemoveDisabledPrivileges";
              v20 = 0x400000319LL;
              v21 = L"FSVC";
              dbgobj::DbgPrint<unsigned short,long,unsigned long>(
                &v19,
                v12,
                &v2->Privileges[v10].Luid.HighPart,
                v11 + 4);
            }
          }
          ++v10;
        }
        while ( v10 < v2->PrivilegeCount );
        v1 = (unsigned int *)v23;
      }
      if ( AdjustTokenPrivileges(TokenHandle, 0, v2, TokenInformationLength[0], 0, 0) )
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v19 = L"FrsService::RemoveDisabledPrivileges";
          v20 = 0x400000336LL;
          v21 = L"FSVC";
          dbgobj::DbgPrint<unsigned short>(&v19, L"Privileges removed successfully");
        }
      }
      else
      {
        CurrentThreadId = GetCurrentThreadId();
        LastError = GetLastError();
        v1 = (unsigned int *)FrsStatusList::PushNewError(
                               "FrsService::RemoveDisabledPrivileges",
                               LastError,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\main\\frsservice.cpp",
                               "FrsService::RemoveDisabledPrivileges",
                               817,
                               CurrentThreadId,
                               0);
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          TokenInformationLength[1] = v1[1];
          v19 = L"FrsService::RemoveDisabledPrivileges";
          v20 = 0x200000332LL;
          v21 = L"FSVC";
          dbgobj::DbgPrint<unsigned short,unsigned int>(
            &v19,
            L"Failed to remove privileges. Error:%d",
            &TokenInformationLength[1]);
        }
      }
    }
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  operator delete[](v2);
  if ( v1 )
  {
    v15 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v16,
                                 v1[1],
                                 v1[2],
                                 *v1,
                                 "base\\fs\\remotefs\\frs\\src\\main\\frsservice.cpp",
                                 "FrsService::RemoveDisabledPrivileges",
                                 832,
                                 v15,
                                 v1);
  }
  return (struct FrsStatus *)v0;
}

```

## disassembly

```asm
0x14000eec4  mov     rax, rsp
0x14000eec7  mov     [rax+8], rbx
0x14000eecb  mov     [rax+10h], rsi
0x14000eecf  mov     [rax+18h], rdi
0x14000eed3  push    rbp
0x14000eed4  push    r12
0x14000eed6  push    r13
0x14000eed8  push    r14
0x14000eeda  push    r15
0x14000eedc  lea     rbp, [rax-1C8h]
0x14000eee3  sub     rsp, 2A0h
0x14000eeea  mov     rax, cs:__security_cookie
0x14000eef1  xor     rax, rsp
0x14000eef4  mov     [rbp+1C0h+var_30], rax
0x14000eefb  xor     edi, edi
0x14000eefd  lea     r8, [rsp+2C0h+TokenHandle]; TokenHandle
0x14000ef02  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14000ef06  mov     [rsp+2C0h+TokenInformationLength], edi
0x14000ef0a  mov     ebx, edi
0x14000ef0c  mov     [rsp+2C0h+TokenHandle], rcx
0x14000ef11  mov     [rsp+2C0h+var_248], rbx
0x14000ef16  mov     esi, edi
0x14000ef18  lea     edx, [rdi+28h]; DesiredAccess
0x14000ef1b  call    cs:__imp_NtOpenProcessToken
0x14000ef22  nop     dword ptr [rax+rax+00h]
0x14000ef27  lea     r12, aFrsserviceRemo_0; "FrsService::RemoveDisabledPrivileges"
0x14000ef2e  mov     r14d, eax
0x14000ef31  lea     r13, aBaseFsRemotefs_103; "base\\fs\\remotefs\\frs\\src\\main\\frs"...
0x14000ef38  lea     r15d, [rdi+1]
0x14000ef3c  test    eax, eax
0x14000ef3e  jns     short loc_14000EF96
0x14000ef40  call    cs:__imp_GetCurrentThreadId
0x14000ef47  nop     dword ptr [rax+rax+00h]
0x14000ef4c  mov     ecx, r14d; Status
0x14000ef4f  mov     ebx, eax
0x14000ef51  call    cs:__imp_RtlNtStatusToDosError
0x14000ef58  nop     dword ptr [rax+rax+00h]
0x14000ef5d  mov     [rsp+2C0h+var_280], rdi
0x14000ef62  mov     r9d, r15d
0x14000ef65  mov     dword ptr [rsp+2C0h+var_288], ebx
0x14000ef69  xor     r8d, r8d
0x14000ef6c  mov     [rsp+2C0h+var_290], 2E7h
0x14000ef74  mov     edx, eax
0x14000ef76  mov     [rsp+2C0h+var_298], r12
0x14000ef7b  mov     [rsp+2C0h+ReturnLength], r13
0x14000ef80  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14000ef85  mov     [rsp+2C0h+var_248], rax
0x14000ef8a  mov     rbx, rax
0x14000ef8d  test    rax, rax
0x14000ef90  jnz     loc_14000F2A3
0x14000ef96  mov     rcx, [rsp+2C0h+TokenHandle]; TokenHandle
0x14000ef9b  lea     rax, [rsp+2C0h+TokenInformationLength]
0x14000efa0  xor     r9d, r9d; TokenInformationLength
0x14000efa3  mov     [rsp+2C0h+ReturnLength], rax; ReturnLength
0x14000efa8  xor     r8d, r8d; TokenInformation
0x14000efab  lea     r14d, [r9+3]
0x14000efaf  mov     edx, r14d; TokenInformationClass
0x14000efb2  call    cs:__imp_GetTokenInformation
0x14000efb9  nop     dword ptr [rax+rax+00h]
0x14000efbe  mov     ecx, [rsp+2C0h+TokenInformationLength]; unsigned __int64
0x14000efc2  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x14000efc7  mov     r9d, [rsp+2C0h+TokenInformationLength]; TokenInformationLength
0x14000efcc  mov     rsi, rax
0x14000efcf  mov     rcx, [rsp+2C0h+TokenHandle]; TokenHandle
0x14000efd4  lea     rax, [rsp+2C0h+TokenInformationLength]
0x14000efd9  mov     r8, rsi; TokenInformation
0x14000efdc  mov     [rsp+2C0h+ReturnLength], rax; ReturnLength
0x14000efe1  mov     edx, r14d; TokenInformationClass
0x14000efe4  call    cs:__imp_GetTokenInformation
0x14000efeb  nop     dword ptr [rax+rax+00h]
0x14000eff0  test    eax, eax
0x14000eff2  jnz     short loc_14000F047
0x14000eff4  call    cs:__imp_GetCurrentThreadId
0x14000effb  nop     dword ptr [rax+rax+00h]
0x14000f000  mov     ebx, eax
0x14000f002  call    cs:__imp_GetLastError
0x14000f009  nop     dword ptr [rax+rax+00h]
0x14000f00e  mov     [rsp+2C0h+var_280], rdi
0x14000f013  mov     r9d, r15d
0x14000f016  mov     dword ptr [rsp+2C0h+var_288], ebx
0x14000f01a  xor     r8d, r8d
0x14000f01d  mov     [rsp+2C0h+var_290], 301h
0x14000f025  mov     edx, eax
0x14000f027  mov     [rsp+2C0h+var_298], r12
0x14000f02c  mov     [rsp+2C0h+ReturnLength], r13
0x14000f031  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14000f036  mov     [rsp+2C0h+var_248], rax
0x14000f03b  mov     rbx, rax
0x14000f03e  test    rax, rax
0x14000f041  jnz     loc_14000F2A3
0x14000f047  lea     r15, aFrsserviceRemo; "FrsService::RemoveDisabledPrivileges"
0x14000f04e  mov     r14d, edi
0x14000f051  lea     r12, aFsvc; "FSVC"
0x14000f058  mov     r13d, 4
0x14000f05e  cmp     [rsi], edi
0x14000f060  jbe     loc_14000F120
0x14000f066  lea     rbx, aFrsserviceRemo; "FrsService::RemoveDisabledPrivileges"
0x14000f06d  mov     eax, r14d
0x14000f070  lea     r15, [rax+rax*2]
0x14000f074  test    byte ptr [rsi+r15*4+0Ch], 2
0x14000f07a  jnz     loc_14000F108
0x14000f080  lea     r12, [rsi+r15*4]
0x14000f084  mov     [rsp+2C0h+TokenInformationLength+4], 104h
0x14000f08c  lea     rdx, [r12+4]; lpLuid
0x14000f091  mov     [rsi+r15*4+0Ch], r13d
0x14000f096  lea     r9, [rsp+2C0h+TokenInformationLength+4]; cchName
0x14000f09b  xor     ecx, ecx; lpSystemName
0x14000f09d  lea     r8, [rbp+1C0h+Name]; lpName
0x14000f0a1  call    cs:__imp_LookupPrivilegeNameW
0x14000f0a8  nop     dword ptr [rax+rax+00h]
0x14000f0ad  test    eax, eax
0x14000f0af  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14000f0b6  jnz     loc_14000F202
0x14000f0bc  test    rax, rax
0x14000f0bf  jz      short loc_14000F101
0x14000f0c1  cmp     [rax+40h], edi
0x14000f0c4  jz      short loc_14000F101
0x14000f0c6  cmp     [rax+38h], r13d
0x14000f0ca  jl      short loc_14000F101
0x14000f0cc  lea     rax, aFsvc; "FSVC"
0x14000f0d3  mov     [rsp+2C0h+var_268], rbx
0x14000f0d8  lea     r8, [rsi+8]
0x14000f0dc  mov     dword ptr [rsp+2C0h+var_260], 319h
0x14000f0e4  lea     r8, [r8+r15*4]
0x14000f0e8  mov     dword ptr [rsp+2C0h+var_260+4], r13d
0x14000f0ed  lea     r9, [r12+4]
0x14000f0f2  mov     [rsp+2C0h+var_258], rax
0x14000f0f7  lea     rcx, [rsp+2C0h+var_268]
0x14000f0fc  call    ??$DbgPrint@GJK@dbgobj@@QEAA_KPEBGAEBJAEBK@Z; dbgobj::DbgPrint<ushort,long,ulong>(ushort const *,long const &,ulong const &)
0x14000f101  lea     r12, aFsvc; "FSVC"
0x14000f108  inc     r14d
0x14000f10b  cmp     r14d, [rsi]
0x14000f10e  jb      loc_14000F06D
0x14000f114  mov     rbx, [rsp+2C0h+var_248]
0x14000f119  lea     r15, aFrsserviceRemo; "FrsService::RemoveDisabledPrivileges"
0x14000f120  mov     r9d, [rsp+2C0h+TokenInformationLength]; BufferLength
0x14000f125  mov     r8, rsi; NewState
0x14000f128  mov     rcx, [rsp+2C0h+TokenHandle]; TokenHandle
0x14000f12d  xor     edx, edx; DisableAllPrivileges
0x14000f12f  mov     [rsp+2C0h+var_298], rdi; ReturnLength
0x14000f134  mov     [rsp+2C0h+ReturnLength], rdi; PreviousState
0x14000f139  call    cs:__imp_AdjustTokenPrivileges
0x14000f140  nop     dword ptr [rax+rax+00h]
0x14000f145  test    eax, eax
0x14000f147  jnz     loc_14000F256
0x14000f14d  call    cs:__imp_GetCurrentThreadId
0x14000f154  nop     dword ptr [rax+rax+00h]
0x14000f159  mov     ebx, eax
0x14000f15b  call    cs:__imp_GetLastError
0x14000f162  nop     dword ptr [rax+rax+00h]
0x14000f167  mov     [rsp+2C0h+var_280], rdi
0x14000f16c  lea     rcx, aFrsserviceRemo_0; "FrsService::RemoveDisabledPrivileges"
0x14000f173  mov     dword ptr [rsp+2C0h+var_288], ebx
0x14000f177  lea     r13, aBaseFsRemotefs_103; "base\\fs\\remotefs\\frs\\src\\main\\frs"...
0x14000f17e  mov     [rsp+2C0h+var_290], 331h
0x14000f186  mov     r9d, 1
0x14000f18c  mov     [rsp+2C0h+var_298], rcx
0x14000f191  xor     r8d, r8d
0x14000f194  mov     edx, eax
0x14000f196  mov     [rsp+2C0h+ReturnLength], r13
0x14000f19b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14000f1a0  mov     rbx, rax
0x14000f1a3  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14000f1aa  test    rax, rax
0x14000f1ad  jz      loc_14000F29C
0x14000f1b3  cmp     [rax+40h], edi
0x14000f1b6  jz      loc_14000F29C
0x14000f1bc  cmp     dword ptr [rax+38h], 2
0x14000f1c0  jl      loc_14000F29C
0x14000f1c6  mov     eax, [rbx+4]
0x14000f1c9  lea     r8, [rsp+2C0h+TokenInformationLength+4]
0x14000f1ce  lea     rdx, aFailedToRemove; "Failed to remove privileges. Error:%d"
0x14000f1d5  mov     [rsp+2C0h+TokenInformationLength+4], eax
0x14000f1d9  lea     rcx, [rsp+2C0h+var_268]
0x14000f1de  mov     [rsp+2C0h+var_268], r15
0x14000f1e3  mov     dword ptr [rsp+2C0h+var_260], 332h
0x14000f1eb  mov     dword ptr [rsp+2C0h+var_260+4], 2
0x14000f1f3  mov     [rsp+2C0h+var_258], r12
0x14000f1f8  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x14000f1fd  jmp     loc_14000F29C
0x14000f202  test    rax, rax
0x14000f205  jz      loc_14000F101
0x14000f20b  cmp     [rax+40h], edi
0x14000f20e  jz      loc_14000F101
0x14000f214  lea     r12, aFsvc; "FSVC"
0x14000f21b  cmp     [rax+38h], r13d
0x14000f21f  jl      loc_14000F108
0x14000f225  lea     r8, [rbp+1C0h+Name]
0x14000f229  mov     [rsp+2C0h+var_268], rbx
0x14000f22e  lea     rdx, aPrivilegeSSetF; "Privilege %s set for removal"
0x14000f235  mov     dword ptr [rsp+2C0h+var_260], 31Fh
0x14000f23d  lea     rcx, [rsp+2C0h+var_268]
0x14000f242  mov     dword ptr [rsp+2C0h+var_260+4], r13d
0x14000f247  mov     [rsp+2C0h+var_258], r12
0x14000f24c  call    ??$DbgPrint@G$$BY0CH@G@dbgobj@@QEAA_KPEBGAEAY0CH@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [39]>(ushort const *,ushort const (&)[39])
0x14000f251  jmp     loc_14000F108
0x14000f256  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14000f25d  test    rax, rax
0x14000f260  jz      short loc_14000F295
0x14000f262  cmp     [rax+40h], edi
0x14000f265  jz      short loc_14000F295
0x14000f267  cmp     [rax+38h], r13d
0x14000f26b  jl      short loc_14000F295
0x14000f26d  lea     rdx, aPrivilegesRemo; "Privileges removed successfully"
0x14000f274  mov     [rsp+2C0h+var_268], r15
0x14000f279  lea     rcx, [rsp+2C0h+var_268]
0x14000f27e  mov     dword ptr [rsp+2C0h+var_260], 336h
0x14000f286  mov     dword ptr [rsp+2C0h+var_260+4], r13d
0x14000f28b  mov     [rsp+2C0h+var_258], r12
0x14000f290  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x14000f295  lea     r13, aBaseFsRemotefs_103; "base\\fs\\remotefs\\frs\\src\\main\\frs"...
0x14000f29c  lea     r12, aFrsserviceRemo_0; "FrsService::RemoveDisabledPrivileges"
0x14000f2a3  mov     rcx, [rsp+2C0h+TokenHandle]; hObject
0x14000f2a8  lea     rax, [rcx-1]
0x14000f2ac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000f2b0  ja      short loc_14000F2BE
0x14000f2b2  call    cs:__imp_CloseHandle
0x14000f2b9  nop     dword ptr [rax+rax+00h]
0x14000f2be  mov     rcx, rsi; Block
0x14000f2c1  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x14000f2c6  test    rbx, rbx
0x14000f2c9  jz      short loc_14000F304
0x14000f2cb  call    cs:__imp_GetCurrentThreadId
0x14000f2d2  nop     dword ptr [rax+rax+00h]
0x14000f2d7  mov     r9d, [rbx]
0x14000f2da  mov     r8d, [rbx+8]
0x14000f2de  mov     edx, [rbx+4]
0x14000f2e1  mov     [rsp+2C0h+var_280], rbx
0x14000f2e6  mov     dword ptr [rsp+2C0h+var_288], eax
0x14000f2ea  mov     [rsp+2C0h+var_290], 340h
0x14000f2f2  mov     [rsp+2C0h+var_298], r12
0x14000f2f7  mov     [rsp+2C0h+ReturnLength], r13
0x14000f2fc  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14000f301  mov     rdi, rax
0x14000f304  mov     rax, rdi
0x14000f307  mov     rcx, [rbp+1C0h+var_30]
0x14000f30e  xor     rcx, rsp; StackCookie
0x14000f311  call    __security_check_cookie
0x14000f316  lea     r11, [rsp+2C0h+var_20]
0x14000f31e  mov     rbx, [r11+30h]
0x14000f322  mov     rsi, [r11+38h]
0x14000f326  mov     rdi, [r11+40h]
0x14000f32a  mov     rsp, r11
0x14000f32d  pop     r15
0x14000f32f  pop     r14
0x14000f331  pop     r13
0x14000f333  pop     r12
0x14000f335  pop     rbp
0x14000f336  retn
```
