# ndisBindLegacyProtocol(_NDIS_MINIPORT_BLOCK *,_NDIS_PROTOCOL_BLOCK *,NDIS_BIND_PROTOCOL_LINK *)

- ea: `0x14016a620`
- end: `0x14016aa88`
- name: `?ndisBindLegacyProtocol@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_PROTOCOL_BLOCK@@PEAUNDIS_BIND_PROTOCOL_LINK@@@Z`
- size: `1128`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_PROTOCOL_BLOCK *, struct NDIS_BIND_PROTOCOL_LINK *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401577d0`

## callees

- `0x140019c70`
- `0x14001c050`
- `0x14003cde0`
- `0x1400566b0`
- `0x14005a5c0`
- `0x14005b1f0`
- `0x14005eca0`
- `0x1400837ac`
- `0x1400b6320`
- `0x1400e6240`
- `0x1400e65c0`
- `0x140156460`
- `0x1401564a0`
- `0x1401564e0`
- `0x140157300`
- `0x14016a620`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14016a7ec`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14016a7ec`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016a801`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016a817`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016a801`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016a817`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016a758`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016a758`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016a9ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016a9ac`
- `ntoskrnl!KeInitializeEvent` at `0x14016a873`
- `ntoskrnl!KeInitializeEvent` at `0x14016a873`
- `ntoskrnl!ExAllocatePool2` at `0x14016a7ca`
- `ntoskrnl!ExAllocatePool2` at `0x14016a7ca`

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
0x14016a620  mov     rax, rsp
0x14016a623  push    rbp
0x14016a624  push    rbx
0x14016a625  push    rdi
0x14016a626  push    r15
0x14016a628  lea     rbp, [rax-48h]
0x14016a62c  sub     rsp, 128h
0x14016a633  mov     [rax+8], rsi
0x14016a637  mov     rbx, rdx
0x14016a63a  mov     rsi, r8
0x14016a63d  mov     [rax-28h], r14
0x14016a641  mov     rdi, rcx
0x14016a644  mov     r8d, 90h; Size
0x14016a64a  xor     edx, edx; Val
0x14016a64c  lea     rcx, [rbp+40h+var_B0]; void *
0x14016a650  call    memset
0x14016a655  xorps   xmm0, xmm0
0x14016a658  mov     [rbp+40h+arg_18], 0C0000001h
0x14016a65f  xorps   xmm1, xmm1
0x14016a662  movups  xmmword ptr [rsp+140h+Destination.Buffer], xmm0
0x14016a667  movups  xmmword ptr [rsp+140h+Source+8], xmm1
0x14016a66c  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x14016a670  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14016a677  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14016a67e  lea     r15, WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids
0x14016a685  jz      short loc_14016A6B4
0x14016a687  mov     rcx, cs:WPP_GLOBAL_Control
0x14016a68e  mov     r9d, 0Ah; int
0x14016a694  mov     qword ptr [rsp+140h+NewIrql], rbx; char
0x14016a699  mov     r8d, 6; int
0x14016a69f  mov     qword ptr [rsp+140h+var_118], rdi; char
0x14016a6a4  mov     dl, 4; int
0x14016a6a6  mov     [rsp+140h+var_120], r15; struct _GUID *
0x14016a6ab  mov     rcx, [rcx+40h]; int
0x14016a6af  call    WPP_RECORDER_SF_qq
0x14016a6b4  mov     rcx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x14016a6b7  mov     [rsp+140h+arg_10], r13
0x14016a6bf  call    ?WAIT_FOR_PROTO_MUTEX@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@@Z; WAIT_FOR_PROTO_MUTEX(_NDIS_PROTOCOL_BLOCK *)
0x14016a6c4  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14016a6c7  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x14016a6cc  test    al, al
0x14016a6ce  jz      loc_14016AA4D
0x14016a6d4  mov     ecx, [rdi+5F0h]
0x14016a6da  lea     eax, [rcx-1]
0x14016a6dd  test    eax, 0FFFFFFFCh
0x14016a6e2  jnz     loc_14016AA4D
0x14016a6e8  cmp     ecx, 3
0x14016a6eb  jz      loc_14016AA4D
0x14016a6f1  mov     edx, 10000h; unsigned int
0x14016a6f6  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14016a6f9  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x14016a6fe  cmp     qword ptr [rdi+190h], 0
0x14016a706  jz      loc_14016A9DF
0x14016a70c  mov     r15, [rdi+0EB8h]
0x14016a713  lea     rax, [rdi+0EE0h]
0x14016a71a  mov     [rbx+1B0h], rax
0x14016a721  add     r15, 8
0x14016a725  mov     [rbx+1B8h], r15
0x14016a72c  mov     dl, 7; enum _NDIS_PT_REFTAG
0x14016a72e  mov     [rsp+140h+arg_8], r12
0x14016a736  mov     rcx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x14016a739  mov     r12, [rdi+0EF8h]
0x14016a740  call    ?ndisReferenceProtocol@@YAEPEAU_NDIS_PROTOCOL_BLOCK@@W4_NDIS_PT_REFTAG@@@Z; ndisReferenceProtocol(_NDIS_PROTOCOL_BLOCK *,_NDIS_PT_REFTAG)
0x14016a745  test    al, al
0x14016a747  jz      loc_14016A9D0
0x14016a74d  lea     rdx, aParametersAdap; "\\Parameters\\Adapters\\"
0x14016a754  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x14016a758  call    cs:__imp_RtlInitUnicodeString
0x14016a75f  nop     dword ptr [rax+rax+00h]
0x14016a764  movups  xmm0, xmmword ptr [r15]
0x14016a768  movzx   edx, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x14016a76f  lea     r13, [rbx+48h]
0x14016a773  mov     ecx, edx
0x14016a775  mov     r8d, 2020444Eh
0x14016a77b  movups  xmmword ptr [rsp+140h+Source+8], xmm0
0x14016a780  sub     word ptr [rsp+140h+Source+0Ah], dx
0x14016a785  movd    eax, xmm0
0x14016a789  shr     rcx, 1
0x14016a78c  sub     ax, dx
0x14016a78f  mov     word ptr [rsp+140h+Source+8], ax
0x14016a794  mov     rax, qword ptr [rsp+140h+Source+10h]
0x14016a799  lea     rcx, [rax+rcx*2]
0x14016a79d  mov     qword ptr [rsp+140h+Source+10h], rcx
0x14016a7a2  mov     ecx, 40h ; '@'
0x14016a7a7  movzx   eax, word ptr [r15]
0x14016a7ab  sub     ax, dx
0x14016a7ae  add     ax, 2
0x14016a7b2  add     ax, [rbp+40h+DestinationString.Length]
0x14016a7b6  add     ax, [r13+0]
0x14016a7bb  movzx   edx, ax
0x14016a7be  xor     eax, eax
0x14016a7c0  mov     word ptr [rsp+140h+Destination.Buffer], ax
0x14016a7c5  mov     word ptr [rsp+140h+Destination.Buffer+2], dx
0x14016a7ca  call    cs:__imp_ExAllocatePool2
0x14016a7d1  nop     dword ptr [rax+rax+00h]
0x14016a7d6  mov     qword ptr [rsp+140h+Source], rax
0x14016a7db  test    rax, rax
0x14016a7de  jz      loc_14016A9C3
0x14016a7e4  mov     rdx, r13; SourceString
0x14016a7e7  lea     rcx, [rsp+140h+Destination.Buffer]; DestinationString
0x14016a7ec  call    cs:__imp_RtlCopyUnicodeString
0x14016a7f3  nop     dword ptr [rax+rax+00h]
0x14016a7f8  lea     rdx, [rbp+40h+DestinationString]; Source
0x14016a7fc  lea     rcx, [rsp+140h+Destination.Buffer]; Destination
0x14016a801  call    cs:__imp_RtlAppendUnicodeStringToString
0x14016a808  nop     dword ptr [rax+rax+00h]
0x14016a80d  lea     rdx, [rsp+140h+Source+8]; Source
0x14016a812  lea     rcx, [rsp+140h+Destination.Buffer]; Destination
0x14016a817  call    cs:__imp_RtlAppendUnicodeStringToString
0x14016a81e  nop     dword ptr [rax+rax+00h]
0x14016a823  movzx   r8d, byte ptr [rbx+39h]; unsigned int
0x14016a828  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14016a82b  movzx   edx, byte ptr [rbx+38h]; unsigned int
0x14016a82f  call    ?ndisUpdateMinimumStackVersion@@YAXPEAU_NDIS_MINIPORT_BLOCK@@KK@Z; ndisUpdateMinimumStackVersion(_NDIS_MINIPORT_BLOCK *,ulong,ulong)
0x14016a834  movzx   eax, word ptr [rsp+140h+Destination.Buffer]
0x14016a839  lea     rcx, [rbp+40h+Event]; Event
0x14016a83d  mov     word ptr [rbp+40h+var_90], ax
0x14016a841  xor     r8d, r8d; State
0x14016a844  movzx   eax, word ptr [rsp+140h+Destination.Buffer+2]
0x14016a849  xor     edx, edx; Type
0x14016a84b  mov     word ptr [rbp+40h+var_90+2], ax
0x14016a84f  mov     eax, dword ptr [rsp+140h+Destination.Buffer+4]
0x14016a853  mov     dword ptr [rbp+40h+var_90+4], eax
0x14016a856  mov     rax, qword ptr [rsp+140h+Source]
0x14016a85b  mov     [rbp+40h+var_88], rax
0x14016a85f  mov     [rbp+40h+var_B0], 0
0x14016a867  mov     [rbp+40h+var_A8], rbx
0x14016a86b  mov     [rbp+40h+var_98], rdi
0x14016a86f  mov     [rbp+40h+var_80], r15
0x14016a873  call    cs:__imp_KeInitializeEvent
0x14016a87a  nop     dword ptr [rax+rax+00h]
0x14016a87f  cmp     byte ptr [rbx+2Ah], 0
0x14016a883  jnz     loc_14016A9A5
0x14016a889  xor     ecx, ecx
0x14016a88b  mov     [rbx+1C8h], rdi
0x14016a892  mov     r14, [rsi+10h]
0x14016a896  mov     [rbp+40h+arg_18], ecx
0x14016a899  test    r14, r14
0x14016a89c  jz      short loc_14016A910
0x14016a89e  mov     [rsi+10h], rcx
0x14016a8a2  lea     rax, [rbp+40h+arg_18]
0x14016a8a6  mov     r9, [r14+10h]; unsigned int *
0x14016a8aa  xor     edx, edx; int *
0x14016a8ac  mov     r8, [r14+8]; void **
0x14016a8b0  mov     qword ptr [rsp+140h+Destination.Length], rax; int *
0x14016a8b5  mov     rax, [r14+38h]
0x14016a8b9  mov     [rsp+140h+var_F0], rcx; struct _STRING *
0x14016a8be  mov     [rsp+140h+var_F8], ecx; unsigned int
0x14016a8c2  mov     rcx, [r14]; int *
0x14016a8c5  mov     [rsp+140h+var_100], rax; struct _UNICODE_STRING *
0x14016a8ca  mov     rax, [r14+30h]
0x14016a8ce  mov     [rsp+140h+var_108], rax; void *
0x14016a8d3  mov     rax, [r14+28h]
0x14016a8d7  mov     qword ptr [rsp+140h+NewIrql], rax; NewIrql
0x14016a8dc  mov     eax, [r14+20h]
0x14016a8e0  mov     dword ptr [rsp+140h+var_118], eax; unsigned int
0x14016a8e4  mov     rax, [r14+18h]
0x14016a8e8  mov     [rsp+140h+var_120], rax; enum _NDIS_MEDIUM *
0x14016a8ed  call    ?ndisOpenAdapterLegacyProtocol@@YAXPEAH0PEAPEAXPEAIPEAW4_NDIS_MEDIUM@@IPEAX4PEAU_UNICODE_STRING@@IPEAU_STRING@@0@Z; ndisOpenAdapterLegacyProtocol(int *,int *,void * *,uint *,_NDIS_MEDIUM *,uint,void *,void *,_UNICODE_STRING *,uint,_STRING *,int *)
0x14016a8f2  mov     rax, [r14+8]
0x14016a8f6  mov     rcx, [rax]
0x14016a8f9  test    rcx, rcx
0x14016a8fc  jz      short loc_14016A931
0x14016a8fe  mov     eax, [rcx+0E0h]
0x14016a904  bts     eax, 1Dh
0x14016a908  mov     [rcx+0E0h], eax
0x14016a90e  jmp     short loc_14016A931
0x14016a910  mov     rax, [rbx+120h]
0x14016a917  lea     r9, [rsp+140h+Destination.Buffer]
0x14016a91c  mov     r8, r15
0x14016a91f  mov     [rsp+140h+var_120], r12
0x14016a924  lea     rdx, [rbp+40h+var_B0]
0x14016a928  lea     rcx, [rbp+40h+arg_18]
0x14016a92c  call    _guard_dispatch_icall
0x14016a931  mov     eax, [rbp+40h+arg_18]
0x14016a934  cmp     eax, 103h
0x14016a939  jnz     short loc_14016A94A
0x14016a93b  lea     rcx, [rbp+40h+Event]; void *
0x14016a93f  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x14016a944  mov     eax, [rbp+40h+var_58]
0x14016a947  mov     [rbp+40h+arg_18], eax
0x14016a94a  mov     qword ptr [rbx+1C8h], 0
0x14016a955  test    eax, eax
0x14016a957  jnz     short loc_14016A96A
0x14016a959  mov     r8b, 1; unsigned __int8
0x14016a95c  mov     rdx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x14016a95f  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x14016a962  call    ?ndisNotifyWmiBindUnbind@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_PROTOCOL_BLOCK@@E@Z; ndisNotifyWmiBindUnbind(_NDIS_MINIPORT_BLOCK *,_NDIS_PROTOCOL_BLOCK *,uchar)
0x14016a967  mov     eax, [rbp+40h+arg_18]
0x14016a96a  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14016a971  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14016a978  jz      short loc_14016A9A5
0x14016a97a  mov     rcx, cs:WPP_GLOBAL_Control
0x14016a981  mov     r9d, 0Ch
0x14016a987  mov     dword ptr [rsp+140h+var_108], eax
0x14016a98b  mov     rax, [rdi+0F10h]
0x14016a992  mov     qword ptr [rsp+140h+NewIrql], rax
0x14016a997  mov     rcx, [rcx+40h]
0x14016a99b  mov     qword ptr [rsp+140h+var_118], r13
0x14016a9a0  call    WPP_RECORDER_SF_ZZL
0x14016a9a5  mov     rcx, qword ptr [rsp+140h+Source]; P
0x14016a9aa  xor     edx, edx; Tag
0x14016a9ac  call    cs:__imp_ExFreePoolWithTag
0x14016a9b3  nop     dword ptr [rax+rax+00h]
0x14016a9b8  mov     qword ptr [rbx+1B0h], 0
0x14016a9c3  mov     r8b, 7; enum _NDIS_PT_REFTAG
0x14016a9c6  xor     edx, edx; unsigned __int8
0x14016a9c8  mov     rcx, rbx; this
0x14016a9cb  call    ?ndisDereferenceProtocol@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@EW4_NDIS_PT_REFTAG@@@Z; ndisDereferenceProtocol(_NDIS_PROTOCOL_BLOCK *,uchar,_NDIS_PT_REFTAG)
0x14016a9d0  mov     r12, [rsp+140h+arg_8]
0x14016a9d8  lea     r15, WPP_a3a0dfe1e6d739a64d48f097d248e118_Traceguids
0x14016a9df  mov     rcx, rbx; struct _NDIS_PROTOCOL_BLOCK *
0x14016a9e2  call    ?RELEASE_PROT_MUTEX@@YAXPEAU_NDIS_PROTOCOL_BLOCK@@@Z; RELEASE_PROT_MUTEX(_NDIS_PROTOCOL_BLOCK *)
0x14016a9e7  mov     r13, [rsp+140h+arg_10]
0x14016a9ef  mov     rsi, [rsp+140h+arg_0]
0x14016a9f7  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14016a9fe  mov     r14, [rsp+120h]
0x14016aa06  mov     eax, [rbp+40h+arg_18]
0x14016aa09  jz      short loc_14016AA3F
0x14016aa0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14016aa12  mov     r9d, 0Dh; int
0x14016aa18  mov     dword ptr [rsp+140h+var_108], eax; char
0x14016aa1c  mov     r8d, 6; int
0x14016aa22  mov     qword ptr [rsp+140h+NewIrql], rbx; char
0x14016aa27  mov     dl, 4; int
0x14016aa29  mov     qword ptr [rsp+140h+var_118], rdi; char
0x14016aa2e  mov     rcx, [rcx+40h]; int
0x14016aa32  mov     [rsp+140h+var_120], r15; struct _GUID *
0x14016aa37  call    WPP_RECORDER_SF_qqL
0x14016aa3c  mov     eax, [rbp+40h+arg_18]
0x14016aa3f  add     rsp, 128h
0x14016aa46  pop     r15
0x14016aa48  pop     rdi
0x14016aa49  pop     rbx
0x14016aa4a  pop     rbp
0x14016aa4b  retn
0x14016aa4d  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14016aa54  jz      short loc_14016A9DF
0x14016aa56  mov     rcx, cs:WPP_GLOBAL_Control
0x14016aa5d  mov     r9d, 0Bh; int
0x14016aa63  mov     qword ptr [rsp+140h+NewIrql], rbx; char
0x14016aa68  mov     r8d, 6; int
0x14016aa6e  mov     qword ptr [rsp+140h+var_118], rdi; char
0x14016aa73  mov     dl, 3; int
0x14016aa75  mov     [rsp+140h+var_120], r15; struct _GUID *
0x14016aa7a  mov     rcx, [rcx+40h]; int
0x14016aa7e  call    WPP_RECORDER_SF_qq
0x14016aa83  jmp     loc_14016A9DF
```
