# AppContainerRegistrationHelper::EnsureExistingState(void *,ushort const *,ushort const *,ushort const *,void * const,APP_CONTAINER_PROFILE_TYPE,_GUID const *)

- ea: `0x180009a34`
- end: `0x18000a185`
- name: `?EnsureExistingState@AppContainerRegistrationHelper@@CAJPEAXPEBG11QEAXW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z`
- size: `1873`
- prototype: `static int __high(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void *const, enum APP_CONTAINER_PROFILE_TYPE, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d980`

## callees

- `0x1800040c0`
- `0x180004250`
- `0x1800044e0`
- `0x1800045bc`
- `0x180009a34`
- `0x18000a18c`
- `0x18000a2f8`
- `0x18000a3e4`
- `0x1800162d0`
- `0x180016644`
- `0x180022830`

## import_xrefs

- `KERNELBASE!AppContainerFreeMemory` at `0x180009fe1`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000a060`
- `KERNELBASE!AppContainerFreeMemory` at `0x180009fe1`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000a060`
- `KERNELBASE!AppContainerLookupDisplayNameMrtReference` at `0x180009ffc`
- `KERNELBASE!AppContainerLookupDisplayNameMrtReference` at `0x180009ffc`
- `KERNELBASE!AppContainerLookupMoniker` at `0x180009f91`
- `KERNELBASE!AppContainerLookupMoniker` at `0x180009f91`

## string_xrefs

- `0x180009ad3`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180009b0e`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180009f2e`: `Name %ls Sid %ls`
- `0x180009f75`: `Name %ls Sid %ls`
- `0x180009ac7`: `Name %ls Sid %ls display %ls type %d`
- `0x180009c90`: `Name %ls Sid %ls path %ls dir %ls`
- `0x180009d77`: `Name %ls Sid %ls path %ls dir %ls`
- `0x180009ded`: `Name %ls Sid %ls path %ls dir %ls`
- `0x180009e4b`: `Name %ls Sid %ls path %ls dir %ls`
- `0x180009eaf`: `Name %ls Sid %ls path %ls dir %ls`
- `0x180009d54`: `INetCache`
- `0x180009d6b`: `INetCache`
- `0x180009b64`: `Name %ls Sid %ls path %ls`
- `0x180009cff`: `Name %ls Sid %ls path %ls`
- `0x18000a0e0`: `Name %ls disp %ls Sid %ls`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::EnsureExistingState(
        void *a1,
        const char *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        void *a5,
        unsigned int a6,
        struct _GUID *a7)
{
  unsigned int v10; // ebx
  unsigned int IsFileOrFolderPresent; // eax
  int v13; // r15d
  int v14; // eax
  int v15; // ebx
  unsigned __int16 *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // rcx
  __int64 v22; // rdx
  unsigned __int16 *v23; // rcx
  unsigned int v24; // eax
  int IsFolderPresent; // r15d
  BOOL v26; // r15d
  int IsRegistryStoragePresent; // eax
  unsigned int v28; // r12d
  unsigned int v29; // eax
  unsigned int v30; // eax
  const struct _EVENT_DESCRIPTOR *v31; // rcx
  __int64 v32; // rbx
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+54h] [rbp-ACh]
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID *v38; // [rsp+60h] [rbp-A0h]
  void *v39; // [rsp+68h] [rbp-98h]
  void *v40; // [rsp+70h] [rbp-90h]
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h]
  unsigned __int16 v44[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v39 = a1;
  v40 = a5;
  v35 = 0;
  v37 = 0;
  v41 = 0;
  v42 = 0;
  v43 = a3;
  v38 = a7;
  v10 = AppContainerRegistrationHelper::DeriveTopLevelFolderPath(a1, a2, v44, (__int64)a4, a6);
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x60A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v10,
      (int)"Name %ls Sid %ls display %ls type %d",
      a2,
      a4,
      a3,
      a6);
    return v10;
  }
  if ( a6 - 1 <= 2 )
  {
    v36 = 0;
    v13 = 0;
    if ( a6 == 2 )
      goto LABEL_24;
  }
  else
  {
    IsFileOrFolderPresent = AppContainerRegistrationHelper::IsFileOrFolderPresent((char *)v44, a7, &v35);
    v10 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x40B,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)IsFileOrFolderPresent,
            (__int64)"Root %ls",
            (const char *)v44);
    if ( (v10 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x612,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v10,
        (int)"Name %ls Sid %ls path %ls",
        a2,
        a4,
        v44);
      return v10;
    }
    if ( !v35 )
    {
      v14 = 0;
      v15 = 1;
LABEL_49:
      v26 = v14 != 0;
      goto LABEL_51;
    }
    v13 = 1;
    v36 = 1;
  }
  if ( !v39 )
  {
    v16 = v44;
    v17 = 260;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v17;
    }
    while ( v17 );
    v10 = v17 == 0 ? 0x80070057 : 0;
    v18 = (260 - v17) & -(__int64)(v17 != 0);
    if ( !v17 )
      goto LABEL_23;
    v19 = 2147483646;
    v20 = &v44[v18];
    v21 = L"\\AC";
    v22 = 260 - v18;
    if ( 260 != v18 )
    {
      do
      {
        if ( !v19 )
          break;
        if ( !*v21 )
          break;
        *v20++ = *v21++;
        --v19;
        --v22;
      }
      while ( v22 );
    }
    v23 = v20 - 1;
    v10 = v22 == 0 ? 0x8007007A : 0;
    if ( v22 )
      v23 = v20;
    *v23 = 0;
    if ( !v22 )
    {
LABEL_23:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x62E,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v10,
        (int)"Name %ls Sid %ls path %ls dir %ls",
        a2,
        a4,
        v44,
        L"\\AC");
      return v10;
    }
  }
