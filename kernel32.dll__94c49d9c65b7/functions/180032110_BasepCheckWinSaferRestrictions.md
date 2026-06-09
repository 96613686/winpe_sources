# BasepCheckWinSaferRestrictions

- ea: `0x180032110`
- end: `0x180032a33`
- name: `BasepCheckWinSaferRestrictions`
- size: `2339`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180032110`
- `0x18007a7d1`
- `0x18007a7dd`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18003234c`
- `ntdll!NtQueryValueKey` at `0x180032382`
- `ntdll!NtQueryValueKey` at `0x18003281b`
- `ntdll!NtQueryValueKey` at `0x18003293e`
- `ntdll!NtQueryValueKey` at `0x18003234c`
- `ntdll!NtQueryValueKey` at `0x180032382`
- `ntdll!NtQueryValueKey` at `0x18003281b`
- `ntdll!NtQueryValueKey` at `0x18003293e`
- `ntdll!RtlEqualSid` at `0x180032531`
- `ntdll!RtlEqualSid` at `0x180032558`
- `ntdll!RtlEqualSid` at `0x180032583`
- `ntdll!RtlEqualSid` at `0x180032531`
- `ntdll!RtlEqualSid` at `0x180032558`
- `ntdll!RtlEqualSid` at `0x180032583`
- `ntdll!NtOpenThreadToken` at `0x18003222a`
- `ntdll!NtOpenThreadToken` at `0x18003222a`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800323de`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800323de`
- `ntdll!NtQueryInformationToken` at `0x1800322c0`
- `ntdll!NtQueryInformationToken` at `0x1800322c0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800321da`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800321da`
- `ntdll!LdrLoadDll` at `0x1800325bb`
- `ntdll!LdrLoadDll` at `0x1800325bb`
- `ntdll!NtSetInformationThread` at `0x180032878`
- `ntdll!NtSetInformationThread` at `0x1800328ca`
- `ntdll!NtSetInformationThread` at `0x180032878`
- `ntdll!NtSetInformationThread` at `0x1800328ca`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800324f3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800324f3`
- `ntdll!LdrUnloadDll` at `0x18003298a`
- `ntdll!LdrUnloadDll` at `0x18003298a`
- `ntdll!NtOpenKey` at `0x1800322e9`
- `ntdll!NtOpenKey` at `0x180032316`
- `ntdll!NtOpenKey` at `0x18003248a`
- `ntdll!NtOpenKey` at `0x1800322e9`
- `ntdll!NtOpenKey` at `0x180032316`
- `ntdll!NtOpenKey` at `0x18003248a`
- `ntdll!RtlAppendUnicodeToString` at `0x18003244f`
- `ntdll!RtlAppendUnicodeToString` at `0x18003244f`
- `ntdll!RtlSubAuthoritySid` at `0x18003251a`
- `ntdll!RtlSubAuthoritySid` at `0x180032541`
- `ntdll!RtlSubAuthoritySid` at `0x18003256c`
- `ntdll!RtlSubAuthoritySid` at `0x18003251a`
- `ntdll!RtlSubAuthoritySid` at `0x180032541`
- `ntdll!RtlSubAuthoritySid` at `0x18003256c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180032439`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180032439`
- `ntdll!LdrGetProcedureAddress` at `0x1800325df`
- `ntdll!LdrGetProcedureAddress` at `0x180032610`
- `ntdll!LdrGetProcedureAddress` at `0x180032641`
- `ntdll!LdrGetProcedureAddress` at `0x180032672`
- `ntdll!LdrGetProcedureAddress` at `0x1800325df`
- `ntdll!LdrGetProcedureAddress` at `0x180032610`
- `ntdll!LdrGetProcedureAddress` at `0x180032641`
- `ntdll!LdrGetProcedureAddress` at `0x180032672`
- `ntdll!RtlInitializeSid` at `0x18003250e`
- `ntdll!RtlInitializeSid` at `0x18003250e`
- `ntdll!NtOpenProcessToken` at `0x180032250`
- `ntdll!NtOpenProcessToken` at `0x1800328ab`
- `ntdll!NtOpenProcessToken` at `0x180032250`
- `ntdll!NtOpenProcessToken` at `0x1800328ab`
- `ntdll!NtClose` at `0x1800323ad`
- `ntdll!NtClose` at `0x1800324dd`
- `ntdll!NtClose` at `0x180032758`
- `ntdll!NtClose` at `0x180032828`
- `ntdll!NtClose` at `0x18003288d`
- `ntdll!NtClose` at `0x1800328d7`
- `ntdll!NtClose` at `0x1800323ad`
- `ntdll!NtClose` at `0x1800324dd`
- `ntdll!NtClose` at `0x180032758`
- `ntdll!NtClose` at `0x180032828`
- `ntdll!NtClose` at `0x18003288d`
- `ntdll!NtClose` at `0x1800328d7`
- `ntdll!RtlFreeUnicodeString` at `0x1800324b7`
- `ntdll!RtlFreeUnicodeString` at `0x1800324b7`
- `ntdll!RtlFreeHeap` at `0x1800324ac`
- `ntdll!RtlFreeHeap` at `0x180032a28`
- `ntdll!RtlFreeHeap` at `0x1800324ac`
- `ntdll!RtlFreeHeap` at `0x180032a28`
- `ntdll!RtlAllocateHeap` at `0x18003241b`
- `ntdll!RtlAllocateHeap` at `0x1800327a4`
- `ntdll!RtlAllocateHeap` at `0x18003241b`
- `ntdll!RtlAllocateHeap` at `0x1800327a4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180032400`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180032400`

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
    if ( qword_1800B5308 == -2 && !v8 )
      return 0;
    RtlAcquireSRWLockExclusive(&gsrwlAppCert);
    v10 = qword_1800B5308;
    if ( qword_1800B5308 )
    {
      if ( qword_1800B5308 == -2 && !v8 )
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
                    (PUNICODE_STRING)&stru_18007D940,
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
          if ( NtOpenKey(&KeyHandle, 1u, (POBJECT_ATTRIBUTES)&stru_18007D8A0) < 0 )
            goto LABEL_108;
          if ( NtQueryValueKey(
                 KeyHandle,
                 (PUNICODE_STRING)&stru_18007D8E0,
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
                 (PUNICODE_STRING)&stru_18007D8D0,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0x50u,
                 &LoadFlags) >= 0
            && v38
            && v36 == 4
            && v37 == 4 )
          {
            dword_1800B5AF8 = 8;
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
                       (PUNICODE_STRING)&stru_18007D8E0,
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
              qword_1800B5308 = -2;
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
          if ( LdrLoadDll(0, &LoadFlags, (PUNICODE_STRING)&stru_18007D8F0, &BaseAddress) < 0 )
          {
            v13 = -1073741511;
            qword_1800B5308 = 0;
            goto LABEL_42;
          }
          if ( LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007D920, 0, &ProcedureAddress) < 0
            || !ProcedureAddress
            || LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007D930, 0, &qword_1800B5DE0) < 0
            || !qword_1800B5DE0
            || LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007D910, 0, &qword_1800B5DF0) < 0
            || !qword_1800B5DF0
            || LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007D900, 0, &qword_1800B5DD8) < 0
            || !qword_1800B5DD8 )
          {
            LdrUnloadDll(BaseAddress);
            qword_1800B5308 = 0;
            v13 = -1073741511;
            goto LABEL_42;
          }
          qword_1800B5308 = (__int64)BaseAddress;
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
          v30 = dword_1800B5AF8 | 5;
        }
        v13 = -1073741790;
        if ( (unsigned int)((__int64 (__fastcall *)(__int64, int *, __int64 *, const wchar_t *))ProcedureAddress)(
                             1,
                             &v29,
                             &v24,
                             L"IGNORESRPV2") )
        {
          KeyHandle = 0;
          if ( (unsigned int)((__int64 (__fastcall *)(__int64, HANDLE, void **, __int64, _QWORD))qword_1800B5DF0)(
                               v24,
                               TokenHandle,
                               &KeyHandle,
                               1,
                               0) )
          {
            if ( KeyHandle )
            {
              ((void (__fastcall *)(__int64, _WORD *, _QWORD))qword_1800B5DD8)(v24, a2, 0);
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
              ((void (__fastcall *)(__int64, _WORD *, _QWORD))qword_1800B5DD8)(v24, a2, 0);
              v13 = -1073740959;
              if ( LastErrorValue == 786 )
                v13 = -1073740942;
            }
          }
          ((void (__fastcall *)(__int64))qword_1800B5DE0)(v24);
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
        v10 = qword_1800B5308;
        goto LABEL_22;
      }
      if ( qword_1800B5308 == -1 )
      {
        qword_1800B5308 = -2;
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
0x180032110  push    rbp
0x180032112  push    rbx
0x180032113  push    rsi
0x180032114  push    rdi
0x180032115  push    r12
0x180032117  push    r13
0x180032119  push    r14
0x18003211b  push    r15
0x18003211d  lea     rbp, [rsp-188h]
0x180032125  sub     rsp, 288h
0x18003212c  mov     rax, cs:__security_cookie
0x180032133  xor     rax, rsp
0x180032136  mov     [rbp+1C0h+var_50], rax
0x18003213d  mov     r12, r8
0x180032140  mov     r15, rdx
0x180032143  mov     rdi, rcx
0x180032146  xor     edx, edx; Val
0x180032148  mov     r8d, 0B0h; Size
0x18003214e  lea     rcx, [rbp+1C0h+var_210]; void *
0x180032152  mov     rsi, r9
0x180032155  call    memset_0
0x18003215a  xor     r13d, r13d
0x18003215d  mov     [rsp+2C0h+var_270], r13
0x180032162  mov     [rsp+2C0h+Handle], r13
0x180032167  mov     [rsp+2C0h+TokenHandle], r13
0x18003216c  test    r15, r15
0x18003216f  jz      loc_180032596
0x180032175  cmp     [r15], r13w
0x180032179  jz      loc_180032596
0x18003217f  lea     ecx, [r13+1]
0x180032183  mov     ebx, r13d
0x180032186  test    rsi, rsi
0x180032189  jnz     short loc_1800321BE
0x18003218b  cmp     cs:qword_1800B5308, 0FFFFFFFFFFFFFFFEh
0x180032193  jnz     short loc_1800321D3
0x180032195  test    ebx, ebx
0x180032197  jnz     short loc_1800321D3
0x180032199  xor     eax, eax
0x18003219b  mov     rcx, [rbp+1C0h+var_50]
0x1800321a2  xor     rcx, rsp; StackCookie
0x1800321a5  call    __security_check_cookie
0x1800321aa  add     rsp, 288h
0x1800321b1  pop     r15
0x1800321b3  pop     r14
0x1800321b5  pop     r13
0x1800321b7  pop     r12
0x1800321b9  pop     rdi
0x1800321ba  pop     rsi
0x1800321bb  pop     rbx
0x1800321bc  pop     rbp
0x1800321bd  retn
0x1800321be  cmp     [rsi], r13w
0x1800321c2  jz      short loc_18003218B
0x1800321c4  mov     eax, gs:179Ch
0x1800321cc  test    eax, eax
0x1800321ce  cmovnz  ebx, ecx
0x1800321d1  jmp     short loc_18003218B
0x1800321d3  lea     rcx, gsrwlAppCert
0x1800321da  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800321e0  mov     rax, cs:qword_1800B5308
0x1800321e7  test    rax, rax
0x1800321ea  jz      loc_1800327C0
0x1800321f0  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800321f4  jz      loc_180032779
0x1800321fa  mov     r14, r13
0x1800321fd  test    rdi, rdi
0x180032200  jnz     loc_18003228B
0x180032206  mov     eax, gs:179Ch
0x18003220e  mov     rdi, 0FFFFFFFFFFFFFFFEh
0x180032215  test    eax, eax
0x180032217  jz      short loc_18003223D
0x180032219  lea     r9, [rsp+2C0h+TokenHandle]; TokenHandle
0x18003221e  mov     edx, 2000000h; DesiredAccess
0x180032223  lea     r8d, [rdi+3]; OpenAsSelf
0x180032227  mov     rcx, rdi; ThreadHandle
0x18003222a  call    cs:__imp_NtOpenThreadToken
0x180032230  mov     ebx, eax
0x180032232  cmp     eax, 0C000007Ch
0x180032237  jnz     loc_180032859
0x18003223d  mov     [rsp+2C0h+TokenHandle], r13
0x180032242  lea     r8, [rsp+2C0h+Handle]; TokenHandle
0x180032247  mov     edx, 0Ah; DesiredAccess
0x18003224c  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180032250  call    cs:__imp_NtOpenProcessToken
0x180032256  mov     ebx, eax
0x180032258  cmp     eax, 0C0000022h
0x18003225d  jz      loc_18003289D
0x180032263  test    ebx, ebx
0x180032265  jns     short loc_18003226C
0x180032267  mov     [rsp+2C0h+Handle], r13
0x18003226c  cmp     [rsp+2C0h+TokenHandle], r13
0x180032271  jnz     loc_1800328B8
0x180032277  test    ebx, ebx
0x180032279  js      loc_1800327CA
0x18003227f  mov     rdi, [rsp+2C0h+Handle]
0x180032284  mov     rax, cs:qword_1800B5308
0x18003228b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18003228f  jb      loc_180032699
0x180032295  lea     rax, [rsp+2C0h+LoadFlags]
0x18003229a  mov     [rsp+2C0h+BaseAddress], r13
0x18003229f  mov     ebx, 1
0x1800322a4  mov     [rsp+2C0h+LoadFlags], r13d
0x1800322a9  mov     edx, ebx; TokenInformationClass
0x1800322ab  mov     [rsp+2C0h+ReturnLength], rax; ReturnLength
0x1800322b0  mov     r9d, 90h; TokenInformationLength
0x1800322b6  lea     r8, [rbp+1C0h+TokenInformation]; TokenInformation
0x1800322bd  mov     rcx, rdi; TokenHandle
0x1800322c0  call    cs:__imp_NtQueryInformationToken
0x1800322c6  test    eax, eax
0x1800322c8  jns     loc_180032500
0x1800322ce  lea     r8, ObjectAttributes; ObjectAttributes
0x1800322d5  mov     [rsp+2C0h+KeyHandle], r13
0x1800322da  mov     edx, 3; DesiredAccess
0x1800322df  mov     [rsp+2C0h+LoadFlags], r13d
0x1800322e4  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x1800322e9  call    cs:__imp_NtOpenKey
0x1800322ef  test    eax, eax
0x1800322f1  jns     loc_1800327F3
0x1800322f7  lea     r8, stru_18007D8A0; ObjectAttributes
0x1800322fe  mov     [rsp+2C0h+KeyHandle], r13
0x180032303  mov     edx, 1; DesiredAccess
0x180032308  mov     [rsp+2C0h+LoadFlags], r13d
0x18003230d  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x180032312  movzx   ebx, r13b
0x180032316  call    cs:__imp_NtOpenKey
0x18003231c  test    eax, eax
0x18003231e  js      loc_1800323BB
0x180032324  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x180032329  lea     rax, [rsp+2C0h+LoadFlags]
0x18003232e  mov     [rsp+2C0h+ResultLength], rax; ResultLength
0x180032333  lea     r9, [rbp+1C0h+KeyValueInformation]; KeyValueInformation
0x180032337  mov     r8d, 2; KeyValueInformationClass
0x18003233d  mov     dword ptr [rsp+2C0h+ReturnLength], 50h ; 'P'; Length
0x180032345  lea     rdx, stru_18007D8E0; ValueName
0x18003234c  call    cs:__imp_NtQueryValueKey
0x180032352  test    eax, eax
0x180032354  jns     loc_1800328F1
0x18003235a  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x18003235f  lea     rax, [rsp+2C0h+LoadFlags]
0x180032364  mov     [rsp+2C0h+ResultLength], rax; ResultLength
0x180032369  lea     r9, [rbp+1C0h+KeyValueInformation]; KeyValueInformation
0x18003236d  mov     r8d, 2; KeyValueInformationClass
0x180032373  mov     dword ptr [rsp+2C0h+ReturnLength], 50h ; 'P'; Length
0x18003237b  lea     rdx, stru_18007D8D0; ValueName
0x180032382  call    cs:__imp_NtQueryValueKey
0x180032388  test    eax, eax
0x18003238a  js      short loc_1800323A8
0x18003238c  cmp     [rbp+1C0h+var_154], r13d
0x180032390  jbe     short loc_1800323A8
0x180032392  cmp     [rbp+1C0h+var_15C], 4
0x180032396  jnz     short loc_1800323A8
0x180032398  cmp     [rbp+1C0h+var_158], 4
0x18003239c  jnz     short loc_1800323A8
0x18003239e  mov     cs:dword_1800B5AF8, 8
0x1800323a8  mov     rcx, [rsp+2C0h+KeyHandle]; Handle
0x1800323ad  call    cs:__imp_NtClose
0x1800323b3  test    bl, bl
0x1800323b5  jnz     loc_1800325A0
0x1800323bb  xorps   xmm0, xmm0
0x1800323be  lea     rcx, [rsp+2C0h+KeyPath]; KeyPath
0x1800323c3  xorps   xmm1, xmm1
0x1800323c6  xor     eax, eax
0x1800323c8  movups  xmmword ptr [rbp+1C0h+ObjectAttributes.ObjectName], xmm0
0x1800323cc  movups  xmmword ptr [rbp+1C0h+ObjectAttributes+1Ch], xmm0
0x1800323d0  movups  xmmword ptr [rsp+2C0h+KeyPath.Length], xmm0
0x1800323d5  movups  xmmword ptr [rsp+2C0h+Destination.Length], xmm1
0x1800323da  movups  xmmword ptr [rbp+1C0h+ObjectAttributes.Length], xmm0
0x1800323de  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800323e4  test    eax, eax
0x1800323e6  js      loc_1800324C5
0x1800323ec  movzx   eax, [rsp+2C0h+KeyPath.Length]
0x1800323f1  add     ax, 78h ; 'x'
0x1800323f5  mov     [rsp+2C0h+Destination.Length], r13w
0x1800323fb  mov     [rsp+2C0h+Destination.MaximumLength], ax
0x180032400  call    cs:__imp_KernelBaseGetGlobalData
0x180032406  mov     rcx, gs:60h
0x18003240f  movzx   r8d, [rsp+2C0h+Destination.MaximumLength]; Size
0x180032415  mov     edx, [rax]; Flags
0x180032417  mov     rcx, [rcx+30h]; HeapHandle
0x18003241b  call    cs:__imp_RtlAllocateHeap
0x180032421  mov     [rsp+2C0h+Destination.Buffer], rax
0x180032426  test    rax, rax
0x180032429  jz      loc_1800324B2
0x18003242f  lea     rdx, [rsp+2C0h+KeyPath]; Source
0x180032434  lea     rcx, [rsp+2C0h+Destination]; Destination
0x180032439  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003243f  test    eax, eax
0x180032441  js      short loc_180032498
0x180032443  lea     rdx, aSoftwarePolici; "\\Software\\Policies\\Microsoft\\Window"...
0x18003244a  lea     rcx, [rsp+2C0h+Destination]; Destination
0x18003244f  call    cs:__imp_RtlAppendUnicodeToString
0x180032455  test    eax, eax
0x180032457  js      short loc_180032498
0x180032459  lea     rax, [rsp+2C0h+Destination]
0x18003245e  mov     [rbp+1C0h+ObjectAttributes.Length], 30h ; '0'
0x180032465  xorps   xmm0, xmm0
0x180032468  mov     [rbp+1C0h+ObjectAttributes.ObjectName], rax
0x18003246c  lea     r8, [rbp+1C0h+ObjectAttributes]; ObjectAttributes
0x180032470  mov     [rbp+1C0h+ObjectAttributes.RootDirectory], r13
0x180032474  mov     edx, 1; DesiredAccess
0x180032479  mov     [rbp+1C0h+ObjectAttributes.Attributes], 40h ; '@'
0x180032480  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x180032485  movdqu  xmmword ptr [rbp+1C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003248a  call    cs:__imp_NtOpenKey
0x180032490  test    eax, eax
0x180032492  jns     loc_180032916
0x180032498  mov     rcx, gs:60h
0x1800324a1  xor     edx, edx; Flags
0x1800324a3  mov     r8, [rsp+2C0h+Destination.Buffer]; P
0x1800324a8  mov     rcx, [rcx+30h]; HeapHandle
0x1800324ac  call    cs:__imp_RtlFreeHeap
0x1800324b2  lea     rcx, [rsp+2C0h+KeyPath]; UnicodeString
0x1800324b7  call    cs:__imp_RtlFreeUnicodeString
0x1800324bd  test    bl, bl
0x1800324bf  jnz     loc_1800325A0
0x1800324c5  mov     cs:qword_1800B5308, 0FFFFFFFFFFFFFFFEh
0x1800324d0  mov     ebx, r13d
0x1800324d3  mov     rcx, [rsp+2C0h+Handle]; Handle
0x1800324d8  test    rcx, rcx
0x1800324db  jz      short loc_1800324E3
0x1800324dd  call    cs:__imp_NtClose
0x1800324e3  test    r14, r14
0x1800324e6  jnz     loc_180032A16
0x1800324ec  lea     rcx, gsrwlAppCert
0x1800324f3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800324f9  mov     eax, ebx
0x1800324fb  jmp     loc_18003219B
0x180032500  mov     r8b, bl; SubAuthorityCount
0x180032503  lea     rdx, IdentifierAuthority; IdentifierAuthority
0x18003250a  lea     rcx, [rbp+1C0h+KeyValueInformation]; Sid
0x18003250e  call    cs:__imp_RtlInitializeSid
0x180032514  xor     edx, edx; SubAuthority
0x180032516  lea     rcx, [rbp+1C0h+KeyValueInformation]; Sid
0x18003251a  call    cs:__imp_RtlSubAuthoritySid
0x180032520  lea     rdx, [rbp+1C0h+KeyValueInformation]; Sid2
0x180032524  mov     dword ptr [rax], 12h
0x18003252a  mov     rcx, [rbp+1C0h+TokenInformation]; Sid1
0x180032531  call    cs:__imp_RtlEqualSid
0x180032537  test    al, al
0x180032539  jnz     short loc_1800324D0
0x18003253b  xor     edx, edx; SubAuthority
0x18003253d  lea     rcx, [rbp+1C0h+KeyValueInformation]; Sid
0x180032541  call    cs:__imp_RtlSubAuthoritySid
0x180032547  lea     rdx, [rbp+1C0h+KeyValueInformation]; Sid2
0x18003254b  mov     dword ptr [rax], 13h
0x180032551  mov     rcx, [rbp+1C0h+TokenInformation]; Sid1
0x180032558  call    cs:__imp_RtlEqualSid
0x18003255e  test    al, al
0x180032560  jnz     loc_1800324D0
0x180032566  xor     edx, edx; SubAuthority
0x180032568  lea     rcx, [rbp+1C0h+KeyValueInformation]; Sid
0x18003256c  call    cs:__imp_RtlSubAuthoritySid
0x180032572  lea     rdx, [rbp+1C0h+KeyValueInformation]; Sid2
0x180032576  mov     dword ptr [rax], 14h
0x18003257c  mov     rcx, [rbp+1C0h+TokenInformation]; Sid1
0x180032583  call    cs:__imp_RtlEqualSid
0x180032589  test    al, al
0x18003258b  jz      loc_1800322CE
0x180032591  jmp     loc_1800324D0
0x180032596  mov     eax, 0C000000Dh
0x18003259b  jmp     loc_18003219B
0x1800325a0  lea     r9, [rsp+2C0h+BaseAddress]; BaseAddress
0x1800325a5  mov     [rsp+2C0h+LoadFlags], 1000h
0x1800325ad  lea     r8, stru_18007D8F0; Name
0x1800325b4  xor     ecx, ecx; SearchPath
0x1800325b6  lea     rdx, [rsp+2C0h+LoadFlags]; LoadFlags
0x1800325bb  call    cs:__imp_LdrLoadDll
0x1800325c1  test    eax, eax
0x1800325c3  js      loc_180032974
0x1800325c9  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x1800325ce  lea     r9, ProcedureAddress; ProcedureAddress
0x1800325d5  xor     r8d, r8d; Ordinal
0x1800325d8  lea     rdx, stru_18007D920; Name
0x1800325df  call    cs:__imp_LdrGetProcedureAddress
0x1800325e5  test    eax, eax
0x1800325e7  js      loc_180032985
0x1800325ed  cmp     cs:ProcedureAddress, r13
0x1800325f4  jz      loc_180032985
0x1800325fa  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x1800325ff  lea     r9, qword_1800B5DE0; ProcedureAddress
0x180032606  xor     r8d, r8d; Ordinal
0x180032609  lea     rdx, stru_18007D930; Name
0x180032610  call    cs:__imp_LdrGetProcedureAddress
0x180032616  test    eax, eax
0x180032618  js      loc_180032985
0x18003261e  cmp     cs:qword_1800B5DE0, r13
0x180032625  jz      loc_180032985
0x18003262b  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x180032630  lea     r9, qword_1800B5DF0; ProcedureAddress
0x180032637  xor     r8d, r8d; Ordinal
0x18003263a  lea     rdx, stru_18007D910; Name
0x180032641  call    cs:__imp_LdrGetProcedureAddress
0x180032647  test    eax, eax
0x180032649  js      loc_180032985
0x18003264f  cmp     cs:qword_1800B5DF0, r13
0x180032656  jz      loc_180032985
0x18003265c  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x180032661  lea     r9, qword_1800B5DD8; ProcedureAddress
0x180032668  xor     r8d, r8d; Ordinal
0x18003266b  lea     rdx, stru_18007D900; Name
  ... truncated ...
```
