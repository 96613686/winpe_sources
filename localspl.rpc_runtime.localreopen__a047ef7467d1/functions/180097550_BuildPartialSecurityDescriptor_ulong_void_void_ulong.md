# BuildPartialSecurityDescriptor(ulong,void *,void * *,ulong *)

- ea: `0x180097550`
- end: `0x180097771`
- name: `?BuildPartialSecurityDescriptor@@YAHKPEAXPEAPEAXPEAK@Z`
- size: `545`
- prototype: `__int64 __fastcall(DWORD GrantedAccess, PSECURITY_DESCRIPTOR pSecurityDescriptor, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b778`

## callees

- `0x180054638`
- `0x180097550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097733`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800975a8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800975a8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18009762b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18009762b`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x1800975bf`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x1800975d0`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180097670`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x1800975bf`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x1800975d0`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180097670`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180097645`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180097645`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800976a2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800976a2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180097689`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180097689`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800975e9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800975e9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180097615`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180097615`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800975ff`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800975ff`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009765e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009765e`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800976b9`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800976ee`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800976b9`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800976ee`
- `SPOOLSS!DllAllocSplMem` at `0x1800976d5`
- `SPOOLSS!DllAllocSplMem` at `0x1800976d5`

## string_xrefs

- `0x180097704`: `Failed to build partial security descriptor.  Error %d`
- `0x18009770b`: `BuildPartialSecurityDescriptor`
- `0x180097743`: `BuildPartialSecurityDescriptor`
- `0x18009775a`: `BuildPartialSecurityDescriptor`

## pseudocode

```c
_BOOL8 __fastcall BuildPartialSecurityDescriptor(
        DWORD GrantedAccess,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        void **a3,
        unsigned int *a4)
{
  int v8; // ebx
  void *v9; // rax
  void *v10; // rdi
  DWORD v11; // eax
  DWORD LastError; // eax
  WINBOOL bOwnerDefaulted; // [rsp+20h] [rbp-60h] BYREF
  DWORD dwBufferLength; // [rsp+24h] [rbp-5Ch] BYREF
  WINBOOL bDaclPresent; // [rsp+28h] [rbp-58h] BYREF
  WINBOOL bSaclPresent; // [rsp+2Ch] [rbp-54h] BYREF
  PSID pOwner; // [rsp+30h] [rbp-50h] BYREF
  PSID pGroup; // [rsp+38h] [rbp-48h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-40h] BYREF
  PACL pSacl; // [rsp+48h] [rbp-38h] BYREF
  _OWORD pSecurityDescriptora[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+70h] [rbp-10h]

  v23 = 0;
  bOwnerDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  bDaclPresent = 0;
  pDacl = 0;
  bSaclPresent = 0;
  memset(pSecurityDescriptora, 0, sizeof(pSecurityDescriptora));
  pSacl = 0;
  dwBufferLength = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptora, 1u) )
    goto LABEL_21;
  v8 = 0;
  if ( AreAllAccessesGranted(GrantedAccess, 0x20000u) || AreAllAccessesGranted(GrantedAccess, 0x80000u) )
  {
    if ( GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
      SetSecurityDescriptorOwner(pSecurityDescriptora, pOwner, bOwnerDefaulted);
    else
      v8 = 1;
    if ( GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bOwnerDefaulted) )
      SetSecurityDescriptorGroup(pSecurityDescriptora, pGroup, bOwnerDefaulted);
    else
      v8 = 1;
    if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
      SetSecurityDescriptorDacl(pSecurityDescriptora, bDaclPresent, pDacl, bOwnerDefaulted);
    else
      v8 = 1;
  }
  if ( AreAllAccessesGranted(GrantedAccess, 0x1000000u) )
  {
    if ( GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bOwnerDefaulted) )
    {
      SetSecurityDescriptorSacl(pSecurityDescriptora, bSaclPresent, pSacl, bOwnerDefaulted);
      goto LABEL_16;
    }
LABEL_21:
    v8 = 1;
    goto LABEL_22;
  }
LABEL_16:
  if ( !v8 )
  {
    dwBufferLength = 0;
    if ( MakeSelfRelativeSD(pSecurityDescriptora, 0, &dwBufferLength) )
    {
      v10 = 0;
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "BuildPartialSecurityDescriptor",
        L"Expected MakeSelfRelativeSD to fail");
    }
    else
    {
      if ( GetLastError() != 122 )
      {
        v8 = 1;
        LastError = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning("BuildPartialSecurityDescriptor", L"Failed: Error %d", LastError);
        goto LABEL_22;
      }
      v9 = (void *)DllAllocSplMem(dwBufferLength);
      v10 = v9;
      if ( !v9 || !MakeSelfRelativeSD(pSecurityDescriptora, v9, &dwBufferLength) )
        goto LABEL_21;
    }
    *a4 = dwBufferLength;
    *a3 = v10;
    return v8 == 0;
  }
LABEL_22:
  v11 = GetLastError();
  LocalSpoolerTelemetry::WriteDbgTraceWarning(
    "BuildPartialSecurityDescriptor",
    L"Failed to build partial security descriptor.  Error %d",
    v11);
  return v8 == 0;
}

```

