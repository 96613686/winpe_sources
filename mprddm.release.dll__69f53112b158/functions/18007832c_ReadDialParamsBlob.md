# ReadDialParamsBlob

- ea: `0x18007832c`
- end: `0x1800785b2`
- name: `ReadDialParamsBlob`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078170`

## callees

- `0x180002be6`
- `0x18003b75c`
- `0x18007832c`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180078453`
- `KERNEL32!LocalFree` at `0x180078538`
- `KERNEL32!LocalFree` at `0x180078453`
- `KERNEL32!LocalFree` at `0x180078538`
- `KERNEL32!LocalAlloc` at `0x180078418`
- `KERNEL32!LocalAlloc` at `0x180078418`
- `ADVAPI32!LsaClose` at `0x180078513`
- `ADVAPI32!LsaClose` at `0x180078513`
- `ADVAPI32!LsaFreeMemory` at `0x180078490`
- `ADVAPI32!LsaFreeMemory` at `0x180078554`
- `ADVAPI32!LsaFreeMemory` at `0x180078490`
- `ADVAPI32!LsaFreeMemory` at `0x180078554`
- `ADVAPI32!LsaOpenPolicy` at `0x1800783c8`
- `ADVAPI32!LsaOpenPolicy` at `0x1800783c8`
- `ADVAPI32!LsaRetrievePrivateData` at `0x1800784e3`
- `ADVAPI32!LsaRetrievePrivateData` at `0x1800784e3`
- `ntdll!RtlNtStatusToDosError` at `0x1800783da`
- `ntdll!RtlNtStatusToDosError` at `0x1800784f9`
- `ntdll!RtlNtStatusToDosError` at `0x1800783da`
- `ntdll!RtlNtStatusToDosError` at `0x1800784f9`
- `ntdll!RtlInitUnicodeString` at `0x1800783a7`
- `ntdll!RtlInitUnicodeString` at `0x1800784c8`
- `ntdll!RtlInitUnicodeString` at `0x1800783a7`
- `ntdll!RtlInitUnicodeString` at `0x1800784c8`

## pseudocode

