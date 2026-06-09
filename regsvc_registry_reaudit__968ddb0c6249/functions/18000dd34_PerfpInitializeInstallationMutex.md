# PerfpInitializeInstallationMutex

- ea: `0x18000dd34`
- end: `0x18000df89`
- name: `PerfpInitializeInstallationMutex`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e158`

## callees

- `0x180007740`
- `0x18000dd34`

## import_xrefs

- `ntdll!RtlDeleteBoundaryDescriptor` at `0x18000df52`
- `ntdll!RtlDeleteBoundaryDescriptor` at `0x18000df52`
- `ntdll!NtCreateMutant` at `0x18000df0e`
- `ntdll!NtCreateMutant` at `0x18000df0e`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x18000de0c`
- `ntdll!RtlAddSIDToBoundaryDescriptor` at `0x18000de0c`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x18000dded`
- `ntdll!RtlCreateBoundaryDescriptor` at `0x18000dded`
- `ntdll!RtlNtStatusToDosError` at `0x18000de18`
- `ntdll!RtlNtStatusToDosError` at `0x18000de18`
- `ntdll!NtClose` at `0x18000de9d`
- `ntdll!NtClose` at `0x18000df3c`
- `ntdll!NtClose` at `0x18000de9d`
- `ntdll!NtClose` at `0x18000df3c`
- `ntdll!NtCreatePrivateNamespace` at `0x18000de72`
- `ntdll!NtCreatePrivateNamespace` at `0x18000de72`
- `ntdll!NtOpenPrivateNamespace` at `0x18000de56`
- `ntdll!NtOpenPrivateNamespace` at `0x18000de56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd85`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000dddd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000dddd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000df61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000df61`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000dd7b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000dd7b`

## string_xrefs

- `0x18000debd`: `Installing`

## pseudocode

```c
__int64 __fastcall PerfpInitializeInstallationMutex(void **a1)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  int v4; // eax
  void *v5; // rbx
  void *v6; // rbx
  HANDLE Handle; // [rsp+20h] [rbp-89h] BYREF
  void *MutantHandle; // [rsp+28h] [rbp-81h] BYREF
  __int64 v10; // [rsp+30h] [rbp-79h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-71h] BYREF
  __int64 v12; // [rsp+40h] [rbp-69h] BYREF
  const wchar_t *v13; // [rsp+48h] [rbp-61h]
  DWORD cbSid; // [rsp+50h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-51h] BYREF
  _BYTE pSid[72]; // [rsp+88h] [rbp-21h] BYREF

  SecurityDescriptor = 0;
  v10 = 0;
  Handle = 0;
  MutantHandle = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;BA)(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
    goto LABEL_2;
  Handle = (HANDLE)qword_18002BEF8;
  if ( !qword_18002BEF8 )
  {
    cbSid = 68;
    v12 = 1179664;
    v13 = L"LoadPerf";
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
    {
LABEL_2:
      LastError = GetLastError();
LABEL_3:
      v3 = LastError;
      goto LABEL_22;
    }
    v10 = RtlCreateBoundaryDescriptor(&v12, 0);
    if ( !v10 )
    {
      v3 = 14;
      goto LABEL_22;
    }
    v4 = RtlAddSIDToBoundaryDescriptor(&v10, pSid);
    if ( v4 < 0 )
      goto LABEL_9;
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    ObjectAttributes.SecurityQualityOfService = 0;
    do
    {
      v4 = NtCreatePrivateNamespace(&Handle, 6, &ObjectAttributes, v10);
      if ( v4 != -1073741771 )
        break;
      v4 = NtOpenPrivateNamespace(&Handle, 6, 0, v10);
    }
    while ( v4 == -1073741766 );
    if ( v4 < 0 )
    {
LABEL_9:
      LastError = RtlNtStatusToDosError(v4);
      goto LABEL_3;
    }
    v5 = (void *)_InterlockedCompareExchange64(&qword_18002BEF8, (signed __int64)Handle, 0);
    if ( v5 )
    {
      NtClose(Handle);
      Handle = v5;
    }
  }
  MutantHandle = hMutex;
  if ( !hMutex )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    v13 = L"Installing";
    ObjectAttributes.RootDirectory = Handle;
    *(_QWORD *)&ObjectAttributes.Attributes = 128;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v12;
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    v12 = 1441812;
    ObjectAttributes.SecurityQualityOfService = 0;
    v4 = NtCreateMutant(&MutantHandle, 0x100001u, &ObjectAttributes, 0);
    if ( v4 < 0 )
    {
      MutantHandle = 0;
      goto LABEL_9;
    }
    v6 = (void *)_InterlockedCompareExchange64((volatile signed __int64 *)&hMutex, (signed __int64)MutantHandle, 0);
    if ( v6 )
    {
      NtClose(MutantHandle);
      MutantHandle = v6;
    }
  }
  v3 = 0;
