# FTInstanceSetup

- ea: `0x14000d230`
- end: `0x14000d72e`
- name: `FTInstanceSetup`
- size: `1278`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140003600`
- `0x140003900`
- `0x14000d230`
- `0x14000d84c`

## import_xrefs

- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000d659`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000d659`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14000d6a2`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14000d6a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db40`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d392`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d5c9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d392`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d5c9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d320`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d3e5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d320`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000d3e5`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d29a`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000d29a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d6b9`
- `ntoskrnl!ObfDereferenceObject` at `0x14000daf9`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d6b9`
- `ntoskrnl!ObfDereferenceObject` at `0x14000daf9`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000d2ce`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000d2ce`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d366`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d425`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d366`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000d425`
- `FLTMGR!FltGetVolumeGuidName` at `0x14000d626`
- `FLTMGR!FltGetVolumeGuidName` at `0x14000d626`
- `FLTMGR!FltObjectReference` at `0x14000d3c4`
- `FLTMGR!FltObjectReference` at `0x14000d3c4`
- `FLTMGR!FltGetVolumeName` at `0x14000d582`
- `FLTMGR!FltGetVolumeName` at `0x14000d5fc`
- `FLTMGR!FltGetVolumeName` at `0x14000d582`
- `FLTMGR!FltGetVolumeName` at `0x14000d5fc`
- `FLTMGR!FltAllocateContext` at `0x14000d452`
- `FLTMGR!FltAllocateContext` at `0x14000d452`
- `FLTMGR!FltReleaseContext` at `0x14000d4a7`
- `FLTMGR!FltReleaseContext` at `0x14000d70c`
- `FLTMGR!FltReleaseContext` at `0x14000db56`
- `FLTMGR!FltReleaseContext` at `0x14000d4a7`
- `FLTMGR!FltReleaseContext` at `0x14000d70c`
- `FLTMGR!FltReleaseContext` at `0x14000db56`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000d27c`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000d27c`
- `FLTMGR!FltSetVolumeContext` at `0x14000d48b`
- `FLTMGR!FltSetVolumeContext` at `0x14000d48b`

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
  _QWORD *PoolWithTag; // rax
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
  _QWORD *v25; // [rsp+80h] [rbp-48h]
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
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x20u, 0x72744C46u);
  v5 = PoolWithTag;
  v25 = PoolWithTag;
  if ( !PoolWithTag )
    goto LABEL_22;
  v14 = *(void **)(a1 + 16);
  PoolWithTag[2] = v14;
  *((_DWORD *)PoolWithTag + 6) = v8;
  *((_DWORD *)PoolWithTag + 7) = a3;
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
          v16[1] = ExAllocatePoolWithTag((POOL_TYPE)512, BufferSizeNeeded, 0x72744C46u);
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
0x14000d230  mov     rax, rsp
0x14000d233  push    rbx
0x14000d234  push    rsi
0x14000d235  push    rdi
0x14000d236  push    r12
0x14000d238  push    r13
0x14000d23a  push    r14
0x14000d23c  push    r15
0x14000d23e  sub     rsp, 90h
0x14000d245  mov     r12d, r8d
0x14000d248  mov     r15, rcx
0x14000d24b  xor     r13d, r13d
0x14000d24e  mov     [rsp+0C8h+var_88], r13d
0x14000d253  mov     [rax-80h], r13
0x14000d257  mov     [rax-68h], r13
0x14000d25b  mov     [rax-78h], r13d
0x14000d25f  mov     [rax-50h], r13
0x14000d263  mov     esi, r13d
0x14000d266  mov     [rax-48h], r13
0x14000d26a  mov     edi, r13d
0x14000d26d  xorps   xmm0, xmm0
0x14000d270  movups  xmmword ptr [rax-60h], xmm0
0x14000d274  lea     rdx, [rax-68h]; DiskDeviceObject
0x14000d278  mov     rcx, [rcx+10h]; Volume
0x14000d27c  call    cs:__imp_FltGetDiskDeviceObject
0x14000d283  nop     dword ptr [rax+rax+00h]
0x14000d288  mov     [rsp+0C8h+var_88], eax
0x14000d28c  test    eax, eax
0x14000d28e  js      short loc_14000D2F7
0x14000d290  lea     rdx, [rsp+0C8h+DosName]; DosName
0x14000d295  mov     rcx, [rsp+0C8h+VolumeDeviceObject]; VolumeDeviceObject
0x14000d29a  call    cs:__imp_IoVolumeDeviceToDosName
0x14000d2a1  nop     dword ptr [rax+rax+00h]
0x14000d2a6  mov     [rsp+0C8h+var_88], eax
0x14000d2aa  test    eax, eax
0x14000d2ac  js      short loc_14000D2F7
0x14000d2ae  mov     rcx, [rsp+0C8h+DosName.Buffer]
0x14000d2b3  lea     r14d, [r13+1]
0x14000d2b7  test    rcx, rcx
0x14000d2ba  jz      short loc_14000D2F0
0x14000d2bc  cmp     [rsp+0C8h+DosName.Length], r14w
0x14000d2c2  jbe     short loc_14000D2FD
0x14000d2c4  cmp     word ptr [rcx+2], 3Ah ; ':'
0x14000d2c9  jnz     short loc_14000D2FD
0x14000d2cb  movzx   ecx, word ptr [rcx]; SourceCharacter
0x14000d2ce  call    cs:__imp_RtlUpcaseUnicodeChar
0x14000d2d5  nop     dword ptr [rax+rax+00h]
0x14000d2da  movzx   ecx, ax
0x14000d2dd  add     ecx, 0FFFFFFBFh
0x14000d2e0  cmp     ecx, 19h
0x14000d2e3  ja      short loc_14000D2FD
0x14000d2e5  mov     edi, r14d
0x14000d2e8  shl     edi, cl
0x14000d2ea  mov     [rsp+0C8h+var_74], edi
0x14000d2ee  jmp     short loc_14000D2FD
0x14000d2f0  mov     edi, 8
0x14000d2f5  jmp     short loc_14000D2EA
0x14000d2f7  mov     r14d, 1
0x14000d2fd  cmp     r12d, 14h
0x14000d301  jnz     short loc_14000D309
0x14000d303  bts     edi, 1Ch
0x14000d307  jmp     short loc_14000D30D
0x14000d309  bts     edi, 1Bh
0x14000d30d  mov     [rsp+0C8h+var_74], edi
0x14000d311  mov     [rsp+0C8h+var_70], r13d
0x14000d316  mov     bl, r13b
0x14000d319  lea     rcx, SessionLock; FastMutex
0x14000d320  call    cs:__imp_ExAcquireFastMutex
0x14000d327  nop     dword ptr [rax+rax+00h]
0x14000d32c  mov     edx, r13d
0x14000d32f  mov     [rsp+0C8h+var_70], edx
0x14000d333  cmp     edx, 8
0x14000d336  jge     short loc_14000D35F
0x14000d338  movsxd  rax, edx
0x14000d33b  lea     rcx, [rax+rax*4]
0x14000d33f  mov     rax, cs:LogSessions
0x14000d346  mov     r8d, [rax+rcx*8+20h]
0x14000d34b  bt      r8d, 1Ah
0x14000d350  jb      short loc_14000D35C
0x14000d352  test    edi, r8d
0x14000d355  jnz     short loc_14000D35C
0x14000d357  add     edx, r14d
0x14000d35a  jmp     short loc_14000D32F
0x14000d35c  mov     bl, r14b
0x14000d35f  lea     rcx, SessionLock; FastMutex
0x14000d366  call    cs:__imp_ExReleaseFastMutex
0x14000d36d  nop     dword ptr [rax+rax+00h]
0x14000d372  test    bl, bl
0x14000d374  jnz     short loc_14000D384
0x14000d376  mov     ebx, 0C0000001h
0x14000d37b  mov     [rsp+0C8h+var_88], ebx
0x14000d37f  jmp     loc_14000D6AF
0x14000d384  mov     edx, 20h ; ' '; NumberOfBytes
0x14000d389  mov     r8d, 72744C46h; Tag
0x14000d38f  mov     ecx, r14d; PoolType
0x14000d392  call    cs:__imp_ExAllocatePoolWithTag
0x14000d399  nop     dword ptr [rax+rax+00h]
0x14000d39e  mov     rsi, rax
0x14000d3a1  mov     [rsp+0C8h+var_48], rax
0x14000d3a9  test    rax, rax
0x14000d3ac  jnz     short loc_14000D3B5
0x14000d3ae  mov     ebx, 0C000009Ah
0x14000d3b3  jmp     short loc_14000D37B
0x14000d3b5  mov     rcx, [r15+10h]; FltObject
0x14000d3b9  mov     [rax+10h], rcx
0x14000d3bd  mov     [rax+18h], edi
0x14000d3c0  mov     [rax+1Ch], r12d
0x14000d3c4  call    cs:__imp_FltObjectReference
0x14000d3cb  nop     dword ptr [rax+rax+00h]
0x14000d3d0  mov     ebx, eax
0x14000d3d2  mov     [rsp+0C8h+var_88], eax
0x14000d3d6  test    eax, eax
0x14000d3d8  js      loc_14000D6AF
0x14000d3de  lea     rcx, FastMutex; FastMutex
0x14000d3e5  call    cs:__imp_ExAcquireFastMutex
0x14000d3ec  nop     dword ptr [rax+rax+00h]
0x14000d3f1  mov     rax, cs:P
0x14000d3f8  lea     rcx, P
0x14000d3ff  cmp     [rax+8], rcx
0x14000d403  jz      short loc_14000D40C
0x14000d405  mov     ecx, 3
0x14000d40a  int     29h; Win8: RtlFailFast(ecx)
0x14000d40c  mov     [rsi], rax
0x14000d40f  mov     [rsi+8], rcx
0x14000d413  mov     [rax+8], rsi
0x14000d417  mov     cs:P, rsi
0x14000d41e  lea     rcx, FastMutex; FastMutex
0x14000d425  call    cs:__imp_ExReleaseFastMutex
0x14000d42c  nop     dword ptr [rax+rax+00h]
0x14000d431  mov     edx, r14d; ContextType
0x14000d434  lea     rax, [rsp+0C8h+NewContext]
0x14000d439  mov     [rsp+0C8h+ReturnedContext], rax; ReturnedContext
0x14000d43e  mov     r9d, 200h; PoolType
0x14000d444  lea     r14d, [r9-8]
0x14000d448  mov     r8d, r14d; ContextSize
0x14000d44b  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000d452  call    cs:__imp_FltAllocateContext
0x14000d459  nop     dword ptr [rax+rax+00h]
0x14000d45e  mov     ebx, eax
0x14000d460  mov     [rsp+0C8h+var_88], eax
0x14000d464  test    eax, eax
0x14000d466  js      loc_14000D6AF
0x14000d46c  mov     r8d, r14d; Size
0x14000d46f  xor     edx, edx; Val
0x14000d471  mov     rcx, [rsp+0C8h+NewContext]; void *
0x14000d476  call    memset
0x14000d47b  lea     r9, [rsp+0C8h+OldContext]; OldContext
0x14000d480  mov     r8, [rsp+0C8h+NewContext]; NewContext
0x14000d485  xor     edx, edx; Operation
0x14000d487  mov     rcx, [r15+10h]; Volume
0x14000d48b  call    cs:__imp_FltSetVolumeContext
0x14000d492  nop     dword ptr [rax+rax+00h]
0x14000d497  mov     ebx, eax
0x14000d499  mov     [rsp+0C8h+var_88], eax
0x14000d49d  mov     rcx, [rsp+0C8h+OldContext]; Context
0x14000d4a2  test    rcx, rcx
0x14000d4a5  jz      short loc_14000D4B3
0x14000d4a7  call    cs:__imp_FltReleaseContext
0x14000d4ae  nop     dword ptr [rax+rax+00h]
0x14000d4b3  test    ebx, ebx
0x14000d4b5  js      loc_14000D6AF
0x14000d4bb  mov     rax, [rsp+0C8h+NewContext]
0x14000d4c0  mov     [rax+30h], r12d
0x14000d4c4  mov     rax, [rsp+0C8h+NewContext]
0x14000d4c9  mov     [rax+1E0h], edi
0x14000d4cf  mov     rcx, [rsp+0C8h+NewContext]
0x14000d4d4  lea     rax, [rcx+0B4h]
0x14000d4db  mov     [rcx+28h], rax
0x14000d4df  mov     rax, [rsp+0C8h+NewContext]
0x14000d4e4  mov     [rax+20h], r13w
0x14000d4e9  mov     r8d, 12Ch; Size
0x14000d4ef  mov     rax, [rsp+0C8h+NewContext]
0x14000d4f4  mov     [rax+22h], r8w
0x14000d4f9  mov     rcx, [rsp+0C8h+NewContext]
0x14000d4fe  add     rcx, 0B4h; void *
0x14000d505  xor     edx, edx; Val
0x14000d507  call    memset
0x14000d50c  movzx   eax, [rsp+0C8h+DosName.Length]
0x14000d511  test    ax, ax
0x14000d514  jz      short loc_14000D540
0x14000d516  mov     rcx, [rsp+0C8h+NewContext]
0x14000d51b  cmp     ax, [rcx+22h]
0x14000d51f  ja      short loc_14000D540
0x14000d521  mov     r8d, eax; Size
0x14000d524  mov     rdx, [rsp+0C8h+DosName.Buffer]; Src
0x14000d529  mov     rcx, [rcx+28h]; void *
0x14000d52d  call    memmove
0x14000d532  movzx   ecx, [rsp+0C8h+DosName.Length]
0x14000d537  mov     rax, [rsp+0C8h+NewContext]
0x14000d53c  mov     [rax+20h], cx
0x14000d540  mov     rcx, [rsp+0C8h+NewContext]
0x14000d545  lea     rax, [rcx+34h]
0x14000d549  mov     [rcx+18h], rax
0x14000d54d  mov     rax, [rsp+0C8h+NewContext]
0x14000d552  mov     [rax+10h], r13w
0x14000d557  mov     r8d, 80h; Size
0x14000d55d  mov     rax, [rsp+0C8h+NewContext]
0x14000d562  mov     [rax+12h], r8w
0x14000d567  mov     rcx, [rsp+0C8h+NewContext]
0x14000d56c  add     rcx, 34h ; '4'; void *
0x14000d570  xor     edx, edx; Val
0x14000d572  call    memset
0x14000d577  lea     r8, [rsp+0C8h+BufferSizeNeeded]; BufferSizeNeeded
0x14000d57c  xor     edx, edx; VolumeName
0x14000d57e  mov     rcx, [r15+10h]; Volume
0x14000d582  call    cs:__imp_FltGetVolumeName
0x14000d589  nop     dword ptr [rax+rax+00h]
0x14000d58e  mov     ebx, eax
0x14000d590  mov     [rsp+0C8h+var_88], eax
0x14000d594  mov     ecx, 80000000h
0x14000d599  add     eax, ecx
0x14000d59b  test    ecx, eax
0x14000d59d  jnz     short loc_14000D5AB
0x14000d59f  cmp     ebx, 0C0000023h
0x14000d5a5  jnz     loc_14000D6AF
0x14000d5ab  cmp     [rsp+0C8h+BufferSizeNeeded], 0FFFFh
0x14000d5b3  ja      short loc_14000D616
0x14000d5b5  mov     rbx, [rsp+0C8h+NewContext]
0x14000d5ba  mov     edx, [rsp+0C8h+BufferSizeNeeded]; NumberOfBytes
0x14000d5be  mov     ecx, 200h; PoolType
0x14000d5c3  mov     r8d, 72744C46h; Tag
0x14000d5c9  call    cs:__imp_ExAllocatePoolWithTag
0x14000d5d0  nop     dword ptr [rax+rax+00h]
0x14000d5d5  mov     [rbx+8], rax
0x14000d5d9  mov     rcx, [rsp+0C8h+NewContext]
0x14000d5de  cmp     [rcx+8], r13
0x14000d5e2  jz      loc_14000D3AE
0x14000d5e8  mov     eax, [rsp+0C8h+BufferSizeNeeded]
0x14000d5ec  mov     [rcx+2], ax
0x14000d5f0  xor     r8d, r8d; BufferSizeNeeded
0x14000d5f3  mov     rdx, [rsp+0C8h+NewContext]; VolumeName
0x14000d5f8  mov     rcx, [r15+10h]; Volume
0x14000d5fc  call    cs:__imp_FltGetVolumeName
0x14000d603  nop     dword ptr [rax+rax+00h]
0x14000d608  mov     ebx, eax
0x14000d60a  mov     [rsp+0C8h+var_88], eax
0x14000d60e  test    eax, eax
0x14000d610  js      loc_14000D6AF
0x14000d616  mov     rdx, [rsp+0C8h+NewContext]
0x14000d61b  add     rdx, 10h; VolumeGuidName
0x14000d61f  xor     r8d, r8d; BufferSizeNeeded
0x14000d622  mov     rcx, [r15+10h]; Volume
0x14000d626  call    cs:__imp_FltGetVolumeGuidName
0x14000d62d  nop     dword ptr [rax+rax+00h]
0x14000d632  mov     rcx, [rsp+0C8h+NewContext]; ObjectName
0x14000d637  cmp     [rcx+8], r13
0x14000d63b  jz      short loc_14000D6AF
0x14000d63d  mov     [rsp+0C8h+DeviceObject], r13
0x14000d645  lea     r8, [rcx+1F0h]; FileObject
0x14000d64c  lea     r9, [rsp+0C8h+DeviceObject]; DeviceObject
0x14000d654  mov     edx, 100000h; DesiredAccess
0x14000d659  call    cs:__imp_IoGetDeviceObjectPointer
0x14000d660  nop     dword ptr [rax+rax+00h]
0x14000d665  test    eax, eax
0x14000d667  js      short loc_14000D6AF
0x14000d669  mov     r8, [rsp+0C8h+NewContext]
0x14000d66e  lea     rax, [r8+1E8h]
0x14000d675  mov     [rsp+0C8h+NotificationEntry], rax; NotificationEntry
0x14000d67a  mov     rax, [r15+10h]
0x14000d67e  mov     [rsp+0C8h+Context], rax; Context
0x14000d683  lea     rax, DeviceChangeNotificationRoutine
0x14000d68a  mov     [rsp+0C8h+ReturnedContext], rax; CallbackRoutine
0x14000d68f  mov     r9, cs:WmiRegistrationContext.Dpc.DpcData; DriverObject
0x14000d696  mov     r8, [r8+1F0h]; EventCategoryData
0x14000d69d  xor     edx, edx; EventCategoryFlags
0x14000d69f  lea     ecx, [rdx+3]; EventCategory
0x14000d6a2  call    cs:__imp_IoRegisterPlugPlayNotification
0x14000d6a9  nop     dword ptr [rax+rax+00h]
0x14000d6ae  nop
0x14000d6af  mov     rcx, [rsp+0C8h+VolumeDeviceObject]; Object
0x14000d6b4  test    rcx, rcx
0x14000d6b7  jz      short loc_14000D6C5
0x14000d6b9  call    cs:__imp_ObfDereferenceObject
0x14000d6c0  nop     dword ptr [rax+rax+00h]
0x14000d6c5  mov     rcx, [rsp+0C8h+DosName.Buffer]; P
0x14000d6ca  test    rcx, rcx
0x14000d6cd  jz      short loc_14000D6DD
0x14000d6cf  xor     edx, edx; Tag
0x14000d6d1  call    cs:__imp_ExFreePoolWithTag
0x14000d6d8  nop     dword ptr [rax+rax+00h]
0x14000d6dd  test    ebx, ebx
0x14000d6df  jns     short loc_14000D702
0x14000d6e1  test    rsi, rsi
0x14000d6e4  jz      short loc_14000D702
0x14000d6e6  mov     rcx, rsi
0x14000d6e9  call    RemoveAttachedVolume
0x14000d6ee  mov     edx, 72744C46h; Tag
0x14000d6f3  mov     rcx, rsi; P
0x14000d6f6  call    cs:__imp_ExFreePoolWithTag
0x14000d6fd  nop     dword ptr [rax+rax+00h]
0x14000d702  mov     rcx, [rsp+0C8h+NewContext]; Context
0x14000d707  test    rcx, rcx
0x14000d70a  jz      short loc_14000D718
0x14000d70c  call    cs:__imp_FltReleaseContext
0x14000d713  nop     dword ptr [rax+rax+00h]
0x14000d718  mov     eax, ebx
0x14000d71a  add     rsp, 90h
0x14000d721  pop     r15
0x14000d723  pop     r14
0x14000d725  pop     r13
  ... truncated ...
```
