# AttachToRequestedDrives

- ea: `0x14000b010`
- end: `0x14000b48f`
- name: `AttachToRequestedDrives`
- size: `1151`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003900`
- `0x14000b010`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b361`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b42e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b443`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b361`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b42e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b443`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da75`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b0d1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b0d1`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000b2af`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000b2af`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b38c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b38c`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000b305`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000b305`
- `ntoskrnl!DbgPrintEx` at `0x14000b05b`
- `ntoskrnl!DbgPrintEx` at `0x14000b184`
- `ntoskrnl!DbgPrintEx` at `0x14000b1b8`
- `ntoskrnl!DbgPrintEx` at `0x14000b24c`
- `ntoskrnl!DbgPrintEx` at `0x14000b294`
- `ntoskrnl!DbgPrintEx` at `0x14000b2de`
- `ntoskrnl!DbgPrintEx` at `0x14000b337`
- `ntoskrnl!DbgPrintEx` at `0x14000b376`
- `ntoskrnl!DbgPrintEx` at `0x14000b3de`
- `ntoskrnl!DbgPrintEx` at `0x14000b46f`
- `ntoskrnl!DbgPrintEx` at `0x14000b05b`
- `ntoskrnl!DbgPrintEx` at `0x14000b184`
- `ntoskrnl!DbgPrintEx` at `0x14000b1b8`
- `ntoskrnl!DbgPrintEx` at `0x14000b24c`
- `ntoskrnl!DbgPrintEx` at `0x14000b294`
- `ntoskrnl!DbgPrintEx` at `0x14000b2de`
- `ntoskrnl!DbgPrintEx` at `0x14000b337`
- `ntoskrnl!DbgPrintEx` at `0x14000b376`
- `ntoskrnl!DbgPrintEx` at `0x14000b3de`
- `ntoskrnl!DbgPrintEx` at `0x14000b46f`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000b452`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000da88`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000b452`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000da88`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000b272`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000b272`
- `FLTMGR!FltAttachVolume` at `0x14000b3b7`
- `FLTMGR!FltAttachVolume` at `0x14000b3b7`
- `FLTMGR!FltObjectDereference` at `0x14000b40e`
- `FLTMGR!FltObjectDereference` at `0x14000b40e`
- `FLTMGR!FltGetVolumeProperties` at `0x14000b1f5`
- `FLTMGR!FltGetVolumeProperties` at `0x14000b1f5`
- `FLTMGR!FltEnumerateVolumes` at `0x14000b080`
- `FLTMGR!FltEnumerateVolumes` at `0x14000b107`
- `FLTMGR!FltEnumerateVolumes` at `0x14000b080`
- `FLTMGR!FltEnumerateVolumes` at `0x14000b107`

## pseudocode

