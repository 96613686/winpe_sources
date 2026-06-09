# RegSecCheckAllowedPaths

- ea: `0x18001782c`
- end: `0x180017b4b`
- name: `RegSecCheckAllowedPaths`
- size: `799`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180017dfc`

## callees

- `0x180007740`
- `0x18001782c`
- `0x180018364`
- `0x18001d698`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180017a05`
- `ntdll!RtlReleaseResource` at `0x180017acb`
- `ntdll!RtlReleaseResource` at `0x180017a05`
- `ntdll!RtlReleaseResource` at `0x180017acb`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800179af`
- `ntdll!RtlAcquireResourceExclusive` at `0x180017a5f`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800179af`
- `ntdll!RtlAcquireResourceExclusive` at `0x180017a5f`
- `ntdll!NtOpenThreadToken` at `0x1800178ee`
- `ntdll!NtOpenThreadToken` at `0x1800178ee`
- `ntdll!NtClose` at `0x180017973`
- `ntdll!NtClose` at `0x180017ad4`
- `ntdll!NtClose` at `0x180017b1f`
- `ntdll!NtClose` at `0x180017973`
- `ntdll!NtClose` at `0x180017ad4`
- `ntdll!NtClose` at `0x180017b1f`
- `ntdll!NtSetInformationThread` at `0x180017922`
- `ntdll!NtSetInformationThread` at `0x180017965`
- `ntdll!NtSetInformationThread` at `0x180017922`
- `ntdll!NtSetInformationThread` at `0x180017965`
- `ntdll!RtlFreeHeap` at `0x1800179d1`
- `ntdll!RtlFreeHeap` at `0x1800179ea`
- `ntdll!RtlFreeHeap` at `0x180017a87`
- `ntdll!RtlFreeHeap` at `0x180017aa0`
- `ntdll!RtlFreeHeap` at `0x1800179d1`
- `ntdll!RtlFreeHeap` at `0x1800179ea`
- `ntdll!RtlFreeHeap` at `0x180017a87`
- `ntdll!RtlFreeHeap` at `0x180017aa0`
- `ntdll!NtQueryKey` at `0x180017a3c`
- `ntdll!NtQueryKey` at `0x180017a3c`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001788e`
- `ntdll!RtlInitUnicodeStringEx` at `0x180017af1`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001788e`
- `ntdll!RtlInitUnicodeStringEx` at `0x180017af1`

## string_xrefs

- `0x180017882`: `\Registry\Machine\System\CurrentControlSet\Control\SecurePipeServers\winreg\AllowedPaths`
- `0x180017ae2`: `\Registry\Machine\System\CurrentControlSet\Control\SecurePipeServers\winreg\AllowedExactPaths`

## pseudocode

