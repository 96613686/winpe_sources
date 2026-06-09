# DeriveAppContainerSidFromAppContainerNameWorker(ushort const *,void * *)

- ea: `0x180001880`
- end: `0x180001b95`
- name: `?DeriveAppContainerSidFromAppContainerNameWorker@@YAJPEBGPEAPEAX@Z`
- size: `789`
- prototype: `__int64 __fastcall(char *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001880`
- `0x180001bd4`
- `0x1800044e0`
- `0x180004594`
- `0x18000f440`
- `0x180016740`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180001afe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180001afe`
- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x180001ab4`
- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x180001ab4`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180001965`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180001965`
- `ntdll!RtlFreeSid` at `0x180001a40`
- `ntdll!RtlFreeSid` at `0x180001a61`
- `ntdll!RtlFreeSid` at `0x180001a40`
- `ntdll!RtlFreeSid` at `0x180001a61`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x180001b21`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x180001b21`

## string_xrefs

- `0x1800018e4`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800019af`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800019e1`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180001a16`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180001a7a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180001adb`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180001b75`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall DeriveAppContainerSidFromAppContainerNameWorker(char *a1, void **a2)
{
  __int64 v4; // rcx
  char *i; // rax
  int v7; // ebx
  unsigned int PackageFamilyNameFromToken; // eax
  int v9; // ebx
  __int64 v10; // rdx
  int v11; // [rsp+20h] [rbp-E8h]
  UINT32 packageFamilyNameLength; // [rsp+40h] [rbp-C8h] BYREF
  PSID Sid; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B8h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+60h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v11);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v11);
    return 2147942487LL;
  }
  v4 = 65;
  for ( i = a1; *(_WORD *)i; i += 2 )
  {
    if ( !--v4 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xBDD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)0x80070057LL,
        (int)"Name %ls",
        a1);
      return 2147942487LL;
    }
  }
  if ( v4 == 65 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xBDF,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      (int)"Name %ls",
      a1);
    return 2147942487LL;
  }
  packageFamilyNameLength = 2162688;
  Sid = 0;
  v14 = 0;
  AppModelPolicy_GetPolicy_Internal(-6, a2, &packageFamilyNameLength, &v14, &Sid);
  if ( packageFamilyNameLength != 2162689 )
  {
    v7 = AppContainerDeriveSidFromMoniker(a1, a2);
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xC03,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v7,
        (int)"Name %ls",
        a1);
      return (unsigned int)v7;
    }
    return 0;
  }
  packageFamilyNameLength = 65;
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(
                                 (HANDLE)0xFFFFFFFFFFFFFFFALL,
                                 &packageFamilyNameLength,
                                 packageFamilyName);
  if ( PackageFamilyNameFromToken )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0xBF2,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
             (const char *)PackageFamilyNameFromToken,
             (unsigned int)"Name %ls",
             a1);
  if ( !lstrcmpiW((LPCWSTR)a1, packageFamilyName) )
    return 0;
  Sid = 0;
  v9 = PackageSidFromFamilyName(packageFamilyName, &Sid);
  if ( v9 >= 0 )
  {
    v9 = AppContainerRegistrationHelper::DeriveChildAppContainerSid(Sid, a1, a2);
    if ( v9 < 0 )
    {
      v10 = 3068;
      goto LABEL_14;
    }
    if ( Sid )
      RtlFreeSid(Sid);
    return 0;
  }
  v10 = 3064;
LABEL_14:
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)(unsigned int)v9,
    (int)"Name %ls family %ls",
    a1,
    packageFamilyName);
  if ( Sid )
    RtlFreeSid(Sid);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180001880  mov     [rsp+arg_18], rsi
