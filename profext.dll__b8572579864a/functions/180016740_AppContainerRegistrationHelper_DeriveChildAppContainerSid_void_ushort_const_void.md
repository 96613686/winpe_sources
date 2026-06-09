# AppContainerRegistrationHelper::DeriveChildAppContainerSid(void *,ushort const *,void * *)

- ea: `0x180016740`
- end: `0x180016ab6`
- name: `?DeriveChildAppContainerSid@AppContainerRegistrationHelper@@SAJPEAXPEBGPEAPEAX@Z`
- size: `886`
- prototype: `__int64 __fastcall(PSID pSid, char *, PSID *Sid)`
- caller_count: `6`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001880`
- `0x1800020d0`
- `0x180002a80`
- `0x18000ca58`
- `0x180016ac0`
- `0x18001fed0`

## callees

- `0x1800044e0`
- `0x18000aacc`
- `0x18000bd18`
- `0x18000c770`
- `0x18000c7d4`
- `0x18000c8d8`
- `0x18000c938`
- `0x18000f41c`
- `0x18000f6cc`
- `0x18000f884`
- `0x180016740`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180016884`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001689d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180016884`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18001689d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180016934`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001694c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180016963`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001697a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180016934`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001694c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180016963`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001697a`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180016848`
- `KERNELBASE!AppContainerDeriveSidFromMoniker` at `0x180016848`
- `ntdll!RtlFreeSid` at `0x180016828`
- `ntdll!RtlFreeSid` at `0x180016828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800168cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800168cf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016a06`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016a06`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800167db`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800167db`

## string_xrefs

- `0x1800167b1`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800167f6`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800168eb`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800169b9`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180016a26`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180016a84`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180016866`: `Name %ls Sid %ls`
- `0x1800169cc`: `Name %ls Sid %ls`
- `0x180016a1a`: `Name %ls Sid %ls`
- `0x180016a5d`: `Name %ls Sid %ls`
- `0x18001690c`: `Sid %ls len %d`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::DeriveChildAppContainerSid(PSID pSid, char *a2, PSID *Sid)
{
  int IsChildAppContainerSid; // ebx
  PSID v7; // rbx
  int v8; // eax
  __int64 v9; // rax
  unsigned int v10; // edi
  unsigned __int16 *v11; // rbx
  int v12; // eax
  int v13; // edi
  DWORD v15; // [rsp+20h] [rbp-38h]
  DWORD v16; // [rsp+28h] [rbp-30h]
  DWORD v17; // [rsp+30h] [rbp-28h]
  DWORD v18; // [rsp+38h] [rbp-20h]
  LPWSTR StringSid; // [rsp+40h] [rbp-18h] BYREF
  PSID Sida[2]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  unsigned __int16 *v22; // [rsp+B8h] [rbp+60h] BYREF

  LODWORD(v22) = 0;
  Sida[0] = 0;
  IsChildAppContainerSid = AppContainerRegistrationHelper::IsChildAppContainerSid(pSid, (int *)&v22);
  if ( IsChildAppContainerSid >= 0 )
  {
    if ( (_DWORD)v22 )
    {
      IsChildAppContainerSid = -2147024809;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)0x80070057LL,
        (int)"Name %ls",
        a2);
      goto LABEL_26;
    }
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( ConvertSidToStringSidW(pSid, &StringSid) )
    {
      v7 = Sida[0];
      if ( Sida[0] )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v22);
        RtlFreeSid(v7);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v22);
      }
      Sida[0] = 0;
      v8 = AppContainerDeriveSidFromMoniker(a2, Sida);
      IsChildAppContainerSid = v8;
      if ( v8 >= 0 )
      {
        if ( *GetSidSubAuthorityCount(pSid) == 8 && *GetSidSubAuthorityCount(Sida[0]) == 8 )
        {
          v9 = -1;
          do
            ++v9;
          while ( StringSid[v9] );
          v10 = 2 * v9 + 90;
          v22 = (unsigned __int16 *)CoTaskMemAlloc(v10);
          v11 = v22;
          if ( v22 )
          {
            v18 = *GetSidSubAuthority(Sida[0], 7u);
            v17 = *GetSidSubAuthority(Sida[0], 6u);
            v16 = *GetSidSubAuthority(Sida[0], 5u);
            v15 = *GetSidSubAuthority(Sida[0], 4u);
            v12 = StringCbPrintfW(v11, v10, L"%s-%lu-%lu-%lu-%lu", StringSid, v15, v16, v17, v18);
            v13 = v12;
            if ( v12 < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x1CD,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                (const char *)(unsigned int)v12,
                (int)"Name %ls Sid %ls",
                a2,
                StringSid);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22);
              wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
              IsChildAppContainerSid = v13;
              goto LABEL_26;
            }
            if ( ConvertStringSidToSidW(v11, Sid) )
            {
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22);
              wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
              IsChildAppContainerSid = 0;
              goto LABEL_26;
            }
            IsChildAppContainerSid = wil::details::in1diag3::Return_GetLastErrorMsg(
                                       retaddr,
                                       (void *)0x1D0,
                                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                                       "Name %ls Sid %ls",
                                       a2,
                                       v11);
          }
          else
          {
            IsChildAppContainerSid = -2147024882;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x1C3,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)0x8007000ELL,
              (int)"Sid %ls len %d",
              (const char *)StringSid,
              v10);
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22);
        }
        else
        {
          IsChildAppContainerSid = -2147418113;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x1B6,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)0x8000FFFFLL,
            (int)"Name %ls Sid %ls",
            a2,
            StringSid);
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1B1,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v8,
          (int)"Name %ls Sid %ls",
          a2,
          StringSid);
      }
    }
    else
    {
      IsChildAppContainerSid = wil::details::in1diag3::Return_GetLastErrorMsg(
                                 retaddr,
                                 (void *)0x1AE,
                                 (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                                 "Name %ls",
                                 a2);
    }
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x1A8,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)(unsigned int)IsChildAppContainerSid,
    (int)"RAC %ls",
    a2);
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(Sida);
  return (unsigned int)IsChildAppContainerSid;
}