```c
NTSTATUS RegSecCheckAllowedPaths()
{
  __int64 *v0; // rdi
  char v1; // r14
  PVOID *v2; // rsi
  PVOID *v3; // r12
  __int64 *i; // r13
  NTSTATUS result; // eax
  int v6; // ebx
  NTSTATUS v7; // r15d
  HANDLE v8; // rbx
  NTSTATUS v9; // r15d
  int ResultLength; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v12; // [rsp+38h] [rbp-C8h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+7Ch] [rbp-84h]
  __int128 v20; // [rsp+80h] [rbp-80h]
  __int64 KeyInformation[30]; // [rsp+90h] [rbp-70h] BYREF

  KeyHandle = 0;
  DWORD1(v16) = 0;
  v19 = 0;
  DestinationString = 0;
  TokenHandle = 0;
  ThreadInformation = 0;
  v12 = 0;
  RtlInitUnicodeStringEx(&DestinationString, AllowedPathsKey);
  v0 = &AllowedPathsChange;
  v1 = 0;
  v2 = &MachineAllowedPaths;
  v3 = &MachineAllowedPathsBase;
  for ( i = &MachineAllowedPathsCount; ; i = (__int64 *)&MachineAllowedExactPathsCount )
  {
    LODWORD(v16) = 48;
    p_DestinationString = &DestinationString;
    *((_QWORD *)&v16 + 1) = 0;
    v18 = 64;
    v20 = 0;
    result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, &TokenHandle);
    if ( ((result + 1073741732) & 0xFFFFFFDF) != 0 )
    {
      if ( result )
        return result;
      ThreadInformation = 0;
      NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    }
    else
    {
      TokenHandle = 0;
    }
    v6 = Wow64NtOpenKey(&KeyHandle, 0x20019u, &v16, 0, ResultLength);
    if ( TokenHandle )
    {
      v7 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
      NtClose(TokenHandle);
      if ( v7 < 0 )
      {
        v6 = v7;
LABEL_10:
        if ( v6 != -1073741766 && v6 != -1073741772 )
          return v6;
        if ( *v0 )
        {
          RtlAcquireResourceExclusive(RegSecReloadLock, 1u);
          if ( *v0 )
          {
            if ( *v2 )
            {
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v2);
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v3);
              *v2 = 0;
              *v3 = 0;
              *(_DWORD *)i = 0;
            }
            *v0 = 0;
          }
          RtlReleaseResource(RegSecReloadLock);
        }
        v6 = 0;
        if ( v1 )
          return v6;
        goto LABEL_28;
      }
    }
    if ( v6 < 0 )
      goto LABEL_10;
    v8 = KeyHandle;
    v9 = NtQueryKey(KeyHandle, KeyBasicInformation, KeyInformation, 0xE4u, &v12);
    if ( v9 < 0 )
      break;
    if ( KeyInformation[0] > *v0 )
    {
      RtlAcquireResourceExclusive(RegSecReloadLock, 1u);
      if ( KeyInformation[0] > *v0 )
      {
        if ( *v2 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v2);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v3);
          *v2 = 0;
          *v3 = 0;
          *(_DWORD *)i = 0;
        }
        RegSecReadAllowedPath(v8, (__int64)i);
      }
      RtlReleaseResource(RegSecReloadLock);
    }
    NtClose(v8);
    if ( v1 )
      return 0;
LABEL_28:
    v1 = 1;
    RtlInitUnicodeStringEx(&DestinationString, AllowedExactPathsKey);
    v0 = &AllowedExactPathsChange;
    v2 = &MachineAllowedExactPaths;
    v3 = &MachineAllowedExactPathsBase;
  }
  NtClose(v8);
  return v9;
}

```

## disassembly

