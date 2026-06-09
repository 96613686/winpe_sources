# OpenMutexW

- ea: `0x1800ba520`
- end: `0x1800ba7b1`
- name: `OpenMutexW`
- size: `657`
- prototype: `HANDLE __stdcall(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180178920`

## callees

- `0x18004b9d0`
- `0x1800731a0`
- `0x1800ba520`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800ba56b`
- `ntdll!RtlInitUnicodeString` at `0x1800ba56b`
- `ntdll!NtOpenMutant` at `0x1800ba5db`
- `ntdll!NtOpenMutant` at `0x1800ba5db`
- `ntdll!NtClose` at `0x1800ba6da`
- `ntdll!NtClose` at `0x1800ba6ef`
- `ntdll!NtClose` at `0x1800ba7a0`
- `ntdll!NtClose` at `0x1800ba6da`
- `ntdll!NtClose` at `0x1800ba6ef`
- `ntdll!NtClose` at `0x1800ba7a0`
- `ntdll!NtOpenProcessToken` at `0x1800ba666`
- `ntdll!NtOpenProcessToken` at `0x1800ba666`
- `ntdll!NtOpenThreadToken` at `0x1800ba726`
- `ntdll!NtOpenThreadToken` at `0x1800ba726`
- `ntdll!NtSetInformationThread` at `0x1800ba753`
- `ntdll!NtSetInformationThread` at `0x1800ba790`
- `ntdll!NtSetInformationThread` at `0x1800ba753`
- `ntdll!NtSetInformationThread` at `0x1800ba790`

## pseudocode

```c
HANDLE __stdcall OpenMutexW(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)
{
  void *v5; // rbx
  NTSTATUS v6; // eax
  int v8; // r15d
  int NamedObjectDirectoryForToken; // r14d
  HANDLE v10; // rcx
  HANDLE TokenHandle; // [rsp+38h] [rbp-29h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-21h] BYREF
  HANDLE MutantHandle; // [rsp+48h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-1h] BYREF
  HANDLE v16; // [rsp+D8h] [rbp+77h] BYREF
  HANDLE Handle; // [rsp+E0h] [rbp+7Fh] BYREF

  MutantHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( !lpName )
  {
    BaseSetLastNTError(3221225485LL);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, lpName);
  v5 = (void *)BaseNamedObjectDirectory;
  v16 = 0;
  TokenHandle = 0;
  ThreadInformation = 0;
  Handle = 0;
  if ( BaseNamedObjectDirectory )
    goto LABEL_3;
  v5 = 0;
  v8 = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    NamedObjectDirectoryForToken = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &v16);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_15;
    ThreadInformation = 0;
    NamedObjectDirectoryForToken = NtSetInformationThread(
                                     (HANDLE)0xFFFFFFFFFFFFFFFELL,
                                     ThreadImpersonationToken,
                                     &ThreadInformation,
                                     8u);
    if ( NamedObjectDirectoryForToken < 0 )
      goto LABEL_15;
    v8 = 1;
  }
  NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( NamedObjectDirectoryForToken >= 0 )
  {
    NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(TokenHandle, 0, 1, 15, &Handle);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&BaseNamedObjectDirectory, (signed __int64)Handle, 0) )
        Handle = 0;
      v5 = (void *)BaseNamedObjectDirectory;
    }
  }
LABEL_15:
  v10 = v16;
  if ( v16 )
  {
    if ( v8 )
    {
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v16, 8u);
      v10 = v16;
    }
    NtClose(v10);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( Handle )
    NtClose(Handle);
  if ( NamedObjectDirectoryForToken < 0 )
  {
    BaseSetLastNTError((unsigned int)NamedObjectDirectoryForToken);
    return 0;
  }
LABEL_3:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v5;
  ObjectAttributes.Attributes = bInheritHandle ? 2 : 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( pfnAdjustObjectAttributesForPrivateNamespace )
    pfnAdjustObjectAttributesForPrivateNamespace(&ObjectAttributes);
  v6 = NtOpenMutant(&MutantHandle, dwDesiredAccess, &ObjectAttributes);
  if ( v6 >= 0 )
    return MutantHandle;
  BaseSetLastNTError((unsigned int)v6);
  return 0;
}

