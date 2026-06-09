# LsapWaitForTrustletStartup

- ea: `0x1800ec388`
- end: `0x1800ec604`
- name: `LsapWaitForTrustletStartup`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800adbf0`

## callees

- `0x18000f808`
- `0x1800df734`
- `0x1800ec388`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ec4ab`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ec4ab`
- `ntdll!NtWaitForSingleObject` at `0x1800ec4d5`
- `ntdll!NtWaitForSingleObject` at `0x1800ec4d5`
- `ntdll!NtClose` at `0x1800ec5c4`
- `ntdll!NtClose` at `0x1800ec5d9`
- `ntdll!NtClose` at `0x1800ec5c4`
- `ntdll!NtClose` at `0x1800ec5d9`
- `ntdll!NtOpenEvent` at `0x1800ec40d`
- `ntdll!NtOpenEvent` at `0x1800ec46c`
- `ntdll!NtOpenEvent` at `0x1800ec538`
- `ntdll!NtOpenEvent` at `0x1800ec40d`
- `ntdll!NtOpenEvent` at `0x1800ec46c`
- `ntdll!NtOpenEvent` at `0x1800ec538`
- `ntdll!RtlInitUnicodeString` at `0x1800ec3ce`
- `ntdll!RtlInitUnicodeString` at `0x1800ec42d`
- `ntdll!RtlInitUnicodeString` at `0x1800ec4f9`
- `ntdll!RtlInitUnicodeString` at `0x1800ec3ce`
- `ntdll!RtlInitUnicodeString` at `0x1800ec42d`
- `ntdll!RtlInitUnicodeString` at `0x1800ec4f9`

## string_xrefs

- `0x1800ec422`: `\LSA_ISO_READY_D`
- `0x1800ec3ab`: `\LSA_ISO_READY`

## pseudocode

```c
__int64 LsapWaitForTrustletStartup()
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  NTSTATUS v2; // eax
  char v3; // al
  BOOL v4; // eax
  union _LARGE_INTEGER *v5; // r8
  NTSTATUS v6; // eax
  LsaHandleCache *v7; // rcx
  int v8; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+10h] BYREF
  __int64 v13; // [rsp+88h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+20h] BYREF

  v13 = 0;
  EventHandle = 0;
  Handle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\LSA_ISO_READY");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
  v1 = v0;
  if ( v0 == -1073741772 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\LSA_ISO_READY_D");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = NtOpenEvent(&EventHandle, 0x100001u, &ObjectAttributes);
    v1 = v2;
    if ( v2 == -1073741772 )
    {
LABEL_3:
      byte_1801A0BC9 = 0;
      v1 = 0;
      goto LABEL_23;
    }
    if ( v2 >= 0 )
    {
      v3 = 0;
      goto LABEL_8;
    }
LABEL_19:
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    v8 = 19;
LABEL_22:
    WPP_SF_sd(
      *((_QWORD *)v7 + 2),
      v8,
      (unsigned int)WPP_e5da1992a0263c0d539144257ad05029_Traceguids,
      (unsigned int)"LsapWaitForTrustletStartup",
      v1);
    goto LABEL_23;
  }
  if ( v0 < 0 )
    goto LABEL_19;
  v3 = 1;
LABEL_8:
  byte_1801A0BC8 = v3;
  v4 = IsDebuggerPresent();
  if ( !v4 )
    v13 = -1000000000;
  v5 = (union _LARGE_INTEGER *)&v13;
  if ( v4 )
    v5 = 0;
  v6 = NtWaitForSingleObject(EventHandle, 0, v5);
  v1 = v6;
  if ( v6 < 0 || v6 == 258 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    v8 = 20;
    goto LABEL_22;
  }
  RtlInitUnicodeString(&DestinationString, L"\\LSA_ISO_DISABLE_CREDENTIAL_GUARD");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = NtOpenEvent(&Handle, 0x1F0003u, &ObjectAttributes);
  if ( v1 == -1073741772 )
    goto LABEL_3;
  byte_1801A0BC9 = LsapIsCredentialGuardAllowedToRun(Handle);
