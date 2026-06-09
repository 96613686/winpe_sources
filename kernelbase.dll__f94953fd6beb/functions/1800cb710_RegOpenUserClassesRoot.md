# RegOpenUserClassesRoot

- ea: `0x1800cb710`
- end: `0x1800cb99a`
- name: `RegOpenUserClassesRoot`
- size: `650`
- prototype: `LSTATUS __stdcall(HANDLE hToken, DWORD dwOptions, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800cb710`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800cb8a9`
- `ntdll!RtlFreeUnicodeString` at `0x1800cb8a9`
- `ntdll!NtOpenKey` at `0x1800cb882`
- `ntdll!NtOpenKey` at `0x1800cb882`
- `ntdll!RtlNtStatusToDosError` at `0x1800cb8c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800cb8ff`
- `ntdll!RtlNtStatusToDosError` at `0x1800cb8c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800cb8ff`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800cb82b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800cb82b`
- `ntdll!RtlAppendUnicodeToString` at `0x1800cb843`
- `ntdll!RtlAppendUnicodeToString` at `0x1800cb843`
- `ntdll!RtlCopyUnicodeString` at `0x1800cb81b`
- `ntdll!RtlCopyUnicodeString` at `0x1800cb81b`
- `ntdll!NtQueryInformationToken` at `0x1800cb786`
- `ntdll!NtQueryInformationToken` at `0x1800cb946`
- `ntdll!NtQueryInformationToken` at `0x1800cb786`
- `ntdll!NtQueryInformationToken` at `0x1800cb946`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800cb7a3`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800cb7a3`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800cb805`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800cb805`
- `ntdll!RtlFreeHeap` at `0x1800cb89e`
- `ntdll!RtlFreeHeap` at `0x1800cb968`
- `ntdll!RtlFreeHeap` at `0x1800cb98f`
- `ntdll!RtlFreeHeap` at `0x1800cb89e`
- `ntdll!RtlFreeHeap` at `0x1800cb968`
- `ntdll!RtlFreeHeap` at `0x1800cb98f`
- `ntdll!RtlAllocateHeap` at `0x1800cb7dd`
- `ntdll!RtlAllocateHeap` at `0x1800cb91e`
- `ntdll!RtlAllocateHeap` at `0x1800cb7dd`
- `ntdll!RtlAllocateHeap` at `0x1800cb91e`

## string_xrefs

