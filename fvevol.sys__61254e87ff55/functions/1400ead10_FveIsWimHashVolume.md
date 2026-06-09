# FveIsWimHashVolume

- ea: `0x1400ead10`
- end: `0x1400eb2f8`
- name: `FveIsWimHashVolume`
- size: `1512`
- prototype: ``
- caller_count: `12`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140024e20`
- `0x14002f710`
- `0x1400663d0`
- `0x14008b614`
- `0x14009113c`
- `0x140098830`
- `0x14009be40`
- `0x14009fb70`
- `0x1400a1d38`
- `0x1400b7280`
- `0x1400b84f4`
- `0x1400ea504`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x14002dbe0`
- `0x140063b74`
- `0x140090834`
- `0x1400dce00`
- `0x1400dd144`
- `0x1400dff1c`
- `0x1400e08f4`
- `0x1400e6538`
- `0x1400ead10`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400eafec`
- `ntoskrnl!ZwFsControlFile` at `0x1400eafec`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400eade8`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400eade8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400eadc7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400eadc7`
- `ntoskrnl!ZwOpenFile` at `0x1400eaf86`
- `ntoskrnl!ZwOpenFile` at `0x1400eaf86`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1400eb158`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1400eb158`
- `ntoskrnl!ZwClose` at `0x1400eb2ba`
- `ntoskrnl!ZwClose` at `0x1400eb2ba`

## pseudocode

```c
bool __fastcall FveIsWimHashVolume(__int64 a1)
{
  NTSTATUS Name; // edi
  bool v3; // r15
  char v4; // r14
  __int64 v5; // r8
  bool v6; // si
  __int64 v7; // rax
  char v8; // al
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  NTSTATUS v11; // eax
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[144]; // [rsp+A0h] [rbp-60h] BYREF
  void *FileHandle; // [rsp+160h] [rbp+60h] BYREF
  __int64 InputBuffer; // [rsp+168h] [rbp+68h] BYREF

  Name = 0;
  v3 = 0;
  memset(v19, 0, sizeof(v19));
  v4 = 0;
  v6 = (unsigned __int8)FveLockQueryIsAcquired((PFAST_MUTEX)(a1 + 1504))
    || (unsigned __int8)FveLockQueryIsAcquired((PFAST_MUTEX)(a1 + 1504));
  FileHandle = 0;
  InputBuffer = 0;
  v7 = *(_QWORD *)(a1 + 120);
  memset(&ObjectAttributes, 0, 44);
  v17 = 0;
  IoStatusBlock = 0;
  if ( (*(_DWORD *)(v7 + 48) & 0x100) == 0 )
    goto LABEL_81;
  v8 = *(_BYTE *)(a1 + 4416);
  if ( (v8 & 4) != 0 )
  {
    v3 = (v8 & 8) != 0;
    goto LABEL_81;
  }
  if ( KeGetCurrentIrql() >= 2u || KeAreAllApcsDisabled() )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_76;
    }
    v10 = 78;
    goto LABEL_75;
  }
  if ( v6 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_76;
    }
    v10 = 79;
LABEL_75:
    WPP_SF_(v9->AttachedDevice, v10, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
LABEL_76:
    Name = -1073741823;
    goto LABEL_77;
  }
  Name = FveFsActionsAllowed2(a1);
  if ( Name < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    goto LABEL_77;
  }
  FvepAcquireDevFveLock(a1, v19, 0);
  if ( *(_DWORD *)(a1 + 1472) || *(_DWORD *)(a1 + 836) == 1 )
  {
    v9 = WPP_GLOBAL_Control;
    v4 = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_76;
    }
    v10 = 81;
    goto LABEL_75;
  }
  FvepReleaseDevFveLock(v19);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9924LL) & 0x8000000) == 0 )
  {
    Name = FveAllocateUnicodePath(&v17);
    if ( Name >= 0 )
    {
      Name = FveVolumeGetName(*(PDEVICE_OBJECT *)(a1 + 112));
      if ( Name >= 0 )
      {
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v17;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Name = ZwOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
        if ( Name >= 0 )
        {
          InputBuffer = 0x100000001LL;
          IoStatusBlock = 0;
          v11 = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x9031Fu, &InputBuffer, 8u, 0, 0);
          Name = v11;
          if ( v11 == -1073741637 || (unsigned int)(v11 + 1073741809) <= 1 || v11 == -1073741822 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                83,
                WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
                (unsigned int)v11);
            }
            IoStatusBlock = 0;
            goto LABEL_45;
          }
          if ( v11 == -2147483643 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                84,
                WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
                2147483653LL);
            }
