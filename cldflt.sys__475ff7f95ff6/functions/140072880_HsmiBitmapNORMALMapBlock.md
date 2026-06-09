# HsmiBitmapNORMALMapBlock

- ea: `0x140072880`
- end: `0x140073003`
- name: `HsmiBitmapNORMALMapBlock`
- size: `1923`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, unsigned int, union _LARGE_INTEGER, PVOID *, _OWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14007255c`

## callees

- `0x140003c50`
- `0x140005194`
- `0x140018660`
- `0x140018fe8`
- `0x1400193f0`
- `0x140019530`
- `0x140019774`
- `0x14001b8dc`
- `0x140072880`
- `0x14007300c`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140072dd0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140072dd0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140072a49`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140072a49`
- `ntoskrnl!IoFreeMdl` at `0x140072fe1`
- `ntoskrnl!IoFreeMdl` at `0x140072fe1`
- `ntoskrnl!IoAllocateMdl` at `0x140072974`
- `ntoskrnl!IoAllocateMdl` at `0x140072d7c`
- `ntoskrnl!IoAllocateMdl` at `0x140072974`
- `ntoskrnl!IoAllocateMdl` at `0x140072d7c`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007299b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14007299b`
- `ntoskrnl!ExAllocatePool2` at `0x140072ce1`
- `ntoskrnl!ExAllocatePool2` at `0x140072ce1`
- `FLTMGR!FltPerformSynchronousIo` at `0x140072ea0`
- `FLTMGR!FltPerformSynchronousIo` at `0x140072ea0`
- `FLTMGR!FltFreeCallbackData` at `0x140072ff2`
- `FLTMGR!FltFreeCallbackData` at `0x140072ff2`
- `FLTMGR!FltAllocateCallbackData` at `0x140072dee`
- `FLTMGR!FltAllocateCallbackData` at `0x140072dee`

## pseudocode

