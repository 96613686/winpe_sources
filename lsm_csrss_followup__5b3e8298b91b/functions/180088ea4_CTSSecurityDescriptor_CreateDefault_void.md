# CTSSecurityDescriptor::CreateDefault(void * *)

- ea: `0x180088ea4`
- end: `0x180089004`
- name: `?CreateDefault@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z`
- size: `352`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800198c4`

## callees

- `0x1800074c0`
- `0x180047dcc`
- `0x18007e504`
- `0x180088ea4`
- `0x18008900c`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180088fd6`
- `ntdll!RtlFreeSid` at `0x180088fe5`
- `ntdll!RtlFreeSid` at `0x180088fd6`
- `ntdll!RtlFreeSid` at `0x180088fe5`
- `ntdll!RtlCreateUserSecurityObject` at `0x180088faa`
- `ntdll!RtlCreateUserSecurityObject` at `0x180088faa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088ff4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088ff4`

## string_xrefs

- `0x180088f2d`: `CUtil::CreateSystemSid failed: 0x%x in %s`
- `0x180088f48`: `CUtil::CreateAdminSid failed: 0x%x in %s`
- `0x180088eea`: `CTSSecurityDescriptor::CreateDefault`
- `0x180088fba`: `RtlCreateUserSecurityObject failed: 0x%x in %s`
- `0x180088f12`: `GetCurrentProcessSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::CreateDefault(CTSSecurityDescriptor *this, void **a2)
{
  unsigned int v3; // ebx
  const char *v4; // rdx
  int CurrentProcessSid; // eax
  int v6; // eax
  int v7; // eax
  NTSTATUS v8; // eax
  __int16 AceData; // [rsp+40h] [rbp-20h] BYREF
  char v11; // [rsp+42h] [rbp-1Eh]
  int v12; // [rsp+44h] [rbp-1Ch]
  PSID *p_Sid; // [rsp+48h] [rbp-18h]
  __int16 v14; // [rsp+50h] [rbp-10h]
  char v15; // [rsp+52h] [rbp-Eh]
  int v16; // [rsp+54h] [rbp-Ch]
  PSID *v17; // [rsp+58h] [rbp-8h]
  PSID Sid; // [rsp+80h] [rbp+20h] BYREF
  PSID v19; // [rsp+88h] [rbp+28h] BYREF
  PSID GroupSid; // [rsp+90h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+98h] [rbp+38h] BYREF

  NewDescriptor = 0;
  GroupSid = 0;
  Sid = 0;
  v19 = 0;
  if ( a2 )
  {
    CurrentProcessSid = CTSSecurityDescriptor::GetCurrentProcessSid(this, &GroupSid);
    v3 = CurrentProcessSid;
    if ( CurrentProcessSid < 0 )
    {
      _DbgPrintMessage(
        8,
        "GetCurrentProcessSid failed: 0x%x in %s",
        (unsigned int)CurrentProcessSid,
        "CTSSecurityDescriptor::CreateDefault");
      goto LABEL_14;
    }
    v6 = CUtils::CreateSystemSid(&Sid);
    v3 = v6;
    if ( v6 < 0 )
    {
      _DbgPrintMessage(
        8,
        "CUtil::CreateSystemSid failed: 0x%x in %s",
        (unsigned int)v6,
        "CTSSecurityDescriptor::CreateDefault");
      goto LABEL_14;
    }
    v7 = CUtils::CreateAdminSid(&v19);
    v3 = v7;
    if ( v7 < 0 )
    {
      _DbgPrintMessage(
        8,
        "CUtil::CreateAdminSid failed: 0x%x in %s",
        (unsigned int)v7,
        "CTSSecurityDescriptor::CreateDefault");
      goto LABEL_14;
    }
    p_Sid = &Sid;
    v12 = 983999;
    v17 = &v19;
    v16 = 983999;
    AceData = 0;
    v11 = 0;
    v14 = 0;
    v15 = 0;
    v8 = RtlCreateUserSecurityObject(
           &AceData,
           2u,
           GroupSid,
           GroupSid,
           0,
           (PGENERIC_MAPPING)&GenericMapping,
           &NewDescriptor);
    v3 = v8 | 0x10000000;
    if ( v8 >= 0 )
    {
      *a2 = NewDescriptor;
      goto LABEL_14;
    }
    v4 = "RtlCreateUserSecurityObject failed: 0x%x in %s";
  }
  else
  {
    v3 = -2147024809;
    v4 = "Invalid Paramater failed: 0x%x in %s";
  }
  _DbgPrintMessage(8, v4, v3, "CTSSecurityDescriptor::CreateDefault");
LABEL_14:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v19 )
    RtlFreeSid(v19);
  if ( GroupSid )
    CoTaskMemFree(GroupSid);
  return v3;
}

```

## disassembly