LABEL_45:
            Name = 0;
            goto LABEL_46;
          }
          if ( v11 >= 0 )
            goto LABEL_46;
        }
      }
    }
LABEL_77:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        87,
        WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
        (unsigned int)Name);
    }
LABEL_81:
    if ( v6 )
      goto LABEL_84;
    goto LABEL_82;
  }
  Name = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
  }
LABEL_46:
  LOBYTE(v5) = 1;
  FvepAcquireDevFveLock(a1, v19, v5);
  v4 = 1;
  if ( IoStatusBlock.Information || (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9924LL) & 0x8000000) != 0 )
  {
    *(_BYTE *)(a1 + 4416) |= 8u;
    v3 = 1;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_57;
    }
    v13 = 85;
  }
  else
  {
    *(_BYTE *)(a1 + 4416) &= ~8u;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_57;
    }
    v13 = 86;
  }
  WPP_SF_(v12->AttachedDevice, v13, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
LABEL_57:
  *(_BYTE *)(a1 + 4416) |= 4u;
  if ( (*(_BYTE *)(a1 + 4416) & 8) != 0 )
    goto LABEL_61;
  if ( *(_QWORD *)(a1 + 4464) )
  {
    ExUnsubscribeWnfStateChange();
    *(_QWORD *)(a1 + 4464) = 0;
  }
  if ( (*(_BYTE *)(a1 + 4416) & 8) != 0 )
  {
LABEL_61:
    v14 = *(_DWORD *)(a1 + 808);
    if ( ((v14 & 0x17F) != 0 && (v14 & 0x40) == 0 || (*(_DWORD *)(a1 + 852) & 0x200) != 0)
      && (*(_DWORD *)(a1 + 852) & 0x4000000) == 0 )
    {
      FveQueueDelayedAutoWorkItem(a1, FveWimHashCheck, a1, 0, 0, 0, 600000000);
    }
  }
LABEL_82:
  if ( !v4 )
  {
    LOBYTE(v5) = 1;
    FvepAcquireDevFveLock(a1, v19, v5);
    v4 = 1;
  }
LABEL_84:
  if ( *(int *)(a1 + 4424) >= 0 || Name >= 0 )
    *(_DWORD *)(a1 + 4424) = Name;
  if ( v4 )
    FvepReleaseDevFveLock(v19);
  if ( FileHandle )
  {
    ZwClose(FileHandle);
    FileHandle = 0;
  }
  FveFreeUnicodePath(&v17);
  return v3;
}

