# Sid::MakeLocalAccountDomain(void)

- ea: `0x1401c7b08`
- end: `0x1401c7cd2`
- name: `?MakeLocalAccountDomain@Sid@@QEAAPEAVFrsStatus@@XZ`
- size: `458`
- prototype: `struct FrsStatus *__fastcall(Sid *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1401c7cd8`

## callees

- `0x1401b9494`
- `0x1401c7b08`
- `0x1401c8070`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401c7b70`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7be0`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7c79`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7b70`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7be0`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7c79`
- `ntdll!RtlNtStatusToDosError` at `0x1401c7b80`
- `ntdll!RtlNtStatusToDosError` at `0x1401c7bf0`
- `ntdll!RtlNtStatusToDosError` at `0x1401c7b80`
- `ntdll!RtlNtStatusToDosError` at `0x1401c7bf0`
- `ADVAPI32!LsaClose` at `0x1401c7c4b`
- `ADVAPI32!LsaClose` at `0x1401c7c4b`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1401c7bce`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1401c7bce`
- `ADVAPI32!LsaOpenPolicy` at `0x1401c7b50`
- `ADVAPI32!LsaOpenPolicy` at `0x1401c7b50`
- `ADVAPI32!LsaFreeMemory` at `0x1401c7c64`
- `ADVAPI32!LsaFreeMemory` at `0x1401c7c64`

## string_xrefs

- `0x1401c7b65`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c7b5c`: `Sid::MakeLocalAccountDomain`

## pseudocode

```c
struct FrsStatus *__fastcall Sid::MakeLocalAccountDomain(Sid *this)
{
  __int64 v2; // rdi
  int v3; // esi
  DWORD v4; // ebx
  ULONG v5; // eax
  __int64 v6; // rcx
  struct FrsStatus *v7; // rbx
  int v8; // esi
  DWORD CurrentThreadId; // ebx
  ULONG v10; // eax
  __int64 v11; // rcx
  DWORD v12; // eax
  __int64 v13; // rcx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+B8h] [rbp+38h] BYREF
  PVOID Buffer; // [rsp+C0h] [rbp+40h] BYREF

  v2 = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Buffer = 0;
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 0x801u, &PolicyHandle);
  if ( v3 >= 0
    || (v4 = GetCurrentThreadId(),
        v5 = RtlNtStatusToDosError(v3),
        (v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v6,
                                    v5,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                    "Sid::MakeLocalAccountDomain",
                                    879,
                                    v4,
                                    0)) == 0) )
  {
    v8 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    if ( v8 >= 0
      || (CurrentThreadId = GetCurrentThreadId(),
          v10 = RtlNtStatusToDosError(v8),
          (v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                      v11,
                                      v10,
                                      0,
                                      1,
                                      "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                      "Sid::MakeLocalAccountDomain",
                                      890,
                                      CurrentThreadId,
                                      0)) == 0) )
    {
      v7 = Sid::Set(this, *((struct _SID **)Buffer + 2));
    }
  }
  if ( PolicyHandle )
  {
    LsaClose(PolicyHandle);
    PolicyHandle = 0;
  }
  if ( Buffer )
  {
    LsaFreeMemory(Buffer);
    Buffer = 0;
  }
  if ( v7 )
  {
    v12 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v13,
                                 *((unsigned int *)v7 + 1),
                                 *((unsigned int *)v7 + 2),
                                 *(unsigned int *)v7,
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 "Sid::MakeLocalAccountDomain",
                                 916,
                                 v12,
                                 v7);
  }
  return (struct FrsStatus *)v2;
}

