# NtfsWalkDownTreeOnDisk

- ea: `0x140201468`
- end: `0x140201d3f`
- name: `NtfsWalkDownTreeOnDisk`
- size: `2263`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140017480`
- `0x140202288`

## callees

- `0x140007ea0`
- `0x1400593c0`
- `0x1400596c0`
- `0x140201468`
- `0x140201d50`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140201949`
- `ntoskrnl!ZwClose` at `0x140201cf8`
- `ntoskrnl!ZwClose` at `0x140201d1c`
- `ntoskrnl!ZwClose` at `0x1402b349d`
- `ntoskrnl!ZwClose` at `0x1402b34ee`
- `ntoskrnl!ZwClose` at `0x140201949`
- `ntoskrnl!ZwClose` at `0x140201cf8`
- `ntoskrnl!ZwClose` at `0x140201d1c`
- `ntoskrnl!ZwClose` at `0x1402b349d`
- `ntoskrnl!ZwClose` at `0x1402b34ee`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140201ac6`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140201ac6`
- `ntoskrnl!IoFileObjectType` at `0x14020151f`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14020153a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14020153a`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x1402016be`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x1402016be`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140201752`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140201752`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402015a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402015a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201c54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201cd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201d0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b34af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b34d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201c54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201cd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201d0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b34af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b34d5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402018c8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140201a1e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402018c8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140201a1e`

## pseudocode

