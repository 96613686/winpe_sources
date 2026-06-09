# FveForcedLockAndRediscoveryWorker

- ea: `0x140072670`
- end: `0x140072b19`
- name: `FveForcedLockAndRediscoveryWorker`
- size: `1193`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140005e60`
- `0x140008e80`
- `0x140008f04`
- `0x14000a694`
- `0x140014e1c`
- `0x140023040`
- `0x140024a64`
- `0x1400251b4`
- `0x14002f334`
- `0x140072670`
- `0x140090834`
- `0x140097240`
- `0x1400b404c`
- `0x1400dce00`
- `0x1400dd144`
- `0x1400e08f4`
- `0x1400e6538`
- `0x1400e6a80`
- `0x1400e9584`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x140072870`
- `ntoskrnl!ZwFsControlFile` at `0x140072870`
- `ntoskrnl!ZwOpenFile` at `0x140072800`
- `ntoskrnl!ZwOpenFile` at `0x140072800`
- `ntoskrnl!ZwClose` at `0x140072ac0`
- `ntoskrnl!ZwClose` at `0x140072ac0`

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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 137, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
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
      v6 = 140;
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
      v6 = 141;
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
      v6 = 142;
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
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
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
            144,
            WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
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
            145,
            WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
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
        146,
        WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
        (unsigned int)Name);
    }
    goto LABEL_57;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v6 = 139;
    v7 = (unsigned int)v3;
LABEL_14:
    WPP_SF_d(v5->AttachedDevice, v6, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v7);
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
               147,
               WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
               (unsigned int)Name);
  }
  return result;
}

