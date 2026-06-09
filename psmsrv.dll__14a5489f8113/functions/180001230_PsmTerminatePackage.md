# PsmTerminatePackage

- ea: `0x180001230`
- end: `0x180001579`
- name: `PsmTerminatePackage`
- size: `841`
- prototype: `__int64 __fastcall(PSID pSid, char, PCWSTR packageFullName)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x180001230`
- `0x180001580`
- `0x1800017b0`
- `0x1800032a0`
- `0x1800092b4`
- `0x18000b1d0`
- `0x18000d010`
- `0x1800114d0`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001ea9c`
- `0x18001eb88`
- `0x18001ed90`
- `0x18001ef34`
- `0x180025460`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800014a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800014a3`
- `ntdll!RtlFreeHeap` at `0x180001378`
- `ntdll!RtlFreeHeap` at `0x180001378`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001416`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001416`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000132e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000132e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001382`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001382`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800013fb`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800013fb`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180001496`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetPackageFullNameFromKey` at `0x180001496`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000129f`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000129f`
- `ext-ms-win-core-psm-service-l1-1-2!PsmHamTerminatePackage` at `0x180001311`
- `ext-ms-win-core-psm-service-l1-1-2!PsmHamTerminatePackage` at `0x180001311`

## pseudocode

```c
__int64 __fastcall PsmTerminatePackage(PSID pSid, unsigned int a2, PCWSTR packageFullName)
{
  const WCHAR *v3; // r12
  PSID v5; // rdi
  LONG IsPackageFamilyNameEnabled; // eax
  __int64 v7; // r8
  unsigned int v8; // ebx
  bool v9; // cc
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 **v13; // rdx
  char *ManagerContext; // rax
  char *v15; // r14
  __int64 *UserContext; // rsi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r8
  char v21; // r12
  volatile signed __int32 *NextApplication; // rdi
  PCWSTR v23; // r14
  __int64 v24; // r13
  int v25; // edx
  int v26; // r8d
  int v27; // eax
  int v28; // r8d
  char v29[8]; // [rsp+28h] [rbp-D8h]
  UINT32 packageFamilyNameLength; // [rsp+44h] [rbp-BCh] BYREF
  PCWSTR v31; // [rsp+48h] [rbp-B8h]
  PVOID P; // [rsp+50h] [rbp-B0h]
  PSID v33; // [rsp+58h] [rbp-A8h]
  WCHAR packageFamilyName[72]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v35[256]; // [rsp+F0h] [rbp-10h] BYREF

  v3 = packageFullName;
  v31 = packageFullName;
  v33 = pSid;
  v5 = pSid;
  memset_0(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength = 65;
  IsPackageFamilyNameEnabled = PackageFamilyNameFromFullName(v3, &packageFamilyNameLength, packageFamilyName);
  v8 = IsPackageFamilyNameEnabled;
  v9 = IsPackageFamilyNameEnabled <= 0;
  if ( IsPackageFamilyNameEnabled
    || (IsPackageFamilyNameEnabled = HamOptInIsPackageFamilyNameEnabledEx(packageFamilyName),
        v8 = IsPackageFamilyNameEnabled,
        v9 = IsPackageFamilyNameEnabled <= 0,
        IsPackageFamilyNameEnabled) )
  {
    if ( !v9 )
      v8 = (unsigned __int16)IsPackageFamilyNameEnabled | 0xC0070000;
    goto LABEL_4;
  }
  ManagerContext = (char *)PsmpFindOrCreateManagerContext(0, a2);
  P = ManagerContext;
  v15 = ManagerContext;
  if ( ManagerContext )
  {
    RtlAcquireSRWLockShared(ManagerContext + 8);
    UserContext = PsmpFindUserContext((__int64)v15, a2, v5);
    RtlReleaseSRWLockShared(v15 + 8, v17, v18, v19);
    if ( !UserContext )
    {
      v8 = -1073741772;
      PsmpDereferenceManagerContext(v15);
      goto LABEL_16;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_S_sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Eu, v20, v3, (char *)v5, a2);
    v21 = 0;
    v8 = 0;
    NextApplication = PsmpGetNextApplication((__int64)UserContext, 0);
    if ( !NextApplication )
      goto LABEL_39;
    v23 = v31;
    do
    {
      v24 = *((_QWORD *)NextApplication + 1);
      packageFamilyNameLength = 256;
      PsmGetPackageFullNameFromKey(v24, v35, &packageFamilyNameLength);
      if ( !(unsigned int)_o__wcsicmp(v35, v23) )
      {
        v21 = 1;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_iS(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v26, *((_QWORD *)NextApplication + 12), v24);
        if ( *((_QWORD *)NextApplication + 24) && !*((_DWORD *)NextApplication + 86) )
          PsmpTraceLogTerminateActiveMixedJob(NextApplication);
        v27 = PsmpChangeApplicationState((__int64)NextApplication, 0, 0, 6u, 6, 0);
        if ( v27 < 0 )
        {
          v8 = v27;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_iSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v28, *((_QWORD *)NextApplication + 12), v24, v27);
        }
      }
      NextApplication = PsmpGetNextApplication((__int64)UserContext, (__int64)NextApplication);
    }
    while ( NextApplication );
    v15 = (char *)P;
    if ( !v21 )
LABEL_39:
      v8 = -1073741772;
    v11 = UserContext[7];
    RtlAcquireSRWLockExclusive(v11 + 8);
    if ( PsmpDereferenceObjectEx((volatile signed __int32 *)UserContext, 0) )
    {
      v12 = UserContext[1];
      if ( *(__int64 **)(v12 + 8) != UserContext + 1 || (v13 = (__int64 **)UserContext[2], *v13 != UserContext + 1) )
        __fastfail(3u);
      *v13 = (__int64 *)v12;
      *(_QWORD *)(v12 + 8) = v13;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
    }
    RtlReleaseSRWLockExclusive(v11 + 8);
    PsmpDereferenceManagerContext(v15);
    v5 = v33;
    v3 = v31;
LABEL_4:
    if ( (v8 & 0x80000000) == 0 )
      return v8;
    goto LABEL_16;
  }
  v8 = -1073741772;
LABEL_16:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    *(_DWORD *)v29 = a2;
    WPP_SF_S_sid_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x21u, v7, v3, (char *)v5, *(_QWORD *)v29, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180001230  mov     [rsp-8+arg_18], rbx
0x180001235  push    rbp
0x180001236  push    rsi
0x180001237  push    rdi
0x180001238  push    r12
0x18000123a  push    r13
0x18000123c  push    r14
0x18000123e  push    r15
0x180001240  lea     rbp, [rsp-100h]
0x180001248  sub     rsp, 200h
0x18000124f  mov     rax, cs:__security_cookie
0x180001256  xor     rax, rsp
0x180001259  mov     [rbp+130h+var_40], rax
0x180001260  mov     r12, r8
0x180001263  mov     [rsp+230h+var_1E8], r8
0x180001268  mov     r15d, edx
0x18000126b  mov     [rsp+230h+var_1D8], rcx
0x180001270  mov     rdi, rcx
0x180001273  mov     [rsp+230h+var_1F0], 0
0x180001278  xor     edx, edx; Val
0x18000127a  lea     rcx, [rsp+230h+packageFamilyName]; void *
0x18000127f  mov     r8d, 82h; Size
0x180001285  call    memset_0
0x18000128a  lea     r8, [rsp+230h+packageFamilyName]; packageFamilyName
0x18000128f  mov     [rsp+230h+packageFamilyNameLength], 41h ; 'A'
0x180001297  lea     rdx, [rsp+230h+packageFamilyNameLength]; packageFamilyNameLength
0x18000129c  mov     rcx, r12; packageFullName
0x18000129f  call    cs:__imp_PackageFamilyNameFromFullName
0x1800012a5  mov     ebx, eax
0x1800012a7  test    eax, eax
0x1800012a9  jz      short loc_1800012E1
0x1800012ab  jg      short loc_18000131B
0x1800012ad  test    ebx, ebx
0x1800012af  js      loc_1800013B8
0x1800012b5  mov     eax, ebx
0x1800012b7  mov     rcx, [rbp+130h+var_40]
0x1800012be  xor     rcx, rsp; StackCookie
0x1800012c1  call    __security_check_cookie
0x1800012c6  mov     rbx, [rsp+230h+arg_18]
0x1800012ce  add     rsp, 200h
0x1800012d5  pop     r15
0x1800012d7  pop     r14
0x1800012d9  pop     r13
0x1800012db  pop     r12
0x1800012dd  pop     rdi
0x1800012de  pop     rsi
0x1800012df  pop     rbp
0x1800012e0  retn
0x1800012e1  lea     r8, [rsp+230h+var_1F0]
0x1800012e6  lea     rcx, [rsp+230h+packageFamilyName]; lpValueName
0x1800012eb  call    HamOptInIsPackageFamilyNameEnabledEx
0x1800012f0  mov     ebx, eax
0x1800012f2  test    eax, eax
0x1800012f4  jnz     short loc_1800012AB
0x1800012f6  mov     edx, r15d
0x1800012f9  cmp     [rsp+230h+var_1F0], al
0x1800012fd  jz      loc_18000139F
0x180001303  mov     r9d, 400h
0x180001309  lea     r8, [rsp+230h+packageFamilyName]
0x18000130e  mov     rcx, rdi
0x180001311  call    cs:__imp_PsmHamTerminatePackage
0x180001317  mov     ebx, eax
0x180001319  jmp     short loc_1800012AD
0x18000131b  movzx   ebx, ax
0x18000131e  or      ebx, 0C0070000h
0x180001324  jmp     short loc_1800012AD
0x180001326  mov     rdi, [rsi+38h]
0x18000132a  lea     rcx, [rdi+8]
0x18000132e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001334  xor     edx, edx
0x180001336  mov     rcx, rsi
0x180001339  call    PsmpDereferenceObjectEx
0x18000133e  test    al, al
0x180001340  jz      short loc_18000137E
0x180001342  lea     rax, [rsi+8]
0x180001346  mov     rcx, [rax]
0x180001349  cmp     [rcx+8], rax
0x18000134d  jnz     short loc_180001358
0x18000134f  mov     rdx, [rax+8]
0x180001353  cmp     [rdx], rax
0x180001356  jz      short loc_18000135F
0x180001358  mov     ecx, 3
0x18000135d  int     29h; Win8: RtlFailFast(ecx)
0x18000135f  mov     [rdx], rcx
0x180001362  mov     r8, rsi; P
0x180001365  mov     [rcx+8], rdx
0x180001369  xor     edx, edx; Flags
0x18000136b  mov     rcx, gs:60h
0x180001374  mov     rcx, [rcx+30h]; HeapHandle
0x180001378  call    cs:__imp_RtlFreeHeap
0x18000137e  lea     rcx, [rdi+8]
0x180001382  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001388  mov     rcx, r14; P
0x18000138b  call    PsmpDereferenceManagerContext
0x180001390  mov     rdi, [rsp+230h+var_1D8]
0x180001395  mov     r12, [rsp+230h+var_1E8]
0x18000139a  jmp     loc_1800012AD
0x18000139f  xor     ecx, ecx
0x1800013a1  call    PsmpFindOrCreateManagerContext
0x1800013a6  mov     [rsp+230h+P], rax
0x1800013ab  mov     r14, rax
0x1800013ae  test    rax, rax
0x1800013b1  jnz     short loc_1800013F7
0x1800013b3  mov     ebx, 0C0000034h
0x1800013b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800013bf  test    byte ptr [rcx+1Ch], 2
0x1800013c3  jz      loc_1800012B5
0x1800013c9  cmp     byte ptr [rcx+19h], 2
0x1800013cd  jb      loc_1800012B5
0x1800013d3  mov     rcx, [rcx+10h]; LoggerHandle
0x1800013d7  mov     edx, 21h ; '!'
0x1800013dc  mov     dword ptr [rsp+230h+var_200], ebx; char
0x1800013e0  mov     r9, r12
0x1800013e3  mov     dword ptr [rsp+230h+var_208], r15d; char
0x1800013e8  mov     [rsp+230h+pSid], rdi; pSid
0x1800013ed  call    WPP_SF_S_sid_dd
0x1800013f2  jmp     loc_1800012B5
0x1800013f7  lea     rcx, [rax+8]
0x1800013fb  call    cs:__imp_RtlAcquireSRWLockShared
0x180001401  mov     r8, rdi
0x180001404  mov     edx, r15d
0x180001407  mov     rcx, r14
0x18000140a  call    PsmpFindUserContext
0x18000140f  lea     rcx, [r14+8]
0x180001413  mov     rsi, rax
0x180001416  call    cs:__imp_RtlReleaseSRWLockShared
0x18000141c  test    rsi, rsi
0x18000141f  jnz     short loc_180001430
0x180001421  mov     rcx, r14; P
0x180001424  mov     ebx, 0C0000034h
0x180001429  call    PsmpDereferenceManagerContext
0x18000142e  jmp     short loc_1800013B8
0x180001430  mov     rcx, cs:WPP_GLOBAL_Control
0x180001437  test    byte ptr [rcx+1Ch], 2
0x18000143b  jz      short loc_18000145E
0x18000143d  cmp     byte ptr [rcx+19h], 4
0x180001441  jb      short loc_18000145E
0x180001443  mov     rcx, [rcx+10h]; LoggerHandle
0x180001447  mov     edx, 1Eh
0x18000144c  mov     dword ptr [rsp+230h+var_208], r15d; char
0x180001451  mov     r9, r12
0x180001454  mov     [rsp+230h+pSid], rdi; pSid
0x180001459  call    WPP_SF_S_sid_d
0x18000145e  xor     edx, edx
0x180001460  mov     rcx, rsi
0x180001463  xor     r12b, r12b
0x180001466  xor     ebx, ebx
0x180001468  call    PsmpGetNextApplication
0x18000146d  mov     rdi, rax
0x180001470  test    rax, rax
0x180001473  jz      loc_18000156F
0x180001479  mov     r14, [rsp+230h+var_1E8]
0x18000147e  mov     r13, [rdi+8]
0x180001482  lea     r8, [rsp+230h+packageFamilyNameLength]
0x180001487  mov     rcx, r13
0x18000148a  mov     [rsp+230h+packageFamilyNameLength], 100h
0x180001492  lea     rdx, [rbp+130h+var_140]
0x180001496  call    cs:__imp_PsmGetPackageFullNameFromKey
0x18000149c  mov     rdx, r14
0x18000149f  lea     rcx, [rbp+130h+var_140]
0x1800014a3  call    cs:__imp__o__wcsicmp
0x1800014a9  test    eax, eax
0x1800014ab  jnz     loc_18000154A
0x1800014b1  mov     r12b, 1
0x1800014b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800014bb  test    byte ptr [rcx+1Ch], 2
0x1800014bf  jz      short loc_1800014D9
0x1800014c1  cmp     byte ptr [rcx+19h], 4
0x1800014c5  jb      short loc_1800014D9
0x1800014c7  mov     r9, [rdi+60h]
0x1800014cb  mov     rcx, [rcx+10h]
0x1800014cf  mov     [rsp+230h+pSid], r13
0x1800014d4  call    WPP_SF_iS
0x1800014d9  cmp     qword ptr [rdi+0C0h], 0
0x1800014e1  jz      short loc_1800014F4
0x1800014e3  cmp     dword ptr [rdi+158h], 0
0x1800014ea  jnz     short loc_1800014F4
0x1800014ec  mov     rcx, rdi
0x1800014ef  call    PsmpTraceLogTerminateActiveMixedJob
0x1800014f4  mov     eax, 6
0x1800014f9  mov     qword ptr [rsp+230h+var_208], 0
0x180001502  mov     r9d, eax
0x180001505  mov     dword ptr [rsp+230h+pSid], eax
0x180001509  xor     r8d, r8d
0x18000150c  xor     edx, edx
0x18000150e  mov     rcx, rdi
0x180001511  call    PsmpChangeApplicationState
0x180001516  test    eax, eax
0x180001518  jns     short loc_18000154A
0x18000151a  mov     ebx, eax
0x18000151c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001523  test    byte ptr [rcx+1Ch], 2
0x180001527  jz      short loc_18000154A
0x180001529  cmp     byte ptr [rcx+19h], 2
0x18000152d  jb      short loc_18000154A
0x18000152f  mov     r9, [rdi+60h]
0x180001533  mov     edx, 20h ; ' '
0x180001538  mov     rcx, [rcx+10h]
0x18000153c  mov     dword ptr [rsp+230h+var_208], eax
0x180001540  mov     [rsp+230h+pSid], r13
0x180001545  call    WPP_SF_iSd
0x18000154a  mov     rdx, rdi
0x18000154d  mov     rcx, rsi
0x180001550  call    PsmpGetNextApplication
0x180001555  mov     rdi, rax
0x180001558  test    rax, rax
0x18000155b  jnz     loc_18000147E
0x180001561  mov     r14, [rsp+230h+P]
0x180001566  test    r12b, r12b
0x180001569  jnz     loc_180001326
0x18000156f  mov     ebx, 0C0000034h
0x180001574  jmp     loc_180001326
```
