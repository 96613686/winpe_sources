# AttemptCredProvLogon(_CRED_PROV_CREDENTIAL *,_TOKEN_GROUPS *,void * *)

- ea: `0x1400140c8`
- end: `0x140014394`
- name: `?AttemptCredProvLogon@@YAKPEAU_CRED_PROV_CREDENTIAL@@PEAU_TOKEN_GROUPS@@PEAPEAX@Z`
- size: `716`
- prototype: `__int64 __fastcall(struct _CRED_PROV_CREDENTIAL *, struct _TOKEN_GROUPS *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140014764`

## callees

- `0x1400140c8`
- `0x140017a1c`
- `0x140018200`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400141e7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400141e7`
- `SspiCli!LsaLogonUser` at `0x140014261`
- `SspiCli!LsaLogonUser` at `0x1400142e1`
- `SspiCli!LsaLogonUser` at `0x140014261`
- `SspiCli!LsaLogonUser` at `0x1400142e1`
- `SspiCli!LsaFreeReturnBuffer` at `0x14001435a`
- `SspiCli!LsaFreeReturnBuffer` at `0x14001435a`
- `SspiCli!LsaDeregisterLogonProcess` at `0x140014369`
- `SspiCli!LsaDeregisterLogonProcess` at `0x140014369`
- `SspiCli!LsaRegisterLogonProcess` at `0x140014195`
- `SspiCli!LsaRegisterLogonProcess` at `0x140014195`
- `ntdll!RtlNtStatusToDosError` at `0x14001432c`
- `ntdll!RtlNtStatusToDosError` at `0x14001432c`
- `ntdll!RtlAdjustPrivilege` at `0x140014178`
- `ntdll!RtlAdjustPrivilege` at `0x140014178`
- `ntdll!NtClose` at `0x14001434b`
- `ntdll!NtClose` at `0x14001434b`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1400141ac`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1400141ac`

## pseudocode

```c
__int64 __fastcall AttemptCredProvLogon(struct _CRED_PROV_CREDENTIAL *a1, struct _TOKEN_GROUPS *a2, void **a3)
{
  NTSTATUS v6; // eax
  NTSTATUS v7; // ecx
  unsigned __int64 v8; // rdx
  const char *v9; // r8
  ULONG v10; // edi
  NTSTATUS v11; // ebx
  __int64 v12; // r8
  NTSTATUS v13; // eax
  unsigned __int8 OldValue[4]; // [rsp+70h] [rbp-59h] BYREF
  NTSTATUS Status; // [rsp+74h] [rbp-55h] BYREF
  ULONG ProfileBufferLength; // [rsp+78h] [rbp-51h] BYREF
  int pvData; // [rsp+7Ch] [rbp-4Dh] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-49h] BYREF
  void *LsaHandle; // [rsp+88h] [rbp-41h] BYREF
  PVOID Buffer; // [rsp+90h] [rbp-39h] BYREF
  ULONG SecurityMode; // [rsp+98h] [rbp-31h] BYREF
  DWORD pcbData; // [rsp+9Ch] [rbp-2Dh] BYREF
  struct _LUID LogonId; // [rsp+A0h] [rbp-29h] BYREF
  _LSA_STRING LogonProcessName; // [rsp+A8h] [rbp-21h] BYREF
  LUID LocallyUniqueId[2]; // [rsp+B8h] [rbp-11h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+C8h] [rbp-1h] BYREF

  LsaHandle = 0;
  Buffer = 0;
  ProfileBufferLength = 0;
  Handle = 0;
  Status = 0;
  SecurityMode = 0;
  OldValue[0] = 0;
  *(_QWORD *)&LogonProcessName.Length = 1048591;
  LogonProcessName.Buffer = "CredProvConsent";
  pvData = 0;
  pcbData = 4;
  *(_OWORD *)&LocallyUniqueId[0].LowPart = 0;
  LogonId = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  v6 = RtlAdjustPrivilege(7u, 1u, 0, OldValue);
  if ( v6 < 0
    || (v6 = LsaRegisterLogonProcess(&LogonProcessName, &LsaHandle, &SecurityMode), v6 < 0)
    || (StringCbCopyA((char *)LocallyUniqueId, v8, v9), v6 = NtAllocateLocallyUniqueId(&LocallyUniqueId[1]), v6 < 0) )
  {
    v7 = v6;
  }
  else
  {
    v10 = 0;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
            L"InteractiveLogonFirst",
            0x10u,
            0,
            &pvData,
            &pcbData)
      && pvData == 1 )
    {
      goto LABEL_9;
    }
    v11 = LsaLogonUser(
            LsaHandle,
            &LogonProcessName,
            CachedInteractive,
            *((_DWORD *)a1 + 1),
            *((PVOID *)a1 + 2),
            *((_DWORD *)a1 + 2),
            a2,
            (PTOKEN_SOURCE)LocallyUniqueId,
            &Buffer,
            &ProfileBufferLength,
            &LogonId,
            &Handle,
            &Quotas,
            &Status);
    if ( v11 >= 0 )
      goto LABEL_18;
    v13 = Status;
    if ( Status != -1073740928 )
    {
LABEL_9:
      v11 = LsaLogonUser(
              LsaHandle,
              &LogonProcessName,
              Interactive,
              *((_DWORD *)a1 + 1),
              *((PVOID *)a1 + 2),
              *((_DWORD *)a1 + 2),
              a2,
              (PTOKEN_SOURCE)LocallyUniqueId,
              &Buffer,
              &ProfileBufferLength,
              &LogonId,
              &Handle,
              &Quotas,
              &Status);
      if ( v11 >= 0 )
        goto LABEL_18;
      v13 = Status;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_DD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, v12, (unsigned int)v11, v13);
      v13 = Status;
    }
    if ( v11 == -1073741714 )
      v11 = v13;
    v7 = v11;
  }
  v10 = RtlNtStatusToDosError(v7);
