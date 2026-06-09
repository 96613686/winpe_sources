# ReadDialParamsBlob

- ea: `0x1800325e8`
- end: `0x180032833`
- name: `ReadDialParamsBlob`
- size: `587`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003222c`
- `0x180032368`

## callees

- `0x18001851c`
- `0x1800325e8`
- `0x180046e12`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180032684`
- `ntdll!RtlNtStatusToDosError` at `0x180032795`
- `ntdll!RtlNtStatusToDosError` at `0x180032684`
- `ntdll!RtlNtStatusToDosError` at `0x180032795`
- `ntdll!RtlInitUnicodeString` at `0x18003265d`
- `ntdll!RtlInitUnicodeString` at `0x180032770`
- `ntdll!RtlInitUnicodeString` at `0x18003265d`
- `ntdll!RtlInitUnicodeString` at `0x180032770`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800326c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800326c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800327c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800327c8`
- `ADVAPI32!LsaOpenPolicy` at `0x180032678`
- `ADVAPI32!LsaOpenPolicy` at `0x180032678`
- `ADVAPI32!LsaFreeMemory` at `0x180032741`
- `ADVAPI32!LsaFreeMemory` at `0x1800327de`
- `ADVAPI32!LsaFreeMemory` at `0x180032741`
- `ADVAPI32!LsaFreeMemory` at `0x1800327de`
- `ADVAPI32!LsaRetrievePrivateData` at `0x180032785`
- `ADVAPI32!LsaRetrievePrivateData` at `0x180032785`
- `ADVAPI32!LsaClose` at `0x1800327a9`
- `ADVAPI32!LsaClose` at `0x1800327a9`

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
0x1800325e8  mov     [rsp-8+arg_0], rbx
0x1800325ed  push    rbp
0x1800325ee  push    rsi
0x1800325ef  push    rdi
0x1800325f0  push    r12
0x1800325f2  push    r13
0x1800325f4  push    r14
0x1800325f6  push    r15
0x1800325f8  lea     rbp, [rsp-27h]
0x1800325fd  sub     rsp, 100h
0x180032604  mov     rax, cs:__security_cookie
0x18003260b  xor     rax, rsp
0x18003260e  mov     [rbp+57h+var_40], rax
0x180032612  xor     r14d, r14d
0x180032615  mov     qword ptr [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x18003261e  mov     [rdx], r14
0x180032621  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180032626  xorps   xmm0, xmm0
0x180032629  mov     [rsp+130h+Buffer], r14
0x18003262e  mov     r12, rdx
0x180032631  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r14
0x180032635  xorps   xmm1, xmm1
0x180032638  mov     [rsp+130h+PolicyHandle], r14
0x18003263d  xor     edx, edx; SourceString
0x18003263f  mov     [r8], r14d
0x180032642  mov     r13, r8
0x180032645  mov     [rsp+130h+ObjectAttributes.RootDirectory], r14
0x18003264a  movups  xmmword ptr [rsp+130h+var_100.Length], xmm0
0x18003264f  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x180032653  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x180032658  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003265d  call    cs:__imp_RtlInitUnicodeString
0x180032663  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x180032668  mov     r8d, 20006h; DesiredAccess
0x18003266e  lea     rdx, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x180032673  lea     rcx, [rsp+130h+DestinationString]; SystemName
0x180032678  call    cs:__imp_LsaOpenPolicy
0x18003267e  test    eax, eax
0x180032680  jz      short loc_18003268F
0x180032682  mov     ecx, eax; Status
0x180032684  call    cs:__imp_RtlNtStatusToDosError
0x18003268a  jmp     loc_1800327EE
0x18003268f  mov     esi, r14d
0x180032692  mov     rdi, r14
0x180032695  mov     r15d, r14d
0x180032698  xor     r9d, r9d
0x18003269b  jmp     loc_180032752
0x1800326a0  mov     rax, [rsp+130h+Buffer]
0x1800326a5  test    rax, rax
0x1800326a8  jz      loc_180032829
0x1800326ae  movzx   ecx, word ptr [rax]
0x1800326b1  add     ecx, esi
0x1800326b3  cmp     ecx, esi
0x1800326b5  jb      loc_18003281F
0x1800326bb  mov     edx, ecx; uBytes
0x1800326bd  mov     ecx, 40h ; '@'; uFlags
0x1800326c2  call    cs:__imp_LocalAlloc
0x1800326c8  mov     r14, rax
0x1800326cb  test    rax, rax
0x1800326ce  jz      loc_180032815
0x1800326d4  test    rdi, rdi
0x1800326d7  jz      short loc_1800326FD
0x1800326d9  mov     r8d, esi; Size
0x1800326dc  mov     rdx, rdi; Src
0x1800326df  mov     rcx, rax; void *
0x1800326e2  call    memcpy_0
0x1800326e7  mov     r8d, esi; Size
0x1800326ea  xor     edx, edx; Val
0x1800326ec  mov     rcx, rdi; void *
0x1800326ef  call    memset_0
0x1800326f4  mov     rcx, rdi; hMem
0x1800326f7  call    cs:__imp_LocalFree
0x1800326fd  mov     rdx, [rsp+130h+Buffer]
0x180032702  mov     ecx, esi
0x180032704  add     rcx, r14; void *
0x180032707  movzx   r8d, word ptr [rdx]; Size
0x18003270b  mov     rdx, [rdx+8]; Src
0x18003270f  call    memcpy_0
0x180032714  mov     rdx, [rsp+130h+Buffer]
0x180032719  mov     rdi, r14
0x18003271c  xor     r14d, r14d
0x18003271f  movzx   ecx, word ptr [rdx]
0x180032722  mov     rax, [rdx+8]
0x180032726  add     esi, ecx
0x180032728  test    rcx, rcx
0x18003272b  jz      short loc_18003273E
0x18003272d  mov     [rax], r14b
0x180032730  inc     rax
0x180032733  sub     rcx, 1
0x180032737  jnz     short loc_18003272D
0x180032739  mov     rdx, [rsp+130h+Buffer]
0x18003273e  mov     rcx, rdx; Buffer
0x180032741  call    cs:__imp_LsaFreeMemory
0x180032747  inc     r15d
0x18003274a  mov     [rsp+130h+Buffer], r14
0x18003274f  mov     r9d, r15d
0x180032752  mov     r8, cs:g_pwszStore; pszFormat
0x180032759  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18003275d  mov     edx, 64h ; 'd'; cbDest
0x180032762  call    StringCbPrintfW
0x180032767  lea     rdx, [rbp+57h+pszDest]; SourceString
0x18003276b  lea     rcx, [rsp+130h+var_100]; DestinationString
0x180032770  call    cs:__imp_RtlInitUnicodeString
0x180032776  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x18003277b  lea     r8, [rsp+130h+Buffer]; PrivateData
0x180032780  lea     rdx, [rsp+130h+var_100]; KeyName
0x180032785  call    cs:__imp_LsaRetrievePrivateData
0x18003278b  test    eax, eax
0x18003278d  jz      loc_1800326A0
0x180032793  mov     ecx, eax; Status
0x180032795  call    cs:__imp_RtlNtStatusToDosError
0x18003279b  cmp     eax, 2
0x18003279e  mov     ebx, r14d
0x1800327a1  cmovnz  ebx, eax
0x1800327a4  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x1800327a9  call    cs:__imp_LsaClose
0x1800327af  test    ebx, ebx
0x1800327b1  jz      short loc_1800327D4
0x1800327b3  test    rdi, rdi
0x1800327b6  jz      short loc_1800327CE
0x1800327b8  mov     r8d, esi; Size
0x1800327bb  xor     edx, edx; Val
0x1800327bd  mov     rcx, rdi; void *
0x1800327c0  call    memset_0
0x1800327c5  mov     rcx, rdi; hMem
0x1800327c8  call    cs:__imp_LocalFree
0x1800327ce  mov     rdi, r14
0x1800327d1  mov     esi, r14d
0x1800327d4  mov     rcx, [rsp+130h+Buffer]; Buffer
0x1800327d9  test    rcx, rcx
0x1800327dc  jz      short loc_1800327E4
0x1800327de  call    cs:__imp_LsaFreeMemory
0x1800327e4  mov     [r12], rdi
0x1800327e8  mov     eax, ebx
0x1800327ea  mov     [r13+0], esi
0x1800327ee  mov     rcx, [rbp+57h+var_40]
0x1800327f2  xor     rcx, rsp; StackCookie
0x1800327f5  call    __security_check_cookie
0x1800327fa  mov     rbx, [rsp+130h+arg_0]
0x180032802  add     rsp, 100h
0x180032809  pop     r15
0x18003280b  pop     r14
0x18003280d  pop     r13
0x18003280f  pop     r12
0x180032811  pop     rdi
0x180032812  pop     rsi
0x180032813  pop     rbp
0x180032814  retn
0x180032815  mov     ebx, 8
0x18003281a  xor     r14d, r14d
0x18003281d  jmp     short loc_1800327A4
0x18003281f  mov     ebx, 216h
0x180032824  jmp     loc_1800327A4
0x180032829  mov     ebx, 8
0x18003282e  jmp     loc_1800327A4
```
