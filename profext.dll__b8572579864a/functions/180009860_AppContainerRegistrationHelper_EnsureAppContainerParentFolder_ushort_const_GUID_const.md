# AppContainerRegistrationHelper::EnsureAppContainerParentFolder(ushort const *,_GUID const *)

- ea: `0x180009860`
- end: `0x180009a2e`
- name: `?EnsureAppContainerParentFolder@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(char *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009504`

## callees

- `0x180002030`
- `0x1800040c0`
- `0x1800044e0`
- `0x180009860`
- `0x18000a2f8`
- `0x180014bd0`
- `0x180022830`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000989e`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000989e`

## string_xrefs

- `0x1800098b2`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180009984`: `Name %ls path %ls`
- `0x1800099e7`: `Path %ls`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::EnsureAppContainerParentFolder(char *a1, const struct _GUID *a2)
{
  unsigned int BasicProfileFolderPath; // eax
  int v5; // eax
  int FolderIfNotPresent; // edi
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  char v12[2]; // [rsp+40h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  BasicProfileFolderPath = GetBasicProfileFolderPath(8, 0, v12, 260);
  v5 = wil::details::in1diag3::Log_IfFailedMsg(
         retaddr,
         (void *)0x467,
         (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
         (const char *)BasicProfileFolderPath,
         (__int64)"Name %ls",
         a1);
  FolderIfNotPresent = v5;
  if ( v5 < 0 )
  {
    AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerGetAppDataFolderFailure, v5, a2);
    return (unsigned int)FolderIfNotPresent;
  }
  FolderIfNotPresent = StringCchCatW((unsigned __int16 *)v12, 0x104u, L"\\Packages");
  if ( FolderIfNotPresent < 0 )
  {
    v8 = 1135;
LABEL_6:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)FolderIfNotPresent,
      (int)"Name %ls",
      a1);
    return (unsigned int)FolderIfNotPresent;
  }
  FolderIfNotPresent = AppContainerRegistrationHelper::CreateFolderIfNotPresent(v12, a2);
  if ( FolderIfNotPresent < 0 )
  {
    v8 = 1137;
    goto LABEL_6;
  }
  FolderIfNotPresent = StringCchCatW((unsigned __int16 *)v12, 0x104u, L"\\");
  if ( FolderIfNotPresent < 0 )
  {
    v9 = 1140;
LABEL_11:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)FolderIfNotPresent,
      (int)"Name %ls path %ls",
      a1,
      v12);
    return (unsigned int)FolderIfNotPresent;
  }
  FolderIfNotPresent = StringCchCatW((unsigned __int16 *)v12, 0x104u, (const unsigned __int16 *)a1);
  if ( FolderIfNotPresent < 0 )
  {
    v9 = 1143;
    goto LABEL_11;
  }
  v10 = AppContainerRegistrationHelper::CreateFolderIfNotPresent(v12, a2);
  v11 = v10;
  if ( v10 >= 0 )
    return 0;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x479,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)(unsigned int)v10,
    (int)"Path %ls",
    v12);
  return v11;
}

```

## disassembly

