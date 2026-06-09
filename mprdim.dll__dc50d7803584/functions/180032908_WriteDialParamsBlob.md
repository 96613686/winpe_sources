# WriteDialParamsBlob

- ea: `0x180032908`
- end: `0x180032aa1`
- name: `WriteDialParamsBlob`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180032368`

## callees

- `0x18001851c`
- `0x180032908`
- `0x180046e70`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800329a2`
- `ntdll!RtlNtStatusToDosError` at `0x180032a20`
- `ntdll!RtlNtStatusToDosError` at `0x1800329a2`
- `ntdll!RtlNtStatusToDosError` at `0x180032a20`
- `ntdll!RtlInitUnicodeString` at `0x18003297b`
- `ntdll!RtlInitUnicodeString` at `0x1800329de`
- `ntdll!RtlInitUnicodeString` at `0x180032a4d`
- `ntdll!RtlInitUnicodeString` at `0x18003297b`
- `ntdll!RtlInitUnicodeString` at `0x1800329de`
- `ntdll!RtlInitUnicodeString` at `0x180032a4d`
- `ADVAPI32!LsaOpenPolicy` at `0x180032996`
- `ADVAPI32!LsaOpenPolicy` at `0x180032996`
- `ADVAPI32!LsaStorePrivateData` at `0x180032a0b`
- `ADVAPI32!LsaStorePrivateData` at `0x180032a60`
- `ADVAPI32!LsaStorePrivateData` at `0x180032a0b`
- `ADVAPI32!LsaStorePrivateData` at `0x180032a60`
- `ADVAPI32!LsaClose` at `0x180032a71`
- `ADVAPI32!LsaClose` at `0x180032a71`

## pseudocode

```c
ULONG __fastcall WriteDialParamsBlob(__int64 a1, WCHAR *a2, unsigned int a3)
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
  RtlInitUnicodeString(&DestinationString, 0);
  v5 = LsaOpenPolicy((PLSA_UNICODE_STRING)&DestinationString, &ObjectAttributes, 0x207F8u, &PolicyHandle);
  if ( v5 )
    return RtlNtStatusToDosError(v5);
  v7 = 0;
  while ( a3 )
  {
    StringCbPrintfW(pszDest, 0x64u, g_pwszStore, v7++);
    RtlInitUnicodeString(&v12, pszDest);
    PrivateData.Buffer = a2;
    v8 = a3;
    if ( a3 > 0xFFFF )
      v8 = 0xFFFF;
    PrivateData.MaximumLength = v8;
    PrivateData.Length = v8;
    v9 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v12, &PrivateData);
    if ( v9 )
    {
      v10 = RtlNtStatusToDosError(v9);
      if ( v10 )
        goto LABEL_12;
      goto LABEL_10;
    }
    a2 = (WCHAR *)((char *)a2 + v8);
    a3 -= v8;
  }
  do
  {
LABEL_10:
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
  }
  while ( !LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v12, 0) );
  v10 = 0;
LABEL_12:
  LsaClose(PolicyHandle);
  return v10;
}

```

## disassembly

