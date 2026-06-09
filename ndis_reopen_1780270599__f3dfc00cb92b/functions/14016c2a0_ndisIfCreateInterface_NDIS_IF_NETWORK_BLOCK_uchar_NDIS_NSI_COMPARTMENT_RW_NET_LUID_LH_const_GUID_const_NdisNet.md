# ndisIfCreateInterface(_NDIS_IF_NETWORK_BLOCK *,uchar,_NDIS_NSI_COMPARTMENT_RW *,_NET_LUID_LH const *,_GUID const *,NdisNetworkInterfacePersistedState const *,_NDIS_FILTER_BLOCK *,NdisIfBlockSource)

- ea: `0x14016c2a0`
- end: `0x14016c6f5`
- name: `?ndisIfCreateInterface@@YAJPEAU_NDIS_IF_NETWORK_BLOCK@@EPEAU_NDIS_NSI_COMPARTMENT_RW@@PEBT_NET_LUID_LH@@PEBU_GUID@@PEBUNdisNetworkInterfacePersistedState@@PEAU_NDIS_FILTER_BLOCK@@W4NdisIfBlockSource@@@Z`
- size: `1109`
- prototype: `__int64 __usercall@<rax>(struct _NDIS_IF_NETWORK_BLOCK *@<rcx>, unsigned __int8@<dl>, struct _NDIS_NSI_COMPARTMENT_RW *@<r8>, const union _NET_LUID_LH *@<r9>, const struct _GUID *, const struct NdisNetworkInterfacePersistedState *, struct _NDIS_FILTER_BLOCK *, enum NdisIfBlockSource)`
- caller_count: `4`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140067310`
- `0x1400741b0`
- `0x1400d0654`
- `0x1400d07f8`

## callees

- `0x14001d240`
- `0x140072110`
- `0x14007e090`
- `0x140080b60`
- `0x1400836c0`
- `0x1400cf3e0`
- `0x1400eb4c0`
- `0x14014ec80`
- `0x14016c2a0`
- `0x14016dfd0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140175bba`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140175c65`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140175bba`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140175c65`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140175bce`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140175c12`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140175c79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140175c97`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140175bce`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140175c12`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140175c79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140175c97`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140175bf4`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140175bf4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140175b94`
- `ntoskrnl!RtlInitUnicodeString` at `0x140175c42`
- `ntoskrnl!RtlInitUnicodeString` at `0x140175b94`
- `ntoskrnl!RtlInitUnicodeString` at `0x140175c42`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016c60d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016c60d`
- `ntoskrnl!ExAllocatePool2` at `0x14016c36e`
- `ntoskrnl!ExAllocatePool2` at `0x14016c36e`
- `ntoskrnl!ExUuidCreate` at `0x140175af8`
- `ntoskrnl!ExUuidCreate` at `0x140175af8`

## pseudocode

```c
__int64 __fastcall ndisIfCreateInterface(
        struct _NDIS_IF_NETWORK_BLOCK *a1,
        char a2,
        struct _NDIS_NSI_COMPARTMENT_RW *a3,
        const union _NET_LUID_LH *a4,
        const struct _GUID *a5,
        const struct NdisNetworkInterfacePersistedState *a6,
        struct _NDIS_FILTER_BLOCK *a7,
        enum NdisIfBlockSource a8)
{
  UINT32 v9; // r12d
  char v10; // al
  unsigned __int16 v12; // si
  __int64 Pool2; // rax
  __int64 v14; // rdi
  _NDIS_MINIPORT_BLOCK *Miniport; // rbx
  _UNICODE_STRING *FilterFriendlyName; // rdx
  unsigned __int16 Length; // ax
  unsigned int v18; // ecx
  size_t v19; // r8
  unsigned int SupportedStatistics; // ecx
  _NET_IF_ADMIN_STATUS ifAdminStatus; // ecx
  unsigned int ifMtu; // ecx
  ULONG64 Value; // rbx
  __int128 v24; // xmm0
  __int64 v25; // rax
  unsigned int Handle; // eax
  unsigned int v27; // edx
  NTSTATUS appended; // esi
  NET_IFTYPE v29; // r8
  int v31; // eax
  __int64 v32; // rdx
  unsigned __int16 v33; // ax
  __int64 v34; // rdx
  unsigned __int16 v35; // ax
  unsigned int v36; // ecx
  size_t v37; // r8
  char v38; // al
  unsigned __int16 v39; // ax
  __int16 v40; // ax
  unsigned int v41; // esi
  size_t v42; // r8
  size_t v43; // r8
  char *v44; // rcx
  char *v45; // rdx
  size_t v46; // r8
  int v47; // [rsp+28h] [rbp-79h]
  UINT32 v48; // [rsp+58h] [rbp-49h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-41h] BYREF
  struct _UNICODE_STRING String; // [rsp+70h] [rbp-31h] BYREF
  UNICODE_STRING Source; // [rsp+80h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-11h] BYREF
  char v53; // [rsp+E8h] [rbp+47h]