```c
__int64 __fastcall HsmiBitmapNORMALMapBlock(
        _QWORD *a1,
        unsigned int a2,
        unsigned int a3,
        union _LARGE_INTEGER a4,
        PVOID *a5,
        _OWORD *a6)
{
  __int64 v7; // rsi
  __int64 v8; // r14
  __int64 v10; // r8
  int Status; // esi
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
  __int128 v33; // [rsp+80h] [rbp-58h] BYREF
  int v34; // [rsp+90h] [rbp-48h]
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
        HsmDbgBreakOnStatus(Status);
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
          HsmDbgBreakOnStatus(Status);
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
              HsmDbgBreakOnStatus(Status);
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
              HsmDbgBreakOnStatus(-1073741595);
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
      HsmDbgBreakOnStatus(-1073741670);
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
      HsmDbgBreakOnStatus(-1073741670);
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
  Status = HsmFileCacheMapData(
             *(PFILE_OBJECT *)(v10 + 8 * v8 + 8),
             a4,
             v10,
             (PVOID *)&v33 + 1,
             &VirtualAddress,
             (ULONG *)&FileObject);
  v34 = Status;
  HsmDbgBreakOnStatus(Status);
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
      HsmDbgBreakOnStatus(-1073741670);
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
      HsmDbgBreakOnStatus(-1073741670);
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
    HsmDbgBreakOnStatus(-1073741595);
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
0x140072880  mov     r11, rsp
0x140072883  mov     [r11+20h], r9
0x140072887  mov     [r11+18h], r8d
0x14007288b  mov     [rsp+arg_8], edx
0x14007288f  mov     [r11+8], rcx
0x140072893  push    rbx
0x140072894  push    rsi
0x140072895  push    r12
0x140072897  push    r13
0x140072899  push    r14
0x14007289b  sub     rsp, 0B0h
0x1400728a2  mov     r13, r9
0x1400728a5  mov     esi, r8d
0x1400728a8  mov     r14d, edx
0x1400728ab  mov     rbx, rcx
0x1400728ae  mov     qword ptr [r11-60h], 0
0x1400728b6  xor     eax, eax
0x1400728b8  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x1400728bd  mov     [r11-78h], rax
0x1400728c1  mov     [r11-58h], rax
0x1400728c5  mov     [r11-50h], rax
0x1400728c9  mov     dword ptr [rsp+0D8h+FileObject], eax
0x1400728cd  lea     r12, WPP_GLOBAL_Control
0x1400728d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400728db  cmp     rcx, r12
0x1400728de  jz      short loc_1400728F1
0x1400728e0  mov     eax, [rcx+2Ch]
0x1400728e3  test    al, 1
0x1400728e5  jz      short loc_1400728F1
0x1400728e7  cmp     byte ptr [rcx+29h], 5
0x1400728eb  jnb     loc_140072BB1
0x1400728f1  mov     r8, [rbx+0A0h]
0x1400728f8  cmp     esi, 0FFFFFFFFh
0x1400728fb  jnz     loc_140072CB6
0x140072901  lea     rcx, [rsp+0D8h+FileObject]
0x140072906  mov     qword ptr [rsp+0D8h+Priority], rcx; __int64
0x14007290b  lea     rcx, [rsp+0D8h+VirtualAddress]
0x140072910  mov     [rsp+0D8h+Irp], rcx; PVOID *
0x140072915  lea     r9, [rsp+0D8h+var_58+8]
0x14007291d  mov     rdx, r13
0x140072920  mov     rcx, [r8+r14*8+8]; FileObject
0x140072925  call    HsmFileCacheMapData
0x14007292a  mov     esi, eax
0x14007292c  mov     [rsp+0D8h+var_48], eax
0x140072933  mov     ecx, eax
0x140072935  call    HsmDbgBreakOnStatus
0x14007293a  test    esi, esi
0x14007293c  js      loc_140072AD8
0x140072942  mov     dword ptr [rsp+0D8h+var_58], 1
0x14007294d  cmp     dword ptr [rsp+0D8h+FileObject], 1000h
0x140072955  jnz     loc_140072C04
0x14007295b  mov     [rsp+0D8h+Irp], 0; Irp
0x140072964  xor     r9d, r9d; ChargeQuota
0x140072967  xor     r8d, r8d; SecondaryBuffer
0x14007296a  mov     edx, 1000h; Length
0x14007296f  mov     rcx, [rsp+0D8h+VirtualAddress]; VirtualAddress
0x140072974  call    cs:__imp_IoAllocateMdl
0x14007297b  nop     dword ptr [rax+rax+00h]
0x140072980  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140072985  mov     [rsp+0D8h+FileObject], rax
0x14007298a  test    rax, rax
0x14007298d  jz      loc_140072B35
0x140072993  xor     r8d, r8d; Operation
0x140072996  xor     edx, edx; AccessMode
0x140072998  mov     rcx, rax; MemoryDescriptorList
0x14007299b  call    cs:__imp_MmProbeAndLockPages
0x1400729a2  nop     dword ptr [rax+rax+00h]
0x1400729a7  mov     rax, [rsp+0D8h+MemoryDescriptorList]
0x1400729ac  jmp     short loc_1400729DE
0x1400729ae  lea     r12, WPP_GLOBAL_Control
0x1400729b5  mov     r13, [rsp+0D8h+arg_18]
0x1400729bd  mov     rbx, [rsp+0D8h+arg_0]
0x1400729c5  mov     esi, [rsp+0D8h+var_48]
0x1400729cc  mov     rax, [rsp+0D8h+FileObject]
0x1400729d1  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x1400729d6  mov     r14d, [rsp+0D8h+arg_8]
0x1400729de  test    esi, esi
0x1400729e0  js      loc_140072AF8
0x1400729e6  mov     r14, rax
0x1400729e9  movaps  xmm0, [rsp+0D8h+var_58]
0x1400729f1  movdqa  [rsp+0D8h+var_38], xmm0
0x1400729fa  lea     rcx, [rsp+0D8h+var_38]
0x140072a02  call    HsmIBitmapNORMALUnpinBlock
0x140072a07  mov     dword ptr [rsp+0D8h+var_58], 2
0x140072a12  mov     rax, [rsp+0D8h+MemoryDescriptorList]
0x140072a17  mov     qword ptr [rsp+0D8h+var_58+8], rax
0x140072a1f  xor     eax, eax
0x140072a21  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140072a26  test    byte ptr [r14+0Ah], 5
0x140072a2b  jnz     loc_140072B2C
0x140072a31  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x140072a39  mov     dword ptr [rsp+0D8h+Irp], eax; BugCheckOnFailure
0x140072a3d  xor     r9d, r9d; RequestedAddress
0x140072a40  xor     edx, edx; AccessMode
0x140072a42  lea     r8d, [rax+1]; CacheType
0x140072a46  mov     rcx, r14; MemoryDescriptorList
0x140072a49  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140072a50  nop     dword ptr [rax+rax+00h]
0x140072a55  mov     [rsp+0D8h+VirtualAddress], rax
0x140072a5a  test    rax, rax
0x140072a5d  jz      loc_140072C76
0x140072a63  mov     rcx, [rsp+0D8h+arg_20]
0x140072a6b  mov     rax, [rsp+0D8h+VirtualAddress]
0x140072a70  mov     [rcx], rax
0x140072a73  mov     [rsp+0D8h+VirtualAddress], 0
0x140072a7c  movaps  xmm0, [rsp+0D8h+var_58]
0x140072a84  mov     rax, [rsp+0D8h+arg_28]
0x140072a8c  movdqu  xmmword ptr [rax], xmm0
0x140072a90  mov     dword ptr [rsp+0D8h+var_58], 0
0x140072a9b  cmp     dword ptr [rsp+0D8h+var_58], 0
0x140072aa3  jnz     loc_140072FBB
0x140072aa9  mov     rax, [rsp+0D8h+MemoryDescriptorList]
0x140072aae  test    rax, rax
0x140072ab1  jnz     loc_140072FDE
0x140072ab7  mov     rcx, [rsp+0D8h+RetNewCallbackData]; CallbackData
0x140072abc  test    rcx, rcx
0x140072abf  jnz     loc_140072FF2
0x140072ac5  mov     eax, esi
0x140072ac7  add     rsp, 0B0h
0x140072ace  pop     r14
0x140072ad0  pop     r13
0x140072ad2  pop     r12
0x140072ad4  pop     rsi
0x140072ad5  pop     rbx
0x140072ad6  retn
0x140072ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x140072adf  cmp     rcx, r12
0x140072ae2  jz      short loc_140072A9B
0x140072ae4  mov     eax, [rcx+2Ch]
0x140072ae7  test    al, 1
0x140072ae9  jz      short loc_140072A9B
0x140072aeb  cmp     byte ptr [rcx+29h], 2
0x140072aef  jb      short loc_140072A9B
0x140072af1  mov     edx, 0Dh
0x140072af6  jmp     short loc_140072B16
0x140072af8  mov     rcx, cs:WPP_GLOBAL_Control
0x140072aff  cmp     rcx, r12
0x140072b02  jz      short loc_140072A9B
0x140072b04  mov     eax, [rcx+2Ch]
0x140072b07  test    al, 1
0x140072b09  jz      short loc_140072A9B
0x140072b0b  cmp     byte ptr [rcx+29h], 2
0x140072b0f  jb      short loc_140072A9B
0x140072b11  mov     edx, 10h
0x140072b16  mov     dword ptr [rsp+0D8h+var_90], esi
0x140072b1a  mov     [rsp+0D8h+var_98], r13
0x140072b1f  mov     dword ptr [rsp+0D8h+var_A0], 0FFFFFFFFh
0x140072b27  jmp     loc_140072BFD
0x140072b2c  mov     rax, [r14+18h]
0x140072b30  jmp     loc_140072A55
0x140072b35  mov     r14d, 0C000009Ah
0x140072b3b  mov     esi, r14d
0x140072b3e  mov     ecx, r14d
0x140072b41  call    HsmDbgBreakOnStatus
0x140072b46  mov     rcx, cs:WPP_GLOBAL_Control
0x140072b4d  cmp     rcx, r12
0x140072b50  jz      loc_140072A9B
0x140072b56  mov     eax, [rcx+2Ch]
0x140072b59  test    al, 1
0x140072b5b  jz      loc_140072A9B
0x140072b61  cmp     byte ptr [rcx+29h], 2
0x140072b65  jb      loc_140072A9B
0x140072b6b  mov     edx, 0Fh
0x140072b70  mov     dword ptr [rsp+0D8h+var_90], r14d
0x140072b75  mov     [rsp+0D8h+var_98], r13
0x140072b7a  mov     dword ptr [rsp+0D8h+var_A0], 0FFFFFFFFh
0x140072b82  mov     r8d, [rsp+0D8h+arg_8]
0x140072b8a  mov     [rsp+0D8h+var_A8], r8d
0x140072b8f  lea     rax, [rbx+20h]
0x140072b93  mov     qword ptr [rsp+0D8h+Priority], rax
0x140072b98  mov     rax, [rbx]
0x140072b9b  mov     [rsp+0D8h+Irp], rax
0x140072ba0  mov     r9, rbx
0x140072ba3  mov     rcx, [rcx+18h]
0x140072ba7  call    WPP_SF_qisddid
0x140072bac  jmp     loc_140072A9B
0x140072bb1  lea     rax, [rbx+20h]
0x140072bb5  mov     edx, 0Ch
0x140072bba  mov     [rsp+0D8h+var_A0], r13
0x140072bbf  mov     [rsp+0D8h+var_A8], r14d
0x140072bc4  mov     qword ptr [rsp+0D8h+Priority], rax
0x140072bc9  mov     rax, [rbx]
0x140072bcc  mov     [rsp+0D8h+Irp], rax
0x140072bd1  mov     r9, rbx
0x140072bd4  mov     rcx, [rcx+18h]
0x140072bd8  call    WPP_SF_qisdi
0x140072bdd  jmp     loc_1400728F1
0x140072be2  mov     edx, 14h
0x140072be7  mov     dword ptr [rsp+0D8h+var_90], esi
0x140072beb  mov     [rsp+0D8h+var_98], r13
0x140072bf0  mov     r8d, [rsp+0D8h+arg_10]
0x140072bf8  mov     dword ptr [rsp+0D8h+var_A0], r8d
0x140072bfd  mov     [rsp+0D8h+var_A8], r14d
0x140072c02  jmp     short loc_140072B8F
0x140072c04  mov     r13d, 0C00000E5h
0x140072c0a  mov     esi, r13d
0x140072c0d  mov     ecx, r13d
0x140072c10  call    HsmDbgBreakOnStatus
0x140072c15  mov     rcx, cs:WPP_GLOBAL_Control
0x140072c1c  cmp     rcx, r12
0x140072c1f  jz      loc_140072A9B
0x140072c25  mov     eax, [rcx+2Ch]
0x140072c28  test    al, 1
0x140072c2a  jz      loc_140072A9B
0x140072c30  cmp     byte ptr [rcx+29h], 2
0x140072c34  jb      loc_140072A9B
0x140072c3a  lea     rax, [rbx+20h]
0x140072c3e  mov     [rsp+0D8h+var_88], r13d
0x140072c43  mov     edx, dword ptr [rsp+0D8h+FileObject]
0x140072c47  mov     dword ptr [rsp+0D8h+var_98], edx
0x140072c4b  mov     dword ptr [rsp+0D8h+var_A0], 0FFFFFFFFh
0x140072c53  mov     [rsp+0D8h+var_A8], r14d
0x140072c58  mov     qword ptr [rsp+0D8h+Priority], rax
0x140072c5d  mov     rax, [rbx]
0x140072c60  mov     [rsp+0D8h+Irp], rax
0x140072c65  mov     r9, rbx
0x140072c68  mov     rcx, [rcx+18h]
0x140072c6c  call    WPP_SF_qisddDDd
0x140072c71  jmp     loc_140072A9B
0x140072c76  mov     r14d, 0C000009Ah
0x140072c7c  mov     esi, r14d
0x140072c7f  mov     ecx, r14d
0x140072c82  call    HsmDbgBreakOnStatus
0x140072c87  mov     rcx, cs:WPP_GLOBAL_Control
0x140072c8e  cmp     rcx, r12
0x140072c91  jz      loc_140072A9B
0x140072c97  mov     eax, [rcx+2Ch]
0x140072c9a  test    al, 1
0x140072c9c  jz      loc_140072A9B
0x140072ca2  cmp     byte ptr [rcx+29h], 2
0x140072ca6  jb      loc_140072A9B
0x140072cac  mov     edx, 11h
0x140072cb1  jmp     loc_140072B70
0x140072cb6  lea     rcx, [r14+r14*2]
0x140072cba  add     rcx, rsi
0x140072cbd  mov     qword ptr [rsp+0D8h+var_38], rcx
0x140072cc5  mov     rax, [r8+rcx*8+10h]
0x140072cca  mov     [rsp+0D8h+FileObject], rax
0x140072ccf  mov     esi, 1000h
0x140072cd4  mov     r8d, 6D427348h
0x140072cda  mov     edx, esi
0x140072cdc  mov     ecx, 40h ; '@'
0x140072ce1  call    cs:__imp_ExAllocatePool2
0x140072ce8  nop     dword ptr [rax+rax+00h]
0x140072ced  mov     [rsp+0D8h+VirtualAddress], rax
0x140072cf2  test    rax, rax
0x140072cf5  jnz     short loc_140072D55
0x140072cf7  mov     r14d, 0C000009Ah
0x140072cfd  mov     esi, r14d
0x140072d00  mov     ecx, r14d
0x140072d03  call    HsmDbgBreakOnStatus
0x140072d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140072d0f  cmp     rcx, r12
0x140072d12  jz      loc_140072A9B
0x140072d18  mov     eax, [rcx+2Ch]
0x140072d1b  test    al, 1
0x140072d1d  jz      loc_140072A9B
0x140072d23  cmp     byte ptr [rcx+29h], 2
0x140072d27  jb      loc_140072A9B
0x140072d2d  mov     edx, 12h
0x140072d32  jmp     short loc_140072D39
0x140072d34  mov     edx, 13h
0x140072d39  mov     dword ptr [rsp+0D8h+var_90], r14d
0x140072d3e  mov     [rsp+0D8h+var_98], r13
0x140072d43  mov     r8d, [rsp+0D8h+arg_10]
0x140072d4b  mov     dword ptr [rsp+0D8h+var_A0], r8d
0x140072d50  jmp     loc_140072B82
0x140072d55  mov     dword ptr [rsp+0D8h+var_58], 3
0x140072d60  mov     qword ptr [rsp+0D8h+var_58+8], rax
0x140072d68  mov     [rsp+0D8h+Irp], 0; Irp
0x140072d71  xor     r9d, r9d; ChargeQuota
0x140072d74  xor     r8d, r8d; SecondaryBuffer
0x140072d77  mov     edx, esi; Length
0x140072d79  mov     rcx, rax; VirtualAddress
0x140072d7c  call    cs:__imp_IoAllocateMdl
0x140072d83  nop     dword ptr [rax+rax+00h]
0x140072d88  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x140072d8d  test    rax, rax
0x140072d90  jnz     short loc_140072DCD
0x140072d92  mov     r14d, 0C000009Ah
0x140072d98  mov     esi, r14d
0x140072d9b  mov     ecx, r14d
0x140072d9e  call    HsmDbgBreakOnStatus
0x140072da3  mov     rcx, cs:WPP_GLOBAL_Control
0x140072daa  cmp     rcx, r12
0x140072dad  jz      loc_140072A9B
0x140072db3  mov     eax, [rcx+2Ch]
0x140072db6  test    al, 1
0x140072db8  jz      loc_140072A9B
0x140072dbe  cmp     byte ptr [rcx+29h], 2
0x140072dc2  jb      loc_140072A9B
0x140072dc8  jmp     loc_140072D34
0x140072dcd  mov     rcx, rax; MemoryDescriptorList
0x140072dd0  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140072dd7  nop     dword ptr [rax+rax+00h]
0x140072ddc  mov     rcx, [rbx+28h]
0x140072de0  lea     r8, [rsp+0D8h+RetNewCallbackData]; RetNewCallbackData
0x140072de5  mov     rdx, [rsp+0D8h+FileObject]; FileObject
0x140072dea  mov     rcx, [rcx+20h]; Instance
0x140072dee  call    cs:__imp_FltAllocateCallbackData
  ... truncated ...
```
