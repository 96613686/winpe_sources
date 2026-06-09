# KeyManager::CreateContainer(HWND__ *,bool)

- ea: `0x180081bf8`
- end: `0x180081ed6`
- name: `?CreateContainer@KeyManager@@QEAAJPEAUHWND__@@_N@Z`
- size: `734`
- prototype: `__int64 __fastcall(KeyManager *__hidden this, HWND, bool)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080ca4`
- `0x180080fbc`
- `0x1800811cc`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18000cbd8`
- `0x180012948`
- `0x180044300`
- `0x180081bf8`
- `0x180083004`
- `0x180083a48`
- `0x180083ab8`
- `0x1800925dc`
- `0x1800926e8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081c5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081ce5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081c5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081ce5`
- `cryptngc!NgcCreateContainer` at `0x180081cdd`
- `cryptngc!NgcCreateContainer` at `0x180081cdd`

## string_xrefs

- `0x180081e48`: `EventWriteNgcCreateContainerSuccessEvent`
- `0x180081e4f`: `Logger::WriteNgcCreateContainerSuccessEvent`
- `0x180081da4`: `Logger::WriteNgcCreateContainerFailureEvent`
- `0x180081d9d`: `EventWriteNgcCreateContainerFailureEvent`
- `0x180081c79`: `GetUserSid`
- `0x180081d18`: `%s: Container already exists. Keep using it. SID: %s, IDP domain: %s, Tenant domain: %s, Flags: %lu, Error code: 0x%08x.`
- `0x180081c80`: `KeyManager::CreateContainer`
- `0x180081d0d`: `KeyManager::CreateContainer`
- `0x180081dbb`: `KeyManager::CreateContainer`
- `0x180081e66`: `KeyManager::CreateContainer`
- `0x180081e71`: `%s: NgcCreateContainer succeeded. SID: %s, IDP domain: %s, Tenant domain: %s, Flags: %lu.`
- `0x180081dc6`: `%s: NgcCreateContainer failed. SID: %s, IDP domain: %s, Tenant domain: %s, Flags: %lu, Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall KeyManager::CreateContainer(const WCHAR **this, HWND a2, __int64 a3)
{
  char v3; // r15
  DWORD TickCount; // ebp
  int UserSid; // eax
  unsigned int Container; // ebx
  _DWORD *v9; // rdi
  const WCHAR *v10; // r8
  const WCHAR *v11; // rdx
  HWND v12; // r9
  unsigned __int16 *v13; // r14
  unsigned __int16 *v14; // rcx
  DWORD v15; // ebp
  __int64 v16; // rdx
  __int64 v17; // rcx
  const WCHAR *v18; // rcx
  const WCHAR *v19; // rdx
  const WCHAR *v20; // r9
  const WCHAR *v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 *v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v30; // [rsp+28h] [rbp-80h]
  __int64 v31; // [rsp+30h] [rbp-78h]
  unsigned __int16 *v32; // [rsp+60h] [rbp-48h] BYREF
  __int64 v33; // [rsp+68h] [rbp-40h] BYREF

  v3 = a3;
  v32 = 0;
  if ( (Microsoft_Windows_HelloForBusinessEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(MS_PROVIDER_HFB_Context, EVENT_HFB_CONTAINERPROVISIONINGOUTER_START, a3, 1, &v33);
  TickCount = GetTickCount();
  UserSid = KeyManager::GetUserSid((KeyManager *)this, &v32);
  Container = UserSid;
  if ( UserSid < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"KeyManager::CreateContainer",
      L"GetUserSid",
      (unsigned int)UserSid);
    v9 = this + 7;
LABEL_30:
    *v9 = 0;
    return Container;
  }
  v10 = this[3];
  v11 = this[2];
  v9 = this + 7;
  v12 = a2;
  v13 = v32;
  v14 = v32;
  HIDWORD(v30) = 0;
  *((_DWORD *)this + 14) = 0;
  Container = NgcCreateContainer(v14, v11, v10, v12, 0);
  v15 = (GetTickCount() - TickCount) / 0x3E8;
  if ( v3 && Container == -2146893809 )
  {
    Logger::TraceInformation(
      L"%s: Container already exists. Keep using it. SID: %s, IDP domain: %s, Tenant domain: %s, Flags: %lu, Error code: 0x%08x.",
      L"KeyManager::CreateContainer",
      v13,
      this[2],
      this[3],
      0,
      -2146893809);
    if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
      McTemplateU0qt_EventWriteTransfer(v17, v16, v15, 1);
    Container = 0;
  }
  else
  {
    v18 = this[3];
    v19 = this[2];
    if ( (Container & 0x80000000) != 0 )
    {
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
      {
        v20 = &cchOriginalDestLength;
        v21 = &cchOriginalDestLength;
        if ( v18 )
          v21 = this[3];
        if ( v19 )
          LODWORD(v20) = (unsigned int)this[2];
        v22 = McTemplateU0zzzqd_EventWriteTransfer(
                (_DWORD)v18,
                (_DWORD)v19,
                (_DWORD)v13,
                (_DWORD)v20,
                (__int64)v21,
                0,
                Container);
        if ( v22 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteNgcCreateContainerFailureEvent",
            L"EventWriteNgcCreateContainerFailureEvent",
            v22);
      }
      LODWORD(v31) = Container;
      LODWORD(v30) = 0;
      Logger::TraceError(
        L"%s: NgcCreateContainer failed. SID: %s, IDP domain: %s, Tenant domain: %s, Flags: %lu, Error code: 0x%08x.",
        L"KeyManager::CreateContainer",
        v13,
        this[2],
        this[3],
        v30,
        v31);
      v24 = 2148073526LL;
      if ( Container == -2146893770 )
      {
        if ( (Microsoft_Windows_HelloForBusinessEnableBits & 8) == 0 )
          goto LABEL_30;
        v25 = EVENT_HFB_CONTAINERPROVISIONINGOUTER_WARNING;
      }
      else
      {
        if ( (Microsoft_Windows_HelloForBusinessEnableBits & 2) == 0 )
          goto LABEL_30;
        v24 = Container;
        v25 = EVENT_HFB_CONTAINERPROVISIONINGOUTER_FAILURE;
      }
      McTemplateU0dq_EventWriteTransfer(v23, v25, v24, v15);
      goto LABEL_30;
    }
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v26 = McTemplateU0zzzq_EventWriteTransfer(
              (_DWORD)v18,
              (_DWORD)v19,
              (_DWORD)v13,
              (unsigned int)this[2],
              (__int64)this[3]);
      if ( v26 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNgcCreateContainerSuccessEvent",
          L"EventWriteNgcCreateContainerSuccessEvent",
          v26);
    }
    Logger::TraceVerbose(
      (wchar_t *)L"%s: NgcCreateContainer succeeded. SID: %s, IDP domain: %s, Tenant domain: %s, Flags: %lu.",
      L"KeyManager::CreateContainer",
      v13,
      this[2],
      this[3],
      0);
    if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
      McTemplateU0qt_EventWriteTransfer(v28, v27, v15, 0);
  }
  *v9 = 1;
  return Container;
}

