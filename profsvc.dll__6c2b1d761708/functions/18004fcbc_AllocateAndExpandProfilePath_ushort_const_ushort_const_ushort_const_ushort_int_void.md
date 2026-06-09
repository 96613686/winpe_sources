# AllocateAndExpandProfilePath(ushort const *,ushort const *,ushort const *,ushort * *,int *,void *)

- ea: `0x18004fcbc`
- end: `0x18004ff3c`
- name: `?AllocateAndExpandProfilePath@@YAJPEBG00PEAPEAGPEAHPEAX@Z`
- size: `640`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 **@<r9>, PWSTR Environment, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009830`

## callees

- `0x180005c80`
- `0x18000e1a0`
- `0x180010b10`
- `0x1800174f0`
- `0x180021cf0`
- `0x180024260`
- `0x180027d34`
- `0x180030ad0`
- `0x1800364c8`
- `0x1800472a4`
- `0x18004fcbc`
- `0x18005041c`

## import_xrefs

- `ntdll!RtlCreateEnvironment` at `0x18004fcf1`
- `ntdll!RtlCreateEnvironment` at `0x18004fcf1`

## string_xrefs

- `0x18004fd05`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004fd42`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004fdb8`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004fe2d`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004feb9`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall AllocateAndExpandProfilePath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        PWSTR Environment,
        void *a6)
{
  PWSTR v6; // rsi
  NTSTATUS v11; // eax
  int v12; // r9d
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // r9d
  __int64 v16; // rdx
  int UserDomainName; // eax
  int v18; // r9d
  __int64 v19; // rdx
  int v20; // eax
  int RoamingVersionExtension; // eax
  __int64 v22; // rdx
  unsigned __int16 *v24; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v25; // [rsp+28h] [rbp-48h]
  __int64 v26; // [rsp+30h] [rbp-40h]
  unsigned __int16 *v27; // [rsp+38h] [rbp-38h] BYREF
  __int64 v28; // [rsp+40h] [rbp-30h]
  __int64 v29; // [rsp+48h] [rbp-28h]
  unsigned __int16 *v30; // [rsp+50h] [rbp-20h] BYREF
  __int64 v31; // [rsp+58h] [rbp-18h]
  __int64 v32; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v6 = Environment;
  *a4 = 0;
  Environment = 0;
  *(_DWORD *)v6 = 0;
  v11 = RtlCreateEnvironment(1u, &Environment);
  if ( v11 >= 0 )
  {
    v14 = SetEnvvar((void **)&Environment, L"USERNAME", a1, v12);
    v13 = v14;
    if ( v14 < 0 )
    {
      v16 = 571;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v14,
        (int)v24);
      goto LABEL_27;
    }
    if ( a2 )
    {
      v14 = SetEnvvar((void **)&Environment, L"LOGONSERVER", a2, v15);
      v13 = v14;
      if ( v14 < 0 )
      {
        v16 = 576;
        goto LABEL_5;
      }
    }
    v27 = 0;
    v28 = 0;
    v29 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v27);
    v28 = -1;
    v29 = -1;
    UserDomainName = GetUserDomainName(a6, &v27);
    v13 = UserDomainName;
    if ( UserDomainName >= 0 )
    {
      UserDomainName = SetEnvvar((void **)&Environment, L"USERDOMAIN_ROAMINGPROFILE", v27, v18);
      v13 = UserDomainName;
      if ( UserDomainName >= 0 )
      {
        v24 = 0;
        v25 = 0;
        v26 = 0;
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
        v25 = -1;
        v26 = -1;
        v20 = ExpandEnvStringAlloc(Environment, a3, &v24);
        v13 = v20;
        if ( v20 >= 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_EnsureCount(&v24);
          if ( v25 >= 5 && StringIsEqual(&v24[v25 - 4], L".man") )
            *(_DWORD *)v6 = 1;
          v30 = 0;
          v31 = 0;
          v32 = 0;
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v30);
          v31 = -1;
          v32 = -1;
          RoamingVersionExtension = GetRoamingVersionExtension(&v30);
          v13 = RoamingVersionExtension;
          if ( RoamingVersionExtension >= 0 )
          {
            RoamingVersionExtension = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Concat(
                                        &v24,
                                        v30);
            v13 = RoamingVersionExtension;
            if ( RoamingVersionExtension >= 0 )
            {
              *a4 = v24;
              v24 = 0;
              v26 = 0;
              v25 = 0;
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v30);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v27);
              v13 = 0;
              goto LABEL_27;
            }
            v22 = 604;
          }
          else
          {
            v22 = 603;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            (const char *)(unsigned int)RoamingVersionExtension,
            (int)v24);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v30);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24B,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            (const char *)(unsigned int)v20,
            (int)v24);
        }
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
        goto LABEL_12;
      }
      v19 = 582;
    }
    else
    {
      v19 = 581;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)UserDomainName,
      (int)v24);
LABEL_12:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v27);
    goto LABEL_27;
  }
  v13 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x236,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
          (const char *)(unsigned int)v11,
          (int)v24);
LABEL_27:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RtlDestroyEnvironment(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RtlDestroyEnvironment(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Environment);
  return v13;
}

```

