# AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)

- ea: `0x180015fe0`
- end: `0x1800162c9`
- name: `?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(__int64, const char *, int, const struct _GUID *)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009504`
- `0x18000c8f4`
- `0x180014d5c`
- `0x180016644`

## callees

- `0x180002030`
- `0x1800040c0`
- `0x1800041ec`
- `0x1800044e0`
- `0x1800045bc`
- `0x180006938`
- `0x18000a2f8`
- `0x18000a540`
- `0x18000f214`
- `0x180015fe0`
- `0x180022830`

## string_xrefs

- `0x18001602f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18001626a`: `Name %ls path %ls`
- `0x1800160d8`: `INetCache`
- `0x1800160f6`: `Name %ls path %ls dir %ls`
- `0x18001614d`: `Name %ls path %ls dir %ls`
- `0x180016192`: `Name %ls path %ls dir %ls`
- `0x1800161df`: `Name %ls path %ls dir %ls`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::DeleteAppContainerRootFolder(
        __int64 a1,
        const char *a2,
        int a3,
        const struct _GUID *a4)
{
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // r14d
  int v14; // edi
  int v15; // eax
  unsigned int v16; // r14d
  bool v17; // al
  int v18; // [rsp+20h] [rbp-E0h]
  char v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v8 = AppContainerRegistrationHelper::DeriveTopLevelFolderPath(a1, a2, v19);
  v9 = wil::details::in1diag3::Log_IfFailedMsg(
         retaddr,
         (void *)0x48E,
         (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
         (const char *)v8,
         (__int64)"Name %ls",
         a2);
  v10 = v9;
  if ( v9 < 0 )
  {
    AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerGetAppDataFolderFailure, v9, a4);
    return v10;
  }
  if ( ((a3 - 1) & 0xFFFFFFFD) == 0 && !a1 )
  {
    v11 = StringCchCatW((unsigned __int16 *)v19, 0x104u, L"\\AC");
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4A1,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v11,
        (int)"Name %ls",
        a2);
      return v12;
    }
  }
  if ( a3 == 2 )
  {
    v12 = AppContainerRegistrationHelper::RemoveSubDirectoryTree(v19, L"INetCache", a4);
    if ( (v12 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4A8,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v12,
        (int)"Name %ls path %ls dir %ls",
        a2,
        v19,
        L"INetCache");
      return v12;
    }
    v12 = AppContainerRegistrationHelper::RemoveSubDirectoryTree(v19, L"INetHistory", a4);
    if ( (v12 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4AB,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v12,
        (int)"Name %ls path %ls dir %ls",
        a2,
        v19,
        L"INetHistory");
      return v12;
    }
    v12 = AppContainerRegistrationHelper::RemoveSubDirectoryTree(v19, L"INetCookies", a4);
    if ( (v12 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4AE,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v12,
        (int)"Name %ls path %ls dir %ls",
        a2,
        v19,
        L"INetCookies");
      return v12;
    }
    v14 = AppContainerRegistrationHelper::RemoveSubDirectoryTree(v19, L"Temp", a4);
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4B1,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v14,
        (int)"Name %ls path %ls dir %ls",
        a2,
        v19,
        L"Temp");
      return (unsigned int)v14;
    }
  }
  else
  {
    v15 = RemoveDirectoryTree((unsigned __int16 *)v19);
    if ( v15 )
    {
      if ( v15 > 0 )
      {
        v10 = (unsigned __int16)v15 | 0x80070000;
        if ( v15 == 2 || v15 == 3 )
          return v10;
        v16 = (unsigned __int16)v15 | 0x80070000;
      }
      else
      {
        v16 = v15;
        v10 = v15;
      }
      v17 = v16 != -2147024891 && v15 != 32;
      LOBYTE(v18) = v17;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x4BC,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v16,
        v18,
        (bool)"Name %ls path %ls",
        a2,
        v19);
      AppContainerRegistrationHelper::LogFailureWithContext(
        &AppModelAppContainerDeleteFolderFailure,
        (const unsigned __int16 *)v19,
        v16,
        a4);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180015fe0  push    rbp
0x180015fe2  push    rbx
0x180015fe3  push    rsi
0x180015fe4  push    rdi
0x180015fe5  push    r12
0x180015fe7  push    r13
0x180015fe9  push    r14
0x180015feb  push    r15
0x180015fed  lea     rbp, [rsp-168h]
0x180015ff5  sub     rsp, 268h
0x180015ffc  mov     rax, cs:__security_cookie
0x180016003  xor     rax, rsp
0x180016006  mov     [rbp+1A0h+var_50], rax
0x18001600d  mov     r15d, r8d
0x180016010  mov     dword ptr [rsp+2A0h+var_280], r8d
0x180016015  lea     r8, [rsp+2A0h+var_260]
0x18001601a  mov     rdi, r9
0x18001601d  mov     rsi, rdx
0x180016020  mov     r14, rcx
0x180016023  call    ?DeriveTopLevelFolderPath@AppContainerRegistrationHelper@@CAJPEAXPEBGPEAG_KW4APP_CONTAINER_PROFILE_TYPE@@@Z; AppContainerRegistrationHelper::DeriveTopLevelFolderPath(void *,ushort const *,ushort *,unsigned __int64,APP_CONTAINER_PROFILE_TYPE)
0x180016028  mov     rcx, [rbp+1A8h]; this
0x18001602f  lea     r12, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016036  lea     r13, aNameLs; "Name %ls"
0x18001603d  mov     [rsp+2A0h+var_278], rsi; char *
0x180016042  mov     r8, r12; unsigned int
0x180016045  mov     [rsp+2A0h+var_280], r13; __int64
0x18001604a  mov     r9d, eax; char *
0x18001604d  mov     edx, 48Eh; void *
0x180016052  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180016057  mov     ebx, eax
0x180016059  test    eax, eax
0x18001605b  jns     short loc_180016073
0x18001605d  mov     r8, rdi; struct _GUID *
0x180016060  lea     rcx, AppModelAppContainerGetAppDataFolderFailure; struct _EVENT_DESCRIPTOR *
0x180016067  mov     edx, eax; int
0x180016069  call    ?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)
0x18001606e  jmp     loc_1800162A3
0x180016073  lea     eax, [r15-1]
0x180016077  test    eax, 0FFFFFFFDh
0x18001607c  jnz     short loc_1800160C9
0x18001607e  test    r14, r14
0x180016081  jnz     short loc_1800160C9
0x180016083  lea     r8, aAc; "\\AC"
0x18001608a  mov     edx, 104h; unsigned __int64
0x18001608f  lea     rcx, [rsp+2A0h+var_260]; unsigned __int16 *
0x180016094  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016099  mov     r14d, eax
0x18001609c  test    eax, eax
0x18001609e  jns     short loc_1800160C9
0x1800160a0  mov     rcx, [rbp+1A8h]; this
0x1800160a7  mov     r9d, eax; char *
0x1800160aa  mov     [rsp+2A0h+var_278], rsi; char *
0x1800160af  mov     r8, r12; unsigned int
0x1800160b2  mov     edx, 4A1h; void *
0x1800160b7  mov     [rsp+2A0h+var_280], r13; int
0x1800160bc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800160c1  mov     eax, r14d
0x1800160c4  jmp     loc_1800162A5
0x1800160c9  lea     rcx, [rsp+2A0h+var_260]; unsigned __int16 *
0x1800160ce  cmp     r15d, 2
0x1800160d2  jnz     loc_180016216
0x1800160d8  lea     r15, aInetcache; "INetCache"
0x1800160df  mov     r8, rdi; struct _GUID *
0x1800160e2  mov     rdx, r15; unsigned __int16 *
0x1800160e5  call    ?RemoveSubDirectoryTree@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@@Z; AppContainerRegistrationHelper::RemoveSubDirectoryTree(ushort const *,ushort const *,_GUID const *)
0x1800160ea  mov     r14d, eax
0x1800160ed  test    eax, eax
0x1800160ef  jns     short loc_18001612A
0x1800160f1  mov     [rsp+2A0h+var_268], r15
0x1800160f6  lea     rdx, aNameLsPathLsDi_0; "Name %ls path %ls dir %ls"
0x1800160fd  lea     rax, [rsp+2A0h+var_260]
0x180016102  mov     [rsp+2A0h+var_270], rax
0x180016107  mov     [rsp+2A0h+var_278], rsi; char *
0x18001610c  mov     [rsp+2A0h+var_280], rdx; int
0x180016111  mov     edx, 4A8h; void *
0x180016116  mov     rcx, [rbp+1A8h]; this
0x18001611d  mov     r9d, r14d; char *
0x180016120  mov     r8, r12; unsigned int
0x180016123  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180016128  jmp     short loc_1800160C1
0x18001612a  lea     r15, aInethistory; "INetHistory"
0x180016131  mov     r8, rdi; struct _GUID *
0x180016134  mov     rdx, r15; unsigned __int16 *
0x180016137  lea     rcx, [rsp+2A0h+var_260]; char *
0x18001613c  call    ?RemoveSubDirectoryTree@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@@Z; AppContainerRegistrationHelper::RemoveSubDirectoryTree(ushort const *,ushort const *,_GUID const *)
0x180016141  mov     r14d, eax
0x180016144  test    eax, eax
0x180016146  jns     short loc_18001616F
0x180016148  mov     [rsp+2A0h+var_268], r15
0x18001614d  lea     rdx, aNameLsPathLsDi_0; "Name %ls path %ls dir %ls"
0x180016154  lea     rax, [rsp+2A0h+var_260]
0x180016159  mov     [rsp+2A0h+var_270], rax
0x18001615e  mov     [rsp+2A0h+var_278], rsi
0x180016163  mov     [rsp+2A0h+var_280], rdx
0x180016168  mov     edx, 4ABh
0x18001616d  jmp     short loc_180016116
0x18001616f  lea     r15, aInetcookies; "INetCookies"
0x180016176  mov     r8, rdi; struct _GUID *
0x180016179  mov     rdx, r15; unsigned __int16 *
0x18001617c  lea     rcx, [rsp+2A0h+var_260]; char *
0x180016181  call    ?RemoveSubDirectoryTree@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@@Z; AppContainerRegistrationHelper::RemoveSubDirectoryTree(ushort const *,ushort const *,_GUID const *)
0x180016186  mov     r14d, eax
0x180016189  test    eax, eax
0x18001618b  jns     short loc_1800161B7
0x18001618d  mov     [rsp+2A0h+var_268], r15
0x180016192  lea     rdx, aNameLsPathLsDi_0; "Name %ls path %ls dir %ls"
0x180016199  lea     rax, [rsp+2A0h+var_260]
0x18001619e  mov     [rsp+2A0h+var_270], rax
0x1800161a3  mov     [rsp+2A0h+var_278], rsi
0x1800161a8  mov     [rsp+2A0h+var_280], rdx
0x1800161ad  mov     edx, 4AEh
0x1800161b2  jmp     loc_180016116
0x1800161b7  lea     r14, aTemp; "Temp"
0x1800161be  mov     r8, rdi; struct _GUID *
0x1800161c1  mov     rdx, r14; unsigned __int16 *
0x1800161c4  lea     rcx, [rsp+2A0h+var_260]; char *
0x1800161c9  call    ?RemoveSubDirectoryTree@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@@Z; AppContainerRegistrationHelper::RemoveSubDirectoryTree(ushort const *,ushort const *,_GUID const *)
0x1800161ce  mov     edi, eax
0x1800161d0  test    eax, eax
0x1800161d2  jns     loc_1800162A3
0x1800161d8  mov     rcx, [rbp+1A8h]; this
0x1800161df  lea     rdx, aNameLsPathLsDi_0; "Name %ls path %ls dir %ls"
0x1800161e6  mov     [rsp+2A0h+var_268], r14
0x1800161eb  lea     rax, [rsp+2A0h+var_260]
0x1800161f0  mov     [rsp+2A0h+var_270], rax
0x1800161f5  mov     r9d, edi; char *
0x1800161f8  mov     [rsp+2A0h+var_278], rsi; char *
0x1800161fd  mov     r8, r12; unsigned int
0x180016200  mov     [rsp+2A0h+var_280], rdx; int
0x180016205  mov     edx, 4B1h; void *
0x18001620a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001620f  mov     eax, edi
0x180016211  jmp     loc_1800162A5
0x180016216  call    RemoveDirectoryTree
0x18001621b  test    eax, eax
0x18001621d  jz      loc_1800162A3
0x180016223  jg      short loc_18001622C
0x180016225  mov     r14d, eax
0x180016228  mov     ebx, eax
0x18001622a  jmp     short loc_180016242
0x18001622c  movzx   ebx, ax
0x18001622f  or      ebx, 80070000h
0x180016235  cmp     eax, 2
0x180016238  jz      short loc_1800162A3
0x18001623a  cmp     eax, 3
0x18001623d  jz      short loc_1800162A3
0x18001623f  mov     r14d, ebx
0x180016242  cmp     r14d, 80070005h
0x180016249  jz      short loc_180016254
0x18001624b  cmp     eax, 20h ; ' '
0x18001624e  jz      short loc_180016254
0x180016250  mov     al, 1
0x180016252  jmp     short loc_180016256
0x180016254  xor     eax, eax
0x180016256  mov     rcx, [rbp+1A8h]; this
0x18001625d  lea     rdx, [rsp+2A0h+var_260]
0x180016262  mov     [rsp+2A0h+var_268], rdx
0x180016267  mov     r9d, r14d; char *
0x18001626a  lea     rdx, aNameLsPathLs; "Name %ls path %ls"
0x180016271  mov     [rsp+2A0h+var_270], rsi; char *
0x180016276  mov     [rsp+2A0h+var_278], rdx; bool
0x18001627b  mov     r8, r12; unsigned int
0x18001627e  mov     edx, 4BCh; void *
0x180016283  mov     byte ptr [rsp+2A0h+var_280], al; int
0x180016287  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001628c  mov     r9, rdi; struct _GUID *
0x18001628f  lea     rdx, [rsp+2A0h+var_260]; unsigned __int16 *
0x180016294  mov     r8d, r14d; int
0x180016297  lea     rcx, AppModelAppContainerDeleteFolderFailure; struct _EVENT_DESCRIPTOR *
0x18001629e  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x1800162a3  mov     eax, ebx
0x1800162a5  mov     rcx, [rbp+1A0h+var_50]
0x1800162ac  xor     rcx, rsp; StackCookie
0x1800162af  call    __security_check_cookie
0x1800162b4  add     rsp, 268h
0x1800162bb  pop     r15
0x1800162bd  pop     r14
0x1800162bf  pop     r13
0x1800162c1  pop     r12
0x1800162c3  pop     rdi
0x1800162c4  pop     rsi
0x1800162c5  pop     rbx
0x1800162c6  pop     rbp
0x1800162c7  retn
```
