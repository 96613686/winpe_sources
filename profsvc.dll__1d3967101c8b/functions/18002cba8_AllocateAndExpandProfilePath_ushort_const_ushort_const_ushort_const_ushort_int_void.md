# AllocateAndExpandProfilePath(ushort const *,ushort const *,ushort const *,ushort * *,int *,void *)

- ea: `0x18002cba8`
- end: `0x18002ce32`
- name: `?AllocateAndExpandProfilePath@@YAJPEBG00PEAPEAGPEAHPEAX@Z`
- size: `650`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, PWSTR Environment, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000be00`

## callees

- `0x1800069d0`
- `0x1800080c8`
- `0x1800111a0`
- `0x180016658`
- `0x18001dc80`
- `0x1800212a0`
- `0x18002aef0`
- `0x18002cba8`
- `0x18002d2d8`
- `0x1800452e8`
- `0x18004d110`

## import_xrefs

- `ntdll!RtlDestroyEnvironment` at `0x18002cc0a`
- `ntdll!RtlDestroyEnvironment` at `0x18002ce1b`
- `ntdll!RtlDestroyEnvironment` at `0x18002cc0a`
- `ntdll!RtlDestroyEnvironment` at `0x18002ce1b`
- `ntdll!RtlCreateEnvironment` at `0x18002cbdd`
- `ntdll!RtlCreateEnvironment` at `0x18002cbdd`

## string_xrefs

- `0x18002cbeb`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002cc39`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002ccac`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002cd21`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002cdad`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  int UserDomainName; // ebx
  int v15; // r9d
  __int64 v16; // rdx
  int v17; // r9d
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  unsigned __int16 *v21; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v22; // [rsp+28h] [rbp-48h]
  __int64 v23; // [rsp+30h] [rbp-40h]
  unsigned __int16 *v24; // [rsp+38h] [rbp-38h] BYREF
  __int64 v25; // [rsp+40h] [rbp-30h]
  __int64 v26; // [rsp+48h] [rbp-28h]
  unsigned __int16 *v27; // [rsp+50h] [rbp-20h] BYREF
  __int64 v28; // [rsp+58h] [rbp-18h]
  __int64 v29; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v6 = Environment;
  *a4 = 0;
  Environment = 0;
  *(_DWORD *)v6 = 0;
  v11 = RtlCreateEnvironment(1u, &Environment);
  if ( v11 < 0 )
  {
    UserDomainName = wil::details::in1diag3::Return_NtStatus(
                       retaddr,
                       (void *)0x236,
                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                       (const char *)(unsigned int)v11,
                       (int)v21);
LABEL_3:
    if ( Environment )
      RtlDestroyEnvironment(Environment);
    return (unsigned int)UserDomainName;
  }
  UserDomainName = SetEnvvar((void **)&Environment, L"USERNAME", a1, v12);
  if ( UserDomainName < 0 )
  {
    v16 = 571;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)UserDomainName,
      (int)v21);
    goto LABEL_3;
  }
  if ( a2 )
  {
    UserDomainName = SetEnvvar((void **)&Environment, L"LOGONSERVER", a2, v15);
    if ( UserDomainName < 0 )
    {
      v16 = 576;
      goto LABEL_8;
    }
  }
  v24 = 0;
  v25 = 0;
  v26 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
  v25 = -1;
  v26 = -1;
  UserDomainName = GetUserDomainName(a6, &v24);
  if ( UserDomainName < 0 )
  {
    v18 = 581;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)UserDomainName,
      (int)v21);
LABEL_15:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
    goto LABEL_3;
  }
  UserDomainName = SetEnvvar((void **)&Environment, L"USERDOMAIN_ROAMINGPROFILE", v24, v17);
  if ( UserDomainName < 0 )
  {
    v18 = 582;
    goto LABEL_14;
  }
  v21 = 0;
  v22 = 0;
  v23 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v21);
  v22 = -1;
  v23 = -1;
  v19 = ExpandEnvStringAlloc(Environment, a3, &v21);
  UserDomainName = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)v19,
      (int)v21);
LABEL_20:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v21);
    goto LABEL_15;
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_EnsureCount(&v21);
  if ( v22 >= 5 && StringIsEqual(&v21[v22 - 4], L".man") )
    *(_DWORD *)v6 = 1;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v27);
  v28 = -1;
  v29 = -1;
  UserDomainName = GetRoamingVersionExtension(&v27);
  if ( UserDomainName < 0 )
  {
    v20 = 603;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)UserDomainName,
      (int)v21);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v27);
    goto LABEL_20;
  }
  UserDomainName = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Concat(
                     &v21,
                     v27);
  if ( UserDomainName < 0 )
  {
    v20 = 604;
    goto LABEL_26;
  }
  *a4 = v21;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v27);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v21);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v24);
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  return 0;
}

```

