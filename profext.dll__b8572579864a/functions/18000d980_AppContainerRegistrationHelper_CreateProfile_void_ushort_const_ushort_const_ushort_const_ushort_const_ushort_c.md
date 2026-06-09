# AppContainerRegistrationHelper::CreateProfile(void *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,void *,APP_CONTAINER_PROFILE_TYPE,unsigned __int64,_GUID const *,ushort *)

- ea: `0x18000d980`
- end: `0x18000e264`
- name: `?CreateProfile@AppContainerRegistrationHelper@@SAJPEAXPEBG1111PEAU_SID_AND_ATTRIBUTES@@K0W4APP_CONTAINER_PROFILE_TYPE@@_KPEBU_GUID@@PEAG@Z`
- size: `2276`
- prototype: `static int __high(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _SID_AND_ATTRIBUTES *, unsigned int, void *, enum APP_CONTAINER_PROFILE_TYPE, unsigned __int64, const struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a80`

## callees

- `0x180003c00`
- `0x1800040c0`
- `0x1800044e0`
- `0x180004594`
- `0x180005174`
- `0x180009504`
- `0x180009a34`
- `0x18000a2f8`
- `0x18000a540`
- `0x18000a7a4`
- `0x18000b984`
- `0x18000c250`
- `0x18000d560`
- `0x18000d980`
- `0x18000ee08`
- `0x18000f614`
- `0x180012424`
- `0x1800162d0`

## import_xrefs

- `KERNELBASE!AppContainerUnregisterSid` at `0x18000dfea`
- `KERNELBASE!AppContainerUnregisterSid` at `0x18000e15c`
- `KERNELBASE!AppContainerUnregisterSid` at `0x18000dfea`
- `KERNELBASE!AppContainerUnregisterSid` at `0x18000e15c`
- `KERNELBASE!AppContainerRegisterSid` at `0x18000dcad`
- `KERNELBASE!AppContainerRegisterSid` at `0x18000dde0`
- `KERNELBASE!AppContainerRegisterSid` at `0x18000dcad`
- `KERNELBASE!AppContainerRegisterSid` at `0x18000dde0`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x18000da88`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x18000e1ad`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x18000da88`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationDeleteAppContainer` at `0x18000e1ad`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationCreateAppContainer` at `0x18000db1e`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationCreateAppContainer` at `0x18000df18`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationCreateAppContainer` at `0x18000db1e`
- `ext-ms-win-net-isoext-l1-1-0!NetworkIsolationCreateAppContainer` at `0x18000df18`

## string_xrefs

- `0x18000da17`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000da51`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000ddfc`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000dab3`: `Name %ls Sid %ls type %d`
- `0x18000da0b`: `Name %ls display %ls Sid %ls type %d`
- `0x18000e226`: `Name %ws Sid %ws type %d`

## pseudocode

