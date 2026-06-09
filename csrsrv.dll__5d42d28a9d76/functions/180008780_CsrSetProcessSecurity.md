# CsrSetProcessSecurity

- ea: `0x180008780`
- end: `0x180008989`
- name: `CsrSetProcessSecurity`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004a20`

## callees

- `0x1800035c0`
- `0x180008780`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800087ab`
- `ntdll!RtlAllocateHeap` at `0x18000883f`
- `ntdll!RtlAllocateHeap` at `0x1800087ab`
- `ntdll!RtlAllocateHeap` at `0x18000883f`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800088f2`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800088f2`
- `ntdll!NtQueryInformationToken` at `0x1800087eb`
- `ntdll!NtQueryInformationToken` at `0x1800087eb`
- `ntdll!NtSetSecurityObject` at `0x18000891a`
- `ntdll!NtSetSecurityObject` at `0x18000891a`
- `ntdll!RtlLengthSid` at `0x18000880e`
- `ntdll!RtlLengthSid` at `0x18000880e`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800088cd`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800088cd`
- `ntdll!RtlFreeHeap` at `0x180008951`
- `ntdll!RtlFreeHeap` at `0x180008973`
- `ntdll!RtlFreeHeap` at `0x180008951`
- `ntdll!RtlFreeHeap` at `0x180008973`
- `ntdll!RtlCreateAcl` at `0x1800088a2`
- `ntdll!RtlCreateAcl` at `0x1800088a2`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180008865`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180008865`

## string_xrefs

- `0x18000887a`: `CsrSetProcessSecurity`
- `0x180008934`: `CsrSetProcessSecurity`

## pseudocode

