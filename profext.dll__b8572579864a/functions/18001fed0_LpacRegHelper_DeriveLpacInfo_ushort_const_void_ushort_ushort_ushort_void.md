# LpacRegHelper::DeriveLpacInfo(ushort const *,void * *,ushort * *,ushort * *,ushort * *,void * *)

- ea: `0x18001fed0`
- end: `0x180020480`
- name: `?DeriveLpacInfo@LpacRegHelper@@CAJPEBGPEAPEAXPEAPEAG221@Z`
- size: `1456`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, void **@<rdx>, unsigned __int16 **@<r8>, unsigned __int16 **@<r9>, unsigned __int16 **, void **)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f390`
- `0x18001fc88`
- `0x180020664`

## callees

- `0x180001854`
- `0x180001ba0`
- `0x180001cfc`
- `0x180001ef0`
- `0x1800044e0`
- `0x180006760`
- `0x18000aacc`
- `0x18000beb0`
- `0x18000c7d4`
- `0x18000c8d8`
- `0x18000c938`
- `0x18000f440`
- `0x18000f6cc`
- `0x18000f884`
- `0x18000f9ac`
- `0x180016740`
- `0x180017014`
- `0x18001a86c`
- `0x18001eef0`
- `0x18001fed0`
- `0x180021534`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x1800200e1`
- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x1800200e1`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180020160`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180020309`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180020160`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180020309`
- `ntdll!RtlFreeSid` at `0x180020138`
- `ntdll!RtlFreeSid` at `0x180020138`
- `ntdll!RtlDowncaseUnicodeString` at `0x1800202b1`
- `ntdll!RtlDowncaseUnicodeString` at `0x1800202b1`
- `ntdll!RtlInitUnicodeString` at `0x18002029a`
- `ntdll!RtlInitUnicodeString` at `0x18002029a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002020c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002020c`

## string_xrefs

- `0x18001ff4a`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001ff83`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001ffec`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020036`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18002008f`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020109`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020193`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x1800201db`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18002022c`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x1800202d9`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18002036e`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LpacRegHelper::DeriveLpacInfo(
        char *a1,
        void **a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        void **a6)
{
  unsigned int LastErrorMsg; // ebx
  int v11; // eax
  HANDLE v12; // rbx
  int IsAppContainerToken; // eax
  __int64 v14; // rdx
  int v15; // esi
  int AppContainerSidFromToken; // eax
  unsigned int PackageFamilyNameFromToken; // eax
  int UserSid; // eax
  __int64 v19; // rdx
  void *v20; // rdx
  unsigned int v21; // r8d
  const char *v22; // r9
  NTSTATUS v23; // eax
  int v24; // eax
  int v25; // eax
  PSID v26; // rax
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rax
  PSID v29; // rax
  PSID Sid; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+48h] [rbp-B8h] BYREF
  char *v32; // [rsp+50h] [rbp-B0h] BYREF
  PSID v33; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  PSID v35; // [rsp+68h] [rbp-98h] BYREF
  HANDLE token; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING UniDest; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v37 = 0;
  token = 0;
  LastErrorMsg = StringCchLengthW((const unsigned __int16 *)a1, 0x41u, (unsigned __int64 *)&token);
  if ( LastErrorMsg == -2147024809 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x80070057LL,
      (int)"Name %ls",
      a1);
    return 2147942487LL;
  }
  if ( (LastErrorMsg & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)LastErrorMsg,
      (int)"Name %ls",
      a1);
    return LastErrorMsg;
  }
  if ( !token )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x80070057LL,
      (int)"Name %ls",
      a1);
    return 2147942487LL;
  }
  token = 0;
  v11 = AppContainerRegistrationHelper::OpenCurrentUserToken((char *)0xE, &token);
  LastErrorMsg = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)v11,
      (int)"Name %ls",
      a1);
LABEL_40:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
    return LastErrorMsg;
  }
  packageFamilyNameLength = 0;
  v12 = token;
  IsAppContainerToken = AppContainerRegistrationHelper::IsAppContainerToken(token, (int *)&packageFamilyNameLength);
  v15 = IsAppContainerToken;
  if ( IsAppContainerToken < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)IsAppContainerToken,
      (int)"Name %ls",
      a1);
LABEL_13:
    LastErrorMsg = v15;
    goto LABEL_40;
  }
  Sid = 0;
  if ( packageFamilyNameLength )
  {
    Sid = 0;
    AppContainerSidFromToken = AppContainerRegistrationHelper::GetAppContainerSidFromToken(v12, &Sid);
    v15 = AppContainerSidFromToken;
    if ( AppContainerSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x138,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)(unsigned int)AppContainerSidFromToken,
        (int)"Name %ls",
        a1);
LABEL_17:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
      goto LABEL_13;
    }
  }
  else
  {
    packageFamilyNameLength = 2162688;
    AppModelPolicy_GetPolicy(v12, v14, &packageFamilyNameLength);
    if ( packageFamilyNameLength == 2162689 )
    {
      packageFamilyNameLength = 65;
      PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(v12, &packageFamilyNameLength, packageFamilyName);
      if ( PackageFamilyNameFromToken )
      {
        LastErrorMsg = wil::details::in1diag3::Return_Win32Msg(
                         retaddr,
                         (void *)0x14C,
                         (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
                         (const char *)PackageFamilyNameFromToken,
                         (unsigned int)"Name %ls",
                         a1);
LABEL_39:
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
        goto LABEL_40;
      }
      Sid = 0;
      v15 = AppContainerDeriveSidFromMoniker(packageFamilyName, &Sid);
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x14F,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
          (const char *)(unsigned int)v15,
          (int)"Name %ls family %ls",
          a1,
          packageFamilyName);
        goto LABEL_17;
      }
    }
  }
  v33 = 0;
  UserSid = GetUserSid(v12, &v33);
  LastErrorMsg = UserSid;
  if ( UserSid < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)UserSid,
      (int)"Name %ls",
      a1);
LABEL_38:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v33);
    goto LABEL_39;
  }
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( !ConvertSidToStringSidW(v33, &StringSid) )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x157,
                     (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
                     "Name %ls",
                     a1);
LABEL_37:
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
    goto LABEL_38;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v32,
    v19,
    65);
  v37 = 2;
  if ( !v32 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v20, v21, v22);
  memset_0(v32, 0, 0x82u);
  *(_QWORD *)&UniDest.Length = 4259840;
  UniDest.Buffer = (PWSTR)v32;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, (PCWSTR)a1);
  v23 = RtlDowncaseUnicodeString(&UniDest, &DestinationString, 0);
  if ( v23 < 0 )
  {
    LastErrorMsg = wil::details::in1diag3::Return_NtStatusMsg(
                     retaddr,
                     (void *)0x163,
                     (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
                     (const char *)(unsigned int)v23,
                     (int)"Name %ls",
                     a1);
LABEL_36:
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v32);
    goto LABEL_37;
  }
  v35 = 0;
  if ( Sid )
  {
    v25 = AppContainerRegistrationHelper::DeriveChildAppContainerSid(Sid, (char *)UniDest.Buffer, &v35);
    LastErrorMsg = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x177,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)(unsigned int)v25,
        (int)"Name %ls",
        v32);
      goto LABEL_35;
    }
  }
  else
  {
    v24 = AppContainerDeriveSidFromMoniker(UniDest.Buffer, &v35);
    LastErrorMsg = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x16F,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)(unsigned int)v24,
        (int)"Name %ls",
        v32);
LABEL_35:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
      goto LABEL_36;
    }
  }
  if ( a2 )
  {
    v26 = Sid;
    Sid = 0;
    *a2 = v26;
  }
  if ( a3 )
  {
    v27 = (unsigned __int16 *)v32;
    v32 = 0;
    *a3 = v27;
  }
  if ( a5 )
  {
    v28 = StringSid;
    StringSid = 0;
    *a5 = v28;
  }
  if ( a6 )
  {
    v29 = v35;
    v35 = 0;
    *a6 = v29;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v35);
  wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v32);
  wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v33);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
  return 0;
}

```

