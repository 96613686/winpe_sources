# KerbGetCallingLuid(_LUID *,void *)

- ea: `0x18009e288`
- end: `0x18009e480`
- name: `?KerbGetCallingLuid@@YAJPEAU_LUID@@PEAX@Z`
- size: `504`
- prototype: `__int64 __fastcall(PLUID DestinationLuid, void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180048a28`
- `0x180048f6c`
- `0x1800548b4`

## callees

- `0x180070680`
- `0x18008b70c`
- `0x18009e288`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009e44d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009e44d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009e36a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009e36a`
- `ntdll!RtlCopyLuid` at `0x18009e406`
- `ntdll!RtlCopyLuid` at `0x18009e406`
- `ntdll!NtOpenProcess` at `0x18009e3b4`
- `ntdll!NtOpenProcess` at `0x18009e3b4`
- `ntdll!NtClose` at `0x18009e410`
- `ntdll!NtClose` at `0x18009e41a`
- `ntdll!NtClose` at `0x18009e457`
- `ntdll!NtClose` at `0x18009e410`
- `ntdll!NtClose` at `0x18009e41a`
- `ntdll!NtClose` at `0x18009e457`
- `ntdll!NtOpenProcessToken` at `0x18009e3cd`
- `ntdll!NtOpenProcessToken` at `0x18009e3cd`
- `ntdll!NtOpenThreadToken` at `0x18009e360`
- `ntdll!NtOpenThreadToken` at `0x18009e360`
- `ntdll!NtQueryInformationToken` at `0x18009e3f3`
- `ntdll!NtQueryInformationToken` at `0x18009e3f3`

## pseudocode

```c
NTSTATUS __fastcall KerbGetCallingLuid(PLUID DestinationLuid, void *a2)
{
  NTSTATUS result; // eax
  NTSTATUS v4; // ebx
  ULONG TokenInformationLength; // [rsp+30h] [rbp-69h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-61h] BYREF
  void *ProcessHandle; // [rsp+40h] [rbp-59h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-51h] BYREF
  _CLIENT_ID ClientId; // [rsp+50h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-39h] BYREF
  __int128 v11; // [rsp+90h] [rbp-9h] BYREF
  __int128 v12; // [rsp+A0h] [rbp+7h]
  _OWORD TokenInformation[3]; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v14; // [rsp+E0h] [rbp+47h]

  ProcessHandle = 0;
  Handle = 0;
  TokenHandle = 0;
  v14 = 0;
  TokenInformationLength = 56;
  v11 = 0;
  v12 = 0;
  ClientId = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( a2 )
  {
    ClientId.UniqueProcess = a2;
    ClientId.UniqueThread = 0;
  }
  else
  {
    result = ((__int64 (__fastcall *)(__int128 *))LsaFunctions->GetClientInfo)(&v11);
    if ( result < 0 )
      return result;
    if ( (BYTE3(v12) & 2) != 0 )
      return -1073741790;
    ClientId.UniqueProcess = (HANDLE)SDWORD2(v11);
    ClientId.UniqueThread = 0;
  }
  result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( result < 0 )
  {
    if ( result != -1073741700 )
      return result;
  }
  else
  {
    RevertToSelf();
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &ClientId);
  if ( v4 < 0 )
    goto LABEL_16;
  v4 = NtOpenProcessToken(ProcessHandle, 8u, &Handle);
  if ( v4 >= 0 )
  {
    v4 = NtQueryInformationToken(
           Handle,
           TokenStatistics,
           TokenInformation,
           TokenInformationLength,
           &TokenInformationLength);
    if ( v4 >= 0 )
      RtlCopyLuid(DestinationLuid, (PLUID)TokenInformation + 1);
    NtClose(Handle);
  }
  NtClose(ProcessHandle);
  if ( v4 < 0 )
LABEL_16:
    KerbTracerT::Log(1, "KerbGetCallingLuid", 1341, "Failed to get LUID\n");
  if ( TokenHandle )
  {
    SetThreadToken(0, TokenHandle);
    NtClose(TokenHandle);
  }
  return v4;
}

