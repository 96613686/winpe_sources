# CTSSecurityDescriptor::CreateDefault(void * *)

- ea: `0x18008db9c`
- end: `0x18008dd15`
- name: `?CreateDefault@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z`
- size: `377`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a66c`

## callees

- `0x1800077a0`
- `0x18004af10`
- `0x180082efc`
- `0x18008db9c`
- `0x18008dd1c`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18008dcd4`
- `ntdll!RtlFreeSid` at `0x18008dce9`
- `ntdll!RtlFreeSid` at `0x18008dcd4`
- `ntdll!RtlFreeSid` at `0x18008dce9`
- `ntdll!RtlCreateUserSecurityObject` at `0x18008dca2`
- `ntdll!RtlCreateUserSecurityObject` at `0x18008dca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008dcfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008dcfe`

## string_xrefs

- `0x18008dc25`: `CUtil::CreateSystemSid failed: 0x%x in %s`
- `0x18008dc40`: `CUtil::CreateAdminSid failed: 0x%x in %s`
- `0x18008dbe2`: `CTSSecurityDescriptor::CreateDefault`
- `0x18008dc0a`: `GetCurrentProcessSid failed: 0x%x in %s`
- `0x18008dcb8`: `RtlCreateUserSecurityObject failed: 0x%x in %s`

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
0x18008db9c  mov     [rsp-18h+Sid], rcx
0x18008dba1  push    rbp
0x18008dba2  push    rbx
0x18008dba3  push    rdi
0x18008dba4  mov     rbp, rsp
0x18008dba7  sub     rsp, 60h
0x18008dbab  mov     [rbp+arg_18], 0
0x18008dbb3  mov     rdi, rdx
0x18008dbb6  mov     [rbp+GroupSid], 0
0x18008dbbe  mov     [rbp+Sid], 0
0x18008dbc6  mov     [rbp+arg_8], 0
0x18008dbce  test    rdx, rdx
0x18008dbd1  jnz     short loc_18008DBF8
0x18008dbd3  mov     ebx, 80070057h
0x18008dbd8  lea     rdx, aInvalidParamat; "Invalid Paramater failed: 0x%x in %s"
0x18008dbdf  mov     r8d, ebx
0x18008dbe2  lea     r9, aCtssecuritydes_1; "CTSSecurityDescriptor::CreateDefault"
0x18008dbe9  mov     ecx, 8; int
0x18008dbee  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008dbf3  jmp     loc_18008DCCB
0x18008dbf8  lea     rdx, [rbp+GroupSid]; void **
0x18008dbfc  call    ?GetCurrentProcessSid@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z; CTSSecurityDescriptor::GetCurrentProcessSid(void * *)
0x18008dc01  mov     ebx, eax
0x18008dc03  test    eax, eax
0x18008dc05  jns     short loc_18008DC13
0x18008dc07  mov     r8d, eax
0x18008dc0a  lea     rdx, aGetcurrentproc; "GetCurrentProcessSid failed: 0x%x in %s"
0x18008dc11  jmp     short loc_18008DBE2
0x18008dc13  lea     rcx, [rbp+Sid]; void **
0x18008dc17  call    ?CreateSystemSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateSystemSid(void * *)
0x18008dc1c  mov     ebx, eax
0x18008dc1e  test    eax, eax
0x18008dc20  jns     short loc_18008DC2E
0x18008dc22  mov     r8d, eax
0x18008dc25  lea     rdx, aCutilCreatesys; "CUtil::CreateSystemSid failed: 0x%x in "...
0x18008dc2c  jmp     short loc_18008DBE2
0x18008dc2e  lea     rcx, [rbp+arg_8]; void **
0x18008dc32  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x18008dc37  mov     ebx, eax
0x18008dc39  test    eax, eax
0x18008dc3b  jns     short loc_18008DC49
0x18008dc3d  mov     r8d, eax
0x18008dc40  lea     rdx, aCutilCreateadm; "CUtil::CreateAdminSid failed: 0x%x in %"...
0x18008dc47  jmp     short loc_18008DBE2
0x18008dc49  mov     r8, [rbp+GroupSid]; OwnerSid
0x18008dc4d  lea     rax, [rbp+Sid]
0x18008dc51  mov     [rbp+var_18], rax
0x18008dc55  mov     ecx, 0F03BFh
0x18008dc5a  lea     rax, [rbp+arg_8]
0x18008dc5e  mov     [rbp+var_1C], ecx
0x18008dc61  mov     [rbp+var_8], rax
0x18008dc65  mov     r9, r8; GroupSid
0x18008dc68  lea     rax, [rbp+arg_18]
0x18008dc6c  mov     [rbp+var_C], ecx
0x18008dc6f  mov     [rsp+60h+NewDescriptor], rax; NewDescriptor
0x18008dc74  lea     rcx, [rbp+AceData]; AceData
0x18008dc78  lea     rax, GenericMapping
0x18008dc7f  mov     [rbp+AceData], 0
0x18008dc85  mov     [rsp+60h+GenericMapping], rax; GenericMapping
0x18008dc8a  mov     edx, 2; AceCount
0x18008dc8f  mov     [rsp+60h+IsDirectoryObject], 0; IsDirectoryObject
0x18008dc94  mov     [rbp+var_1E], 0
0x18008dc98  mov     [rbp+var_10], 0
0x18008dc9e  mov     [rbp+var_E], 0
0x18008dca2  call    cs:__imp_RtlCreateUserSecurityObject
0x18008dca9  nop     dword ptr [rax+rax+00h]
0x18008dcae  mov     ebx, eax
0x18008dcb0  or      ebx, 10000000h
0x18008dcb6  jge     short loc_18008DCC4
0x18008dcb8  lea     rdx, aRtlcreateusers; "RtlCreateUserSecurityObject failed: 0x%"...
0x18008dcbf  jmp     loc_18008DBDF
0x18008dcc4  mov     rax, [rbp+arg_18]
0x18008dcc8  mov     [rdi], rax
0x18008dccb  mov     rcx, [rbp+Sid]; Sid
0x18008dccf  test    rcx, rcx
0x18008dcd2  jz      short loc_18008DCE0
0x18008dcd4  call    cs:__imp_RtlFreeSid
0x18008dcdb  nop     dword ptr [rax+rax+00h]
0x18008dce0  mov     rcx, [rbp+arg_8]; Sid
0x18008dce4  test    rcx, rcx
0x18008dce7  jz      short loc_18008DCF5
0x18008dce9  call    cs:__imp_RtlFreeSid
0x18008dcf0  nop     dword ptr [rax+rax+00h]
0x18008dcf5  mov     rcx, [rbp+GroupSid]; pv
0x18008dcf9  test    rcx, rcx
0x18008dcfc  jz      short loc_18008DD0A
0x18008dcfe  call    cs:__imp_CoTaskMemFree
0x18008dd05  nop     dword ptr [rax+rax+00h]
0x18008dd0a  mov     eax, ebx
0x18008dd0c  add     rsp, 60h
0x18008dd10  pop     rdi
0x18008dd11  pop     rbx
0x18008dd12  pop     rbp
0x18008dd13  retn
```
