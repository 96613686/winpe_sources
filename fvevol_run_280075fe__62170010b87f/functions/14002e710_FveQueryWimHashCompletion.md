# FveQueryWimHashCompletion

- ea: `0x14002e710`
- end: `0x14002ec44`
- name: `FveQueryWimHashCompletion`
- size: `1332`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140089574`
- `0x14008f08c`
- `0x14009ec2c`
- `0x1400a0dec`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000dde8`
- `0x1400218c0`
- `0x140021d00`
- `0x14002e710`
- `0x14008e784`
- `0x1400da590`
- `0x1400da8d4`
- `0x1400dd01c`
- `0x1400de1d4`
- `0x1400e3a5c`
- `0x1400e8438`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x14002e9de`
- `ntoskrnl!ZwFsControlFile` at `0x14002e9de`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14002e813`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14002e813`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002e7ff`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002e7ff`
- `ntoskrnl!ZwOpenFile` at `0x14002e974`
- `ntoskrnl!ZwOpenFile` at `0x14002e974`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e7e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002eaf4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002eba3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002e7e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002eaf4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002eba3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e7c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ea96`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002e7c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ea96`
- `ntoskrnl!ZwClose` at `0x14002ebfc`
- `ntoskrnl!ZwClose` at `0x14002ebfc`

## pseudocode

```c
__int64 __fastcall FveQueryWimHashCompletion(__int64 a1)
{
  bool v2; // r14
  KIRQL v3; // al
  KSPIN_LOCK *v4; // rcx
  NTSTATUS Name; // edi
  char v6; // si
  __int64 v7; // r8
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // r15
  unsigned __int64 v12; // rsi
  char v13; // r14
  unsigned __int64 v14; // rdx
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  KIRQL v17; // al
  char v18; // dl
  void *FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  __int64 InputBuffer; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[144]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 OutputBuffer; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v27; // [rsp+150h] [rbp+50h]

  memset(v25, 0, sizeof(v25));
  v2 = (unsigned __int8)FveLockQueryIsAcquired((PFAST_MUTEX)(a1 + 1504))
    || (unsigned __int8)FveLockQueryIsAcquired((PFAST_MUTEX)(a1 + 1504));
  FileHandle = 0;
  InputBuffer = 0;
  v27 = 0;
  memset(&ObjectAttributes, 0, 44);
  v22 = 0;
  OutputBuffer = 0;
  IoStatusBlock = 0;
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 4456));
  v4 = (KSPIN_LOCK *)(a1 + 4456);
  if ( (*(_BYTE *)(a1 + 4472) & 1) != 0 )
  {
    KeReleaseSpinLock(v4, v3);
    Name = 0;
    v6 = 0;
    goto LABEL_59;
  }
  Name = 0;
  v6 = 0;
  KeReleaseSpinLock(v4, v3);
  if ( !(unsigned __int8)FveIsWimHashVolume(a1) )
  {
LABEL_59:
    if ( !v2 && !v6 )
    {
      LOBYTE(v7) = 1;
      FvepAcquireDevFveLock(a1, v25, v7);
      v6 = 1;
    }
    goto LABEL_62;
  }
  if ( KeGetCurrentIrql() >= 2u || KeAreAllApcsDisabled() )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_53;
    }
    v9 = 88;
    goto LABEL_52;
  }
  if ( v2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_53;
    }
    v9 = 89;
