# WriteDialParamsBlob

- ea: `0x180031de0`
- end: `0x180031f6b`
- name: `WriteDialParamsBlob`
- size: `395`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031788`

## callees

- `0x180009868`
- `0x180031de0`
- `0x180051160`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180031e4d`
- `ntdll!RtlInitUnicodeString` at `0x180031eb0`
- `ntdll!RtlInitUnicodeString` at `0x180031f21`
- `ntdll!RtlInitUnicodeString` at `0x180031e4d`
- `ntdll!RtlInitUnicodeString` at `0x180031eb0`
- `ntdll!RtlInitUnicodeString` at `0x180031f21`
- `ntdll!RtlNtStatusToDosError` at `0x180031e74`
- `ntdll!RtlNtStatusToDosError` at `0x180031ef4`
- `ntdll!RtlNtStatusToDosError` at `0x180031e74`
- `ntdll!RtlNtStatusToDosError` at `0x180031ef4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180031f45`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180031f45`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180031edd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180031f34`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180031edd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180031f34`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180031e68`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180031e68`

## pseudocode

```c
ULONG __fastcall WriteDialParamsBlob(PCWSTR SourceString, WCHAR *a2, unsigned int a3)
{
  NTSTATUS v5; // eax
  unsigned int v7; // ebx
  unsigned int v8; // esi
  NTSTATUS v9; // eax
  ULONG v10; // edi
  PVOID PolicyHandle; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING v12; // [rsp+28h] [rbp-D8h] BYREF
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[56]; // [rsp+90h] [rbp-70h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  PolicyHandle = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v12 = 0;
  PrivateData = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v5 = LsaOpenPolicy((PLSA_UNICODE_STRING)&DestinationString, &ObjectAttributes, 0x207F8u, &PolicyHandle);
  if ( v5 )
    return RtlNtStatusToDosError(v5);
  v7 = 0;
  if ( !a3 )
    goto LABEL_15;
  while ( 1 )
  {
    StringCbPrintfW(
      pszDest,
      0x64u,
      g_pwszStore,
      v7++,
      PolicyHandle,
      *(_QWORD *)&v12.Length,
      v12.Buffer,
      *(_QWORD *)&PrivateData.Length,
      PrivateData.Buffer);
    RtlInitUnicodeString(&v12, pszDest);
    PrivateData.Buffer = a2;
    v8 = a3;
    if ( a3 > 0xFFFF )
      v8 = 0xFFFF;
    PrivateData.MaximumLength = v8;
    PrivateData.Length = v8;
    v9 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v12, &PrivateData);
    if ( v9 )
      break;
    a2 = (WCHAR *)((char *)a2 + v8);
    a3 -= v8;
    if ( !a3 )
      goto LABEL_10;
  }
  v10 = RtlNtStatusToDosError(v9);
  if ( !v10 )
  {
LABEL_15:
    do
    {
LABEL_10:
      StringCbPrintfW(pszDest, 0x64u, g_pwszStore, v7++, PolicyHandle);
      RtlInitUnicodeString(&v12, pszDest);
    }
    while ( !LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v12, 0) );
    v10 = 0;
  }
  LsaClose(PolicyHandle);
  return v10;
}

