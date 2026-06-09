# ndisIfCreateInterface(_NDIS_IF_NETWORK_BLOCK *,uchar,_NDIS_NSI_COMPARTMENT_RW *,_NET_LUID_LH const *,_GUID const *,NdisNetworkInterfacePersistedState const *,_NDIS_FILTER_BLOCK *,NdisIfBlockSource)

- ea: `0x140165310`
- end: `0x140165765`
- name: `?ndisIfCreateInterface@@YAJPEAU_NDIS_IF_NETWORK_BLOCK@@EPEAU_NDIS_NSI_COMPARTMENT_RW@@PEBT_NET_LUID_LH@@PEBU_GUID@@PEBUNdisNetworkInterfacePersistedState@@PEAU_NDIS_FILTER_BLOCK@@W4NdisIfBlockSource@@@Z`
- size: `1109`
- prototype: `__int64 __usercall@<rax>(struct _NDIS_IF_NETWORK_BLOCK *@<rcx>, unsigned __int8@<dl>, struct _NDIS_NSI_COMPARTMENT_RW *@<r8>, const union _NET_LUID_LH *@<r9>, const struct _GUID *, const struct NdisNetworkInterfacePersistedState *, struct _NDIS_FILTER_BLOCK *, enum NdisIfBlockSource)`
- caller_count: `4`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400429b0`
- `0x140062040`
- `0x1400cb4a4`
- `0x1400cb648`

## callees

- `0x1400290e0`
- `0x14006c790`
- `0x1400789c0`
- `0x14007b4c0`
- `0x14007ded0`
- `0x1400ca230`
- `0x1400e62c0`
- `0x140147ce0`
- `0x140165310`
- `0x140167130`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14016ed04`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14016edaf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14016ed04`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14016edaf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016ed18`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016ed5c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016edc3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016ede1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016ed18`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016ed5c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016edc3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14016ede1`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14016ed3e`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14016ed3e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016ecde`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016ed8c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016ecde`
- `ntoskrnl!RtlInitUnicodeString` at `0x14016ed8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016567d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016567d`
- `ntoskrnl!ExAllocatePool2` at `0x1401653de`
- `ntoskrnl!ExAllocatePool2` at `0x1401653de`
- `ntoskrnl!ExUuidCreate` at `0x14016ec42`
- `ntoskrnl!ExUuidCreate` at `0x14016ec42`

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
        RtlInitUnicodeString(&DestinationString, &xmmword_14011D232);
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
        RtlInitUnicodeString(&DestinationString, &xmmword_14011D442);
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
0x140165310  mov     rax, rsp
0x140165313  mov     [rax+20h], r9
0x140165317  mov     [rax+10h], dl
0x14016531a  push    rbp
0x14016531b  push    rsi
0x14016531c  push    r13
0x14016531e  push    r14
0x140165320  push    r15
0x140165322  lea     rbp, [rax-3Fh]
0x140165326  sub     rsp, 0B0h
0x14016532d  mov     [rax-38h], r12
0x140165331  xorps   xmm0, xmm0
0x140165334  mov     r14, rcx
0x140165337  mov     qword ptr [rbp+37h+Source.Length], 40002h
0x14016533f  lea     rcx, asc_1400F5F68; " "
0x140165346  xor     r12d, r12d
0x140165349  xorps   xmm1, xmm1
0x14016534c  mov     [rbp+37h+Source.Buffer], rcx
0x140165350  mov     [rbp+37h+var_80], r12d
0x140165354  mov     rax, r9
0x140165357  mov     r13, r8
0x14016535a  movups  xmmword ptr [rbp+37h+Destination.Length], xmm0
0x14016535e  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm1
0x140165362  movups  xmmword ptr [rbp+37h+String.Length], xmm0
0x140165366  mov     r15, [rbp+37h+arg_30]
0x14016536a  lea     rsi, WPP_RECORDER_INITIALIZED
0x140165371  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140165378  jnz     loc_140165702
0x14016537e  test    r14, r14
0x140165381  jz      loc_140165747
0x140165387  mov     [rsp+0D0h+arg_10], rbx
0x14016538f  mov     rbx, [rbp+37h+arg_28]
0x140165393  test    rbx, rbx
0x140165396  jnz     loc_1401656F0
0x14016539c  test    r15, r15
0x14016539f  jz      short loc_1401653BA
0x1401653a1  mov     rax, [r15+20h]
0x1401653a5  mov     rcx, [rax+0FC8h]
0x1401653ac  cmp     word ptr [rcx+464h], 20h ; ' '
0x1401653b4  ja      loc_140165751
0x1401653ba  mov     edx, 6F8h
0x1401653bf  mov     [rsp+0A8h], rdi
0x1401653c7  mov     ecx, 40h ; '@'
0x1401653cc  mov     dword ptr [rbp+37h+String.Length], 2000000h
0x1401653d3  mov     r8d, 6669444Eh
0x1401653d9  mov     esi, 200h
0x1401653de  call    cs:__imp_ExAllocatePool2
0x1401653e5  nop     dword ptr [rax+rax+00h]
0x1401653ea  mov     rdi, rax
0x1401653ed  test    rax, rax
0x1401653f0  jz      loc_14016575B
0x1401653f6  mov     dword ptr [rax], 600180h
0x1401653fc  mov     r8d, 18h
0x140165402  add     rax, 4F8h
0x140165408  mov     [rbp+37h+arg_0], r12b
0x14016540c  mov     [rbp+37h+String.Buffer], rax
0x140165410  test    rbx, rbx
0x140165413  jnz     loc_14016EA0C
0x140165419  test    r15, r15
0x14016541c  jz      loc_14016EBDB
0x140165422  or      dword ptr [rdi+4], 2
0x140165426  mov     rbx, [r15+20h]
0x14016542a  mov     rdx, [r15+30h]
0x14016542e  mov     dword ptr [rdi+14h], 0FFFFFFFFh
0x140165435  mov     rax, [rbx+0FC8h]
0x14016543c  mov     ecx, [rax+210h]
0x140165442  mov     [rdi+1Ch], ecx
0x140165445  mov     rax, [rbx+0FC8h]
0x14016544c  mov     ecx, [rax+214h]
0x140165452  mov     [rdi+20h], ecx
0x140165455  mov     rax, [rbx+0FC8h]
0x14016545c  mov     ecx, [rax+218h]
0x140165462  mov     [rdi+24h], ecx
0x140165465  mov     [rdi+28h], r12b
0x140165469  movzx   eax, word ptr [rdx]
0x14016546c  cmp     ax, si
0x14016546f  ja      loc_14016564E
0x140165475  mov     [rdi+2F0h], ax
0x14016547c  mov     [rdi+30h], ax
0x140165480  test    ax, ax
0x140165483  jz      short loc_14016549C
0x140165485  movzx   esi, ax
0x140165488  mov     rdx, [rdx+8]; Src
0x14016548c  lea     rcx, [rdi+2F2h]; void *
0x140165493  movzx   r8d, si; Size
0x140165497  call    memmove
0x14016549c  mov     rax, [rbx+0FC8h]
0x1401654a3  movzx   ecx, byte ptr [rax+4C2h]
0x1401654aa  mov     [rdi+2E2h], cl
0x1401654b0  mov     rax, [rbx+0FC8h]
0x1401654b7  movzx   ecx, word ptr [rax+464h]
0x1401654be  mov     [rdi+2Ah], cx
0x1401654c2  mov     r8d, ecx; Size
0x1401654c5  mov     [rdi+284h], cx
0x1401654cc  lea     rcx, [rdi+286h]; void *
0x1401654d3  mov     dword ptr [rdi+2Ch], 2A80286h
0x1401654da  mov     rdx, [rbx+0FC8h]
0x1401654e1  add     rdx, 466h; Src
0x1401654e8  call    memmove
0x1401654ed  movzx   r8d, word ptr [rdi+2Ah]; Size
0x1401654f2  lea     rcx, [rdi+2A8h]; void *
0x1401654f9  mov     [rdi+2A6h], r8w
0x140165501  mov     rdx, [rbx+0FC8h]
0x140165508  add     rdx, 488h; Src
0x14016550f  call    memmove
0x140165514  movups  xmm0, xmmword ptr [r15+298h]
0x14016551c  movups  xmmword ptr [rdi+34h], xmm0
0x140165520  mov     rax, [rbx+0FC8h]
0x140165527  mov     ecx, [rax+588h]
0x14016552d  mov     eax, [r15+150h]
0x140165534  mov     [rdi+58h], eax
0x140165537  mov     eax, [r15+154h]
0x14016553e  mov     [rdi+5Ch], eax
0x140165541  mov     [rdi+54h], ecx
0x140165544  mov     rax, [rbx+0FC8h]
0x14016554b  mov     ecx, [rax+4A8h]
0x140165551  mov     rax, [r15+160h]
0x140165558  mov     [rdi+2D0h], rax
0x14016555f  mov     rax, [r15+168h]
0x140165566  mov     [rdi+2D8h], rax
0x14016556d  mov     eax, [r15+158h]
0x140165574  mov     [rdi+2E4h], eax
0x14016557a  mov     eax, [r15+15Ch]
0x140165581  mov     [rdi+2E8h], eax
0x140165587  mov     [rdi+2C8h], ecx
0x14016558d  mov     rax, [rbx+0FC8h]
0x140165594  mov     ecx, [rax+458h]
0x14016559a  mov     [rdi+278h], ecx
0x1401655a0  mov     rax, [rbx+0FC8h]
0x1401655a7  mov     ecx, [rax+45Ch]
0x1401655ad  mov     [rdi+27Ch], ecx
0x1401655b3  mov     rax, [rbx+0FC8h]
0x1401655ba  mov     rbx, [rbp+37h+arg_18]
0x1401655be  mov     ecx, [rax+460h]
0x1401655c4  mov     rbx, [rbx]
0x1401655c7  mov     [rdi+280h], ecx
0x1401655cd  movups  xmm0, xmmword ptr [r14+20h]
0x1401655d2  mov     rax, [r14+30h]
0x1401655d6  mov     word ptr [rdi+32h], 2F2h
0x1401655dc  movups  xmmword ptr [rdi+44h], xmm0
0x1401655e0  mov     ecx, [rax+10h]
0x1401655e3  mov     rax, [rbp+37h+arg_28]
0x1401655e7  mov     [rdi+60h], ecx
0x1401655ea  mov     word ptr [rdi+2E0h], 0
0x1401655f3  movups  xmmword ptr [rdi+64h], xmm0
0x1401655f7  test    rax, rax
0x1401655fa  jz      short loc_14016565E
0x1401655fc  mov     edx, [rax+20h]
0x1401655ff  test    r13, r13
0x140165602  setnz   cl; bool
0x140165605  call    ?ndisIfNdisProviderGetHandle@@YAPEAX_N@Z; ndisIfNdisProviderGetHandle(bool)
0x14016560a  mov     rcx, rax
0x14016560d  mov     r9, rdi
0x140165610  lea     rax, [rbp+37h+var_80]
0x140165614  mov     r8, r15
0x140165617  mov     qword ptr [rsp+0D0h+var_A0], rax
0x14016561c  mov     eax, [rbp+37h+arg_38]
0x14016561f  mov     dword ptr [rsp+0D0h+var_A8], edx
0x140165623  mov     rdx, rbx
0x140165626  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14016562a  call    ndisIfRegisterInterfaceEx
0x14016562f  mov     esi, eax
0x140165631  test    eax, eax
0x140165633  jz      short loc_140165662
0x140165635  mov     r8d, 18h
0x14016563b  cmp     [rbp+37h+arg_0], 0
0x14016563f  jz      short loc_140165678
0x140165641  mov     ecx, r8d; ifType
0x140165644  mov     edx, r12d; NetLuidIndex
0x140165647  call    NdisIfFreeNetLuidIndex
0x14016564c  jmp     short loc_140165678
0x14016564e  mov     [rdi+2F0h], si
0x140165655  mov     [rdi+30h], si
0x140165659  jmp     loc_140165488
0x14016565e  xor     edx, edx
0x140165660  jmp     short loc_1401655FF
0x140165662  test    r13, r13
0x140165665  jz      short loc_140165678
0x140165667  mov     rdx, rbx
0x14016566a  mov     rcx, r14
0x14016566d  call    ndisIfUpdateLoopbackInterfaceOnNetwork
0x140165672  jmp     short loc_140165678
0x140165674  test    esi, esi
0x140165676  jnz     short loc_140165635
0x140165678  xor     edx, edx; Tag
0x14016567a  mov     rcx, rdi; P
0x14016567d  call    cs:__imp_ExFreePoolWithTag
0x140165684  nop     dword ptr [rax+rax+00h]
0x140165689  mov     rdi, [rsp+0A8h]
0x140165691  mov     rax, [rbp+37h+arg_18]
0x140165695  mov     rbx, [rsp+0D0h+arg_10]
0x14016569d  mov     r12, [rsp+0D0h+var_30]
0x1401656a5  lea     rcx, WPP_RECORDER_INITIALIZED
0x1401656ac  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1401656b3  jz      short loc_1401656DD
0x1401656b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1401656bc  mov     [rsp+48h], esi
0x1401656c0  mov     qword ptr [rsp+0D0h+var_90], r15
0x1401656c5  mov     qword ptr [rsp+0D0h+var_98], rax
0x1401656ca  mov     rcx, [rcx+40h]
0x1401656ce  mov     qword ptr [rsp+0D0h+var_A0], r13
0x1401656d3  mov     qword ptr [rsp+0D0h+var_A8], r14
0x1401656d8  call    WPP_RECORDER_SF_qqqqL
0x1401656dd  mov     eax, esi
0x1401656df  add     rsp, 0B0h
0x1401656e6  pop     r15
0x1401656e8  pop     r14
0x1401656ea  pop     r13
0x1401656ec  pop     rsi
0x1401656ed  pop     rbp
0x1401656ee  retn
0x1401656f0  cmp     word ptr [rbx+40h], 20h ; ' '
0x1401656f5  jbe     loc_14016539C
0x1401656fb  mov     esi, 0C000000Dh
0x140165700  jmp     short loc_140165695
0x140165702  mov     rcx, cs:WPP_GLOBAL_Control
0x140165709  mov     r9d, 0Ch; int
0x14016570f  mov     qword ptr [rsp+0D0h+var_90], r15; char
0x140165714  mov     r8d, 16h; int
0x14016571a  mov     qword ptr [rsp+0D0h+var_98], rax; char
0x14016571f  lea     rax, WPP_a95b111799e83bb10d1a4a940a9bc010_Traceguids
0x140165726  mov     qword ptr [rsp+0D0h+var_A0], r13; char
0x14016572b  mov     rcx, [rcx+40h]; int
0x14016572f  mov     qword ptr [rsp+0D0h+var_A8], r14; char
0x140165734  mov     [rsp+0D0h+var_B0], rax; struct _GUID *
0x140165739  call    WPP_RECORDER_SF_qqqq
0x14016573e  mov     rax, [rbp+37h+arg_18]
0x140165742  jmp     loc_14016537E
0x140165747  mov     esi, 0C000000Dh
0x14016574c  jmp     loc_14016569D
0x140165751  mov     esi, 0C000000Dh
0x140165756  jmp     loc_140165691
0x14016575b  mov     esi, 0C000009Ah
0x140165760  jmp     loc_140165689
0x14016ea0c  movzx   eax, word ptr [rbx+10h]
0x14016ea10  dec     eax; switch 131 cases
0x14016ea12  mov     qword ptr [rdi+1Ch], 2
0x14016ea1a  mov     dword ptr [rdi+24h], 1
0x14016ea21  cmp     eax, 82h
0x14016ea26  ja      short def_14016EA43; jumptable 000000014016EA43 default case, cases 2-22,24-36,38-130
0x14016ea28  lea     rdx, cs:140000000h
0x14016ea2f  cdqe
0x14016ea31  movzx   eax, ds:(byte_1400FF709 - 140000000h)[rdx+rax]
0x14016ea39  mov     ecx, ds:(jpt_14016EA43 - 140000000h)[rdx+rax*4]
0x14016ea40  add     rcx, rdx
0x14016ea43  jmp     rcx; switch jump
0x14016ea49  mov     dword ptr [rdi+1Ch], 4; jumptable 000000014016EA43 case 37
0x14016ea50  jmp     short def_14016EA43; jumptable 000000014016EA43 default case, cases 2-22,24-36,38-130
0x14016ea52  mov     ecx, [rbx+38h]; jumptable 000000014016EA43 case 1
0x14016ea55  sub     ecx, 9
0x14016ea58  jz      short loc_14016EA6D; jumptable 000000014016EA43 case 23
0x14016ea5a  sub     ecx, 1
0x14016ea5d  jz      short loc_14016EA74; jumptable 000000014016EA43 case 131
0x14016ea5f  sub     ecx, 1
0x14016ea62  jz      loc_14016EB1A
0x14016ea68  cmp     ecx, 1
0x14016ea6b  jnz     short def_14016EA43; jumptable 000000014016EA43 default case, cases 2-22,24-36,38-130
0x14016ea6d  mov     dword ptr [rdi+24h], 3; jumptable 000000014016EA43 case 23
0x14016ea74  mov     dword ptr [rdi+1Ch], 3; jumptable 000000014016EA43 case 131
0x14016ea7b  mov     dword ptr [rdi+14h], 0FFFFFFFFh; jumptable 000000014016EA43 default case, cases 2-22,24-36,38-130
0x14016ea82  mov     dword ptr [rdi+4], 1Ch
0x14016ea89  cmp     [rbx+85h], r12b
0x14016ea90  jz      short loc_14016EA99
0x14016ea92  mov     dword ptr [rdi+4], 1Dh
0x14016ea99  cmp     [rbx+84h], r12b
0x14016eaa0  jz      short loc_14016EAA9
0x14016eaa2  mov     byte ptr [rdi+2E2h], 1
0x14016eaa9  mov     rdx, [rbx]
0x14016eaac  xor     eax, eax
0x14016eaae  mov     [rdi+2Ah], eax
0x14016eab1  mov     [rdi+2Eh], ax
0x14016eab5  mov     eax, [rbx+38h]
0x14016eab8  mov     [rdi+58h], eax
0x14016eabb  mov     eax, [rbx+3Ch]
0x14016eabe  mov     [rdi+5Ch], eax
0x14016eac1  xor     eax, eax
0x14016eac3  mov     [rdi+284h], ax
0x14016eaca  mov     [rdi+2A6h], ax
0x14016ead1  mov     [rdi+2D0h], rax
0x14016ead8  mov     [rdi+2D8h], rax
0x14016eadf  mov     [rdi+2E4h], rax
0x14016eae6  mov     [rdi+18h], r12d
0x14016eaea  mov     [rdi+28h], r12b
0x14016eaee  mov     [rdi+27Ch], r12
0x14016eaf5  mov     dword ptr [rdi+2C8h], 2
0x14016eaff  mov     dword ptr [rdi+278h], 6
0x14016eb09  movzx   eax, word ptr [rdx]
0x14016eb0c  cmp     ax, si
0x14016eb0f  jbe     short loc_14016EB26
0x14016eb11  movzx   eax, si
0x14016eb14  mov     [rdi+74h], si
0x14016eb18  jmp     short loc_14016EB2F
0x14016eb1a  mov     dword ptr [rdi+20h], 2
0x14016eb21  jmp     loc_14016EA74; jumptable 000000014016EA43 case 131
0x14016eb26  mov     [rdi+74h], ax
0x14016eb2a  test    ax, ax
0x14016eb2d  jz      short loc_14016EB40
0x14016eb2f  mov     rdx, [rdx+8]; Src
0x14016eb33  lea     rcx, [rdi+76h]; void *
0x14016eb37  movzx   r8d, ax; Size
  ... truncated ...
```
