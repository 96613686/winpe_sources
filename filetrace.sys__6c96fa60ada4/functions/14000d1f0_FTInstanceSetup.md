# FTInstanceSetup

- ea: `0x14000d1f0`
- end: `0x14000d6f0`
- name: `FTInstanceSetup`
- size: `1280`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140003600`
- `0x140003900`
- `0x14000d1f0`
- `0x14000d80c`

## import_xrefs

- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000d61b`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000d61b`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14000d664`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14000d664`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d693`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d693`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dad1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db00`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d2e0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d3a7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d2e0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d3a7`
- `ntoskrnl!ExAllocatePool2` at `0x14000d354`
- `ntoskrnl!ExAllocatePool2` at `0x14000d58b`
- `ntoskrnl!ExAllocatePool2` at `0x14000d354`
- `ntoskrnl!ExAllocatePool2` at `0x14000d58b`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d25a`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d25a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d67b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dab9`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d67b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000dab9`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000d28e`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000d28e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d326`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d3e7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d326`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d3e7`
- `FLTMGR!FltGetVolumeGuidName` at `0x14000d5e8`
- `FLTMGR!FltGetVolumeGuidName` at `0x14000d5e8`
- `FLTMGR!FltObjectReference` at `0x14000d386`
- `FLTMGR!FltObjectReference` at `0x14000d386`
- `FLTMGR!FltGetVolumeName` at `0x14000d544`
- `FLTMGR!FltGetVolumeName` at `0x14000d5be`
- `FLTMGR!FltGetVolumeName` at `0x14000d544`
- `FLTMGR!FltGetVolumeName` at `0x14000d5be`
- `FLTMGR!FltAllocateContext` at `0x14000d414`
- `FLTMGR!FltAllocateContext` at `0x14000d414`
- `FLTMGR!FltReleaseContext` at `0x14000d469`
- `FLTMGR!FltReleaseContext` at `0x14000d6ce`
- `FLTMGR!FltReleaseContext` at `0x14000db16`
- `FLTMGR!FltReleaseContext` at `0x14000d469`
- `FLTMGR!FltReleaseContext` at `0x14000d6ce`
- `FLTMGR!FltReleaseContext` at `0x14000db16`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000d23c`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000d23c`
- `FLTMGR!FltSetVolumeContext` at `0x14000d44d`
- `FLTMGR!FltSetVolumeContext` at `0x14000d44d`

## pseudocode

