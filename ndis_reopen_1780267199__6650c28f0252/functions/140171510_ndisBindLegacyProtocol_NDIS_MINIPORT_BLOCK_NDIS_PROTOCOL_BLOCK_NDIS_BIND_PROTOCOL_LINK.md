# ndisBindLegacyProtocol(_NDIS_MINIPORT_BLOCK *,_NDIS_PROTOCOL_BLOCK *,NDIS_BIND_PROTOCOL_LINK *)

- ea: `0x140171510`
- end: `0x140171978`
- name: `?ndisBindLegacyProtocol@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_PROTOCOL_BLOCK@@PEAUNDIS_BIND_PROTOCOL_LINK@@@Z`
- size: `1128`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_PROTOCOL_BLOCK *, struct NDIS_BIND_PROTOCOL_LINK *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015e770`

## callees

- `0x14000dd10`
- `0x1400100f0`
- `0x14003f590`
- `0x14005aef0`
- `0x14005eaa0`
- `0x14005f7e0`
- `0x140063240`
- `0x140088a2c`
- `0x1400bb750`
- `0x1400eb460`
- `0x1400eb7c0`
- `0x14015d400`
- `0x14015d440`
- `0x14015d480`
- `0x14015e2a0`
- `0x140171510`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1401716dc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401716dc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401716f1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140171707`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401716f1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140171707`
- `ntoskrnl!RtlInitUnicodeString` at `0x140171648`
- `ntoskrnl!RtlInitUnicodeString` at `0x140171648`
- `ntoskrnl!ExFreePoolWithTag` at `0x14017189c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14017189c`
- `ntoskrnl!KeInitializeEvent` at `0x140171763`
- `ntoskrnl!KeInitializeEvent` at `0x140171763`
- `ntoskrnl!ExAllocatePool2` at `0x1401716ba`
- `ntoskrnl!ExAllocatePool2` at `0x1401716ba`

## pseudocode

```c
__int64 __fastcall ndisBindLegacyProtocol(
        struct _NDIS_MINIPORT_BLOCK *a1,
        struct _NDIS_PROTOCOL_BLOCK *a2,
        struct NDIS_BIND_PROTOCOL_LINK *a3)
{
  int v6; // edx
  int v7; // edx
  _NDIS_PNP_DEVICE_STATE PnPDeviceState; // ecx
  _NDIS_BIND_PATHS *BindPaths; // r15
  _UNICODE_STRING *Paths; // r15
  _DEVICE_OBJECT *PhysicalDeviceObject; // r12
  __m128i v12; // xmm0
  __int64 v13; // rdx
  void *m_AdditionalContext; // r14
  int v15; // edx
  int v16; // r8d
  __int64 v17; // rcx
  unsigned int Blink; // eax
  int v19; // edx
  __int64 result; // rax
  int v21; // [rsp+28h] [rbp-E0h]
  _LIST_ENTRY Destination_8; // [rsp+68h] [rbp-A0h] BYREF
  UNICODE_STRING Source_8; // [rsp+78h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-80h] BYREF
  struct _KEVENT v25[7]; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v26; // [rsp+170h] [rbp+68h] BYREF