LABEL_24:
  v24 = AppContainerRegistrationHelper::IsFileOrFolderPresent((char *)v44, a7, &v35);
  v10 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x40B,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v24,
          (__int64)"Root %ls",
          (const char *)v44);
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x633,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v10,
      (int)"Name %ls Sid %ls path %ls",
      a2,
      a4,
      v44);
    return v10;
  }
  if ( v35 )
  {
    v15 = 0;
    v36 = 1;
  }
  else
  {
    v15 = 1;
    if ( !v13 )
      goto LABEL_46;
  }
  IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v44, L"INetCache", a7, &v35);
  if ( IsFolderPresent < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x644,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)IsFolderPresent,
      (int)"Name %ls Sid %ls path %ls dir %ls",
      a2,
      a4,
      v44,
      L"INetCache");
    return (unsigned int)IsFolderPresent;
  }
  if ( !v35 )
    v15 = 1;
  IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v44, L"INetHistory", a7, &v35);
  if ( IsFolderPresent < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x64D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)IsFolderPresent,
      (int)"Name %ls Sid %ls path %ls dir %ls",
      a2,
      a4,
      v44,
      L"INetHistory");
    return (unsigned int)IsFolderPresent;
  }
  if ( !v35 )
    v15 = 1;
  IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v44, L"INetCookies", a7, &v35);
  if ( IsFolderPresent < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x656,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)IsFolderPresent,
      (int)"Name %ls Sid %ls path %ls dir %ls",
      a2,
      a4,
      v44,
      L"INetCookies");
    return (unsigned int)IsFolderPresent;
  }
  if ( !v35 )
    v15 = 1;
  IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v44, L"Temp", a7, &v35);
  if ( IsFolderPresent < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x65F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)IsFolderPresent,
      (int)"Name %ls Sid %ls path %ls dir %ls",
      a2,
      a4,
      v44,
      L"Temp");
    return (unsigned int)IsFolderPresent;
  }
  if ( !v35 )
    v15 = 1;
LABEL_46:
  if ( a6 != 1 && a6 != 3 )
  {
    v14 = v36;
    goto LABEL_49;
  }
  v26 = 0;
