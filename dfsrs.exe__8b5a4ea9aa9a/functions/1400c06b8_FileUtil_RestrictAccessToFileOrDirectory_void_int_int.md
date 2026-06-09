# FileUtil::RestrictAccessToFileOrDirectory(void *,int,int)

- ea: `0x1400c06b8`
- end: `0x1400c0a74`
- name: `?RestrictAccessToFileOrDirectory@FileUtil@@SAPEAVFrsStatus@@PEAXHH@Z`
- size: `956`
- prototype: `struct FrsStatus *__fastcall(HANDLE handle, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400c0a7c`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14000cdc0`
- `0x14001c030`
- `0x14001cf70`
- `0x14001dcac`
- `0x14004ab40`
- `0x1400c06b8`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401c5988`
- `0x1401c5c2c`
- `0x1401c5e2c`
- `0x1401c67b8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400c0860`
- `KERNEL32!GetCurrentThreadId` at `0x1400c089c`
- `KERNEL32!GetCurrentThreadId` at `0x1400c0960`
- `KERNEL32!GetCurrentThreadId` at `0x1400c09cf`
- `KERNEL32!GetCurrentThreadId` at `0x1400c0860`
- `KERNEL32!GetCurrentThreadId` at `0x1400c089c`
- `KERNEL32!GetCurrentThreadId` at `0x1400c0960`
- `KERNEL32!GetCurrentThreadId` at `0x1400c09cf`
- `ADVAPI32!SetSecurityInfo` at `0x1400c0852`
- `ADVAPI32!SetSecurityInfo` at `0x1400c0852`

## string_xrefs

- `0x1400c081b`: `FileUtil::RestrictAccessToFileOrDirectory`
- `0x1400c09ec`: `FileUtil::RestrictAccessToFileOrDirectory`
- `0x1400c09be`: `Failed to create Admins SID, err:%?`
- `0x1400c0927`: `FileUtil::RestrictAccessToFileOrDirectory`
- `0x1400c0996`: `FileUtil::RestrictAccessToFileOrDirectory`
- `0x1400c094f`: `Failed to create System SID, err:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct FrsStatus *__fastcall FileUtil::RestrictAccessToFileOrDirectory(HANDLE handle, __int64 a2, int a3)
{
  __int64 v4; // r8
  unsigned __int8 v5; // si
  struct FrsStatus *v6; // rbx
  __int64 v7; // rdi
  AccessAce *v8; // rax
  unsigned int *v9; // rbx
  PACL v10; // r15
  DWORD v11; // ebx
  DWORD v12; // eax
  __int64 v13; // rcx
  DWORD v14; // eax
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v18; // rbx
  int pSacl; // [rsp+38h] [rbp-D0h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C8h]
  struct FrsStatus *v21; // [rsp+48h] [rbp-C0h]
  AccessAce *v22; // [rsp+58h] [rbp-B0h] BYREF
  void **v23; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+68h] [rbp-A0h]
  const wchar_t *v25; // [rsp+70h] [rbp-98h]
  PACL pDacl; // [rsp+78h] [rbp-90h]
  void **v27; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v28[32]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v29[8]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE psidOwner[120]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v31[128]; // [rsp+128h] [rbp+20h] BYREF

  v4 = (unsigned int)-a3;
  v5 = (_DWORD)v4 != 0 ? 3 : 0;
  AceList<AccessAce>::AceList<AccessAce>(&v27, a2, v4);
  Sid::Sid((Sid *)v29);
  Sid::Sid((Sid *)v31);
  v6 = Sid::Create((Sid *)v29, (PSID_IDENTIFIER_AUTHORITY)&Sid::SecurityNTAuthority, 2u);
  v7 = 0;
  if ( v6 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v23 = (void **)L"FileUtil::RestrictAccessToFileOrDirectory";
      v24 = 0x200000891LL;
      v25 = L"FUTL";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(&v23, L"Failed to create Admins SID, err:%?", v6);
    }
    v21 = v6;
    CurrentThreadId = GetCurrentThreadId();
    pSacl = 2194;
    goto LABEL_17;
  }
  v8 = (AccessAce *)operator new(0x98u);
  v22 = AccessAce::AccessAce(v8, (const struct Sid *)v29, 0x1F01FFu, v5, 1);
  std::vector<ReplicaSetManager *>::push_back(v28, &v22);
  v6 = Sid::Create((Sid *)v31, (PSID_IDENTIFIER_AUTHORITY)&Sid::SecurityNTAuthority, 1u, 18);
  if ( v6 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v23 = (void **)L"FileUtil::RestrictAccessToFileOrDirectory";
      v24 = 0x20000089DLL;
      v25 = L"FUTL";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(&v23, L"Failed to create System SID, err:%?", v6);
    }
    v21 = v6;
    CurrentThreadId = GetCurrentThreadId();
    pSacl = 2206;
LABEL_17:
    v18 = FrsStatusList::PushNewError(
            v17,
            *((unsigned int *)v6 + 1),
            *((unsigned int *)v6 + 2),
            *(unsigned int *)v6,
            "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
            "FileUtil::RestrictAccessToFileOrDirectory",
            pSacl,
            CurrentThreadId,
            v21);
    Sid::~Sid((Sid *)v31);
    Sid::~Sid((Sid *)v29);
    v27 = &AceList<AccessAce>::`vftable';
    PtrList<AccessAce>::~PtrList<AccessAce>(&v27);
    return (struct FrsStatus *)v18;
  }
  v22 = (AccessAce *)operator new(0x98u);
  v22 = AccessAce::AccessAce(v22, (const struct Sid *)v31, 0x1F01FFu, v5, 1);
  std::vector<ReplicaSetManager *>::push_back(v28, &v22);
  LODWORD(v24) = 2;
  LODWORD(v25) = 0;
  pDacl = 0;
  v23 = &Dacl::`vftable';
  v9 = (unsigned int *)Acl::MakeAcl<AuditAce>((Acl *)&v23);
  v10 = pDacl;
  if ( v9
    || (v11 = SetSecurityInfo(handle, SE_FILE_OBJECT, 0x80000005, psidOwner, 0, pDacl, 0),
        v12 = GetCurrentThreadId(),
        (v9 = (unsigned int *)FrsStatusList::PushNewError(
                                v13,
                                v11,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                                "FileUtil::RestrictAccessToFileOrDirectory",
                                2235,
                                v12,
                                0)) != 0) )
  {
    v14 = GetCurrentThreadId();
    v7 = FrsStatusList::PushNewError(
           v15,
           v9[1],
           v9[2],
           *v9,
           "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
           "FileUtil::RestrictAccessToFileOrDirectory",
           2239,
           v14,
           v9);
  }
  operator delete[](v10);
  Sid::~Sid((Sid *)v31);
  Sid::~Sid((Sid *)v29);
  v27 = &AceList<AccessAce>::`vftable';
  PtrList<AccessAce>::~PtrList<AccessAce>(&v27);
  return (struct FrsStatus *)v7;
}