```

## disassembly

```asm
0x18009e288  mov     [rsp-8+arg_10], rbx
0x18009e28d  mov     [rsp-8+arg_18], rdi
0x18009e292  push    rbp
0x18009e293  lea     rbp, [rsp-57h]
0x18009e298  sub     rsp, 0F0h
0x18009e29f  mov     rax, cs:__security_cookie
0x18009e2a6  xor     rax, rsp
0x18009e2a9  mov     [rbp+57h+var_8], rax
0x18009e2ad  xorps   xmm0, xmm0
0x18009e2b0  mov     [rbp+57h+ProcessHandle], 0
0x18009e2b8  xorps   xmm1, xmm1
0x18009e2bb  mov     [rbp+57h+Handle], 0
0x18009e2c3  xor     eax, eax
0x18009e2c5  mov     [rbp+57h+TokenHandle], 0
0x18009e2cd  mov     [rbp+57h+var_10], rax
0x18009e2d1  mov     rdi, rcx
0x18009e2d4  mov     [rbp+57h+TokenInformationLength], 38h ; '8'
0x18009e2db  movups  [rbp+57h+var_60], xmm0
0x18009e2df  movups  [rbp+57h+var_50], xmm0
0x18009e2e3  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x18009e2e7  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18009e2eb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18009e2ef  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18009e2f3  movups  [rbp+57h+TokenInformation], xmm0
0x18009e2f7  movups  [rbp+57h+var_30], xmm0
0x18009e2fb  movups  [rbp+57h+var_20], xmm0
0x18009e2ff  test    rdx, rdx
0x18009e302  jnz     short loc_18009E345
0x18009e304  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18009e30b  lea     rcx, [rbp+57h+var_60]
0x18009e30f  mov     rax, [rax+80h]
0x18009e316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e31b  test    eax, eax
0x18009e31d  js      loc_18009E45F
0x18009e323  test    byte ptr [rbp+57h+var_50+3], 2
0x18009e327  jz      short loc_18009E333
0x18009e329  mov     eax, 0C0000022h
0x18009e32e  jmp     loc_18009E45F
0x18009e333  movsxd  rax, dword ptr [rbp+57h+var_60+8]
0x18009e337  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x18009e33b  mov     [rbp+57h+ClientId.UniqueThread], 0
0x18009e343  jmp     short loc_18009E34D
0x18009e345  mov     [rbp+57h+ClientId.UniqueProcess], rdx
0x18009e349  mov     [rbp+57h+ClientId.UniqueThread], rax
0x18009e34d  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18009e351  mov     r8b, 1; OpenAsSelf
0x18009e354  mov     edx, 0Ch; DesiredAccess
0x18009e359  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18009e360  call    cs:__imp_NtOpenThreadToken
0x18009e366  test    eax, eax
0x18009e368  js      short loc_18009E372
0x18009e36a  call    cs:__imp_RevertToSelf
0x18009e370  jmp     short loc_18009E37D
0x18009e372  cmp     eax, 0C000007Ch
0x18009e377  jnz     loc_18009E45F
0x18009e37d  xorps   xmm0, xmm0
0x18009e380  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18009e387  lea     r9, [rbp+57h+ClientId]; ClientId
0x18009e38b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18009e393  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18009e397  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18009e39e  mov     edx, 400h; DesiredAccess
0x18009e3a3  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x18009e3ab  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18009e3af  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009e3b4  call    cs:__imp_NtOpenProcess
0x18009e3ba  mov     ebx, eax
0x18009e3bc  test    eax, eax
0x18009e3be  js      short loc_18009E424
0x18009e3c0  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18009e3c4  lea     r8, [rbp+57h+Handle]; TokenHandle
0x18009e3c8  mov     edx, 8; DesiredAccess
0x18009e3cd  call    cs:__imp_NtOpenProcessToken
0x18009e3d3  mov     ebx, eax
0x18009e3d5  test    eax, eax
0x18009e3d7  js      short loc_18009E416
0x18009e3d9  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18009e3dd  lea     rax, [rbp+57h+TokenInformationLength]
0x18009e3e1  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x18009e3e5  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18009e3e9  mov     edx, 0Ah; TokenInformationClass
0x18009e3ee  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x18009e3f3  call    cs:__imp_NtQueryInformationToken
0x18009e3f9  mov     ebx, eax
0x18009e3fb  test    eax, eax
0x18009e3fd  js      short loc_18009E40C
0x18009e3ff  lea     rdx, [rbp+57h+TokenInformation+8]; SourceLuid
0x18009e403  mov     rcx, rdi; DestinationLuid
0x18009e406  call    cs:__imp_RtlCopyLuid
0x18009e40c  mov     rcx, [rbp+57h+Handle]; Handle
0x18009e410  call    cs:__imp_NtClose
0x18009e416  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x18009e41a  call    cs:__imp_NtClose
0x18009e420  test    ebx, ebx
0x18009e422  jns     short loc_18009E442
0x18009e424  lea     r9, aFailedToGetLui; "Failed to get LUID\n"
0x18009e42b  mov     r8d, 53Dh
0x18009e431  lea     rdx, aKerbgetcalling; "KerbGetCallingLuid"
0x18009e438  mov     ecx, 1
0x18009e43d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009e442  mov     rdx, [rbp+57h+TokenHandle]; Token
0x18009e446  test    rdx, rdx
0x18009e449  jz      short loc_18009E45D
0x18009e44b  xor     ecx, ecx; Thread
0x18009e44d  call    cs:__imp_SetThreadToken
0x18009e453  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18009e457  call    cs:__imp_NtClose
0x18009e45d  mov     eax, ebx
0x18009e45f  mov     rcx, [rbp+57h+var_8]
0x18009e463  xor     rcx, rsp; StackCookie
0x18009e466  call    __security_check_cookie
0x18009e46b  lea     r11, [rsp+0F0h+var_s0]
0x18009e473  mov     rbx, [r11+20h]
0x18009e477  mov     rdi, [r11+28h]
0x18009e47b  mov     rsp, r11
0x18009e47e  pop     rbp
0x18009e47f  retn
```