LABEL_23:
  if ( EventHandle )
    NtClose(EventHandle);
  if ( Handle )
    NtClose(Handle);
  if ( v1 == 258 )
    return (unsigned int)-1073741604;
  return v1;
}

```

## disassembly

```asm
0x1800ec388  mov     [rsp-8+arg_18], rbx
0x1800ec38d  push    rbp
0x1800ec38e  mov     rbp, rsp
0x1800ec391  sub     rsp, 70h
0x1800ec395  xorps   xmm1, xmm1
0x1800ec398  mov     [rbp+arg_8], 0
0x1800ec3a0  xorps   xmm0, xmm0
0x1800ec3a3  mov     [rbp+EventHandle], 0
0x1800ec3ab  lea     rdx, aLsaIsoReady; "\\LSA_ISO_READY"
0x1800ec3b2  mov     [rbp+Handle], 0
0x1800ec3ba  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800ec3be  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800ec3c2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1800ec3c6  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1800ec3ca  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1800ec3ce  call    cs:__imp_RtlInitUnicodeString
0x1800ec3d5  nop     dword ptr [rax+rax+00h]
0x1800ec3da  lea     rax, [rbp+DestinationString]
0x1800ec3de  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800ec3e5  xorps   xmm0, xmm0
0x1800ec3e8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800ec3ec  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800ec3f0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800ec3f8  mov     edx, 100001h; DesiredAccess
0x1800ec3fd  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800ec404  lea     rcx, [rbp+EventHandle]; EventHandle
0x1800ec408  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ec40d  call    cs:__imp_NtOpenEvent
0x1800ec414  nop     dword ptr [rax+rax+00h]
0x1800ec419  mov     ebx, eax
0x1800ec41b  cmp     eax, 0C0000034h
0x1800ec420  jnz     short loc_1800EC49B
0x1800ec422  lea     rdx, aLsaIsoReadyD; "\\LSA_ISO_READY_D"
0x1800ec429  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800ec42d  call    cs:__imp_RtlInitUnicodeString
0x1800ec434  nop     dword ptr [rax+rax+00h]
0x1800ec439  lea     rax, [rbp+DestinationString]
0x1800ec43d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800ec444  xorps   xmm0, xmm0
0x1800ec447  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800ec44b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800ec44f  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800ec457  mov     edx, 100001h; DesiredAccess
0x1800ec45c  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800ec463  lea     rcx, [rbp+EventHandle]; EventHandle
0x1800ec467  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ec46c  call    cs:__imp_NtOpenEvent
0x1800ec473  nop     dword ptr [rax+rax+00h]
0x1800ec478  mov     ebx, eax
0x1800ec47a  cmp     eax, 0C0000034h
0x1800ec47f  jnz     short loc_1800EC48F
0x1800ec481  mov     cs:byte_1801A0BC9, 0
0x1800ec488  xor     ebx, ebx
0x1800ec48a  jmp     loc_1800EC5BB
0x1800ec48f  test    eax, eax
0x1800ec491  js      loc_1800EC582
0x1800ec497  xor     al, al
0x1800ec499  jmp     short loc_1800EC4A5
0x1800ec49b  test    eax, eax
0x1800ec49d  js      loc_1800EC582
0x1800ec4a3  mov     al, 1
0x1800ec4a5  mov     cs:byte_1801A0BC8, al
0x1800ec4ab  call    cs:__imp_IsDebuggerPresent
0x1800ec4b2  nop     dword ptr [rax+rax+00h]
0x1800ec4b7  test    eax, eax
0x1800ec4b9  jnz     short loc_1800EC4C3
0x1800ec4bb  mov     [rbp+arg_8], 0FFFFFFFFC4653600h
0x1800ec4c3  xor     ecx, ecx
0x1800ec4c5  lea     r8, [rbp+arg_8]
0x1800ec4c9  test    eax, eax
0x1800ec4cb  cmovnz  r8, rcx; Timeout
0x1800ec4cf  mov     rcx, [rbp+EventHandle]; Handle
0x1800ec4d3  xor     edx, edx; Alertable
0x1800ec4d5  call    cs:__imp_NtWaitForSingleObject
0x1800ec4dc  nop     dword ptr [rax+rax+00h]
0x1800ec4e1  mov     ebx, eax
0x1800ec4e3  test    eax, eax
0x1800ec4e5  js      short loc_1800EC562
0x1800ec4e7  cmp     eax, 102h
0x1800ec4ec  jz      short loc_1800EC562
0x1800ec4ee  lea     rdx, aLsaIsoDisableC; "\\LSA_ISO_DISABLE_CREDENTIAL_GUARD"
0x1800ec4f5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800ec4f9  call    cs:__imp_RtlInitUnicodeString
0x1800ec500  nop     dword ptr [rax+rax+00h]
0x1800ec505  lea     rax, [rbp+DestinationString]
0x1800ec509  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800ec510  xorps   xmm0, xmm0
0x1800ec513  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800ec517  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800ec51b  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800ec523  mov     edx, 1F0003h; DesiredAccess
0x1800ec528  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800ec52f  lea     rcx, [rbp+Handle]; EventHandle
0x1800ec533  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ec538  call    cs:__imp_NtOpenEvent
0x1800ec53f  nop     dword ptr [rax+rax+00h]
0x1800ec544  mov     ebx, eax
0x1800ec546  cmp     eax, 0C0000034h
0x1800ec54b  jz      loc_1800EC481
0x1800ec551  mov     rcx, [rbp+Handle]; EventHandle
0x1800ec555  call    ?LsapIsCredentialGuardAllowedToRun@@YAEPEAX@Z; LsapIsCredentialGuardAllowedToRun(void *)
0x1800ec55a  mov     cs:byte_1801A0BC9, al
0x1800ec560  jmp     short loc_1800EC5BB
0x1800ec562  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec569  lea     rax, WPP_GLOBAL_Control
0x1800ec570  cmp     rcx, rax
0x1800ec573  jz      short loc_1800EC5BB
0x1800ec575  test    byte ptr [rcx+1Ch], 1
0x1800ec579  jz      short loc_1800EC5BB
0x1800ec57b  mov     edx, 14h
0x1800ec580  jmp     short loc_1800EC5A0
0x1800ec582  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec589  lea     rax, WPP_GLOBAL_Control
0x1800ec590  cmp     rcx, rax
0x1800ec593  jz      short loc_1800EC5BB
0x1800ec595  test    byte ptr [rcx+1Ch], 1
0x1800ec599  jz      short loc_1800EC5BB
0x1800ec59b  mov     edx, 13h
0x1800ec5a0  mov     rcx, [rcx+10h]
0x1800ec5a4  lea     r9, aLsapwaitfortru_0; "LsapWaitForTrustletStartup"
0x1800ec5ab  lea     r8, WPP_e5da1992a0263c0d539144257ad05029_Traceguids
0x1800ec5b2  mov     [rsp+70h+var_50], ebx
0x1800ec5b6  call    WPP_SF_sd
0x1800ec5bb  mov     rcx, [rbp+EventHandle]; Handle
0x1800ec5bf  test    rcx, rcx
0x1800ec5c2  jz      short loc_1800EC5D0
0x1800ec5c4  call    cs:__imp_NtClose
0x1800ec5cb  nop     dword ptr [rax+rax+00h]
0x1800ec5d0  mov     rcx, [rbp+Handle]; Handle
0x1800ec5d4  test    rcx, rcx
0x1800ec5d7  jz      short loc_1800EC5E5
0x1800ec5d9  call    cs:__imp_NtClose
0x1800ec5e0  nop     dword ptr [rax+rax+00h]
0x1800ec5e5  cmp     ebx, 102h
0x1800ec5eb  mov     eax, 0C00000DCh
0x1800ec5f0  cmovz   ebx, eax
0x1800ec5f3  mov     eax, ebx
0x1800ec5f5  mov     rbx, [rsp+70h+arg_18]
0x1800ec5fd  add     rsp, 70h
0x1800ec601  pop     rbp
0x1800ec602  retn
```