```

## disassembly

```asm
0x140072670  mov     [rsp-8+arg_10], rbx
0x140072675  push    rbp
0x140072676  push    rsi
0x140072677  push    rdi
0x140072678  push    r12
0x14007267a  push    r13
0x14007267c  lea     rbp, [rsp-30h]
0x140072681  sub     rsp, 130h
0x140072688  xorps   xmm0, xmm0
0x14007268b  mov     rdi, rcx
0x14007268e  xor     eax, eax
0x140072690  lea     rcx, [rbp+50h+var_B0]; void *
0x140072694  xor     esi, esi
0x140072696  mov     [rbp+50h+FileHandle], rax
0x14007269a  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x14007269f  xor     edx, edx; Val
0x1400726a1  mov     [rbp+50h+arg_0], rsi
0x1400726a5  mov     r8d, 90h; Size
0x1400726ab  movups  xmmword ptr [rsp+150h+ObjectAttributes+1Ch], xmm0
0x1400726b0  movups  [rsp+150h+var_100], xmm0
0x1400726b5  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x1400726ba  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1400726be  call    memset
0x1400726c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400726ca  lea     r12, WPP_GLOBAL_Control
0x1400726d1  lea     r13, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x1400726d8  cmp     rcx, r12
0x1400726db  jz      short loc_140072725
0x1400726dd  mov     eax, [rcx+2Ch]
0x1400726e0  test    al, 40h
0x1400726e2  jz      short loc_1400726FB
0x1400726e4  cmp     byte ptr [rcx+29h], 5
0x1400726e8  jb      short loc_1400726FB
0x1400726ea  mov     rcx, [rcx+18h]
0x1400726ee  mov     edx, 89h
0x1400726f3  mov     r8, r13
0x1400726f6  call    WPP_SF_
0x1400726fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140072702  cmp     rcx, r12
0x140072705  jz      short loc_140072725
0x140072707  mov     eax, [rcx+2Ch]
0x14007270a  test    al, 40h
0x14007270c  jz      short loc_140072725
0x14007270e  cmp     byte ptr [rcx+29h], 5
0x140072712  jb      short loc_140072725
0x140072714  mov     rcx, [rcx+18h]
0x140072718  mov     edx, 8Ah
0x14007271d  mov     r8, r13
0x140072720  call    WPP_SF_
0x140072725  lea     rcx, [rsp+150h+var_100]
0x14007272a  call    FveAllocateUnicodePath
0x14007272f  mov     ebx, eax
0x140072731  test    eax, eax
0x140072733  jns     short loc_140072774
0x140072735  mov     rcx, cs:WPP_GLOBAL_Control
0x14007273c  cmp     rcx, r12
0x14007273f  jz      loc_140072AAD
0x140072745  mov     edx, [rcx+2Ch]
0x140072748  test    dl, 40h
0x14007274b  jz      loc_140072AAD
0x140072751  cmp     byte ptr [rcx+29h], 2
0x140072755  jb      loc_140072AAD
0x14007275b  mov     edx, 8Bh
0x140072760  mov     r9d, eax
0x140072763  mov     rcx, [rcx+18h]
0x140072767  mov     r8, r13
0x14007276a  call    WPP_SF_d
0x14007276f  jmp     loc_140072AAD
0x140072774  mov     rcx, [rdi+70h]; DeviceObject
0x140072778  lea     rdx, [rsp+150h+var_100]
0x14007277d  call    FveVolumeGetName
0x140072782  mov     ebx, eax
0x140072784  test    eax, eax
0x140072786  jns     short loc_1400727B7
0x140072788  mov     rcx, cs:WPP_GLOBAL_Control
0x14007278f  cmp     rcx, r12
0x140072792  jz      loc_140072AAD
0x140072798  mov     eax, [rcx+2Ch]
0x14007279b  test    al, 40h
0x14007279d  jz      loc_140072AAD
0x1400727a3  cmp     byte ptr [rcx+29h], 2
0x1400727a7  jb      loc_140072AAD
0x1400727ad  mov     edx, 8Ch
0x1400727b2  mov     r9d, ebx
0x1400727b5  jmp     short loc_140072763
0x1400727b7  lea     rax, [rsp+150h+var_100]
0x1400727bc  mov     [rsp+150h+OpenOptions], 20h ; ' '; OpenOptions
0x1400727c4  xorps   xmm0, xmm0
0x1400727c7  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x1400727cc  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1400727d0  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x1400727d8  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1400727dd  mov     [rsp+150h+ObjectAttributes.RootDirectory], rsi
0x1400727e2  mov     edx, 120089h; DesiredAccess
0x1400727e7  mov     [rsp+150h+ObjectAttributes.Attributes], 240h
0x1400727ef  lea     rcx, [rbp+50h+FileHandle]; FileHandle
0x1400727f3  mov     [rsp+150h+ShareAccess], 3; ShareAccess
0x1400727fb  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x140072800  call    cs:__imp_ZwOpenFile
0x140072807  nop     dword ptr [rax+rax+00h]
0x14007280c  mov     ebx, eax
0x14007280e  test    eax, eax
0x140072810  jns     short loc_140072841
0x140072812  mov     rcx, cs:WPP_GLOBAL_Control
0x140072819  cmp     rcx, r12
0x14007281c  jz      loc_140072AAD
0x140072822  mov     eax, [rcx+2Ch]
0x140072825  test    al, 40h
0x140072827  jz      loc_140072AAD
0x14007282d  cmp     byte ptr [rcx+29h], 2
0x140072831  jb      loc_140072AAD
0x140072837  mov     edx, 8Dh
0x14007283c  jmp     loc_1400727B2
0x140072841  mov     rcx, [rbp+50h+FileHandle]; FileHandle
0x140072845  lea     rax, [rbp+50h+IoStatusBlock]
0x140072849  mov     [rsp+150h+OutputBufferLength], esi; OutputBufferLength
0x14007284d  xor     r9d, r9d; ApcContext
0x140072850  mov     [rsp+150h+OutputBuffer], rsi; OutputBuffer
0x140072855  xor     r8d, r8d; ApcRoutine
0x140072858  mov     [rsp+150h+InputBufferLength], esi; InputBufferLength
0x14007285c  xor     edx, edx; Event
0x14007285e  mov     [rsp+150h+InputBuffer], rsi; InputBuffer
0x140072863  mov     [rsp+150h+OpenOptions], 90020h; FsControlCode
0x14007286b  mov     qword ptr [rsp+150h+ShareAccess], rax; IoStatusBlock
0x140072870  call    cs:__imp_ZwFsControlFile
0x140072877  nop     dword ptr [rax+rax+00h]
0x14007287c  mov     ebx, eax
0x14007287e  test    eax, eax
0x140072880  jns     short loc_1400728B1
0x140072882  mov     rcx, cs:WPP_GLOBAL_Control
0x140072889  cmp     rcx, r12
0x14007288c  jz      loc_140072AAD
0x140072892  mov     eax, [rcx+2Ch]
0x140072895  test    al, 40h
0x140072897  jz      loc_140072AAD
0x14007289d  cmp     byte ptr [rcx+29h], 2
0x1400728a1  jb      loc_140072AAD
0x1400728a7  mov     edx, 8Eh
0x1400728ac  jmp     loc_1400727B2
0x1400728b1  mov     r8b, 1
0x1400728b4  lea     rdx, [rbp+50h+var_B0]
0x1400728b8  mov     rcx, rdi
0x1400728bb  call    FvepAcquireDevFveLock
0x1400728c0  mov     rcx, rdi
0x1400728c3  call    FveRundownAllReadsAndWrites
0x1400728c8  test    dword ptr [rdi+354h], 200h
0x1400728d2  jz      loc_140072A01
0x1400728d8  mov     rdx, [rdi+3F8h]
0x1400728df  test    rdx, rdx
0x1400728e2  jnz     short loc_14007291F
0x1400728e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400728eb  cmp     rcx, r12
0x1400728ee  jz      loc_1400729EB
0x1400728f4  mov     eax, [rcx+2Ch]
0x1400728f7  test    al, 40h
0x1400728f9  jz      loc_1400729EB
0x1400728ff  cmp     byte ptr [rcx+29h], 2
0x140072903  jb      loc_1400729EB
0x140072909  mov     rcx, [rcx+18h]
0x14007290d  mov     edx, 8Fh
0x140072912  mov     r8, r13
0x140072915  call    WPP_SF_
0x14007291a  jmp     loc_1400729EB
0x14007291f  mov     rcx, [rdi+3D8h]
0x140072926  lea     r8, [rbp+50h+arg_0]
0x14007292a  add     rcx, 40h ; '@'
0x14007292e  call    FveDatasetVmkGetFvek
0x140072933  mov     ebx, eax
0x140072935  test    eax, eax
0x140072937  jns     short loc_14007296C
0x140072939  mov     rcx, cs:WPP_GLOBAL_Control
0x140072940  cmp     rcx, r12
0x140072943  jz      short loc_140072966
0x140072945  mov     eax, [rcx+2Ch]
0x140072948  test    al, 40h
0x14007294a  jz      short loc_140072966
0x14007294c  cmp     byte ptr [rcx+29h], 2
0x140072950  jb      short loc_140072966
0x140072952  mov     rcx, [rcx+18h]
0x140072956  mov     edx, 90h
0x14007295b  mov     r9d, ebx
0x14007295e  mov     r8, r13
0x140072961  call    WPP_SF_d
0x140072966  mov     rsi, [rbp+50h+arg_0]
0x14007296a  jmp     short loc_1400729EB
0x14007296c  mov     rsi, [rbp+50h+arg_0]
0x140072970  mov     rcx, rsi
0x140072973  call    FveDatumKeyGetSize
0x140072978  movzx   r8d, ax
0x14007297c  test    r8d, r8d
0x14007297f  jnz     short loc_140072988
0x140072981  mov     ebx, 0C000000Dh
0x140072986  jmp     short loc_1400729EB
0x140072988  mov     byte ptr [rsp+150h+OutputBuffer], 1
0x14007298d  lea     rdx, [rsi+0Ch]
0x140072991  mov     byte ptr [rsp+150h+InputBufferLength], 1
0x140072996  mov     r9, rdx
0x140072999  mov     [rsp+150h+InputBuffer], 0
0x1400729a2  mov     rcx, rdi
0x1400729a5  mov     qword ptr [rsp+150h+OpenOptions], 0
0x1400729ae  mov     [rsp+150h+ShareAccess], r8d
0x1400729b3  call    SetBandSecurityInfo
0x1400729b8  mov     ebx, eax
0x1400729ba  test    eax, eax
0x1400729bc  jns     short loc_140072A01
0x1400729be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400729c5  cmp     rcx, r12
0x1400729c8  jz      short loc_1400729EB
0x1400729ca  mov     eax, [rcx+2Ch]
0x1400729cd  test    al, 40h
0x1400729cf  jz      short loc_1400729EB
0x1400729d1  cmp     byte ptr [rcx+29h], 2
0x1400729d5  jb      short loc_1400729EB
0x1400729d7  mov     rcx, [rcx+18h]
0x1400729db  mov     edx, 91h
0x1400729e0  mov     r9d, ebx
0x1400729e3  mov     r8, r13
0x1400729e6  call    WPP_SF_d
0x1400729eb  mov     rcx, rdi
0x1400729ee  call    FveResumeAllReadsAndWrites
0x1400729f3  lea     rcx, [rbp+50h+var_B0]
0x1400729f7  call    FvepReleaseDevFveLock
0x1400729fc  jmp     loc_140072AA0
0x140072a01  mov     ebx, 1Dh
0x140072a06  xor     r9d, r9d
0x140072a09  xor     r8d, r8d
0x140072a0c  mov     [rsp+150h+ShareAccess], ebx
0x140072a10  mov     rcx, rdi
0x140072a13  lea     edx, [rbx+23h]
0x140072a16  call    SetFveState
0x140072a1b  mov     rcx, rdi
0x140072a1e  mov     dword ptr [rdi+32Ch], 0C0210000h
0x140072a28  call    FveResumeAllReadsAndWrites
0x140072a2d  mov     r9d, ebx
0x140072a30  mov     r8b, 1
0x140072a33  xor     edx, edx
0x140072a35  mov     rcx, rdi; Context
0x140072a38  call    FveCleanup
0x140072a3d  lea     rcx, [rbp+50h+var_B0]
0x140072a41  call    FvepReleaseDevFveLock
0x140072a46  lea     edx, [rbx-16h]
0x140072a49  mov     rcx, rdi
0x140072a4c  call    FveRaiseStatusChangedEvent
0x140072a51  mov     r8b, 1
0x140072a54  xor     edx, edx
0x140072a56  mov     rcx, rdi; Context
0x140072a59  call    FveDiscoverVolume
0x140072a5e  mov     ecx, 80000000h
0x140072a63  mov     ebx, eax
0x140072a65  add     eax, ecx
0x140072a67  test    ecx, eax
0x140072a69  jnz     short loc_140072AA0
0x140072a6b  cmp     ebx, 0C0210000h
0x140072a71  jz      short loc_140072AA0
0x140072a73  mov     rcx, cs:WPP_GLOBAL_Control
0x140072a7a  cmp     rcx, r12
0x140072a7d  jz      short loc_140072AA0
0x140072a7f  mov     eax, [rcx+2Ch]
0x140072a82  test    al, 40h
0x140072a84  jz      short loc_140072AA0
0x140072a86  cmp     byte ptr [rcx+29h], 2
0x140072a8a  jb      short loc_140072AA0
0x140072a8c  mov     rcx, [rcx+18h]
0x140072a90  mov     edx, 92h
0x140072a95  mov     r9d, ebx
0x140072a98  mov     r8, r13
0x140072a9b  call    WPP_SF_d
0x140072aa0  test    rsi, rsi
0x140072aa3  jz      short loc_140072AAD
0x140072aa5  mov     rcx, rsi
0x140072aa8  call    FveDatumFree
0x140072aad  lea     rcx, [rsp+150h+var_100]
0x140072ab2  call    FveFreeUnicodePath
0x140072ab7  mov     rcx, [rbp+50h+FileHandle]; Handle
0x140072abb  test    rcx, rcx
0x140072abe  jz      short loc_140072AD4
0x140072ac0  call    cs:__imp_ZwClose
0x140072ac7  nop     dword ptr [rax+rax+00h]
0x140072acc  mov     [rbp+50h+FileHandle], 0
0x140072ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x140072adb  cmp     rcx, r12
0x140072ade  jz      short loc_140072B01
0x140072ae0  mov     eax, [rcx+2Ch]
0x140072ae3  test    al, 40h
0x140072ae5  jz      short loc_140072B01
0x140072ae7  cmp     byte ptr [rcx+29h], 5
0x140072aeb  jb      short loc_140072B01
0x140072aed  mov     rcx, [rcx+18h]
0x140072af1  mov     edx, 93h
0x140072af6  mov     r9d, ebx
0x140072af9  mov     r8, r13
0x140072afc  call    WPP_SF_d
0x140072b01  mov     rbx, [rsp+150h+arg_10]
0x140072b09  add     rsp, 130h
0x140072b10  pop     r13
0x140072b12  pop     r12
0x140072b14  pop     rdi
0x140072b15  pop     rsi
0x140072b16  pop     rbp
0x140072b17  retn
  ... truncated ...
```
