# VerifyPackageRegistrationForUserAndGetPackageFullName(ActivationProperties &,AppDeploymentInfo *)

- ea: `0x1800bd6cc`
- end: `0x1800bd9ec`
- name: `?VerifyPackageRegistrationForUserAndGetPackageFullName@@YAXAEAUActivationProperties@@PEAUAppDeploymentInfo@@@Z`
- size: `800`
- prototype: `void(struct ActivationProperties *, struct AppDeploymentInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b617c`

## callees

- `0x18000b132`
- `0x18000d354`
- `0x1800125f4`
- `0x1800130e4`
- `0x18003fd7c`
- `0x1800a1b70`
- `0x1800bd6cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bd883`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bd883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd864`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd94a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bd94a`
- `AppXDeploymentClient!__imp_GetPackageRegistrationStatusForUserAndDefaultAccount` at `0x1800bd802`
- `AppXDeploymentClient!__imp_GetPackageRegistrationStatusForUserAndDefaultAccount` at `0x1800bd8c9`
- `AppXDeploymentClient!__imp_GetPackageRegistrationStatusForUserAndDefaultAccount` at `0x1800bd802`
- `AppXDeploymentClient!__imp_GetPackageRegistrationStatusForUserAndDefaultAccount` at `0x1800bd8c9`
- `ext-ms-win-core-app-package-registration-l1-1-0!EnsurePackageRegisteredForMultiUserSession` at `0x1800bd726`
- `ext-ms-win-core-app-package-registration-l1-1-0!EnsurePackageRegisteredForMultiUserSession` at `0x1800bd726`

## string_xrefs

- `0x1800bd971`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bd986`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bd99b`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bd9b0`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bd9c5`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800bd9da`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`

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
  __int64 v13; // r8
  void *v14; // rdi
  char *v15; // rcx
  unsigned __int64 v16; // rdx
  char *v17; // rsi
  __int64 v18; // rbx
  char *v19; // rcx
  int PackageRegistrationStatusForUserAndDefaultAccount; // eax
  __int64 v21; // r8
  const unsigned __int16 *v22; // rcx
  int v23; // eax
  int v24; // eax
  char **v25; // rcx
  unsigned __int64 v26; // rdx
  char *v27; // rdi
  __int64 v28; // rbx
  unsigned __int16 **v29; // [rsp+20h] [rbp-30h]
  int v30; // [rsp+20h] [rbp-30h]
  int v31; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v33; // [rsp+90h] [rbp+40h] BYREF
  void *Src; // [rsp+98h] [rbp+48h] BYREF

  v4 = IsEnsurePackageRegisteredForMultiUserSessionPresent();
  v5 = (const unsigned __int16 *)((char *)a1 + 160);
  v6 = *((_QWORD *)a1 + 40);
  if ( v4 )
  {
    if ( *((_QWORD *)a1 + 23) > 7u )
      v5 = *(const unsigned __int16 **)v5;
    v7 = (const WCHAR *)((char *)a1 + 64);
    if ( *((_QWORD *)a1 + 11) <= 7u )
      v8 = (WCHAR *)((char *)a1 + 64);
    else
      v8 = *(WCHAR **)v7;
    v9 = EnsurePackageRegisteredForMultiUserSession(v8, v5, *((_QWORD *)a1 + 40));
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v9,
        (int)v29);
    Src = 0;
    if ( *((_QWORD *)a1 + 11) > 7u )
      v7 = *(const WCHAR **)v7;
    v12 = DevPlat::Shared::PraidAndPackageInfoFromAppId(v7, v10, (unsigned __int16 **)&Src, v11, v29);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x176,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v12,
        v30);
    v14 = Src;
    v15 = (char *)a1 + 128;
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)Src + v16) );
    if ( v16 > *((_QWORD *)a1 + 19) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v15,
        v16,
        v13,
        Src);
    }
    else
    {
      if ( *((_QWORD *)a1 + 19) <= 7u )
        v17 = (char *)a1 + 128;
      else
        v17 = *(char **)v15;
      *((_QWORD *)v15 + 2) = v16;
      v18 = 2 * v16;
      memmove_0(v17, v14, 2 * v16);
      *(_WORD *)&v17[v18] = 0;
    }
    if ( v14 )
      CoTaskMemFree(v14);
  }
  else
  {
    v33 = 0;
    if ( *((_QWORD *)a1 + 23) <= 7u )
      v19 = (char *)a1 + 160;
    else
      v19 = *(char **)v5;
    PackageRegistrationStatusForUserAndDefaultAccount = GetPackageRegistrationStatusForUserAndDefaultAccount(
                                                          v19,
                                                          v6,
                                                          1,
                                                          &v33);
    if ( PackageRegistrationStatusForUserAndDefaultAccount < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)PackageRegistrationStatusForUserAndDefaultAccount,
        0);
    if ( v33 )
    {
      LODWORD(Src) = 0;
      if ( *((_QWORD *)a1 + 23) <= 7u )
        v22 = (const unsigned __int16 *)((char *)a1 + 160);
      else
        v22 = *(const unsigned __int16 **)v5;
      v23 = RegisterDesktopAppXPackageFamilyForUser(v22, 0xFFFFFFFF, *((_QWORD *)a1 + 40), (int *)&Src, a2);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x18E,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
          (const char *)(unsigned int)v23,
          v31);
      if ( *((_QWORD *)a1 + 23) > 7u )
        v5 = *(const unsigned __int16 **)v5;
      v24 = GetPackageRegistrationStatusForUserAndDefaultAccount(v5, *((_QWORD *)a1 + 40), 1, &v33);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x196,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
          (const char *)(unsigned int)v24,
          0);
      if ( v33 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x197,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
          (const char *)0x80270254LL,
          0);
    }
    v25 = (char **)((char *)a1 + 128);
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(2 * v26) );
    if ( v26 > *((_QWORD *)a1 + 19) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v25, v26, v21, 0);
    }
    else
    {
      if ( *((_QWORD *)a1 + 19) <= 7u )
        v27 = (char *)a1 + 128;
      else
        v27 = *v25;
      *((_QWORD *)a1 + 18) = v26;
      v28 = 2 * v26;
      memmove_0(v27, 0, 2 * v26);
      *(_WORD *)&v27[v28] = 0;
    }
  }
}

