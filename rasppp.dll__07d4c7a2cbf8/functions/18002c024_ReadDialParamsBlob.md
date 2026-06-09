# ReadDialParamsBlob

- ea: `0x18002c024`
- end: `0x18002c26f`
- name: `ReadDialParamsBlob`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002bee8`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002c024`
- `0x18002c278`
- `0x180032460`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002c099`
- `ntdll!RtlInitUnicodeString` at `0x18002c1ac`
- `ntdll!RtlInitUnicodeString` at `0x18002c099`
- `ntdll!RtlInitUnicodeString` at `0x18002c1ac`
- `ntdll!RtlNtStatusToDosError` at `0x18002c0c0`
- `ntdll!RtlNtStatusToDosError` at `0x18002c1d1`
- `ntdll!RtlNtStatusToDosError` at `0x18002c0c0`
- `ntdll!RtlNtStatusToDosError` at `0x18002c1d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c133`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c133`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c204`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c0fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c0fe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002c17d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002c21a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002c17d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002c21a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18002c1c1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18002c1c1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002c1e5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002c1e5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002c0b4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002c0b4`

## pseudocode

```c
ULONG __fastcall ReadDialParamsBlob(__int64 a1, _QWORD *a2, unsigned int *a3)
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
  __int64 v15; // rcx
  _BYTE *v16; // rax
  NTSTATUS PrivateData; // eax
  ULONG v18; // eax
  int v19; // ebx
  PVOID Buffer; // [rsp+20h] [rbp-B9h] BYREF
  PVOID PolicyHandle; // [rsp+28h] [rbp-B1h] BYREF
  struct _UNICODE_STRING v22; // [rsp+30h] [rbp-A9h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-99h] BYREF
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
  RtlInitUnicodeString(&DestinationString, 0);
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
0x18002c024  mov     [rsp-8+arg_0], rbx
0x18002c029  push    rbp
0x18002c02a  push    rsi
0x18002c02b  push    rdi
0x18002c02c  push    r12
0x18002c02e  push    r13
0x18002c030  push    r14
0x18002c032  push    r15
0x18002c034  lea     rbp, [rsp-27h]
0x18002c039  sub     rsp, 100h
0x18002c040  mov     rax, cs:__security_cookie
0x18002c047  xor     rax, rsp
0x18002c04a  mov     [rbp+57h+var_40], rax
0x18002c04e  xor     r14d, r14d
0x18002c051  mov     qword ptr [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x18002c05a  mov     [rdx], r14
0x18002c05d  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18002c062  xorps   xmm0, xmm0
0x18002c065  mov     [rsp+130h+Buffer], r14
0x18002c06a  mov     r12, rdx
0x18002c06d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r14
0x18002c071  xorps   xmm1, xmm1
0x18002c074  mov     [rsp+130h+PolicyHandle], r14
0x18002c079  xor     edx, edx; SourceString
0x18002c07b  mov     [r8], r14d
0x18002c07e  mov     r13, r8
0x18002c081  mov     [rsp+130h+ObjectAttributes.RootDirectory], r14
0x18002c086  movups  xmmword ptr [rsp+130h+var_100.Length], xmm0
0x18002c08b  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18002c08f  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x18002c094  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c099  call    cs:__imp_RtlInitUnicodeString
0x18002c09f  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x18002c0a4  mov     r8d, 20006h; DesiredAccess
0x18002c0aa  lea     rdx, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x18002c0af  lea     rcx, [rsp+130h+DestinationString]; SystemName
0x18002c0b4  call    cs:__imp_LsaOpenPolicy
0x18002c0ba  test    eax, eax
0x18002c0bc  jz      short loc_18002C0CB
0x18002c0be  mov     ecx, eax; Status
0x18002c0c0  call    cs:__imp_RtlNtStatusToDosError
0x18002c0c6  jmp     loc_18002C22A
0x18002c0cb  mov     esi, r14d
0x18002c0ce  mov     rdi, r14
0x18002c0d1  mov     r15d, r14d
0x18002c0d4  xor     r9d, r9d
0x18002c0d7  jmp     loc_18002C18E
0x18002c0dc  mov     rax, [rsp+130h+Buffer]
0x18002c0e1  test    rax, rax
0x18002c0e4  jz      loc_18002C265
0x18002c0ea  movzx   ecx, word ptr [rax]
0x18002c0ed  add     ecx, esi
0x18002c0ef  cmp     ecx, esi
0x18002c0f1  jb      loc_18002C25B
0x18002c0f7  mov     edx, ecx; uBytes
0x18002c0f9  mov     ecx, 40h ; '@'; uFlags
0x18002c0fe  call    cs:__imp_LocalAlloc
0x18002c104  mov     r14, rax
0x18002c107  test    rax, rax
0x18002c10a  jz      loc_18002C251
0x18002c110  test    rdi, rdi
0x18002c113  jz      short loc_18002C139
0x18002c115  mov     r8d, esi; Size
0x18002c118  mov     rdx, rdi; Src
0x18002c11b  mov     rcx, rax; void *
0x18002c11e  call    memcpy_0
0x18002c123  mov     r8d, esi; Size
0x18002c126  xor     edx, edx; Val
0x18002c128  mov     rcx, rdi; void *
0x18002c12b  call    memset_0
0x18002c130  mov     rcx, rdi; hMem
0x18002c133  call    cs:__imp_LocalFree
0x18002c139  mov     rdx, [rsp+130h+Buffer]
0x18002c13e  mov     ecx, esi
0x18002c140  add     rcx, r14; void *
0x18002c143  movzx   r8d, word ptr [rdx]; Size
0x18002c147  mov     rdx, [rdx+8]; Src
0x18002c14b  call    memcpy_0
0x18002c150  mov     rdx, [rsp+130h+Buffer]
0x18002c155  mov     rdi, r14
0x18002c158  xor     r14d, r14d
0x18002c15b  movzx   ecx, word ptr [rdx]
0x18002c15e  mov     rax, [rdx+8]
0x18002c162  add     esi, ecx
0x18002c164  test    rcx, rcx
0x18002c167  jz      short loc_18002C17A
0x18002c169  mov     [rax], r14b
0x18002c16c  inc     rax
0x18002c16f  sub     rcx, 1
0x18002c173  jnz     short loc_18002C169
0x18002c175  mov     rdx, [rsp+130h+Buffer]
0x18002c17a  mov     rcx, rdx; Buffer
0x18002c17d  call    cs:__imp_LsaFreeMemory
0x18002c183  inc     r15d
0x18002c186  mov     [rsp+130h+Buffer], r14
0x18002c18b  mov     r9d, r15d
0x18002c18e  mov     r8, cs:g_pwszStore; pszFormat
0x18002c195  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18002c199  mov     edx, 64h ; 'd'; cbDest
0x18002c19e  call    StringCbPrintfW
0x18002c1a3  lea     rdx, [rbp+57h+pszDest]; SourceString
0x18002c1a7  lea     rcx, [rsp+130h+var_100]; DestinationString
0x18002c1ac  call    cs:__imp_RtlInitUnicodeString
0x18002c1b2  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x18002c1b7  lea     r8, [rsp+130h+Buffer]; PrivateData
0x18002c1bc  lea     rdx, [rsp+130h+var_100]; KeyName
0x18002c1c1  call    cs:__imp_LsaRetrievePrivateData
0x18002c1c7  test    eax, eax
0x18002c1c9  jz      loc_18002C0DC
0x18002c1cf  mov     ecx, eax; Status
0x18002c1d1  call    cs:__imp_RtlNtStatusToDosError
0x18002c1d7  cmp     eax, 2
0x18002c1da  mov     ebx, r14d
0x18002c1dd  cmovnz  ebx, eax
0x18002c1e0  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x18002c1e5  call    cs:__imp_LsaClose
0x18002c1eb  test    ebx, ebx
0x18002c1ed  jz      short loc_18002C210
0x18002c1ef  test    rdi, rdi
0x18002c1f2  jz      short loc_18002C20A
0x18002c1f4  mov     r8d, esi; Size
0x18002c1f7  xor     edx, edx; Val
0x18002c1f9  mov     rcx, rdi; void *
0x18002c1fc  call    memset_0
0x18002c201  mov     rcx, rdi; hMem
0x18002c204  call    cs:__imp_LocalFree
0x18002c20a  mov     rdi, r14
0x18002c20d  mov     esi, r14d
0x18002c210  mov     rcx, [rsp+130h+Buffer]; Buffer
0x18002c215  test    rcx, rcx
0x18002c218  jz      short loc_18002C220
0x18002c21a  call    cs:__imp_LsaFreeMemory
0x18002c220  mov     [r12], rdi
0x18002c224  mov     eax, ebx
0x18002c226  mov     [r13+0], esi
0x18002c22a  mov     rcx, [rbp+57h+var_40]
0x18002c22e  xor     rcx, rsp; StackCookie
0x18002c231  call    __security_check_cookie
0x18002c236  mov     rbx, [rsp+130h+arg_0]
0x18002c23e  add     rsp, 100h
0x18002c245  pop     r15
0x18002c247  pop     r14
0x18002c249  pop     r13
0x18002c24b  pop     r12
0x18002c24d  pop     rdi
0x18002c24e  pop     rsi
0x18002c24f  pop     rbp
0x18002c250  retn
0x18002c251  mov     ebx, 8
0x18002c256  xor     r14d, r14d
0x18002c259  jmp     short loc_18002C1E0
0x18002c25b  mov     ebx, 216h
0x18002c260  jmp     loc_18002C1E0
0x18002c265  mov     ebx, 8
0x18002c26a  jmp     loc_18002C1E0
```
