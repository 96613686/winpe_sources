# NdisRegisterProtocolDriver

- ea: `0x1400b7b60`
- end: `0x1400b8047`
- name: `NdisRegisterProtocolDriver`
- size: `1255`
- prototype: `NDIS_STATUS __stdcall(NDIS_HANDLE ProtocolDriverContext, PNDIS_PROTOCOL_DRIVER_CHARACTERISTICS ProtocolCharacteristics, PNDIS_HANDLE NdisProtocolHandle)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x14001d030`
- `0x1400208f0`
- `0x14003d920`
- `0x14004e050`
- `0x14004e0c0`
- `0x140054b80`
- `0x14005a920`
- `0x140079e30`
- `0x14007d130`
- `0x140087490`
- `0x14008e2e8`
- `0x1400b6ecc`
- `0x1400b7b60`
- `0x140137aa0`
- `0x14015c390`
- `0x14015cf80`
- `0x140169020`
- `0x1401692b0`
- `0x14016aa90`
- `0x14016b140`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x1400b7d60`
- `ntoskrnl!KeInitializeMutex` at `0x1400b7d60`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400b7dd6`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400b7dd6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7dec`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7e0a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7e28`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7dec`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7e0a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b7e28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7f1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7fb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7fff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7f1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7fb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7fff`
- `ntoskrnl!ExAllocatePool2` at `0x1400b7cf1`
- `ntoskrnl!ExAllocatePool2` at `0x1400b7cf1`

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
0x1400b7b60  mov     [rsp-38h+arg_0], rbx
0x1400b7b65  mov     [rsp-38h+arg_10], r8
0x1400b7b6a  push    rbp
0x1400b7b6b  push    rsi
0x1400b7b6c  push    rdi
0x1400b7b6d  push    r12
0x1400b7b6f  push    r13
0x1400b7b71  push    r14
0x1400b7b73  push    r15
0x1400b7b75  mov     rbp, rsp
0x1400b7b78  sub     rsp, 70h
0x1400b7b7c  xor     ebx, ebx
0x1400b7b7e  mov     qword ptr [rbp+String2.Length], 0C000Ah
0x1400b7b86  lea     rax, aTcpip; "TCPIP"
0x1400b7b8d  mov     [rbp+arg_18], ebx
0x1400b7b90  mov     [rbp+String2.Buffer], rax
0x1400b7b94  mov     rsi, rdx
0x1400b7b97  lea     rax, aTcpip6; "TCPIP6"
0x1400b7b9e  mov     qword ptr [rbp+var_20.Length], 0E000Ch
0x1400b7ba6  mov     [rbp+var_20.Buffer], rax
0x1400b7baa  lea     r9d, [rbx+0Ah]; int
0x1400b7bae  lea     rax, aNdistest6; "NDISTEST6"
0x1400b7bb5  mov     qword ptr [rbp+var_10.Length], 140012h
0x1400b7bbd  mov     [rbp+var_10.Buffer], rax
0x1400b7bc1  lea     r12d, [rbx+0Ch]
0x1400b7bc5  mov     r15, rcx
0x1400b7bc8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b7bcf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b7bd6  lea     r14, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400b7bdd  jz      short loc_1400B7C03
0x1400b7bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7be6  lea     rax, [rdx+10h]
0x1400b7bea  mov     [rsp+70h+var_48], rax; __int64
0x1400b7bef  lea     r8d, [rbx+0Dh]; int
0x1400b7bf3  mov     dl, 4; int
0x1400b7bf5  mov     [rsp+70h+var_50], r14; struct _GUID *
0x1400b7bfa  mov     rcx, [rcx+40h]; int
0x1400b7bfe  call    WPP_RECORDER_SF_Z
0x1400b7c03  call    ?ndisIfEnsureNsiInitialized@@YAJXZ; ndisIfEnsureNsiInitialized(void)
0x1400b7c08  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1400b7c0f  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x1400b7c14  lea     rdx, [rbp+arg_18]; unsigned int *
0x1400b7c18  mov     rcx, rsi; struct _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *
0x1400b7c1b  call    ?ndisValidateProtocolDriverCharacteristicsHeader@@YAHPEBU_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS@@PEAK@Z; ndisValidateProtocolDriverCharacteristicsHeader(_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS const *,ulong *)
0x1400b7c20  mov     edi, eax
0x1400b7c22  test    eax, eax
0x1400b7c24  jnz     short loc_1400B7C63
0x1400b7c26  mov     rcx, rsi; struct _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *
0x1400b7c29  call    ?ndisValidate60Protocol@@YAHPEAU_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS@@@Z; ndisValidate60Protocol(_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *)
0x1400b7c2e  mov     edi, 0C0010005h
0x1400b7c33  cmp     eax, edi
0x1400b7c35  jz      short loc_1400B7C63
0x1400b7c37  cmp     byte ptr [rsi+4], 6
0x1400b7c3b  lea     rdi, [rsi+5]
0x1400b7c3f  ja      loc_1400B7CCA
0x1400b7c45  jnz     loc_1400B7CD3
0x1400b7c4b  cmp     byte ptr [rdi], 59h ; 'Y'
0x1400b7c4e  jnb     short loc_1400B7CCA
0x1400b7c50  cmp     byte ptr [rdi], 32h ; '2'
0x1400b7c53  jb      short loc_1400B7CD3
0x1400b7c55  test    dword ptr [rsi+8], 0FFFFFF9h
0x1400b7c5c  jz      short loc_1400B7CD3
0x1400b7c5e  mov     edi, 0C000000Dh
0x1400b7c63  lea     r15, WPP_RECORDER_INITIALIZED
0x1400b7c6a  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1400b7c71  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x1400b7c76  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400b7c7d  jz      short loc_1400B7CAF
0x1400b7c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7c86  lea     rax, [rsi+10h]
0x1400b7c8a  mov     dword ptr [rsp+70h+var_38], edi; char
0x1400b7c8e  mov     r9d, r12d; int
0x1400b7c91  mov     qword ptr [rsp+70h+var_40], rax; __int64
0x1400b7c96  mov     r8d, 0Dh; int
0x1400b7c9c  mov     [rsp+70h+var_48], rbx; char
0x1400b7ca1  mov     rcx, [rcx+40h]; int
0x1400b7ca5  mov     [rsp+70h+var_50], r14; struct _GUID *
0x1400b7caa  call    WPP_RECORDER_SF_qZL
0x1400b7caf  mov     rbx, [rsp+70h+arg_0]
0x1400b7cb7  mov     eax, edi
0x1400b7cb9  add     rsp, 70h
0x1400b7cbd  pop     r15
0x1400b7cbf  pop     r14
0x1400b7cc1  pop     r13
0x1400b7cc3  pop     r12
0x1400b7cc5  pop     rdi
0x1400b7cc6  pop     rsi
0x1400b7cc7  pop     rbp
0x1400b7cc8  retn
0x1400b7cca  test    dword ptr [rsi+8], 0FFFFFF1h
0x1400b7cd1  jnz     short loc_1400B7C5E
0x1400b7cd3  lea     r13, [rsi+10h]
0x1400b7cd7  mov     ecx, 40h ; '@'
0x1400b7cdc  movzx   r14d, word ptr [r13+0]
0x1400b7ce1  mov     r8d, 6270444Eh
0x1400b7ce7  add     r14d, 382h
0x1400b7cee  mov     edx, r14d
0x1400b7cf1  call    cs:__imp_ExAllocatePool2
0x1400b7cf8  nop     dword ptr [rax+rax+00h]
0x1400b7cfd  mov     rbx, rax
0x1400b7d00  test    rax, rax
0x1400b7d03  jnz     short loc_1400B7D16
0x1400b7d05  mov     edi, 0C000009Ah
0x1400b7d0a  lea     r14, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400b7d11  jmp     loc_1400B7C63
0x1400b7d16  xor     edx, edx
0x1400b7d18  lea     r12, [rax+338h]
0x1400b7d1f  add     rax, 340h
0x1400b7d25  mov     [r12], rdx
0x1400b7d29  lea     rcx, ?NotifyBindComplete@_NDIS_PROTOCOL_BLOCK@@QEAAXXZ; _NDIS_PROTOCOL_BLOCK::NotifyBindComplete(void)
0x1400b7d30  mov     [rbx+378h], rdx
0x1400b7d37  mov     [rax+28h], rcx
0x1400b7d3b  lea     rcx, ?CallbackThunk@?$KWorkItemBase@VMINIPORT_HOOK_DRIVER@@V?$KCoalescingWorkItem@VMINIPORT_HOOK_DRIVER@@@@@@CAXPEAX@Z; KWorkItemBase<MINIPORT_HOOK_DRIVER,KCoalescingWorkItem<MINIPORT_HOOK_DRIVER>>::CallbackThunk(void *)
0x1400b7d42  mov     [rax+10h], rcx
0x1400b7d46  lea     rcx, [rbx+168h]; Mutex
0x1400b7d4d  mov     [rax], rdx
0x1400b7d50  mov     [rax+30h], edx
0x1400b7d53  mov     edx, 0FFFFh; Level
0x1400b7d58  mov     [rax+20h], rbx
0x1400b7d5c  mov     [rax+18h], rax
0x1400b7d60  call    cs:__imp_KeInitializeMutex
0x1400b7d67  nop     dword ptr [rax+rax+00h]
0x1400b7d6c  mov     al, [rsi+6]
0x1400b7d6f  mov     cl, [rsi+4]
0x1400b7d72  mov     r8b, [rdi]
0x1400b7d75  mov     [rbx+3Ah], al
0x1400b7d78  mov     al, [rsi+7]
0x1400b7d7b  mov     [rbx+3Bh], al
0x1400b7d7e  lea     rax, [rbx+380h]
0x1400b7d85  mov     [rbx+8], r15
0x1400b7d89  lea     r15, [rbx+48h]
0x1400b7d8d  mov     [rbx+2], r14w
0x1400b7d92  mov     r14b, 6
0x1400b7d95  mov     [r15+8], rax
0x1400b7d99  mov     eax, [rsi+8]
0x1400b7d9c  mov     [rbx+40h], eax
0x1400b7d9f  mov     word ptr [rbx], 103h
0x1400b7da4  mov     [rbx+38h], cl
0x1400b7da7  mov     [rbx+39h], r8b
0x1400b7dab  cmp     cl, r14b
0x1400b7dae  ja      short loc_1400B7DC0
0x1400b7db0  jnz     short loc_1400B7DB8
0x1400b7db2  cmp     r8b, 32h ; '2'
0x1400b7db6  jnb     short loc_1400B7DC0
0x1400b7db8  and     eax, 0F0000000h
0x1400b7dbd  mov     [rbx+40h], eax
0x1400b7dc0  movzx   eax, word ptr [r13+0]
0x1400b7dc5  xor     r8d, r8d; AllocateDestinationString
0x1400b7dc8  mov     rdx, r13; SourceString
0x1400b7dcb  mov     [r15], ax
0x1400b7dcf  mov     rcx, r15; DestinationString
0x1400b7dd2  mov     [rbx+4Ah], ax
0x1400b7dd6  call    cs:__imp_RtlUpcaseUnicodeString
0x1400b7ddd  nop     dword ptr [rax+rax+00h]
0x1400b7de2  xor     r8d, r8d; CaseInSensitive
0x1400b7de5  lea     rdx, [rbp+String2]; String2
0x1400b7de9  mov     rcx, r15; String1
0x1400b7dec  call    cs:__imp_RtlCompareUnicodeString
0x1400b7df3  nop     dword ptr [rax+rax+00h]
0x1400b7df8  lea     rdx, [rbp+var_20]; String2
0x1400b7dfc  mov     rcx, r15; String1
0x1400b7dff  test    eax, eax
0x1400b7e01  setz    al
0x1400b7e04  xor     r8d, r8d; CaseInSensitive
0x1400b7e07  mov     [rbx+58h], al
0x1400b7e0a  call    cs:__imp_RtlCompareUnicodeString
0x1400b7e11  nop     dword ptr [rax+rax+00h]
0x1400b7e16  lea     rdx, [rbp+var_10]; String2
0x1400b7e1a  mov     rcx, r15; String1
0x1400b7e1d  test    eax, eax
0x1400b7e1f  setz    al
0x1400b7e22  xor     r8d, r8d; CaseInSensitive
0x1400b7e25  mov     [rbx+59h], al
0x1400b7e28  call    cs:__imp_RtlCompareUnicodeString
0x1400b7e2f  nop     dword ptr [rax+rax+00h]
0x1400b7e34  test    eax, eax
0x1400b7e36  setz    al
0x1400b7e39  mov     [rbx+5Ah], al
0x1400b7e3c  mov     rax, [rsi+28h]
0x1400b7e40  mov     [rbx+60h], rax
0x1400b7e44  mov     rax, [rsi+30h]
0x1400b7e48  mov     [rbx+68h], rax
0x1400b7e4c  mov     rax, [rsi+38h]
0x1400b7e50  mov     [rbx+70h], rax
0x1400b7e54  mov     rax, [rsi+40h]
0x1400b7e58  mov     [rbx+78h], rax
0x1400b7e5c  mov     rax, [rsi+48h]
0x1400b7e60  mov     [rbx+80h], rax
0x1400b7e67  mov     rax, [rsi+50h]
0x1400b7e6b  mov     [rbx+90h], rax
0x1400b7e72  mov     rax, [rsi+60h]
0x1400b7e76  mov     [rbx+0A0h], rax
0x1400b7e7d  mov     rax, [rsi+68h]
0x1400b7e81  mov     [rbx+0B0h], rax
0x1400b7e88  mov     rax, [rsi+70h]
0x1400b7e8c  mov     [rbx+0B8h], rax
0x1400b7e93  mov     rax, [rsi+58h]
0x1400b7e97  mov     [rbx+140h], rax
0x1400b7e9e  cmp     [rsi+4], r14b
0x1400b7ea2  ja      short loc_1400B7EAB
0x1400b7ea4  jnz     short loc_1400B7EB6
0x1400b7ea6  cmp     byte ptr [rdi], 1
0x1400b7ea9  jb      short loc_1400B7EB6
0x1400b7eab  mov     rax, [rsi+78h]
0x1400b7eaf  mov     [rbx+308h], rax
0x1400b7eb6  lea     r14, [rbx+20h]
0x1400b7eba  mov     dl, 10h; unsigned __int8
0x1400b7ebc  mov     rcx, r14; struct _REFERENCE_EX *
0x1400b7ebf  call    ?ndisInitializeRef@@YAXPEAU_REFERENCE_EX@@E@Z; ndisInitializeRef(_REFERENCE_EX *,uchar)
0x1400b7ec4  cmp     byte ptr [rbx+38h], 6
0x1400b7ec8  ja      short loc_1400B7ED7
0x1400b7eca  jnz     short loc_1400B7ED2
0x1400b7ecc  cmp     byte ptr [rbx+39h], 52h ; 'R'
0x1400b7ed0  jnb     short loc_1400B7ED7
0x1400b7ed2  mov     r9b, 1
0x1400b7ed5  jmp     short loc_1400B7EDA
0x1400b7ed7  xor     r9b, r9b
0x1400b7eda  mov     r8b, 1
0x1400b7edd  lea     rcx, [rbp+arg_18]
0x1400b7ee1  mov     rdx, r15
0x1400b7ee4  call    ?ndisBindGetProtocolDriver@@YA?AV?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@PEAU_UNICODE_STRING@@_N1@Z; ndisBindGetProtocolDriver(_UNICODE_STRING *,bool,bool)
0x1400b7ee9  mov     rdx, rax
0x1400b7eec  mov     rcx, r12
0x1400b7eef  call    ??4?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@QEAAAEAV0@$$QEAV0@@Z; KRef<NDIS_BIND_PROTOCOL_DRIVER>::operator=(KRef<NDIS_BIND_PROTOCOL_DRIVER> &&)
0x1400b7ef4  lea     rcx, [rbp+arg_18]
0x1400b7ef8  call    ?unref@?$KRef@UNDIS_BIND_PROTOCOL_DRIVER@@@@AEAAXXZ; KRef<NDIS_BIND_PROTOCOL_DRIVER>::unref(void)
0x1400b7efd  cmp     qword ptr [r12], 0
0x1400b7f02  jnz     short loc_1400B7F3E
0x1400b7f04  mov     dl, 0FFh; unsigned __int8
0x1400b7f06  mov     rcx, r14; SpinLock
0x1400b7f09  call    ?ndisDereferenceRef@@YAEPEAU_REFERENCE_EX@@E@Z; ndisDereferenceRef(_REFERENCE_EX *,uchar)
0x1400b7f0e  mov     rcx, rbx; this
0x1400b7f11  call    ??1_NDIS_PROTOCOL_BLOCK@@QEAA@XZ; _NDIS_PROTOCOL_BLOCK::~_NDIS_PROTOCOL_BLOCK(void)
0x1400b7f16  xor     edx, edx; Tag
0x1400b7f18  mov     rcx, rbx; P
0x1400b7f1b  call    cs:__imp_ExFreePoolWithTag
0x1400b7f22  nop     dword ptr [rax+rax+00h]
0x1400b7f27  mov     edi, 0C000009Ah
0x1400b7f2c  lea     r14, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400b7f33  mov     r12d, 0Ch
0x1400b7f39  jmp     loc_1400B7C63
0x1400b7f3e  call    Feature_NdisTriageData__private_IsEnabledDeviceUsageNoInline
0x1400b7f43  test    eax, eax
0x1400b7f45  jz      loc_1400B7FCF
0x1400b7f4b  mov     rcx, rbx
0x1400b7f4e  call    ndisRegisterProtocolTriageData
0x1400b7f53  mov     edi, eax
0x1400b7f55  test    eax, eax
0x1400b7f57  jz      short loc_1400B7FCF
0x1400b7f59  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b7f60  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400b7f67  jz      short loc_1400B7F9A
0x1400b7f69  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7f70  mov     r9d, 0Bh; int
0x1400b7f76  mov     dword ptr [rsp+70h+var_40], eax; char
0x1400b7f7a  mov     dl, 2; int
0x1400b7f7c  lea     rax, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400b7f83  mov     [rsp+70h+var_48], rbx; char
0x1400b7f88  mov     [rsp+70h+var_50], rax; struct _GUID *
0x1400b7f8d  mov     rcx, [rcx+40h]; int
0x1400b7f91  lea     r8d, [r9+2]; int
0x1400b7f95  call    WPP_RECORDER_SF_qD
0x1400b7f9a  mov     dl, 0FFh; unsigned __int8
0x1400b7f9c  mov     rcx, r14; SpinLock
0x1400b7f9f  call    ?ndisDereferenceRef@@YAEPEAU_REFERENCE_EX@@E@Z; ndisDereferenceRef(_REFERENCE_EX *,uchar)
0x1400b7fa4  mov     rcx, rbx; this
0x1400b7fa7  call    ??1_NDIS_PROTOCOL_BLOCK@@QEAA@XZ; _NDIS_PROTOCOL_BLOCK::~_NDIS_PROTOCOL_BLOCK(void)
0x1400b7fac  xor     edx, edx; Tag
0x1400b7fae  mov     rcx, rbx; P
0x1400b7fb1  call    cs:__imp_ExFreePoolWithTag
0x1400b7fb8  nop     dword ptr [rax+rax+00h]
0x1400b7fbd  lea     r14, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x1400b7fc4  mov     r12d, 0Ch
0x1400b7fca  jmp     loc_1400B7C6A
0x1400b7fcf  mov     r12, [rbp+arg_10]
0x1400b7fd3  mov     rdx, rsi; struct _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *
0x1400b7fd6  mov     rcx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x1400b7fd9  mov     [r12], rbx
0x1400b7fdd  call    ?ndisInvokeSetOptions@@_Y2PAGE@@AHPEAU_NDIS_PROTOCOL_BLOCK@@PEAU_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS@@@Z; ndisInvokeSetOptions(_NDIS_PROTOCOL_BLOCK *,_NDIS_PROTOCOL_DRIVER_CHARACTERISTICS *)
0x1400b7fe2  mov     edi, eax
0x1400b7fe4  test    eax, eax
0x1400b7fe6  jz      short loc_1400B8016
0x1400b7fe8  mov     dl, 0FFh; unsigned __int8
0x1400b7fea  mov     rcx, r14; SpinLock
0x1400b7fed  call    ?ndisDereferenceRef@@YAEPEAU_REFERENCE_EX@@E@Z; ndisDereferenceRef(_REFERENCE_EX *,uchar)
0x1400b7ff2  mov     rcx, rbx; this
0x1400b7ff5  call    ??1_NDIS_PROTOCOL_BLOCK@@QEAA@XZ; _NDIS_PROTOCOL_BLOCK::~_NDIS_PROTOCOL_BLOCK(void)
0x1400b7ffa  xor     edx, edx; Tag
0x1400b7ffc  mov     rcx, rbx; P
0x1400b7fff  call    cs:__imp_ExFreePoolWithTag
0x1400b8006  nop     dword ptr [rax+rax+00h]
0x1400b800b  xor     ebx, ebx
0x1400b800d  mov     [r12], rbx
0x1400b8011  jmp     loc_1400B7F2C
0x1400b8016  movzx   eax, byte ptr [rbx+3Bh]
0x1400b801a  mov     r8b, 1; unsigned __int8
0x1400b801d  movzx   r9d, byte ptr [rbx+3Ah]; unsigned int
0x1400b8022  movzx   edx, byte ptr [rbx+39h]; unsigned int
0x1400b8026  movzx   ecx, byte ptr [rbx+38h]; unsigned int
0x1400b802a  mov     [rsp+70h+var_48], r15; struct _UNICODE_STRING *
  ... truncated ...
```