## disassembly

```asm
0x18001fed0  mov     [rsp-8+arg_18], rbx
0x18001fed5  push    rbp
0x18001fed6  push    rsi
0x18001fed7  push    rdi
0x18001fed8  push    r12
0x18001feda  push    r13
0x18001fedc  push    r14
0x18001fede  push    r15
0x18001fee0  lea     rbp, [rsp-40h]
0x18001fee5  sub     rsp, 140h
0x18001feec  mov     rax, cs:__security_cookie
0x18001fef3  xor     rax, rsp
0x18001fef6  mov     [rbp+70h+var_40], rax
0x18001fefa  mov     r12, r8
0x18001fefd  mov     r13, rdx
0x18001ff00  mov     rdi, rcx
0x18001ff03  mov     r15, [rbp+70h+arg_20]
0x18001ff0a  mov     r14, [rbp+70h+arg_28]
0x18001ff11  xor     esi, esi
0x18001ff13  mov     [rsp+170h+var_F8], esi
0x18001ff17  mov     [rsp+170h+token], rsi
0x18001ff1c  lea     r8, [rsp+170h+token]; unsigned __int64 *
0x18001ff21  lea     edx, [rsi+41h]; unsigned __int64
0x18001ff24  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001ff29  mov     ebx, eax
0x18001ff2b  mov     eax, 80070057h
0x18001ff30  cmp     ebx, eax
0x18001ff32  jnz     short loc_18001FF67
0x18001ff34  mov     [rsp+170h+var_148], rdi; char *
0x18001ff39  lea     rdx, aNameLs; "Name %ls"
0x18001ff40  mov     [rsp+170h+var_150], rdx; int
0x18001ff45  mov     edx, 126h; void *
0x18001ff4a  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ff51  mov     r9d, eax; char *
0x18001ff54  mov     rcx, [rbp+78h]; this
0x18001ff58  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001ff5d  mov     eax, 80070057h
0x18001ff62  jmp     loc_18002044F
0x18001ff67  test    ebx, ebx
0x18001ff69  jns     short loc_18001FF9B
0x18001ff6b  mov     rcx, [rbp+78h]; this
0x18001ff6f  mov     [rsp+170h+var_148], rdi; char *
0x18001ff74  lea     rdx, aNameLs; "Name %ls"
0x18001ff7b  mov     [rsp+170h+var_150], rdx; int
0x18001ff80  mov     r9d, ebx; char *
0x18001ff83  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001ff8a  mov     edx, 127h; void *
0x18001ff8f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001ff94  mov     eax, ebx
0x18001ff96  jmp     loc_18002044F
0x18001ff9b  cmp     [rsp+170h+token], rsi
0x18001ffa0  jnz     short loc_18001FFBA
0x18001ffa2  mov     [rsp+170h+var_148], rdi
0x18001ffa7  lea     rdx, aNameLs; "Name %ls"
0x18001ffae  mov     [rsp+170h+var_150], rdx
0x18001ffb3  mov     edx, 128h
0x18001ffb8  jmp     short loc_18001FF4A
0x18001ffba  mov     [rsp+170h+token], rsi
0x18001ffbf  lea     rdx, [rsp+170h+token]; void **
0x18001ffc4  mov     ecx, 0Eh; char *
0x18001ffc9  call    ?OpenCurrentUserToken@AppContainerRegistrationHelper@@SAJKPEAPEAX@Z; AppContainerRegistrationHelper::OpenCurrentUserToken(ulong,void * *)
0x18001ffce  mov     ebx, eax
0x18001ffd0  test    eax, eax
0x18001ffd2  jns     short loc_180020002
0x18001ffd4  mov     rcx, [rbp+78h]; this
0x18001ffd8  mov     [rsp+170h+var_148], rdi; char *
0x18001ffdd  lea     rdx, aNameLs; "Name %ls"
0x18001ffe4  mov     [rsp+170h+var_150], rdx; int
0x18001ffe9  mov     r9d, eax; char *
0x18001ffec  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fff3  mov     edx, 12Dh; void *
0x18001fff8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001fffd  jmp     loc_1800203B4
0x180020002  mov     [rsp+170h+packageFamilyNameLength], esi
0x180020006  lea     rdx, [rsp+170h+packageFamilyNameLength]; int *
0x18002000b  mov     rbx, [rsp+170h+token]
0x180020010  mov     rcx, rbx; void *
0x180020013  call    ?IsAppContainerToken@AppContainerRegistrationHelper@@SAJPEAXPEAH@Z; AppContainerRegistrationHelper::IsAppContainerToken(void *,int *)
0x180020018  mov     esi, eax
0x18002001a  test    eax, eax
0x18002001c  jns     short loc_18002004E
0x18002001e  mov     rcx, [rbp+78h]; this
0x180020022  mov     [rsp+170h+var_148], rdi; char *
0x180020027  lea     rdx, aNameLs; "Name %ls"
0x18002002e  mov     [rsp+170h+var_150], rdx; int
0x180020033  mov     r9d, eax; char *
0x180020036  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002003d  mov     edx, 131h; void *
0x180020042  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020047  mov     ebx, esi
0x180020049  jmp     loc_1800203B4
0x18002004e  xor     esi, esi
0x180020050  mov     [rsp+170h+Sid], rsi
0x180020055  mov     rcx, rbx; void *
0x180020058  cmp     [rsp+170h+packageFamilyNameLength], esi
0x18002005c  jz      short loc_1800200AD
0x18002005e  mov     [rsp+170h+Sid], rsi
0x180020063  lea     rdx, [rsp+170h+Sid]; void **
0x180020068  call    ?GetAppContainerSidFromToken@AppContainerRegistrationHelper@@SAJPEAXPEAPEAX@Z; AppContainerRegistrationHelper::GetAppContainerSidFromToken(void *,void * *)
0x18002006d  mov     esi, eax
0x18002006f  test    eax, eax
0x180020071  jns     loc_1800201A9
0x180020077  mov     rcx, [rbp+78h]; this
0x18002007b  mov     [rsp+170h+var_148], rdi; char *
0x180020080  lea     rdx, aNameLs; "Name %ls"
0x180020087  mov     [rsp+170h+var_150], rdx; int
0x18002008c  mov     r9d, eax; char *
0x18002008f  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020096  mov     edx, 138h; void *
0x18002009b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800200a0  nop
0x1800200a1  lea     rcx, [rsp+170h+Sid]
0x1800200a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800200ab  jmp     short loc_180020047
0x1800200ad  mov     [rsp+170h+packageFamilyNameLength], 210000h
0x1800200b5  lea     r8, [rsp+170h+packageFamilyNameLength]
0x1800200ba  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x1800200bf  cmp     [rsp+170h+packageFamilyNameLength], 210001h
0x1800200c7  jnz     loc_1800201AB
0x1800200cd  mov     [rsp+170h+packageFamilyNameLength], 41h ; 'A'
0x1800200d5  lea     r8, [rbp+70h+packageFamilyName]; packageFamilyName
0x1800200d9  lea     rdx, [rsp+170h+packageFamilyNameLength]; packageFamilyNameLength
0x1800200de  mov     rcx, rbx; token
0x1800200e1  call    cs:__imp_GetPackageFamilyNameFromToken
0x1800200e8  nop     dword ptr [rax+rax+00h]
0x1800200ed  test    eax, eax
0x1800200ef  jz      short loc_180020121
0x1800200f1  mov     rcx, [rbp+78h]; this
0x1800200f5  mov     [rsp+170h+var_148], rdi; char *
0x1800200fa  lea     rdx, aNameLs; "Name %ls"
0x180020101  mov     [rsp+170h+var_150], rdx; unsigned int
0x180020106  mov     r9d, eax; char *
0x180020109  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020110  mov     edx, 14Ch; void *
0x180020115  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002011a  mov     ebx, eax
0x18002011c  jmp     loc_1800203A9
0x180020121  mov     rsi, [rsp+170h+Sid]
0x180020126  test    rsi, rsi
0x180020129  jz      short loc_18002014E
0x18002012b  lea     rcx, [rsp+170h+var_118]; this
0x180020130  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180020135  mov     rcx, rsi; Sid
0x180020138  call    cs:__imp_RtlFreeSid
0x18002013f  nop     dword ptr [rax+rax+00h]
0x180020144  lea     rcx, [rsp+170h+var_118]; this
0x180020149  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002014e  mov     [rsp+170h+Sid], 0
0x180020157  lea     rdx, [rsp+170h+Sid]
0x18002015c  lea     rcx, [rbp+70h+packageFamilyName]
0x180020160  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180020167  nop     dword ptr [rax+rax+00h]
0x18002016c  mov     esi, eax
0x18002016e  test    eax, eax
0x180020170  jns     short loc_1800201A9
0x180020172  mov     rcx, [rbp+78h]; this
0x180020176  lea     rax, [rbp+70h+packageFamilyName]
0x18002017a  mov     [rsp+170h+var_140], rax
0x18002017f  mov     [rsp+170h+var_148], rdi; char *
0x180020184  lea     rax, aNameLsFamilyLs; "Name %ls family %ls"
0x18002018b  mov     [rsp+170h+var_150], rax; int
0x180020190  mov     r9d, esi; char *
0x180020193  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002019a  mov     edx, 14Fh; void *
0x18002019f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800201a4  jmp     loc_1800200A1
0x1800201a9  xor     esi, esi
0x1800201ab  mov     [rsp+170h+var_118], rsi
0x1800201b0  lea     rdx, [rsp+170h+var_118]; void **
0x1800201b5  mov     rcx, rbx; TokenHandle
0x1800201b8  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x1800201bd  mov     ebx, eax
0x1800201bf  test    eax, eax
0x1800201c1  jns     short loc_1800201F1
0x1800201c3  mov     rcx, [rbp+78h]; this
0x1800201c7  mov     [rsp+170h+var_148], rdi; char *
0x1800201cc  lea     rdx, aNameLs; "Name %ls"
0x1800201d3  mov     [rsp+170h+var_150], rdx; int
0x1800201d8  mov     r9d, eax; char *
0x1800201db  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800201e2  mov     edx, 154h; void *
0x1800201e7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800201ec  jmp     loc_18002039E
0x1800201f1  mov     [rsp+170h+StringSid], rsi
0x1800201f6  xor     edx, edx
0x1800201f8  lea     rcx, [rsp+170h+StringSid]
0x1800201fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180020202  lea     rdx, [rsp+170h+StringSid]; StringSid
0x180020207  mov     rcx, [rsp+170h+var_118]; Sid
0x18002020c  call    cs:__imp_ConvertSidToStringSidW
0x180020213  nop     dword ptr [rax+rax+00h]
0x180020218  test    eax, eax
0x18002021a  jnz     short loc_180020244
0x18002021c  mov     rcx, [rbp+78h]; this
0x180020220  mov     [rsp+170h+var_150], rdi; char *
0x180020225  lea     r9, aNameLs; "Name %ls"
0x18002022c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020233  mov     edx, 157h; void *
0x180020238  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002023d  mov     ebx, eax
0x18002023f  jmp     loc_180020393
0x180020244  mov     ebx, 41h ; 'A'
0x180020249  mov     r8d, ebx
0x18002024c  lea     rcx, [rsp+170h+var_120]
0x180020251  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180020256  mov     [rsp+170h+var_F8], 2
0x18002025e  mov     rax, [rbp+78h]
0x180020262  mov     rcx, [rsp+170h+var_120]; void *
0x180020267  test    rcx, rcx
0x18002026a  jz      loc_180020477
0x180020270  xor     edx, edx; Val
0x180020272  lea     r8d, [rbx+41h]; Size
0x180020276  call    memset_0
0x18002027b  xorps   xmm0, xmm0
0x18002027e  movups  xmmword ptr [rbp+70h+UniDest.Length], xmm0
0x180020282  mov     rax, [rsp+170h+var_120]
0x180020287  mov     [rbp+70h+UniDest.Buffer], rax
0x18002028b  mov     [rbp+70h+UniDest.MaximumLength], bx
0x18002028f  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x180020293  mov     rdx, rdi; SourceString
0x180020296  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x18002029a  call    cs:__imp_RtlInitUnicodeString
0x1800202a1  nop     dword ptr [rax+rax+00h]
0x1800202a6  xor     r8d, r8d; AllocateDestinationString
0x1800202a9  lea     rdx, [rbp+70h+DestinationString]; UniSource
0x1800202ad  lea     rcx, [rbp+70h+UniDest]; UniDest
0x1800202b1  call    cs:__imp_RtlDowncaseUnicodeString
0x1800202b8  nop     dword ptr [rax+rax+00h]
0x1800202bd  test    eax, eax
0x1800202bf  jns     short loc_1800202F1
0x1800202c1  mov     rcx, [rbp+78h]; this
0x1800202c5  mov     [rsp+170h+var_148], rdi; char *
0x1800202ca  lea     rdx, aNameLs; "Name %ls"
0x1800202d1  mov     [rsp+170h+var_150], rdx; int
0x1800202d6  mov     r9d, eax; char *
0x1800202d9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800202e0  mov     edx, 163h; void *
0x1800202e5  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800202ea  mov     ebx, eax
0x1800202ec  jmp     loc_180020388
0x1800202f1  mov     rcx, [rsp+170h+Sid]; pSid
0x1800202f6  mov     [rsp+170h+var_108], rsi
0x1800202fb  test    rcx, rcx
0x1800202fe  jnz     short loc_18002033C
0x180020300  lea     rdx, [rsp+170h+var_108]
0x180020305  mov     rcx, [rbp+70h+UniDest.Buffer]
0x180020309  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180020310  nop     dword ptr [rax+rax+00h]
0x180020315  mov     ebx, eax
0x180020317  test    eax, eax
0x180020319  jns     loc_1800203C3
0x18002031f  mov     rdx, [rsp+170h+var_120]
0x180020324  mov     [rsp+170h+var_148], rdx
0x180020329  lea     rdx, aNameLs; "Name %ls"
0x180020330  mov     [rsp+170h+var_150], rdx
0x180020335  mov     edx, 16Fh
0x18002033a  jmp     short loc_18002036B
0x18002033c  lea     r8, [rsp+170h+var_108]; Sid
0x180020341  mov     rdx, [rbp+70h+UniDest.Buffer]; char *
0x180020345  call    ?DeriveChildAppContainerSid@AppContainerRegistrationHelper@@SAJPEAXPEBGPEAPEAX@Z; AppContainerRegistrationHelper::DeriveChildAppContainerSid(void *,ushort const *,void * *)
0x18002034a  mov     ebx, eax
0x18002034c  test    eax, eax
0x18002034e  jns     short loc_1800203C3
0x180020350  mov     rdx, [rsp+170h+var_120]
0x180020355  mov     [rsp+170h+var_148], rdx; char *
0x18002035a  lea     rdx, aNameLs; "Name %ls"
0x180020361  mov     [rsp+170h+var_150], rdx; int
0x180020366  mov     edx, 177h; void *
0x18002036b  mov     r9d, eax; char *
0x18002036e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020375  mov     rcx, [rbp+78h]; this
0x180020379  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002037e  lea     rcx, [rsp+170h+var_108]
0x180020383  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020388  lea     rcx, [rsp+170h+var_120]
0x18002038d  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180020392  nop
0x180020393  lea     rcx, [rsp+170h+StringSid]
0x180020398  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18002039d  nop
0x18002039e  lea     rcx, [rsp+170h+var_118]
0x1800203a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteUserSid@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteUserSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800203a8  nop
0x1800203a9  lea     rcx, [rsp+170h+Sid]
0x1800203ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800203b3  nop
0x1800203b4  lea     rcx, [rsp+170h+token]
0x1800203b9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800203be  jmp     loc_18001FF94
0x1800203c3  test    r13, r13
0x1800203c6  jz      short loc_1800203D6
0x1800203c8  mov     rax, [rsp+170h+Sid]
0x1800203cd  mov     [rsp+170h+Sid], rsi
0x1800203d2  mov     [r13+0], rax
0x1800203d6  test    r12, r12
0x1800203d9  jz      short loc_1800203E9
0x1800203db  mov     rax, [rsp+170h+var_120]
0x1800203e0  mov     [rsp+170h+var_120], rsi
0x1800203e5  mov     [r12], rax
0x1800203e9  test    r15, r15
  ... truncated ...
```
