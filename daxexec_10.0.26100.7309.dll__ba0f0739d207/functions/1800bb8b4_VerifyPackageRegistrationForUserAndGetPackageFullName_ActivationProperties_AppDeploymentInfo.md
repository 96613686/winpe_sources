# VerifyPackageRegistrationForUserAndGetPackageFullName(ActivationProperties &,AppDeploymentInfo *)

- ea: `0x1800bb8b4`
- end: `0x1800bbb4e`
- name: `?VerifyPackageRegistrationForUserAndGetPackageFullName@@YAXAEAUActivationProperties@@PEAUAppDeploymentInfo@@@Z`
- size: `666`
- prototype: `void(struct ActivationProperties *, struct AppDeploymentInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b45b0`

## callees

- `0x18000b64c`
- `0x180010a84`
- `0x180011b04`
- `0x18003ddec`
- `0x1800a01cc`
- `0x1800bb8b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bba06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bba06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bba25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bba25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bba17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbaac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bba17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbaac`
- `AppXDeploymentClient!__imp_GetPackageRegistrationStatusForUserAndDefaultAccount` at `0x1800bb9a6`
- `AppXDeploymentClient!__imp_GetPackageRegistrationStatusForUserAndDefaultAccount` at `0x1800bba6b`
- `AppXDeploymentClient!__imp_GetPackageRegistrationStatusForUserAndDefaultAccount` at `0x1800bb9a6`
- `AppXDeploymentClient!__imp_GetPackageRegistrationStatusForUserAndDefaultAccount` at `0x1800bba6b`
- `ext-ms-win-core-app-package-registration-l1-1-0!EnsurePackageRegisteredForMultiUserSession` at `0x1800bb90c`
- `ext-ms-win-core-app-package-registration-l1-1-0!EnsurePackageRegisteredForMultiUserSession` at `0x1800bb90c`

## string_xrefs

- `0x1800bbad3`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bbae8`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bbafd`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bbb12`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bbb27`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bbb3c`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall VerifyPackageRegistrationForUserAndGetPackageFullName(
        struct ActivationProperties *a1,
        struct AppDeploymentInfo *a2)
{
  char v4; // al
  const unsigned __int16 *v5; // rdi
  __int64 v6; // rdx
  const WCHAR *v7; // rbx
  WCHAR *v8; // rcx
  int v9; // eax
  const unsigned __int16 *v10; // rdx
  unsigned __int16 **v11; // r9
  int v12; // eax
  void *v13; // rbx
  char *v14; // rcx
  int PackageRegistrationStatusForUserAndDefaultAccount; // eax
  const unsigned __int16 *v16; // rcx
  int v17; // eax
  int v18; // eax
  unsigned __int16 **v19; // [rsp+20h] [rbp-30h]
  int v20; // [rsp+20h] [rbp-30h]
  int v21; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v23; // [rsp+90h] [rbp+40h] BYREF
  void *Src; // [rsp+98h] [rbp+48h] BYREF

  v4 = IsEnsurePackageRegisteredForMultiUserSessionPresent();
  v5 = (const unsigned __int16 *)((char *)a1 + 160);
  v6 = *((_QWORD *)a1 + 40);
  if ( v4 )
  {
    if ( *((_QWORD *)a1 + 23) > 7u )
      v5 = *(const unsigned __int16 **)v5;
    v7 = (const WCHAR *)((char *)a1 + 64);
    v8 = (WCHAR *)((char *)a1 + 64);
    if ( *((_QWORD *)a1 + 11) > 7u )
      v8 = *(WCHAR **)v7;
    v9 = EnsurePackageRegisteredForMultiUserSession(v8, v5, *((_QWORD *)a1 + 40));
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v9,
        (int)v19);
    Src = 0;
    if ( *((_QWORD *)a1 + 11) > 7u )
      v7 = *(const WCHAR **)v7;
    v12 = DevPlat::Shared::PraidAndPackageInfoFromAppId(v7, v10, (unsigned __int16 **)&Src, v11, v19);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x176,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v12,
        v20);
    v13 = Src;
    std::wstring::operator=((char *)a1 + 128, Src);
    if ( v13 )
      CoTaskMemFree(v13);
  }
  else
  {
    v23 = 0;
    v14 = (char *)a1 + 160;
    if ( *((_QWORD *)a1 + 23) > 7u )
      v14 = *(char **)v5;
    PackageRegistrationStatusForUserAndDefaultAccount = GetPackageRegistrationStatusForUserAndDefaultAccount(
                                                          v14,
                                                          v6,
                                                          1,
                                                          &v23);
    if ( PackageRegistrationStatusForUserAndDefaultAccount < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)PackageRegistrationStatusForUserAndDefaultAccount,
        0);
    if ( v23 )
    {
      LODWORD(Src) = 0;
      v16 = (const unsigned __int16 *)((char *)a1 + 160);
      if ( *((_QWORD *)a1 + 23) > 7u )
        v16 = *(const unsigned __int16 **)v5;
      v17 = RegisterDesktopAppXPackageFamilyForUser(v16, 0xFFFFFFFF, *((_QWORD *)a1 + 40), (int *)&Src, a2);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x18E,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
          (const char *)(unsigned int)v17,
          v21);
      if ( *((_QWORD *)a1 + 23) > 7u )
        v5 = *(const unsigned __int16 **)v5;
      v18 = GetPackageRegistrationStatusForUserAndDefaultAccount(v5, *((_QWORD *)a1 + 40), 1, &v23);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x196,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
          (const char *)(unsigned int)v18,
          0);
      if ( v23 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x197,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
          (const char *)0x80270254LL,
          0);
    }
    std::wstring::operator=((char *)a1 + 128, 0);
  }
}

```