```asm
0x180088ea4  mov     [rsp-18h+Sid], rcx
0x180088ea9  push    rbp
0x180088eaa  push    rbx
0x180088eab  push    rdi
0x180088eac  mov     rbp, rsp
0x180088eaf  sub     rsp, 60h
0x180088eb3  mov     [rbp+arg_18], 0
0x180088ebb  mov     rdi, rdx
0x180088ebe  mov     [rbp+GroupSid], 0
0x180088ec6  mov     [rbp+Sid], 0
0x180088ece  mov     [rbp+arg_8], 0
0x180088ed6  test    rdx, rdx
0x180088ed9  jnz     short loc_180088F00
0x180088edb  mov     ebx, 80070057h
0x180088ee0  lea     rdx, aInvalidParamat; "Invalid Paramater failed: 0x%x in %s"
0x180088ee7  mov     r8d, ebx
0x180088eea  lea     r9, aCtssecuritydes_1; "CTSSecurityDescriptor::CreateDefault"
0x180088ef1  mov     ecx, 8; int
0x180088ef6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180088efb  jmp     loc_180088FCD
0x180088f00  lea     rdx, [rbp+GroupSid]; void **
0x180088f04  call    ?GetCurrentProcessSid@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z; CTSSecurityDescriptor::GetCurrentProcessSid(void * *)
0x180088f09  mov     ebx, eax
0x180088f0b  test    eax, eax
0x180088f0d  jns     short loc_180088F1B
0x180088f0f  mov     r8d, eax
0x180088f12  lea     rdx, aGetcurrentproc; "GetCurrentProcessSid failed: 0x%x in %s"
0x180088f19  jmp     short loc_180088EEA
0x180088f1b  lea     rcx, [rbp+Sid]; void **
0x180088f1f  call    ?CreateSystemSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateSystemSid(void * *)
0x180088f24  mov     ebx, eax
0x180088f26  test    eax, eax
0x180088f28  jns     short loc_180088F36
0x180088f2a  mov     r8d, eax
0x180088f2d  lea     rdx, aCutilCreatesys; "CUtil::CreateSystemSid failed: 0x%x in "...
0x180088f34  jmp     short loc_180088EEA
0x180088f36  lea     rcx, [rbp+arg_8]; void **
0x180088f3a  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x180088f3f  mov     ebx, eax
0x180088f41  test    eax, eax
0x180088f43  jns     short loc_180088F51
0x180088f45  mov     r8d, eax
0x180088f48  lea     rdx, aCutilCreateadm; "CUtil::CreateAdminSid failed: 0x%x in %"...
0x180088f4f  jmp     short loc_180088EEA
0x180088f51  mov     r8, [rbp+GroupSid]; OwnerSid
0x180088f55  lea     rax, [rbp+Sid]
0x180088f59  mov     [rbp+var_18], rax
0x180088f5d  mov     ecx, 0F03BFh
0x180088f62  lea     rax, [rbp+arg_8]
0x180088f66  mov     [rbp+var_1C], ecx
0x180088f69  mov     [rbp+var_8], rax
0x180088f6d  mov     r9, r8; GroupSid
0x180088f70  lea     rax, [rbp+arg_18]
0x180088f74  mov     [rbp+var_C], ecx
0x180088f77  mov     [rsp+60h+NewDescriptor], rax; NewDescriptor
0x180088f7c  lea     rcx, [rbp+AceData]; AceData
0x180088f80  lea     rax, GenericMapping
0x180088f87  mov     [rbp+AceData], 0
0x180088f8d  mov     [rsp+60h+GenericMapping], rax; GenericMapping
0x180088f92  mov     edx, 2; AceCount
0x180088f97  mov     [rsp+60h+IsDirectoryObject], 0; IsDirectoryObject
0x180088f9c  mov     [rbp+var_1E], 0
0x180088fa0  mov     [rbp+var_10], 0
0x180088fa6  mov     [rbp+var_E], 0
0x180088faa  call    cs:__imp_RtlCreateUserSecurityObject
0x180088fb0  mov     ebx, eax
0x180088fb2  or      ebx, 10000000h
0x180088fb8  jge     short loc_180088FC6
0x180088fba  lea     rdx, aRtlcreateusers; "RtlCreateUserSecurityObject failed: 0x%"...
0x180088fc1  jmp     loc_180088EE7
0x180088fc6  mov     rax, [rbp+arg_18]
0x180088fca  mov     [rdi], rax
0x180088fcd  mov     rcx, [rbp+Sid]; Sid
0x180088fd1  test    rcx, rcx
0x180088fd4  jz      short loc_180088FDC
0x180088fd6  call    cs:__imp_RtlFreeSid
0x180088fdc  mov     rcx, [rbp+arg_8]; Sid
0x180088fe0  test    rcx, rcx
0x180088fe3  jz      short loc_180088FEB
0x180088fe5  call    cs:__imp_RtlFreeSid
0x180088feb  mov     rcx, [rbp+GroupSid]; pv
0x180088fef  test    rcx, rcx
0x180088ff2  jz      short loc_180088FFA
0x180088ff4  call    cs:__imp_CoTaskMemFree
0x180088ffa  mov     eax, ebx
0x180088ffc  add     rsp, 60h
0x180089000  pop     rdi
0x180089001  pop     rbx
0x180089002  pop     rbp
0x180089003  retn
```
