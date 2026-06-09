# NdisRegisterProtocolDriver

- ea: `0x1400bcf90`
- end: `0x1400bd477`
- name: `NdisRegisterProtocolDriver`
- size: `1255`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE ProtocolDriverContext, PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS ProtocolCharacteristics, PNDIS_HANDLE NdisProtocolHandle)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140011190`
- `0x140014a50`
- `0x1400400d0`
- `0x140053280`
- `0x1400532f0`
- `0x140059c80`
- `0x14005ef10`
- `0x14007f500`
- `0x140082a20`
- `0x14008c780`
- `0x140092d28`
- `0x1400bc2fc`
- `0x1400bcf90`
- `0x14013eaa0`
- `0x140163330`
- `0x140163f20`
- `0x14016ff10`
- `0x1401701a0`
- `0x140171980`
- `0x140172030`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x1400bd190`
- `ntoskrnl!KeInitializeMutex` at `0x1400bd190`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400bd206`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400bd206`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400bd21c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400bd23a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400bd258`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400bd21c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400bd23a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400bd258`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd34b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd3e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd42f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd34b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd3e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd42f`
- `ntoskrnl!ExAllocatePool2` at `0x1400bd121`
- `ntoskrnl!ExAllocatePool2` at `0x1400bd121`

## pseudocode

```c
NDIS_STATUS __stdcall NdisRegisterProtocolDriver(
        NDIS_HANDLE ProtocolDriverContext,
        PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS ProtocolCharacteristics,
        PNDIS_HANDLE NdisProtocolHandle)
{
  _NDIS_PROTOCOL_BLOCK *v3; // rbx
  PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS v4; // rsi
  NDIS_STATUS v6; // edi
  unsigned __int8 *p_MinorNdisVersion; // rdi
  int v8; // edx
  _UNICODE_STRING *v10; // r13
  unsigned int v11; // r14d
  __int64 Pool2; // rax
  _QWORD *v13; // r12
  __int64 v14; // rax
  unsigned __int8 MajorNdisVersion; // cl
  unsigned __int8 v16; // r8
  unsigned int Flags; // eax
  unsigned __int16 Length; // ax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 ProtocolDriver; // rax
  NDIS_STATUS v22; // eax
  int v23; // edx
  _UNICODE_STRING *p_Name; // [rsp+28h] [rbp-48h]
  UNICODE_STRING String2; // [rsp+40h] [rbp-30h] BYREF
  UNICODE_STRING v26; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING v27; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+C8h] [rbp+58h] BYREF

  LOBYTE(v3) = 0;
  *(_QWORD *)&String2.Length = 786442;
  v29 = 0;
  String2.Buffer = L"TCPIP";
  v4 = ProtocolCharacteristics;
  *(_QWORD *)&v26.Length = 917516;
  v26.Buffer = L"TCPIP6";
  *(_QWORD *)&v27.Length = 1310738;
  v27.Buffer = L"NDISTEST6";
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    p_Name = &ProtocolCharacteristics->Name;
    LOBYTE(ProtocolCharacteristics) = 4;
    WPP_RECORDER_SF_Z(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)ProtocolCharacteristics,
      13,
      10,
      (struct _GUID *)&WPP_e3923b1e1d063659b60938af674e4994_Traceguids,
      (__int64)p_Name);
  }
  ndisIfEnsureNsiInitialized();
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  v6 = ndisValidateProtocolDriverCharacteristicsHeader(v4, &v29);
  if ( !v6 )
  {
    v6 = -1073676283;
    if ( (unsigned int)ndisValidate60Protocol(v4) != -1073676283 )
    {
      p_MinorNdisVersion = &v4->MinorNdisVersion;
      if ( v4->MajorNdisVersion <= 6u )
      {
        if ( v4->MajorNdisVersion != 6 )
        {
LABEL_15:
          v10 = &v4->Name;
          v11 = v4->Name.Length + 898;
          Pool2 = ExAllocatePool2(64, v11, 1651524686);
          v3 = (_NDIS_PROTOCOL_BLOCK *)Pool2;
          if ( Pool2 )
          {
            v13 = (_QWORD *)(Pool2 + 824);
            v14 = Pool2 + 832;
            *v13 = 0;
            v3->Triage.__ptr_.__value_ = 0;
            *(_QWORD *)(v14 + 40) = _NDIS_PROTOCOL_BLOCK::NotifyBindComplete;
            *(_QWORD *)(v14 + 16) = KWorkItemBase<MINIPORT_HOOK_DRIVER,KCoalescingWorkItem<MINIPORT_HOOK_DRIVER>>::CallbackThunk;
            *(_QWORD *)v14 = 0;
            *(_DWORD *)(v14 + 48) = 0;
            *(_QWORD *)(v14 + 32) = v3;
            *(_QWORD *)(v14 + 24) = v14;
            KeInitializeMutex(&v3->Mutex, 0xFFFFu);
            MajorNdisVersion = v4->MajorNdisVersion;
            v16 = *p_MinorNdisVersion;
            v3->MajorDriverVersion = v4->MajorDriverVersion;
            v3->MinorDriverVersion = v4->MinorDriverVersion;
            v3->ProtocolDriverContext = ProtocolDriverContext;
            v3->Header.Size = v11;
            v3->Name.Buffer = (wchar_t *)&v3[1].Header.Type;
            Flags = v4->Flags;
            v3->Flags = Flags;
            *(_WORD *)&v3->Header.Type = 259;
            v3->MajorNdisVersion = MajorNdisVersion;
            v3->MinorNdisVersion = v16;
            if ( MajorNdisVersion <= 6u && (MajorNdisVersion != 6 || v16 < 0x32u) )
              v3->Flags = Flags & 0xF0000000;
            Length = v10->Length;
            v3->Name.Length = v10->Length;
            v3->Name.MaximumLength = Length;
            RtlUpcaseUnicodeString(&v3->Name, &v4->Name, 0);
            v3->IsIPv4 = RtlCompareUnicodeString(&v3->Name, &String2, 0) == 0;
            v3->IsIPv6 = RtlCompareUnicodeString(&v3->Name, &v26, 0) == 0;
            v3->IsNdisTest6 = RtlCompareUnicodeString(&v3->Name, &v27, 0) == 0;
            v3->BindAdapterHandlerEx = v4->BindAdapterHandlerEx;
            v3->UnbindAdapterHandlerEx = v4->UnbindAdapterHandlerEx;
            v3->OpenAdapterCompleteHandlerEx = v4->OpenAdapterCompleteHandlerEx;
            v3->CloseAdapterCompleteHandlerEx = v4->CloseAdapterCompleteHandlerEx;
            v3->PnPEventHandler = (int (__fastcall *)(void *, _NET_PNP_EVENT *))v4->NetPnPEventHandler;
            v3->UninstallHandler = v4->UninstallHandler;
            v3->StatusHandlerEx = v4->StatusHandlerEx;
            v3->ReceiveNetBufferListsHandler = v4->ReceiveNetBufferListsHandler;
            v3->SendNetBufferListsCompleteHandler = v4->SendNetBufferListsCompleteHandler;
            v3->OidRequestCompleteHandler = v4->OidRequestCompleteHandler;
            if ( v4->MajorNdisVersion > 6u || v4->MajorNdisVersion == 6 && *p_MinorNdisVersion )
              v3->DirectOidRequestCompleteHandler = v4->DirectOidRequestCompleteHandler;
            ndisInitializeRef(&v3->Ref, 0x10u);
            LOBYTE(v20) = v3->MajorNdisVersion <= 6u && (v3->MajorNdisVersion != 6 || v3->MinorNdisVersion < 0x52u);
            LOBYTE(v19) = 1;
            ProtocolDriver = ndisBindGetProtocolDriver(&v29, &v3->Name, v19, v20);
            KRef<NDIS_BIND_PROTOCOL_DRIVER>::operator=(v13, ProtocolDriver);
            KRef<NDIS_BIND_PROTOCOL_DRIVER>::unref(&v29);
            if ( *v13 )
            {
              if ( (unsigned int)Feature_NdisTriageData__private_IsEnabledDeviceUsageNoInline()
                && (v22 = ndisRegisterProtocolTriageData(v3), (v6 = v22) != 0) )
              {
                if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v23) = 2;
                  WPP_RECORDER_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 8),
                    v23,
                    13,
                    11,
                    (struct _GUID *)&WPP_e3923b1e1d063659b60938af674e4994_Traceguids,
                    (char)v3,
                    v22);
                }
                ndisDereferenceRef(&v3->Ref.SpinLock, 0xFFu);
                _NDIS_PROTOCOL_BLOCK::~_NDIS_PROTOCOL_BLOCK(v3);
                ExFreePoolWithTag(v3, 0);
              }
              else
              {
                *NdisProtocolHandle = v3;
                v6 = ndisInvokeSetOptions(v3, v4);
                if ( v6 )
                {
                  ndisDereferenceRef(&v3->Ref.SpinLock, 0xFFu);
                  _NDIS_PROTOCOL_BLOCK::~_NDIS_PROTOCOL_BLOCK(v3);
                  ExFreePoolWithTag(v3, 0);
                  LOBYTE(v3) = 0;
                  *NdisProtocolHandle = 0;
                }
                else
                {
                  ndisWriteDriverNDISVersionToServiceKey(
                    v3->MajorNdisVersion,
                    v3->MinorNdisVersion,
                    1,
                    v3->MajorDriverVersion,
                    v3->MinorDriverVersion,
                    &v3->Name);
                  ndisRegisterProtocolDriverCommon(v3);
                  v6 = 0;
                }
              }
            }
            else
            {
              ndisDereferenceRef(&v3->Ref.SpinLock, 0xFFu);
              _NDIS_PROTOCOL_BLOCK::~_NDIS_PROTOCOL_BLOCK(v3);
              ExFreePoolWithTag(v3, 0);
              v6 = -1073741670;
            }
          }
          else
          {
            v6 = -1073741670;
          }
          goto LABEL_11;
        }
        if ( *p_MinorNdisVersion < 0x59u )
        {
          if ( *p_MinorNdisVersion >= 0x32u && (v4->Flags & 0xFFFFFF9) != 0 )
            goto LABEL_10;
          goto LABEL_15;
        }
      }
      if ( (v4->Flags & 0xFFFFFF1) != 0 )
      {
LABEL_10:
        v6 = -1073741811;
        goto LABEL_11;
      }
      goto LABEL_15;
    }
  }
