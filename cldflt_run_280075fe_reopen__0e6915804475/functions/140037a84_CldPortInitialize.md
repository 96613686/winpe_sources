# CldPortInitialize

- ea: `0x140037a84`
- end: `0x140037e23`
- name: `CldPortInitialize`
- size: `927`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140087080`

## callees

- `0x140003c50`
- `0x14000d908`
- `0x14000d95c`
- `0x14000ddc8`
- `0x140037a84`
- `0x140042e60`
- `0x140082050`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140037b14`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037b14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037de6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037dff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037de6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037dff`
- `ntoskrnl!ExAllocatePool2` at `0x140037c4d`
- `ntoskrnl!ExAllocatePool2` at `0x140037c4d`
- `FLTMGR!FltInitializePushLock` at `0x140037ad5`
- `FLTMGR!FltInitializePushLock` at `0x140037afd`
- `FLTMGR!FltInitializePushLock` at `0x140037ad5`
- `FLTMGR!FltInitializePushLock` at `0x140037afd`
- `FLTMGR!FltCreateCommunicationPort` at `0x140037bec`
- `FLTMGR!FltCreateCommunicationPort` at `0x140037bec`

## string_xrefs

- `0x140037ca5`: `\Registry\Machine\System\CurrentControlSet\Services\%s\Parameters`

## pseudocode

```c
__int64 CldPortInitialize()
{
  WCHAR *v0; // rdi
  __int64 v1; // rdx
  __int64 v2; // rbx
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  wchar_t *Pool2; // rax
  _QWORD v7[2]; // [rsp+40h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF
  PVOID P; // [rsp+A8h] [rbp+6Fh] BYREF

  v7[0] = 2097182;
  P = 0;
  v0 = 0;
  v7[1] = L"D:P(A;;GA;;;AU)";
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  FltInitializePushLock(&PushLock);
  qword_1400286A0 = (__int64)&qword_140028698;
  qword_140028698 = (__int64)&qword_140028698;
  FltInitializePushLock(&qword_1400286A8);
  RtlInitUnicodeString(&DestinationString, L"\\CLDMSGPORT");
  LODWORD(v2) = SeSddlSecurityDescriptorFromSDDL(v7, v1, &P);
  HsmDbgBreakOnStatus((unsigned int)v2);
  if ( (int)v2 >= 0 )
  {
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.SecurityDescriptor = P;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.SecurityQualityOfService = 0;
    v2 = (unsigned int)FltCreateCommunicationPort(
                         Globals,
                         &ServerPort,
                         &ObjectAttributes,
                         0,
                         CldiPortNotifyConnect,
                         CldiPortNotifyDisconnect,
                         (PFLT_MESSAGE_NOTIFY)CldiPortNotifyMessage,
                         0x7FFFFFFF);
    HsmDbgBreakOnStatus(v2);
    if ( (int)v2 >= 0 )
    {
      Pool2 = (wchar_t *)ExAllocatePool2(64, 260, 1649699907);
      v0 = Pool2;
      if ( Pool2 )
      {
        LODWORD(v2) = RtlStringCchPrintfW(
                        Pool2,
                        0x82u,
                        L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\%s\\Parameters",
                        L"CldFlt");
        if ( (int)v2 >= 0 )
        {
          LODWORD(v2) = HsmpGetRegDword(v0, L"USMsgTimeoutMillis");
          HsmDbgBreakOnStatus((unsigned int)v2);
          if ( (int)v2 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                167,
                WPP_452df49304b034ad87c0baec305776b3_Traceguids,
                (unsigned int)v2);
            }
            LODWORD(v2) = 0;
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              166,
              WPP_452df49304b034ad87c0baec305776b3_Traceguids,
              0,
              (int)qword_140028870 / -10000);
          }
        }
        else
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v4 = 165;
            goto LABEL_6;
          }
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v4 = 164;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v4 = 163;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v4 = 162;
LABEL_6:
      WPP_SF_d(v3->AttachedDevice, v4, WPP_452df49304b034ad87c0baec305776b3_Traceguids, (unsigned int)v2);
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v0 )
    ExFreePoolWithTag(v0, 0x62546C43u);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140037a84  mov     [rsp-8+arg_10], rbx
