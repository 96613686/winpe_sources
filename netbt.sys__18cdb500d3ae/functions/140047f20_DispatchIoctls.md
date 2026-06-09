# DispatchIoctls

- ea: `0x140047f20`
- end: `0x1400485e1`
- name: `DispatchIoctls`
- size: `1729`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140047d90`

## callees

- `0x140004880`
- `0x14000b2f0`
- `0x14000b810`
- `0x14000d594`
- `0x14000e408`
- `0x140014760`
- `0x140014df8`
- `0x14001b9d4`
- `0x14001c214`
- `0x14001db4c`
- `0x14001fc60`
- `0x140020424`
- `0x140021050`
- `0x140023cb4`
- `0x140024b08`
- `0x140024ed8`
- `0x140025f58`
- `0x140029c64`
- `0x14002ca6c`
- `0x14002e5a8`
- `0x14002e6fc`
- `0x140040294`
- `0x1400405d4`
- `0x140041ed0`
- `0x140047f20`
- `0x1400485e8`
- `0x1400487cc`
- `0x14004d390`
- `0x1400527ac`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004817a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004817a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048022`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048022`
- `TDI!TdiCopyBufferToMdl` at `0x14004800e`
- `TDI!TdiCopyBufferToMdl` at `0x14004800e`

## pseudocode

```c
__int64 __fastcall DispatchIoctls(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3, __int64 a4)
{
  unsigned int v4; // edi
  ULONG v5; // r12d
  NTSTATUS WinsSettings; // eax
  NTSTATUS Name; // ebx
  __int64 result; // rax
  struct _IRP *MasterIrp; // rcx
  unsigned __int64 v13; // rdx
  PMDL v14; // rax
  PMDL v15; // rcx
  unsigned int ByteCount; // ebx
  _DWORD *MappedSystemVa; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IRP *v19; // r13
  struct _IO_STACK_LOCATION *v20; // r14
  unsigned int Options; // edx
  __int64 *v22; // r8
  __int64 v23; // r13
  int v24; // edx
  __int64 v25; // r9
  NTSTATUS v26; // eax
  PMDL v27; // rax
  PMDL MdlAddress; // rax
  __int64 v29; // [rsp+40h] [rbp-40h] BYREF
  _OWORD v30[3]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v31; // [rsp+D0h] [rbp+50h] BYREF
  PVOID SourceBuffer; // [rsp+D8h] [rbp+58h] BYREF

  v4 = *(_DWORD *)(a3 + 24);
  v5 = 0;
  SourceBuffer = 0;
  LODWORD(v31) = 0;
  if ( SBYTE2(xmmword_140038420) < 0 )
    WPP_SF_qqDdZ(
      (_DWORD)DeviceObject,
      (_DWORD)Irp,
      (v4 >> 2) & 0xFFF,
      (_DWORD)DeviceObject,
      (char)Irp,
      v4,
      v4 >> 2,
      (__int64)&DeviceObject[1].Queue.Wcb.NumberOfMapRegisters);
  if ( v4 == 2162842 )
  {
    WinsSettings = NbtQueryWinsSettings(DeviceObject, Irp);
LABEL_5:
    Name = WinsSettings;
LABEL_6:
    if ( SBYTE2(xmmword_140038420) < 0 )
      WPP_SF_qqD(1047, 50, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, DeviceObject, Irp, Name);
    if ( (Name & 0xC0000000) != 0xC0000000 && ((v4 - 2162814) & 0xFFFFFFF3) == 0 && v4 != 2162826 )
    {
      Name = TdiCopyBufferToMdl(SourceBuffer, 0, v5, Irp->MdlAddress, 0, (PULONG)&Irp->IoStatus.Information);
      ExFreePoolWithTag(SourceBuffer, 0);
    }
    if ( Name != 259 )
      NTIoComplete(Irp);
    return (unsigned int)Name;
  }
  if ( v4 == 2212076 )
    return NbtProcessTcpDirectQuery(Irp);
  if ( v4 <= 0x2180E0 )
  {
    if ( v4 != 2195680 )
    {
      if ( v4 > 0x2100D6 )
      {
        v13 = 0x140000000uLL;
        switch ( v4 )
        {
          case 0x218078u:
            DelayedNbtResyncRemoteCache();
            Name = 0;
            goto LABEL_6;
          case 0x218088u:
            WinsSettings = NTReReadRegistry(DeviceObject, 0);
            goto LABEL_5;
          case 0x2180C4u:
          case 0x2180C8u:
            WinsSettings = NbtSetExtendedAddress(DeviceObject, a3, v4);
            goto LABEL_5;
          case 0x2180CCu:
            LOBYTE(v13) = 1;
            dword_14003962C = 196611;
            WinsSettings = ReRegisterLocalNames(0, v13);
            goto LABEL_5;
          case 0x2180D0u:
            v5 = *(_DWORD *)(a3 + 16);
            if ( v5 >= 0x1C )
            {
              WinsSettings = NbtAddEntryToRemoteHashTable(
                               (_DWORD)DeviceObject,
                               2,
                               Irp->AssociatedIrp.MasterIrp,
                               *(&Irp->AssociatedIrp.MasterIrp->Flags + 1),
                               Irp->AssociatedIrp.MasterIrp->AssociatedIrp.IrpCount,
                               BYTE1(Irp->AssociatedIrp.MasterIrp->Flags));
              goto LABEL_5;
            }
            if ( (BYTE3(xmmword_140038420) & 1) != 0 )
              WPP_SF_(1048, 48, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids);
            Name = -1073741789;
            break;
          default:
            goto LABEL_88;
        }
        goto LABEL_6;
      }
      if ( v4 != 2162902 )
      {
        Name = -1073741823;
        switch ( v4 )
        {
          case 0x21007Eu:
            MdlAddress = Irp->MdlAddress;
            if ( !MdlAddress )
              goto LABEL_6;
            LODWORD(v31) = MdlAddress->ByteCount;
            WinsSettings = NbtQueryBcastVsWins(DeviceObject, &SourceBuffer, &v31);
            v5 = v31;
            goto LABEL_5;
          case 0x210082u:
            v14 = Irp->MdlAddress;
            if ( !v14 )
              goto LABEL_6;
            LODWORD(v31) = v14->ByteCount;
            WinsSettings = NbtQueryConnectionList(DeviceObject, &SourceBuffer, &v31);
            v5 = v31;
            goto LABEL_5;
          case 0x210086u:
            v27 = Irp->MdlAddress;
            if ( !v27 )
              goto LABEL_6;
            LODWORD(v31) = v27->ByteCount;
            WinsSettings = NbtQueryAdapterStatus(DeviceObject, &SourceBuffer, &v31, 1);
            v5 = v31;
            goto LABEL_5;
          case 0x210096u:
            Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
            if ( Irp->MdlAddress )
            {
              MasterIrp = Irp->AssociatedIrp.MasterIrp;
              if ( MasterIrp )
              {
                if ( *(_DWORD *)(a3 + 16) >= 0x18u )
                {
                  LOBYTE(a4) = 1;
                  Name = NbtQueryFindName(MasterIrp, DeviceObject, Irp, a4);
                  if ( Name == 259 )
                    return 259;
                }
              }
            }
            *(_BYTE *)(a3 + 3) &= ~1u;
            goto LABEL_6;
          case 0x2100A6u:
            WinsSettings = GetIpAddrs(DeviceObject, Irp);
            goto LABEL_5;
          case 0x2100AAu:
            v15 = Irp->MdlAddress;
            if ( v15 )
            {
              ByteCount = v15->ByteCount;
              if ( ByteCount < 8 )
              {
                Name = -2147483643;
              }
              else
              {
                if ( (v15->MdlFlags & 5) != 0 )
                  MappedSystemVa = v15->MappedSystemVa;
                else
                  MappedSystemVa = MmMapLockedPagesSpecifyCache(v15, 0, MmCached, 0, 0, 0x40000010u);
                if ( MappedSystemVa )
                {
                  *MappedSystemVa = DeviceObject[1].AlignmentRequirement;
                  MappedSystemVa[1] = *(&DeviceObject[1].AlignmentRequirement + 1);
                  if ( ByteCount >= 0xC )
                    MappedSystemVa[2] = DeviceObject[1].ReferenceCount;
                  Name = 0;
                }
                else
                {
                  Name = -1073741670;
                }
              }
            }
            goto LABEL_6;
          case 0x2100AEu:
            if ( !Irp->MdlAddress )
              goto LABEL_6;
            CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
            v29 = 0;
            CurrentStackLocation->Control |= 1u;
            v19 = Irp->AssociatedIrp.MasterIrp;
            v20 = Irp->Tail.Overlay.CurrentStackLocation;
            if ( !v19 )
              goto LABEL_46;
            Options = v20->Parameters.Create.Options;
            if ( Options < 0x20 )
              goto LABEL_46;
            memset(v30, 0, 44);
            Name = GetNetBiosNameFromTransportAddress(&v19->Size + 1, Options - 4, v30);
            if ( Name < 0 )
              goto LABEL_46;
            if ( LOWORD(v30[0]) || WORD2(v30[1]) != 16 )
            {
              Name = -1073741811;
            }
            else if ( DeviceObject[2].DeviceQueue.Busy )
            {
              if ( **(_BYTE **)((char *)&v30[1] + 12) != 42 || *(_DWORD *)&v19->Type )
              {
                Name = GetTracker(&v29, 18);
                if ( Name >= 0 )
                {
                  LODWORD(v22) = 0;
                  if ( *(_DWORD *)&v19->Type )
                  {
                    v22 = &v31;
                    v31 = *(unsigned int *)&v19->Type;
                  }
                  v23 = v29;
                  v24 = HIDWORD(v30[1]);
                  v25 = v29;
                  *(_QWORD *)(v29 + 176) = Irp;
                  *(_QWORD *)(v25 + 32) = DeviceObject;
                  v26 = NbtSendNodeStatus(
                          (_DWORD)DeviceObject,
                          v24,
                          (_DWORD)v22,
                          v25,
                          (__int64)CopyNodeStatusResponseCompletion);
                  Name = v26;
                  if ( v26 == 259 )
                    return 259;
                  if ( !v26 )
                    Name = -1073741823;
                  FreeTracker(v23, 4);
                  v20->Control &= ~1u;
                  goto LABEL_6;
                }
              }
              else
              {
                Name = -1073741634;
              }
            }
            else
            {
              Name = -1073741436;
            }
LABEL_46:
            v20->Control &= ~1u;
            goto LABEL_6;
          default:
            goto LABEL_88;
        }
      }
      WinsSettings = NbtGetInterfaceInfo(Irp);
      goto LABEL_5;
    }
    v5 = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options;
    if ( v5 >= 0x10 )
    {
      WinsSettings = NbtFlushEntryFromRemoteHashTable(Irp->AssociatedIrp.MasterIrp);
      goto LABEL_5;
    }
    if ( (BYTE3(xmmword_140038420) & 1) != 0 )
      WPP_SF_(1048, 49, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids);
LABEL_88:
    Name = -1073741811;
    goto LABEL_6;
  }
  if ( v4 <= 0x21C08C )
  {
    if ( v4 == 2211980 || v4 == 2195696 )
    {
LABEL_91:
      result = NbtDispatchClusterIoctl(DeviceObject, Irp, (__int64)&v31);
      Name = result;
      if ( (_DWORD)v31 )
        return result;
      goto LABEL_6;
    }
    goto LABEL_88;
  }
  switch ( v4 )
  {
    case 0x21C092u:
    case 0x21C0B2u:
      result = NbtDispatchLmHostsIoctl((_DWORD)DeviceObject, (_DWORD)Irp, a3, v4, (__int64)&v31);
      Name = result;
      if ( !(_DWORD)v31 )
        goto LABEL_6;
      break;
    case 0x21C09Eu:
    case 0x21C0A2u:
    case 0x21C0E4u:
      result = NbtDispatchWinsServerIoctl(DeviceObject, Irp, a3, v4, &v31);
      Name = result;
      if ( !(_DWORD)v31 )
        goto LABEL_6;
      break;
    case 0x21C0B4u:
    case 0x21C0B8u:
    case 0x21C0BCu:
    case 0x21C0C0u:
      goto LABEL_91;
    case 0x21C0D8u:
      WinsSettings = NbtClientSetTcpInfo(
                       *(_QWORD *)(*(_QWORD *)(a3 + 48) + 24LL),
                       Irp->AssociatedIrp.MasterIrp,
                       *(unsigned int *)(a3 + 16));
      goto LABEL_5;
    case 0x21C0DCu:
      WinsSettings = NbtSetSmbBindingInfo(DeviceObject, Irp, a3);
      goto LABEL_5;
    case 0x21C0E8u:
      WinsSettings = NbtProcessIoControlEndpoint(Irp, a3);
      goto LABEL_5;
    default:
      goto LABEL_88;
  }
  return result;
}

