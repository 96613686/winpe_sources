# IkeLoadSaDbSecurity

- ea: `0x180003a08`
- end: `0x180003b89`
- name: `IkeLoadSaDbSecurity`
- size: `385`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003848`

## callees

- `0x180001ba8`
- `0x1800037c4`
- `0x180003a08`
- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180050850`
- `0x1800ecb24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b16`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180003aa5`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180003aa5`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180003b0c`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180003b0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b45`

## string_xrefs

- `0x180003a3f`: `IkeLoadSaDbSecurity`
- `0x180003ab5`: `IkeLoadSaDbSecurity`
- `0x180003b4d`: `IkeLoadSaDbSecurity`
- `0x180003b59`: `IkeLoadSaDbSecurity`
- `0x180003a78`: `IkeLookupRpcSdRegConfig`
- `0x180003b1f`: `CreatePrivateObjectSecurityEx`

## pseudocode

```c
__int64 __fastcall IkeLoadSaDbSecurity(PSECURITY_DESCRIPTOR *NewDescriptor)
{
  int v2; // esi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rbx
  PSECURITY_DESCRIPTOR v9; // rdi
  __int64 v10; // rcx
  __int64 LastError; // r8
  const char *v12; // rdx
  int v14; // [rsp+40h] [rbp-20h] BYREF
  ULONG SecurityDescriptorLength; // [rsp+44h] [rbp-1Ch] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptorInput; // [rsp+48h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-10h] BYREF

  SecurityDescriptorLength = 0;
  v2 = 0;
  SecurityDescriptorInput = 0;
  v14 = 0;
  hMem = 0;
  TraceLogHelper("IkeLoadSaDbSecurity", 1);
  v6 = WfpRegQueryBinary(v4, v3, v5, &SecurityDescriptorLength, (LPBYTE *)&SecurityDescriptorInput, &v14);
  v8 = IkeReturnError(v6, "IkeLookupRpcSdRegConfig");
  if ( !v8 )
  {
    if ( v14 )
    {
      v9 = SecurityDescriptorInput;
      if ( !RtlValidRelativeSecurityDescriptor(SecurityDescriptorInput, SecurityDescriptorLength, 0) )
      {
        LastError = 1338;
        v12 = "IkeLoadSaDbSecurity";
LABEL_10:
        v8 = WfpReportSysErrorAsWinError(v10, v12, LastError, 1);
        goto LABEL_11;
      }
      hMem = v9;
    }
    else
    {
      v8 = IkeSecurityDescriptorCreateFromSddl(v7, &hMem);
      if ( v8 )
        goto LABEL_11;
      v9 = hMem;
      v2 = 1;
    }
    if ( CreatePrivateObjectSecurityEx(0, v9, NewDescriptor, 0, 0, 0x18u, 0, (PGENERIC_MAPPING)&IKE_GENERIC_MAPPING) )
      goto LABEL_11;
    LastError = GetLastError();
    v12 = "CreatePrivateObjectSecurityEx";
    goto LABEL_10;
  }
LABEL_11:
  WfpMemFree((LPCVOID *)&SecurityDescriptorInput);
  if ( v2 )
    LocalFree(hMem);
  TraceLogHelper("IkeLoadSaDbSecurity", 0);
  return IkeReturnError(v8, "IkeLoadSaDbSecurity");
}

```

## disassembly

