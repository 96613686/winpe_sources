# AppContainerRegistrationHelper::DeriveTopLevelFolderPath(void *,ushort const *,ushort *,unsigned __int64,APP_CONTAINER_PROFILE_TYPE)

- ea: `0x1800045bc`
- end: `0x180004c77`
- name: `?DeriveTopLevelFolderPath@AppContainerRegistrationHelper@@CAJPEAXPEBGPEAG_KW4APP_CONTAINER_PROFILE_TYPE@@@Z`
- size: `1723`
- prototype: `__int64 __fastcall(void *, const char *, unsigned __int16 *, __int64, int)`
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004c80`
- `0x180009a34`
- `0x180014480`
- `0x180014d5c`
- `0x180015fe0`

## callees

- `0x180001854`
- `0x180001ba0`
- `0x180001ef0`
- `0x180002030`
- `0x1800044e0`
- `0x1800045bc`
- `0x180006400`
- `0x180006738`
- `0x18000aacc`
- `0x18000c7d4`
- `0x18000f614`
- `0x18000f6cc`
- `0x180018c68`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004677`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004677`
- `KERNELBASE!OpenStateExplicit` at `0x180004974`
- `KERNELBASE!OpenStateExplicit` at `0x180004974`
- `KERNELBASE!GetStateRootFolder` at `0x180004a36`
- `KERNELBASE!GetStateRootFolder` at `0x180004a36`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004b01`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004b01`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004937`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004bf9`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004937`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180004bf9`
- `profapi!__imp_GetAppContainerPathFromSidString` at `0x180004b67`
- `profapi!__imp_GetAppContainerPathFromSidString` at `0x180004b67`

## string_xrefs

- `0x18000464f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800046c5`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800048ec`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800049a1`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004a0c`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004aca`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004b24`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004b8d`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800046b2`: `Name %ls path %ls`
- `0x1800048fb`: `Name %ls path %ls prefix %ls`
- `0x180004b16`: `Name %ls Sid %ls`
- `0x180004b7f`: `Name %ls Sid %ls parent %ls`
- `0x180004c6b`: `Path %ls len %Iu`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::DeriveTopLevelFolderPath(
        void *a1,
        const char *a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  int v8; // eax
  unsigned int LastErrorMsg; // ebx
  unsigned __int16 *v10; // rcx
  __int64 v11; // rdx
  __int64 v13; // r8
  unsigned __int16 *v14; // r9
  __int64 v15; // r10
  __int64 v16; // rax
  const wchar_t *v17; // rcx
  __int64 v18; // rdx
  unsigned __int16 *v19; // rcx
  __int64 v20; // rdx
  unsigned __int16 *v21; // rax
  __int64 v22; // r8
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  unsigned __int16 *v25; // r9
  __int64 v26; // rdx
  unsigned __int16 *v27; // rcx
  __int64 v28; // rdx
  unsigned __int16 *v29; // rax
  __int64 v30; // r8
  unsigned __int16 *v31; // rax
  bool v32; // zf
  __int64 v33; // rdx
  unsigned __int16 *v34; // r8
  __int64 v35; // rdx
  unsigned __int16 *v36; // rax
  __int64 v37; // rax
  __int64 v38; // rdx
  int SidString; // eax
  HANDLE v40; // rbx
  int AppContainerPathFromSidString; // r14d
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v44[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v45[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a3 = 0;
  if ( a1 )
  {
    LODWORD(StringSid) = 2162688;
    AppModelPolicy_GetPolicy(-6, a2, &StringSid);
    if ( (_DWORD)StringSid == 2162689 )
    {
      hObject = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &hObject,
        0);
      SidString = GetSidString((void *)0xFFFFFFFFFFFFFFFALL, (unsigned __int16 **)&hObject);
      LastErrorMsg = SidString;
      if ( SidString < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x306,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)SidString,
          (int)"Name %ls",
          a2);
LABEL_66:
        wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&hObject);
        return LastErrorMsg;
      }
      StringSid = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &StringSid,
        0);
      if ( !ConvertSidToStringSidW(a1, &StringSid) )
      {
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0x30A,
                         (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                         "Name %ls Sid %ls",
                         a2,
                         hObject);
        wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
        goto LABEL_66;
      }
      v40 = hObject;
      AppContainerPathFromSidString = GetAppContainerPathFromSidString(hObject, StringSid, v45, 260);
      if ( AppContainerPathFromSidString < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x311,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)AppContainerPathFromSidString,
          (int)"Name %ls Sid %ls parent %ls",
          a2,
          v40,
          StringSid);
        wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
        LastErrorMsg = AppContainerPathFromSidString;
        goto LABEL_66;
      }
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&hObject);
    }
    else
    {
      LastErrorMsg = GetBasicProfileFolderPath(6, 0, v45, 260);
      if ( (LastErrorMsg & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x317,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)LastErrorMsg,
          (int)"Name %ls",
          a2);
        return LastErrorMsg;
      }
    }
    LastErrorMsg = StringCchCatW(v45, 0x104u, L"\\#!");
    if ( (LastErrorMsg & 0x80000000) == 0 )
    {
      LastErrorMsg = StringCchCatW(v45, 0x104u, (const unsigned __int16 *)a2);
      if ( (LastErrorMsg & 0x80000000) == 0 )
        goto LABEL_14;
      v11 = 801;
    }
    else
    {
      v11 = 798;
    }
    goto LABEL_12;
  }
  if ( (unsigned int)(a5 - 1) > 2 )
  {
    LastErrorMsg = GetBasicProfileFolderPath(5, 0, v45, 260);
    if ( (LastErrorMsg & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)LastErrorMsg,
        (int)"Name %ls",
        a2);
      return LastErrorMsg;
    }
    v35 = 260;
    v36 = v45;
    do
    {
      if ( !*v36 )
        break;
      ++v36;
      --v35;
    }
    while ( v35 );
    LastErrorMsg = v35 == 0 ? 0x80070057 : 0;
    v13 = (260 - v35) & -(__int64)(v35 != 0);
    if ( !v35 )
      goto LABEL_44;
    v14 = &v45[v13];
    v15 = 2147483646;
    v16 = 2147483646;
    v17 = L"\\AppData\\Local";
    v18 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v16 )
          break;
        if ( !*v17 )
          break;
        *v14++ = *v17++;
        --v16;
        --v18;
      }
      while ( v18 );
    }
    v19 = v14 - 1;
    LastErrorMsg = v18 == 0 ? 0x8007007A : 0;
    if ( v18 )
      v19 = v14;
    *v19 = 0;
    if ( !v18 )
    {
LABEL_44:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2ED,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)LastErrorMsg,
        (int)"Name %ls path %ls prefix %ls",
        a2,
        v45,
        L"\\AppData\\Local");
      return LastErrorMsg;
    }
    v20 = 260;
    v21 = v45;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v20;
    }
    while ( v20 );
    LastErrorMsg = v20 == 0 ? 0x80070057 : 0;
    v22 = (260 - v20) & -(__int64)(v20 != 0);
    if ( !v20 )
      goto LABEL_45;
    v23 = L"\\Packages\\";
    v24 = 2147483646;
    v25 = &v45[v22];
    v26 = 260 - v22;
    if ( v22 != 260 )
    {
      do
      {
        if ( !v24 )
          break;
        if ( !*v23 )
          break;
        *v25++ = *v23++;
        --v24;
        --v26;
      }
      while ( v26 );
    }
    v27 = v25 - 1;
    LastErrorMsg = v26 == 0 ? 0x8007007A : 0;
    if ( v26 )
      v27 = v25;
    *v27 = 0;
    if ( v26 )
    {
      v28 = 260;
      v29 = v45;
      do
      {
        if ( !*v29 )
          break;
        ++v29;
        --v28;
      }
      while ( v28 );
      LastErrorMsg = v28 == 0 ? 0x80070057 : 0;
      v30 = (260 - v28) & -(__int64)(v28 != 0);
      if ( v28 )
      {
        v31 = (unsigned __int16 *)a2;
        v33 = 260 - v30;
        v32 = v30 == 260;
        v34 = &v45[v30];
        if ( !v32 )
        {
          do
          {
            if ( !v15 )
              break;
            if ( !*v31 )
              break;
            *v34++ = *v31++;
            --v15;
            --v33;
          }
          while ( v33 );
        }
        v10 = v34 - 1;
        LastErrorMsg = v33 == 0 ? 0x8007007A : 0;
        if ( v33 )
          v10 = v34;
        *v10 = 0;
        if ( v33 )
          goto LABEL_14;
      }
      v11 = 755;
    }
    else
    {
LABEL_45:
      v11 = 752;
    }
