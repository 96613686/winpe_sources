# DfscpContainerCreateNotify

- ea: `0x14001a040`
- end: `0x14001a48d`
- name: `DfscpContainerCreateNotify`
- size: `1101`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path`

## callees

- `0x140002340`
- `0x1400025f4`
- `0x1400027f8`
- `0x140006380`
- `0x140011bc8`
- `0x1400125a4`
- `0x140018098`
- `0x14001a040`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001a137`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a14e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a137`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a14e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001a15e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001a3f1`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001a15e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001a3f1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001a172`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001a172`
- `ntoskrnl!PsCreateSiloContext` at `0x14001a0c0`
- `ntoskrnl!PsCreateSiloContext` at `0x14001a0c0`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001a11d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001a3de`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001a11d`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001a3de`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001a183`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001a400`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001a183`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001a400`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14001a39c`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14001a39c`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001a387`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001a387`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001a444`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001a444`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a374`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a374`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a368`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a368`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001a326`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001a326`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a311`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a311`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001a0f7`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001a10e`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001a0f7`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001a10e`

## pseudocode

```c
__int64 __fastcall DfscpContainerCreateNotify(__int64 a1)
{
  int v2; // eax
  NTSTATUS v3; // edi
  _QWORD *v4; // rax
  __int64 v5; // rbx
  int inserted; // eax
  __int64 v7; // rdx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  unsigned int SiloMonitorContextSlot; // eax
  __int64 v13; // rbx
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF
  void *v17; // [rsp+98h] [rbp+40h] BYREF

  v17 = 0;
  DestinationString = 0;
  SymbolicLinkName = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids, a1);
  v2 = PsCreateSiloContext(a1, 272, 512, DfscpContainerCleanupNotify, &v17);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids, a1, v2);
    }
  }
  else
  {
    memset(v17, 0, 0x110u);
    v4 = v17;
    *((_QWORD *)v17 + 1) = v17;
    *v4 = v4;
    ExInitializeResourceLite((PERESOURCE)((char *)v17 + 16));
    ExInitializeResourceLite((PERESOURCE)((char *)v17 + 152));
    v5 = PsAttachSiloToCurrentThread(a1);
    RtlInitUnicodeString(&DestinationString, L"\\Device\\DfsClient");
    RtlInitUnicodeString(&SymbolicLinkName, L"\\Dfs");
    IoDeleteSymbolicLink(&SymbolicLinkName);
    v3 = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
    PsDetachSiloFromCurrentThread(v5);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids,
          (unsigned int)v3);
      }
      goto LABEL_40;
    }
    inserted = DfscCacheInitialize((char *)v17 + 128, 0, (unsigned int)(dword_14000C764 << 10));
    v3 = inserted;
    if ( inserted < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_36;
      }
      v9 = 12;
LABEL_35:
      WPP_SF_D(v8->AttachedDevice, v9, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids, (unsigned int)inserted);
LABEL_36:
      v13 = PsAttachSiloToCurrentThread(a1);
      IoDeleteSymbolicLink(&SymbolicLinkName);
      PsDetachSiloFromCurrentThread(v13);
      goto LABEL_40;
    }
    LOBYTE(v7) = 1;
    inserted = DfscCacheInitialize((char *)v17 + 136, v7, (unsigned int)(dword_14000C760 << 10));
    v3 = inserted;
    if ( inserted < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_36;
      }
      v9 = 13;
      goto LABEL_35;
    }
    inserted = DfscNetUseTableInitialize((char *)v17 + 256);
    v3 = inserted;
    if ( inserted < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_36;
      }
      v9 = 14;
      goto LABEL_35;
    }
    inserted = DfscNetUseTableInitialize((char *)v17 + 264);
    v3 = inserted;
    if ( inserted < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_36;
      }
      v9 = 15;
      goto LABEL_35;
    }
    inserted = DfscCredTableInitialize((char *)v17 + 144);
    v3 = inserted;
    if ( inserted < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_36;
      }
      v9 = 16;
      goto LABEL_35;
    }
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement, 1u);
    v10 = (_QWORD *)qword_14000C7F0;
    if ( *(__int64 **)qword_14000C7F0 != &qword_14000C7E8 )
      __fastfail(3u);
    v11 = v17;
    *((_QWORD *)v17 + 1) = qword_14000C7F0;
    *v11 = &qword_14000C7E8;
    *v10 = v11;
    qword_14000C7F0 = (__int64)v11;
    ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement);
    KeLeaveCriticalRegion();
    SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(qword_14000C7F8);
    inserted = PsInsertPermanentSiloContext(a1, SiloMonitorContextSlot, v17);
    v3 = inserted;
    if ( inserted < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_36;
      }
      v9 = 17;
      goto LABEL_35;
    }
  }
