# CldStreamRetrieveData

- ea: `0x14006f1a8`
- end: `0x14006f431`
- name: `CldStreamRetrieveData`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003e3a8`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14006f1a8`
- `0x14006f438`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006f2bd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006f2bd`
- `ntoskrnl!IoFreeMdl` at `0x14006f412`
- `ntoskrnl!IoFreeMdl` at `0x14006f412`
- `ntoskrnl!IoAllocateMdl` at `0x14006f1f9`
- `ntoskrnl!IoAllocateMdl` at `0x14006f1f9`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006f289`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006f289`
- `ntoskrnl!MmUnlockPages` at `0x14006f3fe`
- `ntoskrnl!MmUnlockPages` at `0x14006f3fe`

## pseudocode

```c
__int64 __fastcall CldStreamRetrieveData(__int64 *a1, union _LARGE_INTEGER a2, ULONG *a3, void *a4)
{
  __int64 v7; // rdi
  __int64 v8; // r13
  char *MappedSystemVa; // r14
  struct _MDL *Mdl; // rax
  struct _MDL *v11; // rbx
  int Data; // edi
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx

  v7 = *a1;
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)*a1 + 16LL) + 32LL);
  MappedSystemVa = 0;
  Mdl = IoAllocateMdl(a4, *a3, 0, 0, 0);
  v11 = Mdl;
  if ( Mdl )
  {
    MmProbeAndLockPages(Mdl, 1, IoWriteAccess);
    if ( (v11->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v11->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000010u);
    if ( MappedSystemVa )
    {
      Data = HsmRecallRetrieveData(**(_QWORD **)(v7 + 8), *(_QWORD *)v7, a2, a3, MappedSystemVa);
      HsmDbgBreakOnStatus((unsigned int)Data);
      if ( Data < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          54,
          WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids,
          v8,
          *a3,
          a4,
          Data);
      }
    }
    else
    {
      Data = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v14 = 53;
        goto LABEL_6;
      }
    }
  }
  else
  {
    Data = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v14 = 51;
LABEL_6:
      WPP_SF_qqqd(v13->AttachedDevice, v14, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, v8, *a3, a4, -1073741670);
    }
  }
  if ( MappedSystemVa )
    MmUnlockPages(v11);
  if ( v11 )
    IoFreeMdl(v11);
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x14006f1a8  mov     [rsp+arg_18], r9
0x14006f1ad  mov     [rsp+arg_10], r8
0x14006f1b2  push    rbx
0x14006f1b3  push    rsi
0x14006f1b4  push    rdi
0x14006f1b5  push    r12
0x14006f1b7  push    r13
0x14006f1b9  push    r14
0x14006f1bb  push    r15
0x14006f1bd  sub     rsp, 50h
0x14006f1c1  mov     r12, r9
0x14006f1c4  mov     r15, r8
0x14006f1c7  mov     rsi, rdx
0x14006f1ca  mov     rdi, [rcx]
0x14006f1cd  mov     rax, [rdi]
0x14006f1d0  mov     rcx, [rax+10h]
0x14006f1d4  mov     r13, [rcx+20h]
0x14006f1d8  mov     [rsp+88h+arg_0], r13
0x14006f1e0  xor     r14d, r14d
0x14006f1e3  mov     [rsp+88h+var_40], r14
0x14006f1e8  mov     [rsp+88h+Irp], r14; Irp
0x14006f1ed  xor     r9d, r9d; ChargeQuota
0x14006f1f0  xor     r8d, r8d; SecondaryBuffer
0x14006f1f3  mov     edx, [r15]; Length
0x14006f1f6  mov     rcx, r12; VirtualAddress
0x14006f1f9  call    cs:__imp_IoAllocateMdl
0x14006f200  nop     dword ptr [rax+rax+00h]
0x14006f205  mov     rbx, rax
0x14006f208  mov     [rsp+88h+var_48], rax
0x14006f20d  test    rax, rax
0x14006f210  jnz     short loc_14006F27A
0x14006f212  mov     esi, 0C000009Ah
0x14006f217  mov     edi, esi
0x14006f219  mov     ecx, esi
0x14006f21b  call    HsmDbgBreakOnStatus
0x14006f220  lea     rax, WPP_GLOBAL_Control
0x14006f227  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f22e  cmp     rcx, rax
0x14006f231  jz      loc_14006F3F6
0x14006f237  test    dword ptr [rcx+2Ch], 100h
0x14006f23e  jz      loc_14006F3F6
0x14006f244  cmp     byte ptr [rcx+29h], 2
0x14006f248  jb      loc_14006F3F6
0x14006f24e  lea     edx, [rbx+33h]
0x14006f251  mov     [rsp+88h+var_58], esi
0x14006f255  mov     rcx, [rcx+18h]
0x14006f259  mov     eax, [r15]
0x14006f25c  mov     qword ptr [rsp+88h+Priority], r12
0x14006f261  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006f268  mov     r9, r13
0x14006f26b  mov     [rsp+88h+Irp], rax
0x14006f270  call    WPP_SF_qqqd
0x14006f275  jmp     loc_14006F3F6
0x14006f27a  mov     r14d, 1
0x14006f280  mov     r8d, r14d; Operation
0x14006f283  mov     dl, r14b; AccessMode
0x14006f286  mov     rcx, rbx; MemoryDescriptorList
0x14006f289  call    cs:__imp_MmProbeAndLockPages
0x14006f290  nop     dword ptr [rax+rax+00h]
0x14006f295  nop
0x14006f296  test    byte ptr [rbx+0Ah], 5
0x14006f29a  jz      short loc_14006F2A2
0x14006f29c  mov     r14, [rbx+18h]
0x14006f2a0  jmp     short loc_14006F2CC
0x14006f2a2  mov     [rsp+88h+Priority], 40000010h; Priority
0x14006f2aa  mov     dword ptr [rsp+88h+Irp], 0; BugCheckOnFailure
0x14006f2b2  xor     r9d, r9d; RequestedAddress
0x14006f2b5  mov     r8d, r14d; CacheType
0x14006f2b8  xor     edx, edx; AccessMode
0x14006f2ba  mov     rcx, rbx; MemoryDescriptorList
0x14006f2bd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006f2c4  nop     dword ptr [rax+rax+00h]
0x14006f2c9  mov     r14, rax
0x14006f2cc  test    r14, r14
0x14006f2cf  jnz     short loc_14006F316
0x14006f2d1  mov     esi, 0C000009Ah
0x14006f2d6  mov     edi, esi
0x14006f2d8  mov     ecx, esi
0x14006f2da  call    HsmDbgBreakOnStatus
0x14006f2df  lea     rax, WPP_GLOBAL_Control
0x14006f2e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f2ed  cmp     rcx, rax
0x14006f2f0  jz      loc_14006F3F6
0x14006f2f6  test    dword ptr [rcx+2Ch], 100h
0x14006f2fd  jz      loc_14006F3F6
0x14006f303  cmp     byte ptr [rcx+29h], 2
0x14006f307  jb      loc_14006F3F6
0x14006f30d  lea     edx, [r14+35h]
0x14006f311  jmp     loc_14006F251
0x14006f316  mov     rcx, [rdi+8]
0x14006f31a  mov     [rsp+88h+Irp], r14; Buffer
0x14006f31f  mov     r9, r15; int
0x14006f322  mov     r8, rsi; int
0x14006f325  mov     rdx, [rdi]; int
0x14006f328  mov     rcx, [rcx]; int
0x14006f32b  call    HsmRecallRetrieveData
0x14006f330  mov     edi, eax
0x14006f332  mov     ecx, eax
0x14006f334  call    HsmDbgBreakOnStatus
0x14006f339  test    edi, edi
0x14006f33b  jns     loc_14006F3F6
0x14006f341  lea     rax, WPP_GLOBAL_Control
0x14006f348  mov     r10, cs:WPP_GLOBAL_Control
0x14006f34f  cmp     r10, rax
0x14006f352  jz      loc_14006F3F6
0x14006f358  test    dword ptr [r10+2Ch], 100h
0x14006f360  jz      loc_14006F3F6
0x14006f366  cmp     byte ptr [r10+29h], 2
0x14006f36b  jb      loc_14006F3F6
0x14006f371  mov     edx, 36h ; '6'
0x14006f376  mov     [rsp+88h+var_58], edi
0x14006f37a  mov     rcx, [r10+18h]
0x14006f37e  jmp     loc_14006F259
0x14006f383  mov     edi, eax
0x14006f385  mov     ecx, eax
0x14006f387  call    HsmDbgBreakOnStatus
0x14006f38c  lea     rax, WPP_GLOBAL_Control
0x14006f393  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f39a  cmp     rcx, rax
0x14006f39d  jz      short loc_14006F3EC
0x14006f39f  test    dword ptr [rcx+2Ch], 100h
0x14006f3a6  jz      short loc_14006F3EC
0x14006f3a8  cmp     byte ptr [rcx+29h], 2
0x14006f3ac  jb      short loc_14006F3EC
0x14006f3ae  mov     rax, [rsp+88h+arg_10]
0x14006f3b6  mov     r8d, [rax]
0x14006f3b9  mov     edx, 34h ; '4'
0x14006f3be  mov     [rsp+88h+var_58], edi
0x14006f3c2  mov     rax, [rsp+88h+arg_18]
0x14006f3ca  mov     qword ptr [rsp+88h+Priority], rax
0x14006f3cf  mov     [rsp+88h+Irp], r8
0x14006f3d4  mov     r9, [rsp+88h+arg_0]
0x14006f3dc  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006f3e3  mov     rcx, [rcx+18h]
0x14006f3e7  call    WPP_SF_qqqd
0x14006f3ec  mov     rbx, [rsp+88h+var_48]
0x14006f3f1  mov     r14, [rsp+88h+var_40]
0x14006f3f6  test    r14, r14
0x14006f3f9  jz      short loc_14006F40A
0x14006f3fb  mov     rcx, rbx; MemoryDescriptorList
0x14006f3fe  call    cs:__imp_MmUnlockPages
0x14006f405  nop     dword ptr [rax+rax+00h]
0x14006f40a  test    rbx, rbx
0x14006f40d  jz      short loc_14006F41E
0x14006f40f  mov     rcx, rbx; Mdl
0x14006f412  call    cs:__imp_IoFreeMdl
0x14006f419  nop     dword ptr [rax+rax+00h]
0x14006f41e  mov     eax, edi
0x14006f420  add     rsp, 50h
0x14006f424  pop     r15
0x14006f426  pop     r14
0x14006f428  pop     r13
0x14006f42a  pop     r12
0x14006f42c  pop     rdi
0x14006f42d  pop     rsi
0x14006f42e  pop     rbx
0x14006f42f  retn
```
