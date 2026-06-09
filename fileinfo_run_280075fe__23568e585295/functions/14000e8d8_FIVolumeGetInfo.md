# FIVolumeGetInfo

- ea: `0x14000e8d8`
- end: `0x14000ec0a`
- name: `FIVolumeGetInfo`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1400100d0`
- `0x140016a40`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x140002608`
- `0x140002644`
- `0x1400026a0`
- `0x140003920`
- `0x140003a80`
- `0x14000e8d8`
- `0x140014648`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ebbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ebd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ebbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ebd4`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x14000ea11`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x14000ea11`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000e935`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000e935`
- `ntoskrnl!ExAllocatePool2` at `0x14000e989`
- `ntoskrnl!ExAllocatePool2` at `0x14000e9de`
- `ntoskrnl!ExAllocatePool2` at `0x14000e989`
- `ntoskrnl!ExAllocatePool2` at `0x14000e9de`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000ea30`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14000ea30`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eba8`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eba8`
- `FLTMGR!FltQueryVolumeInformation` at `0x14000ea8e`
- `FLTMGR!FltQueryVolumeInformation` at `0x14000ea8e`
- `FLTMGR!FltGetVolumeProperties` at `0x14000e95c`
- `FLTMGR!FltGetVolumeProperties` at `0x14000e9b4`
- `FLTMGR!FltGetVolumeProperties` at `0x14000e95c`
- `FLTMGR!FltGetVolumeProperties` at `0x14000e9b4`

## pseudocode

```c
__int64 __fastcall FIVolumeGetInfo(__int64 a1, __int64 a2)
{
  _WORD *v2; // rdi
  struct _FLT_VOLUME_PROPERTIES *v3; // rsi
  NTSTATUS VolumeProperties; // ebx
  ULONG v7; // ebx
  struct _FLT_VOLUME_PROPERTIES *Pool2; // rax
  UNICODE_STRING *p_RealDeviceName; // rbx
  _WORD *v10; // rax
  PDEVICE_OBJECT BaseFileSystemDeviceObject; // r13
  ULONG DeviceType; // r13d
  int v13; // r12d
  unsigned __int8 v14; // al
  __int64 v15; // rdx
  __int64 v16; // r8
  char v17; // al
  int v18; // r9d
  __int64 v19; // rax
  signed __int32 v21[8]; // [rsp+0h] [rbp-89h] BYREF
  ULONG LengthReturned; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v23[2]; // [rsp+38h] [rbp-51h] BYREF
  ULONG Characteristics; // [rsp+40h] [rbp-49h]
  PDEVICE_OBJECT DeviceObject; // [rsp+48h] [rbp-41h] BYREF
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-39h] BYREF
  _DWORD v27[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v28; // [rsp+60h] [rbp-29h]
  __int64 v29; // [rsp+68h] [rbp-21h]
  int v30; // [rsp+70h] [rbp-19h]
  int v31; // [rsp+74h] [rbp-15h]
  __int64 v32; // [rsp+78h] [rbp-11h]
  struct _IO_STATUS_BLOCK Iosb; // [rsp+80h] [rbp-9h] BYREF
  __int128 FsInformation; // [rsp+90h] [rbp+7h] BYREF
  __int64 v35; // [rsp+A0h] [rbp+17h]

  LengthReturned = 0;
  DeviceObject = 0;
  Iosb = 0;
  v35 = 0;
  v2 = 0;
  FsInformation = 0;
  v31 = 0;
  v3 = 0;
  FileObject = 0;
  if ( IoGetTopLevelIrp() )
  {
    VolumeProperties = -1073741823;
    goto LABEL_19;
  }
  VolumeProperties = FltGetVolumeProperties(*(PFLT_VOLUME *)a1, 0, 0, &LengthReturned);
  if ( VolumeProperties == -1073741789 )
  {
    v7 = LengthReturned;
    Pool2 = (struct _FLT_VOLUME_PROPERTIES *)ExAllocatePool2(256, LengthReturned, 1886800198);
    v3 = Pool2;
    if ( !Pool2 )
    {
LABEL_5:
      VolumeProperties = -1073741670;
      goto LABEL_19;
    }
    VolumeProperties = FltGetVolumeProperties(*(PFLT_VOLUME *)a1, Pool2, v7, &LengthReturned);
    if ( VolumeProperties >= 0 )
    {
      p_RealDeviceName = &v3->RealDeviceName;
      v10 = (_WORD *)ExAllocatePool2(256, v3->RealDeviceName.Length + 2LL, 1853245766);
      v2 = v10;
      if ( !v10 )
        goto LABEL_5;
      memmove(v10, v3->RealDeviceName.Buffer, p_RealDeviceName->Length);
      v2[(unsigned __int64)p_RealDeviceName->Length >> 1] = 0;
      BaseFileSystemDeviceObject = IoGetBaseFileSystemDeviceObject(*(PFILE_OBJECT *)(a1 + 16));
      VolumeProperties = IoGetDeviceObjectPointer(&v3->RealDeviceName, 0x80u, &FileObject, &DeviceObject);
      if ( VolumeProperties >= 0 )
      {
        DeviceType = BaseFileSystemDeviceObject->DeviceType;
        v23[0] = DeviceType;
        Characteristics = DeviceObject->Characteristics;
        v23[1] = Characteristics | 0x20;
        v13 = 1;
        v23[0] = PfVolumeSupportedForPrefetch(v23) == 0;
        VolumeProperties = FltQueryVolumeInformation(
                             *(PFLT_INSTANCE *)(a1 + 8),
                             &Iosb,
                             &FsInformation,
                             0x18u,
                             FileFsVolumeInformation);
        if ( (VolumeProperties & 0xC0000000) == 0xC0000000 )
        {
          if ( DeviceType != 20 )
            goto LABEL_19;
          v35 = 0;
          FsInformation = 0;
          *(_QWORD *)&FsInformation = MEMORY[0xFFFFF78000000014];
        }
        FILockExclusiveAcquire(a2 + 24);
        *(_DWORD *)(a2 + 132) = v23[0] | *(_DWORD *)(a2 + 132) & 0xFFFFFFFE;
        _InterlockedOr(v21, 0);
        v14 = PfDeviceTypeTranslate(DeviceType, *(unsigned int *)(a2 + 112));
        v17 = PfDeviceCharsTranslate(Characteristics, v15, v16, (unsigned int)v15 ^ ((unsigned __int8)v15 ^ v14) & 0xF);
        *(_DWORD *)(a2 + 112) = v18 ^ ((unsigned __int8)v18 ^ (unsigned __int8)(16 * v17)) & 0xF0;
        *(_QWORD *)(a2 + 80) = FsInformation;
        *(_DWORD *)(a2 + 88) = DWORD2(FsInformation);
        if ( *(WCHAR **)(a2 + 104) == FIUnknown )
        {
          *(_QWORD *)(a2 + 104) = v2;
          v19 = -1;
          do
            ++v19;
          while ( v2[v19] );
          *(_WORD *)(a2 + 94) = v19;
          v2 = 0;
          v13 = 0;
        }
        FILockExclusiveRelease(a2 + 24);
        if ( !v13 )
        {
          v27[0] = dword_140009A74;
          v28 = 0;
          v27[1] = 0;
          v30 = 0;
          v32 = 0;
          v29 = a2;
          FIVolumeLog(v27);
        }
        VolumeProperties = 0;
      }
    }
  }
LABEL_19:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  return (unsigned int)VolumeProperties;
}