```

## disassembly

```asm
0x180016740  push    rbp
0x180016742  push    rbx
0x180016743  push    rsi
0x180016744  push    rdi
0x180016745  push    r12
0x180016747  push    r13
0x180016749  push    r14
0x18001674b  push    r15
0x18001674d  mov     rbp, rsp
0x180016750  sub     rsp, 58h
0x180016754  mov     r15, rdx
0x180016757  xor     esi, esi
0x180016759  lea     rdx, [rbp+arg_18]; int *
0x18001675d  mov     dword ptr [rbp+arg_18], esi
0x180016760  mov     [rbp+Sid], rsi
0x180016764  mov     r13, r8
0x180016767  mov     rdi, rcx
0x18001676a  call    ?IsChildAppContainerSid@AppContainerRegistrationHelper@@CAJQEAXPEAH@Z; AppContainerRegistrationHelper::IsChildAppContainerSid(void * const,int *)
0x18001676f  mov     ebx, eax
0x180016771  test    eax, eax
0x180016773  jns     short loc_18001678D
0x180016775  lea     rax, aRacLs; "RAC %ls"
0x18001677c  mov     [rsp+58h+var_30], r15
0x180016781  mov     [rsp+58h+var_38], rax
0x180016786  mov     edx, 1A8h
0x18001678b  jmp     short loc_1800167AD
0x18001678d  cmp     dword ptr [rbp+arg_18], esi
0x180016790  jz      short loc_1800167C5
0x180016792  lea     r9, aNameLs; "Name %ls"
0x180016799  mov     [rsp+58h+var_30], r15; char *
0x18001679e  mov     [rsp+58h+var_38], r9; int
0x1800167a3  mov     ebx, 80070057h
0x1800167a8  mov     edx, 1AAh; void *
0x1800167ad  mov     rcx, [rbp+40h]; this
0x1800167b1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800167b8  mov     r9d, ebx; char *
0x1800167bb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800167c0  jmp     loc_180016A99
0x1800167c5  xor     edx, edx
0x1800167c7  mov     [rbp+StringSid], rsi
0x1800167cb  lea     rcx, [rbp+StringSid]
0x1800167cf  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800167d4  lea     rdx, [rbp+StringSid]; StringSid
0x1800167d8  mov     rcx, rdi; Sid
0x1800167db  call    cs:__imp_ConvertSidToStringSidW
0x1800167e2  nop     dword ptr [rax+rax+00h]
0x1800167e7  test    eax, eax
0x1800167e9  jnz     short loc_180016813
0x1800167eb  mov     rcx, [rbp+40h]; this
0x1800167ef  lea     r9, aNameLs; "Name %ls"
0x1800167f6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800167fd  mov     [rsp+58h+var_38], r15; char *
0x180016802  mov     edx, 1AEh; void *
0x180016807  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18001680c  mov     ebx, eax
0x18001680e  jmp     loc_180016A90
0x180016813  mov     rbx, [rbp+Sid]
0x180016817  test    rbx, rbx
0x18001681a  jz      short loc_18001683D
0x18001681c  lea     rcx, [rbp+arg_18]; this
0x180016820  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180016825  mov     rcx, rbx; Sid
0x180016828  call    cs:__imp_RtlFreeSid
0x18001682f  nop     dword ptr [rax+rax+00h]
0x180016834  lea     rcx, [rbp+arg_18]; this
0x180016838  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001683d  lea     rdx, [rbp+Sid]
0x180016841  mov     [rbp+Sid], rsi
0x180016845  mov     rcx, r15
0x180016848  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18001684f  nop     dword ptr [rax+rax+00h]
0x180016854  mov     ebx, eax
0x180016856  test    eax, eax
0x180016858  jns     short loc_180016881
0x18001685a  mov     rdx, [rbp+StringSid]
0x18001685e  mov     r9d, eax
0x180016861  mov     [rsp+58h+var_28], rdx
0x180016866  lea     rdx, aNameLsSidLs; "Name %ls Sid %ls"
0x18001686d  mov     [rsp+58h+var_30], r15
0x180016872  mov     [rsp+58h+var_38], rdx
0x180016877  mov     edx, 1B1h
0x18001687c  jmp     loc_180016A80
0x180016881  mov     rcx, rdi; pSid
0x180016884  call    cs:__imp_GetSidSubAuthorityCount
0x18001688b  nop     dword ptr [rax+rax+00h]
0x180016890  cmp     byte ptr [rax], 8
0x180016893  jnz     loc_180016A59
0x180016899  mov     rcx, [rbp+Sid]; pSid
0x18001689d  call    cs:__imp_GetSidSubAuthorityCount
0x1800168a4  nop     dword ptr [rax+rax+00h]
0x1800168a9  cmp     byte ptr [rax], 8
0x1800168ac  jnz     loc_180016A59
0x1800168b2  mov     rcx, [rbp+StringSid]
0x1800168b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800168ba  inc     rax
0x1800168bd  cmp     [rcx+rax*2], si
0x1800168c1  jnz     short loc_1800168BA
0x1800168c3  lea     edi, ds:5Ah[rax*2]
0x1800168ca  mov     ecx, edi; cb
0x1800168cc  mov     r12d, edi
0x1800168cf  call    cs:__imp_CoTaskMemAlloc
0x1800168d6  nop     dword ptr [rax+rax+00h]
0x1800168db  mov     [rbp+arg_18], rax
0x1800168df  mov     rbx, rax
0x1800168e2  test    rax, rax
0x1800168e5  jnz     short loc_18001692B
0x1800168e7  mov     rax, [rbp+StringSid]
0x1800168eb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800168f2  mov     rcx, [rbp+40h]; this
0x1800168f6  mov     ebx, 8007000Eh
0x1800168fb  mov     dword ptr [rsp+58h+var_28], edi
0x1800168ff  mov     r9d, ebx; char *
0x180016902  mov     [rsp+58h+var_30], rax; char *
0x180016907  mov     edx, 1C3h; void *
0x18001690c  lea     rax, aSidLsLenD; "Sid %ls len %d"
0x180016913  mov     [rsp+58h+var_38], rax; int
0x180016918  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001691d  lea     rcx, [rbp+arg_18]
0x180016921  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180016926  jmp     loc_180016A90
0x18001692b  mov     rcx, [rbp+Sid]; pSid
0x18001692f  mov     edx, 7; nSubAuthority
0x180016934  call    cs:__imp_GetSidSubAuthority
0x18001693b  nop     dword ptr [rax+rax+00h]
0x180016940  mov     rcx, [rbp+Sid]; pSid
0x180016944  mov     edx, 6; nSubAuthority
0x180016949  mov     r14d, [rax]
0x18001694c  call    cs:__imp_GetSidSubAuthority
0x180016953  nop     dword ptr [rax+rax+00h]
0x180016958  mov     rcx, [rbp+Sid]; pSid
0x18001695c  mov     edx, 5; nSubAuthority
0x180016961  mov     esi, [rax]
0x180016963  call    cs:__imp_GetSidSubAuthority
0x18001696a  nop     dword ptr [rax+rax+00h]
0x18001696f  mov     rcx, [rbp+Sid]; pSid
0x180016973  mov     edx, 4; nSubAuthority
0x180016978  mov     edi, [rax]
0x18001697a  call    cs:__imp_GetSidSubAuthority
0x180016981  nop     dword ptr [rax+rax+00h]
0x180016986  mov     r9, [rbp+StringSid]
0x18001698a  lea     r8, aSLuLuLuLu; "%s-%lu-%lu-%lu-%lu"
0x180016991  mov     [rsp+58h+var_20], r14d
0x180016996  mov     rdx, r12; unsigned __int64
0x180016999  mov     dword ptr [rsp+58h+var_28], esi
0x18001699d  mov     rcx, rbx; unsigned __int16 *
0x1800169a0  mov     eax, [rax]
0x1800169a2  mov     dword ptr [rsp+58h+var_30], edi
0x1800169a6  mov     dword ptr [rsp+58h+var_38], eax
0x1800169aa  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800169af  mov     edi, eax
0x1800169b1  test    eax, eax
0x1800169b3  jns     short loc_180016A00
0x1800169b5  mov     rdx, [rbp+StringSid]
0x1800169b9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800169c0  mov     rcx, [rbp+40h]; this
0x1800169c4  mov     r9d, eax; char *
0x1800169c7  mov     [rsp+58h+var_28], rdx
0x1800169cc  lea     rdx, aNameLsSidLs; "Name %ls Sid %ls"
0x1800169d3  mov     [rsp+58h+var_30], r15; char *
0x1800169d8  mov     [rsp+58h+var_38], rdx; int
0x1800169dd  mov     edx, 1CDh; void *
0x1800169e2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800169e7  lea     rcx, [rbp+arg_18]
0x1800169eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800169f0  lea     rcx, [rbp+StringSid]
0x1800169f4  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x1800169f9  mov     ebx, edi
0x1800169fb  jmp     loc_180016A99
0x180016a00  mov     rdx, r13; Sid
0x180016a03  mov     rcx, rbx; StringSid
0x180016a06  call    cs:__imp_ConvertStringSidToSidW
0x180016a0d  nop     dword ptr [rax+rax+00h]
0x180016a12  test    eax, eax
0x180016a14  jnz     short loc_180016A43
0x180016a16  mov     rcx, [rbp+40h]; this
0x180016a1a  lea     r9, aNameLsSidLs; "Name %ls Sid %ls"
0x180016a21  mov     [rsp+58h+var_30], rbx
0x180016a26  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016a2d  mov     edx, 1D0h; void *
0x180016a32  mov     [rsp+58h+var_38], r15; char *
0x180016a37  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180016a3c  mov     ebx, eax
0x180016a3e  jmp     loc_18001691D
0x180016a43  lea     rcx, [rbp+arg_18]
0x180016a47  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180016a4c  lea     rcx, [rbp+StringSid]
0x180016a50  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180016a55  xor     ebx, ebx
0x180016a57  jmp     short loc_180016A99
0x180016a59  mov     rax, [rbp+StringSid]
0x180016a5d  lea     rdx, aNameLsSidLs; "Name %ls Sid %ls"
0x180016a64  mov     [rsp+58h+var_28], rax
0x180016a69  mov     ebx, 8000FFFFh
0x180016a6e  mov     [rsp+58h+var_30], r15; char *
0x180016a73  mov     r9d, ebx; char *
0x180016a76  mov     [rsp+58h+var_38], rdx; int
0x180016a7b  mov     edx, 1B6h; void *
0x180016a80  mov     rcx, [rbp+40h]; this
0x180016a84  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016a8b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180016a90  lea     rcx, [rbp+StringSid]
0x180016a94  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x180016a99  lea     rcx, [rbp+Sid]
0x180016a9d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180016aa2  mov     eax, ebx
0x180016aa4  add     rsp, 58h
0x180016aa8  pop     r15
0x180016aaa  pop     r14
0x180016aac  pop     r13
0x180016aae  pop     r12
0x180016ab0  pop     rdi
0x180016ab1  pop     rsi
0x180016ab2  pop     rbx
0x180016ab3  pop     rbp
0x180016ab4  retn
```