LABEL_11:
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qZL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v8,
      13,
      12,
      (struct _GUID *)&WPP_e3923b1e1d063659b60938af674e4994_Traceguids,
      (char)v3,
      (__int64)&v4->Name,
      v6);
  return v6;
}

```

## disassembly

```asm
0x1400bcf90  mov     [rsp-38h+arg_0], rbx
0x1400bcf95  mov     [rsp-38h+arg_10], r8
0x1400bcf9a  push    rbp
0x1400bcf9b  push    rsi
0x1400bcf9c  push    rdi
0x1400bcf9d  push    r12
0x1400bcf9f  push    r13
0x1400bcfa1  push    r14
0x1400bcfa3  push    r15
0x1400bcfa5  mov     rbp, rsp
0x1400bcfa8  sub     rsp, 70h
0x1400bcfac  xor     ebx, ebx
0x1400bcfae  mov     qword ptr [rbp+String2.Length], 0C000Ah
0x1400bcfb6  lea     rax, aTcpip; "TCPIP"
0x1400bcfbd  mov     [rbp+arg_18], ebx
0x1400bcfc0  mov     [rbp+String2.Buffer], rax
0x1400bcfc4  mov     rsi, rdx
0x1400bcfc7  lea     rax, aTcpip6; "TCPIP6"
0x1400bcfce  mov     qword ptr [rbp+var_20.Length], 0E000Ch
0x1400bcfd6  mov     [rbp+var_20.Buffer], rax
0x1400bcfda  lea     r9d, [rbx+0Ah]; int
0x1400bcfde  lea     rax, aNdistest6; "NDISTEST6"
0x1400bcfe5  mov     qword ptr [rbp+var_10.Length], 140012h
0x1400bcfed  mov     [rbp+var_10.Buffer], rax
0x1400bcff1  lea     r12d, [rbx+0Ch]
0x1400bcff5  mov     r15, rcx
0x1400bcff8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400bcfff  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400bd006  lea     r14, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400bd00d  jz      short loc_1400BD033
0x1400bd00f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd016  lea     rax, [rdx+10h]
0x1400bd01a  mov     [rsp+70h+var_48], rax; __int64
0x1400bd01f  lea     r8d, [rbx+0Dh]; int
0x1400bd023  mov     dl, 4; int
0x1400bd025  mov     [rsp+70h+var_50], r14; struct _GUID *
0x1400bd02a  mov     rcx, [rcx+40h]; int
0x1400bd02e  call    WPP_RECORDER_SF_Z
0x1400bd033  call    ?ndisIfEnsureNsiInitialized@@YAJXZ; ndisIfEnsureNsiInitialized(void)
0x1400bd038  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1400bd03f  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x1400bd044  lea     rdx, [rbp+arg_18]; unsigned int *
0x1400bd048  mov     rcx, rsi; struct _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *
0x1400bd04b  call    ?ndisValidateProtocolDriverCharacteristicsHeader@@YAHPEBU_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS@@PEAK@Z; ndisValidateProtocolDriverCharacteristicsHeader(_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS const *,ulong *)
0x1400bd050  mov     edi, eax
0x1400bd052  test    eax, eax
0x1400bd054  jnz     short loc_1400BD093
0x1400bd056  mov     rcx, rsi; struct _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *
0x1400bd059  call    ?ndisValidate60Protocol@@YAHPEAU_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS@@@Z; ndisValidate60Protocol(_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *)
0x1400bd05e  mov     edi, 0C0010005h
0x1400bd063  cmp     eax, edi
0x1400bd065  jz      short loc_1400BD093
0x1400bd067  cmp     byte ptr [rsi+4], 6
0x1400bd06b  lea     rdi, [rsi+5]
0x1400bd06f  ja      loc_1400BD0FA
0x1400bd075  jnz     loc_1400BD103
0x1400bd07b  cmp     byte ptr [rdi], 59h ; 'Y'
0x1400bd07e  jnb     short loc_1400BD0FA
0x1400bd080  cmp     byte ptr [rdi], 32h ; '2'
0x1400bd083  jb      short loc_1400BD103
0x1400bd085  test    dword ptr [rsi+8], 0FFFFFF9h
0x1400bd08c  jz      short loc_1400BD103
0x1400bd08e  mov     edi, 0C000000Dh
0x1400bd093  lea     r15, WPP_RECORDER_INITIALIZED
0x1400bd09a  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1400bd0a1  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x1400bd0a6  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400bd0ad  jz      short loc_1400BD0DF
0x1400bd0af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd0b6  lea     rax, [rsi+10h]
0x1400bd0ba  mov     dword ptr [rsp+70h+var_38], edi; char
0x1400bd0be  mov     r9d, r12d; int
0x1400bd0c1  mov     qword ptr [rsp+70h+var_40], rax; __int64
0x1400bd0c6  mov     r8d, 0Dh; int
0x1400bd0cc  mov     [rsp+70h+var_48], rbx; char
0x1400bd0d1  mov     rcx, [rcx+40h]; int
0x1400bd0d5  mov     [rsp+70h+var_50], r14; struct _GUID *
0x1400bd0da  call    WPP_RECORDER_SF_qZL
0x1400bd0df  mov     rbx, [rsp+70h+arg_0]
0x1400bd0e7  mov     eax, edi
0x1400bd0e9  add     rsp, 70h
0x1400bd0ed  pop     r15
0x1400bd0ef  pop     r14
0x1400bd0f1  pop     r13
0x1400bd0f3  pop     r12
0x1400bd0f5  pop     rdi
0x1400bd0f6  pop     rsi
0x1400bd0f7  pop     rbp
0x1400bd0f8  retn
0x1400bd0fa  test    dword ptr [rsi+8], 0FFFFFF1h
0x1400bd101  jnz     short loc_1400BD08E
0x1400bd103  lea     r13, [rsi+10h]
0x1400bd107  mov     ecx, 40h ; '@'
0x1400bd10c  movzx   r14d, word ptr [r13+0]
0x1400bd111  mov     r8d, 6270444Eh
0x1400bd117  add     r14d, 382h
0x1400bd11e  mov     edx, r14d
0x1400bd121  call    cs:__imp_ExAllocatePool2
0x1400bd128  nop     dword ptr [rax+rax+00h]
0x1400bd12d  mov     rbx, rax
0x1400bd130  test    rax, rax
0x1400bd133  jnz     short loc_1400BD146
0x1400bd135  mov     edi, 0C000009Ah
0x1400bd13a  lea     r14, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400bd141  jmp     loc_1400BD093
0x1400bd146  xor     edx, edx
0x1400bd148  lea     r12, [rax+338h]
0x1400bd14f  add     rax, 340h
0x1400bd155  mov     [r12], rdx
0x1400bd159  lea     rcx, ?NotifyBindComplete@_NDIS_PROTOCOL_BLOCK@@QEAAXXZ; _NDIS_PROTOCOL_BLOCK::NotifyBindComplete(void)
0x1400bd160  mov     [rbx+378h], rdx
0x1400bd167  mov     [rax+28h], rcx
0x1400bd16b  lea     rcx, ?CallbackThunk@?$KWorkItemBase@VMINIPORT_HOOK_DRIVER@@V?$KCoalescingWorkItem@VMINIPORT_HOOK_DRIVER@@@@@@CAXPEAX@Z; KWorkItemBase<MINIPORT_HOOK_DRIVER,KCoalescingWorkItem<MINIPORT_HOOK_DRIVER>>::CallbackThunk(void *)
0x1400bd172  mov     [rax+10h], rcx
0x1400bd176  lea     rcx, [rbx+168h]; Mutex
0x1400bd17d  mov     [rax], rdx
0x1400bd180  mov     [rax+30h], edx
0x1400bd183  mov     edx, 0FFFFh; Level
0x1400bd188  mov     [rax+20h], rbx
0x1400bd18c  mov     [rax+18h], rax
0x1400bd190  call    cs:__imp_KeInitializeMutex
0x1400bd197  nop     dword ptr [rax+rax+00h]
0x1400bd19c  mov     al, [rsi+6]
0x1400bd19f  mov     cl, [rsi+4]
0x1400bd1a2  mov     r8b, [rdi]
0x1400bd1a5  mov     [rbx+3Ah], al
0x1400bd1a8  mov     al, [rsi+7]
0x1400bd1ab  mov     [rbx+3Bh], al
0x1400bd1ae  lea     rax, [rbx+380h]
0x1400bd1b5  mov     [rbx+8], r15
0x1400bd1b9  lea     r15, [rbx+48h]
0x1400bd1bd  mov     [rbx+2], r14w
0x1400bd1c2  mov     r14b, 6
0x1400bd1c5  mov     [r15+8], rax
0x1400bd1c9  mov     eax, [rsi+8]
0x1400bd1cc  mov     [rbx+40h], eax
0x1400bd1cf  mov     word ptr [rbx], 103h
0x1400bd1d4  mov     [rbx+38h], cl
0x1400bd1d7  mov     [rbx+39h], r8b
0x1400bd1db  cmp     cl, r14b
0x1400bd1de  ja      short loc_1400BD1F0
0x1400bd1e0  jnz     short loc_1400BD1E8
0x1400bd1e2  cmp     r8b, 32h ; '2'
0x1400bd1e6  jnb     short loc_1400BD1F0
0x1400bd1e8  and     eax, 0F0000000h
0x1400bd1ed  mov     [rbx+40h], eax
0x1400bd1f0  movzx   eax, word ptr [r13+0]
0x1400bd1f5  xor     r8d, r8d; AllocateDestinationString
0x1400bd1f8  mov     rdx, r13; SourceString
0x1400bd1fb  mov     [r15], ax
0x1400bd1ff  mov     rcx, r15; DestinationString
0x1400bd202  mov     [rbx+4Ah], ax
0x1400bd206  call    cs:__imp_RtlUpcaseUnicodeString
0x1400bd20d  nop     dword ptr [rax+rax+00h]
0x1400bd212  xor     r8d, r8d; CaseInSensitive
0x1400bd215  lea     rdx, [rbp+String2]; String2
0x1400bd219  mov     rcx, r15; String1
0x1400bd21c  call    cs:__imp_RtlCompareUnicodeString
0x1400bd223  nop     dword ptr [rax+rax+00h]
0x1400bd228  lea     rdx, [rbp+var_20]; String2
0x1400bd22c  mov     rcx, r15; String1
0x1400bd22f  test    eax, eax
0x1400bd231  setz    al
0x1400bd234  xor     r8d, r8d; CaseInSensitive
0x1400bd237  mov     [rbx+58h], al
0x1400bd23a  call    cs:__imp_RtlCompareUnicodeString
0x1400bd241  nop     dword ptr [rax+rax+00h]
0x1400bd246  lea     rdx, [rbp+var_10]; String2
0x1400bd24a  mov     rcx, r15; String1
0x1400bd24d  test    eax, eax
0x1400bd24f  setz    al
0x1400bd252  xor     r8d, r8d; CaseInSensitive
0x1400bd255  mov     [rbx+59h], al
0x1400bd258  call    cs:__imp_RtlCompareUnicodeString
0x1400bd25f  nop     dword ptr [rax+rax+00h]
0x1400bd264  test    eax, eax
0x1400bd266  setz    al
0x1400bd269  mov     [rbx+5Ah], al
0x1400bd26c  mov     rax, [rsi+28h]
0x1400bd270  mov     [rbx+60h], rax
0x1400bd274  mov     rax, [rsi+30h]
0x1400bd278  mov     [rbx+68h], rax
0x1400bd27c  mov     rax, [rsi+38h]
0x1400bd280  mov     [rbx+70h], rax
0x1400bd284  mov     rax, [rsi+40h]
0x1400bd288  mov     [rbx+78h], rax
0x1400bd28c  mov     rax, [rsi+48h]
0x1400bd290  mov     [rbx+80h], rax
0x1400bd297  mov     rax, [rsi+50h]
0x1400bd29b  mov     [rbx+90h], rax
0x1400bd2a2  mov     rax, [rsi+60h]
0x1400bd2a6  mov     [rbx+0A0h], rax
0x1400bd2ad  mov     rax, [rsi+68h]
0x1400bd2b1  mov     [rbx+0B0h], rax
0x1400bd2b8  mov     rax, [rsi+70h]
0x1400bd2bc  mov     [rbx+0B8h], rax
0x1400bd2c3  mov     rax, [rsi+58h]
0x1400bd2c7  mov     [rbx+140h], rax
0x1400bd2ce  cmp     [rsi+4], r14b
0x1400bd2d2  ja      short loc_1400BD2DB
0x1400bd2d4  jnz     short loc_1400BD2E6
0x1400bd2d6  cmp     byte ptr [rdi], 1
0x1400bd2d9  jb      short loc_1400BD2E6
0x1400bd2db  mov     rax, [rsi+78h]
0x1400bd2df  mov     [rbx+308h], rax
0x1400bd2e6  lea     r14, [rbx+20h]
0x1400bd2ea  mov     dl, 10h; unsigned __int8
0x1400bd2ec  mov     rcx, r14; struct _REFERENCE_EX *
0x1400bd2ef  call    ?ndisInitializeRef@@YAXPEAU_REFERENCE_EX@@E@Z; ndisInitializeRef(_REFERENCE_EX *,uchar)
0x1400bd2f4  cmp     byte ptr [rbx+38h], 6
0x1400bd2f8  ja      short loc_1400BD307
0x1400bd2fa  jnz     short loc_1400BD302
0x1400bd2fc  cmp     byte ptr [rbx+39h], 52h ; 'R'
0x1400bd300  jnb     short loc_1400BD307
0x1400bd302  mov     r9b, 1
0x1400bd305  jmp     short loc_1400BD30A
0x1400bd307  xor     r9b, r9b
0x1400bd30a  mov     r8b, 1
0x1400bd30d  lea     rcx, [rbp+arg_18]
0x1400bd311  mov     rdx, r15
0x1400bd314  call    ?ndisBindGetProtocolDriver@@YA?AV?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@PEAU_UNICODE_STRING@@_N1@Z; ndisBindGetProtocolDriver(_UNICODE_STRING *,bool,bool)
0x1400bd319  mov     rdx, rax
0x1400bd31c  mov     rcx, r12
0x1400bd31f  call    ??4?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@QEAAAEAV0@$$QEAV0@@Z; KRef<NDIS_BIND_PROTOCOL_DRIVER>::operator=(KRef<NDIS_BIND_PROTOCOL_DRIVER> &&)
0x1400bd324  lea     rcx, [rbp+arg_18]
0x1400bd328  call    ?unref@?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@AEAAXXZ; KRef<NDIS_BIND_PROTOCOL_DRIVER>::unref(void)
0x1400bd32d  cmp     qword ptr [r12], 0
0x1400bd332  jnz     short loc_1400BD36E
0x1400bd334  mov     dl, 0FFh; unsigned __int8
0x1400bd336  mov     rcx, r14; SpinLock
0x1400bd339  call    ?ndisDereferenceRef@@YAEPEAU_REFERENCE_EX@@E@Z; ndisDereferenceRef(_REFERENCE_EX *,uchar)
0x1400bd33e  mov     rcx, rbx; this
0x1400bd341  call    ??1_NDIS_PROTOCOL_BLOCK@@QEAA@XZ; _NDIS_PROTOCOL_BLOCK::~_NDIS_PROTOCOL_BLOCK(void)
0x1400bd346  xor     edx, edx; Tag
0x1400bd348  mov     rcx, rbx; P
0x1400bd34b  call    cs:__imp_ExFreePoolWithTag
0x1400bd352  nop     dword ptr [rax+rax+00h]
0x1400bd357  mov     edi, 0C000009Ah
0x1400bd35c  lea     r14, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400bd363  mov     r12d, 0Ch
0x1400bd369  jmp     loc_1400BD093
0x1400bd36e  call    Feature_NdisTriageData__private_IsEnabledDeviceUsageNoInline
0x1400bd373  test    eax, eax
0x1400bd375  jz      loc_1400BD3FF
0x1400bd37b  mov     rcx, rbx
0x1400bd37e  call    ndisRegisterProtocolTriageData
0x1400bd383  mov     edi, eax
0x1400bd385  test    eax, eax
0x1400bd387  jz      short loc_1400BD3FF
0x1400bd389  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400bd390  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400bd397  jz      short loc_1400BD3CA
0x1400bd399  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd3a0  mov     r9d, 0Bh; int
0x1400bd3a6  mov     dword ptr [rsp+70h+var_40], eax; char
0x1400bd3aa  mov     dl, 2; int
0x1400bd3ac  lea     rax, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400bd3b3  mov     [rsp+70h+var_48], rbx; char
0x1400bd3b8  mov     [rsp+70h+var_50], rax; struct _GUID *
0x1400bd3bd  mov     rcx, [rcx+40h]; int
0x1400bd3c1  lea     r8d, [r9+2]; int
0x1400bd3c5  call    WPP_RECORDER_SF_qD
0x1400bd3ca  mov     dl, 0FFh; unsigned __int8
0x1400bd3cc  mov     rcx, r14; SpinLock
0x1400bd3cf  call    ?ndisDereferenceRef@@YAEPEAU_REFERENCE_EX@@E@Z; ndisDereferenceRef(_REFERENCE_EX *,uchar)
0x1400bd3d4  mov     rcx, rbx; this
0x1400bd3d7  call    ??1_NDIS_PROTOCOL_BLOCK@@QEAA@XZ; _NDIS_PROTOCOL_BLOCK::~_NDIS_PROTOCOL_BLOCK(void)
0x1400bd3dc  xor     edx, edx; Tag
0x1400bd3de  mov     rcx, rbx; P
0x1400bd3e1  call    cs:__imp_ExFreePoolWithTag
0x1400bd3e8  nop     dword ptr [rax+rax+00h]
0x1400bd3ed  lea     r14, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400bd3f4  mov     r12d, 0Ch
0x1400bd3fa  jmp     loc_1400BD09A
0x1400bd3ff  mov     r12, [rbp+arg_10]
0x1400bd403  mov     rdx, rsi; struct _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *
0x1400bd406  mov     rcx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x1400bd409  mov     [r12], rbx
0x1400bd40d  call    ?ndisInvokeSetOptions@@_Y2PAGE@@AHPEAU_NDIS_PROTOCOL_BLOCK@@PEAU_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS@@@Z; ndisInvokeSetOptions(_NDIS_PROTOCOL_BLOCK *,_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *)
0x1400bd412  mov     edi, eax
0x1400bd414  test    eax, eax
0x1400bd416  jz      short loc_1400BD446
0x1400bd418  mov     dl, 0FFh; unsigned __int8
0x1400bd41a  mov     rcx, r14; SpinLock
0x1400bd41d  call    ?ndisDereferenceRef@@YAEPEAU_REFERENCE_EX@@E@Z; ndisDereferenceRef(_REFERENCE_EX *,uchar)
0x1400bd422  mov     rcx, rbx; this
0x1400bd425  call    ??1_NDIS_PROTOCOL_BLOCK@@QEAA@XZ; _NDIS_PROTOCOL_BLOCK::~_NDIS_PROTOCOL_BLOCK(void)
0x1400bd42a  xor     edx, edx; Tag
0x1400bd42c  mov     rcx, rbx; P
0x1400bd42f  call    cs:__imp_ExFreePoolWithTag
0x1400bd436  nop     dword ptr [rax+rax+00h]
0x1400bd43b  xor     ebx, ebx
0x1400bd43d  mov     [r12], rbx
0x1400bd441  jmp     loc_1400BD35C
0x1400bd446  movzx   eax, byte ptr [rbx+3Bh]
0x1400bd44a  mov     r8b, 1; unsigned __int8
0x1400bd44d  movzx   r9d, byte ptr [rbx+3Ah]; unsigned int
0x1400bd452  movzx   edx, byte ptr [rbx+39h]; unsigned int
0x1400bd456  movzx   ecx, byte ptr [rbx+38h]; unsigned int
0x1400bd45a  mov     [rsp+70h+var_48], r15; struct _UNICODE_STRING *
  ... truncated ...
```
