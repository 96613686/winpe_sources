# RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18000e5d4`
- end: `0x18000e8e2`
- name: `?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `782`
- prototype: `__int64 __fastcall(RegistryPath *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e4e0`
- `0x18002b1a0`

## callees

- `0x1800073c0`
- `0x18000a178`
- `0x18000c160`
- `0x18000c190`
- `0x18000ced0`
- `0x18000db54`
- `0x18000e5d4`
- `0x180027448`
- `0x1800274cc`
- `0x18002bc58`
- `0x18002e850`
- `0x180046984`
- `0x180046ae0`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000e838`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000e838`
- `ntdll!NtQueryKey` at `0x18000e725`
- `ntdll!NtQueryKey` at `0x18000e787`
- `ntdll!NtQueryKey` at `0x18000e725`
- `ntdll!NtQueryKey` at `0x18000e787`

## string_xrefs

- `0x18000e85f`: `RegistryPath::Append`
- `0x18000e61d`: `RegistryPath::Initialize`
- `0x18000e6be`: `RegistryPath::Initialize`
- `0x18000e692`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000e68b`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18000e6d0`: `%s: Root path is empty. Retrieve path using the root key handle.`
- `0x18000e7c4`: `\Registry\Machine`
- `0x18000e7e4`: `\Registry\User`

## pseudocode

```c
__int64 __fastcall RegistryPath::Initialize(
        RegistryPath *this,
        HKEY a2,
        const unsigned __int16 *PredefinedRegistryHandlePath,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // r13
  int v8; // ebx
  __int64 v9; // r8
  unsigned int v10; // eax
  NTSTATUS v11; // r14d
  void *v12; // rcx
  __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r12
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // rax
  int v18; // ebp
  size_t v19; // rax
  unsigned __int16 *v20; // rdx
  ULONG ResultLength; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int16 *v23; // [rsp+38h] [rbp-90h]
  _BYTE v24[16]; // [rsp+40h] [rbp-88h] BYREF
  const wchar_t *v25; // [rsp+50h] [rbp-78h]
  __int64 v26; // [rsp+58h] [rbp-70h]
  const wchar_t *v27; // [rsp+60h] [rbp-68h]
  __int64 v28; // [rsp+68h] [rbp-60h]

  v4 = 0;
  v23 = a4;
  if ( a2 )
  {
    v11 = 0;
    RegistryPath::Reset(this);
    *((_QWORD *)this + 4) = a2;
    if ( (unsigned int)IsEmptyString(PredefinedRegistryHandlePath) )
    {
      Logger::TraceVerbose(
        L"%s: Root path is empty. Retrieve path using the root key handle.",
        L"RegistryPath::Initialize");
      if ( a2 == HKEY_PERFORMANCE_TEXT || (unsigned __int64)(a2 + 0x20000000) <= 7 || a2 == HKEY_PERFORMANCE_NLSTEXT )
      {
        PredefinedRegistryHandlePath = RegistryPath::GetPredefinedRegistryHandlePath(a2);
      }
      else
      {
        v12 = (void *)*((_QWORD *)this + 4);
        ResultLength = 0;
        v11 = NtQueryKey(v12, KeyNameInformation, 0, 0, &ResultLength);
        if ( v11 == -1073741789 )
        {
          v13 = ResultLength + 2LL;
          v14 = (unsigned __int16 *)MIDL_user_allocate(v13);
          v4 = v14;
          if ( !v14 )
          {
            Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistryPath::Initialize");
            goto LABEL_29;
          }
          memset_0(v14, 0, v13);
          v11 = NtQueryKey(*((HANDLE *)this + 4), KeyNameInformation, v4, v13, &ResultLength);
        }
        if ( v11 < 0 )
        {
          Logger::TraceError(
            L"%s: %s failed with NTSTATUS: 0x%08x.",
            L"RegistryPath::Initialize",
            L"NtQueryKey",
            (unsigned int)v11);
          goto LABEL_29;
        }
        PredefinedRegistryHandlePath = v4 + 2;
      }
    }
    v15 = SplitPath(PredefinedRegistryHandlePath, L"\\Registry\\Machine");
    if ( v15 )
    {
      v16 = L"HKEY_LOCAL_MACHINE";
    }
    else
    {
      v17 = SplitPath(PredefinedRegistryHandlePath, L"\\Registry\\User");
      v16 = L"HKEY_USERS";
      v15 = v17;
      if ( !v17 )
        v16 = PredefinedRegistryHandlePath;
    }
    v18 = RegistryPath::Append(this, v16);
    if ( v18
      || !(unsigned int)IsEmptyString(v15) && (v18 = RegistryPath::Append(this, v15)) != 0
      || (v8 = 0,
          v19 = wcsnlen(*(const wchar_t **)this, *((_QWORD *)this + 1)),
          v20 = v23,
          *((_QWORD *)this + 3) = v19,
          (v18 = RegistryPath::Append(this, v20)) != 0) )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"RegistryPath::Initialize",
        L"RegistryPath::Append",
        (unsigned int)v18);
      if ( v18 > 0 )
        v8 = (unsigned __int16)v18 | 0x80070000;
      else
        v8 = v18;
    }
    if ( !v11 )
    {
LABEL_30:
      if ( v8 >= 0 )
        goto LABEL_34;
      goto LABEL_31;
    }
LABEL_29:
    v8 = v11 | 0x10000000;
    goto LABEL_30;
  }
  v8 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistryPath::Initialize", L"rootKey");
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v25 = L"RegistryPath::Initialize";
    v26 = 50;
    v27 = L"rootKey";
    v28 = 16;
    v10 = McGenEventWrite_EventWriteTransfer(
            &UserDeviceRegistrationEventProvider_Context,
            NullOrEmptyParameterFailureEvent,
            v9,
            3,
            v24);
    if ( v10 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v10);
  }
