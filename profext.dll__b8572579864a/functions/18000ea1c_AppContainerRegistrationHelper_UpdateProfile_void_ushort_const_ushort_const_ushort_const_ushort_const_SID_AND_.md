# AppContainerRegistrationHelper::UpdateProfile(void *,ushort const *,ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,void * const,APP_CONTAINER_PROFILE_TYPE,unsigned __int64,_GUID const *,ushort *)

- ea: `0x18000ea1c`
- end: `0x18000edff`
- name: `?UpdateProfile@AppContainerRegistrationHelper@@SAJPEAXPEBG111PEAU_SID_AND_ATTRIBUTES@@KQEAXW4APP_CONTAINER_PROFILE_TYPE@@_KPEBU_GUID@@PEAG@Z`
- size: `995`
- prototype: `static int __high(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _SID_AND_ATTRIBUTES *, unsigned int, void *const, enum APP_CONTAINER_PROFILE_TYPE, unsigned __int64, const struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180003c00`
- `0x1800040c0`
- `0x180004594`
- `0x180005174`
- `0x18000a2f8`
- `0x18000a540`
- `0x18000a7a4`
- `0x18000b984`
- `0x18000c250`
- `0x18000d560`
- `0x18000ea1c`
- `0x18000ee08`
- `0x18000f614`
- `0x180012424`

## import_xrefs

- `KERNELBASE!AppContainerRegisterSid` at `0x18000ea45`
- `KERNELBASE!AppContainerRegisterSid` at `0x18000ea45`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x18000eb65`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x18000eb65`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationCreateAppContainer` at `0x18000ec05`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationCreateAppContainer` at `0x18000ec05`

## string_xrefs

