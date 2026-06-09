# RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18000554c`
- end: `0x18000588e`
- name: `?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `834`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, HKEY, wchar_t *String1, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000468c`
- `0x1800053d0`
- `0x180005894`
- `0x180005bbc`
- `0x1800792e0`
- `0x18009ea50`
- `0x18009eb34`
- `0x18009f1dc`
- `0x1800b30c0`

## callees

- `0x1800048cc`
- `0x18000554c`
- `0x180005ba0`
- `0x180006190`
- `0x1800084f4`
- `0x180009780`
- `0x18000bac0`
- `0x18000cbd8`
- `0x180012cf0`
- `0x18003334c`
- `0x180044300`
- `0x180044ca0`
- `0x180044d30`
- `0x18009614c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800057e6`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800057e6`
- `ntdll!NtQueryKey` at `0x18000569d`
- `ntdll!NtQueryKey` at `0x1800056ff`
- `ntdll!NtQueryKey` at `0x18000569d`
- `ntdll!NtQueryKey` at `0x1800056ff`

## string_xrefs

- `0x18000580d`: `RegistryPath::Append`
- `0x180005597`: `RegistryPath::Initialize`
- `0x180005631`: `RegistryPath::Initialize`
- `0x180005747`: `\Registry\Machine`
- `0x18000577f`: `\Registry\User`
- `0x18000560d`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180005606`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x180005649`: `%s: Root path is empty. Retrieve path using the root key handle.`

## pseudocode

```c
__int64 __fastcall RegistryPath::Initialize(RegistryPath *this, HKEY a2, wchar_t *String1, unsigned __int16 *a4)
{
  wchar_t *v7; // r13
  int v8; // ebx
  __int64 v9; // r8
  unsigned int v10; // eax
  NTSTATUS v11; // r15d
  void *v12; // rcx
  __int64 v13; // rbx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  int v16; // esi
  size_t v17; // rax
  unsigned __int16 *v18; // rdx
  ULONG ResultLength; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int16 *v21; // [rsp+38h] [rbp-90h]
  _BYTE v22[16]; // [rsp+40h] [rbp-88h] BYREF
  const wchar_t *v23; // [rsp+50h] [rbp-78h]
  __int64 v24; // [rsp+58h] [rbp-70h]
  const wchar_t *v25; // [rsp+60h] [rbp-68h]
  __int64 v26; // [rsp+68h] [rbp-60h]

  v21 = a4;
  v7 = 0;
  if ( a2 )
  {
    v11 = 0;
    RegistryPath::Reset(this);
    *((_QWORD *)this + 4) = a2;
    if ( !String1 || !*String1 )
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Root path is empty. Retrieve path using the root key handle.",
        L"RegistryPath::Initialize");
      if ( a2 == HKEY_PERFORMANCE_TEXT || (unsigned __int64)(a2 + 0x20000000) <= 7 || a2 == HKEY_PERFORMANCE_NLSTEXT )
      {
        String1 = (wchar_t *)RegistryPath::GetPredefinedRegistryHandlePath(a2);
      }
      else
      {
        v12 = (void *)*((_QWORD *)this + 4);
        ResultLength = 0;
        v11 = NtQueryKey(v12, KeyNameInformation, 0, 0, &ResultLength);
        if ( v11 == -1073741789 )
        {
          v13 = ResultLength + 2LL;
          v14 = (wchar_t *)SafeAlloc(v13);
          v7 = v14;
          if ( !v14 )
          {
            Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistryPath::Initialize");
            goto LABEL_36;
          }
          memset_0(v14, 0, v13);
          v11 = NtQueryKey(*((HANDLE *)this + 4), KeyNameInformation, v7, v13, &ResultLength);
        }
        if ( v11 < 0 )
        {
          Logger::TraceError(
            L"%s: %s failed with NTSTATUS: 0x%08x.",
            L"RegistryPath::Initialize",
            L"NtQueryKey",
            (unsigned int)v11);
          goto LABEL_36;
        }
        String1 = v7 + 2;
      }
      if ( !String1 )
        goto LABEL_27;
    }
    if ( !wcsnicmp(String1, L"\\Registry\\Machine", 0x11u) )
    {
      v15 = String1 + 17;
      if ( String1[17] == 92 || !*v15 )
      {
        String1 = (wchar_t *)L"HKEY_LOCAL_MACHINE";
        goto LABEL_28;
      }
    }
    if ( !wcsnicmp(String1, L"\\Registry\\User", 0xEu) && ((v15 = String1 + 14, String1[14] == 92) || !*v15) )
      String1 = L"HKEY_USERS";
    else
