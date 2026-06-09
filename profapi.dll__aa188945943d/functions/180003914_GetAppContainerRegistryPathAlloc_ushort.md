# GetAppContainerRegistryPathAlloc(ushort * *)

- ea: `0x180003914`
- end: `0x180003e12`
- name: `?GetAppContainerRegistryPathAlloc@@YAJPEAPEAG@Z`
- size: `1278`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003840`
- `0x180015d60`

## callees

- `0x180003914`
- `0x180003e20`
- `0x180003fdc`
- `0x180004990`
- `0x180005b60`
- `0x180005b90`
- `0x18000608c`
- `0x1800064b0`
- `0x18000a214`
- `0x18000ce3c`
- `0x18000d00c`
- `0x18000dc34`
- `0x18000fa10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ae0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003afd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ca1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ae0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003afd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ca1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800039cc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800039cc`
- `ntdll!RtlFreeSid` at `0x180003d74`
- `ntdll!RtlFreeSid` at `0x180003d7f`
- `ntdll!RtlFreeSid` at `0x180003d98`
- `ntdll!RtlFreeSid` at `0x180003dd5`
- `ntdll!RtlFreeSid` at `0x180003de0`
- `ntdll!RtlFreeSid` at `0x180003df9`
- `ntdll!RtlFreeSid` at `0x180003d74`
- `ntdll!RtlFreeSid` at `0x180003d7f`
- `ntdll!RtlFreeSid` at `0x180003d98`
- `ntdll!RtlFreeSid` at `0x180003dd5`
- `ntdll!RtlFreeSid` at `0x180003de0`
- `ntdll!RtlFreeSid` at `0x180003df9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003a1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003a1b`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180003bc4`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180003bc4`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x180003bdb`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!PackageSidFromFamilyName` at `0x180003bdb`

## string_xrefs

- `0x180003b57`: `minio\profapi\registry.cpp`
- `0x180003bf9`: `minio\profapi\registry.cpp`
- `0x180003c47`: `minio\profapi\registry.cpp`
- `0x180003c7c`: `minio\profapi\registry.cpp`
- `0x180003ce2`: `minio\profapi\registry.cpp`
- `0x180003d3f`: `minio\profapi\registry.cpp`
- `0x180003d5c`: `minio\profapi\registry.cpp`
- `0x180003daa`: `minio\profapi\registry.cpp`

## pseudocode

```c
__int64 __fastcall GetAppContainerRegistryPathAlloc(unsigned __int16 **a1)
{
  int IsRunningInAppContainer; // eax
  __int64 v3; // rdx
  unsigned int LastError; // ebx
  char *v5; // rbx
  const char *v6; // r9
  PSID v7; // rsi
  int SidString; // eax
  unsigned int v9; // edi
  const char *v10; // r9
  int AppContainerSpecificSubPath; // eax
  HLOCAL v12; // rdi
  int v13; // eax
  int v14; // esi
  unsigned __int16 *v15; // rax
  unsigned int PackageFamilyNameFromToken; // eax
  unsigned int v18; // eax
  bool v19; // cc
  int v20; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  unsigned int *ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int ReturnLengthb; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v26; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v34; // [rsp+78h] [rbp-88h] BYREF
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+88h] [rbp-78h]
  HLOCAL hMem[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v38[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-50h] BYREF
  void *TokenInformation; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  *a1 = 0;
  packageFamilyNameLength = 0;
  TokenHandle = 0;
  IsRunningInAppContainer = _IsRunningInAppContainer((int *)&packageFamilyNameLength, &TokenHandle);
  LastError = IsRunningInAppContainer;
  if ( IsRunningInAppContainer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"minio\\profapi\\registry.cpp",
      (const char *)(unsigned int)IsRunningInAppContainer,
      ReturnLength);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return LastError;
  }
  Sid = 0;
  v26 = 0;
  *(_QWORD *)v38 = 0;
  v39 = 0;
  ReturnLengtha = v38;
  v5 = (char *)TokenHandle;
  AppModelPolicy_GetPolicy_Internal(TokenHandle, v3, &v26, &v39);
  if ( packageFamilyNameLength )
  {
    v26 = 76;
    if ( GetTokenInformation(v5, TokenAppContainerSid, &TokenInformation, 0x4Cu, &v26) )
    {
      v7 = TokenInformation;
LABEL_5:
      hMem[0] = 0;
      hMem[1] = (HLOCAL)-1LL;
      hMem[2] = (HLOCAL)-1LL;
      SidString = GetSidString(v5, (unsigned __int16 **)hMem);
      v9 = SidString;
      if ( SidString < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x60,
          (unsigned int)"minio\\profapi\\registry.cpp",
          (const char *)(unsigned int)SidString,
          (int)ReturnLengtha);
LABEL_29:
        if ( hMem[0] )
          LocalFree(hMem[0]);
        if ( Sid )
          RtlFreeSid(Sid);
        v19 = (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_34:
        if ( v19 )
          CloseHandle(v5);
        return v9;
      }
      StringSid = 0;
      v29 = -1;
      v30 = -1;
      if ( ConvertSidToStringSidW(v7, &StringSid) )
      {
        v31 = 0;
        v32 = 0;
        v33 = 0;
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v31);
        v32 = -1;
        v33 = -1;
        AppContainerSpecificSubPath = _GetAppContainerSpecificSubPath(v5, StringSid, 1, &v31);
        v9 = AppContainerSpecificSubPath;
        if ( AppContainerSpecificSubPath >= 0 )
        {
          v34 = 0;
          v35 = 0;
          v36 = 0;
          ReturnLengthb = (int)v31;
          v12 = hMem[0];
          v13 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
                  &v34,
                  L"%s\\%s%s",
                  hMem[0],
                  L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Storage\\");
          v14 = v13;
          if ( v13 >= 0 )
          {
            v15 = v34;
            v34 = 0;
            v36 = 0;
            v35 = 0;
            *a1 = v15;
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v34);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v31);
            if ( StringSid )
            {
              LocalFree(StringSid);
              StringSid = 0;
            }
            v29 = 0;
            v30 = 0;
            if ( v12 )
              LocalFree(v12);
            if ( Sid )
              RtlFreeSid(Sid);
            if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v5);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6D,
            (unsigned int)"minio\\profapi\\registry.cpp",
            (const char *)(unsigned int)v13,
            ReturnLengthb);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v34);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v31);
          Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free((__int64)&StringSid);
          Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free((__int64)hMem);
          if ( Sid )
            RtlFreeSid(Sid);
          LastError = v14;
          goto LABEL_45;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"minio\\profapi\\registry.cpp",
          (const char *)(unsigned int)AppContainerSpecificSubPath,
          (int)ReturnLengtha);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v31);
        if ( StringSid )
        {
          LocalFree(StringSid);
          StringSid = 0;
        }
        v29 = 0;
        v30 = 0;
        goto LABEL_29;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x63,
                    (unsigned int)"minio\\profapi\\registry.cpp",
                    v10);
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free((__int64)&StringSid);
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free((__int64)hMem);
LABEL_43:
      if ( Sid )
        RtlFreeSid(Sid);