```c
void __fastcall AttachToRequestedDrives(PFLT_GENERIC_WORKITEM FltWorkItem, struct _FLT_FILTER *FltObject, int *Context)
{
  struct _FLT_GENERIC_WORKITEM *v5; // rdi
  int v6; // r12d
  NTSTATUS v7; // eax
  PFLT_VOLUME *PoolWithTag; // rax
  PVOID *v9; // r14
  NTSTATUS v10; // eax
  ULONG i; // r15d
  bool v12; // di
  __int64 v13; // rsi
  NTSTATUS v14; // eax
  const CHAR *v15; // r8
  unsigned int v16; // ecx
  int v17; // ebx
  ULONG j; // ebx
  ULONG v19; // [rsp+2Ch] [rbp-BCh] BYREF
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+30h] [rbp-B8h] BYREF
  ULONG LengthReturned; // [rsp+38h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+40h] [rbp-A8h] BYREF
  PFLT_VOLUME *v23; // [rsp+50h] [rbp-98h]
  _FLT_VOLUME_PROPERTIES VolumeProperties; // [rsp+60h] [rbp-88h] BYREF
  ULONG NumberVolumesReturned; // [rsp+108h] [rbp+20h] BYREF

  v5 = FltWorkItem;
  NumberVolumesReturned = 0;
  v19 = 0;
  DiskDeviceObject = 0;
  DosName = 0;
  DbgPrintEx(0x8Eu, 2u, "FileTrace!AttachToRequestedDrives: Start\n");
  v6 = *Context;
  v7 = FltEnumerateVolumes((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor, 0, 0, &NumberVolumesReturned);
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -1073741789 )
    goto LABEL_45;
  NumberVolumesReturned += 2;
  PoolWithTag = (PFLT_VOLUME *)ExAllocatePoolWithTag(PagedPool, 8LL * NumberVolumesReturned, 0x72744C46u);
  v9 = (PVOID *)PoolWithTag;
  v23 = PoolWithTag;
  if ( !PoolWithTag )
    goto LABEL_10;
  v10 = FltEnumerateVolumes(FltObject, PoolWithTag, NumberVolumesReturned, &v19);
  if ( v10 < 0 || v19 >= NumberVolumesReturned )
  {
    if ( v10 == -1073741789 )
      v10 = -1073741823;
  }
  else
  {
    NumberVolumesReturned = v19;
  }
  if ( v10 < 0 )
  {
LABEL_10:
    if ( v9 )
      goto LABEL_44;
    goto LABEL_45;
  }
  for ( i = 0; i < NumberVolumesReturned; ++i )
  {
    v12 = 0;
    DbgPrintEx(0x8Eu, 2u, "\tChecking Volume: ");
    v13 = i;
    if ( (v6 & 0x4000000) == 0 )
    {
      LengthReturned = 0;
      memset(&VolumeProperties, 0, sizeof(VolumeProperties));
      v14 = FltGetVolumeProperties((PFLT_VOLUME)v9[v13], &VolumeProperties, 0x48u, &LengthReturned);
      if ( (int)(v14 + 0x80000000) < 0 || v14 == -2147483643 )
      {
        if ( VolumeProperties.DeviceType == 20 )
        {
          if ( (v6 & 0x10000000) != 0 )
          {
            v15 = "Network drive mask ";
            goto LABEL_23;
          }
        }
        else if ( (v6 & 0x8000000) != 0 )
        {
          v15 = "Local drive mask ";
LABEL_23:
          v12 = 1;
          DbgPrintEx(0x8Eu, 2u, v15);
        }
      }
      if ( v12 )
        goto LABEL_37;
      DosName = 0;
      if ( FltGetDiskDeviceObject((PFLT_VOLUME)v9[v13], &DiskDeviceObject) < 0 )
      {
        DbgPrintEx(0x8Eu, 2u, "Bad device object ->FAIL\n");
        continue;
      }
      if ( IoVolumeDeviceToDosName(DiskDeviceObject, &DosName) < 0 )
      {
        DbgPrintEx(0x8Eu, 2u, "Bad volume name ");
      }
      else
      {
        DbgPrintEx(0x8Eu, 2u, "Drive letter '%c' ", *DosName.Buffer);
        if ( DosName.Length > 1u && DosName.Buffer[1] == 58 )
        {
          v16 = RtlUpcaseUnicodeChar(*DosName.Buffer) - 65;
          if ( v16 <= 0x19 )
          {
            v17 = 1 << v16;
            DbgPrintEx(0x8Eu, 2u, "Bit mask 0x%x ", 1 << v16);
            v12 = (v17 & v6) != 0;
          }
        }
        ExFreePoolWithTag(DosName.Buffer, 0);
      }
      if ( DiskDeviceObject )
      {
        ObfDereferenceObject(DiskDeviceObject);
        DiskDeviceObject = 0;
      }
      goto LABEL_36;
    }
    v12 = 1;
    DbgPrintEx(0x8Eu, 2u, "All drives mask ");
LABEL_36:
    if ( v12 )
    {
LABEL_37:
      FltAttachVolume((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor, (PFLT_VOLUME)v9[v13], 0, 0);
      DbgPrintEx(0x8Eu, 2u, "->PASS\n");
      continue;
    }
    DbgPrintEx(0x8Eu, 2u, "->FAIL\n");
  }
  for ( j = 0; j < NumberVolumesReturned; ++j )
    FltObjectDereference(v9[j]);
  v5 = FltWorkItem;
LABEL_44:
  ExFreePoolWithTag(v9, 0x72744C46u);
LABEL_45:
  ExFreePoolWithTag(Context, 0x72744C46u);
  FltFreeGenericWorkItem(v5);
  DbgPrintEx(0x8Eu, 2u, "FileTrace!AttachToRequestedDrives: End\n");
}

```

## disassembly

