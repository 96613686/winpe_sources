# LpacRegHelper::CreateLpacProfile(ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,unsigned __int64 const *,ulong,void * *)

- ea: `0x18001f390`
- end: `0x18001f5dd`
- name: `?CreateLpacProfile@LpacRegHelper@@SAJPEBG00PEAU_SID_AND_ATTRIBUTES@@KPEB_KKPEAPEAX@Z`
- size: `589`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, struct _SID_AND_ATTRIBUTES *@<r9>, unsigned int, const unsigned __int64 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001dcb0`

## callees

- `0x1800044e0`
- `0x180004594`
- `0x18000aacc`
- `0x18000c7d4`
- `0x18000c8d8`
- `0x18000c938`
- `0x18000f884`
- `0x18001f390`
- `0x18001f5e4`
- `0x18001fa9c`
- `0x18001fed0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18001f4a0`
- `ntdll!RtlFreeSid` at `0x18001f4a0`
- `USERENV!CreateAppContainerProfile` at `0x18001f41d`
- `USERENV!CreateAppContainerProfile` at `0x18001f41d`

## string_xrefs

- `0x18001f438`: `Failed to create AppContainer profile for %ls`
- `0x18001f3bc`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f447`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f4ef`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f557`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f546`: `Failed to create AppContainer capabilities registry for %ls`
- `0x18001f588`: `Failed to install AppContainer mitigations registry for %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LpacRegHelper::CreateLpacProfile(
        char *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SID_AND_ATTRIBUTES *a4,
        unsigned int a5,
        const unsigned __int64 *a6,
        unsigned int a7,
        void **a8)
{
  __int64 v10; // rdx
  int AppContainerProfile; // ebx
  unsigned int v12; // esi
  void **v13; // r14
  PSID v14; // rbx
  int v15; // eax
  void *v16; // rcx
  void *v17; // rcx
  const char *v18; // rax
  __int64 v19; // rdx
  void *v20; // rax
  int v22; // [rsp+20h] [rbp-38h]
  int v23; // [rsp+20h] [rbp-38h]
  unsigned int v24; // [rsp+20h] [rbp-38h]
  unsigned __int16 *v25; // [rsp+30h] [rbp-28h] BYREF
  PSID Sid; // [rsp+38h] [rbp-20h] BYREF
  void *v27; // [rsp+40h] [rbp-18h] BYREF
  _BYTE v28[16]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  unsigned __int16 *v30; // [rsp+90h] [rbp+38h] BYREF

  if ( a1 )
  {
    if ( !a2 )
    {
      v10 = 427;
      goto LABEL_3;
    }
    if ( !a3 )
    {
      v10 = 428;
      goto LABEL_3;
    }
    v12 = a5;
    if ( a5 && !a4 )
    {
      v10 = 429;
      goto LABEL_3;
    }
    v13 = a8;
    if ( !a8 )
    {
      v10 = 430;
      goto LABEL_3;
    }
    v27 = 0;
    AppContainerProfile = CreateAppContainerProfile(a1, a2);
    if ( AppContainerProfile >= 0 )
    {
      Sid = 0;
      v25 = 0;
      v30 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v30,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v25,
        0);
      v14 = Sid;
      if ( Sid )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v28);
        RtlFreeSid(v14);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
      }
      Sid = 0;
      v15 = LpacRegHelper::DeriveLpacInfo(a1, &Sid, &v25, 0, &v30, 0);
      AppContainerProfile = v15;
      if ( v15 >= 0 )
      {
        AppContainerProfile = LpacRegHelper::CreateRegistryLpacCapabilities(v16, v25, v30, a4, v12, v27);
        if ( AppContainerProfile >= 0 )
        {
          AppContainerProfile = LpacRegHelper::CreateRegistryLpacMitigations(v17, v25, v30, a6, v24);
          if ( AppContainerProfile >= 0 )
          {
            v20 = v27;
            v27 = 0;
            *v13 = v20;
            wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v30);
            wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v25);
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
            AppContainerProfile = 0;
            goto LABEL_26;
          }
          v18 = "Failed to install AppContainer mitigations registry for %ls";
          v19 = 479;
        }
        else
        {
          v18 = "Failed to create AppContainer capabilities registry for %ls";
          v19 = 468;
        }
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
          (const char *)(unsigned int)AppContainerProfile,
          (int)v18,
          a1);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C7,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
          (const char *)(unsigned int)v15,
          v23);
      }
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v30);
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v25);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1BB,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)(unsigned int)AppContainerProfile,
        (int)"Failed to create AppContainer profile for %ls",
        a1);
    }