  memset(v25, 0, 0x90u);
  v26 = -1073741823;
  Destination_8 = 0;
  Source_8 = 0;
  DestinationString = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v6,
      6,
      10,
      (struct _GUID *)&WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids,
      (char)a1,
      (char)a2);
  }
  WAIT_FOR_PROTO_MUTEX(a2);
  if ( !ndisIsMiniportStarted(a1)
    || (PnPDeviceState = a1->PnPDeviceState, ((PnPDeviceState - 1) & 0xFFFFFFFC) != 0)
    || PnPDeviceState == NdisPnPDeviceStopped )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 3;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v7,
        6,
        11,
        (struct _GUID *)&WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids,
        (char)a1,
        (char)a2);
    }
  }
  else
  {
    MINIPORT_TEST_FLAG(a1, 0x10000u);
    if ( a1->EthDB )
    {
      BindPaths = a1->BindPaths;
      a2->BindDeviceName = &a1->MiniportName;
      Paths = BindPaths->Paths;
      a2->RootDeviceName = Paths;
      PhysicalDeviceObject = a1->PhysicalDeviceObject;
      if ( ndisReferenceProtocol(a2, PTREF_BINDING) )
      {
        RtlInitUnicodeString(&DestinationString, L"\\Parameters\\Adapters\\");
        Source_8 = *Paths;
        v12 = (__m128i)Source_8;
        Source_8.MaximumLength -= ndisDeviceStr.Length;
        Source_8.Length = _mm_cvtsi128_si32(v12) - ndisDeviceStr.Length;
        Source_8.Buffer += (unsigned __int64)ndisDeviceStr.Length >> 1;
        v13 = (unsigned __int16)(a2->Name.Length + DestinationString.Length + Paths->Length - ndisDeviceStr.Length + 2);
        LOWORD(Destination_8.Flink) = 0;
        WORD1(Destination_8.Flink) = v13;
        Destination_8.Blink = (_LIST_ENTRY *)ExAllocatePool2(64, v13, 538985550);
        if ( Destination_8.Blink )
        {
          RtlCopyUnicodeString((PUNICODE_STRING)&Destination_8, &a2->Name);
          RtlAppendUnicodeStringToString((PUNICODE_STRING)&Destination_8, &DestinationString);
          RtlAppendUnicodeStringToString((PUNICODE_STRING)&Destination_8, &Source_8);
          ndisUpdateMinimumStackVersion(a1, a2->MajorNdisVersion, a2->MinorNdisVersion);
          v25[1].Header.WaitListHead = Destination_8;
          *(_QWORD *)&v25[0].Header.Lock = 0;
          v25[0].Header.WaitListHead.Flink = (_LIST_ENTRY *)a2;
          *(_QWORD *)&v25[1].Header.Lock = a1;
          *(_QWORD *)&v25[2].Header.Lock = Paths;
          KeInitializeEvent(&v25[4], NotificationEvent, 0);
          if ( !a2->Ref.Closing )
          {
            a2->BindingAdapter = a1;
            m_AdditionalContext = a3->BindState.m_AdditionalContext;
            v26 = 0;
            if ( m_AdditionalContext )
            {
              a3->BindState.m_AdditionalContext = 0;
              ndisOpenAdapterLegacyProtocol(
                *(int **)m_AdditionalContext,
                0,
                *((void ***)m_AdditionalContext + 1),
                *((unsigned int **)m_AdditionalContext + 2),
                *((enum _NDIS_MEDIUM **)m_AdditionalContext + 3),
                *((_DWORD *)m_AdditionalContext + 8),
                *((_QWORD *)m_AdditionalContext + 5),
                *((void **)m_AdditionalContext + 6),
                *((struct _UNICODE_STRING **)m_AdditionalContext + 7),
                0,
                0,
                (int *)&v26);
              v17 = **((_QWORD **)m_AdditionalContext + 1);
              if ( v17 )
                *(_DWORD *)(v17 + 224) |= 0x20000000u;
            }
            else
            {
              v21 = (int)PhysicalDeviceObject;
              ((void (__fastcall *)(unsigned int *, struct _KEVENT *, _UNICODE_STRING *, _LIST_ENTRY *))a2->BindAdapterHandler)(
                &v26,
                v25,
                Paths,
                &Destination_8);
            }
            Blink = v26;
            if ( v26 == 259 )
            {
              ndisWaitForKernelObject(&v25[4]);
              Blink = (unsigned int)v25[3].Header.WaitListHead.Blink;
              v26 = (unsigned int)v25[3].Header.WaitListHead.Blink;
            }
            a2->BindingAdapter = 0;
            if ( !Blink )
            {
              ndisNotifyWmiBindUnbind(a1, a2, 1u);
              LOBYTE(Blink) = v26;
            }
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_ZZL(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v15,
                v16,
                12,
                v21,
                (__int64)&a2->Name,
                (__int64)a1->pAdapterInstanceName,
                Blink);
          }
          ExFreePoolWithTag(Destination_8.Blink, 0);
          a2->BindDeviceName = 0;
        }
        ndisDereferenceProtocol(a2, 0, PTREF_BINDING);
      }
    }
  }
  RELEASE_PROT_MUTEX(a2);
  result = v26;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 4;
    WPP_RECORDER_SF_qqL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v19,
      6,
      13,
      (struct _GUID *)&WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids,
      (char)a1,
      (char)a2,
      v26);
    return v26;
  }
  return result;
}