LABEL_27:
      v15 = 0;
LABEL_28:
    v16 = RegistryPath::Append((const wchar_t **)this, String1);
    if ( v16
      || !(unsigned int)IsEmptyString(v15) && (v16 = RegistryPath::Append((const wchar_t **)this, v15)) != 0
      || (v8 = 0,
          v17 = wcsnlen(*(const wchar_t **)this, *((_QWORD *)this + 1)),
          v18 = v21,
          *((_QWORD *)this + 3) = v17,
          (v16 = RegistryPath::Append((const wchar_t **)this, v18)) != 0) )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"RegistryPath::Initialize",
        L"RegistryPath::Append",
        (unsigned int)v16);
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      else
        v8 = v16;
    }
    if ( !v11 )
    {
LABEL_37:
      if ( v8 >= 0 )
        goto LABEL_41;
      goto LABEL_38;
    }
LABEL_36:
    v8 = v11 | 0x10000000;
    goto LABEL_37;
  }
  v8 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistryPath::Initialize", L"rootKey");
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v23 = L"RegistryPath::Initialize";
    v24 = 50;
    v25 = L"rootKey";
    v26 = 16;
    v10 = McGenEventWrite_EventWriteTransfer(
            &UserDeviceRegistrationEventProvider_Context,
            NullOrEmptyParameterFailureEvent,
            v9,
            3,
            v22);
    if ( v10 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v10);
  }
LABEL_38:
  if ( *((HKEY *)this + 4) == a2 )
    *((_QWORD *)this + 4) = 0;
  RegistryPath::Reset(this);
LABEL_41:
  SafeFree(v7);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistryPath::Initialize", (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000554c  push    rbx
