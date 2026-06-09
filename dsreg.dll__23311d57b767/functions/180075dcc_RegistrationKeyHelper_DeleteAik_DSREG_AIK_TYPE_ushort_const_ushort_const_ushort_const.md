# RegistrationKeyHelper::DeleteAik(DSREG_AIK_TYPE,ushort const *,ushort const *,ushort const *)

- ea: `0x180075dcc`
- end: `0x1800760e9`
- name: `?DeleteAik@RegistrationKeyHelper@@SAJW4DSREG_AIK_TYPE@@PEBG11@Z`
- size: `797`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180053630`
- `0x1800543ec`
- `0x180056418`
- `0x180056ccc`
- `0x1800b46f0`
- `0x1800b4e64`
- `0x1800b651c`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x18005b3c0`
- `0x180067c20`
- `0x180075dcc`
- `0x18008e444`
- `0x18008e564`

## import_xrefs

- `popkeycli!NgcDeleteTokenBindingAik` at `0x180075f5e`
- `popkeycli!NgcDeleteTokenBindingAik` at `0x180075f5e`

## string_xrefs

- `0x180075fd9`: `Logger::WriteNgcDeleteTokenBindingAikFailureEvent`
- `0x180075fd2`: `EventWriteNgcDeleteTokenBindingAikFailureEvent`
- `0x180076068`: `EventWriteNgcDeleteTokenBindingAikSuccessEvent`
- `0x18007606f`: `Logger::WriteNgcDeleteTokenBindingAikSuccessEvent`
- `0x180075e04`: `RegistrationKeyHelper::DeleteAik`
- `0x180075e1e`: `RegistrationKeyHelper::DeleteAik`
- `0x180075e47`: `RegistrationKeyHelper::DeleteAik`
- `0x180075e76`: `RegistrationKeyHelper::DeleteAik`
- `0x180075ec0`: `RegistrationKeyHelper::DeleteAik`
- `0x180075f2d`: `RegistrationKeyHelper::DeleteAik`
- `0x180075ff1`: `RegistrationKeyHelper::DeleteAik`
- `0x180076087`: `RegistrationKeyHelper::DeleteAik`
- `0x1800760ca`: `RegistrationKeyHelper::DeleteAik`
- `0x180075ffd`: `%s: Token binding AIK (type %s) couldn't be deleted (possibly due to key not existing). NgcCreateTokenBindingAik failed with error code 0x%08x. IDP domain: %s, Tenant-based ID: %s, User SID: %s.`
- `0x180075f39`: `%s: Calling NgcDeleteTokenBindingAik with key type: %d (%s), IDP domain: %s, Tenant-based ID: %s, User SID: %s...`
- `0x180076099`: `%s: Token binding AIK (type %s) successfully deleted. IDP domain: %s, Tenant-based ID: %s, User SID: %s.`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::DeleteAik(
        unsigned int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const wchar_t *a4)
{
  unsigned __int16 *v5; // rdi
  unsigned int v8; // ebx
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // r8
  unsigned int v11; // ebp
  int v12; // eax
  const wchar_t *v13; // r14
  __int64 AikTypeName; // rax
  __int64 v15; // r12
  bool v16; // zf
  const WCHAR *v17; // rcx
  const WCHAR *v18; // rax
  unsigned int v19; // eax
  const WCHAR *v20; // rcx
  const WCHAR *v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rax
  unsigned __int16 *v25[11]; // [rsp+40h] [rbp-58h] BYREF

  v5 = 0;
  v25[0] = 0;
  if ( (unsigned int)IsEmptyString(a3) )
  {
    v8 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null or empty.", L"RegistrationKeyHelper::DeleteAik", L"tenantId");
    v9 = L"tenantId";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::DeleteAik", v9);
    goto LABEL_40;
  }
  if ( (unsigned int)IsEmptyString(a2) )
  {
    v8 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null or empty.", L"RegistrationKeyHelper::DeleteAik", L"deviceKeyId");
    v9 = L"deviceKeyId";
    goto LABEL_3;
  }
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      v11 = 1;
    }
    else
    {
      if ( a1 != 2 )
      {
        Logger::TraceError(L"%s: Unknown aikType value: %d", L"RegistrationKeyHelper::DeleteAik", a1);
        v8 = -2147024809;
        goto LABEL_40;
      }
      v11 = 2;
    }
  }
  else
  {
    v11 = 0;
  }
  v12 = StringAppend(v25, v10);
  v8 = v12;
  if ( v12 < 0 || (v12 = StringAppend(v25, L"_"), v8 = v12, v12 < 0) || (v12 = StringAppend(v25, a2), v8 = v12, v12 < 0) )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationKeyHelper::DeleteAik",
      L"StringAppend",
      (unsigned int)v12);
    v5 = v25[0];
  }
  else
  {
    v13 = L"<NULL>";
    if ( a4 )
      v13 = a4;
    AikTypeName = GetAikTypeName(a1);
    v5 = v25[0];
    v15 = AikTypeName;
    Logger::TraceInformation(
      L"%s: Calling NgcDeleteTokenBindingAik with key type: %d (%s), IDP domain: %s, Tenant-based ID: %s, User SID: %s...",
      L"RegistrationKeyHelper::DeleteAik",
      v11,
      AikTypeName,
      L"login.windows.net",
      v25[0],
      v13);
    v8 = NgcDeleteTokenBindingAik(v11, L"login.windows.net", v5, a4);
    if ( (v8 & 0x80000000) == 0 )
    {
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
      {
        v20 = &cchOriginalDestLength;
        v21 = &cchOriginalDestLength;
        if ( a4 )
          v21 = a4;
        if ( v5 )
          v20 = v5;
        v22 = McTemplateU0dzzz_EventWriteTransfer(
                (_DWORD)v20,
                (unsigned int)NgcDeleteTokenBindingAikSuccessEvent,
                v11,
                (unsigned int)L"login.windows.net",
                (__int64)v20,
                (__int64)v21);
        if ( v22 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteNgcDeleteTokenBindingAikSuccessEvent",
            L"EventWriteNgcDeleteTokenBindingAikSuccessEvent",
            v22);
      }
      Logger::TraceInformation(
        L"%s: Token binding AIK (type %s) successfully deleted. IDP domain: %s, Tenant-based ID: %s, User SID: %s.",
        L"RegistrationKeyHelper::DeleteAik",
        v15,
        L"login.windows.net",
        v5,
        v13);
    }
    else
    {
      if ( a1 == 1 )
        v16 = v8 == -2147024894;
      else
        v16 = v8 == -2146893802;
      if ( !v16 && (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
      {
        v17 = &cchOriginalDestLength;
        v18 = &cchOriginalDestLength;
        if ( a4 )
          v18 = a4;
        if ( v5 )
          v17 = v5;
        v19 = McTemplateU0dzzzd_EventWriteTransfer(
                (_DWORD)v17,
                (unsigned int)NgcDeleteTokenBindingAikFailureEvent,
                v11,
                (unsigned int)L"login.windows.net",
                (__int64)v17,
                (__int64)v18,
                v8);
        if ( v19 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteNgcDeleteTokenBindingAikFailureEvent",
            L"EventWriteNgcDeleteTokenBindingAikFailureEvent",
            v19);
      }
      Logger::TraceWarning(
        (wchar_t *)L"%s: Token binding AIK (type %s) couldn't be deleted (possibly due to key not existing). NgcCreateToke"
                    "nBindingAik failed with error code 0x%08x. IDP domain: %s, Tenant-based ID: %s, User SID: %s.",
        L"RegistrationKeyHelper::DeleteAik",
        v15,
        v8,
        L"login.windows.net",
        v5,
        v13);
    }
  }
LABEL_40:
  SafeFree(v5);
  v23 = GetAikTypeName(a1);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x. %s: %s.", L"RegistrationKeyHelper::DeleteAik", v8, L"aikType", v23);
  return v8;
}

```

## disassembly

```asm
0x180075dcc  push    rbx
0x180075dce  push    rbp
0x180075dcf  push    rsi
0x180075dd0  push    rdi
0x180075dd1  push    r12
0x180075dd3  push    r13
0x180075dd5  push    r14
0x180075dd7  push    r15
0x180075dd9  sub     rsp, 58h
0x180075ddd  mov     esi, ecx
0x180075ddf  xor     edi, edi
0x180075de1  mov     rcx, r8; unsigned __int16 *
0x180075de4  mov     [rsp+98h+var_58], rdi
0x180075de9  mov     r15, r9
0x180075dec  mov     r14, rdx
0x180075def  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180075df4  test    eax, eax
0x180075df6  jz      short loc_180075E2F
0x180075df8  lea     r8, aTenantid_1; "tenantId"
0x180075dff  mov     ebx, 80070057h
0x180075e04  lea     rdx, aRegistrationke_6; "RegistrationKeyHelper::DeleteAik"
0x180075e0b  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180075e12  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075e17  lea     rdx, aTenantid_1; "tenantId"
0x180075e1e  lea     rcx, aRegistrationke_6; "RegistrationKeyHelper::DeleteAik"
0x180075e25  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180075e2a  jmp     loc_1800760A5
0x180075e2f  mov     rcx, r14; unsigned __int16 *
0x180075e32  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180075e37  test    eax, eax
0x180075e39  jz      short loc_180075E63
0x180075e3b  lea     r8, aDevicekeyid; "deviceKeyId"
0x180075e42  mov     ebx, 80070057h
0x180075e47  lea     rdx, aRegistrationke_6; "RegistrationKeyHelper::DeleteAik"
0x180075e4e  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180075e55  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075e5a  lea     rdx, aDevicekeyid; "deviceKeyId"
0x180075e61  jmp     short loc_180075E1E
0x180075e63  mov     ecx, esi
0x180075e65  test    esi, esi
0x180075e67  jz      short loc_180075EA1
0x180075e69  sub     ecx, 1
0x180075e6c  jz      short loc_180075E9A
0x180075e6e  cmp     ecx, 1
0x180075e71  jz      short loc_180075E93
0x180075e73  mov     r8d, esi
0x180075e76  lea     rdx, aRegistrationke_6; "RegistrationKeyHelper::DeleteAik"
0x180075e7d  lea     rcx, aSUnknownAiktyp; "%s: Unknown aikType value: %d"
0x180075e84  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075e89  mov     ebx, 80070057h
0x180075e8e  jmp     loc_1800760A5
0x180075e93  mov     ebp, 2
0x180075e98  jmp     short loc_180075EA3
0x180075e9a  mov     ebp, 1
0x180075e9f  jmp     short loc_180075EA3
0x180075ea1  xor     ebp, ebp
0x180075ea3  mov     rdx, r8; unsigned __int16 *
0x180075ea6  lea     rcx, [rsp+98h+var_58]; unsigned __int16 **
0x180075eab  call    ?StringAppend@@YAJPEAPEAGPEBG@Z; StringAppend(ushort * *,ushort const *)
0x180075eb0  mov     ebx, eax
0x180075eb2  test    eax, eax
0x180075eb4  jns     short loc_180075EDD
0x180075eb6  mov     r9d, eax
0x180075eb9  lea     r8, aStringappend; "StringAppend"
0x180075ec0  lea     rdx, aRegistrationke_6; "RegistrationKeyHelper::DeleteAik"
0x180075ec7  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180075ece  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075ed3  mov     rdi, [rsp+98h+var_58]
0x180075ed8  jmp     loc_1800760A5
0x180075edd  lea     rdx, asc_1800F0FF4; "_"
0x180075ee4  lea     rcx, [rsp+98h+var_58]; unsigned __int16 **
0x180075ee9  call    ?StringAppend@@YAJPEAPEAGPEBG@Z; StringAppend(ushort * *,ushort const *)
0x180075eee  mov     ebx, eax
0x180075ef0  test    eax, eax
0x180075ef2  js      short loc_180075EB6
0x180075ef4  mov     rdx, r14; unsigned __int16 *
0x180075ef7  lea     rcx, [rsp+98h+var_58]; unsigned __int16 **
0x180075efc  call    ?StringAppend@@YAJPEAPEAGPEBG@Z; StringAppend(ushort * *,ushort const *)
0x180075f01  mov     ebx, eax
0x180075f03  test    eax, eax
0x180075f05  js      short loc_180075EB6
0x180075f07  test    r15, r15
0x180075f0a  lea     r14, aNull_2; "<NULL>"
0x180075f11  mov     ecx, esi
0x180075f13  cmovnz  r14, r15
0x180075f17  call    GetAikTypeName
0x180075f1c  mov     rdi, [rsp+98h+var_58]
0x180075f21  lea     r13, aLoginWindowsNe; "login.windows.net"
0x180075f28  mov     [rsp+98h+var_68], r14
0x180075f2d  lea     rdx, aRegistrationke_6; "RegistrationKeyHelper::DeleteAik"
0x180075f34  mov     [rsp+98h+var_70], rdi
0x180075f39  lea     rcx, aSCallingNgcdel; "%s: Calling NgcDeleteTokenBindingAik wi"...
0x180075f40  mov     r9, rax
0x180075f43  mov     [rsp+98h+var_78], r13
0x180075f48  mov     r8d, ebp
0x180075f4b  mov     r12, rax
0x180075f4e  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180075f53  mov     r9, r15
0x180075f56  mov     r8, rdi
0x180075f59  mov     rdx, r13
0x180075f5c  mov     ecx, ebp
0x180075f5e  call    cs:__imp_NgcDeleteTokenBindingAik
0x180075f64  mov     ebx, eax
0x180075f66  test    eax, eax
0x180075f68  jns     loc_180076024
0x180075f6e  mov     ecx, esi
0x180075f70  test    esi, esi
0x180075f72  jz      short loc_180075F82
0x180075f74  sub     ecx, 1
0x180075f77  jz      loc_180076019
0x180075f7d  cmp     ecx, 1
0x180075f80  jnz     short loc_180075F8A
0x180075f82  cmp     ebx, 80090016h
0x180075f88  jz      short loc_180075FEC
0x180075f8a  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x180075f91  jz      short loc_180075FEC
0x180075f93  lea     rcx, cchOriginalDestLength
0x180075f9a  mov     dword ptr [rsp+98h+var_68], ebx
0x180075f9e  mov     rax, rcx
0x180075fa1  lea     rdx, NgcDeleteTokenBindingAikFailureEvent
0x180075fa8  test    r15, r15
0x180075fab  mov     r9, r13
0x180075fae  mov     r8d, ebp
0x180075fb1  cmovnz  rax, r15
0x180075fb5  test    rdi, rdi
0x180075fb8  mov     [rsp+98h+var_70], rax
0x180075fbd  cmovnz  rcx, rdi
0x180075fc1  mov     [rsp+98h+var_78], rcx
0x180075fc6  call    McTemplateU0dzzzd_EventWriteTransfer
0x180075fcb  test    eax, eax
0x180075fcd  jz      short loc_180075FEC
0x180075fcf  mov     r9d, eax
0x180075fd2  lea     r8, aEventwritengcd_1; "EventWriteNgcDeleteTokenBindingAikFailu"...
0x180075fd9  lea     rdx, aLoggerWritengc_4; "Logger::WriteNgcDeleteTokenBindingAikFa"...
0x180075fe0  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180075fe7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075fec  mov     [rsp+98h+var_68], r14
0x180075ff1  lea     rdx, aRegistrationke_6; "RegistrationKeyHelper::DeleteAik"
0x180075ff8  mov     [rsp+98h+var_70], rdi
0x180075ffd  lea     rcx, aSTokenBindingA_6; "%s: Token binding AIK (type %s) couldn'"...
0x180076004  mov     r9d, ebx
0x180076007  mov     [rsp+98h+var_78], r13
0x18007600c  mov     r8, r12
0x18007600f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180076014  jmp     loc_1800760A5
0x180076019  cmp     ebx, 80070002h
0x18007601f  jmp     loc_180075F88
0x180076024  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18007602b  jz      short loc_180076082
0x18007602d  lea     rcx, cchOriginalDestLength
0x180076034  test    r15, r15
0x180076037  mov     rax, rcx
0x18007603a  lea     rdx, NgcDeleteTokenBindingAikSuccessEvent
0x180076041  cmovnz  rax, r15
0x180076045  mov     r9, r13
0x180076048  mov     [rsp+98h+var_70], rax
0x18007604d  test    rdi, rdi
0x180076050  mov     r8d, ebp
0x180076053  cmovnz  rcx, rdi
0x180076057  mov     [rsp+98h+var_78], rcx
0x18007605c  call    McTemplateU0dzzz_EventWriteTransfer
0x180076061  test    eax, eax
0x180076063  jz      short loc_180076082
0x180076065  mov     r9d, eax
0x180076068  lea     r8, aEventwritengcd_6; "EventWriteNgcDeleteTokenBindingAikSucce"...
0x18007606f  lea     rdx, aLoggerWritengc_35; "Logger::WriteNgcDeleteTokenBindingAikSu"...
0x180076076  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18007607d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076082  mov     [rsp+98h+var_70], r14
0x180076087  lea     rdx, aRegistrationke_6; "RegistrationKeyHelper::DeleteAik"
0x18007608e  mov     r9, r13
0x180076091  mov     [rsp+98h+var_78], rdi
0x180076096  mov     r8, r12
0x180076099  lea     rcx, aSTokenBindingA_5; "%s: Token binding AIK (type %s) success"...
0x1800760a0  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800760a5  mov     rcx, rdi; lpMem
0x1800760a8  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800760ad  mov     ecx, esi
0x1800760af  call    GetAikTypeName
0x1800760b4  lea     rcx, aSHr0x08xSS; "%s - hr: 0x%08x. %s: %s."
0x1800760bb  mov     [rsp+98h+var_78], rax
0x1800760c0  lea     r9, aAiktype; "aikType"
0x1800760c7  mov     r8d, ebx
0x1800760ca  lea     rdx, aRegistrationke_6; "RegistrationKeyHelper::DeleteAik"
0x1800760d1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800760d6  mov     eax, ebx
0x1800760d8  add     rsp, 58h
0x1800760dc  pop     r15
0x1800760de  pop     r14
0x1800760e0  pop     r13
0x1800760e2  pop     r12
0x1800760e4  pop     rdi
0x1800760e5  pop     rsi
0x1800760e6  pop     rbp
0x1800760e7  pop     rbx
0x1800760e8  retn
```