- `0x18000ea80`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000eb7d`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000ec16`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000ec72`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000ece5`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000edd0`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
int __fastcall AppContainerRegistrationHelper::UpdateProfile(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9,
        const unsigned __int16 *a10,
        struct _GUID *a11,
        unsigned __int16 *a12)
{
  unsigned int v15; // ebx
  int v16; // r9d
  unsigned int v18; // eax
  int v19; // ebx
  __int64 v20; // rbx
  const char *AppContainer; // rdi
  unsigned int IsAppContainerAllowedToNotRegisterWithFirewall; // eax
  int v23; // ebx
  int v24; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v26; // [rsp+60h] [rbp+8h] BYREF

  v26 = a1;
  v15 = AppContainerRegisterSid(a8, a2, a3);
  if ( (int)(v15 + 0x80000000) < 0 || v15 == -2147024713 )
  {
    if ( ((a9 - 1) & 0xFFFFFFFD) == 0 )
      return 0;
    if ( (unsigned __int8)IsNetworkIsolationDeleteAppContainerPresent() )
    {
      AppContainerRegistrationHelper::LogSuccess(&AppModelFirewallAppContainerDeletionStart, a2, 0);
      v18 = NetworkIsolationDeleteAppContainer(a8, a4);
      v19 = v18;
      if ( v18 != 2 )
        wil::details::in1diag3::Log_IfWin32ErrorMsg(
          retaddr,
          (void *)0x80B,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v18,
          (unsigned int)"Name %ls display %ls",
          (const char *)a2,
          a4);
      AppContainerRegistrationHelper::LogFailureWithContext(&AppModelFirewallAppContainerDeletionStop, a2, v19, 0);
    }
    if ( !(unsigned __int8)IsNetworkIsolationDeleteAppContainerPresent() )
      return 0;
    AppContainerRegistrationHelper::LogSuccess(&AppModelFirewallAppContainerCreationStart, a2, 0);
    v20 = a5;
    AppContainer = (const char *)(unsigned int)NetworkIsolationCreateAppContainer(a8, a2, a3, a5, a6, a7);
    wil::details::in1diag3::Log_IfWin32ErrorMsg(
      retaddr,
      (void *)0x81A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      AppContainer,
      (unsigned int)"Name %ls, %ls, %ls",
      (const char *)a2,
      a3,
      v20);
    if ( (_DWORD)AppContainer == 1753 )
    {
      LOBYTE(v26) = 0;
      IsAppContainerAllowedToNotRegisterWithFirewall = AppContainerRegistrationHelper::IsAppContainerAllowedToNotRegisterWithFirewall(
                                                         a2,
                                                         (bool *)&v26);
      if ( (int)wil::details::in1diag3::Log_IfFailedMsg(
                  retaddr,
                  (void *)0x820,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                  (const char *)IsAppContainerAllowedToNotRegisterWithFirewall,
                  (__int64)"Name %ls",
                  (const char *)a2) >= 0 )
      {
        if ( (_BYTE)v26 )
        {
          AppContainerRegistrationHelper::LogSuccess(&AppModelFirewallAppContainerCreationSkipped, a2, 0);
          LODWORD(AppContainer) = 0;
        }
      }
    }
    AppContainerRegistrationHelper::LogFailureWithContext(
      &AppModelFirewallAppContainerCreationStop,
      a2,
      (int)AppContainer,
      0);
    if ( !(_DWORD)AppContainer || (_DWORD)AppContainer == 183 )
      return 0;
    if ( (int)AppContainer > 0 )
      LODWORD(AppContainer) = (unsigned __int16)AppContainer | 0x80070000;
    v23 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x82E,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)(unsigned int)AppContainer,
            (__int64)"Name %ls display %ls",
            (const char *)a2,
            a3);
    AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerRegisterFirewallFailure, v23, a11);
    AppContainerRegistrationHelper::SetAPIContextIfFailed(v23, 0x830u, a3, 0x104u, a12);
    if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
    {
      LODWORD(v26) = v23;
      a10 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180031038,
        (unsigned int)byte_18002AE73,
        0,
        0,
        (__int64)&a10,
        (__int64)&v26);
    }
    if ( v23 == 1753 || v23 == 1722 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( v23 == -2147024891 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else if ( v23 >= 0 )
    {
      return v23;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v23,
      v24);
    return v23;
  }
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x7FA,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)v15,
    (__int64)"Name %ls display %ls",
    (const char *)a2,
    a3);
  AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerRegisterSidFailure, v15, 0);
  if ( (unsigned int)dword_180031038 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
    {
      LODWORD(v26) = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180031038,
        (unsigned int)&word_18002AFDE,
        (_DWORD)a11,
        v16,
        (__int64)&v26);
    }
  }
  return AppContainerRegistrationHelper::SetAPIContextIfFailed(v15, 0x7FFu, a3, 0x104u, a12);
}

```

## disassembly