```

## disassembly

```asm
0x1800bd6cc  mov     [rsp-28h+arg_0], rbx
0x1800bd6d1  push    rbp
0x1800bd6d2  push    rsi
0x1800bd6d3  push    rdi
0x1800bd6d4  push    r14
0x1800bd6d6  push    r15
0x1800bd6d8  mov     rbp, rsp
0x1800bd6db  sub     rsp, 50h
0x1800bd6df  mov     rbx, rdx
0x1800bd6e2  mov     rsi, rcx
0x1800bd6e5  call    IsEnsurePackageRegisteredForMultiUserSessionPresent
0x1800bd6ea  lea     rdi, [rsi+0A0h]
0x1800bd6f1  mov     rdx, [rsi+140h]
0x1800bd6f8  xor     r15d, r15d
0x1800bd6fb  test    al, al
0x1800bd6fd  jz      loc_1800BD7C9
0x1800bd703  cmp     qword ptr [rdi+18h], 7
0x1800bd708  jbe     short loc_1800BD70D
0x1800bd70a  mov     rdi, [rdi]
0x1800bd70d  lea     rbx, [rsi+40h]
0x1800bd711  cmp     qword ptr [rbx+18h], 7
0x1800bd716  jbe     short loc_1800BD71D
0x1800bd718  mov     rcx, [rbx]
0x1800bd71b  jmp     short loc_1800BD720
0x1800bd71d  mov     rcx, rbx
0x1800bd720  mov     r8, rdx
0x1800bd723  mov     rdx, rdi
0x1800bd726  call    cs:__imp_EnsurePackageRegisteredForMultiUserSession
0x1800bd72d  nop     dword ptr [rax+rax+00h]
0x1800bd732  mov     rcx, [rbp+28h]; this
0x1800bd736  test    eax, eax
0x1800bd738  js      loc_1800BD983
0x1800bd73e  mov     [rbp+Src], r15
0x1800bd742  cmp     qword ptr [rbx+18h], 7
0x1800bd747  jbe     short loc_1800BD74C
0x1800bd749  mov     rbx, [rbx]
0x1800bd74c  lea     r8, [rbp+Src]; unsigned __int16 **
0x1800bd750  mov     rcx, rbx; applicationUserModelId
0x1800bd753  call    ?PraidAndPackageInfoFromAppId@Shared@DevPlat@@YAJPEBGPEAPEAG11@Z; DevPlat::Shared::PraidAndPackageInfoFromAppId(ushort const *,ushort * *,ushort * *,ushort * *)
0x1800bd758  mov     rcx, [rbp+28h]; this
0x1800bd75c  test    eax, eax
0x1800bd75e  js      loc_1800BD998
0x1800bd764  mov     rdi, [rbp+Src]
0x1800bd768  lea     rcx, [rsi+80h]
0x1800bd76f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bd773  inc     rdx
0x1800bd776  cmp     [rdi+rdx*2], r15w
0x1800bd77b  jnz     short loc_1800BD773
0x1800bd77d  cmp     rdx, [rcx+18h]
0x1800bd781  ja      short loc_1800BD7AF
0x1800bd783  cmp     qword ptr [rcx+18h], 7
0x1800bd788  jbe     short loc_1800BD78F
0x1800bd78a  mov     rsi, [rcx]
0x1800bd78d  jmp     short loc_1800BD792
0x1800bd78f  mov     rsi, rcx
0x1800bd792  mov     [rcx+10h], rdx
0x1800bd796  lea     rbx, [rdx+rdx]
0x1800bd79a  mov     r8, rbx; Size
0x1800bd79d  mov     rdx, rdi; Src
0x1800bd7a0  mov     rcx, rsi; void *
0x1800bd7a3  call    memmove_0
0x1800bd7a8  mov     [rbx+rsi], r15w
0x1800bd7ad  jmp     short loc_1800BD7B8
0x1800bd7af  mov     r9, rdi
0x1800bd7b2  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800bd7b7  nop
0x1800bd7b8  test    rdi, rdi
0x1800bd7bb  jz      loc_1800BD956
0x1800bd7c1  mov     rcx, rdi
0x1800bd7c4  jmp     loc_1800BD94A
0x1800bd7c9  mov     [rbp+arg_10], r15d
0x1800bd7cd  mov     [rbp+pv], r15
0x1800bd7d1  cmp     qword ptr [rdi+18h], 7
0x1800bd7d6  jbe     short loc_1800BD7DD
0x1800bd7d8  mov     rcx, [rdi]
0x1800bd7db  jmp     short loc_1800BD7E0
0x1800bd7dd  mov     rcx, rdi
0x1800bd7e0  lea     rax, [rbp+pv]
0x1800bd7e4  mov     [rsp+50h+var_18], rax
0x1800bd7e9  mov     [rsp+50h+var_20], r15
0x1800bd7ee  mov     [rsp+50h+var_28], r15
0x1800bd7f3  mov     [rsp+50h+var_30], r15; int
0x1800bd7f8  lea     r9, [rbp+arg_10]
0x1800bd7fc  mov     r8d, 1
0x1800bd802  call    cs:__imp_GetPackageRegistrationStatusForUserAndDefaultAccount
0x1800bd809  nop     dword ptr [rax+rax+00h]
0x1800bd80e  mov     rcx, [rbp+28h]; this
0x1800bd812  test    eax, eax
0x1800bd814  js      loc_1800BD9AD
0x1800bd81a  cmp     [rbp+arg_10], r15d
0x1800bd81e  jz      loc_1800BD8F0
0x1800bd824  mov     dword ptr [rbp+Src], r15d
0x1800bd828  cmp     qword ptr [rdi+18h], 7
0x1800bd82d  jbe     short loc_1800BD834
0x1800bd82f  mov     rcx, [rdi]
0x1800bd832  jmp     short loc_1800BD837
0x1800bd834  mov     rcx, rdi; unsigned __int16 *
0x1800bd837  mov     [rsp+50h+var_30], rbx; int
0x1800bd83c  lea     r9, [rbp+Src]; int *
0x1800bd840  mov     r8, [rsi+140h]; unsigned __int64
0x1800bd847  or      edx, 0FFFFFFFFh; unsigned int
0x1800bd84a  call    ?RegisterDesktopAppXPackageFamilyForUser@@YAJPEBGK_KPEAHPEAUAppDeploymentInfo@@@Z; RegisterDesktopAppXPackageFamilyForUser(ushort const *,ulong,unsigned __int64,int *,AppDeploymentInfo *)
0x1800bd84f  mov     rcx, [rbp+28h]; this
0x1800bd853  test    eax, eax
0x1800bd855  js      loc_1800BD9C2
0x1800bd85b  mov     r14, [rbp+pv]
0x1800bd85f  test    r14, r14
0x1800bd862  jz      short loc_1800BD88F
0x1800bd864  call    cs:__imp_GetLastError
0x1800bd86b  nop     dword ptr [rax+rax+00h]
0x1800bd870  mov     ebx, eax
0x1800bd872  mov     rcx, r14; pv
0x1800bd875  call    cs:__imp_CoTaskMemFree
0x1800bd87c  nop     dword ptr [rax+rax+00h]
0x1800bd881  mov     ecx, ebx; dwErrCode
0x1800bd883  call    cs:__imp_SetLastError
0x1800bd88a  nop     dword ptr [rax+rax+00h]
0x1800bd88f  mov     [rbp+pv], r15
0x1800bd893  cmp     qword ptr [rdi+18h], 7
0x1800bd898  jbe     short loc_1800BD89D
0x1800bd89a  mov     rdi, [rdi]
0x1800bd89d  lea     rax, [rbp+pv]
0x1800bd8a1  mov     [rsp+50h+var_18], rax
0x1800bd8a6  mov     [rsp+50h+var_20], r15
0x1800bd8ab  mov     [rsp+50h+var_28], r15
0x1800bd8b0  mov     [rsp+50h+var_30], r15; int
0x1800bd8b5  lea     r9, [rbp+arg_10]
0x1800bd8b9  mov     r8d, 1
0x1800bd8bf  mov     rdx, [rsi+140h]
0x1800bd8c6  mov     rcx, rdi
0x1800bd8c9  call    cs:__imp_GetPackageRegistrationStatusForUserAndDefaultAccount
0x1800bd8d0  nop     dword ptr [rax+rax+00h]
0x1800bd8d5  mov     rcx, [rbp+28h]; this
0x1800bd8d9  test    eax, eax
0x1800bd8db  js      loc_1800BD9D7
0x1800bd8e1  cmp     [rbp+arg_10], r15d
0x1800bd8e5  setnz   al
0x1800bd8e8  mov     rcx, [rbp+28h]; this
0x1800bd8ec  test    al, al
0x1800bd8ee  jnz     short loc_1800BD96B
0x1800bd8f0  mov     r9, [rbp+pv]
0x1800bd8f4  lea     rcx, [rsi+80h]
0x1800bd8fb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bd8ff  inc     rdx
0x1800bd902  cmp     [r9+rdx*2], r15w
0x1800bd907  jnz     short loc_1800BD8FF
0x1800bd909  cmp     rdx, [rcx+18h]
0x1800bd90d  ja      short loc_1800BD93B
0x1800bd90f  cmp     qword ptr [rcx+18h], 7
0x1800bd914  jbe     short loc_1800BD91B
0x1800bd916  mov     rdi, [rcx]
0x1800bd919  jmp     short loc_1800BD91E
0x1800bd91b  mov     rdi, rcx
0x1800bd91e  mov     [rcx+10h], rdx
0x1800bd922  lea     rbx, [rdx+rdx]
0x1800bd926  mov     r8, rbx; Size
0x1800bd929  mov     rdx, r9; Src
0x1800bd92c  mov     rcx, rdi; void *
0x1800bd92f  call    memmove_0
0x1800bd934  mov     [rbx+rdi], r15w
0x1800bd939  jmp     short loc_1800BD941
0x1800bd93b  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800bd940  nop
0x1800bd941  mov     rcx, [rbp+pv]; pv
0x1800bd945  test    rcx, rcx
0x1800bd948  jz      short loc_1800BD956
0x1800bd94a  call    cs:__imp_CoTaskMemFree
0x1800bd951  nop     dword ptr [rax+rax+00h]
0x1800bd956  mov     rbx, [rsp+50h+arg_0]
0x1800bd95e  add     rsp, 50h
0x1800bd962  pop     r15
0x1800bd964  pop     r14
0x1800bd966  pop     rdi
0x1800bd967  pop     rsi
0x1800bd968  pop     rbp
0x1800bd969  retn
0x1800bd96b  mov     r9d, 80270254h; char *
0x1800bd971  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bd978  mov     edx, 197h; void *
0x1800bd97d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bd983  mov     r9d, eax; char *
0x1800bd986  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bd98d  mov     edx, 173h; void *
0x1800bd992  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bd998  mov     r9d, eax; char *
0x1800bd99b  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bd9a2  mov     edx, 176h; void *
0x1800bd9a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bd9ad  mov     r9d, eax; char *
0x1800bd9b0  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bd9b7  mov     edx, 184h; void *
0x1800bd9bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bd9c2  mov     r9d, eax; char *
0x1800bd9c5  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bd9cc  mov     edx, 18Eh; void *
0x1800bd9d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bd9d7  mov     r9d, eax; char *
0x1800bd9da  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800bd9e1  mov     edx, 196h; void *
0x1800bd9e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