```asm
0x180032908  mov     [rsp-8+arg_0], rbx
0x18003290d  mov     [rsp-8+arg_18], rsi
0x180032912  push    rbp
0x180032913  push    rdi
0x180032914  push    r12
0x180032916  push    r13
0x180032918  push    r14
0x18003291a  lea     rbp, [rsp-10h]
0x18003291f  sub     rsp, 110h
0x180032926  mov     rax, cs:__security_cookie
0x18003292d  xor     rax, rsp
0x180032930  mov     [rbp+30h+var_30], rax
0x180032934  xor     eax, eax
0x180032936  mov     qword ptr [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x18003293f  xorps   xmm0, xmm0
0x180032942  mov     qword ptr [rsp+130h+ObjectAttributes.Attributes], rax
0x180032947  mov     r14, rdx
0x18003294a  mov     [rsp+130h+PolicyHandle], rax
0x18003294f  xorps   xmm1, xmm1
0x180032952  mov     [rsp+130h+ObjectAttributes.RootDirectory], rax
0x180032957  xor     edx, edx; SourceString
0x180032959  mov     [rsp+130h+ObjectAttributes.ObjectName], rax
0x18003295e  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180032963  mov     edi, r8d
0x180032966  movups  xmmword ptr [rsp+130h+var_108.Length], xmm0
0x18003296b  movups  xmmword ptr [rsp+130h+PrivateData.Length], xmm1
0x180032970  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x180032975  movdqu  xmmword ptr [rsp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003297b  call    cs:__imp_RtlInitUnicodeString
0x180032981  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x180032986  mov     r8d, 207F8h; DesiredAccess
0x18003298c  lea     rdx, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x180032991  lea     rcx, [rsp+130h+DestinationString]; SystemName
0x180032996  call    cs:__imp_LsaOpenPolicy
0x18003299c  test    eax, eax
0x18003299e  jz      short loc_1800329AD
0x1800329a0  mov     ecx, eax; Status
0x1800329a2  call    cs:__imp_RtlNtStatusToDosError
0x1800329a8  jmp     loc_180032A79
0x1800329ad  xor     ebx, ebx
0x1800329af  mov     r13d, 0FFFFh
0x1800329b5  lea     r12d, [rbx+64h]
0x1800329b9  test    edi, edi
0x1800329bb  jz      short loc_180032A2C
0x1800329bd  mov     r8, cs:g_pwszStore; pszFormat
0x1800329c4  lea     rcx, [rbp+30h+pszDest]; pszDest
0x1800329c8  mov     r9d, ebx
0x1800329cb  mov     rdx, r12; cbDest
0x1800329ce  call    StringCbPrintfW
0x1800329d3  lea     rdx, [rbp+30h+pszDest]; SourceString
0x1800329d7  inc     ebx
0x1800329d9  lea     rcx, [rsp+130h+var_108]; DestinationString
0x1800329de  call    cs:__imp_RtlInitUnicodeString
0x1800329e4  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x1800329e9  lea     r8, [rsp+130h+PrivateData]; PrivateData
0x1800329ee  cmp     edi, r13d
0x1800329f1  mov     [rsp+130h+PrivateData.Buffer], r14
0x1800329f6  mov     esi, edi
0x1800329f8  lea     rdx, [rsp+130h+var_108]; KeyName
0x1800329fd  cmova   esi, r13d
0x180032a01  mov     [rsp+130h+PrivateData.MaximumLength], si
0x180032a06  mov     [rsp+130h+PrivateData.Length], si
0x180032a0b  call    cs:__imp_LsaStorePrivateData
0x180032a11  test    eax, eax
0x180032a13  jnz     short loc_180032A1E
0x180032a15  mov     eax, esi
0x180032a17  add     r14, rax
0x180032a1a  sub     edi, esi
0x180032a1c  jmp     short loc_1800329B9
0x180032a1e  mov     ecx, eax; Status
0x180032a20  call    cs:__imp_RtlNtStatusToDosError
0x180032a26  mov     edi, eax
0x180032a28  test    eax, eax
0x180032a2a  jnz     short loc_180032A6C
0x180032a2c  mov     r8, cs:g_pwszStore; pszFormat
0x180032a33  lea     rcx, [rbp+30h+pszDest]; pszDest
0x180032a37  mov     r9d, ebx
0x180032a3a  mov     rdx, r12; cbDest
0x180032a3d  call    StringCbPrintfW
0x180032a42  lea     rdx, [rbp+30h+pszDest]; SourceString
0x180032a46  inc     ebx
0x180032a48  lea     rcx, [rsp+130h+var_108]; DestinationString
0x180032a4d  call    cs:__imp_RtlInitUnicodeString
0x180032a53  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x180032a58  lea     rdx, [rsp+130h+var_108]; KeyName
0x180032a5d  xor     r8d, r8d; PrivateData
0x180032a60  call    cs:__imp_LsaStorePrivateData
0x180032a66  test    eax, eax
0x180032a68  jz      short loc_180032A2C
0x180032a6a  xor     edi, edi
0x180032a6c  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x180032a71  call    cs:__imp_LsaClose
0x180032a77  mov     eax, edi
0x180032a79  mov     rcx, [rbp+30h+var_30]
0x180032a7d  xor     rcx, rsp; StackCookie
0x180032a80  call    __security_check_cookie
0x180032a85  lea     r11, [rsp+130h+var_20]
0x180032a8d  mov     rbx, [r11+30h]
0x180032a91  mov     rsi, [r11+48h]
0x180032a95  mov     rsp, r11
0x180032a98  pop     r14
0x180032a9a  pop     r13
0x180032a9c  pop     r12
0x180032a9e  pop     rdi
0x180032a9f  pop     rbp
0x180032aa0  retn
```