```

## disassembly

```asm
0x1400c06b8  mov     rax, rsp
0x1400c06bb  mov     [rax+10h], rbx
0x1400c06bf  mov     [rax+18h], rsi
0x1400c06c3  mov     [rax+20h], rdi
0x1400c06c7  push    rbp
0x1400c06c8  push    r12
0x1400c06ca  push    r13
0x1400c06cc  push    r14
0x1400c06ce  push    r15
0x1400c06d0  lea     rbp, [rax-0D8h]
0x1400c06d7  sub     rsp, 1B0h
0x1400c06de  mov     rax, cs:__security_cookie
0x1400c06e5  xor     rax, rsp
0x1400c06e8  mov     [rbp+0D0h+var_30], rax
0x1400c06ef  mov     r12, rcx
0x1400c06f2  neg     r8d
0x1400c06f5  sbb     sil, sil
0x1400c06f8  and     sil, 3
0x1400c06fc  lea     rcx, [rsp+1D0h+var_158]
0x1400c0701  call    ??0?$AceList@VAccessAce@@@@QEAA@XZ; AceList<AccessAce>::AceList<AccessAce>(void)
0x1400c0706  nop
0x1400c0707  lea     rcx, [rbp+0D0h+var_130]; this
0x1400c070b  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x1400c0710  nop
0x1400c0711  lea     rcx, [rbp+0D0h+var_B0]; this
0x1400c0715  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x1400c071a  nop
0x1400c071b  mov     dword ptr [rsp+1D0h+psidGroup], 220h
0x1400c0723  mov     r9d, 20h ; ' '
0x1400c0729  lea     r14d, [r9-1Eh]
0x1400c072d  mov     r8d, r14d; nSubAuthorityCount
0x1400c0730  lea     rdx, ?SecurityNTAuthority@Sid@@2U_SID_IDENTIFIER_AUTHORITY@@B; pIdentifierAuthority
0x1400c0737  lea     rcx, [rbp+0D0h+var_130]; this
0x1400c073b  call    ?Create@Sid@@QEAAPEAVFrsStatus@@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; Sid::Create(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x1400c0740  mov     rbx, rax
0x1400c0743  xor     edi, edi
0x1400c0745  test    rax, rax
0x1400c0748  jnz     loc_1400C097F
0x1400c074e  mov     r15d, 98h
0x1400c0754  mov     ecx, r15d; Size
0x1400c0757  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400c075c  mov     [rsp+1D0h+var_180], rax
0x1400c0761  lea     r13d, [r14-1]
0x1400c0765  mov     dword ptr [rsp+1D0h+psidGroup], r13d; int
0x1400c076a  mov     r9b, sil; unsigned __int8
0x1400c076d  mov     r8d, 1F01FFh; unsigned int
0x1400c0773  lea     rdx, [rbp+0D0h+var_130]; struct Sid *
0x1400c0777  mov     rcx, rax; this
0x1400c077a  call    ??0AccessAce@@QEAA@AEBVSid@@KEH@Z; AccessAce::AccessAce(Sid const &,ulong,uchar,int)
0x1400c077f  mov     [rsp+1D0h+var_180], rax
0x1400c0784  lea     rdx, [rsp+1D0h+var_180]
0x1400c0789  lea     rcx, [rbp+0D0h+var_150]
0x1400c078d  call    ?push_back@?$vector@PEAVReplicaSetManager@@V?$allocator@PEAVReplicaSetManager@@@std@@@std@@QEAAXAEBQEAVReplicaSetManager@@@Z; std::vector<ReplicaSetManager *>::push_back(ReplicaSetManager * const &)
0x1400c0792  lea     r9d, [r14+10h]
0x1400c0796  mov     r8d, r13d; nSubAuthorityCount
0x1400c0799  lea     rdx, ?SecurityNTAuthority@Sid@@2U_SID_IDENTIFIER_AUTHORITY@@B; pIdentifierAuthority
0x1400c07a0  lea     rcx, [rbp+0D0h+var_B0]; this
0x1400c07a4  call    ?Create@Sid@@QEAAPEAVFrsStatus@@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; Sid::Create(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x1400c07a9  mov     rbx, rax
0x1400c07ac  test    rax, rax
0x1400c07af  jnz     loc_1400C0910
0x1400c07b5  mov     ecx, r15d; Size
0x1400c07b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400c07bd  mov     [rsp+1D0h+var_180], rax
0x1400c07c2  mov     dword ptr [rsp+1D0h+psidGroup], r13d; int
0x1400c07c7  mov     r9b, sil; unsigned __int8
0x1400c07ca  mov     r8d, 1F01FFh; unsigned int
0x1400c07d0  lea     rdx, [rbp+0D0h+var_B0]; struct Sid *
0x1400c07d4  mov     rcx, rax; this
0x1400c07d7  call    ??0AccessAce@@QEAA@AEBVSid@@KEH@Z; AccessAce::AccessAce(Sid const &,ulong,uchar,int)
0x1400c07dc  mov     [rsp+1D0h+var_180], rax
0x1400c07e1  lea     rdx, [rsp+1D0h+var_180]
0x1400c07e6  lea     rcx, [rbp+0D0h+var_150]
0x1400c07ea  call    ?push_back@?$vector@PEAVReplicaSetManager@@V?$allocator@PEAVReplicaSetManager@@@std@@@std@@QEAAXAEBQEAVReplicaSetManager@@@Z; std::vector<ReplicaSetManager *>::push_back(ReplicaSetManager * const &)
0x1400c07ef  mov     dword ptr [rsp+1D0h+var_170], r14d
0x1400c07f4  mov     dword ptr [rsp+1D0h+var_168], edi
0x1400c07f8  mov     [rsp+1D0h+var_160], rdi
0x1400c07fd  lea     rax, ??_7Dacl@@6B@; const Dacl::`vftable'
0x1400c0804  mov     [rsp+1D0h+var_178], rax
0x1400c0809  lea     rdx, [rsp+1D0h+var_158]
0x1400c080e  lea     rcx, [rsp+1D0h+var_178]; this
0x1400c0813  call    ??$MakeAcl@VAuditAce@@@Acl@@IEAAPEAVFrsStatus@@AEAV?$AceList@VAuditAce@@@@@Z; Acl::MakeAcl<AuditAce>(AceList<AuditAce> &)
0x1400c0818  mov     rbx, rax
0x1400c081b  lea     rsi, aFileutilRestri_0; "FileUtil::RestrictAccessToFileOrDirecto"...
0x1400c0822  lea     r14, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400c0829  mov     r15, [rsp+1D0h+var_160]
0x1400c082e  test    rax, rax
0x1400c0831  jnz     short loc_1400C089C
0x1400c0833  mov     [rsp+1D0h+pSacl], rdi; pSacl
0x1400c0838  mov     [rsp+1D0h+pDacl], r15; pDacl
0x1400c083d  mov     [rsp+1D0h+psidGroup], rdi; psidGroup
0x1400c0842  lea     r9, [rbp+0D0h+psidOwner]; psidOwner
0x1400c0846  mov     r8d, 80000005h; SecurityInfo
0x1400c084c  mov     edx, r13d; ObjectType
0x1400c084f  mov     rcx, r12; handle
0x1400c0852  call    cs:__imp_SetSecurityInfo
0x1400c0859  nop     dword ptr [rax+rax+00h]
0x1400c085e  mov     ebx, eax
0x1400c0860  call    cs:__imp_GetCurrentThreadId
0x1400c0867  nop     dword ptr [rax+rax+00h]
0x1400c086c  mov     [rsp+1D0h+var_190], rdi
0x1400c0871  mov     dword ptr [rsp+1D0h+var_198], eax
0x1400c0875  mov     dword ptr [rsp+1D0h+pSacl], 8BBh
0x1400c087d  mov     [rsp+1D0h+pDacl], rsi
0x1400c0882  mov     [rsp+1D0h+psidGroup], r14
0x1400c0887  mov     r9d, r13d
0x1400c088a  xor     r8d, r8d
0x1400c088d  mov     edx, ebx
0x1400c088f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400c0894  mov     rbx, rax
0x1400c0897  test    rax, rax
0x1400c089a  jz      short loc_1400C08D5
0x1400c089c  call    cs:__imp_GetCurrentThreadId
0x1400c08a3  nop     dword ptr [rax+rax+00h]
0x1400c08a8  mov     [rsp+1D0h+var_190], rbx
0x1400c08ad  mov     dword ptr [rsp+1D0h+var_198], eax
0x1400c08b1  mov     dword ptr [rsp+1D0h+pSacl], 8BFh
0x1400c08b9  mov     [rsp+1D0h+pDacl], rsi
0x1400c08be  mov     [rsp+1D0h+psidGroup], r14
0x1400c08c3  mov     r9d, [rbx]
0x1400c08c6  mov     r8d, [rbx+8]
0x1400c08ca  mov     edx, [rbx+4]
0x1400c08cd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400c08d2  mov     rdi, rax
0x1400c08d5  mov     rcx, r15; Block
0x1400c08d8  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1400c08dd  nop
0x1400c08de  lea     rcx, [rbp+0D0h+var_B0]; this
0x1400c08e2  call    ??1Sid@@UEAA@XZ; Sid::~Sid(void)
0x1400c08e7  nop
0x1400c08e8  lea     rcx, [rbp+0D0h+var_130]; this
0x1400c08ec  call    ??1Sid@@UEAA@XZ; Sid::~Sid(void)
0x1400c08f1  nop
0x1400c08f2  lea     rax, ??_7?$AceList@VAccessAce@@@@6B@; const AceList<AccessAce>::`vftable'
0x1400c08f9  mov     [rsp+1D0h+var_158], rax
0x1400c08fe  lea     rcx, [rsp+1D0h+var_158]
0x1400c0903  call    ??1?$PtrList@VAccessAce@@@@UEAA@XZ; PtrList<AccessAce>::~PtrList<AccessAce>(void)
0x1400c0908  mov     rax, rdi
0x1400c090b  jmp     loc_1400C0A43
0x1400c0910  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400c0917  test    rax, rax
0x1400c091a  jz      short loc_1400C0960
0x1400c091c  cmp     [rax+40h], edi
0x1400c091f  jz      short loc_1400C0960
0x1400c0921  cmp     [rax+38h], r14d
0x1400c0925  jl      short loc_1400C0960
0x1400c0927  lea     rax, aFileutilRestri; "FileUtil::RestrictAccessToFileOrDirecto"...
0x1400c092e  mov     [rsp+1D0h+var_178], rax
0x1400c0933  mov     dword ptr [rsp+1D0h+var_170], 89Dh
0x1400c093b  mov     dword ptr [rsp+1D0h+var_170+4], r14d
0x1400c0940  lea     rax, aFutl; "FUTL"
0x1400c0947  mov     [rsp+1D0h+var_168], rax
0x1400c094c  mov     r8, rbx
0x1400c094f  lea     rdx, aFailedToCreate_0; "Failed to create System SID, err:%?"
0x1400c0956  lea     rcx, [rsp+1D0h+var_178]
0x1400c095b  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400c0960  call    cs:__imp_GetCurrentThreadId
0x1400c0967  nop     dword ptr [rax+rax+00h]
0x1400c096c  mov     [rsp+1D0h+var_190], rbx
0x1400c0971  mov     dword ptr [rsp+1D0h+var_198], eax
0x1400c0975  mov     dword ptr [rsp+1D0h+pSacl], 89Eh
0x1400c097d  jmp     short loc_1400C09EC
0x1400c097f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400c0986  test    rax, rax
0x1400c0989  jz      short loc_1400C09CF
0x1400c098b  cmp     [rax+40h], edi
0x1400c098e  jz      short loc_1400C09CF
0x1400c0990  cmp     [rax+38h], r14d
0x1400c0994  jl      short loc_1400C09CF
0x1400c0996  lea     rax, aFileutilRestri; "FileUtil::RestrictAccessToFileOrDirecto"...
0x1400c099d  mov     [rsp+1D0h+var_178], rax
0x1400c09a2  mov     dword ptr [rsp+1D0h+var_170], 891h
0x1400c09aa  mov     dword ptr [rsp+1D0h+var_170+4], r14d
0x1400c09af  lea     rax, aFutl; "FUTL"
0x1400c09b6  mov     [rsp+1D0h+var_168], rax
0x1400c09bb  mov     r8, rbx
0x1400c09be  lea     rdx, aFailedToCreate_3; "Failed to create Admins SID, err:%?"
0x1400c09c5  lea     rcx, [rsp+1D0h+var_178]
0x1400c09ca  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400c09cf  call    cs:__imp_GetCurrentThreadId
0x1400c09d6  nop     dword ptr [rax+rax+00h]
0x1400c09db  mov     [rsp+1D0h+var_190], rbx
0x1400c09e0  mov     dword ptr [rsp+1D0h+var_198], eax
0x1400c09e4  mov     dword ptr [rsp+1D0h+pSacl], 892h
0x1400c09ec  lea     rsi, aFileutilRestri_0; "FileUtil::RestrictAccessToFileOrDirecto"...
0x1400c09f3  mov     [rsp+1D0h+pDacl], rsi
0x1400c09f8  lea     r14, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400c09ff  mov     [rsp+1D0h+psidGroup], r14
0x1400c0a04  mov     r9d, [rbx]
0x1400c0a07  mov     r8d, [rbx+8]
0x1400c0a0b  mov     edx, [rbx+4]
0x1400c0a0e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400c0a13  mov     rbx, rax
0x1400c0a16  lea     rcx, [rbp+0D0h+var_B0]; this
0x1400c0a1a  call    ??1Sid@@UEAA@XZ; Sid::~Sid(void)
0x1400c0a1f  nop
0x1400c0a20  lea     rcx, [rbp+0D0h+var_130]; this
0x1400c0a24  call    ??1Sid@@UEAA@XZ; Sid::~Sid(void)
0x1400c0a29  nop
0x1400c0a2a  lea     rax, ??_7?$AceList@VAccessAce@@@@6B@; const AceList<AccessAce>::`vftable'
0x1400c0a31  mov     [rsp+1D0h+var_158], rax
0x1400c0a36  lea     rcx, [rsp+1D0h+var_158]
0x1400c0a3b  call    ??1?$PtrList@VAccessAce@@@@UEAA@XZ; PtrList<AccessAce>::~PtrList<AccessAce>(void)
0x1400c0a40  mov     rax, rbx
0x1400c0a43  mov     rcx, [rbp+0D0h+var_30]
0x1400c0a4a  xor     rcx, rsp; StackCookie
0x1400c0a4d  call    __security_check_cookie
0x1400c0a52  lea     r11, [rsp+1D0h+var_20]
0x1400c0a5a  mov     rbx, [r11+38h]
0x1400c0a5e  mov     rsi, [r11+40h]
0x1400c0a62  mov     rdi, [r11+48h]
0x1400c0a66  mov     rsp, r11
0x1400c0a69  pop     r15
0x1400c0a6b  pop     r14
0x1400c0a6d  pop     r13
0x1400c0a6f  pop     r12
0x1400c0a71  pop     rbp
0x1400c0a72  retn
```
