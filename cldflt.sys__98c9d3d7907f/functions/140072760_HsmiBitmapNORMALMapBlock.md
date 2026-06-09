# HsmiBitmapNORMALMapBlock

- ea: `0x140072760`
- end: `0x140072ee3`
- name: `HsmiBitmapNORMALMapBlock`
- size: `1923`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14007243c`

## callees

- `0x140003c50`
- `0x140005194`
- `0x1400185e0`
- `0x140018f68`
- `0x140019370`
- `0x1400194b0`
- `0x1400196f4`
- `0x14001b85c`
- `0x140072760`
- `0x140072eec`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140072cb0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140072cb0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140072929`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140072929`
- `ntoskrnl!IoFreeMdl` at `0x140072ec1`
- `ntoskrnl!IoFreeMdl` at `0x140072ec1`
- `ntoskrnl!IoAllocateMdl` at `0x140072854`
- `ntoskrnl!IoAllocateMdl` at `0x140072c5c`
- `ntoskrnl!IoAllocateMdl` at `0x140072854`
- `ntoskrnl!IoAllocateMdl` at `0x140072c5c`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007287b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007287b`
- `ntoskrnl!ExAllocatePool2` at `0x140072bc1`
- `ntoskrnl!ExAllocatePool2` at `0x140072bc1`
- `FLTMGR!FltPerformSynchronousIo` at `0x140072d80`
- `FLTMGR!FltPerformSynchronousIo` at `0x140072d80`
- `FLTMGR!FltFreeCallbackData` at `0x140072ed2`
- `FLTMGR!FltFreeCallbackData` at `0x140072ed2`
- `FLTMGR!FltAllocateCallbackData` at `0x140072cce`
- `FLTMGR!FltAllocateCallbackData` at `0x140072cce`

## pseudocode

