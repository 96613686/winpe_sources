# NegpIsHardcodedServiceAccount(void *,void *,ulong,_UNICODE_STRING * *,_UNICODE_STRING * *,_UNICODE_STRING * *,ulong *)

- ea: `0x180016abc`
- end: `0x180016e11`
- name: `?NegpIsHardcodedServiceAccount@@YAHPEAX0KPEAPEAU_UNICODE_STRING@@11PEAK@Z`
- size: `853`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, struct _UNICODE_STRING **, struct _UNICODE_STRING **, struct _UNICODE_STRING **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009ac50`

## callees

- `0x18000c300`
- `0x18000d3b0`
- `0x1800163d0`
- `0x180016abc`
- `0x180016f70`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180016b28`
- `ntdll!RtlCompareUnicodeString` at `0x180016b4d`
- `ntdll!RtlCompareUnicodeString` at `0x180016b6e`
- `ntdll!RtlCompareUnicodeString` at `0x180016b8f`
- `ntdll!RtlCompareUnicodeString` at `0x180016cb5`
- `ntdll!RtlCompareUnicodeString` at `0x180016ce7`
- `ntdll!RtlCompareUnicodeString` at `0x180016d12`
- `ntdll!RtlCompareUnicodeString` at `0x180016d3d`
- `ntdll!RtlCompareUnicodeString` at `0x180016d68`
- `ntdll!RtlCompareUnicodeString` at `0x180016d93`
- `ntdll!RtlCompareUnicodeString` at `0x180016b28`
- `ntdll!RtlCompareUnicodeString` at `0x180016b4d`
- `ntdll!RtlCompareUnicodeString` at `0x180016b6e`
- `ntdll!RtlCompareUnicodeString` at `0x180016b8f`
- `ntdll!RtlCompareUnicodeString` at `0x180016cb5`
- `ntdll!RtlCompareUnicodeString` at `0x180016ce7`
- `ntdll!RtlCompareUnicodeString` at `0x180016d12`
- `ntdll!RtlCompareUnicodeString` at `0x180016d3d`
- `ntdll!RtlCompareUnicodeString` at `0x180016d68`
- `ntdll!RtlCompareUnicodeString` at `0x180016d93`

## pseudocode