```c
__int64 __fastcall NtfsWalkDownTreeOnDisk(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PVOID FileInformation)
{
  void *v7; // r12
  __int64 v8; // r15
  unsigned int v9; // r14d
  unsigned int v10; // esi
  int v11; // eax
  NTSTATUS v12; // ebx
  _DWORD *v13; // rdi
  __int64 v14; // rdi
  unsigned int v15; // ecx
  NTSTATUS v16; // eax
  int Information; // eax
  __int64 v18; // r14
  unsigned int v19; // eax
  int v20; // eax
  int v21; // ecx
  _QWORD *PoolWithTag; // rax
  _QWORD *v23; // rdi
  __int64 v24; // r8
  __int64 v25; // rcx
  int v26; // edx
  _DWORD *v27; // rax
  HANDLE *v29; // rdi
  char v30; // [rsp+80h] [rbp-B8h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-90h] BYREF
  _QWORD *v33; // [rsp+B0h] [rbp-88h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-70h] BYREF
  unsigned int v36; // [rsp+F8h] [rbp-40h]
  __int64 v37; // [rsp+100h] [rbp-38h]
  int v39; // [rsp+158h] [rbp+20h]
  int v40; // [rsp+160h] [rbp+28h]

  v37 = *(_QWORD *)(a1 + 104);
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  Handle = 0;
  v7 = 0;
  v33 = 0;
  LODWORD(v8) = 0;
  v9 = 0x10000;
  v39 = 0x10000;
  v10 = 0;
  v40 = 0;
  v11 = *(_DWORD *)(a1 + 4);
  if ( (v11 & 0x200) == 0 )
  {
    v40 = 512;
    *(_DWORD *)(a1 + 4) = v11 | 0x200;
  }
  if ( !a3 || !*(_BYTE *)(a3 + 68) )
  {
    v12 = ObOpenObjectByPointer(a2, 0x200u, 0, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Handle);
    if ( v12 < 0 )
      goto LABEL_94;
LABEL_5:
    if ( a3 && *(_BYTE *)(a3 + 68) )
    {
      v12 = -1073741536;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_94;
      v24 = 1004982;
      goto LABEL_68;
    }
    if ( (_DWORD)v8 == v10 )
    {
      PoolWithTag = ExAllocatePoolWithTag(PoolType, 8LL * (unsigned int)(v8 + 3), 0x4646744Eu);
      v23 = PoolWithTag;
      if ( !PoolWithTag )
      {
        v12 = -1073741670;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_94;
        v24 = 1005001;
LABEL_68:
        NtfsStatusTraceAndDebugInternal(0, (unsigned int)v12, v24);
        goto LABEL_94;
      }
      if ( (_DWORD)v8 )
      {
        memmove(PoolWithTag, v7, 8LL * (unsigned int)v8);
        ExFreePoolWithTag(v7, 0);
      }
      *(_OWORD *)&v23[(unsigned int)v8] = 0;
      v23[(unsigned int)v8 + 2] = 0;
      v7 = v23;
      v33 = v23;
      LODWORD(v8) = v8 + 3;
      v9 = v39;
    }
    v13 = (_DWORD *)*((_QWORD *)v7 + v10);
    if ( !v13 )
    {
      do
      {
        v27 = ExAllocatePoolWithTag(PoolType, v9, 0x4646744Eu);
        v13 = v27;
        if ( v27 )
          break;
        v9 >>= 1;
        v39 = v9;
        v36 = v9;
      }
      while ( v9 > 0x1000 );
      if ( !v27 )
      {
        v12 = -1073741670;
        if ( NtfsStatusDebugFlags )
        {
          v24 = 1005039;
          goto LABEL_68;
        }
        goto LABEL_94;
      }
      memset(v27, 0, v9);
      v13[2] = v9 - 20;
      *((_QWORD *)v7 + v10) = v13;
    }
    if ( ++v10 == 1 )
    {
      RtlInitUnicodeString(&DestinationString, 0);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    }
    else
    {
      v13 = (_DWORD *)*((_QWORD *)v7 + v10 - 2);
      v25 = (unsigned int)v13[4];
      DestinationString.Buffer = (PWSTR)((char *)v13 + v25 + 88);
      DestinationString.MaximumLength = *(_WORD *)((char *)v13 + v25 + 80);
      DestinationString.Length = DestinationString.MaximumLength;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = *(HANDLE *)v13;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v26 = *(_DWORD *)((char *)v13 + v25 + 20);
      if ( v26 )
        v13[4] += v26;
      else
        v13[4] = v13[3];
    }
    if ( v10 != 1 )
      v12 = NtfsInheritStorageReserveId(a1, *(_QWORD *)v13, (int)&DestinationString, 4, FileInformation);
    if ( v12 < 0 )
    {
      if ( NtfsStatusDebugFlags
        && (unsigned int)v12 < 0xFFFFFFED
        && v12 != -1073741802
        && v12 != -1073741807
        && (unsigned int)(v12 + 2147483643) > 1
        && v12 != -1073741608 )
      {
        v24 = 1005126;
        goto LABEL_68;
      }
    }
    else
    {
      v12 = IoCreateFileSpecifyDeviceObjectHint(
              *((PHANDLE *)v7 + v10 - 1),
              0x100001u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              7u,
              1u,
              0x200021u,
              0,
              0,
              CreateFileTypeNone,
              0,
              0x900u,
              *(PVOID *)(*(_QWORD *)(v37 + 248) + 8LL));
      if ( v12 >= 0 )
      {
        v30 = 0;
        while ( !a3 || !*(_BYTE *)(a3 + 68) )
        {
          v14 = *((_QWORD *)v7 + v10 - 1);
          v15 = *(_DWORD *)(v14 + 16);
          if ( v15 != *(_DWORD *)(v14 + 12) )
          {
            while ( 1 )
            {
LABEL_22:
              if ( a3 && *(_BYTE *)(a3 + 68) )
              {
                v12 = -1073741536;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_94;
                v24 = 1005272;
                goto LABEL_68;
              }
              v18 = v15;
              v19 = *(_DWORD *)(v15 + v14 + 80);
              if ( v19 > 4 || *(_WORD *)(v15 + v14 + 88) != 46 || v19 == 4 && *(_WORD *)(v15 + v14 + 90) != 46 )
              {
                v20 = *(_DWORD *)(v15 + v14 + 76);
                if ( (v20 & 0x10) != 0
                  && ((v20 & 0x400) == 0
                   || (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(v15 + v14 + 84))) )
                {
                  v30 = 1;
                  goto LABEL_30;
                }
                DestinationString.Buffer = (PWSTR)(v18 + v14 + 88);
                DestinationString.MaximumLength = *(_WORD *)(v18 + v14 + 80);
                DestinationString.Length = DestinationString.MaximumLength;
                v12 = NtfsInheritStorageReserveId(a1, *(_QWORD *)v14, (int)&DestinationString, 16, FileInformation);
                if ( v12 < 0 )
                  break;
              }
              v21 = *(_DWORD *)(v18 + v14 + 20);
              if ( v21 )
                v15 = *(_DWORD *)(v14 + 16) + v21;
              else
                v15 = *(_DWORD *)(v14 + 12);
              *(_DWORD *)(v14 + 16) = v15;
              if ( !*(_DWORD *)(v18 + v14 + 20) )
                goto LABEL_30;
            }
            if ( NtfsStatusDebugFlags
              && (unsigned int)v12 < 0xFFFFFFED
              && v12 != -1073741802
              && v12 != -1073741807
              && (unsigned int)(v12 + 2147483643) > 1
              && v12 != -1073741608 )
            {
              v24 = 1005313;
              goto LABEL_68;
            }
            goto LABEL_94;
          }
          v16 = ZwQueryDirectoryFile(
                  *(HANDLE *)v14,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  (PVOID)(v14 + 20),
                  *(_DWORD *)(v14 + 8),
                  FileFullDirectoryInformation,
                  0,
                  0,
                  0);
          v12 = v16;
          if ( v16 == -1073741809 || v16 == -2147483642 )
            v12 = 0;
          if ( v12 < 0 )
            goto LABEL_94;
          *(_DWORD *)(v14 + 12) = IoStatusBlock.Information;
          Information = IoStatusBlock.Information;
          *(_DWORD *)(v14 + 16) = 0;
          v15 = 0;
          if ( Information )
            goto LABEL_22;
          ZwClose(*(HANDLE *)v14);
          *(_QWORD *)v14 = 0;
          --v10;
LABEL_30:
          if ( !v10 )
            goto LABEL_94;
          if ( v30 )
          {
            v9 = v39;
            goto LABEL_5;
          }
        }
        v12 = -1073741536;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_94;
        v24 = 1005173;
        goto LABEL_68;
      }
      if ( NtfsStatusDebugFlags
        && (unsigned int)v12 < 0xFFFFFFED
        && v12 != -1073741802
        && v12 != -1073741807
        && (unsigned int)(v12 + 2147483643) > 1
        && v12 != -1073741608 )
      {
        v24 = 1005159;
        goto LABEL_68;
      }
    }
    goto LABEL_94;
  }
  v12 = -1073741536;
  if ( NtfsStatusDebugFlags )
  {
    v24 = 1004957;
    goto LABEL_68;
  }
LABEL_94:
  while ( (_DWORD)v8 )
  {
    v8 = (unsigned int)(v8 - 1);
    v29 = (HANDLE *)*((_QWORD *)v7 + v8);
    if ( v29 )
    {
      if ( *v29 )
        ZwClose(*v29);
      ExFreePoolWithTag(v29, 0);
    }
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( Handle )
    ZwClose(Handle);
  if ( v40 )
    *(_DWORD *)(a1 + 4) &= ~v40;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140201468  mov     r11, rsp
0x14020146b  mov     [r11+10h], rbx
0x14020146f  mov     [r11+18h], rsi
0x140201473  mov     [r11+20h], r9d
0x140201477  mov     [r11+8], rcx
0x14020147b  push    rdi
0x14020147c  push    r12
0x14020147e  push    r13
0x140201480  push    r14
0x140201482  push    r15
0x140201484  sub     rsp, 110h
0x14020148b  mov     r13, r8
0x14020148e  mov     r10, rdx
0x140201491  mov     rax, [rcx+68h]
0x140201495  mov     [rsp+138h+var_38], rax
0x14020149d  xorps   xmm0, xmm0
0x1402014a0  movups  xmmword ptr [r11-70h], xmm0
0x1402014a5  movups  xmmword ptr [r11-60h], xmm0
0x1402014aa  movups  xmmword ptr [r11-54h], xmm0
0x1402014af  movups  xmmword ptr [rsp+138h+DestinationString.Length], xmm0
0x1402014b7  xorps   xmm1, xmm1
0x1402014ba  movups  xmmword ptr [r11-80h], xmm1
0x1402014bf  xor     r8d, r8d
0x1402014c2  mov     [r11-90h], r8
0x1402014c9  mov     r12d, r8d
0x1402014cc  mov     [r11-88h], r8
0x1402014d3  mov     r15d, r8d
0x1402014d6  mov     [r11-0ACh], r8d
0x1402014dd  mov     r14d, 10000h
0x1402014e3  mov     [r11+20h], r14d
0x1402014e7  mov     esi, r8d
0x1402014ea  mov     [rsp+138h+arg_20], r8d
0x1402014f2  mov     eax, [rcx+4]
0x1402014f5  mov     r11d, 200h
0x1402014fb  test    r11d, eax
0x1402014fe  jz      loc_140201CE5
0x140201504  test    r13, r13
0x140201507  jnz     loc_140201C2E
0x14020150d  lea     rax, [rsp+138h+var_90]
0x140201515  mov     [rsp+138h+Handle], rax; Handle
0x14020151a  mov     [rsp+138h+AccessMode], r8b; AccessMode
0x14020151f  mov     rax, cs:__imp_IoFileObjectType
0x140201526  mov     rcx, [rax]
0x140201529  mov     [rsp+138h+ObjectType], rcx; ObjectType
0x14020152e  xor     r9d, r9d; DesiredAccess
0x140201531  xor     r8d, r8d; PassedAccessState
0x140201534  mov     edx, r11d; HandleAttributes
0x140201537  mov     rcx, r10; Object
0x14020153a  call    cs:__imp_ObOpenObjectByPointer
0x140201541  nop     dword ptr [rax+rax+00h]
0x140201546  mov     ebx, eax
0x140201548  mov     [rsp+138h+var_B4], eax
0x14020154f  test    eax, eax
0x140201551  js      loc_140201C70
0x140201557  test    r13, r13
0x14020155a  jnz     loc_14020191D
0x140201560  cmp     r15d, esi
0x140201563  jz      loc_1402018B1
0x140201569  mov     eax, esi
0x14020156b  mov     rdi, [r12+rax*8]
0x14020156f  mov     [rsp+138h+var_A8], rdi
0x140201577  test    rdi, rdi
0x14020157a  jz      loc_140201A0F
0x140201580  mov     r14d, 1
0x140201586  add     esi, r14d
0x140201589  mov     [rsp+138h+var_B0], esi
0x140201590  cmp     esi, r14d
0x140201593  jnz     loc_140201983
0x140201599  xor     edx, edx; SourceString
0x14020159b  lea     rcx, [rsp+138h+DestinationString]; DestinationString
0x1402015a3  call    cs:__imp_RtlInitUnicodeString
0x1402015aa  nop     dword ptr [rax+rax+00h]
0x1402015af  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x1402015ba  mov     rax, [rsp+138h+var_90]
0x1402015c2  mov     [rsp+138h+ObjectAttributes.RootDirectory], rax
0x1402015ca  mov     [rsp+138h+ObjectAttributes.Attributes], 200h
0x1402015d5  lea     rax, [rsp+138h+DestinationString]
0x1402015dd  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x1402015e5  xorps   xmm0, xmm0
0x1402015e8  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402015f1  cmp     esi, r14d
0x1402015f4  jz      short loc_14020162A
0x1402015f6  mov     rax, [rsp+138h+FileInformation]
0x1402015fe  mov     [rsp+138h+ObjectType], rax; FileInformation
0x140201603  mov     r9d, 4; int
0x140201609  lea     r8, [rsp+138h+DestinationString]; int
0x140201611  mov     rdx, [rdi]; int
0x140201614  mov     rcx, qword ptr [rsp+138h+arg_0]; int
0x14020161c  call    NtfsInheritStorageReserveId
0x140201621  mov     ebx, eax
0x140201623  mov     [rsp+138h+var_B4], eax
0x14020162a  test    ebx, ebx
0x14020162c  js      loc_140201BF1
0x140201632  lea     eax, [rsi-1]
0x140201635  mov     rcx, [r12+rax*8]; FileHandle
0x140201639  mov     [rsp+138h+var_A8], rcx
0x140201641  mov     rax, [rsp+138h+var_38]
0x140201649  mov     rax, [rax+0F8h]
0x140201650  mov     rdx, [rax+8]
0x140201654  mov     [rsp+138h+DeviceObject], rdx; DeviceObject
0x140201659  mov     [rsp+138h+Options], 900h; Options
0x140201661  mov     [rsp+138h+InternalParameters], 0; InternalParameters
0x14020166a  mov     [rsp+138h+CreateFileType], 0; CreateFileType
0x140201672  mov     [rsp+138h+EaLength], 0; EaLength
0x14020167a  mov     [rsp+138h+EaBuffer], 0; EaBuffer
0x140201683  mov     [rsp+138h+CreateOptions], 200021h; CreateOptions
0x14020168b  mov     [rsp+138h+Disposition], r14d; Disposition
0x140201690  mov     dword ptr [rsp+138h+Handle], 7; ShareAccess
0x140201698  mov     dword ptr [rsp+138h+AccessMode], 0; FileAttributes
0x1402016a0  mov     [rsp+138h+ObjectType], 0; AllocationSize
0x1402016a9  lea     r9, [rsp+138h+IoStatusBlock]; IoStatusBlock
0x1402016b1  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x1402016b9  mov     edx, 100001h; DesiredAccess
0x1402016be  call    cs:__imp_IoCreateFileSpecifyDeviceObjectHint
0x1402016c5  nop     dword ptr [rax+rax+00h]
0x1402016ca  mov     ebx, eax
0x1402016cc  mov     [rsp+138h+var_B4], eax
0x1402016d3  test    eax, eax
0x1402016d5  js      loc_140201B9C
0x1402016db  mov     [rsp+138h+var_B8], 0
0x1402016e3  test    r13, r13
0x1402016e6  jz      short loc_1402016F3
0x1402016e8  cmp     byte ptr [r13+44h], 0
0x1402016ed  jnz     loc_140201B6B
0x1402016f3  lea     r14d, [rsi-1]
0x1402016f7  mov     rdi, [r12+r14*8]
0x1402016fb  mov     [rsp+138h+var_A8], rdi
0x140201703  mov     ecx, [rdi+10h]
0x140201706  cmp     ecx, [rdi+0Ch]
0x140201709  jnz     loc_1402017A9
0x14020170f  lea     rcx, [rdi+14h]
0x140201713  mov     byte ptr [rsp+138h+EaLength], 0; RestartScan
0x140201718  mov     [rsp+138h+EaBuffer], 0; FileName
0x140201721  mov     byte ptr [rsp+138h+CreateOptions], 0; ReturnSingleEntry
0x140201726  mov     [rsp+138h+Disposition], 2; FileInformationClass
0x14020172e  mov     eax, [rdi+8]
0x140201731  mov     dword ptr [rsp+138h+Handle], eax; Length
0x140201735  mov     qword ptr [rsp+138h+AccessMode], rcx; FileInformation
0x14020173a  lea     rax, [rsp+138h+IoStatusBlock]
0x140201742  mov     [rsp+138h+ObjectType], rax; IoStatusBlock
0x140201747  xor     r9d, r9d; ApcContext
0x14020174a  xor     r8d, r8d; ApcRoutine
0x14020174d  xor     edx, edx; Event
0x14020174f  mov     rcx, [rdi]; FileHandle
0x140201752  call    cs:__imp_ZwQueryDirectoryFile
0x140201759  nop     dword ptr [rax+rax+00h]
0x14020175e  mov     ebx, eax
0x140201760  mov     [rsp+138h+var_B4], eax
0x140201767  cmp     eax, 0C000000Fh
0x14020176c  jz      loc_1402018A3
0x140201772  cmp     eax, 80000006h
0x140201777  jz      loc_1402018A3
0x14020177d  test    ebx, ebx
0x14020177f  js      loc_140201C70
0x140201785  mov     rax, [rsp+138h+IoStatusBlock.Information]
0x14020178d  mov     [rdi+0Ch], eax
0x140201790  mov     rax, [rsp+138h+IoStatusBlock.Information]
0x140201798  mov     dword ptr [rdi+10h], 0
0x14020179f  xor     ecx, ecx
0x1402017a1  test    eax, eax
0x1402017a3  jz      loc_140201946
0x1402017a9  test    r13, r13
0x1402017ac  jz      short loc_1402017B9
0x1402017ae  cmp     byte ptr [r13+44h], 0
0x1402017b3  jnz     loc_140201AAA
0x1402017b9  mov     r14d, ecx
0x1402017bc  mov     eax, [r14+rdi+50h]
0x1402017c1  cmp     eax, 4
0x1402017c4  jbe     loc_140201883
0x1402017ca  mov     eax, [r14+rdi+4Ch]
0x1402017cf  test    al, 10h
0x1402017d1  jnz     loc_14020196C
0x1402017d7  lea     rax, [rdi+58h]
0x1402017db  add     rax, r14
0x1402017de  mov     [rsp+138h+DestinationString.Buffer], rax
0x1402017e6  movzx   eax, word ptr [r14+rdi+50h]
0x1402017ec  mov     [rsp+138h+DestinationString.MaximumLength], ax
0x1402017f4  mov     [rsp+138h+DestinationString.Length], ax
0x1402017fc  mov     rax, [rsp+138h+FileInformation]
0x140201804  mov     [rsp+138h+ObjectType], rax; FileInformation
0x140201809  mov     r9d, 10h; int
0x14020180f  lea     r8, [rsp+138h+DestinationString]; int
0x140201817  mov     rdx, [rdi]; int
0x14020181a  mov     rcx, qword ptr [rsp+138h+arg_0]; int
0x140201822  call    NtfsInheritStorageReserveId
0x140201827  mov     ebx, eax
0x140201829  mov     [rsp+138h+var_B4], eax
0x140201830  test    eax, eax
0x140201832  js      loc_140201B89
0x140201838  mov     ecx, [r14+rdi+14h]
0x14020183d  test    ecx, ecx
0x14020183f  jz      short loc_14020187E
0x140201841  add     ecx, [rdi+10h]
0x140201844  mov     [rdi+10h], ecx
0x140201847  cmp     dword ptr [r14+rdi+14h], 0
0x14020184d  jnz     loc_1402017A9
0x140201853  test    esi, esi
0x140201855  jz      loc_140201C70
0x14020185b  cmp     [rsp+138h+var_B8], 0
0x140201863  jz      loc_1402016E3
0x140201869  test    esi, esi
0x14020186b  jz      loc_140201C70
0x140201871  mov     r14d, [rsp+138h+arg_18]
0x140201879  jmp     loc_140201557
0x14020187e  mov     ecx, [rdi+0Ch]
0x140201881  jmp     short loc_140201844
0x140201883  cmp     word ptr [r14+rdi+58h], 2Eh ; '.'
0x14020188a  jnz     loc_1402017CA
0x140201890  cmp     eax, 4
0x140201893  jnz     short loc_140201838
0x140201895  cmp     word ptr [r14+rdi+5Ah], 2Eh ; '.'
0x14020189c  jz      short loc_140201838
0x14020189e  jmp     loc_1402017CA
0x1402018a3  xor     ebx, ebx
0x1402018a5  mov     [rsp+138h+var_B4], ebx
0x1402018ac  jmp     loc_14020177D
0x1402018b1  mov     ecx, cs:PoolType; PoolType
0x1402018b7  lea     r14d, [r15+3]
0x1402018bb  mov     edx, r14d
0x1402018be  shl     rdx, 3; NumberOfBytes
0x1402018c2  mov     r8d, 4646744Eh; Tag
0x1402018c8  call    cs:__imp_ExAllocatePoolWithTag
0x1402018cf  nop     dword ptr [rax+rax+00h]
0x1402018d4  mov     rdi, rax
0x1402018d7  test    rax, rax
0x1402018da  jz      loc_140201A7E
0x1402018e0  test    r15d, r15d
0x1402018e3  jnz     loc_140201C3D
0x1402018e9  mov     eax, r15d
0x1402018ec  xorps   xmm0, xmm0
0x1402018ef  xor     ecx, ecx
0x1402018f1  movups  xmmword ptr [rdi+rax*8], xmm0
0x1402018f5  mov     [rdi+rax*8+10h], rcx
0x1402018fa  mov     r12, rdi
0x1402018fd  mov     [rsp+138h+var_88], rdi
0x140201905  mov     r15d, r14d
0x140201908  mov     [rsp+138h+var_AC], r14d
0x140201910  mov     r14d, [rsp+138h+arg_18]
0x140201918  jmp     loc_140201569
0x14020191d  cmp     byte ptr [r13+44h], 0
0x140201922  jz      loc_140201560
0x140201928  mov     al, cs:NtfsStatusDebugFlags
0x14020192e  mov     ebx, 0C0000120h
0x140201933  test    al, al
0x140201935  jz      loc_140201A8D
0x14020193b  mov     r8d, 0F55B6h
0x140201941  jmp     loc_140201A9F
0x140201946  mov     rcx, [rdi]; Handle
0x140201949  call    cs:__imp_ZwClose
0x140201950  nop     dword ptr [rax+rax+00h]
0x140201955  mov     qword ptr [rdi], 0
0x14020195c  mov     esi, r14d
0x14020195f  mov     [rsp+138h+var_B0], r14d
0x140201967  jmp     loc_140201853
0x14020196c  bt      eax, 0Ah
0x140201970  jb      loc_140201AC1
0x140201976  mov     [rsp+138h+var_B8], 1
0x14020197e  jmp     loc_140201853
0x140201983  lea     eax, [rsi-2]
0x140201986  mov     rdi, [r12+rax*8]
0x14020198a  mov     [rsp+138h+var_A8], rdi
0x140201992  mov     ecx, [rdi+10h]
0x140201995  lea     rax, [rdi+58h]
0x140201999  add     rax, rcx
0x14020199c  mov     [rsp+138h+DestinationString.Buffer], rax
0x1402019a4  movzx   eax, word ptr [rcx+rdi+50h]
0x1402019a9  mov     [rsp+138h+DestinationString.MaximumLength], ax
0x1402019b1  mov     [rsp+138h+DestinationString.Length], ax
0x1402019b9  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x1402019c4  mov     rax, [rdi]
0x1402019c7  mov     [rsp+138h+ObjectAttributes.RootDirectory], rax
0x1402019cf  mov     [rsp+138h+ObjectAttributes.Attributes], 200h
0x1402019da  lea     rax, [rsp+138h+DestinationString]
0x1402019e2  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x1402019ea  xorps   xmm0, xmm0
0x1402019ed  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402019f6  mov     edx, [rcx+rdi+14h]
0x1402019fa  test    edx, edx
0x1402019fc  jz      loc_140201C65
0x140201a02  mov     ecx, [rdi+10h]
0x140201a05  add     ecx, edx
0x140201a07  mov     [rdi+10h], ecx
0x140201a0a  jmp     loc_1402015F1
0x140201a0f  mov     ecx, cs:PoolType; PoolType
0x140201a15  mov     edx, r14d; NumberOfBytes
0x140201a18  mov     r8d, 4646744Eh; Tag
0x140201a1e  call    cs:__imp_ExAllocatePoolWithTag
0x140201a25  nop     dword ptr [rax+rax+00h]
0x140201a2a  mov     rdi, rax
0x140201a2d  mov     [rsp+138h+var_A8], rax
0x140201a35  test    rax, rax
0x140201a38  jnz     short loc_140201A56
0x140201a3a  shr     r14d, 1
0x140201a3d  mov     [rsp+138h+arg_18], r14d
0x140201a45  mov     [rsp+138h+var_40], r14d
0x140201a4d  cmp     r14d, 1000h
0x140201a54  ja      short loc_140201A0F
0x140201a56  test    rdi, rdi
0x140201a59  jz      loc_140201B4D
0x140201a5f  mov     r8d, r14d; Size
  ... truncated ...
```
