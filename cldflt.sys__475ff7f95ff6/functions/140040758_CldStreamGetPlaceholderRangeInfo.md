# CldStreamGetPlaceholderRangeInfo

- ea: `0x140040758`
- end: `0x140040ac7`
- name: `CldStreamGetPlaceholderRangeInfo`
- size: `879`
- prototype: `__int64 __fastcall(__int64 **, __int64, int, __int64, __int64, ULONG Length, PVOID VirtualAddress, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14003de10`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140010998`
- `0x140010c9c`
- `0x140040758`
- `0x14007807c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400408f6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400408f6`
- `ntoskrnl!IoFreeMdl` at `0x140040aa8`
- `ntoskrnl!IoFreeMdl` at `0x140040aa8`
- `ntoskrnl!IoAllocateMdl` at `0x140040835`
- `ntoskrnl!IoAllocateMdl` at `0x140040835`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400408c2`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400408c2`
- `ntoskrnl!MmUnlockPages` at `0x140040a94`
- `ntoskrnl!MmUnlockPages` at `0x140040a94`

## pseudocode

```c
__int64 __fastcall CldStreamGetPlaceholderRangeInfo(
        __int64 **a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        ULONG Length,
        PVOID VirtualAddress,
        __int64 a8)
{
  int v8; // edi
  __int64 v11; // r15
  PVOID MappedSystemVa; // r14
  struct _MDL *v13; // rbx
  __int64 PlaceholderRangeInfo; // rdi
  __int64 v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  struct _MDL *Mdl; // rax
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  struct _MDL *v24; // [rsp+60h] [rbp-48h]

  v8 = a4;
  v11 = *(_QWORD *)(*(_QWORD *)(**a1 + 16) + 32LL);
  MappedSystemVa = 0;
  if ( a2 != v11 )
  {
    v13 = 0;
    LODWORD(PlaceholderRangeInfo) = -1073741811;
    HsmDbgBreakOnStatus(3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v16 = **a1;
      if ( v16 )
        v17 = *(_DWORD *)(v16 + 28);
      else
        v17 = 0;
      WPP_SF_iiqqLd(WPP_GLOBAL_Control->AttachedDevice, v16, v15, a2, v11, a1, v16, v17);
    }
    goto LABEL_31;
  }
  Mdl = IoAllocateMdl(VirtualAddress, Length, 0, 0, 0);
  v13 = Mdl;
  v24 = Mdl;
  if ( !Mdl )
  {
    LODWORD(PlaceholderRangeInfo) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_31;
    }
    v20 = 80;
    goto LABEL_14;
  }
  MmProbeAndLockPages(Mdl, 1, IoWriteAccess);
  if ( (v13->MdlFlags & 5) != 0 )
    MappedSystemVa = v13->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v13, 0, MmCached, 0, 0, 0x40000010u);
  if ( !MappedSystemVa )
  {
    LODWORD(PlaceholderRangeInfo) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_31;
    }
    v20 = 82;
LABEL_14:
    WPP_SF_qqqd(
      v19->AttachedDevice,
      v20,
      WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids,
      v11,
      Length,
      VirtualAddress,
      -1073741670);
    goto LABEL_31;
  }
  PlaceholderRangeInfo = (unsigned int)HsmProcessGetPlaceholderRangeInfo(
                                         **a1,
                                         a3,
                                         v8,
                                         a5,
                                         (__int64)MappedSystemVa,
                                         Length,
                                         a8);
  HsmDbgBreakOnStatus(PlaceholderRangeInfo);
  if ( (int)PlaceholderRangeInfo < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v21 = **a1;
    if ( v21 )
      v22 = *(_DWORD *)(v21 + 28);
    else
      v22 = 0;
    WPP_SF_iqqLdiiDd(
      WPP_GLOBAL_Control->AttachedDevice,
      WPP_GLOBAL_Control,
      a4,
      a2,
      a1,
      v21,
      v22,
      a3,
      a4,
      a5,
      Length,
      PlaceholderRangeInfo,
      v24,
      0);
  }