```

## disassembly

```asm
0x1401c7b08  mov     [rsp-28h+arg_0], rbx
0x1401c7b0d  mov     [rsp-28h+arg_18], rsi
0x1401c7b12  push    rbp
0x1401c7b13  push    rdi
0x1401c7b14  push    r12
0x1401c7b16  push    r14
0x1401c7b18  push    r15
0x1401c7b1a  mov     rbp, rsp
0x1401c7b1d  sub     rsp, 80h
0x1401c7b24  xorps   xmm0, xmm0
0x1401c7b27  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1401c7b2b  mov     r14, rcx
0x1401c7b2e  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1401c7b32  xor     edi, edi
0x1401c7b34  xor     ecx, ecx; SystemName
0x1401c7b36  mov     r8d, 801h; DesiredAccess
0x1401c7b3c  mov     [rbp+PolicyHandle], rdi
0x1401c7b40  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1401c7b44  mov     [rbp+Buffer], rdi
0x1401c7b48  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1401c7b4c  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1401c7b50  call    cs:__imp_LsaOpenPolicy
0x1401c7b57  nop     dword ptr [rax+rax+00h]
0x1401c7b5c  lea     r15, aSidMakelocalac_0; "Sid::MakeLocalAccountDomain"
0x1401c7b63  mov     esi, eax
0x1401c7b65  lea     r12, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c7b6c  test    eax, eax
0x1401c7b6e  jns     short loc_1401C7BC1
0x1401c7b70  call    cs:__imp_GetCurrentThreadId
0x1401c7b77  nop     dword ptr [rax+rax+00h]
0x1401c7b7c  mov     ecx, esi; Status
0x1401c7b7e  mov     ebx, eax
0x1401c7b80  call    cs:__imp_RtlNtStatusToDosError
0x1401c7b87  nop     dword ptr [rax+rax+00h]
0x1401c7b8c  mov     [rsp+80h+var_40], rdi
0x1401c7b91  lea     r9d, [rdi+1]
0x1401c7b95  mov     [rsp+80h+var_48], ebx
0x1401c7b99  xor     r8d, r8d
0x1401c7b9c  mov     [rsp+80h+var_50], 36Fh
0x1401c7ba4  mov     edx, eax
0x1401c7ba6  mov     [rsp+80h+var_58], r15
0x1401c7bab  mov     [rsp+80h+var_60], r12
0x1401c7bb0  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c7bb5  mov     rbx, rax
0x1401c7bb8  test    rax, rax
0x1401c7bbb  jnz     loc_1401C7C42
0x1401c7bc1  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1401c7bc5  lea     r8, [rbp+Buffer]; Buffer
0x1401c7bc9  mov     edx, 5; InformationClass
0x1401c7bce  call    cs:__imp_LsaQueryInformationPolicy
0x1401c7bd5  nop     dword ptr [rax+rax+00h]
0x1401c7bda  mov     esi, eax
0x1401c7bdc  test    eax, eax
0x1401c7bde  jns     short loc_1401C7C2F
0x1401c7be0  call    cs:__imp_GetCurrentThreadId
0x1401c7be7  nop     dword ptr [rax+rax+00h]
0x1401c7bec  mov     ecx, esi; Status
0x1401c7bee  mov     ebx, eax
0x1401c7bf0  call    cs:__imp_RtlNtStatusToDosError
0x1401c7bf7  nop     dword ptr [rax+rax+00h]
0x1401c7bfc  mov     [rsp+80h+var_40], rdi
0x1401c7c01  mov     r9d, 1
0x1401c7c07  mov     [rsp+80h+var_48], ebx
0x1401c7c0b  xor     r8d, r8d
0x1401c7c0e  mov     [rsp+80h+var_50], 37Ah
0x1401c7c16  mov     edx, eax
0x1401c7c18  mov     [rsp+80h+var_58], r15
0x1401c7c1d  mov     [rsp+80h+var_60], r12
0x1401c7c22  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c7c27  mov     rbx, rax
0x1401c7c2a  test    rax, rax
0x1401c7c2d  jnz     short loc_1401C7C42
0x1401c7c2f  mov     rax, [rbp+Buffer]
0x1401c7c33  mov     rcx, r14; this
0x1401c7c36  mov     rdx, [rax+10h]; struct _SID *
0x1401c7c3a  call    ?Set@Sid@@QEAAPEAVFrsStatus@@PEBU_SID@@@Z; Sid::Set(_SID const *)
0x1401c7c3f  mov     rbx, rax
0x1401c7c42  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1401c7c46  test    rcx, rcx
0x1401c7c49  jz      short loc_1401C7C5B
0x1401c7c4b  call    cs:__imp_LsaClose
0x1401c7c52  nop     dword ptr [rax+rax+00h]
0x1401c7c57  mov     [rbp+PolicyHandle], rdi
0x1401c7c5b  mov     rcx, [rbp+Buffer]; Buffer
0x1401c7c5f  test    rcx, rcx
0x1401c7c62  jz      short loc_1401C7C74
0x1401c7c64  call    cs:__imp_LsaFreeMemory
0x1401c7c6b  nop     dword ptr [rax+rax+00h]
0x1401c7c70  mov     [rbp+Buffer], rdi
0x1401c7c74  test    rbx, rbx
0x1401c7c77  jz      short loc_1401C7CB2
0x1401c7c79  call    cs:__imp_GetCurrentThreadId
0x1401c7c80  nop     dword ptr [rax+rax+00h]
0x1401c7c85  mov     r9d, [rbx]
0x1401c7c88  mov     r8d, [rbx+8]
0x1401c7c8c  mov     edx, [rbx+4]
0x1401c7c8f  mov     [rsp+80h+var_40], rbx
0x1401c7c94  mov     [rsp+80h+var_48], eax
0x1401c7c98  mov     [rsp+80h+var_50], 394h
0x1401c7ca0  mov     [rsp+80h+var_58], r15
0x1401c7ca5  mov     [rsp+80h+var_60], r12
0x1401c7caa  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c7caf  mov     rdi, rax
0x1401c7cb2  lea     r11, [rsp+80h+var_s0]
0x1401c7cba  mov     rax, rdi
0x1401c7cbd  mov     rbx, [r11+30h]
0x1401c7cc1  mov     rsi, [r11+48h]
0x1401c7cc5  mov     rsp, r11
0x1401c7cc8  pop     r15
0x1401c7cca  pop     r14
0x1401c7ccc  pop     r12
0x1401c7cce  pop     rdi
0x1401c7ccf  pop     rbp
0x1401c7cd0  retn
```