LABEL_51:
  IsRegistryStoragePresent = AppContainerRegistrationHelper::IsRegistryStoragePresent(
                               v39,
                               (const unsigned __int16 *)a2,
                               a4,
                               a7,
                               &v37);
  v28 = IsRegistryStoragePresent;
  if ( IsRegistryStoragePresent < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x67C,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)IsRegistryStoragePresent,
      (int)"Name %ls Sid %ls",
      a2,
      a4);
    return v28;
  }
  if ( v37 )
    v26 = 1;
  else
    v15 = 1;
  if ( ((a6 - 1) & 0xFFFFFFFD) != 0 )
  {
    v29 = AppContainerLookupMoniker(v40, &v41);
    v28 = v29;
    if ( v29 == -2147024894 )
    {
      v15 = 1;
    }
    else
    {
      if ( (int)wil::details::in1diag3::Log_IfFailedMsg(
                  retaddr,
                  (void *)0x68F,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                  (const char *)v29,
                  (__int64)"Name %ls Sid %ls",
                  a2,
                  a4) < 0 )
      {
        v31 = &AppModelAppContainerGetNameFailure;
        goto LABEL_71;
      }
      AppContainerFreeMemory(v41);
      v26 = 1;
    }
    v30 = AppContainerLookupDisplayNameMrtReference(v40, &v42);
    v28 = v30;
    if ( v30 == -2147024894 )
    {
      v15 = 1;
      goto LABEL_64;
    }
    if ( (int)wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x69F,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                (const char *)v30,
                (__int64)"Name %ls Sid %ls",
                a2,
                a4) >= 0 )
    {
      AppContainerFreeMemory(v42);
      goto LABEL_65;
    }
    v31 = (const struct _EVENT_DESCRIPTOR *)"\"";
LABEL_71:
    AppContainerRegistrationHelper::LogFailure(v31, v28, v38);
    return v28;
  }
LABEL_64:
  if ( !v26 )
  {
    v34 = AppContainerRegistrationHelper::DeleteStorageLocations(v39, (const unsigned __int16 *)a2, a4, a6, v38);
    if ( v34 + 2147024894 > 1 )
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x6CE,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v34,
        (__int64)"Name %ls Sid %ls",
        a2,
        a4);
    return 0;
  }
LABEL_65:
  if ( !v15 )
    return 2147942583LL;
  v32 = v43;
  v33 = AppContainerRegistrationHelper::DeleteProfileW((__int64)v39, a2, v43, (__int64)a4, v40, a6, v38);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x6BE,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)v33,
    (__int64)"Name %ls disp %ls Sid %ls",
    a2,
    v32,
    a4);
  return 0;
}