LABEL_31:
  if ( MappedSystemVa )
    MmUnlockPages(v13);
  if ( v13 )
    IoFreeMdl(v13);
  return (unsigned int)PlaceholderRangeInfo;
}

```

## disassembly

```asm
0x140040758  mov     [rsp+arg_18], r9
0x14004075d  mov     [rsp+arg_10], r8d
0x140040762  mov     [rsp+arg_8], rdx
0x140040767  push    rbx
0x140040768  push    rsi
0x140040769  push    rdi
0x14004076a  push    r12
0x14004076c  push    r13
0x14004076e  push    r14
0x140040770  push    r15
0x140040772  sub     rsp, 70h
0x140040776  mov     rdi, r9
0x140040779  mov     r12, rdx
0x14004077c  mov     rsi, rcx
0x14004077f  mov     rax, [rcx]
0x140040782  mov     r10, [rax]
0x140040785  mov     rax, [r10+10h]
0x140040789  mov     r15, [rax+20h]
0x14004078d  xor     r14d, r14d
0x140040790  mov     [rsp+0A8h+var_40], r14
0x140040795  cmp     rdx, r15
0x140040798  jz      short loc_14004080C
0x14004079a  xor     ebx, ebx
0x14004079c  mov     edi, 0C000000Dh
0x1400407a1  mov     ecx, edi
0x1400407a3  call    HsmDbgBreakOnStatus
0x1400407a8  lea     rax, WPP_GLOBAL_Control
0x1400407af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400407b6  cmp     rcx, rax
0x1400407b9  jz      loc_140040A8C
0x1400407bf  test    dword ptr [rcx+2Ch], 100h
0x1400407c6  jz      loc_140040A8C
0x1400407cc  cmp     byte ptr [rcx+29h], 2
0x1400407d0  jb      loc_140040A8C
0x1400407d6  mov     rax, [rsi]
0x1400407d9  mov     rdx, [rax]
0x1400407dc  test    rdx, rdx
0x1400407df  jz      short loc_1400407E6
0x1400407e1  mov     eax, [rdx+1Ch]
0x1400407e4  jmp     short loc_1400407E8
0x1400407e6  xor     eax, eax
0x1400407e8  mov     [rsp+0A8h+var_70], eax
0x1400407ec  mov     [rsp+0A8h+var_78], rdx
0x1400407f1  mov     qword ptr [rsp+0A8h+Priority], rsi
0x1400407f6  mov     [rsp+0A8h+Irp], r15
0x1400407fb  mov     r9, r12
0x1400407fe  mov     rcx, [rcx+18h]
0x140040802  call    WPP_SF_iiqqLd
0x140040807  jmp     loc_140040A8C
0x14004080c  mov     [rsp+0A8h+arg_0], r15
0x140040814  mov     [rsp+0A8h+Irp], r14; Irp
0x140040819  xor     r9d, r9d; ChargeQuota
0x14004081c  xor     r8d, r8d; SecondaryBuffer
0x14004081f  mov     r12d, [rsp+0A8h+Length]
0x140040827  mov     edx, r12d; Length
0x14004082a  mov     r13, [rsp+0A8h+VirtualAddress]
0x140040832  mov     rcx, r13; VirtualAddress
0x140040835  call    cs:__imp_IoAllocateMdl
0x14004083c  nop     dword ptr [rax+rax+00h]
0x140040841  mov     rbx, rax
0x140040844  mov     [rsp+0A8h+var_48], rax
0x140040849  test    rax, rax
0x14004084c  jnz     short loc_1400408B3
0x14004084e  mov     esi, 0C000009Ah
0x140040853  mov     edi, esi
0x140040855  mov     ecx, esi
0x140040857  call    HsmDbgBreakOnStatus
0x14004085c  lea     rax, WPP_GLOBAL_Control
0x140040863  mov     rcx, cs:WPP_GLOBAL_Control
0x14004086a  cmp     rcx, rax
0x14004086d  jz      loc_140040A8C
0x140040873  test    dword ptr [rcx+2Ch], 100h
0x14004087a  jz      loc_140040A8C
0x140040880  cmp     byte ptr [rcx+29h], 2
0x140040884  jb      loc_140040A8C
0x14004088a  lea     edx, [rbx+50h]
0x14004088d  mov     dword ptr [rsp+0A8h+var_78], esi
0x140040891  mov     qword ptr [rsp+0A8h+Priority], r13
0x140040896  mov     [rsp+0A8h+Irp], r12
0x14004089b  mov     r9, r15
0x14004089e  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x1400408a5  mov     rcx, [rcx+18h]
0x1400408a9  call    WPP_SF_qqqd
0x1400408ae  jmp     loc_140040A8C
0x1400408b3  mov     r14d, 1
0x1400408b9  mov     r8d, r14d; Operation
0x1400408bc  mov     dl, r14b; AccessMode
0x1400408bf  mov     rcx, rbx; MemoryDescriptorList
0x1400408c2  call    cs:__imp_MmProbeAndLockPages
0x1400408c9  nop     dword ptr [rax+rax+00h]
0x1400408ce  nop
0x1400408cf  test    byte ptr [rbx+0Ah], 5
0x1400408d3  jz      short loc_1400408DB
0x1400408d5  mov     r14, [rbx+18h]
0x1400408d9  jmp     short loc_140040905
0x1400408db  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x1400408e3  mov     dword ptr [rsp+0A8h+Irp], 0; BugCheckOnFailure
0x1400408eb  xor     r9d, r9d; RequestedAddress
0x1400408ee  mov     r8d, r14d; CacheType
0x1400408f1  xor     edx, edx; AccessMode
0x1400408f3  mov     rcx, rbx; MemoryDescriptorList
0x1400408f6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400408fd  nop     dword ptr [rax+rax+00h]
0x140040902  mov     r14, rax
0x140040905  test    r14, r14
0x140040908  jnz     short loc_14004094F
0x14004090a  mov     esi, 0C000009Ah
0x14004090f  mov     edi, esi
0x140040911  mov     ecx, esi
0x140040913  call    HsmDbgBreakOnStatus
0x140040918  lea     rax, WPP_GLOBAL_Control
0x14004091f  mov     rcx, cs:WPP_GLOBAL_Control
0x140040926  cmp     rcx, rax
0x140040929  jz      loc_140040A8C
0x14004092f  test    dword ptr [rcx+2Ch], 100h
0x140040936  jz      loc_140040A8C
0x14004093c  cmp     byte ptr [rcx+29h], 2
0x140040940  jb      loc_140040A8C
0x140040946  lea     edx, [r14+52h]
0x14004094a  jmp     loc_14004088D
0x14004094f  mov     rcx, [rsi]
0x140040952  mov     rax, [rsp+0A8h+arg_38]
0x14004095a  mov     [rsp+0A8h+var_78], rax
0x14004095f  mov     [rsp+0A8h+Priority], r12d
0x140040964  mov     [rsp+0A8h+Irp], r14
0x140040969  mov     r15, [rsp+0A8h+arg_20]
0x140040971  mov     r9, r15
0x140040974  mov     r8, rdi
0x140040977  mov     r13d, [rsp+0A8h+arg_10]
0x14004097f  mov     edx, r13d
0x140040982  mov     rcx, [rcx]
0x140040985  call    HsmProcessGetPlaceholderRangeInfo
0x14004098a  mov     edi, eax
0x14004098c  mov     ecx, eax
0x14004098e  call    HsmDbgBreakOnStatus
0x140040993  test    edi, edi
0x140040995  jns     loc_140040A8C
0x14004099b  lea     rax, WPP_GLOBAL_Control
0x1400409a2  mov     rdx, cs:WPP_GLOBAL_Control
0x1400409a9  cmp     rdx, rax
0x1400409ac  jz      loc_140040A8C
0x1400409b2  test    dword ptr [rdx+2Ch], 100h
0x1400409b9  jz      loc_140040A8C
0x1400409bf  cmp     byte ptr [rdx+29h], 2
0x1400409c3  jb      loc_140040A8C
0x1400409c9  mov     rax, [rsi]
0x1400409cc  mov     rcx, [rax]
0x1400409cf  test    rcx, rcx
0x1400409d2  jz      short loc_1400409D9
0x1400409d4  mov     eax, [rcx+1Ch]
0x1400409d7  jmp     short loc_1400409DB
0x1400409d9  xor     eax, eax
0x1400409db  mov     [rsp+0A8h+var_50], edi
0x1400409df  mov     [rsp+0A8h+var_58], r12d
0x1400409e4  mov     [rsp+0A8h+var_60], r15
0x1400409e9  mov     r8, [rsp+0A8h+arg_18]
0x1400409f1  mov     [rsp+0A8h+var_68], r8
0x1400409f6  mov     [rsp+0A8h+var_70], r13d
0x1400409fb  mov     dword ptr [rsp+0A8h+var_78], eax
0x1400409ff  mov     qword ptr [rsp+0A8h+Priority], rcx
0x140040a04  mov     [rsp+0A8h+Irp], rsi
0x140040a09  mov     r9, [rsp+0A8h+arg_8]
0x140040a11  mov     rcx, [rdx+18h]
0x140040a15  call    WPP_SF_iqqLdiiDd
0x140040a1a  jmp     short loc_140040A8C
0x140040a1c  mov     edi, eax
0x140040a1e  mov     ecx, eax
0x140040a20  call    HsmDbgBreakOnStatus
0x140040a25  lea     rax, WPP_GLOBAL_Control
0x140040a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140040a33  cmp     rcx, rax
0x140040a36  jz      short loc_140040A82
0x140040a38  test    dword ptr [rcx+2Ch], 100h
0x140040a3f  jz      short loc_140040A82
0x140040a41  cmp     byte ptr [rcx+29h], 2
0x140040a45  jb      short loc_140040A82
0x140040a47  mov     r8d, [rsp+0A8h+Length]
0x140040a4f  mov     edx, 51h ; 'Q'
0x140040a54  mov     dword ptr [rsp+0A8h+var_78], edi
0x140040a58  mov     rax, [rsp+0A8h+VirtualAddress]
0x140040a60  mov     qword ptr [rsp+0A8h+Priority], rax
0x140040a65  mov     [rsp+0A8h+Irp], r8
0x140040a6a  mov     r9, [rsp+0A8h+arg_0]
0x140040a72  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140040a79  mov     rcx, [rcx+18h]
0x140040a7d  call    WPP_SF_qqqd
0x140040a82  mov     rbx, [rsp+0A8h+var_48]
0x140040a87  mov     r14, [rsp+0A8h+var_40]
0x140040a8c  test    r14, r14
0x140040a8f  jz      short loc_140040AA0
0x140040a91  mov     rcx, rbx; MemoryDescriptorList
0x140040a94  call    cs:__imp_MmUnlockPages
0x140040a9b  nop     dword ptr [rax+rax+00h]
0x140040aa0  test    rbx, rbx
0x140040aa3  jz      short loc_140040AB4
0x140040aa5  mov     rcx, rbx; Mdl
0x140040aa8  call    cs:__imp_IoFreeMdl
0x140040aaf  nop     dword ptr [rax+rax+00h]
0x140040ab4  mov     eax, edi
0x140040ab6  add     rsp, 70h
0x140040aba  pop     r15
0x140040abc  pop     r14
0x140040abe  pop     r13
0x140040ac0  pop     r12
0x140040ac2  pop     rdi
0x140040ac3  pop     rsi
0x140040ac4  pop     rbx
0x140040ac5  retn
```
