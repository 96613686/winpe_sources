# FveQueryWimHashCompletion

- ea: `0x14002f710`
- end: `0x14002fc44`
- name: `FveQueryWimHashCompletion`
- size: `1332`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14008b614`
- `0x14009113c`
- `0x14009fb70`
- `0x1400a1d38`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000dfd0`
- `0x140022bf0`
- `0x140023040`
- `0x14002f710`
- `0x140090834`
- `0x1400dce00`
- `0x1400dd144`
- `0x1400dff1c`
- `0x1400e08f4`
- `0x1400e6538`
- `0x1400ead10`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x14002f9de`
- `ntoskrnl!ZwFsControlFile` at `0x14002f9de`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14002f813`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14002f813`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002f7ff`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002f7ff`
- `ntoskrnl!ZwOpenFile` at `0x14002f974`
- `ntoskrnl!ZwOpenFile` at `0x14002f974`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f7e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002faf4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fba3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f7e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002faf4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002fba3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f7c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fa96`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f7c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002fa96`
- `ntoskrnl!ZwClose` at `0x14002fbfc`
- `ntoskrnl!ZwClose` at `0x14002fbfc`

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
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 4472));
  v4 = (KSPIN_LOCK *)(a1 + 4472);
  if ( (*(_BYTE *)(a1 + 4488) & 1) != 0 )
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
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9924LL) & 0x10000000) != 0 )
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
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 4472));
  v18 = *(_BYTE *)(a1 + 4488);
  *(_QWORD *)(a1 + 4448) = v11;
  *(_QWORD *)(a1 + 4456) = v12;
  *(_BYTE *)(a1 + 4488) = v18 ^ (v13 ^ v18) & 1;
  if ( v13 )
  {
    *(_DWORD *)(a1 + 4480) = 0;
    *(_QWORD *)(a1 + 4440) = 0;
    *(_QWORD *)(a1 + 4432) = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 4472), v17);
  v6 = 1;
LABEL_62:
  if ( *(int *)(a1 + 4484) >= 0 || Name >= 0 )
    *(_DWORD *)(a1 + 4484) = Name;
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
0x14002f710  mov     [rsp-8+arg_8], rbx
0x14002f715  mov     [rsp-8+arg_10], rsi
0x14002f71a  push    rbp
0x14002f71b  push    rdi
0x14002f71c  push    r12
0x14002f71e  push    r14
0x14002f720  push    r15
0x14002f722  lea     rbp, [rsp-60h]
0x14002f727  sub     rsp, 160h
0x14002f72e  mov     rax, cs:__security_cookie
0x14002f735  xor     rax, rsp
0x14002f738  mov     [rbp+80h+var_28], rax
0x14002f73c  mov     rbx, rcx
0x14002f73f  xor     edx, edx; Val
0x14002f741  lea     rcx, [rbp+80h+var_D0]; void *
0x14002f745  mov     r8d, 90h; Size
0x14002f74b  call    memset
0x14002f750  lea     rdi, [rbx+5E0h]
0x14002f757  mov     r15d, 1
0x14002f75d  mov     dl, r15b
0x14002f760  mov     rcx, rdi; FastMutex
0x14002f763  call    FveLockQueryIsAcquired
0x14002f768  test    al, al
0x14002f76a  jnz     short loc_14002F77F
0x14002f76c  xor     edx, edx
0x14002f76e  mov     rcx, rdi; FastMutex
0x14002f771  call    FveLockQueryIsAcquired
0x14002f776  test    al, al
0x14002f778  jnz     short loc_14002F77F
0x14002f77a  xor     r14b, r14b
0x14002f77d  jmp     short loc_14002F782
0x14002f77f  mov     r14b, r15b
0x14002f782  xorps   xmm0, xmm0
0x14002f785  mov     [rsp+180h+FileHandle], 0
0x14002f78e  xor     eax, eax
0x14002f790  lea     r12, [rbx+1178h]
0x14002f797  xorps   xmm1, xmm1
0x14002f79a  mov     [rsp+180h+var_128], rax
0x14002f79f  movups  xmmword ptr [rbp+80h+ObjectAttributes.ObjectName], xmm0
0x14002f7a3  mov     rcx, r12; SpinLock
0x14002f7a6  mov     [rbp+80h+var_30], rax
0x14002f7aa  movups  xmmword ptr [rbp+80h+ObjectAttributes+1Ch], xmm0
0x14002f7ae  movups  xmmword ptr [rbp+80h+ObjectAttributes.Length], xmm0
0x14002f7b2  movups  [rsp+180h+var_120], xmm0
0x14002f7b7  movups  [rbp+80h+var_40], xmm1
0x14002f7bb  movups  xmmword ptr [rsp+180h+IoStatusBlock], xmm0
0x14002f7c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f7c7  nop     dword ptr [rax+rax+00h]
0x14002f7cc  mov     rcx, r12; SpinLock
0x14002f7cf  mov     dl, al; NewIrql
0x14002f7d1  test    [rbx+1188h], r15b
0x14002f7d8  jnz     loc_14002FBA3
0x14002f7de  xor     edi, edi
0x14002f7e0  xor     sil, sil
0x14002f7e3  call    cs:__imp_KeReleaseSpinLock
0x14002f7ea  nop     dword ptr [rax+rax+00h]
0x14002f7ef  mov     rcx, rbx
0x14002f7f2  call    FveIsWimHashVolume
0x14002f7f7  test    al, al
0x14002f7f9  jz      loc_14002FBB4
0x14002f7ff  call    cs:__imp_KeGetCurrentIrql
0x14002f806  nop     dword ptr [rax+rax+00h]
0x14002f80b  cmp     al, 2
0x14002f80d  jnb     loc_14002FB2F
0x14002f813  call    cs:__imp_KeAreAllApcsDisabled
0x14002f81a  nop     dword ptr [rax+rax+00h]
0x14002f81f  test    al, al
0x14002f821  jnz     loc_14002FB2F
0x14002f827  test    r14b, r14b
0x14002f82a  jz      short loc_14002F860
0x14002f82c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f833  lea     rax, WPP_GLOBAL_Control
0x14002f83a  cmp     rcx, rax
0x14002f83d  jz      loc_14002FB64
0x14002f843  mov     eax, [rcx+2Ch]
0x14002f846  test    al, 8
0x14002f848  jz      loc_14002FB64
0x14002f84e  cmp     byte ptr [rcx+29h], 3
0x14002f852  jb      loc_14002FB64
0x14002f858  lea     edx, [rdi+59h]
0x14002f85b  jmp     loc_14002FB54
0x14002f860  xor     r8d, r8d
0x14002f863  lea     rdx, [rbp+80h+var_D0]
0x14002f867  mov     rcx, rbx
0x14002f86a  call    FvepAcquireDevFveLock
0x14002f86f  mov     sil, r15b
0x14002f872  cmp     [rbx+5C0h], edi
0x14002f878  jnz     loc_14002FB08
0x14002f87e  mov     eax, [rbx+344h]
0x14002f884  cmp     eax, r15d
0x14002f887  jz      loc_14002FB08
0x14002f88d  cmp     eax, 2
0x14002f890  jnz     short loc_14002F8A2
0x14002f892  test    dword ptr [rbx+354h], 200h
0x14002f89c  jz      loc_14002FBD0
0x14002f8a2  lea     rcx, [rbp+80h+var_D0]
0x14002f8a6  call    FvepReleaseDevFveLock
0x14002f8ab  mov     rax, [rbx+8]
0x14002f8af  test    dword ptr [rax+26C4h], 10000000h
0x14002f8b9  jz      short loc_14002F8FB
0x14002f8bb  xor     r15d, r15d
0x14002f8be  xor     esi, esi
0x14002f8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f8c7  lea     rax, WPP_GLOBAL_Control
0x14002f8ce  cmp     rcx, rax
0x14002f8d1  jz      short loc_14002F8F3
0x14002f8d3  mov     eax, [rcx+2Ch]
0x14002f8d6  test    al, 8
0x14002f8d8  jz      short loc_14002F8F3
0x14002f8da  cmp     byte ptr [rcx+29h], 4
0x14002f8de  jb      short loc_14002F8F3
0x14002f8e0  mov     rcx, [rcx+18h]
0x14002f8e4  lea     edx, [rsi+5Bh]
0x14002f8e7  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002f8ee  call    WPP_SF_
0x14002f8f3  mov     r14b, 1
0x14002f8f6  jmp     loc_14002FA00
0x14002f8fb  lea     rcx, [rsp+180h+var_120]
0x14002f900  xor     sil, sil
0x14002f903  call    FveAllocateUnicodePath
0x14002f908  mov     edi, eax
0x14002f90a  test    eax, eax
0x14002f90c  js      loc_14002FB69
0x14002f912  mov     rcx, [rbx+70h]; DeviceObject
0x14002f916  lea     rdx, [rsp+180h+var_120]
0x14002f91b  call    FveVolumeGetName
0x14002f920  mov     edi, eax
0x14002f922  test    eax, eax
0x14002f924  js      loc_14002FB69
0x14002f92a  lea     rax, [rsp+180h+var_120]
0x14002f92f  mov     [rsp+180h+OpenOptions], 20h ; ' '; OpenOptions
0x14002f937  xorps   xmm0, xmm0
0x14002f93a  mov     [rbp+80h+ObjectAttributes.ObjectName], rax
0x14002f93e  lea     r9, [rsp+180h+IoStatusBlock]; IoStatusBlock
0x14002f943  mov     [rbp+80h+ObjectAttributes.Length], 30h ; '0'
0x14002f94a  lea     r8, [rbp+80h+ObjectAttributes]; ObjectAttributes
0x14002f94e  mov     [rbp+80h+ObjectAttributes.RootDirectory], 0
0x14002f956  mov     edx, 120089h; DesiredAccess
0x14002f95b  mov     [rbp+80h+ObjectAttributes.Attributes], 240h
0x14002f962  lea     rcx, [rsp+180h+FileHandle]; FileHandle
0x14002f967  mov     [rsp+180h+ShareAccess], 3; ShareAccess
0x14002f96f  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002f974  call    cs:__imp_ZwOpenFile
0x14002f97b  nop     dword ptr [rax+rax+00h]
0x14002f980  mov     edi, eax
0x14002f982  test    eax, eax
0x14002f984  js      loc_14002FB69
0x14002f98a  mov     rcx, [rsp+180h+FileHandle]; FileHandle
0x14002f98f  lea     rax, [rbp+80h+var_40]
0x14002f993  mov     [rsp+180h+OutputBufferLength], 18h; OutputBufferLength
0x14002f99b  xorps   xmm0, xmm0
0x14002f99e  mov     [rsp+180h+OutputBuffer], rax; OutputBuffer
0x14002f9a3  xor     r9d, r9d; ApcContext
0x14002f9a6  mov     [rsp+180h+InputBufferLength], 8; InputBufferLength
0x14002f9ae  lea     rax, [rsp+180h+var_128]
0x14002f9b3  mov     [rsp+180h+InputBuffer], rax; InputBuffer
0x14002f9b8  xor     r8d, r8d; ApcRoutine
0x14002f9bb  lea     rax, [rsp+180h+IoStatusBlock]
0x14002f9c0  mov     [rsp+180h+OpenOptions], 9032Ch; FsControlCode
0x14002f9c8  xor     edx, edx; Event
0x14002f9ca  mov     qword ptr [rsp+180h+ShareAccess], rax; IoStatusBlock
0x14002f9cf  mov     dword ptr [rsp+180h+var_128], r15d
0x14002f9d4  mov     dword ptr [rsp+180h+var_128+4], r15d
0x14002f9d9  movups  xmmword ptr [rsp+180h+IoStatusBlock], xmm0
0x14002f9de  call    cs:__imp_ZwFsControlFile
0x14002f9e5  nop     dword ptr [rax+rax+00h]
0x14002f9ea  mov     edi, eax
0x14002f9ec  test    eax, eax
0x14002f9ee  js      loc_14002FB69
0x14002f9f4  mov     r14b, byte ptr [rbp+80h+var_40]
0x14002f9f8  mov     r15, qword ptr [rbp+80h+var_40+8]
0x14002f9fc  mov     rsi, [rbp+80h+var_30]
0x14002fa00  mov     r8b, 1
0x14002fa03  lea     rdx, [rbp+80h+var_D0]
0x14002fa07  mov     rcx, rbx
0x14002fa0a  call    FvepAcquireDevFveLock
0x14002fa0f  test    r14b, r14b
0x14002fa12  jz      short loc_14002FA4B
0x14002fa14  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fa1b  lea     rax, WPP_GLOBAL_Control
0x14002fa22  cmp     rcx, rax
0x14002fa25  jz      short loc_14002FA93
0x14002fa27  mov     eax, [rcx+2Ch]
0x14002fa2a  test    al, 8
0x14002fa2c  jz      short loc_14002FA93
0x14002fa2e  cmp     byte ptr [rcx+29h], 4
0x14002fa32  jb      short loc_14002FA93
0x14002fa34  mov     rcx, [rcx+18h]
0x14002fa38  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002fa3f  mov     edx, 5Ch ; '\'
0x14002fa44  call    WPP_SF_
0x14002fa49  jmp     short loc_14002FA93
0x14002fa4b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fa52  lea     rax, WPP_GLOBAL_Control
0x14002fa59  cmp     rcx, rax
0x14002fa5c  jz      short loc_14002FA93
0x14002fa5e  mov     eax, [rcx+2Ch]
0x14002fa61  test    al, 8
0x14002fa63  jz      short loc_14002FA93
0x14002fa65  cmp     byte ptr [rcx+29h], 4
0x14002fa69  jb      short loc_14002FA93
0x14002fa6b  test    rsi, rsi
0x14002fa6e  jnz     short loc_14002FA74
0x14002fa70  xor     eax, eax
0x14002fa72  jmp     short loc_14002FA7D
0x14002fa74  imul    rax, r15, 64h ; 'd'
0x14002fa78  xor     edx, edx
0x14002fa7a  div     rsi
0x14002fa7d  mov     rcx, [rcx+18h]
0x14002fa81  mov     r9, r15
0x14002fa84  mov     qword ptr [rsp+180h+OpenOptions], rax
0x14002fa89  mov     qword ptr [rsp+180h+ShareAccess], rsi
0x14002fa8e  call    WPP_SF_III
0x14002fa93  mov     rcx, r12; SpinLock
0x14002fa96  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002fa9d  nop     dword ptr [rax+rax+00h]
0x14002faa2  mov     dl, [rbx+1188h]
0x14002faa8  mov     r8b, dl
0x14002faab  mov     [rbx+1160h], r15
0x14002fab2  xor     r8b, r14b
0x14002fab5  mov     [rbx+1168h], rsi
0x14002fabc  and     r8b, 1
0x14002fac0  xor     r8b, dl
0x14002fac3  mov     [rbx+1188h], r8b
0x14002faca  test    r14b, r14b
0x14002facd  jz      short loc_14002FAEF
0x14002facf  mov     dword ptr [rbx+1180h], 0
0x14002fad9  mov     qword ptr [rbx+1158h], 0
0x14002fae4  mov     qword ptr [rbx+1150h], 0
0x14002faef  mov     dl, al; NewIrql
0x14002faf1  mov     rcx, r12; SpinLock
0x14002faf4  call    cs:__imp_KeReleaseSpinLock
0x14002fafb  nop     dword ptr [rax+rax+00h]
0x14002fb00  mov     sil, 1
0x14002fb03  jmp     loc_14002FBD0
0x14002fb08  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fb0f  lea     rax, WPP_GLOBAL_Control
0x14002fb16  cmp     rcx, rax
0x14002fb19  jz      short loc_14002FB64
0x14002fb1b  mov     eax, [rcx+2Ch]
0x14002fb1e  test    al, 8
0x14002fb20  jz      short loc_14002FB64
0x14002fb22  cmp     byte ptr [rcx+29h], 3
0x14002fb26  jb      short loc_14002FB64
0x14002fb28  mov     edx, 5Ah ; 'Z'
0x14002fb2d  jmp     short loc_14002FB54
0x14002fb2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fb36  lea     rax, WPP_GLOBAL_Control
0x14002fb3d  cmp     rcx, rax
0x14002fb40  jz      short loc_14002FB64
0x14002fb42  mov     eax, [rcx+2Ch]
0x14002fb45  test    al, 8
0x14002fb47  jz      short loc_14002FB64
0x14002fb49  cmp     byte ptr [rcx+29h], 3
0x14002fb4d  jb      short loc_14002FB64
0x14002fb4f  mov     edx, 58h ; 'X'
0x14002fb54  mov     rcx, [rcx+18h]
0x14002fb58  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002fb5f  call    WPP_SF_
0x14002fb64  mov     edi, 0C0000001h
0x14002fb69  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fb70  lea     rax, WPP_GLOBAL_Control
0x14002fb77  cmp     rcx, rax
0x14002fb7a  jz      short loc_14002FBB4
0x14002fb7c  mov     eax, [rcx+2Ch]
0x14002fb7f  test    al, 8
0x14002fb81  jz      short loc_14002FBB4
0x14002fb83  cmp     byte ptr [rcx+29h], 2
0x14002fb87  jb      short loc_14002FBB4
0x14002fb89  mov     rcx, [rcx+18h]
0x14002fb8d  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14002fb94  mov     edx, 5Eh ; '^'
0x14002fb99  mov     r9d, edi
0x14002fb9c  call    WPP_SF_d
0x14002fba1  jmp     short loc_14002FBB4
0x14002fba3  call    cs:__imp_KeReleaseSpinLock
0x14002fbaa  nop     dword ptr [rax+rax+00h]
0x14002fbaf  xor     edi, edi
0x14002fbb1  xor     sil, sil
0x14002fbb4  test    r14b, r14b
0x14002fbb7  jnz     short loc_14002FBD0
0x14002fbb9  test    sil, sil
0x14002fbbc  jnz     short loc_14002FBD0
0x14002fbbe  mov     r8b, r15b
0x14002fbc1  lea     rdx, [rbp+80h+var_D0]
0x14002fbc5  mov     rcx, rbx
0x14002fbc8  call    FvepAcquireDevFveLock
0x14002fbcd  mov     sil, r15b
0x14002fbd0  mov     eax, [rbx+1184h]
0x14002fbd6  test    eax, eax
0x14002fbd8  jns     short loc_14002FBDE
0x14002fbda  test    edi, edi
0x14002fbdc  js      short loc_14002FBE4
0x14002fbde  mov     [rbx+1184h], edi
0x14002fbe4  test    sil, sil
0x14002fbe7  jz      short loc_14002FBF2
0x14002fbe9  lea     rcx, [rbp+80h+var_D0]
0x14002fbed  call    FvepReleaseDevFveLock
0x14002fbf2  mov     rcx, [rsp+180h+FileHandle]; Handle
0x14002fbf7  test    rcx, rcx
  ... truncated ...
```
