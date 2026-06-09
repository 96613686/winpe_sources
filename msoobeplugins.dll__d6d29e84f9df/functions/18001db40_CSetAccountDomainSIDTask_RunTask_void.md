# CSetAccountDomainSIDTask::RunTask(void)

- ea: `0x18001db40`
- end: `0x18001dce8`
- name: `?RunTask@CSetAccountDomainSIDTask@@UEAAJXZ`
- size: `424`
- prototype: `__int64 __fastcall(CSetAccountDomainSIDTask *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x18001db40`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001dbc9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001dbc9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001dbf3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001dc40`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001dbf3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001dc40`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x18001dc20`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x18001dc58`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x18001dc20`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaSetInformationPolicy` at `0x18001dc58`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001dc8c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001dc8c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001dca9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001dca9`
- `ntdll!RtlInitUnicodeString` at `0x18001dc0f`
- `ntdll!RtlInitUnicodeString` at `0x18001dc0f`

## string_xrefs

- `0x18001dc65`: `Commit: failed to save the DNS Domain information in the LSA [0x%08X]`
- `0x18001dc6e`: `Commit: failed to query the LSA for the DNS Domain information [0x%08X]`
- `0x18001dc77`: `Commit: failed to save the Account Domain info in the LSA [0x%08X]`
- `0x18001dc97`: `Commit: failed to query the LSA for the Account Domain information [0x%08X]`
- `0x18001dcb4`: `Commit: failed to open the LSA [0x%08X]`

## pseudocode

```c
__int64 __fastcall CSetAccountDomainSIDTask::RunTask(const WCHAR *this)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  NTSTATUS v7; // eax
  PVOID PolicyHandle; // [rsp+20h] [rbp-60h] BYREF
  PVOID Buffer; // [rsp+28h] [rbp-58h] BYREF
  PVOID v11; // [rsp+30h] [rbp-50h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-48h] BYREF
  _DWORD v13[4]; // [rsp+68h] [rbp-18h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v13[2] = 1;
  PolicyHandle = 0;
  v13[0] = 12;
  v13[1] = 2;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  ObjectAttributes.SecurityQualityOfService = v13;
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 9u, &PolicyHandle);
  v3 = v2 | 0x10000000;
  if ( v2 < 0 )
  {
    UnattendLogW(1, L"Commit: failed to open the LSA [0x%08X]", v3);
  }
  else
  {
    Buffer = 0;
    v4 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    v3 = v4 | 0x10000000;
    if ( v4 < 0 )
    {
      UnattendLogW(1, L"Commit: failed to query the LSA for the Account Domain information [0x%08X]", v3);
    }
    else
    {
      RtlInitUnicodeString((PUNICODE_STRING)Buffer, this + 276);
      v5 = LsaSetInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, Buffer);
      v3 = v5 | 0x10000000;
      if ( v5 < 0 )
      {
        UnattendLogW(1, L"Commit: failed to save the Account Domain info in the LSA [0x%08X]", v3);
      }
      else
      {
        v11 = 0;
        v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &v11);
        v3 = v6 | 0x10000000;
        if ( v6 < 0 )
        {
          UnattendLogW(1, L"Commit: failed to query the LSA for the DNS Domain information [0x%08X]", v3);
        }
        else
        {
          v7 = LsaSetInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, v11);
          v3 = v7 | 0x10000000;
          if ( v7 < 0 )
            UnattendLogW(1, L"Commit: failed to save the DNS Domain information in the LSA [0x%08X]", v3);
        }
      }
      LsaFreeMemory(Buffer);
    }
    LsaClose(PolicyHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x18001db40  mov     [rsp-18h+arg_8], rbx
0x18001db45  mov     [rsp-18h+arg_10], rsi
0x18001db4a  push    rbp
0x18001db4b  push    rdi
0x18001db4c  push    r15
0x18001db4e  mov     rbp, rsp
0x18001db51  sub     rsp, 80h
0x18001db58  mov     rax, cs:__security_cookie
0x18001db5f  xor     rax, rsp
0x18001db62  mov     [rbp+var_8], rax
0x18001db66  mov     rdi, rcx
0x18001db69  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001db71  lea     rax, [rbp+var_18]
0x18001db75  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18001db7d  mov     esi, 1
0x18001db82  mov     [rbp+var_10], 1
0x18001db89  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18001db8d  mov     [rbp+PolicyHandle], 0
0x18001db95  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18001db99  mov     [rbp+var_18], 0Ch
0x18001dba0  xor     ecx, ecx; SystemName
0x18001dba2  mov     [rbp+var_14], 2
0x18001dba9  lea     r8d, [rsi+8]; DesiredAccess
0x18001dbad  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001dbb5  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18001dbbd  mov     [rbp+ObjectAttributes.SecurityDescriptor], 0
0x18001dbc5  mov     [rbp+ObjectAttributes.SecurityQualityOfService], rax
0x18001dbc9  call    cs:__imp_LsaOpenPolicy
0x18001dbcf  mov     ebx, eax
0x18001dbd1  mov     r15d, 10000000h
0x18001dbd7  or      ebx, r15d
0x18001dbda  jl      loc_18001DCB1
0x18001dbe0  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18001dbe4  lea     r8, [rbp+Buffer]; Buffer
0x18001dbe8  lea     edx, [rsi+4]; InformationClass
0x18001dbeb  mov     [rbp+Buffer], 0
0x18001dbf3  call    cs:__imp_LsaQueryInformationPolicy
0x18001dbf9  mov     ebx, eax
0x18001dbfb  or      ebx, r15d
0x18001dbfe  jl      loc_18001DC94
0x18001dc04  mov     rcx, [rbp+Buffer]; DestinationString
0x18001dc08  lea     rdx, [rdi+228h]; SourceString
0x18001dc0f  call    cs:__imp_RtlInitUnicodeString
0x18001dc15  mov     r8, [rbp+Buffer]; Buffer
0x18001dc19  lea     edx, [rsi+4]; InformationClass
0x18001dc1c  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18001dc20  call    cs:__imp_LsaSetInformationPolicy
0x18001dc26  mov     ebx, eax
0x18001dc28  or      ebx, r15d
0x18001dc2b  jl      short loc_18001DC77
0x18001dc2d  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18001dc31  lea     r8, [rbp+var_50]; Buffer
0x18001dc35  lea     edx, [rsi+0Bh]; InformationClass
0x18001dc38  mov     [rbp+var_50], 0
0x18001dc40  call    cs:__imp_LsaQueryInformationPolicy
0x18001dc46  mov     ebx, eax
0x18001dc48  or      ebx, r15d
0x18001dc4b  jl      short loc_18001DC6E
0x18001dc4d  mov     r8, [rbp+var_50]; Buffer
0x18001dc51  lea     edx, [rsi+0Bh]; InformationClass
0x18001dc54  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18001dc58  call    cs:__imp_LsaSetInformationPolicy
0x18001dc5e  mov     ebx, eax
0x18001dc60  or      ebx, r15d
0x18001dc63  jge     short loc_18001DC88
0x18001dc65  lea     rdx, aCommitFailedTo_2; "Commit: failed to save the DNS Domain i"...
0x18001dc6c  jmp     short loc_18001DC7E
0x18001dc6e  lea     rdx, aCommitFailedTo_3; "Commit: failed to query the LSA for the"...
0x18001dc75  jmp     short loc_18001DC7E
0x18001dc77  lea     rdx, aCommitFailedTo_0; "Commit: failed to save the Account Doma"...
0x18001dc7e  mov     r8d, ebx
0x18001dc81  mov     ecx, esi
0x18001dc83  call    UnattendLogW
0x18001dc88  mov     rcx, [rbp+Buffer]; Buffer
0x18001dc8c  call    cs:__imp_LsaFreeMemory
0x18001dc92  jmp     short loc_18001DCA5
0x18001dc94  mov     r8d, ebx
0x18001dc97  lea     rdx, aCommitFailedTo; "Commit: failed to query the LSA for the"...
0x18001dc9e  mov     ecx, esi
0x18001dca0  call    UnattendLogW
0x18001dca5  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18001dca9  call    cs:__imp_LsaClose
0x18001dcaf  jmp     short loc_18001DCC2
0x18001dcb1  mov     r8d, ebx
0x18001dcb4  lea     rdx, aCommitFailedTo_1; "Commit: failed to open the LSA [0x%08X]"
0x18001dcbb  mov     ecx, esi
0x18001dcbd  call    UnattendLogW
0x18001dcc2  mov     eax, ebx
0x18001dcc4  mov     rcx, [rbp+var_8]
0x18001dcc8  xor     rcx, rsp; StackCookie
0x18001dccb  call    __security_check_cookie
0x18001dcd0  lea     r11, [rsp+80h+var_s0]
0x18001dcd8  mov     rbx, [r11+28h]
0x18001dcdc  mov     rsi, [r11+30h]
0x18001dce0  mov     rsp, r11
0x18001dce3  pop     r15
0x18001dce5  pop     rdi
0x18001dce6  pop     rbp
0x18001dce7  retn
```