LABEL_40:
  if ( v17 )
    PsDereferenceSiloContext();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids, a1, v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001a040  push    rbp
0x14001a042  push    rbx
0x14001a043  push    rsi
0x14001a044  push    rdi
0x14001a045  push    r14
0x14001a047  push    r15
0x14001a049  mov     rbp, rsp
0x14001a04c  sub     rsp, 58h
0x14001a050  xorps   xmm0, xmm0
0x14001a053  mov     [rbp+arg_8], 0
0x14001a05b  xorps   xmm1, xmm1
0x14001a05e  mov     rsi, rcx
0x14001a061  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001a065  movups  xmmword ptr [rbp+SymbolicLinkName.Length], xmm1
0x14001a069  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a070  lea     r14, WPP_GLOBAL_Control
0x14001a077  lea     r15, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids
0x14001a07e  cmp     rcx, r14
0x14001a081  jz      short loc_14001A0A0
0x14001a083  test    dword ptr [rcx+2Ch], 200000h
0x14001a08a  jz      short loc_14001A0A0
0x14001a08c  mov     rcx, [rcx+18h]
0x14001a090  mov     edx, 0Ah
0x14001a095  mov     r9, rsi
0x14001a098  mov     r8, r15
0x14001a09b  call    WPP_SF_q
0x14001a0a0  lea     rax, [rbp+arg_8]
0x14001a0a4  mov     ebx, 110h
0x14001a0a9  mov     edx, ebx
0x14001a0ab  mov     [rsp+58h+var_38], rax
0x14001a0b0  lea     r9, DfscpContainerCleanupNotify
0x14001a0b7  mov     r8d, 200h
0x14001a0bd  mov     rcx, rsi
0x14001a0c0  call    cs:__imp_PsCreateSiloContext
0x14001a0c7  nop     dword ptr [rax+rax+00h]
0x14001a0cc  mov     edi, eax
0x14001a0ce  test    eax, eax
0x14001a0d0  js      loc_14001A40E
0x14001a0d6  mov     rcx, [rbp+arg_8]; void *
0x14001a0da  mov     r8d, ebx; Size
0x14001a0dd  xor     edx, edx; Val
0x14001a0df  call    memset
0x14001a0e4  mov     rax, [rbp+arg_8]
0x14001a0e8  mov     [rax+8], rax
0x14001a0ec  mov     [rax], rax
0x14001a0ef  mov     rcx, [rbp+arg_8]
0x14001a0f3  add     rcx, 10h; Resource
0x14001a0f7  call    cs:__imp_ExInitializeResourceLite
0x14001a0fe  nop     dword ptr [rax+rax+00h]
0x14001a103  mov     rcx, [rbp+arg_8]
0x14001a107  add     rcx, 98h; Resource
0x14001a10e  call    cs:__imp_ExInitializeResourceLite
0x14001a115  nop     dword ptr [rax+rax+00h]
0x14001a11a  mov     rcx, rsi
0x14001a11d  call    cs:__imp_PsAttachSiloToCurrentThread
0x14001a124  nop     dword ptr [rax+rax+00h]
0x14001a129  lea     rdx, SourceString; "\\Device\\DfsClient"
0x14001a130  mov     rbx, rax
0x14001a133  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001a137  call    cs:__imp_RtlInitUnicodeString
0x14001a13e  nop     dword ptr [rax+rax+00h]
0x14001a143  lea     rdx, aDfs; "\\Dfs"
0x14001a14a  lea     rcx, [rbp+SymbolicLinkName]; DestinationString
0x14001a14e  call    cs:__imp_RtlInitUnicodeString
0x14001a155  nop     dword ptr [rax+rax+00h]
0x14001a15a  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x14001a15e  call    cs:__imp_IoDeleteSymbolicLink
0x14001a165  nop     dword ptr [rax+rax+00h]
0x14001a16a  lea     rdx, [rbp+DestinationString]; DeviceName
0x14001a16e  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x14001a172  call    cs:__imp_IoCreateSymbolicLink
0x14001a179  nop     dword ptr [rax+rax+00h]
0x14001a17e  mov     rcx, rbx
0x14001a181  mov     edi, eax
0x14001a183  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14001a18a  nop     dword ptr [rax+rax+00h]
0x14001a18f  test    edi, edi
0x14001a191  jns     short loc_14001A1C9
0x14001a193  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a19a  cmp     rcx, r14
0x14001a19d  jz      loc_14001A43B
0x14001a1a3  test    dword ptr [rcx+2Ch], 100000h
0x14001a1aa  jz      loc_14001A43B
0x14001a1b0  mov     rcx, [rcx+18h]
0x14001a1b4  mov     edx, 0Bh
0x14001a1b9  mov     r9d, edi
0x14001a1bc  mov     r8, r15
0x14001a1bf  call    WPP_SF_D
0x14001a1c4  jmp     loc_14001A43B
0x14001a1c9  mov     r8d, cs:dword_14000C764
0x14001a1d0  xor     edx, edx
0x14001a1d2  mov     rcx, [rbp+arg_8]
0x14001a1d6  shl     r8d, 0Ah
0x14001a1da  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14001a1de  call    DfscCacheInitialize
0x14001a1e3  mov     edi, eax
0x14001a1e5  test    eax, eax
0x14001a1e7  jns     short loc_14001A210
0x14001a1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a1f0  cmp     rcx, r14
0x14001a1f3  jz      loc_14001A3DB
0x14001a1f9  test    dword ptr [rcx+2Ch], 100000h
0x14001a200  jz      loc_14001A3DB
0x14001a206  mov     edx, 0Ch
0x14001a20b  jmp     loc_14001A3CC
0x14001a210  mov     r8d, cs:dword_14000C760
0x14001a217  mov     dl, 1
0x14001a219  mov     rcx, [rbp+arg_8]
0x14001a21d  shl     r8d, 0Ah
0x14001a221  add     rcx, 88h
0x14001a228  call    DfscCacheInitialize
0x14001a22d  mov     edi, eax
0x14001a22f  test    eax, eax
0x14001a231  jns     short loc_14001A25A
0x14001a233  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a23a  cmp     rcx, r14
0x14001a23d  jz      loc_14001A3DB
0x14001a243  test    dword ptr [rcx+2Ch], 100000h
0x14001a24a  jz      loc_14001A3DB
0x14001a250  mov     edx, 0Dh
0x14001a255  jmp     loc_14001A3CC
0x14001a25a  mov     rcx, [rbp+arg_8]
0x14001a25e  add     rcx, 100h
0x14001a265  call    DfscNetUseTableInitialize
0x14001a26a  mov     edi, eax
0x14001a26c  test    eax, eax
0x14001a26e  jns     short loc_14001A297
0x14001a270  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a277  cmp     rcx, r14
0x14001a27a  jz      loc_14001A3DB
0x14001a280  test    dword ptr [rcx+2Ch], 100000h
0x14001a287  jz      loc_14001A3DB
0x14001a28d  mov     edx, 0Eh
0x14001a292  jmp     loc_14001A3CC
0x14001a297  mov     rcx, [rbp+arg_8]
0x14001a29b  add     rcx, 108h
0x14001a2a2  call    DfscNetUseTableInitialize
0x14001a2a7  mov     edi, eax
0x14001a2a9  test    eax, eax
0x14001a2ab  jns     short loc_14001A2D4
0x14001a2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2b4  cmp     rcx, r14
0x14001a2b7  jz      loc_14001A3DB
0x14001a2bd  test    dword ptr [rcx+2Ch], 100000h
0x14001a2c4  jz      loc_14001A3DB
0x14001a2ca  mov     edx, 0Fh
0x14001a2cf  jmp     loc_14001A3CC
0x14001a2d4  mov     rcx, [rbp+arg_8]
0x14001a2d8  add     rcx, 90h
0x14001a2df  call    DfscCredTableInitialize
0x14001a2e4  mov     edi, eax
0x14001a2e6  test    eax, eax
0x14001a2e8  jns     short loc_14001A311
0x14001a2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2f1  cmp     rcx, r14
0x14001a2f4  jz      loc_14001A3DB
0x14001a2fa  test    dword ptr [rcx+2Ch], 100000h
0x14001a301  jz      loc_14001A3DB
0x14001a307  mov     edx, 10h
0x14001a30c  jmp     loc_14001A3CC
0x14001a311  call    cs:__imp_KeEnterCriticalRegion
0x14001a318  nop     dword ptr [rax+rax+00h]
0x14001a31d  mov     dl, 1; Wait
0x14001a31f  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14001a326  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001a32d  nop     dword ptr [rax+rax+00h]
0x14001a332  mov     rcx, cs:qword_14000C7F0
0x14001a339  lea     rdx, qword_14000C7E8
0x14001a340  cmp     [rcx], rdx
0x14001a343  jz      short loc_14001A34C
0x14001a345  mov     ecx, 3
0x14001a34a  int     29h; Win8: RtlFailFast(ecx)
0x14001a34c  mov     rax, [rbp+arg_8]
0x14001a350  mov     [rax+8], rcx
0x14001a354  mov     [rax], rdx
0x14001a357  mov     [rcx], rax
0x14001a35a  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14001a361  mov     cs:qword_14000C7F0, rax
0x14001a368  call    cs:__imp_ExReleaseResourceLite
0x14001a36f  nop     dword ptr [rax+rax+00h]
0x14001a374  call    cs:__imp_KeLeaveCriticalRegion
0x14001a37b  nop     dword ptr [rax+rax+00h]
0x14001a380  mov     rcx, cs:qword_14000C7F8
0x14001a387  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14001a38e  nop     dword ptr [rax+rax+00h]
0x14001a393  mov     r8, [rbp+arg_8]
0x14001a397  mov     rcx, rsi
0x14001a39a  mov     edx, eax
0x14001a39c  call    cs:__imp_PsInsertPermanentSiloContext
0x14001a3a3  nop     dword ptr [rax+rax+00h]
0x14001a3a8  mov     edi, eax
0x14001a3aa  test    eax, eax
0x14001a3ac  jns     loc_14001A43B
0x14001a3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3b9  cmp     rcx, r14
0x14001a3bc  jz      short loc_14001A3DB
0x14001a3be  test    dword ptr [rcx+2Ch], 100000h
0x14001a3c5  jz      short loc_14001A3DB
0x14001a3c7  mov     edx, 11h
0x14001a3cc  mov     rcx, [rcx+18h]
0x14001a3d0  mov     r9d, eax
0x14001a3d3  mov     r8, r15
0x14001a3d6  call    WPP_SF_D
0x14001a3db  mov     rcx, rsi
0x14001a3de  call    cs:__imp_PsAttachSiloToCurrentThread
0x14001a3e5  nop     dword ptr [rax+rax+00h]
0x14001a3ea  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x14001a3ee  mov     rbx, rax
0x14001a3f1  call    cs:__imp_IoDeleteSymbolicLink
0x14001a3f8  nop     dword ptr [rax+rax+00h]
0x14001a3fd  mov     rcx, rbx
0x14001a400  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14001a407  nop     dword ptr [rax+rax+00h]
0x14001a40c  jmp     short loc_14001A43B
0x14001a40e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a415  cmp     rcx, r14
0x14001a418  jz      short loc_14001A43B
0x14001a41a  test    dword ptr [rcx+2Ch], 100000h
0x14001a421  jz      short loc_14001A43B
0x14001a423  mov     rcx, [rcx+18h]
0x14001a427  mov     edx, 12h
0x14001a42c  mov     r9, rsi
0x14001a42f  mov     dword ptr [rsp+58h+var_38], eax
0x14001a433  mov     r8, r15
0x14001a436  call    WPP_SF_qD
0x14001a43b  mov     rcx, [rbp+arg_8]
0x14001a43f  test    rcx, rcx
0x14001a442  jz      short loc_14001A450
0x14001a444  call    cs:__imp_PsDereferenceSiloContext
0x14001a44b  nop     dword ptr [rax+rax+00h]
0x14001a450  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a457  cmp     rcx, r14
0x14001a45a  jz      short loc_14001A47D
0x14001a45c  test    dword ptr [rcx+2Ch], 200000h
0x14001a463  jz      short loc_14001A47D
0x14001a465  mov     rcx, [rcx+18h]
0x14001a469  mov     edx, 13h
0x14001a46e  mov     r9, rsi
0x14001a471  mov     dword ptr [rsp+58h+var_38], edi
0x14001a475  mov     r8, r15
0x14001a478  call    WPP_SF_qD
0x14001a47d  mov     eax, edi
0x14001a47f  add     rsp, 58h
0x14001a483  pop     r15
0x14001a485  pop     r14
0x14001a487  pop     rdi
0x14001a488  pop     rsi
0x14001a489  pop     rbx
0x14001a48a  pop     rbp
0x14001a48b  retn
```