LABEL_18:
  if ( a3 )
  {
    *a3 = Handle;
  }
  else if ( Handle )
  {
    NtClose(Handle);
  }
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( LsaHandle )
    LsaDeregisterLogonProcess(LsaHandle);
  return v10;
}

```

## disassembly

```asm
0x1400140c8  mov     [rsp-8+arg_18], rbx
0x1400140cd  push    rbp
0x1400140ce  push    rsi
0x1400140cf  push    rdi
0x1400140d0  push    r14
0x1400140d2  push    r15
0x1400140d4  lea     rbp, [rsp-37h]
0x1400140d9  sub     rsp, 100h
0x1400140e0  mov     rax, cs:__security_cookie
0x1400140e7  xor     rax, rsp
0x1400140ea  mov     [rbp+57h+var_28], rax
0x1400140ee  xorps   xmm1, xmm1
0x1400140f1  mov     [rbp+57h+LsaHandle], 0
0x1400140f9  mov     r14, r8
0x1400140fc  mov     [rbp+57h+Buffer], 0
0x140014104  mov     r15, rdx
0x140014107  mov     [rbp+57h+var_A8], 0
0x14001410e  mov     rsi, rcx
0x140014111  mov     [rbp+57h+Handle], 0
0x140014119  lea     rax, aCredprovconsen; "CredProvConsent"
0x140014120  mov     [rbp+57h+Status], 0
0x140014127  xorps   xmm0, xmm0
0x14001412a  mov     [rbp+57h+SecurityMode], 0
0x140014131  mov     ebx, 10h
0x140014136  mov     [rbp+57h+OldValue], 0
0x14001413a  lea     r9, [rbp+57h+OldValue]; OldValue
0x14001413e  mov     qword ptr [rbp+57h+LogonProcessName.Length], 10000Fh
0x140014146  xor     r8d, r8d; ForThread
0x140014149  mov     [rbp+57h+LogonProcessName.Buffer], rax
0x14001414d  mov     dl, 1; NewValue
0x14001414f  mov     [rbp+57h+var_A4], 0
0x140014156  lea     ecx, [rbx-9]; Privilege
0x140014159  mov     [rbp+57h+var_84], 4
0x140014160  movups  xmmword ptr [rbp+57h+LocallyUniqueId.LowPart], xmm0
0x140014164  mov     qword ptr [rbp+57h+var_80.LowPart], 0
0x14001416c  movups  xmmword ptr [rbp+57h+var_58.PagedPoolLimit], xmm1
0x140014170  movups  xmmword ptr [rbp+57h+var_58.MinimumWorkingSetSize], xmm1
0x140014174  movups  xmmword ptr [rbp+57h+var_58.PagefileLimit], xmm1
0x140014178  call    cs:__imp_RtlAdjustPrivilege
0x14001417e  test    eax, eax
0x140014180  jns     short loc_140014189
0x140014182  mov     ecx, eax
0x140014184  jmp     loc_14001432C
0x140014189  lea     r8, [rbp+57h+SecurityMode]; SecurityMode
0x14001418d  lea     rdx, [rbp+57h+LsaHandle]; LsaHandle
0x140014191  lea     rcx, [rbp+57h+LogonProcessName]; LogonProcessName
0x140014195  call    cs:__imp_LsaRegisterLogonProcess
0x14001419b  test    eax, eax
0x14001419d  js      short loc_140014182
0x14001419f  lea     rcx, [rbp+57h+LocallyUniqueId]; char *
0x1400141a3  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1400141a8  lea     rcx, [rbp+57h+LocallyUniqueId.LowPart+8]; LocallyUniqueId
0x1400141ac  call    cs:__imp_NtAllocateLocallyUniqueId
0x1400141b2  test    eax, eax
0x1400141b4  js      short loc_140014182
0x1400141b6  lea     rax, [rbp+57h+var_84]
0x1400141ba  xor     edi, edi
0x1400141bc  mov     [rsp+120h+pcbData], rax; pcbData
0x1400141c1  lea     r8, aInteractivelog; "InteractiveLogonFirst"
0x1400141c8  lea     rax, [rbp+57h+var_A4]
0x1400141cc  mov     r9d, ebx; dwFlags
0x1400141cf  mov     [rsp+120h+pvData], rax; pvData
0x1400141d4  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400141db  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400141e2  mov     [rsp+120h+pdwType], rdi; pdwType
0x1400141e7  call    cs:__imp_RegGetValueW
0x1400141ed  test    eax, eax
0x1400141ef  jnz     short loc_1400141FB
0x1400141f1  cmp     [rbp+57h+var_A4], 1
0x1400141f5  jz      loc_14001427B
0x1400141fb  mov     r9d, [rsi+4]; AuthenticationPackage
0x1400141ff  lea     rax, [rbp+57h+Status]
0x140014203  mov     rcx, [rbp+57h+LsaHandle]; LsaHandle
0x140014207  lea     rdx, [rbp+57h+LogonProcessName]; OriginName
0x14001420b  mov     [rsp+120h+SubStatus], rax; SubStatus
0x140014210  mov     r8d, 0Bh; LogonType
0x140014216  lea     rax, [rbp+57h+var_58]
0x14001421a  mov     [rsp+120h+Quotas], rax; Quotas
0x14001421f  lea     rax, [rbp+57h+Handle]
0x140014223  mov     [rsp+120h+Token], rax; Token
0x140014228  lea     rax, [rbp+57h+var_80]
0x14001422c  mov     [rsp+120h+LogonId], rax; LogonId
0x140014231  lea     rax, [rbp+57h+var_A8]
0x140014235  mov     [rsp+120h+ProfileBufferLength], rax; ProfileBufferLength
0x14001423a  lea     rax, [rbp+57h+Buffer]
0x14001423e  mov     [rsp+120h+ProfileBuffer], rax; ProfileBuffer
0x140014243  lea     rax, [rbp+57h+LocallyUniqueId]
0x140014247  mov     [rsp+120h+SourceContext], rax; SourceContext
0x14001424c  mov     eax, [rsi+8]
0x14001424f  mov     [rsp+120h+pcbData], r15; LocalGroups
0x140014254  mov     dword ptr [rsp+120h+pvData], eax; AuthenticationInformationLength
0x140014258  mov     rax, [rsi+10h]
0x14001425c  mov     [rsp+120h+pdwType], rax; AuthenticationInformation
0x140014261  call    cs:__imp_LsaLogonUser
0x140014267  mov     ebx, eax
0x140014269  test    eax, eax
0x14001426b  jns     loc_140014334
0x140014271  mov     eax, [rbp+57h+Status]
0x140014274  cmp     eax, 0C0000380h
0x140014279  jz      short loc_1400142F0
0x14001427b  mov     r9d, [rsi+4]; AuthenticationPackage
0x14001427f  lea     rax, [rbp+57h+Status]
0x140014283  mov     rcx, [rbp+57h+LsaHandle]; LsaHandle
0x140014287  lea     rdx, [rbp+57h+LogonProcessName]; OriginName
0x14001428b  mov     [rsp+120h+SubStatus], rax; SubStatus
0x140014290  mov     r8d, 2; LogonType
0x140014296  lea     rax, [rbp+57h+var_58]
0x14001429a  mov     [rsp+120h+Quotas], rax; Quotas
0x14001429f  lea     rax, [rbp+57h+Handle]
0x1400142a3  mov     [rsp+120h+Token], rax; Token
0x1400142a8  lea     rax, [rbp+57h+var_80]
0x1400142ac  mov     [rsp+120h+LogonId], rax; LogonId
0x1400142b1  lea     rax, [rbp+57h+var_A8]
0x1400142b5  mov     [rsp+120h+ProfileBufferLength], rax; ProfileBufferLength
0x1400142ba  lea     rax, [rbp+57h+Buffer]
0x1400142be  mov     [rsp+120h+ProfileBuffer], rax; ProfileBuffer
0x1400142c3  lea     rax, [rbp+57h+LocallyUniqueId]
0x1400142c7  mov     [rsp+120h+SourceContext], rax; SourceContext
0x1400142cc  mov     eax, [rsi+8]
0x1400142cf  mov     [rsp+120h+pcbData], r15; LocalGroups
0x1400142d4  mov     dword ptr [rsp+120h+pvData], eax; AuthenticationInformationLength
0x1400142d8  mov     rax, [rsi+10h]
0x1400142dc  mov     [rsp+120h+pdwType], rax; AuthenticationInformation
0x1400142e1  call    cs:__imp_LsaLogonUser
0x1400142e7  mov     ebx, eax
0x1400142e9  test    eax, eax
0x1400142eb  jns     short loc_140014334
0x1400142ed  mov     eax, [rbp+57h+Status]
0x1400142f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400142f7  lea     rdx, WPP_GLOBAL_Control
0x1400142fe  cmp     rcx, rdx
0x140014301  jz      short loc_140014321
0x140014303  test    byte ptr [rcx+1Ch], 2
0x140014307  jz      short loc_140014321
0x140014309  mov     rcx, [rcx+10h]
0x14001430d  mov     edx, 1Fh
0x140014312  mov     r9d, ebx
0x140014315  mov     dword ptr [rsp+120h+pdwType], eax
0x140014319  call    WPP_SF_DD
0x14001431e  mov     eax, [rbp+57h+Status]
0x140014321  cmp     ebx, 0C000006Eh
0x140014327  cmovz   ebx, eax
0x14001432a  mov     ecx, ebx; Status
0x14001432c  call    cs:__imp_RtlNtStatusToDosError
0x140014332  mov     edi, eax
0x140014334  test    r14, r14
0x140014337  jz      short loc_140014342
0x140014339  mov     rax, [rbp+57h+Handle]
0x14001433d  mov     [r14], rax
0x140014340  jmp     short loc_140014351
0x140014342  mov     rcx, [rbp+57h+Handle]; Handle
0x140014346  test    rcx, rcx
0x140014349  jz      short loc_140014351
0x14001434b  call    cs:__imp_NtClose
0x140014351  mov     rcx, [rbp+57h+Buffer]; Buffer
0x140014355  test    rcx, rcx
0x140014358  jz      short loc_140014360
0x14001435a  call    cs:__imp_LsaFreeReturnBuffer
0x140014360  mov     rcx, [rbp+57h+LsaHandle]; LsaHandle
0x140014364  test    rcx, rcx
0x140014367  jz      short loc_14001436F
0x140014369  call    cs:__imp_LsaDeregisterLogonProcess
0x14001436f  mov     eax, edi
0x140014371  mov     rcx, [rbp+57h+var_28]
0x140014375  xor     rcx, rsp; StackCookie
0x140014378  call    __security_check_cookie
0x14001437d  mov     rbx, [rsp+120h+arg_18]
0x140014385  add     rsp, 100h
0x14001438c  pop     r15
0x14001438e  pop     r14
0x140014390  pop     rdi
0x140014391  pop     rsi
0x140014392  pop     rbp
0x140014393  retn
```