```asm
0x18001782c  push    rbp
0x18001782e  push    rbx
0x18001782f  push    rsi
0x180017830  push    rdi
0x180017831  push    r12
0x180017833  push    r13
0x180017835  push    r14
0x180017837  push    r15
0x180017839  lea     rbp, [rsp-98h]
0x180017841  sub     rsp, 198h
0x180017848  mov     rax, cs:__security_cookie
0x18001784f  xor     rax, rsp
0x180017852  mov     [rbp+0D0h+var_50], rax
0x180017859  xor     r15d, r15d
0x18001785c  xorps   xmm0, xmm0
0x18001785f  mov     [rsp+1D0h+KeyHandle], r15
0x180017864  mov     [rsp+1D0h+var_16C], r15d
0x180017869  mov     [rsp+1D0h+var_154], r15d
0x18001786e  movups  xmmword ptr [rsp+1D0h+DestinationString.Length], xmm0
0x180017873  mov     [rsp+1D0h+TokenHandle], r15
0x180017878  mov     [rsp+1D0h+ThreadInformation], r15
0x18001787d  mov     [rsp+1D0h+var_198], r15d
0x180017882  lea     rdx, AllowedPathsKey; "\\Registry\\Machine\\System\\CurrentCon"...
0x180017889  lea     rcx, [rsp+1D0h+DestinationString]; DestinationString
0x18001788e  call    cs:__imp_RtlInitUnicodeStringEx
0x180017894  lea     rdi, AllowedPathsChange
0x18001789b  mov     r14b, r15b
0x18001789e  lea     rsi, MachineAllowedPaths
0x1800178a5  lea     r12, MachineAllowedPathsBase
0x1800178ac  lea     r13, MachineAllowedPathsCount
0x1800178b3  lea     rax, [rsp+1D0h+DestinationString]
0x1800178b8  mov     [rsp+1D0h+var_170], 30h ; '0'
0x1800178c0  xorps   xmm0, xmm0
0x1800178c3  mov     [rsp+1D0h+var_160], rax
0x1800178c8  lea     r9, [rsp+1D0h+TokenHandle]; TokenHandle
0x1800178cd  mov     [rsp+1D0h+var_168], r15
0x1800178d2  mov     r8b, 1; OpenAsSelf
0x1800178d5  mov     [rsp+1D0h+var_158], 40h ; '@'
0x1800178dd  mov     edx, 2000000h; DesiredAccess
0x1800178e2  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800178e9  movdqu  [rbp+0D0h+var_150], xmm0
0x1800178ee  call    cs:__imp_NtOpenThreadToken
0x1800178f4  lea     ecx, [rax+3FFFFFA4h]
0x1800178fa  test    ecx, 0FFFFFFDFh
0x180017900  jz      short loc_18001792A
0x180017902  test    eax, eax
0x180017904  jnz     loc_180017B28
0x18001790a  lea     r9d, [rax+8]; ThreadInformationLength
0x18001790e  mov     [rsp+1D0h+ThreadInformation], r15
0x180017913  lea     r8, [rsp+1D0h+ThreadInformation]; ThreadInformation
0x180017918  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18001791f  lea     edx, [rax+5]; ThreadInformationClass
0x180017922  call    cs:__imp_NtSetInformationThread
0x180017928  jmp     short loc_18001792F
0x18001792a  mov     [rsp+1D0h+TokenHandle], r15
0x18001792f  xor     r9d, r9d; int
0x180017932  lea     r8, [rsp+1D0h+var_170]; int
0x180017937  mov     edx, 20019h; int
0x18001793c  lea     rcx, [rsp+1D0h+KeyHandle]; int
0x180017941  call    Wow64NtOpenKey
0x180017946  mov     ebx, eax
0x180017948  cmp     [rsp+1D0h+TokenHandle], r15
0x18001794d  jz      short loc_180017989
0x18001794f  mov     r9d, 8; ThreadInformationLength
0x180017955  lea     r8, [rsp+1D0h+TokenHandle]; ThreadInformation
0x18001795a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180017961  lea     edx, [r9-3]; ThreadInformationClass
0x180017965  call    cs:__imp_NtSetInformationThread
0x18001796b  mov     rcx, [rsp+1D0h+TokenHandle]; Handle
0x180017970  mov     r15d, eax
0x180017973  call    cs:__imp_NtClose
0x180017979  test    r15d, r15d
0x18001797c  jns     short loc_180017986
0x18001797e  mov     ebx, r15d
0x180017981  xor     r15d, r15d
0x180017984  jmp     short loc_180017991
0x180017986  xor     r15d, r15d
0x180017989  test    ebx, ebx
0x18001798b  jns     loc_180017A1E
0x180017991  cmp     ebx, 0C000003Ah
0x180017997  jz      short loc_1800179A1
0x180017999  cmp     ebx, 0C0000034h
0x18001799f  jnz     short loc_180017A17
0x1800179a1  cmp     [rdi], r15
0x1800179a4  jz      short loc_180017A0B
0x1800179a6  mov     rcx, cs:RegSecReloadLock; Resource
0x1800179ad  mov     dl, 1; Wait
0x1800179af  call    cs:__imp_RtlAcquireResourceExclusive
0x1800179b5  cmp     [rdi], r15
0x1800179b8  jz      short loc_1800179FE
0x1800179ba  mov     r8, [rsi]; P
0x1800179bd  test    r8, r8
0x1800179c0  jz      short loc_1800179FB
0x1800179c2  mov     rcx, gs:60h
0x1800179cb  xor     edx, edx; Flags
0x1800179cd  mov     rcx, [rcx+30h]; HeapHandle
0x1800179d1  call    cs:__imp_RtlFreeHeap
0x1800179d7  mov     rcx, gs:60h
0x1800179e0  xor     edx, edx; Flags
0x1800179e2  mov     r8, [r12]; P
0x1800179e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800179ea  call    cs:__imp_RtlFreeHeap
0x1800179f0  mov     [rsi], r15
0x1800179f3  mov     [r12], r15
0x1800179f7  mov     [r13+0], r15d
0x1800179fb  mov     [rdi], r15
0x1800179fe  mov     rcx, cs:RegSecReloadLock; Resource
0x180017a05  call    cs:__imp_RtlReleaseResource
0x180017a0b  mov     ebx, r15d
0x180017a0e  test    r14b, r14b
0x180017a11  jz      loc_180017AE2
0x180017a17  mov     eax, ebx
0x180017a19  jmp     loc_180017B28
0x180017a1e  mov     rbx, [rsp+1D0h+KeyHandle]
0x180017a23  lea     rax, [rsp+1D0h+var_198]
0x180017a28  mov     rcx, rbx; KeyHandle
0x180017a2b  mov     qword ptr [rsp+1D0h+ResultLength], rax; ResultLength
0x180017a30  mov     r9d, 0E4h; Length
0x180017a36  lea     r8, [rbp+0D0h+KeyInformation]; KeyInformation
0x180017a3a  xor     edx, edx; KeyInformationClass
0x180017a3c  call    cs:__imp_NtQueryKey
0x180017a42  mov     r15d, eax
0x180017a45  test    eax, eax
0x180017a47  js      loc_180017B1C
0x180017a4d  mov     rax, [rdi]
0x180017a50  cmp     [rbp+0D0h+KeyInformation], rax
0x180017a54  jle     short loc_180017AD1
0x180017a56  mov     rcx, cs:RegSecReloadLock; Resource
0x180017a5d  mov     dl, 1; Wait
0x180017a5f  call    cs:__imp_RtlAcquireResourceExclusive
0x180017a65  mov     rax, [rdi]
0x180017a68  cmp     [rbp+0D0h+KeyInformation], rax
0x180017a6c  jle     short loc_180017AC4
0x180017a6e  mov     r8, [rsi]; P
0x180017a71  xor     edi, edi
0x180017a73  test    r8, r8
0x180017a76  jz      short loc_180017AB1
0x180017a78  mov     rcx, gs:60h
0x180017a81  xor     edx, edx; Flags
0x180017a83  mov     rcx, [rcx+30h]; HeapHandle
0x180017a87  call    cs:__imp_RtlFreeHeap
0x180017a8d  mov     rcx, gs:60h
0x180017a96  xor     edx, edx; Flags
0x180017a98  mov     r8, [r12]; P
0x180017a9c  mov     rcx, [rcx+30h]; HeapHandle
0x180017aa0  call    cs:__imp_RtlFreeHeap
0x180017aa6  mov     [rsi], rdi
0x180017aa9  mov     [r12], rdi
0x180017aad  mov     [r13+0], edi
0x180017ab1  mov     r9, r12
0x180017ab4  mov     qword ptr [rsp+1D0h+ResultLength], r13; __int64
0x180017ab9  mov     r8, rsi
0x180017abc  mov     rcx, rbx; KeyHandle
0x180017abf  call    RegSecReadAllowedPath
0x180017ac4  mov     rcx, cs:RegSecReloadLock; Resource
0x180017acb  call    cs:__imp_RtlReleaseResource
0x180017ad1  mov     rcx, rbx; Handle
0x180017ad4  call    cs:__imp_NtClose
0x180017ada  xor     r15d, r15d
0x180017add  test    r14b, r14b
0x180017ae0  jnz     short loc_180017B18
0x180017ae2  lea     rdx, AllowedExactPathsKey; "\\Registry\\Machine\\System\\CurrentCon"...
0x180017ae9  mov     r14b, 1
0x180017aec  lea     rcx, [rsp+1D0h+DestinationString]; DestinationString
0x180017af1  call    cs:__imp_RtlInitUnicodeStringEx
0x180017af7  lea     rdi, AllowedExactPathsChange
0x180017afe  lea     rsi, MachineAllowedExactPaths
0x180017b05  lea     r12, MachineAllowedExactPathsBase
0x180017b0c  lea     r13, MachineAllowedExactPathsCount
0x180017b13  jmp     loc_1800178B3
0x180017b18  xor     eax, eax
0x180017b1a  jmp     short loc_180017B28
0x180017b1c  mov     rcx, rbx; Handle
0x180017b1f  call    cs:__imp_NtClose
0x180017b25  mov     eax, r15d
0x180017b28  mov     rcx, [rbp+0D0h+var_50]
0x180017b2f  xor     rcx, rsp; StackCookie
0x180017b32  call    __security_check_cookie
0x180017b37  add     rsp, 198h
0x180017b3e  pop     r15
0x180017b40  pop     r14
0x180017b42  pop     r13
0x180017b44  pop     r12
0x180017b46  pop     rdi
0x180017b47  pop     rsi
0x180017b48  pop     rbx
0x180017b49  pop     rbp
0x180017b4a  retn
```