LABEL_31:
  if ( *((HKEY *)this + 4) == a2 )
    *((_QWORD *)this + 4) = 0;
  RegistryPath::Reset(this);
LABEL_34:
  SafeFree(v4);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistryPath::Initialize", (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000e5d4  push    rbx
0x18000e5d6  push    rbp
0x18000e5d7  push    rsi
0x18000e5d8  push    rdi
0x18000e5d9  push    r12
0x18000e5db  push    r13
0x18000e5dd  push    r14
0x18000e5df  push    r15
0x18000e5e1  sub     rsp, 88h
0x18000e5e8  mov     rax, cs:__security_cookie
0x18000e5ef  xor     rax, rsp
0x18000e5f2  mov     [rsp+0C8h+var_58], rax
0x18000e5f7  xor     r13d, r13d
0x18000e5fa  mov     [rsp+0C8h+var_90], r9
0x18000e5ff  mov     rbx, r8
0x18000e602  mov     r15, rdx
0x18000e605  mov     rdi, rcx
0x18000e608  test    rdx, rdx
0x18000e60b  jnz     loc_18000E6AA
0x18000e611  lea     rbp, aRootkey; "rootKey"
0x18000e618  mov     ebx, 80070057h
0x18000e61d  lea     rsi, aRegistrypathIn_0; "RegistryPath::Initialize"
0x18000e624  mov     r8, rbp
0x18000e627  mov     rdx, rsi
0x18000e62a  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000e631  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e636  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000e63d  jz      loc_18000E88F
0x18000e643  lea     rax, [rsp+0C8h+var_88]
0x18000e648  mov     [rsp+0C8h+var_78], rsi
0x18000e64d  lea     r9d, [r15+3]
0x18000e651  mov     [rsp+0C8h+ResultLength], rax
0x18000e656  lea     rdx, NullOrEmptyParameterFailureEvent
0x18000e65d  mov     [rsp+0C8h+var_70], 32h ; '2'
0x18000e666  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000e66d  mov     [rsp+0C8h+var_68], rbp
0x18000e672  mov     [rsp+0C8h+var_60], 10h
0x18000e67b  call    McGenEventWrite_EventWriteTransfer
0x18000e680  test    eax, eax
0x18000e682  jz      loc_18000E88F
0x18000e688  mov     r9d, eax
0x18000e68b  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18000e692  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000e699  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000e6a0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e6a5  jmp     loc_18000E88F
0x18000e6aa  xor     r14d, r14d
0x18000e6ad  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18000e6b2  mov     rcx, rbx; unsigned __int16 *
0x18000e6b5  mov     [rdi+20h], r15
0x18000e6b9  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000e6be  lea     rsi, aRegistrypathIn_0; "RegistryPath::Initialize"
0x18000e6c5  test    eax, eax
0x18000e6c7  jz      loc_18000E7C4
0x18000e6cd  mov     rdx, rsi
0x18000e6d0  lea     rcx, aSRootPathIsEmp; "%s: Root path is empty. Retrieve path u"...
0x18000e6d7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000e6dc  cmp     r15, 0FFFFFFFF80000050h
0x18000e6e3  jz      loc_18000E7B9
0x18000e6e9  mov     eax, 80000000h
0x18000e6ee  add     rax, r15
0x18000e6f1  cmp     rax, 7
0x18000e6f5  jbe     loc_18000E7B9
0x18000e6fb  cmp     r15, 0FFFFFFFF80000060h
0x18000e702  jz      loc_18000E7B9
0x18000e708  mov     rcx, [rdi+20h]; KeyHandle
0x18000e70c  lea     rax, [rsp+0C8h+var_98]
0x18000e711  xor     r9d, r9d; Length
0x18000e714  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18000e719  xor     r8d, r8d; KeyInformation
0x18000e71c  mov     [rsp+0C8h+var_98], r13d
0x18000e721  lea     edx, [r14+3]; KeyInformationClass
0x18000e725  call    cs:__imp_NtQueryKey
0x18000e72b  mov     r14d, eax
0x18000e72e  cmp     eax, 0C0000023h
0x18000e733  jnz     short loc_18000E790
0x18000e735  mov     ebx, [rsp+0C8h+var_98]
0x18000e739  add     rbx, 2
0x18000e73d  mov     rcx, rbx; size
0x18000e740  call    MIDL_user_allocate
0x18000e745  mov     r13, rax
0x18000e748  test    rax, rax
0x18000e74b  jnz     short loc_18000E761
0x18000e74d  mov     rdx, rsi
0x18000e750  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000e757  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000e75c  jmp     loc_18000E884
0x18000e761  mov     r8, rbx; Size
0x18000e764  xor     edx, edx; Val
0x18000e766  mov     rcx, r13; void *
0x18000e769  call    memset_0
0x18000e76e  mov     rcx, [rdi+20h]; KeyHandle
0x18000e772  lea     rax, [rsp+0C8h+var_98]
0x18000e777  mov     r9d, ebx; Length
0x18000e77a  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18000e77f  mov     r8, r13; KeyInformation
0x18000e782  mov     edx, 3; KeyInformationClass
0x18000e787  call    cs:__imp_NtQueryKey
0x18000e78d  mov     r14d, eax
0x18000e790  test    r14d, r14d
0x18000e793  jns     short loc_18000E7B3
0x18000e795  mov     r9d, r14d
0x18000e798  lea     r8, aNtquerykey; "NtQueryKey"
0x18000e79f  mov     rdx, rsi
0x18000e7a2  lea     rcx, aSSFailedWithNt; "%s: %s failed with NTSTATUS: 0x%08x."
0x18000e7a9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e7ae  jmp     loc_18000E884
0x18000e7b3  lea     rbx, [r13+4]
0x18000e7b7  jmp     short loc_18000E7C4
0x18000e7b9  mov     rcx, r15; HKEY
0x18000e7bc  call    ?GetPredefinedRegistryHandlePath@RegistryPath@@CAPEBGPEAUHKEY__@@@Z; RegistryPath::GetPredefinedRegistryHandlePath(HKEY__ *)
0x18000e7c1  mov     rbx, rax
0x18000e7c4  lea     rdx, aRegistryMachin; "\\Registry\\Machine"
0x18000e7cb  mov     rcx, rbx; unsigned __int16 *
0x18000e7ce  call    ?SplitPath@@YAPEBGPEBG0@Z; SplitPath(ushort const *,ushort const *)
0x18000e7d3  mov     r12, rax
0x18000e7d6  test    rax, rax
0x18000e7d9  jz      short loc_18000E7E4
0x18000e7db  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x18000e7e2  jmp     short loc_18000E804
0x18000e7e4  lea     rdx, aRegistryUser; "\\Registry\\User"
0x18000e7eb  mov     rcx, rbx; unsigned __int16 *
0x18000e7ee  call    ?SplitPath@@YAPEBGPEBG0@Z; SplitPath(ushort const *,ushort const *)
0x18000e7f3  test    rax, rax
0x18000e7f6  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x18000e7fd  mov     r12, rax
0x18000e800  cmovz   rdx, rbx; unsigned __int16 *
0x18000e804  mov     rcx, rdi; this
0x18000e807  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18000e80c  mov     ebp, eax
0x18000e80e  test    eax, eax
0x18000e810  jnz     short loc_18000E855
0x18000e812  mov     rcx, r12; unsigned __int16 *
0x18000e815  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000e81a  test    eax, eax
0x18000e81c  jnz     short loc_18000E82F
0x18000e81e  mov     rdx, r12; unsigned __int16 *
0x18000e821  mov     rcx, rdi; this
0x18000e824  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18000e829  mov     ebp, eax
0x18000e82b  test    eax, eax
0x18000e82d  jnz     short loc_18000E855
0x18000e82f  mov     rdx, [rdi+8]; MaxCount
0x18000e833  xor     ebx, ebx
0x18000e835  mov     rcx, [rdi]; Source
0x18000e838  call    cs:__imp_wcsnlen
0x18000e83e  mov     rdx, [rsp+0C8h+var_90]; unsigned __int16 *
0x18000e843  mov     rcx, rdi; this
0x18000e846  mov     [rdi+18h], rax
0x18000e84a  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18000e84f  mov     ebp, eax
0x18000e851  test    eax, eax
0x18000e853  jz      short loc_18000E87F
0x18000e855  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000e85c  mov     rdx, rsi
0x18000e85f  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x18000e866  mov     r9d, ebp
0x18000e869  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e86e  test    ebp, ebp
0x18000e870  jg      short loc_18000E876
0x18000e872  mov     ebx, ebp
0x18000e874  jmp     short loc_18000E87F
0x18000e876  movzx   ebx, bp
0x18000e879  or      ebx, 80070000h
0x18000e87f  test    r14d, r14d
0x18000e882  jz      short loc_18000E88B
0x18000e884  mov     ebx, r14d
0x18000e887  bts     ebx, 1Ch
0x18000e88b  test    ebx, ebx
0x18000e88d  jns     short loc_18000E8A5
0x18000e88f  cmp     [rdi+20h], r15
0x18000e893  jnz     short loc_18000E89D
0x18000e895  mov     qword ptr [rdi+20h], 0
0x18000e89d  mov     rcx, rdi; this
0x18000e8a0  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18000e8a5  mov     rcx, r13; lpMem
0x18000e8a8  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000e8ad  mov     r8d, ebx
0x18000e8b0  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000e8b7  mov     rdx, rsi
0x18000e8ba  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000e8bf  mov     eax, ebx
0x18000e8c1  mov     rcx, [rsp+0C8h+var_58]
0x18000e8c6  xor     rcx, rsp; StackCookie
0x18000e8c9  call    __security_check_cookie
0x18000e8ce  add     rsp, 88h
0x18000e8d5  pop     r15
0x18000e8d7  pop     r14
0x18000e8d9  pop     r13
0x18000e8db  pop     r12
0x18000e8dd  pop     rdi
0x18000e8de  pop     rsi
0x18000e8df  pop     rbp
0x18000e8e0  pop     rbx
0x18000e8e1  retn
```