```

## disassembly

```asm
0x1400ead10  mov     [rsp-8+arg_10], rbx
0x1400ead15  mov     [rsp-8+arg_18], rsi
0x1400ead1a  push    rbp
0x1400ead1b  push    rdi
0x1400ead1c  push    r13
0x1400ead1e  push    r14
0x1400ead20  push    r15
0x1400ead22  lea     rbp, [rsp-30h]
0x1400ead27  sub     rsp, 130h
0x1400ead2e  mov     rbx, rcx
0x1400ead31  xor     edx, edx; Val
0x1400ead33  lea     rcx, [rbp+50h+var_B0]; void *
0x1400ead37  mov     r8d, 90h; Size
0x1400ead3d  xor     edi, edi
0x1400ead3f  xor     r15b, r15b
0x1400ead42  call    memset
0x1400ead47  lea     rsi, [rbx+5E0h]
0x1400ead4e  mov     dl, 1
0x1400ead50  mov     rcx, rsi; FastMutex
0x1400ead53  xor     r14b, r14b
0x1400ead56  call    FveLockQueryIsAcquired
0x1400ead5b  test    al, al
0x1400ead5d  jnz     short loc_1400EAD72
0x1400ead5f  xor     edx, edx
0x1400ead61  mov     rcx, rsi; FastMutex
0x1400ead64  call    FveLockQueryIsAcquired
0x1400ead69  test    al, al
0x1400ead6b  jnz     short loc_1400EAD72
0x1400ead6d  xor     sil, sil
0x1400ead70  jmp     short loc_1400EAD75
0x1400ead72  mov     sil, 1
0x1400ead75  xorps   xmm0, xmm0
0x1400ead78  mov     [rbp+50h+FileHandle], rdi
0x1400ead7c  xor     eax, eax
0x1400ead7e  xorps   xmm1, xmm1
0x1400ead81  mov     [rbp+50h+arg_8], rax
0x1400ead85  mov     rax, [rbx+78h]
0x1400ead89  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x1400ead8d  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x1400ead92  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x1400ead96  movups  [rsp+150h+var_F0], xmm0
0x1400ead9b  movups  xmmword ptr [rsp+150h+IoStatusBlock], xmm1
0x1400eada0  test    dword ptr [rax+30h], 100h
0x1400eada7  jz      loc_1400EB273
0x1400eadad  mov     al, [rbx+1140h]
0x1400eadb3  test    al, 4
0x1400eadb5  jz      short loc_1400EADC7
0x1400eadb7  mov     r15b, al
0x1400eadba  shr     r15b, 3
0x1400eadbe  and     r15b, 1
0x1400eadc2  jmp     loc_1400EB273
0x1400eadc7  call    cs:__imp_KeGetCurrentIrql
0x1400eadce  nop     dword ptr [rax+rax+00h]
0x1400eadd3  lea     rdi, WPP_GLOBAL_Control
0x1400eadda  mov     r13d, 8
0x1400eade0  cmp     al, 2
0x1400eade2  jnb     loc_1400EB206
0x1400eade8  call    cs:__imp_KeAreAllApcsDisabled
0x1400eadef  nop     dword ptr [rax+rax+00h]
0x1400eadf4  test    al, al
0x1400eadf6  jnz     loc_1400EB206
0x1400eadfc  test    sil, sil
0x1400eadff  jz      short loc_1400EAE30
0x1400eae01  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eae08  cmp     rcx, rdi
0x1400eae0b  jz      loc_1400EB235
0x1400eae11  mov     eax, [rcx+2Ch]
0x1400eae14  test    r13b, al
0x1400eae17  jz      loc_1400EB235
0x1400eae1d  cmp     byte ptr [rcx+29h], 3
0x1400eae21  jb      loc_1400EB235
0x1400eae27  lea     edx, [r13+47h]
0x1400eae2b  jmp     loc_1400EB225
0x1400eae30  mov     rcx, rbx
0x1400eae33  call    FveFsActionsAllowed2
0x1400eae38  mov     edi, eax
0x1400eae3a  test    eax, eax
0x1400eae3c  jns     short loc_1400EAE85
0x1400eae3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eae45  lea     rax, WPP_GLOBAL_Control
0x1400eae4c  cmp     rcx, rax
0x1400eae4f  jz      loc_1400EB241
0x1400eae55  mov     edx, [rcx+2Ch]
0x1400eae58  test    r13b, dl
0x1400eae5b  jz      loc_1400EB241
0x1400eae61  cmp     byte ptr [rcx+29h], 3
0x1400eae65  jb      loc_1400EB241
0x1400eae6b  mov     rcx, [rcx+18h]
0x1400eae6f  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400eae76  mov     edx, 50h ; 'P'
0x1400eae7b  call    WPP_SF_
0x1400eae80  jmp     loc_1400EB23A
0x1400eae85  xor     r8d, r8d
0x1400eae88  lea     rdx, [rbp+50h+var_B0]
0x1400eae8c  mov     rcx, rbx
0x1400eae8f  call    FvepAcquireDevFveLock
0x1400eae94  cmp     dword ptr [rbx+5C0h], 0
0x1400eae9b  jnz     loc_1400EB1DB
0x1400eaea1  cmp     dword ptr [rbx+344h], 1
0x1400eaea8  jz      loc_1400EB1DB
0x1400eaeae  lea     rcx, [rbp+50h+var_B0]
0x1400eaeb2  call    FvepReleaseDevFveLock
0x1400eaeb7  mov     rax, [rbx+8]
0x1400eaebb  test    dword ptr [rax+26C4h], 8000000h
0x1400eaec5  jz      short loc_1400EAF0E
0x1400eaec7  xor     edi, edi
0x1400eaec9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eaed0  lea     rax, WPP_GLOBAL_Control
0x1400eaed7  cmp     rcx, rax
0x1400eaeda  jz      loc_1400EB0A3
0x1400eaee0  mov     eax, [rcx+2Ch]
0x1400eaee3  test    r13b, al
0x1400eaee6  jz      loc_1400EB0A3
0x1400eaeec  cmp     byte ptr [rcx+29h], 4
0x1400eaef0  jb      loc_1400EB0A3
0x1400eaef6  mov     rcx, [rcx+18h]
0x1400eaefa  lea     edx, [rdi+52h]
0x1400eaefd  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400eaf04  call    WPP_SF_
0x1400eaf09  jmp     loc_1400EB0A3
0x1400eaf0e  lea     rcx, [rsp+150h+var_F0]
0x1400eaf13  call    FveAllocateUnicodePath
0x1400eaf18  mov     edi, eax
0x1400eaf1a  test    eax, eax
0x1400eaf1c  js      loc_1400EB23A
0x1400eaf22  mov     rcx, [rbx+70h]; DeviceObject
0x1400eaf26  lea     rdx, [rsp+150h+var_F0]
0x1400eaf2b  call    FveVolumeGetName
0x1400eaf30  mov     edi, eax
0x1400eaf32  test    eax, eax
0x1400eaf34  js      loc_1400EB23A
0x1400eaf3a  lea     rax, [rsp+150h+var_F0]
0x1400eaf3f  mov     [rsp+150h+OpenOptions], 20h ; ' '; OpenOptions
0x1400eaf47  xorps   xmm0, xmm0
0x1400eaf4a  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x1400eaf4e  lea     r9, [rsp+150h+IoStatusBlock]; IoStatusBlock
0x1400eaf53  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x1400eaf5b  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1400eaf60  mov     [rsp+150h+ObjectAttributes.RootDirectory], 0
0x1400eaf69  mov     edx, 120089h; DesiredAccess
0x1400eaf6e  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x1400eaf75  lea     rcx, [rbp+50h+FileHandle]; FileHandle
0x1400eaf79  mov     [rsp+150h+ShareAccess], 3; ShareAccess
0x1400eaf81  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400eaf86  call    cs:__imp_ZwOpenFile
0x1400eaf8d  nop     dword ptr [rax+rax+00h]
0x1400eaf92  mov     edi, eax
0x1400eaf94  test    eax, eax
0x1400eaf96  js      loc_1400EB23A
0x1400eaf9c  mov     rcx, [rbp+50h+FileHandle]; FileHandle
0x1400eafa0  mov     eax, 1
0x1400eafa5  mov     [rsp+150h+OutputBufferLength], 0; OutputBufferLength
0x1400eafad  xorps   xmm0, xmm0
0x1400eafb0  mov     [rsp+150h+OutputBuffer], 0; OutputBuffer
0x1400eafb9  xor     r9d, r9d; ApcContext
0x1400eafbc  mov     dword ptr [rbp+50h+arg_8], eax
0x1400eafbf  xor     r8d, r8d; ApcRoutine
0x1400eafc2  mov     dword ptr [rbp+50h+arg_8+4], eax
0x1400eafc5  xor     edx, edx; Event
0x1400eafc7  mov     [rsp+150h+InputBufferLength], r13d; InputBufferLength
0x1400eafcc  lea     rax, [rbp+50h+arg_8]
0x1400eafd0  mov     [rsp+150h+InputBuffer], rax; InputBuffer
0x1400eafd5  lea     rax, [rsp+150h+IoStatusBlock]
0x1400eafda  mov     [rsp+150h+OpenOptions], 9031Fh; FsControlCode
0x1400eafe2  mov     qword ptr [rsp+150h+ShareAccess], rax; IoStatusBlock
0x1400eafe7  movups  xmmword ptr [rsp+150h+IoStatusBlock], xmm0
0x1400eafec  call    cs:__imp_ZwFsControlFile
0x1400eaff3  nop     dword ptr [rax+rax+00h]
0x1400eaff8  mov     edi, eax
0x1400eaffa  cmp     eax, 0C00000BBh
0x1400eafff  jz      short loc_1400EB060
0x1400eb001  add     eax, 3FFFFFF1h
0x1400eb006  cmp     eax, 1
0x1400eb009  jbe     short loc_1400EB060
0x1400eb00b  cmp     edi, 0C0000002h
0x1400eb011  jz      short loc_1400EB060
0x1400eb013  mov     r9d, 80000005h
0x1400eb019  cmp     edi, r9d
0x1400eb01c  jnz     short loc_1400EB056
0x1400eb01e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb025  lea     rax, WPP_GLOBAL_Control
0x1400eb02c  cmp     rcx, rax
0x1400eb02f  jz      short loc_1400EB0A1
0x1400eb031  mov     eax, [rcx+2Ch]
0x1400eb034  test    r13b, al
0x1400eb037  jz      short loc_1400EB0A1
0x1400eb039  cmp     byte ptr [rcx+29h], 4
0x1400eb03d  jb      short loc_1400EB0A1
0x1400eb03f  mov     rcx, [rcx+18h]
0x1400eb043  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400eb04a  mov     edx, 54h ; 'T'
0x1400eb04f  call    WPP_SF_d
0x1400eb054  jmp     short loc_1400EB0A1
0x1400eb056  test    edi, edi
0x1400eb058  js      loc_1400EB23A
0x1400eb05e  jmp     short loc_1400EB0A3
0x1400eb060  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb067  lea     rax, WPP_GLOBAL_Control
0x1400eb06e  cmp     rcx, rax
0x1400eb071  jz      short loc_1400EB099
0x1400eb073  mov     eax, [rcx+2Ch]
0x1400eb076  test    r13b, al
0x1400eb079  jz      short loc_1400EB099
0x1400eb07b  cmp     byte ptr [rcx+29h], 3
0x1400eb07f  jb      short loc_1400EB099
0x1400eb081  mov     rcx, [rcx+18h]
0x1400eb085  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400eb08c  mov     edx, 53h ; 'S'
0x1400eb091  mov     r9d, edi
0x1400eb094  call    WPP_SF_d
0x1400eb099  xorps   xmm0, xmm0
0x1400eb09c  movups  xmmword ptr [rsp+150h+IoStatusBlock], xmm0
0x1400eb0a1  xor     edi, edi
0x1400eb0a3  mov     r8b, 1
0x1400eb0a6  lea     rdx, [rbp+50h+var_B0]
0x1400eb0aa  mov     rcx, rbx
0x1400eb0ad  call    FvepAcquireDevFveLock
0x1400eb0b2  cmp     [rsp+150h+IoStatusBlock.Information], 0
0x1400eb0b8  mov     r14b, 1
0x1400eb0bb  jnz     short loc_1400EB0FC
0x1400eb0bd  mov     rax, [rbx+8]
0x1400eb0c1  test    dword ptr [rax+26C4h], 8000000h
0x1400eb0cb  jnz     short loc_1400EB0FC
0x1400eb0cd  and     byte ptr [rbx+1140h], 0F7h
0x1400eb0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb0db  lea     rax, WPP_GLOBAL_Control
0x1400eb0e2  cmp     rcx, rax
0x1400eb0e5  jz      short loc_1400EB13C
0x1400eb0e7  mov     eax, [rcx+2Ch]
0x1400eb0ea  test    r13b, al
0x1400eb0ed  jz      short loc_1400EB13C
0x1400eb0ef  cmp     byte ptr [rcx+29h], 4
0x1400eb0f3  jb      short loc_1400EB13C
0x1400eb0f5  mov     edx, 56h ; 'V'
0x1400eb0fa  jmp     short loc_1400EB12C
0x1400eb0fc  or      [rbx+1140h], r13b
0x1400eb103  mov     r15b, r14b
0x1400eb106  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb10d  lea     rax, WPP_GLOBAL_Control
0x1400eb114  cmp     rcx, rax
0x1400eb117  jz      short loc_1400EB13C
0x1400eb119  mov     eax, [rcx+2Ch]
0x1400eb11c  test    r13b, al
0x1400eb11f  jz      short loc_1400EB13C
0x1400eb121  cmp     byte ptr [rcx+29h], 4
0x1400eb125  jb      short loc_1400EB13C
0x1400eb127  mov     edx, 55h ; 'U'
0x1400eb12c  mov     rcx, [rcx+18h]
0x1400eb130  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400eb137  call    WPP_SF_
0x1400eb13c  or      byte ptr [rbx+1140h], 4
0x1400eb143  test    [rbx+1140h], r13b
0x1400eb14a  jnz     short loc_1400EB178
0x1400eb14c  mov     rcx, [rbx+1170h]
0x1400eb153  test    rcx, rcx
0x1400eb156  jz      short loc_1400EB16F
0x1400eb158  call    cs:__imp_ExUnsubscribeWnfStateChange
0x1400eb15f  nop     dword ptr [rax+rax+00h]
0x1400eb164  mov     qword ptr [rbx+1170h], 0
0x1400eb16f  test    [rbx+1140h], r13b
0x1400eb176  jz      short loc_1400EB1D1
0x1400eb178  mov     eax, [rbx+328h]
0x1400eb17e  test    eax, 17Fh
0x1400eb183  jz      short loc_1400EB189
0x1400eb185  test    al, 40h
0x1400eb187  jz      short loc_1400EB195
0x1400eb189  test    dword ptr [rbx+354h], 200h
0x1400eb193  jz      short loc_1400EB1D1
0x1400eb195  test    dword ptr [rbx+354h], 4000000h
0x1400eb19f  jnz     short loc_1400EB1D1
0x1400eb1a1  mov     [rsp+150h+InputBuffer], 23C34600h
0x1400eb1aa  lea     rdx, FveWimHashCheck
0x1400eb1b1  mov     qword ptr [rsp+150h+OpenOptions], 0
0x1400eb1ba  xor     r9d, r9d
0x1400eb1bd  mov     r8, rbx
0x1400eb1c0  mov     qword ptr [rsp+150h+ShareAccess], 0
0x1400eb1c9  mov     rcx, rbx
0x1400eb1cc  call    FveQueueDelayedAutoWorkItem
0x1400eb1d1  test    edi, edi
0x1400eb1d3  jns     loc_1400EB278
0x1400eb1d9  jmp     short loc_1400EB23A
0x1400eb1db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb1e2  lea     rdi, WPP_GLOBAL_Control
0x1400eb1e9  mov     r14b, 1
0x1400eb1ec  cmp     rcx, rdi
0x1400eb1ef  jz      short loc_1400EB235
0x1400eb1f1  mov     eax, [rcx+2Ch]
0x1400eb1f4  test    r13b, al
0x1400eb1f7  jz      short loc_1400EB235
0x1400eb1f9  cmp     byte ptr [rcx+29h], 3
0x1400eb1fd  jb      short loc_1400EB235
0x1400eb1ff  mov     edx, 51h ; 'Q'
0x1400eb204  jmp     short loc_1400EB225
0x1400eb206  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb20d  cmp     rcx, rdi
0x1400eb210  jz      short loc_1400EB235
0x1400eb212  mov     eax, [rcx+2Ch]
0x1400eb215  test    r13b, al
0x1400eb218  jz      short loc_1400EB235
0x1400eb21a  cmp     byte ptr [rcx+29h], 3
  ... truncated ...
```
