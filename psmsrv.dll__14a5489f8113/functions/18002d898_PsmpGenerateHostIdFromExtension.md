# PsmpGenerateHostIdFromExtension

- ea: `0x18002d898`
- end: `0x18002daaa`
- name: `PsmpGenerateHostIdFromExtension`
- size: `530`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, __int64, __int64, __int64, int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002cfc4`

## callees

- `0x18001b7e0`
- `0x18001c10c`
- `0x18002d898`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18002da62`
- `ntdll!NtSetInformationThread` at `0x18002da62`
- `ntdll!NtClose` at `0x18002da81`
- `ntdll!NtClose` at `0x18002da81`
- `ntdll!NtOpenThreadToken` at `0x18002d92a`
- `ntdll!NtOpenThreadToken` at `0x18002d92a`
- `ntdll!NtQueryInformationToken` at `0x18002d956`
- `ntdll!NtQueryInformationToken` at `0x18002d984`
- `ntdll!NtQueryInformationToken` at `0x18002d956`
- `ntdll!NtQueryInformationToken` at `0x18002d984`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002d9ba`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002d9ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002da2c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002da2c`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x18002d9d6`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x18002d9d6`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x18002da1e`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x18002da1e`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x18002da3c`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x18002da3c`

## pseudocode

```c
__int64 __fastcall PsmpGenerateHostIdFromExtension(
        HANDLE TokenHandle,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        _QWORD *a7)
{
  NTSTATUS InformationToken; // ebx
  __int64 v12; // rdi
  int v13; // eax
  __int64 ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandlea; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[1056]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v19[12]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v20[464]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v17 = 0;
  ReturnLength = 0;
  memset_0(v18, 0, 0x418u);
  TokenHandlea = 0;
  if ( !NtCurrentTeb()->IsImpersonating
    || (InformationToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandlea),
        InformationToken >= 0) )
  {
    InformationToken = NtQueryInformationToken(
                         TokenHandle,
                         TokenSessionId,
                         (char *)&ReturnLength + 4,
                         4u,
                         (PULONG)&ReturnLength);
    if ( InformationToken >= 0 )
    {
      InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, v19, 0x54u, (PULONG)&ReturnLength);
      if ( InformationToken >= 0 )
      {
        v12 = v19[0];
        LODWORD(ReturnLength) = 464;
        v13 = a4 ? PsmCreateKeyWithDynamicId(a2, a3, a4, v20, &ReturnLength) : PsmCreateKey(a2, a3, v20, &ReturnLength);
        InformationToken = v13;
        if ( v13 >= 0 )
        {
          if ( (a6 & 0x10000000) != 0 )
          {
            InformationToken = -1073741776;
          }
          else
          {
            HamHostIdInitializeKey(v20, v12, HIDWORD(ReturnLength), 0, 0, v18, ReturnLength);
            if ( TokenHandlea )
              RevertToSelf();
            InformationToken = HamHostIdFindOrCreate(v18, &v17);
            if ( TokenHandlea )
              NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandlea, 8u);
            if ( InformationToken >= 0 )
            {
              InformationToken = 0;
              *a7 = v17;
            }
          }
        }
      }
    }
  }
  if ( TokenHandlea )
    NtClose(TokenHandlea);
  return (unsigned int)InformationToken;
}

```

## disassembly