```

## disassembly

```asm
0x14000e8d8  mov     [rsp-8+arg_10], rbx
0x14000e8dd  push    rbp
0x14000e8de  push    rsi
0x14000e8df  push    rdi
0x14000e8e0  push    r12
0x14000e8e2  push    r13
0x14000e8e4  push    r14
0x14000e8e6  push    r15
0x14000e8e8  lea     rbp, [rsp-27h]
0x14000e8ed  sub     rsp, 0B0h
0x14000e8f4  mov     rax, cs:__security_cookie
0x14000e8fb  xor     rax, rsp
0x14000e8fe  mov     [rbp+57h+var_38], rax
0x14000e902  xor     r12d, r12d
0x14000e905  xorps   xmm0, xmm0
0x14000e908  xorps   xmm1, xmm1
0x14000e90b  mov     [rbp+57h+LengthReturned], r12d
0x14000e90f  xor     eax, eax
0x14000e911  mov     [rbp+57h+DeviceObject], r12
0x14000e915  movups  xmmword ptr [rbp+57h+Iosb], xmm0
0x14000e919  mov     [rbp+57h+var_40], rax
0x14000e91d  mov     edi, r12d
0x14000e920  movups  [rbp+57h+FsInformation], xmm1
0x14000e924  mov     [rbp+57h+var_6C], r12d
0x14000e928  mov     esi, r12d
0x14000e92b  mov     [rbp+57h+FileObject], r12
0x14000e92f  mov     r14, rdx
0x14000e932  mov     r15, rcx
0x14000e935  call    cs:__imp_IoGetTopLevelIrp
0x14000e93c  nop     dword ptr [rax+rax+00h]
0x14000e941  test    rax, rax
0x14000e944  jz      short loc_14000E950
0x14000e946  mov     ebx, 0C0000001h
0x14000e94b  jmp     loc_14000EB9F
0x14000e950  mov     rcx, [r15]; Volume
0x14000e953  lea     r9, [rbp+57h+LengthReturned]; LengthReturned
0x14000e957  xor     r8d, r8d; VolumePropertiesLength
0x14000e95a  xor     edx, edx; VolumeProperties
0x14000e95c  call    cs:__imp_FltGetVolumeProperties
0x14000e963  nop     dword ptr [rax+rax+00h]
0x14000e968  mov     ebx, eax
0x14000e96a  cmp     eax, 0C0000023h
0x14000e96f  jnz     loc_14000EB9F
0x14000e975  mov     ebx, [rbp+57h+LengthReturned]
0x14000e978  mov     r13d, 100h
0x14000e97e  mov     edx, ebx
0x14000e980  mov     ecx, r13d
0x14000e983  mov     r8d, 70764946h
0x14000e989  call    cs:__imp_ExAllocatePool2
0x14000e990  nop     dword ptr [rax+rax+00h]
0x14000e995  mov     rsi, rax
0x14000e998  test    rax, rax
0x14000e99b  jnz     short loc_14000E9A7
0x14000e99d  mov     ebx, 0C000009Ah
0x14000e9a2  jmp     loc_14000EB9F
0x14000e9a7  mov     rcx, [r15]; Volume
0x14000e9aa  lea     r9, [rbp+57h+LengthReturned]; LengthReturned
0x14000e9ae  mov     r8d, ebx; VolumePropertiesLength
0x14000e9b1  mov     rdx, rsi; VolumeProperties
0x14000e9b4  call    cs:__imp_FltGetVolumeProperties
0x14000e9bb  nop     dword ptr [rax+rax+00h]
0x14000e9c0  mov     ebx, eax
0x14000e9c2  test    eax, eax
0x14000e9c4  js      loc_14000EB9F
0x14000e9ca  lea     rbx, [rsi+38h]
0x14000e9ce  mov     r8d, 6E764946h
0x14000e9d4  movzx   edx, word ptr [rbx]
0x14000e9d7  mov     rcx, r13
0x14000e9da  add     rdx, 2
0x14000e9de  call    cs:__imp_ExAllocatePool2
0x14000e9e5  nop     dword ptr [rax+rax+00h]
0x14000e9ea  mov     rdi, rax
0x14000e9ed  test    rax, rax
0x14000e9f0  jz      short loc_14000E99D
0x14000e9f2  movzx   r8d, word ptr [rbx]; Size
0x14000e9f6  mov     rcx, rax; void *
0x14000e9f9  mov     rdx, [rsi+40h]; Src
0x14000e9fd  call    memmove
0x14000ea02  movzx   ecx, word ptr [rbx]
0x14000ea05  shr     rcx, 1
0x14000ea08  mov     [rdi+rcx*2], r12w
0x14000ea0d  mov     rcx, [r15+10h]; FileObject
0x14000ea11  call    cs:__imp_IoGetBaseFileSystemDeviceObject
0x14000ea18  nop     dword ptr [rax+rax+00h]
0x14000ea1d  lea     r9, [rbp+57h+DeviceObject]; DeviceObject
0x14000ea21  mov     edx, 80h; DesiredAccess
0x14000ea26  lea     r8, [rbp+57h+FileObject]; FileObject
0x14000ea2a  mov     rcx, rbx; ObjectName
0x14000ea2d  mov     r13, rax
0x14000ea30  call    cs:__imp_IoGetDeviceObjectPointer
0x14000ea37  nop     dword ptr [rax+rax+00h]
0x14000ea3c  mov     ebx, eax
0x14000ea3e  test    eax, eax
0x14000ea40  js      loc_14000EB9F
0x14000ea46  mov     rax, [rbp+57h+DeviceObject]
0x14000ea4a  lea     rcx, [rbp+57h+var_A8]
0x14000ea4e  mov     r13d, [r13+48h]
0x14000ea52  mov     [rbp+57h+var_A8], r13d
0x14000ea56  mov     eax, [rax+34h]
0x14000ea59  mov     [rbp+57h+var_A0], eax
0x14000ea5c  or      eax, 20h
0x14000ea5f  mov     [rbp+57h+var_A4], eax
0x14000ea62  call    PfVolumeSupportedForPrefetch
0x14000ea67  mov     ecx, r12d
0x14000ea6a  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x14000ea6e  test    eax, eax
0x14000ea70  lea     rdx, [rbp+57h+Iosb]; Iosb
0x14000ea74  mov     r12d, 1
0x14000ea7a  setz    cl
0x14000ea7d  mov     [rsp+0E0h+FsInformationClass], r12d; FsInformationClass
0x14000ea82  mov     [rbp+57h+var_A8], ecx
0x14000ea85  mov     rcx, [r15+8]; Instance
0x14000ea89  lea     r9d, [r12+17h]; Length
0x14000ea8e  call    cs:__imp_FltQueryVolumeInformation
0x14000ea95  nop     dword ptr [rax+rax+00h]
0x14000ea9a  mov     ecx, 0C0000000h
0x14000ea9f  mov     ebx, eax
0x14000eaa1  and     eax, ecx
0x14000eaa3  cmp     eax, ecx
0x14000eaa5  jnz     short loc_14000EACF
0x14000eaa7  cmp     r13d, 14h
0x14000eaab  jnz     loc_14000EB9F
0x14000eab1  xor     eax, eax
0x14000eab3  xorps   xmm0, xmm0
0x14000eab6  mov     [rbp+57h+var_40], rax
0x14000eaba  mov     rax, 0FFFFF78000000014h
0x14000eac4  movups  [rbp+57h+FsInformation], xmm0
0x14000eac8  mov     rax, [rax]
0x14000eacb  mov     qword ptr [rbp+57h+FsInformation], rax
0x14000eacf  lea     rcx, [r14+18h]
0x14000ead3  call    FILockExclusiveAcquire
0x14000ead8  mov     eax, [r14+84h]
0x14000eadf  and     eax, 0FFFFFFFEh
0x14000eae2  or      eax, [rbp+57h+var_A8]
0x14000eae5  mov     [r14+84h], eax
0x14000eaec  xor     r15d, r15d
0x14000eaef  lock or [rsp+0E0h+var_E0], r15d
0x14000eaf4  mov     edx, [r14+70h]
0x14000eaf8  mov     ecx, r13d
0x14000eafb  call    PfDeviceTypeTranslate
0x14000eb00  mov     ecx, [rbp+57h+var_A0]
0x14000eb03  mov     r9d, eax
0x14000eb06  xor     r9d, edx
0x14000eb09  and     r9d, 0Fh
0x14000eb0d  xor     r9d, edx
0x14000eb10  call    PfDeviceCharsTranslate
0x14000eb15  shl     eax, 4
0x14000eb18  xor     eax, r9d
0x14000eb1b  and     eax, 0F0h
0x14000eb20  xor     eax, r9d
0x14000eb23  mov     [r14+70h], eax
0x14000eb27  mov     rax, qword ptr [rbp+57h+FsInformation]
0x14000eb2b  mov     [r14+50h], rax
0x14000eb2f  mov     eax, dword ptr [rbp+57h+FsInformation+8]
0x14000eb32  mov     [r14+58h], eax
0x14000eb36  lea     rax, FIUnknown; "\\FI_UNKNOWN"
0x14000eb3d  cmp     [r14+68h], rax
0x14000eb41  jnz     short loc_14000EB60
0x14000eb43  mov     [r14+68h], rdi
0x14000eb47  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000eb4b  inc     rax
0x14000eb4e  cmp     [rdi+rax*2], r15w
0x14000eb53  jnz     short loc_14000EB4B
0x14000eb55  mov     [r14+5Eh], ax
0x14000eb5a  mov     rdi, r15
0x14000eb5d  mov     r12d, r15d
0x14000eb60  lea     rcx, [r14+18h]
0x14000eb64  call    FILockExclusiveRelease
0x14000eb69  test    r12d, r12d
0x14000eb6c  jnz     short loc_14000EB99
0x14000eb6e  mov     eax, cs:dword_140009A74
0x14000eb74  lea     rcx, [rbp+57h+var_88]
0x14000eb78  xor     r12d, r12d
0x14000eb7b  mov     [rbp+57h+var_88], eax
0x14000eb7e  mov     [rbp+57h+var_80], r12
0x14000eb82  mov     [rbp+57h+var_84], r12d
0x14000eb86  mov     [rbp+57h+var_70], r12d
0x14000eb8a  mov     [rbp+57h+var_68], r12
0x14000eb8e  mov     [rbp+57h+var_78], r14
0x14000eb92  call    FIVolumeLog
0x14000eb97  jmp     short loc_14000EB9C
0x14000eb99  xor     r12d, r12d
0x14000eb9c  mov     ebx, r12d
0x14000eb9f  mov     rcx, [rbp+57h+FileObject]; Object
0x14000eba3  test    rcx, rcx
0x14000eba6  jz      short loc_14000EBB4
0x14000eba8  call    cs:__imp_ObfDereferenceObject
0x14000ebaf  nop     dword ptr [rax+rax+00h]
0x14000ebb4  test    rdi, rdi
0x14000ebb7  jz      short loc_14000EBCA
0x14000ebb9  xor     edx, edx; Tag
0x14000ebbb  mov     rcx, rdi; P
0x14000ebbe  call    cs:__imp_ExFreePoolWithTag
0x14000ebc5  nop     dword ptr [rax+rax+00h]
0x14000ebca  test    rsi, rsi
0x14000ebcd  jz      short loc_14000EBE0
0x14000ebcf  xor     edx, edx; Tag
0x14000ebd1  mov     rcx, rsi; P
0x14000ebd4  call    cs:__imp_ExFreePoolWithTag
0x14000ebdb  nop     dword ptr [rax+rax+00h]
0x14000ebe0  mov     eax, ebx
0x14000ebe2  mov     rcx, [rbp+57h+var_38]
0x14000ebe6  xor     rcx, rsp; StackCookie
0x14000ebe9  call    __security_check_cookie
0x14000ebee  mov     rbx, [rsp+0E0h+arg_10]
0x14000ebf6  add     rsp, 0B0h
0x14000ebfd  pop     r15
0x14000ebff  pop     r14
0x14000ec01  pop     r13
0x14000ec03  pop     r12
0x14000ec05  pop     rdi
0x14000ec06  pop     rsi
0x14000ec07  pop     rbp
0x14000ec08  retn
```