```

## disassembly

```asm
0x180009a34  push    rbp
0x180009a36  push    rbx
0x180009a37  push    rsi
0x180009a38  push    rdi
0x180009a39  push    r12
0x180009a3b  push    r13
0x180009a3d  push    r14
0x180009a3f  push    r15
0x180009a41  lea     rbp, [rsp-1B8h]
0x180009a49  sub     rsp, 2B8h
0x180009a50  mov     rax, cs:__security_cookie
0x180009a57  xor     rax, rsp
0x180009a5a  mov     [rbp+1F0h+var_50], rax
0x180009a61  mov     r12, [rbp+1F0h+arg_30]
0x180009a68  mov     rax, rcx
0x180009a6b  mov     r13d, [rbp+1F0h+arg_28]
0x180009a72  mov     rsi, r8
0x180009a75  mov     [rsp+2F0h+var_288], rcx
0x180009a7a  mov     r14, r9
0x180009a7d  mov     rcx, [rbp+1F0h+arg_20]
0x180009a84  mov     rdi, rdx
0x180009a87  mov     [rsp+2F0h+var_280], rcx
0x180009a8c  xor     ecx, ecx
0x180009a8e  mov     [rsp+2F0h+var_2A0], ecx
0x180009a92  mov     [rsp+2F0h+var_298], ecx
0x180009a96  mov     [rsp+2F0h+var_278], rcx
0x180009a9b  mov     [rbp+1F0h+var_270], rcx
0x180009a9f  mov     rcx, rax
0x180009aa2  mov     [rbp+1F0h+var_268], r8
0x180009aa6  lea     r8, [rbp+1F0h+var_260]
0x180009aaa  mov     [rsp+2F0h+var_290], r12
0x180009aaf  mov     dword ptr [rsp+2F0h+var_2D0], r13d
0x180009ab4  call    ?DeriveTopLevelFolderPath@AppContainerRegistrationHelper@@CAJPEAXPEBGPEAG_KW4APP_CONTAINER_PROFILE_TYPE@@@Z; AppContainerRegistrationHelper::DeriveTopLevelFolderPath(void *,ushort const *,ushort *,unsigned __int64,APP_CONTAINER_PROFILE_TYPE)
0x180009ab9  xor     r10d, r10d
0x180009abc  mov     ebx, eax
0x180009abe  test    eax, eax
0x180009ac0  jns     short loc_180009B04
0x180009ac2  mov     dword ptr [rsp+2F0h+var_2B0], r13d
0x180009ac7  lea     rax, aNameLsSidLsDis; "Name %ls Sid %ls display %ls type %d"
0x180009ace  mov     [rsp+2F0h+var_2B8], rsi
0x180009ad3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009ada  mov     [rsp+2F0h+var_2C0], r14
0x180009adf  mov     edx, 60Ah; void *
0x180009ae4  mov     [rsp+2F0h+var_2C8], rdi; char *
0x180009ae9  mov     [rsp+2F0h+var_2D0], rax; int
0x180009aee  mov     rcx, [rbp+1F8h]; this
0x180009af5  mov     r9d, ebx; char *
0x180009af8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009afd  mov     eax, ebx
0x180009aff  jmp     loc_18000A161
0x180009b04  lea     eax, [r13-1]
0x180009b08  mov     r11d, 1
0x180009b0e  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009b15  lea     rbx, aRootLs; "Root %ls"
0x180009b1c  cmp     eax, 2
0x180009b1f  jbe     loc_180009BC5
0x180009b25  lea     r8, [rsp+2F0h+var_2A0]; int *
0x180009b2a  mov     rdx, r12; struct _GUID *
0x180009b2d  lea     rcx, [rbp+1F0h+var_260]; char *
0x180009b31  call    ?IsFileOrFolderPresent@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFileOrFolderPresent(ushort const *,_GUID const *,int *)
0x180009b36  mov     rcx, [rbp+1F8h]; this
0x180009b3d  lea     rdx, [rbp+1F0h+var_260]
0x180009b41  mov     [rsp+2F0h+var_2C8], rdx; char *
0x180009b46  mov     r9d, eax; char *
0x180009b49  mov     edx, 40Bh; void *
0x180009b4e  mov     [rsp+2F0h+var_2D0], rbx; __int64
0x180009b53  mov     r8, rsi; unsigned int
0x180009b56  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180009b5b  xor     r10d, r10d
0x180009b5e  mov     ebx, eax
0x180009b60  test    eax, eax
0x180009b62  jns     short loc_180009B9F
0x180009b64  lea     rdx, aNameLsSidLsPat_0; "Name %ls Sid %ls path %ls"
0x180009b6b  lea     rax, [rbp+1F0h+var_260]
0x180009b6f  mov     [rsp+2F0h+var_2B8], rax
0x180009b74  mov     [rsp+2F0h+var_2C0], r14
0x180009b79  mov     [rsp+2F0h+var_2C8], rdi; char *
0x180009b7e  mov     [rsp+2F0h+var_2D0], rdx; int
0x180009b83  mov     edx, 612h; void *
0x180009b88  mov     rcx, [rbp+1F8h]; this
0x180009b8f  mov     r8, rsi; unsigned int
0x180009b92  mov     r9d, ebx; char *
0x180009b95  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009b9a  jmp     loc_180009AFD
0x180009b9f  cmp     [rsp+2F0h+var_2A0], r10d
0x180009ba4  jz      short loc_180009BB6
0x180009ba6  mov     r11d, 1
0x180009bac  mov     r15d, r11d
0x180009baf  mov     [rsp+2F0h+var_29C], r11d
0x180009bb4  jmp     short loc_180009BD7
0x180009bb6  mov     ecx, 1
0x180009bbb  mov     eax, r10d
0x180009bbe  mov     ebx, ecx
0x180009bc0  jmp     loc_180009EF4
0x180009bc5  mov     [rsp+2F0h+var_29C], r10d
0x180009bca  mov     r15d, r10d
0x180009bcd  cmp     r13d, 2
0x180009bd1  jz      loc_180009CB9
0x180009bd7  cmp     [rsp+2F0h+var_288], r10
0x180009bdc  jnz     loc_180009CB9
0x180009be2  mov     edx, 104h
0x180009be7  lea     rax, [rbp+1F0h+var_260]
0x180009beb  mov     r8d, edx
0x180009bee  cmp     [rax], r10w
0x180009bf2  jz      short loc_180009BFD
0x180009bf4  add     rax, 2
0x180009bf8  sub     r8, r11
0x180009bfb  jnz     short loc_180009BEE
0x180009bfd  mov     rax, r8
0x180009c00  mov     rcx, rdx
0x180009c03  neg     rax
0x180009c06  mov     rax, r8
0x180009c09  sbb     ebx, ebx
0x180009c0b  sub     rcx, r8
0x180009c0e  not     ebx
0x180009c10  and     ebx, 80070057h
0x180009c16  neg     rax
0x180009c19  sbb     r9, r9
0x180009c1c  and     r9, rcx
0x180009c1f  test    r8, r8
0x180009c22  jz      short loc_180009C81
0x180009c24  lea     r8, [rbp+1F0h+var_260]
0x180009c28  mov     eax, 7FFFFFFEh
0x180009c2d  lea     r8, [r8+r9*2]
0x180009c31  lea     rcx, aAc; "\\AC"
0x180009c38  sub     rdx, r9
0x180009c3b  jz      short loc_180009C60
0x180009c3d  test    rax, rax
0x180009c40  jz      short loc_180009C60
0x180009c42  movzx   r9d, word ptr [rcx]
0x180009c46  test    r9w, r9w
0x180009c4a  jz      short loc_180009C60
0x180009c4c  mov     [r8], r9w
0x180009c50  add     rcx, 2
0x180009c54  add     r8, 2
0x180009c58  sub     rax, r11
0x180009c5b  sub     rdx, r11
0x180009c5e  jnz     short loc_180009C3D
0x180009c60  mov     rax, rdx
0x180009c63  lea     rcx, [r8-2]
0x180009c67  neg     rax
0x180009c6a  sbb     ebx, ebx
0x180009c6c  not     ebx
0x180009c6e  and     ebx, 8007007Ah
0x180009c74  test    rdx, rdx
0x180009c77  cmovnz  rcx, r8
0x180009c7b  mov     [rcx], r10w
0x180009c7f  jnz     short loc_180009CB9
0x180009c81  lea     rax, aAc; "\\AC"
0x180009c88  mov     r8, rsi
0x180009c8b  mov     [rsp+2F0h+var_2B0], rax
0x180009c90  lea     rdx, aNameLsSidLsPat; "Name %ls Sid %ls path %ls dir %ls"
0x180009c97  lea     rax, [rbp+1F0h+var_260]
0x180009c9b  mov     [rsp+2F0h+var_2B8], rax
0x180009ca0  mov     [rsp+2F0h+var_2C0], r14
0x180009ca5  mov     [rsp+2F0h+var_2C8], rdi
0x180009caa  mov     [rsp+2F0h+var_2D0], rdx
0x180009caf  mov     edx, 62Eh
0x180009cb4  jmp     loc_180009AEE
0x180009cb9  lea     r8, [rsp+2F0h+var_2A0]; int *
0x180009cbe  mov     rdx, r12; struct _GUID *
0x180009cc1  lea     rcx, [rbp+1F0h+var_260]; char *
0x180009cc5  call    ?IsFileOrFolderPresent@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFileOrFolderPresent(ushort const *,_GUID const *,int *)
0x180009cca  mov     rcx, [rbp+1F8h]; this
0x180009cd1  lea     rdx, aRootLs; "Root %ls"
0x180009cd8  lea     r8, [rbp+1F0h+var_260]
0x180009cdc  mov     r9d, eax; char *
0x180009cdf  mov     [rsp+2F0h+var_2C8], r8; char *
0x180009ce4  mov     r8, rsi; unsigned int
0x180009ce7  mov     [rsp+2F0h+var_2D0], rdx; __int64
0x180009cec  mov     edx, 40Bh; void *
0x180009cf1  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180009cf6  xor     r10d, r10d
0x180009cf9  mov     ebx, eax
0x180009cfb  test    eax, eax
0x180009cfd  jns     short loc_180009D28
0x180009cff  lea     rdx, aNameLsSidLsPat_0; "Name %ls Sid %ls path %ls"
0x180009d06  lea     rax, [rbp+1F0h+var_260]
0x180009d0a  mov     [rsp+2F0h+var_2B8], rax
0x180009d0f  mov     [rsp+2F0h+var_2C0], r14
0x180009d14  mov     [rsp+2F0h+var_2C8], rdi
0x180009d19  mov     [rsp+2F0h+var_2D0], rdx
0x180009d1e  mov     edx, 633h
0x180009d23  jmp     loc_180009B88
0x180009d28  cmp     [rsp+2F0h+var_2A0], r10d
0x180009d2d  jz      short loc_180009D3C
0x180009d2f  mov     ebx, r10d
0x180009d32  mov     [rsp+2F0h+var_29C], 1
0x180009d3a  jmp     short loc_180009D4C
0x180009d3c  mov     ecx, 1
0x180009d41  mov     ebx, ecx
0x180009d43  test    r15d, r15d
0x180009d46  jz      loc_180009EE5
0x180009d4c  lea     r9, [rsp+2F0h+var_2A0]; int *
0x180009d51  mov     r8, r12; struct _GUID *
0x180009d54  lea     rdx, aInetcache; "INetCache"
0x180009d5b  lea     rcx, [rbp+1F0h+var_260]; char *
0x180009d5f  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180009d64  mov     r15d, eax
0x180009d67  test    eax, eax
0x180009d69  jns     short loc_180009DB5
0x180009d6b  lea     rax, aInetcache; "INetCache"
0x180009d72  mov     [rsp+2F0h+var_2B0], rax
0x180009d77  lea     rdx, aNameLsSidLsPat; "Name %ls Sid %ls path %ls dir %ls"
0x180009d7e  lea     rax, [rbp+1F0h+var_260]
0x180009d82  mov     [rsp+2F0h+var_2B8], rax
0x180009d87  mov     [rsp+2F0h+var_2C0], r14
0x180009d8c  mov     [rsp+2F0h+var_2C8], rdi; char *
0x180009d91  mov     [rsp+2F0h+var_2D0], rdx; int
0x180009d96  mov     edx, 644h; void *
0x180009d9b  mov     rcx, [rbp+1F8h]; this
0x180009da2  mov     r8, rsi; unsigned int
0x180009da5  mov     r9d, r15d; char *
0x180009da8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009dad  mov     eax, r15d
0x180009db0  jmp     loc_18000A161
0x180009db5  cmp     [rsp+2F0h+var_2A0], 0
0x180009dba  lea     r9, [rsp+2F0h+var_2A0]; int *
0x180009dbf  mov     eax, 1
0x180009dc4  lea     rdx, aInethistory; "INetHistory"
0x180009dcb  mov     r8, r12; struct _GUID *
0x180009dce  lea     rcx, [rbp+1F0h+var_260]; char *
0x180009dd2  cmovz   ebx, eax
0x180009dd5  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180009dda  mov     r15d, eax
0x180009ddd  test    eax, eax
0x180009ddf  jns     short loc_180009E13
0x180009de1  lea     rax, aInethistory; "INetHistory"
0x180009de8  mov     [rsp+2F0h+var_2B0], rax
0x180009ded  lea     rdx, aNameLsSidLsPat; "Name %ls Sid %ls path %ls dir %ls"
0x180009df4  lea     rax, [rbp+1F0h+var_260]
0x180009df8  mov     [rsp+2F0h+var_2B8], rax
0x180009dfd  mov     [rsp+2F0h+var_2C0], r14
0x180009e02  mov     [rsp+2F0h+var_2C8], rdi
0x180009e07  mov     [rsp+2F0h+var_2D0], rdx
0x180009e0c  mov     edx, 64Dh
0x180009e11  jmp     short loc_180009D9B
0x180009e13  cmp     [rsp+2F0h+var_2A0], 0
0x180009e18  lea     r9, [rsp+2F0h+var_2A0]; int *
0x180009e1d  mov     eax, 1
0x180009e22  lea     rdx, aInetcookies; "INetCookies"
0x180009e29  mov     r8, r12; struct _GUID *
0x180009e2c  lea     rcx, [rbp+1F0h+var_260]; char *
0x180009e30  cmovz   ebx, eax
0x180009e33  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180009e38  mov     r15d, eax
0x180009e3b  test    eax, eax
0x180009e3d  jns     short loc_180009E74
0x180009e3f  lea     rax, aInetcookies; "INetCookies"
0x180009e46  mov     [rsp+2F0h+var_2B0], rax
0x180009e4b  lea     rdx, aNameLsSidLsPat; "Name %ls Sid %ls path %ls dir %ls"
0x180009e52  lea     rax, [rbp+1F0h+var_260]
0x180009e56  mov     [rsp+2F0h+var_2B8], rax
0x180009e5b  mov     [rsp+2F0h+var_2C0], r14
0x180009e60  mov     [rsp+2F0h+var_2C8], rdi
0x180009e65  mov     [rsp+2F0h+var_2D0], rdx
0x180009e6a  mov     edx, 656h
0x180009e6f  jmp     loc_180009D9B
0x180009e74  cmp     [rsp+2F0h+var_2A0], 0
0x180009e79  lea     r9, [rsp+2F0h+var_2A0]; int *
0x180009e7e  mov     eax, 1
0x180009e83  lea     rdx, aTemp; "Temp"
0x180009e8a  mov     r8, r12; struct _GUID *
0x180009e8d  lea     rcx, [rbp+1F0h+var_260]; char *
0x180009e91  cmovz   ebx, eax
0x180009e94  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180009e99  xor     r10d, r10d
0x180009e9c  mov     r15d, eax
0x180009e9f  test    eax, eax
0x180009ea1  jns     short loc_180009ED8
0x180009ea3  lea     rax, aTemp; "Temp"
0x180009eaa  mov     [rsp+2F0h+var_2B0], rax
0x180009eaf  lea     rdx, aNameLsSidLsPat; "Name %ls Sid %ls path %ls dir %ls"
0x180009eb6  lea     rax, [rbp+1F0h+var_260]
0x180009eba  mov     [rsp+2F0h+var_2B8], rax
0x180009ebf  mov     [rsp+2F0h+var_2C0], r14
0x180009ec4  mov     [rsp+2F0h+var_2C8], rdi
0x180009ec9  mov     [rsp+2F0h+var_2D0], rdx
0x180009ece  mov     edx, 65Fh
0x180009ed3  jmp     loc_180009D9B
0x180009ed8  cmp     [rsp+2F0h+var_2A0], r10d
0x180009edd  mov     ecx, 1
0x180009ee2  cmovz   ebx, ecx
0x180009ee5  cmp     r13d, ecx
0x180009ee8  jz      short loc_180009F00
0x180009eea  cmp     r13d, 3
0x180009eee  jz      short loc_180009F00
0x180009ef0  mov     eax, [rsp+2F0h+var_29C]
0x180009ef4  mov     r15d, r10d
0x180009ef7  test    eax, eax
0x180009ef9  jz      short loc_180009F03
0x180009efb  mov     r15d, ecx
0x180009efe  jmp     short loc_180009F03
0x180009f00  mov     r15d, r10d
0x180009f03  mov     rcx, [rsp+2F0h+var_288]; void *
0x180009f08  lea     rax, [rsp+2F0h+var_298]
0x180009f0d  mov     r9, r12; struct _GUID *
0x180009f10  mov     [rsp+2F0h+var_2D0], rax; int *
0x180009f15  mov     r8, r14; unsigned __int16 *
0x180009f18  mov     rdx, rdi; unsigned __int16 *
  ... truncated ...
```
