# AppContainerRegistrationHelper::CleanupChildAppContainers(void * const,_GUID const *)

- ea: `0x18000fcb4`
- end: `0x18000fe9e`
- name: `?CleanupChildAppContainers@AppContainerRegistrationHelper@@CAJQEAXPEBU_GUID@@@Z`
- size: `490`
- prototype: `static int(void *const, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800162d0`

## callees

- `0x1800040c0`
- `0x180004594`
- `0x18000a2f8`
- `0x18000fcb4`
- `0x180012424`
- `0x18001b914`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe0c`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000fdfc`
- `KERNELBASE!AppContainerFreeMemory` at `0x18000fdfc`
- `KERNELBASE!AppContainerLookupDisplayNameMrtReference` at `0x18000fd59`
- `KERNELBASE!AppContainerLookupDisplayNameMrtReference` at `0x18000fd59`
- `profapi!__imp_CreateAppContainerEnumerator` at `0x18000fcd3`
- `profapi!__imp_CreateAppContainerEnumerator` at `0x18000fcd3`
- `profapi!__imp_GetNextAppContainerSid` at `0x18000fd14`
- `profapi!__imp_GetNextAppContainerSid` at `0x18000fe20`
- `profapi!__imp_GetNextAppContainerSid` at `0x18000fd14`
- `profapi!__imp_GetNextAppContainerSid` at `0x18000fe20`
- `profapi!__imp_DeleteAppContainerEnumerator` at `0x18000fe5e`
- `profapi!__imp_DeleteAppContainerEnumerator` at `0x18000fe5e`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x18000fd99`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x18000fd99`

## string_xrefs

- `0x18000fce9`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000fd2a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000fd6f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000fdc0`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000fe36`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000fe74`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::CleanupChildAppContainers(void *const a1, const struct _GUID *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int NextAppContainerSid; // eax
  int v7; // ebx
  int v8; // eax
  int v9; // edi
  signed int v10; // eax
  int v11; // eax
  int v12; // eax
  unsigned int v13; // edi
  int v14; // [rsp+20h] [rbp-20h]
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HLOCAL hMem; // [rsp+70h] [rbp+30h] BYREF
  char *v18; // [rsp+78h] [rbp+38h] BYREF

  v15 = 0;
  v3 = CreateAppContainerEnumerator(a1, &v15);
  v4 = v3;
  if ( v3 >= 0 )
  {
    hMem = 0;
    NextAppContainerSid = GetNextAppContainerSid(v15, &hMem);
    v7 = NextAppContainerSid;
    if ( NextAppContainerSid >= 0 )
    {
      if ( !NextAppContainerSid )
      {
        while ( 1 )
        {
          v18 = 0;
          v8 = AppContainerLookupDisplayNameMrtReference(hMem, &v18);
          v9 = v8;
          if ( v8 >= 0 )
          {
            if ( (unsigned __int8)IsNetworkIsolationDeleteAppContainerPresent() )
            {
              v10 = NetworkIsolationDeleteAppContainer(hMem, v18);
              if ( (v10 & 0xFFFFFFFD) != 0 )
              {
                if ( v10 > 0 )
                  v10 = (unsigned __int16)v10 | 0x80070000;
                v9 = wil::details::in1diag3::Log_IfFailedMsg(
                       retaddr,
                       (void *)0x449,
                       (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                       (const char *)(unsigned int)v10,
                       (__int64)"RAC %ls",
                       v18);
                AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerUnregisterFirewallFailure, v9, a2);
              }
            }
            AppContainerFreeMemory(v18);
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x437,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)(unsigned int)v8,
              v14);
          }
          LocalFree(hMem);
          v11 = GetNextAppContainerSid(v15, &hMem);
          v7 = v11;
          if ( v11 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x454,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)(unsigned int)v11,
              v14);
          if ( v9 < 0 )
            break;
          if ( v7 )
            goto LABEL_20;
        }
        v7 = v9;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x430,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)NextAppContainerSid,
        v14);
    }
LABEL_20:
    v12 = DeleteAppContainerEnumerator(v15);
    v13 = v12;
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x459,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)(unsigned int)v12,
        v14);
    if ( v7 < 0 )
      return (unsigned int)v7;
    return v13;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v3,
      v14);
    return v4;
  }
}

```

## disassembly