```asm
0x180009860  mov     [rsp+arg_10], rbx
0x180009865  push    rbp
0x180009866  push    rsi
0x180009867  push    rdi
0x180009868  push    r14
0x18000986a  push    r15
0x18000986c  sub     rsp, 260h
0x180009873  mov     rax, cs:__security_cookie
0x18000987a  xor     rax, rsp
0x18000987d  mov     [rsp+288h+var_38], rax
0x180009885  mov     rsi, rdx
0x180009888  lea     r8, [rsp+288h+var_248]
0x18000988d  xor     edx, edx
0x18000988f  mov     rbx, rcx
0x180009892  mov     r14d, 104h
0x180009898  mov     r9d, r14d
0x18000989b  lea     ecx, [rdx+8]
0x18000989e  call    cs:__imp_GetBasicProfileFolderPath
0x1800098a5  nop     dword ptr [rax+rax+00h]
0x1800098aa  mov     rcx, [rsp+288h]; this
0x1800098b2  lea     rbp, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800098b9  lea     r15, aNameLs; "Name %ls"
0x1800098c0  mov     [rsp+288h+var_260], rbx; char *
0x1800098c5  mov     r9d, eax; char *
0x1800098c8  mov     [rsp+288h+var_268], r15; __int64
0x1800098cd  mov     r8, rbp; unsigned int
0x1800098d0  mov     edx, 467h; void *
0x1800098d5  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800098da  mov     edi, eax
0x1800098dc  test    eax, eax
0x1800098de  jns     short loc_1800098F8
0x1800098e0  mov     r8, rsi; struct _GUID *
0x1800098e3  lea     rcx, AppModelAppContainerGetAppDataFolderFailure; struct _EVENT_DESCRIPTOR *
0x1800098ea  mov     edx, eax; int
0x1800098ec  call    ?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)
0x1800098f1  mov     eax, edi
0x1800098f3  jmp     loc_180009A06
0x1800098f8  lea     r8, aPackages_0; "\\Packages"
0x1800098ff  mov     rdx, r14; unsigned __int64
0x180009902  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x180009907  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000990c  mov     edi, eax
0x18000990e  test    eax, eax
0x180009910  jns     short loc_180009936
0x180009912  mov     edx, 46Fh; void *
0x180009917  mov     rcx, [rsp+288h]; this
0x18000991f  mov     r8, rbp; unsigned int
0x180009922  mov     [rsp+288h+var_260], rbx; char *
0x180009927  mov     r9d, edi; char *
0x18000992a  mov     [rsp+288h+var_268], r15; int
0x18000992f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009934  jmp     short loc_1800098F1
0x180009936  mov     rdx, rsi; struct _GUID *
0x180009939  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000993e  call    ?CreateFolderIfNotPresent@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateFolderIfNotPresent(ushort const *,_GUID const *)
0x180009943  mov     edi, eax
0x180009945  test    eax, eax
0x180009947  jns     short loc_180009950
0x180009949  mov     edx, 471h
0x18000994e  jmp     short loc_180009917
0x180009950  lea     r8, asc_180026BFC; "\\"
0x180009957  mov     rdx, r14; unsigned __int64
0x18000995a  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x18000995f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009964  mov     edi, eax
0x180009966  test    eax, eax
0x180009968  jns     short loc_1800099A2
0x18000996a  mov     edx, 474h; void *
0x18000996f  mov     rcx, [rsp+288h]; this
0x180009977  lea     rax, [rsp+288h+var_248]
0x18000997c  mov     [rsp+288h+var_258], rax
0x180009981  mov     r8, rbp; unsigned int
0x180009984  lea     rax, aNameLsPathLs; "Name %ls path %ls"
0x18000998b  mov     [rsp+288h+var_260], rbx; char *
0x180009990  mov     r9d, edi; char *
0x180009993  mov     [rsp+288h+var_268], rax; int
0x180009998  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000999d  jmp     loc_1800098F1
0x1800099a2  mov     r8, rbx; unsigned __int16 *
0x1800099a5  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800099aa  mov     rdx, r14; unsigned __int64
0x1800099ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800099b2  mov     edi, eax
0x1800099b4  test    eax, eax
0x1800099b6  jns     short loc_1800099BF
0x1800099b8  mov     edx, 477h
0x1800099bd  jmp     short loc_18000996F
0x1800099bf  mov     rdx, rsi; struct _GUID *
0x1800099c2  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x1800099c7  call    ?CreateFolderIfNotPresent@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateFolderIfNotPresent(ushort const *,_GUID const *)
0x1800099cc  mov     ebx, eax
0x1800099ce  test    eax, eax
0x1800099d0  jns     short loc_180009A04
0x1800099d2  mov     rcx, [rsp+288h]; this
0x1800099da  lea     rax, [rsp+288h+var_248]
0x1800099df  mov     [rsp+288h+var_260], rax; char *
0x1800099e4  mov     r9d, ebx; char *
0x1800099e7  lea     rax, aPathLs_0; "Path %ls"
0x1800099ee  mov     r8, rbp; unsigned int
0x1800099f1  mov     edx, 479h; void *
0x1800099f6  mov     [rsp+288h+var_268], rax; int
0x1800099fb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009a00  mov     eax, ebx
0x180009a02  jmp     short loc_180009A06
0x180009a04  xor     eax, eax
0x180009a06  mov     rcx, [rsp+288h+var_38]
0x180009a0e  xor     rcx, rsp; StackCookie
0x180009a11  call    __security_check_cookie
0x180009a16  mov     rbx, [rsp+288h+arg_10]
0x180009a1e  add     rsp, 260h
0x180009a25  pop     r15
0x180009a27  pop     r14
0x180009a29  pop     rdi
0x180009a2a  pop     rsi
0x180009a2b  pop     rbp
0x180009a2c  retn
```