```

## disassembly

```asm
0x180081bf8  mov     r11, rsp
0x180081bfb  mov     [r11+18h], rbx
0x180081bff  mov     [r11+20h], rbp
0x180081c03  push    rsi
0x180081c04  push    rdi
0x180081c05  push    r12
0x180081c07  push    r14
0x180081c09  push    r15
0x180081c0b  sub     rsp, 80h
0x180081c12  mov     rax, cs:__security_cookie
0x180081c19  xor     rax, rsp
0x180081c1c  mov     [rsp+0A8h+var_30], rax
0x180081c21  xor     r12d, r12d
0x180081c24  mov     r15b, r8b
0x180081c27  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 1
0x180081c2e  mov     r14, rdx
0x180081c31  mov     rsi, rcx
0x180081c34  mov     [r11-48h], r12
0x180081c38  jz      short loc_180081C5B
0x180081c3a  lea     rax, [r11-40h]
0x180081c3e  lea     r9d, [r12+1]
0x180081c43  mov     [rsp+0A8h+var_88], rax
0x180081c48  lea     rdx, EVENT_HFB_CONTAINERPROVISIONINGOUTER_START
0x180081c4f  lea     rcx, MS_PROVIDER_HFB_Context
0x180081c56  call    McGenEventWrite_EventWriteTransfer
0x180081c5b  call    cs:__imp_GetTickCount
0x180081c61  lea     rdx, [rsp+0A8h+var_48]; unsigned __int16 **
0x180081c66  mov     rcx, rsi; this
0x180081c69  mov     ebp, eax
0x180081c6b  call    ?GetUserSid@KeyManager@@AEAAJPEAPEAG@Z; KeyManager::GetUserSid(ushort * *)
0x180081c70  mov     ebx, eax
0x180081c72  test    eax, eax
0x180081c74  jns     short loc_180081C9C
0x180081c76  mov     r9d, eax
0x180081c79  lea     r8, aGetusersid; "GetUserSid"
0x180081c80  lea     rdx, aKeymanagerCrea_0; "KeyManager::CreateContainer"
0x180081c87  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180081c8e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081c93  lea     rdi, [rsi+38h]
0x180081c97  jmp     loc_180081EA8
0x180081c9c  mov     r8, [rsi+18h]
0x180081ca0  lea     rax, [rsi+28h]
0x180081ca4  mov     rdx, [rsi+10h]
0x180081ca8  lea     rdi, [rsi+38h]
0x180081cac  mov     [rsp+0A8h+var_58], rax
0x180081cb1  mov     r9, r14
0x180081cb4  mov     r14, [rsp+0A8h+var_48]
0x180081cb9  mov     [rsp+0A8h+var_60], r12
0x180081cbe  mov     rcx, r14
0x180081cc1  mov     [rsp+0A8h+var_68], r12
0x180081cc6  mov     [rsp+0A8h+var_70], r12
0x180081ccb  mov     dword ptr [rsp+0A8h+var_78], r12d
0x180081cd0  mov     [rsp+0A8h+var_80], r12
0x180081cd5  mov     [rsp+0A8h+var_88], r12
0x180081cda  mov     [rdi], r12d
0x180081cdd  call    cs:__imp_NgcCreateContainer
0x180081ce3  mov     ebx, eax
0x180081ce5  call    cs:__imp_GetTickCount
0x180081ceb  mov     ecx, eax
0x180081ced  mov     eax, 10624DD3h
0x180081cf2  sub     ecx, ebp
0x180081cf4  mul     ecx
0x180081cf6  mov     ebp, edx
0x180081cf8  shr     ebp, 6
0x180081cfb  test    r15b, r15b
0x180081cfe  jz      short loc_180081D54
0x180081d00  mov     eax, 8009000Fh
0x180081d05  cmp     ebx, eax
0x180081d07  jnz     short loc_180081D54
0x180081d09  mov     r9, [rsi+10h]
0x180081d0d  lea     rdx, aKeymanagerCrea_0; "KeyManager::CreateContainer"
0x180081d14  mov     dword ptr [rsp+0A8h+var_78], eax
0x180081d18  lea     rcx, aSContainerAlre; "%s: Container already exists. Keep usin"...
0x180081d1f  mov     rax, [rsi+18h]
0x180081d23  mov     r8, r14
0x180081d26  mov     dword ptr [rsp+0A8h+var_80], r12d
0x180081d2b  mov     [rsp+0A8h+var_88], rax
0x180081d30  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180081d35  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x180081d3c  jz      short loc_180081D4C
0x180081d3e  mov     r9d, 1
0x180081d44  mov     r8d, ebp
0x180081d47  call    McTemplateU0qt_EventWriteTransfer
0x180081d4c  mov     ebx, r12d
0x180081d4f  jmp     loc_180081E9E
0x180081d54  mov     rcx, [rsi+18h]
0x180081d58  mov     rdx, [rsi+10h]
0x180081d5c  test    ebx, ebx
0x180081d5e  jns     loc_180081E28
0x180081d64  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180081d6b  jz      short loc_180081DB7
0x180081d6d  test    rcx, rcx
0x180081d70  mov     dword ptr [rsp+0A8h+var_78], ebx
0x180081d74  lea     r9, cchOriginalDestLength
0x180081d7b  mov     r8, r14
0x180081d7e  mov     rax, r9
0x180081d81  cmovnz  rax, rcx
0x180081d85  test    rdx, rdx
0x180081d88  mov     [rsp+0A8h+var_88], rax
0x180081d8d  cmovnz  r9, rdx
0x180081d91  call    McTemplateU0zzzqd_EventWriteTransfer
0x180081d96  test    eax, eax
0x180081d98  jz      short loc_180081DB7
0x180081d9a  mov     r9d, eax
0x180081d9d  lea     r8, aEventwritengcc_3; "EventWriteNgcCreateContainerFailureEven"...
0x180081da4  lea     rdx, aLoggerWritengc_30; "Logger::WriteNgcCreateContainerFailureE"...
0x180081dab  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180081db2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081db7  mov     rax, [rsi+18h]
0x180081dbb  lea     rdx, aKeymanagerCrea_0; "KeyManager::CreateContainer"
0x180081dc2  mov     r9, [rsi+10h]
0x180081dc6  lea     rcx, aSNgccreatecont; "%s: NgcCreateContainer failed. SID: %s,"...
0x180081dcd  mov     dword ptr [rsp+0A8h+var_78], ebx
0x180081dd1  mov     r8, r14
0x180081dd4  mov     dword ptr [rsp+0A8h+var_80], r12d
0x180081dd9  mov     [rsp+0A8h+var_88], rax
0x180081dde  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081de3  mov     r8d, 80090036h
0x180081de9  cmp     ebx, r8d
0x180081dec  jnz     short loc_180081E0F
0x180081dee  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 8
0x180081df5  jz      loc_180081EA8
0x180081dfb  lea     rdx, EVENT_HFB_CONTAINERPROVISIONINGOUTER_WARNING
0x180081e02  mov     r9d, ebp
0x180081e05  call    McTemplateU0dq_EventWriteTransfer
0x180081e0a  jmp     loc_180081EA8
0x180081e0f  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 2
0x180081e16  jz      loc_180081EA8
0x180081e1c  mov     r8d, ebx
0x180081e1f  lea     rdx, EVENT_HFB_CONTAINERPROVISIONINGOUTER_FAILURE
0x180081e26  jmp     short loc_180081E02
0x180081e28  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x180081e2f  jz      short loc_180081E62
0x180081e31  mov     r9, rdx
0x180081e34  mov     [rsp+0A8h+var_88], rcx
0x180081e39  mov     r8, r14
0x180081e3c  call    McTemplateU0zzzq_EventWriteTransfer
0x180081e41  test    eax, eax
0x180081e43  jz      short loc_180081E62
0x180081e45  mov     r9d, eax
0x180081e48  lea     r8, aEventwritengcc_1; "EventWriteNgcCreateContainerSuccessEven"...
0x180081e4f  lea     rdx, aLoggerWritengc_8; "Logger::WriteNgcCreateContainerSuccessE"...
0x180081e56  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180081e5d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081e62  mov     rax, [rsi+18h]
0x180081e66  lea     rdx, aKeymanagerCrea_0; "KeyManager::CreateContainer"
0x180081e6d  mov     r9, [rsi+10h]
0x180081e71  lea     rcx, aSNgccreatecont_0; "%s: NgcCreateContainer succeeded. SID: "...
0x180081e78  mov     dword ptr [rsp+0A8h+var_80], r12d
0x180081e7d  mov     r8, r14
0x180081e80  mov     [rsp+0A8h+var_88], rax
0x180081e85  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180081e8a  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x180081e91  jz      short loc_180081E9E
0x180081e93  xor     r9d, r9d
0x180081e96  mov     r8d, ebp
0x180081e99  call    McTemplateU0qt_EventWriteTransfer
0x180081e9e  mov     dword ptr [rdi], 1
0x180081ea4  test    ebx, ebx
0x180081ea6  jns     short loc_180081EAB
0x180081ea8  mov     [rdi], r12d
0x180081eab  mov     eax, ebx
0x180081ead  mov     rcx, [rsp+0A8h+var_30]
0x180081eb2  xor     rcx, rsp; StackCookie
0x180081eb5  call    __security_check_cookie
0x180081eba  lea     r11, [rsp+0A8h+var_28]
0x180081ec2  mov     rbx, [r11+40h]
0x180081ec6  mov     rbp, [r11+48h]
0x180081eca  mov     rsp, r11
0x180081ecd  pop     r15
0x180081ecf  pop     r14
0x180081ed1  pop     r12
0x180081ed3  pop     rdi
0x180081ed4  pop     rsi
0x180081ed5  retn
```
