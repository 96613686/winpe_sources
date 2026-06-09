# AttachToRequestedDrives

- ea: `0x14000b010`
- end: `0x14000b497`
- name: `AttachToRequestedDrives`
- size: `1159`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003900`
- `0x14000b010`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b364`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b436`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b44b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b364`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b436`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b44b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da35`
- `ntoskrnl!ExAllocatePool2` at `0x14000b0d1`
- `ntoskrnl!ExAllocatePool2` at `0x14000b0d1`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000b2b2`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14000b2b2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b38f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b38f`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000b308`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14000b308`
- `ntoskrnl!DbgPrintEx` at `0x14000b05b`
- `ntoskrnl!DbgPrintEx` at `0x14000b187`
- `ntoskrnl!DbgPrintEx` at `0x14000b1bb`
- `ntoskrnl!DbgPrintEx` at `0x14000b24f`
- `ntoskrnl!DbgPrintEx` at `0x14000b297`
- `ntoskrnl!DbgPrintEx` at `0x14000b2e1`
- `ntoskrnl!DbgPrintEx` at `0x14000b33a`
- `ntoskrnl!DbgPrintEx` at `0x14000b379`
- `ntoskrnl!DbgPrintEx` at `0x14000b3e1`
- `ntoskrnl!DbgPrintEx` at `0x14000b477`
- `ntoskrnl!DbgPrintEx` at `0x14000b05b`
- `ntoskrnl!DbgPrintEx` at `0x14000b187`
- `ntoskrnl!DbgPrintEx` at `0x14000b1bb`
- `ntoskrnl!DbgPrintEx` at `0x14000b24f`
- `ntoskrnl!DbgPrintEx` at `0x14000b297`
- `ntoskrnl!DbgPrintEx` at `0x14000b2e1`
- `ntoskrnl!DbgPrintEx` at `0x14000b33a`
- `ntoskrnl!DbgPrintEx` at `0x14000b379`
- `ntoskrnl!DbgPrintEx` at `0x14000b3e1`
- `ntoskrnl!DbgPrintEx` at `0x14000b477`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000b45a`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000da48`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000b45a`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000da48`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000b275`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000b275`
- `FLTMGR!FltAttachVolume` at `0x14000b3ba`
- `FLTMGR!FltAttachVolume` at `0x14000b3ba`
- `FLTMGR!FltObjectDereference` at `0x14000b416`
- `FLTMGR!FltObjectDereference` at `0x14000b416`
- `FLTMGR!FltGetVolumeProperties` at `0x14000b1f8`
- `FLTMGR!FltGetVolumeProperties` at `0x14000b1f8`
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
  PFLT_VOLUME *Pool2; // rax
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
  Pool2 = (PFLT_VOLUME *)ExAllocatePool2(256, 8LL * NumberVolumesReturned, 1920224326);
  v9 = (PVOID *)Pool2;
  v23 = Pool2;
  if ( !Pool2 )
    goto LABEL_10;
  v10 = FltEnumerateVolumes(FltObject, Pool2, NumberVolumesReturned, &v19);
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
0x14000b0a1  jnz     loc_14000B443
0x14000b0a7  mov     [rsp+0E8h+var_C0], esi
0x14000b0ab  mov     [rsp+0E8h+var_C0], esi
0x14000b0af  mov     eax, [rsp+0E8h+NumberVolumesReturned]
0x14000b0b6  add     eax, 2
0x14000b0b9  mov     [rsp+0E8h+NumberVolumesReturned], eax
0x14000b0c0  mov     edx, eax
0x14000b0c2  shl     rdx, 3
0x14000b0c6  mov     ecx, 100h
0x14000b0cb  mov     r8d, 72744C46h
0x14000b0d1  call    cs:__imp_ExAllocatePool2
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
0x14000b149  jnz     loc_14000B42E
0x14000b14f  jmp     loc_14000B443
0x14000b154  mov     r15d, esi
0x14000b157  mov     [rsp+0E8h+var_C0], esi
0x14000b15b  mov     edi, 1
0x14000b160  lea     ebx, [rdi+1]
0x14000b163  cmp     r15d, [rsp+0E8h+NumberVolumesReturned]
0x14000b16b  jnb     loc_14000B401
0x14000b171  mov     dil, sil
0x14000b174  mov     [rsp+0E8h+var_C8], sil
0x14000b179  lea     r8, aCheckingVolume; "\tChecking Volume: "
0x14000b180  mov     edx, ebx; Level
0x14000b182  mov     ecx, 8Eh; ComponentId
0x14000b187  call    cs:__imp_DbgPrintEx
0x14000b18e  nop     dword ptr [rax+rax+00h]
0x14000b193  mov     eax, r15d
0x14000b196  lea     rsi, ds:0[rax*8]
0x14000b19e  bt      r12d, 1Ah
0x14000b1a3  jnb     short loc_14000B1CC
0x14000b1a5  mov     dil, 1
0x14000b1a8  mov     [rsp+0E8h+var_C8], dil
0x14000b1ad  lea     r8, aAllDrivesMask; "All drives mask "
0x14000b1b4  mov     edx, ebx; Level
0x14000b1b6  mov     ecx, 8Eh; ComponentId
0x14000b1bb  call    cs:__imp_DbgPrintEx
0x14000b1c2  nop     dword ptr [rax+rax+00h]
0x14000b1c7  jmp     loc_14000B3A4
0x14000b1cc  mov     [rsp+0E8h+LengthReturned], 0
0x14000b1d4  xor     edx, edx; Val
0x14000b1d6  lea     r8d, [rdx+48h]; Size
0x14000b1da  lea     rcx, [rsp+0E8h+VolumeProperties]; void *
0x14000b1df  call    memset
0x14000b1e4  lea     r9, [rsp+0E8h+LengthReturned]; LengthReturned
0x14000b1e9  mov     r8d, 48h ; 'H'; VolumePropertiesLength
0x14000b1ef  lea     rdx, [rsp+0E8h+VolumeProperties]; VolumeProperties
0x14000b1f4  mov     rcx, [rsi+r14]; Volume
0x14000b1f8  call    cs:__imp_FltGetVolumeProperties
0x14000b1ff  nop     dword ptr [rax+rax+00h]
0x14000b204  mov     [rsp+0E8h+var_C4], eax
0x14000b208  mov     edx, 80000000h
0x14000b20d  lea     ecx, [rax+rdx]
0x14000b210  test    edx, ecx
0x14000b212  jnz     short loc_14000B21B
0x14000b214  cmp     eax, 80000005h
0x14000b219  jnz     short loc_14000B25B
0x14000b21b  cmp     [rsp+0E8h+VolumeProperties.DeviceType], 14h
0x14000b220  jnz     short loc_14000B232
0x14000b222  bt      r12d, 1Ch
0x14000b227  jnb     short loc_14000B25B
0x14000b229  lea     r8, aNetworkDriveMa; "Network drive mask "
0x14000b230  jmp     short loc_14000B240
0x14000b232  bt      r12d, 1Bh
0x14000b237  jnb     short loc_14000B25B
0x14000b239  lea     r8, aLocalDriveMask; "Local drive mask "
0x14000b240  mov     dil, 1
0x14000b243  mov     edx, ebx; Level
0x14000b245  mov     ecx, 8Eh; ComponentId
0x14000b24a  mov     [rsp+0E8h+var_C8], dil
0x14000b24f  call    cs:__imp_DbgPrintEx
0x14000b256  nop     dword ptr [rax+rax+00h]
0x14000b25b  test    dil, dil
0x14000b25e  jnz     loc_14000B3A9
0x14000b264  xorps   xmm0, xmm0
0x14000b267  movups  xmmword ptr [rsp+0E8h+DosName.Length], xmm0
0x14000b26c  lea     rdx, [rsp+0E8h+DiskDeviceObject]; DiskDeviceObject
0x14000b271  mov     rcx, [rsi+r14]; Volume
0x14000b275  call    cs:__imp_FltGetDiskDeviceObject
0x14000b27c  nop     dword ptr [rax+rax+00h]
0x14000b281  mov     [rsp+0E8h+var_C4], eax
0x14000b285  test    eax, eax
0x14000b287  jns     short loc_14000B2A8
0x14000b289  lea     r8, aBadDeviceObjec; "Bad device object ->FAIL\n"
0x14000b290  mov     edx, ebx; Level
0x14000b292  mov     ecx, 8Eh; ComponentId
0x14000b297  call    cs:__imp_DbgPrintEx
0x14000b29e  nop     dword ptr [rax+rax+00h]
0x14000b2a3  jmp     loc_14000B3ED
0x14000b2a8  lea     rdx, [rsp+0E8h+DosName]; DosName
0x14000b2ad  mov     rcx, [rsp+0E8h+DiskDeviceObject]; VolumeDeviceObject
0x14000b2b2  call    cs:__imp_IoVolumeDeviceToDosName
0x14000b2b9  nop     dword ptr [rax+rax+00h]
0x14000b2be  mov     [rsp+0E8h+var_C4], eax
0x14000b2c2  mov     edx, ebx; Level
0x14000b2c4  mov     ecx, 8Eh; ComponentId
0x14000b2c9  test    eax, eax
0x14000b2cb  js      loc_14000B372
0x14000b2d1  mov     rax, [rsp+0E8h+DosName.Buffer]
0x14000b2d6  movzx   r9d, word ptr [rax]
0x14000b2da  lea     r8, aDriveLetterC; "Drive letter '%c' "
0x14000b2e1  call    cs:__imp_DbgPrintEx
0x14000b2e8  nop     dword ptr [rax+rax+00h]
0x14000b2ed  mov     eax, 1
0x14000b2f2  cmp     [rsp+0E8h+DosName.Length], ax
0x14000b2f7  jbe     short loc_14000B35D
0x14000b2f9  mov     rcx, [rsp+0E8h+DosName.Buffer]
0x14000b2fe  cmp     word ptr [rcx+2], 3Ah ; ':'
0x14000b303  jnz     short loc_14000B35D
0x14000b305  movzx   ecx, word ptr [rcx]; SourceCharacter
0x14000b308  call    cs:__imp_RtlUpcaseUnicodeChar
0x14000b30f  nop     dword ptr [rax+rax+00h]
0x14000b314  movzx   ecx, ax
0x14000b317  add     ecx, 0FFFFFFBFh
0x14000b31a  cmp     ecx, 19h
0x14000b31d  ja      short loc_14000B35D
0x14000b31f  mov     ebx, 1
0x14000b324  shl     ebx, cl
0x14000b326  mov     r9d, ebx
0x14000b329  lea     r8, aBitMask0xX; "Bit mask 0x%x "
0x14000b330  mov     edx, 2; Level
0x14000b335  mov     ecx, 8Eh; ComponentId
0x14000b33a  call    cs:__imp_DbgPrintEx
0x14000b341  nop     dword ptr [rax+rax+00h]
0x14000b346  test    r12d, ebx
0x14000b349  movzx   edi, dil
0x14000b34d  mov     eax, 1
0x14000b352  cmovnz  edi, eax
0x14000b355  mov     [rsp+0E8h+var_C8], dil
0x14000b35a  lea     ebx, [rax+1]
0x14000b35d  xor     edx, edx; Tag
0x14000b35f  mov     rcx, [rsp+0E8h+DosName.Buffer]; P
0x14000b364  call    cs:__imp_ExFreePoolWithTag
0x14000b36b  nop     dword ptr [rax+rax+00h]
0x14000b370  jmp     short loc_14000B385
0x14000b372  lea     r8, aBadVolumeName; "Bad volume name "
0x14000b379  call    cs:__imp_DbgPrintEx
0x14000b380  nop     dword ptr [rax+rax+00h]
0x14000b385  mov     rcx, [rsp+0E8h+DiskDeviceObject]; Object
0x14000b38a  test    rcx, rcx
0x14000b38d  jz      short loc_14000B3A4
0x14000b38f  call    cs:__imp_ObfDereferenceObject
0x14000b396  nop     dword ptr [rax+rax+00h]
0x14000b39b  mov     [rsp+0E8h+DiskDeviceObject], 0
0x14000b3a4  test    dil, dil
0x14000b3a7  jz      short loc_14000B3D3
0x14000b3a9  xor     r9d, r9d; RetInstance
0x14000b3ac  xor     r8d, r8d; InstanceName
0x14000b3af  mov     rdx, [rsi+r14]; Volume
0x14000b3b3  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x14000b3ba  call    cs:__imp_FltAttachVolume
0x14000b3c1  nop     dword ptr [rax+rax+00h]
0x14000b3c6  mov     [rsp+0E8h+var_C4], eax
0x14000b3ca  lea     r8, aPass; "->PASS\n"
0x14000b3d1  jmp     short loc_14000B3DA
0x14000b3d3  lea     r8, aFail; "->FAIL\n"
0x14000b3da  mov     edx, ebx; Level
0x14000b3dc  mov     ecx, 8Eh; ComponentId
0x14000b3e1  call    cs:__imp_DbgPrintEx
0x14000b3e8  nop     dword ptr [rax+rax+00h]
0x14000b3ed  mov     edi, 1
0x14000b3f2  add     r15d, edi
0x14000b3f5  mov     [rsp+0E8h+var_C0], r15d
0x14000b3fa  xor     esi, esi
0x14000b3fc  jmp     loc_14000B163
0x14000b401  mov     ebx, esi
0x14000b403  mov     [rsp+0E8h+var_C0], ebx
0x14000b407  cmp     ebx, [rsp+0E8h+NumberVolumesReturned]
0x14000b40e  jnb     short loc_14000B426
0x14000b410  mov     ecx, ebx
0x14000b412  mov     rcx, [r14+rcx*8]; FltObject
0x14000b416  call    cs:__imp_FltObjectDereference
0x14000b41d  nop     dword ptr [rax+rax+00h]
0x14000b422  add     ebx, edi
0x14000b424  jmp     short loc_14000B403
0x14000b426  mov     rdi, [rsp+0E8h+arg_0]
0x14000b42e  mov     edx, 72744C46h; Tag
0x14000b433  mov     rcx, r14; P
0x14000b436  call    cs:__imp_ExFreePoolWithTag
0x14000b43d  nop     dword ptr [rax+rax+00h]
0x14000b442  nop
0x14000b443  mov     edx, 72744C46h; Tag
0x14000b448  mov     rcx, r13; P
0x14000b44b  call    cs:__imp_ExFreePoolWithTag
0x14000b452  nop     dword ptr [rax+rax+00h]
0x14000b457  mov     rcx, rdi; FltWorkItem
0x14000b45a  call    cs:__imp_FltFreeGenericWorkItem
0x14000b461  nop     dword ptr [rax+rax+00h]
0x14000b466  lea     r8, aFiletraceAttac_0; "FileTrace!AttachToRequestedDrives: End"...
0x14000b46d  mov     edx, 2; Level
0x14000b472  mov     ecx, 8Eh; ComponentId
0x14000b477  call    cs:__imp_DbgPrintEx
0x14000b47e  nop     dword ptr [rax+rax+00h]
0x14000b483  add     rsp, 0B0h
0x14000b48a  pop     r15
0x14000b48c  pop     r14
0x14000b48e  pop     r13
0x14000b490  pop     r12
0x14000b492  pop     rdi
0x14000b493  pop     rsi
0x14000b494  pop     rbx
0x14000b495  retn
0x14000da20  push    rbp
0x14000da22  sub     rsp, 20h
0x14000da26  mov     rbp, rdx
0x14000da29  mov     edx, 72744C46h; Tag
0x14000da2e  mov     rcx, [rbp+100h]; P
0x14000da35  call    cs:__imp_ExFreePoolWithTag
0x14000da3c  nop     dword ptr [rax+rax+00h]
0x14000da41  mov     rcx, [rbp+0F0h]; FltWorkItem
0x14000da48  call    cs:__imp_FltFreeGenericWorkItem
0x14000da4f  nop     dword ptr [rax+rax+00h]
0x14000da54  nop
0x14000da55  add     rsp, 20h
0x14000da59  pop     rbp
0x14000da5a  retn
```
