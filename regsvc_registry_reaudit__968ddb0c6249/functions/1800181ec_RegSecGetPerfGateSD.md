# RegSecGetPerfGateSD

- ea: `0x1800181ec`
- end: `0x18001835e`
- name: `RegSecGetPerfGateSD`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800180b4`

## callees

- `0x1800181ec`
- `0x180018538`
- `0x18001d698`

## import_xrefs

- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180018314`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180018314`
- `ntdll!NtOpenThreadToken` at `0x180018259`
- `ntdll!NtOpenThreadToken` at `0x180018259`
- `ntdll!NtClose` at `0x1800182c9`
- `ntdll!NtClose` at `0x1800182ee`
- `ntdll!NtClose` at `0x1800182c9`
- `ntdll!NtClose` at `0x1800182ee`
- `ntdll!NtSetInformationThread` at `0x180018283`
- `ntdll!NtSetInformationThread` at `0x1800182bd`
- `ntdll!NtSetInformationThread` at `0x180018283`
- `ntdll!NtSetInformationThread` at `0x1800182bd`
- `ntdll!RtlFreeHeap` at `0x180018331`
- `ntdll!RtlFreeHeap` at `0x180018349`
- `ntdll!RtlFreeHeap` at `0x180018331`
- `ntdll!RtlFreeHeap` at `0x180018349`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001822c`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001822c`

## string_xrefs

- `0x180018209`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Perflib`

## pseudocode