```asm
0x180003a08  mov     [rsp-18h+arg_8], rbx
0x180003a0d  mov     [rsp-18h+arg_10], rsi
0x180003a12  push    rbp
0x180003a13  push    rdi
0x180003a14  push    r14
0x180003a16  mov     rbp, rsp
0x180003a19  sub     rsp, 60h
0x180003a1d  mov     rax, cs:__security_cookie
0x180003a24  xor     rax, rsp
0x180003a27  mov     [rbp+var_8], rax
0x180003a2b  mov     r14, rcx
0x180003a2e  mov     [rbp+SecurityDescriptorLength], 0
0x180003a35  xor     esi, esi
0x180003a37  mov     [rbp+SecurityDescriptorInput], 0
0x180003a3f  lea     rcx, aIkeloadsadbsec; "IkeLoadSaDbSecurity"
0x180003a46  mov     [rbp+var_20], 0
0x180003a4d  mov     [rbp+hMem], 0
0x180003a55  lea     edx, [rsi+1]
0x180003a58  call    TraceLogHelper
0x180003a5d  lea     rax, [rbp+var_20]
0x180003a61  mov     qword ptr [rsp+60h+AutoInheritFlags], rax
0x180003a66  lea     r9, [rbp+SecurityDescriptorLength]
0x180003a6a  lea     rax, [rbp+SecurityDescriptorInput]
0x180003a6e  mov     qword ptr [rsp+60h+IsContainerObject], rax
0x180003a73  call    WfpRegQueryBinary
0x180003a78  lea     rdx, aIkelookuprpcsd; "IkeLookupRpcSdRegConfig"
0x180003a7f  mov     rcx, rax
0x180003a82  call    IkeReturnError
0x180003a87  mov     rbx, rax
0x180003a8a  test    rax, rax
0x180003a8d  jnz     loc_180003B34
0x180003a93  cmp     [rbp+var_20], esi
0x180003a96  jz      short loc_180003AC4
0x180003a98  mov     rdi, [rbp+SecurityDescriptorInput]
0x180003a9c  xor     r8d, r8d; RequiredInformation
0x180003a9f  mov     edx, [rbp+SecurityDescriptorLength]; SecurityDescriptorLength
0x180003aa2  mov     rcx, rdi; SecurityDescriptorInput
0x180003aa5  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180003aab  test    al, al
0x180003aad  jnz     short loc_180003ABE
0x180003aaf  mov     r8d, 53Ah
0x180003ab5  lea     rdx, aIkeloadsadbsec; "IkeLoadSaDbSecurity"
0x180003abc  jmp     short loc_180003B26
0x180003abe  mov     [rbp+hMem], rdi
0x180003ac2  jmp     short loc_180003ADC
0x180003ac4  lea     rdx, [rbp+hMem]
0x180003ac8  call    IkeSecurityDescriptorCreateFromSddl
0x180003acd  mov     rbx, rax
0x180003ad0  test    rax, rax
0x180003ad3  jnz     short loc_180003B34
0x180003ad5  mov     rdi, [rbp+hMem]
0x180003ad9  lea     esi, [rax+1]
0x180003adc  lea     rax, IKE_GENERIC_MAPPING
0x180003ae3  xor     r9d, r9d; ObjectType
0x180003ae6  mov     [rsp+60h+GenericMapping], rax; GenericMapping
0x180003aeb  mov     r8, r14; NewDescriptor
0x180003aee  mov     [rsp+60h+Token], 0; Token
0x180003af7  mov     rdx, rdi; CreatorDescriptor
0x180003afa  mov     [rsp+60h+AutoInheritFlags], 18h; AutoInheritFlags
0x180003b02  xor     ecx, ecx; ParentDescriptor
0x180003b04  mov     [rsp+60h+IsContainerObject], 0; IsContainerObject
0x180003b0c  call    cs:__imp_CreatePrivateObjectSecurityEx
0x180003b12  test    eax, eax
0x180003b14  jnz     short loc_180003B34
0x180003b16  call    cs:__imp_GetLastError
0x180003b1c  mov     r8d, eax
0x180003b1f  lea     rdx, aCreateprivateo; "CreatePrivateObjectSecurityEx"
0x180003b26  mov     r9d, 1
0x180003b2c  call    WfpReportSysErrorAsWinError
0x180003b31  mov     rbx, rax
0x180003b34  lea     rcx, [rbp+SecurityDescriptorInput]
0x180003b38  call    WfpMemFree
0x180003b3d  test    esi, esi
0x180003b3f  jz      short loc_180003B4B
0x180003b41  mov     rcx, [rbp+hMem]; hMem
0x180003b45  call    cs:__imp_LocalFree
0x180003b4b  xor     edx, edx
0x180003b4d  lea     rcx, aIkeloadsadbsec; "IkeLoadSaDbSecurity"
0x180003b54  call    TraceLogHelper
0x180003b59  lea     rdx, aIkeloadsadbsec; "IkeLoadSaDbSecurity"
0x180003b60  mov     rcx, rbx
0x180003b63  call    IkeReturnError
0x180003b68  mov     rcx, [rbp+var_8]
0x180003b6c  xor     rcx, rsp; StackCookie
0x180003b6f  call    __security_check_cookie
0x180003b74  lea     r11, [rsp+60h+var_s0]
0x180003b79  mov     rbx, [r11+28h]
0x180003b7d  mov     rsi, [r11+30h]
0x180003b81  mov     rsp, r11
0x180003b84  pop     r14
0x180003b86  pop     rdi
0x180003b87  pop     rbp
0x180003b88  retn
```
