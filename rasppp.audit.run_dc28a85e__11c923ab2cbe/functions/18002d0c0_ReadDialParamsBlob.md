# ReadDialParamsBlob

- ea: `0x18002d0c0`
- end: `0x18002d357`
- name: `ReadDialParamsBlob`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002cf7c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002d0c0`
- `0x18002d360`
- `0x180033a80`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002d135`
- `ntdll!RtlInitUnicodeString` at `0x18002d26c`
- `ntdll!RtlInitUnicodeString` at `0x18002d135`
- `ntdll!RtlInitUnicodeString` at `0x18002d26c`
- `ntdll!RtlNtStatusToDosError` at `0x18002d168`
- `ntdll!RtlNtStatusToDosError` at `0x18002d29d`
- `ntdll!RtlNtStatusToDosError` at `0x18002d168`
- `ntdll!RtlNtStatusToDosError` at `0x18002d29d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d1e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d1e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d1ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d1ac`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002d237`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002d2f8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002d237`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002d2f8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18002d287`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18002d287`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002d2b7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002d2b7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002d156`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002d156`

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
0x18002d0c0  mov     [rsp-8+arg_0], rbx
0x18002d0c5  push    rbp
0x18002d0c6  push    rsi
0x18002d0c7  push    rdi
0x18002d0c8  push    r12
0x18002d0ca  push    r13
0x18002d0cc  push    r14
0x18002d0ce  push    r15
0x18002d0d0  lea     rbp, [rsp-27h]
0x18002d0d5  sub     rsp, 100h
0x18002d0dc  mov     rax, cs:__security_cookie
0x18002d0e3  xor     rax, rsp
0x18002d0e6  mov     [rbp+57h+var_40], rax
0x18002d0ea  xor     r14d, r14d
0x18002d0ed  mov     qword ptr [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x18002d0f6  mov     [rdx], r14
0x18002d0f9  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18002d0fe  xorps   xmm0, xmm0
0x18002d101  mov     [rsp+130h+Buffer], r14
0x18002d106  mov     r12, rdx
0x18002d109  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r14
0x18002d10d  xorps   xmm1, xmm1
0x18002d110  mov     [rsp+130h+PolicyHandle], r14
0x18002d115  xor     edx, edx; SourceString
0x18002d117  mov     [r8], r14d
0x18002d11a  mov     r13, r8
0x18002d11d  mov     [rsp+130h+ObjectAttributes.RootDirectory], r14
0x18002d122  movups  xmmword ptr [rsp+130h+var_100.Length], xmm0
0x18002d127  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18002d12b  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x18002d130  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002d135  call    cs:__imp_RtlInitUnicodeString
0x18002d13c  nop     dword ptr [rax+rax+00h]
0x18002d141  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x18002d146  mov     r8d, 20006h; DesiredAccess
0x18002d14c  lea     rdx, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x18002d151  lea     rcx, [rsp+130h+DestinationString]; SystemName
0x18002d156  call    cs:__imp_LsaOpenPolicy
0x18002d15d  nop     dword ptr [rax+rax+00h]
0x18002d162  test    eax, eax
0x18002d164  jz      short loc_18002D179
0x18002d166  mov     ecx, eax; Status
0x18002d168  call    cs:__imp_RtlNtStatusToDosError
0x18002d16f  nop     dword ptr [rax+rax+00h]
0x18002d174  jmp     loc_18002D30E
0x18002d179  mov     esi, r14d
0x18002d17c  mov     rdi, r14
0x18002d17f  mov     r15d, r14d
0x18002d182  xor     r9d, r9d
0x18002d185  jmp     loc_18002D24E
0x18002d18a  mov     rax, [rsp+130h+Buffer]
0x18002d18f  test    rax, rax
0x18002d192  jz      loc_18002D34D
0x18002d198  movzx   ecx, word ptr [rax]
0x18002d19b  add     ecx, esi
0x18002d19d  cmp     ecx, esi
0x18002d19f  jb      loc_18002D343
0x18002d1a5  mov     edx, ecx; uBytes
0x18002d1a7  mov     ecx, 40h ; '@'; uFlags
0x18002d1ac  call    cs:__imp_LocalAlloc
0x18002d1b3  nop     dword ptr [rax+rax+00h]
0x18002d1b8  mov     r14, rax
0x18002d1bb  test    rax, rax
0x18002d1be  jz      loc_18002D336
0x18002d1c4  test    rdi, rdi
0x18002d1c7  jz      short loc_18002D1F3
0x18002d1c9  mov     r8d, esi; Size
0x18002d1cc  mov     rdx, rdi; Src
0x18002d1cf  mov     rcx, rax; void *
0x18002d1d2  call    memcpy_0
0x18002d1d7  mov     r8d, esi; Size
0x18002d1da  xor     edx, edx; Val
0x18002d1dc  mov     rcx, rdi; void *
0x18002d1df  call    memset_0
0x18002d1e4  mov     rcx, rdi; hMem
0x18002d1e7  call    cs:__imp_LocalFree
0x18002d1ee  nop     dword ptr [rax+rax+00h]
0x18002d1f3  mov     rdx, [rsp+130h+Buffer]
0x18002d1f8  mov     ecx, esi
0x18002d1fa  add     rcx, r14; void *
0x18002d1fd  movzx   r8d, word ptr [rdx]; Size
0x18002d201  mov     rdx, [rdx+8]; Src
0x18002d205  call    memcpy_0
0x18002d20a  mov     rdx, [rsp+130h+Buffer]
0x18002d20f  mov     rdi, r14
0x18002d212  xor     r14d, r14d
0x18002d215  movzx   ecx, word ptr [rdx]
0x18002d218  mov     rax, [rdx+8]
0x18002d21c  add     esi, ecx
0x18002d21e  test    rcx, rcx
0x18002d221  jz      short loc_18002D234
0x18002d223  mov     [rax], r14b
0x18002d226  inc     rax
0x18002d229  sub     rcx, 1
0x18002d22d  jnz     short loc_18002D223
0x18002d22f  mov     rdx, [rsp+130h+Buffer]
0x18002d234  mov     rcx, rdx; Buffer
0x18002d237  call    cs:__imp_LsaFreeMemory
0x18002d23e  nop     dword ptr [rax+rax+00h]
0x18002d243  inc     r15d
0x18002d246  mov     [rsp+130h+Buffer], r14
0x18002d24b  mov     r9d, r15d
0x18002d24e  mov     r8, cs:g_pwszStore; pszFormat
0x18002d255  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18002d259  mov     edx, 64h ; 'd'; cbDest
0x18002d25e  call    StringCbPrintfW
0x18002d263  lea     rdx, [rbp+57h+pszDest]; SourceString
0x18002d267  lea     rcx, [rsp+130h+var_100]; DestinationString
0x18002d26c  call    cs:__imp_RtlInitUnicodeString
0x18002d273  nop     dword ptr [rax+rax+00h]
0x18002d278  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x18002d27d  lea     r8, [rsp+130h+Buffer]; PrivateData
0x18002d282  lea     rdx, [rsp+130h+var_100]; KeyName
0x18002d287  call    cs:__imp_LsaRetrievePrivateData
0x18002d28e  nop     dword ptr [rax+rax+00h]
0x18002d293  test    eax, eax
0x18002d295  jz      loc_18002D18A
0x18002d29b  mov     ecx, eax; Status
0x18002d29d  call    cs:__imp_RtlNtStatusToDosError
0x18002d2a4  nop     dword ptr [rax+rax+00h]
0x18002d2a9  cmp     eax, 2
0x18002d2ac  mov     ebx, r14d
0x18002d2af  cmovnz  ebx, eax
0x18002d2b2  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x18002d2b7  call    cs:__imp_LsaClose
0x18002d2be  nop     dword ptr [rax+rax+00h]
0x18002d2c3  test    ebx, ebx
0x18002d2c5  jz      short loc_18002D2EE
0x18002d2c7  test    rdi, rdi
0x18002d2ca  jz      short loc_18002D2E8
0x18002d2cc  mov     r8d, esi; Size
0x18002d2cf  xor     edx, edx; Val
0x18002d2d1  mov     rcx, rdi; void *
0x18002d2d4  call    memset_0
0x18002d2d9  mov     rcx, rdi; hMem
0x18002d2dc  call    cs:__imp_LocalFree
0x18002d2e3  nop     dword ptr [rax+rax+00h]
0x18002d2e8  mov     rdi, r14
0x18002d2eb  mov     esi, r14d
0x18002d2ee  mov     rcx, [rsp+130h+Buffer]; Buffer
0x18002d2f3  test    rcx, rcx
0x18002d2f6  jz      short loc_18002D304
0x18002d2f8  call    cs:__imp_LsaFreeMemory
0x18002d2ff  nop     dword ptr [rax+rax+00h]
0x18002d304  mov     [r12], rdi
0x18002d308  mov     eax, ebx
0x18002d30a  mov     [r13+0], esi
0x18002d30e  mov     rcx, [rbp+57h+var_40]
0x18002d312  xor     rcx, rsp; StackCookie
0x18002d315  call    __security_check_cookie
0x18002d31a  mov     rbx, [rsp+130h+arg_0]
0x18002d322  add     rsp, 100h
0x18002d329  pop     r15
0x18002d32b  pop     r14
0x18002d32d  pop     r13
0x18002d32f  pop     r12
0x18002d331  pop     rdi
0x18002d332  pop     rsi
0x18002d333  pop     rbp
0x18002d334  retn
0x18002d336  mov     ebx, 8
0x18002d33b  xor     r14d, r14d
0x18002d33e  jmp     loc_18002D2B2
0x18002d343  mov     ebx, 216h
0x18002d348  jmp     loc_18002D2B2
0x18002d34d  mov     ebx, 8
0x18002d352  jmp     loc_18002D2B2
```