```c
PSECURITY_DESCRIPTOR RegSecGetPerfGateSD()
{
  NTSTATUS v0; // eax
  int v1; // edi
  NTSTATUS v2; // ebx
  int SDFromRegistry; // ebx
  bool v5; // sf
  PSECURITY_DESCRIPTOR v6; // rbx
  int v7; // [rsp+20h] [rbp-58h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  __int128 v9; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+50h] [rbp-28h]
  __int64 v11; // [rsp+58h] [rbp-20h]
  __int128 v12; // [rsp+60h] [rbp-18h]
  HANDLE Handle; // [rsp+A0h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+A8h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp+38h] BYREF
  __int64 ThreadInformation; // [rsp+B8h] [rbp+40h] BYREF

  *(_QWORD *)&v9 = 48;
  Handle = 0;
  TokenHandle = 0;
  ThreadInformation = 0;
  DestinationString = 0;
  SecurityDescriptor = 0;
  v11 = 64;
  RtlInitUnicodeStringEx(&DestinationString, PerfRemoteRegistryKey);
  *((_QWORD *)&v9 + 1) = 0;
  p_DestinationString = &DestinationString;
  v12 = 0;
  v0 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, &TokenHandle);
  if ( ((v0 + 1073741732) & 0xFFFFFFDF) != 0 )
  {
    if ( v0 )
      return 0;
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  else
  {
    TokenHandle = 0;
  }
  v1 = Wow64NtOpenKey(&Handle, 0x20019u, &v9, 0, v7);
  if ( TokenHandle )
  {
    v2 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    NtClose(TokenHandle);
    if ( v2 < 0 )
      return 0;
  }
  if ( v1 < 0 )
    return 0;
  SDFromRegistry = RegSecReadSDFromRegistry(Handle, (struct _ACL **)&SecurityDescriptor);
  NtClose(Handle);
  v5 = SDFromRegistry < 0;
  v6 = SecurityDescriptor;
  if ( v5 && SecurityDescriptor )
  {
    SecurityDescriptor = 0;
    LOBYTE(Handle) = 0;
    if ( RtlGetGroupSecurityDescriptor(v6, &SecurityDescriptor, (PBOOLEAN)&Handle) >= 0 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SecurityDescriptor);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1800181ec  push    rbp
0x1800181ee  push    rbx
0x1800181ef  push    rsi
0x1800181f0  push    rdi
0x1800181f1  mov     rbp, rsp
0x1800181f4  sub     rsp, 78h
0x1800181f8  xor     esi, esi
0x1800181fa  mov     qword ptr [rbp+var_38], 30h ; '0'
0x180018202  xorps   xmm0, xmm0
0x180018205  mov     [rbp+Handle], rsi
0x180018209  lea     rdx, PerfRemoteRegistryKey; "\\Registry\\Machine\\Software\\Microsof"...
0x180018210  mov     [rbp+TokenHandle], rsi
0x180018214  lea     rcx, [rbp+DestinationString]; DestinationString
0x180018218  mov     [rbp+ThreadInformation], rsi
0x18001821c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180018220  mov     [rbp+SecurityDescriptor], rsi
0x180018224  mov     [rbp+var_20], 40h ; '@'
0x18001822c  call    cs:__imp_RtlInitUnicodeStringEx
0x180018232  lea     rax, [rbp+DestinationString]
0x180018236  mov     [rbp+var_30], rsi
0x18001823a  xorps   xmm0, xmm0
0x18001823d  mov     [rbp+var_28], rax
0x180018241  lea     rbx, [rsi-2]
0x180018245  mov     r8b, 1; OpenAsSelf
0x180018248  mov     rcx, rbx; ThreadHandle
0x18001824b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001824f  mov     edx, 2000000h; DesiredAccess
0x180018254  movdqu  [rbp+var_18], xmm0
0x180018259  call    cs:__imp_NtOpenThreadToken
0x18001825f  lea     ecx, [rax+3FFFFFA4h]
0x180018265  test    ecx, 0FFFFFFDFh
0x18001826b  jz      short loc_18001828B
0x18001826d  test    eax, eax
0x18001826f  jnz     short loc_1800182D7
0x180018271  lea     r9d, [rsi+8]; ThreadInformationLength
0x180018275  mov     [rbp+ThreadInformation], rsi
0x180018279  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18001827d  mov     rcx, rbx; ThreadHandle
0x180018280  lea     edx, [rsi+5]; ThreadInformationClass
0x180018283  call    cs:__imp_NtSetInformationThread
0x180018289  jmp     short loc_18001828F
0x18001828b  mov     [rbp+TokenHandle], rsi
0x18001828f  xor     r9d, r9d; int
0x180018292  lea     r8, [rbp+var_38]; int
0x180018296  mov     edx, 20019h; int
0x18001829b  lea     rcx, [rbp+Handle]; int
0x18001829f  call    Wow64NtOpenKey
0x1800182a4  mov     edi, eax
0x1800182a6  cmp     [rbp+TokenHandle], rsi
0x1800182aa  jz      short loc_1800182D3
0x1800182ac  mov     r9d, 8; ThreadInformationLength
0x1800182b2  lea     r8, [rbp+TokenHandle]; ThreadInformation
0x1800182b6  mov     rcx, rbx; ThreadHandle
0x1800182b9  lea     edx, [r9-3]; ThreadInformationClass
0x1800182bd  call    cs:__imp_NtSetInformationThread
0x1800182c3  mov     rcx, [rbp+TokenHandle]; Handle
0x1800182c7  mov     ebx, eax
0x1800182c9  call    cs:__imp_NtClose
0x1800182cf  test    ebx, ebx
0x1800182d1  js      short loc_1800182D7
0x1800182d3  test    edi, edi
0x1800182d5  jns     short loc_1800182DB
0x1800182d7  xor     eax, eax
0x1800182d9  jmp     short loc_180018355
0x1800182db  mov     rcx, [rbp+Handle]; Handle
0x1800182df  lea     rdx, [rbp+SecurityDescriptor]
0x1800182e3  call    RegSecReadSDFromRegistry
0x1800182e8  mov     rcx, [rbp+Handle]; Handle
0x1800182ec  mov     ebx, eax
0x1800182ee  call    cs:__imp_NtClose
0x1800182f4  test    ebx, ebx
0x1800182f6  mov     rbx, [rbp+SecurityDescriptor]
0x1800182fa  jns     short loc_180018352
0x1800182fc  test    rbx, rbx
0x1800182ff  jz      short loc_180018352
0x180018301  lea     r8, [rbp+Handle]; GroupDefaulted
0x180018305  mov     [rbp+SecurityDescriptor], rsi
0x180018309  lea     rdx, [rbp+SecurityDescriptor]; Group
0x18001830d  mov     byte ptr [rbp+Handle], sil
0x180018311  mov     rcx, rbx; SecurityDescriptor
0x180018314  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18001831a  test    eax, eax
0x18001831c  js      short loc_180018337
0x18001831e  mov     rcx, gs:60h
0x180018327  xor     edx, edx; Flags
0x180018329  mov     r8, [rbp+SecurityDescriptor]; P
0x18001832d  mov     rcx, [rcx+30h]; HeapHandle
0x180018331  call    cs:__imp_RtlFreeHeap
0x180018337  mov     rcx, gs:60h
0x180018340  mov     r8, rbx; P
0x180018343  xor     edx, edx; Flags
0x180018345  mov     rcx, [rcx+30h]; HeapHandle
0x180018349  call    cs:__imp_RtlFreeHeap
0x18001834f  mov     rbx, rsi
0x180018352  mov     rax, rbx
0x180018355  add     rsp, 78h
0x180018359  pop     rdi
0x18001835a  pop     rsi
0x18001835b  pop     rbx
0x18001835c  pop     rbp
0x18001835d  retn
```
