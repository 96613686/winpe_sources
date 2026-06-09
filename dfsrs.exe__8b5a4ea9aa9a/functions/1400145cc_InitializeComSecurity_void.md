# InitializeComSecurity(void)

- ea: `0x1400145cc`
- end: `0x140014b6c`
- name: `?InitializeComSecurity@@YAPEAVFrsStatus@@XZ`
- size: `1440`
- prototype: `struct FrsStatus *(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140015408`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000c910`
- `0x14000cb00`
- `0x1400145cc`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140014ae9`
- `KERNEL32!LocalFree` at `0x140014ae9`
- `KERNEL32!GetLastError` at `0x140014683`
- `KERNEL32!GetLastError` at `0x1400146f2`
- `KERNEL32!GetLastError` at `0x140014783`
- `KERNEL32!GetLastError` at `0x1400148a5`
- `KERNEL32!GetLastError` at `0x14001490f`
- `KERNEL32!GetLastError` at `0x14001497d`
- `KERNEL32!GetLastError` at `0x140014683`
- `KERNEL32!GetLastError` at `0x1400146f2`
- `KERNEL32!GetLastError` at `0x140014783`
- `KERNEL32!GetLastError` at `0x1400148a5`
- `KERNEL32!GetLastError` at `0x14001490f`
- `KERNEL32!GetLastError` at `0x14001497d`
- `KERNEL32!GetCurrentThreadId` at `0x140014675`
- `KERNEL32!GetCurrentThreadId` at `0x1400146e4`
- `KERNEL32!GetCurrentThreadId` at `0x140014775`
- `KERNEL32!GetCurrentThreadId` at `0x14001482b`
- `KERNEL32!GetCurrentThreadId` at `0x140014897`
- `KERNEL32!GetCurrentThreadId` at `0x140014901`
- `KERNEL32!GetCurrentThreadId` at `0x14001496f`
- `KERNEL32!GetCurrentThreadId` at `0x140014aa6`
- `KERNEL32!GetCurrentThreadId` at `0x140014aff`
- `KERNEL32!GetCurrentThreadId` at `0x140014675`
- `KERNEL32!GetCurrentThreadId` at `0x1400146e4`
- `KERNEL32!GetCurrentThreadId` at `0x140014775`
- `KERNEL32!GetCurrentThreadId` at `0x14001482b`
- `KERNEL32!GetCurrentThreadId` at `0x140014897`
- `KERNEL32!GetCurrentThreadId` at `0x140014901`
- `KERNEL32!GetCurrentThreadId` at `0x14001496f`
- `KERNEL32!GetCurrentThreadId` at `0x140014aa6`
- `KERNEL32!GetCurrentThreadId` at `0x140014aff`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140014657`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140014657`
- `ADVAPI32!CreateWellKnownSid` at `0x1400146d4`
- `ADVAPI32!CreateWellKnownSid` at `0x140014765`
- `ADVAPI32!CreateWellKnownSid` at `0x1400146d4`
- `ADVAPI32!CreateWellKnownSid` at `0x140014765`
- `ADVAPI32!SetEntriesInAclW` at `0x140014819`
- `ADVAPI32!SetEntriesInAclW` at `0x140014819`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140014887`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140014887`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400148f1`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400148f1`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14001495f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14001495f`
- `ole32!CoInitializeSecurity` at `0x140014a50`
- `ole32!CoInitializeSecurity` at `0x140014a50`
- `ole32!CoInitializeEx` at `0x1400149c1`
- `ole32!CoInitializeEx` at `0x1400149c1`

## string_xrefs

- `0x140014663`: `InitializeComSecurity`
- `0x1400149d6`: `InitializeComSecurity`
- `0x1400149fe`: `Successfully initialized COM runtime.`
- `0x140014a84`: `Failed to initialize security. Error:0x%x`

## pseudocode

```c
struct FrsStatus *InitializeComSecurity(void)
{
  __int64 v0; // rdi
  unsigned int *v1; // rbx
  DWORD v2; // ebx
  DWORD v3; // eax
  __int64 v4; // rcx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v7; // rcx
  unsigned int v8; // esi
  __int64 v9; // r14
  _BYTE *v10; // r15
  DWORD v11; // ebx
  DWORD v12; // eax
  __int64 v13; // rax
  DWORD v14; // esi
  DWORD v15; // eax
  __int64 v16; // rcx
  DWORD v17; // ebx
  DWORD v18; // eax
  __int64 v19; // rcx
  DWORD v20; // ebx
  DWORD v21; // eax
  __int64 v22; // rcx
  DWORD v23; // ebx
  DWORD v24; // eax
  __int64 v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  DWORD v28; // eax
  __int64 v29; // rcx
  DWORD cbSid[2]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+88h] [rbp-80h]
  WELL_KNOWN_SID_TYPE WellKnownSidType[2]; // [rsp+90h] [rbp-78h] BYREF
  int v35; // [rsp+98h] [rbp-70h]
  int v36; // [rsp+9Ch] [rbp-6Ch]
  const wchar_t *v37; // [rsp+A0h] [rbp-68h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries[3]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE pSid[288]; // [rsp+138h] [rbp+30h] BYREF

  v0 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  cbSid[0] = 0;
  v33 = 0;
  pListOfExplicitEntries[0].grfAccessPermissions = 0;
  v1 = 0;
  memset_0(&pListOfExplicitEntries[0].grfAccessMode, 0, 0x8Cu);
  WellKnownSidType[0] = WinBuiltinBackupOperatorsSid;
  v35 = 22;
  WellKnownSidType[1] = WinBuiltinAdministratorsSid;
  if ( InitializeSecurityDescriptor(&pSecurityDescriptor[8], 1u)
    || (v2 = GetCurrentThreadId(),
        v3 = GetLastError(),
        (v1 = (unsigned int *)FrsStatusList::PushNewError(
                                v4,
                                v3,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                                "InitializeComSecurity",
                                368,
                                v2,
                                0)) == 0) )
  {
    cbSid[0] = 68;
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LastError = GetLastError();
      v1 = (unsigned int *)FrsStatusList::PushNewError(
                             v7,
                             LastError,
                             0,
                             1,
                             "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                             "InitializeComSecurity",
                             378,
                             CurrentThreadId,
                             0);
    }
  }
  v8 = 0;
  if ( !v1 )
  {
    while ( v8 < 3 )
    {
      v9 = v8;
      cbSid[0] = 68;
      v10 = &pSid[68 * v8 + 80];
      if ( !CreateWellKnownSid(WellKnownSidType[v8], 0, v10, cbSid) )
      {
        v11 = GetCurrentThreadId();
        v12 = GetLastError();
        v1 = (unsigned int *)FrsStatusList::PushNewError(
                               "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                               v12,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                               "InitializeComSecurity",
                               392,
                               v11,
                               0);
      }
      ++v8;
      v13 = v9;
      *(_QWORD *)&pListOfExplicitEntries[v13].Trustee.MultipleTrusteeOperation = 0;
      pListOfExplicitEntries[v13].Trustee.pMultipleTrustee = 0;
      pListOfExplicitEntries[v13].Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
      pListOfExplicitEntries[v13].Trustee.ptstrName = (LPWCH)v10;
      pListOfExplicitEntries[v13].grfAccessMode = GRANT_ACCESS;
      pListOfExplicitEntries[v13].grfAccessPermissions = 1;
      pListOfExplicitEntries[v13].grfInheritance = 3;
      if ( v1 )
        goto LABEL_30;
    }
    v14 = SetEntriesInAclW(3u, pListOfExplicitEntries, 0, (PACL *)pSecurityDescriptor);
    if ( !v14
      || (v15 = GetCurrentThreadId(),
          (v1 = (unsigned int *)FrsStatusList::PushNewError(
                                  v16,
                                  v14,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                                  "InitializeComSecurity",
                                  414,
                                  v15,
                                  0)) == 0) )
    {
      if ( SetSecurityDescriptorOwner(&pSecurityDescriptor[8], pSid, 0)
        || (v17 = GetCurrentThreadId(),
            v18 = GetLastError(),
            (v1 = (unsigned int *)FrsStatusList::PushNewError(
                                    v19,
                                    v18,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                                    "InitializeComSecurity",
                                    423,
                                    v17,
                                    0)) == 0) )
      {
        if ( SetSecurityDescriptorGroup(&pSecurityDescriptor[8], pSid, 0)
          || (v20 = GetCurrentThreadId(),
              v21 = GetLastError(),
              (v1 = (unsigned int *)FrsStatusList::PushNewError(
                                      v22,
                                      v21,
                                      0,
                                      1,
                                      "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                                      "InitializeComSecurity",
                                      432,
                                      v20,
                                      0)) == 0) )
        {
          if ( SetSecurityDescriptorDacl(&pSecurityDescriptor[8], 1, *(PACL *)pSecurityDescriptor, 0)
            || (v23 = GetCurrentThreadId(),
                v24 = GetLastError(),
                (v1 = (unsigned int *)FrsStatusList::PushNewError(
                                        v25,
                                        v24,
                                        0,
                                        1,
                                        "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                                        "InitializeComSecurity",
                                        441,
                                        v23,
                                        0)) == 0) )
          {
            cbSid[1] = CoInitializeEx(0, 0);
            if ( (cbSid[1] & 0x80000000) != 0 )
              goto LABEL_27;
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              *(_QWORD *)WellKnownSidType = L"InitializeComSecurity";
              v35 = 448;
              v36 = 4;
              v37 = L"MAIN";
              dbgobj::DbgPrint<unsigned short>(WellKnownSidType, L"Successfully initialized COM runtime.");
            }
            cbSid[1] = CoInitializeSecurity(&pSecurityDescriptor[8], -1, 0, 0, 6u, 3u, 0, 0x2040u, 0);
            if ( (cbSid[1] & 0x80000000) != 0 )
            {
LABEL_27:
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
              {
                *(_QWORD *)WellKnownSidType = L"InitializeComSecurity";
                v35 = 462;
                v36 = 2;
                v37 = L"MAIN";
                dbgobj::DbgPrint<unsigned short,unsigned int>(
                  WellKnownSidType,
                  L"Failed to initialize security. Error:0x%x",
                  &cbSid[1]);
              }
              v26 = GetCurrentThreadId();
              v1 = (unsigned int *)FrsStatusList::PushNewError(
                                     v27,
                                     cbSid[1],
                                     0,
                                     4,
                                     "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                                     "InitializeComSecurity",
                                     463,
                                     v26,
                                     0);
            }
          }
        }
      }
    }
  }