- `0x1800cb7f4`: `\Registry\User\`

## pseudocode

```c
LSTATUS __stdcall RegOpenUserClassesRoot(HANDLE hToken, DWORD dwOptions, REGSAM samDesired, PHKEY phkResult)
{
  int v7; // eax
  PSID *Heap; // rsi
  int inited; // ebx
  LSTATUS result; // eax
  ULONG TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _BYTE TokenInformation[112]; // [rsp+A0h] [rbp-60h] BYREF

  TokenInformationLength = 0;
  UnicodeString = 0;
  if ( !phkResult || !hToken || dwOptions )
    return 87;
  v7 = NtQueryInformationToken(hToken, TokenUser, TokenInformation, 0x64u, &TokenInformationLength);
  if ( v7 >= 0 )
  {
    Heap = (PSID *)TokenInformation;
    goto LABEL_6;
  }
  result = RtlNtStatusToDosError(v7);
  if ( result == 122 )
  {
    Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
    if ( !Heap )
      return 8;
    inited = NtQueryInformationToken(hToken, TokenUser, Heap, TokenInformationLength, &TokenInformationLength);
    if ( inited < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      return RtlNtStatusToDosError(inited);
    }
LABEL_6:
    inited = RtlConvertSidToUnicodeString(&UnicodeString, *Heap, 1u);
    if ( inited >= 0 )
    {
      Destination = 0;
      Destination.MaximumLength = UnicodeString.Length + 50;
      Destination.Buffer = (PWSTR)RtlAllocateHeap(
                                    NtCurrentPeb()->ProcessHeap,
                                    0,
                                    (unsigned __int16)(UnicodeString.Length + 50));
      if ( Destination.Buffer )
      {
        DestinationString = 0;
        inited = RtlInitUnicodeStringEx(&DestinationString, L"\\Registry\\User\\");
        if ( inited >= 0 )
        {
          RtlCopyUnicodeString(&Destination, &DestinationString);
          inited = RtlAppendUnicodeStringToString(&Destination, &UnicodeString);
          if ( inited >= 0 )
          {
            inited = RtlAppendUnicodeToString(&Destination, L"_Classes");
            if ( inited >= 0 )
            {
              *(_QWORD *)&ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = &Destination;
              *(_QWORD *)&ObjectAttributes.Attributes = 64;
              ObjectAttributes.RootDirectory = 0;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              inited = NtOpenKey((PHANDLE)phkResult, samDesired, &ObjectAttributes);
            }
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
      }
      else
      {
        inited = -1073741801;
      }
      RtlFreeUnicodeString(&UnicodeString);
    }
    if ( Heap != (PSID *)TokenInformation )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( inited >= 0 )
      *phkResult = (HKEY)((unsigned __int64)*phkResult | 2);
    return RtlNtStatusToDosError(inited);
  }
  return result;
}

```

## disassembly

```asm
0x1800cb710  push    rbp
0x1800cb712  push    rbx
0x1800cb713  push    rdi
0x1800cb714  push    r14
0x1800cb716  push    r15
0x1800cb718  lea     rbp, [rsp-20h]
0x1800cb71d  sub     rsp, 120h
0x1800cb724  mov     rax, cs:__security_cookie
0x1800cb72b  xor     rax, rsp
0x1800cb72e  mov     [rbp+40h+var_30], rax
0x1800cb732  xor     r15d, r15d
0x1800cb735  xorps   xmm0, xmm0
0x1800cb738  mov     [rsp+140h+TokenInformationLength], r15d
0x1800cb73d  mov     rdi, r9
0x1800cb740  mov     r14d, r8d
0x1800cb743  mov     rbx, rcx
0x1800cb746  movups  xmmword ptr [rsp+140h+UnicodeString.Length], xmm0
0x1800cb74b  test    r9, r9
0x1800cb74e  jz      loc_1800CB8F6
0x1800cb754  test    rcx, rcx
0x1800cb757  jz      loc_1800CB8F6
0x1800cb75d  test    edx, edx
0x1800cb75f  jnz     loc_1800CB8F6
0x1800cb765  lea     rax, [rsp+140h+TokenInformationLength]
0x1800cb76a  mov     [rsp+140h+arg_8], rsi
0x1800cb772  mov     r9d, 64h ; 'd'; TokenInformationLength
0x1800cb778  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x1800cb77d  lea     r8, [rbp+40h+TokenInformation]; TokenInformation
0x1800cb781  mov     edx, 1; TokenInformationClass
0x1800cb786  call    cs:__imp_NtQueryInformationToken
0x1800cb78c  test    eax, eax
0x1800cb78e  js      loc_1800CB8FD
0x1800cb794  lea     rsi, [rbp+40h+TokenInformation]
0x1800cb798  mov     rdx, [rsi]; Sid
0x1800cb79b  lea     rcx, [rsp+140h+UnicodeString]; UnicodeString
0x1800cb7a0  mov     r8b, 1; AllocateDestinationString
0x1800cb7a3  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800cb7a9  mov     ebx, eax
0x1800cb7ab  test    eax, eax
0x1800cb7ad  js      loc_1800CB8AF
0x1800cb7b3  movzx   eax, [rsp+140h+UnicodeString.Length]
0x1800cb7b8  xorps   xmm0, xmm0
0x1800cb7bb  movups  xmmword ptr [rsp+140h+Destination.Length], xmm0
0x1800cb7c0  add     ax, 32h ; '2'
0x1800cb7c4  xor     edx, edx; Flags
0x1800cb7c6  movzx   r8d, ax; Size
0x1800cb7ca  mov     [rsp+140h+Destination.MaximumLength], r8w
0x1800cb7d0  mov     rcx, gs:60h
0x1800cb7d9  mov     rcx, [rcx+30h]; HeapHandle
0x1800cb7dd  call    cs:__imp_RtlAllocateHeap
0x1800cb7e3  mov     [rsp+140h+Destination.Buffer], rax
0x1800cb7e8  test    rax, rax
0x1800cb7eb  jz      loc_1800CB8EF
0x1800cb7f1  xorps   xmm0, xmm0
0x1800cb7f4  lea     rdx, aRegistryUser_0; "\\Registry\\User\\"
0x1800cb7fb  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x1800cb800  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x1800cb805  call    cs:__imp_RtlInitUnicodeStringEx
0x1800cb80b  mov     ebx, eax
0x1800cb80d  test    eax, eax
0x1800cb80f  js      short loc_1800CB88A
0x1800cb811  lea     rdx, [rsp+140h+DestinationString]; SourceString
0x1800cb816  lea     rcx, [rsp+140h+Destination]; DestinationString
0x1800cb81b  call    cs:__imp_RtlCopyUnicodeString
0x1800cb821  lea     rdx, [rsp+140h+UnicodeString]; Source
0x1800cb826  lea     rcx, [rsp+140h+Destination]; Destination
0x1800cb82b  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800cb831  mov     ebx, eax
0x1800cb833  test    eax, eax
0x1800cb835  js      short loc_1800CB88A
0x1800cb837  lea     rdx, aClasses_0; "_Classes"
0x1800cb83e  lea     rcx, [rsp+140h+Destination]; Destination
0x1800cb843  call    cs:__imp_RtlAppendUnicodeToString
0x1800cb849  mov     ebx, eax
0x1800cb84b  test    eax, eax
0x1800cb84d  js      short loc_1800CB88A
0x1800cb84f  lea     rax, [rsp+140h+Destination]
0x1800cb854  mov     qword ptr [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x1800cb85d  xorps   xmm0, xmm0
0x1800cb860  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x1800cb865  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x1800cb86a  mov     qword ptr [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x1800cb872  mov     edx, r14d; DesiredAccess
0x1800cb875  mov     [rsp+140h+ObjectAttributes.RootDirectory], r15
0x1800cb87a  mov     rcx, rdi; KeyHandle
0x1800cb87d  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800cb882  call    cs:__imp_NtOpenKey
0x1800cb888  mov     ebx, eax
0x1800cb88a  mov     rcx, gs:60h
0x1800cb893  xor     edx, edx; Flags
0x1800cb895  mov     r8, [rsp+140h+Destination.Buffer]; P
0x1800cb89a  mov     rcx, [rcx+30h]; HeapHandle
0x1800cb89e  call    cs:__imp_RtlFreeHeap
0x1800cb8a4  lea     rcx, [rsp+140h+UnicodeString]; UnicodeString
0x1800cb8a9  call    cs:__imp_RtlFreeUnicodeString
0x1800cb8af  lea     rax, [rbp+40h+TokenInformation]
0x1800cb8b3  cmp     rsi, rax
0x1800cb8b6  jnz     loc_1800CB97D
0x1800cb8bc  test    ebx, ebx
0x1800cb8be  js      short loc_1800CB8C4
0x1800cb8c0  or      qword ptr [rdi], 2
0x1800cb8c4  mov     ecx, ebx; Status
0x1800cb8c6  call    cs:__imp_RtlNtStatusToDosError
0x1800cb8cc  mov     rsi, [rsp+140h+arg_8]
0x1800cb8d4  mov     rcx, [rbp+40h+var_30]
0x1800cb8d8  xor     rcx, rsp; StackCookie
0x1800cb8db  call    __security_check_cookie
0x1800cb8e0  add     rsp, 120h
0x1800cb8e7  pop     r15
0x1800cb8e9  pop     r14
0x1800cb8eb  pop     rdi
0x1800cb8ec  pop     rbx
0x1800cb8ed  pop     rbp
0x1800cb8ee  retn
0x1800cb8ef  mov     ebx, 0C0000017h
0x1800cb8f4  jmp     short loc_1800CB8A4
0x1800cb8f6  mov     eax, 57h ; 'W'
0x1800cb8fb  jmp     short loc_1800CB8D4
0x1800cb8fd  mov     ecx, eax; Status
0x1800cb8ff  call    cs:__imp_RtlNtStatusToDosError
0x1800cb905  cmp     eax, 7Ah ; 'z'
0x1800cb908  jnz     short loc_1800CB8CC
0x1800cb90a  mov     rcx, gs:60h
0x1800cb913  xor     edx, edx; Flags
0x1800cb915  mov     r8d, [rsp+140h+TokenInformationLength]; Size
0x1800cb91a  mov     rcx, [rcx+30h]; HeapHandle
0x1800cb91e  call    cs:__imp_RtlAllocateHeap
0x1800cb924  mov     rsi, rax
0x1800cb927  test    rax, rax
0x1800cb92a  jz      short loc_1800CB973
0x1800cb92c  mov     r9d, [rsp+140h+TokenInformationLength]; TokenInformationLength
0x1800cb931  lea     rax, [rsp+140h+TokenInformationLength]
0x1800cb936  mov     r8, rsi; TokenInformation
0x1800cb939  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x1800cb93e  mov     edx, 1; TokenInformationClass
0x1800cb943  mov     rcx, rbx; TokenHandle
0x1800cb946  call    cs:__imp_NtQueryInformationToken
0x1800cb94c  mov     ebx, eax
0x1800cb94e  test    eax, eax
0x1800cb950  jns     loc_1800CB798
0x1800cb956  mov     rcx, gs:60h
0x1800cb95f  mov     r8, rsi; P
0x1800cb962  xor     edx, edx; Flags
0x1800cb964  mov     rcx, [rcx+30h]; HeapHandle
0x1800cb968  call    cs:__imp_RtlFreeHeap
0x1800cb96e  jmp     loc_1800CB8C4
0x1800cb973  mov     eax, 8
0x1800cb978  jmp     loc_1800CB8CC
0x1800cb97d  mov     rcx, gs:60h
0x1800cb986  mov     r8, rsi; P
0x1800cb989  xor     edx, edx; Flags
0x1800cb98b  mov     rcx, [rcx+30h]; HeapHandle
0x1800cb98f  call    cs:__imp_RtlFreeHeap
0x1800cb995  jmp     loc_1800CB8BC
```