LABEL_12:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)LastErrorMsg,
      (int)"Name %ls path %ls",
      a2,
      v45);
    return LastErrorMsg;
  }
  hObject = 0;
  v8 = AppContainerRegistrationHelper::OpenCurrentUserToken((char *)0x20008, &hObject);
  LastErrorMsg = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2DC,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v8,
      (int)"Name %ls",
      a2);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return LastErrorMsg;
  }
  v37 = OpenStateExplicit(hObject, a2);
  v44[0] = v37;
  if ( !v37 )
  {
    v38 = 735;
LABEL_53:
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)v38,
                     (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                     "Name %ls",
                     a2);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v44);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    return LastErrorMsg;
  }
  LODWORD(StringSid) = 260;
  if ( !(unsigned int)GetStateRootFolder(v37, v45, &StringSid) )
  {
    v38 = 739;
    goto LABEL_53;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v44);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
LABEL_14:
  LastErrorMsg = StringCchCopyW(a3, 0x104u, v45);
  if ( (LastErrorMsg & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x325,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)LastErrorMsg,
      (int)"Path %ls len %Iu",
      (const char *)v45,
      260);
    return LastErrorMsg;
  }
  return 0;
}

```

## disassembly

```asm
0x1800045bc  push    rbp
0x1800045be  push    rbx
0x1800045bf  push    rsi
0x1800045c0  push    rdi
0x1800045c1  push    r12
0x1800045c3  push    r14
0x1800045c5  push    r15
0x1800045c7  lea     rbp, [rsp-180h]
0x1800045cf  sub     rsp, 280h
0x1800045d6  mov     rax, cs:__security_cookie
0x1800045dd  xor     rax, rsp
0x1800045e0  mov     [rbp+1B0h+var_40], rax
0x1800045e7  xor     r12d, r12d
0x1800045ea  mov     r15, r8
0x1800045ed  mov     rsi, rdx
0x1800045f0  mov     rdi, rcx
0x1800045f3  test    r8, r8
0x1800045f6  jz      loc_1800049CD
0x1800045fc  mov     [r15], r12w
0x180004600  test    rdi, rdi
0x180004603  jnz     loc_180004A69
0x180004609  mov     eax, [rbp+1B0h+arg_20]
0x18000460f  lea     r14d, [rdi+2]
0x180004613  dec     eax
0x180004615  cmp     eax, r14d
0x180004618  ja      loc_180004925
0x18000461e  lea     rdx, [rsp+2B0h+hObject]; void **
0x180004623  mov     [rsp+2B0h+hObject], r12
0x180004628  mov     ecx, 20008h; char *
0x18000462d  call    ?OpenCurrentUserToken@AppContainerRegistrationHelper@@SAJKPEAPEAX@Z; AppContainerRegistrationHelper::OpenCurrentUserToken(ulong,void * *)
0x180004632  mov     ebx, eax
0x180004634  test    eax, eax
0x180004636  jns     loc_18000496C
0x18000463c  mov     rcx, [rbp+1B8h]; this
0x180004643  lea     rdx, aNameLs; "Name %ls"
0x18000464a  mov     [rsp+2B0h+var_288], rsi; char *
0x18000464f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004656  mov     [rsp+2B0h+var_290], rdx; int
0x18000465b  mov     r9d, eax; char *
0x18000465e  mov     edx, 2DCh; void *
0x180004663  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004668  mov     rcx, [rsp+2B0h+hObject]; hObject
0x18000466d  lea     rax, [rcx-1]
0x180004671  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004675  ja      short loc_1800046D9
0x180004677  call    cs:__imp_CloseHandle
0x18000467e  nop     dword ptr [rax+rax+00h]
0x180004683  jmp     short loc_1800046D9
0x180004685  mov     rax, rdx
0x180004688  lea     rcx, [r8-2]
0x18000468c  neg     rax
0x18000468f  sbb     ebx, ebx
0x180004691  not     ebx
0x180004693  and     ebx, r11d
0x180004696  test    rdx, rdx
0x180004699  cmovnz  rcx, r8
0x18000469d  mov     [rcx], r12w
0x1800046a1  jnz     short loc_1800046FD
0x1800046a3  mov     edx, 2F3h; void *
0x1800046a8  lea     rax, [rsp+2B0h+var_250]
0x1800046ad  mov     [rsp+2B0h+var_280], rax
0x1800046b2  lea     rax, aNameLsPathLs; "Name %ls path %ls"
0x1800046b9  mov     [rsp+2B0h+var_288], rsi; char *
0x1800046be  mov     rcx, [rbp+1B8h]; this
0x1800046c5  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800046cc  mov     r9d, ebx; char *
0x1800046cf  mov     [rsp+2B0h+var_290], rax; int
0x1800046d4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800046d9  mov     eax, ebx
0x1800046db  mov     rcx, [rbp+1B0h+var_40]
0x1800046e2  xor     rcx, rsp; StackCookie
0x1800046e5  call    __security_check_cookie
0x1800046ea  add     rsp, 280h
0x1800046f1  pop     r15
0x1800046f3  pop     r14
0x1800046f5  pop     r12
0x1800046f7  pop     rdi
0x1800046f8  pop     rsi
0x1800046f9  pop     rbx
0x1800046fa  pop     rbp
0x1800046fb  retn
0x1800046fd  lea     r8, [rsp+2B0h+var_250]; unsigned __int16 *
0x180004702  mov     rdx, rdi; unsigned __int64
0x180004705  mov     rcx, r15; unsigned __int16 *
0x180004708  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000470d  mov     ebx, eax
0x18000470f  test    eax, eax
0x180004711  js      loc_180004C57
0x180004717  xor     eax, eax
0x180004719  jmp     short loc_1800046DB
0x18000471b  mov     rax, rdx
0x18000471e  lea     r11, aAppdataLocal_0; "\\AppData\\Local"
0x180004725  neg     rax
0x180004728  mov     rcx, rdi
0x18000472b  mov     rax, rdx
0x18000472e  sbb     ebx, ebx
0x180004730  sub     rcx, rdx
0x180004733  not     ebx
0x180004735  and     ebx, 80070057h
0x18000473b  neg     rax
0x18000473e  sbb     r8, r8
0x180004741  and     r8, rcx
0x180004744  test    rdx, rdx
0x180004747  jz      loc_1800048DB
0x18000474d  mov     rdx, rdi
0x180004750  lea     r9, [rsp+2B0h+var_250]
0x180004755  lea     r9, [r9+r8*2]
0x180004759  mov     r10d, 7FFFFFFEh
0x18000475f  mov     eax, r10d
0x180004762  mov     rcx, r11
0x180004765  sub     rdx, r8
0x180004768  jz      short loc_18000478C
0x18000476a  test    rax, rax
0x18000476d  jz      short loc_18000478C
0x18000476f  movzx   r8d, word ptr [rcx]
0x180004773  test    r8w, r8w
0x180004777  jz      short loc_18000478C
0x180004779  mov     [r9], r8w
0x18000477d  add     rcx, r14
0x180004780  add     r9, r14
0x180004783  dec     rax
0x180004786  sub     rdx, 1
0x18000478a  jnz     short loc_18000476A
0x18000478c  mov     rax, rdx
0x18000478f  lea     rcx, [r9-2]
0x180004793  neg     rax
0x180004796  sbb     ebx, ebx
0x180004798  not     ebx
0x18000479a  and     ebx, 8007007Ah
0x1800047a0  test    rdx, rdx
0x1800047a3  cmovnz  rcx, r9
0x1800047a7  mov     [rcx], r12w
0x1800047ab  jz      loc_1800048DB
0x1800047b1  mov     rdx, rdi
0x1800047b4  lea     rax, [rsp+2B0h+var_250]
0x1800047b9  cmp     [rax], r12w
0x1800047bd  jz      short loc_1800047C8
0x1800047bf  add     rax, r14
0x1800047c2  sub     rdx, 1
0x1800047c6  jnz     short loc_1800047B9
0x1800047c8  mov     rax, rdx
0x1800047cb  mov     rcx, rdi
0x1800047ce  neg     rax
0x1800047d1  mov     rax, rdx
0x1800047d4  sbb     ebx, ebx
0x1800047d6  sub     rcx, rdx
0x1800047d9  not     ebx
0x1800047db  and     ebx, 80070057h
0x1800047e1  neg     rax
0x1800047e4  sbb     r8, r8
0x1800047e7  and     r8, rcx
0x1800047ea  test    rdx, rdx
0x1800047ed  jz      loc_18000491B
0x1800047f3  mov     rdx, rdi
0x1800047f6  lea     r9, [rsp+2B0h+var_250]
0x1800047fb  lea     rcx, aPackages; "\\Packages\\"
0x180004802  mov     rax, r10
0x180004805  lea     r9, [r9+r8*2]
0x180004809  sub     rdx, r8
0x18000480c  jz      short loc_180004830
0x18000480e  test    rax, rax
0x180004811  jz      short loc_180004830
0x180004813  movzx   r8d, word ptr [rcx]
0x180004817  test    r8w, r8w
0x18000481b  jz      short loc_180004830
0x18000481d  mov     [r9], r8w
0x180004821  add     rcx, r14
0x180004824  add     r9, r14
0x180004827  dec     rax
0x18000482a  sub     rdx, 1
0x18000482e  jnz     short loc_18000480E
0x180004830  mov     rax, rdx
0x180004833  lea     rcx, [r9-2]
0x180004837  neg     rax
0x18000483a  mov     r11d, 8007007Ah
0x180004840  sbb     ebx, ebx
0x180004842  not     ebx
0x180004844  and     ebx, r11d
0x180004847  test    rdx, rdx
0x18000484a  cmovnz  rcx, r9
0x18000484e  mov     [rcx], r12w
0x180004852  jz      loc_18000491B
0x180004858  mov     rdx, rdi
0x18000485b  lea     rax, [rsp+2B0h+var_250]
0x180004860  cmp     [rax], r12w
0x180004864  jz      short loc_18000486F
0x180004866  add     rax, r14
0x180004869  sub     rdx, 1
0x18000486d  jnz     short loc_180004860
0x18000486f  mov     rax, rdx
0x180004872  mov     rcx, rdi
0x180004875  neg     rax
0x180004878  mov     rax, rdx
0x18000487b  sbb     ebx, ebx
0x18000487d  sub     rcx, rdx
0x180004880  not     ebx
0x180004882  and     ebx, 80070057h
0x180004888  neg     rax
0x18000488b  sbb     r8, r8
0x18000488e  and     r8, rcx
0x180004891  test    rdx, rdx
0x180004894  jz      loc_1800046A3
0x18000489a  mov     rdx, rdi
0x18000489d  mov     rax, rsi
0x1800048a0  sub     rdx, r8
0x1800048a3  lea     r8, [rsp+r8*2+2B0h+var_250]
0x1800048a8  jz      loc_180004685
0x1800048ae  test    r10, r10
0x1800048b1  jz      loc_180004685
0x1800048b7  movzx   ecx, word ptr [rax]
0x1800048ba  test    cx, cx
0x1800048bd  jz      loc_180004685
0x1800048c3  mov     [r8], cx
0x1800048c7  add     rax, r14
0x1800048ca  add     r8, r14
0x1800048cd  dec     r10
0x1800048d0  sub     rdx, 1
0x1800048d4  jnz     short loc_1800048AE
0x1800048d6  jmp     loc_180004685
0x1800048db  mov     rcx, [rbp+1B8h]; this
0x1800048e2  lea     rax, [rsp+2B0h+var_250]
0x1800048e7  mov     [rsp+2B0h+var_278], r11
0x1800048ec  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800048f3  mov     [rsp+2B0h+var_280], rax
0x1800048f8  mov     r9d, ebx; char *
0x1800048fb  lea     rax, aNameLsPathLsPr; "Name %ls path %ls prefix %ls"
0x180004902  mov     [rsp+2B0h+var_288], rsi; char *
0x180004907  mov     edx, 2EDh; void *
0x18000490c  mov     [rsp+2B0h+var_290], rax; int
0x180004911  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004916  jmp     loc_1800046D9
0x18000491b  mov     edx, 2F0h
0x180004920  jmp     loc_1800046A8
0x180004925  xor     edx, edx
0x180004927  lea     r8, [rsp+2B0h+var_250]
0x18000492c  mov     edi, 104h
0x180004931  mov     r9d, edi
0x180004934  lea     ecx, [rdx+5]
0x180004937  call    cs:__imp_GetBasicProfileFolderPath
0x18000493e  nop     dword ptr [rax+rax+00h]
0x180004943  mov     ebx, eax
0x180004945  test    eax, eax
0x180004947  js      loc_1800049D7
0x18000494d  mov     edx, edi
0x18000494f  lea     rax, [rsp+2B0h+var_250]
0x180004954  cmp     [rax], r12w
0x180004958  jz      loc_18000471B
0x18000495e  add     rax, r14
0x180004961  sub     rdx, 1
0x180004965  jnz     short loc_180004954
0x180004967  jmp     loc_18000471B
0x18000496c  mov     rcx, [rsp+2B0h+hObject]
0x180004971  mov     rdx, rsi
0x180004974  call    cs:__imp_OpenStateExplicit
0x18000497b  nop     dword ptr [rax+rax+00h]
0x180004980  mov     [rsp+2B0h+var_260], rax
0x180004985  test    rax, rax
0x180004988  jnz     loc_180004A20
0x18000498e  mov     edx, 2DFh; void *
0x180004993  mov     rcx, [rbp+1B8h]; this
0x18000499a  lea     r9, aNameLs; "Name %ls"
0x1800049a1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800049a8  mov     [rsp+2B0h+var_290], rsi; char *
0x1800049ad  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800049b2  lea     rcx, [rsp+2B0h+var_260]
0x1800049b7  mov     ebx, eax
0x1800049b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800049be  lea     rcx, [rsp+2B0h+hObject]
0x1800049c3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800049c8  jmp     loc_1800046D9
0x1800049cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800049d2  jmp     loc_1800045FC
0x1800049d7  lea     rdx, aNameLs; "Name %ls"
0x1800049de  mov     [rsp+2B0h+var_288], rsi
0x1800049e3  mov     [rsp+2B0h+var_290], rdx
0x1800049e8  mov     edx, 2E9h
0x1800049ed  jmp     short loc_180004A05
0x1800049ef  lea     rdx, aNameLs; "Name %ls"
0x1800049f6  mov     [rsp+2B0h+var_288], rsi; char *
0x1800049fb  mov     [rsp+2B0h+var_290], rdx; int
0x180004a00  mov     edx, 317h; void *
0x180004a05  mov     rcx, [rbp+1B8h]; this
0x180004a0c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004a13  mov     r9d, ebx; char *
0x180004a16  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004a1b  jmp     loc_1800046D9
0x180004a20  mov     edi, 104h
0x180004a25  lea     r8, [rsp+2B0h+StringSid]
0x180004a2a  lea     rdx, [rsp+2B0h+var_250]
0x180004a2f  mov     dword ptr [rsp+2B0h+StringSid], edi
0x180004a33  mov     rcx, rax
0x180004a36  call    cs:__imp_GetStateRootFolder
0x180004a3d  nop     dword ptr [rax+rax+00h]
0x180004a42  test    eax, eax
0x180004a44  jnz     short loc_180004A50
0x180004a46  mov     edx, 2E3h
0x180004a4b  jmp     loc_180004993
0x180004a50  lea     rcx, [rsp+2B0h+var_260]
0x180004a55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004a5a  lea     rcx, [rsp+2B0h+hObject]
  ... truncated ...
```