```asm
0x14000b010  mov     rax, rsp
0x14000b013  mov     [rax+18h], r8
0x14000b017  mov     [rax+8], rcx
0x14000b01b  push    rbx
0x14000b01c  push    rsi
0x14000b01d  push    rdi
0x14000b01e  push    r12
0x14000b020  push    r13
0x14000b022  push    r14
0x14000b024  push    r15
0x14000b026  sub     rsp, 0B0h
0x14000b02d  mov     r13, r8
0x14000b030  mov     rbx, rdx
0x14000b033  mov     rdi, rcx
0x14000b036  xor     esi, esi
0x14000b038  mov     [rax+20h], esi
0x14000b03b  mov     [rsp+0E8h+var_BC], esi
0x14000b03f  mov     [rsp+0E8h+DiskDeviceObject], rsi
0x14000b044  xorps   xmm0, xmm0
0x14000b047  movups  xmmword ptr [rsp+0E8h+DosName.Length], xmm0
0x14000b04c  lea     r8, Format; "FileTrace!AttachToRequestedDrives: Star"...
0x14000b053  lea     edx, [rsi+2]; Level
0x14000b056  mov     ecx, 8Eh; ComponentId
0x14000b05b  call    cs:__imp_DbgPrintEx
0x14000b062  nop     dword ptr [rax+rax+00h]
0x14000b067  nop
0x14000b068  mov     r12d, [r13+0]
0x14000b06c  lea     r9, [rsp+0E8h+NumberVolumesReturned]; NumberVolumesReturned
0x14000b074  xor     r8d, r8d; VolumeListSize
0x14000b077  xor     edx, edx; VolumeList
0x14000b079  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000b080  call    cs:__imp_FltEnumerateVolumes
0x14000b087  nop     dword ptr [rax+rax+00h]
0x14000b08c  mov     [rsp+0E8h+var_C4], eax
0x14000b090  mov     edx, 80000000h
0x14000b095  lea     ecx, [rax+rdx]
0x14000b098  test    edx, ecx
0x14000b09a  jnz     short loc_14000B0A7
0x14000b09c  cmp     eax, 0C0000023h
0x14000b0a1  jnz     loc_14000B43B
0x14000b0a7  mov     [rsp+0E8h+var_C0], esi
0x14000b0ab  mov     [rsp+0E8h+var_C0], esi
0x14000b0af  mov     eax, [rsp+0E8h+NumberVolumesReturned]
0x14000b0b6  add     eax, 2
0x14000b0b9  mov     [rsp+0E8h+NumberVolumesReturned], eax
0x14000b0c0  mov     edx, eax
0x14000b0c2  shl     rdx, 3; NumberOfBytes
0x14000b0c6  mov     ecx, 1; PoolType
0x14000b0cb  mov     r8d, 72744C46h; Tag
0x14000b0d1  call    cs:__imp_ExAllocatePoolWithTag
0x14000b0d8  nop     dword ptr [rax+rax+00h]
0x14000b0dd  mov     r14, rax
0x14000b0e0  mov     [rsp+0E8h+var_98], rax
0x14000b0e5  test    rax, rax
0x14000b0e8  jnz     short loc_14000B0F4
0x14000b0ea  mov     [rsp+0E8h+var_C4], 0C000009Ah
0x14000b0f2  jmp     short loc_14000B146
0x14000b0f4  lea     r9, [rsp+0E8h+var_BC]; NumberVolumesReturned
0x14000b0f9  mov     r8d, [rsp+0E8h+NumberVolumesReturned]; VolumeListSize
0x14000b101  mov     rdx, r14; VolumeList
0x14000b104  mov     rcx, rbx; Filter
0x14000b107  call    cs:__imp_FltEnumerateVolumes
0x14000b10e  nop     dword ptr [rax+rax+00h]
0x14000b113  mov     [rsp+0E8h+var_C4], eax
0x14000b117  test    eax, eax
0x14000b119  js      short loc_14000B131
0x14000b11b  mov     ecx, [rsp+0E8h+var_BC]
0x14000b11f  cmp     ecx, [rsp+0E8h+NumberVolumesReturned]
0x14000b126  jnb     short loc_14000B131
0x14000b128  mov     [rsp+0E8h+NumberVolumesReturned], ecx
0x14000b12f  jmp     short loc_14000B142
0x14000b131  mov     ecx, 0C0000001h
0x14000b136  cmp     eax, 0C0000023h
0x14000b13b  cmovz   eax, ecx
0x14000b13e  mov     [rsp+0E8h+var_C4], eax
0x14000b142  test    eax, eax
0x14000b144  jns     short loc_14000B154
0x14000b146  test    r14, r14
0x14000b149  jnz     loc_14000B426
0x14000b14f  jmp     loc_14000B43B
0x14000b154  mov     r15d, esi
0x14000b157  mov     [rsp+0E8h+var_C0], esi
0x14000b15b  mov     ebx, 2
0x14000b160  cmp     r15d, [rsp+0E8h+NumberVolumesReturned]
0x14000b168  jnb     loc_14000B3F9
0x14000b16e  mov     dil, sil
0x14000b171  mov     [rsp+0E8h+var_C8], sil
0x14000b176  lea     r8, aCheckingVolume; "\tChecking Volume: "
0x14000b17d  mov     edx, ebx; Level
0x14000b17f  mov     ecx, 8Eh; ComponentId
0x14000b184  call    cs:__imp_DbgPrintEx
0x14000b18b  nop     dword ptr [rax+rax+00h]
0x14000b190  mov     eax, r15d
0x14000b193  lea     rsi, ds:0[rax*8]
0x14000b19b  bt      r12d, 1Ah
0x14000b1a0  jnb     short loc_14000B1C9
0x14000b1a2  mov     dil, 1
0x14000b1a5  mov     [rsp+0E8h+var_C8], dil
0x14000b1aa  lea     r8, aAllDrivesMask; "All drives mask "
0x14000b1b1  mov     edx, ebx; Level
0x14000b1b3  mov     ecx, 8Eh; ComponentId
0x14000b1b8  call    cs:__imp_DbgPrintEx
0x14000b1bf  nop     dword ptr [rax+rax+00h]
0x14000b1c4  jmp     loc_14000B3A1
0x14000b1c9  mov     [rsp+0E8h+LengthReturned], 0
0x14000b1d1  xor     edx, edx; Val
0x14000b1d3  lea     r8d, [rdx+48h]; Size
0x14000b1d7  lea     rcx, [rsp+0E8h+VolumeProperties]; void *
0x14000b1dc  call    memset
0x14000b1e1  lea     r9, [rsp+0E8h+LengthReturned]; LengthReturned
0x14000b1e6  mov     r8d, 48h ; 'H'; VolumePropertiesLength
0x14000b1ec  lea     rdx, [rsp+0E8h+VolumeProperties]; VolumeProperties
0x14000b1f1  mov     rcx, [rsi+r14]; Volume
0x14000b1f5  call    cs:__imp_FltGetVolumeProperties
0x14000b1fc  nop     dword ptr [rax+rax+00h]
0x14000b201  mov     [rsp+0E8h+var_C4], eax
0x14000b205  mov     edx, 80000000h
0x14000b20a  lea     ecx, [rax+rdx]
0x14000b20d  test    edx, ecx
0x14000b20f  jnz     short loc_14000B218
0x14000b211  cmp     eax, 80000005h
0x14000b216  jnz     short loc_14000B258
0x14000b218  cmp     [rsp+0E8h+VolumeProperties.DeviceType], 14h
0x14000b21d  jnz     short loc_14000B22F
0x14000b21f  bt      r12d, 1Ch
0x14000b224  jnb     short loc_14000B258
0x14000b226  lea     r8, aNetworkDriveMa; "Network drive mask "
0x14000b22d  jmp     short loc_14000B23D
0x14000b22f  bt      r12d, 1Bh
0x14000b234  jnb     short loc_14000B258
0x14000b236  lea     r8, aLocalDriveMask; "Local drive mask "
0x14000b23d  mov     dil, 1
0x14000b240  mov     edx, ebx; Level
0x14000b242  mov     ecx, 8Eh; ComponentId
0x14000b247  mov     [rsp+0E8h+var_C8], dil
0x14000b24c  call    cs:__imp_DbgPrintEx
0x14000b253  nop     dword ptr [rax+rax+00h]
0x14000b258  test    dil, dil
0x14000b25b  jnz     loc_14000B3A6
0x14000b261  xorps   xmm0, xmm0
0x14000b264  movups  xmmword ptr [rsp+0E8h+DosName.Length], xmm0
0x14000b269  lea     rdx, [rsp+0E8h+DiskDeviceObject]; DiskDeviceObject
0x14000b26e  mov     rcx, [rsi+r14]; Volume
0x14000b272  call    cs:__imp_FltGetDiskDeviceObject
0x14000b279  nop     dword ptr [rax+rax+00h]
0x14000b27e  mov     [rsp+0E8h+var_C4], eax
0x14000b282  test    eax, eax
0x14000b284  jns     short loc_14000B2A5
0x14000b286  lea     r8, aBadDeviceObjec; "Bad device object ->FAIL\n"
0x14000b28d  mov     edx, ebx; Level
0x14000b28f  mov     ecx, 8Eh; ComponentId
0x14000b294  call    cs:__imp_DbgPrintEx
0x14000b29b  nop     dword ptr [rax+rax+00h]
0x14000b2a0  jmp     loc_14000B3EA
0x14000b2a5  lea     rdx, [rsp+0E8h+DosName]; DosName
0x14000b2aa  mov     rcx, [rsp+0E8h+DiskDeviceObject]; VolumeDeviceObject
0x14000b2af  call    cs:__imp_IoVolumeDeviceToDosName
0x14000b2b6  nop     dword ptr [rax+rax+00h]
0x14000b2bb  mov     [rsp+0E8h+var_C4], eax
0x14000b2bf  mov     edx, ebx; Level
0x14000b2c1  mov     ecx, 8Eh; ComponentId
0x14000b2c6  test    eax, eax
0x14000b2c8  js      loc_14000B36F
0x14000b2ce  mov     rax, [rsp+0E8h+DosName.Buffer]
0x14000b2d3  movzx   r9d, word ptr [rax]
0x14000b2d7  lea     r8, aDriveLetterC; "Drive letter '%c' "
0x14000b2de  call    cs:__imp_DbgPrintEx
0x14000b2e5  nop     dword ptr [rax+rax+00h]
0x14000b2ea  mov     eax, 1
0x14000b2ef  cmp     [rsp+0E8h+DosName.Length], ax
0x14000b2f4  jbe     short loc_14000B35A
0x14000b2f6  mov     rcx, [rsp+0E8h+DosName.Buffer]
0x14000b2fb  cmp     word ptr [rcx+2], 3Ah ; ':'
0x14000b300  jnz     short loc_14000B35A
0x14000b302  movzx   ecx, word ptr [rcx]; SourceCharacter
0x14000b305  call    cs:__imp_RtlUpcaseUnicodeChar
0x14000b30c  nop     dword ptr [rax+rax+00h]
0x14000b311  movzx   ecx, ax
0x14000b314  add     ecx, 0FFFFFFBFh
0x14000b317  cmp     ecx, 19h
0x14000b31a  ja      short loc_14000B35A
0x14000b31c  mov     ebx, 1
0x14000b321  shl     ebx, cl
0x14000b323  mov     r9d, ebx
0x14000b326  lea     r8, aBitMask0xX; "Bit mask 0x%x "
0x14000b32d  mov     edx, 2; Level
0x14000b332  mov     ecx, 8Eh; ComponentId
0x14000b337  call    cs:__imp_DbgPrintEx
0x14000b33e  nop     dword ptr [rax+rax+00h]
0x14000b343  test    r12d, ebx
0x14000b346  movzx   edi, dil
0x14000b34a  mov     eax, 1
0x14000b34f  cmovnz  edi, eax
0x14000b352  mov     [rsp+0E8h+var_C8], dil
0x14000b357  lea     ebx, [rax+1]
0x14000b35a  xor     edx, edx; Tag
0x14000b35c  mov     rcx, [rsp+0E8h+DosName.Buffer]; P
0x14000b361  call    cs:__imp_ExFreePoolWithTag
0x14000b368  nop     dword ptr [rax+rax+00h]
0x14000b36d  jmp     short loc_14000B382
0x14000b36f  lea     r8, aBadVolumeName; "Bad volume name "
0x14000b376  call    cs:__imp_DbgPrintEx
0x14000b37d  nop     dword ptr [rax+rax+00h]
0x14000b382  mov     rcx, [rsp+0E8h+DiskDeviceObject]; Object
0x14000b387  test    rcx, rcx
0x14000b38a  jz      short loc_14000B3A1
0x14000b38c  call    cs:__imp_ObfDereferenceObject
0x14000b393  nop     dword ptr [rax+rax+00h]
0x14000b398  mov     [rsp+0E8h+DiskDeviceObject], 0
0x14000b3a1  test    dil, dil
0x14000b3a4  jz      short loc_14000B3D0
0x14000b3a6  xor     r9d, r9d; RetInstance
0x14000b3a9  xor     r8d, r8d; InstanceName
0x14000b3ac  mov     rdx, [rsi+r14]; Volume
0x14000b3b0  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000b3b7  call    cs:__imp_FltAttachVolume
0x14000b3be  nop     dword ptr [rax+rax+00h]
0x14000b3c3  mov     [rsp+0E8h+var_C4], eax
0x14000b3c7  lea     r8, aPass; "->PASS\n"
0x14000b3ce  jmp     short loc_14000B3D7
0x14000b3d0  lea     r8, aFail; "->FAIL\n"
0x14000b3d7  mov     edx, ebx; Level
0x14000b3d9  mov     ecx, 8Eh; ComponentId
0x14000b3de  call    cs:__imp_DbgPrintEx
0x14000b3e5  nop     dword ptr [rax+rax+00h]
0x14000b3ea  inc     r15d
0x14000b3ed  mov     [rsp+0E8h+var_C0], r15d
0x14000b3f2  xor     esi, esi
0x14000b3f4  jmp     loc_14000B160
0x14000b3f9  mov     ebx, esi
0x14000b3fb  mov     [rsp+0E8h+var_C0], ebx
0x14000b3ff  cmp     ebx, [rsp+0E8h+NumberVolumesReturned]
0x14000b406  jnb     short loc_14000B41E
0x14000b408  mov     ecx, ebx
0x14000b40a  mov     rcx, [r14+rcx*8]; FltObject
0x14000b40e  call    cs:__imp_FltObjectDereference
0x14000b415  nop     dword ptr [rax+rax+00h]
0x14000b41a  inc     ebx
0x14000b41c  jmp     short loc_14000B3FB
0x14000b41e  mov     rdi, [rsp+0E8h+arg_0]
0x14000b426  mov     edx, 72744C46h; Tag
0x14000b42b  mov     rcx, r14; P
0x14000b42e  call    cs:__imp_ExFreePoolWithTag
0x14000b435  nop     dword ptr [rax+rax+00h]
0x14000b43a  nop
0x14000b43b  mov     edx, 72744C46h; Tag
0x14000b440  mov     rcx, r13; P
0x14000b443  call    cs:__imp_ExFreePoolWithTag
0x14000b44a  nop     dword ptr [rax+rax+00h]
0x14000b44f  mov     rcx, rdi; FltWorkItem
0x14000b452  call    cs:__imp_FltFreeGenericWorkItem
0x14000b459  nop     dword ptr [rax+rax+00h]
0x14000b45e  lea     r8, aFiletraceAttac_0; "FileTrace!AttachToRequestedDrives: End"...
0x14000b465  mov     edx, 2; Level
0x14000b46a  mov     ecx, 8Eh; ComponentId
0x14000b46f  call    cs:__imp_DbgPrintEx
0x14000b476  nop     dword ptr [rax+rax+00h]
0x14000b47b  add     rsp, 0B0h
0x14000b482  pop     r15
0x14000b484  pop     r14
0x14000b486  pop     r13
0x14000b488  pop     r12
0x14000b48a  pop     rdi
0x14000b48b  pop     rsi
0x14000b48c  pop     rbx
0x14000b48d  retn
0x14000da60  push    rbp
0x14000da62  sub     rsp, 20h
0x14000da66  mov     rbp, rdx
0x14000da69  mov     edx, 72744C46h; Tag
0x14000da6e  mov     rcx, [rbp+100h]; P
0x14000da75  call    cs:__imp_ExFreePoolWithTag
0x14000da7c  nop     dword ptr [rax+rax+00h]
0x14000da81  mov     rcx, [rbp+0F0h]; FltWorkItem
0x14000da88  call    cs:__imp_FltFreeGenericWorkItem
0x14000da8f  nop     dword ptr [rax+rax+00h]
0x14000da94  nop
0x14000da95  add     rsp, 20h
0x14000da99  pop     rbp
0x14000da9a  retn
```
