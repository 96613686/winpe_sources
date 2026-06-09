# Dot11InitVElanRegistry

- ea: `0x1400bd2d8`
- end: `0x1400bd6bd`
- name: `Dot11InitVElanRegistry`
- size: `997`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14001666c`
- `0x140036e68`

## callees

- `0x140020dc0`
- `0x14009bbb0`
- `0x1400bc008`
- `0x1400bd2d8`
- `0x1400bd6c4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400bd3df`
- `ntoskrnl!ZwClose` at `0x1400bd607`
- `ntoskrnl!ZwClose` at `0x1400bd3df`
- `ntoskrnl!ZwClose` at `0x1400bd607`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd523`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd599`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd523`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bd599`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bd40e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bd62e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bd40e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400bd62e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd63f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd652`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd63f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd652`
- `ntoskrnl!ZwCreateKey` at `0x1400bd4f6`
- `ntoskrnl!ZwCreateKey` at `0x1400bd57c`
- `ntoskrnl!ZwCreateKey` at `0x1400bd5ed`
- `ntoskrnl!ZwCreateKey` at `0x1400bd4f6`
- `ntoskrnl!ZwCreateKey` at `0x1400bd57c`
- `ntoskrnl!ZwCreateKey` at `0x1400bd5ed`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400bd34a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400bd34a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400bd368`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400bd368`
- `ntoskrnl!RtlStringFromGUID` at `0x1400bd498`
- `ntoskrnl!RtlStringFromGUID` at `0x1400bd498`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400bd508`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400bd508`

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
0x1400bd2d8  mov     [rsp-8+arg_8], rbx
0x1400bd2dd  mov     [rsp-8+arg_10], rsi
0x1400bd2e2  push    rbp
0x1400bd2e3  push    rdi
0x1400bd2e4  push    r12
0x1400bd2e6  push    r14
0x1400bd2e8  push    r15
0x1400bd2ea  lea     rbp, [rsp-37h]
0x1400bd2ef  sub     rsp, 0C0h
0x1400bd2f6  mov     rax, cs:__security_cookie
0x1400bd2fd  xor     rax, rsp
0x1400bd300  mov     [rbp+57h+var_28], rax
0x1400bd304  xorps   xmm1, xmm1
0x1400bd307  mov     r15, rcx
0x1400bd30a  xor     r12d, r12d
0x1400bd30d  lea     rcx, [rbp+57h+Dacl]
0x1400bd311  xorps   xmm0, xmm0
0x1400bd314  mov     [rbp+57h+Handle], r12
0x1400bd318  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x1400bd31c  mov     [rbp+57h+Dacl], r12
0x1400bd320  mov     edi, edx
0x1400bd322  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400bd326  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400bd32a  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400bd32e  call    Dot11BuildRegistryAcl
0x1400bd333  mov     r14, [rbp+57h+Dacl]
0x1400bd337  mov     ebx, eax
0x1400bd339  test    eax, eax
0x1400bd33b  js      loc_1400BD3CE
0x1400bd341  lea     edx, [r12+1]; Revision
0x1400bd346  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400bd34a  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400bd351  nop     dword ptr [rax+rax+00h]
0x1400bd356  mov     ebx, eax
0x1400bd358  test    eax, eax
0x1400bd35a  js      short loc_1400BD3CE
0x1400bd35c  xor     r9d, r9d; DaclDefaulted
0x1400bd35f  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1400bd363  mov     r8, r14; Dacl
0x1400bd366  mov     dl, 1; DaclPresent
0x1400bd368  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400bd36f  nop     dword ptr [rax+rax+00h]
0x1400bd374  mov     ebx, eax
0x1400bd376  test    eax, eax
0x1400bd378  js      short loc_1400BD3CE
0x1400bd37a  cmp     edi, 1
0x1400bd37d  jz      loc_1400BD47F
0x1400bd383  cmp     edi, 2
0x1400bd386  jz      loc_1400BD46F
0x1400bd38c  cmp     edi, 4
0x1400bd38f  jz      loc_1400BD45F
0x1400bd395  cmp     edi, 8
0x1400bd398  jz      loc_1400BD44F
0x1400bd39e  cmp     edi, 10h
0x1400bd3a1  jz      loc_1400BD43F
0x1400bd3a7  cmp     edi, 20h ; ' '
0x1400bd3aa  jz      loc_1400BD44F
0x1400bd3b0  cmp     edi, 40h ; '@'
0x1400bd3b3  jz      loc_1400BD45F
0x1400bd3b9  cmp     edi, 40000000h
0x1400bd3bf  jz      short loc_1400BD42F
0x1400bd3c1  cmp     edi, 80000000h
0x1400bd3c7  jz      short loc_1400BD41F
0x1400bd3c9  mov     ebx, 0C000000Dh
0x1400bd3ce  mov     rcx, r15
0x1400bd3d1  call    Dot11DeInitVElanRegistry
0x1400bd3d6  mov     rcx, [rbp+57h+Handle]; Handle
0x1400bd3da  test    rcx, rcx
0x1400bd3dd  jz      short loc_1400BD3EF
0x1400bd3df  call    cs:__imp_ZwClose
0x1400bd3e6  nop     dword ptr [rax+rax+00h]
0x1400bd3eb  mov     [rbp+57h+Handle], r12
0x1400bd3ef  test    r14, r14
0x1400bd3f2  jz      loc_1400BD65E
0x1400bd3f8  lea     rcx, [r14-10h]; P
0x1400bd3fc  mov     rax, [rcx]
0x1400bd3ff  test    rax, rax
0x1400bd402  jz      loc_1400BD64F
0x1400bd408  mov     rdx, rcx; Entry
0x1400bd40b  mov     rcx, rax; Lookaside
0x1400bd40e  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400bd415  nop     dword ptr [rax+rax+00h]
0x1400bd41a  jmp     loc_1400BD65E
0x1400bd41f  lea     rdi, aNetmon; "NetMon"
0x1400bd426  lea     rsi, aNetmonmib; "NetMonMib"
0x1400bd42d  jmp     short loc_1400BD48D
0x1400bd42f  lea     rdi, aMfg; "Mfg"
0x1400bd436  lea     rsi, aMfgmib; "MfgMib"
0x1400bd43d  jmp     short loc_1400BD48D
0x1400bd43f  lea     rdi, aWfd; "WFD"
0x1400bd446  lea     rsi, aWfdmib; "WFDMib"
0x1400bd44d  jmp     short loc_1400BD48D
0x1400bd44f  lea     rdi, aExtap; "ExtAP"
0x1400bd456  lea     rsi, aExtapmib; "ExtAPMib"
0x1400bd45d  jmp     short loc_1400BD48D
0x1400bd45f  lea     rdi, aExtsta; "ExtSTA"
0x1400bd466  lea     rsi, aExtstamib; "ExtSTAMib"
0x1400bd46d  jmp     short loc_1400BD48D
0x1400bd46f  lea     rdi, aAp; "AP"
0x1400bd476  lea     rsi, aApmib; "APMib"
0x1400bd47d  jmp     short loc_1400BD48D
0x1400bd47f  lea     rdi, aSta; "STA"
0x1400bd486  lea     rsi, aStamib; "STAMib"
0x1400bd48d  lea     rcx, [r15+1338h]; Guid
0x1400bd494  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1400bd498  call    cs:__imp_RtlStringFromGUID
0x1400bd49f  nop     dword ptr [rax+rax+00h]
0x1400bd4a4  mov     ebx, eax
0x1400bd4a6  test    eax, eax
0x1400bd4a8  js      loc_1400BD3CE
0x1400bd4ae  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400bd4b5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400bd4b9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400bd4bd  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1400bd4c1  lea     rax, [rbp+57h+GuidString]
0x1400bd4c5  mov     [rsp+0E0h+Disposition], r12; Disposition
0x1400bd4ca  xorps   xmm0, xmm0
0x1400bd4cd  mov     [rsp+0E0h+CreateOptions], r12d; CreateOptions
0x1400bd4d2  xor     r9d, r9d; TitleIndex
0x1400bd4d5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400bd4d9  mov     edx, 2001Fh; DesiredAccess
0x1400bd4de  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400bd4e5  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400bd4ec  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400bd4f1  mov     [rsp+0E0h+Class], r12; Class
0x1400bd4f6  call    cs:__imp_ZwCreateKey
0x1400bd4fd  nop     dword ptr [rax+rax+00h]
0x1400bd502  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x1400bd506  mov     ebx, eax
0x1400bd508  call    cs:__imp_RtlFreeUnicodeString
0x1400bd50f  nop     dword ptr [rax+rax+00h]
0x1400bd514  test    ebx, ebx
0x1400bd516  js      loc_1400BD3CE
0x1400bd51c  mov     rdx, rdi; SourceString
0x1400bd51f  lea     rcx, [rbp+57h+GuidString]; DestinationString
0x1400bd523  call    cs:__imp_RtlInitUnicodeString
0x1400bd52a  nop     dword ptr [rax+rax+00h]
0x1400bd52f  mov     rax, [rbp+57h+Handle]
0x1400bd533  lea     rcx, [r15+1318h]; KeyHandle
0x1400bd53a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400bd53e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400bd542  lea     rax, [rbp+57h+GuidString]
0x1400bd546  mov     [rsp+0E0h+Disposition], r12; Disposition
0x1400bd54b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400bd54f  mov     edi, 240h
0x1400bd554  lea     rax, [rbp+57h+SecurityDescriptor]
0x1400bd558  mov     [rsp+0E0h+CreateOptions], r12d; CreateOptions
0x1400bd55d  xor     r9d, r9d; TitleIndex
0x1400bd560  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x1400bd564  mov     edx, 2001Fh; DesiredAccess
0x1400bd569  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400bd570  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x1400bd573  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r12
0x1400bd577  mov     [rsp+0E0h+Class], r12; Class
0x1400bd57c  call    cs:__imp_ZwCreateKey
0x1400bd583  nop     dword ptr [rax+rax+00h]
0x1400bd588  mov     ebx, eax
0x1400bd58a  test    eax, eax
0x1400bd58c  js      loc_1400BD3CE
0x1400bd592  mov     rdx, rsi; SourceString
0x1400bd595  lea     rcx, [rbp+57h+GuidString]; DestinationString
0x1400bd599  call    cs:__imp_RtlInitUnicodeString
0x1400bd5a0  nop     dword ptr [rax+rax+00h]
0x1400bd5a5  mov     rax, [rbp+57h+Handle]
0x1400bd5a9  lea     rcx, [r15+1310h]; KeyHandle
0x1400bd5b0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400bd5b4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400bd5b8  lea     rax, [rbp+57h+GuidString]
0x1400bd5bc  mov     [rsp+0E0h+Disposition], r12; Disposition
0x1400bd5c1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400bd5c5  xor     r9d, r9d; TitleIndex
0x1400bd5c8  lea     rax, [rbp+57h+SecurityDescriptor]
0x1400bd5cc  mov     [rsp+0E0h+CreateOptions], r12d; CreateOptions
0x1400bd5d1  mov     edx, 2001Fh; DesiredAccess
0x1400bd5d6  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x1400bd5da  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400bd5e1  mov     [rbp+57h+ObjectAttributes.Attributes], edi
0x1400bd5e4  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r12
0x1400bd5e8  mov     [rsp+0E0h+Class], r12; Class
0x1400bd5ed  call    cs:__imp_ZwCreateKey
0x1400bd5f4  nop     dword ptr [rax+rax+00h]
0x1400bd5f9  mov     ebx, eax
0x1400bd5fb  test    eax, eax
0x1400bd5fd  js      loc_1400BD3CE
0x1400bd603  mov     rcx, [rbp+57h+Handle]; Handle
0x1400bd607  call    cs:__imp_ZwClose
0x1400bd60e  nop     dword ptr [rax+rax+00h]
0x1400bd613  mov     [rbp+57h+Handle], r12
0x1400bd617  test    r14, r14
0x1400bd61a  jz      short loc_1400BD64B
0x1400bd61c  lea     rcx, [r14-10h]; P
0x1400bd620  mov     rax, [rcx]
0x1400bd623  test    rax, rax
0x1400bd626  jz      short loc_1400BD63C
0x1400bd628  mov     rdx, rcx; Entry
0x1400bd62b  mov     rcx, rax; Lookaside
0x1400bd62e  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400bd635  nop     dword ptr [rax+rax+00h]
0x1400bd63a  jmp     short loc_1400BD64B
0x1400bd63c  mov     edx, [rcx+8]; Tag
0x1400bd63f  call    cs:__imp_ExFreePoolWithTag
0x1400bd646  nop     dword ptr [rax+rax+00h]
0x1400bd64b  xor     eax, eax
0x1400bd64d  jmp     short loc_1400BD694
0x1400bd64f  mov     edx, [rcx+8]; Tag
0x1400bd652  call    cs:__imp_ExFreePoolWithTag
0x1400bd659  nop     dword ptr [rax+rax+00h]
0x1400bd65e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd665  lea     rax, WPP_GLOBAL_Control
0x1400bd66c  cmp     rcx, rax
0x1400bd66f  jz      short loc_1400BD692
0x1400bd671  test    dword ptr [rcx+2Ch], 200h
0x1400bd678  jz      short loc_1400BD692
0x1400bd67a  mov     rcx, [rcx+18h]
0x1400bd67e  lea     r8, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids
0x1400bd685  mov     edx, 0Bh
0x1400bd68a  mov     r9d, ebx
0x1400bd68d  call    WPP_SF_d
0x1400bd692  mov     eax, ebx
0x1400bd694  mov     rcx, [rbp+57h+var_28]
0x1400bd698  xor     rcx, rsp; StackCookie
0x1400bd69b  call    __security_check_cookie
0x1400bd6a0  lea     r11, [rsp+0E0h+var_20]
0x1400bd6a8  mov     rbx, [r11+38h]
0x1400bd6ac  mov     rsi, [r11+40h]
0x1400bd6b0  mov     rsp, r11
0x1400bd6b3  pop     r15
0x1400bd6b5  pop     r14
0x1400bd6b7  pop     r12
0x1400bd6b9  pop     rdi
0x1400bd6ba  pop     rbp
0x1400bd6bb  retn
```