```c
__int64 CsrSetProcessSecurity()
{
  PSID *Heap; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  ULONG v3; // eax
  ULONG v4; // r14d
  struct _ACL *v5; // rax
  struct _ACL *v6; // rsi
  ULONG ReturnLength; // [rsp+50h] [rbp+8h] BYREF

  ReturnLength = 0;
  Heap = (PSID *)RtlAllocateHeap(CsrHeap, (CsrBaseTag + 1310720) | 8, 0x54u);
  if ( !Heap )
    return 3221225495LL;
  SecurityDescriptor = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, Heap, 0x54u, &ReturnLength);
  if ( SecurityDescriptor >= 0 )
  {
    v3 = RtlLengthSid(*Heap);
    v4 = v3 + 20;
    ReturnLength = v3 + 60;
    v5 = (struct _ACL *)RtlAllocateHeap(CsrHeap, (CsrBaseTag + 1310720) | 8, v3 + 60);
    v6 = v5;
    if ( v5 )
    {
      SecurityDescriptor = RtlCreateSecurityDescriptor(v5, 1u);
      if ( SecurityDescriptor < 0
        || (SecurityDescriptor = RtlCreateAcl(v6 + 5, v4, 2u), SecurityDescriptor < 0)
        || (SecurityDescriptor = RtlAddAccessAllowedAce(v6 + 5, 2u, 0x20C79u, *Heap), SecurityDescriptor < 0)
        || (SecurityDescriptor = RtlSetDaclSecurityDescriptor(v6, 1u, v6 + 5, 0), SecurityDescriptor < 0)
        || (SecurityDescriptor = NtSetSecurityObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, 4u, v6), SecurityDescriptor < 0) )
      {
        CsrpLogFailure("CsrSetProcessSecurity");
      }
      RtlFreeHeap(CsrHeap, 0, v6);
    }
    else
    {
      SecurityDescriptor = -1073741801;
    }
  }
  RtlFreeHeap(CsrHeap, 0, Heap);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x180008780  push    rbx
0x180008782  push    rdi
0x180008783  sub     rsp, 38h
0x180008787  mov     edx, cs:CsrBaseTag
0x18000878d  mov     r8d, 54h ; 'T'; Size
0x180008793  mov     rcx, cs:CsrHeap; HeapHandle
0x18000879a  add     edx, 140000h
0x1800087a0  or      edx, 8; Flags
0x1800087a3  mov     [rsp+48h+arg_0], 0
0x1800087ab  call    cs:__imp_RtlAllocateHeap
0x1800087b2  nop     dword ptr [rax+rax+00h]
0x1800087b7  mov     rdi, rax
0x1800087ba  test    rax, rax
0x1800087bd  jnz     short loc_1800087CC
0x1800087bf  mov     eax, 0C0000017h
0x1800087c4  add     rsp, 38h
0x1800087c8  pop     rdi
0x1800087c9  pop     rbx
0x1800087ca  retn
0x1800087cc  lea     rax, [rsp+48h+arg_0]
0x1800087d1  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800087d7  mov     r8, rdi; TokenInformation
0x1800087da  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800087df  mov     edx, 1; TokenInformationClass
0x1800087e4  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x1800087eb  call    cs:__imp_NtQueryInformationToken
0x1800087f2  nop     dword ptr [rax+rax+00h]
0x1800087f7  mov     ebx, eax
0x1800087f9  test    eax, eax
0x1800087fb  js      loc_180008967
0x180008801  mov     rcx, [rdi]; Sid
0x180008804  mov     [rsp+48h+arg_10], rsi
0x180008809  mov     [rsp+48h+var_18], r14
0x18000880e  call    cs:__imp_RtlLengthSid
0x180008815  nop     dword ptr [rax+rax+00h]
0x18000881a  mov     edx, cs:CsrBaseTag
0x180008820  mov     rcx, cs:CsrHeap; HeapHandle
0x180008827  add     edx, 140000h
0x18000882d  or      edx, 8; Flags
0x180008830  lea     r14d, [rax+14h]
0x180008834  lea     eax, [r14+28h]
0x180008838  mov     r8d, eax; Size
0x18000883b  mov     [rsp+48h+arg_0], eax
0x18000883f  call    cs:__imp_RtlAllocateHeap
0x180008846  nop     dword ptr [rax+rax+00h]
0x18000884b  mov     rsi, rax
0x18000884e  test    rax, rax
0x180008851  jnz     short loc_18000885D
0x180008853  mov     ebx, 0C0000017h
0x180008858  jmp     loc_18000895D
0x18000885d  mov     edx, 1; Revision
0x180008862  mov     rcx, rsi; SecurityDescriptor
0x180008865  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000886c  nop     dword ptr [rax+rax+00h]
0x180008871  mov     ebx, eax
0x180008873  test    eax, eax
0x180008875  jns     short loc_180008890
0x180008877  mov     r8d, eax
0x18000887a  lea     rcx, aCsrsetprocesss; "CsrSetProcessSecurity"
0x180008881  mov     edx, 453h
0x180008886  call    CsrpLogFailure
0x18000888b  jmp     loc_180008945
0x180008890  mov     r8d, 2; AclRevision
0x180008896  mov     [rsp+48h+arg_8], rbp
0x18000889b  mov     edx, r14d; AclLength
0x18000889e  lea     rcx, [rsi+28h]; Acl
0x1800088a2  call    cs:__imp_RtlCreateAcl
0x1800088a9  nop     dword ptr [rax+rax+00h]
0x1800088ae  mov     ebx, eax
0x1800088b0  test    eax, eax
0x1800088b2  jns     short loc_1800088BB
0x1800088b4  mov     edx, 45Fh
0x1800088b9  jmp     short loc_180008931
0x1800088bb  mov     r9, [rdi]; Sid
0x1800088be  lea     rcx, [rsi+28h]; Acl
0x1800088c2  mov     edx, 2; AceRevision
0x1800088c7  mov     r8d, 20C79h; AccessMask
0x1800088cd  call    cs:__imp_RtlAddAccessAllowedAce
0x1800088d4  nop     dword ptr [rax+rax+00h]
0x1800088d9  mov     ebx, eax
0x1800088db  test    eax, eax
0x1800088dd  jns     short loc_1800088E6
0x1800088df  mov     edx, 477h
0x1800088e4  jmp     short loc_180008931
0x1800088e6  xor     r9d, r9d; DaclDefaulted
0x1800088e9  lea     r8, [rsi+28h]; Dacl
0x1800088ed  mov     dl, 1; DaclPresent
0x1800088ef  mov     rcx, rsi; SecurityDescriptor
0x1800088f2  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800088f9  nop     dword ptr [rax+rax+00h]
0x1800088fe  mov     ebx, eax
0x180008900  test    eax, eax
0x180008902  jns     short loc_18000890B
0x180008904  mov     edx, 487h
0x180008909  jmp     short loc_180008931
0x18000890b  mov     r8, rsi; SecurityDescriptor
0x18000890e  mov     edx, 4; SecurityInformation
0x180008913  mov     rcx, 0FFFFFFFFFFFFFFFFh; Handle
0x18000891a  call    cs:__imp_NtSetSecurityObject
0x180008921  nop     dword ptr [rax+rax+00h]
0x180008926  mov     ebx, eax
0x180008928  test    eax, eax
0x18000892a  jns     short loc_180008940
0x18000892c  mov     edx, 496h
0x180008931  mov     r8d, eax
0x180008934  lea     rcx, aCsrsetprocesss; "CsrSetProcessSecurity"
0x18000893b  call    CsrpLogFailure
0x180008940  mov     rbp, [rsp+48h+arg_8]
0x180008945  mov     rcx, cs:CsrHeap; HeapHandle
0x18000894c  mov     r8, rsi; BaseAddress
0x18000894f  xor     edx, edx; Flags
0x180008951  call    cs:__imp_RtlFreeHeap
0x180008958  nop     dword ptr [rax+rax+00h]
0x18000895d  mov     rsi, [rsp+48h+arg_10]
0x180008962  mov     r14, [rsp+48h+var_18]
0x180008967  mov     rcx, cs:CsrHeap; HeapHandle
0x18000896e  mov     r8, rdi; BaseAddress
0x180008971  xor     edx, edx; Flags
0x180008973  call    cs:__imp_RtlFreeHeap
0x18000897a  nop     dword ptr [rax+rax+00h]
0x18000897f  mov     eax, ebx
0x180008981  add     rsp, 38h
0x180008985  pop     rdi
0x180008986  pop     rbx
0x180008987  retn
```