0x18000554e  push    rbp
0x18000554f  push    rsi
0x180005550  push    rdi
0x180005551  push    r12
0x180005553  push    r13
0x180005555  push    r14
0x180005557  push    r15
0x180005559  sub     rsp, 88h
0x180005560  mov     rax, cs:__security_cookie
0x180005567  xor     rax, rsp
0x18000556a  mov     [rsp+0C8h+var_58], rax
0x18000556f  xor     esi, esi
0x180005571  mov     [rsp+0C8h+var_90], r9
0x180005576  mov     rbx, r8
0x180005579  mov     r12, rdx
0x18000557c  mov     rdi, rcx
0x18000557f  mov     r13d, esi
0x180005582  test    rdx, rdx
0x180005585  jnz     loc_180005625
0x18000558b  lea     r14, aRootkey; "rootKey"
0x180005592  mov     ebx, 80070057h
0x180005597  lea     rbp, aRegistrypathIn_0; "RegistryPath::Initialize"
0x18000559e  mov     r8, r14
0x1800055a1  mov     rdx, rbp
0x1800055a4  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800055ab  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800055b0  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800055b7  jz      loc_18000583F
0x1800055bd  lea     rax, [rsp+0C8h+var_88]
0x1800055c2  mov     [rsp+0C8h+var_78], rbp
0x1800055c7  lea     r9d, [r12+3]
0x1800055cc  mov     [rsp+0C8h+ResultLength], rax
0x1800055d1  lea     rdx, NullOrEmptyParameterFailureEvent
0x1800055d8  mov     [rsp+0C8h+var_70], 32h ; '2'
0x1800055e1  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x1800055e8  mov     [rsp+0C8h+var_68], r14
0x1800055ed  mov     [rsp+0C8h+var_60], 10h
0x1800055f6  call    McGenEventWrite_EventWriteTransfer
0x1800055fb  test    eax, eax
0x1800055fd  jz      loc_18000583F
0x180005603  mov     r9d, eax
0x180005606  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18000560d  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180005614  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18000561b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005620  jmp     loc_18000583F
0x180005625  mov     r15d, esi
0x180005628  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18000562d  mov     [rdi+20h], r12
0x180005631  lea     rbp, aRegistrypathIn_0; "RegistryPath::Initialize"
0x180005638  test    rbx, rbx
0x18000563b  jz      short loc_180005646
0x18000563d  cmp     [rbx], si
0x180005640  jnz     loc_180005741
0x180005646  mov     rdx, rbp
0x180005649  lea     rcx, aSRootPathIsEmp; "%s: Root path is empty. Retrieve path u"...
0x180005650  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180005655  cmp     r12, 0FFFFFFFF80000050h
0x18000565c  jz      loc_180005731
0x180005662  mov     eax, 80000000h
0x180005667  add     rax, r12
0x18000566a  cmp     rax, 7
0x18000566e  jbe     loc_180005731
0x180005674  cmp     r12, 0FFFFFFFF80000060h
0x18000567b  jz      loc_180005731
0x180005681  mov     rcx, [rdi+20h]; KeyHandle
0x180005685  lea     rax, [rsp+0C8h+var_98]
0x18000568a  xor     r9d, r9d; Length
0x18000568d  mov     [rsp+0C8h+var_98], esi
0x180005691  xor     r8d, r8d; KeyInformation
0x180005694  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x180005699  lea     edx, [r9+3]; KeyInformationClass
0x18000569d  call    cs:__imp_NtQueryKey
0x1800056a3  mov     r15d, eax
0x1800056a6  cmp     eax, 0C0000023h
0x1800056ab  jnz     short loc_180005708
0x1800056ad  mov     ebx, [rsp+0C8h+var_98]
0x1800056b1  add     rbx, 2
0x1800056b5  mov     rcx, rbx; unsigned __int64
0x1800056b8  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x1800056bd  mov     r13, rax
0x1800056c0  test    rax, rax
0x1800056c3  jnz     short loc_1800056D9
0x1800056c5  mov     rdx, rbp
0x1800056c8  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800056cf  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800056d4  jmp     loc_180005834
0x1800056d9  mov     r8, rbx; Size
0x1800056dc  xor     edx, edx; Val
0x1800056de  mov     rcx, r13; void *
0x1800056e1  call    memset_0
0x1800056e6  mov     rcx, [rdi+20h]; KeyHandle
0x1800056ea  lea     rax, [rsp+0C8h+var_98]
0x1800056ef  mov     r9d, ebx; Length
0x1800056f2  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x1800056f7  mov     r8, r13; KeyInformation
0x1800056fa  mov     edx, 3; KeyInformationClass
0x1800056ff  call    cs:__imp_NtQueryKey
0x180005705  mov     r15d, eax
0x180005708  test    r15d, r15d
0x18000570b  jns     short loc_18000572B
0x18000570d  mov     r9d, r15d
0x180005710  lea     r8, aNtquerykey; "NtQueryKey"
0x180005717  mov     rdx, rbp
0x18000571a  lea     rcx, aSSFailedWithNt; "%s: %s failed with NTSTATUS: 0x%08x."
0x180005721  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005726  jmp     loc_180005834
0x18000572b  lea     rbx, [r13+4]
0x18000572f  jmp     short loc_18000573C
0x180005731  mov     rcx, r12; HKEY
0x180005734  call    ?GetPredefinedRegistryHandlePath@RegistryPath@@CAPEBGPEAUHKEY__@@@Z; RegistryPath::GetPredefinedRegistryHandlePath(HKEY__ *)
0x180005739  mov     rbx, rax
0x18000573c  test    rbx, rbx
0x18000573f  jz      short loc_1800057AC
0x180005741  mov     r8d, 11h; MaxCount
0x180005747  lea     rdx, aRegistryMachin; "\\Registry\\Machine"
0x18000574e  mov     rcx, rbx; String1
0x180005751  call    _wcsnicmp
0x180005756  test    eax, eax
0x180005758  jnz     short loc_180005774
0x18000575a  lea     r14, [rbx+22h]
0x18000575e  cmp     word ptr [r14], 5Ch ; '\'
0x180005763  jz      short loc_18000576B
0x180005765  cmp     [r14], si
0x180005769  jnz     short loc_180005774
0x18000576b  lea     rbx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x180005772  jmp     short loc_1800057AF
0x180005774  test    rbx, rbx
0x180005777  jz      short loc_1800057AC
0x180005779  mov     r8d, 0Eh; MaxCount
0x18000577f  lea     rdx, aRegistryUser; "\\Registry\\User"
0x180005786  mov     rcx, rbx; String1
0x180005789  call    _wcsnicmp
0x18000578e  test    eax, eax
0x180005790  jnz     short loc_1800057AC
0x180005792  lea     r14, [rbx+1Ch]
0x180005796  cmp     word ptr [r14], 5Ch ; '\'
0x18000579b  jz      short loc_1800057A3
0x18000579d  cmp     [r14], si
0x1800057a1  jnz     short loc_1800057AC
0x1800057a3  lea     rbx, aHkeyUsers; "HKEY_USERS"
0x1800057aa  jmp     short loc_1800057AF
0x1800057ac  mov     r14, rsi
0x1800057af  mov     rdx, rbx; unsigned __int16 *
0x1800057b2  mov     rcx, rdi; this
0x1800057b5  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x1800057ba  mov     esi, eax
0x1800057bc  test    eax, eax
0x1800057be  jnz     short loc_180005803
0x1800057c0  mov     rcx, r14; unsigned __int16 *
0x1800057c3  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800057c8  test    eax, eax
0x1800057ca  jnz     short loc_1800057DD
0x1800057cc  mov     rdx, r14; unsigned __int16 *
0x1800057cf  mov     rcx, rdi; this
0x1800057d2  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x1800057d7  mov     esi, eax
0x1800057d9  test    eax, eax
0x1800057db  jnz     short loc_180005803
0x1800057dd  mov     rdx, [rdi+8]; MaxCount
0x1800057e1  xor     ebx, ebx
0x1800057e3  mov     rcx, [rdi]; Source
0x1800057e6  call    cs:__imp_wcsnlen
0x1800057ec  mov     rdx, [rsp+0C8h+var_90]; unsigned __int16 *
0x1800057f1  mov     rcx, rdi; this
0x1800057f4  mov     [rdi+18h], rax
0x1800057f8  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x1800057fd  mov     esi, eax
0x1800057ff  test    eax, eax
0x180005801  jz      short loc_18000582D
0x180005803  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18000580a  mov     rdx, rbp
0x18000580d  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x180005814  mov     r9d, esi
0x180005817  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000581c  test    esi, esi
0x18000581e  jg      short loc_180005824
0x180005820  mov     ebx, esi
0x180005822  jmp     short loc_18000582D
0x180005824  movzx   ebx, si
0x180005827  or      ebx, 80070000h
0x18000582d  xor     esi, esi
0x18000582f  test    r15d, r15d
0x180005832  jz      short loc_18000583B
0x180005834  mov     ebx, r15d
0x180005837  bts     ebx, 1Ch
0x18000583b  test    ebx, ebx
0x18000583d  jns     short loc_180005851
0x18000583f  cmp     [rdi+20h], r12
0x180005843  jnz     short loc_180005849
0x180005845  mov     [rdi+20h], rsi
0x180005849  mov     rcx, rdi; this
0x18000584c  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x180005851  mov     rcx, r13; lpMem
0x180005854  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180005859  mov     r8d, ebx
0x18000585c  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180005863  mov     rdx, rbp
0x180005866  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000586b  mov     eax, ebx
0x18000586d  mov     rcx, [rsp+0C8h+var_58]
0x180005872  xor     rcx, rsp; StackCookie
0x180005875  call    __security_check_cookie
0x18000587a  add     rsp, 88h
0x180005881  pop     r15
0x180005883  pop     r14
0x180005885  pop     r13
0x180005887  pop     r12
0x180005889  pop     rdi
0x18000588a  pop     rsi
0x18000588b  pop     rbp
0x18000588c  pop     rbx
0x18000588d  retn
```
