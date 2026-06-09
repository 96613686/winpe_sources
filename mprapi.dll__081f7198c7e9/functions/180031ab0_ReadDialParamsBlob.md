# ReadDialParamsBlob

- ea: `0x180031ab0`
- end: `0x180031cfc`
- name: `ReadDialParamsBlob`
- size: `588`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031608`
- `0x180031788`

## callees

- `0x180009868`
- `0x180031ab0`
- `0x180051112`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031b8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031b8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c91`
- `ntdll!RtlInitUnicodeString` at `0x180031b26`
- `ntdll!RtlInitUnicodeString` at `0x180031c39`
- `ntdll!RtlInitUnicodeString` at `0x180031b26`
- `ntdll!RtlInitUnicodeString` at `0x180031c39`
- `ntdll!RtlNtStatusToDosError` at `0x180031b4d`
- `ntdll!RtlNtStatusToDosError` at `0x180031c5e`
- `ntdll!RtlNtStatusToDosError` at `0x180031b4d`
- `ntdll!RtlNtStatusToDosError` at `0x180031c5e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180031c72`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180031c72`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180031c0a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180031ca7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180031c0a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180031ca7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x180031c4e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x180031c4e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180031b41`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180031b41`

## pseudocode

```c
ULONG __fastcall ReadDialParamsBlob(PCWSTR SourceString, _QWORD *a2, unsigned int *a3)
{
  NTSTATUS v5; // eax
  ULONG result; // eax
  unsigned int v7; // esi
  void *v8; // rdi
  unsigned int v9; // r15d
  __int64 i; // r9
  unsigned int v11; // ecx
  char *v12; // rax
  char *v13; // r14
  PVOID v14; // rdx
  __int64 v15; // rax
  _BYTE *v16; // rcx
  NTSTATUS PrivateData; // eax
  ULONG v18; // eax
  int v19; // ebx
  PVOID Buffer; // [rsp+20h] [rbp-B9h] BYREF
  PVOID PolicyHandle; // [rsp+28h] [rbp-B1h] BYREF
  struct _UNICODE_STRING v22; // [rsp+30h] [rbp-A9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-99h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-89h] BYREF
  wchar_t pszDest[56]; // [rsp+80h] [rbp-59h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a2 = 0;
  Buffer = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 0;
  PolicyHandle = 0;
  *a3 = 0;
  ObjectAttributes.RootDirectory = 0;
  v22 = 0;
  ObjectAttributes.ObjectName = 0;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v5 = LsaOpenPolicy((PLSA_UNICODE_STRING)&DestinationString, &ObjectAttributes, 0x20006u, &PolicyHandle);
  if ( v5 )
    return RtlNtStatusToDosError(v5);
  v7 = 0;
  v8 = 0;
  v9 = 0;
  for ( i = 0; ; i = v9 )
  {
    StringCbPrintfW(pszDest, 0x64u, g_pwszStore, i, Buffer);
    RtlInitUnicodeString(&v22, pszDest);
    PrivateData = LsaRetrievePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v22, (PLSA_UNICODE_STRING *)&Buffer);
    if ( PrivateData )
      break;
    if ( !Buffer )
    {
      v19 = 8;
      goto LABEL_16;
    }
    v11 = v7 + *(unsigned __int16 *)Buffer;
    if ( v11 < v7 )
    {
      v19 = 534;
      goto LABEL_16;
    }
    v12 = (char *)LocalAlloc(0x40u, v11);
    v13 = v12;
    if ( !v12 )
    {
      v19 = 8;
      goto LABEL_16;
    }
    if ( v8 )
    {
      memcpy_0(v12, v8, v7);
      memset_0(v8, 0, v7);
      LocalFree(v8);
    }
    memcpy_0(&v13[v7], *((const void **)Buffer + 1), *(unsigned __int16 *)Buffer);
    v14 = Buffer;
    v8 = v13;
    v15 = *(unsigned __int16 *)Buffer;
    v16 = (_BYTE *)*((_QWORD *)Buffer + 1);
    v7 += v15;
    if ( *(_WORD *)Buffer )
    {
      do
      {
        *v16++ = 0;
        --v15;
      }
      while ( v15 );
      v14 = Buffer;
    }
    LsaFreeMemory(v14);
    ++v9;
    Buffer = 0;
  }
  v18 = RtlNtStatusToDosError(PrivateData);
  v19 = 0;
  if ( v18 != 2 )
    v19 = v18;