```

## disassembly

```asm
0x1800ba520  mov     r11, rsp
0x1800ba523  push    rbp
0x1800ba524  push    rsi
0x1800ba525  push    rdi
0x1800ba526  push    r12
0x1800ba528  lea     rbp, [r11-5Fh]
0x1800ba52c  sub     rsp, 98h
0x1800ba533  xorps   xmm0, xmm0
0x1800ba536  xor     r12d, r12d
0x1800ba539  xor     eax, eax
0x1800ba53b  mov     [rbp+57h+MutantHandle], r12
0x1800ba53f  mov     edi, edx
0x1800ba541  mov     esi, ecx
0x1800ba543  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800ba547  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800ba54b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800ba54f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800ba553  test    r8, r8
0x1800ba556  jz      loc_1800BA612
0x1800ba55c  mov     [r11+8], rbx
0x1800ba560  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800ba564  mov     rdx, r8; SourceString
0x1800ba567  mov     [r11+10h], r14
0x1800ba56b  call    cs:__imp_RtlInitUnicodeString
0x1800ba572  nop     dword ptr [rax+rax+00h]
0x1800ba577  mov     rbx, cs:BaseNamedObjectDirectory
0x1800ba57e  mov     [rbp+57h+arg_10], r12
0x1800ba582  mov     [rbp+57h+TokenHandle], r12
0x1800ba586  mov     [rbp+57h+ThreadInformation], r12
0x1800ba58a  mov     [rbp+57h+Handle], r12
0x1800ba58e  test    rbx, rbx
0x1800ba591  jz      loc_1800BA632
0x1800ba597  neg     edi
0x1800ba599  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800ba5a0  xorps   xmm0, xmm0
0x1800ba5a3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800ba5a7  sbb     eax, eax
0x1800ba5a9  and     eax, 2
0x1800ba5ac  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x1800ba5af  lea     rax, [rbp+57h+DestinationString]
0x1800ba5b3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800ba5b7  mov     rax, cs:pfnAdjustObjectAttributesForPrivateNamespace
0x1800ba5be  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ba5c3  test    rax, rax
0x1800ba5c6  jz      short loc_1800BA5D1
0x1800ba5c8  lea     rcx, [rbp+57h+ObjectAttributes]
0x1800ba5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba5d1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800ba5d5  mov     edx, esi; DesiredAccess
0x1800ba5d7  lea     rcx, [rbp+57h+MutantHandle]; MutantHandle
0x1800ba5db  call    cs:__imp_NtOpenMutant
0x1800ba5e2  nop     dword ptr [rax+rax+00h]
0x1800ba5e7  test    eax, eax
0x1800ba5e9  jns     short loc_1800BA62C
0x1800ba5eb  mov     ecx, eax
0x1800ba5ed  call    BaseSetLastNTError
0x1800ba5f2  xor     eax, eax
0x1800ba5f4  mov     rbx, [rsp+0B0h+arg_0]
0x1800ba5fc  mov     r14, [rsp+0B0h+arg_8]
0x1800ba604  add     rsp, 98h
0x1800ba60b  pop     r12
0x1800ba60d  pop     rdi
0x1800ba60e  pop     rsi
0x1800ba60f  pop     rbp
0x1800ba610  retn
0x1800ba612  mov     ecx, 0C000000Dh
0x1800ba617  call    BaseSetLastNTError
0x1800ba61c  xor     eax, eax
0x1800ba61e  add     rsp, 98h
0x1800ba625  pop     r12
0x1800ba627  pop     rdi
0x1800ba628  pop     rsi
0x1800ba629  pop     rbp
0x1800ba62a  retn
0x1800ba62c  mov     rax, [rbp+57h+MutantHandle]
0x1800ba630  jmp     short loc_1800BA5F4
0x1800ba632  mov     rax, gs:30h
0x1800ba63b  mov     rbx, r12
0x1800ba63e  mov     [rsp+90h], r15
0x1800ba646  mov     r15d, r12d
0x1800ba649  cmp     [rax+179Ch], r12d
0x1800ba650  jnz     loc_1800BA713
0x1800ba656  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800ba65a  mov     edx, 8; DesiredAccess
0x1800ba65f  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800ba666  call    cs:__imp_NtOpenProcessToken
0x1800ba66d  nop     dword ptr [rax+rax+00h]
0x1800ba672  mov     r14d, eax
0x1800ba675  test    eax, eax
0x1800ba677  js      short loc_1800BA6BC
0x1800ba679  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800ba67d  lea     rax, [rbp+57h+Handle]
0x1800ba681  xor     edx, edx
0x1800ba683  mov     [rsp+20h], rax; __int64
0x1800ba688  mov     r9d, 0Fh
0x1800ba68e  mov     r8d, 1
0x1800ba694  call    BasepGetNamedObjectDirectoryForToken
0x1800ba699  mov     r14d, eax
0x1800ba69c  test    eax, eax
0x1800ba69e  js      short loc_1800BA6BC
0x1800ba6a0  mov     rcx, [rbp+57h+Handle]
0x1800ba6a4  xor     eax, eax
0x1800ba6a6  lock cmpxchg cs:BaseNamedObjectDirectory, rcx
0x1800ba6af  jnz     short loc_1800BA6B5
0x1800ba6b1  mov     [rbp+57h+Handle], r12
0x1800ba6b5  mov     rbx, cs:BaseNamedObjectDirectory
0x1800ba6bc  mov     rcx, [rbp+57h+arg_10]
0x1800ba6c0  test    rcx, rcx
0x1800ba6c3  jnz     loc_1800BA775
0x1800ba6c9  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800ba6cd  mov     r15, [rsp+90h]
0x1800ba6d5  test    rcx, rcx
0x1800ba6d8  jz      short loc_1800BA6E6
0x1800ba6da  call    cs:__imp_NtClose
0x1800ba6e1  nop     dword ptr [rax+rax+00h]
0x1800ba6e6  mov     rcx, [rbp+57h+Handle]; Handle
0x1800ba6ea  test    rcx, rcx
0x1800ba6ed  jz      short loc_1800BA6FB
0x1800ba6ef  call    cs:__imp_NtClose
0x1800ba6f6  nop     dword ptr [rax+rax+00h]
0x1800ba6fb  test    r14d, r14d
0x1800ba6fe  jns     loc_1800BA597
0x1800ba704  mov     ecx, r14d
0x1800ba707  call    BaseSetLastNTError
0x1800ba70c  xor     eax, eax
0x1800ba70e  jmp     loc_1800BA5F4
0x1800ba713  lea     r9, [rbp+57h+arg_10]; TokenHandle
0x1800ba717  mov     r8b, 1; OpenAsSelf
0x1800ba71a  mov     edx, 4; DesiredAccess
0x1800ba71f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800ba726  call    cs:__imp_NtOpenThreadToken
0x1800ba72d  nop     dword ptr [rax+rax+00h]
0x1800ba732  mov     r14d, eax
0x1800ba735  test    eax, eax
0x1800ba737  js      short loc_1800BA6BC
0x1800ba739  mov     r9d, 8; ThreadInformationLength
0x1800ba73f  mov     [rbp+57h+ThreadInformation], r12
0x1800ba743  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800ba747  mov     edx, 5; ThreadInformationClass
0x1800ba74c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800ba753  call    cs:__imp_NtSetInformationThread
0x1800ba75a  nop     dword ptr [rax+rax+00h]
0x1800ba75f  mov     r14d, eax
0x1800ba762  test    eax, eax
0x1800ba764  js      loc_1800BA6BC
0x1800ba76a  mov     r15d, 1
0x1800ba770  jmp     loc_1800BA656
0x1800ba775  test    r15d, r15d
0x1800ba778  jz      short loc_1800BA7A0
0x1800ba77a  mov     r9d, 8; ThreadInformationLength
0x1800ba780  lea     r8, [rbp+57h+arg_10]; ThreadInformation
0x1800ba784  mov     edx, 5; ThreadInformationClass
0x1800ba789  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800ba790  call    cs:__imp_NtSetInformationThread
0x1800ba797  nop     dword ptr [rax+rax+00h]
0x1800ba79c  mov     rcx, [rbp+57h+arg_10]; Handle
0x1800ba7a0  call    cs:__imp_NtClose
0x1800ba7a7  nop     dword ptr [rax+rax+00h]
0x1800ba7ac  jmp     loc_1800BA6C9
```