```c
__int64 AppContainerRegistrationHelper::CreateProfile(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        ...)
{
  unsigned int v7; // r13d
  void *v8; // r15
  unsigned int StorageLocations; // esi
  __int64 result; // rax
  const char *v11; // rbx
  unsigned int AppContainer; // eax
  int v13; // ebx
  unsigned int IsAppContainerAllowedToNotRegisterWithFirewall; // eax
  int v15; // ebx
  int v16; // r9d
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // ebx
  int v20; // r9d
  __int64 v21; // rdx
  unsigned int v22; // eax
  signed int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  const char *v27; // rbx
  int v28; // [rsp+20h] [rbp-30h]
  __int64 v29; // [rsp+38h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  __int64 v33; // [rsp+B8h] [rbp+68h] BYREF
  va_list va; // [rsp+B8h] [rbp+68h]
  __int64 v35; // [rsp+C0h] [rbp+70h]
  __int64 v36; // [rsp+C8h] [rbp+78h]
  void *v37; // [rsp+D0h] [rbp+80h]
  __int64 v38; // [rsp+D8h] [rbp+88h]
  const unsigned __int16 *v39; // [rsp+E0h] [rbp+90h] BYREF
  va_list va1; // [rsp+E0h] [rbp+90h]
  struct _GUID *v41; // [rsp+E8h] [rbp+98h]
  unsigned __int16 *v42; // [rsp+F0h] [rbp+A0h]
  va_list va2; // [rsp+F8h] [rbp+A8h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v33 = va_arg(va1, _QWORD);
  v35 = va_arg(va1, _QWORD);
  v36 = va_arg(va1, _QWORD);
  v37 = va_arg(va1, void *);
  v38 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v39 = va_arg(va2, const unsigned __int16 *);
  v41 = va_arg(va2, struct _GUID *);
  v42 = va_arg(va2, unsigned __int16 *);
  v7 = v38;
  v8 = v37;
  StorageLocations = AppContainerRegistrationHelper::EnsureExistingState(a1, a2, a3, a5, v37, v38, v41);
  if ( (StorageLocations & 0x80000000) != 0 )
  {
    AppContainerRegistrationHelper::SetAPIContextIfFailed(StorageLocations, 0x6EFu, a5, 0x208u, v42);
    if ( StorageLocations == -2147024713 )
    {
      if ( ((v7 - 1) & 0xFFFFFFFD) != 0 )
      {
        if ( (unsigned __int8)IsNetworkIsolationDeleteAppContainerPresent() )
        {
          AppContainerRegistrationHelper::LogSuccess(&AppModelFirewallAppContainerDeletionStart, a2, 0);
          v11 = (const char *)(unsigned int)NetworkIsolationDeleteAppContainer(v37, a3);
          wil::details::in1diag3::Log_IfWin32ErrorMsg(
            retaddr,
            (void *)0x6FE,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            v11,
            (unsigned int)"Name %ls Sid %ls type %d",
            (const char *)a2,
            a5,
            v7);
          AppContainerRegistrationHelper::LogFailureWithContext(
            &AppModelFirewallAppContainerDeletionStop,
            a2,
            (int)v11,
            0);
        }
        if ( (unsigned __int8)IsNetworkIsolationDeleteAppContainerPresent() )
        {
          AppContainerRegistrationHelper::LogSuccess(&AppModelFirewallAppContainerCreationStart, a2, 0);
          AppContainer = NetworkIsolationCreateAppContainer(v37, a2, a3, a4, v35, v36);
          v13 = AppContainer;
          if ( AppContainer == 1753 || AppContainer == 1722 )
          {
            LOBYTE(v33) = 0;
            IsAppContainerAllowedToNotRegisterWithFirewall = AppContainerRegistrationHelper::IsAppContainerAllowedToNotRegisterWithFirewall(
                                                               a2,
                                                               (bool *)va);
            if ( (int)wil::details::in1diag3::Log_IfFailedMsg(
                        retaddr,
                        (void *)0x717,
                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                        (const char *)IsAppContainerAllowedToNotRegisterWithFirewall,
                        (__int64)"Name %ls",
                        (const char *)a2) >= 0
              && (_BYTE)v33 )
            {
              AppContainerRegistrationHelper::LogSuccess(&AppModelFirewallAppContainerCreationSkipped, a2, 0);
              v13 = 183;
            }
          }
          else
          {
            wil::details::in1diag3::Log_IfWin32ErrorMsg(
              retaddr,
              (void *)0x723,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)AppContainer,
              (unsigned int)"Name %ls, %ls, %ls",
              (const char *)a2,
              a3,
              a4);
          }
          AppContainerRegistrationHelper::LogFailureWithContext(&AppModelFirewallAppContainerCreationStop, a2, v13, 0);
          if ( v13 )
          {
            if ( v13 > 0 )
              StorageLocations = (unsigned __int16)v13 | 0x80070000;
            else
              StorageLocations = v13;
            AppContainerRegistrationHelper::SetAPIContextIfFailed(StorageLocations, 0x730u, a2, 0x208u, v42);
            if ( v13 != 183 )
            {
              wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x736,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                (const char *)StorageLocations,
                (__int64)"Name %ls",
                (const char *)a2);
              if ( (unsigned int)dword_180031038 > 5 )
              {
                if ( (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
                {
                  LODWORD(v33) = StorageLocations;
                  v39 = a2;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                    (unsigned int)&dword_180031038,
                    (unsigned int)&dword_18002AEE4,
                    0,
                    0,
                    (__int64)va1,
                    (__int64)va);
                }
              }
            }
            if ( StorageLocations != -2147024713 )
              goto LABEL_30;
          }
        }
      }
      v15 = AppContainerRegisterSid(v37, a2, a3);
      if ( v15 < 0 )
      {
        StorageLocations = AppContainerRegistrationHelper::SetAPIContextIfFailed(v15, 0x749u, a3, 0x208u, v42);
        if ( v15 != -2147024713 )
        {
          wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x74E,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)(unsigned int)v15,
            (__int64)"Name %ls display %ls",
            (const char *)a2,
            a3);
          AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerRegisterSidFailure, v15, 0);
          if ( (unsigned int)dword_180031038 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
            {
              LODWORD(v33) = v15;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_180031038,
                (unsigned int)&unk_18002B258,
                (_DWORD)v41,
                v16,
                (__int64)va);
            }
          }
        }
        if ( StorageLocations != -2147024713 )
        {
LABEL_30:
          v17 = AppContainerRegistrationHelper::DeleteProfileW(
                  a1,
                  (const char *)a2,
                  (__int64)a3,
                  (__int64)a5,
                  v37,
                  v7,
                  v41);
          wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x763,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)v17,
            (__int64)"Name %ls display %ls",
            (const char *)a2,
            a3);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x6F0,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)StorageLocations,
        (int)"Name %ls display %ls Sid %ls type %d",
        (const char *)a2,
        a3,
        a5,
        v7);
    }
    return StorageLocations;
  }
  v18 = AppContainerRegisterSid(v8, a2, a3);
  v19 = wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x76A,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v18,
          (__int64)"Name %ls display %ls",
          (const char *)a2,
          a3);
  if ( (v19 & 0x80000000) != 0 )
  {
    AppContainerRegistrationHelper::SetAPIContextIfFailed(v19, 0x76Du, a3, 0x208u, v42);
    if ( v19 != -2147024713 )
    {
      AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerRegisterSidFailure, v19, 0);
      if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
      {
        LODWORD(v33) = v19;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180031038,
          (unsigned int)byte_18002AE39,
          (_DWORD)v41,
          v20,
          (__int64)va);
      }
      v21 = 1913;
      goto LABEL_37;
    }
  }
  if ( ((v7 - 1) & 0xFFFFFFFD) != 0 && (unsigned __int8)IsNetworkIsolationDeleteAppContainerPresent() )
  {
    AppContainerRegistrationHelper::LogSuccess(&AppModelFirewallAppContainerCreationStart, a2, 0);
    v22 = NetworkIsolationCreateAppContainer(v8, a2, a3, a4, v35, v36);
    v23 = v22;
    if ( v22 == 1753 || v22 == 1722 )
    {
      LOBYTE(v33) = 0;
      v24 = AppContainerRegistrationHelper::IsAppContainerAllowedToNotRegisterWithFirewall(a2, (bool *)va);
      if ( (int)wil::details::in1diag3::Log_IfFailedMsg(
                  retaddr,
                  (void *)0x795,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                  (const char *)v24,
                  (__int64)"Name %ls",
                  (const char *)a2) >= 0
        && (_BYTE)v33 )
      {
        AppContainerRegistrationHelper::LogSuccess(&AppModelFirewallAppContainerCreationSkipped, a2, 0);
        v23 = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Log_IfWin32ErrorMsg(
        retaddr,
        (void *)0x7A0,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v22,
        (unsigned int)"Name %ls, %ls, %ls",
        (const char *)a2,
        a3,
        a4);
    }
    AppContainerRegistrationHelper::LogFailureWithContext(&AppModelFirewallAppContainerCreationStop, a2, v23, 0);
    if ( v23 )
    {
      if ( v23 != 183 )
      {
        v25 = AppContainerUnregisterSid(v8);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x7A8,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v25,
          (__int64)"Name %ls",
          (const char *)a2);
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
        v19 = wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x7AB,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                (const char *)(unsigned int)v23,
                (__int64)"Name %ls",
                (const char *)a2);
        AppContainerRegistrationHelper::SetAPIContextIfFailed(v19, 0x7ACu, a2, 0x208u, v42);
        AppContainerRegistrationHelper::LogFailure(&AppModelAppContainerRegisterFirewallFailure, v19, v41);
        if ( v19 != -2147024713 )
        {
          if ( (unsigned int)dword_180031038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031038, 0x400000000000LL) )
          {
            LODWORD(v33) = v19;
            v39 = a2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_180031038,
              (unsigned int)byte_18002AF95,
              0,
              0,
              (__int64)va1,
              (__int64)va);
          }
          if ( v19 == 1753 || v19 == 1722 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( v19 == -2147024891 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          return v19;
        }
        v19 = -2147024886;
        v21 = 1966;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)v19,
          v28);
        return v19;
      }
    }
  }
  HIDWORD(v29) = HIDWORD(v42);
  StorageLocations = AppContainerRegistrationHelper::CreateStorageLocations(a1, a2, a5, v8, v7);
  if ( (StorageLocations & 0x80000000) == 0 )
    return 0;
  v26 = AppContainerUnregisterSid(v8);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x7CB,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)v26,
    (__int64)"Name %ls",
    (const char *)a2);
  if ( v7 != 3 && (unsigned __int8)IsNetworkIsolationDeleteAppContainerPresent() )
  {
    AppContainerRegistrationHelper::LogSuccess(&AppModelFirewallAppContainerDeletionStart, a2, 0);
    v27 = (const char *)(unsigned int)NetworkIsolationDeleteAppContainer(v8, a3);
    wil::details::in1diag3::Log_IfWin32ErrorMsg(
      retaddr,
      (void *)0x7D4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      v27,
      (unsigned int)"Name %ls display %ls",
      (const char *)a2,
      a3);
    AppContainerRegistrationHelper::LogFailureWithContext(&AppModelFirewallAppContainerDeletionStop, a2, (int)v27, 0);
  }
  result = 2147943418LL;
  if ( StorageLocations != -2147023878 )
  {
    LODWORD(v29) = v7;
    if ( StorageLocations == -2147024713 )
      StorageLocations = -2147024886;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x7DB,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)StorageLocations,
      (int)"Name %ws Sid %ws type %d",
      (const char *)a2,
      a5,
      v29);
    return StorageLocations;
  }
  return result;
}

```

