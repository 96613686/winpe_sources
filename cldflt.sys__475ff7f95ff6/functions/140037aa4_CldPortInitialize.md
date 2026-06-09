# CldPortInitialize

- ea: `0x140037aa4`
- end: `0x140037e43`
- name: `CldPortInitialize`
- size: `927`
- prototype: `__int64()`
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
- `0x140037aa4`
- `0x140042f50`
- `0x1400821f0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140037b34`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037b34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037e1f`
- `ntoskrnl!ExAllocatePool2` at `0x140037c6d`
- `ntoskrnl!ExAllocatePool2` at `0x140037c6d`
- `FLTMGR!FltInitializePushLock` at `0x140037af5`
- `FLTMGR!FltInitializePushLock` at `0x140037b1d`
- `FLTMGR!FltInitializePushLock` at `0x140037af5`
- `FLTMGR!FltInitializePushLock` at `0x140037b1d`
- `FLTMGR!FltCreateCommunicationPort` at `0x140037c0c`
- `FLTMGR!FltCreateCommunicationPort` at `0x140037c0c`

## string_xrefs

- `0x140037cc5`: `\Registry\Machine\System\CurrentControlSet\Services\%s\Parameters`

## pseudocode

```c
__int64 CldPortInitialize()
{
  WCHAR *v0; // rdi
  __int64 v1; // rdx
  __int64 RegDword; // rbx
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
  RegDword = (unsigned int)SeSddlSecurityDescriptorFromSDDL(v7, v1, &P);
  HsmDbgBreakOnStatus(RegDword);
  if ( (int)RegDword >= 0 )
  {
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.SecurityDescriptor = P;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.SecurityQualityOfService = 0;
    RegDword = (unsigned int)FltCreateCommunicationPort(
                               Globals,
                               &ServerPort,
                               &ObjectAttributes,
                               0,
                               CldiPortNotifyConnect,
                               CldiPortNotifyDisconnect,
                               CldiPortNotifyMessage,
                               0x7FFFFFFF);
    HsmDbgBreakOnStatus(RegDword);
    if ( (int)RegDword >= 0 )
    {
      Pool2 = (wchar_t *)ExAllocatePool2(64, 260, 1649699907);
      v0 = Pool2;
      if ( Pool2 )
      {
        LODWORD(RegDword) = RtlStringCchPrintfW(
                              Pool2,
                              0x82u,
                              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\%s\\Parameters",
                              L"CldFlt");
        if ( (int)RegDword >= 0 )
        {
          RegDword = (unsigned int)HsmpGetRegDword(v0, L"USMsgTimeoutMillis");
          HsmDbgBreakOnStatus(RegDword);
          if ( (int)RegDword < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                167,
                WPP_452df49304b034ad87c0baec305776b3_Traceguids,
                (unsigned int)RegDword);
            }
            LODWORD(RegDword) = 0;
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_452df49304b034ad87c0baec305776b3_Traceguids);
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
      WPP_SF_d(v3->AttachedDevice, v4, WPP_452df49304b034ad87c0baec305776b3_Traceguids, (unsigned int)RegDword);
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v0 )
    ExFreePoolWithTag(v0, 0x62546C43u);
  return (unsigned int)RegDword;
}

```

## disassembly

```asm
0x140037aa4  mov     [rsp-8+arg_10], rbx
0x140037aa9  mov     [rsp-8+arg_18], rdi
0x140037aae  push    rbp
0x140037aaf  lea     rbp, [rsp-57h]
0x140037ab4  sub     rsp, 90h
0x140037abb  xorps   xmm0, xmm0
0x140037abe  mov     [rbp+57h+var_50], 20001Eh
0x140037ac6  lea     rax, aDPAGaAu; "D:P(A;;GA;;;AU)"
0x140037acd  mov     [rbp+57h+P], 0
0x140037ad5  xor     edi, edi
0x140037ad7  mov     [rbp+57h+var_48], rax
0x140037adb  lea     rcx, PushLock; PushLock
0x140037ae2  mov     [rbp+57h+arg_0], edi
0x140037ae5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140037ae9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140037aed  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140037af1  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140037af5  call    cs:__imp_FltInitializePushLock
0x140037afc  nop     dword ptr [rax+rax+00h]
0x140037b01  lea     rax, qword_140028698
0x140037b08  mov     cs:qword_1400286A0, rax
0x140037b0f  mov     cs:qword_140028698, rax
0x140037b16  lea     rcx, qword_1400286A8; PushLock
0x140037b1d  call    cs:__imp_FltInitializePushLock
0x140037b24  nop     dword ptr [rax+rax+00h]
0x140037b29  lea     rdx, aCldmsgport; "\\CLDMSGPORT"
0x140037b30  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140037b34  call    cs:__imp_RtlInitUnicodeString
0x140037b3b  nop     dword ptr [rax+rax+00h]
0x140037b40  lea     r8, [rbp+57h+P]
0x140037b44  lea     rcx, [rbp+57h+var_50]
0x140037b48  call    SeSddlSecurityDescriptorFromSDDL
0x140037b4d  mov     ecx, eax
0x140037b4f  mov     ebx, eax
0x140037b51  call    HsmDbgBreakOnStatus
0x140037b56  test    ebx, ebx
0x140037b58  jns     short loc_140037BA5
0x140037b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b61  lea     rax, WPP_GLOBAL_Control
0x140037b68  cmp     rcx, rax
0x140037b6b  jz      loc_140037DFB
0x140037b71  test    dword ptr [rcx+2Ch], 100h
0x140037b78  jz      loc_140037DFB
0x140037b7e  cmp     byte ptr [rcx+29h], 2
0x140037b82  jb      loc_140037DFB
0x140037b88  mov     edx, 0A2h
0x140037b8d  mov     rcx, [rcx+18h]
0x140037b91  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x140037b98  mov     r9d, ebx
0x140037b9b  call    WPP_SF_d
0x140037ba0  jmp     loc_140037DFB
0x140037ba5  mov     rcx, cs:Globals; Filter
0x140037bac  lea     rax, [rbp+57h+DestinationString]
0x140037bb0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140037bb4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140037bb8  mov     rax, [rbp+57h+P]
0x140037bbc  lea     rdx, ServerPort; ServerPort
0x140037bc3  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x140037bc7  xor     r9d, r9d; ServerPortCookie
0x140037bca  mov     [rsp+90h+MaxConnections], 7FFFFFFFh; MaxConnections
0x140037bd2  lea     rax, CldiPortNotifyMessage
0x140037bd9  mov     [rsp+90h+MessageNotifyCallback], rax; MessageNotifyCallback
0x140037bde  lea     rax, CldiPortNotifyDisconnect
0x140037be5  mov     [rsp+90h+DisconnectNotifyCallback], rax; DisconnectNotifyCallback
0x140037bea  lea     rax, CldiPortNotifyConnect
0x140037bf1  mov     [rsp+90h+ConnectNotifyCallback], rax; ConnectNotifyCallback
0x140037bf6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140037bfd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x140037c01  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140037c08  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rdi
0x140037c0c  call    cs:__imp_FltCreateCommunicationPort
0x140037c13  nop     dword ptr [rax+rax+00h]
0x140037c18  mov     ecx, eax
0x140037c1a  mov     ebx, eax
0x140037c1c  call    HsmDbgBreakOnStatus
0x140037c21  test    ebx, ebx
0x140037c23  jns     short loc_140037C5D
0x140037c25  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c2c  lea     rax, WPP_GLOBAL_Control
0x140037c33  cmp     rcx, rax
0x140037c36  jz      loc_140037DFB
0x140037c3c  test    dword ptr [rcx+2Ch], 100h
0x140037c43  jz      loc_140037DFB
0x140037c49  cmp     byte ptr [rcx+29h], 2
0x140037c4d  jb      loc_140037DFB
0x140037c53  mov     edx, 0A3h
0x140037c58  jmp     loc_140037B8D
0x140037c5d  mov     edx, 104h
0x140037c62  mov     ecx, 40h ; '@'
0x140037c67  mov     r8d, 62546C43h
0x140037c6d  call    cs:__imp_ExAllocatePool2
0x140037c74  nop     dword ptr [rax+rax+00h]
0x140037c79  mov     rdi, rax
0x140037c7c  test    rax, rax
0x140037c7f  jnz     short loc_140037CB9
0x140037c81  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c88  lea     rax, WPP_GLOBAL_Control
0x140037c8f  cmp     rcx, rax
0x140037c92  jz      loc_140037DFB
0x140037c98  test    dword ptr [rcx+2Ch], 100h
0x140037c9f  jz      loc_140037DFB
0x140037ca5  cmp     byte ptr [rcx+29h], 2
0x140037ca9  jb      loc_140037DFB
0x140037caf  mov     edx, 0A4h
0x140037cb4  jmp     loc_140037B8D
0x140037cb9  lea     r9, aCldflt; "CldFlt"
0x140037cc0  mov     edx, 82h; cchDest
0x140037cc5  lea     r8, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140037ccc  mov     rcx, rdi; pszDest
0x140037ccf  call    RtlStringCchPrintfW
0x140037cd4  mov     ebx, eax
0x140037cd6  test    eax, eax
0x140037cd8  jns     short loc_140037D12
0x140037cda  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ce1  lea     rax, WPP_GLOBAL_Control
0x140037ce8  cmp     rcx, rax
0x140037ceb  jz      loc_140037DFB
0x140037cf1  test    dword ptr [rcx+2Ch], 100h
0x140037cf8  jz      loc_140037DFB
0x140037cfe  cmp     byte ptr [rcx+29h], 2
0x140037d02  jb      loc_140037DFB
0x140037d08  mov     edx, 0A5h
0x140037d0d  jmp     loc_140037B8D
0x140037d12  lea     r8, [rbp+57h+arg_0]
0x140037d16  mov     rcx, rdi; SourceString
0x140037d19  lea     rdx, aUsmsgtimeoutmi; "USMsgTimeoutMillis"
0x140037d20  call    HsmpGetRegDword
0x140037d25  mov     ecx, eax
0x140037d27  mov     ebx, eax
0x140037d29  call    HsmDbgBreakOnStatus
0x140037d2e  test    ebx, ebx
0x140037d30  js      loc_140037DBF
0x140037d36  mov     r9d, [rbp+57h+arg_0]
0x140037d3a  cmp     r9d, 3E8h
0x140037d41  jnb     short loc_140037DAF
0x140037d43  mov     rcx, cs:WPP_GLOBAL_Control
0x140037d4a  lea     rax, WPP_GLOBAL_Control
0x140037d51  cmp     rcx, rax
0x140037d54  jz      loc_140037DFB
0x140037d5a  test    dword ptr [rcx+2Ch], 100h
0x140037d61  jz      loc_140037DFB
0x140037d67  cmp     byte ptr [rcx+29h], 3
0x140037d6b  jb      loc_140037DFB
0x140037d71  mov     rcx, [rcx+18h]
0x140037d75  mov     rax, 0CB923A29C779A6B5h
0x140037d7f  imul    cs:qword_140028870
0x140037d86  mov     r8, rdx
0x140037d89  mov     edx, 0A6h
0x140037d8e  sar     r8, 0Bh
0x140037d92  mov     rax, r8
0x140037d95  shr     rax, 3Fh
0x140037d99  add     r8, rax
0x140037d9c  mov     dword ptr [rsp+90h+ConnectNotifyCallback], r8d
0x140037da1  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x140037da8  call    WPP_SF_Dd
0x140037dad  jmp     short loc_140037DFB
0x140037daf  imul    rcx, r9, 0FFFFFFFFFFFFD8F0h
0x140037db6  mov     cs:qword_140028870, rcx
0x140037dbd  jmp     short loc_140037DFB
0x140037dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140037dc6  lea     rax, WPP_GLOBAL_Control
0x140037dcd  cmp     rcx, rax
0x140037dd0  jz      short loc_140037DF9
0x140037dd2  test    dword ptr [rcx+2Ch], 100h
0x140037dd9  jz      short loc_140037DF9
0x140037ddb  cmp     byte ptr [rcx+29h], 4
0x140037ddf  jb      short loc_140037DF9
0x140037de1  mov     rcx, [rcx+18h]
0x140037de5  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x140037dec  mov     edx, 0A7h
0x140037df1  mov     r9d, ebx
0x140037df4  call    WPP_SF_d
0x140037df9  xor     ebx, ebx
0x140037dfb  mov     rcx, [rbp+57h+P]; P
0x140037dff  test    rcx, rcx
0x140037e02  jz      short loc_140037E12
0x140037e04  xor     edx, edx; Tag
0x140037e06  call    cs:__imp_ExFreePoolWithTag
0x140037e0d  nop     dword ptr [rax+rax+00h]
0x140037e12  test    rdi, rdi
0x140037e15  jz      short loc_140037E2B
0x140037e17  mov     edx, 62546C43h; Tag
0x140037e1c  mov     rcx, rdi; P
0x140037e1f  call    cs:__imp_ExFreePoolWithTag
0x140037e26  nop     dword ptr [rax+rax+00h]
0x140037e2b  lea     r11, [rsp+90h+var_s0]
0x140037e33  mov     eax, ebx
0x140037e35  mov     rbx, [r11+20h]
0x140037e39  mov     rdi, [r11+28h]
0x140037e3d  mov     rsp, r11
0x140037e40  pop     rbp
0x140037e41  retn
```