LABEL_16:
  LsaClose(PolicyHandle);
  if ( v19 )
  {
    if ( v8 )
    {
      memset_0(v8, 0, v7);
      LocalFree(v8);
    }
    v8 = 0;
    v7 = 0;
  }
  if ( Buffer )
    LsaFreeMemory(Buffer);
  *a2 = v8;
  result = v19;
  *a3 = v7;
  return result;
}

```

## disassembly

```asm
0x180031ab0  mov     [rsp-8+arg_18], rbx
0x180031ab5  push    rbp
0x180031ab6  push    rsi
0x180031ab7  push    rdi
0x180031ab8  push    r12
0x180031aba  push    r13
0x180031abc  push    r14
0x180031abe  push    r15
0x180031ac0  lea     rbp, [rsp-27h]
0x180031ac5  sub     rsp, 100h
0x180031acc  mov     rax, cs:__security_cookie
0x180031ad3  xor     rax, rsp
0x180031ad6  mov     [rbp+57h+var_40], rax
0x180031ada  xor     r14d, r14d
0x180031add  mov     qword ptr [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x180031ae6  mov     [rdx], r14
0x180031ae9  xorps   xmm0, xmm0
0x180031aec  mov     r12, rdx
0x180031aef  mov     [rsp+130h+Buffer], r14
0x180031af4  mov     rdx, rcx; SourceString
0x180031af7  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r14
0x180031afb  xorps   xmm1, xmm1
0x180031afe  mov     [rsp+130h+PolicyHandle], r14
0x180031b03  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180031b08  mov     [r8], r14d
0x180031b0b  mov     r13, r8
0x180031b0e  mov     [rsp+130h+ObjectAttributes.RootDirectory], r14
0x180031b13  movups  xmmword ptr [rsp+130h+var_100.Length], xmm0
0x180031b18  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x180031b1c  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x180031b21  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180031b26  call    cs:__imp_RtlInitUnicodeString
0x180031b2c  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x180031b31  mov     r8d, 20006h; DesiredAccess
0x180031b37  lea     rdx, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x180031b3c  lea     rcx, [rsp+130h+DestinationString]; SystemName
0x180031b41  call    cs:__imp_LsaOpenPolicy
0x180031b47  test    eax, eax
0x180031b49  jz      short loc_180031B58
0x180031b4b  mov     ecx, eax; Status
0x180031b4d  call    cs:__imp_RtlNtStatusToDosError
0x180031b53  jmp     loc_180031CB7
0x180031b58  mov     esi, r14d
0x180031b5b  mov     rdi, r14
0x180031b5e  mov     r15d, r14d
0x180031b61  xor     r9d, r9d
0x180031b64  jmp     loc_180031C1B
0x180031b69  mov     rax, [rsp+130h+Buffer]
0x180031b6e  test    rax, rax
0x180031b71  jz      loc_180031CF2
0x180031b77  movzx   ecx, word ptr [rax]
0x180031b7a  add     ecx, esi
0x180031b7c  cmp     ecx, esi
0x180031b7e  jb      loc_180031CE8
0x180031b84  mov     edx, ecx; uBytes
0x180031b86  mov     ecx, 40h ; '@'; uFlags
0x180031b8b  call    cs:__imp_LocalAlloc
0x180031b91  mov     r14, rax
0x180031b94  test    rax, rax
0x180031b97  jz      loc_180031CDE
0x180031b9d  test    rdi, rdi
0x180031ba0  jz      short loc_180031BC6
0x180031ba2  mov     r8d, esi; Size
0x180031ba5  mov     rdx, rdi; Src
0x180031ba8  mov     rcx, rax; void *
0x180031bab  call    memcpy_0
0x180031bb0  mov     r8d, esi; Size
0x180031bb3  xor     edx, edx; Val
0x180031bb5  mov     rcx, rdi; void *
0x180031bb8  call    memset_0
0x180031bbd  mov     rcx, rdi; hMem
0x180031bc0  call    cs:__imp_LocalFree
0x180031bc6  mov     rdx, [rsp+130h+Buffer]
0x180031bcb  mov     ecx, esi
0x180031bcd  add     rcx, r14; void *
0x180031bd0  movzx   r8d, word ptr [rdx]; Size
0x180031bd4  mov     rdx, [rdx+8]; Src
0x180031bd8  call    memcpy_0
0x180031bdd  mov     rdx, [rsp+130h+Buffer]
0x180031be2  mov     rdi, r14
0x180031be5  xor     r14d, r14d
0x180031be8  movzx   eax, word ptr [rdx]
0x180031beb  mov     rcx, [rdx+8]
0x180031bef  add     esi, eax
0x180031bf1  test    rax, rax
0x180031bf4  jz      short loc_180031C07
0x180031bf6  mov     [rcx], r14b
0x180031bf9  inc     rcx
0x180031bfc  sub     rax, 1
0x180031c00  jnz     short loc_180031BF6
0x180031c02  mov     rdx, [rsp+130h+Buffer]
0x180031c07  mov     rcx, rdx; Buffer
0x180031c0a  call    cs:__imp_LsaFreeMemory
0x180031c10  inc     r15d
0x180031c13  mov     [rsp+130h+Buffer], r14
0x180031c18  mov     r9d, r15d
0x180031c1b  mov     r8, cs:g_pwszStore; pszFormat
0x180031c22  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180031c26  mov     edx, 64h ; 'd'; cbDest
0x180031c2b  call    StringCbPrintfW
0x180031c30  lea     rdx, [rbp+57h+pszDest]; SourceString
0x180031c34  lea     rcx, [rsp+130h+var_100]; DestinationString
0x180031c39  call    cs:__imp_RtlInitUnicodeString
0x180031c3f  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x180031c44  lea     r8, [rsp+130h+Buffer]; PrivateData
0x180031c49  lea     rdx, [rsp+130h+var_100]; KeyName
0x180031c4e  call    cs:__imp_LsaRetrievePrivateData
0x180031c54  test    eax, eax
0x180031c56  jz      loc_180031B69
0x180031c5c  mov     ecx, eax; Status
0x180031c5e  call    cs:__imp_RtlNtStatusToDosError
0x180031c64  cmp     eax, 2
0x180031c67  mov     ebx, r14d
0x180031c6a  cmovnz  ebx, eax
0x180031c6d  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x180031c72  call    cs:__imp_LsaClose
0x180031c78  test    ebx, ebx
0x180031c7a  jz      short loc_180031C9D
0x180031c7c  test    rdi, rdi
0x180031c7f  jz      short loc_180031C97
0x180031c81  mov     r8d, esi; Size
0x180031c84  xor     edx, edx; Val
0x180031c86  mov     rcx, rdi; void *
0x180031c89  call    memset_0
0x180031c8e  mov     rcx, rdi; hMem
0x180031c91  call    cs:__imp_LocalFree
0x180031c97  mov     rdi, r14
0x180031c9a  mov     esi, r14d
0x180031c9d  mov     rcx, [rsp+130h+Buffer]; Buffer
0x180031ca2  test    rcx, rcx
0x180031ca5  jz      short loc_180031CAD
0x180031ca7  call    cs:__imp_LsaFreeMemory
0x180031cad  mov     [r12], rdi
0x180031cb1  mov     eax, ebx
0x180031cb3  mov     [r13+0], esi
0x180031cb7  mov     rcx, [rbp+57h+var_40]
0x180031cbb  xor     rcx, rsp; StackCookie
0x180031cbe  call    __security_check_cookie
0x180031cc3  mov     rbx, [rsp+130h+arg_18]
0x180031ccb  add     rsp, 100h
0x180031cd2  pop     r15
0x180031cd4  pop     r14
0x180031cd6  pop     r13
0x180031cd8  pop     r12
0x180031cda  pop     rdi
0x180031cdb  pop     rsi
0x180031cdc  pop     rbp
0x180031cdd  retn
0x180031cde  mov     ebx, 8
0x180031ce3  xor     r14d, r14d
0x180031ce6  jmp     short loc_180031C6D
0x180031ce8  mov     ebx, 216h
0x180031ced  jmp     loc_180031C6D
0x180031cf2  mov     ebx, 8
0x180031cf7  jmp     loc_180031C6D
```