LABEL_45:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return LastError;
    }
    v20 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x4B,
            (unsigned int)"minio\\profapi\\registry.cpp",
            v6);
    goto LABEL_51;
  }
  if ( v26 == 2162689 )
  {
    packageFamilyNameLength = 65;
    PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(v5, &packageFamilyNameLength, packageFamilyName);
    if ( !PackageFamilyNameFromToken )
    {
      v18 = PackageSidFromFamilyName(packageFamilyName, &Sid);
      if ( v18 )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x55,
               (unsigned int)"minio\\profapi\\registry.cpp",
               (const char *)v18,
               (unsigned int)v38);
        if ( Sid )
          RtlFreeSid(Sid);
        v19 = (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
        goto LABEL_34;
      }
      v7 = Sid;
      goto LABEL_5;
    }
    v20 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x53,
            (unsigned int)"minio\\profapi\\registry.cpp",
            (const char *)PackageFamilyNameFromToken,
            (unsigned int)v38);
LABEL_51:
    LastError = v20;
    goto LABEL_43;
  }
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180003914  mov     [rsp-8+arg_8], rbx
0x180003919  mov     [rsp-8+arg_10], rsi
0x18000391e  push    rbp
0x18000391f  push    rdi
0x180003920  push    r12
0x180003922  push    r14
0x180003924  push    r15
0x180003926  lea     rbp, [rsp-0B0h]
0x18000392e  sub     rsp, 1B0h
0x180003935  mov     rax, cs:__security_cookie
0x18000393c  xor     rax, rsp
0x18000393f  mov     [rbp+0D0h+var_30], rax
0x180003946  mov     r14, rcx
0x180003949  xor     r15d, r15d
0x18000394c  mov     [rcx], r15
0x18000394f  mov     [rsp+1D0h+packageFamilyNameLength], r15d
0x180003954  mov     [rsp+1D0h+TokenHandle], r15
0x180003959  lea     rdx, [rsp+1D0h+TokenHandle]; void **
0x18000395e  lea     rcx, [rsp+1D0h+packageFamilyNameLength]; int *
0x180003963  call    ?_IsRunningInAppContainer@@YAJPEAHPEAPEAX@Z; _IsRunningInAppContainer(int *,void * *)
0x180003968  mov     ebx, eax
0x18000396a  test    eax, eax
0x18000396c  js      loc_180003B4D
0x180003972  mov     [rsp+1D0h+Sid], r15
0x180003977  mov     [rsp+1D0h+var_194], r15d
0x18000397c  mov     qword ptr [rbp+0D0h+var_128], r15
0x180003980  mov     [rbp+0D0h+var_120], r15
0x180003984  lea     rax, [rbp+0D0h+var_128]
0x180003988  mov     [rsp+1D0h+ReturnLength], rax; unsigned int
0x18000398d  lea     r9, [rbp+0D0h+var_120]
0x180003991  lea     r8, [rsp+1D0h+var_194]
0x180003996  mov     rbx, [rsp+1D0h+TokenHandle]
0x18000399b  mov     rcx, rbx
0x18000399e  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x1800039a3  cmp     [rsp+1D0h+packageFamilyNameLength], r15d
0x1800039a8  jz      loc_180003B80
0x1800039ae  lea     r9d, [r15+4Ch]; TokenInformationLength
0x1800039b2  mov     [rsp+1D0h+var_194], r9d
0x1800039b7  lea     rax, [rsp+1D0h+var_194]
0x1800039bc  mov     [rsp+1D0h+ReturnLength], rax; int
0x1800039c1  lea     r8, [rbp+0D0h+TokenInformation]; TokenInformation
0x1800039c5  lea     edx, [r15+1Fh]; TokenInformationClass
0x1800039c9  mov     rcx, rbx; TokenHandle
0x1800039cc  call    cs:__imp_GetTokenInformation
0x1800039d2  test    eax, eax
0x1800039d4  jz      loc_180003D38
0x1800039da  mov     rsi, [rbp+0D0h+TokenInformation]
0x1800039de  mov     [rbp+0D0h+hMem], r15
0x1800039e2  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800039e6  mov     [rbp+0D0h+var_138], r12
0x1800039ea  mov     [rbp+0D0h+var_130], r12
0x1800039ee  lea     rdx, [rbp+0D0h+hMem]; unsigned __int16 **
0x1800039f2  mov     rcx, rbx; TokenHandle
0x1800039f5  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x1800039fa  mov     edi, eax
0x1800039fc  test    eax, eax
0x1800039fe  js      loc_180003BEF
0x180003a04  mov     [rsp+1D0h+StringSid], r15
0x180003a09  mov     [rsp+1D0h+var_180], r12
0x180003a0e  mov     [rsp+1D0h+var_178], r12
0x180003a13  lea     rdx, [rsp+1D0h+StringSid]; StringSid
0x180003a18  mov     rcx, rsi; Sid
0x180003a1b  call    cs:__imp_ConvertSidToStringSidW
0x180003a21  test    eax, eax
0x180003a23  jz      loc_180003DA3
0x180003a29  mov     [rsp+1D0h+var_170], r15
0x180003a2e  mov     [rsp+1D0h+var_168], r15
0x180003a33  mov     [rsp+1D0h+var_160], r15
0x180003a38  lea     rcx, [rsp+1D0h+var_170]
0x180003a3d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003a42  mov     [rsp+1D0h+var_168], r12
0x180003a47  mov     [rsp+1D0h+var_160], r12
0x180003a4c  lea     r9, [rsp+1D0h+var_170]; unsigned __int16 **
0x180003a51  lea     r8d, [r12+2]; int
0x180003a56  mov     rdx, [rsp+1D0h+StringSid]; unsigned __int16 *
0x180003a5b  mov     rcx, rbx; void *
0x180003a5e  call    ?_GetAppContainerSpecificSubPath@@YAJPEAXPEBGHPEAPEAG@Z; _GetAppContainerSpecificSubPath(void *,ushort const *,int,ushort * *)
0x180003a63  mov     edi, eax
0x180003a65  test    eax, eax
0x180003a67  js      loc_180003C72
0x180003a6d  mov     [rsp+1D0h+var_158], r15
0x180003a72  mov     [rbp+0D0h+var_150], r15
0x180003a76  mov     [rbp+0D0h+var_148], r15
0x180003a7a  mov     rax, [rsp+1D0h+var_170]
0x180003a7f  mov     [rsp+1D0h+ReturnLength], rax; int
0x180003a84  lea     r9, aSoftwareClasse; "Software\\Classes\\Local Settings\\Soft"...
0x180003a8b  mov     rdi, [rbp+0D0h+hMem]
0x180003a8f  mov     r8, rdi
0x180003a92  lea     rdx, aSSS; "%s\\%s%s"
0x180003a99  lea     rcx, [rsp+1D0h+var_158]
0x180003a9e  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180003aa3  mov     esi, eax
0x180003aa5  test    eax, eax
0x180003aa7  js      loc_180003CD8
0x180003aad  mov     rax, [rsp+1D0h+var_158]
0x180003ab2  mov     [rsp+1D0h+var_158], r15
0x180003ab7  mov     [rbp+0D0h+var_148], r15
0x180003abb  mov     [rbp+0D0h+var_150], r15
0x180003abf  mov     [r14], rax
0x180003ac2  lea     rcx, [rsp+1D0h+var_158]
0x180003ac7  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003acc  lea     rcx, [rsp+1D0h+var_170]
0x180003ad1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003ad6  mov     rcx, [rsp+1D0h+StringSid]; hMem
0x180003adb  test    rcx, rcx
0x180003ade  jz      short loc_180003AEB
0x180003ae0  call    cs:__imp_LocalFree
0x180003ae6  mov     [rsp+1D0h+StringSid], r15
0x180003aeb  mov     [rsp+1D0h+var_180], r15
0x180003af0  mov     [rsp+1D0h+var_178], r15
0x180003af5  test    rdi, rdi
0x180003af8  jz      short loc_180003B04
0x180003afa  mov     rcx, rdi; hMem
0x180003afd  call    cs:__imp_LocalFree
0x180003b03  nop
0x180003b04  mov     rcx, [rsp+1D0h+Sid]; Sid
0x180003b09  test    rcx, rcx
0x180003b0c  jnz     loc_180003DE0
0x180003b12  lea     rax, [rbx-1]
0x180003b16  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003b1a  jbe     loc_180003DEB
0x180003b20  xor     eax, eax
0x180003b22  mov     rcx, [rbp+0D0h+var_30]
0x180003b29  xor     rcx, rsp; StackCookie
0x180003b2c  call    __security_check_cookie
0x180003b31  lea     r11, [rsp+1D0h+var_20]
0x180003b39  mov     rbx, [r11+38h]
0x180003b3d  mov     rsi, [r11+40h]
0x180003b41  mov     rsp, r11
0x180003b44  pop     r15
0x180003b46  pop     r14
0x180003b48  pop     r12
0x180003b4a  pop     rdi
0x180003b4b  pop     rbp
0x180003b4c  retn
0x180003b4d  mov     rcx, [rbp+0D8h]; this
0x180003b54  mov     r9d, ebx; char *
0x180003b57  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180003b5e  mov     edx, 3Ah ; ':'; void *
0x180003b63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b68  nop
0x180003b69  mov     rcx, [rsp+1D0h+TokenHandle]; hObject
0x180003b6e  lea     rdx, [rcx-1]
0x180003b72  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180003b76  jbe     loc_180003D2D
0x180003b7c  mov     eax, ebx
0x180003b7e  jmp     short loc_180003B22
0x180003b80  cmp     [rsp+1D0h+var_194], 210001h
0x180003b88  jz      short loc_180003BB0
0x180003b8a  mov     rcx, [rsp+1D0h+Sid]; Sid
0x180003b8f  test    rcx, rcx
0x180003b92  jnz     loc_180003DF9
0x180003b98  lea     rax, [rbx-1]
0x180003b9c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003ba0  jbe     loc_180003E04
0x180003ba6  mov     eax, 8000FFFFh
0x180003bab  jmp     loc_180003B22
0x180003bb0  mov     [rsp+1D0h+packageFamilyNameLength], 41h ; 'A'
0x180003bb8  lea     r8, [rbp+0D0h+packageFamilyName]; packageFamilyName
0x180003bbc  lea     rdx, [rsp+1D0h+packageFamilyNameLength]; packageFamilyNameLength
0x180003bc1  mov     rcx, rbx; token
0x180003bc4  call    cs:__imp_GetPackageFamilyNameFromToken
0x180003bca  test    eax, eax
0x180003bcc  jnz     loc_180003D52
0x180003bd2  lea     rdx, [rsp+1D0h+Sid]
0x180003bd7  lea     rcx, [rbp+0D0h+packageFamilyName]
0x180003bdb  call    cs:__imp_PackageSidFromFamilyName
0x180003be1  test    eax, eax
0x180003be3  jnz     short loc_180003C3D
0x180003be5  mov     rsi, [rsp+1D0h+Sid]
0x180003bea  jmp     loc_1800039DE
0x180003bef  mov     rcx, [rbp+0D8h]; this
0x180003bf6  mov     r9d, edi; char *
0x180003bf9  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180003c00  mov     edx, 60h ; '`'; void *
0x180003c05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c0a  mov     rcx, [rbp+0D0h+hMem]; hMem
0x180003c0e  test    rcx, rcx
0x180003c11  jz      short loc_180003C1A
0x180003c13  call    cs:__imp_LocalFree
0x180003c19  nop
0x180003c1a  mov     rcx, [rsp+1D0h+Sid]; Sid
0x180003c1f  test    rcx, rcx
0x180003c22  jnz     loc_180003D98
0x180003c28  lea     rax, [rbx-1]
0x180003c2c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003c30  jbe     loc_180003D8A
0x180003c36  mov     eax, edi
0x180003c38  jmp     loc_180003B22
0x180003c3d  mov     rcx, [rbp+0D8h]; this
0x180003c44  mov     r9d, eax; char *
0x180003c47  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180003c4e  mov     edx, 55h ; 'U'; void *
0x180003c53  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180003c58  mov     edi, eax
0x180003c5a  mov     rcx, [rsp+1D0h+Sid]; Sid
0x180003c5f  test    rcx, rcx
0x180003c62  jnz     loc_180003D7F
0x180003c68  lea     rdx, [rbx-1]
0x180003c6c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180003c70  jmp     short loc_180003C30
0x180003c72  mov     rcx, [rbp+0D8h]; this
0x180003c79  mov     r9d, edi; char *
0x180003c7c  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180003c83  mov     edx, 6Ah ; 'j'; void *
0x180003c88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c8d  lea     rcx, [rsp+1D0h+var_170]
0x180003c92  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003c97  mov     rcx, [rsp+1D0h+StringSid]; hMem
0x180003c9c  test    rcx, rcx
0x180003c9f  jz      short loc_180003CAC
0x180003ca1  call    cs:__imp_LocalFree
0x180003ca7  mov     [rsp+1D0h+StringSid], r15
0x180003cac  mov     [rsp+1D0h+var_180], r15
0x180003cb1  mov     [rsp+1D0h+var_178], r15
0x180003cb6  jmp     loc_180003C0A
0x180003cbb  mov     rcx, [rsp+1D0h+Sid]; Sid
0x180003cc0  test    rcx, rcx
0x180003cc3  jnz     loc_180003D74
0x180003cc9  lea     rcx, [rsp+1D0h+TokenHandle]
0x180003cce  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003cd3  jmp     loc_180003B7C
0x180003cd8  mov     rcx, [rbp+0D8h]; this
0x180003cdf  mov     r9d, esi; char *
0x180003ce2  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180003ce9  mov     edx, 6Dh ; 'm'; void *
0x180003cee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cf3  lea     rcx, [rsp+1D0h+var_158]
0x180003cf8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003cfd  lea     rcx, [rsp+1D0h+var_170]
0x180003d02  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003d07  lea     rcx, [rsp+1D0h+StringSid]
0x180003d0c  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180003d11  lea     rcx, [rbp+0D0h+hMem]
0x180003d15  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180003d1a  nop
0x180003d1b  mov     rcx, [rsp+1D0h+Sid]; Sid
0x180003d20  test    rcx, rcx
0x180003d23  jnz     loc_180003DD5
0x180003d29  mov     ebx, esi
0x180003d2b  jmp     short loc_180003CC9
0x180003d2d  call    cs:__imp_CloseHandle
0x180003d33  jmp     loc_180003B7C
0x180003d38  mov     rcx, [rbp+0D8h]; this
0x180003d3f  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180003d46  mov     edx, 4Bh ; 'K'; void *
0x180003d4b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003d50  jmp     short loc_180003D6D
0x180003d52  mov     rcx, [rbp+0D8h]; this
0x180003d59  mov     r9d, eax; char *
0x180003d5c  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180003d63  mov     edx, 53h ; 'S'; void *
0x180003d68  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180003d6d  mov     ebx, eax
0x180003d6f  jmp     loc_180003CBB
0x180003d74  call    cs:__imp_RtlFreeSid
0x180003d7a  jmp     loc_180003CC9
0x180003d7f  call    cs:__imp_RtlFreeSid
0x180003d85  jmp     loc_180003C68
0x180003d8a  mov     rcx, rbx; hObject
0x180003d8d  call    cs:__imp_CloseHandle
0x180003d93  jmp     loc_180003C36
0x180003d98  call    cs:__imp_RtlFreeSid
0x180003d9e  jmp     loc_180003C28
0x180003da3  mov     rcx, [rbp+0D8h]; this
0x180003daa  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x180003db1  mov     edx, 63h ; 'c'; void *
0x180003db6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003dbb  mov     ebx, eax
0x180003dbd  lea     rcx, [rsp+1D0h+StringSid]
0x180003dc2  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180003dc7  lea     rcx, [rbp+0D0h+hMem]
0x180003dcb  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180003dd0  jmp     loc_180003CBB
0x180003dd5  call    cs:__imp_RtlFreeSid
0x180003ddb  jmp     loc_180003D29
0x180003de0  call    cs:__imp_RtlFreeSid
0x180003de6  jmp     loc_180003B12
0x180003deb  mov     rcx, rbx; hObject
0x180003dee  call    cs:__imp_CloseHandle
0x180003df4  jmp     loc_180003B20
0x180003df9  call    cs:__imp_RtlFreeSid
0x180003dff  jmp     loc_180003B98
0x180003e04  mov     rcx, rbx; hObject
0x180003e07  call    cs:__imp_CloseHandle
0x180003e0d  jmp     loc_180003BA6
```