## disassembly

```asm
0x18002cba8  push    rbp
0x18002cbaa  push    rbx
0x18002cbab  push    rsi
0x18002cbac  push    rdi
0x18002cbad  push    r12
0x18002cbaf  push    r14
0x18002cbb1  push    r15
0x18002cbb3  mov     rbp, rsp
0x18002cbb6  sub     rsp, 70h
0x18002cbba  mov     rsi, [rbp+Environment]
0x18002cbbe  xor     r12d, r12d
0x18002cbc1  mov     rdi, rdx
0x18002cbc4  mov     [r9], r12
0x18002cbc7  mov     rbx, rcx
0x18002cbca  mov     [rbp+Environment], r12
0x18002cbce  lea     rdx, [rbp+Environment]; Environment
0x18002cbd2  mov     cl, 1; Inherit
0x18002cbd4  mov     [rsi], r12d
0x18002cbd7  mov     r14, r9
0x18002cbda  mov     r15, r8
0x18002cbdd  call    cs:__imp_RtlCreateEnvironment
0x18002cbe3  test    eax, eax
0x18002cbe5  jns     short loc_18002CC17
0x18002cbe7  mov     rcx, [rbp+38h]; this
0x18002cbeb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002cbf2  mov     r9d, eax; char *
0x18002cbf5  mov     edx, 236h; void *
0x18002cbfa  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002cbff  mov     ebx, eax
0x18002cc01  mov     rcx, [rbp+Environment]; Environment
0x18002cc05  test    rcx, rcx
0x18002cc08  jz      short loc_18002CC10
0x18002cc0a  call    cs:__imp_RtlDestroyEnvironment
0x18002cc10  mov     eax, ebx
0x18002cc12  jmp     loc_18002CE23
0x18002cc17  mov     r8, rbx; unsigned __int16 *
0x18002cc1a  lea     rdx, aUsername_0; "USERNAME"
0x18002cc21  lea     rcx, [rbp+Environment]; void **
0x18002cc25  call    ?SetEnvvar@@YAJPEAPEAXPEBG1H@Z; SetEnvvar(void * *,ushort const *,ushort const *,int)
0x18002cc2a  mov     ebx, eax
0x18002cc2c  test    eax, eax
0x18002cc2e  jns     short loc_18002CC4A
0x18002cc30  mov     edx, 23Bh; void *
0x18002cc35  mov     rcx, [rbp+38h]; this
0x18002cc39  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002cc40  mov     r9d, ebx; char *
0x18002cc43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc48  jmp     short loc_18002CC01
0x18002cc4a  test    rdi, rdi
0x18002cc4d  jz      short loc_18002CC6F
0x18002cc4f  mov     r8, rdi; unsigned __int16 *
0x18002cc52  lea     rdx, aLogonserver; "LOGONSERVER"
0x18002cc59  lea     rcx, [rbp+Environment]; void **
0x18002cc5d  call    ?SetEnvvar@@YAJPEAPEAXPEBG1H@Z; SetEnvvar(void * *,ushort const *,ushort const *,int)
0x18002cc62  mov     ebx, eax
0x18002cc64  test    eax, eax
0x18002cc66  jns     short loc_18002CC6F
0x18002cc68  mov     edx, 240h
0x18002cc6d  jmp     short loc_18002CC35
0x18002cc6f  lea     rcx, [rbp+var_38]
0x18002cc73  mov     [rbp+var_38], r12
0x18002cc77  mov     [rbp+var_30], r12
0x18002cc7b  mov     [rbp+var_28], r12
0x18002cc7f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002cc84  mov     rcx, [rbp+arg_28]; void *
0x18002cc88  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x18002cc8c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002cc90  mov     [rbp+var_30], rdi
0x18002cc94  mov     [rbp+var_28], rdi
0x18002cc98  call    ?GetUserDomainName@@YAJPEAXPEAPEAG@Z; GetUserDomainName(void *,ushort * *)
0x18002cc9d  mov     ebx, eax
0x18002cc9f  test    eax, eax
0x18002cca1  jns     short loc_18002CCC9
0x18002cca3  mov     edx, 245h; void *
0x18002cca8  mov     rcx, [rbp+38h]; this
0x18002ccac  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ccb3  mov     r9d, ebx; char *
0x18002ccb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ccbb  lea     rcx, [rbp+var_38]
0x18002ccbf  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ccc4  jmp     loc_18002CC01
0x18002ccc9  mov     r8, [rbp+var_38]; unsigned __int16 *
0x18002cccd  lea     rdx, aUserdomainRoam; "USERDOMAIN_ROAMINGPROFILE"
0x18002ccd4  lea     rcx, [rbp+Environment]; void **
0x18002ccd8  call    ?SetEnvvar@@YAJPEAPEAXPEBG1H@Z; SetEnvvar(void * *,ushort const *,ushort const *,int)
0x18002ccdd  mov     ebx, eax
0x18002ccdf  test    eax, eax
0x18002cce1  jns     short loc_18002CCEA
0x18002cce3  mov     edx, 246h
0x18002cce8  jmp     short loc_18002CCA8
0x18002ccea  lea     rcx, [rbp+var_50]
0x18002ccee  mov     [rbp+var_50], r12
0x18002ccf2  mov     [rbp+var_48], r12
0x18002ccf6  mov     [rbp+var_40], r12
0x18002ccfa  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ccff  mov     rcx, [rbp+Environment]; void *
0x18002cd03  lea     r8, [rbp+var_50]; unsigned __int16 **
0x18002cd07  mov     rdx, r15; unsigned __int16 *
0x18002cd0a  mov     [rbp+var_48], rdi
0x18002cd0e  mov     [rbp+var_40], rdi
0x18002cd12  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x18002cd17  mov     ebx, eax
0x18002cd19  test    eax, eax
0x18002cd1b  jns     short loc_18002CD43
0x18002cd1d  mov     rcx, [rbp+38h]; this
0x18002cd21  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002cd28  mov     r9d, eax; char *
0x18002cd2b  mov     edx, 24Bh; void *
0x18002cd30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd35  lea     rcx, [rbp+var_50]
0x18002cd39  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002cd3e  jmp     loc_18002CCBB
0x18002cd43  lea     rcx, [rbp+var_50]
0x18002cd47  call    ?_EnsureCount@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCount(void)
0x18002cd4c  mov     rcx, [rbp+var_48]
0x18002cd50  cmp     rcx, 5
0x18002cd54  jb      short loc_18002CD78
0x18002cd56  mov     rax, [rbp+var_50]
0x18002cd5a  lea     rdx, aMan; ".man"
0x18002cd61  add     rax, 0FFFFFFFFFFFFFFF8h
0x18002cd65  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x18002cd69  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18002cd6e  test    eax, eax
0x18002cd70  jz      short loc_18002CD78
0x18002cd72  mov     dword ptr [rsi], 1
0x18002cd78  lea     rcx, [rbp+var_20]
0x18002cd7c  mov     [rbp+var_20], r12
0x18002cd80  mov     [rbp+var_18], r12
0x18002cd84  mov     [rbp+var_10], r12
0x18002cd88  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002cd8d  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x18002cd91  mov     [rbp+var_18], rdi
0x18002cd95  mov     [rbp+var_10], rdi
0x18002cd99  call    ?GetRoamingVersionExtension@@YAJPEAPEAG@Z; GetRoamingVersionExtension(ushort * *)
0x18002cd9e  mov     ebx, eax
0x18002cda0  test    eax, eax
0x18002cda2  jns     short loc_18002CDCA
0x18002cda4  mov     edx, 25Bh; void *
0x18002cda9  mov     rcx, [rbp+38h]; this
0x18002cdad  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002cdb4  mov     r9d, ebx; char *
0x18002cdb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cdbc  lea     rcx, [rbp+var_20]
0x18002cdc0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002cdc5  jmp     loc_18002CD35
0x18002cdca  mov     rdx, [rbp+var_20]
0x18002cdce  lea     rcx, [rbp+var_50]
0x18002cdd2  call    ?Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Concat(ushort const *)
0x18002cdd7  mov     ebx, eax
0x18002cdd9  test    eax, eax
0x18002cddb  jns     short loc_18002CDE4
0x18002cddd  mov     edx, 25Ch
0x18002cde2  jmp     short loc_18002CDA9
0x18002cde4  mov     rax, [rbp+var_50]
0x18002cde8  lea     rcx, [rbp+var_20]
0x18002cdec  mov     [r14], rax
0x18002cdef  mov     [rbp+var_50], r12
0x18002cdf3  mov     [rbp+var_40], r12
0x18002cdf7  mov     [rbp+var_48], r12
0x18002cdfb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ce00  lea     rcx, [rbp+var_50]
0x18002ce04  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ce09  lea     rcx, [rbp+var_38]
0x18002ce0d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ce12  mov     rcx, [rbp+Environment]; Environment
0x18002ce16  test    rcx, rcx
0x18002ce19  jz      short loc_18002CE21
0x18002ce1b  call    cs:__imp_RtlDestroyEnvironment
0x18002ce21  xor     eax, eax
0x18002ce23  add     rsp, 70h
0x18002ce27  pop     r15
0x18002ce29  pop     r14
0x18002ce2b  pop     r12
0x18002ce2d  pop     rdi
0x18002ce2e  pop     rsi
0x18002ce2f  pop     rbx
0x18002ce30  pop     rbp
0x18002ce31  retn
```
