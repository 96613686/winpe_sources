# DsRolepSetLsaDomainPolicyInfo

- ea: `0x18002276c`
- end: `0x180022892`
- name: `DsRolepSetLsaDomainPolicyInfo`
- size: `294`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, PCWSTR@<rdx>, PCWSTR@<r8>, __int64, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x180020dbc`
- `0x18002276c`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180022838`
- `ntdll!RtlNtStatusToDosError` at `0x180022844`
- `ntdll!RtlNtStatusToDosError` at `0x180022870`
- `ntdll!RtlNtStatusToDosError` at `0x180022838`
- `ntdll!RtlNtStatusToDosError` at `0x180022844`
- `ntdll!RtlNtStatusToDosError` at `0x180022870`
- `ntdll!RtlInitUnicodeString` at `0x1800227f3`
- `ntdll!RtlInitUnicodeString` at `0x180022800`
- `ntdll!RtlInitUnicodeString` at `0x18002280d`
- `ntdll!RtlInitUnicodeString` at `0x1800227f3`
- `ntdll!RtlInitUnicodeString` at `0x180022800`
- `ntdll!RtlInitUnicodeString` at `0x18002280d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180022868`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180022868`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800227e6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800227e6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x18002282e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x18002282e`

## pseudocode

```c
ULONG __fastcall DsRolepSetLsaDomainPolicyInfo(
        PCWSTR SourceString,
        PCWSTR a2,
        PCWSTR a3,
        __int128 *a4,
        __int64 a5,
        char a6)
{
  __int128 v11; // xmm0
  NTSTATUS v12; // ebx
  ULONG v13; // eax
  PVOID PolicyHandle; // [rsp+20h] [rbp-89h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+28h] [rbp-81h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING v17; // [rsp+70h] [rbp-39h] BYREF
  struct _UNICODE_STRING v18; // [rsp+80h] [rbp-29h] BYREF
  __int128 v19; // [rsp+90h] [rbp-19h]
  __int64 v20; // [rsp+A0h] [rbp-9h]

  memset_0(&DestinationString, 0, 0x48u);
  PolicyHandle = 0;
  if ( (a6 & 4) != 0 )
    return 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  LsaOpenPolicy(0, &ObjectAttributes, 0x207F8u, &PolicyHandle);
  RtlInitUnicodeString(&DestinationString, a2);
  RtlInitUnicodeString(&v17, SourceString);
  RtlInitUnicodeString(&v18, a3);
  v11 = *a4;
  v20 = a5;
  v19 = v11;
  v12 = LsaSetInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &DestinationString);
  if ( RtlNtStatusToDosError(v12) )
  {
    v13 = RtlNtStatusToDosError(v12);
    DsRolepLogPrintRoutine(4, "Setting DnsDomainInformation failed with 0x%lx\n", v13);
  }
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return RtlNtStatusToDosError(v12);
}

```

## disassembly

```asm
0x18002276c  push    rbp
0x18002276e  push    rbx
0x18002276f  push    rsi
0x180022770  push    rdi
0x180022771  push    r14
0x180022773  push    r15
0x180022775  lea     rbp, [rsp-1Fh]
0x18002277a  sub     rsp, 0C8h
0x180022781  mov     rax, cs:__security_cookie
0x180022788  xor     rax, rsp
0x18002278b  mov     [rbp+47h+var_40], rax
0x18002278f  mov     r15, [rbp+47h+arg_20]
0x180022793  mov     rdi, rdx
0x180022796  xor     edx, edx; Val
0x180022798  mov     rsi, r8
0x18002279b  mov     rbx, rcx
0x18002279e  mov     r14, r9
0x1800227a1  lea     rcx, [rbp+47h+DestinationString]; void *
0x1800227a5  lea     r8d, [rdx+48h]; Size
0x1800227a9  call    memset_0
0x1800227ae  test    [rbp+47h+arg_28], 4
0x1800227b2  mov     [rsp+0F0h+PolicyHandle], 0
0x1800227bb  jz      short loc_1800227C4
0x1800227bd  xor     eax, eax
0x1800227bf  jmp     loc_180022876
0x1800227c4  xorps   xmm0, xmm0
0x1800227c7  lea     r9, [rsp+0F0h+PolicyHandle]; PolicyHandle
0x1800227cc  mov     r8d, 207F8h; DesiredAccess
0x1800227d2  lea     rdx, [rsp+0F0h+ObjectAttributes]; ObjectAttributes
0x1800227d7  xor     ecx, ecx; SystemName
0x1800227d9  movups  xmmword ptr [rsp+0F0h+ObjectAttributes.Length], xmm0
0x1800227de  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x1800227e2  movups  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800227e6  call    cs:__imp_LsaOpenPolicy
0x1800227ec  mov     rdx, rdi; SourceString
0x1800227ef  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1800227f3  call    cs:__imp_RtlInitUnicodeString
0x1800227f9  mov     rdx, rbx; SourceString
0x1800227fc  lea     rcx, [rbp+47h+var_80]; DestinationString
0x180022800  call    cs:__imp_RtlInitUnicodeString
0x180022806  mov     rdx, rsi; SourceString
0x180022809  lea     rcx, [rbp+47h+var_70]; DestinationString
0x18002280d  call    cs:__imp_RtlInitUnicodeString
0x180022813  movups  xmm0, xmmword ptr [r14]
0x180022817  mov     rcx, [rsp+0F0h+PolicyHandle]; PolicyHandle
0x18002281c  lea     r8, [rbp+47h+DestinationString]; Buffer
0x180022820  mov     edx, 0Ch; InformationClass
0x180022825  mov     [rbp+47h+var_50], r15
0x180022829  movdqu  [rbp+47h+var_60], xmm0
0x18002282e  call    cs:__imp_LsaSetInformationPolicy
0x180022834  mov     ecx, eax; Status
0x180022836  mov     ebx, eax
0x180022838  call    cs:__imp_RtlNtStatusToDosError
0x18002283e  test    eax, eax
0x180022840  jz      short loc_18002285E
0x180022842  mov     ecx, ebx; Status
0x180022844  call    cs:__imp_RtlNtStatusToDosError
0x18002284a  lea     rdx, aSettingDnsdoma; "Setting DnsDomainInformation failed wit"...
0x180022851  mov     ecx, 4
0x180022856  mov     r8d, eax
0x180022859  call    DsRolepLogPrintRoutine
0x18002285e  mov     rcx, [rsp+0F0h+PolicyHandle]; ObjectHandle
0x180022863  test    rcx, rcx
0x180022866  jz      short loc_18002286E
0x180022868  call    cs:__imp_LsaClose
0x18002286e  mov     ecx, ebx; Status
0x180022870  call    cs:__imp_RtlNtStatusToDosError
0x180022876  mov     rcx, [rbp+47h+var_40]
0x18002287a  xor     rcx, rsp; StackCookie
0x18002287d  call    __security_check_cookie
0x180022882  add     rsp, 0C8h
0x180022889  pop     r15
0x18002288b  pop     r14
0x18002288d  pop     rdi
0x18002288e  pop     rsi
0x18002288f  pop     rbx
0x180022890  pop     rbp
0x180022891  retn
```
