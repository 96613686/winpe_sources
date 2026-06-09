# DfscInitVariables

- ea: `0x14002a488`
- end: `0x14002a8fb`
- name: `DfscInitVariables`
- size: `1139`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002a904`

## callees

- `0x140002570`
- `0x1400027f8`
- `0x140011bc8`
- `0x1400125a4`
- `0x140018098`
- `0x140018544`
- `0x1400187e4`
- `0x140019d5c`
- `0x1400286dc`
- `0x14002a488`
- `0x14002aafc`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002a554`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002a554`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a7cf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a7cf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002a53a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002a53a`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002a613`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002a613`
- `ntoskrnl!KeAllocateCalloutStack` at `0x14002a753`
- `ntoskrnl!KeAllocateCalloutStack` at `0x14002a753`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14002a5c4`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14002a5c4`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002a62d`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002a640`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002a7b3`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002a62d`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002a640`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002a7b3`
- `ntoskrnl!ExAllocatePool2` at `0x14002a518`
- `ntoskrnl!ExAllocatePool2` at `0x14002a518`

## pseudocode

```c
__int64 __fastcall DfscInitVariables(PCUNICODE_STRING SourceString)
{
  BOOL v2; // eax
  int v3; // ebx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  int ProcessInformation; // [rsp+50h] [rbp+8h] BYREF

  LODWORD(xmmword_14000C740) = 0;
  *((_QWORD *)&xmmword_14000C740 + 1) = 0x93A8000093A80LL;
  dword_14000C760 = 2048;
  dword_14000C764 = 2048;
  Destination.Length = 0;
  *(_QWORD *)&xmmword_14000C750 = 0x38400000100LL;
  *((_QWORD *)&xmmword_14000C750 + 1) = 0x10000000064LL;
  dword_14000C768 = 10;
  Destination.MaximumLength = SourceString->Length + 24;
  Destination.Buffer = (PWSTR)ExAllocatePool2(258, Destination.MaximumLength, 1866688068);
  if ( Destination.Buffer )
  {
    RtlCopyUnicodeString(&Destination, SourceString);
    if ( !RtlAppendUnicodeToString(&Destination, L"\\Parameters") )
      DfscPolicyReadRegistryParameters();
  }
  LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) &= 0xFFFFFFF9;
  DfscReadLinkedConnectionPolicy();
  ProcessInformation = 0;
  qword_14000C720 = (__int64)&qword_14000C718;
  qword_14000C718 = (__int64)&qword_14000C718;
  qword_14000C7F0 = (__int64)&qword_14000C7E8;
  qword_14000C7E8 = (__int64)&qword_14000C7E8;
  v2 = ZwQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessLUIDDeviceMapsEnabled, &ProcessInformation, 4u, 0) >= 0
    && ProcessInformation != 0;
  DfsLUIDDeviceMapsEnabled = v2;
  DfscPathNameMaxDepth = 4;
  ExInitializePagedLookasideList(&DfscPathNameLookasideList, 0, 0, 0, 0x60u, 0x70634644u, 4u);
  DfscInitializationStatus |= 2u;
  ExInitializeResourceLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement);
  ExInitializeResourceLite((PERESOURCE)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  DfscInitializationStatus |= 1u;
  v3 = DfscCacheInitialize(&WPP_MAIN_CB.ActiveThreadCount, 0, dword_14000C764 << 10);
  if ( v3 >= 0 )
  {
    DfscInitializationStatus |= 4u;
    v3 = DfscCacheInitialize(&WPP_MAIN_CB.SecurityDescriptor, 1, dword_14000C760 << 10);
    if ( v3 >= 0 )
    {
      DfscInitializationStatus |= 8u;
      v3 = DfscNetUseTableInitialize(&Table);
      if ( v3 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
        {
          v5 = 12;
          goto LABEL_41;
        }
      }
      else
      {
        DfscInitializationStatus |= 0x10u;
        v3 = DfscNetUseTableInitialize(&qword_14000C710);
        if ( v3 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
          {
            v5 = 13;
            goto LABEL_41;
          }
        }
        else
        {
          DfscInitializationStatus |= 0x20u;
          v3 = DfscCredTableInitialize((struct _ERESOURCE **)&WPP_MAIN_CB.DeviceLock);
          if ( v3 )
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
            {
              v5 = 14;
              goto LABEL_41;
            }
          }
          else
          {
            DfscInitializationStatus |= 0x40u;
            Context = (PVOID)KeAllocateCalloutStack(0);
            if ( Context )
            {
              DfscInitializationStatus |= 0x80u;
              ExInitializeResourceLite(&Resource);
              byte_14000C76E = 0;
              RtlInitUnicodeString(&DestinationString, 0);
              DfscInitializeAndRegisterDAKeyChangeNotification();
              DfscInitializationStatus |= 0x100u;
              v3 = DfscInitializeContainerModule();
              if ( v3 >= 0 )
              {
                v3 = DfscRegisterMup();
                if ( v3 )
                {
                  v4 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
                  {
                    v5 = 17;
                    goto LABEL_41;
                  }
                }
                else
                {
                  LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) |= 1u;
                }
              }
              else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_a6101336a5263c931323b4a3bab755fb_Traceguids);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
              {
                WPP_SF_(
                  WPP_GLOBAL_Control->AttachedDevice,
                  (unsigned int)(v3 + 15),
                  WPP_a6101336a5263c931323b4a3bab755fb_Traceguids);
              }
              return (unsigned int)-1073741670;
            }
          }
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        v5 = 11;
        goto LABEL_41;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      v5 = 10;
LABEL_41:
      WPP_SF_D(v4->AttachedDevice, v5, WPP_a6101336a5263c931323b4a3bab755fb_Traceguids, (unsigned int)v3);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002a488  mov     [rsp+arg_8], rbx
0x14002a48d  push    rsi
0x14002a48e  sub     rsp, 40h
0x14002a492  mov     eax, 93A80h
0x14002a497  mov     dword ptr cs:xmmword_14000C740, 0
0x14002a4a1  mov     dword ptr cs:xmmword_14000C740+8, eax
0x14002a4a7  mov     rbx, rcx
0x14002a4aa  mov     dword ptr cs:xmmword_14000C740+0Ch, eax
0x14002a4b0  mov     r8d, 6F436644h
0x14002a4b6  mov     eax, 800h
0x14002a4bb  mov     dword ptr cs:xmmword_14000C750+0Ch, 100h
0x14002a4c5  mov     cs:dword_14000C760, eax
0x14002a4cb  mov     cs:dword_14000C764, eax
0x14002a4d1  xor     eax, eax
0x14002a4d3  mov     cs:Destination.Length, ax
0x14002a4da  mov     dword ptr cs:xmmword_14000C750, 100h
0x14002a4e4  mov     dword ptr cs:xmmword_14000C750+4, 384h
0x14002a4ee  mov     dword ptr cs:xmmword_14000C750+8, 64h ; 'd'
0x14002a4f8  mov     cs:dword_14000C768, 0Ah
0x14002a502  movzx   eax, word ptr [rcx]
0x14002a505  mov     ecx, 102h
0x14002a50a  add     ax, 18h
0x14002a50e  movzx   edx, ax
0x14002a511  mov     cs:Destination.MaximumLength, dx
0x14002a518  call    cs:__imp_ExAllocatePool2
0x14002a51f  nop     dword ptr [rax+rax+00h]
0x14002a524  mov     cs:Destination.Buffer, rax
0x14002a52b  test    rax, rax
0x14002a52e  jz      short loc_14002A569
0x14002a530  mov     rdx, rbx; SourceString
0x14002a533  lea     rcx, Destination; DestinationString
0x14002a53a  call    cs:__imp_RtlCopyUnicodeString
0x14002a541  nop     dword ptr [rax+rax+00h]
0x14002a546  lea     rdx, aParameters_0; "\\Parameters"
0x14002a54d  lea     rcx, Destination; Destination
0x14002a554  call    cs:__imp_RtlAppendUnicodeToString
0x14002a55b  nop     dword ptr [rax+rax+00h]
0x14002a560  test    eax, eax
0x14002a562  jnz     short loc_14002A569
0x14002a564  call    DfscPolicyReadRegistryParameters
0x14002a569  and     dword ptr cs:WPP_MAIN_CB.Queue+30h, 0FFFFFFF9h
0x14002a570  call    DfscReadLinkedConnectionPolicy
0x14002a575  lea     rax, qword_14000C718
0x14002a57c  mov     [rsp+48h+ProcessInformation], 0
0x14002a584  mov     esi, 4
0x14002a589  mov     cs:qword_14000C720, rax
0x14002a590  mov     cs:qword_14000C718, rax
0x14002a597  lea     r8, [rsp+48h+ProcessInformation]; ProcessInformation
0x14002a59c  lea     rax, qword_14000C7E8
0x14002a5a3  mov     [rsp+48h+ReturnLength], 0; ReturnLength
0x14002a5ac  mov     r9d, esi; ProcessInformationLength
0x14002a5af  mov     cs:qword_14000C7F0, rax
0x14002a5b6  lea     edx, [rsi+18h]; ProcessInformationClass
0x14002a5b9  mov     cs:qword_14000C7E8, rax
0x14002a5c0  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14002a5c4  call    cs:__imp_ZwQueryInformationProcess
0x14002a5cb  nop     dword ptr [rax+rax+00h]
0x14002a5d0  test    eax, eax
0x14002a5d2  jns     short loc_14002A5D8
0x14002a5d4  xor     eax, eax
0x14002a5d6  jmp     short loc_14002A5E1
0x14002a5d8  xor     eax, eax
0x14002a5da  cmp     [rsp+48h+ProcessInformation], eax
0x14002a5de  setnz   al
0x14002a5e1  mov     [rsp+48h+Depth], si; Depth
0x14002a5e6  lea     rcx, DfscPathNameLookasideList; Lookaside
0x14002a5ed  mov     [rsp+48h+Tag], 70634644h; Tag
0x14002a5f5  xor     r9d, r9d; Flags
0x14002a5f8  xor     r8d, r8d; Free
0x14002a5fb  mov     [rsp+48h+ReturnLength], 60h ; '`'; Size
0x14002a604  xor     edx, edx; Allocate
0x14002a606  mov     cs:DfsLUIDDeviceMapsEnabled, eax
0x14002a60c  mov     cs:DfscPathNameMaxDepth, si
0x14002a613  call    cs:__imp_ExInitializePagedLookasideList
0x14002a61a  nop     dword ptr [rax+rax+00h]
0x14002a61f  or      cs:DfscInitializationStatus, 2
0x14002a626  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14002a62d  call    cs:__imp_ExInitializeResourceLite
0x14002a634  nop     dword ptr [rax+rax+00h]
0x14002a639  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Resource
0x14002a640  call    cs:__imp_ExInitializeResourceLite
0x14002a647  nop     dword ptr [rax+rax+00h]
0x14002a64c  mov     r8d, cs:dword_14000C764
0x14002a653  lea     rcx, WPP_MAIN_CB.ActiveThreadCount
0x14002a65a  or      cs:DfscInitializationStatus, 1
0x14002a661  xor     edx, edx
0x14002a663  shl     r8d, 0Ah
0x14002a667  call    DfscCacheInitialize
0x14002a66c  mov     ebx, eax
0x14002a66e  test    eax, eax
0x14002a670  jns     short loc_14002A6A0
0x14002a672  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a679  lea     rax, WPP_GLOBAL_Control
0x14002a680  cmp     rcx, rax
0x14002a683  jz      loc_14002A8ED
0x14002a689  test    dword ptr [rcx+2Ch], 100000h
0x14002a690  jz      loc_14002A8ED
0x14002a696  mov     edx, 0Ah
0x14002a69b  jmp     loc_14002A8DA
0x14002a6a0  mov     r8d, cs:dword_14000C760
0x14002a6a7  lea     rcx, WPP_MAIN_CB.SecurityDescriptor
0x14002a6ae  or      cs:DfscInitializationStatus, esi
0x14002a6b4  mov     dl, 1
0x14002a6b6  shl     r8d, 0Ah
0x14002a6ba  call    DfscCacheInitialize
0x14002a6bf  mov     ebx, eax
0x14002a6c1  test    eax, eax
0x14002a6c3  jns     short loc_14002A6F3
0x14002a6c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a6cc  lea     rax, WPP_GLOBAL_Control
0x14002a6d3  cmp     rcx, rax
0x14002a6d6  jz      loc_14002A8ED
0x14002a6dc  test    dword ptr [rcx+2Ch], 100000h
0x14002a6e3  jz      loc_14002A8ED
0x14002a6e9  mov     edx, 0Bh
0x14002a6ee  jmp     loc_14002A8DA
0x14002a6f3  or      cs:DfscInitializationStatus, 8
0x14002a6fa  lea     rcx, Table
0x14002a701  call    DfscNetUseTableInitialize
0x14002a706  mov     ebx, eax
0x14002a708  test    eax, eax
0x14002a70a  jnz     loc_14002A8B9
0x14002a710  or      cs:DfscInitializationStatus, 10h
0x14002a717  lea     rcx, qword_14000C710
0x14002a71e  call    DfscNetUseTableInitialize
0x14002a723  mov     ebx, eax
0x14002a725  test    eax, eax
0x14002a727  jnz     loc_14002A896
0x14002a72d  or      cs:DfscInitializationStatus, 20h
0x14002a734  lea     rcx, WPP_MAIN_CB.DeviceLock
0x14002a73b  call    DfscCredTableInitialize
0x14002a740  mov     ebx, eax
0x14002a742  test    eax, eax
0x14002a744  jnz     loc_14002A873
0x14002a74a  or      cs:DfscInitializationStatus, 40h
0x14002a751  xor     ecx, ecx
0x14002a753  call    cs:__imp_KeAllocateCalloutStack
0x14002a75a  nop     dword ptr [rax+rax+00h]
0x14002a75f  mov     cs:Context, rax
0x14002a766  test    rax, rax
0x14002a769  jnz     short loc_14002A7A4
0x14002a76b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a772  lea     rax, WPP_GLOBAL_Control
0x14002a779  cmp     rcx, rax
0x14002a77c  jz      short loc_14002A79A
0x14002a77e  test    dword ptr [rcx+2Ch], 100000h
0x14002a785  jz      short loc_14002A79A
0x14002a787  mov     rcx, [rcx+18h]
0x14002a78b  lea     edx, [rbx+0Fh]
0x14002a78e  lea     r8, WPP_a6101336a5263c931323b4a3bab755fb_Traceguids
0x14002a795  call    WPP_SF_
0x14002a79a  mov     ebx, 0C000009Ah
0x14002a79f  jmp     loc_14002A8ED
0x14002a7a4  bts     cs:DfscInitializationStatus, 7
0x14002a7ac  lea     rcx, Resource; Resource
0x14002a7b3  call    cs:__imp_ExInitializeResourceLite
0x14002a7ba  nop     dword ptr [rax+rax+00h]
0x14002a7bf  xor     edx, edx; SourceString
0x14002a7c1  mov     cs:byte_14000C76E, 0
0x14002a7c8  lea     rcx, DestinationString; DestinationString
0x14002a7cf  call    cs:__imp_RtlInitUnicodeString
0x14002a7d6  nop     dword ptr [rax+rax+00h]
0x14002a7db  call    DfscInitializeAndRegisterDAKeyChangeNotification
0x14002a7e0  bts     cs:DfscInitializationStatus, 8
0x14002a7e8  call    DfscInitializeContainerModule
0x14002a7ed  mov     ebx, eax
0x14002a7ef  test    eax, eax
0x14002a7f1  jns     short loc_14002A831
0x14002a7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a7fa  lea     rax, WPP_GLOBAL_Control
0x14002a801  cmp     rcx, rax
0x14002a804  jz      loc_14002A8ED
0x14002a80a  test    dword ptr [rcx+2Ch], 100000h
0x14002a811  jz      loc_14002A8ED
0x14002a817  mov     rcx, [rcx+18h]
0x14002a81b  lea     r8, WPP_a6101336a5263c931323b4a3bab755fb_Traceguids
0x14002a822  mov     edx, 10h
0x14002a827  call    WPP_SF_
0x14002a82c  jmp     loc_14002A8ED
0x14002a831  call    DfscRegisterMup
0x14002a836  mov     ebx, eax
0x14002a838  test    eax, eax
0x14002a83a  jnz     short loc_14002A848
0x14002a83c  or      dword ptr cs:WPP_MAIN_CB.Queue+30h, 1
0x14002a843  jmp     loc_14002A8ED
0x14002a848  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a84f  lea     rax, WPP_GLOBAL_Control
0x14002a856  cmp     rcx, rax
0x14002a859  jz      loc_14002A8ED
0x14002a85f  test    dword ptr [rcx+2Ch], 100000h
0x14002a866  jz      loc_14002A8ED
0x14002a86c  mov     edx, 11h
0x14002a871  jmp     short loc_14002A8DA
0x14002a873  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a87a  lea     rax, WPP_GLOBAL_Control
0x14002a881  cmp     rcx, rax
0x14002a884  jz      short loc_14002A8ED
0x14002a886  test    dword ptr [rcx+2Ch], 100000h
0x14002a88d  jz      short loc_14002A8ED
0x14002a88f  mov     edx, 0Eh
0x14002a894  jmp     short loc_14002A8DA
0x14002a896  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a89d  lea     rax, WPP_GLOBAL_Control
0x14002a8a4  cmp     rcx, rax
0x14002a8a7  jz      short loc_14002A8ED
0x14002a8a9  test    dword ptr [rcx+2Ch], 100000h
0x14002a8b0  jz      short loc_14002A8ED
0x14002a8b2  mov     edx, 0Dh
0x14002a8b7  jmp     short loc_14002A8DA
0x14002a8b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a8c0  lea     rax, WPP_GLOBAL_Control
0x14002a8c7  cmp     rcx, rax
0x14002a8ca  jz      short loc_14002A8ED
0x14002a8cc  test    dword ptr [rcx+2Ch], 100000h
0x14002a8d3  jz      short loc_14002A8ED
0x14002a8d5  mov     edx, 0Ch
0x14002a8da  mov     rcx, [rcx+18h]
0x14002a8de  lea     r8, WPP_a6101336a5263c931323b4a3bab755fb_Traceguids
0x14002a8e5  mov     r9d, ebx
0x14002a8e8  call    WPP_SF_D
0x14002a8ed  mov     eax, ebx
0x14002a8ef  mov     rbx, [rsp+48h+arg_8]
0x14002a8f4  add     rsp, 40h
0x14002a8f8  pop     rsi
0x14002a8f9  retn
```
