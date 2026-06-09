# RxNotifyChangeDirectory

- ea: `0x140068e90`
- end: `0x140069182`
- name: `RxNotifyChangeDirectory`
- size: `754`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, PMRX_FCB MrxFcb)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140068330`

## callees

- `0x140009b80`
- `0x140016d40`
- `0x140016e20`
- `0x140016e70`
- `0x140017280`
- `0x140057660`
- `0x140067ad0`
- `0x140068070`
- `0x140068e90`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140068f53`
- `ntoskrnl!KeInitializeEvent` at `0x140068f53`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140068fd3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140068fd3`

## string_xrefs

- `0x14007b2a2`: `RxNotifyChangeDirectory`

## pseudocode

```c
__int64 __fastcall RxNotifyChangeDirectory(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb, __int64 a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  __int64 result; // rax
  ULONG Options; // ecx
  PMDL MdlAddress; // rcx
  PVOID MappedSystemVa; // rdx
  _QWORD *v13; // rax
  unsigned int v14; // ebx
  ULONG v15; // r8d
  PCSTR v16; // r9
  struct _IRP *MasterIrp; // rcx
  const CHAR *BugCheckOnFailure; // [rsp+20h] [rbp-58h]
  ULONG BugCheckOnFailurea; // [rsp+20h] [rbp-58h]
  ULONG Priority; // [rsp+28h] [rbp-50h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids,
      (__int64)RxContext->RdbssDbgExtension & 2);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids, Irp);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      30,
      &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids,
      CurrentStackLocation->Parameters.Create.Options);
  }
  *(_BYTE *)(a4 + 147) = 1;
  result = *(unsigned int *)(a4 + 268);
  if ( ((int)result <= -1 || (unsigned int)(result - 267) <= 1) && (_DWORD)result == *(_DWORD *)(a4 + 264) )
  {
    *(_DWORD *)(a4 + 268) = 0;
  }
  else
  {
    LODWORD(RxContext->RdbssDbgExtension) |= 2u;
    KeInitializeEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType, NotificationEvent, 0);
    *((_WORD *)&RxContext->9 + 60) = 8;
    Options = CurrentStackLocation->Parameters.Create.Options;
    *((_BYTE *)&RxContext->9 + 136) = CurrentStackLocation->Flags & 1;
    *((_DWORD *)&RxContext->9 + 35) = Options;
    *((_DWORD *)&RxContext->9 + 36) = CurrentStackLocation->Parameters.Read.Length;
    if ( Irp->UserBuffer || (MasterIrp = Irp->AssociatedIrp.MasterIrp) == 0 )
    {
      RxLockUserBuffer(RxContext, Irp, IoWriteAccess, CurrentStackLocation->Parameters.Read.Length);
      MdlAddress = Irp->MdlAddress;
      if ( MdlAddress )
      {
        if ( (MdlAddress->MdlFlags & 5) != 0 )
          MappedSystemVa = MdlAddress->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
        v13 = (_QWORD *)((char *)&RxContext->9 + 152);
        *((_QWORD *)&RxContext->9 + 19) = MappedSystemVa;
      }
      else
      {
        v13 = (_QWORD *)((char *)&RxContext->9 + 152);
      }
    }
    else
    {
      v13 = (_QWORD *)((char *)&RxContext->9 + 152);
      *((_QWORD *)&RxContext->9 + 19) = MasterIrp;
    }
    if ( *v13 )
    {
      _RxAcquireFcb(MrxFcb, 0, 1u, 0, BugCheckOnFailure, Priority);
      v14 = RxLowIoSubmit(RxContext, Irp, MrxFcb, RxLowIoNotifyChangeDirectoryCompletion);
      _RxReleaseFcb(0, (PMRX_FCB)&MrxFcb->Header, v15, v16, BugCheckOnFailurea);
    }
    else
    {
      v14 = -1073741670;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids, v14);
    }
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x140068e90  push    rbx
0x140068e92  push    rsi
0x140068e93  push    rdi
0x140068e94  push    r12
0x140068e96  push    r13
0x140068e98  push    r14
0x140068e9a  push    r15
0x140068e9c  sub     rsp, 40h
0x140068ea0  mov     rbx, r9
0x140068ea3  mov     r12, r8
0x140068ea6  mov     rsi, rdx
0x140068ea9  mov     rdi, rcx
0x140068eac  mov     r15, [rdx+0B8h]
0x140068eb3  lea     r13, WPP_GLOBAL_Control
0x140068eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ec1  cmp     rcx, r13
0x140068ec4  jz      short loc_140068ED1
0x140068ec6  mov     eax, [rcx+2Ch]
0x140068ec9  test    al, 2
0x140068ecb  jnz     loc_1400690BC
0x140068ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ed8  cmp     rcx, r13
0x140068edb  jz      short loc_140068EE8
0x140068edd  mov     eax, [rcx+2Ch]
0x140068ee0  test    al, 2
0x140068ee2  jnz     loc_1400690E0
0x140068ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x140068eef  cmp     rcx, r13
0x140068ef2  jz      short loc_140068EFF
0x140068ef4  mov     eax, [rcx+2Ch]
0x140068ef7  test    al, 2
0x140068ef9  jnz     loc_14006910C
0x140068eff  mov     rcx, cs:WPP_GLOBAL_Control
0x140068f06  cmp     rcx, r13
0x140068f09  jz      short loc_140068F16
0x140068f0b  mov     eax, [rcx+2Ch]
0x140068f0e  test    al, 2
0x140068f10  jnz     loc_140069133
0x140068f16  mov     byte ptr [rbx+93h], 1
0x140068f1d  mov     eax, [rbx+10Ch]
0x140068f23  cmp     eax, 0FFFFFFFFh
0x140068f26  jle     loc_140069095
0x140068f2c  lea     ecx, [rax-10Bh]
0x140068f32  cmp     ecx, 1
0x140068f35  jbe     loc_140069095
0x140068f3b  xor     r14d, r14d
0x140068f3e  mov     [rsp+78h+var_48], r14d
0x140068f43  or      dword ptr [rdi+78h], 2
0x140068f47  lea     rcx, [rdi+180h]; Event
0x140068f4e  xor     r8d, r8d; State
0x140068f51  xor     edx, edx; Type
0x140068f53  call    cs:__imp_KeInitializeEvent
0x140068f5a  nop     dword ptr [rax+rax+00h]
0x140068f5f  mov     word ptr [rdi+208h], 8
0x140068f68  mov     ecx, [r15+10h]
0x140068f6c  movzx   eax, byte ptr [r15+2]
0x140068f71  and     al, 1
0x140068f73  mov     [rdi+218h], al
0x140068f79  mov     [rdi+21Ch], ecx
0x140068f7f  mov     eax, [r15+8]
0x140068f83  mov     [rdi+220h], eax
0x140068f89  cmp     [rsi+70h], r14
0x140068f8d  jz      loc_140069041
0x140068f93  mov     r9d, [r15+8]; BufferLength
0x140068f97  mov     r8d, 1; Operation
0x140068f9d  mov     rdx, rsi; Irp
0x140068fa0  mov     rcx, rdi; RxContext
0x140068fa3  call    RxLockUserBuffer
0x140068fa8  mov     rcx, [rsi+8]; MemoryDescriptorList
0x140068fac  test    rcx, rcx
0x140068faf  jz      loc_14006905A
0x140068fb5  test    byte ptr [rcx+0Ah], 5
0x140068fb9  jnz     short loc_140069030
0x140068fbb  mov     [rsp+78h+Priority], 40000010h; SerialNumber
0x140068fc3  mov     dword ptr [rsp+78h+BugCheckOnFailure], r14d; SerialNumber
0x140068fc8  xor     r9d, r9d; RequestedAddress
0x140068fcb  xor     edx, edx; AccessMode
0x140068fcd  mov     r8d, 1; CacheType
0x140068fd3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140068fda  nop     dword ptr [rax+rax+00h]
0x140068fdf  mov     rdx, rax
0x140068fe2  lea     rax, [rdi+228h]
0x140068fe9  mov     [rax], rdx
0x140068fec  cmp     qword ptr [rax], 0
0x140068ff0  jz      short loc_140069036
0x140068ff2  xor     r9d, r9d; LineNumber
0x140068ff5  xor     edx, edx; RxContext
0x140068ff7  mov     r8d, 1; Mode
0x140068ffd  mov     rcx, r12; Fcb
0x140069000  call    __RxAcquireFcb
0x140069005  mov     [rsp+78h+var_48], eax
0x140069009  lea     r9, RxLowIoNotifyChangeDirectoryCompletion; CompletionRoutine
0x140069010  mov     r8, r12; Fcb
0x140069013  mov     rdx, rsi; Irp
0x140069016  mov     rcx, rdi; RxContext
0x140069019  call    RxLowIoSubmit
0x14006901e  mov     ebx, eax
0x140069020  mov     [rsp+78h+var_48], eax
0x140069024  mov     rdx, r12; MrxFcb
0x140069027  xor     ecx, ecx; RxContext
0x140069029  call    __RxReleaseFcb
0x14006902e  jmp     short loc_14006906B
0x140069030  mov     rdx, [rcx+18h]
0x140069034  jmp     short loc_140068FE2
0x140069036  mov     ebx, 0C000009Ah
0x14006903b  mov     [rsp+78h+var_48], ebx
0x14006903f  jmp     short loc_14006906B
0x140069041  mov     rcx, [rsi+18h]
0x140069045  test    rcx, rcx
0x140069048  jz      loc_140068F93
0x14006904e  lea     rax, [rdi+228h]
0x140069055  mov     [rax], rcx
0x140069058  jmp     short loc_140068FEC
0x14006905a  mov     [rsp+78h+var_48], 0C000000Dh
0x140069062  lea     rax, [rdi+228h]
0x140069069  jmp     short loc_140068FEC
0x14006906b  mov     rcx, cs:WPP_GLOBAL_Control
0x140069072  cmp     rcx, r13
0x140069075  jz      short loc_140069082
0x140069077  mov     eax, [rcx+2Ch]
0x14006907a  test    al, 2
0x14006907c  jnz     loc_14006915B
0x140069082  mov     eax, ebx
0x140069084  add     rsp, 40h
0x140069088  pop     r15
0x14006908a  pop     r14
0x14006908c  pop     r13
0x14006908e  pop     r12
0x140069090  pop     rdi
0x140069091  pop     rsi
0x140069092  pop     rbx
0x140069093  retn
0x140069095  cmp     eax, [rbx+108h]
0x14006909b  jnz     loc_140068F3B
0x1400690a1  xor     r14d, r14d
0x1400690a4  mov     [rbx+10Ch], r14d
0x1400690ab  add     rsp, 40h
0x1400690af  pop     r15
0x1400690b1  pop     r14
0x1400690b3  pop     r13
0x1400690b5  pop     r12
0x1400690b7  pop     rdi
0x1400690b8  pop     rsi
0x1400690b9  pop     rbx
0x1400690ba  retn
0x1400690bc  cmp     byte ptr [rcx+29h], 4
0x1400690c0  jb      loc_140068ED1
0x1400690c6  mov     edx, 1Bh
0x1400690cb  lea     r8, WPP_ac55395600da34284848d4e5839e1eb6_Traceguids
0x1400690d2  mov     rcx, [rcx+18h]
0x1400690d6  call    WPP_SF_
0x1400690db  jmp     loc_140068ED1
0x1400690e0  cmp     byte ptr [rcx+29h], 4
0x1400690e4  jb      loc_140068EE8
0x1400690ea  mov     r9d, [rdi+78h]
0x1400690ee  and     r9d, 2
0x1400690f2  mov     edx, 1Ch
0x1400690f7  lea     r8, WPP_ac55395600da34284848d4e5839e1eb6_Traceguids
0x1400690fe  mov     rcx, [rcx+18h]
0x140069102  call    WPP_SF_d
0x140069107  jmp     loc_140068EE8
0x14006910c  cmp     byte ptr [rcx+29h], 4
0x140069110  jb      loc_140068EFF
0x140069116  mov     edx, 1Dh
0x14006911b  mov     r9, rsi
0x14006911e  lea     r8, WPP_ac55395600da34284848d4e5839e1eb6_Traceguids
0x140069125  mov     rcx, [rcx+18h]
0x140069129  call    WPP_SF_q
0x14006912e  jmp     loc_140068EFF
0x140069133  cmp     byte ptr [rcx+29h], 4
0x140069137  jb      loc_140068F16
0x14006913d  mov     edx, 1Eh
0x140069142  mov     r9d, [r15+10h]
0x140069146  lea     r8, WPP_ac55395600da34284848d4e5839e1eb6_Traceguids
0x14006914d  mov     rcx, [rcx+18h]
0x140069151  call    WPP_SF_d
0x140069156  jmp     loc_140068F16
0x14006915b  cmp     byte ptr [rcx+29h], 4
0x14006915f  jb      loc_140069082
0x140069165  mov     edx, 1Fh
0x14006916a  mov     r9d, ebx
0x14006916d  lea     r8, WPP_ac55395600da34284848d4e5839e1eb6_Traceguids
0x140069174  mov     rcx, [rcx+18h]
0x140069178  call    WPP_SF_d
0x14006917d  jmp     loc_140069082
0x14007b290  push    rbp
0x14007b292  sub     rsp, 30h
0x14007b296  mov     rbp, rdx
0x14007b299  test    cl, cl
0x14007b29b  jz      short loc_14007B2AF
0x14007b29d  mov     edx, 23Eh
0x14007b2a2  lea     rcx, aRxnotifychange; "RxNotifyChangeDirectory"
0x14007b2a9  call    RxLogAbnormalTermination
0x14007b2ae  nop
0x14007b2af  lea     rax, WPP_GLOBAL_Control
0x14007b2b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b2bd  cmp     rcx, rax
0x14007b2c0  jz      short loc_14007B2E9
0x14007b2c2  mov     eax, [rcx+2Ch]
0x14007b2c5  test    al, 2
0x14007b2c7  jz      short loc_14007B2E9
0x14007b2c9  cmp     byte ptr [rcx+29h], 4
0x14007b2cd  jb      short loc_14007B2E9
0x14007b2cf  mov     edx, 1Fh
0x14007b2d4  mov     r9d, [rbp+30h]
0x14007b2d8  lea     r8, WPP_ac55395600da34284848d4e5839e1eb6_Traceguids
0x14007b2df  mov     rcx, [rcx+18h]
0x14007b2e3  call    WPP_SF_d
0x14007b2e8  nop
0x14007b2e9  add     rsp, 30h
0x14007b2ed  pop     rbp
0x14007b2ee  retn
```