LABEL_52:
    WPP_SF_(v8->AttachedDevice, v9, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
LABEL_53:
    Name = -1073741823;
    goto LABEL_54;
  }
  FvepAcquireDevFveLock(a1, v25, 0);
  v6 = 1;
  if ( *(_DWORD *)(a1 + 1472) || (v10 = *(_DWORD *)(a1 + 836), v10 == 1) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_53;
    }
    v9 = 90;
    goto LABEL_52;
  }
  if ( v10 == 2 && (*(_DWORD *)(a1 + 852) & 0x200) == 0 )
    goto LABEL_62;
  FvepReleaseDevFveLock(v25);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9676LL) & 0x10000000) != 0 )
  {
    v11 = 0;
    v12 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    v13 = 1;
  }
  else
  {
    v6 = 0;
    Name = FveAllocateUnicodePath(&v22);
    if ( Name < 0 )
      goto LABEL_54;
    Name = FveVolumeGetName(*(PDEVICE_OBJECT *)(a1 + 112));
    if ( Name < 0 )
      goto LABEL_54;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v22;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Name = ZwOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
    if ( Name < 0
      || (InputBuffer = 0x100000001LL,
          IoStatusBlock = 0,
          Name = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x9032Cu, &InputBuffer, 8u, &OutputBuffer, 0x18u),
          Name < 0) )
    {
LABEL_54:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          94,
          WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
          (unsigned int)Name);
      }
      goto LABEL_59;
    }
    v13 = OutputBuffer;
    v11 = *((_QWORD *)&OutputBuffer + 1);
    v12 = v27;
  }
  LOBYTE(v7) = 1;
  FvepAcquireDevFveLock(a1, v25, v7);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    if ( v12 )
    {
      v16 = 100 * v11 / v12;
      v14 = 100 * v11 % v12;
    }
    else
    {
      v16 = 0;
    }
    WPP_SF_III(WPP_GLOBAL_Control->AttachedDevice, v14, v15, v11, v12, v16);
  }
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 4456));
  v18 = *(_BYTE *)(a1 + 4472);
  *(_QWORD *)(a1 + 4432) = v11;
  *(_QWORD *)(a1 + 4440) = v12;
  *(_BYTE *)(a1 + 4472) = v18 ^ (v13 ^ v18) & 1;
  if ( v13 )
  {
    *(_DWORD *)(a1 + 4464) = 0;
    *(_QWORD *)(a1 + 4424) = 0;
    *(_QWORD *)(a1 + 4416) = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 4456), v17);
  v6 = 1;
LABEL_62:
  if ( *(int *)(a1 + 4468) >= 0 || Name >= 0 )
    *(_DWORD *)(a1 + 4468) = Name;
  if ( v6 )
    FvepReleaseDevFveLock(v25);
  if ( FileHandle )
  {
    ZwClose(FileHandle);
    FileHandle = 0;
  }
  return FveFreeUnicodePath(&v22);
}

