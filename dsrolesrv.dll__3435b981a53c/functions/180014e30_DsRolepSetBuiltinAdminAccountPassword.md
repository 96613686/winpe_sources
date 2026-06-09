# DsRolepSetBuiltinAdminAccountPassword

- ea: `0x180014e30`
- end: `0x180014fff`
- name: `DsRolepSetBuiltinAdminAccountPassword`
- size: `463`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005400`

## callees

- `0x180014e30`
- `0x18002c01e`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180014fee`
- `ntdll!RtlNtStatusToDosError` at `0x180014fee`
- `ntdll!RtlInitUnicodeString` at `0x180014f82`
- `ntdll!RtlInitUnicodeString` at `0x180014f82`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180014ee9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180014ee9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180014eda`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180014eda`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180014fe6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180014fe6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180014eb9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180014eb9`
- `SAMLIB!SamCloseHandle` at `0x180014fc3`
- `SAMLIB!SamCloseHandle` at `0x180014fd0`
- `SAMLIB!SamCloseHandle` at `0x180014fdb`
- `SAMLIB!SamCloseHandle` at `0x180014fc3`
- `SAMLIB!SamCloseHandle` at `0x180014fd0`
- `SAMLIB!SamCloseHandle` at `0x180014fdb`
- `SAMLIB!SamOpenUser` at `0x180014f5c`
- `SAMLIB!SamOpenUser` at `0x180014f5c`
- `SAMLIB!SamSetInformationUser` at `0x180014fb4`
- `SAMLIB!SamSetInformationUser` at `0x180014fb4`
- `SAMLIB!SamOpenDomain` at `0x180014f33`
- `SAMLIB!SamOpenDomain` at `0x180014f33`
- `SAMLIB!SamConnect` at `0x180014f09`
- `SAMLIB!SamConnect` at `0x180014f09`

## pseudocode

```c
ULONG __fastcall DsRolepSetBuiltinAdminAccountPassword(PCWSTR SourceString)
{
  int v2; // ebx
  __int64 v4; // [rsp+20h] [rbp-E0h] BYREF
  PVOID Buffer; // [rsp+28h] [rbp-D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v8[224]; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v9; // [rsp+150h] [rbp+50h]
  int v10; // [rsp+18Ch] [rbp+8Ch]
  char v11; // [rsp+1A9h] [rbp+A9h]
  PVOID PolicyHandle; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v13; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v14; // [rsp+1E8h] [rbp+E8h] BYREF

  v4 = 0;
  v14 = 0;
  v13 = 0;
  Buffer = 0;
  PolicyHandle = 0;
  memset_0(v8, 0, 0x13Cu);
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v2 >= 0 )
  {
    v2 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    LsaClose(PolicyHandle);
    if ( v2 >= 0 )
    {
      v2 = SamConnect(0, &v4, 0x2000000, &ObjectAttributes);
      if ( v2 >= 0 )
      {
        v2 = SamOpenDomain(v4, 0x2000000, *((_QWORD *)Buffer + 2), &v14);
        if ( v2 >= 0 )
        {
          v2 = SamOpenUser(v14, 0x2000000, 500, &v13);
          if ( v2 >= 0 )
          {
            memset_0(v8, 0, 0x13Cu);
            RtlInitUnicodeString(&DestinationString, SourceString);
            v11 = 1;
            v9 = DestinationString;
            v10 = 0x1000000;
            v2 = SamSetInformationUser(v13, 21, v8);
            SamCloseHandle(v13);
          }
          SamCloseHandle(v14);
        }
        SamCloseHandle(v4);
      }
      LsaFreeMemory(Buffer);
    }
  }
  return RtlNtStatusToDosError(v2);
}