```c
__int64 __fastcall HsmiBitmapNORMALMapBlock(
        _QWORD *a1,
        unsigned int a2,
        unsigned int a3,
        LARGE_INTEGER a4,
        PVOID *a5,
        _OWORD *a6)
{
  __int64 v7; // rsi
  __int64 v8; // r14
  __int64 v10; // r8
  NTSTATUS Status; // esi
  unsigned int v12; // r8d
  struct _MDL *v13; // rax
  PMDL v14; // r14
  PVOID MappedSystemVa; // rax
  PDEVICE_OBJECT v17; // rcx
  int v18; // edx
  PDEVICE_OBJECT v19; // rcx
  int v20; // edx
  int v21; // r8d
  void *Pool2; // rax
  struct _MDL *Mdl; // rax
  char v24; // [rsp+38h] [rbp-A0h]
  char v25; // [rsp+38h] [rbp-A0h]
  char LowPart; // [rsp+40h] [rbp-98h]
  char v27; // [rsp+40h] [rbp-98h]
  char v28; // [rsp+48h] [rbp-90h]
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+60h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+68h] [rbp-70h] BYREF
  PMDL MemoryDescriptorList; // [rsp+70h] [rbp-68h]
  PVOID VirtualAddress; // [rsp+78h] [rbp-60h] BYREF
  __int128 v33; // [rsp+80h] [rbp-58h]
  NTSTATUS v34; // [rsp+90h] [rbp-48h]
  _OWORD v35[3]; // [rsp+A0h] [rbp-38h] BYREF

  v7 = a3;
  v8 = a2;
  VirtualAddress = 0;
  MemoryDescriptorList = 0;
  RetNewCallbackData = 0;
  v33 = 0u;
  LODWORD(FileObject) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qisdi(WPP_GLOBAL_Control->AttachedDevice, 12, a3, (_DWORD)a1, *a1, (__int64)(a1 + 4), a2, a4.QuadPart);
  }
  v10 = a1[20];
  if ( (_DWORD)v7 != -1 )
  {
    *(_QWORD *)&v35[0] = v7 + 3 * v8;
    FileObject = *(PFILE_OBJECT *)(v10 + 8LL * *(_QWORD *)&v35[0] + 16);
    Pool2 = (void *)ExAllocatePool2(64, 4096, 1833071432);
    VirtualAddress = Pool2;
    if ( Pool2 )
    {
      LODWORD(v33) = 3;
      *((_QWORD *)&v33 + 1) = Pool2;
      Mdl = IoAllocateMdl(Pool2, 0x1000u, 0, 0, 0);
      MemoryDescriptorList = Mdl;
      if ( Mdl )
      {
        MmBuildMdlForNonPagedPool(Mdl);
        Status = FltAllocateCallbackData(*(PFLT_INSTANCE *)(a1[5] + 32LL), FileObject, &RetNewCallbackData);
        HsmDbgBreakOnStatus((unsigned int)Status);
        if ( Status >= 0 )
        {
          RetNewCallbackData->Iopb->MajorFunction = 3;
          RetNewCallbackData->Iopb->Parameters.Read.ByteOffset = a4;
          RetNewCallbackData->Iopb->Parameters.Read.Length = 4096;
          RetNewCallbackData->Iopb->IrpFlags |= 0x101u;
          RetNewCallbackData->Iopb->IrpFlags |= 4u;
          RetNewCallbackData->Iopb->IrpFlags |= 0x42u;
          RetNewCallbackData->Iopb->Parameters.Create.EaBuffer = MemoryDescriptorList;
          MemoryDescriptorList = 0;
          FltPerformSynchronousIo(RetNewCallbackData);
          Status = RetNewCallbackData->IoStatus.Status;
          HsmDbgBreakOnStatus((unsigned int)Status);
          if ( Status >= 0 )
          {
            LODWORD(FileObject) = RetNewCallbackData->IoStatus.Information;
            if ( (_DWORD)FileObject == 4096 )
            {
              Status = HsmiBitmapNORMALVerifyBitmapPages(
                         *(_QWORD *)(a1[20] + 8LL * *(_QWORD *)&v35[0] + 16),
                         (_DWORD)a1,
                         a4.LowPart,
                         (_DWORD)VirtualAddress,
                         4096);
              HsmDbgBreakOnStatus((unsigned int)Status);
              if ( Status >= 0 )
              {
LABEL_12:
                *a5 = VirtualAddress;
                VirtualAddress = 0;
                *a6 = v33;
                LODWORD(v33) = 0;
                goto LABEL_13;
              }
            }
            else
            {
              Status = -1073741595;
              HsmDbgBreakOnStatus(3221225701LL);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qisddiDDd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  (_DWORD)FileObject,
                  a3,
                  (_DWORD)a1,
                  *a1,
                  (__int64)(a1 + 4),
                  v8,
                  a3,
                  a4.QuadPart,
                  (char)FileObject);
              }
            }
            goto LABEL_13;
          }
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_13;
          }
          v18 = 21;
        }
        else
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_13;
          }
          v18 = 20;
        }
        v28 = Status;
        LowPart = a4.LowPart;
        v12 = a3;
        v24 = a3;
LABEL_32:
        WPP_SF_qisddid(v17->AttachedDevice, v18, v12, (_DWORD)a1, *a1, (__int64)(a1 + 4), v8, v24, LowPart, v28);
        goto LABEL_13;
      }
      Status = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_13;
      }
      v20 = 19;
    }
    else
    {
      Status = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_13;
      }
      v20 = 18;
    }
    v27 = a4.LowPart;
    v25 = a3;
    goto LABEL_30;
  }
  Status = HsmFileCacheMapData(*(PFILE_OBJECT *)(v10 + 8 * v8 + 8), &VirtualAddress, (__int64)&FileObject);
  v34 = Status;
  HsmDbgBreakOnStatus((unsigned int)Status);
  if ( Status < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_13;
    }
    v18 = 13;
    v28 = Status;
    LowPart = a4.LowPart;
    v24 = -1;
    goto LABEL_32;
  }
  LODWORD(v33) = 1;
  if ( (_DWORD)FileObject == 4096 )
  {
    v13 = IoAllocateMdl(VirtualAddress, 0x1000u, 0, 0, 0);
    MemoryDescriptorList = v13;
    FileObject = (PFILE_OBJECT)v13;
    if ( v13 )
    {
      MmProbeAndLockPages(v13, 0, IoReadAccess);
      v14 = MemoryDescriptorList;
      v35[0] = v33;
      HsmIBitmapNORMALUnpinBlock(v35);
      LODWORD(v33) = 2;
      *((_QWORD *)&v33 + 1) = MemoryDescriptorList;
      MemoryDescriptorList = 0;
      if ( (v14->MdlFlags & 5) != 0 )
        MappedSystemVa = v14->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v14, 0, MmCached, 0, 0, 0x40000010u);
      VirtualAddress = MappedSystemVa;
      if ( MappedSystemVa )
        goto LABEL_12;
      Status = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v20 = 17;
        goto LABEL_29;
      }
    }
    else
    {
      Status = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v20 = 15;
LABEL_29:
        v27 = a4.LowPart;
        v25 = -1;
LABEL_30:
        WPP_SF_qisddid(v19->AttachedDevice, v20, a2, (_DWORD)a1, *a1, (__int64)(a1 + 4), a2, v25, v27, 154);
      }
    }
  }
  else
  {
    Status = -1073741595;
    HsmDbgBreakOnStatus(3221225701LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qisddDDd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)FileObject,
        v21,
        (_DWORD)a1,
        *a1,
        (__int64)(a1 + 4),
        v8,
        -1,
        (char)FileObject);
    }
  }
LABEL_13:
  if ( (_DWORD)v33 )
  {
    v35[0] = v33;
    HsmIBitmapNORMALUnpinBlock(v35);
  }
  if ( MemoryDescriptorList )
    IoFreeMdl(MemoryDescriptorList);
  if ( RetNewCallbackData )
    FltFreeCallbackData(RetNewCallbackData);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140072760  mov     r11, rsp
0x140072763  mov     [r11+20h], r9
0x140072767  mov     [r11+18h], r8d
0x14007276b  mov     [rsp+arg_8], edx
0x14007276f  mov     [r11+8], rcx
0x140072773  push    rbx
0x140072774  push    rsi
0x140072775  push    r12
0x140072777  push    r13
0x140072779  push    r14
0x14007277b  sub     rsp, 0B0h
0x140072782  mov     r13, r9
0x140072785  mov     esi, r8d
0x140072788  mov     r14d, edx
0x14007278b  mov     rbx, rcx
0x14007278e  mov     qword ptr [r11-60h], 0
0x140072796  xor     eax, eax
0x140072798  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x14007279d  mov     [r11-78h], rax
0x1400727a1  mov     [r11-58h], rax
0x1400727a5  mov     [r11-50h], rax
0x1400727a9  mov     dword ptr [rsp+0D8h+FileObject], eax
0x1400727ad  lea     r12, WPP_GLOBAL_Control
0x1400727b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400727bb  cmp     rcx, r12
0x1400727be  jz      short loc_1400727D1
0x1400727c0  mov     eax, [rcx+2Ch]
0x1400727c3  test    al, 1
0x1400727c5  jz      short loc_1400727D1
0x1400727c7  cmp     byte ptr [rcx+29h], 5
0x1400727cb  jnb     loc_140072A91
0x1400727d1  mov     r8, [rbx+0A0h]
0x1400727d8  cmp     esi, 0FFFFFFFFh
0x1400727db  jnz     loc_140072B96
0x1400727e1  lea     rcx, [rsp+0D8h+FileObject]
0x1400727e6  mov     qword ptr [rsp+0D8h+Priority], rcx; __int64
0x1400727eb  lea     rcx, [rsp+0D8h+VirtualAddress]
0x1400727f0  mov     [rsp+0D8h+Irp], rcx; PVOID *
0x1400727f5  lea     r9, [rsp+0D8h+var_58+8]
0x1400727fd  mov     rdx, r13
0x140072800  mov     rcx, [r8+r14*8+8]; FileObject
0x140072805  call    HsmFileCacheMapData
0x14007280a  mov     esi, eax
0x14007280c  mov     [rsp+0D8h+var_48], eax
0x140072813  mov     ecx, eax
0x140072815  call    HsmDbgBreakOnStatus
0x14007281a  test    esi, esi
0x14007281c  js      loc_1400729B8
0x140072822  mov     dword ptr [rsp+0D8h+var_58], 1
0x14007282d  cmp     dword ptr [rsp+0D8h+FileObject], 1000h
0x140072835  jnz     loc_140072AE4
0x14007283b  mov     [rsp+0D8h+Irp], 0; Irp
0x140072844  xor     r9d, r9d; ChargeQuota
0x140072847  xor     r8d, r8d; SecondaryBuffer
0x14007284a  mov     edx, 1000h; Length
0x14007284f  mov     rcx, [rsp+0D8h+VirtualAddress]; VirtualAddress
0x140072854  call    cs:__imp_IoAllocateMdl
0x14007285b  nop     dword ptr [rax+rax+00h]
0x140072860  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140072865  mov     [rsp+0D8h+FileObject], rax
0x14007286a  test    rax, rax
0x14007286d  jz      loc_140072A15
0x140072873  xor     r8d, r8d; Operation
0x140072876  xor     edx, edx; AccessMode
0x140072878  mov     rcx, rax; MemoryDescriptorList
0x14007287b  call    cs:__imp_MmProbeAndLockPages
0x140072882  nop     dword ptr [rax+rax+00h]
0x140072887  mov     rax, [rsp+0D8h+MemoryDescriptorList]
0x14007288c  jmp     short loc_1400728BE
0x14007288e  lea     r12, WPP_GLOBAL_Control
0x140072895  mov     r13, [rsp+0D8h+arg_18]
0x14007289d  mov     rbx, [rsp+0D8h+arg_0]
0x1400728a5  mov     esi, [rsp+0D8h+var_48]
0x1400728ac  mov     rax, [rsp+0D8h+FileObject]
0x1400728b1  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x1400728b6  mov     r14d, [rsp+0D8h+arg_8]
0x1400728be  test    esi, esi
0x1400728c0  js      loc_1400729D8
0x1400728c6  mov     r14, rax
0x1400728c9  movaps  xmm0, [rsp+0D8h+var_58]
0x1400728d1  movdqa  [rsp+0D8h+var_38], xmm0
0x1400728da  lea     rcx, [rsp+0D8h+var_38]
0x1400728e2  call    HsmIBitmapNORMALUnpinBlock
0x1400728e7  mov     dword ptr [rsp+0D8h+var_58], 2
0x1400728f2  mov     rax, [rsp+0D8h+MemoryDescriptorList]
0x1400728f7  mov     qword ptr [rsp+0D8h+var_58+8], rax
0x1400728ff  xor     eax, eax
0x140072901  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140072906  test    byte ptr [r14+0Ah], 5
0x14007290b  jnz     loc_140072A0C
0x140072911  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x140072919  mov     dword ptr [rsp+0D8h+Irp], eax; BugCheckOnFailure
0x14007291d  xor     r9d, r9d; RequestedAddress
0x140072920  xor     edx, edx; AccessMode
0x140072922  lea     r8d, [rax+1]; CacheType
0x140072926  mov     rcx, r14; MemoryDescriptorList
0x140072929  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140072930  nop     dword ptr [rax+rax+00h]
0x140072935  mov     [rsp+0D8h+VirtualAddress], rax
0x14007293a  test    rax, rax
0x14007293d  jz      loc_140072B56
0x140072943  mov     rcx, [rsp+0D8h+arg_20]
0x14007294b  mov     rax, [rsp+0D8h+VirtualAddress]
0x140072950  mov     [rcx], rax
0x140072953  mov     [rsp+0D8h+VirtualAddress], 0
0x14007295c  movaps  xmm0, [rsp+0D8h+var_58]
0x140072964  mov     rax, [rsp+0D8h+arg_28]
0x14007296c  movdqu  xmmword ptr [rax], xmm0
0x140072970  mov     dword ptr [rsp+0D8h+var_58], 0
0x14007297b  cmp     dword ptr [rsp+0D8h+var_58], 0
0x140072983  jnz     loc_140072E9B
0x140072989  mov     rax, [rsp+0D8h+MemoryDescriptorList]
0x14007298e  test    rax, rax
0x140072991  jnz     loc_140072EBE
0x140072997  mov     rcx, [rsp+0D8h+RetNewCallbackData]; CallbackData
0x14007299c  test    rcx, rcx
0x14007299f  jnz     loc_140072ED2
0x1400729a5  mov     eax, esi
0x1400729a7  add     rsp, 0B0h
0x1400729ae  pop     r14
0x1400729b0  pop     r13
0x1400729b2  pop     r12
0x1400729b4  pop     rsi
0x1400729b5  pop     rbx
0x1400729b6  retn
0x1400729b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400729bf  cmp     rcx, r12
0x1400729c2  jz      short loc_14007297B
0x1400729c4  mov     eax, [rcx+2Ch]
0x1400729c7  test    al, 1
0x1400729c9  jz      short loc_14007297B
0x1400729cb  cmp     byte ptr [rcx+29h], 2
0x1400729cf  jb      short loc_14007297B
0x1400729d1  mov     edx, 0Dh
0x1400729d6  jmp     short loc_1400729F6
0x1400729d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400729df  cmp     rcx, r12
0x1400729e2  jz      short loc_14007297B
0x1400729e4  mov     eax, [rcx+2Ch]
0x1400729e7  test    al, 1
0x1400729e9  jz      short loc_14007297B
0x1400729eb  cmp     byte ptr [rcx+29h], 2
0x1400729ef  jb      short loc_14007297B
0x1400729f1  mov     edx, 10h
0x1400729f6  mov     dword ptr [rsp+0D8h+var_90], esi
0x1400729fa  mov     [rsp+0D8h+var_98], r13
0x1400729ff  mov     dword ptr [rsp+0D8h+var_A0], 0FFFFFFFFh
0x140072a07  jmp     loc_140072ADD
0x140072a0c  mov     rax, [r14+18h]
0x140072a10  jmp     loc_140072935
0x140072a15  mov     r14d, 0C000009Ah
0x140072a1b  mov     esi, r14d
0x140072a1e  mov     ecx, r14d
0x140072a21  call    HsmDbgBreakOnStatus
0x140072a26  mov     rcx, cs:WPP_GLOBAL_Control
0x140072a2d  cmp     rcx, r12
0x140072a30  jz      loc_14007297B
0x140072a36  mov     eax, [rcx+2Ch]
0x140072a39  test    al, 1
0x140072a3b  jz      loc_14007297B
0x140072a41  cmp     byte ptr [rcx+29h], 2
0x140072a45  jb      loc_14007297B
0x140072a4b  mov     edx, 0Fh
0x140072a50  mov     dword ptr [rsp+0D8h+var_90], r14d
0x140072a55  mov     [rsp+0D8h+var_98], r13
0x140072a5a  mov     dword ptr [rsp+0D8h+var_A0], 0FFFFFFFFh
0x140072a62  mov     r8d, [rsp+0D8h+arg_8]
0x140072a6a  mov     [rsp+0D8h+var_A8], r8d
0x140072a6f  lea     rax, [rbx+20h]
0x140072a73  mov     qword ptr [rsp+0D8h+Priority], rax
0x140072a78  mov     rax, [rbx]
0x140072a7b  mov     [rsp+0D8h+Irp], rax
0x140072a80  mov     r9, rbx
0x140072a83  mov     rcx, [rcx+18h]
0x140072a87  call    WPP_SF_qisddid
0x140072a8c  jmp     loc_14007297B
0x140072a91  lea     rax, [rbx+20h]
0x140072a95  mov     edx, 0Ch
0x140072a9a  mov     [rsp+0D8h+var_A0], r13
0x140072a9f  mov     [rsp+0D8h+var_A8], r14d
0x140072aa4  mov     qword ptr [rsp+0D8h+Priority], rax
0x140072aa9  mov     rax, [rbx]
0x140072aac  mov     [rsp+0D8h+Irp], rax
0x140072ab1  mov     r9, rbx
0x140072ab4  mov     rcx, [rcx+18h]
0x140072ab8  call    WPP_SF_qisdi
0x140072abd  jmp     loc_1400727D1
0x140072ac2  mov     edx, 14h
0x140072ac7  mov     dword ptr [rsp+0D8h+var_90], esi
0x140072acb  mov     [rsp+0D8h+var_98], r13
0x140072ad0  mov     r8d, [rsp+0D8h+arg_10]
0x140072ad8  mov     dword ptr [rsp+0D8h+var_A0], r8d
0x140072add  mov     [rsp+0D8h+var_A8], r14d
0x140072ae2  jmp     short loc_140072A6F
0x140072ae4  mov     r13d, 0C00000E5h
0x140072aea  mov     esi, r13d
0x140072aed  mov     ecx, r13d
0x140072af0  call    HsmDbgBreakOnStatus
0x140072af5  mov     rcx, cs:WPP_GLOBAL_Control
0x140072afc  cmp     rcx, r12
0x140072aff  jz      loc_14007297B
0x140072b05  mov     eax, [rcx+2Ch]
0x140072b08  test    al, 1
0x140072b0a  jz      loc_14007297B
0x140072b10  cmp     byte ptr [rcx+29h], 2
0x140072b14  jb      loc_14007297B
0x140072b1a  lea     rax, [rbx+20h]
0x140072b1e  mov     [rsp+0D8h+var_88], r13d
0x140072b23  mov     edx, dword ptr [rsp+0D8h+FileObject]
0x140072b27  mov     dword ptr [rsp+0D8h+var_98], edx
0x140072b2b  mov     dword ptr [rsp+0D8h+var_A0], 0FFFFFFFFh
0x140072b33  mov     [rsp+0D8h+var_A8], r14d
0x140072b38  mov     qword ptr [rsp+0D8h+Priority], rax
0x140072b3d  mov     rax, [rbx]
0x140072b40  mov     [rsp+0D8h+Irp], rax
0x140072b45  mov     r9, rbx
0x140072b48  mov     rcx, [rcx+18h]
0x140072b4c  call    WPP_SF_qisddDDd
0x140072b51  jmp     loc_14007297B
0x140072b56  mov     r14d, 0C000009Ah
0x140072b5c  mov     esi, r14d
0x140072b5f  mov     ecx, r14d
0x140072b62  call    HsmDbgBreakOnStatus
0x140072b67  mov     rcx, cs:WPP_GLOBAL_Control
0x140072b6e  cmp     rcx, r12
0x140072b71  jz      loc_14007297B
0x140072b77  mov     eax, [rcx+2Ch]
0x140072b7a  test    al, 1
0x140072b7c  jz      loc_14007297B
0x140072b82  cmp     byte ptr [rcx+29h], 2
0x140072b86  jb      loc_14007297B
0x140072b8c  mov     edx, 11h
0x140072b91  jmp     loc_140072A50
0x140072b96  lea     rcx, [r14+r14*2]
0x140072b9a  add     rcx, rsi
0x140072b9d  mov     qword ptr [rsp+0D8h+var_38], rcx
0x140072ba5  mov     rax, [r8+rcx*8+10h]
0x140072baa  mov     [rsp+0D8h+FileObject], rax
0x140072baf  mov     esi, 1000h
0x140072bb4  mov     r8d, 6D427348h
0x140072bba  mov     edx, esi
0x140072bbc  mov     ecx, 40h ; '@'
0x140072bc1  call    cs:__imp_ExAllocatePool2
0x140072bc8  nop     dword ptr [rax+rax+00h]
0x140072bcd  mov     [rsp+0D8h+VirtualAddress], rax
0x140072bd2  test    rax, rax
0x140072bd5  jnz     short loc_140072C35
0x140072bd7  mov     r14d, 0C000009Ah
0x140072bdd  mov     esi, r14d
0x140072be0  mov     ecx, r14d
0x140072be3  call    HsmDbgBreakOnStatus
0x140072be8  mov     rcx, cs:WPP_GLOBAL_Control
0x140072bef  cmp     rcx, r12
0x140072bf2  jz      loc_14007297B
0x140072bf8  mov     eax, [rcx+2Ch]
0x140072bfb  test    al, 1
0x140072bfd  jz      loc_14007297B
0x140072c03  cmp     byte ptr [rcx+29h], 2
0x140072c07  jb      loc_14007297B
0x140072c0d  mov     edx, 12h
0x140072c12  jmp     short loc_140072C19
0x140072c14  mov     edx, 13h
0x140072c19  mov     dword ptr [rsp+0D8h+var_90], r14d
0x140072c1e  mov     [rsp+0D8h+var_98], r13
0x140072c23  mov     r8d, [rsp+0D8h+arg_10]
0x140072c2b  mov     dword ptr [rsp+0D8h+var_A0], r8d
0x140072c30  jmp     loc_140072A62
0x140072c35  mov     dword ptr [rsp+0D8h+var_58], 3
0x140072c40  mov     qword ptr [rsp+0D8h+var_58+8], rax
0x140072c48  mov     [rsp+0D8h+Irp], 0; Irp
0x140072c51  xor     r9d, r9d; ChargeQuota
0x140072c54  xor     r8d, r8d; SecondaryBuffer
0x140072c57  mov     edx, esi; Length
0x140072c59  mov     rcx, rax; VirtualAddress
0x140072c5c  call    cs:__imp_IoAllocateMdl
0x140072c63  nop     dword ptr [rax+rax+00h]
0x140072c68  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140072c6d  test    rax, rax
0x140072c70  jnz     short loc_140072CAD
0x140072c72  mov     r14d, 0C000009Ah
0x140072c78  mov     esi, r14d
0x140072c7b  mov     ecx, r14d
0x140072c7e  call    HsmDbgBreakOnStatus
0x140072c83  mov     rcx, cs:WPP_GLOBAL_Control
0x140072c8a  cmp     rcx, r12
0x140072c8d  jz      loc_14007297B
0x140072c93  mov     eax, [rcx+2Ch]
0x140072c96  test    al, 1
0x140072c98  jz      loc_14007297B
0x140072c9e  cmp     byte ptr [rcx+29h], 2
0x140072ca2  jb      loc_14007297B
0x140072ca8  jmp     loc_140072C14
0x140072cad  mov     rcx, rax; MemoryDescriptorList
0x140072cb0  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140072cb7  nop     dword ptr [rax+rax+00h]
0x140072cbc  mov     rcx, [rbx+28h]
0x140072cc0  lea     r8, [rsp+0D8h+RetNewCallbackData]; RetNewCallbackData
0x140072cc5  mov     rdx, [rsp+0D8h+FileObject]; FileObject
0x140072cca  mov     rcx, [rcx+20h]; Instance
0x140072cce  call    cs:__imp_FltAllocateCallbackData
  ... truncated ...
```