```asm
0x18002d898  push    rbp
0x18002d89a  push    rbx
0x18002d89b  push    rsi
0x18002d89c  push    rdi
0x18002d89d  push    r12
0x18002d89f  push    r14
0x18002d8a1  push    r15
0x18002d8a3  lea     rbp, [rsp-5B0h]
0x18002d8ab  sub     rsp, 6B0h
0x18002d8b2  mov     rax, cs:__security_cookie
0x18002d8b9  xor     rax, rsp
0x18002d8bc  mov     [rbp+5E0h+var_40], rax
0x18002d8c3  mov     r12, [rbp+5E0h+arg_30]
0x18002d8ca  mov     r15, r8
0x18002d8cd  mov     r14, rdx
0x18002d8d0  mov     [rsp+6E0h+var_6A0], 0
0x18002d8d9  mov     rdi, rcx
0x18002d8dc  mov     [rsp+6E0h+TokenInformation], 0
0x18002d8e4  xor     edx, edx; Val
0x18002d8e6  mov     [rsp+6E0h+var_6B0], 0
0x18002d8ee  mov     r8d, 418h; Size
0x18002d8f4  lea     rcx, [rsp+6E0h+var_690]; void *
0x18002d8f9  mov     rsi, r9
0x18002d8fc  call    memset_0
0x18002d901  mov     [rsp+6E0h+TokenHandle], 0
0x18002d90a  mov     eax, gs:179Ch
0x18002d912  test    eax, eax
0x18002d914  jz      short loc_18002D93A
0x18002d916  lea     r9, [rsp+6E0h+TokenHandle]; TokenHandle
0x18002d91b  mov     r8b, 1; OpenAsSelf
0x18002d91e  mov     edx, 0Ch; DesiredAccess
0x18002d923  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002d92a  call    cs:__imp_NtOpenThreadToken
0x18002d930  mov     ebx, eax
0x18002d932  test    eax, eax
0x18002d934  js      loc_18002DA77
0x18002d93a  mov     r9d, 4; TokenInformationLength
0x18002d940  lea     rax, [rsp+6E0h+var_6B0]
0x18002d945  lea     r8, [rsp+6E0h+TokenInformation]; TokenInformation
0x18002d94a  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x18002d94f  mov     rcx, rdi; TokenHandle
0x18002d952  lea     edx, [r9+8]; TokenInformationClass
0x18002d956  call    cs:__imp_NtQueryInformationToken
0x18002d95c  mov     ebx, eax
0x18002d95e  test    eax, eax
0x18002d960  js      loc_18002DA77
0x18002d966  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18002d96c  lea     rax, [rsp+6E0h+var_6B0]
0x18002d971  lea     r8, [rbp+5E0h+var_270]; TokenInformation
0x18002d978  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x18002d97d  mov     rcx, rdi; TokenHandle
0x18002d980  lea     edx, [r9-53h]; TokenInformationClass
0x18002d984  call    cs:__imp_NtQueryInformationToken
0x18002d98a  mov     ebx, eax
0x18002d98c  test    eax, eax
0x18002d98e  js      loc_18002DA77
0x18002d994  mov     rdi, [rbp+5E0h+var_270]
0x18002d99b  mov     rdx, r15
0x18002d99e  mov     [rsp+6E0h+var_6B0], 1D0h
0x18002d9a6  mov     rcx, r14
0x18002d9a9  test    rsi, rsi
0x18002d9ac  jnz     short loc_18002D9C2
0x18002d9ae  lea     r9, [rsp+6E0h+var_6B0]
0x18002d9b3  lea     r8, [rbp+5E0h+var_210]
0x18002d9ba  call    cs:__imp_PsmCreateKey
0x18002d9c0  jmp     short loc_18002D9DC
0x18002d9c2  lea     rax, [rsp+6E0h+var_6B0]
0x18002d9c7  mov     r8, rsi
0x18002d9ca  lea     r9, [rbp+5E0h+var_210]
0x18002d9d1  mov     [rsp+6E0h+ReturnLength], rax
0x18002d9d6  call    cs:__imp_PsmCreateKeyWithDynamicId
0x18002d9dc  mov     ebx, eax
0x18002d9de  test    eax, eax
0x18002d9e0  js      loc_18002DA77
0x18002d9e6  test    [rbp+5E0h+arg_28], 10000000h
0x18002d9f0  jz      short loc_18002D9F9
0x18002d9f2  mov     ebx, 0C0000030h
0x18002d9f7  jmp     short loc_18002DA77
0x18002d9f9  mov     r8d, [rsp+6E0h+TokenInformation]
0x18002d9fe  lea     rax, [rsp+6E0h+var_690]
0x18002da03  mov     [rsp+6E0h+var_6B8], rax
0x18002da08  lea     rcx, [rbp+5E0h+var_210]
0x18002da0f  xor     r9d, r9d
0x18002da12  mov     [rsp+6E0h+ReturnLength], 0
0x18002da1b  mov     rdx, rdi
0x18002da1e  call    cs:__imp_HamHostIdInitializeKey
0x18002da24  cmp     [rsp+6E0h+TokenHandle], 0
0x18002da2a  jz      short loc_18002DA32
0x18002da2c  call    cs:__imp_RevertToSelf
0x18002da32  lea     rdx, [rsp+6E0h+var_6A0]
0x18002da37  lea     rcx, [rsp+6E0h+var_690]
0x18002da3c  call    cs:__imp_HamHostIdFindOrCreate
0x18002da42  cmp     [rsp+6E0h+TokenHandle], 0
0x18002da48  mov     ebx, eax
0x18002da4a  jz      short loc_18002DA68
0x18002da4c  mov     r9d, 8; ThreadInformationLength
0x18002da52  lea     r8, [rsp+6E0h+TokenHandle]; ThreadInformation
0x18002da57  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002da5e  lea     edx, [r9-3]; ThreadInformationClass
0x18002da62  call    cs:__imp_NtSetInformationThread
0x18002da68  test    ebx, ebx
0x18002da6a  js      short loc_18002DA77
0x18002da6c  mov     rax, [rsp+6E0h+var_6A0]
0x18002da71  xor     ebx, ebx
0x18002da73  mov     [r12], rax
0x18002da77  mov     rcx, [rsp+6E0h+TokenHandle]; Handle
0x18002da7c  test    rcx, rcx
0x18002da7f  jz      short loc_18002DA87
0x18002da81  call    cs:__imp_NtClose
0x18002da87  mov     eax, ebx
0x18002da89  mov     rcx, [rbp+5E0h+var_40]
0x18002da90  xor     rcx, rsp; StackCookie
0x18002da93  call    __security_check_cookie
0x18002da98  add     rsp, 6B0h
0x18002da9f  pop     r15
0x18002daa1  pop     r14
0x18002daa3  pop     r12
0x18002daa5  pop     rdi
0x18002daa6  pop     rsi
0x18002daa7  pop     rbx
0x18002daa8  pop     rbp
0x18002daa9  retn
```
