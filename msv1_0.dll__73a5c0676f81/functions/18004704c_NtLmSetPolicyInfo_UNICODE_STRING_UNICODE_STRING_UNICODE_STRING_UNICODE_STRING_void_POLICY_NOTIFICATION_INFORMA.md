# NtLmSetPolicyInfo(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_POLICY_NOTIFICATION_INFORMATION_CLASS,uchar)

- ea: `0x18004704c`
- end: `0x180047f44`
- name: `?NtLmSetPolicyInfo@@YAJPEAU_UNICODE_STRING@@000PEAXW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@E@Z`
- size: `3832`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *, enum _POLICY_NOTIFICATION_INFORMATION_CLASS, char)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180046dd0`
- `0x18004a1c0`

## callees

- `0x180006c50`
- `0x18000c5d0`
- `0x18000c630`
- `0x18000cba0`
- `0x18000ceb0`
- `0x18000df40`
- `0x180018514`
- `0x180018674`
- `0x18001fefc`
- `0x18002ee7c`
- `0x18002fb50`
- `0x18002fb90`
- `0x180030844`
- `0x18003509c`
- `0x180035de0`
- `0x180040a0c`
- `0x180040bac`
- `0x180046c50`
- `0x18004704c`
- `0x18004ab2c`
- `0x18004ac28`
- `0x18004d7dc`
- `0x18004d878`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800472c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800474e2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800475cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180047662`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800472c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800474e2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800475cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180047662`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800470f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800471bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180047392`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180047534`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800470f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800471bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180047392`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180047534`
- `ntdll!NtQuerySystemTime` at `0x1800470e3`
- `ntdll!NtQuerySystemTime` at `0x1800470e3`
- `ntdll!RtlLengthSid` at `0x1800478d3`
- `ntdll!RtlLengthSid` at `0x180047959`
- `ntdll!RtlLengthSid` at `0x180047986`
- `ntdll!RtlLengthSid` at `0x1800478d3`
- `ntdll!RtlLengthSid` at `0x180047959`
- `ntdll!RtlLengthSid` at `0x180047986`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004713b`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800477bb`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004713b`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800477bb`
- `ntdll!RtlCopySid` at `0x180047969`
- `ntdll!RtlCopySid` at `0x180047969`
- `ntdll!RtlAvlInsertNodeEx` at `0x180047aba`
- `ntdll!RtlAvlInsertNodeEx` at `0x180047aba`
- `ntdll!RtlAvlRemoveNode` at `0x180047a3f`
- `ntdll!RtlAvlRemoveNode` at `0x180047a3f`
- `ntdll!RtlFreeOemString` at `0x180047efa`
- `ntdll!RtlFreeOemString` at `0x180047f11`
- `ntdll!RtlFreeOemString` at `0x180047efa`
- `ntdll!RtlFreeOemString` at `0x180047f11`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x18004730c`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x1800473dd`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x1800476a7`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x18004730c`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x1800473dd`
- `ntdll!RtlUpcaseUnicodeStringToOemString` at `0x1800476a7`
- `ntdll!RtlEqualDomainName` at `0x180047867`
- `ntdll!RtlEqualDomainName` at `0x180047867`
- `ntdll!RtlReleaseResource` at `0x180047e74`
- `ntdll!RtlReleaseResource` at `0x180047ee3`
- `ntdll!RtlReleaseResource` at `0x180047e74`
- `ntdll!RtlReleaseResource` at `0x180047ee3`
- `ntdll!RtlEqualUnicodeString` at `0x180047154`
- `ntdll!RtlEqualUnicodeString` at `0x1800471ee`
- `ntdll!RtlEqualUnicodeString` at `0x180047233`
- `ntdll!RtlEqualUnicodeString` at `0x180047154`
- `ntdll!RtlEqualUnicodeString` at `0x1800471ee`
- `ntdll!RtlEqualUnicodeString` at `0x180047233`
- `ntdll!RtlInitString` at `0x180047339`
- `ntdll!RtlInitString` at `0x1800473ff`
- `ntdll!RtlInitString` at `0x1800476d4`
- `ntdll!RtlInitString` at `0x180047339`
- `ntdll!RtlInitString` at `0x1800473ff`
- `ntdll!RtlInitString` at `0x1800476d4`
- `ntdll!RtlInitUnicodeString` at `0x18004710f`
- `ntdll!RtlInitUnicodeString` at `0x1800471d5`
- `ntdll!RtlInitUnicodeString` at `0x1800472e9`
- `ntdll!RtlInitUnicodeString` at `0x1800473ae`
- `ntdll!RtlInitUnicodeString` at `0x180047505`
- `ntdll!RtlInitUnicodeString` at `0x18004754c`
- `ntdll!RtlInitUnicodeString` at `0x1800475f2`
- `ntdll!RtlInitUnicodeString` at `0x180047688`
- `ntdll!RtlInitUnicodeString` at `0x18004710f`
- `ntdll!RtlInitUnicodeString` at `0x1800471d5`
- `ntdll!RtlInitUnicodeString` at `0x1800472e9`
- `ntdll!RtlInitUnicodeString` at `0x1800473ae`
- `ntdll!RtlInitUnicodeString` at `0x180047505`
- `ntdll!RtlInitUnicodeString` at `0x18004754c`
- `ntdll!RtlInitUnicodeString` at `0x1800475f2`
- `ntdll!RtlInitUnicodeString` at `0x180047688`

## pseudocode