## disassembly

```asm
0x180097550  push    rbp
0x180097552  push    rbx
0x180097553  push    rsi
0x180097554  push    rdi
0x180097555  push    r13
0x180097557  push    r14
0x180097559  push    r15
0x18009755b  mov     rbp, rsp
0x18009755e  sub     rsp, 80h
0x180097565  xor     eax, eax
0x180097567  xorps   xmm0, xmm0
0x18009756a  mov     rdi, rdx
0x18009756d  mov     [rbp+var_10], rax
0x180097571  mov     esi, ecx
0x180097573  mov     [rbp+bOwnerDefaulted], eax
0x180097576  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18009757a  mov     [rbp+pOwner], rax
0x18009757e  lea     r13d, [rax+1]
0x180097582  mov     [rbp+pGroup], rax
0x180097586  mov     edx, r13d; dwRevision
0x180097589  mov     [rbp+bDaclPresent], eax
0x18009758c  mov     r14, r9
0x18009758f  mov     [rbp+pDacl], rax
0x180097593  mov     r15, r8
0x180097596  mov     [rbp+bSaclPresent], eax
0x180097599  movups  [rbp+pSecurityDescriptor], xmm0
0x18009759d  mov     [rbp+pSacl], rax
0x1800975a1  movups  [rbp+var_20], xmm0
0x1800975a5  mov     [rbp+dwBufferLength], eax
0x1800975a8  call    cs:__imp_InitializeSecurityDescriptor
0x1800975ae  test    eax, eax
0x1800975b0  jz      loc_1800976F8
0x1800975b6  mov     edx, 20000h; DesiredAccess
0x1800975bb  mov     ecx, esi; GrantedAccess
0x1800975bd  xor     ebx, ebx
0x1800975bf  call    cs:__imp_AreAllAccessesGranted
0x1800975c5  test    eax, eax
0x1800975c7  jnz     short loc_1800975DE
0x1800975c9  mov     edx, 80000h; DesiredAccess
0x1800975ce  mov     ecx, esi; GrantedAccess
0x1800975d0  call    cs:__imp_AreAllAccessesGranted
0x1800975d6  test    eax, eax
0x1800975d8  jz      loc_180097669
0x1800975de  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800975e2  mov     rcx, rdi; pSecurityDescriptor
0x1800975e5  lea     rdx, [rbp+pOwner]; pOwner
0x1800975e9  call    cs:__imp_GetSecurityDescriptorOwner
0x1800975ef  test    eax, eax
0x1800975f1  jz      short loc_180097607
0x1800975f3  mov     r8d, [rbp+bOwnerDefaulted]; bOwnerDefaulted
0x1800975f7  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800975fb  mov     rdx, [rbp+pOwner]; pOwner
0x1800975ff  call    cs:__imp_SetSecurityDescriptorOwner
0x180097605  jmp     short loc_18009760A
0x180097607  mov     ebx, r13d
0x18009760a  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18009760e  mov     rcx, rdi; pSecurityDescriptor
0x180097611  lea     rdx, [rbp+pGroup]; pGroup
0x180097615  call    cs:__imp_GetSecurityDescriptorGroup
0x18009761b  test    eax, eax
0x18009761d  jz      short loc_180097633
0x18009761f  mov     r8d, [rbp+bOwnerDefaulted]; bGroupDefaulted
0x180097623  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180097627  mov     rdx, [rbp+pGroup]; pGroup
0x18009762b  call    cs:__imp_SetSecurityDescriptorGroup
0x180097631  jmp     short loc_180097636
0x180097633  mov     ebx, r13d
0x180097636  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18009763a  mov     rcx, rdi; pSecurityDescriptor
0x18009763d  lea     r8, [rbp+pDacl]; pDacl
0x180097641  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180097645  call    cs:__imp_GetSecurityDescriptorDacl
0x18009764b  test    eax, eax
0x18009764d  jz      short loc_180097666
0x18009764f  mov     r9d, [rbp+bOwnerDefaulted]; bDaclDefaulted
0x180097653  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180097657  mov     r8, [rbp+pDacl]; pDacl
0x18009765b  mov     edx, [rbp+bDaclPresent]; bDaclPresent
0x18009765e  call    cs:__imp_SetSecurityDescriptorDacl
0x180097664  jmp     short loc_180097669
0x180097666  mov     ebx, r13d
0x180097669  mov     edx, 1000000h; DesiredAccess
0x18009766e  mov     ecx, esi; GrantedAccess
0x180097670  call    cs:__imp_AreAllAccessesGranted
0x180097676  test    eax, eax
0x180097678  jz      short loc_1800976A8
0x18009767a  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x18009767e  mov     rcx, rdi; pSecurityDescriptor
0x180097681  lea     r8, [rbp+pSacl]; pSacl
0x180097685  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x180097689  call    cs:__imp_GetSecurityDescriptorSacl
0x18009768f  test    eax, eax
0x180097691  jz      short loc_1800976F8
0x180097693  mov     r9d, [rbp+bOwnerDefaulted]; bSaclDefaulted
0x180097697  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18009769b  mov     r8, [rbp+pSacl]; pSacl
0x18009769f  mov     edx, [rbp+bSaclPresent]; bSaclPresent
0x1800976a2  call    cs:__imp_SetSecurityDescriptorSacl
0x1800976a8  test    ebx, ebx
0x1800976aa  jnz     short loc_1800976FB
0x1800976ac  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x1800976b0  mov     [rbp+dwBufferLength], ebx
0x1800976b3  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1800976b5  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800976b9  call    cs:__imp_MakeSelfRelativeSD
0x1800976bf  test    eax, eax
0x1800976c1  jnz     loc_180097751
0x1800976c7  call    cs:__imp_GetLastError
0x1800976cd  cmp     eax, 7Ah ; 'z'
0x1800976d0  jnz     short loc_180097730
0x1800976d2  mov     ecx, [rbp+dwBufferLength]
0x1800976d5  call    cs:__imp_DllAllocSplMem
0x1800976db  mov     rdi, rax
0x1800976de  test    rax, rax
0x1800976e1  jz      short loc_1800976F8
0x1800976e3  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x1800976e7  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1800976ea  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800976ee  call    cs:__imp_MakeSelfRelativeSD
0x1800976f4  test    eax, eax
0x1800976f6  jnz     short loc_180097766
0x1800976f8  mov     ebx, r13d
0x1800976fb  call    cs:__imp_GetLastError
0x180097701  mov     r8d, eax
0x180097704  lea     rdx, aFailedToBuildP; "Failed to build partial security descri"...
0x18009770b  lea     rcx, aBuildpartialse; "BuildPartialSecurityDescriptor"
0x180097712  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180097717  xor     eax, eax
0x180097719  test    ebx, ebx
0x18009771b  setz    al
0x18009771e  add     rsp, 80h
0x180097725  pop     r15
0x180097727  pop     r14
0x180097729  pop     r13
0x18009772b  pop     rdi
0x18009772c  pop     rsi
0x18009772d  pop     rbx
0x18009772e  pop     rbp
0x18009772f  retn
0x180097730  mov     ebx, r13d
0x180097733  call    cs:__imp_GetLastError
0x180097739  mov     r8d, eax
0x18009773c  lea     rdx, aFailedErrorD_0; "Failed: Error %d"
0x180097743  lea     rcx, aBuildpartialse; "BuildPartialSecurityDescriptor"
0x18009774a  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18009774f  jmp     short loc_1800976FB
0x180097751  xor     edi, edi
0x180097753  lea     rdx, aExpectedMakese; "Expected MakeSelfRelativeSD to fail"
0x18009775a  lea     rcx, aBuildpartialse; "BuildPartialSecurityDescriptor"
0x180097761  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180097766  mov     eax, [rbp+dwBufferLength]
0x180097769  mov     [r14], eax
0x18009776c  mov     [r15], rdi
0x18009776f  jmp     short loc_180097717
```