```

## disassembly

```asm
0x140047f20  push    rbp
0x140047f22  push    rsi
0x140047f23  push    rdi
0x140047f24  push    r12
0x140047f26  push    r13
0x140047f28  push    r14
0x140047f2a  push    r15
0x140047f2c  mov     rbp, rsp
0x140047f2f  sub     rsp, 80h
0x140047f36  mov     edi, [r8+18h]
0x140047f3a  xor     r13d, r13d
0x140047f3d  mov     r12d, r13d
0x140047f40  mov     [rbp+SourceBuffer], r13
0x140047f44  mov     dword ptr [rbp+arg_10], r13d
0x140047f48  mov     r14, r8
0x140047f4b  mov     rsi, rdx
0x140047f4e  mov     r15, rcx
0x140047f51  cmp     byte ptr cs:xmmword_140038420+2, r13b
0x140047f58  jl      loc_14004839B
0x140047f5e  mov     [rsp+80h+arg_0], rbx
0x140047f66  cmp     edi, 21009Ah
0x140047f6c  jnz     short loc_140047FD6
0x140047f6e  mov     rdx, rsi
0x140047f71  mov     rcx, r15
0x140047f74  call    NbtQueryWinsSettings
0x140047f79  mov     ebx, eax
0x140047f7b  cmp     byte ptr cs:xmmword_140038420+2, 0
0x140047f82  jl      loc_1400485BA
0x140047f88  mov     eax, ebx
0x140047f8a  and     eax, 0C0000000h
0x140047f8f  cmp     eax, 0C0000000h
0x140047f94  jz      short loc_140047FA3
0x140047f96  lea     eax, [rdi-21007Eh]
0x140047f9c  test    eax, 0FFFFFFF3h
0x140047fa1  jz      short loc_140047FEB
0x140047fa3  cmp     ebx, 103h
0x140047fa9  jz      short loc_140047FB8
0x140047fab  xor     r8d, r8d
0x140047fae  mov     edx, ebx
0x140047fb0  mov     rcx, rsi; Irp
0x140047fb3  call    NTIoComplete
0x140047fb8  mov     eax, ebx
0x140047fba  mov     rbx, [rsp+80h+arg_0]
0x140047fc2  add     rsp, 80h
0x140047fc9  pop     r15
0x140047fcb  pop     r14
0x140047fcd  pop     r13
0x140047fcf  pop     r12
0x140047fd1  pop     rdi
0x140047fd2  pop     rsi
0x140047fd3  pop     rbp
0x140047fd4  retn
0x140047fd6  cmp     edi, 21C0ECh
0x140047fdc  jnz     short loc_140048033
0x140047fde  mov     rdx, r14
0x140047fe1  mov     rcx, rsi; Irp
0x140047fe4  call    NbtProcessTcpDirectQuery
0x140047fe9  jmp     short loc_140047FBA
0x140047feb  cmp     edi, 21008Ah
0x140047ff1  jz      short loc_140047FA3
0x140047ff3  mov     r9, [rsi+8]; DestinationMdlChain
0x140047ff7  lea     rax, [rsi+38h]
0x140047ffb  mov     rcx, [rbp+SourceBuffer]; SourceBuffer
0x140047fff  mov     r8d, r12d; SourceBytesToCopy
0x140048002  mov     [rsp+80h+BytesCopied], rax; BytesCopied
0x140048007  xor     edx, edx; SourceOffset
0x140048009  mov     [rsp+80h+DestinationOffset], r13d; DestinationOffset
0x14004800e  call    cs:__imp_TdiCopyBufferToMdl
0x140048015  nop     dword ptr [rax+rax+00h]
0x14004801a  mov     rcx, [rbp+SourceBuffer]; P
0x14004801e  xor     edx, edx; Tag
0x140048020  mov     ebx, eax
0x140048022  call    cs:__imp_ExFreePoolWithTag
0x140048029  nop     dword ptr [rax+rax+00h]
0x14004802e  jmp     loc_140047FA3
0x140048033  cmp     edi, 2180E0h
0x140048039  ja      loc_140048199
0x14004803f  jz      loc_1400484FF
0x140048045  cmp     edi, 2100D6h
0x14004804b  ja      loc_1400480D6
0x140048051  jz      loc_14004847C
0x140048057  lea     eax, [rdi-21007Eh]; switch 49 cases
0x14004805d  cmp     eax, 30h
0x140048060  ja      def_140048084; jumptable 0000000140048084 default case, cases 2162815-2162817,2162819-2162821,2162823-2162837,2162839-2162853,2162855-2162857,2162859-2162861
0x140048066  lea     rdx, cs:140000000h
0x14004806d  mov     ebx, 0C0000001h
0x140048072  movzx   eax, ds:(byte_140034720 - 140000000h)[rdx+rax]
0x14004807a  mov     ecx, ds:(jpt_140048084 - 140000000h)[rdx+rax*4]
0x140048081  add     rcx, rdx
0x140048084  jmp     rcx; switch jump
0x14004808a  mov     rax, [rsi+0B8h]; jumptable 0000000140048084 case 2162838
0x140048091  or      byte ptr [rax+3], 1
0x140048095  cmp     [rsi+8], r12
0x140048099  jz      short loc_1400480CC
0x14004809b  mov     rcx, [rsi+18h]
0x14004809f  test    rcx, rcx
0x1400480a2  jz      short loc_1400480CC
0x1400480a4  cmp     dword ptr [r14+10h], 18h
0x1400480a9  jb      short loc_1400480CC
0x1400480ab  mov     r9b, 1
0x1400480ae  mov     r8, rsi
0x1400480b1  mov     rdx, r15
0x1400480b4  call    NbtQueryFindName
0x1400480b9  mov     ebx, eax
0x1400480bb  cmp     eax, 103h
0x1400480c0  jnz     short loc_1400480CC
0x1400480c2  mov     eax, 103h
0x1400480c7  jmp     loc_140047FBA
0x1400480cc  and     byte ptr [r14+3], 0FEh
0x1400480d1  jmp     loc_140047F7B
0x1400480d6  lea     eax, [rdi-218078h]; switch 89 cases
0x1400480dc  cmp     eax, 58h
0x1400480df  ja      def_140048084; jumptable 0000000140048084 default case, cases 2162815-2162817,2162819-2162821,2162823-2162837,2162839-2162853,2162855-2162857,2162859-2162861
0x1400480e5  lea     rdx, cs:140000000h
0x1400480ec  movzx   eax, ds:(byte_140034769 - 140000000h)[rdx+rax]
0x1400480f4  mov     ecx, ds:(jpt_1400480FE - 140000000h)[rdx+rax*4]
0x1400480fb  add     rcx, rdx
0x1400480fe  jmp     rcx; switch jump
0x140048104  xor     edx, edx; jumptable 00000001400480FE case 2195592
0x140048106  mov     rcx, r15
0x140048109  call    NTReReadRegistry
0x14004810e  jmp     loc_140047F79
0x140048113  mov     rax, [rsi+8]; jumptable 0000000140048084 case 2162818
0x140048117  test    rax, rax
0x14004811a  jz      loc_140047F7B
0x140048120  mov     eax, [rax+28h]
0x140048123  lea     r8, [rbp+arg_10]
0x140048127  lea     rdx, [rbp+SourceBuffer]
0x14004812b  mov     dword ptr [rbp+arg_10], eax
0x14004812e  mov     rcx, r15
0x140048131  call    NbtQueryConnectionList
0x140048136  mov     r12d, dword ptr [rbp+arg_10]
0x14004813a  jmp     loc_140047F79
0x14004813f  mov     rcx, [rsi+8]; jumptable 0000000140048084 case 2162858
0x140048143  test    rcx, rcx
0x140048146  jz      loc_140047F7B
0x14004814c  mov     ebx, [rcx+28h]
0x14004814f  cmp     ebx, 8
0x140048152  jb      loc_1400483E0
0x140048158  test    byte ptr [rcx+0Ah], 5
0x14004815c  jnz     loc_1400482A3
0x140048162  mov     dword ptr [rsp+80h+BytesCopied], 40000010h; Priority
0x14004816a  xor     r9d, r9d; RequestedAddress
0x14004816d  xor     edx, edx; AccessMode
0x14004816f  mov     [rsp+80h+DestinationOffset], r13d; BugCheckOnFailure
0x140048174  mov     r8d, 1; CacheType
0x14004817a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140048181  nop     dword ptr [rax+rax+00h]
0x140048186  test    rax, rax
0x140048189  jnz     loc_14004823E
0x14004818f  mov     ebx, 0C000009Ah
0x140048194  jmp     loc_140047F7B
0x140048199  cmp     edi, 21C08Ch
0x14004819f  jbe     loc_140048547
0x1400481a5  lea     eax, [rdi-21C092h]; switch 87 cases
0x1400481ab  cmp     eax, 56h
0x1400481ae  ja      def_140048084; jumptable 0000000140048084 default case, cases 2162815-2162817,2162819-2162821,2162823-2162837,2162839-2162853,2162855-2162857,2162859-2162861
0x1400481b4  lea     rdx, cs:140000000h
0x1400481bb  movzx   eax, ds:(byte_1400347DE - 140000000h)[rdx+rax]
0x1400481c3  mov     ecx, ds:(jpt_1400481CD - 140000000h)[rdx+rax*4]
0x1400481ca  add     rcx, rdx
0x1400481cd  jmp     rcx; switch jump
0x1400481d3  lea     rax, [rbp+arg_10]; jumptable 00000001400481CD cases 2211986,2212018
0x1400481d7  mov     r9d, edi
0x1400481da  mov     rdx, rsi
0x1400481dd  mov     qword ptr [rsp+80h+DestinationOffset], rax
0x1400481e2  call    NbtDispatchLmHostsIoctl
0x1400481e7  mov     ebx, eax
0x1400481e9  cmp     dword ptr [rbp+arg_10], r12d
0x1400481ed  jnz     loc_140047FBA
0x1400481f3  jmp     loc_140047F7B
0x1400481f8  mov     r8d, edi; jumptable 00000001400480FE cases 2195652,2195656
0x1400481fb  mov     rdx, r14
0x1400481fe  call    NbtSetExtendedAddress
0x140048203  jmp     loc_140047F79
0x140048208  cmp     [rsi+8], r12; jumptable 0000000140048084 case 2162862
0x14004820c  jz      loc_140047F7B
0x140048212  mov     rax, [rsi+0B8h]
0x140048219  mov     [rbp+var_40], r13
0x14004821d  or      byte ptr [rax+3], 1
0x140048221  mov     r13, [rsi+18h]
0x140048225  mov     r14, [rsi+0B8h]
0x14004822c  test    r13, r13
0x14004822f  jnz     short loc_1400482AC
0x140048231  and     byte ptr [r14+3], 0FEh
0x140048236  xor     r13d, r13d
0x140048239  jmp     loc_140047F7B
0x14004823e  mov     ecx, [r15+1E8h]
0x140048245  mov     [rax], ecx
0x140048247  mov     ecx, [r15+1ECh]
0x14004824e  mov     [rax+4], ecx
0x140048251  cmp     ebx, 0Ch
0x140048254  jnb     loc_1400483EA
0x14004825a  mov     ebx, r13d
0x14004825d  jmp     loc_140047F7B
0x140048262  xor     r9d, r9d; jumptable 00000001400480FE case 2195576
0x140048265  xor     r8d, r8d
0x140048268  xor     edx, edx
0x14004826a  xor     ecx, ecx
0x14004826c  call    DelayedNbtResyncRemoteCache
0x140048271  mov     ebx, r13d
0x140048274  jmp     loc_140047F7B
0x140048279  mov     rcx, [r14+30h]; jumptable 00000001400481CD case 2212056
0x14004827d  mov     r8d, [r14+10h]
0x140048281  mov     rdx, [rsi+18h]
0x140048285  mov     rcx, [rcx+18h]
0x140048289  call    NbtClientSetTcpInfo
0x14004828e  jmp     loc_140047F79
0x140048293  mov     rdx, r14; jumptable 00000001400481CD case 2212072
0x140048296  mov     rcx, rsi
0x140048299  call    NbtProcessIoControlEndpoint
0x14004829e  jmp     loc_140047F79
0x1400482a3  mov     rax, [rcx+18h]
0x1400482a7  jmp     loc_140048186
0x1400482ac  mov     edx, [r14+10h]
0x1400482b0  cmp     edx, 20h ; ' '
0x1400482b3  jb      loc_140048231
0x1400482b9  xorps   xmm0, xmm0
0x1400482bc  lea     rcx, [r13+4]
0x1400482c0  movups  xmmword ptr [rbp+var_28], xmm0
0x1400482c4  add     edx, 0FFFFFFFCh
0x1400482c7  lea     r8, [rbp+var_38]
0x1400482cb  movups  xmmword ptr [rbp+var_28+0Ch], xmm0
0x1400482cf  movups  [rbp+var_38], xmm0
0x1400482d3  call    GetNetBiosNameFromTransportAddress
0x1400482d8  mov     ebx, eax
0x1400482da  test    eax, eax
0x1400482dc  js      loc_140048231
0x1400482e2  cmp     word ptr [rbp+var_38], r12w
0x1400482e7  jnz     loc_140048417
0x1400482ed  cmp     word ptr [rbp+var_28+4], 10h
0x1400482f2  jnz     loc_140048417
0x1400482f8  cmp     [r15+360h], r12b
0x1400482ff  jz      loc_1400483F9
0x140048305  mov     rax, qword ptr [rbp+var_28+0Ch]
0x140048309  cmp     byte ptr [rax], 2Ah ; '*'
0x14004830c  jz      loc_140048403
0x140048312  mov     edx, 12h
0x140048317  lea     rcx, [rbp+var_40]
0x14004831b  call    GetTracker
0x140048320  mov     ebx, eax
0x140048322  test    eax, eax
0x140048324  js      loc_140048231
0x14004832a  mov     eax, [r13+0]
0x14004832e  xor     r8d, r8d
0x140048331  test    eax, eax
0x140048333  jz      short loc_140048340
0x140048335  mov     dword ptr [rbp+arg_10+4], r8d
0x140048339  lea     r8, [rbp+arg_10]
0x14004833d  mov     dword ptr [rbp+arg_10], eax
0x140048340  mov     r13, [rbp+var_40]
0x140048344  lea     rax, CopyNodeStatusResponseCompletion
0x14004834b  mov     rdx, qword ptr [rbp+var_28+0Ch]
0x14004834f  mov     r9, r13
0x140048352  mov     rcx, r15
0x140048355  mov     qword ptr [rsp+80h+DestinationOffset], rax
0x14004835a  mov     [r13+0B0h], rsi
0x140048361  mov     [r13+20h], r15
0x140048365  call    NbtSendNodeStatus
0x14004836a  mov     ebx, eax
0x14004836c  cmp     eax, 103h
0x140048371  jz      loc_1400480C2
0x140048377  test    eax, eax
0x140048379  mov     edx, 4
0x14004837e  mov     eax, 0C0000001h
0x140048383  mov     rcx, r13
0x140048386  cmovz   ebx, eax
0x140048389  call    FreeTracker
0x14004838e  and     byte ptr [r14+3], 0FEh
0x140048393  xor     r13d, r13d
0x140048396  jmp     loc_140047F7B
0x14004839b  mov     r8d, edi
0x14004839e  lea     rax, [rcx+1C8h]
0x1400483a5  mov     [rsp+80h+var_48], rax
0x1400483aa  mov     r9, r15
0x1400483ad  shr     r8d, 2
0x1400483b1  and     r8d, 0FFFh
0x1400483b8  mov     [rsp+80h+var_50], r8d
0x1400483bd  mov     dword ptr [rsp+80h+BytesCopied], edi
0x1400483c1  mov     qword ptr [rsp+80h+DestinationOffset], rsi
0x1400483c6  call    WPP_SF_qqDdZ
0x1400483cb  jmp     loc_140047F5E
0x1400483d0  mov     rdx, rsi; jumptable 0000000140048084 case 2162854
0x1400483d3  mov     rcx, r15
0x1400483d6  call    GetIpAddrs
0x1400483db  jmp     loc_140047F79
0x1400483e0  mov     ebx, 80000005h
0x1400483e5  jmp     loc_140047F7B
0x1400483ea  mov     ecx, [r15+154h]
0x1400483f1  mov     [rax+8], ecx
0x1400483f4  jmp     loc_14004825A
0x1400483f9  mov     ebx, 0C0000184h
0x1400483fe  jmp     loc_140048231
0x140048403  cmp     [r13+0], r12d
0x140048407  jnz     loc_140048312
0x14004840d  mov     ebx, 0C00000BEh
0x140048412  jmp     loc_140048231
0x140048417  mov     ebx, 0C000000Dh
0x14004841c  jmp     loc_140048231
0x140048421  mov     rax, [rsi+8]; jumptable 0000000140048084 case 2162822
  ... truncated ...
```