```c
__int64 __fastcall NtLmSetPolicyInfo(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        void *a5,
        enum _POLICY_NOTIFICATION_INFORMATION_CLASS a6,
        char a7)
{
  __int128 v10; // xmm6
  int v12; // ebx
  int v13; // eax
  __int64 v14; // r9
  NTSTATUS updated; // ebx
  _BYTE *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rbx
  unsigned __int64 v19; // rbx
  unsigned int v20; // ecx
  NTSTATUS v21; // ebx
  unsigned int v22; // ecx
  NTSTATUS v23; // ebx
  unsigned int v24; // r8d
  __int64 v25; // rbx
  unsigned __int64 v26; // rbx
  __int64 v27; // rbx
  unsigned __int64 v28; // rbx
  __int64 v29; // rbx
  unsigned __int64 v30; // rbx
  unsigned int v31; // ecx
  NTSTATUS v32; // ebx
  struct _UNICODE_STRING v33; // xmm0
  char v34; // al
  __int128 v35; // xmm1
  int v36; // ecx
  void *v37; // rsi
  void *v38; // r15
  __int64 i; // r14
  __int64 v40; // rdi
  __int64 v41; // r13
  _DWORD *v42; // r12
  __int64 ActiveLogon; // rax
  __int64 v44; // r14
  __int64 v45; // rbx
  int Length; // edi
  int v47; // ebx
  ULONG v48; // eax
  _DWORD *v49; // rax
  void *v50; // rbx
  ULONG v51; // eax
  __int64 v52; // rdx
  __int64 v53; // r8
  PSID v54; // rbx
  void *v55; // rbx
  __int64 v56; // rcx
  _QWORD *v57; // rax
  __int64 v58; // r8
  __int64 v59; // rax
  struct _RTL_BALANCED_NODE *v60; // rbx
  struct _RTL_BALANCED_NODE *v61; // rax
  int PrimaryCredential; // eax
  __int64 v63; // rdx
  _OWORD *v64; // rax
  _OWORD *v65; // rcx
  __int128 v66; // xmm1
  int v67; // eax
  DWORD nSize[2]; // [rsp+58h] [rbp-B0h] BYREF
  PSID DestinationSid; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int Size; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int Size_4; // [rsp+6Ch] [rbp-9Ch]
  _OWORD *v73; // [rsp+70h] [rbp-98h] BYREF
  __int128 v74; // [rsp+78h] [rbp-90h] BYREF
  int v75; // [rsp+88h] [rbp-80h]
  _OWORD *v76; // [rsp+90h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-70h] BYREF
  DWORD v78; // [rsp+A8h] [rbp-60h] BYREF
  struct _STRING OemString; // [rsp+B0h] [rbp-58h] BYREF
  struct _STRING v80; // [rsp+C0h] [rbp-48h] BYREF
  WCHAR Buffer[264]; // [rsp+D8h] [rbp-30h] BYREF

  *(_QWORD *)&OemString.Length = 0;
  *(_QWORD *)&v80.Length = 0;
  OemString.Buffer = 0;
  v10 = 0;
  v80.Buffer = 0;
  v74 = 0;
  memset_0(Buffer, 0, 0x202u);
  v78 = 16;
  DestinationString = 0;
  nSize[0] = 257;
  NtQuerySystemTime(&SystemTime);
  if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, nSize) )
    Buffer[0] = 0;
  v12 = 0;
  RtlInitUnicodeString(&DestinationString, Buffer);
  if ( !a7 )
  {
    v13 = SsprQueryTreeName(&v74);
    v10 = v74;
    v12 = v13;
  }
  RtlAcquireResourceExclusive(&NtLmGlobalCritSect, 1u);
  if ( a7 )
  {
LABEL_8:
    v12 = NtLmDuplicateUnicodeString(&NtLmGlobalUnicodeDnsHostNameString, &DestinationString);
    if ( a7 )
      goto LABEL_13;
    goto LABEL_9;
  }
  if ( !RtlEqualUnicodeString(&NtLmGlobalUnicodeDnsHostNameString, &DestinationString, 1u) )
  {
    ((void (__fastcall *)(PWSTR))LsaFunctions->FreePrivateHeap)(NtLmGlobalUnicodeDnsHostNameString.Buffer);
    goto LABEL_8;
  }
LABEL_9:
  if ( v12 >= 0 )
  {
    if ( *((_QWORD *)&NtLmGlobalUnicodeDnsTreeName + 1) )
      NtLmFree(*((_QWORD *)&NtLmGlobalUnicodeDnsTreeName + 1));
    NtLmGlobalUnicodeDnsTreeName = v10;
  }
LABEL_13:
  nSize[0] = 257;
  if ( !GetComputerNameExW(ComputerNamePhysicalDnsHostname, Buffer, nSize) )
    Buffer[0] = 0;
  RtlInitUnicodeString(&DestinationString, Buffer);
  if ( !a7 )
  {
    if ( RtlEqualUnicodeString(&NtLmGlobalUnicodePhysicalDnsHostNameString, &DestinationString, 1u) )
      goto LABEL_19;
    ((void (__fastcall *)(PWSTR))LsaFunctions->FreePrivateHeap)(NtLmGlobalUnicodePhysicalDnsHostNameString.Buffer);
  }
  NtLmDuplicateUnicodeString(&NtLmGlobalUnicodePhysicalDnsHostNameString, &DestinationString);
LABEL_19:
  NtLmGlobalUsePhysicalNames = RtlEqualUnicodeString(
                                 &NtLmGlobalUnicodeDnsHostNameString,
                                 &NtLmGlobalUnicodePhysicalDnsHostNameString,
                                 1u) == 0;
  if ( !a7 )
  {
    if ( a6 != PolicyNotifyDnsDomainInformation )
      goto LABEL_76;
    goto LABEL_42;
  }
  if ( !a2 || !a2->Buffer )
    goto LABEL_32;
  v14 = a2->Length >> 1;
  if ( (unsigned __int64)a2->Length + 2 <= 0x20 )
  {
    v18 = (unsigned int)v14;
    _o_wcsncpy_s(&NtLmGlobalUnicodeComputerName, 16);
    v19 = 2 * v18;
    if ( v19 >= 0x20 )
      goto LABEL_78;
    *(WCHAR *)((char *)&NtLmGlobalUnicodeComputerName + v19) = 0;
    RtlInitUnicodeString(&NtLmGlobalUnicodeComputerNameString, &NtLmGlobalUnicodeComputerName);
    OemString = NtLmGlobalOemComputerNameString;
    v21 = RtlUpcaseUnicodeStringToOemString(&NtLmGlobalOemComputerNameString, &NtLmGlobalUnicodeComputerNameString, 1u);
    if ( v21 < 0 )
    {
      OemString.Buffer = 0;
      NtLmGetRandomOemName(v20, NtLmGlobalOemComputerName);
      RtlInitString(&NtLmGlobalOemComputerNameString, NtLmGlobalOemComputerName);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_33:
        if ( NtLmGlobalUsePhysicalNames )
        {
          if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, &NtLmGlobalUnicodePhysicalComputerName, &v78) )
          {
            RtlInitUnicodeString(&NtLmGlobalUnicodePhysicalComputerNameString, &NtLmGlobalUnicodePhysicalComputerName);
            *(_DWORD *)&NtLmGlobalOemPhysicalComputerNameString.Length = 0x100000;
            NtLmGlobalOemPhysicalComputerNameString.Buffer = NtLmGlobalOemPhysicalComputerName;
            v23 = RtlUpcaseUnicodeStringToOemString(
                    &NtLmGlobalOemPhysicalComputerNameString,
                    &NtLmGlobalUnicodePhysicalComputerNameString,
                    0);
            if ( v23 >= 0 )
            {
LABEL_42:
              v16 = WPP_GLOBAL_Control;
              goto LABEL_43;
            }
            NtLmGetRandomOemName(v22, NtLmGlobalOemPhysicalComputerName);
            RtlInitString(&NtLmGlobalOemPhysicalComputerNameString, NtLmGlobalOemPhysicalComputerName);
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_Ds(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                (unsigned int)WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                v23,
                (__int64)NtLmGlobalOemComputerName);
              goto LABEL_42;
            }
LABEL_43:
            if ( a1 && a1->Buffer )
            {
              v24 = a1->Length >> 1;
              if ( (unsigned __int64)a1->Length + 2 > 0x200 )
              {
                updated = -1073741534;
                if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
                  goto LABEL_153;
                v17 = 18;
                goto LABEL_49;
              }
              v25 = v24;
              _o_wcsncpy_s(&NtLmGlobalUnicodeDnsComputerName, 256);
              v26 = 2 * v25;
              if ( v26 >= 0x200 )
                goto LABEL_78;
              *(WCHAR *)((char *)&NtLmGlobalUnicodeDnsComputerName + v26) = 0;
              RtlInitUnicodeString(&NtLmGlobalUnicodeDnsComputerNameString, &NtLmGlobalUnicodeDnsComputerName);
              v16 = WPP_GLOBAL_Control;
            }
            nSize[0] = 256;
            if ( NtLmGlobalUsePhysicalNames )
            {
              if ( GetComputerNameExW(
                     ComputerNamePhysicalDnsFullyQualified,
                     &NtLmGlobalUnicodePhysicalDnsComputerName,
                     nSize) )
              {
                RtlInitUnicodeString(
                  &NtLmGlobalUnicodePhysicalDnsComputerNameString,
                  &NtLmGlobalUnicodePhysicalDnsComputerName);
                v16 = WPP_GLOBAL_Control;
LABEL_57:
                if ( a3 && a3->Buffer )
                {
                  v24 = a3->Length >> 1;
                  if ( (unsigned __int64)a3->Length + 2 > 0x200 )
                  {
                    updated = -1073741534;
                    if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
                      goto LABEL_153;
                    v17 = 19;
                    goto LABEL_49;
                  }
                  v27 = v24;
                  _o_wcsncpy_s(&NtLmGlobalUnicodeDnsDomainName, 256);
                  v28 = 2 * v27;
                  if ( v28 >= 0x200 )
                    goto LABEL_78;
                  *(WCHAR *)((char *)&NtLmGlobalUnicodeDnsDomainName + v28) = 0;
                  RtlInitUnicodeString(&NtLmGlobalUnicodeDnsDomainNameString, &NtLmGlobalUnicodeDnsDomainName);
                  v16 = WPP_GLOBAL_Control;
                }
                if ( !a4 || !a4->Buffer )
                  goto LABEL_76;
                v24 = a4->Length >> 1;
                if ( (unsigned __int64)a4->Length + 2 > 0x200 )
                {
                  updated = -1073741562;
                  if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
                    goto LABEL_153;
                  v17 = 20;
LABEL_49:
                  v14 = v24;
                  goto LABEL_26;
                }
                v29 = v24;
                _o_wcsncpy_s(&NtLmGlobalUnicodePrimaryDomainName, 256);
                v30 = 2 * v29;
                if ( v30 < 0x200 )
                {
                  *(WCHAR *)((char *)&NtLmGlobalUnicodePrimaryDomainName + v30) = 0;
                  RtlInitUnicodeString(&NtLmGlobalUnicodePrimaryDomainNameString, &NtLmGlobalUnicodePrimaryDomainName);
                  v80 = NtLmGlobalOemPrimaryDomainNameString;
                  v32 = RtlUpcaseUnicodeStringToOemString(
                          &NtLmGlobalOemPrimaryDomainNameString,
                          &NtLmGlobalUnicodePrimaryDomainNameString,
                          1u);
                  if ( v32 < 0 )
                  {
                    v80.Buffer = 0;
                    NtLmGetRandomOemName(v31, NtLmGlobalOemPrimaryDomainName);
                    RtlInitString(&NtLmGlobalOemPrimaryDomainNameString, NtLmGlobalOemPrimaryDomainName);
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_Ds(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        21,
                        (unsigned int)WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                        v32,
                        (__int64)NtLmGlobalOemPrimaryDomainName);
                    }
                  }
LABEL_76:
                  if ( a5 )
                  {
                    v33 = NtLmGlobalUnicodePrimaryDomainNameString;
                    v75 = 1;
                    v34 = 1;
                    v35 = (__int128)NtLmGlobalOemPrimaryDomainNameString;
                    v36 = 0x10000;
                  }
                  else
                  {
                    v33 = NtLmGlobalUnicodeComputerNameString;
                    v75 = 0;
                    v34 = 0;
                    v35 = (__int128)NtLmGlobalOemComputerNameString;
                    v36 = 0x20000;
                  }
                  NtLmGlobalOemTargetName = v35;
                  NtLmGlobalTargetFlags = v36;
                  NtLmGlobalUnicodeTargetName = v33;
                  NtLmGlobalDomainJoined = v34;
                  updated = SsprUpdateTargetInfo();
                  if ( updated >= 0 && !a7 )
                  {
                    v37 = 0;
                    *((LUID *)&v74 + 1) = NtLmGlobalLuidMachineLogon;
                    v38 = 0;
                    *(_QWORD *)&v74 = 996;
                    v73 = 0;
                    Size = 0;
                    v76 = 0;
                    nSize[1] = 0;
                    RtlAcquireResourceExclusive(&NlpActiveLogonLock, 1u);
                    for ( i = 0; ; i = Size_4 + 1 )
                    {
                      v40 = 0;
                      Size_4 = i;
                      if ( (unsigned int)i >= 2 )
                        break;
                      if ( v37 )
                      {
                        memset_0(v37, 0, Size);
                        ((void (__fastcall *)(void *))LsaFunctions->FreeLsaHeap)(v37);
                        v37 = 0;
                        v73 = 0;
                        Size = 0;
                      }
                      if ( v38 )
                      {
                        memset_0(v38, 0, nSize[1]);
                        ((void (__fastcall *)(void *))LsaFunctions->FreeLsaHeap)(v38);
                        v38 = 0;
                        nSize[1] = 0;
                        v76 = 0;
                      }
                      v41 = (unsigned int)i;
                      v42 = (_DWORD *)&v74 + 2 * i;
                      ActiveLogon = NlpFindActiveLogon(v42);
                      v44 = ActiveLogon;
                      if ( ActiveLogon )
                      {
                        v45 = ActiveLogon + 88;
                        if ( RtlEqualDomainName(
                               (PUNICODE_STRING)(ActiveLogon + 88),
                               &NtLmGlobalUnicodePrimaryDomainNameString) )
                        {
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                          {
                            WPP_SF_Z(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              22,
                              WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                              v45);
                          }
                          updated = 0;
                          break;
                        }
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                        {
                          WPP_SF_DDZZ(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            23,
                            (unsigned int)WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                            *(_DWORD *)(v44 + 48),
                            *(_DWORD *)(v44 + 44),
                            v45,
                            (__int64)&NtLmGlobalUnicodePrimaryDomainNameString);
                        }
                        Length = NtLmGlobalUnicodePrimaryDomainNameString.Length;
                        v47 = *(unsigned __int16 *)(v44 + 72);
                        v48 = Length
                            + 142
                            + v47
                            + *(unsigned __int16 *)(v44 + 104)
                            + ((RtlLengthSid(*(PSID *)(v44 + 64)) + 7) & 0xFFFFFFF8);
                        LODWORD(DestinationSid) = v48 + ((v48 + 7) & 0xFFFFFFF8) + *(_DWORD *)(v44 + 124);
                        v49 = (_DWORD *)((__int64 (__fastcall *)(_QWORD))qword_180088390)((unsigned int)DestinationSid);
                        v40 = (__int64)v49;
                        if ( !v49 )
                        {
                          updated = -1073741801;
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          {
                            WPP_SF_dd(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              24,
                              WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                              Size_4,
                              (_DWORD)DestinationSid);
                          }
                          break;
                        }
                        v49[10] = 1296847950;
                        v49[11] = *(_DWORD *)(v44 + 44);
                        v49[12] = *(_DWORD *)(v44 + 48);
                        v49[30] = *(_DWORD *)(v44 + 120);
                        v49[14] = *(_DWORD *)(v44 + 56);
                        v50 = *(void **)(v44 + 64);
                        DestinationSid = (PSID)(((unsigned __int64)v49 + 139) & 0xFFFFFFFFFFFFFFFCuLL);
                        v51 = RtlLengthSid(v50);
                        updated = RtlCopySid(v51, DestinationSid, v50);
                        if ( updated < 0 )
                        {
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          {
                            WPP_SF_DDDqqq(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              v52,
                              v53,
                              *((unsigned int *)&v74 + 2 * v41 + 1),
                              *v42,
                              updated,
                              v40,
                              v44,
                              DestinationSid);
                          }
                          break;
                        }
                        v54 = DestinationSid;
                        *(_QWORD *)(v40 + 64) = DestinationSid;
                        DestinationSid = (PSID)(((unsigned __int64)v54 + RtlLengthSid(*(PSID *)(v44 + 64)) + 1)
                                              & 0xFFFFFFFFFFFFFFFEuLL);
                        NlpPutString(v40 + 72, v44 + 72, &DestinationSid);
                        NlpPutString(v40 + 88, &NtLmGlobalUnicodePrimaryDomainNameString, &DestinationSid);
                        NlpPutString(v40 + 104, v44 + 104, &DestinationSid);
                        *(_DWORD *)(v40 + 52) = *(_DWORD *)(v44 + 52);
                        if ( *(_DWORD *)(v44 + 124) )
                        {
                          v55 = (void *)(((unsigned __int64)DestinationSid + 7) & 0xFFFFFFFFFFFFFFF8uLL);
                          memcpy_0(v55, *(const void **)(v44 + 128), *(unsigned int *)(v44 + 124));
                          *(_QWORD *)(v40 + 128) = v55;
                          *(_DWORD *)(v40 + 124) = *(_DWORD *)(v44 + 124);
                        }
                        v56 = *(_QWORD *)v44;
                        if ( *(_QWORD *)(*(_QWORD *)v44 + 8LL) != v44
                          || (v57 = *(_QWORD **)(v44 + 8), *v57 != v44)
                          || (*v57 = v56,
                              *(_QWORD *)(v56 + 8) = v57,
                              RtlAvlRemoveNode(&NlpActiveLogonTable, v44 + 16),
                              v59 = NlpActiveLogonListAnchor,
                              *(__int64 **)(NlpActiveLogonListAnchor + 8) != &NlpActiveLogonListAnchor) )
                        {
                          __fastfail(3u);
                        }
                        *(_QWORD *)v40 = NlpActiveLogonListAnchor;
                        LOBYTE(v58) = 0;
                        *(_QWORD *)(v40 + 8) = &NlpActiveLogonListAnchor;
                        *(_QWORD *)(v59 + 8) = v40;
                        v60 = NlpActiveLogonTable;
                        NlpActiveLogonListAnchor = v40;
                        if ( NlpActiveLogonTable )
                        {
                          while ( 1 )
                          {
                            if ( (int)NlpActiveLogonCompare((void *)(v40 + 44), v60) < 0 )
                            {
                              v61 = v60->Children[0];
                              if ( !v60->Children[0] )
                              {
                                LOBYTE(v58) = 0;
                                break;
                              }
                            }
                            else
                            {
                              v61 = v60->Children[1];
                              if ( !v61 )
                              {
                                LOBYTE(v58) = 1;
                                break;
                              }
                            }
                            v60 = v61;
                          }
                        }
                        RtlAvlInsertNodeEx(&NlpActiveLogonTable, v60, v58, v40 + 16);
                        ((void (__fastcall *)(__int64))qword_180088398)(v44);
                        PrimaryCredential = NlpGetPrimaryCredential(v42, &v73, &Size);
                        if ( PrimaryCredential >= 0 )
                        {
                          v40 = 0;
                          updated = NlpMakePrimaryCredentialFromPasswordOrOwf(
                                      (unsigned int)&NtLmGlobalUnicodePrimaryDomainNameString,
                                      (unsigned int)&NtLmGlobalUnicodeComputerNameString,
                                      0,
                                      0,
                                      (__int64)&NtLmGlobalUnicodeComputerNameString,
                                      v75,
                                      (__int64)&v76,
                                      (__int64)&nSize[1]);
                          if ( updated < 0 )
                          {
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                            {
                              WPP_SF_DDd(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                27,
                                WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                                *((unsigned int *)&v74 + 2 * v41 + 1),
                                *v42,
                                updated);
                            }
                            v37 = v73;
                            v38 = v76;
                            break;
                          }
                          v38 = v76;
                          v63 = 2;
                          v37 = v73;
                          v64 = v76 + 2;
                          v65 = v73 + 2;
                          do
                          {
                            *v64 = *v65;
                            v64[1] = v65[1];
                            v64[2] = v65[2];
                            v64[3] = v65[3];
                            v64[4] = v65[4];
                            v64[5] = v65[5];
                            v64[6] = v65[6];
                            v66 = v65[7];
                            v65 += 8;
                            v64[7] = v66;
                            v64 += 8;
                            --v63;
                          }
                          while ( v63 );
                          *v64 = *v65;
                          v64[1] = v65[1];
                          v64[2] = v65[2];
                          v64[3] = v65[3];
                          v64[4] = v65[4];
                          v64[5] = v65[5];
                          v67 = NlpDeletePrimaryCredential(v42);
                          if ( v67 >= 0 )
                          {
                            updated = NlpAddPrimaryCredential(v42, v38, nSize[1]);
                            if ( updated < 0 )
                            {
                              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                              {
                                WPP_SF_DDd(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  29,
                                  WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                                  *((unsigned int *)&v74 + 2 * v41 + 1),
                                  *v42,
                                  updated);
                              }
                              break;
                            }
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                            {
                              WPP_SF_dd(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                30,
                                WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                                *((unsigned int *)&v74 + 2 * v41 + 1),
                                *v42);
                            }
                            ++dword_180089C88;
                          }
                          else
                          {
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                            {
                              WPP_SF_DDd(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                28,
                                WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                                *((unsigned int *)&v74 + 2 * v41 + 1),
                                *v42,
                                v67);
                            }
                            updated = 0;
                          }
                        }
                        else
                        {
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                          {
                            WPP_SF_DDd(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              26,
                              WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                              *((unsigned int *)&v74 + 2 * v41 + 1),
                              *v42,
                              PrimaryCredential);
                          }
                          v37 = v73;
                          updated = 0;
                        }
                      }
                      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                      {
                        WPP_SF_dd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          31,
                          WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
                          *((unsigned int *)&v74 + 2 * v41 + 1),
                          *v42);
                      }
                    }
                    RtlReleaseResource(&NlpActiveLogonLock);
                    if ( v37 )
                    {
                      memset_0(v37, 0, Size);
                      ((void (__fastcall *)(void *))LsaFunctions->FreeLsaHeap)(v37);
                    }
                    if ( v38 )
                    {
                      memset_0(v38, 0, nSize[1]);
                      ((void (__fastcall *)(void *))LsaFunctions->FreeLsaHeap)(v38);
                    }
                    if ( v40 )
                      ((void (__fastcall *)(__int64))qword_180088398)(v40);
                  }
                  goto LABEL_153;
                }
LABEL_78:
                _report_rangecheckfailure();
              }
              v16 = WPP_GLOBAL_Control;
            }
            NtLmGlobalUnicodePhysicalDnsComputerNameString = NtLmGlobalUnicodeDnsComputerNameString;
            goto LABEL_57;
          }
          v16 = WPP_GLOBAL_Control;
        }
        NtLmGlobalUnicodePhysicalComputerNameString = NtLmGlobalUnicodeComputerNameString;
        NtLmGlobalOemPhysicalComputerNameString = NtLmGlobalOemComputerNameString;
        goto LABEL_43;
      }
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids,
        v21,
        (__int64)NtLmGlobalOemComputerName);
    }
LABEL_32:
    v16 = WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  updated = -1073741534;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = 15;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids, v14);
  }
LABEL_153:
  RtlReleaseResource(&NtLmGlobalCritSect);
  if ( OemString.Buffer != NtLmGlobalOemComputerName )
    RtlFreeOemString(&OemString);
  if ( v80.Buffer != NtLmGlobalOemPrimaryDomainName )
    RtlFreeOemString(&v80);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18004704c  mov     rax, rsp
0x18004704f  push    rbp
0x180047050  push    rbx
0x180047051  push    rsi
0x180047052  push    rdi
0x180047053  push    r12
0x180047055  push    r13
0x180047057  push    r14
0x180047059  push    r15
0x18004705b  lea     rbp, [rax-248h]
0x180047062  sub     rsp, 308h
0x180047069  movaps  xmmword ptr [rax-58h], xmm6
0x18004706d  mov     rax, cs:__security_cookie
0x180047074  xor     rax, rsp
0x180047077  mov     [rbp+240h+var_60], rax
0x18004707e  mov     r15, r8
0x180047081  mov     qword ptr [rbp+240h+OemString.Length], 0
0x180047089  mov     rsi, rdx
0x18004708c  mov     qword ptr [rbp+240h+var_288.Length], 0
0x180047094  mov     r14, rcx
0x180047097  mov     [rbp+240h+OemString.Buffer], 0
0x18004709f  xorps   xmm6, xmm6
0x1800470a2  mov     [rbp+240h+var_288.Buffer], 0
0x1800470aa  xor     edx, edx; Val
0x1800470ac  lea     rcx, [rbp+240h+Buffer]; void *
0x1800470b0  mov     r8d, 202h; Size
0x1800470b6  mov     r13, r9
0x1800470b9  movups  [rsp+340h+var_2D8+8], xmm6
0x1800470be  call    memset_0
0x1800470c3  xorps   xmm0, xmm0
0x1800470c6  mov     [rbp+240h+var_2A0], 10h
0x1800470cd  mov     r12d, 101h
0x1800470d3  lea     rcx, SystemTime; SystemTime
0x1800470da  movups  xmmword ptr [rbp+240h+DestinationString.Length], xmm0
0x1800470de  mov     [rsp+340h+nSize], r12d
0x1800470e3  call    cs:__imp_NtQuerySystemTime
0x1800470e9  lea     r8, [rsp+340h+nSize]; nSize
0x1800470ee  mov     ecx, 1; NameType
0x1800470f3  lea     rdx, [rbp+240h+Buffer]; lpBuffer
0x1800470f7  call    cs:__imp_GetComputerNameExW
0x1800470fd  test    eax, eax
0x1800470ff  jnz     short loc_180047105
0x180047101  mov     [rbp+240h+Buffer], ax
0x180047105  lea     rdx, [rbp+240h+Buffer]; SourceString
0x180047109  xor     ebx, ebx
0x18004710b  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x18004710f  call    cs:__imp_RtlInitUnicodeString
0x180047115  mov     dil, [rbp+240h+arg_30]
0x18004711c  test    dil, dil
0x18004711f  jnz     short loc_180047132
0x180047121  lea     rcx, [rsp+340h+var_2D8+8]
0x180047126  call    SsprQueryTreeName
0x18004712b  movups  xmm6, [rsp+340h+var_2D8+8]
0x180047130  mov     ebx, eax
0x180047132  mov     dl, 1; Wait
0x180047134  lea     rcx, NtLmGlobalCritSect; Resource
0x18004713b  call    cs:__imp_RtlAcquireResourceExclusive
0x180047141  lea     rdx, [rbp+240h+DestinationString]; String2
0x180047145  test    dil, dil
0x180047148  jnz     short loc_18004717C
0x18004714a  mov     r8b, 1; CaseInsensitive
0x18004714d  lea     rcx, NtLmGlobalUnicodeDnsHostNameString; String1
0x180047154  call    cs:__imp_RtlEqualUnicodeString
0x18004715a  test    al, al
0x18004715c  jnz     short loc_18004718F
0x18004715e  mov     rax, cs:LsaFunctions
0x180047165  mov     rcx, cs:NtLmGlobalUnicodeDnsHostNameString.Buffer
0x18004716c  mov     rax, [rax+188h]
0x180047173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047178  lea     rdx, [rbp+240h+DestinationString]
0x18004717c  lea     rcx, NtLmGlobalUnicodeDnsHostNameString
0x180047183  call    NtLmDuplicateUnicodeString
0x180047188  mov     ebx, eax
0x18004718a  test    dil, dil
0x18004718d  jnz     short loc_1800471AC
0x18004718f  test    ebx, ebx
0x180047191  js      short loc_1800471AC
0x180047193  mov     rcx, qword ptr cs:NtLmGlobalUnicodeDnsTreeName+8
0x18004719a  test    rcx, rcx
0x18004719d  jz      short loc_1800471A4
0x18004719f  call    NtLmFree
0x1800471a4  movdqu  cs:NtLmGlobalUnicodeDnsTreeName, xmm6
0x1800471ac  lea     r8, [rsp+340h+nSize]; nSize
0x1800471b1  mov     [rsp+340h+nSize], r12d
0x1800471b6  lea     rdx, [rbp+240h+Buffer]; lpBuffer
0x1800471ba  mov     ecx, 5; NameType
0x1800471bf  call    cs:__imp_GetComputerNameExW
0x1800471c5  test    eax, eax
0x1800471c7  jnz     short loc_1800471CD
0x1800471c9  mov     [rbp+240h+Buffer], ax
0x1800471cd  lea     rdx, [rbp+240h+Buffer]; SourceString
0x1800471d1  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x1800471d5  call    cs:__imp_RtlInitUnicodeString
0x1800471db  lea     rdx, [rbp+240h+DestinationString]; String2
0x1800471df  lea     rcx, NtLmGlobalUnicodePhysicalDnsHostNameString; String1
0x1800471e6  test    dil, dil
0x1800471e9  jnz     short loc_18004721D
0x1800471eb  mov     r8b, 1; CaseInsensitive
0x1800471ee  call    cs:__imp_RtlEqualUnicodeString
0x1800471f4  test    al, al
0x1800471f6  jnz     short loc_180047222
0x1800471f8  mov     rax, cs:LsaFunctions
0x1800471ff  mov     rcx, cs:NtLmGlobalUnicodePhysicalDnsHostNameString.Buffer
0x180047206  mov     rax, [rax+188h]
0x18004720d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047212  lea     rdx, [rbp+240h+DestinationString]
0x180047216  lea     rcx, NtLmGlobalUnicodePhysicalDnsHostNameString
0x18004721d  call    NtLmDuplicateUnicodeString
0x180047222  mov     r8b, 1; CaseInsensitive
0x180047225  lea     rdx, NtLmGlobalUnicodePhysicalDnsHostNameString; String2
0x18004722c  lea     rcx, NtLmGlobalUnicodeDnsHostNameString; String1
0x180047233  call    cs:__imp_RtlEqualUnicodeString
0x180047239  test    al, al
0x18004723b  lea     r12, WPP_GLOBAL_Control
0x180047242  setz    cs:NtLmGlobalUsePhysicalNames
0x180047249  test    dil, dil
0x18004724c  jz      loc_180047464
0x180047252  test    rsi, rsi
0x180047255  jz      loc_18004736E
0x18004725b  mov     r8, [rsi+8]
0x18004725f  test    r8, r8
0x180047262  jz      loc_18004736E
0x180047268  movzx   eax, word ptr [rsi]
0x18004726b  mov     r9d, eax
0x18004726e  add     rax, 2
0x180047272  shr     r9d, 1
0x180047275  cmp     rax, 20h ; ' '
0x180047279  jbe     short loc_1800472B4
0x18004727b  mov     ebx, 0C0000122h
0x180047280  mov     rcx, cs:WPP_GLOBAL_Control
0x180047287  cmp     rcx, r12
0x18004728a  jz      loc_180047EDC
0x180047290  test    byte ptr [rcx+1Ch], 1
0x180047294  jz      loc_180047EDC
0x18004729a  mov     edx, 0Fh
0x18004729f  mov     rcx, [rcx+10h]
0x1800472a3  lea     r8, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x1800472aa  call    WPP_SF_d
0x1800472af  jmp     loc_180047EDC
0x1800472b4  lea     rsi, NtLmGlobalUnicodeComputerName
0x1800472bb  mov     ebx, r9d
0x1800472be  mov     rcx, rsi
0x1800472c1  mov     edx, 10h
0x1800472c6  call    cs:__imp__o_wcsncpy_s
0x1800472cc  add     rbx, rbx
0x1800472cf  cmp     rbx, 20h ; ' '
0x1800472d3  jnb     loc_180047731
0x1800472d9  xor     eax, eax
0x1800472db  lea     rcx, NtLmGlobalUnicodeComputerNameString; DestinationString
0x1800472e2  mov     rdx, rsi; SourceString
0x1800472e5  mov     [rbx+rsi], ax
0x1800472e9  call    cs:__imp_RtlInitUnicodeString
0x1800472ef  movups  xmm0, xmmword ptr cs:NtLmGlobalOemComputerNameString.Length
0x1800472f6  mov     r8b, 1; AllocateDestinationString
0x1800472f9  lea     rdx, NtLmGlobalUnicodeComputerNameString; SourceString
0x180047300  lea     rcx, NtLmGlobalOemComputerNameString; DestinationString
0x180047307  movdqu  xmmword ptr [rbp+240h+OemString.Length], xmm0
0x18004730c  call    cs:__imp_RtlUpcaseUnicodeStringToOemString
0x180047312  mov     ebx, eax
0x180047314  test    eax, eax
0x180047316  jns     short loc_18004736E
0x180047318  lea     rsi, NtLmGlobalOemComputerName
0x18004731f  mov     [rbp+240h+OemString.Buffer], 0
0x180047327  mov     rdx, rsi; char *
0x18004732a  call    ?NtLmGetRandomOemName@@YAXKPEAD@Z; NtLmGetRandomOemName(ulong,char *)
0x18004732f  mov     rdx, rsi; SourceString
0x180047332  lea     rcx, NtLmGlobalOemComputerNameString; DestinationString
0x180047339  call    cs:__imp_RtlInitString
0x18004733f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047346  cmp     rcx, r12
0x180047349  jz      short loc_180047375
0x18004734b  test    byte ptr [rcx+1Ch], 1
0x18004734f  jz      short loc_180047375
0x180047351  mov     rcx, [rcx+10h]
0x180047355  lea     r8, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x18004735c  mov     edx, 10h
0x180047361  mov     [rsp+340h+var_320], rsi
0x180047366  mov     r9d, ebx
0x180047369  call    WPP_SF_Ds
0x18004736e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047375  cmp     cs:NtLmGlobalUsePhysicalNames, 0
0x18004737c  jz      loc_180047444
0x180047382  lea     r8, [rbp+240h+var_2A0]; nSize
0x180047386  mov     ecx, 4; NameType
0x18004738b  lea     rdx, NtLmGlobalUnicodePhysicalComputerName; lpBuffer
0x180047392  call    cs:__imp_GetComputerNameExW
0x180047398  test    eax, eax
0x18004739a  jz      loc_18004743D
0x1800473a0  lea     rdx, NtLmGlobalUnicodePhysicalComputerName; SourceString
0x1800473a7  lea     rcx, NtLmGlobalUnicodePhysicalComputerNameString; DestinationString
0x1800473ae  call    cs:__imp_RtlInitUnicodeString
0x1800473b4  lea     rsi, NtLmGlobalOemPhysicalComputerName
0x1800473bb  mov     dword ptr cs:NtLmGlobalOemPhysicalComputerNameString.Length, 100000h
0x1800473c5  xor     r8d, r8d; AllocateDestinationString
0x1800473c8  mov     cs:NtLmGlobalOemPhysicalComputerNameString.Buffer, rsi
0x1800473cf  lea     rdx, NtLmGlobalUnicodePhysicalComputerNameString; SourceString
0x1800473d6  lea     rcx, NtLmGlobalOemPhysicalComputerNameString; DestinationString
0x1800473dd  call    cs:__imp_RtlUpcaseUnicodeStringToOemString
0x1800473e3  mov     ebx, eax
0x1800473e5  test    eax, eax
0x1800473e7  jns     loc_180047471
0x1800473ed  mov     rdx, rsi; char *
0x1800473f0  call    ?NtLmGetRandomOemName@@YAXKPEAD@Z; NtLmGetRandomOemName(ulong,char *)
0x1800473f5  mov     rdx, rsi; SourceString
0x1800473f8  lea     rcx, NtLmGlobalOemPhysicalComputerNameString; DestinationString
0x1800473ff  call    cs:__imp_RtlInitString
0x180047405  mov     rcx, cs:WPP_GLOBAL_Control
0x18004740c  cmp     rcx, r12
0x18004740f  jz      short loc_180047478
0x180047411  test    byte ptr [rcx+1Ch], 1
0x180047415  jz      short loc_180047478
0x180047417  mov     rcx, [rcx+10h]
0x18004741b  lea     rax, NtLmGlobalOemComputerName
0x180047422  mov     edx, 11h
0x180047427  mov     [rsp+340h+var_320], rax
0x18004742c  mov     r9d, ebx
0x18004742f  lea     r8, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x180047436  call    WPP_SF_Ds
0x18004743b  jmp     short loc_180047471
0x18004743d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047444  movups  xmm0, xmmword ptr cs:NtLmGlobalUnicodeComputerNameString.Length
0x18004744b  movups  xmm1, xmmword ptr cs:NtLmGlobalOemComputerNameString.Length
0x180047452  movdqu  xmmword ptr cs:NtLmGlobalUnicodePhysicalComputerNameString.Length, xmm0
0x18004745a  movdqu  xmmword ptr cs:NtLmGlobalOemPhysicalComputerNameString.Length, xmm1
0x180047462  jmp     short loc_180047478
0x180047464  cmp     [rbp+240h+arg_28], 4
0x18004746b  jnz     loc_180047709
0x180047471  mov     rcx, cs:WPP_GLOBAL_Control
0x180047478  mov     esi, 200h
0x18004747d  test    r14, r14
0x180047480  jz      loc_180047512
0x180047486  cmp     qword ptr [r14+8], 0
0x18004748b  jz      loc_180047512
0x180047491  movzx   eax, word ptr [r14]
0x180047495  mov     r8d, eax
0x180047498  add     rax, 2
0x18004749c  shr     r8d, 1
0x18004749f  cmp     rax, rsi
0x1800474a2  jbe     short loc_1800474C9
0x1800474a4  mov     ebx, 0C0000122h
0x1800474a9  cmp     rcx, r12
0x1800474ac  jz      loc_180047EDC
0x1800474b2  test    byte ptr [rcx+1Ch], 1
0x1800474b6  jz      loc_180047EDC
0x1800474bc  mov     edx, 12h
0x1800474c1  mov     r9d, r8d
0x1800474c4  jmp     loc_18004729F
0x1800474c9  mov     ebx, r8d
0x1800474cc  mov     edx, 100h
0x1800474d1  mov     r9d, r8d
0x1800474d4  mov     r8, [r14+8]
0x1800474d8  lea     r14, NtLmGlobalUnicodeDnsComputerName
0x1800474df  mov     rcx, r14
0x1800474e2  call    cs:__imp__o_wcsncpy_s
0x1800474e8  add     rbx, rbx
0x1800474eb  cmp     rbx, rsi
0x1800474ee  jnb     loc_180047731
0x1800474f4  xor     eax, eax
0x1800474f6  lea     rcx, NtLmGlobalUnicodeDnsComputerNameString; DestinationString
0x1800474fd  mov     rdx, r14; SourceString
0x180047500  mov     [rbx+r14], ax
0x180047505  call    cs:__imp_RtlInitUnicodeString
0x18004750b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047512  cmp     cs:NtLmGlobalUsePhysicalNames, 0
0x180047519  mov     [rsp+340h+nSize], 100h
0x180047521  jz      short loc_180047562
0x180047523  lea     r8, [rsp+340h+nSize]; nSize
0x180047528  mov     ecx, 7; NameType
0x18004752d  lea     rdx, NtLmGlobalUnicodePhysicalDnsComputerName; lpBuffer
0x180047534  call    cs:__imp_GetComputerNameExW
0x18004753a  test    eax, eax
0x18004753c  jz      short loc_18004755B
0x18004753e  lea     rdx, NtLmGlobalUnicodePhysicalDnsComputerName; SourceString
0x180047545  lea     rcx, NtLmGlobalUnicodePhysicalDnsComputerNameString; DestinationString
0x18004754c  call    cs:__imp_RtlInitUnicodeString
0x180047552  mov     rcx, cs:WPP_GLOBAL_Control
0x180047559  jmp     short loc_180047571
0x18004755b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047562  movups  xmm0, xmmword ptr cs:NtLmGlobalUnicodeDnsComputerNameString.Length
0x180047569  movdqu  xmmword ptr cs:NtLmGlobalUnicodePhysicalDnsComputerNameString.Length, xmm0
0x180047571  test    r15, r15
0x180047574  jz      loc_1800475FF
0x18004757a  cmp     qword ptr [r15+8], 0
0x18004757f  jz      short loc_1800475FF
0x180047581  movzx   eax, word ptr [r15]
0x180047585  mov     r8d, eax
0x180047588  add     rax, 2
0x18004758c  shr     r8d, 1
0x18004758f  cmp     rax, rsi
0x180047592  jbe     short loc_1800475B6
0x180047594  mov     ebx, 0C0000122h
0x180047599  cmp     rcx, r12
0x18004759c  jz      loc_180047EDC
0x1800475a2  test    byte ptr [rcx+1Ch], 1
0x1800475a6  jz      loc_180047EDC
0x1800475ac  mov     edx, 13h
0x1800475b1  jmp     loc_1800474C1
0x1800475b6  mov     ebx, r8d
0x1800475b9  lea     r14, NtLmGlobalUnicodeDnsDomainName
0x1800475c0  mov     r9d, r8d
  ... truncated ...
```
