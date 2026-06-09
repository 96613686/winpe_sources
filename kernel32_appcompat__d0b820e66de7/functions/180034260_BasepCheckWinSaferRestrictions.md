# BasepCheckWinSaferRestrictions

- ea: `0x180034260`
- end: `0x180034c8a`
- name: `BasepCheckWinSaferRestrictions`
- size: `2602`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180034260`
- `0x180082751`
- `0x18008275d`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x1800344c1`
- `ntdll!NtQueryValueKey` at `0x1800344fd`
- `ntdll!NtQueryValueKey` at `0x180034a36`
- `ntdll!NtQueryValueKey` at `0x180034b83`
- `ntdll!NtQueryValueKey` at `0x1800344c1`
- `ntdll!NtQueryValueKey` at `0x1800344fd`
- `ntdll!NtQueryValueKey` at `0x180034a36`
- `ntdll!NtQueryValueKey` at `0x180034b83`
- `ntdll!RtlEqualSid` at `0x180034700`
- `ntdll!RtlEqualSid` at `0x180034737`
- `ntdll!RtlEqualSid` at `0x18003476e`
- `ntdll!RtlEqualSid` at `0x180034700`
- `ntdll!RtlEqualSid` at `0x180034737`
- `ntdll!RtlEqualSid` at `0x18003476e`
- `ntdll!NtOpenThreadToken` at `0x180034381`
- `ntdll!NtOpenThreadToken` at `0x180034381`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180034565`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180034565`
- `ntdll!NtQueryInformationToken` at `0x180034423`
- `ntdll!NtQueryInformationToken` at `0x180034423`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003432b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003432b`
- `ntdll!LdrLoadDll` at `0x1800347ac`
- `ntdll!LdrLoadDll` at `0x1800347ac`
- `ntdll!NtSetInformationThread` at `0x180034a9f`
- `ntdll!NtSetInformationThread` at `0x180034b03`
- `ntdll!NtSetInformationThread` at `0x180034a9f`
- `ntdll!NtSetInformationThread` at `0x180034b03`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800346b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800346b0`
- `ntdll!LdrUnloadDll` at `0x180034bd5`
- `ntdll!LdrUnloadDll` at `0x180034bd5`
- `ntdll!NtOpenKey` at `0x180034452`
- `ntdll!NtOpenKey` at `0x180034485`
- `ntdll!NtOpenKey` at `0x18003462f`
- `ntdll!NtOpenKey` at `0x180034452`
- `ntdll!NtOpenKey` at `0x180034485`
- `ntdll!NtOpenKey` at `0x18003462f`
- `ntdll!RtlAppendUnicodeToString` at `0x1800345ee`
- `ntdll!RtlAppendUnicodeToString` at `0x1800345ee`
- `ntdll!RtlSubAuthoritySid` at `0x1800346e3`
- `ntdll!RtlSubAuthoritySid` at `0x18003471a`
- `ntdll!RtlSubAuthoritySid` at `0x180034751`
- `ntdll!RtlSubAuthoritySid` at `0x1800346e3`
- `ntdll!RtlSubAuthoritySid` at `0x18003471a`
- `ntdll!RtlSubAuthoritySid` at `0x180034751`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800345d2`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800345d2`
- `ntdll!LdrGetProcedureAddress` at `0x1800347d6`
- `ntdll!LdrGetProcedureAddress` at `0x18003480d`
- `ntdll!LdrGetProcedureAddress` at `0x180034844`
- `ntdll!LdrGetProcedureAddress` at `0x18003487b`
- `ntdll!LdrGetProcedureAddress` at `0x1800347d6`
- `ntdll!LdrGetProcedureAddress` at `0x18003480d`
- `ntdll!LdrGetProcedureAddress` at `0x180034844`
- `ntdll!LdrGetProcedureAddress` at `0x18003487b`
- `ntdll!RtlInitializeSid` at `0x1800346d1`
- `ntdll!RtlInitializeSid` at `0x1800346d1`
- `ntdll!NtOpenProcessToken` at `0x1800343ad`
- `ntdll!NtOpenProcessToken` at `0x180034ade`
- `ntdll!NtOpenProcessToken` at `0x1800343ad`
- `ntdll!NtOpenProcessToken` at `0x180034ade`
- `ntdll!NtClose` at `0x18003452e`
- `ntdll!NtClose` at `0x180034694`
- `ntdll!NtClose` at `0x180034967`
- `ntdll!NtClose` at `0x180034a49`
- `ntdll!NtClose` at `0x180034aba`
- `ntdll!NtClose` at `0x180034b16`
- `ntdll!NtClose` at `0x18003452e`
- `ntdll!NtClose` at `0x180034694`
- `ntdll!NtClose` at `0x180034967`
- `ntdll!NtClose` at `0x180034a49`
- `ntdll!NtClose` at `0x180034aba`
- `ntdll!NtClose` at `0x180034b16`
- `ntdll!RtlFreeUnicodeString` at `0x180034668`
- `ntdll!RtlFreeUnicodeString` at `0x180034668`
- `ntdll!RtlFreeHeap` at `0x180034657`
- `ntdll!RtlFreeHeap` at `0x180034c79`
- `ntdll!RtlFreeHeap` at `0x180034657`
- `ntdll!RtlFreeHeap` at `0x180034c79`
- `ntdll!RtlAllocateHeap` at `0x1800345ae`
- `ntdll!RtlAllocateHeap` at `0x1800349b9`
- `ntdll!RtlAllocateHeap` at `0x1800345ae`
- `ntdll!RtlAllocateHeap` at `0x1800349b9`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003458d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003458d`

## pseudocode

```c
__int64 __fastcall BasepCheckWinSaferRestrictions(HANDLE TokenHandle, _WORD *a2, __int64 a3, const void **a4)
{
  BOOL v8; // ebx
  unsigned __int64 v10; // rax
  void *v11; // r14
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  bool v14; // bl
  ULONG *GlobalData; // rax
  PVOID Heap; // rax
  NTSTATUS v17; // ebx
  NTSTATUS v18; // edi
  ULONG LastErrorValue; // edi
  ULONG LoadFlags; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandlea; // [rsp+40h] [rbp-C0h] BYREF
  PVOID BaseAddress; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+B0h] [rbp-50h] BYREF
  int v30; // [rsp+B4h] [rbp-4Ch]
  _WORD *v31; // [rsp+B8h] [rbp-48h]
  __int64 v32; // [rsp+C0h] [rbp-40h]
  int v33; // [rsp+130h] [rbp+30h]
  void *v34; // [rsp+138h] [rbp+38h]
  _BYTE KeyValueInformation[4]; // [rsp+160h] [rbp+60h] BYREF
  int v36; // [rsp+164h] [rbp+64h]
  int v37; // [rsp+168h] [rbp+68h]
  int v38; // [rsp+16Ch] [rbp+6Ch]
  PSID TokenInformation[18]; // [rsp+1E0h] [rbp+E0h] BYREF

  memset_0(&v29, 0, 0xB0u);
  v24 = 0;
  Handle = 0;
  TokenHandlea = 0;
  if ( a2 && *a2 )
  {
    v8 = 0;
    if ( a4 && *(_WORD *)a4 )
      v8 = NtCurrentTeb()->IsImpersonating != 0;
    if ( qword_1800BD308 == -2 && !v8 )
      return 0;
    RtlAcquireSRWLockExclusive(&gsrwlAppCert);
    v10 = qword_1800BD308;
    if ( qword_1800BD308 )
    {
      if ( qword_1800BD308 == -2 && !v8 )
        goto LABEL_77;
      v11 = 0;
      if ( TokenHandle )
      {
LABEL_22:
        if ( v10 >= 0xFFFFFFFFFFFFFFFEuLL )
        {
          BaseAddress = 0;
          LoadFlags = 0;
          if ( NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x90u, &LoadFlags) >= 0 )
          {
            RtlInitializeSid(KeyValueInformation, (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority, 1u);
            *RtlSubAuthoritySid(KeyValueInformation, 0) = 18;
            if ( RtlEqualSid(TokenInformation[0], KeyValueInformation) )
              goto LABEL_41;
            *RtlSubAuthoritySid(KeyValueInformation, 0) = 19;
            if ( RtlEqualSid(TokenInformation[0], KeyValueInformation) )
              goto LABEL_41;
            *RtlSubAuthoritySid(KeyValueInformation, 0) = 20;
            if ( RtlEqualSid(TokenInformation[0], KeyValueInformation) )
              goto LABEL_41;
          }
          KeyHandle = 0;
          LoadFlags = 0;
          if ( NtOpenKey(&KeyHandle, 3u, (POBJECT_ATTRIBUTES)&::ObjectAttributes) >= 0 )
          {
            v17 = NtQueryValueKey(
                    KeyHandle,
                    (PUNICODE_STRING)&stru_1800857A0,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x50u,
                    &LoadFlags);
            NtClose(KeyHandle);
            if ( v17 >= 0 && v36 == 4 && v37 == 4 && v38 )
              goto LABEL_40;
          }
          KeyHandle = 0;
          LoadFlags = 0;
          v14 = 0;
          if ( NtOpenKey(&KeyHandle, 1u, (POBJECT_ATTRIBUTES)&stru_180085700) < 0 )
            goto LABEL_108;
          if ( NtQueryValueKey(
                 KeyHandle,
                 (PUNICODE_STRING)&stru_180085740,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0x50u,
                 &LoadFlags) >= 0
            && v36 == 4
            && v37 == 4 )
          {
            v14 = v38 != 0;
          }
          if ( NtQueryValueKey(
                 KeyHandle,
                 (PUNICODE_STRING)&stru_180085730,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0x50u,
                 &LoadFlags) >= 0
            && v38
            && v36 == 4
            && v37 == 4 )
          {
            dword_1800BDAF8 = 8;
          }
          NtClose(KeyHandle);
          if ( !v14 )
          {
LABEL_108:
            KeyPath = 0;
            Destination = 0;
            memset(&ObjectAttributes, 0, 44);
            if ( RtlFormatCurrentUserKeyPath(&KeyPath) < 0 )
              goto LABEL_40;
            Destination.Length = 0;
            Destination.MaximumLength = KeyPath.Length + 120;
            GlobalData = (ULONG *)KernelBaseGetGlobalData();
            Destination.Buffer = (PWSTR)RtlAllocateHeap(
                                          NtCurrentPeb()->ProcessHeap,
                                          *GlobalData,
                                          Destination.MaximumLength);
            if ( Destination.Buffer )
            {
              if ( RtlAppendUnicodeStringToString(&Destination, &KeyPath) >= 0
                && RtlAppendUnicodeToString(
                     &Destination,
                     L"\\Software\\Policies\\Microsoft\\Windows\\Safer\\CodeIdentifiers") >= 0 )
              {
                ObjectAttributes.Length = 48;
                ObjectAttributes.ObjectName = &Destination;
                ObjectAttributes.RootDirectory = 0;
                ObjectAttributes.Attributes = 64;
                *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                if ( NtOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0
                  && NtQueryValueKey(
                       KeyHandle,
                       (PUNICODE_STRING)&stru_180085740,
                       KeyValuePartialInformation,
                       KeyValueInformation,
                       0x50u,
                       &LoadFlags) >= 0
                  && v36 == 4
                  && v37 == 4
                  && v38 )
                {
                  v14 = 1;
                }
              }
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
            }
            RtlFreeUnicodeString(&KeyPath);
            if ( !v14 )
            {
LABEL_40:
              qword_1800BD308 = -2;
LABEL_41:
              v13 = 0;
LABEL_42:
              if ( Handle )
                NtClose(Handle);
              if ( v11 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
              goto LABEL_46;
            }
          }
          LoadFlags = 4096;
          if ( LdrLoadDll(0, &LoadFlags, (PUNICODE_STRING)&stru_180085750, &BaseAddress) < 0 )
          {
            v13 = -1073741511;
            qword_1800BD308 = 0;
            goto LABEL_42;
          }
          if ( LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180085780, 0, &ProcedureAddress) < 0
            || !ProcedureAddress
            || LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180085790, 0, &qword_1800BDDE0) < 0
            || !qword_1800BDDE0
            || LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180085770, 0, &qword_1800BDDF0) < 0
            || !qword_1800BDDF0
            || LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180085760, 0, &qword_1800BDDD8) < 0
            || !qword_1800BDDD8 )
          {
            LdrUnloadDll(BaseAddress);
            qword_1800BD308 = 0;
            v13 = -1073741511;
            goto LABEL_42;
          }
          qword_1800BD308 = (__int64)BaseAddress;
        }
        memset_0(&v29, 0, 0xB0u);
        v29 = 176;
        v31 = a2;
        v33 = 2;
        if ( a4 && *(_WORD *)a4 )
        {
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned __int16 *)a4 + 2LL);
          v11 = Heap;
          if ( !Heap )
          {
            v13 = -1073741801;
            goto LABEL_42;
          }
          memcpy_0(Heap, a4[1], *(unsigned __int16 *)a4);
          *((_WORD *)v11 + ((unsigned __int64)*(unsigned __int16 *)a4 >> 1)) = 0;
          v30 = 33;
          v32 = 0;
          v34 = v11;
        }
        else
        {
          v32 = a3;
          v30 = dword_1800BDAF8 | 5;
        }
        v13 = -1073741790;
        if ( (unsigned int)((__int64 (__fastcall *)(__int64, int *, __int64 *, const wchar_t *))ProcedureAddress)(
                             1,
                             &v29,
                             &v24,
                             L"IGNORESRPV2") )
        {
          KeyHandle = 0;
          if ( (unsigned int)((__int64 (__fastcall *)(__int64, HANDLE, void **, __int64, _QWORD))qword_1800BDDF0)(
                               v24,
                               TokenHandle,
                               &KeyHandle,
                               1,
                               0) )
          {
            if ( KeyHandle )
            {
              ((void (__fastcall *)(__int64, _WORD *, _QWORD))qword_1800BDDD8)(v24, a2, 0);
              NtClose(KeyHandle);
              v13 = -1073740959;
            }
            else
            {
              v13 = 0;
            }
          }
          else
          {
            LastErrorValue = NtCurrentTeb()->LastErrorValue;
            if ( LastErrorValue == 1260 || LastErrorValue == 786 )
            {
              ((void (__fastcall *)(__int64, _WORD *, _QWORD))qword_1800BDDD8)(v24, a2, 0);
              v13 = -1073740959;
              if ( LastErrorValue == 786 )
                v13 = -1073740942;
            }
          }
          ((void (__fastcall *)(__int64))qword_1800BDDE0)(v24);
        }
        goto LABEL_42;
      }
      if ( NtCurrentTeb()->IsImpersonating
        && (v12 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, &TokenHandlea),
            v13 = v12,
            v12 != -1073741700) )
      {
        if ( v12 < 0 )
          goto LABEL_46;
        KeyHandle = 0;
        v13 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &KeyHandle, 8u);
        if ( v13 < 0 )
        {
          NtClose(TokenHandlea);
          TokenHandlea = 0;
          goto LABEL_46;
        }
      }
      else
      {
        TokenHandlea = 0;
      }
      v13 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xAu, &Handle);
      if ( v13 == -1073741790 )
        v13 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &Handle);
      if ( v13 < 0 )
        Handle = 0;
      if ( TokenHandlea )
      {
        v18 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandlea, 8u);
        NtClose(TokenHandlea);
        TokenHandlea = 0;
        if ( v18 < 0 )
        {
          v13 = v18;
          goto LABEL_42;
        }
      }
      if ( v13 >= 0 )
      {
        TokenHandle = Handle;
        v10 = qword_1800BD308;
        goto LABEL_22;
      }
      if ( qword_1800BD308 == -1 )
      {
        qword_1800BD308 = -2;
LABEL_77:
        v13 = 0;
      }
    }
    else
    {
      v13 = -1073741511;
    }
