# FveForcedLockAndRediscoveryWorker

- ea: `0x140070690`
- end: `0x140070b39`
- name: `FveForcedLockAndRediscoveryWorker`
- size: `1193`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140005e50`
- `0x140008dc0`
- `0x140008e44`
- `0x14000a5d4`
- `0x140014464`
- `0x140021d00`
- `0x140023a64`
- `0x1400241b4`
- `0x14002e334`
- `0x140070690`
- `0x14008e784`
- `0x140095190`
- `0x1400b2dc4`
- `0x1400da590`
- `0x1400da8d4`
- `0x1400de1d4`
- `0x1400e3a5c`
- `0x1400e3ec8`
- `0x1400e6cd4`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x140070890`
- `ntoskrnl!ZwFsControlFile` at `0x140070890`
- `ntoskrnl!ZwOpenFile` at `0x140070820`
- `ntoskrnl!ZwOpenFile` at `0x140070820`
- `ntoskrnl!ZwClose` at `0x140070ae0`
- `ntoskrnl!ZwClose` at `0x140070ae0`

## pseudocode

```c
NTSTATUS __fastcall FveForcedLockAndRediscoveryWorker(PDEVICE_OBJECT *Context)
{
  __int64 v2; // rsi
  int v3; // eax
  NTSTATUS Name; // ebx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // r8
  PDEVICE_OBJECT v9; // rdx
  unsigned __int16 Size; // ax
  NTSTATUS result; // eax
  ULONG InputBufferLength; // [rsp+38h] [rbp-C8h]
  int OutputBuffer; // [rsp+40h] [rbp-C0h]
  __int128 v14; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v17[176]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v18; // [rsp+160h] [rbp+60h] BYREF
  void *FileHandle; // [rsp+168h] [rbp+68h] BYREF

  v2 = 0;
  FileHandle = 0;
  v18 = 0;
  v14 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(v17, 0, 0x90u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
    }
  }
  v3 = FveAllocateUnicodePath(&v14);
  Name = v3;
  if ( v3 >= 0 )
  {
    Name = FveVolumeGetName(Context[14]);
    if ( Name < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_59;
      }
      v6 = 142;
      goto LABEL_20;
    }
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Name = ZwOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
    if ( Name < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_59;
      }
      v6 = 143;
      goto LABEL_20;
    }
    Name = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x90020u, 0, 0, 0, 0);
    if ( Name < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_59;
      }
      v6 = 144;
LABEL_20:
      v7 = (unsigned int)Name;
      goto LABEL_14;
    }
    LOBYTE(v8) = 1;
    FvepAcquireDevFveLock(Context, v17, v8);
    FveRundownAllReadsAndWrites((__int64)Context);
    if ( (*((_DWORD *)Context + 213) & 0x200) != 0 )
    {
      v9 = Context[127];
      if ( !v9 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 145, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
        }
        goto LABEL_50;
      }
      Name = FveDatasetVmkGetFvek(&Context[123]->DeviceExtension, v9, &v18);
      if ( Name < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            146,
            WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
            (unsigned int)Name);
        }
        v2 = v18;
        goto LABEL_50;
      }
      v2 = v18;
      Size = FveDatumKeyGetSize(v18);
      if ( !Size )
      {
        Name = -1073741811;
LABEL_50:
        FveResumeAllReadsAndWrites((__int64)Context);
        FvepReleaseDevFveLock(v17);
LABEL_57:
        if ( v2 )
          FveDatumFree(v2);
        goto LABEL_59;
      }
      LOBYTE(OutputBuffer) = 1;
      LOBYTE(InputBufferLength) = 1;
      Name = SetBandSecurityInfo(Context, v2 + 12, Size, v2 + 12, Size, 0, 0, InputBufferLength, OutputBuffer);
      if ( Name < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            147,
            WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
            (unsigned int)Name);
        }
        goto LABEL_50;
      }
    }
    SetFveState((_DWORD)Context, 64, 0, 0, 29);
    *((_DWORD *)Context + 203) = -1071579136;
    FveResumeAllReadsAndWrites((__int64)Context);
    FveCleanup(Context);
    FvepReleaseDevFveLock(v17);
    FveRaiseStatusChangedEvent(Context, 7);
    Name = FveDiscoverVolume(Context);
    if ( (int)(Name + 0x80000000) >= 0
      && Name != -1071579136
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        148,
        WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
        (unsigned int)Name);
    }
    goto LABEL_57;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v6 = 141;
    v7 = (unsigned int)v3;
LABEL_14:
    WPP_SF_d(v5->AttachedDevice, v6, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v7);
  }
LABEL_59:
  result = FveFreeUnicodePath(&v14);
  if ( FileHandle )
  {
    result = ZwClose(FileHandle);
    FileHandle = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return WPP_SF_d(
               WPP_GLOBAL_Control->AttachedDevice,
               149,
               WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
               (unsigned int)Name);
  }
  return result;
}

```