```c
__int64 __fastcall FTInstanceSetup(__int64 a1, __int64 a2, int a3)
{
  _QWORD *v5; // rsi
  int v6; // edi
  unsigned int v7; // ecx
  int v8; // edi
  char v9; // bl
  int i; // edx
  int v11; // r8d
  NTSTATUS VolumeName; // ebx
  __int64 Pool2; // rax
  void *v14; // rcx
  _QWORD *v15; // rax
  _QWORD *v16; // rbx
  PFLT_CONTEXT NewContext; // [rsp+48h] [rbp-80h] BYREF
  ULONG BufferSizeNeeded; // [rsp+50h] [rbp-78h] BYREF
  int v20; // [rsp+54h] [rbp-74h]
  int v21; // [rsp+58h] [rbp-70h]
  PVOID VolumeDeviceObject; // [rsp+60h] [rbp-68h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+68h] [rbp-60h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+78h] [rbp-50h] BYREF
  __int64 v25; // [rsp+80h] [rbp-48h]
  PDEVICE_OBJECT DeviceObject; // [rsp+88h] [rbp-40h] BYREF

  NewContext = 0;
  VolumeDeviceObject = 0;
  BufferSizeNeeded = 0;
  OldContext = 0;
  v5 = 0;
  v25 = 0;
  v6 = 0;
  DosName = 0;
  if ( FltGetDiskDeviceObject(*(PFLT_VOLUME *)(a1 + 16), (PDEVICE_OBJECT *)&VolumeDeviceObject) < 0
    || IoVolumeDeviceToDosName(VolumeDeviceObject, &DosName) < 0 )
  {
    goto LABEL_10;
  }
  if ( DosName.Buffer )
  {
    if ( DosName.Length <= 1u )
      goto LABEL_10;
    if ( DosName.Buffer[1] != 58 )
      goto LABEL_10;
    v7 = RtlUpcaseUnicodeChar(*DosName.Buffer) - 65;
    if ( v7 > 0x19 )
      goto LABEL_10;
    v6 = 1 << v7;
  }
  else
  {
    v6 = 8;
  }
  v20 = v6;
LABEL_10:
  if ( a3 == 20 )
    v8 = v6 | 0x10000000;
  else
    v8 = v6 | 0x8000000;
  v20 = v8;
  v21 = 0;
  v9 = 0;
  ExAcquireFastMutex(&SessionLock);
  for ( i = 0; ; ++i )
  {
    v21 = i;
    if ( i >= 8 )
      break;
    v11 = *((_DWORD *)LogSessions + 10 * i + 8);
    if ( (v11 & 0x4000000) != 0 || (v11 & v8) != 0 )
    {
      v9 = 1;
      break;
    }
  }
  ExReleaseFastMutex(&SessionLock);
  if ( !v9 )
  {
    VolumeName = -1073741823;
    goto LABEL_41;
  }
  Pool2 = ExAllocatePool2(256, 32, 1920224326);
  v5 = (_QWORD *)Pool2;
  v25 = Pool2;
  if ( !Pool2 )
    goto LABEL_22;
  v14 = *(void **)(a1 + 16);
  *(_QWORD *)(Pool2 + 16) = v14;
  *(_DWORD *)(Pool2 + 24) = v8;
  *(_DWORD *)(Pool2 + 28) = a3;
  VolumeName = FltObjectReference(v14);
  if ( VolumeName >= 0 )
  {
    ExAcquireFastMutex(&FastMutex);
    v15 = P;
    if ( *((PVOID **)P + 1) != &P )
      __fastfail(3u);
    *v5 = P;
    v5[1] = &P;
    v15[1] = v5;
    P = v5;
    ExReleaseFastMutex(&FastMutex);
    VolumeName = FltAllocateContext(
                   (PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor,
                   1u,
                   0x1F8u,
                   (POOL_TYPE)512,
                   &NewContext);
    if ( VolumeName >= 0 )
    {
      memset(NewContext, 0, 0x1F8u);
      VolumeName = FltSetVolumeContext(
                     *(PFLT_VOLUME *)(a1 + 16),
                     FLT_SET_CONTEXT_REPLACE_IF_EXISTS,
                     NewContext,
                     &OldContext);
      if ( OldContext )
        FltReleaseContext(OldContext);
      if ( VolumeName >= 0 )
      {
        *((_DWORD *)NewContext + 12) = a3;
        *((_DWORD *)NewContext + 120) = v8;
        *((_QWORD *)NewContext + 5) = (char *)NewContext + 180;
        *((_WORD *)NewContext + 16) = 0;
        *((_WORD *)NewContext + 17) = 300;
        memset((char *)NewContext + 180, 0, 0x12Cu);
        if ( DosName.Length && DosName.Length <= *((_WORD *)NewContext + 17) )
        {
          memmove(*((void **)NewContext + 5), DosName.Buffer, DosName.Length);
          *((_WORD *)NewContext + 16) = DosName.Length;
        }
        *((_QWORD *)NewContext + 3) = (char *)NewContext + 52;
        *((_WORD *)NewContext + 8) = 0;
        *((_WORD *)NewContext + 9) = 128;
        memset((char *)NewContext + 52, 0, 0x80u);
        VolumeName = FltGetVolumeName(*(PFLT_VOLUME *)(a1 + 16), 0, &BufferSizeNeeded);
        if ( (int)(VolumeName + 0x80000000) < 0 || VolumeName == -1073741789 )
        {
          if ( BufferSizeNeeded > 0xFFFF )
            goto LABEL_38;
          v16 = NewContext;
          v16[1] = ExAllocatePool2(64, BufferSizeNeeded, 1920224326);
          if ( !*((_QWORD *)NewContext + 1) )
          {
LABEL_22:
            VolumeName = -1073741670;
            goto LABEL_41;
          }
          *((_WORD *)NewContext + 1) = BufferSizeNeeded;
          VolumeName = FltGetVolumeName(*(PFLT_VOLUME *)(a1 + 16), (PUNICODE_STRING)NewContext, 0);
          if ( VolumeName >= 0 )
          {
LABEL_38:
            FltGetVolumeGuidName(*(PFLT_VOLUME *)(a1 + 16), (PUNICODE_STRING)NewContext + 1, 0);
            if ( *((_QWORD *)NewContext + 1) )
            {
              DeviceObject = 0;
              if ( IoGetDeviceObjectPointer(
                     (PUNICODE_STRING)NewContext,
                     0x100000u,
                     (PFILE_OBJECT *)NewContext + 62,
                     &DeviceObject) >= 0 )
                IoRegisterPlugPlayNotification(
                  EventCategoryTargetDeviceChange,
                  0,
                  *((PVOID *)NewContext + 62),
                  (PDRIVER_OBJECT)WmiRegistrationContext.Dpc.DpcData,
                  DeviceChangeNotificationRoutine,
                  *(PVOID *)(a1 + 16),
                  (PVOID *)NewContext + 61);
            }
          }
        }
      }
    }
  }
LABEL_41:
  if ( VolumeDeviceObject )
    ObfDereferenceObject(VolumeDeviceObject);
  if ( DosName.Buffer )
    ExFreePoolWithTag(DosName.Buffer, 0);
  if ( VolumeName < 0 && v5 )
  {
    RemoveAttachedVolume((PVOID *)v5);
    ExFreePoolWithTag(v5, 0x72744C46u);
  }
  if ( NewContext )
    FltReleaseContext(NewContext);
  return (unsigned int)VolumeName;
}

```

