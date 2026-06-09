# ReadDialParamsBlob

- ea: `0x180074674`
- end: `0x1800748bf`
- name: `ReadDialParamsBlob`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800744ac`

## callees

- `0x180002ba6`
- `0x180039f60`
- `0x180074674`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180074783`
- `KERNEL32!LocalFree` at `0x180074854`
- `KERNEL32!LocalFree` at `0x180074783`
- `KERNEL32!LocalFree` at `0x180074854`
- `KERNEL32!LocalAlloc` at `0x18007474e`
- `KERNEL32!LocalAlloc` at `0x18007474e`
- `ADVAPI32!LsaClose` at `0x180074835`
- `ADVAPI32!LsaClose` at `0x180074835`
- `ADVAPI32!LsaFreeMemory` at `0x1800747cd`
- `ADVAPI32!LsaFreeMemory` at `0x18007486a`
- `ADVAPI32!LsaFreeMemory` at `0x1800747cd`
- `ADVAPI32!LsaFreeMemory` at `0x18007486a`
- `ADVAPI32!LsaOpenPolicy` at `0x180074704`
- `ADVAPI32!LsaOpenPolicy` at `0x180074704`
- `ADVAPI32!LsaRetrievePrivateData` at `0x180074811`
- `ADVAPI32!LsaRetrievePrivateData` at `0x180074811`
- `ntdll!RtlNtStatusToDosError` at `0x180074710`
- `ntdll!RtlNtStatusToDosError` at `0x180074821`
- `ntdll!RtlNtStatusToDosError` at `0x180074710`
- `ntdll!RtlNtStatusToDosError` at `0x180074821`
- `ntdll!RtlInitUnicodeString` at `0x1800746e9`
- `ntdll!RtlInitUnicodeString` at `0x1800747fc`
- `ntdll!RtlInitUnicodeString` at `0x1800746e9`
- `ntdll!RtlInitUnicodeString` at `0x1800747fc`

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
0x180074674  mov     [rsp-8+arg_0], rbx
0x180074679  push    rbp
0x18007467a  push    rsi
0x18007467b  push    rdi
0x18007467c  push    r12
0x18007467e  push    r13
0x180074680  push    r14
0x180074682  push    r15
0x180074684  lea     rbp, [rsp-27h]
0x180074689  sub     rsp, 100h
0x180074690  mov     rax, cs:__security_cookie
0x180074697  xor     rax, rsp
0x18007469a  mov     [rbp+57h+var_40], rax
0x18007469e  xor     r14d, r14d
0x1800746a1  mov     qword ptr [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x1800746aa  mov     [rdx], r14
0x1800746ad  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1800746b2  xorps   xmm0, xmm0
0x1800746b5  mov     [rsp+130h+Buffer], r14
0x1800746ba  mov     r12, rdx
0x1800746bd  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r14
0x1800746c1  xorps   xmm1, xmm1
0x1800746c4  mov     [rsp+130h+PolicyHandle], r14
0x1800746c9  xor     edx, edx; SourceString
0x1800746cb  mov     [r8], r14d
0x1800746ce  mov     r13, r8
0x1800746d1  mov     [rsp+130h+ObjectAttributes.RootDirectory], r14
0x1800746d6  movups  xmmword ptr [rsp+130h+var_100.Length], xmm0
0x1800746db  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x1800746df  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x1800746e4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800746e9  call    cs:__imp_RtlInitUnicodeString
0x1800746ef  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x1800746f4  mov     r8d, 20006h; DesiredAccess
0x1800746fa  lea     rdx, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1800746ff  lea     rcx, [rsp+130h+DestinationString]; SystemName
0x180074704  call    cs:__imp_LsaOpenPolicy
0x18007470a  test    eax, eax
0x18007470c  jz      short loc_18007471B
0x18007470e  mov     ecx, eax; Status
0x180074710  call    cs:__imp_RtlNtStatusToDosError
0x180074716  jmp     loc_18007487A
0x18007471b  mov     esi, r14d
0x18007471e  mov     rdi, r14
0x180074721  mov     r15d, r14d
0x180074724  xor     r9d, r9d
0x180074727  jmp     loc_1800747DE
0x18007472c  mov     rax, [rsp+130h+Buffer]
0x180074731  test    rax, rax
0x180074734  jz      loc_1800748B5
0x18007473a  movzx   ecx, word ptr [rax]
0x18007473d  add     ecx, esi
0x18007473f  cmp     ecx, esi
0x180074741  jb      loc_1800748AB
0x180074747  mov     edx, ecx; uBytes
0x180074749  mov     ecx, 40h ; '@'; uFlags
0x18007474e  call    cs:__imp_LocalAlloc
0x180074754  mov     r14, rax
0x180074757  test    rax, rax
0x18007475a  jz      loc_1800748A1
0x180074760  test    rdi, rdi
0x180074763  jz      short loc_180074789
0x180074765  mov     r8d, esi; Size
0x180074768  mov     rdx, rdi; Src
0x18007476b  mov     rcx, rax; void *
0x18007476e  call    memcpy_0
0x180074773  mov     r8d, esi; Size
0x180074776  xor     edx, edx; Val
0x180074778  mov     rcx, rdi; void *
0x18007477b  call    memset_0
0x180074780  mov     rcx, rdi; hMem
0x180074783  call    cs:__imp_LocalFree
0x180074789  mov     rdx, [rsp+130h+Buffer]
0x18007478e  mov     ecx, esi
0x180074790  add     rcx, r14; void *
0x180074793  movzx   r8d, word ptr [rdx]; Size
0x180074797  mov     rdx, [rdx+8]; Src
0x18007479b  call    memcpy_0
0x1800747a0  mov     rdx, [rsp+130h+Buffer]
0x1800747a5  mov     rdi, r14
0x1800747a8  xor     r14d, r14d
0x1800747ab  movzx   ecx, word ptr [rdx]
0x1800747ae  mov     rax, [rdx+8]
0x1800747b2  add     esi, ecx
0x1800747b4  test    rcx, rcx
0x1800747b7  jz      short loc_1800747CA
0x1800747b9  mov     [rax], r14b
0x1800747bc  inc     rax
0x1800747bf  sub     rcx, 1
0x1800747c3  jnz     short loc_1800747B9
0x1800747c5  mov     rdx, [rsp+130h+Buffer]
0x1800747ca  mov     rcx, rdx; Buffer
0x1800747cd  call    cs:__imp_LsaFreeMemory
0x1800747d3  inc     r15d
0x1800747d6  mov     [rsp+130h+Buffer], r14
0x1800747db  mov     r9d, r15d
0x1800747de  mov     r8, cs:g_pwszStore; pszFormat
0x1800747e5  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800747e9  mov     edx, 64h ; 'd'; cbDest
0x1800747ee  call    StringCbPrintfW
0x1800747f3  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1800747f7  lea     rcx, [rsp+130h+var_100]; DestinationString
0x1800747fc  call    cs:__imp_RtlInitUnicodeString
0x180074802  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x180074807  lea     r8, [rsp+130h+Buffer]; PrivateData
0x18007480c  lea     rdx, [rsp+130h+var_100]; KeyName
0x180074811  call    cs:__imp_LsaRetrievePrivateData
0x180074817  test    eax, eax
0x180074819  jz      loc_18007472C
0x18007481f  mov     ecx, eax; Status
0x180074821  call    cs:__imp_RtlNtStatusToDosError
0x180074827  cmp     eax, 2
0x18007482a  mov     ebx, r14d
0x18007482d  cmovnz  ebx, eax
0x180074830  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x180074835  call    cs:__imp_LsaClose
0x18007483b  test    ebx, ebx
0x18007483d  jz      short loc_180074860
0x18007483f  test    rdi, rdi
0x180074842  jz      short loc_18007485A
0x180074844  mov     r8d, esi; Size
0x180074847  xor     edx, edx; Val
0x180074849  mov     rcx, rdi; void *
0x18007484c  call    memset_0
0x180074851  mov     rcx, rdi; hMem
0x180074854  call    cs:__imp_LocalFree
0x18007485a  mov     rdi, r14
0x18007485d  mov     esi, r14d
0x180074860  mov     rcx, [rsp+130h+Buffer]; Buffer
0x180074865  test    rcx, rcx
0x180074868  jz      short loc_180074870
0x18007486a  call    cs:__imp_LsaFreeMemory
0x180074870  mov     [r12], rdi
0x180074874  mov     eax, ebx
0x180074876  mov     [r13+0], esi
0x18007487a  mov     rcx, [rbp+57h+var_40]
0x18007487e  xor     rcx, rsp; StackCookie
0x180074881  call    __security_check_cookie
0x180074886  mov     rbx, [rsp+130h+arg_0]
0x18007488e  add     rsp, 100h
0x180074895  pop     r15
0x180074897  pop     r14
0x180074899  pop     r13
0x18007489b  pop     r12
0x18007489d  pop     rdi
0x18007489e  pop     rsi
0x18007489f  pop     rbp
0x1800748a0  retn
0x1800748a1  mov     ebx, 8
0x1800748a6  xor     r14d, r14d
0x1800748a9  jmp     short loc_180074830
0x1800748ab  mov     ebx, 216h
0x1800748b0  jmp     loc_180074830
0x1800748b5  mov     ebx, 8
0x1800748ba  jmp     loc_180074830
```