0x180001885  push    rdi
0x180001886  sub     rsp, 100h
0x18000188d  mov     rax, cs:__security_cookie
0x180001894  xor     rax, rsp
0x180001897  mov     [rsp+108h+var_18], rax
0x18000189f  mov     rsi, rdx
0x1800018a2  mov     rdi, rcx
0x1800018a5  test    rcx, rcx
0x1800018a8  jz      loc_1800019A7
0x1800018ae  test    rdx, rdx
0x1800018b1  jz      loc_180001A72
0x1800018b7  mov     ecx, 41h ; 'A'
0x1800018bc  mov     rax, rdi
0x1800018bf  nop
0x1800018c0  cmp     word ptr [rax], 0
0x1800018c4  jz      short loc_180001907
0x1800018c6  add     rax, 2
0x1800018ca  sub     rcx, 1
0x1800018ce  jnz     short loc_1800018C0
0x1800018d0  mov     rcx, [rsp+108h]; this
0x1800018d8  lea     rax, aNameLs; "Name %ls"
0x1800018df  mov     [rsp+108h+var_E0], rdi; char *
0x1800018e4  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800018eb  mov     r9d, 80070057h; char *
0x1800018f1  mov     qword ptr [rsp+108h+var_E8], rax; int
0x1800018f6  mov     edx, 0BDDh; void *
0x1800018fb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180001900  mov     eax, 80070057h
0x180001905  jmp     short loc_180001985
0x180001907  mov     eax, 41h ; 'A'
0x18000190c  cmp     rax, rcx
0x18000190f  jz      loc_1800019CD
0x180001915  lea     rax, [rsp+108h+Sid]
0x18000191a  mov     [rsp+108h+arg_10], rbx
0x180001922  xor     ebx, ebx
0x180001924  mov     [rsp+108h+packageFamilyNameLength], 210000h
0x18000192c  lea     r9, [rsp+108h+var_B8]
0x180001931  mov     [rsp+108h+Sid], rbx
0x180001936  lea     r8, [rsp+108h+packageFamilyNameLength]
0x18000193b  mov     [rsp+108h+var_B8], rbx
0x180001940  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x180001947  mov     qword ptr [rsp+108h+var_E8], rax
0x18000194c  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x180001951  cmp     [rsp+108h+packageFamilyNameLength], 210001h
0x180001959  jz      loc_180001A9B
0x18000195f  mov     rdx, rsi
0x180001962  mov     rcx, rdi
0x180001965  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18000196c  nop     dword ptr [rax+rax+00h]
0x180001971  mov     ebx, eax
0x180001973  test    eax, eax
0x180001975  js      loc_180001B61
0x18000197b  xor     eax, eax
0x18000197d  mov     rbx, [rsp+108h+arg_10]
0x180001985  mov     rcx, [rsp+108h+var_18]
0x18000198d  xor     rcx, rsp; StackCookie
0x180001990  call    __security_check_cookie
0x180001995  mov     rsi, [rsp+108h+arg_18]
0x18000199d  add     rsp, 100h
0x1800019a4  pop     rdi
0x1800019a5  retn
0x1800019a7  mov     rcx, [rsp+108h]; this
0x1800019af  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800019b6  mov     r9d, 80070057h; char *
0x1800019bc  mov     edx, 0BD8h; void *
0x1800019c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800019c6  mov     eax, 80070057h
0x1800019cb  jmp     short loc_180001985
0x1800019cd  mov     rcx, [rsp+108h]; this
0x1800019d5  lea     rax, aNameLs; "Name %ls"
0x1800019dc  mov     [rsp+108h+var_E0], rdi; char *
0x1800019e1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800019e8  mov     r9d, 80070057h; char *
0x1800019ee  mov     qword ptr [rsp+108h+var_E8], rax; int
0x1800019f3  mov     edx, 0BDFh; void *
0x1800019f8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800019fd  mov     eax, 80070057h
0x180001a02  jmp     short loc_180001985
0x180001a04  mov     rcx, [rsp+108h]; this
0x180001a0c  lea     rax, [rsp+108h+packageFamilyName]
0x180001a11  mov     [rsp+108h+var_D8], rax
0x180001a16  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180001a1d  lea     rax, aNameLsFamilyLs; "Name %ls family %ls"
0x180001a24  mov     [rsp+108h+var_E0], rdi; char *
0x180001a29  mov     r9d, ebx; char *
0x180001a2c  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180001a31  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180001a36  mov     rcx, [rsp+108h+Sid]; Sid
0x180001a3b  test    rcx, rcx
0x180001a3e  jz      short loc_180001A4C
0x180001a40  call    cs:__imp_RtlFreeSid
0x180001a47  nop     dword ptr [rax+rax+00h]
0x180001a4c  mov     eax, ebx
0x180001a4e  jmp     loc_18000197D
0x180001a53  mov     rcx, [rsp+108h+Sid]; Sid
0x180001a58  test    rcx, rcx
0x180001a5b  jz      loc_18000197B
0x180001a61  call    cs:__imp_RtlFreeSid
0x180001a68  nop     dword ptr [rax+rax+00h]
0x180001a6d  jmp     loc_18000197B
0x180001a72  mov     rcx, [rsp+108h]; this
0x180001a7a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180001a81  mov     r9d, 80070057h; char *
0x180001a87  mov     edx, 0BD9h; void *
0x180001a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001a91  mov     eax, 80070057h
0x180001a96  jmp     loc_180001985
0x180001a9b  lea     r8, [rsp+108h+packageFamilyName]; packageFamilyName
0x180001aa0  mov     [rsp+108h+packageFamilyNameLength], 41h ; 'A'
0x180001aa8  lea     rdx, [rsp+108h+packageFamilyNameLength]; packageFamilyNameLength
0x180001aad  mov     rcx, 0FFFFFFFFFFFFFFFAh; token
0x180001ab4  call    cs:__imp_GetPackageFamilyNameFromToken
0x180001abb  nop     dword ptr [rax+rax+00h]
0x180001ac0  mov     r9d, eax; char *
0x180001ac3  test    eax, eax
0x180001ac5  jz      short loc_180001AF6
0x180001ac7  mov     rcx, [rsp+108h]; this
0x180001acf  lea     rax, aNameLs; "Name %ls"
0x180001ad6  mov     [rsp+108h+var_E0], rdi; char *
0x180001adb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180001ae2  mov     edx, 0BF2h; void *
0x180001ae7  mov     qword ptr [rsp+108h+var_E8], rax; unsigned int
0x180001aec  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180001af1  jmp     loc_18000197D
0x180001af6  lea     rdx, [rsp+108h+packageFamilyName]; lpString2
0x180001afb  mov     rcx, rdi; lpString1
0x180001afe  call    cs:__imp_lstrcmpiW
0x180001b05  nop     dword ptr [rax+rax+00h]
0x180001b0a  test    eax, eax
0x180001b0c  jz      loc_18000197B
0x180001b12  lea     rdx, [rsp+108h+Sid]
0x180001b17  mov     [rsp+108h+Sid], rbx
0x180001b1c  lea     rcx, [rsp+108h+packageFamilyName]
0x180001b21  call    cs:__imp_PackageSidFromFamilyName
0x180001b28  nop     dword ptr [rax+rax+00h]
0x180001b2d  mov     ebx, eax
0x180001b2f  test    eax, eax
0x180001b31  jns     short loc_180001B3D
0x180001b33  mov     edx, 0BF8h; void *
0x180001b38  jmp     loc_180001A04
0x180001b3d  mov     rcx, [rsp+108h+Sid]; pSid
0x180001b42  mov     r8, rsi; Sid
0x180001b45  mov     rdx, rdi; char *
0x180001b48  call    ?DeriveChildAppContainerSid@AppContainerRegistrationHelper@@SAJPEAXPEBGPEAPEAX@Z; AppContainerRegistrationHelper::DeriveChildAppContainerSid(void *,ushort const *,void * *)
0x180001b4d  mov     ebx, eax
0x180001b4f  test    eax, eax
0x180001b51  jns     loc_180001A53
0x180001b57  mov     edx, 0BFCh
0x180001b5c  jmp     loc_180001A04
0x180001b61  mov     rcx, [rsp+108h]; this
0x180001b69  lea     rax, aNameLs; "Name %ls"
0x180001b70  mov     [rsp+108h+var_E0], rdi; char *
0x180001b75  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180001b7c  mov     r9d, ebx; char *
0x180001b7f  mov     qword ptr [rsp+108h+var_E8], rax; int
0x180001b84  mov     edx, 0C03h; void *
0x180001b89  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180001b8e  mov     eax, ebx
0x180001b90  jmp     loc_18000197D
```
