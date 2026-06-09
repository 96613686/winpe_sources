# CldStreamGetPlaceholderRangeInfo

- ea: `0x140040748`
- end: `0x140040ab7`
- name: `CldStreamGetPlaceholderRangeInfo`
- size: `879`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, ULONG Length, PVOID VirtualAddress, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14003ddf0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140010918`
- `0x140010c1c`
- `0x140040748`
- `0x140077f3c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400408e6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400408e6`
- `ntoskrnl!IoFreeMdl` at `0x140040a98`
- `ntoskrnl!IoFreeMdl` at `0x140040a98`
- `ntoskrnl!IoAllocateMdl` at `0x140040825`
- `ntoskrnl!IoAllocateMdl` at `0x140040825`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400408b2`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400408b2`
- `ntoskrnl!MmUnlockPages` at `0x140040a84`
- `ntoskrnl!MmUnlockPages` at `0x140040a84`

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
0x140040748  mov     [rsp+arg_18], r9
0x14004074d  mov     [rsp+arg_10], r8d
0x140040752  mov     [rsp+arg_8], rdx
0x140040757  push    rbx
0x140040758  push    rsi
0x140040759  push    rdi
0x14004075a  push    r12
0x14004075c  push    r13
0x14004075e  push    r14
0x140040760  push    r15
0x140040762  sub     rsp, 70h
0x140040766  mov     rdi, r9
0x140040769  mov     r12, rdx
0x14004076c  mov     rsi, rcx
0x14004076f  mov     rax, [rcx]
0x140040772  mov     r10, [rax]
0x140040775  mov     rax, [r10+10h]
0x140040779  mov     r15, [rax+20h]
0x14004077d  xor     r14d, r14d
0x140040780  mov     [rsp+0A8h+var_40], r14
0x140040785  cmp     rdx, r15
0x140040788  jz      short loc_1400407FC
0x14004078a  xor     ebx, ebx
0x14004078c  mov     edi, 0C000000Dh
0x140040791  mov     ecx, edi
0x140040793  call    HsmDbgBreakOnStatus
0x140040798  lea     rax, WPP_GLOBAL_Control
0x14004079f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400407a6  cmp     rcx, rax
0x1400407a9  jz      loc_140040A7C
0x1400407af  test    dword ptr [rcx+2Ch], 100h
0x1400407b6  jz      loc_140040A7C
0x1400407bc  cmp     byte ptr [rcx+29h], 2
0x1400407c0  jb      loc_140040A7C
0x1400407c6  mov     rax, [rsi]
0x1400407c9  mov     rdx, [rax]
0x1400407cc  test    rdx, rdx
0x1400407cf  jz      short loc_1400407D6
0x1400407d1  mov     eax, [rdx+1Ch]
0x1400407d4  jmp     short loc_1400407D8
0x1400407d6  xor     eax, eax
0x1400407d8  mov     [rsp+0A8h+var_70], eax
0x1400407dc  mov     [rsp+0A8h+var_78], rdx
0x1400407e1  mov     qword ptr [rsp+0A8h+Priority], rsi
0x1400407e6  mov     [rsp+0A8h+Irp], r15
0x1400407eb  mov     r9, r12
0x1400407ee  mov     rcx, [rcx+18h]
0x1400407f2  call    WPP_SF_iiqqLd
0x1400407f7  jmp     loc_140040A7C
0x1400407fc  mov     [rsp+0A8h+arg_0], r15
0x140040804  mov     [rsp+0A8h+Irp], r14; Irp
0x140040809  xor     r9d, r9d; ChargeQuota
0x14004080c  xor     r8d, r8d; SecondaryBuffer
0x14004080f  mov     r12d, [rsp+0A8h+Length]
0x140040817  mov     edx, r12d; Length
0x14004081a  mov     r13, [rsp+0A8h+VirtualAddress]
0x140040822  mov     rcx, r13; VirtualAddress
0x140040825  call    cs:__imp_IoAllocateMdl
0x14004082c  nop     dword ptr [rax+rax+00h]
0x140040831  mov     rbx, rax
0x140040834  mov     [rsp+0A8h+var_48], rax
0x140040839  test    rax, rax
0x14004083c  jnz     short loc_1400408A3
0x14004083e  mov     esi, 0C000009Ah
0x140040843  mov     edi, esi
0x140040845  mov     ecx, esi
0x140040847  call    HsmDbgBreakOnStatus
0x14004084c  lea     rax, WPP_GLOBAL_Control
0x140040853  mov     rcx, cs:WPP_GLOBAL_Control
0x14004085a  cmp     rcx, rax
0x14004085d  jz      loc_140040A7C
0x140040863  test    dword ptr [rcx+2Ch], 100h
0x14004086a  jz      loc_140040A7C
0x140040870  cmp     byte ptr [rcx+29h], 2
0x140040874  jb      loc_140040A7C
0x14004087a  lea     edx, [rbx+50h]
0x14004087d  mov     dword ptr [rsp+0A8h+var_78], esi
0x140040881  mov     qword ptr [rsp+0A8h+Priority], r13
0x140040886  mov     [rsp+0A8h+Irp], r12
0x14004088b  mov     r9, r15
0x14004088e  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140040895  mov     rcx, [rcx+18h]
0x140040899  call    WPP_SF_qqqd
0x14004089e  jmp     loc_140040A7C
0x1400408a3  mov     r14d, 1
0x1400408a9  mov     r8d, r14d; Operation
0x1400408ac  mov     dl, r14b; AccessMode
0x1400408af  mov     rcx, rbx; MemoryDescriptorList
0x1400408b2  call    cs:__imp_MmProbeAndLockPages
0x1400408b9  nop     dword ptr [rax+rax+00h]
0x1400408be  nop
0x1400408bf  test    byte ptr [rbx+0Ah], 5
0x1400408c3  jz      short loc_1400408CB
0x1400408c5  mov     r14, [rbx+18h]
0x1400408c9  jmp     short loc_1400408F5
0x1400408cb  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x1400408d3  mov     dword ptr [rsp+0A8h+Irp], 0; BugCheckOnFailure
0x1400408db  xor     r9d, r9d; RequestedAddress
0x1400408de  mov     r8d, r14d; CacheType
0x1400408e1  xor     edx, edx; AccessMode
0x1400408e3  mov     rcx, rbx; MemoryDescriptorList
0x1400408e6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400408ed  nop     dword ptr [rax+rax+00h]
0x1400408f2  mov     r14, rax
0x1400408f5  test    r14, r14
0x1400408f8  jnz     short loc_14004093F
0x1400408fa  mov     esi, 0C000009Ah
0x1400408ff  mov     edi, esi
0x140040901  mov     ecx, esi
0x140040903  call    HsmDbgBreakOnStatus
0x140040908  lea     rax, WPP_GLOBAL_Control
0x14004090f  mov     rcx, cs:WPP_GLOBAL_Control
0x140040916  cmp     rcx, rax
0x140040919  jz      loc_140040A7C
0x14004091f  test    dword ptr [rcx+2Ch], 100h
0x140040926  jz      loc_140040A7C
0x14004092c  cmp     byte ptr [rcx+29h], 2
0x140040930  jb      loc_140040A7C
0x140040936  lea     edx, [r14+52h]
0x14004093a  jmp     loc_14004087D
0x14004093f  mov     rcx, [rsi]
0x140040942  mov     rax, [rsp+0A8h+arg_38]
0x14004094a  mov     [rsp+0A8h+var_78], rax
0x14004094f  mov     [rsp+0A8h+Priority], r12d
0x140040954  mov     [rsp+0A8h+Irp], r14
0x140040959  mov     r15, [rsp+0A8h+arg_20]
0x140040961  mov     r9, r15
0x140040964  mov     r8, rdi
0x140040967  mov     r13d, [rsp+0A8h+arg_10]
0x14004096f  mov     edx, r13d
0x140040972  mov     rcx, [rcx]
0x140040975  call    HsmProcessGetPlaceholderRangeInfo
0x14004097a  mov     edi, eax
0x14004097c  mov     ecx, eax
0x14004097e  call    HsmDbgBreakOnStatus
0x140040983  test    edi, edi
0x140040985  jns     loc_140040A7C
0x14004098b  lea     rax, WPP_GLOBAL_Control
0x140040992  mov     rdx, cs:WPP_GLOBAL_Control
0x140040999  cmp     rdx, rax
0x14004099c  jz      loc_140040A7C
0x1400409a2  test    dword ptr [rdx+2Ch], 100h
0x1400409a9  jz      loc_140040A7C
0x1400409af  cmp     byte ptr [rdx+29h], 2
0x1400409b3  jb      loc_140040A7C
0x1400409b9  mov     rax, [rsi]
0x1400409bc  mov     rcx, [rax]
0x1400409bf  test    rcx, rcx
0x1400409c2  jz      short loc_1400409C9
0x1400409c4  mov     eax, [rcx+1Ch]
0x1400409c7  jmp     short loc_1400409CB
0x1400409c9  xor     eax, eax
0x1400409cb  mov     [rsp+0A8h+var_50], edi
0x1400409cf  mov     [rsp+0A8h+var_58], r12d
0x1400409d4  mov     [rsp+0A8h+var_60], r15
0x1400409d9  mov     r8, [rsp+0A8h+arg_18]
0x1400409e1  mov     [rsp+0A8h+var_68], r8
0x1400409e6  mov     [rsp+0A8h+var_70], r13d
0x1400409eb  mov     dword ptr [rsp+0A8h+var_78], eax
0x1400409ef  mov     qword ptr [rsp+0A8h+Priority], rcx
0x1400409f4  mov     [rsp+0A8h+Irp], rsi
0x1400409f9  mov     r9, [rsp+0A8h+arg_8]
0x140040a01  mov     rcx, [rdx+18h]
0x140040a05  call    WPP_SF_iqqLdiiDd
0x140040a0a  jmp     short loc_140040A7C
0x140040a0c  mov     edi, eax
0x140040a0e  mov     ecx, eax
0x140040a10  call    HsmDbgBreakOnStatus
0x140040a15  lea     rax, WPP_GLOBAL_Control
0x140040a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140040a23  cmp     rcx, rax
0x140040a26  jz      short loc_140040A72
0x140040a28  test    dword ptr [rcx+2Ch], 100h
0x140040a2f  jz      short loc_140040A72
0x140040a31  cmp     byte ptr [rcx+29h], 2
0x140040a35  jb      short loc_140040A72
0x140040a37  mov     r8d, [rsp+0A8h+Length]
0x140040a3f  mov     edx, 51h ; 'Q'
0x140040a44  mov     dword ptr [rsp+0A8h+var_78], edi
0x140040a48  mov     rax, [rsp+0A8h+VirtualAddress]
0x140040a50  mov     qword ptr [rsp+0A8h+Priority], rax
0x140040a55  mov     [rsp+0A8h+Irp], r8
0x140040a5a  mov     r9, [rsp+0A8h+arg_0]
0x140040a62  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140040a69  mov     rcx, [rcx+18h]
0x140040a6d  call    WPP_SF_qqqd
0x140040a72  mov     rbx, [rsp+0A8h+var_48]
0x140040a77  mov     r14, [rsp+0A8h+var_40]
0x140040a7c  test    r14, r14
0x140040a7f  jz      short loc_140040A90
0x140040a81  mov     rcx, rbx; MemoryDescriptorList
0x140040a84  call    cs:__imp_MmUnlockPages
0x140040a8b  nop     dword ptr [rax+rax+00h]
0x140040a90  test    rbx, rbx
0x140040a93  jz      short loc_140040AA4
0x140040a95  mov     rcx, rbx; Mdl
0x140040a98  call    cs:__imp_IoFreeMdl
0x140040a9f  nop     dword ptr [rax+rax+00h]
0x140040aa4  mov     eax, edi
0x140040aa6  add     rsp, 70h
0x140040aaa  pop     r15
0x140040aac  pop     r14
0x140040aae  pop     r13
0x140040ab0  pop     r12
0x140040ab2  pop     rdi
0x140040ab3  pop     rsi
0x140040ab4  pop     rbx
0x140040ab5  retn
```