  *(_QWORD *)&Source.Length = 262146;
  v9 = 0;
  Source.Buffer = L" ";
  v48 = 0;
  v10 = (char)a4;
  Destination = 0;
  DestinationString = 0;
  String = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_qqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      a2,
      22,
      12,
      (struct _GUID *)&WPP_a95b111799e83bb10d1a4a940a9bc010_Traceguids,
      (char)a1,
      (char)a3,
      (char)a4,
      (char)a7);
    v10 = (char)a4;
  }
  if ( a1 )
  {
    if ( a6 && *((_WORD *)a6 + 32) > 0x20u )
    {
      appended = -1073741811;
      goto LABEL_25;
    }
    if ( a7 && a7->Miniport->IfBlock->ifPhysAddress.Length > 0x20u )
    {
      appended = -1073741811;
      goto LABEL_24;
    }
    *(_DWORD *)&String.Length = 0x2000000;
    v12 = 512;
    Pool2 = ExAllocatePool2(64, 1784, 1718174798);
    v14 = Pool2;
    if ( !Pool2 )
    {
      appended = -1073741670;
      goto LABEL_24;
    }
    *(_DWORD *)Pool2 = 6291840;
    v53 = 0;
    String.Buffer = (wchar_t *)(Pool2 + 1272);
    if ( !a6 )
    {
      if ( a7 )
      {
        *(_DWORD *)(Pool2 + 4) |= 2u;
        Miniport = a7->Miniport;
        FilterFriendlyName = a7->FilterFriendlyName;
        *(_DWORD *)(Pool2 + 20) = -1;
        *(_DWORD *)(Pool2 + 28) = Miniport->IfBlock->AccessType;
        *(_DWORD *)(Pool2 + 32) = Miniport->IfBlock->DirectionType;
        *(_DWORD *)(Pool2 + 36) = Miniport->IfBlock->ConnectionType;
        *(_BYTE *)(Pool2 + 40) = 0;
        Length = FilterFriendlyName->Length;
        if ( FilterFriendlyName->Length > 0x200u )
        {
          *(_WORD *)(v14 + 752) = 512;
          *(_WORD *)(v14 + 48) = 512;
        }
        else
        {
          *(_WORD *)(v14 + 752) = Length;
          *(_WORD *)(v14 + 48) = Length;
          if ( !Length )
          {
LABEL_14:
            *(_BYTE *)(v14 + 738) = Miniport->IfBlock->ifHideInterfaceInUi;
            v18 = Miniport->IfBlock->ifPhysAddress.Length;
            *(_WORD *)(v14 + 42) = v18;
            *(_WORD *)(v14 + 644) = v18;
            *(_DWORD *)(v14 + 44) = 44565126;
            memmove((void *)(v14 + 646), Miniport->IfBlock->ifPhysAddress.Address, v18);
            v19 = *(unsigned __int16 *)(v14 + 42);
            *(_WORD *)(v14 + 678) = v19;
            memmove((void *)(v14 + 680), Miniport->IfBlock->PermanentPhysAddress.Address, v19);
            *(_GUID *)(v14 + 52) = a7->InterfaceGuid;
            SupportedStatistics = Miniport->IfBlock->SupportedStatistics;
            *(_DWORD *)(v14 + 88) = a7->MediaType;
            *(_DWORD *)(v14 + 92) = a7->PhysicalMediaType;
            *(_DWORD *)(v14 + 84) = SupportedStatistics;
            ifAdminStatus = Miniport->IfBlock->ifAdminStatus;
            *(_QWORD *)(v14 + 720) = a7->XmitLinkSpeed;
            *(_QWORD *)(v14 + 728) = a7->RcvLinkSpeed;
            *(_DWORD *)(v14 + 740) = a7->MediaConnectState;
            *(_DWORD *)(v14 + 744) = a7->MediaDuplexState;
            *(_DWORD *)(v14 + 712) = ifAdminStatus;
            *(_DWORD *)(v14 + 632) = Miniport->IfBlock->ifOperStatus;
            *(_DWORD *)(v14 + 636) = Miniport->IfBlock->ifOperStatusFlags;
            ifMtu = Miniport->IfBlock->ifMtu;
            Value = a4->Value;
            *(_DWORD *)(v14 + 640) = ifMtu;
            goto LABEL_15;
          }
          v12 = Length;
        }
        memmove((void *)(v14 + 754), FilterFriendlyName->Buffer, v12);
        goto LABEL_14;
      }
      v38 = a2;
      if ( a2 )
      {
        appended = NdisIfAllocateNetLuidIndexEx(24, *((_DWORD *)a3 + 404) & 1, &v48);
        if ( appended )
        {
LABEL_23:
          ExFreePoolWithTag((PVOID)v14, 0);
LABEL_24:
          v10 = (char)a4;
          goto LABEL_25;
        }
        v9 = v48;
        *((_WORD *)a3 + 7) = 24;
        v53 = 1;
        *((_QWORD *)a3 + 1) = *((_QWORD *)a3 + 1)
                            & 0xFFFF000000000000uLL
                            ^ ((unsigned __int64)v9 << 24)
                            & 0xFFFFFF000000LL;
        appended = ExUuidCreate((UUID *)a3 + 2);
        if ( appended < 0 )
          goto LABEL_16;
        v38 = a2;
      }
      Value = *((_QWORD *)a3 + 1);
      *(_QWORD *)(v14 + 28) = 1;
      *(_DWORD *)(v14 + 36) = 1;
      *(_BYTE *)(v14 + 40) = 0;
      *(_QWORD *)(v14 + 88) = 17;
      *(_DWORD *)(v14 + 640) = 1500;
      *(_QWORD *)(v14 + 720) = 0x40000000;
      *(_QWORD *)(v14 + 728) = 0x40000000;
      *(_DWORD *)(v14 + 740) = 1;
      *(_DWORD *)(v14 + 744) = 2;
      *(_QWORD *)(v14 + 632) = 1;
      *(_OWORD *)(v14 + 52) = *((_OWORD *)a3 + 2);
      if ( v38 )
      {
        RtlInitUnicodeString(&DestinationString, &xmmword_140123222);
        *(_DWORD *)&Destination.Length = 0x2000000;
        Destination.Buffer = (wchar_t *)(v14 + 754);
        RtlCopyUnicodeString(&Destination, &DestinationString);
        appended = RtlAppendUnicodeStringToString(&Destination, &Source);
        if ( appended < 0 )
          goto LABEL_16;
        appended = RtlIntegerToUnicodeString(*(_DWORD *)(*((_QWORD *)a1 + 6) + 16LL), 0xAu, &String);
        if ( appended < 0 )
          goto LABEL_16;
        appended = RtlAppendUnicodeStringToString(&Destination, &String);
        if ( appended < 0 )
          goto LABEL_16;
        v39 = Destination.Length;
        *(_WORD *)(v14 + 752) = Destination.Length;
        *(_WORD *)(v14 + 48) = v39;
        RtlInitUnicodeString(&DestinationString, &xmmword_140123432);
        *(_DWORD *)&Destination.Length = 0x2000000;
        Destination.Buffer = (wchar_t *)(v14 + 118);
        RtlCopyUnicodeString(&Destination, &DestinationString);
        appended = RtlAppendUnicodeStringToString(&Destination, &Source);
        if ( appended < 0 || (appended = RtlAppendUnicodeStringToString(&Destination, &String), appended < 0) )
        {
LABEL_16:
          v29 = 24;
          goto LABEL_17;
        }
        v40 = *(_WORD *)(v14 + 48);
        v41 = Destination.Length;
        v42 = *(unsigned __int16 *)(v14 + 752);
        *(_WORD *)(v14 + 116) = Destination.Length;
        *((_WORD *)a3 + 24) = v40;
        memmove((char *)a3 + 50, (const void *)(v14 + 754), v42);
        v43 = v41;
        *((_WORD *)a3 + 282) = v41;
        v44 = (char *)a3 + 566;
        v45 = (char *)(v14 + 118);
      }
      else
      {
        if ( !ndisIsValidIfString((const struct _IF_COUNTED_STRING_LH *)((char *)a3 + 48))
          || !ndisIsValidIfString((const struct _IF_COUNTED_STRING_LH *)((char *)a3 + 564)) )
        {
          appended = -1073676267;
LABEL_17:
          if ( v53 )
            NdisIfFreeNetLuidIndex(v29, v9);
          goto LABEL_23;
        }
        v46 = *((unsigned __int16 *)a3 + 24);
        *(_WORD *)(v14 + 48) = v46;
        memmove((void *)(v14 + 754), (char *)a3 + 50, v46);
        v43 = *((unsigned __int16 *)a3 + 282);
        v45 = (char *)a3 + 566;
        *(_WORD *)(v14 + 116) = v43;
        v44 = (char *)(v14 + 118);
      }
      memmove(v44, v45, v43);
      *(_DWORD *)(v14 + 712) = 1;
LABEL_15:
      v24 = *((_OWORD *)a1 + 2);
      v25 = *((_QWORD *)a1 + 6);
      *(_WORD *)(v14 + 50) = 754;
      *(_OWORD *)(v14 + 68) = v24;
      *(_DWORD *)(v14 + 96) = *(_DWORD *)(v25 + 16);
      *(_WORD *)(v14 + 736) = 0;
      *(_OWORD *)(v14 + 100) = v24;
      Handle = (unsigned int)ndisIfNdisProviderGetHandle(a3 != 0);
      appended = ndisIfRegisterInterfaceEx(Handle, Value, (_DWORD)a7, v14, a8, v27, (__int64)&v48);
      if ( !appended )
      {
        if ( a3 )
          ndisIfUpdateLoopbackInterfaceOnNetwork(a1, Value);
        goto LABEL_23;
      }
      goto LABEL_16;
    }
    v31 = *((unsigned __int16 *)a6 + 8) - 1;
    *(_QWORD *)(v14 + 28) = 2;
    *(_DWORD *)(v14 + 36) = 1;
    switch ( v31 )
    {
      case 0:
        switch ( *((_DWORD *)a6 + 14) )
        {
          case 9:
            goto LABEL_39;
          case 0xA:
            goto LABEL_40;
          case 0xB:
            *(_DWORD *)(v14 + 32) = 2;
            goto LABEL_40;
          case 0xC:
            goto LABEL_39;
        }
        break;
      case 22:
LABEL_39:
        *(_DWORD *)(v14 + 36) = 3;
        goto LABEL_40;
      case 36:
        *(_DWORD *)(v14 + 28) = 4;
        break;
      case 130:
LABEL_40:
        *(_DWORD *)(v14 + 28) = 3;
        break;
      default:
        break;
    }
    *(_DWORD *)(v14 + 20) = -1;
    *(_DWORD *)(v14 + 4) = 28;
    if ( *((_BYTE *)a6 + 133) )
      *(_DWORD *)(v14 + 4) = 29;
    if ( *((_BYTE *)a6 + 132) )
      *(_BYTE *)(v14 + 738) = 1;
    v32 = *(_QWORD *)a6;
    *(_DWORD *)(v14 + 42) = 0;
    *(_WORD *)(v14 + 46) = 0;
    *(_DWORD *)(v14 + 88) = *((_DWORD *)a6 + 14);
    *(_DWORD *)(v14 + 92) = *((_DWORD *)a6 + 15);
    *(_WORD *)(v14 + 644) = 0;
    *(_WORD *)(v14 + 678) = 0;
    *(_QWORD *)(v14 + 720) = 0;
    *(_QWORD *)(v14 + 728) = 0;
    *(_QWORD *)(v14 + 740) = 0;
    *(_DWORD *)(v14 + 24) = 0;
    *(_BYTE *)(v14 + 40) = 0;
    *(_QWORD *)(v14 + 636) = 0;
    *(_DWORD *)(v14 + 712) = 2;
    *(_DWORD *)(v14 + 632) = 6;
    v33 = *(_WORD *)v32;
    if ( *(_WORD *)v32 <= 0x200u )
    {
      *(_WORD *)(v14 + 116) = v33;
      if ( !v33 )
      {
LABEL_50:
        v34 = *((_QWORD *)a6 + 1);
        v35 = *(_WORD *)v34;
        if ( *(_WORD *)v34 )
        {
          if ( v35 > 0x200u )
            v35 = 512;
          *(_WORD *)(v14 + 752) = v35;
          memmove((void *)(v14 + 754), *(const void **)(v34 + 8), v35);
          *(_WORD *)(v14 + 48) = *(_WORD *)(v14 + 752);
        }
        v36 = *((unsigned __int16 *)a6 + 32);
        *(struct _GUID *)(v14 + 52) = *a5;
        if ( (_WORD)v36 )
        {
          *(_WORD *)(v14 + 42) = v36;
          *(_WORD *)(v14 + 644) = v36;
          *(_DWORD *)(v14 + 44) = 44565126;
          memmove((void *)(v14 + 646), (char *)a6 + 66, v36);
          v37 = *(unsigned __int16 *)(v14 + 42);
          *(_WORD *)(v14 + 678) = v37;
          memmove((void *)(v14 + 680), (char *)a6 + 100, v37);
        }
        Value = a4->Value;
        goto LABEL_15;
      }
    }
    else
    {
      v33 = 512;
      *(_WORD *)(v14 + 116) = 512;
    }
    memmove((void *)(v14 + 118), *(const void **)(v32 + 8), v33);
    goto LABEL_50;
  }
  appended = -1073741811;