## disassembly

```asm
0x18004fcbc  push    rbp
0x18004fcbe  push    rbx
0x18004fcbf  push    rsi
0x18004fcc0  push    rdi
0x18004fcc1  push    r12
0x18004fcc3  push    r14
0x18004fcc5  push    r15
0x18004fcc7  mov     rbp, rsp
0x18004fcca  sub     rsp, 70h
0x18004fcce  mov     rsi, [rbp+Environment]
0x18004fcd2  xor     r12d, r12d
0x18004fcd5  mov     rdi, rdx
0x18004fcd8  mov     [r9], r12
0x18004fcdb  mov     rbx, rcx
0x18004fcde  mov     [rbp+Environment], r12
0x18004fce2  lea     rdx, [rbp+Environment]; Environment
0x18004fce6  mov     cl, 1; Inherit
0x18004fce8  mov     [rsi], r12d
0x18004fceb  mov     r14, r9
0x18004fcee  mov     r15, r8
0x18004fcf1  call    cs:__imp_RtlCreateEnvironment
0x18004fcf8  nop     dword ptr [rax+rax+00h]
0x18004fcfd  test    eax, eax
0x18004fcff  jns     short loc_18004FD20
0x18004fd01  mov     rcx, [rbp+38h]; this
0x18004fd05  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004fd0c  mov     r9d, eax; char *
0x18004fd0f  mov     edx, 236h; void *
0x18004fd14  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004fd19  mov     ebx, eax
0x18004fd1b  jmp     loc_18004FF21
0x18004fd20  mov     r8, rbx; unsigned __int16 *
0x18004fd23  lea     rdx, aUsername_0; "USERNAME"
0x18004fd2a  lea     rcx, [rbp+Environment]; void **
0x18004fd2e  call    ?SetEnvvar@@YAJPEAPEAXPEBG1H@Z; SetEnvvar(void * *,ushort const *,ushort const *,int)
0x18004fd33  mov     ebx, eax
0x18004fd35  test    eax, eax
0x18004fd37  jns     short loc_18004FD56
0x18004fd39  mov     edx, 23Bh; void *
0x18004fd3e  mov     rcx, [rbp+38h]; this
0x18004fd42  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004fd49  mov     r9d, eax; char *
0x18004fd4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fd51  jmp     loc_18004FF21
0x18004fd56  test    rdi, rdi
0x18004fd59  jz      short loc_18004FD7B
0x18004fd5b  mov     r8, rdi; unsigned __int16 *
0x18004fd5e  lea     rdx, aLogonserver; "LOGONSERVER"
0x18004fd65  lea     rcx, [rbp+Environment]; void **
0x18004fd69  call    ?SetEnvvar@@YAJPEAPEAXPEBG1H@Z; SetEnvvar(void * *,ushort const *,ushort const *,int)
0x18004fd6e  mov     ebx, eax
0x18004fd70  test    eax, eax
0x18004fd72  jns     short loc_18004FD7B
0x18004fd74  mov     edx, 240h
0x18004fd79  jmp     short loc_18004FD3E
0x18004fd7b  lea     rcx, [rbp+var_38]
0x18004fd7f  mov     [rbp+var_38], r12
0x18004fd83  mov     [rbp+var_30], r12
0x18004fd87  mov     [rbp+var_28], r12
0x18004fd8b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004fd90  mov     rcx, [rbp+arg_28]; void *
0x18004fd94  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x18004fd98  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004fd9c  mov     [rbp+var_30], rdi
0x18004fda0  mov     [rbp+var_28], rdi
0x18004fda4  call    ?GetUserDomainName@@YAJPEAXPEAPEAG@Z; GetUserDomainName(void *,ushort * *)
0x18004fda9  mov     ebx, eax
0x18004fdab  test    eax, eax
0x18004fdad  jns     short loc_18004FDD5
0x18004fdaf  mov     edx, 245h; void *
0x18004fdb4  mov     rcx, [rbp+38h]; this
0x18004fdb8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004fdbf  mov     r9d, eax; char *
0x18004fdc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fdc7  lea     rcx, [rbp+var_38]
0x18004fdcb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004fdd0  jmp     loc_18004FF21
0x18004fdd5  mov     r8, [rbp+var_38]; unsigned __int16 *
0x18004fdd9  lea     rdx, aUserdomainRoam; "USERDOMAIN_ROAMINGPROFILE"
0x18004fde0  lea     rcx, [rbp+Environment]; void **
0x18004fde4  call    ?SetEnvvar@@YAJPEAPEAXPEBG1H@Z; SetEnvvar(void * *,ushort const *,ushort const *,int)
0x18004fde9  mov     ebx, eax
0x18004fdeb  test    eax, eax
0x18004fded  jns     short loc_18004FDF6
0x18004fdef  mov     edx, 246h
0x18004fdf4  jmp     short loc_18004FDB4
0x18004fdf6  lea     rcx, [rbp+var_50]
0x18004fdfa  mov     [rbp+var_50], r12
0x18004fdfe  mov     [rbp+var_48], r12
0x18004fe02  mov     [rbp+var_40], r12
0x18004fe06  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004fe0b  mov     rcx, [rbp+Environment]; void *
0x18004fe0f  lea     r8, [rbp+var_50]; unsigned __int16 **
0x18004fe13  mov     rdx, r15; unsigned __int16 *
0x18004fe16  mov     [rbp+var_48], rdi
0x18004fe1a  mov     [rbp+var_40], rdi
0x18004fe1e  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x18004fe23  mov     ebx, eax
0x18004fe25  test    eax, eax
0x18004fe27  jns     short loc_18004FE4F
0x18004fe29  mov     rcx, [rbp+38h]; this
0x18004fe2d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004fe34  mov     r9d, eax; char *
0x18004fe37  mov     edx, 24Bh; void *
0x18004fe3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fe41  lea     rcx, [rbp+var_50]
0x18004fe45  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004fe4a  jmp     loc_18004FDC7
0x18004fe4f  lea     rcx, [rbp+var_50]
0x18004fe53  call    ?_EnsureCount@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCount(void)
0x18004fe58  mov     rcx, [rbp+var_48]
0x18004fe5c  cmp     rcx, 5
0x18004fe60  jb      short loc_18004FE84
0x18004fe62  mov     rax, [rbp+var_50]
0x18004fe66  lea     rdx, aMan; ".man"
0x18004fe6d  add     rax, 0FFFFFFFFFFFFFFF8h
0x18004fe71  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x18004fe75  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18004fe7a  test    eax, eax
0x18004fe7c  jz      short loc_18004FE84
0x18004fe7e  mov     dword ptr [rsi], 1
0x18004fe84  lea     rcx, [rbp+var_20]
0x18004fe88  mov     [rbp+var_20], r12
0x18004fe8c  mov     [rbp+var_18], r12
0x18004fe90  mov     [rbp+var_10], r12
0x18004fe94  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004fe99  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x18004fe9d  mov     [rbp+var_18], rdi
0x18004fea1  mov     [rbp+var_10], rdi
0x18004fea5  call    ?GetRoamingVersionExtension@@YAJPEAPEAG@Z; GetRoamingVersionExtension(ushort * *)
0x18004feaa  mov     ebx, eax
0x18004feac  test    eax, eax
0x18004feae  jns     short loc_18004FED6
0x18004feb0  mov     edx, 25Bh; void *
0x18004feb5  mov     rcx, [rbp+38h]; this
0x18004feb9  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004fec0  mov     r9d, eax; char *
0x18004fec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fec8  lea     rcx, [rbp+var_20]
0x18004fecc  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004fed1  jmp     loc_18004FE41
0x18004fed6  mov     rdx, [rbp+var_20]
0x18004feda  lea     rcx, [rbp+var_50]
0x18004fede  call    ?Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Concat(ushort const *)
0x18004fee3  mov     ebx, eax
0x18004fee5  test    eax, eax
0x18004fee7  jns     short loc_18004FEF0
0x18004fee9  mov     edx, 25Ch
0x18004feee  jmp     short loc_18004FEB5
0x18004fef0  mov     rax, [rbp+var_50]
0x18004fef4  lea     rcx, [rbp+var_20]
0x18004fef8  mov     [r14], rax
0x18004fefb  mov     [rbp+var_50], r12
0x18004feff  mov     [rbp+var_40], r12
0x18004ff03  mov     [rbp+var_48], r12
0x18004ff07  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004ff0c  lea     rcx, [rbp+var_50]
0x18004ff10  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004ff15  lea     rcx, [rbp+var_38]
0x18004ff19  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004ff1e  mov     ebx, r12d
0x18004ff21  lea     rcx, [rbp+Environment]
0x18004ff25  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?RtlDestroyEnvironment@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RtlDestroyEnvironment(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RtlDestroyEnvironment(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004ff2a  mov     eax, ebx
0x18004ff2c  add     rsp, 70h
0x18004ff30  pop     r15
0x18004ff32  pop     r14
0x18004ff34  pop     r12
0x18004ff36  pop     rdi
0x18004ff37  pop     rsi
0x18004ff38  pop     rbx
0x18004ff39  pop     rbp
0x18004ff3a  retn
```