```c
ULONG __fastcall ReadDialParamsBlob(__int64 a1, _QWORD *a2, unsigned int *a3)
{
  unsigned int v5; // esi
  void *v6; // rbx
  NTSTATUS v7; // eax
  ULONG result; // eax
  unsigned int v9; // r13d
  __int64 i; // r9
  unsigned int v11; // ecx
  char *v12; // rax
  char *v13; // r14
  unsigned __int64 v14; // rcx
  NTSTATUS PrivateData; // eax
  ULONG v16; // eax
  int v17; // edi
  PVOID Buffer; // [rsp+20h] [rbp-B9h] BYREF
  PVOID PolicyHandle; // [rsp+28h] [rbp-B1h] BYREF
  struct _UNICODE_STRING v20; // [rsp+30h] [rbp-A9h] BYREF
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
  v5 = 0;
  ObjectAttributes.ObjectName = 0;
  v6 = 0;
  v20 = 0;
  DestinationString = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v7 = LsaOpenPolicy((PLSA_UNICODE_STRING)&DestinationString, &ObjectAttributes, 0x20006u, &PolicyHandle);
  if ( v7 )
    return RtlNtStatusToDosError(v7);
  v9 = 0;
  for ( i = 0; ; i = v9 )
  {
    StringCbPrintfW(pszDest, 0x64u, g_pwszStore, i, Buffer);
    RtlInitUnicodeString(&v20, pszDest);
    PrivateData = LsaRetrievePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v20, (PLSA_UNICODE_STRING *)&Buffer);
    if ( PrivateData )
      break;
    if ( !Buffer )
    {
      v17 = 8;
      goto LABEL_13;
    }
    v11 = v5 + *(unsigned __int16 *)Buffer;
    if ( v11 < v5 )
    {
      v17 = 534;
      goto LABEL_13;
    }
    v12 = (char *)LocalAlloc(0x40u, v11);
    v13 = v12;
    if ( !v12 )
    {
      v17 = 8;
      goto LABEL_13;
    }
    if ( v6 )
    {
      memcpy_0(v12, v6, v5);
      memset_0(v6, 0, v5);
      LocalFree(v6);
    }
    memcpy_0(&v13[v5], *((const void **)Buffer + 1), *(unsigned __int16 *)Buffer);
    v6 = v13;
    v14 = *(unsigned __int16 *)Buffer;
    v5 += v14;
    memset(*((void **)Buffer + 1), 0, v14);
    LsaFreeMemory(Buffer);
    ++v9;
    Buffer = 0;
  }
  v16 = RtlNtStatusToDosError(PrivateData);
  v17 = 0;
  if ( v16 != 2 )
    v17 = v16;
LABEL_13:
  LsaClose(PolicyHandle);
  if ( v17 )
  {
    if ( v6 )
    {
      memset_0(v6, 0, v5);
      LocalFree(v6);
    }
    v6 = 0;
    v5 = 0;
  }
  if ( Buffer )
    LsaFreeMemory(Buffer);
  *a2 = v6;
  result = v17;
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x18007832c  mov     [rsp-8+arg_0], rbx
0x180078331  push    rbp
0x180078332  push    rsi
0x180078333  push    rdi
0x180078334  push    r12
0x180078336  push    r13
0x180078338  push    r14
0x18007833a  push    r15
0x18007833c  lea     rbp, [rsp-27h]
0x180078341  sub     rsp, 100h
0x180078348  mov     rax, cs:__security_cookie
0x18007834f  xor     rax, rsp
0x180078352  mov     [rbp+57h+var_40], rax
0x180078356  xor     r14d, r14d
0x180078359  mov     qword ptr [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x180078362  mov     [rdx], r14
0x180078365  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18007836a  xorps   xmm0, xmm0
0x18007836d  mov     [rsp+130h+Buffer], r14
0x180078372  mov     r15, rdx
0x180078375  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], r14
0x180078379  xorps   xmm1, xmm1
0x18007837c  mov     [rsp+130h+PolicyHandle], r14
0x180078381  xor     edx, edx; SourceString
0x180078383  mov     [r8], r14d
0x180078386  mov     r12, r8
0x180078389  mov     [rsp+130h+ObjectAttributes.RootDirectory], r14
0x18007838e  mov     esi, r14d
0x180078391  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x180078395  mov     ebx, r14d
0x180078398  movups  xmmword ptr [rsp+130h+var_100.Length], xmm0
0x18007839d  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm1
0x1800783a2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800783a7  call    cs:__imp_RtlInitUnicodeString
0x1800783ae  nop     dword ptr [rax+rax+00h]
0x1800783b3  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x1800783b8  mov     r8d, 20006h; DesiredAccess
0x1800783be  lea     rdx, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x1800783c3  lea     rcx, [rsp+130h+DestinationString]; SystemName
0x1800783c8  call    cs:__imp_LsaOpenPolicy
0x1800783cf  nop     dword ptr [rax+rax+00h]
0x1800783d4  test    eax, eax
0x1800783d6  jz      short loc_1800783EB
0x1800783d8  mov     ecx, eax; Status
0x1800783da  call    cs:__imp_RtlNtStatusToDosError
0x1800783e1  nop     dword ptr [rax+rax+00h]
0x1800783e6  jmp     loc_180078569
0x1800783eb  mov     r13d, r14d
0x1800783ee  xor     r9d, r9d
0x1800783f1  jmp     loc_1800784AA
0x1800783f6  mov     rax, [rsp+130h+Buffer]
0x1800783fb  test    rax, rax
0x1800783fe  jz      loc_1800785A8
0x180078404  movzx   ecx, word ptr [rax]
0x180078407  add     ecx, esi
0x180078409  cmp     ecx, esi
0x18007840b  jb      loc_18007859E
0x180078411  mov     edx, ecx; uBytes
0x180078413  mov     ecx, 40h ; '@'; uFlags
0x180078418  call    cs:__imp_LocalAlloc
0x18007841f  nop     dword ptr [rax+rax+00h]
0x180078424  mov     r14, rax
0x180078427  test    rax, rax
0x18007842a  jz      loc_180078591
0x180078430  test    rbx, rbx
0x180078433  jz      short loc_18007845F
0x180078435  mov     r8d, esi; Size
0x180078438  mov     rdx, rbx; Src
0x18007843b  mov     rcx, rax; void *
0x18007843e  call    memcpy_0
0x180078443  mov     r8d, esi; Size
0x180078446  xor     edx, edx; Val
0x180078448  mov     rcx, rbx; void *
0x18007844b  call    memset_0
0x180078450  mov     rcx, rbx; hMem
0x180078453  call    cs:__imp_LocalFree
0x18007845a  nop     dword ptr [rax+rax+00h]
0x18007845f  mov     rdx, [rsp+130h+Buffer]
0x180078464  mov     ecx, esi
0x180078466  add     rcx, r14; void *
0x180078469  movzx   r8d, word ptr [rdx]; Size
0x18007846d  mov     rdx, [rdx+8]; Src
0x180078471  call    memcpy_0
0x180078476  mov     rdi, [rsp+130h+Buffer]
0x18007847b  xor     eax, eax
0x18007847d  mov     rbx, r14
0x180078480  movzx   ecx, word ptr [rdi]
0x180078483  mov     rdi, [rdi+8]
0x180078487  add     esi, ecx
0x180078489  rep stosb
0x18007848b  mov     rcx, [rsp+130h+Buffer]; Buffer
0x180078490  call    cs:__imp_LsaFreeMemory
0x180078497  nop     dword ptr [rax+rax+00h]
0x18007849c  xor     r14d, r14d
0x18007849f  inc     r13d
0x1800784a2  mov     [rsp+130h+Buffer], r14
0x1800784a7  mov     r9d, r13d
0x1800784aa  mov     r8, cs:g_pwszStore; pszFormat
0x1800784b1  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800784b5  mov     edx, 64h ; 'd'; cbDest
0x1800784ba  call    StringCbPrintfW
0x1800784bf  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1800784c3  lea     rcx, [rsp+130h+var_100]; DestinationString
0x1800784c8  call    cs:__imp_RtlInitUnicodeString
0x1800784cf  nop     dword ptr [rax+rax+00h]
0x1800784d4  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x1800784d9  lea     r8, [rsp+130h+Buffer]; PrivateData
0x1800784de  lea     rdx, [rsp+130h+var_100]; KeyName
0x1800784e3  call    cs:__imp_LsaRetrievePrivateData
0x1800784ea  nop     dword ptr [rax+rax+00h]
0x1800784ef  test    eax, eax
0x1800784f1  jz      loc_1800783F6
0x1800784f7  mov     ecx, eax; Status
0x1800784f9  call    cs:__imp_RtlNtStatusToDosError
0x180078500  nop     dword ptr [rax+rax+00h]
0x180078505  cmp     eax, 2
0x180078508  mov     edi, r14d
0x18007850b  cmovnz  edi, eax
0x18007850e  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x180078513  call    cs:__imp_LsaClose
0x18007851a  nop     dword ptr [rax+rax+00h]
0x18007851f  test    edi, edi
0x180078521  jz      short loc_18007854A
0x180078523  test    rbx, rbx
0x180078526  jz      short loc_180078544
0x180078528  mov     r8d, esi; Size
0x18007852b  xor     edx, edx; Val
0x18007852d  mov     rcx, rbx; void *
0x180078530  call    memset_0
0x180078535  mov     rcx, rbx; hMem
0x180078538  call    cs:__imp_LocalFree
0x18007853f  nop     dword ptr [rax+rax+00h]
0x180078544  mov     rbx, r14
0x180078547  mov     esi, r14d
0x18007854a  mov     rcx, [rsp+130h+Buffer]; Buffer
0x18007854f  test    rcx, rcx
0x180078552  jz      short loc_180078560
0x180078554  call    cs:__imp_LsaFreeMemory
0x18007855b  nop     dword ptr [rax+rax+00h]
0x180078560  mov     [r15], rbx
0x180078563  mov     eax, edi
0x180078565  mov     [r12], esi
0x180078569  mov     rcx, [rbp+57h+var_40]
0x18007856d  xor     rcx, rsp; StackCookie
0x180078570  call    __security_check_cookie
0x180078575  mov     rbx, [rsp+130h+arg_0]
0x18007857d  add     rsp, 100h
0x180078584  pop     r15
0x180078586  pop     r14
0x180078588  pop     r13
0x18007858a  pop     r12
0x18007858c  pop     rdi
0x18007858d  pop     rsi
0x18007858e  pop     rbp
0x18007858f  retn
0x180078591  mov     edi, 8
0x180078596  xor     r14d, r14d
0x180078599  jmp     loc_18007850E
0x18007859e  mov     edi, 216h
0x1800785a3  jmp     loc_18007850E
0x1800785a8  mov     edi, 8
0x1800785ad  jmp     loc_18007850E
```
