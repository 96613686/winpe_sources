# AppContainerRegistrationHelper::DeleteRegistryStorage(void *,ushort const *,ushort const *,_GUID const *)

- ea: `0x180016554`
- end: `0x18001663e`
- name: `?DeleteRegistryStorage@AppContainerRegistrationHelper@@CAJPEAXPEBG1PEBU_GUID@@@Z`
- size: `234`
- prototype: `static int(void *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009504`
- `0x180016644`

## callees

- `0x180003d30`
- `0x1800040c0`
- `0x1800044e0`
- `0x180008044`
- `0x18000a540`
- `0x180016554`
- `0x180022830`

## string_xrefs

- `0x18001659f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800165e8`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180016593`: `Name %ls Sid %ls`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::DeleteRegistryStorage(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4)
{
  HKEY v7; // rcx
  int v8; // ebx
  unsigned int v9; // eax
  char v11[2]; // [rsp+40h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+0h]

  v8 = AppContainerRegistrationHelper::DeriveTopLevelRegistryKey(a1, a2, a3, (unsigned __int16 *)v11);
  if ( v8 >= 0 )
  {
    v9 = RemoveRegistryTree(v7, (WCHAR *)v11);
    v8 = v9;
    if ( v9 && v9 != -2147024894 )
    {
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x39E,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v9,
        (__int64)"Subkey %ls",
        v11);
      AppContainerRegistrationHelper::LogFailureWithContext(
        &AppModelAppContainerDeleteRegistryKeyFailure,
        (unsigned __int16 *)v11,
        v8,
        a4);
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x398,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v8,
      (int)"Name %ls Sid %ls",
      (const char *)a2,
      a3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016554  push    rbx
0x180016556  push    rbp
0x180016557  push    rsi
0x180016558  push    rdi
0x180016559  sub     rsp, 468h
0x180016560  mov     rax, cs:__security_cookie
0x180016567  xor     rax, rsp
0x18001656a  mov     [rsp+488h+var_38], rax
0x180016572  mov     rbp, r9
0x180016575  mov     rsi, r8
0x180016578  lea     r9, [rsp+488h+var_448]; unsigned __int16 *
0x18001657d  mov     rdi, rdx
0x180016580  call    ?DeriveTopLevelRegistryKey@AppContainerRegistrationHelper@@CAJPEAXPEBG1PEAG_K@Z; AppContainerRegistrationHelper::DeriveTopLevelRegistryKey(void *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x180016585  mov     ebx, eax
0x180016587  test    eax, eax
0x180016589  jns     short loc_1800165BF
0x18001658b  mov     rcx, [rsp+488h]; this
0x180016593  lea     rax, aNameLsSidLs; "Name %ls Sid %ls"
0x18001659a  mov     [rsp+488h+var_458], rsi
0x18001659f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800165a6  mov     [rsp+488h+var_460], rdi; char *
0x1800165ab  mov     r9d, ebx; char *
0x1800165ae  mov     edx, 398h; void *
0x1800165b3  mov     [rsp+488h+var_468], rax; int
0x1800165b8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800165bd  jmp     short loc_18001661F
0x1800165bf  lea     rdx, [rsp+488h+var_448]; unsigned __int16 *
0x1800165c4  call    ?RemoveRegistryTree@@YAJPEAUHKEY__@@PEBG@Z; RemoveRegistryTree(HKEY__ *,ushort const *)
0x1800165c9  mov     ebx, eax
0x1800165cb  test    eax, eax
0x1800165cd  jz      short loc_18001661F
0x1800165cf  cmp     eax, 80070002h
0x1800165d4  jz      short loc_18001661F
0x1800165d6  mov     rcx, [rsp+488h]; this
0x1800165de  lea     rax, [rsp+488h+var_448]
0x1800165e3  mov     [rsp+488h+var_460], rax; char *
0x1800165e8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800165ef  lea     rax, aSubkeyLs; "Subkey %ls"
0x1800165f6  mov     r9d, ebx; char *
0x1800165f9  mov     edx, 39Eh; void *
0x1800165fe  mov     [rsp+488h+var_468], rax; __int64
0x180016603  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180016608  mov     r9, rbp; struct _GUID *
0x18001660b  lea     rdx, [rsp+488h+var_448]; unsigned __int16 *
0x180016610  mov     r8d, ebx; int
0x180016613  lea     rcx, AppModelAppContainerDeleteRegistryKeyFailure; struct _EVENT_DESCRIPTOR *
0x18001661a  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18001661f  mov     eax, ebx
0x180016621  mov     rcx, [rsp+488h+var_38]
0x180016629  xor     rcx, rsp; StackCookie
0x18001662c  call    __security_check_cookie
0x180016631  add     rsp, 468h
0x180016638  pop     rdi
0x180016639  pop     rsi
0x18001663a  pop     rbp
0x18001663b  pop     rbx
0x18001663c  retn
```