0x140037a89  mov     [rsp-8+arg_18], rdi
0x140037a8e  push    rbp
0x140037a8f  lea     rbp, [rsp-57h]
0x140037a94  sub     rsp, 90h
0x140037a9b  xorps   xmm0, xmm0
0x140037a9e  mov     [rbp+57h+var_50], 20001Eh
0x140037aa6  lea     rax, aDPAGaAu; "D:P(A;;GA;;;AU)"
0x140037aad  mov     [rbp+57h+P], 0
0x140037ab5  xor     edi, edi
0x140037ab7  mov     [rbp+57h+var_48], rax
0x140037abb  lea     rcx, PushLock; PushLock
0x140037ac2  mov     [rbp+57h+arg_0], edi
0x140037ac5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140037ac9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140037acd  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140037ad1  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140037ad5  call    cs:__imp_FltInitializePushLock
0x140037adc  nop     dword ptr [rax+rax+00h]
0x140037ae1  lea     rax, qword_140028698
0x140037ae8  mov     cs:qword_1400286A0, rax
0x140037aef  mov     cs:qword_140028698, rax
0x140037af6  lea     rcx, qword_1400286A8; PushLock
0x140037afd  call    cs:__imp_FltInitializePushLock
0x140037b04  nop     dword ptr [rax+rax+00h]
0x140037b09  lea     rdx, aCldmsgport; "\\CLDMSGPORT"
0x140037b10  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140037b14  call    cs:__imp_RtlInitUnicodeString
0x140037b1b  nop     dword ptr [rax+rax+00h]
0x140037b20  lea     r8, [rbp+57h+P]
0x140037b24  lea     rcx, [rbp+57h+var_50]
0x140037b28  call    SeSddlSecurityDescriptorFromSDDL
0x140037b2d  mov     ecx, eax
0x140037b2f  mov     ebx, eax
0x140037b31  call    HsmDbgBreakOnStatus
0x140037b36  test    ebx, ebx
0x140037b38  jns     short loc_140037B85
0x140037b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b41  lea     rax, WPP_GLOBAL_Control
0x140037b48  cmp     rcx, rax
0x140037b4b  jz      loc_140037DDB
0x140037b51  test    dword ptr [rcx+2Ch], 100h
0x140037b58  jz      loc_140037DDB
0x140037b5e  cmp     byte ptr [rcx+29h], 2
0x140037b62  jb      loc_140037DDB
0x140037b68  mov     edx, 0A2h
0x140037b6d  mov     rcx, [rcx+18h]
0x140037b71  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x140037b78  mov     r9d, ebx
0x140037b7b  call    WPP_SF_d
0x140037b80  jmp     loc_140037DDB
0x140037b85  mov     rcx, cs:Globals; Filter
0x140037b8c  lea     rax, [rbp+57h+DestinationString]
0x140037b90  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140037b94  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140037b98  mov     rax, [rbp+57h+P]
0x140037b9c  lea     rdx, ServerPort; ServerPort
0x140037ba3  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x140037ba7  xor     r9d, r9d; ServerPortCookie
0x140037baa  mov     [rsp+90h+MaxConnections], 7FFFFFFFh; MaxConnections
0x140037bb2  lea     rax, CldiPortNotifyMessage
0x140037bb9  mov     [rsp+90h+MessageNotifyCallback], rax; MessageNotifyCallback
0x140037bbe  lea     rax, CldiPortNotifyDisconnect
0x140037bc5  mov     [rsp+90h+DisconnectNotifyCallback], rax; DisconnectNotifyCallback
0x140037bca  lea     rax, CldiPortNotifyConnect
0x140037bd1  mov     [rsp+90h+ConnectNotifyCallback], rax; ConnectNotifyCallback
0x140037bd6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140037bdd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x140037be1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140037be8  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rdi
0x140037bec  call    cs:__imp_FltCreateCommunicationPort
0x140037bf3  nop     dword ptr [rax+rax+00h]
0x140037bf8  mov     ecx, eax
0x140037bfa  mov     ebx, eax
0x140037bfc  call    HsmDbgBreakOnStatus
0x140037c01  test    ebx, ebx
0x140037c03  jns     short loc_140037C3D
0x140037c05  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c0c  lea     rax, WPP_GLOBAL_Control
0x140037c13  cmp     rcx, rax
0x140037c16  jz      loc_140037DDB
0x140037c1c  test    dword ptr [rcx+2Ch], 100h
0x140037c23  jz      loc_140037DDB
0x140037c29  cmp     byte ptr [rcx+29h], 2
0x140037c2d  jb      loc_140037DDB
0x140037c33  mov     edx, 0A3h
0x140037c38  jmp     loc_140037B6D
0x140037c3d  mov     edx, 104h
0x140037c42  mov     ecx, 40h ; '@'
0x140037c47  mov     r8d, 62546C43h
0x140037c4d  call    cs:__imp_ExAllocatePool2
0x140037c54  nop     dword ptr [rax+rax+00h]
0x140037c59  mov     rdi, rax
0x140037c5c  test    rax, rax
0x140037c5f  jnz     short loc_140037C99
0x140037c61  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c68  lea     rax, WPP_GLOBAL_Control
0x140037c6f  cmp     rcx, rax
0x140037c72  jz      loc_140037DDB
0x140037c78  test    dword ptr [rcx+2Ch], 100h
0x140037c7f  jz      loc_140037DDB
0x140037c85  cmp     byte ptr [rcx+29h], 2
0x140037c89  jb      loc_140037DDB
0x140037c8f  mov     edx, 0A4h
0x140037c94  jmp     loc_140037B6D
0x140037c99  lea     r9, aCldflt; "CldFlt"
0x140037ca0  mov     edx, 82h; cchDest
0x140037ca5  lea     r8, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140037cac  mov     rcx, rdi; pszDest
0x140037caf  call    RtlStringCchPrintfW
0x140037cb4  mov     ebx, eax
0x140037cb6  test    eax, eax
0x140037cb8  jns     short loc_140037CF2
0x140037cba  mov     rcx, cs:WPP_GLOBAL_Control
0x140037cc1  lea     rax, WPP_GLOBAL_Control
0x140037cc8  cmp     rcx, rax
0x140037ccb  jz      loc_140037DDB
0x140037cd1  test    dword ptr [rcx+2Ch], 100h
0x140037cd8  jz      loc_140037DDB
0x140037cde  cmp     byte ptr [rcx+29h], 2
0x140037ce2  jb      loc_140037DDB
0x140037ce8  mov     edx, 0A5h
0x140037ced  jmp     loc_140037B6D
0x140037cf2  lea     r8, [rbp+57h+arg_0]
0x140037cf6  mov     rcx, rdi; SourceString
0x140037cf9  lea     rdx, aUsmsgtimeoutmi; "USMsgTimeoutMillis"
0x140037d00  call    HsmpGetRegDword
0x140037d05  mov     ecx, eax
0x140037d07  mov     ebx, eax
0x140037d09  call    HsmDbgBreakOnStatus
0x140037d0e  test    ebx, ebx
0x140037d10  js      loc_140037D9F
0x140037d16  mov     r9d, [rbp+57h+arg_0]
0x140037d1a  cmp     r9d, 3E8h
0x140037d21  jnb     short loc_140037D8F
0x140037d23  mov     rcx, cs:WPP_GLOBAL_Control
0x140037d2a  lea     rax, WPP_GLOBAL_Control
0x140037d31  cmp     rcx, rax
0x140037d34  jz      loc_140037DDB
0x140037d3a  test    dword ptr [rcx+2Ch], 100h
0x140037d41  jz      loc_140037DDB
0x140037d47  cmp     byte ptr [rcx+29h], 3
0x140037d4b  jb      loc_140037DDB
0x140037d51  mov     rcx, [rcx+18h]
0x140037d55  mov     rax, 0CB923A29C779A6B5h
0x140037d5f  imul    cs:qword_140028870
0x140037d66  mov     r8, rdx
0x140037d69  mov     edx, 0A6h
0x140037d6e  sar     r8, 0Bh
0x140037d72  mov     rax, r8
0x140037d75  shr     rax, 3Fh
0x140037d79  add     r8, rax
0x140037d7c  mov     dword ptr [rsp+90h+ConnectNotifyCallback], r8d
0x140037d81  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x140037d88  call    WPP_SF_Dd
0x140037d8d  jmp     short loc_140037DDB
0x140037d8f  imul    rcx, r9, 0FFFFFFFFFFFFD8F0h
0x140037d96  mov     cs:qword_140028870, rcx
0x140037d9d  jmp     short loc_140037DDB
0x140037d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140037da6  lea     rax, WPP_GLOBAL_Control
0x140037dad  cmp     rcx, rax
0x140037db0  jz      short loc_140037DD9
0x140037db2  test    dword ptr [rcx+2Ch], 100h
0x140037db9  jz      short loc_140037DD9
0x140037dbb  cmp     byte ptr [rcx+29h], 4
0x140037dbf  jb      short loc_140037DD9
0x140037dc1  mov     rcx, [rcx+18h]
0x140037dc5  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x140037dcc  mov     edx, 0A7h
0x140037dd1  mov     r9d, ebx
0x140037dd4  call    WPP_SF_d
0x140037dd9  xor     ebx, ebx
0x140037ddb  mov     rcx, [rbp+57h+P]; P
0x140037ddf  test    rcx, rcx
0x140037de2  jz      short loc_140037DF2
0x140037de4  xor     edx, edx; Tag
0x140037de6  call    cs:__imp_ExFreePoolWithTag
0x140037ded  nop     dword ptr [rax+rax+00h]
0x140037df2  test    rdi, rdi
0x140037df5  jz      short loc_140037E0B
0x140037df7  mov     edx, 62546C43h; Tag
0x140037dfc  mov     rcx, rdi; P
0x140037dff  call    cs:__imp_ExFreePoolWithTag
0x140037e06  nop     dword ptr [rax+rax+00h]
0x140037e0b  lea     r11, [rsp+90h+var_s0]
0x140037e13  mov     eax, ebx
0x140037e15  mov     rbx, [r11+20h]
0x140037e19  mov     rdi, [r11+28h]
0x140037e1d  mov     rsp, r11
0x140037e20  pop     rbp
0x140037e21  retn
```