## disassembly

```asm
0x14000d1f0  mov     rax, rsp
0x14000d1f3  push    rbx
0x14000d1f4  push    rsi
0x14000d1f5  push    rdi
0x14000d1f6  push    r12
0x14000d1f8  push    r13
0x14000d1fa  push    r14
0x14000d1fc  push    r15
0x14000d1fe  sub     rsp, 90h
0x14000d205  mov     r12d, r8d
0x14000d208  mov     r15, rcx
0x14000d20b  xor     r13d, r13d
0x14000d20e  mov     [rsp+0C8h+var_88], r13d
0x14000d213  mov     [rax-80h], r13
0x14000d217  mov     [rax-68h], r13
0x14000d21b  mov     [rax-78h], r13d
0x14000d21f  mov     [rax-50h], r13
0x14000d223  mov     esi, r13d
0x14000d226  mov     [rax-48h], r13
0x14000d22a  mov     edi, r13d
0x14000d22d  xorps   xmm0, xmm0
0x14000d230  movups  xmmword ptr [rax-60h], xmm0
0x14000d234  lea     rdx, [rax-68h]; DiskDeviceObject
0x14000d238  mov     rcx, [rcx+10h]; Volume
0x14000d23c  call    cs:__imp_FltGetDiskDeviceObject
0x14000d243  nop     dword ptr [rax+rax+00h]
0x14000d248  mov     [rsp+0C8h+var_88], eax
0x14000d24c  test    eax, eax
0x14000d24e  js      short loc_14000D2B7
0x14000d250  lea     rdx, [rsp+0C8h+DosName]; DosName
0x14000d255  mov     rcx, [rsp+0C8h+VolumeDeviceObject]; VolumeDeviceObject
0x14000d25a  call    cs:__imp_IoVolumeDeviceToDosName
0x14000d261  nop     dword ptr [rax+rax+00h]
0x14000d266  mov     [rsp+0C8h+var_88], eax
0x14000d26a  test    eax, eax
0x14000d26c  js      short loc_14000D2B7
0x14000d26e  mov     rcx, [rsp+0C8h+DosName.Buffer]
0x14000d273  lea     r14d, [r13+1]
0x14000d277  test    rcx, rcx
0x14000d27a  jz      short loc_14000D2B0
0x14000d27c  cmp     [rsp+0C8h+DosName.Length], r14w
0x14000d282  jbe     short loc_14000D2BD
0x14000d284  cmp     word ptr [rcx+2], 3Ah ; ':'
0x14000d289  jnz     short loc_14000D2BD
0x14000d28b  movzx   ecx, word ptr [rcx]; SourceCharacter
0x14000d28e  call    cs:__imp_RtlUpcaseUnicodeChar
0x14000d295  nop     dword ptr [rax+rax+00h]
0x14000d29a  movzx   ecx, ax
0x14000d29d  add     ecx, 0FFFFFFBFh
0x14000d2a0  cmp     ecx, 19h
0x14000d2a3  ja      short loc_14000D2BD
0x14000d2a5  mov     edi, r14d
0x14000d2a8  shl     edi, cl
0x14000d2aa  mov     [rsp+0C8h+var_74], edi
0x14000d2ae  jmp     short loc_14000D2BD
0x14000d2b0  mov     edi, 8
0x14000d2b5  jmp     short loc_14000D2AA
0x14000d2b7  mov     r14d, 1
0x14000d2bd  cmp     r12d, 14h
0x14000d2c1  jnz     short loc_14000D2C9
0x14000d2c3  bts     edi, 1Ch
0x14000d2c7  jmp     short loc_14000D2CD
0x14000d2c9  bts     edi, 1Bh
0x14000d2cd  mov     [rsp+0C8h+var_74], edi
0x14000d2d1  mov     [rsp+0C8h+var_70], r13d
0x14000d2d6  mov     bl, r13b
0x14000d2d9  lea     rcx, SessionLock; FastMutex
0x14000d2e0  call    cs:__imp_ExAcquireFastMutex
0x14000d2e7  nop     dword ptr [rax+rax+00h]
0x14000d2ec  mov     edx, r13d
0x14000d2ef  mov     [rsp+0C8h+var_70], edx
0x14000d2f3  cmp     edx, 8
0x14000d2f6  jge     short loc_14000D31F
0x14000d2f8  movsxd  rax, edx
0x14000d2fb  lea     rcx, [rax+rax*4]
0x14000d2ff  mov     rax, cs:LogSessions
0x14000d306  mov     r8d, [rax+rcx*8+20h]
0x14000d30b  bt      r8d, 1Ah
0x14000d310  jb      short loc_14000D31C
0x14000d312  test    edi, r8d
0x14000d315  jnz     short loc_14000D31C
0x14000d317  add     edx, r14d
0x14000d31a  jmp     short loc_14000D2EF
0x14000d31c  mov     bl, r14b
0x14000d31f  lea     rcx, SessionLock; FastMutex
0x14000d326  call    cs:__imp_ExReleaseFastMutex
0x14000d32d  nop     dword ptr [rax+rax+00h]
0x14000d332  test    bl, bl
0x14000d334  jnz     short loc_14000D344
0x14000d336  mov     ebx, 0C0000001h
0x14000d33b  mov     [rsp+0C8h+var_88], ebx
0x14000d33f  jmp     loc_14000D671
0x14000d344  mov     edx, 20h ; ' '
0x14000d349  mov     ecx, 100h
0x14000d34e  mov     r8d, 72744C46h
0x14000d354  call    cs:__imp_ExAllocatePool2
0x14000d35b  nop     dword ptr [rax+rax+00h]
0x14000d360  mov     rsi, rax
0x14000d363  mov     [rsp+0C8h+var_48], rax
0x14000d36b  test    rax, rax
0x14000d36e  jnz     short loc_14000D377
0x14000d370  mov     ebx, 0C000009Ah
0x14000d375  jmp     short loc_14000D33B
0x14000d377  mov     rcx, [r15+10h]; FltObject
0x14000d37b  mov     [rax+10h], rcx
0x14000d37f  mov     [rax+18h], edi
0x14000d382  mov     [rax+1Ch], r12d
0x14000d386  call    cs:__imp_FltObjectReference
0x14000d38d  nop     dword ptr [rax+rax+00h]
0x14000d392  mov     ebx, eax
0x14000d394  mov     [rsp+0C8h+var_88], eax
0x14000d398  test    eax, eax
0x14000d39a  js      loc_14000D671
0x14000d3a0  lea     rcx, FastMutex; FastMutex
0x14000d3a7  call    cs:__imp_ExAcquireFastMutex
0x14000d3ae  nop     dword ptr [rax+rax+00h]
0x14000d3b3  mov     rax, cs:P
0x14000d3ba  lea     rcx, P
0x14000d3c1  cmp     [rax+8], rcx
0x14000d3c5  jz      short loc_14000D3CE
0x14000d3c7  mov     ecx, 3
0x14000d3cc  int     29h; Win8: RtlFailFast(ecx)
0x14000d3ce  mov     [rsi], rax
0x14000d3d1  mov     [rsi+8], rcx
0x14000d3d5  mov     [rax+8], rsi
0x14000d3d9  mov     cs:P, rsi
0x14000d3e0  lea     rcx, FastMutex; FastMutex
0x14000d3e7  call    cs:__imp_ExReleaseFastMutex
0x14000d3ee  nop     dword ptr [rax+rax+00h]
0x14000d3f3  mov     edx, r14d; ContextType
0x14000d3f6  lea     rax, [rsp+0C8h+NewContext]
0x14000d3fb  mov     [rsp+0C8h+ReturnedContext], rax; ReturnedContext
0x14000d400  mov     r9d, 200h; PoolType
0x14000d406  lea     r14d, [r9-8]
0x14000d40a  mov     r8d, r14d; ContextSize
0x14000d40d  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000d414  call    cs:__imp_FltAllocateContext
0x14000d41b  nop     dword ptr [rax+rax+00h]
0x14000d420  mov     ebx, eax
0x14000d422  mov     [rsp+0C8h+var_88], eax
0x14000d426  test    eax, eax
0x14000d428  js      loc_14000D671
0x14000d42e  mov     r8d, r14d; Size
0x14000d431  xor     edx, edx; Val
0x14000d433  mov     rcx, [rsp+0C8h+NewContext]; void *
0x14000d438  call    memset
0x14000d43d  lea     r9, [rsp+0C8h+OldContext]; OldContext
0x14000d442  mov     r8, [rsp+0C8h+NewContext]; NewContext
0x14000d447  xor     edx, edx; Operation
0x14000d449  mov     rcx, [r15+10h]; Volume
0x14000d44d  call    cs:__imp_FltSetVolumeContext
0x14000d454  nop     dword ptr [rax+rax+00h]
0x14000d459  mov     ebx, eax
0x14000d45b  mov     [rsp+0C8h+var_88], eax
0x14000d45f  mov     rcx, [rsp+0C8h+OldContext]; Context
0x14000d464  test    rcx, rcx
0x14000d467  jz      short loc_14000D475
0x14000d469  call    cs:__imp_FltReleaseContext
0x14000d470  nop     dword ptr [rax+rax+00h]
0x14000d475  test    ebx, ebx
0x14000d477  js      loc_14000D671
0x14000d47d  mov     rax, [rsp+0C8h+NewContext]
0x14000d482  mov     [rax+30h], r12d
0x14000d486  mov     rax, [rsp+0C8h+NewContext]
0x14000d48b  mov     [rax+1E0h], edi
0x14000d491  mov     rcx, [rsp+0C8h+NewContext]
0x14000d496  lea     rax, [rcx+0B4h]
0x14000d49d  mov     [rcx+28h], rax
0x14000d4a1  mov     rax, [rsp+0C8h+NewContext]
0x14000d4a6  mov     [rax+20h], r13w
0x14000d4ab  mov     r8d, 12Ch; Size
0x14000d4b1  mov     rax, [rsp+0C8h+NewContext]
0x14000d4b6  mov     [rax+22h], r8w
0x14000d4bb  mov     rcx, [rsp+0C8h+NewContext]
0x14000d4c0  add     rcx, 0B4h; void *
0x14000d4c7  xor     edx, edx; Val
0x14000d4c9  call    memset
0x14000d4ce  movzx   eax, [rsp+0C8h+DosName.Length]
0x14000d4d3  test    ax, ax
0x14000d4d6  jz      short loc_14000D502
0x14000d4d8  mov     rcx, [rsp+0C8h+NewContext]
0x14000d4dd  cmp     ax, [rcx+22h]
0x14000d4e1  ja      short loc_14000D502
0x14000d4e3  mov     r8d, eax; Size
0x14000d4e6  mov     rdx, [rsp+0C8h+DosName.Buffer]; Src
0x14000d4eb  mov     rcx, [rcx+28h]; void *
0x14000d4ef  call    memmove
0x14000d4f4  movzx   ecx, [rsp+0C8h+DosName.Length]
0x14000d4f9  mov     rax, [rsp+0C8h+NewContext]
0x14000d4fe  mov     [rax+20h], cx
0x14000d502  mov     rcx, [rsp+0C8h+NewContext]
0x14000d507  lea     rax, [rcx+34h]
0x14000d50b  mov     [rcx+18h], rax
0x14000d50f  mov     rax, [rsp+0C8h+NewContext]
0x14000d514  mov     [rax+10h], r13w
0x14000d519  mov     r8d, 80h; Size
0x14000d51f  mov     rax, [rsp+0C8h+NewContext]
0x14000d524  mov     [rax+12h], r8w
0x14000d529  mov     rcx, [rsp+0C8h+NewContext]
0x14000d52e  add     rcx, 34h ; '4'; void *
0x14000d532  xor     edx, edx; Val
0x14000d534  call    memset
0x14000d539  lea     r8, [rsp+0C8h+BufferSizeNeeded]; BufferSizeNeeded
0x14000d53e  xor     edx, edx; VolumeName
0x14000d540  mov     rcx, [r15+10h]; Volume
0x14000d544  call    cs:__imp_FltGetVolumeName
0x14000d54b  nop     dword ptr [rax+rax+00h]
0x14000d550  mov     ebx, eax
0x14000d552  mov     [rsp+0C8h+var_88], eax
0x14000d556  mov     ecx, 80000000h
0x14000d55b  add     eax, ecx
0x14000d55d  test    ecx, eax
0x14000d55f  jnz     short loc_14000D56D
0x14000d561  cmp     ebx, 0C0000023h
0x14000d567  jnz     loc_14000D671
0x14000d56d  cmp     [rsp+0C8h+BufferSizeNeeded], 0FFFFh
0x14000d575  ja      short loc_14000D5D8
0x14000d577  mov     rbx, [rsp+0C8h+NewContext]
0x14000d57c  mov     edx, [rsp+0C8h+BufferSizeNeeded]
0x14000d580  mov     ecx, 40h ; '@'
0x14000d585  mov     r8d, 72744C46h
0x14000d58b  call    cs:__imp_ExAllocatePool2
0x14000d592  nop     dword ptr [rax+rax+00h]
0x14000d597  mov     [rbx+8], rax
0x14000d59b  mov     rcx, [rsp+0C8h+NewContext]
0x14000d5a0  cmp     [rcx+8], r13
0x14000d5a4  jz      loc_14000D370
0x14000d5aa  mov     eax, [rsp+0C8h+BufferSizeNeeded]
0x14000d5ae  mov     [rcx+2], ax
0x14000d5b2  xor     r8d, r8d; BufferSizeNeeded
0x14000d5b5  mov     rdx, [rsp+0C8h+NewContext]; VolumeName
0x14000d5ba  mov     rcx, [r15+10h]; Volume
0x14000d5be  call    cs:__imp_FltGetVolumeName
0x14000d5c5  nop     dword ptr [rax+rax+00h]
0x14000d5ca  mov     ebx, eax
0x14000d5cc  mov     [rsp+0C8h+var_88], eax
0x14000d5d0  test    eax, eax
0x14000d5d2  js      loc_14000D671
0x14000d5d8  mov     rdx, [rsp+0C8h+NewContext]
0x14000d5dd  add     rdx, 10h; VolumeGuidName
0x14000d5e1  xor     r8d, r8d; BufferSizeNeeded
0x14000d5e4  mov     rcx, [r15+10h]; Volume
0x14000d5e8  call    cs:__imp_FltGetVolumeGuidName
0x14000d5ef  nop     dword ptr [rax+rax+00h]
0x14000d5f4  mov     rcx, [rsp+0C8h+NewContext]; ObjectName
0x14000d5f9  cmp     [rcx+8], r13
0x14000d5fd  jz      short loc_14000D671
0x14000d5ff  mov     [rsp+0C8h+DeviceObject], r13
0x14000d607  lea     r8, [rcx+1F0h]; FileObject
0x14000d60e  lea     r9, [rsp+0C8h+DeviceObject]; DeviceObject
0x14000d616  mov     edx, 100000h; DesiredAccess
0x14000d61b  call    cs:__imp_IoGetDeviceObjectPointer
0x14000d622  nop     dword ptr [rax+rax+00h]
0x14000d627  test    eax, eax
0x14000d629  js      short loc_14000D671
0x14000d62b  mov     r8, [rsp+0C8h+NewContext]
0x14000d630  lea     rax, [r8+1E8h]
0x14000d637  mov     [rsp+0C8h+NotificationEntry], rax; NotificationEntry
0x14000d63c  mov     rax, [r15+10h]
0x14000d640  mov     [rsp+0C8h+Context], rax; Context
0x14000d645  lea     rax, DeviceChangeNotificationRoutine
0x14000d64c  mov     [rsp+0C8h+ReturnedContext], rax; CallbackRoutine
0x14000d651  mov     r9, cs:WmiRegistrationContext.Dpc.DpcData; DriverObject
0x14000d658  mov     r8, [r8+1F0h]; EventCategoryData
0x14000d65f  xor     edx, edx; EventCategoryFlags
0x14000d661  lea     ecx, [rdx+3]; EventCategory
0x14000d664  call    cs:__imp_IoRegisterPlugPlayNotification
0x14000d66b  nop     dword ptr [rax+rax+00h]
0x14000d670  nop
0x14000d671  mov     rcx, [rsp+0C8h+VolumeDeviceObject]; Object
0x14000d676  test    rcx, rcx
0x14000d679  jz      short loc_14000D687
0x14000d67b  call    cs:__imp_ObfDereferenceObject
0x14000d682  nop     dword ptr [rax+rax+00h]
0x14000d687  mov     rcx, [rsp+0C8h+DosName.Buffer]; P
0x14000d68c  test    rcx, rcx
0x14000d68f  jz      short loc_14000D69F
0x14000d691  xor     edx, edx; Tag
0x14000d693  call    cs:__imp_ExFreePoolWithTag
0x14000d69a  nop     dword ptr [rax+rax+00h]
0x14000d69f  test    ebx, ebx
0x14000d6a1  jns     short loc_14000D6C4
0x14000d6a3  test    rsi, rsi
0x14000d6a6  jz      short loc_14000D6C4
0x14000d6a8  mov     rcx, rsi
0x14000d6ab  call    RemoveAttachedVolume
0x14000d6b0  mov     edx, 72744C46h; Tag
0x14000d6b5  mov     rcx, rsi; P
0x14000d6b8  call    cs:__imp_ExFreePoolWithTag
0x14000d6bf  nop     dword ptr [rax+rax+00h]
0x14000d6c4  mov     rcx, [rsp+0C8h+NewContext]; Context
0x14000d6c9  test    rcx, rcx
0x14000d6cc  jz      short loc_14000D6DA
0x14000d6ce  call    cs:__imp_FltReleaseContext
0x14000d6d5  nop     dword ptr [rax+rax+00h]
0x14000d6da  mov     eax, ebx
0x14000d6dc  add     rsp, 90h
0x14000d6e3  pop     r15
0x14000d6e5  pop     r14
0x14000d6e7  pop     r13
  ... truncated ...
```
