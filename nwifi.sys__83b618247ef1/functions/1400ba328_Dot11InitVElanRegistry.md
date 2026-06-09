# Dot11InitVElanRegistry

- ea: `0x1400ba328`
- end: `0x1400ba70d`
- name: `Dot11InitVElanRegistry`
- size: `997`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14001667c`
- `0x140036c48`

## callees

- `0x140020dc0`
- `0x14009a3d0`
- `0x1400b9008`
- `0x1400ba328`
- `0x1400ba714`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400ba42f`
- `ntoskrnl!ZwClose` at `0x1400ba657`
- `ntoskrnl!ZwClose` at `0x1400ba42f`
- `ntoskrnl!ZwClose` at `0x1400ba657`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ba573`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ba5e9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ba573`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ba5e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba45e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba67e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba45e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba67e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba68f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba6a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba68f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba6a2`
- `ntoskrnl!ZwCreateKey` at `0x1400ba546`
- `ntoskrnl!ZwCreateKey` at `0x1400ba5cc`
- `ntoskrnl!ZwCreateKey` at `0x1400ba63d`
- `ntoskrnl!ZwCreateKey` at `0x1400ba546`
- `ntoskrnl!ZwCreateKey` at `0x1400ba5cc`
- `ntoskrnl!ZwCreateKey` at `0x1400ba63d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400ba39a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400ba39a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ba3b8`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ba3b8`
- `ntoskrnl!RtlStringFromGUID` at `0x1400ba4e8`
- `ntoskrnl!RtlStringFromGUID` at `0x1400ba4e8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400ba558`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400ba558`

## pseudocode

```c
__int64 __fastcall Dot11InitVElanRegistry(__int64 a1, int a2)
{
  int v4; // eax
  struct _ACL *v5; // r14
  NTSTATUS v6; // ebx
  const WCHAR *v7; // rdi
  const WCHAR *v8; // rsi
  HANDLE Handle; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-31h] BYREF
  PACL Dacl; // [rsp+88h] [rbp-1h] BYREF
  _BYTE SecurityDescriptor[40]; // [rsp+90h] [rbp+7h] BYREF

  Handle = 0;
  GuidString = 0;
  Dacl = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = Dot11BuildRegistryAcl(&Dacl);
  v5 = Dacl;
  v6 = v4;
  if ( v4 < 0 )
    goto LABEL_14;
  v6 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v6 < 0 )
    goto LABEL_14;
  v6 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v5, 0);
  if ( v6 < 0 )
    goto LABEL_14;
  switch ( a2 )
  {
    case 1:
      v7 = L"STA";
      v8 = L"STAMib";
      break;
    case 2:
      v7 = L"AP";
      v8 = L"APMib";
      break;
    case 4:
      goto LABEL_23;
    case 8:
      goto LABEL_22;
    case 0x10:
      v7 = L"WFD";
      v8 = L"WFDMib";
      break;
    case 0x20:
LABEL_22:
      v7 = L"ExtAP";
      v8 = L"ExtAPMib";
      break;
    case 0x40:
LABEL_23:
      v7 = L"ExtSTA";
      v8 = L"ExtSTAMib";
      break;
    case 0x40000000:
      v7 = L"Mfg";
      v8 = L"MfgMib";
      break;
    case 0x80000000:
      v7 = L"NetMon";
      v8 = L"NetMonMib";
      break;
    default:
      v6 = -1073741811;
LABEL_14:
      Dot11DeInitVElanRegistry(a1);
      if ( Handle )
      {
        ZwClose(Handle);
        Handle = 0;
      }
      if ( v5 )
      {
        if ( v5[-2] )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v5[-2], &v5[-2]);
        else
          ExFreePoolWithTag(&v5[-2], *(_DWORD *)&v5[-1].AclRevision);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids,
          (unsigned int)v6);
      }
      return (unsigned int)v6;
  }
  v6 = RtlStringFromGUID((const GUID *const)(a1 + 4920), &GuidString);
  if ( v6 < 0 )
    goto LABEL_14;
  ObjectAttributes.RootDirectory = WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
  ObjectAttributes.ObjectName = &GuidString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateKey(&Handle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  RtlFreeUnicodeString(&GuidString);
  if ( v6 < 0 )
    goto LABEL_14;
  RtlInitUnicodeString(&GuidString, v7);
  ObjectAttributes.RootDirectory = Handle;
  ObjectAttributes.ObjectName = &GuidString;
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityQualityOfService = 0;
  v6 = ZwCreateKey((PHANDLE)(a1 + 4888), 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v6 < 0 )
    goto LABEL_14;
  RtlInitUnicodeString(&GuidString, v8);
  ObjectAttributes.RootDirectory = Handle;
  ObjectAttributes.ObjectName = &GuidString;
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityQualityOfService = 0;
  v6 = ZwCreateKey((PHANDLE)(a1 + 4880), 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v6 < 0 )
    goto LABEL_14;
  ZwClose(Handle);
  Handle = 0;
  if ( v5 )
  {
    if ( v5[-2] )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v5[-2], &v5[-2]);
    else
      ExFreePoolWithTag(&v5[-2], *(_DWORD *)&v5[-1].AclRevision);
  }
  return 0;
}