```asm
0x18000fcb4  mov     [rsp-18h+arg_0], rbx
0x18000fcb9  push    rbp
0x18000fcba  push    rdi
0x18000fcbb  push    r14
0x18000fcbd  mov     rbp, rsp
0x18000fcc0  sub     rsp, 40h
0x18000fcc4  mov     r14, rdx
0x18000fcc7  mov     [rbp+var_10], 0
0x18000fccf  lea     rdx, [rbp+var_10]
0x18000fcd3  call    cs:__imp_CreateAppContainerEnumerator
0x18000fcda  nop     dword ptr [rax+rax+00h]
0x18000fcdf  mov     ebx, eax
0x18000fce1  test    eax, eax
0x18000fce3  jns     short loc_18000FD04
0x18000fce5  mov     rcx, [rbp+18h]; this
0x18000fce9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000fcf0  mov     r9d, eax; char *
0x18000fcf3  mov     edx, 42Dh; void *
0x18000fcf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fcfd  mov     eax, ebx
0x18000fcff  jmp     loc_18000FE8F
0x18000fd04  mov     rcx, [rbp+var_10]
0x18000fd08  lea     rdx, [rbp+hMem]
0x18000fd0c  mov     [rbp+hMem], 0
0x18000fd14  call    cs:__imp_GetNextAppContainerSid
0x18000fd1b  nop     dword ptr [rax+rax+00h]
0x18000fd20  mov     ebx, eax
0x18000fd22  test    eax, eax
0x18000fd24  jns     short loc_18000FD43
0x18000fd26  mov     rcx, [rbp+18h]; this
0x18000fd2a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000fd31  mov     r9d, eax; char *
0x18000fd34  mov     edx, 430h; void *
0x18000fd39  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fd3e  jmp     loc_18000FE5A
0x18000fd43  jnz     loc_18000FE5A
0x18000fd49  mov     rcx, [rbp+hMem]
0x18000fd4d  lea     rdx, [rbp+arg_18]
0x18000fd51  mov     [rbp+arg_18], 0
0x18000fd59  call    cs:__imp_AppContainerLookupDisplayNameMrtReference
0x18000fd60  nop     dword ptr [rax+rax+00h]
0x18000fd65  mov     edi, eax
0x18000fd67  test    eax, eax
0x18000fd69  jns     short loc_18000FD88
0x18000fd6b  mov     rcx, [rbp+18h]; this
0x18000fd6f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000fd76  mov     r9d, eax; char *
0x18000fd79  mov     edx, 437h; void *
0x18000fd7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fd83  jmp     loc_18000FE08
0x18000fd88  call    IsNetworkIsolationDeleteAppContainerPresent
0x18000fd8d  test    al, al
0x18000fd8f  jz      short loc_18000FDF8
0x18000fd91  mov     rdx, [rbp+arg_18]
0x18000fd95  mov     rcx, [rbp+hMem]
0x18000fd99  call    cs:__imp_NetworkIsolationDeleteAppContainer
0x18000fda0  nop     dword ptr [rax+rax+00h]
0x18000fda5  test    eax, 0FFFFFFFDh
0x18000fdaa  jz      short loc_18000FDF8
0x18000fdac  mov     rdx, [rbp+arg_18]
0x18000fdb0  test    eax, eax
0x18000fdb2  jle     short loc_18000FDBC
0x18000fdb4  movzx   eax, ax
0x18000fdb7  or      eax, 80070000h
0x18000fdbc  mov     rcx, [rbp+18h]; this
0x18000fdc0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000fdc7  mov     [rsp+40h+var_18], rdx; char *
0x18000fdcc  mov     r9d, eax; char *
0x18000fdcf  lea     rdx, aRacLs; "RAC %ls"
0x18000fdd6  mov     [rsp+40h+var_20], rdx; int
0x18000fddb  mov     edx, 449h; void *
0x18000fde0  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000fde5  mov     r8, r14; struct _GUID *
0x18000fde8  lea     rcx, AppModelAppContainerUnregisterFirewallFailure; struct _EVENT_DESCRIPTOR *
0x18000fdef  mov     edx, eax; int
0x18000fdf1  mov     edi, eax
0x18000fdf3  call    ?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)
0x18000fdf8  mov     rcx, [rbp+arg_18]
0x18000fdfc  call    cs:__imp_AppContainerFreeMemory
0x18000fe03  nop     dword ptr [rax+rax+00h]
0x18000fe08  mov     rcx, [rbp+hMem]; hMem
0x18000fe0c  call    cs:__imp_LocalFree
0x18000fe13  nop     dword ptr [rax+rax+00h]
0x18000fe18  mov     rcx, [rbp+var_10]
0x18000fe1c  lea     rdx, [rbp+hMem]
0x18000fe20  call    cs:__imp_GetNextAppContainerSid
0x18000fe27  nop     dword ptr [rax+rax+00h]
0x18000fe2c  mov     ebx, eax
0x18000fe2e  test    eax, eax
0x18000fe30  jns     short loc_18000FE4A
0x18000fe32  mov     rcx, [rbp+18h]; this
0x18000fe36  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000fe3d  mov     r9d, eax; char *
0x18000fe40  mov     edx, 454h; void *
0x18000fe45  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fe4a  test    edi, edi
0x18000fe4c  js      short loc_18000FE58
0x18000fe4e  test    ebx, ebx
0x18000fe50  jz      loc_18000FD49
0x18000fe56  jmp     short loc_18000FE5A
0x18000fe58  mov     ebx, edi
0x18000fe5a  mov     rcx, [rbp+var_10]
0x18000fe5e  call    cs:__imp_DeleteAppContainerEnumerator
0x18000fe65  nop     dword ptr [rax+rax+00h]
0x18000fe6a  mov     edi, eax
0x18000fe6c  test    eax, eax
0x18000fe6e  jns     short loc_18000FE88
0x18000fe70  mov     rcx, [rbp+18h]; this
0x18000fe74  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000fe7b  mov     r9d, eax; char *
0x18000fe7e  mov     edx, 459h; void *
0x18000fe83  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fe88  test    ebx, ebx
0x18000fe8a  cmovs   edi, ebx
0x18000fe8d  mov     eax, edi
0x18000fe8f  mov     rbx, [rsp+40h+arg_0]
0x18000fe94  add     rsp, 40h
0x18000fe98  pop     r14
0x18000fe9a  pop     rdi
0x18000fe9b  pop     rbp
0x18000fe9c  retn
```