LABEL_22:
  if ( v10 )
    RtlDeleteBoundaryDescriptor();
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  *a1 = MutantHandle;
  return v3;
}

```

## disassembly

```asm
0x18000dd34  push    rbp
0x18000dd36  push    rbx
0x18000dd37  push    rsi
0x18000dd38  push    rdi
0x18000dd39  lea     rbp, [rsp-3Fh]
0x18000dd3e  sub     rsp, 0E8h
0x18000dd45  mov     rax, cs:__security_cookie
0x18000dd4c  xor     rax, rsp
0x18000dd4f  mov     [rbp+57h+var_30], rax
0x18000dd53  xor     esi, esi
0x18000dd55  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000dd59  mov     rdi, rcx
0x18000dd5c  mov     [rbp+57h+SecurityDescriptor], rsi
0x18000dd60  xor     r9d, r9d; SecurityDescriptorSize
0x18000dd63  mov     [rbp+57h+var_D0], rsi
0x18000dd67  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;SY)"
0x18000dd6e  mov     [rsp+100h+Handle], rsi
0x18000dd73  lea     edx, [rsi+1]; StringSDRevision
0x18000dd76  mov     [rsp+100h+MutantHandle], rsi
0x18000dd7b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000dd81  test    eax, eax
0x18000dd83  jnz     short loc_18000DD92
0x18000dd85  call    cs:__imp_GetLastError
0x18000dd8b  mov     ebx, eax
0x18000dd8d  jmp     loc_18000DF49
0x18000dd92  mov     rax, cs:qword_18002BEF8
0x18000dd99  mov     [rsp+100h+Handle], rax
0x18000dd9e  test    rax, rax
0x18000dda1  jnz     loc_18000DEA8
0x18000dda7  xorps   xmm0, xmm0
0x18000ddaa  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000ddb1  xor     edx, edx; DomainSid
0x18000ddb3  mov     [rbp+57h+var_C0], 120010h
0x18000ddbb  lea     rax, aLoadperf; "LoadPerf"
0x18000ddc2  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000ddc6  mov     [rbp+57h+var_B8], rax
0x18000ddca  lea     r8, [rbp+57h+pSid]; pSid
0x18000ddce  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18000ddd1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000ddd5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000ddd9  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000dddd  call    cs:__imp_CreateWellKnownSid
0x18000dde3  test    eax, eax
0x18000dde5  jz      short loc_18000DD85
0x18000dde7  xor     edx, edx
0x18000dde9  lea     rcx, [rbp+57h+var_C0]
0x18000dded  call    cs:__imp_RtlCreateBoundaryDescriptor
0x18000ddf3  mov     [rbp+57h+var_D0], rax
0x18000ddf7  test    rax, rax
0x18000ddfa  jnz     short loc_18000DE04
0x18000ddfc  lea     ebx, [rax+0Eh]
0x18000ddff  jmp     loc_18000DF49
0x18000de04  lea     rdx, [rbp+57h+pSid]
0x18000de08  lea     rcx, [rbp+57h+var_D0]
0x18000de0c  call    cs:__imp_RtlAddSIDToBoundaryDescriptor
0x18000de12  test    eax, eax
0x18000de14  jns     short loc_18000DE23
0x18000de16  mov     ecx, eax; Status
0x18000de18  call    cs:__imp_RtlNtStatusToDosError
0x18000de1e  jmp     loc_18000DD8B
0x18000de23  mov     rax, [rbp+57h+SecurityDescriptor]
0x18000de27  mov     ebx, 6
0x18000de2c  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18000de30  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000de37  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18000de3b  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x18000de3e  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18000de42  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rsi
0x18000de46  jmp     short loc_18000DE63
0x18000de48  mov     r9, [rbp+57h+var_D0]
0x18000de4c  lea     rcx, [rsp+100h+Handle]
0x18000de51  xor     r8d, r8d
0x18000de54  mov     edx, ebx
0x18000de56  call    cs:__imp_NtOpenPrivateNamespace
0x18000de5c  cmp     eax, 0C000003Ah
0x18000de61  jnz     short loc_18000DE7F
0x18000de63  mov     r9, [rbp+57h+var_D0]
0x18000de67  lea     r8, [rbp+57h+ObjectAttributes]
0x18000de6b  mov     edx, ebx
0x18000de6d  lea     rcx, [rsp+100h+Handle]
0x18000de72  call    cs:__imp_NtCreatePrivateNamespace
0x18000de78  cmp     eax, 0C0000035h
0x18000de7d  jz      short loc_18000DE48
0x18000de7f  test    eax, eax
0x18000de81  js      short loc_18000DE16
0x18000de83  mov     rcx, [rsp+100h+Handle]
0x18000de88  xor     eax, eax
0x18000de8a  lock cmpxchg cs:qword_18002BEF8, rcx
0x18000de93  mov     rbx, rax
0x18000de96  jz      short loc_18000DEA8
0x18000de98  mov     rcx, [rsp+100h+Handle]; Handle
0x18000de9d  call    cs:__imp_NtClose
0x18000dea3  mov     [rsp+100h+Handle], rbx
0x18000dea8  mov     rax, cs:hMutex
0x18000deaf  mov     [rsp+100h+MutantHandle], rax
0x18000deb4  test    rax, rax
0x18000deb7  jnz     loc_18000DF47
0x18000debd  lea     rax, aInstalling; "Installing"
0x18000dec4  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000decc  mov     [rbp+57h+var_B8], rax
0x18000ded0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000ded4  mov     rax, [rsp+100h+Handle]
0x18000ded9  lea     rcx, [rsp+100h+MutantHandle]; MutantHandle
0x18000dede  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18000dee2  xor     r9d, r9d; InitialOwner
0x18000dee5  lea     rax, [rbp+57h+var_C0]
0x18000dee9  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 80h
0x18000def1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000def5  mov     edx, 100001h; DesiredAccess
0x18000defa  mov     rax, [rbp+57h+SecurityDescriptor]
0x18000defe  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18000df02  mov     [rbp+57h+var_C0], 160014h
0x18000df0a  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rsi
0x18000df0e  call    cs:__imp_NtCreateMutant
0x18000df14  test    eax, eax
0x18000df16  jns     short loc_18000DF22
0x18000df18  mov     [rsp+100h+MutantHandle], rsi
0x18000df1d  jmp     loc_18000DE16
0x18000df22  mov     rcx, [rsp+100h+MutantHandle]
0x18000df27  xor     eax, eax
0x18000df29  lock cmpxchg cs:hMutex, rcx
0x18000df32  mov     rbx, rax
0x18000df35  jz      short loc_18000DF47
0x18000df37  mov     rcx, [rsp+100h+MutantHandle]; Handle
0x18000df3c  call    cs:__imp_NtClose
0x18000df42  mov     [rsp+100h+MutantHandle], rbx
0x18000df47  mov     ebx, esi
0x18000df49  mov     rcx, [rbp+57h+var_D0]
0x18000df4d  test    rcx, rcx
0x18000df50  jz      short loc_18000DF58
0x18000df52  call    cs:__imp_RtlDeleteBoundaryDescriptor
0x18000df58  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18000df5c  test    rcx, rcx
0x18000df5f  jz      short loc_18000DF67
0x18000df61  call    cs:__imp_LocalFree
0x18000df67  mov     rax, [rsp+100h+MutantHandle]
0x18000df6c  mov     [rdi], rax
0x18000df6f  mov     eax, ebx
0x18000df71  mov     rcx, [rbp+57h+var_30]
0x18000df75  xor     rcx, rsp; StackCookie
0x18000df78  call    __security_check_cookie
0x18000df7d  add     rsp, 0E8h
0x18000df84  pop     rdi
0x18000df85  pop     rsi
0x18000df86  pop     rbx
0x18000df87  pop     rbp
0x18000df88  retn
```