```asm
0x18000ea1c  mov     [rsp+arg_8], rbx
0x18000ea21  mov     [rsp+arg_10], rsi
0x18000ea26  mov     [rsp+arg_0], rcx
0x18000ea2b  push    rdi
0x18000ea2c  push    r14
0x18000ea2e  push    r15
0x18000ea30  sub     rsp, 40h
0x18000ea34  mov     rcx, [rsp+58h+arg_38]
0x18000ea3c  mov     rdi, r9
0x18000ea3f  mov     r14, r8
0x18000ea42  mov     rsi, rdx
0x18000ea45  call    cs:__imp_AppContainerRegisterSid
0x18000ea4c  nop     dword ptr [rax+rax+00h]
0x18000ea51  mov     ebx, eax
0x18000ea53  mov     eax, 80000000h
0x18000ea58  lea     ecx, [rbx+rax]
0x18000ea5b  test    eax, ecx
0x18000ea5d  jnz     loc_18000EB24
0x18000ea63  cmp     ebx, 800700B7h
0x18000ea69  jz      loc_18000EB24
0x18000ea6f  mov     rcx, [rsp+58h]; this
0x18000ea74  lea     r15, aNameLsDisplayL_0; "Name %ls display %ls"
0x18000ea7b  mov     [rsp+58h+var_28], r14
0x18000ea80  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ea87  mov     [rsp+58h+var_30], rsi; char *
0x18000ea8c  mov     r9d, ebx; char *
0x18000ea8f  mov     edx, 7FAh; void *
0x18000ea94  mov     [rsp+58h+var_38], r15; __int64
0x18000ea99  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000ea9e  xor     r8d, r8d; struct _GUID *
0x18000eaa1  lea     rcx, AppModelAppContainerRegisterSidFailure; struct _EVENT_DESCRIPTOR *
0x18000eaa8  mov     edx, ebx; int
0x18000eaaa  call    ?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)
0x18000eaaf  mov     eax, cs:dword_180031038
0x18000eab5  cmp     eax, 5
0x18000eab8  jbe     short loc_18000EAFD
0x18000eaba  mov     rdx, 400000000000h
0x18000eac4  lea     rcx, dword_180031038
0x18000eacb  call    _tlgKeywordOn
0x18000ead0  test    al, al
0x18000ead2  jz      short loc_18000EAFD
0x18000ead4  mov     r8, [rsp+58h+arg_50]
0x18000eadc  lea     rax, [rsp+58h+arg_0]
0x18000eae1  lea     rdx, word_18002AFDE
0x18000eae8  mov     [rsp+58h+var_38], rax
0x18000eaed  lea     rcx, dword_180031038
0x18000eaf4  mov     dword ptr [rsp+58h+arg_0], ebx
0x18000eaf8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000eafd  mov     rax, [rsp+58h+arg_58]
0x18000eb05  mov     r9d, 104h; unsigned __int64
0x18000eb0b  mov     r8, r14; unsigned __int16 *
0x18000eb0e  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x18000eb13  mov     edx, 7FFh; unsigned int
0x18000eb18  mov     ecx, ebx; int
0x18000eb1a  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x18000eb1f  jmp     loc_18000EDEA
0x18000eb24  mov     eax, [rsp+58h+arg_40]
0x18000eb2b  dec     eax
0x18000eb2d  test    eax, 0FFFFFFFDh
0x18000eb32  jz      loc_18000EDE8
0x18000eb38  call    IsNetworkIsolationDeleteAppContainerPresent
0x18000eb3d  lea     r15, aNameLsDisplayL_0; "Name %ls display %ls"
0x18000eb44  test    al, al
0x18000eb46  jz      short loc_18000EBB5
0x18000eb48  xor     r8d, r8d; struct _GUID *
0x18000eb4b  lea     rcx, AppModelFirewallAppContainerDeletionStart; struct _EVENT_DESCRIPTOR *
0x18000eb52  mov     rdx, rsi; unsigned __int16 *
0x18000eb55  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000eb5a  mov     rcx, [rsp+58h+arg_38]
0x18000eb62  mov     rdx, rdi
0x18000eb65  call    cs:__imp_NetworkIsolationDeleteAppContainer
0x18000eb6c  nop     dword ptr [rax+rax+00h]
0x18000eb71  mov     ebx, eax
0x18000eb73  cmp     eax, 2
0x18000eb76  jz      short loc_18000EBA0
0x18000eb78  mov     rcx, [rsp+58h]; this
0x18000eb7d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000eb84  mov     [rsp+58h+var_28], rdi
0x18000eb89  mov     r9d, eax; char *
0x18000eb8c  mov     [rsp+58h+var_30], rsi; char *
0x18000eb91  mov     edx, 80Bh; void *
0x18000eb96  mov     [rsp+58h+var_38], r15; unsigned int
0x18000eb9b  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18000eba0  xor     r9d, r9d; struct _GUID *
0x18000eba3  lea     rcx, AppModelFirewallAppContainerDeletionStop; struct _EVENT_DESCRIPTOR *
0x18000ebaa  mov     r8d, ebx; int
0x18000ebad  mov     rdx, rsi; unsigned __int16 *
0x18000ebb0  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18000ebb5  call    IsNetworkIsolationDeleteAppContainerPresent
0x18000ebba  test    al, al
0x18000ebbc  jz      loc_18000EDE8
0x18000ebc2  xor     r8d, r8d; struct _GUID *
0x18000ebc5  lea     rcx, AppModelFirewallAppContainerCreationStart; struct _EVENT_DESCRIPTOR *
0x18000ebcc  mov     rdx, rsi; unsigned __int16 *
0x18000ebcf  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000ebd4  mov     eax, [rsp+58h+arg_30]
0x18000ebdb  mov     r8, r14
0x18000ebde  mov     rbx, [rsp+58h+arg_20]
0x18000ebe6  mov     rdx, rsi
0x18000ebe9  mov     rcx, [rsp+58h+arg_38]
0x18000ebf1  mov     r9, rbx
0x18000ebf4  mov     dword ptr [rsp+58h+var_30], eax
0x18000ebf8  mov     rax, [rsp+58h+arg_28]
0x18000ec00  mov     [rsp+58h+var_38], rax
0x18000ec05  call    cs:__imp_NetworkIsolationCreateAppContainer
0x18000ec0c  nop     dword ptr [rax+rax+00h]
0x18000ec11  mov     rcx, [rsp+58h]; this
0x18000ec16  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ec1d  mov     edi, eax
0x18000ec1f  mov     [rsp+58h+var_20], rbx
0x18000ec24  lea     rax, aNameLsLsLs; "Name %ls, %ls, %ls"
0x18000ec2b  mov     [rsp+58h+var_28], r14
0x18000ec30  mov     r9d, edi; char *
0x18000ec33  mov     [rsp+58h+var_30], rsi; char *
0x18000ec38  mov     edx, 81Ah; void *
0x18000ec3d  mov     [rsp+58h+var_38], rax; unsigned int
0x18000ec42  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18000ec47  cmp     edi, 6D9h
0x18000ec4d  jnz     short loc_18000ECAA
0x18000ec4f  lea     rdx, [rsp+58h+arg_0]; bool *
0x18000ec54  mov     byte ptr [rsp+58h+arg_0], 0
0x18000ec59  mov     rcx, rsi; lpString2
0x18000ec5c  call    ?IsAppContainerAllowedToNotRegisterWithFirewall@AppContainerRegistrationHelper@@CAJPEBGPEA_N@Z; AppContainerRegistrationHelper::IsAppContainerAllowedToNotRegisterWithFirewall(ushort const *,bool *)
0x18000ec61  mov     rcx, [rsp+58h]; this
0x18000ec66  lea     rdx, aNameLs; "Name %ls"
0x18000ec6d  mov     [rsp+58h+var_30], rsi; char *
0x18000ec72  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ec79  mov     [rsp+58h+var_38], rdx; __int64
0x18000ec7e  mov     r9d, eax; char *
0x18000ec81  mov     edx, 820h; void *
0x18000ec86  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000ec8b  test    eax, eax
0x18000ec8d  js      short loc_18000ECAA
0x18000ec8f  cmp     byte ptr [rsp+58h+arg_0], 0
0x18000ec94  jz      short loc_18000ECAA
0x18000ec96  xor     r8d, r8d; struct _GUID *
0x18000ec99  lea     rcx, AppModelFirewallAppContainerCreationSkipped; struct _EVENT_DESCRIPTOR *
0x18000eca0  mov     rdx, rsi; unsigned __int16 *
0x18000eca3  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000eca8  xor     edi, edi
0x18000ecaa  xor     r9d, r9d; struct _GUID *
0x18000ecad  lea     rcx, AppModelFirewallAppContainerCreationStop; struct _EVENT_DESCRIPTOR *
0x18000ecb4  mov     r8d, edi; int
0x18000ecb7  mov     rdx, rsi; unsigned __int16 *
0x18000ecba  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18000ecbf  test    edi, edi
0x18000ecc1  jz      loc_18000EDE8
0x18000ecc7  cmp     edi, 0B7h
0x18000eccd  jz      loc_18000EDE8
0x18000ecd3  test    edi, edi
0x18000ecd5  jle     short loc_18000ECE0
0x18000ecd7  movzx   edi, di
0x18000ecda  or      edi, 80070000h
0x18000ece0  mov     rcx, [rsp+58h]; this
0x18000ece5  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ecec  mov     [rsp+58h+var_28], r14
0x18000ecf1  mov     r9d, edi; char *
0x18000ecf4  mov     [rsp+58h+var_30], rsi; char *
0x18000ecf9  mov     edx, 82Eh; void *
0x18000ecfe  mov     [rsp+58h+var_38], r15; __int64
0x18000ed03  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000ed08  mov     r8, [rsp+58h+arg_50]; struct _GUID *
0x18000ed10  lea     rcx, AppModelAppContainerRegisterFirewallFailure; struct _EVENT_DESCRIPTOR *
0x18000ed17  mov     edx, eax; int
0x18000ed19  mov     ebx, eax
0x18000ed1b  call    ?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)
0x18000ed20  mov     rcx, [rsp+58h+arg_58]
0x18000ed28  mov     r9d, 104h; unsigned __int64
0x18000ed2e  mov     [rsp+58h+var_38], rcx; unsigned __int16 *
0x18000ed33  mov     r8, r14; unsigned __int16 *
0x18000ed36  mov     ecx, ebx; int
0x18000ed38  mov     edx, 830h; unsigned int
0x18000ed3d  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x18000ed42  mov     ecx, cs:dword_180031038
0x18000ed48  cmp     ecx, 5
0x18000ed4b  jbe     short loc_18000EDA3
0x18000ed4d  mov     rdx, 400000000000h
0x18000ed57  lea     rcx, dword_180031038
0x18000ed5e  call    _tlgKeywordOn
0x18000ed63  test    al, al
0x18000ed65  jz      short loc_18000EDA3
0x18000ed67  lea     rax, [rsp+58h+arg_0]
0x18000ed6c  mov     dword ptr [rsp+58h+arg_0], ebx
0x18000ed70  mov     [rsp+58h+var_30], rax
0x18000ed75  lea     rdx, byte_18002AE73
0x18000ed7c  lea     rax, [rsp+58h+arg_48]
0x18000ed84  mov     [rsp+58h+arg_48], rsi
0x18000ed8c  xor     r9d, r9d
0x18000ed8f  mov     [rsp+58h+var_38], rax; int
0x18000ed94  xor     r8d, r8d
0x18000ed97  lea     rcx, dword_180031038
0x18000ed9e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000eda3  cmp     ebx, 6D9h
0x18000eda9  jz      short loc_18000EDB3
0x18000edab  cmp     ebx, 6BAh
0x18000edb1  jnz     short loc_18000EDB8
0x18000edb3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000edb8  cmp     ebx, 80070005h
0x18000edbe  jnz     short loc_18000EDC7
0x18000edc0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000edc5  jmp     short loc_18000EDCB
0x18000edc7  test    ebx, ebx
0x18000edc9  jns     short loc_18000EDE4
0x18000edcb  mov     rcx, [rsp+58h]; this
0x18000edd0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000edd7  mov     r9d, ebx; char *
0x18000edda  mov     edx, 83Dh; void *
0x18000eddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ede4  mov     eax, ebx
0x18000ede6  jmp     short loc_18000EDEA
0x18000ede8  xor     eax, eax
0x18000edea  mov     rbx, [rsp+58h+arg_8]
0x18000edef  mov     rsi, [rsp+58h+arg_10]
0x18000edf4  add     rsp, 40h
0x18000edf8  pop     r15
0x18000edfa  pop     r14
0x18000edfc  pop     rdi
0x18000edfd  retn
```
