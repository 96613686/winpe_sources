# CldStreamRetrieveData

- ea: `0x14006f2c8`
- end: `0x14006f551`
- name: `CldStreamRetrieveData`
- size: `649`
- prototype: `__int64 __fastcall(__int64 *, int, ULONG *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003e3c8`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14006f2c8`
- `0x14006f558`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006f3dd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006f3dd`
- `ntoskrnl!IoFreeMdl` at `0x14006f532`
- `ntoskrnl!IoFreeMdl` at `0x14006f532`
- `ntoskrnl!IoAllocateMdl` at `0x14006f319`
- `ntoskrnl!IoAllocateMdl` at `0x14006f319`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006f3a9`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006f3a9`
- `ntoskrnl!MmUnlockPages` at `0x14006f51e`
- `ntoskrnl!MmUnlockPages` at `0x14006f51e`

## pseudocode

```c
__int64 __fastcall CldStreamRetrieveData(__int64 *a1, int a2, ULONG *a3, void *a4)
{
  __int64 v7; // rdi
  __int64 v8; // r13
  PVOID MappedSystemVa; // r14
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
      MappedSystemVa = v11->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000010u);
    if ( MappedSystemVa )
    {
      Data = HsmRecallRetrieveData(**(_QWORD **)(v7 + 8), *(_QWORD *)v7, a2, (int)a3, MappedSystemVa);
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
0x14006f2c8  mov     [rsp+arg_18], r9
0x14006f2cd  mov     [rsp+arg_10], r8
0x14006f2d2  push    rbx
0x14006f2d3  push    rsi
0x14006f2d4  push    rdi
0x14006f2d5  push    r12
0x14006f2d7  push    r13
0x14006f2d9  push    r14
0x14006f2db  push    r15
0x14006f2dd  sub     rsp, 50h
0x14006f2e1  mov     r12, r9
0x14006f2e4  mov     r15, r8
0x14006f2e7  mov     rsi, rdx
0x14006f2ea  mov     rdi, [rcx]
0x14006f2ed  mov     rax, [rdi]
0x14006f2f0  mov     rcx, [rax+10h]
0x14006f2f4  mov     r13, [rcx+20h]
0x14006f2f8  mov     [rsp+88h+arg_0], r13
0x14006f300  xor     r14d, r14d
0x14006f303  mov     [rsp+88h+var_40], r14
0x14006f308  mov     [rsp+88h+Irp], r14; Irp
0x14006f30d  xor     r9d, r9d; ChargeQuota
0x14006f310  xor     r8d, r8d; SecondaryBuffer
0x14006f313  mov     edx, [r15]; Length
0x14006f316  mov     rcx, r12; VirtualAddress
0x14006f319  call    cs:__imp_IoAllocateMdl
0x14006f320  nop     dword ptr [rax+rax+00h]
0x14006f325  mov     rbx, rax
0x14006f328  mov     [rsp+88h+var_48], rax
0x14006f32d  test    rax, rax
0x14006f330  jnz     short loc_14006F39A
0x14006f332  mov     esi, 0C000009Ah
0x14006f337  mov     edi, esi
0x14006f339  mov     ecx, esi
0x14006f33b  call    HsmDbgBreakOnStatus
0x14006f340  lea     rax, WPP_GLOBAL_Control
0x14006f347  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f34e  cmp     rcx, rax
0x14006f351  jz      loc_14006F516
0x14006f357  test    dword ptr [rcx+2Ch], 100h
0x14006f35e  jz      loc_14006F516
0x14006f364  cmp     byte ptr [rcx+29h], 2
0x14006f368  jb      loc_14006F516
0x14006f36e  lea     edx, [rbx+33h]
0x14006f371  mov     [rsp+88h+var_58], esi
0x14006f375  mov     rcx, [rcx+18h]
0x14006f379  mov     eax, [r15]
0x14006f37c  mov     qword ptr [rsp+88h+Priority], r12
0x14006f381  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006f388  mov     r9, r13
0x14006f38b  mov     [rsp+88h+Irp], rax
0x14006f390  call    WPP_SF_qqqd
0x14006f395  jmp     loc_14006F516
0x14006f39a  mov     r14d, 1
0x14006f3a0  mov     r8d, r14d; Operation
0x14006f3a3  mov     dl, r14b; AccessMode
0x14006f3a6  mov     rcx, rbx; MemoryDescriptorList
0x14006f3a9  call    cs:__imp_MmProbeAndLockPages
0x14006f3b0  nop     dword ptr [rax+rax+00h]
0x14006f3b5  nop
0x14006f3b6  test    byte ptr [rbx+0Ah], 5
0x14006f3ba  jz      short loc_14006F3C2
0x14006f3bc  mov     r14, [rbx+18h]
0x14006f3c0  jmp     short loc_14006F3EC
0x14006f3c2  mov     [rsp+88h+Priority], 40000010h; Priority
0x14006f3ca  mov     dword ptr [rsp+88h+Irp], 0; BugCheckOnFailure
0x14006f3d2  xor     r9d, r9d; RequestedAddress
0x14006f3d5  mov     r8d, r14d; CacheType
0x14006f3d8  xor     edx, edx; AccessMode
0x14006f3da  mov     rcx, rbx; MemoryDescriptorList
0x14006f3dd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006f3e4  nop     dword ptr [rax+rax+00h]
0x14006f3e9  mov     r14, rax
0x14006f3ec  test    r14, r14
0x14006f3ef  jnz     short loc_14006F436
0x14006f3f1  mov     esi, 0C000009Ah
0x14006f3f6  mov     edi, esi
0x14006f3f8  mov     ecx, esi
0x14006f3fa  call    HsmDbgBreakOnStatus
0x14006f3ff  lea     rax, WPP_GLOBAL_Control
0x14006f406  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f40d  cmp     rcx, rax
0x14006f410  jz      loc_14006F516
0x14006f416  test    dword ptr [rcx+2Ch], 100h
0x14006f41d  jz      loc_14006F516
0x14006f423  cmp     byte ptr [rcx+29h], 2
0x14006f427  jb      loc_14006F516
0x14006f42d  lea     edx, [r14+35h]
0x14006f431  jmp     loc_14006F371
0x14006f436  mov     rcx, [rdi+8]
0x14006f43a  mov     [rsp+88h+Irp], r14; Buffer
0x14006f43f  mov     r9, r15; int
0x14006f442  mov     r8, rsi; int
0x14006f445  mov     rdx, [rdi]; int
0x14006f448  mov     rcx, [rcx]; int
0x14006f44b  call    HsmRecallRetrieveData
0x14006f450  mov     edi, eax
0x14006f452  mov     ecx, eax
0x14006f454  call    HsmDbgBreakOnStatus
0x14006f459  test    edi, edi
0x14006f45b  jns     loc_14006F516
0x14006f461  lea     rax, WPP_GLOBAL_Control
0x14006f468  mov     r10, cs:WPP_GLOBAL_Control
0x14006f46f  cmp     r10, rax
0x14006f472  jz      loc_14006F516
0x14006f478  test    dword ptr [r10+2Ch], 100h
0x14006f480  jz      loc_14006F516
0x14006f486  cmp     byte ptr [r10+29h], 2
0x14006f48b  jb      loc_14006F516
0x14006f491  mov     edx, 36h ; '6'
0x14006f496  mov     [rsp+88h+var_58], edi
0x14006f49a  mov     rcx, [r10+18h]
0x14006f49e  jmp     loc_14006F379
0x14006f4a3  mov     edi, eax
0x14006f4a5  mov     ecx, eax
0x14006f4a7  call    HsmDbgBreakOnStatus
0x14006f4ac  lea     rax, WPP_GLOBAL_Control
0x14006f4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f4ba  cmp     rcx, rax
0x14006f4bd  jz      short loc_14006F50C
0x14006f4bf  test    dword ptr [rcx+2Ch], 100h
0x14006f4c6  jz      short loc_14006F50C
0x14006f4c8  cmp     byte ptr [rcx+29h], 2
0x14006f4cc  jb      short loc_14006F50C
0x14006f4ce  mov     rax, [rsp+88h+arg_10]
0x14006f4d6  mov     r8d, [rax]
0x14006f4d9  mov     edx, 34h ; '4'
0x14006f4de  mov     [rsp+88h+var_58], edi
0x14006f4e2  mov     rax, [rsp+88h+arg_18]
0x14006f4ea  mov     qword ptr [rsp+88h+Priority], rax
0x14006f4ef  mov     [rsp+88h+Irp], r8
0x14006f4f4  mov     r9, [rsp+88h+arg_0]
0x14006f4fc  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006f503  mov     rcx, [rcx+18h]
0x14006f507  call    WPP_SF_qqqd
0x14006f50c  mov     rbx, [rsp+88h+var_48]
0x14006f511  mov     r14, [rsp+88h+var_40]
0x14006f516  test    r14, r14
0x14006f519  jz      short loc_14006F52A
0x14006f51b  mov     rcx, rbx; MemoryDescriptorList
0x14006f51e  call    cs:__imp_MmUnlockPages
0x14006f525  nop     dword ptr [rax+rax+00h]
0x14006f52a  test    rbx, rbx
0x14006f52d  jz      short loc_14006F53E
0x14006f52f  mov     rcx, rbx; Mdl
0x14006f532  call    cs:__imp_IoFreeMdl
0x14006f539  nop     dword ptr [rax+rax+00h]
0x14006f53e  mov     eax, edi
0x14006f540  add     rsp, 50h
0x14006f544  pop     r15
0x14006f546  pop     r14
0x14006f548  pop     r13
0x14006f54a  pop     r12
0x14006f54c  pop     rdi
0x14006f54d  pop     rsi
0x14006f54e  pop     rbx
0x14006f54f  retn
```