```c
__int64 __fastcall NegpIsHardcodedServiceAccount(
        void *a1,
        void *a2,
        unsigned int a3,
        struct _RTL_BALANCED_NODE **a4,
        struct _UNICODE_STRING **a5,
        struct _UNICODE_STRING **a6,
        unsigned int *a7)
{
  struct _RTL_BALANCED_NODE **v7; // r15
  struct _RTL_BALANCED_NODE **v9; // rdi
  void *v10; // rdx
  struct _MSV1_0_INTERACTIVE_LOGON *v11; // rsi
  const UNICODE_STRING *v12; // r12
  char *v13; // rbx
  struct _UNICODE_STRING *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  const UNICODE_STRING *p_UserName; // rsi
  void *v19; // rdx
  void *v20; // rdx
  void *v21; // rdx
  struct _MSV1_0_INTERACTIVE_LOGON *v22; // [rsp+68h] [rbp+20h] BYREF

  v7 = (struct _RTL_BALANCED_NODE **)a5;
  v9 = (struct _RTL_BALANCED_NODE **)a6;
  *a4 = 0;
  v22 = 0;
  *v7 = 0;
  *v9 = 0;
  if ( (int)NegpMapLogonRequest(a1, a2, a3, &v22) < 0 )
    goto LABEL_18;
  v11 = v22;
  v12 = (const UNICODE_STRING *)WellKnownSids;
  if ( RtlCompareUnicodeString(&NTAuthorityName, &v22->LogonDomainName, 1u) )
    goto LABEL_27;
  if ( !RtlCompareUnicodeString(&LocalServiceName, &v11->UserName, 1u) )
  {
    v13 = (char *)WellKnownSids + 1264;
    goto LABEL_17;
  }
  if ( !RtlCompareUnicodeString(&NetworkServiceName, &v11->UserName, 1u) )
  {
    v13 = (char *)WellKnownSids + 1312;
    goto LABEL_15;
  }
  if ( RtlCompareUnicodeString(&SystemName, &v11->UserName, 1u) )
  {
    if ( !RtlCompareUnicodeString(&IUserName, &v11->UserName, 1u) )
    {
      v13 = (char *)WellKnownSids + 1360;
      goto LABEL_32;
    }
LABEL_27:
    if ( RtlCompareUnicodeString(v12 + 80, &v11->LogonDomainName, 1u) )
      goto LABEL_18;
    p_UserName = &v11->UserName;
    v13 = (char *)WellKnownSids + 1264;
    if ( RtlCompareUnicodeString((PCUNICODE_STRING)WellKnownSids + 79, p_UserName, 1u) )
    {
      v13 = (char *)WellKnownSids + 1312;
      if ( RtlCompareUnicodeString((PCUNICODE_STRING)WellKnownSids + 82, p_UserName, 1u) )
      {
        v13 = (char *)WellKnownSids + 736;
        if ( !RtlCompareUnicodeString((PCUNICODE_STRING)WellKnownSids + 46, p_UserName, 1u) )
          goto LABEL_7;
        v13 = (char *)WellKnownSids + 1360;
        if ( RtlCompareUnicodeString((PCUNICODE_STRING)WellKnownSids + 85, p_UserName, 1u) )
          goto LABEL_18;
LABEL_32:
        *a7 = 8225;
        goto LABEL_8;
      }
LABEL_15:
      *a7 = 8217;
      goto LABEL_8;
    }
LABEL_17:
    *a7 = 8216;
    goto LABEL_8;
  }
  v13 = (char *)WellKnownSids + 736;
LABEL_7:
  *a7 = 8205;
LABEL_8:
  v14 = (struct _UNICODE_STRING *)LsapAllocate(16);
  *a4 = (struct _RTL_BALANCED_NODE *)v14;
  if ( v14 )
  {
    if ( (int)LsapDuplicateString(v14, v13) >= 0 )
    {
      v15 = LsapAllocate(16);
      *v7 = (struct _RTL_BALANCED_NODE *)v15;
      if ( v15 )
      {
        if ( (int)LsapDuplicateString(v15, &v12[80]) >= 0 )
        {
          v16 = LsapAllocate(16);
          *v9 = (struct _RTL_BALANCED_NODE *)v16;
          if ( v16 )
            return 1;
        }
      }
    }
  }
LABEL_18:
  if ( *v7 )
  {
    LsapSubProv_FreeRoutine((*v7)->Children[1], v10);
    LsapSubProv_FreeRoutine(*v7, v19);
    *v7 = 0;
  }
  if ( *a4 )
  {
    LsapSubProv_FreeRoutine((*a4)->Children[1], v10);
    LsapSubProv_FreeRoutine(*a4, v20);
    *a4 = 0;
  }
  if ( *v9 )
  {
    LsapSubProv_FreeRoutine((*v9)->Children[1], v10);
    LsapSubProv_FreeRoutine(*v9, v21);
    *v9 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180016abc  mov     rax, rsp
0x180016abf  mov     [rax+8], rbx
0x180016ac3  mov     [rax+10h], rbp
0x180016ac7  push    rsi
0x180016ac8  push    rdi
0x180016ac9  push    r12
0x180016acb  push    r14
0x180016acd  push    r15
0x180016acf  sub     rsp, 20h
0x180016ad3  mov     r15, [rsp+48h+arg_20]
0x180016ad8  mov     r14, r9
0x180016adb  mov     rdi, [rsp+48h+arg_28]
0x180016ae0  mov     qword ptr [r9], 0
0x180016ae7  lea     r9, [rax+20h]; struct _MSV1_0_INTERACTIVE_LOGON **
0x180016aeb  mov     qword ptr [rax+20h], 0
0x180016af3  mov     qword ptr [r15], 0
0x180016afa  mov     qword ptr [rdi], 0
0x180016b01  call    ?NegpMapLogonRequest@@YAJPEAX0KPEAPEAU_MSV1_0_INTERACTIVE_LOGON@@@Z; NegpMapLogonRequest(void *,void *,ulong,_MSV1_0_INTERACTIVE_LOGON * *)
0x180016b06  test    eax, eax
0x180016b08  js      loc_180016C7D
0x180016b0e  mov     rsi, [rsp+48h+arg_18]
0x180016b13  lea     rcx, ?NTAuthorityName@@3U_UNICODE_STRING@@A; String1
0x180016b1a  mov     r12, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180016b21  mov     r8b, 1; CaseInsensitive
0x180016b24  lea     rdx, [rsi+8]; String2
0x180016b28  call    cs:__imp_RtlCompareUnicodeString
0x180016b2f  nop     dword ptr [rax+rax+00h]
0x180016b34  test    eax, eax
0x180016b36  jnz     loc_180016CD8
0x180016b3c  lea     rbx, [rsi+18h]
0x180016b40  mov     r8b, 1; CaseInsensitive
0x180016b43  mov     rdx, rbx; String2
0x180016b46  lea     rcx, ?LocalServiceName@@3U_UNICODE_STRING@@A; String1
0x180016b4d  call    cs:__imp_RtlCompareUnicodeString
0x180016b54  nop     dword ptr [rax+rax+00h]
0x180016b59  test    eax, eax
0x180016b5b  jz      loc_180016C5C
0x180016b61  mov     r8b, 1; CaseInsensitive
0x180016b64  lea     rcx, ?NetworkServiceName@@3U_UNICODE_STRING@@A; String1
0x180016b6b  mov     rdx, rbx; String2
0x180016b6e  call    cs:__imp_RtlCompareUnicodeString
0x180016b75  nop     dword ptr [rax+rax+00h]
0x180016b7a  test    eax, eax
0x180016b7c  jz      loc_180016C3B
0x180016b82  mov     r8b, 1; CaseInsensitive
0x180016b85  lea     rcx, ?SystemName@@3U_UNICODE_STRING@@A; String1
0x180016b8c  mov     rdx, rbx; String2
0x180016b8f  call    cs:__imp_RtlCompareUnicodeString
0x180016b96  nop     dword ptr [rax+rax+00h]
0x180016b9b  test    eax, eax
0x180016b9d  jnz     loc_180016CA8
0x180016ba3  mov     rbx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180016baa  add     rbx, 2E0h
0x180016bb1  mov     rax, [rsp+48h+arg_30]
0x180016bb9  mov     dword ptr [rax], 200Dh
0x180016bbf  mov     esi, 10h
0x180016bc4  mov     ecx, esi
0x180016bc6  call    LsapAllocate
0x180016bcb  mov     [r14], rax
0x180016bce  test    rax, rax
0x180016bd1  jz      loc_180016C7D
0x180016bd7  mov     rdx, rbx
0x180016bda  mov     rcx, rax
0x180016bdd  call    LsapDuplicateString
0x180016be2  test    eax, eax
0x180016be4  js      loc_180016C7D
0x180016bea  mov     ecx, esi
0x180016bec  call    LsapAllocate
0x180016bf1  mov     [r15], rax
0x180016bf4  test    rax, rax
0x180016bf7  jz      loc_180016C7D
0x180016bfd  lea     rdx, [r12+500h]
0x180016c05  mov     rcx, rax
0x180016c08  call    LsapDuplicateString
0x180016c0d  test    eax, eax
0x180016c0f  js      short loc_180016C7D
0x180016c11  mov     ecx, esi
0x180016c13  call    LsapAllocate
0x180016c18  mov     [rdi], rax
0x180016c1b  test    rax, rax
0x180016c1e  jz      short loc_180016C7D
0x180016c20  lea     eax, [rsi-0Fh]
0x180016c23  mov     rbx, [rsp+48h+arg_0]
0x180016c28  mov     rbp, [rsp+48h+arg_8]
0x180016c2d  add     rsp, 20h
0x180016c31  pop     r15
0x180016c33  pop     r14
0x180016c35  pop     r12
0x180016c37  pop     rdi
0x180016c38  pop     rsi
0x180016c39  retn
0x180016c3b  mov     rbx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180016c42  add     rbx, 520h
0x180016c49  mov     rax, [rsp+48h+arg_30]
0x180016c51  mov     dword ptr [rax], 2019h
0x180016c57  jmp     loc_180016BBF
0x180016c5c  mov     rbx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180016c63  add     rbx, 4F0h
0x180016c6a  mov     rax, [rsp+48h+arg_30]
0x180016c72  mov     dword ptr [rax], 2018h
0x180016c78  jmp     loc_180016BBF
0x180016c7d  mov     rcx, [r15]
0x180016c80  test    rcx, rcx
0x180016c83  jnz     loc_180016DBA
0x180016c89  mov     rcx, [r14]
0x180016c8c  test    rcx, rcx
0x180016c8f  jnz     loc_180016DD7
0x180016c95  mov     rcx, [rdi]
0x180016c98  test    rcx, rcx
0x180016c9b  jnz     loc_180016DF4
0x180016ca1  xor     eax, eax
0x180016ca3  jmp     loc_180016C23
0x180016ca8  mov     r8b, 1; CaseInsensitive
0x180016cab  lea     rcx, ?IUserName@@3U_UNICODE_STRING@@A; String1
0x180016cb2  mov     rdx, rbx; String2
0x180016cb5  call    cs:__imp_RtlCompareUnicodeString
0x180016cbc  nop     dword ptr [rax+rax+00h]
0x180016cc1  test    eax, eax
0x180016cc3  jnz     short loc_180016CD8
0x180016cc5  mov     rbx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180016ccc  add     rbx, 550h
0x180016cd3  jmp     loc_180016DA7
0x180016cd8  mov     r8b, 1; CaseInsensitive
0x180016cdb  lea     rdx, [rsi+8]; String2
0x180016cdf  lea     rcx, [r12+500h]; String1
0x180016ce7  call    cs:__imp_RtlCompareUnicodeString
0x180016cee  nop     dword ptr [rax+rax+00h]
0x180016cf3  test    eax, eax
0x180016cf5  jnz     short loc_180016C7D
0x180016cf7  mov     rbx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180016cfe  add     rsi, 18h
0x180016d02  add     rbx, 4F0h
0x180016d09  mov     r8b, 1; CaseInsensitive
0x180016d0c  mov     rcx, rbx; String1
0x180016d0f  mov     rdx, rsi; String2
0x180016d12  call    cs:__imp_RtlCompareUnicodeString
0x180016d19  nop     dword ptr [rax+rax+00h]
0x180016d1e  test    eax, eax
0x180016d20  jz      loc_180016C6A
0x180016d26  mov     rbx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180016d2d  mov     r8b, 1; CaseInsensitive
0x180016d30  add     rbx, 520h
0x180016d37  mov     rdx, rsi; String2
0x180016d3a  mov     rcx, rbx; String1
0x180016d3d  call    cs:__imp_RtlCompareUnicodeString
0x180016d44  nop     dword ptr [rax+rax+00h]
0x180016d49  test    eax, eax
0x180016d4b  jz      loc_180016C49
0x180016d51  mov     rbx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180016d58  mov     r8b, 1; CaseInsensitive
0x180016d5b  add     rbx, 2E0h
0x180016d62  mov     rdx, rsi; String2
0x180016d65  mov     rcx, rbx; String1
0x180016d68  call    cs:__imp_RtlCompareUnicodeString
0x180016d6f  nop     dword ptr [rax+rax+00h]
0x180016d74  test    eax, eax
0x180016d76  jz      loc_180016BB1
0x180016d7c  mov     rbx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180016d83  mov     r8b, 1; CaseInsensitive
0x180016d86  add     rbx, 550h
0x180016d8d  mov     rdx, rsi; String2
0x180016d90  mov     rcx, rbx; String1
0x180016d93  call    cs:__imp_RtlCompareUnicodeString
0x180016d9a  nop     dword ptr [rax+rax+00h]
0x180016d9f  test    eax, eax
0x180016da1  jnz     loc_180016C7D
0x180016da7  mov     rax, [rsp+48h+arg_30]
0x180016daf  mov     dword ptr [rax], 2021h
0x180016db5  jmp     loc_180016BBF
0x180016dba  mov     rcx, [rcx+8]; struct _RTL_BALANCED_NODE *
0x180016dbe  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180016dc3  mov     rcx, [r15]; struct _RTL_BALANCED_NODE *
0x180016dc6  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180016dcb  mov     qword ptr [r15], 0
0x180016dd2  jmp     loc_180016C89
0x180016dd7  mov     rcx, [rcx+8]; struct _RTL_BALANCED_NODE *
0x180016ddb  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180016de0  mov     rcx, [r14]; struct _RTL_BALANCED_NODE *
0x180016de3  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180016de8  mov     qword ptr [r14], 0
0x180016def  jmp     loc_180016C95
0x180016df4  mov     rcx, [rcx+8]; struct _RTL_BALANCED_NODE *
0x180016df8  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180016dfd  mov     rcx, [rdi]; struct _RTL_BALANCED_NODE *
0x180016e00  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180016e05  mov     qword ptr [rdi], 0
0x180016e0c  jmp     loc_180016CA1
```
