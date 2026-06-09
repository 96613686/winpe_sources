# _MoveLsaSecret(ushort const *,ushort const *)

- ea: `0x1800bee24`
- end: `0x1800bef88`
- name: `?_MoveLsaSecret@@YAJPEBG0@Z`
- size: `356`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800be948`

## callees

- `0x180008544`
- `0x180031f90`
- `0x1800bee24`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800beeab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800beeab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800bee69`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800bee69`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800bef1e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800bef5d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800bef1e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800bef5d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800beef5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800bef45`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800beef5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800bef45`
- `ntdll!RtlInitUnicodeString` at `0x1800bee91`
- `ntdll!RtlInitUnicodeString` at `0x1800beee3`
- `ntdll!RtlInitUnicodeString` at `0x1800bef33`
- `ntdll!RtlInitUnicodeString` at `0x1800bee91`
- `ntdll!RtlInitUnicodeString` at `0x1800beee3`
- `ntdll!RtlInitUnicodeString` at `0x1800bef33`

## string_xrefs

- `0x1800beec1`: `shell\oobe\common\lib\autologon.cpp`
- `0x1800bef0b`: `shell\oobe\common\lib\autologon.cpp`

## pseudocode

```c
__int64 __fastcall _MoveLsaSecret(PCWSTR SourceString, PCWSTR a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  __int64 v9; // rdx
  NTSTATUS v10; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-60h] BYREF
  struct _UNICODE_STRING v13; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING v14; // [rsp+40h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  PLSA_UNICODE_STRING PrivateData; // [rsp+B0h] [rbp+30h] BYREF
  PVOID PolicyHandle; // [rsp+B8h] [rbp+38h] BYREF

  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x24u, &PolicyHandle);
  v5 = v4 | 0x10000000;
  if ( v4 < 0 )
  {
    v6 = 138;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
      (const char *)v5,
      *(int *)&DestinationString.Length);
    goto LABEL_12;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  PrivateData = 0;
  v7 = LsaRetrievePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
  v5 = v7 | 0x10000000;
  if ( v7 < 0 )
  {
    v6 = 145;
    goto LABEL_5;
  }
  v13 = 0;
  RtlInitUnicodeString(&v13, a2);
  v8 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&v13, PrivateData);
  v5 = v8 | 0x10000000;
  if ( v8 >= 0 )
  {
    v14 = 0;
    RtlInitUnicodeString(&v14, 0);
    v10 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, (PLSA_UNICODE_STRING)&v14);
    v5 = v10 | 0x10000000;
    if ( v10 >= 0 )
    {
      LsaFreeMemory(PrivateData);
      v5 = 0;
      goto LABEL_12;
    }
    v9 = 158;
  }
  else
  {
    v9 = 154;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
    (const char *)v5,
    *(int *)&DestinationString.Length);
  LsaFreeMemory(PrivateData);
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v5;
}