## disassembly

```asm
0x1800bb8b4  mov     [rsp-28h+arg_0], rbx
0x1800bb8b9  push    rbp
0x1800bb8ba  push    rsi
0x1800bb8bb  push    rdi
0x1800bb8bc  push    r14
0x1800bb8be  push    r15
0x1800bb8c0  mov     rbp, rsp
0x1800bb8c3  sub     rsp, 50h
0x1800bb8c7  mov     rbx, rdx
0x1800bb8ca  mov     rsi, rcx
0x1800bb8cd  call    IsEnsurePackageRegisteredForMultiUserSessionPresent
0x1800bb8d2  lea     rdi, [rsi+0A0h]
0x1800bb8d9  mov     rdx, [rsi+140h]
0x1800bb8e0  xor     r15d, r15d
0x1800bb8e3  test    al, al
0x1800bb8e5  jz      loc_1800BB96F
0x1800bb8eb  cmp     qword ptr [rdi+18h], 7
0x1800bb8f0  jbe     short loc_1800BB8F5
0x1800bb8f2  mov     rdi, [rdi]
0x1800bb8f5  lea     rbx, [rsi+40h]
0x1800bb8f9  mov     rcx, rbx
0x1800bb8fc  cmp     qword ptr [rbx+18h], 7
0x1800bb901  jbe     short loc_1800BB906
0x1800bb903  mov     rcx, [rbx]
0x1800bb906  mov     r8, rdx
0x1800bb909  mov     rdx, rdi
0x1800bb90c  call    cs:__imp_EnsurePackageRegisteredForMultiUserSession
0x1800bb913  nop     dword ptr [rax+rax+00h]
0x1800bb918  mov     rcx, [rbp+28h]; this
0x1800bb91c  test    eax, eax
0x1800bb91e  js      loc_1800BBAE5
0x1800bb924  mov     [rbp+Src], r15
0x1800bb928  cmp     qword ptr [rbx+18h], 7
0x1800bb92d  jbe     short loc_1800BB932
0x1800bb92f  mov     rbx, [rbx]
0x1800bb932  lea     r8, [rbp+Src]; unsigned __int16 **
0x1800bb936  mov     rcx, rbx; applicationUserModelId
0x1800bb939  call    ?PraidAndPackageInfoFromAppId@Shared@DevPlat@@YAJPEBGPEAPEAG11@Z; DevPlat::Shared::PraidAndPackageInfoFromAppId(ushort const *,ushort * *,ushort * *,ushort * *)
0x1800bb93e  mov     rcx, [rbp+28h]; this
0x1800bb942  test    eax, eax
0x1800bb944  js      loc_1800BBAFA
0x1800bb94a  lea     rcx, [rsi+80h]; void *
0x1800bb951  mov     rbx, [rbp+Src]
0x1800bb955  mov     rdx, rbx; Src
0x1800bb958  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800bb95d  nop
0x1800bb95e  test    rbx, rbx
0x1800bb961  jz      loc_1800BBAB8
0x1800bb967  mov     rcx, rbx
0x1800bb96a  jmp     loc_1800BBAAC
0x1800bb96f  mov     [rbp+arg_10], r15d
0x1800bb973  mov     [rbp+pv], r15
0x1800bb977  mov     rcx, rdi
0x1800bb97a  cmp     qword ptr [rdi+18h], 7
0x1800bb97f  jbe     short loc_1800BB984
0x1800bb981  mov     rcx, [rdi]
0x1800bb984  lea     rax, [rbp+pv]
0x1800bb988  mov     [rsp+50h+var_18], rax
0x1800bb98d  mov     [rsp+50h+var_20], r15
0x1800bb992  mov     [rsp+50h+var_28], r15
0x1800bb997  mov     [rsp+50h+var_30], r15; int
0x1800bb99c  lea     r9, [rbp+arg_10]
0x1800bb9a0  mov     r8d, 1
0x1800bb9a6  call    cs:__imp_GetPackageRegistrationStatusForUserAndDefaultAccount
0x1800bb9ad  nop     dword ptr [rax+rax+00h]
0x1800bb9b2  mov     rcx, [rbp+28h]; this
0x1800bb9b6  test    eax, eax
0x1800bb9b8  js      loc_1800BBB0F
0x1800bb9be  cmp     [rbp+arg_10], r15d
0x1800bb9c2  jz      loc_1800BBA92
0x1800bb9c8  mov     dword ptr [rbp+Src], r15d
0x1800bb9cc  mov     rcx, rdi
0x1800bb9cf  cmp     qword ptr [rdi+18h], 7
0x1800bb9d4  jbe     short loc_1800BB9D9
0x1800bb9d6  mov     rcx, [rdi]; unsigned __int16 *
0x1800bb9d9  mov     [rsp+50h+var_30], rbx; int
0x1800bb9de  lea     r9, [rbp+Src]; int *
0x1800bb9e2  mov     r8, [rsi+140h]; unsigned __int64
0x1800bb9e9  or      edx, 0FFFFFFFFh; unsigned int
0x1800bb9ec  call    ?RegisterDesktopAppXPackageFamilyForUser@@YAJPEBGK_KPEAHPEAUAppDeploymentInfo@@@Z; RegisterDesktopAppXPackageFamilyForUser(ushort const *,ulong,unsigned __int64,int *,AppDeploymentInfo *)
0x1800bb9f1  mov     rcx, [rbp+28h]; this
0x1800bb9f5  test    eax, eax
0x1800bb9f7  js      loc_1800BBB24
0x1800bb9fd  mov     r14, [rbp+pv]
0x1800bba01  test    r14, r14
0x1800bba04  jz      short loc_1800BBA31
0x1800bba06  call    cs:__imp_GetLastError
0x1800bba0d  nop     dword ptr [rax+rax+00h]
0x1800bba12  mov     ebx, eax
0x1800bba14  mov     rcx, r14; pv
0x1800bba17  call    cs:__imp_CoTaskMemFree
0x1800bba1e  nop     dword ptr [rax+rax+00h]
0x1800bba23  mov     ecx, ebx; dwErrCode
0x1800bba25  call    cs:__imp_SetLastError
0x1800bba2c  nop     dword ptr [rax+rax+00h]
0x1800bba31  mov     [rbp+pv], r15
0x1800bba35  cmp     qword ptr [rdi+18h], 7
0x1800bba3a  jbe     short loc_1800BBA3F
0x1800bba3c  mov     rdi, [rdi]
0x1800bba3f  lea     rax, [rbp+pv]
0x1800bba43  mov     [rsp+50h+var_18], rax
0x1800bba48  mov     [rsp+50h+var_20], r15
0x1800bba4d  mov     [rsp+50h+var_28], r15
0x1800bba52  mov     [rsp+50h+var_30], r15; int
0x1800bba57  lea     r9, [rbp+arg_10]
0x1800bba5b  mov     r8d, 1
0x1800bba61  mov     rdx, [rsi+140h]
0x1800bba68  mov     rcx, rdi
0x1800bba6b  call    cs:__imp_GetPackageRegistrationStatusForUserAndDefaultAccount
0x1800bba72  nop     dword ptr [rax+rax+00h]
0x1800bba77  mov     rcx, [rbp+28h]; this
0x1800bba7b  test    eax, eax
0x1800bba7d  js      loc_1800BBB39
0x1800bba83  cmp     [rbp+arg_10], r15d
0x1800bba87  setnz   al
0x1800bba8a  mov     rcx, [rbp+28h]; this
0x1800bba8e  test    al, al
0x1800bba90  jnz     short loc_1800BBACD
0x1800bba92  lea     rcx, [rsi+80h]; void *
0x1800bba99  mov     rdx, [rbp+pv]; Src
0x1800bba9d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800bbaa2  nop
0x1800bbaa3  mov     rcx, [rbp+pv]; pv
0x1800bbaa7  test    rcx, rcx
0x1800bbaaa  jz      short loc_1800BBAB8
0x1800bbaac  call    cs:__imp_CoTaskMemFree
0x1800bbab3  nop     dword ptr [rax+rax+00h]
0x1800bbab8  mov     rbx, [rsp+50h+arg_0]
0x1800bbac0  add     rsp, 50h
0x1800bbac4  pop     r15
0x1800bbac6  pop     r14
0x1800bbac8  pop     rdi
0x1800bbac9  pop     rsi
0x1800bbaca  pop     rbp
0x1800bbacb  retn
0x1800bbacd  mov     r9d, 80270254h; char *
0x1800bbad3  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bbada  mov     edx, 197h; void *
0x1800bbadf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bbae5  mov     r9d, eax; char *
0x1800bbae8  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bbaef  mov     edx, 173h; void *
0x1800bbaf4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bbafa  mov     r9d, eax; char *
0x1800bbafd  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bbb04  mov     edx, 176h; void *
0x1800bbb09  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bbb0f  mov     r9d, eax; char *
0x1800bbb12  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bbb19  mov     edx, 184h; void *
0x1800bbb1e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bbb24  mov     r9d, eax; char *
0x1800bbb27  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bbb2e  mov     edx, 18Eh; void *
0x1800bbb33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bbb39  mov     r9d, eax; char *
0x1800bbb3c  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bbb43  mov     edx, 196h; void *
0x1800bbb48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