LABEL_25:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqqqL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      a2,
      (_DWORD)a3,
      (_DWORD)a4,
      v47,
      (char)a1,
      (char)a3,
      v10,
      (char)a7,
      appended);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14016c2a0  mov     rax, rsp
0x14016c2a3  mov     [rax+20h], r9
0x14016c2a7  mov     [rax+10h], dl
0x14016c2aa  push    rbp
0x14016c2ab  push    rsi
0x14016c2ac  push    r13
0x14016c2ae  push    r14
0x14016c2b0  push    r15
0x14016c2b2  lea     rbp, [rax-3Fh]
0x14016c2b6  sub     rsp, 0B0h
0x14016c2bd  mov     [rax-38h], r12
0x14016c2c1  xorps   xmm0, xmm0
0x14016c2c4  mov     r14, rcx
0x14016c2c7  mov     qword ptr [rbp+37h+Source.Length], 40002h
0x14016c2cf  lea     rcx, asc_1400FAF98; " "
0x14016c2d6  xor     r12d, r12d
0x14016c2d9  xorps   xmm1, xmm1
0x14016c2dc  mov     [rbp+37h+Source.Buffer], rcx
0x14016c2e0  mov     [rbp+37h+var_80], r12d
0x14016c2e4  mov     rax, r9
0x14016c2e7  mov     r13, r8
0x14016c2ea  movups  xmmword ptr [rbp+37h+Destination.Length], xmm0
0x14016c2ee  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm1
0x14016c2f2  movups  xmmword ptr [rbp+37h+String.Length], xmm0
0x14016c2f6  mov     r15, [rbp+37h+arg_30]
0x14016c2fa  lea     rsi, WPP_RECORDER_INITIALIZED
0x14016c301  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14016c308  jnz     loc_14016C692
0x14016c30e  test    r14, r14
0x14016c311  jz      loc_14016C6D7
0x14016c317  mov     [rsp+0D0h+arg_10], rbx
0x14016c31f  mov     rbx, [rbp+37h+arg_28]
0x14016c323  test    rbx, rbx
0x14016c326  jnz     loc_14016C680
0x14016c32c  test    r15, r15
0x14016c32f  jz      short loc_14016C34A
0x14016c331  mov     rax, [r15+20h]
0x14016c335  mov     rcx, [rax+0FC8h]
0x14016c33c  cmp     word ptr [rcx+464h], 20h ; ' '
0x14016c344  ja      loc_14016C6E1
0x14016c34a  mov     edx, 6F8h
0x14016c34f  mov     [rsp+0A8h], rdi
0x14016c357  mov     ecx, 40h ; '@'
0x14016c35c  mov     dword ptr [rbp+37h+String.Length], 2000000h
0x14016c363  mov     r8d, 6669444Eh
0x14016c369  mov     esi, 200h
0x14016c36e  call    cs:__imp_ExAllocatePool2
0x14016c375  nop     dword ptr [rax+rax+00h]
0x14016c37a  mov     rdi, rax
0x14016c37d  test    rax, rax
0x14016c380  jz      loc_14016C6EB
0x14016c386  mov     dword ptr [rax], 600180h
0x14016c38c  mov     r8d, 18h
0x14016c392  add     rax, 4F8h
0x14016c398  mov     [rbp+37h+arg_0], r12b
0x14016c39c  mov     [rbp+37h+String.Buffer], rax
0x14016c3a0  test    rbx, rbx
0x14016c3a3  jnz     loc_1401758C2
0x14016c3a9  test    r15, r15
0x14016c3ac  jz      loc_140175A91
0x14016c3b2  or      dword ptr [rdi+4], 2
0x14016c3b6  mov     rbx, [r15+20h]
0x14016c3ba  mov     rdx, [r15+30h]
0x14016c3be  mov     dword ptr [rdi+14h], 0FFFFFFFFh
0x14016c3c5  mov     rax, [rbx+0FC8h]
0x14016c3cc  mov     ecx, [rax+210h]
0x14016c3d2  mov     [rdi+1Ch], ecx
0x14016c3d5  mov     rax, [rbx+0FC8h]
0x14016c3dc  mov     ecx, [rax+214h]
0x14016c3e2  mov     [rdi+20h], ecx
0x14016c3e5  mov     rax, [rbx+0FC8h]
0x14016c3ec  mov     ecx, [rax+218h]
0x14016c3f2  mov     [rdi+24h], ecx
0x14016c3f5  mov     [rdi+28h], r12b
0x14016c3f9  movzx   eax, word ptr [rdx]
0x14016c3fc  cmp     ax, si
0x14016c3ff  ja      loc_14016C5DE
0x14016c405  mov     [rdi+2F0h], ax
0x14016c40c  mov     [rdi+30h], ax
0x14016c410  test    ax, ax
0x14016c413  jz      short loc_14016C42C
0x14016c415  movzx   esi, ax
0x14016c418  mov     rdx, [rdx+8]; Src
0x14016c41c  lea     rcx, [rdi+2F2h]; void *
0x14016c423  movzx   r8d, si; Size
0x14016c427  call    memmove
0x14016c42c  mov     rax, [rbx+0FC8h]
0x14016c433  movzx   ecx, byte ptr [rax+4C2h]
0x14016c43a  mov     [rdi+2E2h], cl
0x14016c440  mov     rax, [rbx+0FC8h]
0x14016c447  movzx   ecx, word ptr [rax+464h]
0x14016c44e  mov     [rdi+2Ah], cx
0x14016c452  mov     r8d, ecx; Size
0x14016c455  mov     [rdi+284h], cx
0x14016c45c  lea     rcx, [rdi+286h]; void *
0x14016c463  mov     dword ptr [rdi+2Ch], 2A80286h
0x14016c46a  mov     rdx, [rbx+0FC8h]
0x14016c471  add     rdx, 466h; Src
0x14016c478  call    memmove
0x14016c47d  movzx   r8d, word ptr [rdi+2Ah]; Size
0x14016c482  lea     rcx, [rdi+2A8h]; void *
0x14016c489  mov     [rdi+2A6h], r8w
0x14016c491  mov     rdx, [rbx+0FC8h]
0x14016c498  add     rdx, 488h; Src
0x14016c49f  call    memmove
0x14016c4a4  movups  xmm0, xmmword ptr [r15+298h]
0x14016c4ac  movups  xmmword ptr [rdi+34h], xmm0
0x14016c4b0  mov     rax, [rbx+0FC8h]
0x14016c4b7  mov     ecx, [rax+588h]
0x14016c4bd  mov     eax, [r15+150h]
0x14016c4c4  mov     [rdi+58h], eax
0x14016c4c7  mov     eax, [r15+154h]
0x14016c4ce  mov     [rdi+5Ch], eax
0x14016c4d1  mov     [rdi+54h], ecx
0x14016c4d4  mov     rax, [rbx+0FC8h]
0x14016c4db  mov     ecx, [rax+4A8h]
0x14016c4e1  mov     rax, [r15+160h]
0x14016c4e8  mov     [rdi+2D0h], rax
0x14016c4ef  mov     rax, [r15+168h]
0x14016c4f6  mov     [rdi+2D8h], rax
0x14016c4fd  mov     eax, [r15+158h]
0x14016c504  mov     [rdi+2E4h], eax
0x14016c50a  mov     eax, [r15+15Ch]
0x14016c511  mov     [rdi+2E8h], eax
0x14016c517  mov     [rdi+2C8h], ecx
0x14016c51d  mov     rax, [rbx+0FC8h]
0x14016c524  mov     ecx, [rax+458h]
0x14016c52a  mov     [rdi+278h], ecx
0x14016c530  mov     rax, [rbx+0FC8h]
0x14016c537  mov     ecx, [rax+45Ch]
0x14016c53d  mov     [rdi+27Ch], ecx
0x14016c543  mov     rax, [rbx+0FC8h]
0x14016c54a  mov     rbx, [rbp+37h+arg_18]
0x14016c54e  mov     ecx, [rax+460h]
0x14016c554  mov     rbx, [rbx]
0x14016c557  mov     [rdi+280h], ecx
0x14016c55d  movups  xmm0, xmmword ptr [r14+20h]
0x14016c562  mov     rax, [r14+30h]
0x14016c566  mov     word ptr [rdi+32h], 2F2h
0x14016c56c  movups  xmmword ptr [rdi+44h], xmm0
0x14016c570  mov     ecx, [rax+10h]
0x14016c573  mov     rax, [rbp+37h+arg_28]
0x14016c577  mov     [rdi+60h], ecx
0x14016c57a  mov     word ptr [rdi+2E0h], 0
0x14016c583  movups  xmmword ptr [rdi+64h], xmm0
0x14016c587  test    rax, rax
0x14016c58a  jz      short loc_14016C5EE
0x14016c58c  mov     edx, [rax+20h]
0x14016c58f  test    r13, r13
0x14016c592  setnz   cl; bool
0x14016c595  call    ?ndisIfNdisProviderGetHandle@@YAPEAX_N@Z; ndisIfNdisProviderGetHandle(bool)
0x14016c59a  mov     rcx, rax
0x14016c59d  mov     r9, rdi
0x14016c5a0  lea     rax, [rbp+37h+var_80]
0x14016c5a4  mov     r8, r15
0x14016c5a7  mov     qword ptr [rsp+0D0h+var_A0], rax
0x14016c5ac  mov     eax, [rbp+37h+arg_38]
0x14016c5af  mov     dword ptr [rsp+0D0h+var_A8], edx
0x14016c5b3  mov     rdx, rbx
0x14016c5b6  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14016c5ba  call    ndisIfRegisterInterfaceEx
0x14016c5bf  mov     esi, eax
0x14016c5c1  test    eax, eax
0x14016c5c3  jz      short loc_14016C5F2
0x14016c5c5  mov     r8d, 18h
0x14016c5cb  cmp     [rbp+37h+arg_0], 0
0x14016c5cf  jz      short loc_14016C608
0x14016c5d1  mov     ecx, r8d; ifType
0x14016c5d4  mov     edx, r12d; NetLuidIndex
0x14016c5d7  call    NdisIfFreeNetLuidIndex
0x14016c5dc  jmp     short loc_14016C608
0x14016c5de  mov     [rdi+2F0h], si
0x14016c5e5  mov     [rdi+30h], si
0x14016c5e9  jmp     loc_14016C418
0x14016c5ee  xor     edx, edx
0x14016c5f0  jmp     short loc_14016C58F
0x14016c5f2  test    r13, r13
0x14016c5f5  jz      short loc_14016C608
0x14016c5f7  mov     rdx, rbx
0x14016c5fa  mov     rcx, r14
0x14016c5fd  call    ndisIfUpdateLoopbackInterfaceOnNetwork
0x14016c602  jmp     short loc_14016C608
0x14016c604  test    esi, esi
0x14016c606  jnz     short loc_14016C5C5
0x14016c608  xor     edx, edx; Tag
0x14016c60a  mov     rcx, rdi; P
0x14016c60d  call    cs:__imp_ExFreePoolWithTag
0x14016c614  nop     dword ptr [rax+rax+00h]
0x14016c619  mov     rdi, [rsp+0A8h]
0x14016c621  mov     rax, [rbp+37h+arg_18]
0x14016c625  mov     rbx, [rsp+0D0h+arg_10]
0x14016c62d  mov     r12, [rsp+0D0h+var_30]
0x14016c635  lea     rcx, WPP_RECORDER_INITIALIZED
0x14016c63c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14016c643  jz      short loc_14016C66D
0x14016c645  mov     rcx, cs:WPP_GLOBAL_Control
0x14016c64c  mov     [rsp+48h], esi
0x14016c650  mov     qword ptr [rsp+0D0h+var_90], r15
0x14016c655  mov     qword ptr [rsp+0D0h+var_98], rax
0x14016c65a  mov     rcx, [rcx+40h]
0x14016c65e  mov     qword ptr [rsp+0D0h+var_A0], r13
0x14016c663  mov     qword ptr [rsp+0D0h+var_A8], r14
0x14016c668  call    WPP_RECORDER_SF_qqqqL
0x14016c66d  mov     eax, esi
0x14016c66f  add     rsp, 0B0h
0x14016c676  pop     r15
0x14016c678  pop     r14
0x14016c67a  pop     r13
0x14016c67c  pop     rsi
0x14016c67d  pop     rbp
0x14016c67e  retn
0x14016c680  cmp     word ptr [rbx+40h], 20h ; ' '
0x14016c685  jbe     loc_14016C32C
0x14016c68b  mov     esi, 0C000000Dh
0x14016c690  jmp     short loc_14016C625
0x14016c692  mov     rcx, cs:WPP_GLOBAL_Control
0x14016c699  mov     r9d, 0Ch; int
0x14016c69f  mov     qword ptr [rsp+0D0h+var_90], r15; char
0x14016c6a4  mov     r8d, 16h; int
0x14016c6aa  mov     qword ptr [rsp+0D0h+var_98], rax; char
0x14016c6af  lea     rax, WPP_a95b111799e83bb10d1a4a940a9bc010_Traceguids
0x14016c6b6  mov     qword ptr [rsp+0D0h+var_A0], r13; char
0x14016c6bb  mov     rcx, [rcx+40h]; int
0x14016c6bf  mov     qword ptr [rsp+0D0h+var_A8], r14; char
0x14016c6c4  mov     [rsp+0D0h+var_B0], rax; struct _GUID *
0x14016c6c9  call    WPP_RECORDER_SF_qqqq
0x14016c6ce  mov     rax, [rbp+37h+arg_18]
0x14016c6d2  jmp     loc_14016C30E
0x14016c6d7  mov     esi, 0C000000Dh
0x14016c6dc  jmp     loc_14016C62D
0x14016c6e1  mov     esi, 0C000000Dh
0x14016c6e6  jmp     loc_14016C621
0x14016c6eb  mov     esi, 0C000009Ah
0x14016c6f0  jmp     loc_14016C619
0x1401758c2  movzx   eax, word ptr [rbx+10h]
0x1401758c6  dec     eax; switch 131 cases
0x1401758c8  mov     qword ptr [rdi+1Ch], 2
0x1401758d0  mov     dword ptr [rdi+24h], 1
0x1401758d7  cmp     eax, 82h
0x1401758dc  ja      short def_1401758F9; jumptable 00000001401758F9 default case, cases 2-22,24-36,38-130
0x1401758de  lea     rdx, cs:140000000h
0x1401758e5  cdqe
0x1401758e7  movzx   eax, ds:(byte_140104709 - 140000000h)[rdx+rax]
0x1401758ef  mov     ecx, ds:(jpt_1401758F9 - 140000000h)[rdx+rax*4]
0x1401758f6  add     rcx, rdx
0x1401758f9  jmp     rcx; switch jump
0x1401758ff  mov     dword ptr [rdi+1Ch], 4; jumptable 00000001401758F9 case 37
0x140175906  jmp     short def_1401758F9; jumptable 00000001401758F9 default case, cases 2-22,24-36,38-130
0x140175908  mov     ecx, [rbx+38h]; jumptable 00000001401758F9 case 1
0x14017590b  sub     ecx, 9
0x14017590e  jz      short loc_140175923; jumptable 00000001401758F9 case 23
0x140175910  sub     ecx, 1
0x140175913  jz      short loc_14017592A; jumptable 00000001401758F9 case 131
0x140175915  sub     ecx, 1
0x140175918  jz      loc_1401759D0
0x14017591e  cmp     ecx, 1
0x140175921  jnz     short def_1401758F9; jumptable 00000001401758F9 default case, cases 2-22,24-36,38-130
0x140175923  mov     dword ptr [rdi+24h], 3; jumptable 00000001401758F9 case 23
0x14017592a  mov     dword ptr [rdi+1Ch], 3; jumptable 00000001401758F9 case 131
0x140175931  mov     dword ptr [rdi+14h], 0FFFFFFFFh; jumptable 00000001401758F9 default case, cases 2-22,24-36,38-130
0x140175938  mov     dword ptr [rdi+4], 1Ch
0x14017593f  cmp     [rbx+85h], r12b
0x140175946  jz      short loc_14017594F
0x140175948  mov     dword ptr [rdi+4], 1Dh
0x14017594f  cmp     [rbx+84h], r12b
0x140175956  jz      short loc_14017595F
0x140175958  mov     byte ptr [rdi+2E2h], 1
0x14017595f  mov     rdx, [rbx]
0x140175962  xor     eax, eax
0x140175964  mov     [rdi+2Ah], eax
0x140175967  mov     [rdi+2Eh], ax
0x14017596b  mov     eax, [rbx+38h]
0x14017596e  mov     [rdi+58h], eax
0x140175971  mov     eax, [rbx+3Ch]
0x140175974  mov     [rdi+5Ch], eax
0x140175977  xor     eax, eax
0x140175979  mov     [rdi+284h], ax
0x140175980  mov     [rdi+2A6h], ax
0x140175987  mov     [rdi+2D0h], rax
0x14017598e  mov     [rdi+2D8h], rax
0x140175995  mov     [rdi+2E4h], rax
0x14017599c  mov     [rdi+18h], r12d
0x1401759a0  mov     [rdi+28h], r12b
0x1401759a4  mov     [rdi+27Ch], r12
0x1401759ab  mov     dword ptr [rdi+2C8h], 2
0x1401759b5  mov     dword ptr [rdi+278h], 6
0x1401759bf  movzx   eax, word ptr [rdx]
0x1401759c2  cmp     ax, si
0x1401759c5  jbe     short loc_1401759DC
0x1401759c7  movzx   eax, si
0x1401759ca  mov     [rdi+74h], si
0x1401759ce  jmp     short loc_1401759E5
0x1401759d0  mov     dword ptr [rdi+20h], 2
0x1401759d7  jmp     loc_14017592A; jumptable 00000001401758F9 case 131
0x1401759dc  mov     [rdi+74h], ax
0x1401759e0  test    ax, ax
0x1401759e3  jz      short loc_1401759F6
0x1401759e5  mov     rdx, [rdx+8]; Src
0x1401759e9  lea     rcx, [rdi+76h]; void *
0x1401759ed  movzx   r8d, ax; Size
  ... truncated ...
```