```

## disassembly

```asm
0x140171510  mov     rax, rsp
0x140171513  push    rbp
0x140171514  push    rbx
0x140171515  push    rdi
0x140171516  push    r15
0x140171518  lea     rbp, [rax-48h]
0x14017151c  sub     rsp, 128h
0x140171523  mov     [rax+8], rsi
0x140171527  mov     rbx, rdx
0x14017152a  mov     rsi, r8
0x14017152d  mov     [rax-28h], r14
0x140171531  mov     rdi, rcx
0x140171534  mov     r8d, 90h; Size
0x14017153a  xor     edx, edx; Val
0x14017153c  lea     rcx, [rbp+40h+var_B0]; void *
0x140171540  call    memset
0x140171545  xorps   xmm0, xmm0
0x140171548  mov     [rbp+40h+arg_18], 0C0000001h
0x14017154f  xorps   xmm1, xmm1
0x140171552  movups  xmmword ptr [rsp+140h+Destination.Buffer], xmm0
0x140171557  movups  xmmword ptr [rsp+140h+Source+8], xmm1
0x14017155c  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x140171560  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140171567  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14017156e  lea     r15, WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids
0x140171575  jz      short loc_1401715A4
0x140171577  mov     rcx, cs:WPP_GLOBAL_Control
0x14017157e  mov     r9d, 0Ah; int
0x140171584  mov     qword ptr [rsp+140h+NewIrql], rbx; char
0x140171589  mov     r8d, 6; int
0x14017158f  mov     qword ptr [rsp+140h+var_118], rdi; char
0x140171594  mov     dl, 4; int
0x140171596  mov     [rsp+140h+var_120], r15; struct _GUID *
0x14017159b  mov     rcx, [rcx+40h]; int
0x14017159f  call    WPP_RECORDER_SF_qq
0x1401715a4  mov     rcx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x1401715a7  mov     [rsp+140h+arg_10], r13
0x1401715af  call    ?WAIT_FOR_PROTO_MUTEX@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@@Z; WAIT_FOR_PROTO_MUTEX(_NDIS_PROTOCOL_BLOCK *)
0x1401715b4  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1401715b7  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x1401715bc  test    al, al
0x1401715be  jz      loc_14017193D
0x1401715c4  mov     ecx, [rdi+5F0h]
0x1401715ca  lea     eax, [rcx-1]
0x1401715cd  test    eax, 0FFFFFFFCh
0x1401715d2  jnz     loc_14017193D
0x1401715d8  cmp     ecx, 3
0x1401715db  jz      loc_14017193D
0x1401715e1  mov     edx, 10000h; unsigned int
0x1401715e6  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1401715e9  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1401715ee  cmp     qword ptr [rdi+190h], 0
0x1401715f6  jz      loc_1401718CF
0x1401715fc  mov     r15, [rdi+0EB8h]
0x140171603  lea     rax, [rdi+0EE0h]
0x14017160a  mov     [rbx+1B0h], rax
0x140171611  add     r15, 8
0x140171615  mov     [rbx+1B8h], r15
0x14017161c  mov     dl, 7; enum _NDIS_PT_REFTAG
0x14017161e  mov     [rsp+140h+arg_8], r12
0x140171626  mov     rcx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x140171629  mov     r12, [rdi+0EF8h]
0x140171630  call    ?ndisReferenceProtocol@@YAEPEAU_NDIS_PROTOCOL_BLOCK@@W4_NDIS_PT_REFTAG@@@Z; ndisReferenceProtocol(_NDIS_PROTOCOL_BLOCK *,_NDIS_PT_REFTAG)
0x140171635  test    al, al
0x140171637  jz      loc_1401718C0
0x14017163d  lea     rdx, aParametersAdap; "\\Parameters\\Adapters\\"
0x140171644  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x140171648  call    cs:__imp_RtlInitUnicodeString
0x14017164f  nop     dword ptr [rax+rax+00h]
0x140171654  movups  xmm0, xmmword ptr [r15]
0x140171658  movzx   edx, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x14017165f  lea     r13, [rbx+48h]
0x140171663  mov     ecx, edx
0x140171665  mov     r8d, 2020444Eh
0x14017166b  movups  xmmword ptr [rsp+140h+Source+8], xmm0
0x140171670  sub     word ptr [rsp+140h+Source+0Ah], dx
0x140171675  movd    eax, xmm0
0x140171679  shr     rcx, 1
0x14017167c  sub     ax, dx
0x14017167f  mov     word ptr [rsp+140h+Source+8], ax
0x140171684  mov     rax, qword ptr [rsp+140h+Source+10h]
0x140171689  lea     rcx, [rax+rcx*2]
0x14017168d  mov     qword ptr [rsp+140h+Source+10h], rcx
0x140171692  mov     ecx, 40h ; '@'
0x140171697  movzx   eax, word ptr [r15]
0x14017169b  sub     ax, dx
0x14017169e  add     ax, 2
0x1401716a2  add     ax, [rbp+40h+DestinationString.Length]
0x1401716a6  add     ax, [r13+0]
0x1401716ab  movzx   edx, ax
0x1401716ae  xor     eax, eax
0x1401716b0  mov     word ptr [rsp+140h+Destination.Buffer], ax
0x1401716b5  mov     word ptr [rsp+140h+Destination.Buffer+2], dx
0x1401716ba  call    cs:__imp_ExAllocatePool2
0x1401716c1  nop     dword ptr [rax+rax+00h]
0x1401716c6  mov     qword ptr [rsp+140h+Source], rax
0x1401716cb  test    rax, rax
0x1401716ce  jz      loc_1401718B3
0x1401716d4  mov     rdx, r13; SourceString
0x1401716d7  lea     rcx, [rsp+140h+Destination.Buffer]; DestinationString
0x1401716dc  call    cs:__imp_RtlCopyUnicodeString
0x1401716e3  nop     dword ptr [rax+rax+00h]
0x1401716e8  lea     rdx, [rbp+40h+DestinationString]; Source
0x1401716ec  lea     rcx, [rsp+140h+Destination.Buffer]; Destination
0x1401716f1  call    cs:__imp_RtlAppendUnicodeStringToString
0x1401716f8  nop     dword ptr [rax+rax+00h]
0x1401716fd  lea     rdx, [rsp+140h+Source+8]; Source
0x140171702  lea     rcx, [rsp+140h+Destination.Buffer]; Destination
0x140171707  call    cs:__imp_RtlAppendUnicodeStringToString
0x14017170e  nop     dword ptr [rax+rax+00h]
0x140171713  movzx   r8d, byte ptr [rbx+39h]; unsigned int
0x140171718  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14017171b  movzx   edx, byte ptr [rbx+38h]; unsigned int
0x14017171f  call    ?ndisUpdateMinimumStackVersion@@YAXPEAU_NDIS_MINIPORT_BLOCK@@KK@Z; ndisUpdateMinimumStackVersion(_NDIS_MINIPORT_BLOCK *,ulong,ulong)
0x140171724  movzx   eax, word ptr [rsp+140h+Destination.Buffer]
0x140171729  lea     rcx, [rbp+40h+Event]; Event
0x14017172d  mov     word ptr [rbp+40h+var_90], ax
0x140171731  xor     r8d, r8d; State
0x140171734  movzx   eax, word ptr [rsp+140h+Destination.Buffer+2]
0x140171739  xor     edx, edx; Type
0x14017173b  mov     word ptr [rbp+40h+var_90+2], ax
0x14017173f  mov     eax, dword ptr [rsp+140h+Destination.Buffer+4]
0x140171743  mov     dword ptr [rbp+40h+var_90+4], eax
0x140171746  mov     rax, qword ptr [rsp+140h+Source]
0x14017174b  mov     [rbp+40h+var_88], rax
0x14017174f  mov     [rbp+40h+var_B0], 0
0x140171757  mov     [rbp+40h+var_A8], rbx
0x14017175b  mov     [rbp+40h+var_98], rdi
0x14017175f  mov     [rbp+40h+var_80], r15
0x140171763  call    cs:__imp_KeInitializeEvent
0x14017176a  nop     dword ptr [rax+rax+00h]
0x14017176f  cmp     byte ptr [rbx+2Ah], 0
0x140171773  jnz     loc_140171895
0x140171779  xor     ecx, ecx
0x14017177b  mov     [rbx+1C8h], rdi
0x140171782  mov     r14, [rsi+10h]
0x140171786  mov     [rbp+40h+arg_18], ecx
0x140171789  test    r14, r14
0x14017178c  jz      short loc_140171800
0x14017178e  mov     [rsi+10h], rcx
0x140171792  lea     rax, [rbp+40h+arg_18]
0x140171796  mov     r9, [r14+10h]; unsigned int *
0x14017179a  xor     edx, edx; int *
0x14017179c  mov     r8, [r14+8]; void **
0x1401717a0  mov     qword ptr [rsp+140h+Destination.Length], rax; int *
0x1401717a5  mov     rax, [r14+38h]
0x1401717a9  mov     [rsp+140h+var_F0], rcx; struct _STRING *
0x1401717ae  mov     [rsp+140h+var_F8], ecx; unsigned int
0x1401717b2  mov     rcx, [r14]; int *
0x1401717b5  mov     [rsp+140h+var_100], rax; struct _UNICODE_STRING *
0x1401717ba  mov     rax, [r14+30h]
0x1401717be  mov     [rsp+140h+var_108], rax; void *
0x1401717c3  mov     rax, [r14+28h]
0x1401717c7  mov     qword ptr [rsp+140h+NewIrql], rax; NewIrql
0x1401717cc  mov     eax, [r14+20h]
0x1401717d0  mov     dword ptr [rsp+140h+var_118], eax; unsigned int
0x1401717d4  mov     rax, [r14+18h]
0x1401717d8  mov     [rsp+140h+var_120], rax; enum _NDIS_MEDIUM *
0x1401717dd  call    ?ndisOpenAdapterLegacyProtocol@@YAXPEAH0PEAPEAXPEAIPEAW4_NDIS_MEDIUM@@IPEAX4PEAU_UNICODE_STRING@@IPEAU_STRING@@0@Z; ndisOpenAdapterLegacyProtocol(int *,int *,void * *,uint *,_NDIS_MEDIUM *,uint,void *,void *,_UNICODE_STRING *,uint,_STRING *,int *)
0x1401717e2  mov     rax, [r14+8]
0x1401717e6  mov     rcx, [rax]
0x1401717e9  test    rcx, rcx
0x1401717ec  jz      short loc_140171821
0x1401717ee  mov     eax, [rcx+0E0h]
0x1401717f4  bts     eax, 1Dh
0x1401717f8  mov     [rcx+0E0h], eax
0x1401717fe  jmp     short loc_140171821
0x140171800  mov     rax, [rbx+120h]
0x140171807  lea     r9, [rsp+140h+Destination.Buffer]
0x14017180c  mov     r8, r15
0x14017180f  mov     [rsp+140h+var_120], r12
0x140171814  lea     rdx, [rbp+40h+var_B0]
0x140171818  lea     rcx, [rbp+40h+arg_18]
0x14017181c  call    _guard_dispatch_icall
0x140171821  mov     eax, [rbp+40h+arg_18]
0x140171824  cmp     eax, 103h
0x140171829  jnz     short loc_14017183A
0x14017182b  lea     rcx, [rbp+40h+Event]; void *
0x14017182f  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140171834  mov     eax, [rbp+40h+var_58]
0x140171837  mov     [rbp+40h+arg_18], eax
0x14017183a  mov     qword ptr [rbx+1C8h], 0
0x140171845  test    eax, eax
0x140171847  jnz     short loc_14017185A
0x140171849  mov     r8b, 1; unsigned __int8
0x14017184c  mov     rdx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x14017184f  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x140171852  call    ?ndisNotifyWmiBindUnbind@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_PROTOCOL_BLOCK@@E@Z; ndisNotifyWmiBindUnbind(_NDIS_MINIPORT_BLOCK *,_NDIS_PROTOCOL_BLOCK *,uchar)
0x140171857  mov     eax, [rbp+40h+arg_18]
0x14017185a  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140171861  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140171868  jz      short loc_140171895
0x14017186a  mov     rcx, cs:WPP_GLOBAL_Control
0x140171871  mov     r9d, 0Ch
0x140171877  mov     dword ptr [rsp+140h+var_108], eax
0x14017187b  mov     rax, [rdi+0F10h]
0x140171882  mov     qword ptr [rsp+140h+NewIrql], rax
0x140171887  mov     rcx, [rcx+40h]
0x14017188b  mov     qword ptr [rsp+140h+var_118], r13
0x140171890  call    WPP_RECORDER_SF_ZZL
0x140171895  mov     rcx, qword ptr [rsp+140h+Source]; P
0x14017189a  xor     edx, edx; Tag
0x14017189c  call    cs:__imp_ExFreePoolWithTag
0x1401718a3  nop     dword ptr [rax+rax+00h]
0x1401718a8  mov     qword ptr [rbx+1B0h], 0
0x1401718b3  mov     r8b, 7; enum _NDIS_PT_REFTAG
0x1401718b6  xor     edx, edx; unsigned __int8
0x1401718b8  mov     rcx, rbx; this
0x1401718bb  call    ?ndisDereferenceProtocol@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@EW4_NDIS_PT_REFTAG@@@Z; ndisDereferenceProtocol(_NDIS_PROTOCOL_BLOCK *,uchar,_NDIS_PT_REFTAG)
0x1401718c0  mov     r12, [rsp+140h+arg_8]
0x1401718c8  lea     r15, WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids
0x1401718cf  mov     rcx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x1401718d2  call    ?RELEASE_PROT_MUTEX@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@@Z; RELEASE_PROT_MUTEX(_NDIS_PROTOCOL_BLOCK *)
0x1401718d7  mov     r13, [rsp+140h+arg_10]
0x1401718df  mov     rsi, [rsp+140h+arg_0]
0x1401718e7  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1401718ee  mov     r14, [rsp+120h]
0x1401718f6  mov     eax, [rbp+40h+arg_18]
0x1401718f9  jz      short loc_14017192F
0x1401718fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140171902  mov     r9d, 0Dh; int
0x140171908  mov     dword ptr [rsp+140h+var_108], eax; char
0x14017190c  mov     r8d, 6; int
0x140171912  mov     qword ptr [rsp+140h+NewIrql], rbx; char
0x140171917  mov     dl, 4; int
0x140171919  mov     qword ptr [rsp+140h+var_118], rdi; char
0x14017191e  mov     rcx, [rcx+40h]; int
0x140171922  mov     [rsp+140h+var_120], r15; struct _GUID *
0x140171927  call    WPP_RECORDER_SF_qqL
0x14017192c  mov     eax, [rbp+40h+arg_18]
0x14017192f  add     rsp, 128h
0x140171936  pop     r15
0x140171938  pop     rdi
0x140171939  pop     rbx
0x14017193a  pop     rbp
0x14017193b  retn
0x14017193d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140171944  jz      short loc_1401718CF
0x140171946  mov     rcx, cs:WPP_GLOBAL_Control
0x14017194d  mov     r9d, 0Bh; int
0x140171953  mov     qword ptr [rsp+140h+NewIrql], rbx; char
0x140171958  mov     r8d, 6; int
0x14017195e  mov     qword ptr [rsp+140h+var_118], rdi; char
0x140171963  mov     dl, 3; int
0x140171965  mov     [rsp+140h+var_120], r15; struct _GUID *
0x14017196a  mov     rcx, [rcx+40h]; int
0x14017196e  call    WPP_RECORDER_SF_qq
0x140171973  jmp     loc_1401718CF
```