## disassembly

```asm
0x140070690  mov     [rsp-8+arg_10], rbx
0x140070695  push    rbp
0x140070696  push    rsi
0x140070697  push    rdi
0x140070698  push    r12
0x14007069a  push    r13
0x14007069c  lea     rbp, [rsp-30h]
0x1400706a1  sub     rsp, 130h
0x1400706a8  xorps   xmm0, xmm0
0x1400706ab  mov     rdi, rcx
0x1400706ae  xor     eax, eax
0x1400706b0  lea     rcx, [rbp+50h+var_B0]; void *
0x1400706b4  xor     esi, esi
0x1400706b6  mov     [rbp+50h+FileHandle], rax
0x1400706ba  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x1400706bf  xor     edx, edx; Val
0x1400706c1  mov     [rbp+50h+arg_0], rsi
0x1400706c5  mov     r8d, 90h; Size
0x1400706cb  movups  xmmword ptr [rsp+150h+ObjectAttributes+1Ch], xmm0
0x1400706d0  movups  [rsp+150h+var_100], xmm0
0x1400706d5  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x1400706da  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1400706de  call    memset
0x1400706e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400706ea  lea     r12, WPP_GLOBAL_Control
0x1400706f1  lea     r13, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x1400706f8  cmp     rcx, r12
0x1400706fb  jz      short loc_140070745
0x1400706fd  mov     eax, [rcx+2Ch]
0x140070700  test    al, 40h
0x140070702  jz      short loc_14007071B
0x140070704  cmp     byte ptr [rcx+29h], 5
0x140070708  jb      short loc_14007071B
0x14007070a  mov     rcx, [rcx+18h]
0x14007070e  mov     edx, 8Bh
0x140070713  mov     r8, r13
0x140070716  call    WPP_SF_
0x14007071b  mov     rcx, cs:WPP_GLOBAL_Control
0x140070722  cmp     rcx, r12
0x140070725  jz      short loc_140070745
0x140070727  mov     eax, [rcx+2Ch]
0x14007072a  test    al, 40h
0x14007072c  jz      short loc_140070745
0x14007072e  cmp     byte ptr [rcx+29h], 5
0x140070732  jb      short loc_140070745
0x140070734  mov     rcx, [rcx+18h]
0x140070738  mov     edx, 8Ch
0x14007073d  mov     r8, r13
0x140070740  call    WPP_SF_
0x140070745  lea     rcx, [rsp+150h+var_100]
0x14007074a  call    FveAllocateUnicodePath
0x14007074f  mov     ebx, eax
0x140070751  test    eax, eax
0x140070753  jns     short loc_140070794
0x140070755  mov     rcx, cs:WPP_GLOBAL_Control
0x14007075c  cmp     rcx, r12
0x14007075f  jz      loc_140070ACD
0x140070765  mov     edx, [rcx+2Ch]
0x140070768  test    dl, 40h
0x14007076b  jz      loc_140070ACD
0x140070771  cmp     byte ptr [rcx+29h], 2
0x140070775  jb      loc_140070ACD
0x14007077b  mov     edx, 8Dh
0x140070780  mov     r9d, eax
0x140070783  mov     rcx, [rcx+18h]
0x140070787  mov     r8, r13
0x14007078a  call    WPP_SF_d
0x14007078f  jmp     loc_140070ACD
0x140070794  mov     rcx, [rdi+70h]; DeviceObject
0x140070798  lea     rdx, [rsp+150h+var_100]
0x14007079d  call    FveVolumeGetName
0x1400707a2  mov     ebx, eax
0x1400707a4  test    eax, eax
0x1400707a6  jns     short loc_1400707D7
0x1400707a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400707af  cmp     rcx, r12
0x1400707b2  jz      loc_140070ACD
0x1400707b8  mov     eax, [rcx+2Ch]
0x1400707bb  test    al, 40h
0x1400707bd  jz      loc_140070ACD
0x1400707c3  cmp     byte ptr [rcx+29h], 2
0x1400707c7  jb      loc_140070ACD
0x1400707cd  mov     edx, 8Eh
0x1400707d2  mov     r9d, ebx
0x1400707d5  jmp     short loc_140070783
0x1400707d7  lea     rax, [rsp+150h+var_100]
0x1400707dc  mov     [rsp+150h+OpenOptions], 20h ; ' '; OpenOptions
0x1400707e4  xorps   xmm0, xmm0
0x1400707e7  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x1400707ec  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400707f0  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x1400707f8  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1400707fd  mov     [rsp+150h+ObjectAttributes.RootDirectory], rsi
0x140070802  mov     edx, 120089h; DesiredAccess
0x140070807  mov     [rsp+150h+ObjectAttributes.Attributes], 240h
0x14007080f  lea     rcx, [rbp+50h+FileHandle]; FileHandle
0x140070813  mov     [rsp+150h+ShareAccess], 3; ShareAccess
0x14007081b  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x140070820  call    cs:__imp_ZwOpenFile
0x140070827  nop     dword ptr [rax+rax+00h]
0x14007082c  mov     ebx, eax
0x14007082e  test    eax, eax
0x140070830  jns     short loc_140070861
0x140070832  mov     rcx, cs:WPP_GLOBAL_Control
0x140070839  cmp     rcx, r12
0x14007083c  jz      loc_140070ACD
0x140070842  mov     eax, [rcx+2Ch]
0x140070845  test    al, 40h
0x140070847  jz      loc_140070ACD
0x14007084d  cmp     byte ptr [rcx+29h], 2
0x140070851  jb      loc_140070ACD
0x140070857  mov     edx, 8Fh
0x14007085c  jmp     loc_1400707D2
0x140070861  mov     rcx, [rbp+50h+FileHandle]; FileHandle
0x140070865  lea     rax, [rbp+50h+IoStatusBlock]
0x140070869  mov     [rsp+150h+OutputBufferLength], esi; OutputBufferLength
0x14007086d  xor     r9d, r9d; ApcContext
0x140070870  mov     [rsp+150h+OutputBuffer], rsi; OutputBuffer
0x140070875  xor     r8d, r8d; ApcRoutine
0x140070878  mov     [rsp+150h+InputBufferLength], esi; InputBufferLength
0x14007087c  xor     edx, edx; Event
0x14007087e  mov     [rsp+150h+InputBuffer], rsi; InputBuffer
0x140070883  mov     [rsp+150h+OpenOptions], 90020h; FsControlCode
0x14007088b  mov     qword ptr [rsp+150h+ShareAccess], rax; IoStatusBlock
0x140070890  call    cs:__imp_ZwFsControlFile
0x140070897  nop     dword ptr [rax+rax+00h]
0x14007089c  mov     ebx, eax
0x14007089e  test    eax, eax
0x1400708a0  jns     short loc_1400708D1
0x1400708a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400708a9  cmp     rcx, r12
0x1400708ac  jz      loc_140070ACD
0x1400708b2  mov     eax, [rcx+2Ch]
0x1400708b5  test    al, 40h
0x1400708b7  jz      loc_140070ACD
0x1400708bd  cmp     byte ptr [rcx+29h], 2
0x1400708c1  jb      loc_140070ACD
0x1400708c7  mov     edx, 90h
0x1400708cc  jmp     loc_1400707D2
0x1400708d1  mov     r8b, 1
0x1400708d4  lea     rdx, [rbp+50h+var_B0]
0x1400708d8  mov     rcx, rdi
0x1400708db  call    FvepAcquireDevFveLock
0x1400708e0  mov     rcx, rdi
0x1400708e3  call    FveRundownAllReadsAndWrites
0x1400708e8  test    dword ptr [rdi+354h], 200h
0x1400708f2  jz      loc_140070A21
0x1400708f8  mov     rdx, [rdi+3F8h]
0x1400708ff  test    rdx, rdx
0x140070902  jnz     short loc_14007093F
0x140070904  mov     rcx, cs:WPP_GLOBAL_Control
0x14007090b  cmp     rcx, r12
0x14007090e  jz      loc_140070A0B
0x140070914  mov     eax, [rcx+2Ch]
0x140070917  test    al, 40h
0x140070919  jz      loc_140070A0B
0x14007091f  cmp     byte ptr [rcx+29h], 2
0x140070923  jb      loc_140070A0B
0x140070929  mov     rcx, [rcx+18h]
0x14007092d  mov     edx, 91h
0x140070932  mov     r8, r13
0x140070935  call    WPP_SF_
0x14007093a  jmp     loc_140070A0B
0x14007093f  mov     rcx, [rdi+3D8h]
0x140070946  lea     r8, [rbp+50h+arg_0]
0x14007094a  add     rcx, 40h ; '@'
0x14007094e  call    FveDatasetVmkGetFvek
0x140070953  mov     ebx, eax
0x140070955  test    eax, eax
0x140070957  jns     short loc_14007098C
0x140070959  mov     rcx, cs:WPP_GLOBAL_Control
0x140070960  cmp     rcx, r12
0x140070963  jz      short loc_140070986
0x140070965  mov     eax, [rcx+2Ch]
0x140070968  test    al, 40h
0x14007096a  jz      short loc_140070986
0x14007096c  cmp     byte ptr [rcx+29h], 2
0x140070970  jb      short loc_140070986
0x140070972  mov     rcx, [rcx+18h]
0x140070976  mov     edx, 92h
0x14007097b  mov     r9d, ebx
0x14007097e  mov     r8, r13
0x140070981  call    WPP_SF_d
0x140070986  mov     rsi, [rbp+50h+arg_0]
0x14007098a  jmp     short loc_140070A0B
0x14007098c  mov     rsi, [rbp+50h+arg_0]
0x140070990  mov     rcx, rsi
0x140070993  call    FveDatumKeyGetSize
0x140070998  movzx   r8d, ax
0x14007099c  test    r8d, r8d
0x14007099f  jnz     short loc_1400709A8
0x1400709a1  mov     ebx, 0C000000Dh
0x1400709a6  jmp     short loc_140070A0B
0x1400709a8  mov     byte ptr [rsp+150h+OutputBuffer], 1
0x1400709ad  lea     rdx, [rsi+0Ch]
0x1400709b1  mov     byte ptr [rsp+150h+InputBufferLength], 1
0x1400709b6  mov     r9, rdx
0x1400709b9  mov     [rsp+150h+InputBuffer], 0
0x1400709c2  mov     rcx, rdi
0x1400709c5  mov     qword ptr [rsp+150h+OpenOptions], 0
0x1400709ce  mov     [rsp+150h+ShareAccess], r8d
0x1400709d3  call    SetBandSecurityInfo
0x1400709d8  mov     ebx, eax
0x1400709da  test    eax, eax
0x1400709dc  jns     short loc_140070A21
0x1400709de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400709e5  cmp     rcx, r12
0x1400709e8  jz      short loc_140070A0B
0x1400709ea  mov     eax, [rcx+2Ch]
0x1400709ed  test    al, 40h
0x1400709ef  jz      short loc_140070A0B
0x1400709f1  cmp     byte ptr [rcx+29h], 2
0x1400709f5  jb      short loc_140070A0B
0x1400709f7  mov     rcx, [rcx+18h]
0x1400709fb  mov     edx, 93h
0x140070a00  mov     r9d, ebx
0x140070a03  mov     r8, r13
0x140070a06  call    WPP_SF_d
0x140070a0b  mov     rcx, rdi
0x140070a0e  call    FveResumeAllReadsAndWrites
0x140070a13  lea     rcx, [rbp+50h+var_B0]
0x140070a17  call    FvepReleaseDevFveLock
0x140070a1c  jmp     loc_140070AC0
0x140070a21  mov     ebx, 1Dh
0x140070a26  xor     r9d, r9d
0x140070a29  xor     r8d, r8d
0x140070a2c  mov     [rsp+150h+ShareAccess], ebx
0x140070a30  mov     rcx, rdi
0x140070a33  lea     edx, [rbx+23h]
0x140070a36  call    SetFveState
0x140070a3b  mov     rcx, rdi
0x140070a3e  mov     dword ptr [rdi+32Ch], 0C0210000h
0x140070a48  call    FveResumeAllReadsAndWrites
0x140070a4d  mov     r9d, ebx
0x140070a50  mov     r8b, 1
0x140070a53  xor     edx, edx
0x140070a55  mov     rcx, rdi; Context
0x140070a58  call    FveCleanup
0x140070a5d  lea     rcx, [rbp+50h+var_B0]
0x140070a61  call    FvepReleaseDevFveLock
0x140070a66  lea     edx, [rbx-16h]
0x140070a69  mov     rcx, rdi
0x140070a6c  call    FveRaiseStatusChangedEvent
0x140070a71  mov     r8b, 1
0x140070a74  xor     edx, edx
0x140070a76  mov     rcx, rdi; Context
0x140070a79  call    FveDiscoverVolume
0x140070a7e  mov     ecx, 80000000h
0x140070a83  mov     ebx, eax
0x140070a85  add     eax, ecx
0x140070a87  test    ecx, eax
0x140070a89  jnz     short loc_140070AC0
0x140070a8b  cmp     ebx, 0C0210000h
0x140070a91  jz      short loc_140070AC0
0x140070a93  mov     rcx, cs:WPP_GLOBAL_Control
0x140070a9a  cmp     rcx, r12
0x140070a9d  jz      short loc_140070AC0
0x140070a9f  mov     eax, [rcx+2Ch]
0x140070aa2  test    al, 40h
0x140070aa4  jz      short loc_140070AC0
0x140070aa6  cmp     byte ptr [rcx+29h], 2
0x140070aaa  jb      short loc_140070AC0
0x140070aac  mov     rcx, [rcx+18h]
0x140070ab0  mov     edx, 94h
0x140070ab5  mov     r9d, ebx
0x140070ab8  mov     r8, r13
0x140070abb  call    WPP_SF_d
0x140070ac0  test    rsi, rsi
0x140070ac3  jz      short loc_140070ACD
0x140070ac5  mov     rcx, rsi
0x140070ac8  call    FveDatumFree
0x140070acd  lea     rcx, [rsp+150h+var_100]
0x140070ad2  call    FveFreeUnicodePath
0x140070ad7  mov     rcx, [rbp+50h+FileHandle]; Handle
0x140070adb  test    rcx, rcx
0x140070ade  jz      short loc_140070AF4
0x140070ae0  call    cs:__imp_ZwClose
0x140070ae7  nop     dword ptr [rax+rax+00h]
0x140070aec  mov     [rbp+50h+FileHandle], 0
0x140070af4  mov     rcx, cs:WPP_GLOBAL_Control
0x140070afb  cmp     rcx, r12
0x140070afe  jz      short loc_140070B21
0x140070b00  mov     eax, [rcx+2Ch]
0x140070b03  test    al, 40h
0x140070b05  jz      short loc_140070B21
0x140070b07  cmp     byte ptr [rcx+29h], 5
0x140070b0b  jb      short loc_140070B21
0x140070b0d  mov     rcx, [rcx+18h]
0x140070b11  mov     edx, 95h
0x140070b16  mov     r9d, ebx
0x140070b19  mov     r8, r13
0x140070b1c  call    WPP_SF_d
0x140070b21  mov     rbx, [rsp+150h+arg_10]
0x140070b29  add     rsp, 130h
0x140070b30  pop     r13
0x140070b32  pop     r12
0x140070b34  pop     rdi
0x140070b35  pop     rsi
0x140070b36  pop     rbp
0x140070b37  retn
  ... truncated ...
```