LABEL_26:
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
    return (unsigned int)AppContainerProfile;
  }
  v10 = 426;
LABEL_3:
  AppContainerProfile = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
    (const char *)0x80070057LL,
    v22);
  return (unsigned int)AppContainerProfile;
}

```

## disassembly

```asm
0x18001f390  push    rbp
0x18001f392  push    rbx
0x18001f393  push    rsi
0x18001f394  push    rdi
0x18001f395  push    r14
0x18001f397  push    r15
0x18001f399  mov     rbp, rsp
0x18001f39c  sub     rsp, 58h
0x18001f3a0  mov     r15, r9
0x18001f3a3  mov     rdi, rcx
0x18001f3a6  test    rcx, rcx
0x18001f3a9  jnz     short loc_18001F3CD
0x18001f3ab  mov     edx, 1AAh; void *
0x18001f3b0  mov     ebx, 80070057h
0x18001f3b5  mov     rcx, [rbp+30h]; this
0x18001f3b9  mov     r9d, ebx; char *
0x18001f3bc  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f3c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f3c8  jmp     loc_18001F5CD
0x18001f3cd  test    rdx, rdx
0x18001f3d0  jnz     short loc_18001F3D9
0x18001f3d2  mov     edx, 1ABh
0x18001f3d7  jmp     short loc_18001F3B0
0x18001f3d9  test    r8, r8
0x18001f3dc  jnz     short loc_18001F3E5
0x18001f3de  mov     edx, 1ACh
0x18001f3e3  jmp     short loc_18001F3B0
0x18001f3e5  mov     esi, [rbp+arg_20]
0x18001f3e8  test    esi, esi
0x18001f3ea  jz      short loc_18001F3F8
0x18001f3ec  test    r15, r15
0x18001f3ef  jnz     short loc_18001F3F8
0x18001f3f1  mov     edx, 1ADh
0x18001f3f6  jmp     short loc_18001F3B0
0x18001f3f8  mov     r14, [rbp+arg_38]
0x18001f3fc  test    r14, r14
0x18001f3ff  jnz     short loc_18001F408
0x18001f401  mov     edx, 1AEh
0x18001f406  jmp     short loc_18001F3B0
0x18001f408  mov     [rbp+var_18], 0
0x18001f410  lea     rax, [rbp+var_18]
0x18001f414  mov     [rsp+58h+var_30], rax
0x18001f419  mov     dword ptr [rsp+58h+var_38], esi
0x18001f41d  call    cs:__imp_CreateAppContainerProfile
0x18001f424  nop     dword ptr [rax+rax+00h]
0x18001f429  mov     ebx, eax
0x18001f42b  test    eax, eax
0x18001f42d  jns     short loc_18001F45D
0x18001f42f  mov     rcx, [rbp+30h]; this
0x18001f433  mov     [rsp+58h+var_30], rdi; char *
0x18001f438  lea     rax, aFailedToCreate; "Failed to create AppContainer profile f"...
0x18001f43f  mov     [rsp+58h+var_38], rax; int
0x18001f444  mov     r9d, ebx; char *
0x18001f447  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f44e  mov     edx, 1BBh; void *
0x18001f453  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001f458  jmp     loc_18001F5C4
0x18001f45d  mov     [rbp+Sid], 0
0x18001f465  mov     [rbp+var_28], 0
0x18001f46d  mov     [rbp+arg_0], 0
0x18001f475  xor     edx, edx
0x18001f477  lea     rcx, [rbp+arg_0]
0x18001f47b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001f480  xor     edx, edx
0x18001f482  lea     rcx, [rbp+var_28]
0x18001f486  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001f48b  mov     rbx, [rbp+Sid]
0x18001f48f  test    rbx, rbx
0x18001f492  jz      short loc_18001F4B5
0x18001f494  lea     rcx, [rbp+var_10]; this
0x18001f498  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001f49d  mov     rcx, rbx; Sid
0x18001f4a0  call    cs:__imp_RtlFreeSid
0x18001f4a7  nop     dword ptr [rax+rax+00h]
0x18001f4ac  lea     rcx, [rbp+var_10]; this
0x18001f4b0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001f4b5  mov     [rbp+Sid], 0
0x18001f4bd  mov     [rsp+58h+var_30], 0; void **
0x18001f4c6  lea     rax, [rbp+arg_0]
0x18001f4ca  mov     [rsp+58h+var_38], rax; int
0x18001f4cf  xor     r9d, r9d; unsigned __int16 **
0x18001f4d2  lea     r8, [rbp+var_28]; unsigned __int16 **
0x18001f4d6  lea     rdx, [rbp+Sid]; void **
0x18001f4da  mov     rcx, rdi; char *
0x18001f4dd  call    ?DeriveLpacInfo@LpacRegHelper@@CAJPEBGPEAPEAXPEAPEAG221@Z; LpacRegHelper::DeriveLpacInfo(ushort const *,void * *,ushort * *,ushort * *,ushort * *,void * *)
0x18001f4e2  mov     ebx, eax
0x18001f4e4  test    eax, eax
0x18001f4e6  jns     short loc_18001F523
0x18001f4e8  mov     rcx, [rbp+30h]; this
0x18001f4ec  mov     r9d, eax; char *
0x18001f4ef  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f4f6  mov     edx, 1C7h; void *
0x18001f4fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f500  nop
0x18001f501  lea     rcx, [rbp+arg_0]
0x18001f505  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001f50a  nop
0x18001f50b  lea     rcx, [rbp+var_28]
0x18001f50f  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001f514  nop
0x18001f515  lea     rcx, [rbp+Sid]
0x18001f519  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f51e  jmp     loc_18001F5C4
0x18001f523  mov     rax, [rbp+var_18]
0x18001f527  mov     [rsp+58h+var_30], rax; void *
0x18001f52c  mov     dword ptr [rsp+58h+var_38], esi; unsigned int
0x18001f530  mov     r9, r15; struct _SID_AND_ATTRIBUTES *
0x18001f533  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x18001f537  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x18001f53b  call    ?CreateRegistryLpacCapabilities@LpacRegHelper@@CAJPEAXPEBG1PEAU_SID_AND_ATTRIBUTES@@K0@Z; LpacRegHelper::CreateRegistryLpacCapabilities(void *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,void *)
0x18001f540  mov     ebx, eax
0x18001f542  test    eax, eax
0x18001f544  jns     short loc_18001F571
0x18001f546  lea     rax, aFailedToCreate_0; "Failed to create AppContainer capabilit"...
0x18001f54d  mov     edx, 1D4h; void *
0x18001f552  mov     [rsp+58h+var_30], rdi; char *
0x18001f557  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f55e  mov     r9d, ebx; char *
0x18001f561  mov     [rsp+58h+var_38], rax; int
0x18001f566  mov     rcx, [rbp+30h]; this
0x18001f56a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001f56f  jmp     short loc_18001F501
0x18001f571  mov     r9, [rbp+arg_28]; unsigned __int64 *
0x18001f575  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x18001f579  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x18001f57d  call    ?CreateRegistryLpacMitigations@LpacRegHelper@@CAJPEAXPEBG1PEB_KK@Z; LpacRegHelper::CreateRegistryLpacMitigations(void *,ushort const *,ushort const *,unsigned __int64 const *,ulong)
0x18001f582  mov     ebx, eax
0x18001f584  test    eax, eax
0x18001f586  jns     short loc_18001F596
0x18001f588  lea     rax, aFailedToInstal; "Failed to install AppContainer mitigati"...
0x18001f58f  mov     edx, 1DFh
0x18001f594  jmp     short loc_18001F552
0x18001f596  mov     rax, [rbp+var_18]
0x18001f59a  mov     [rbp+var_18], 0
0x18001f5a2  mov     [r14], rax
0x18001f5a5  lea     rcx, [rbp+arg_0]
0x18001f5a9  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001f5ae  nop
0x18001f5af  lea     rcx, [rbp+var_28]
0x18001f5b3  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001f5b8  nop
0x18001f5b9  lea     rcx, [rbp+Sid]
0x18001f5bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f5c2  xor     ebx, ebx
0x18001f5c4  lea     rcx, [rbp+var_18]
0x18001f5c8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f5cd  mov     eax, ebx
0x18001f5cf  add     rsp, 58h
0x18001f5d3  pop     r15
0x18001f5d5  pop     r14
0x18001f5d7  pop     rdi
0x18001f5d8  pop     rsi
0x18001f5d9  pop     rbx
0x18001f5da  pop     rbp
0x18001f5db  retn
```
