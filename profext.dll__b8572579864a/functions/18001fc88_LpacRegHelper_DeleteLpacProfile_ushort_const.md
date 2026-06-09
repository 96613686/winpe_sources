# LpacRegHelper::DeleteLpacProfile(ushort const *)

- ea: `0x18001fc88`
- end: `0x18001fde3`
- name: `?DeleteLpacProfile@LpacRegHelper@@SAJPEBG@Z`
- size: `347`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001de40`

## callees

- `0x1800044e0`
- `0x180004594`
- `0x18000aacc`
- `0x18000c7d4`
- `0x18000c8d8`
- `0x18000c938`
- `0x18000f884`
- `0x18001fc88`
- `0x18001fdec`
- `0x18001fed0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18001fd19`
- `ntdll!RtlFreeSid` at `0x18001fd19`
- `USERENV!DeleteAppContainerProfile` at `0x18001fc96`
- `USERENV!DeleteAppContainerProfile` at `0x18001fc96`

## string_xrefs

- `0x18001fcc0`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001fd68`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001fda6`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001fd97`: `Failed to create AppContainer capabilities registry for %ls`
- `0x18001fcb1`: `Failed to delete AppContainer profile for %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LpacRegHelper::DeleteLpacProfile(char *a1)
{
  int v2; // ebx
  PSID v3; // rbx
  int v4; // eax
  void *v5; // rcx
  int v7; // [rsp+20h] [rbp-20h]
  _BYTE v8[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned __int16 *v10; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int16 *v11; // [rsp+70h] [rbp+30h] BYREF
  PSID Sid; // [rsp+78h] [rbp+38h] BYREF

  v2 = DeleteAppContainerProfile();
  if ( v2 >= 0 )
  {
    Sid = 0;
    v11 = 0;
    v10 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v10,
      0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v11,
      0);
    v3 = Sid;
    if ( Sid )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v8);
      RtlFreeSid(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v8);
    }
    Sid = 0;
    v4 = LpacRegHelper::DeriveLpacInfo(a1, &Sid, &v11, 0, &v10, 0);
    v2 = v4;
    if ( v4 >= 0 )
    {
      v2 = LpacRegHelper::DeleteRegistryLpac(v5, v11, v10);
      if ( v2 >= 0 )
        v2 = 0;
      else
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x202,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
          (const char *)(unsigned int)v2,
          (int)"Failed to create AppContainer capabilities registry for %ls",
          a1);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FA,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)(unsigned int)v4,
        v7);
    }
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v10);
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&v11);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)v2,
      (int)"Failed to delete AppContainer profile for %ls",
      a1);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001fc88  push    rbp
0x18001fc8a  push    rbx
0x18001fc8b  push    rdi
0x18001fc8c  mov     rbp, rsp
0x18001fc8f  sub     rsp, 40h
0x18001fc93  mov     rdi, rcx
0x18001fc96  call    cs:__imp_DeleteAppContainerProfile
0x18001fc9d  nop     dword ptr [rax+rax+00h]
0x18001fca2  mov     ebx, eax
0x18001fca4  test    eax, eax
0x18001fca6  jns     short loc_18001FCD6
0x18001fca8  mov     rcx, [rbp+18h]; this
0x18001fcac  mov     [rsp+40h+var_18], rdi; char *
0x18001fcb1  lea     rax, aFailedToDelete; "Failed to delete AppContainer profile f"...
0x18001fcb8  mov     [rsp+40h+var_20], rax; int
0x18001fcbd  mov     r9d, ebx; char *
0x18001fcc0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fcc7  mov     edx, 1EDh; void *
0x18001fccc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001fcd1  jmp     loc_18001FDD8
0x18001fcd6  mov     [rbp+Sid], 0
0x18001fcde  mov     [rbp+arg_10], 0
0x18001fce6  mov     [rbp+arg_8], 0
0x18001fcee  xor     edx, edx
0x18001fcf0  lea     rcx, [rbp+arg_8]
0x18001fcf4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001fcf9  xor     edx, edx
0x18001fcfb  lea     rcx, [rbp+arg_10]
0x18001fcff  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001fd04  mov     rbx, [rbp+Sid]
0x18001fd08  test    rbx, rbx
0x18001fd0b  jz      short loc_18001FD2E
0x18001fd0d  lea     rcx, [rbp+var_10]; this
0x18001fd11  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001fd16  mov     rcx, rbx; Sid
0x18001fd19  call    cs:__imp_RtlFreeSid
0x18001fd20  nop     dword ptr [rax+rax+00h]
0x18001fd25  lea     rcx, [rbp+var_10]; this
0x18001fd29  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001fd2e  mov     [rbp+Sid], 0
0x18001fd36  mov     [rsp+40h+var_18], 0; void **
0x18001fd3f  lea     rax, [rbp+arg_8]
0x18001fd43  mov     [rsp+40h+var_20], rax; int
0x18001fd48  xor     r9d, r9d; unsigned __int16 **
0x18001fd4b  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18001fd4f  lea     rdx, [rbp+Sid]; void **
0x18001fd53  mov     rcx, rdi; char *
0x18001fd56  call    ?DeriveLpacInfo@LpacRegHelper@@CAJPEBGPEAPEAXPEAPEAG221@Z; LpacRegHelper::DeriveLpacInfo(ushort const *,void * *,ushort * *,ushort * *,ushort * *,void * *)
0x18001fd5b  mov     ebx, eax
0x18001fd5d  test    eax, eax
0x18001fd5f  jns     short loc_18001FD7B
0x18001fd61  mov     rcx, [rbp+18h]; this
0x18001fd65  mov     r9d, eax; char *
0x18001fd68  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fd6f  mov     edx, 1FAh; void *
0x18001fd74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd79  jmp     short loc_18001FDBB
0x18001fd7b  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x18001fd7f  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18001fd83  call    ?DeleteRegistryLpac@LpacRegHelper@@CAJPEAXPEBG1@Z; LpacRegHelper::DeleteRegistryLpac(void *,ushort const *,ushort const *)
0x18001fd88  mov     ebx, eax
0x18001fd8a  test    eax, eax
0x18001fd8c  jns     short loc_18001FDB9
0x18001fd8e  mov     rcx, [rbp+18h]; this
0x18001fd92  mov     [rsp+40h+var_18], rdi; char *
0x18001fd97  lea     rax, aFailedToCreate_0; "Failed to create AppContainer capabilit"...
0x18001fd9e  mov     [rsp+40h+var_20], rax; int
0x18001fda3  mov     r9d, ebx; char *
0x18001fda6  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fdad  mov     edx, 202h; void *
0x18001fdb2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001fdb7  jmp     short loc_18001FDBB
0x18001fdb9  xor     ebx, ebx
0x18001fdbb  lea     rcx, [rbp+arg_8]
0x18001fdbf  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001fdc4  nop
0x18001fdc5  lea     rcx, [rbp+arg_10]
0x18001fdc9  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001fdce  nop
0x18001fdcf  lea     rcx, [rbp+Sid]
0x18001fdd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001fdd8  mov     eax, ebx
0x18001fdda  add     rsp, 40h
0x18001fdde  pop     rdi
0x18001fddf  pop     rbx
0x18001fde0  pop     rbp
0x18001fde1  retn
```