LABEL_46:
    RtlReleaseSRWLockExclusive(&gsrwlAppCert);
    return (unsigned int)v13;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180034260  push    rbp
0x180034262  push    rbx
0x180034263  push    rsi
0x180034264  push    rdi
0x180034265  push    r12
0x180034267  push    r13
0x180034269  push    r14
0x18003426b  push    r15
0x18003426d  lea     rbp, [rsp-188h]
0x180034275  sub     rsp, 288h
0x18003427c  mov     rax, cs:__security_cookie
0x180034283  xor     rax, rsp
0x180034286  mov     [rbp+1C0h+var_50], rax
0x18003428d  mov     r12, r8
0x180034290  mov     r15, rdx
0x180034293  mov     rdi, rcx
0x180034296  xor     edx, edx; Val
0x180034298  mov     r8d, 0B0h; Size
0x18003429e  lea     rcx, [rbp+1C0h+var_210]; void *
0x1800342a2  mov     rsi, r9
0x1800342a5  call    memset_0
0x1800342aa  xor     r13d, r13d
0x1800342ad  mov     [rsp+2C0h+var_270], r13
0x1800342b2  mov     [rsp+2C0h+Handle], r13
0x1800342b7  mov     [rsp+2C0h+TokenHandle], r13
0x1800342bc  test    r15, r15
0x1800342bf  jz      loc_180034787
0x1800342c5  cmp     [r15], r13w
0x1800342c9  jz      loc_180034787
0x1800342cf  lea     ecx, [r13+1]
0x1800342d3  mov     ebx, r13d
0x1800342d6  test    rsi, rsi
0x1800342d9  jnz     short loc_18003430F
0x1800342db  cmp     cs:qword_1800BD308, 0FFFFFFFFFFFFFFFEh
0x1800342e3  jnz     short loc_180034324
0x1800342e5  test    ebx, ebx
0x1800342e7  jnz     short loc_180034324
0x1800342e9  xor     eax, eax
0x1800342eb  mov     rcx, [rbp+1C0h+var_50]
0x1800342f2  xor     rcx, rsp; StackCookie
0x1800342f5  call    __security_check_cookie
0x1800342fa  add     rsp, 288h
0x180034301  pop     r15
0x180034303  pop     r14
0x180034305  pop     r13
0x180034307  pop     r12
0x180034309  pop     rdi
0x18003430a  pop     rsi
0x18003430b  pop     rbx
0x18003430c  pop     rbp
0x18003430d  retn
0x18003430f  cmp     [rsi], r13w
0x180034313  jz      short loc_1800342DB
0x180034315  mov     eax, gs:179Ch
0x18003431d  test    eax, eax
0x18003431f  cmovnz  ebx, ecx
0x180034322  jmp     short loc_1800342DB
0x180034324  lea     rcx, gsrwlAppCert
0x18003432b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180034332  nop     dword ptr [rax+rax+00h]
0x180034337  mov     rax, cs:qword_1800BD308
0x18003433e  test    rax, rax
0x180034341  jz      loc_1800349DB
0x180034347  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18003434b  jz      loc_18003498E
0x180034351  mov     r14, r13
0x180034354  test    rdi, rdi
0x180034357  jnz     loc_1800343EE
0x18003435d  mov     eax, gs:179Ch
0x180034365  mov     rdi, 0FFFFFFFFFFFFFFFEh
0x18003436c  test    eax, eax
0x18003436e  jz      short loc_18003439A
0x180034370  lea     r9, [rsp+2C0h+TokenHandle]; TokenHandle
0x180034375  mov     edx, 2000000h; DesiredAccess
0x18003437a  lea     r8d, [rdi+3]; OpenAsSelf
0x18003437e  mov     rcx, rdi; ThreadHandle
0x180034381  call    cs:__imp_NtOpenThreadToken
0x180034388  nop     dword ptr [rax+rax+00h]
0x18003438d  mov     ebx, eax
0x18003438f  cmp     eax, 0C000007Ch
0x180034394  jnz     loc_180034A80
0x18003439a  mov     [rsp+2C0h+TokenHandle], r13
0x18003439f  lea     r8, [rsp+2C0h+Handle]; TokenHandle
0x1800343a4  mov     edx, 0Ah; DesiredAccess
0x1800343a9  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800343ad  call    cs:__imp_NtOpenProcessToken
0x1800343b4  nop     dword ptr [rax+rax+00h]
0x1800343b9  mov     ebx, eax
0x1800343bb  cmp     eax, 0C0000022h
0x1800343c0  jz      loc_180034AD0
0x1800343c6  test    ebx, ebx
0x1800343c8  jns     short loc_1800343CF
0x1800343ca  mov     [rsp+2C0h+Handle], r13
0x1800343cf  cmp     [rsp+2C0h+TokenHandle], r13
0x1800343d4  jnz     loc_180034AF1
0x1800343da  test    ebx, ebx
0x1800343dc  js      loc_1800349E5
0x1800343e2  mov     rdi, [rsp+2C0h+Handle]
0x1800343e7  mov     rax, cs:qword_1800BD308
0x1800343ee  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800343f2  jb      loc_1800348A8
0x1800343f8  lea     rax, [rsp+2C0h+LoadFlags]
0x1800343fd  mov     [rsp+2C0h+BaseAddress], r13
0x180034402  mov     ebx, 1
0x180034407  mov     [rsp+2C0h+LoadFlags], r13d
0x18003440c  mov     edx, ebx; TokenInformationClass
0x18003440e  mov     [rsp+2C0h+ReturnLength], rax; ReturnLength
0x180034413  mov     r9d, 90h; TokenInformationLength
0x180034419  lea     r8, [rbp+1C0h+TokenInformation]; TokenInformation
0x180034420  mov     rcx, rdi; TokenHandle
0x180034423  call    cs:__imp_NtQueryInformationToken
0x18003442a  nop     dword ptr [rax+rax+00h]
0x18003442f  test    eax, eax
0x180034431  jns     loc_1800346C3
0x180034437  lea     r8, ObjectAttributes; ObjectAttributes
0x18003443e  mov     [rsp+2C0h+KeyHandle], r13
0x180034443  mov     edx, 3; DesiredAccess
0x180034448  mov     [rsp+2C0h+LoadFlags], r13d
0x18003444d  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x180034452  call    cs:__imp_NtOpenKey
0x180034459  nop     dword ptr [rax+rax+00h]
0x18003445e  test    eax, eax
0x180034460  jns     loc_180034A0E
0x180034466  lea     r8, stru_180085700; ObjectAttributes
0x18003446d  mov     [rsp+2C0h+KeyHandle], r13
0x180034472  mov     edx, 1; DesiredAccess
0x180034477  mov     [rsp+2C0h+LoadFlags], r13d
0x18003447c  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x180034481  movzx   ebx, r13b
0x180034485  call    cs:__imp_NtOpenKey
0x18003448c  nop     dword ptr [rax+rax+00h]
0x180034491  test    eax, eax
0x180034493  js      loc_180034542
0x180034499  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x18003449e  lea     rax, [rsp+2C0h+LoadFlags]
0x1800344a3  mov     [rsp+2C0h+ResultLength], rax; ResultLength
0x1800344a8  lea     r9, [rbp+1C0h+KeyValueInformation]; KeyValueInformation
0x1800344ac  mov     r8d, 2; KeyValueInformationClass
0x1800344b2  mov     dword ptr [rsp+2C0h+ReturnLength], 50h ; 'P'; Length
0x1800344ba  lea     rdx, stru_180085740; ValueName
0x1800344c1  call    cs:__imp_NtQueryValueKey
0x1800344c8  nop     dword ptr [rax+rax+00h]
0x1800344cd  test    eax, eax
0x1800344cf  jns     loc_180034B36
0x1800344d5  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x1800344da  lea     rax, [rsp+2C0h+LoadFlags]
0x1800344df  mov     [rsp+2C0h+ResultLength], rax; ResultLength
0x1800344e4  lea     r9, [rbp+1C0h+KeyValueInformation]; KeyValueInformation
0x1800344e8  mov     r8d, 2; KeyValueInformationClass
0x1800344ee  mov     dword ptr [rsp+2C0h+ReturnLength], 50h ; 'P'; Length
0x1800344f6  lea     rdx, stru_180085730; ValueName
0x1800344fd  call    cs:__imp_NtQueryValueKey
0x180034504  nop     dword ptr [rax+rax+00h]
0x180034509  test    eax, eax
0x18003450b  js      short loc_180034529
0x18003450d  cmp     [rbp+1C0h+var_154], r13d
0x180034511  jbe     short loc_180034529
0x180034513  cmp     [rbp+1C0h+var_15C], 4
0x180034517  jnz     short loc_180034529
0x180034519  cmp     [rbp+1C0h+var_158], 4
0x18003451d  jnz     short loc_180034529
0x18003451f  mov     cs:dword_1800BDAF8, 8
0x180034529  mov     rcx, [rsp+2C0h+KeyHandle]; Handle
0x18003452e  call    cs:__imp_NtClose
0x180034535  nop     dword ptr [rax+rax+00h]
0x18003453a  test    bl, bl
0x18003453c  jnz     loc_180034791
0x180034542  xorps   xmm0, xmm0
0x180034545  lea     rcx, [rsp+2C0h+KeyPath]; KeyPath
0x18003454a  xorps   xmm1, xmm1
0x18003454d  xor     eax, eax
0x18003454f  movups  xmmword ptr [rbp+1C0h+ObjectAttributes.ObjectName], xmm0
0x180034553  movups  xmmword ptr [rbp+1C0h+ObjectAttributes+1Ch], xmm0
0x180034557  movups  xmmword ptr [rsp+2C0h+KeyPath.Length], xmm0
0x18003455c  movups  xmmword ptr [rsp+2C0h+Destination.Length], xmm1
0x180034561  movups  xmmword ptr [rbp+1C0h+ObjectAttributes.Length], xmm0
0x180034565  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18003456c  nop     dword ptr [rax+rax+00h]
0x180034571  test    eax, eax
0x180034573  js      loc_18003467C
0x180034579  movzx   eax, [rsp+2C0h+KeyPath.Length]
0x18003457e  add     ax, 78h ; 'x'
0x180034582  mov     [rsp+2C0h+Destination.Length], r13w
0x180034588  mov     [rsp+2C0h+Destination.MaximumLength], ax
0x18003458d  call    cs:__imp_KernelBaseGetGlobalData
0x180034594  nop     dword ptr [rax+rax+00h]
0x180034599  mov     rcx, gs:60h
0x1800345a2  movzx   r8d, [rsp+2C0h+Destination.MaximumLength]; Size
0x1800345a8  mov     edx, [rax]; Flags
0x1800345aa  mov     rcx, [rcx+30h]; HeapHandle
0x1800345ae  call    cs:__imp_RtlAllocateHeap
0x1800345b5  nop     dword ptr [rax+rax+00h]
0x1800345ba  mov     [rsp+2C0h+Destination.Buffer], rax
0x1800345bf  test    rax, rax
0x1800345c2  jz      loc_180034663
0x1800345c8  lea     rdx, [rsp+2C0h+KeyPath]; Source
0x1800345cd  lea     rcx, [rsp+2C0h+Destination]; Destination
0x1800345d2  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800345d9  nop     dword ptr [rax+rax+00h]
0x1800345de  test    eax, eax
0x1800345e0  js      short loc_180034643
0x1800345e2  lea     rdx, aSoftwarePolici; "\\Software\\Policies\\Microsoft\\Window"...
0x1800345e9  lea     rcx, [rsp+2C0h+Destination]; Destination
0x1800345ee  call    cs:__imp_RtlAppendUnicodeToString
0x1800345f5  nop     dword ptr [rax+rax+00h]
0x1800345fa  test    eax, eax
0x1800345fc  js      short loc_180034643
0x1800345fe  lea     rax, [rsp+2C0h+Destination]
0x180034603  mov     [rbp+1C0h+ObjectAttributes.Length], 30h ; '0'
0x18003460a  xorps   xmm0, xmm0
0x18003460d  mov     [rbp+1C0h+ObjectAttributes.ObjectName], rax
0x180034611  lea     r8, [rbp+1C0h+ObjectAttributes]; ObjectAttributes
0x180034615  mov     [rbp+1C0h+ObjectAttributes.RootDirectory], r13
0x180034619  mov     edx, 1; DesiredAccess
0x18003461e  mov     [rbp+1C0h+ObjectAttributes.Attributes], 40h ; '@'
0x180034625  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x18003462a  movdqu  xmmword ptr [rbp+1C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003462f  call    cs:__imp_NtOpenKey
0x180034636  nop     dword ptr [rax+rax+00h]
0x18003463b  test    eax, eax
0x18003463d  jns     loc_180034B5B
0x180034643  mov     rcx, gs:60h
0x18003464c  xor     edx, edx; Flags
0x18003464e  mov     r8, [rsp+2C0h+Destination.Buffer]; P
0x180034653  mov     rcx, [rcx+30h]; HeapHandle
0x180034657  call    cs:__imp_RtlFreeHeap
0x18003465e  nop     dword ptr [rax+rax+00h]
0x180034663  lea     rcx, [rsp+2C0h+KeyPath]; UnicodeString
0x180034668  call    cs:__imp_RtlFreeUnicodeString
0x18003466f  nop     dword ptr [rax+rax+00h]
0x180034674  test    bl, bl
0x180034676  jnz     loc_180034791
0x18003467c  mov     cs:qword_1800BD308, 0FFFFFFFFFFFFFFFEh
0x180034687  mov     ebx, r13d
0x18003468a  mov     rcx, [rsp+2C0h+Handle]; Handle
0x18003468f  test    rcx, rcx
0x180034692  jz      short loc_1800346A0
0x180034694  call    cs:__imp_NtClose
0x18003469b  nop     dword ptr [rax+rax+00h]
0x1800346a0  test    r14, r14
0x1800346a3  jnz     loc_180034C67
0x1800346a9  lea     rcx, gsrwlAppCert
0x1800346b0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800346b7  nop     dword ptr [rax+rax+00h]
0x1800346bc  mov     eax, ebx
0x1800346be  jmp     loc_1800342EB
0x1800346c3  mov     r8b, bl; SubAuthorityCount
0x1800346c6  lea     rdx, IdentifierAuthority; IdentifierAuthority
0x1800346cd  lea     rcx, [rbp+1C0h+KeyValueInformation]; Sid
0x1800346d1  call    cs:__imp_RtlInitializeSid
0x1800346d8  nop     dword ptr [rax+rax+00h]
0x1800346dd  xor     edx, edx; SubAuthority
0x1800346df  lea     rcx, [rbp+1C0h+KeyValueInformation]; Sid
0x1800346e3  call    cs:__imp_RtlSubAuthoritySid
0x1800346ea  nop     dword ptr [rax+rax+00h]
0x1800346ef  lea     rdx, [rbp+1C0h+KeyValueInformation]; Sid2
0x1800346f3  mov     dword ptr [rax], 12h
0x1800346f9  mov     rcx, [rbp+1C0h+TokenInformation]; Sid1
0x180034700  call    cs:__imp_RtlEqualSid
0x180034707  nop     dword ptr [rax+rax+00h]
0x18003470c  test    al, al
0x18003470e  jnz     loc_180034687
0x180034714  xor     edx, edx; SubAuthority
0x180034716  lea     rcx, [rbp+1C0h+KeyValueInformation]; Sid
0x18003471a  call    cs:__imp_RtlSubAuthoritySid
0x180034721  nop     dword ptr [rax+rax+00h]
0x180034726  lea     rdx, [rbp+1C0h+KeyValueInformation]; Sid2
0x18003472a  mov     dword ptr [rax], 13h
0x180034730  mov     rcx, [rbp+1C0h+TokenInformation]; Sid1
0x180034737  call    cs:__imp_RtlEqualSid
0x18003473e  nop     dword ptr [rax+rax+00h]
0x180034743  test    al, al
0x180034745  jnz     loc_180034687
0x18003474b  xor     edx, edx; SubAuthority
0x18003474d  lea     rcx, [rbp+1C0h+KeyValueInformation]; Sid
0x180034751  call    cs:__imp_RtlSubAuthoritySid
0x180034758  nop     dword ptr [rax+rax+00h]
0x18003475d  lea     rdx, [rbp+1C0h+KeyValueInformation]; Sid2
0x180034761  mov     dword ptr [rax], 14h
0x180034767  mov     rcx, [rbp+1C0h+TokenInformation]; Sid1
0x18003476e  call    cs:__imp_RtlEqualSid
0x180034775  nop     dword ptr [rax+rax+00h]
0x18003477a  test    al, al
0x18003477c  jz      loc_180034437
0x180034782  jmp     loc_180034687
0x180034787  mov     eax, 0C000000Dh
0x18003478c  jmp     loc_1800342EB
0x180034791  lea     r9, [rsp+2C0h+BaseAddress]; BaseAddress
0x180034796  mov     [rsp+2C0h+LoadFlags], 1000h
0x18003479e  lea     r8, stru_180085750; Name
0x1800347a5  xor     ecx, ecx; SearchPath
0x1800347a7  lea     rdx, [rsp+2C0h+LoadFlags]; LoadFlags
0x1800347ac  call    cs:__imp_LdrLoadDll
0x1800347b3  nop     dword ptr [rax+rax+00h]
0x1800347b8  test    eax, eax
0x1800347ba  js      loc_180034BBF
0x1800347c0  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x1800347c5  lea     r9, ProcedureAddress; ProcedureAddress
0x1800347cc  xor     r8d, r8d; Ordinal
0x1800347cf  lea     rdx, stru_180085780; Name
  ... truncated ...
```