```

## disassembly

```asm
0x1800bee24  mov     [rsp-18h+arg_0], rbx
0x1800bee29  mov     [rsp-18h+arg_8], rsi
0x1800bee2e  push    rbp
0x1800bee2f  push    rdi
0x1800bee30  push    r14
0x1800bee32  mov     rbp, rsp
0x1800bee35  sub     rsp, 80h
0x1800bee3c  xorps   xmm0, xmm0
0x1800bee3f  mov     [rbp+PolicyHandle], 0
0x1800bee47  mov     rsi, rdx
0x1800bee4a  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800bee4e  mov     rdi, rcx
0x1800bee51  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800bee55  xor     ecx, ecx; SystemName
0x1800bee57  mov     r8d, 24h ; '$'; DesiredAccess
0x1800bee5d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800bee61  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800bee65  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800bee69  call    cs:__imp_LsaOpenPolicy
0x1800bee6f  mov     ebx, eax
0x1800bee71  mov     r14d, 10000000h
0x1800bee77  or      ebx, r14d
0x1800bee7a  jge     short loc_1800BEE83
0x1800bee7c  mov     edx, 8Ah
0x1800bee81  jmp     short loc_1800BEEBD
0x1800bee83  xorps   xmm0, xmm0
0x1800bee86  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800bee8a  mov     rdx, rdi; SourceString
0x1800bee8d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800bee91  call    cs:__imp_RtlInitUnicodeString
0x1800bee97  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800bee9b  lea     r8, [rbp+PrivateData]; PrivateData
0x1800bee9f  lea     rdx, [rbp+DestinationString]; KeyName
0x1800beea3  mov     [rbp+PrivateData], 0
0x1800beeab  call    cs:__imp_LsaRetrievePrivateData
0x1800beeb1  mov     ebx, eax
0x1800beeb3  or      ebx, r14d
0x1800beeb6  jge     short loc_1800BEED5
0x1800beeb8  mov     edx, 91h; void *
0x1800beebd  mov     rcx, [rbp+18h]; this
0x1800beec1  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800beec8  mov     r9d, ebx; char *
0x1800beecb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800beed0  jmp     loc_1800BEF65
0x1800beed5  xorps   xmm0, xmm0
0x1800beed8  lea     rcx, [rbp+var_50]; DestinationString
0x1800beedc  mov     rdx, rsi; SourceString
0x1800beedf  movups  xmmword ptr [rbp+var_50.Length], xmm0
0x1800beee3  call    cs:__imp_RtlInitUnicodeString
0x1800beee9  mov     r8, [rbp+PrivateData]; PrivateData
0x1800beeed  lea     rdx, [rbp+var_50]; KeyName
0x1800beef1  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800beef5  call    cs:__imp_LsaStorePrivateData
0x1800beefb  mov     ebx, eax
0x1800beefd  or      ebx, r14d
0x1800bef00  jge     short loc_1800BEF26
0x1800bef02  mov     edx, 9Ah; void *
0x1800bef07  mov     rcx, [rbp+18h]; this
0x1800bef0b  lea     r8, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x1800bef12  mov     r9d, ebx; char *
0x1800bef15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bef1a  mov     rcx, [rbp+PrivateData]; Buffer
0x1800bef1e  call    cs:__imp_LsaFreeMemory
0x1800bef24  jmp     short loc_1800BEF65
0x1800bef26  xorps   xmm0, xmm0
0x1800bef29  lea     rcx, [rbp+var_40]; DestinationString
0x1800bef2d  xor     edx, edx; SourceString
0x1800bef2f  movups  xmmword ptr [rbp+var_40.Length], xmm0
0x1800bef33  call    cs:__imp_RtlInitUnicodeString
0x1800bef39  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800bef3d  lea     r8, [rbp+var_40]; PrivateData
0x1800bef41  lea     rdx, [rbp+DestinationString]; KeyName
0x1800bef45  call    cs:__imp_LsaStorePrivateData
0x1800bef4b  mov     ebx, eax
0x1800bef4d  or      ebx, r14d
0x1800bef50  jge     short loc_1800BEF59
0x1800bef52  mov     edx, 9Eh
0x1800bef57  jmp     short loc_1800BEF07
0x1800bef59  mov     rcx, [rbp+PrivateData]; Buffer
0x1800bef5d  call    cs:__imp_LsaFreeMemory
0x1800bef63  xor     ebx, ebx
0x1800bef65  lea     rcx, [rbp+PolicyHandle]
0x1800bef69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800bef6e  lea     r11, [rsp+80h+var_s0]
0x1800bef76  mov     eax, ebx
0x1800bef78  mov     rbx, [r11+20h]
0x1800bef7c  mov     rsi, [r11+28h]
0x1800bef80  mov     rsp, r11
0x1800bef83  pop     r14
0x1800bef85  pop     rdi
0x1800bef86  pop     rbp
0x1800bef87  retn
```