## disassembly

```asm
0x18000d980  mov     r11, rsp
0x18000d983  mov     [r11+10h], rbx
0x18000d987  mov     [r11+20h], r9
0x18000d98b  mov     [r11+8], rcx
0x18000d98f  push    rbp
0x18000d990  push    rsi
0x18000d991  push    rdi
0x18000d992  push    r12
0x18000d994  push    r13
0x18000d996  push    r14
0x18000d998  push    r15
0x18000d99a  mov     rbp, rsp
0x18000d99d  sub     rsp, 50h
0x18000d9a1  mov     rax, [rbp+arg_58]
0x18000d9a8  mov     r12, r8
0x18000d9ab  mov     rbx, [rbp+arg_20]
0x18000d9af  mov     rdi, rdx
0x18000d9b2  mov     r13d, dword ptr [rbp+arg_48]
0x18000d9b9  mov     r9, rbx
0x18000d9bc  mov     r15, [rbp+arg_40]
0x18000d9c3  mov     [r11-58h], rax
0x18000d9c7  mov     [r11-60h], r13d
0x18000d9cb  mov     [r11-68h], r15
0x18000d9cf  call    ?EnsureExistingState@AppContainerRegistrationHelper@@CAJPEAXPEBG11QEAXW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::EnsureExistingState(void *,ushort const *,ushort const *,ushort const *,void * const,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x18000d9d4  mov     esi, eax
0x18000d9d6  test    eax, eax
0x18000d9d8  jns     loc_18000DDD7
0x18000d9de  mov     rax, [rbp+arg_60]
0x18000d9e5  mov     r9d, 208h; unsigned __int64
0x18000d9eb  mov     r8, rbx; unsigned __int16 *
0x18000d9ee  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18000d9f3  mov     edx, 6EFh; unsigned int
0x18000d9f8  mov     ecx, esi; int
0x18000d9fa  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x18000d9ff  cmp     esi, 800700B7h
0x18000da05  jz      short loc_18000DA46
0x18000da07  mov     rcx, [rbp+38h]; this
0x18000da0b  lea     rax, aNameLsDisplayL; "Name %ls display %ls Sid %ls type %d"
0x18000da12  mov     [rsp+50h+var_10], r13d
0x18000da17  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000da1e  mov     [rsp+50h+var_18], rbx
0x18000da23  mov     r9d, esi; char *
0x18000da26  mov     [rsp+50h+var_20], r12
0x18000da2b  mov     edx, 6F0h; void *
0x18000da30  mov     [rsp+50h+var_28], rdi; char *
0x18000da35  mov     [rsp+50h+var_30], rax; int
0x18000da3a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000da3f  mov     eax, esi
0x18000da41  jmp     loc_18000E24B
0x18000da46  lea     eax, [r13-1]
0x18000da4a  lea     r15, dword_180031038
0x18000da51  lea     r14, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000da58  test    eax, 0FFFFFFFDh
0x18000da5d  jz      loc_18000DCA0
0x18000da63  call    IsNetworkIsolationDeleteAppContainerPresent
0x18000da68  test    al, al
0x18000da6a  jz      short loc_18000DADE
0x18000da6c  xor     r8d, r8d; struct _GUID *
0x18000da6f  lea     rcx, AppModelFirewallAppContainerDeletionStart; struct _EVENT_DESCRIPTOR *
0x18000da76  mov     rdx, rdi; unsigned __int16 *
0x18000da79  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000da7e  mov     rcx, [rbp+arg_40]
0x18000da85  mov     rdx, r12
0x18000da88  call    cs:__imp_NetworkIsolationDeleteAppContainer
0x18000da8f  nop     dword ptr [rax+rax+00h]
0x18000da94  mov     rcx, [rbp+38h]; this
0x18000da98  mov     r8, r14; unsigned int
0x18000da9b  mov     ebx, eax
0x18000da9d  mov     dword ptr [rsp+50h+var_18], r13d
0x18000daa2  mov     rax, [rbp+arg_20]
0x18000daa6  mov     r9d, ebx; char *
0x18000daa9  mov     [rsp+50h+var_20], rax
0x18000daae  mov     edx, 6FEh; void *
0x18000dab3  lea     rax, aNameLsSidLsTyp; "Name %ls Sid %ls type %d"
0x18000daba  mov     [rsp+50h+var_28], rdi; char *
0x18000dabf  mov     [rsp+50h+var_30], rax; unsigned int
0x18000dac4  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18000dac9  xor     r9d, r9d; struct _GUID *
0x18000dacc  lea     rcx, AppModelFirewallAppContainerDeletionStop; struct _EVENT_DESCRIPTOR *
0x18000dad3  mov     r8d, ebx; int
0x18000dad6  mov     rdx, rdi; unsigned __int16 *
0x18000dad9  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18000dade  call    IsNetworkIsolationDeleteAppContainerPresent
0x18000dae3  test    al, al
0x18000dae5  jz      loc_18000DCA0
0x18000daeb  xor     r8d, r8d; struct _GUID *
0x18000daee  lea     rcx, AppModelFirewallAppContainerCreationStart; struct _EVENT_DESCRIPTOR *
0x18000daf5  mov     rdx, rdi; unsigned __int16 *
0x18000daf8  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000dafd  mov     eax, dword ptr [rbp+arg_38]
0x18000db00  mov     r8, r12
0x18000db03  mov     r9, [rbp+arg_18]
0x18000db07  mov     rdx, rdi
0x18000db0a  mov     rcx, [rbp+arg_40]
0x18000db11  mov     dword ptr [rsp+50h+var_28], eax
0x18000db15  mov     rax, [rbp+arg_30]
0x18000db19  mov     [rsp+50h+var_30], rax
0x18000db1e  call    cs:__imp_NetworkIsolationCreateAppContainer
0x18000db25  nop     dword ptr [rax+rax+00h]
0x18000db2a  mov     ebx, eax
0x18000db2c  cmp     eax, 6D9h
0x18000db31  jz      short loc_18000DB6F
0x18000db33  cmp     eax, 6BAh
0x18000db38  jz      short loc_18000DB6F
0x18000db3a  mov     rax, [rbp+arg_18]
0x18000db3e  mov     r9d, ebx; char *
0x18000db41  mov     rcx, [rbp+38h]; this
0x18000db45  mov     r8, r14; unsigned int
0x18000db48  mov     [rsp+50h+var_18], rax
0x18000db4d  mov     edx, 723h; void *
0x18000db52  mov     [rsp+50h+var_20], r12
0x18000db57  lea     rax, aNameLsLsLs; "Name %ls, %ls, %ls"
0x18000db5e  mov     [rsp+50h+var_28], rdi; char *
0x18000db63  mov     [rsp+50h+var_30], rax; unsigned int
0x18000db68  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18000db6d  jmp     short loc_18000DBC5
0x18000db6f  lea     rdx, [rbp+arg_28]; bool *
0x18000db73  mov     byte ptr [rbp+arg_28], 0
0x18000db77  mov     rcx, rdi; lpString2
0x18000db7a  call    ?IsAppContainerAllowedToNotRegisterWithFirewall@AppContainerRegistrationHelper@@CAJPEBGPEA_N@Z; AppContainerRegistrationHelper::IsAppContainerAllowedToNotRegisterWithFirewall(ushort const *,bool *)
0x18000db7f  mov     rcx, [rbp+38h]; this
0x18000db83  lea     rdx, aNameLs; "Name %ls"
0x18000db8a  mov     [rsp+50h+var_28], rdi; char *
0x18000db8f  mov     r9d, eax; char *
0x18000db92  mov     [rsp+50h+var_30], rdx; __int64
0x18000db97  mov     r8, r14; unsigned int
0x18000db9a  mov     edx, 717h; void *
0x18000db9f  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000dba4  test    eax, eax
0x18000dba6  js      short loc_18000DBC5
0x18000dba8  cmp     byte ptr [rbp+arg_28], 0
0x18000dbac  jz      short loc_18000DBC5
0x18000dbae  xor     r8d, r8d; struct _GUID *
0x18000dbb1  lea     rcx, AppModelFirewallAppContainerCreationSkipped; struct _EVENT_DESCRIPTOR *
0x18000dbb8  mov     rdx, rdi; unsigned __int16 *
0x18000dbbb  call    ?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000dbc0  mov     ebx, 0B7h
0x18000dbc5  xor     r9d, r9d; struct _GUID *
0x18000dbc8  lea     rcx, AppModelFirewallAppContainerCreationStop; struct _EVENT_DESCRIPTOR *
0x18000dbcf  mov     r8d, ebx; int
0x18000dbd2  mov     rdx, rdi; unsigned __int16 *
0x18000dbd5  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18000dbda  test    ebx, ebx
0x18000dbdc  jz      loc_18000DCA0
0x18000dbe2  jg      short loc_18000DBE8
0x18000dbe4  mov     esi, ebx
0x18000dbe6  jmp     short loc_18000DBF1
0x18000dbe8  movzx   esi, bx
0x18000dbeb  or      esi, 80070000h
0x18000dbf1  mov     rax, [rbp+arg_60]
0x18000dbf8  mov     r9d, 208h; unsigned __int64
0x18000dbfe  mov     r8, rdi; unsigned __int16 *
0x18000dc01  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18000dc06  mov     edx, 730h; unsigned int
0x18000dc0b  mov     ecx, esi; int
0x18000dc0d  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x18000dc12  cmp     ebx, 0B7h
0x18000dc18  jz      short loc_18000DC94
0x18000dc1a  mov     rcx, [rbp+38h]; this
0x18000dc1e  lea     rax, aNameLs; "Name %ls"
0x18000dc25  mov     [rsp+50h+var_28], rdi; char *
0x18000dc2a  mov     r9d, esi; char *
0x18000dc2d  mov     r8, r14; unsigned int
0x18000dc30  mov     [rsp+50h+var_30], rax; __int64
0x18000dc35  mov     edx, 736h; void *
0x18000dc3a  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000dc3f  mov     eax, cs:dword_180031038
0x18000dc45  cmp     eax, 5
0x18000dc48  jbe     short loc_18000DC94
0x18000dc4a  mov     rdx, 400000000000h
0x18000dc54  mov     rcx, r15
0x18000dc57  call    _tlgKeywordOn
0x18000dc5c  test    al, al
0x18000dc5e  jz      short loc_18000DC94
0x18000dc60  lea     rax, [rbp+arg_28]
0x18000dc64  mov     dword ptr [rbp+arg_28], esi
0x18000dc67  mov     [rsp+50h+var_28], rax
0x18000dc6c  lea     rdx, dword_18002AEE4
0x18000dc73  lea     rax, [rbp+arg_50]
0x18000dc7a  mov     [rbp+arg_50], rdi
0x18000dc81  xor     r9d, r9d
0x18000dc84  mov     [rsp+50h+var_30], rax
0x18000dc89  xor     r8d, r8d
0x18000dc8c  mov     rcx, r15
0x18000dc8f  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000dc94  cmp     esi, 800700B7h
0x18000dc9a  jnz     loc_18000DD78
0x18000dca0  mov     rcx, [rbp+arg_40]
0x18000dca7  mov     r8, r12
0x18000dcaa  mov     rdx, rdi
0x18000dcad  call    cs:__imp_AppContainerRegisterSid
0x18000dcb4  nop     dword ptr [rax+rax+00h]
0x18000dcb9  mov     ebx, eax
0x18000dcbb  test    eax, eax
0x18000dcbd  jns     loc_18000DA3F
0x18000dcc3  mov     rax, [rbp+arg_60]
0x18000dcca  mov     r9d, 208h; unsigned __int64
0x18000dcd0  mov     r8, r12; unsigned __int16 *
0x18000dcd3  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18000dcd8  mov     edx, 749h; unsigned int
0x18000dcdd  mov     ecx, ebx; int
0x18000dcdf  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x18000dce4  mov     esi, eax
0x18000dce6  cmp     ebx, 800700B7h
0x18000dcec  jz      short loc_18000DD6C
0x18000dcee  mov     rcx, [rbp+38h]; this
0x18000dcf2  lea     rax, aNameLsDisplayL_0; "Name %ls display %ls"
0x18000dcf9  mov     [rsp+50h+var_20], r12
0x18000dcfe  mov     r9d, ebx; char *
0x18000dd01  mov     [rsp+50h+var_28], rdi; char *
0x18000dd06  mov     r8, r14; unsigned int
0x18000dd09  mov     edx, 74Eh; void *
0x18000dd0e  mov     [rsp+50h+var_30], rax; __int64
0x18000dd13  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000dd18  xor     r8d, r8d; struct _GUID *
0x18000dd1b  lea     rcx, AppModelAppContainerRegisterSidFailure; struct _EVENT_DESCRIPTOR *
0x18000dd22  mov     edx, ebx; int
0x18000dd24  call    ?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)
0x18000dd29  mov     eax, cs:dword_180031038
0x18000dd2f  cmp     eax, 5
0x18000dd32  jbe     short loc_18000DD6C
0x18000dd34  mov     rdx, 400000000000h
0x18000dd3e  mov     rcx, r15
0x18000dd41  call    _tlgKeywordOn
0x18000dd46  test    al, al
0x18000dd48  jz      short loc_18000DD6C
0x18000dd4a  mov     r8, [rbp+arg_58]
0x18000dd51  lea     rax, [rbp+arg_28]
0x18000dd55  lea     rdx, unk_18002B258
0x18000dd5c  mov     [rsp+50h+var_30], rax
0x18000dd61  mov     rcx, r15
0x18000dd64  mov     dword ptr [rbp+arg_28], ebx
0x18000dd67  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000dd6c  cmp     esi, 800700B7h
0x18000dd72  jz      loc_18000DA3F
0x18000dd78  mov     rax, [rbp+arg_58]
0x18000dd7f  mov     r8, r12
0x18000dd82  mov     r9, [rbp+arg_20]
0x18000dd86  mov     rdx, rdi
0x18000dd89  mov     rcx, [rbp+arg_0]
0x18000dd8d  mov     [rsp+50h+var_20], rax
0x18000dd92  mov     rax, [rbp+arg_40]
0x18000dd99  mov     dword ptr [rsp+50h+var_28], r13d
0x18000dd9e  mov     [rsp+50h+var_30], rax
0x18000dda3  call    ?DeleteProfileW@AppContainerRegistrationHelper@@SAJPEAXPEBG11QEAXW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteProfileW(void *,ushort const *,ushort const *,ushort const *,void * const,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x18000dda8  mov     rcx, [rbp+38h]; this
0x18000ddac  lea     rdx, aNameLsDisplayL_0; "Name %ls display %ls"
0x18000ddb3  mov     [rsp+50h+var_20], r12
0x18000ddb8  mov     r9d, eax; char *
0x18000ddbb  mov     [rsp+50h+var_28], rdi; char *
0x18000ddc0  mov     r8, r14; unsigned int
0x18000ddc3  mov     [rsp+50h+var_30], rdx; __int64
0x18000ddc8  mov     edx, 763h; void *
0x18000ddcd  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000ddd2  jmp     loc_18000DA3F
0x18000ddd7  mov     r8, r12
0x18000ddda  mov     rdx, rdi
0x18000dddd  mov     rcx, r15
0x18000dde0  call    cs:__imp_AppContainerRegisterSid
0x18000dde7  nop     dword ptr [rax+rax+00h]
0x18000ddec  mov     rcx, [rbp+38h]; this
0x18000ddf0  lea     rdx, aNameLsDisplayL_0; "Name %ls display %ls"
0x18000ddf7  mov     [rsp+50h+var_20], r12
0x18000ddfc  lea     r14, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000de03  mov     [rsp+50h+var_28], rdi; char *
0x18000de08  mov     r9d, eax; char *
0x18000de0b  mov     [rsp+50h+var_30], rdx; __int64
0x18000de10  mov     r8, r14; unsigned int
0x18000de13  mov     edx, 76Ah; void *
0x18000de18  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000de1d  mov     ebx, eax
0x18000de1f  test    eax, eax
0x18000de21  jns     loc_18000DEC6
0x18000de27  mov     rax, [rbp+arg_60]
0x18000de2e  mov     r9d, 208h; unsigned __int64
0x18000de34  mov     r8, r12; unsigned __int16 *
0x18000de37  mov     [rsp+50h+var_30], rax; unsigned __int16 *
0x18000de3c  mov     edx, 76Dh; unsigned int
0x18000de41  mov     ecx, ebx; int
0x18000de43  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x18000de48  cmp     ebx, 800700B7h
0x18000de4e  jz      short loc_18000DEC6
0x18000de50  xor     r8d, r8d; struct _GUID *
0x18000de53  lea     rcx, AppModelAppContainerRegisterSidFailure; struct _EVENT_DESCRIPTOR *
0x18000de5a  mov     edx, ebx; int
0x18000de5c  call    ?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)
0x18000de61  mov     eax, cs:dword_180031038
0x18000de67  cmp     eax, 5
0x18000de6a  jbe     short loc_18000DEAB
0x18000de6c  lea     r15, dword_180031038
0x18000de73  mov     rdx, 400000000000h
0x18000de7d  mov     rcx, r15
0x18000de80  call    _tlgKeywordOn
0x18000de85  test    al, al
0x18000de87  jz      short loc_18000DEAB
0x18000de89  mov     r8, [rbp+arg_58]
0x18000de90  lea     rax, [rbp+arg_28]
0x18000de94  lea     rdx, byte_18002AE39
0x18000de9b  mov     [rsp+50h+var_30], rax; int
0x18000dea0  mov     rcx, r15
  ... truncated ...
```