```

## disassembly

```asm
0x180031de0  push    rbp
0x180031de2  push    rbx
0x180031de3  push    rsi
0x180031de4  push    rdi
0x180031de5  push    r12
0x180031de7  push    r13
0x180031de9  push    r14
0x180031deb  lea     rbp, [rsp-10h]
0x180031df0  sub     rsp, 110h
0x180031df7  mov     rax, cs:__security_cookie
0x180031dfe  xor     rax, rsp
0x180031e01  mov     [rbp+40h+var_40], rax
0x180031e05  xor     eax, eax
0x180031e07  mov     qword ptr [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x180031e10  xorps   xmm0, xmm0
0x180031e13  mov     qword ptr [rsp+140h+ObjectAttributes.Attributes], rax
0x180031e18  mov     r14, rdx
0x180031e1b  mov     [rsp+140h+PolicyHandle], rax
0x180031e20  mov     rdx, rcx; SourceString
0x180031e23  mov     [rsp+140h+ObjectAttributes.RootDirectory], rax
0x180031e28  xorps   xmm1, xmm1
0x180031e2b  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x180031e30  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x180031e35  mov     edi, r8d
0x180031e38  movups  xmmword ptr [rsp+140h+var_118.Length], xmm0
0x180031e3d  movups  xmmword ptr [rsp+140h+PrivateData.Length], xmm1
0x180031e42  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x180031e47  movdqu  xmmword ptr [rsp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x180031e4d  call    cs:__imp_RtlInitUnicodeString
0x180031e53  lea     r9, [rsp+140h+PolicyHandle]; PolicyHandle
0x180031e58  mov     r8d, 207F8h; DesiredAccess
0x180031e5e  lea     rdx, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x180031e63  lea     rcx, [rsp+140h+DestinationString]; SystemName
0x180031e68  call    cs:__imp_LsaOpenPolicy
0x180031e6e  test    eax, eax
0x180031e70  jz      short loc_180031E7F
0x180031e72  mov     ecx, eax; Status
0x180031e74  call    cs:__imp_RtlNtStatusToDosError
0x180031e7a  jmp     loc_180031F4D
0x180031e7f  xor     ebx, ebx
0x180031e81  lea     r12d, [rbx+64h]
0x180031e85  test    edi, edi
0x180031e87  jz      short loc_180031F00
0x180031e89  mov     r13d, 0FFFFh
0x180031e8f  mov     r8, cs:g_pwszStore; pszFormat
0x180031e96  lea     rcx, [rbp+40h+pszDest]; pszDest
0x180031e9a  mov     r9d, ebx
0x180031e9d  mov     rdx, r12; cbDest
0x180031ea0  call    StringCbPrintfW
0x180031ea5  lea     rdx, [rbp+40h+pszDest]; SourceString
0x180031ea9  inc     ebx
0x180031eab  lea     rcx, [rsp+140h+var_118]; DestinationString
0x180031eb0  call    cs:__imp_RtlInitUnicodeString
0x180031eb6  mov     rcx, [rsp+140h+PolicyHandle]; PolicyHandle
0x180031ebb  lea     r8, [rsp+140h+PrivateData]; PrivateData
0x180031ec0  cmp     edi, r13d
0x180031ec3  mov     [rsp+140h+PrivateData.Buffer], r14
0x180031ec8  mov     esi, edi
0x180031eca  lea     rdx, [rsp+140h+var_118]; KeyName
0x180031ecf  cmova   esi, r13d
0x180031ed3  mov     [rsp+140h+PrivateData.MaximumLength], si
0x180031ed8  mov     [rsp+140h+PrivateData.Length], si
0x180031edd  call    cs:__imp_LsaStorePrivateData
0x180031ee3  test    eax, eax
0x180031ee5  jnz     short loc_180031EF2
0x180031ee7  mov     eax, esi
0x180031ee9  add     r14, rax
0x180031eec  sub     edi, esi
0x180031eee  jnz     short loc_180031E8F
0x180031ef0  jmp     short loc_180031F00
0x180031ef2  mov     ecx, eax; Status
0x180031ef4  call    cs:__imp_RtlNtStatusToDosError
0x180031efa  mov     edi, eax
0x180031efc  test    eax, eax
0x180031efe  jnz     short loc_180031F40
0x180031f00  mov     r8, cs:g_pwszStore; pszFormat
0x180031f07  lea     rcx, [rbp+40h+pszDest]; pszDest
0x180031f0b  mov     r9d, ebx
0x180031f0e  mov     rdx, r12; cbDest
0x180031f11  call    StringCbPrintfW
0x180031f16  lea     rdx, [rbp+40h+pszDest]; SourceString
0x180031f1a  inc     ebx
0x180031f1c  lea     rcx, [rsp+140h+var_118]; DestinationString
0x180031f21  call    cs:__imp_RtlInitUnicodeString
0x180031f27  mov     rcx, [rsp+140h+PolicyHandle]; PolicyHandle
0x180031f2c  lea     rdx, [rsp+140h+var_118]; KeyName
0x180031f31  xor     r8d, r8d; PrivateData
0x180031f34  call    cs:__imp_LsaStorePrivateData
0x180031f3a  test    eax, eax
0x180031f3c  jz      short loc_180031F00
0x180031f3e  xor     edi, edi
0x180031f40  mov     rcx, [rsp+140h+PolicyHandle]; ObjectHandle
0x180031f45  call    cs:__imp_LsaClose
0x180031f4b  mov     eax, edi
0x180031f4d  mov     rcx, [rbp+40h+var_40]
0x180031f51  xor     rcx, rsp; StackCookie
0x180031f54  call    __security_check_cookie
0x180031f59  add     rsp, 110h
0x180031f60  pop     r14
0x180031f62  pop     r13
0x180031f64  pop     r12
0x180031f66  pop     rdi
0x180031f67  pop     rsi
0x180031f68  pop     rbx
0x180031f69  pop     rbp
0x180031f6a  retn
```