LABEL_30:
  if ( *(_QWORD *)pSecurityDescriptor )
  {
    LocalFree(*(HLOCAL *)pSecurityDescriptor);
    *(_QWORD *)pSecurityDescriptor = 0;
  }
  if ( v1 )
  {
    v28 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v29,
                                 v1[1],
                                 v1[2],
                                 *v1,
                                 "base\\fs\\remotefs\\frs\\src\\main\\main.cpp",
                                 "InitializeComSecurity",
                                 472,
                                 v28,
                                 v1);
  }
  return (struct FrsStatus *)v0;
}

```

## disassembly

```asm
0x1400145cc  mov     rax, rsp
0x1400145cf  mov     [rax+8], rbx
0x1400145d3  mov     [rax+10h], rsi
0x1400145d7  mov     [rax+18h], rdi
0x1400145db  push    rbp
0x1400145dc  push    r12
0x1400145de  push    r13
0x1400145e0  push    r14
0x1400145e2  push    r15
0x1400145e4  lea     rbp, [rax-188h]
0x1400145eb  sub     rsp, 260h
0x1400145f2  mov     rax, cs:__security_cookie
0x1400145f9  xor     rax, rsp
0x1400145fc  mov     [rbp+180h+var_30], rax
0x140014603  xor     edi, edi
0x140014605  lea     rcx, [rbp+180h+pListOfExplicitEntries.grfAccessMode]; void *
0x140014609  xorps   xmm0, xmm0
0x14001460c  mov     qword ptr [rsp+280h+pSecurityDescriptor], rdi
0x140014611  xor     eax, eax
0x140014613  mov     [rsp+280h+cbSid], edi
0x140014617  xor     edx, edx; Val
0x140014619  mov     [rbp+180h+var_200], rax
0x14001461d  mov     r8d, 8Ch; Size
0x140014623  mov     [rbp+180h+pListOfExplicitEntries.grfAccessPermissions], edi
0x140014626  mov     ebx, edi
0x140014628  movups  [rsp+280h+pSecurityDescriptor+8], xmm0
0x14001462d  movups  [rsp+280h+var_218+8], xmm0
0x140014632  call    memset_0
0x140014637  lea     r12d, [rdi+1]
0x14001463b  mov     [rbp+180h+WellKnownSidType], 21h ; '!'
0x140014642  lea     esi, [rdi+1Ah]
0x140014645  mov     [rbp+180h+var_1F0], 16h
0x14001464c  mov     edx, r12d; dwRevision
0x14001464f  mov     [rbp+180h+WellKnownSidType+4], esi
0x140014652  lea     rcx, [rsp+280h+pSecurityDescriptor+8]; pSecurityDescriptor
0x140014657  call    cs:__imp_InitializeSecurityDescriptor
0x14001465e  nop     dword ptr [rax+rax+00h]
0x140014663  lea     r13, aInitializecoms; "InitializeComSecurity"
0x14001466a  lea     r14, aBaseFsRemotefs_6; "base\\fs\\remotefs\\frs\\src\\main\\mai"...
0x140014671  test    eax, eax
0x140014673  jnz     short loc_1400146BF
0x140014675  call    cs:__imp_GetCurrentThreadId
0x14001467c  nop     dword ptr [rax+rax+00h]
0x140014681  mov     ebx, eax
0x140014683  call    cs:__imp_GetLastError
0x14001468a  nop     dword ptr [rax+rax+00h]
0x14001468f  mov     [rsp+280h+pReserved3], rdi
0x140014694  mov     r9d, r12d
0x140014697  mov     [rsp+280h+dwCapabilities], ebx
0x14001469b  xor     r8d, r8d
0x14001469e  mov     dword ptr [rsp+280h+pAuthList], 170h
0x1400146a6  mov     edx, eax
0x1400146a8  mov     qword ptr [rsp+280h+dwImpLevel], r13
0x1400146ad  mov     qword ptr [rsp+280h+dwAuthnLevel], r14
0x1400146b2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400146b7  mov     rbx, rax
0x1400146ba  test    rax, rax
0x1400146bd  jnz     short loc_140014729
0x1400146bf  lea     r9, [rsp+280h+cbSid]; cbSid
0x1400146c4  mov     [rsp+280h+cbSid], 44h ; 'D'
0x1400146cc  lea     r8, [rbp+180h+pSid]; pSid
0x1400146d0  xor     edx, edx; DomainSid
0x1400146d2  mov     ecx, esi; WellKnownSidType
0x1400146d4  call    cs:__imp_CreateWellKnownSid
0x1400146db  nop     dword ptr [rax+rax+00h]
0x1400146e0  test    eax, eax
0x1400146e2  jnz     short loc_140014729
0x1400146e4  call    cs:__imp_GetCurrentThreadId
0x1400146eb  nop     dword ptr [rax+rax+00h]
0x1400146f0  mov     ebx, eax
0x1400146f2  call    cs:__imp_GetLastError
0x1400146f9  nop     dword ptr [rax+rax+00h]
0x1400146fe  mov     [rsp+280h+pReserved3], rdi
0x140014703  mov     r9d, r12d
0x140014706  mov     [rsp+280h+dwCapabilities], ebx
0x14001470a  xor     r8d, r8d
0x14001470d  mov     dword ptr [rsp+280h+pAuthList], 17Ah
0x140014715  mov     edx, eax
0x140014717  mov     qword ptr [rsp+280h+dwImpLevel], r13
0x14001471c  mov     qword ptr [rsp+280h+dwAuthnLevel], r14
0x140014721  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140014726  mov     rbx, rax
0x140014729  mov     esi, edi
0x14001472b  test    rbx, rbx
0x14001472e  jnz     loc_140014ADF
0x140014734  cmp     esi, 3
0x140014737  jnb     loc_140014809
0x14001473d  mov     r14d, esi
0x140014740  lea     r15, [rbp+180h+var_100]
0x140014747  imul    rax, r14, 44h ; 'D'
0x14001474b  lea     r9, [rsp+280h+cbSid]; cbSid
0x140014750  mov     [rsp+280h+cbSid], 44h ; 'D'
0x140014758  mov     ecx, [rbp+r14*4+180h+WellKnownSidType]; WellKnownSidType
0x14001475d  add     r15, rax
0x140014760  mov     r8, r15; pSid
0x140014763  xor     edx, edx; DomainSid
0x140014765  call    cs:__imp_CreateWellKnownSid
0x14001476c  nop     dword ptr [rax+rax+00h]
0x140014771  test    eax, eax
0x140014773  jnz     short loc_1400147C1
0x140014775  call    cs:__imp_GetCurrentThreadId
0x14001477c  nop     dword ptr [rax+rax+00h]
0x140014781  mov     ebx, eax
0x140014783  call    cs:__imp_GetLastError
0x14001478a  nop     dword ptr [rax+rax+00h]
0x14001478f  mov     [rsp+280h+pReserved3], rdi
0x140014794  lea     rcx, aBaseFsRemotefs_6; "base\\fs\\remotefs\\frs\\src\\main\\mai"...
0x14001479b  mov     [rsp+280h+dwCapabilities], ebx
0x14001479f  mov     r9d, r12d
0x1400147a2  mov     dword ptr [rsp+280h+pAuthList], 188h
0x1400147aa  xor     r8d, r8d
0x1400147ad  mov     qword ptr [rsp+280h+dwImpLevel], r13
0x1400147b2  mov     edx, eax
0x1400147b4  mov     qword ptr [rsp+280h+dwAuthnLevel], rcx
0x1400147b9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400147be  mov     rbx, rax
0x1400147c1  lea     rax, [r14+r14*2]
0x1400147c5  add     esi, r12d
0x1400147c8  add     rax, rax
0x1400147cb  mov     qword ptr [rbp+rax*8+180h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rdi
0x1400147d0  mov     [rbp+rax*8+180h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rdi
0x1400147d5  mov     [rbp+rax*8+180h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1400147dd  mov     [rbp+rax*8+180h+pListOfExplicitEntries.Trustee.ptstrName], r15
0x1400147e2  mov     [rbp+rax*8+180h+pListOfExplicitEntries.grfAccessMode], r12d
0x1400147e7  mov     [rbp+rax*8+180h+pListOfExplicitEntries.grfAccessPermissions], r12d
0x1400147ec  mov     [rbp+rax*8+180h+pListOfExplicitEntries.grfInheritance], 3
0x1400147f4  test    rbx, rbx
0x1400147f7  jz      loc_140014734
0x1400147fd  lea     r14, aBaseFsRemotefs_6; "base\\fs\\remotefs\\frs\\src\\main\\mai"...
0x140014804  jmp     loc_140014ADF
0x140014809  xor     r8d, r8d; OldAcl
0x14001480c  lea     r9, [rsp+280h+pSecurityDescriptor]; NewAcl
0x140014811  lea     rdx, [rbp+180h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140014815  lea     ecx, [r8+3]; cCountOfExplicitEntries
0x140014819  call    cs:__imp_SetEntriesInAclW
0x140014820  nop     dword ptr [rax+rax+00h]
0x140014825  mov     esi, eax
0x140014827  test    eax, eax
0x140014829  jz      short loc_140014874
0x14001482b  call    cs:__imp_GetCurrentThreadId
0x140014832  nop     dword ptr [rax+rax+00h]
0x140014837  mov     [rsp+280h+pReserved3], rdi
0x14001483c  lea     r14, aBaseFsRemotefs_6; "base\\fs\\remotefs\\frs\\src\\main\\mai"...
0x140014843  mov     [rsp+280h+dwCapabilities], eax
0x140014847  mov     r9d, r12d
0x14001484a  mov     dword ptr [rsp+280h+pAuthList], 19Eh
0x140014852  xor     r8d, r8d
0x140014855  mov     qword ptr [rsp+280h+dwImpLevel], r13
0x14001485a  mov     edx, esi
0x14001485c  mov     qword ptr [rsp+280h+dwAuthnLevel], r14
0x140014861  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140014866  mov     rbx, rax
0x140014869  test    rax, rax
0x14001486c  jnz     loc_140014ADF
0x140014872  jmp     short loc_14001487B
0x140014874  lea     r14, aBaseFsRemotefs_6; "base\\fs\\remotefs\\frs\\src\\main\\mai"...
0x14001487b  xor     r8d, r8d; bOwnerDefaulted
0x14001487e  lea     rdx, [rbp+180h+pSid]; pOwner
0x140014882  lea     rcx, [rsp+280h+pSecurityDescriptor+8]; pSecurityDescriptor
0x140014887  call    cs:__imp_SetSecurityDescriptorOwner
0x14001488e  nop     dword ptr [rax+rax+00h]
0x140014893  test    eax, eax
0x140014895  jnz     short loc_1400148E5
0x140014897  call    cs:__imp_GetCurrentThreadId
0x14001489e  nop     dword ptr [rax+rax+00h]
0x1400148a3  mov     ebx, eax
0x1400148a5  call    cs:__imp_GetLastError
0x1400148ac  nop     dword ptr [rax+rax+00h]
0x1400148b1  mov     [rsp+280h+pReserved3], rdi
0x1400148b6  mov     r9d, r12d
0x1400148b9  mov     [rsp+280h+dwCapabilities], ebx
0x1400148bd  xor     r8d, r8d
0x1400148c0  mov     dword ptr [rsp+280h+pAuthList], 1A7h
0x1400148c8  mov     edx, eax
0x1400148ca  mov     qword ptr [rsp+280h+dwImpLevel], r13
0x1400148cf  mov     qword ptr [rsp+280h+dwAuthnLevel], r14
0x1400148d4  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400148d9  mov     rbx, rax
0x1400148dc  test    rax, rax
0x1400148df  jnz     loc_140014ADF
0x1400148e5  xor     r8d, r8d; bGroupDefaulted
0x1400148e8  lea     rdx, [rbp+180h+pSid]; pGroup
0x1400148ec  lea     rcx, [rsp+280h+pSecurityDescriptor+8]; pSecurityDescriptor
0x1400148f1  call    cs:__imp_SetSecurityDescriptorGroup
0x1400148f8  nop     dword ptr [rax+rax+00h]
0x1400148fd  test    eax, eax
0x1400148ff  jnz     short loc_14001494F
0x140014901  call    cs:__imp_GetCurrentThreadId
0x140014908  nop     dword ptr [rax+rax+00h]
0x14001490d  mov     ebx, eax
0x14001490f  call    cs:__imp_GetLastError
0x140014916  nop     dword ptr [rax+rax+00h]
0x14001491b  mov     [rsp+280h+pReserved3], rdi
0x140014920  mov     r9d, r12d
0x140014923  mov     [rsp+280h+dwCapabilities], ebx
0x140014927  xor     r8d, r8d
0x14001492a  mov     dword ptr [rsp+280h+pAuthList], 1B0h
0x140014932  mov     edx, eax
0x140014934  mov     qword ptr [rsp+280h+dwImpLevel], r13
0x140014939  mov     qword ptr [rsp+280h+dwAuthnLevel], r14
0x14001493e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140014943  mov     rbx, rax
0x140014946  test    rax, rax
0x140014949  jnz     loc_140014ADF
0x14001494f  mov     r8, qword ptr [rsp+280h+pSecurityDescriptor]; pDacl
0x140014954  lea     rcx, [rsp+280h+pSecurityDescriptor+8]; pSecurityDescriptor
0x140014959  xor     r9d, r9d; bDaclDefaulted
0x14001495c  mov     edx, r12d; bDaclPresent
0x14001495f  call    cs:__imp_SetSecurityDescriptorDacl
0x140014966  nop     dword ptr [rax+rax+00h]
0x14001496b  test    eax, eax
0x14001496d  jnz     short loc_1400149BD
0x14001496f  call    cs:__imp_GetCurrentThreadId
0x140014976  nop     dword ptr [rax+rax+00h]
0x14001497b  mov     ebx, eax
0x14001497d  call    cs:__imp_GetLastError
0x140014984  nop     dword ptr [rax+rax+00h]
0x140014989  mov     [rsp+280h+pReserved3], rdi
0x14001498e  mov     r9d, r12d
0x140014991  mov     [rsp+280h+dwCapabilities], ebx
0x140014995  xor     r8d, r8d
0x140014998  mov     dword ptr [rsp+280h+pAuthList], 1B9h
0x1400149a0  mov     edx, eax
0x1400149a2  mov     qword ptr [rsp+280h+dwImpLevel], r13
0x1400149a7  mov     qword ptr [rsp+280h+dwAuthnLevel], r14
0x1400149ac  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400149b1  mov     rbx, rax
0x1400149b4  test    rax, rax
0x1400149b7  jnz     loc_140014ADF
0x1400149bd  xor     edx, edx; dwCoInit
0x1400149bf  xor     ecx, ecx; pvReserved
0x1400149c1  call    cs:__imp_CoInitializeEx
0x1400149c8  nop     dword ptr [rax+rax+00h]
0x1400149cd  mov     [rsp+280h+cbSid+4], eax
0x1400149d1  mov     esi, 4
0x1400149d6  lea     r15, aInitializecoms_0; "InitializeComSecurity"
0x1400149dd  lea     r12, aMain_1; "MAIN"
0x1400149e4  test    eax, eax
0x1400149e6  js      short loc_140014A64
0x1400149e8  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400149ef  test    rax, rax
0x1400149f2  jz      short loc_140014A20
0x1400149f4  cmp     [rax+40h], edi
0x1400149f7  jz      short loc_140014A20
0x1400149f9  cmp     [rax+38h], esi
0x1400149fc  jl      short loc_140014A20
0x1400149fe  lea     rdx, aSuccessfullyIn; "Successfully initialized COM runtime."
0x140014a05  mov     qword ptr [rbp+180h+WellKnownSidType], r15
0x140014a09  lea     rcx, [rbp+180h+WellKnownSidType]
0x140014a0d  mov     [rbp+180h+var_1F0], 1C0h
0x140014a14  mov     [rbp+180h+var_1EC], esi
0x140014a17  mov     [rbp+180h+var_1E8], r12
0x140014a1b  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140014a20  mov     [rsp+280h+pReserved3], rdi; pReserved3
0x140014a25  lea     rcx, [rsp+280h+pSecurityDescriptor+8]; pSecDesc
0x140014a2a  mov     [rsp+280h+dwCapabilities], 2040h; dwCapabilities
0x140014a32  xor     r9d, r9d; pReserved1
0x140014a35  mov     [rsp+280h+pAuthList], rdi; pAuthList
0x140014a3a  xor     r8d, r8d; asAuthSvc
0x140014a3d  mov     [rsp+280h+dwImpLevel], 3; dwImpLevel
0x140014a45  or      edx, 0FFFFFFFFh; cAuthSvc
0x140014a48  mov     [rsp+280h+dwAuthnLevel], 6; dwAuthnLevel
0x140014a50  call    cs:__imp_CoInitializeSecurity
0x140014a57  nop     dword ptr [rax+rax+00h]
0x140014a5c  mov     [rsp+280h+cbSid+4], eax
0x140014a60  test    eax, eax
0x140014a62  jns     short loc_140014ADF
0x140014a64  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140014a6b  test    rax, rax
0x140014a6e  jz      short loc_140014AA6
0x140014a70  cmp     [rax+40h], edi
0x140014a73  jz      short loc_140014AA6
0x140014a75  cmp     dword ptr [rax+38h], 2
0x140014a79  jl      short loc_140014AA6
0x140014a7b  lea     r8, [rsp+280h+cbSid+4]
0x140014a80  mov     qword ptr [rbp+180h+WellKnownSidType], r15
0x140014a84  lea     rdx, aFailedToInitia; "Failed to initialize security. Error:0x"...
0x140014a8b  mov     [rbp+180h+var_1F0], 1CEh
0x140014a92  lea     rcx, [rbp+180h+WellKnownSidType]
0x140014a96  mov     [rbp+180h+var_1EC], 2
0x140014a9d  mov     [rbp+180h+var_1E8], r12
0x140014aa1  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x140014aa6  call    cs:__imp_GetCurrentThreadId
0x140014aad  nop     dword ptr [rax+rax+00h]
0x140014ab2  mov     edx, [rsp+280h+cbSid+4]
0x140014ab6  mov     r9d, esi
0x140014ab9  mov     [rsp+280h+pReserved3], rdi
0x140014abe  xor     r8d, r8d
0x140014ac1  mov     [rsp+280h+dwCapabilities], eax
0x140014ac5  mov     dword ptr [rsp+280h+pAuthList], 1CFh
0x140014acd  mov     qword ptr [rsp+280h+dwImpLevel], r13
0x140014ad2  mov     qword ptr [rsp+280h+dwAuthnLevel], r14
0x140014ad7  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140014adc  mov     rbx, rax
0x140014adf  mov     rcx, qword ptr [rsp+280h+pSecurityDescriptor]; hMem
0x140014ae4  test    rcx, rcx
0x140014ae7  jz      short loc_140014AFA
0x140014ae9  call    cs:__imp_LocalFree
0x140014af0  nop     dword ptr [rax+rax+00h]
0x140014af5  mov     qword ptr [rsp+280h+pSecurityDescriptor], rdi
  ... truncated ...
```