```

## disassembly

```asm
0x1400ba328  mov     [rsp-8+arg_8], rbx
0x1400ba32d  mov     [rsp-8+arg_10], rsi
0x1400ba332  push    rbp
0x1400ba333  push    rdi
0x1400ba334  push    r12
0x1400ba336  push    r14
0x1400ba338  push    r15
0x1400ba33a  lea     rbp, [rsp-37h]
0x1400ba33f  sub     rsp, 0C0h
0x1400ba346  mov     rax, cs:__security_cookie
0x1400ba34d  xor     rax, rsp
0x1400ba350  mov     [rbp+57h+var_28], rax
0x1400ba354  xorps   xmm1, xmm1
0x1400ba357  mov     r15, rcx
0x1400ba35a  xor     r12d, r12d
0x1400ba35d  lea     rcx, [rbp+57h+Dacl]
0x1400ba361  xorps   xmm0, xmm0
0x1400ba364  mov     [rbp+57h+Handle], r12
0x1400ba368  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x1400ba36c  mov     [rbp+57h+Dacl], r12
0x1400ba370  mov     edi, edx
0x1400ba372  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400ba376  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400ba37a  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400ba37e  call    Dot11BuildRegistryAcl
0x1400ba383  mov     r14, [rbp+57h+Dacl]
0x1400ba387  mov     ebx, eax
0x1400ba389  test    eax, eax
0x1400ba38b  js      loc_1400BA41E
0x1400ba391  lea     edx, [r12+1]; Revision
0x1400ba396  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400ba39a  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400ba3a1  nop     dword ptr [rax+rax+00h]
0x1400ba3a6  mov     ebx, eax
0x1400ba3a8  test    eax, eax
0x1400ba3aa  js      short loc_1400BA41E
0x1400ba3ac  xor     r9d, r9d; DaclDefaulted
0x1400ba3af  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400ba3b3  mov     r8, r14; Dacl
0x1400ba3b6  mov     dl, 1; DaclPresent
0x1400ba3b8  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400ba3bf  nop     dword ptr [rax+rax+00h]
0x1400ba3c4  mov     ebx, eax
0x1400ba3c6  test    eax, eax
0x1400ba3c8  js      short loc_1400BA41E
0x1400ba3ca  cmp     edi, 1
0x1400ba3cd  jz      loc_1400BA4CF
0x1400ba3d3  cmp     edi, 2
0x1400ba3d6  jz      loc_1400BA4BF
0x1400ba3dc  cmp     edi, 4
0x1400ba3df  jz      loc_1400BA4AF
0x1400ba3e5  cmp     edi, 8
0x1400ba3e8  jz      loc_1400BA49F
0x1400ba3ee  cmp     edi, 10h
0x1400ba3f1  jz      loc_1400BA48F
0x1400ba3f7  cmp     edi, 20h ; ' '
0x1400ba3fa  jz      loc_1400BA49F
0x1400ba400  cmp     edi, 40h ; '@'
0x1400ba403  jz      loc_1400BA4AF
0x1400ba409  cmp     edi, 40000000h
0x1400ba40f  jz      short loc_1400BA47F
0x1400ba411  cmp     edi, 80000000h
0x1400ba417  jz      short loc_1400BA46F
0x1400ba419  mov     ebx, 0C000000Dh
0x1400ba41e  mov     rcx, r15
0x1400ba421  call    Dot11DeInitVElanRegistry
0x1400ba426  mov     rcx, [rbp+57h+Handle]; Handle
0x1400ba42a  test    rcx, rcx
0x1400ba42d  jz      short loc_1400BA43F
0x1400ba42f  call    cs:__imp_ZwClose
0x1400ba436  nop     dword ptr [rax+rax+00h]
0x1400ba43b  mov     [rbp+57h+Handle], r12
0x1400ba43f  test    r14, r14
0x1400ba442  jz      loc_1400BA6AE
0x1400ba448  lea     rcx, [r14-10h]; P
0x1400ba44c  mov     rax, [rcx]
0x1400ba44f  test    rax, rax
0x1400ba452  jz      loc_1400BA69F
0x1400ba458  mov     rdx, rcx; Entry
0x1400ba45b  mov     rcx, rax; Lookaside
0x1400ba45e  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400ba465  nop     dword ptr [rax+rax+00h]
0x1400ba46a  jmp     loc_1400BA6AE
0x1400ba46f  lea     rdi, aNetmon; "NetMon"
0x1400ba476  lea     rsi, aNetmonmib; "NetMonMib"
0x1400ba47d  jmp     short loc_1400BA4DD
0x1400ba47f  lea     rdi, aMfg; "Mfg"
0x1400ba486  lea     rsi, aMfgmib; "MfgMib"
0x1400ba48d  jmp     short loc_1400BA4DD
0x1400ba48f  lea     rdi, aWfd; "WFD"
0x1400ba496  lea     rsi, aWfdmib; "WFDMib"
0x1400ba49d  jmp     short loc_1400BA4DD
0x1400ba49f  lea     rdi, aExtap; "ExtAP"
0x1400ba4a6  lea     rsi, aExtapmib; "ExtAPMib"
0x1400ba4ad  jmp     short loc_1400BA4DD
0x1400ba4af  lea     rdi, aExtsta; "ExtSTA"
0x1400ba4b6  lea     rsi, aExtstamib; "ExtSTAMib"
0x1400ba4bd  jmp     short loc_1400BA4DD
0x1400ba4bf  lea     rdi, aAp; "AP"
0x1400ba4c6  lea     rsi, aApmib; "APMib"
0x1400ba4cd  jmp     short loc_1400BA4DD
0x1400ba4cf  lea     rdi, aSta; "STA"
0x1400ba4d6  lea     rsi, aStamib; "STAMib"
0x1400ba4dd  lea     rcx, [r15+1338h]; Guid
0x1400ba4e4  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1400ba4e8  call    cs:__imp_RtlStringFromGUID
0x1400ba4ef  nop     dword ptr [rax+rax+00h]
0x1400ba4f4  mov     ebx, eax
0x1400ba4f6  test    eax, eax
0x1400ba4f8  js      loc_1400BA41E
0x1400ba4fe  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400ba505  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400ba509  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400ba50d  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1400ba511  lea     rax, [rbp+57h+GuidString]
0x1400ba515  mov     [rsp+0E0h+Disposition], r12; Disposition
0x1400ba51a  xorps   xmm0, xmm0
0x1400ba51d  mov     [rsp+0E0h+CreateOptions], r12d; CreateOptions
0x1400ba522  xor     r9d, r9d; TitleIndex
0x1400ba525  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400ba529  mov     edx, 2001Fh; DesiredAccess
0x1400ba52e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400ba535  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400ba53c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ba541  mov     [rsp+0E0h+Class], r12; Class
0x1400ba546  call    cs:__imp_ZwCreateKey
0x1400ba54d  nop     dword ptr [rax+rax+00h]
0x1400ba552  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x1400ba556  mov     ebx, eax
0x1400ba558  call    cs:__imp_RtlFreeUnicodeString
0x1400ba55f  nop     dword ptr [rax+rax+00h]
0x1400ba564  test    ebx, ebx
0x1400ba566  js      loc_1400BA41E
0x1400ba56c  mov     rdx, rdi; SourceString
0x1400ba56f  lea     rcx, [rbp+57h+GuidString]; DestinationString
0x1400ba573  call    cs:__imp_RtlInitUnicodeString
0x1400ba57a  nop     dword ptr [rax+rax+00h]
0x1400ba57f  mov     rax, [rbp+57h+Handle]
0x1400ba583  lea     rcx, [r15+1318h]; KeyHandle
0x1400ba58a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400ba58e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400ba592  lea     rax, [rbp+57h+GuidString]
0x1400ba596  mov     [rsp+0E0h+Disposition], r12; Disposition
0x1400ba59b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400ba59f  mov     edi, 240h
0x1400ba5a4  lea     rax, [rbp+57h+SecurityDescriptor]
0x1400ba5a8  mov     [rsp+0E0h+CreateOptions], r12d; CreateOptions
0x1400ba5ad  xor     r9d, r9d; TitleIndex
0x1400ba5b0  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x1400ba5b4  mov     edx, 2001Fh; DesiredAccess
0x1400ba5b9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400ba5c0  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x1400ba5c3  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r12
0x1400ba5c7  mov     [rsp+0E0h+Class], r12; Class
0x1400ba5cc  call    cs:__imp_ZwCreateKey
0x1400ba5d3  nop     dword ptr [rax+rax+00h]
0x1400ba5d8  mov     ebx, eax
0x1400ba5da  test    eax, eax
0x1400ba5dc  js      loc_1400BA41E
0x1400ba5e2  mov     rdx, rsi; SourceString
0x1400ba5e5  lea     rcx, [rbp+57h+GuidString]; DestinationString
0x1400ba5e9  call    cs:__imp_RtlInitUnicodeString
0x1400ba5f0  nop     dword ptr [rax+rax+00h]
0x1400ba5f5  mov     rax, [rbp+57h+Handle]
0x1400ba5f9  lea     rcx, [r15+1310h]; KeyHandle
0x1400ba600  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400ba604  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400ba608  lea     rax, [rbp+57h+GuidString]
0x1400ba60c  mov     [rsp+0E0h+Disposition], r12; Disposition
0x1400ba611  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400ba615  xor     r9d, r9d; TitleIndex
0x1400ba618  lea     rax, [rbp+57h+SecurityDescriptor]
0x1400ba61c  mov     [rsp+0E0h+CreateOptions], r12d; CreateOptions
0x1400ba621  mov     edx, 2001Fh; DesiredAccess
0x1400ba626  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x1400ba62a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400ba631  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x1400ba634  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r12
0x1400ba638  mov     [rsp+0E0h+Class], r12; Class
0x1400ba63d  call    cs:__imp_ZwCreateKey
0x1400ba644  nop     dword ptr [rax+rax+00h]
0x1400ba649  mov     ebx, eax
0x1400ba64b  test    eax, eax
0x1400ba64d  js      loc_1400BA41E
0x1400ba653  mov     rcx, [rbp+57h+Handle]; Handle
0x1400ba657  call    cs:__imp_ZwClose
0x1400ba65e  nop     dword ptr [rax+rax+00h]
0x1400ba663  mov     [rbp+57h+Handle], r12
0x1400ba667  test    r14, r14
0x1400ba66a  jz      short loc_1400BA69B
0x1400ba66c  lea     rcx, [r14-10h]; P
0x1400ba670  mov     rax, [rcx]
0x1400ba673  test    rax, rax
0x1400ba676  jz      short loc_1400BA68C
0x1400ba678  mov     rdx, rcx; Entry
0x1400ba67b  mov     rcx, rax; Lookaside
0x1400ba67e  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400ba685  nop     dword ptr [rax+rax+00h]
0x1400ba68a  jmp     short loc_1400BA69B
0x1400ba68c  mov     edx, [rcx+8]; Tag
0x1400ba68f  call    cs:__imp_ExFreePoolWithTag
0x1400ba696  nop     dword ptr [rax+rax+00h]
0x1400ba69b  xor     eax, eax
0x1400ba69d  jmp     short loc_1400BA6E4
0x1400ba69f  mov     edx, [rcx+8]; Tag
0x1400ba6a2  call    cs:__imp_ExFreePoolWithTag
0x1400ba6a9  nop     dword ptr [rax+rax+00h]
0x1400ba6ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba6b5  lea     rax, WPP_GLOBAL_Control
0x1400ba6bc  cmp     rcx, rax
0x1400ba6bf  jz      short loc_1400BA6E2
0x1400ba6c1  test    dword ptr [rcx+2Ch], 200h
0x1400ba6c8  jz      short loc_1400BA6E2
0x1400ba6ca  mov     rcx, [rcx+18h]
0x1400ba6ce  lea     r8, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids
0x1400ba6d5  mov     edx, 0Bh
0x1400ba6da  mov     r9d, ebx
0x1400ba6dd  call    WPP_SF_d
0x1400ba6e2  mov     eax, ebx
0x1400ba6e4  mov     rcx, [rbp+57h+var_28]
0x1400ba6e8  xor     rcx, rsp; StackCookie
0x1400ba6eb  call    __security_check_cookie
0x1400ba6f0  lea     r11, [rsp+0E0h+var_20]
0x1400ba6f8  mov     rbx, [r11+38h]
0x1400ba6fc  mov     rsi, [r11+40h]
0x1400ba700  mov     rsp, r11
0x1400ba703  pop     r15
0x1400ba705  pop     r14
0x1400ba707  pop     r12
0x1400ba709  pop     rdi
0x1400ba70a  pop     rbp
0x1400ba70b  retn
```