```

## disassembly

```asm
0x14002e710  mov     [rsp-8+arg_8], rbx
0x14002e715  mov     [rsp-8+arg_10], rsi
0x14002e71a  push    rbp
0x14002e71b  push    rdi
0x14002e71c  push    r12
0x14002e71e  push    r14
0x14002e720  push    r15
0x14002e722  lea     rbp, [rsp-60h]
0x14002e727  sub     rsp, 160h
0x14002e72e  mov     rax, cs:__security_cookie
0x14002e735  xor     rax, rsp
0x14002e738  mov     [rbp+80h+var_28], rax
0x14002e73c  mov     rbx, rcx
0x14002e73f  xor     edx, edx; Val
0x14002e741  lea     rcx, [rbp+80h+var_D0]; void *
0x14002e745  mov     r8d, 90h; Size
0x14002e74b  call    memset
0x14002e750  lea     rdi, [rbx+5E0h]
0x14002e757  mov     r15d, 1
0x14002e75d  mov     dl, r15b
0x14002e760  mov     rcx, rdi; FastMutex
0x14002e763  call    FveLockQueryIsAcquired
0x14002e768  test    al, al
0x14002e76a  jnz     short loc_14002E77F
0x14002e76c  xor     edx, edx
0x14002e76e  mov     rcx, rdi; FastMutex
0x14002e771  call    FveLockQueryIsAcquired
0x14002e776  test    al, al
0x14002e778  jnz     short loc_14002E77F
0x14002e77a  xor     r14b, r14b
0x14002e77d  jmp     short loc_14002E782
0x14002e77f  mov     r14b, r15b
0x14002e782  xorps   xmm0, xmm0
0x14002e785  mov     [rsp+180h+FileHandle], 0
0x14002e78e  xor     eax, eax
0x14002e790  lea     r12, [rbx+1168h]
0x14002e797  xorps   xmm1, xmm1
0x14002e79a  mov     [rsp+180h+var_128], rax
0x14002e79f  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x14002e7a3  mov     rcx, r12; SpinLock
0x14002e7a6  mov     [rbp+80h+var_30], rax
0x14002e7aa  movups  xmmword ptr [rbp+80h+ObjectAttributes+1Ch], xmm0
0x14002e7ae  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x14002e7b2  movups  [rsp+180h+var_120], xmm0
0x14002e7b7  movups  [rbp+80h+var_40], xmm1
0x14002e7bb  movups  xmmword ptr [rsp+180h+IoStatusBlock], xmm0
0x14002e7c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002e7c7  nop     dword ptr [rax+rax+00h]
0x14002e7cc  mov     rcx, r12; SpinLock
0x14002e7cf  mov     dl, al; NewIrql
0x14002e7d1  test    [rbx+1178h], r15b
0x14002e7d8  jnz     loc_14002EBA3
0x14002e7de  xor     edi, edi
0x14002e7e0  xor     sil, sil
0x14002e7e3  call    cs:__imp_KeReleaseSpinLock
0x14002e7ea  nop     dword ptr [rax+rax+00h]
0x14002e7ef  mov     rcx, rbx
0x14002e7f2  call    FveIsWimHashVolume
0x14002e7f7  test    al, al
0x14002e7f9  jz      loc_14002EBB4
0x14002e7ff  call    cs:__imp_KeGetCurrentIrql
0x14002e806  nop     dword ptr [rax+rax+00h]
0x14002e80b  cmp     al, 2
0x14002e80d  jnb     loc_14002EB2F
0x14002e813  call    cs:__imp_KeAreAllApcsDisabled
0x14002e81a  nop     dword ptr [rax+rax+00h]
0x14002e81f  test    al, al
0x14002e821  jnz     loc_14002EB2F
0x14002e827  test    r14b, r14b
0x14002e82a  jz      short loc_14002E860
0x14002e82c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e833  lea     rax, WPP_GLOBAL_Control
0x14002e83a  cmp     rcx, rax
0x14002e83d  jz      loc_14002EB64
0x14002e843  mov     eax, [rcx+2Ch]
0x14002e846  test    al, 8
0x14002e848  jz      loc_14002EB64
0x14002e84e  cmp     byte ptr [rcx+29h], 3
0x14002e852  jb      loc_14002EB64
0x14002e858  lea     edx, [rdi+59h]
0x14002e85b  jmp     loc_14002EB54
0x14002e860  xor     r8d, r8d
0x14002e863  lea     rdx, [rbp+80h+var_D0]
0x14002e867  mov     rcx, rbx
0x14002e86a  call    FvepAcquireDevFveLock
0x14002e86f  mov     sil, r15b
0x14002e872  cmp     [rbx+5C0h], edi
0x14002e878  jnz     loc_14002EB08
0x14002e87e  mov     eax, [rbx+344h]
0x14002e884  cmp     eax, r15d
0x14002e887  jz      loc_14002EB08
0x14002e88d  cmp     eax, 2
0x14002e890  jnz     short loc_14002E8A2
0x14002e892  test    dword ptr [rbx+354h], 200h
0x14002e89c  jz      loc_14002EBD0
0x14002e8a2  lea     rcx, [rbp+80h+var_D0]
0x14002e8a6  call    FvepReleaseDevFveLock
0x14002e8ab  mov     rax, [rbx+8]
0x14002e8af  test    dword ptr [rax+25CCh], 10000000h
0x14002e8b9  jz      short loc_14002E8FB
0x14002e8bb  xor     r15d, r15d
0x14002e8be  xor     esi, esi
0x14002e8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e8c7  lea     rax, WPP_GLOBAL_Control
0x14002e8ce  cmp     rcx, rax
0x14002e8d1  jz      short loc_14002E8F3
0x14002e8d3  mov     eax, [rcx+2Ch]
0x14002e8d6  test    al, 8
0x14002e8d8  jz      short loc_14002E8F3
0x14002e8da  cmp     byte ptr [rcx+29h], 4
0x14002e8de  jb      short loc_14002E8F3
0x14002e8e0  mov     rcx, [rcx+18h]
0x14002e8e4  lea     edx, [rsi+5Bh]
0x14002e8e7  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002e8ee  call    WPP_SF_
0x14002e8f3  mov     r14b, 1
0x14002e8f6  jmp     loc_14002EA00
0x14002e8fb  lea     rcx, [rsp+180h+var_120]
0x14002e900  xor     sil, sil
0x14002e903  call    FveAllocateUnicodePath
0x14002e908  mov     edi, eax
0x14002e90a  test    eax, eax
0x14002e90c  js      loc_14002EB69
0x14002e912  mov     rcx, [rbx+70h]; DeviceObject
0x14002e916  lea     rdx, [rsp+180h+var_120]
0x14002e91b  call    FveVolumeGetName
0x14002e920  mov     edi, eax
0x14002e922  test    eax, eax
0x14002e924  js      loc_14002EB69
0x14002e92a  lea     rax, [rsp+180h+var_120]
0x14002e92f  mov     [rsp+180h+OpenOptions], 20h ; ' '; OpenOptions
0x14002e937  xorps   xmm0, xmm0
0x14002e93a  mov     [rbp+80h+ObjectAttributes.ObjectName], rax
0x14002e93e  lea     r9, [rsp+180h+IoStatusBlock]; IoStatusBlock
0x14002e943  mov     [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x14002e94a  lea     r8, [rbp+80h+ObjectAttributes]; ObjectAttributes
0x14002e94e  mov     [rbp+80h+ObjectAttributes.RootDirectory], 0
0x14002e956  mov     edx, 120089h; DesiredAccess
0x14002e95b  mov     [rbp+80h+ObjectAttributes.Attributes], 240h
0x14002e962  lea     rcx, [rsp+180h+FileHandle]; FileHandle
0x14002e967  mov     [rsp+180h+ShareAccess], 3; ShareAccess
0x14002e96f  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002e974  call    cs:__imp_ZwOpenFile
0x14002e97b  nop     dword ptr [rax+rax+00h]
0x14002e980  mov     edi, eax
0x14002e982  test    eax, eax
0x14002e984  js      loc_14002EB69
0x14002e98a  mov     rcx, [rsp+180h+FileHandle]; FileHandle
0x14002e98f  lea     rax, [rbp+80h+var_40]
0x14002e993  mov     [rsp+180h+OutputBufferLength], 18h; OutputBufferLength
0x14002e99b  xorps   xmm0, xmm0
0x14002e99e  mov     [rsp+180h+OutputBuffer], rax; OutputBuffer
0x14002e9a3  xor     r9d, r9d; ApcContext
0x14002e9a6  mov     [rsp+180h+InputBufferLength], 8; InputBufferLength
0x14002e9ae  lea     rax, [rsp+180h+var_128]
0x14002e9b3  mov     [rsp+180h+InputBuffer], rax; InputBuffer
0x14002e9b8  xor     r8d, r8d; ApcRoutine
0x14002e9bb  lea     rax, [rsp+180h+IoStatusBlock]
0x14002e9c0  mov     [rsp+180h+OpenOptions], 9032Ch; FsControlCode
0x14002e9c8  xor     edx, edx; Event
0x14002e9ca  mov     qword ptr [rsp+180h+ShareAccess], rax; IoStatusBlock
0x14002e9cf  mov     dword ptr [rsp+180h+var_128], r15d
0x14002e9d4  mov     dword ptr [rsp+180h+var_128+4], r15d
0x14002e9d9  movups  xmmword ptr [rsp+180h+IoStatusBlock], xmm0
0x14002e9de  call    cs:__imp_ZwFsControlFile
0x14002e9e5  nop     dword ptr [rax+rax+00h]
0x14002e9ea  mov     edi, eax
0x14002e9ec  test    eax, eax
0x14002e9ee  js      loc_14002EB69
0x14002e9f4  mov     r14b, byte ptr [rbp+80h+var_40]
0x14002e9f8  mov     r15, qword ptr [rbp+80h+var_40+8]
0x14002e9fc  mov     rsi, [rbp+80h+var_30]
0x14002ea00  mov     r8b, 1
0x14002ea03  lea     rdx, [rbp+80h+var_D0]
0x14002ea07  mov     rcx, rbx
0x14002ea0a  call    FvepAcquireDevFveLock
0x14002ea0f  test    r14b, r14b
0x14002ea12  jz      short loc_14002EA4B
0x14002ea14  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ea1b  lea     rax, WPP_GLOBAL_Control
0x14002ea22  cmp     rcx, rax
0x14002ea25  jz      short loc_14002EA93
0x14002ea27  mov     eax, [rcx+2Ch]
0x14002ea2a  test    al, 8
0x14002ea2c  jz      short loc_14002EA93
0x14002ea2e  cmp     byte ptr [rcx+29h], 4
0x14002ea32  jb      short loc_14002EA93
0x14002ea34  mov     rcx, [rcx+18h]
0x14002ea38  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002ea3f  mov     edx, 5Ch ; '\'
0x14002ea44  call    WPP_SF_
0x14002ea49  jmp     short loc_14002EA93
0x14002ea4b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ea52  lea     rax, WPP_GLOBAL_Control
0x14002ea59  cmp     rcx, rax
0x14002ea5c  jz      short loc_14002EA93
0x14002ea5e  mov     eax, [rcx+2Ch]
0x14002ea61  test    al, 8
0x14002ea63  jz      short loc_14002EA93
0x14002ea65  cmp     byte ptr [rcx+29h], 4
0x14002ea69  jb      short loc_14002EA93
0x14002ea6b  test    rsi, rsi
0x14002ea6e  jnz     short loc_14002EA74
0x14002ea70  xor     eax, eax
0x14002ea72  jmp     short loc_14002EA7D
0x14002ea74  imul    rax, r15, 64h ; 'd'
0x14002ea78  xor     edx, edx
0x14002ea7a  div     rsi
0x14002ea7d  mov     rcx, [rcx+18h]
0x14002ea81  mov     r9, r15
0x14002ea84  mov     qword ptr [rsp+180h+OpenOptions], rax
0x14002ea89  mov     qword ptr [rsp+180h+ShareAccess], rsi
0x14002ea8e  call    WPP_SF_III
0x14002ea93  mov     rcx, r12; SpinLock
0x14002ea96  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ea9d  nop     dword ptr [rax+rax+00h]
0x14002eaa2  mov     dl, [rbx+1178h]
0x14002eaa8  mov     r8b, dl
0x14002eaab  mov     [rbx+1150h], r15
0x14002eab2  xor     r8b, r14b
0x14002eab5  mov     [rbx+1158h], rsi
0x14002eabc  and     r8b, 1
0x14002eac0  xor     r8b, dl
0x14002eac3  mov     [rbx+1178h], r8b
0x14002eaca  test    r14b, r14b
0x14002eacd  jz      short loc_14002EAEF
0x14002eacf  mov     dword ptr [rbx+1170h], 0
0x14002ead9  mov     qword ptr [rbx+1148h], 0
0x14002eae4  mov     qword ptr [rbx+1140h], 0
0x14002eaef  mov     dl, al; NewIrql
0x14002eaf1  mov     rcx, r12; SpinLock
0x14002eaf4  call    cs:__imp_KeReleaseSpinLock
0x14002eafb  nop     dword ptr [rax+rax+00h]
0x14002eb00  mov     sil, 1
0x14002eb03  jmp     loc_14002EBD0
0x14002eb08  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eb0f  lea     rax, WPP_GLOBAL_Control
0x14002eb16  cmp     rcx, rax
0x14002eb19  jz      short loc_14002EB64
0x14002eb1b  mov     eax, [rcx+2Ch]
0x14002eb1e  test    al, 8
0x14002eb20  jz      short loc_14002EB64
0x14002eb22  cmp     byte ptr [rcx+29h], 3
0x14002eb26  jb      short loc_14002EB64
0x14002eb28  mov     edx, 5Ah ; 'Z'
0x14002eb2d  jmp     short loc_14002EB54
0x14002eb2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eb36  lea     rax, WPP_GLOBAL_Control
0x14002eb3d  cmp     rcx, rax
0x14002eb40  jz      short loc_14002EB64
0x14002eb42  mov     eax, [rcx+2Ch]
0x14002eb45  test    al, 8
0x14002eb47  jz      short loc_14002EB64
0x14002eb49  cmp     byte ptr [rcx+29h], 3
0x14002eb4d  jb      short loc_14002EB64
0x14002eb4f  mov     edx, 58h ; 'X'
0x14002eb54  mov     rcx, [rcx+18h]
0x14002eb58  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002eb5f  call    WPP_SF_
0x14002eb64  mov     edi, 0C0000001h
0x14002eb69  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eb70  lea     rax, WPP_GLOBAL_Control
0x14002eb77  cmp     rcx, rax
0x14002eb7a  jz      short loc_14002EBB4
0x14002eb7c  mov     eax, [rcx+2Ch]
0x14002eb7f  test    al, 8
0x14002eb81  jz      short loc_14002EBB4
0x14002eb83  cmp     byte ptr [rcx+29h], 2
0x14002eb87  jb      short loc_14002EBB4
0x14002eb89  mov     rcx, [rcx+18h]
0x14002eb8d  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002eb94  mov     edx, 5Eh ; '^'
0x14002eb99  mov     r9d, edi
0x14002eb9c  call    WPP_SF_d
0x14002eba1  jmp     short loc_14002EBB4
0x14002eba3  call    cs:__imp_KeReleaseSpinLock
0x14002ebaa  nop     dword ptr [rax+rax+00h]
0x14002ebaf  xor     edi, edi
0x14002ebb1  xor     sil, sil
0x14002ebb4  test    r14b, r14b
0x14002ebb7  jnz     short loc_14002EBD0
0x14002ebb9  test    sil, sil
0x14002ebbc  jnz     short loc_14002EBD0
0x14002ebbe  mov     r8b, r15b
0x14002ebc1  lea     rdx, [rbp+80h+var_D0]
0x14002ebc5  mov     rcx, rbx
0x14002ebc8  call    FvepAcquireDevFveLock
0x14002ebcd  mov     sil, r15b
0x14002ebd0  mov     eax, [rbx+1174h]
0x14002ebd6  test    eax, eax
0x14002ebd8  jns     short loc_14002EBDE
0x14002ebda  test    edi, edi
0x14002ebdc  js      short loc_14002EBE4
0x14002ebde  mov     [rbx+1174h], edi
0x14002ebe4  test    sil, sil
0x14002ebe7  jz      short loc_14002EBF2
0x14002ebe9  lea     rcx, [rbp+80h+var_D0]
0x14002ebed  call    FvepReleaseDevFveLock
0x14002ebf2  mov     rcx, [rsp+180h+FileHandle]; Handle
0x14002ebf7  test    rcx, rcx
  ... truncated ...
```