```

## disassembly

```asm
0x180014e30  push    rbp
0x180014e32  push    rbx
0x180014e33  push    rdi
0x180014e34  lea     rbp, [rsp-0B0h]
0x180014e3c  sub     rsp, 1B0h
0x180014e43  mov     rdi, rcx
0x180014e46  mov     [rsp+1C0h+var_1A0], 0
0x180014e4f  lea     rcx, [rsp+1C0h+var_150]; void *
0x180014e54  mov     [rbp+0C0h+arg_18], 0
0x180014e5f  xor     edx, edx; Val
0x180014e61  mov     [rbp+0C0h+arg_10], 0
0x180014e6c  mov     r8d, 13Ch; Size
0x180014e72  mov     [rsp+1C0h+Buffer], 0
0x180014e7b  mov     [rbp+0C0h+PolicyHandle], 0
0x180014e86  call    memset_0
0x180014e8b  xorps   xmm1, xmm1
0x180014e8e  lea     r9, [rbp+0C0h+PolicyHandle]; PolicyHandle
0x180014e95  xorps   xmm0, xmm0
0x180014e98  lea     rdx, [rsp+1C0h+ObjectAttributes]; ObjectAttributes
0x180014e9d  mov     r8d, 1; DesiredAccess
0x180014ea3  xor     ecx, ecx; SystemName
0x180014ea5  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x180014eaa  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.Length], xmm1
0x180014eaf  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.ObjectName], xmm1
0x180014eb4  movups  xmmword ptr [rsp+1C0h+ObjectAttributes.SecurityDescriptor], xmm1
0x180014eb9  call    cs:__imp_LsaOpenPolicy
0x180014ebf  mov     ebx, eax
0x180014ec1  test    eax, eax
0x180014ec3  js      loc_180014FEC
0x180014ec9  mov     rcx, [rbp+0C0h+PolicyHandle]; PolicyHandle
0x180014ed0  lea     r8, [rsp+1C0h+Buffer]; Buffer
0x180014ed5  mov     edx, 5; InformationClass
0x180014eda  call    cs:__imp_LsaQueryInformationPolicy
0x180014ee0  mov     rcx, [rbp+0C0h+PolicyHandle]; ObjectHandle
0x180014ee7  mov     ebx, eax
0x180014ee9  call    cs:__imp_LsaClose
0x180014eef  test    ebx, ebx
0x180014ef1  js      loc_180014FEC
0x180014ef7  lea     r9, [rsp+1C0h+ObjectAttributes]
0x180014efc  mov     r8d, 2000000h
0x180014f02  lea     rdx, [rsp+1C0h+var_1A0]
0x180014f07  xor     ecx, ecx
0x180014f09  call    cs:__imp_SamConnect
0x180014f0f  mov     ebx, eax
0x180014f11  test    eax, eax
0x180014f13  js      loc_180014FE1
0x180014f19  mov     r8, [rsp+1C0h+Buffer]
0x180014f1e  lea     r9, [rbp+0C0h+arg_18]
0x180014f25  mov     rcx, [rsp+1C0h+var_1A0]
0x180014f2a  mov     edx, 2000000h
0x180014f2f  mov     r8, [r8+10h]
0x180014f33  call    cs:__imp_SamOpenDomain
0x180014f39  mov     ebx, eax
0x180014f3b  test    eax, eax
0x180014f3d  js      loc_180014FD6
0x180014f43  mov     rcx, [rbp+0C0h+arg_18]
0x180014f4a  lea     r9, [rbp+0C0h+arg_10]
0x180014f51  mov     edx, 2000000h
0x180014f56  mov     r8d, 1F4h
0x180014f5c  call    cs:__imp_SamOpenUser
0x180014f62  mov     ebx, eax
0x180014f64  test    eax, eax
0x180014f66  js      short loc_180014FC9
0x180014f68  xor     edx, edx; Val
0x180014f6a  lea     rcx, [rsp+1C0h+var_150]; void *
0x180014f6f  mov     r8d, 13Ch; Size
0x180014f75  call    memset_0
0x180014f7a  mov     rdx, rdi; SourceString
0x180014f7d  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x180014f82  call    cs:__imp_RtlInitUnicodeString
0x180014f88  movups  xmm0, xmmword ptr [rsp+1C0h+DestinationString.Length]
0x180014f8d  mov     rcx, [rbp+0C0h+arg_10]
0x180014f94  lea     r8, [rsp+1C0h+var_150]
0x180014f99  mov     edx, 15h
0x180014f9e  mov     [rbp+0C0h+var_17], 1
0x180014fa5  movdqu  [rbp+0C0h+var_70], xmm0
0x180014faa  mov     [rbp+0C0h+var_34], 1000000h
0x180014fb4  call    cs:__imp_SamSetInformationUser
0x180014fba  mov     rcx, [rbp+0C0h+arg_10]
0x180014fc1  mov     ebx, eax
0x180014fc3  call    cs:__imp_SamCloseHandle
0x180014fc9  mov     rcx, [rbp+0C0h+arg_18]
0x180014fd0  call    cs:__imp_SamCloseHandle
0x180014fd6  mov     rcx, [rsp+1C0h+var_1A0]
0x180014fdb  call    cs:__imp_SamCloseHandle
0x180014fe1  mov     rcx, [rsp+1C0h+Buffer]; Buffer
0x180014fe6  call    cs:__imp_LsaFreeMemory
0x180014fec  mov     ecx, ebx; Status
0x180014fee  call    cs:__imp_RtlNtStatusToDosError
0x180014ff4  add     rsp, 1B0h
0x180014ffb  pop     rdi
0x180014ffc  pop     rbx
0x180014ffd  pop     rbp
0x180014ffe  retn
```
