# RegOpenUserClassesRoot

- ea: `0x1800d2610`
- end: `0x1800d28ff`
- name: `RegOpenUserClassesRoot`
- size: `751`
- prototype: `LSTATUS __stdcall(HANDLE hToken, DWORD dwOptions, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800d2610`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800d27e3`
- `ntdll!RtlFreeUnicodeString` at `0x1800d27e3`
- `ntdll!NtOpenKey` at `0x1800d27b0`
- `ntdll!NtOpenKey` at `0x1800d27b0`
- `ntdll!RtlNtStatusToDosError` at `0x1800d2806`
- `ntdll!RtlNtStatusToDosError` at `0x1800d2846`
- `ntdll!RtlNtStatusToDosError` at `0x1800d2806`
- `ntdll!RtlNtStatusToDosError` at `0x1800d2846`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800d274d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800d274d`
- `ntdll!RtlAppendUnicodeToString` at `0x1800d276b`
- `ntdll!RtlAppendUnicodeToString` at `0x1800d276b`
- `ntdll!RtlCopyUnicodeString` at `0x1800d2737`
- `ntdll!RtlCopyUnicodeString` at `0x1800d2737`
- `ntdll!NtQueryInformationToken` at `0x1800d2686`
- `ntdll!NtQueryInformationToken` at `0x1800d2899`
- `ntdll!NtQueryInformationToken` at `0x1800d2686`
- `ntdll!NtQueryInformationToken` at `0x1800d2899`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800d26a9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800d26a9`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800d2717`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800d2717`
- `ntdll!RtlFreeHeap` at `0x1800d27d2`
- `ntdll!RtlFreeHeap` at `0x1800d28c1`
- `ntdll!RtlFreeHeap` at `0x1800d28ee`
- `ntdll!RtlFreeHeap` at `0x1800d27d2`
- `ntdll!RtlFreeHeap` at `0x1800d28c1`
- `ntdll!RtlFreeHeap` at `0x1800d28ee`
- `ntdll!RtlAllocateHeap` at `0x1800d26e9`
- `ntdll!RtlAllocateHeap` at `0x1800d286b`
- `ntdll!RtlAllocateHeap` at `0x1800d26e9`
- `ntdll!RtlAllocateHeap` at `0x1800d286b`

## string_xrefs

- `0x1800d2706`: `\Registry\User\`

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
0x1800d2610  push    rbp
0x1800d2612  push    rbx
0x1800d2613  push    rdi
0x1800d2614  push    r14
0x1800d2616  push    r15
0x1800d2618  lea     rbp, [rsp-20h]
0x1800d261d  sub     rsp, 120h
0x1800d2624  mov     rax, cs:__security_cookie
0x1800d262b  xor     rax, rsp
0x1800d262e  mov     [rbp+40h+var_30], rax
0x1800d2632  xor     r15d, r15d
0x1800d2635  xorps   xmm0, xmm0
0x1800d2638  mov     [rsp+140h+TokenInformationLength], r15d
0x1800d263d  mov     rdi, r9
0x1800d2640  mov     r14d, r8d
0x1800d2643  mov     rbx, rcx
0x1800d2646  movups  xmmword ptr [rsp+140h+UnicodeString.Length], xmm0
0x1800d264b  test    r9, r9
0x1800d264e  jz      loc_1800D283D
0x1800d2654  test    rcx, rcx
0x1800d2657  jz      loc_1800D283D
0x1800d265d  test    edx, edx
0x1800d265f  jnz     loc_1800D283D
0x1800d2665  lea     rax, [rsp+140h+TokenInformationLength]
0x1800d266a  mov     [rsp+140h+arg_8], rsi
0x1800d2672  mov     r9d, 64h ; 'd'; TokenInformationLength
0x1800d2678  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x1800d267d  lea     r8, [rbp+40h+TokenInformation]; TokenInformation
0x1800d2681  mov     edx, 1; TokenInformationClass
0x1800d2686  call    cs:__imp_NtQueryInformationToken
0x1800d268d  nop     dword ptr [rax+rax+00h]
0x1800d2692  test    eax, eax
0x1800d2694  js      loc_1800D2844
0x1800d269a  lea     rsi, [rbp+40h+TokenInformation]
0x1800d269e  mov     rdx, [rsi]; Sid
0x1800d26a1  lea     rcx, [rsp+140h+UnicodeString]; UnicodeString
0x1800d26a6  mov     r8b, 1; AllocateDestinationString
0x1800d26a9  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800d26b0  nop     dword ptr [rax+rax+00h]
0x1800d26b5  mov     ebx, eax
0x1800d26b7  test    eax, eax
0x1800d26b9  js      loc_1800D27EF
0x1800d26bf  movzx   eax, [rsp+140h+UnicodeString.Length]
0x1800d26c4  xorps   xmm0, xmm0
0x1800d26c7  movups  xmmword ptr [rsp+140h+Destination.Length], xmm0
0x1800d26cc  add     ax, 32h ; '2'
0x1800d26d0  xor     edx, edx; Flags
0x1800d26d2  movzx   r8d, ax; Size
0x1800d26d6  mov     [rsp+140h+Destination.MaximumLength], r8w
0x1800d26dc  mov     rcx, gs:60h
0x1800d26e5  mov     rcx, [rcx+30h]; HeapHandle
0x1800d26e9  call    cs:__imp_RtlAllocateHeap
0x1800d26f0  nop     dword ptr [rax+rax+00h]
0x1800d26f5  mov     [rsp+140h+Destination.Buffer], rax
0x1800d26fa  test    rax, rax
0x1800d26fd  jz      loc_1800D2836
0x1800d2703  xorps   xmm0, xmm0
0x1800d2706  lea     rdx, aRegistryUser_0; "\\Registry\\User\\"
0x1800d270d  lea     rcx, [rsp+140h+DestinationString]; DestinationString
0x1800d2712  movups  xmmword ptr [rsp+140h+DestinationString.Length], xmm0
0x1800d2717  call    cs:__imp_RtlInitUnicodeStringEx
0x1800d271e  nop     dword ptr [rax+rax+00h]
0x1800d2723  mov     ebx, eax
0x1800d2725  test    eax, eax
0x1800d2727  js      loc_1800D27BE
0x1800d272d  lea     rdx, [rsp+140h+DestinationString]; SourceString
0x1800d2732  lea     rcx, [rsp+140h+Destination]; DestinationString
0x1800d2737  call    cs:__imp_RtlCopyUnicodeString
0x1800d273e  nop     dword ptr [rax+rax+00h]
0x1800d2743  lea     rdx, [rsp+140h+UnicodeString]; Source
0x1800d2748  lea     rcx, [rsp+140h+Destination]; Destination
0x1800d274d  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800d2754  nop     dword ptr [rax+rax+00h]
0x1800d2759  mov     ebx, eax
0x1800d275b  test    eax, eax
0x1800d275d  js      short loc_1800D27BE
0x1800d275f  lea     rdx, aClasses_0; "_Classes"
0x1800d2766  lea     rcx, [rsp+140h+Destination]; Destination
0x1800d276b  call    cs:__imp_RtlAppendUnicodeToString
0x1800d2772  nop     dword ptr [rax+rax+00h]
0x1800d2777  mov     ebx, eax
0x1800d2779  test    eax, eax
0x1800d277b  js      short loc_1800D27BE
0x1800d277d  lea     rax, [rsp+140h+Destination]
0x1800d2782  mov     qword ptr [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x1800d278b  xorps   xmm0, xmm0
0x1800d278e  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x1800d2793  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x1800d2798  mov     qword ptr [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x1800d27a0  mov     edx, r14d; DesiredAccess
0x1800d27a3  mov     [rsp+140h+ObjectAttributes.RootDirectory], r15
0x1800d27a8  mov     rcx, rdi; KeyHandle
0x1800d27ab  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d27b0  call    cs:__imp_NtOpenKey
0x1800d27b7  nop     dword ptr [rax+rax+00h]
0x1800d27bc  mov     ebx, eax
0x1800d27be  mov     rcx, gs:60h
0x1800d27c7  xor     edx, edx; Flags
0x1800d27c9  mov     r8, [rsp+140h+Destination.Buffer]; P
0x1800d27ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800d27d2  call    cs:__imp_RtlFreeHeap
0x1800d27d9  nop     dword ptr [rax+rax+00h]
0x1800d27de  lea     rcx, [rsp+140h+UnicodeString]; UnicodeString
0x1800d27e3  call    cs:__imp_RtlFreeUnicodeString
0x1800d27ea  nop     dword ptr [rax+rax+00h]
0x1800d27ef  lea     rax, [rbp+40h+TokenInformation]
0x1800d27f3  cmp     rsi, rax
0x1800d27f6  jnz     loc_1800D28DC
0x1800d27fc  test    ebx, ebx
0x1800d27fe  js      short loc_1800D2804
0x1800d2800  or      qword ptr [rdi], 2
0x1800d2804  mov     ecx, ebx; Status
0x1800d2806  call    cs:__imp_RtlNtStatusToDosError
0x1800d280d  nop     dword ptr [rax+rax+00h]
0x1800d2812  mov     rsi, [rsp+140h+arg_8]
0x1800d281a  mov     rcx, [rbp+40h+var_30]
0x1800d281e  xor     rcx, rsp; StackCookie
0x1800d2821  call    __security_check_cookie
0x1800d2826  add     rsp, 120h
0x1800d282d  pop     r15
0x1800d282f  pop     r14
0x1800d2831  pop     rdi
0x1800d2832  pop     rbx
0x1800d2833  pop     rbp
0x1800d2834  retn
0x1800d2836  mov     ebx, 0C0000017h
0x1800d283b  jmp     short loc_1800D27DE
0x1800d283d  mov     eax, 57h ; 'W'
0x1800d2842  jmp     short loc_1800D281A
0x1800d2844  mov     ecx, eax; Status
0x1800d2846  call    cs:__imp_RtlNtStatusToDosError
0x1800d284d  nop     dword ptr [rax+rax+00h]
0x1800d2852  cmp     eax, 7Ah ; 'z'
0x1800d2855  jnz     short loc_1800D2812
0x1800d2857  mov     rcx, gs:60h
0x1800d2860  xor     edx, edx; Flags
0x1800d2862  mov     r8d, [rsp+140h+TokenInformationLength]; Size
0x1800d2867  mov     rcx, [rcx+30h]; HeapHandle
0x1800d286b  call    cs:__imp_RtlAllocateHeap
0x1800d2872  nop     dword ptr [rax+rax+00h]
0x1800d2877  mov     rsi, rax
0x1800d287a  test    rax, rax
0x1800d287d  jz      short loc_1800D28D2
0x1800d287f  mov     r9d, [rsp+140h+TokenInformationLength]; TokenInformationLength
0x1800d2884  lea     rax, [rsp+140h+TokenInformationLength]
0x1800d2889  mov     r8, rsi; TokenInformation
0x1800d288c  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x1800d2891  mov     edx, 1; TokenInformationClass
0x1800d2896  mov     rcx, rbx; TokenHandle
0x1800d2899  call    cs:__imp_NtQueryInformationToken
0x1800d28a0  nop     dword ptr [rax+rax+00h]
0x1800d28a5  mov     ebx, eax
0x1800d28a7  test    eax, eax
0x1800d28a9  jns     loc_1800D269E
0x1800d28af  mov     rcx, gs:60h
0x1800d28b8  mov     r8, rsi; P
0x1800d28bb  xor     edx, edx; Flags
0x1800d28bd  mov     rcx, [rcx+30h]; HeapHandle
0x1800d28c1  call    cs:__imp_RtlFreeHeap
0x1800d28c8  nop     dword ptr [rax+rax+00h]
0x1800d28cd  jmp     loc_1800D2804
0x1800d28d2  mov     eax, 8
0x1800d28d7  jmp     loc_1800D2812
0x1800d28dc  mov     rcx, gs:60h
0x1800d28e5  mov     r8, rsi; P
0x1800d28e8  xor     edx, edx; Flags
0x1800d28ea  mov     rcx, [rcx+30h]; HeapHandle
0x1800d28ee  call    cs:__imp_RtlFreeHeap
0x1800d28f5  nop     dword ptr [rax+rax+00h]
0x1800d28fa  jmp     loc_1800D27FC
```
