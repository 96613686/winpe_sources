# FveIsWimHashVolume

- ea: `0x1400e8438`
- end: `0x1400e8a20`
- name: `FveIsWimHashVolume`
- size: `1512`
- prototype: ``
- caller_count: `12`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140023e20`
- `0x14002e710`
- `0x140064340`
- `0x140089574`
- `0x14008f08c`
- `0x14009677c`
- `0x140099d90`
- `0x14009ec2c`
- `0x1400a0dec`
- `0x1400b5f84`
- `0x1400b71f8`
- `0x1400e7c4c`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x14002cbe0`
- `0x140061af4`
- `0x14008e784`
- `0x1400da590`
- `0x1400da8d4`
- `0x1400dd01c`
- `0x1400de1d4`
- `0x1400e3a5c`
- `0x1400e8438`

## import_xrefs

- `ntoskrnl!ZwFsControlFile` at `0x1400e8714`
- `ntoskrnl!ZwFsControlFile` at `0x1400e8714`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400e8510`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400e8510`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400e84ef`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400e84ef`
- `ntoskrnl!ZwOpenFile` at `0x1400e86ae`
- `ntoskrnl!ZwOpenFile` at `0x1400e86ae`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1400e8880`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1400e8880`
- `ntoskrnl!ZwClose` at `0x1400e89e2`
- `ntoskrnl!ZwClose` at `0x1400e89e2`

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
  v8 = *(_BYTE *)(a1 + 4400);
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
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9676LL) & 0x8000000) == 0 )
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
  if ( IoStatusBlock.Information || (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9676LL) & 0x8000000) != 0 )
  {
    *(_BYTE *)(a1 + 4400) |= 8u;
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
    *(_BYTE *)(a1 + 4400) &= ~8u;
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
  *(_BYTE *)(a1 + 4400) |= 4u;
  if ( (*(_BYTE *)(a1 + 4400) & 8) != 0 )
    goto LABEL_61;
  if ( *(_QWORD *)(a1 + 4448) )
  {
    ExUnsubscribeWnfStateChange();
    *(_QWORD *)(a1 + 4448) = 0;
  }
  if ( (*(_BYTE *)(a1 + 4400) & 8) != 0 )
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
  if ( *(int *)(a1 + 4408) >= 0 || Name >= 0 )
    *(_DWORD *)(a1 + 4408) = Name;
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
0x1400e8438  mov     [rsp-8+arg_10], rbx
0x1400e843d  mov     [rsp-8+arg_18], rsi
0x1400e8442  push    rbp
0x1400e8443  push    rdi
0x1400e8444  push    r13
0x1400e8446  push    r14
0x1400e8448  push    r15
0x1400e844a  lea     rbp, [rsp-30h]
0x1400e844f  sub     rsp, 130h
0x1400e8456  mov     rbx, rcx
0x1400e8459  xor     edx, edx; Val
0x1400e845b  lea     rcx, [rbp+50h+var_B0]; void *
0x1400e845f  mov     r8d, 90h; Size
0x1400e8465  xor     edi, edi
0x1400e8467  xor     r15b, r15b
0x1400e846a  call    memset
0x1400e846f  lea     rsi, [rbx+5E0h]
0x1400e8476  mov     dl, 1
0x1400e8478  mov     rcx, rsi; FastMutex
0x1400e847b  xor     r14b, r14b
0x1400e847e  call    FveLockQueryIsAcquired
0x1400e8483  test    al, al
0x1400e8485  jnz     short loc_1400E849A
0x1400e8487  xor     edx, edx
0x1400e8489  mov     rcx, rsi; FastMutex
0x1400e848c  call    FveLockQueryIsAcquired
0x1400e8491  test    al, al
0x1400e8493  jnz     short loc_1400E849A
0x1400e8495  xor     sil, sil
0x1400e8498  jmp     short loc_1400E849D
0x1400e849a  mov     sil, 1
0x1400e849d  xorps   xmm0, xmm0
0x1400e84a0  mov     [rbp+50h+FileHandle], rdi
0x1400e84a4  xor     eax, eax
0x1400e84a6  xorps   xmm1, xmm1
0x1400e84a9  mov     [rbp+50h+arg_8], rax
0x1400e84ad  mov     rax, [rbx+78h]
0x1400e84b1  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x1400e84b5  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x1400e84ba  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x1400e84be  movups  [rsp+150h+var_F0], xmm0
0x1400e84c3  movups  xmmword ptr [rsp+150h+IoStatusBlock], xmm1
0x1400e84c8  test    dword ptr [rax+30h], 100h
0x1400e84cf  jz      loc_1400E899B
0x1400e84d5  mov     al, [rbx+1130h]
0x1400e84db  test    al, 4
0x1400e84dd  jz      short loc_1400E84EF
0x1400e84df  mov     r15b, al
0x1400e84e2  shr     r15b, 3
0x1400e84e6  and     r15b, 1
0x1400e84ea  jmp     loc_1400E899B
0x1400e84ef  call    cs:__imp_KeGetCurrentIrql
0x1400e84f6  nop     dword ptr [rax+rax+00h]
0x1400e84fb  lea     rdi, WPP_GLOBAL_Control
0x1400e8502  mov     r13d, 8
0x1400e8508  cmp     al, 2
0x1400e850a  jnb     loc_1400E892E
0x1400e8510  call    cs:__imp_KeAreAllApcsDisabled
0x1400e8517  nop     dword ptr [rax+rax+00h]
0x1400e851c  test    al, al
0x1400e851e  jnz     loc_1400E892E
0x1400e8524  test    sil, sil
0x1400e8527  jz      short loc_1400E8558
0x1400e8529  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8530  cmp     rcx, rdi
0x1400e8533  jz      loc_1400E895D
0x1400e8539  mov     eax, [rcx+2Ch]
0x1400e853c  test    r13b, al
0x1400e853f  jz      loc_1400E895D
0x1400e8545  cmp     byte ptr [rcx+29h], 3
0x1400e8549  jb      loc_1400E895D
0x1400e854f  lea     edx, [r13+47h]
0x1400e8553  jmp     loc_1400E894D
0x1400e8558  mov     rcx, rbx
0x1400e855b  call    FveFsActionsAllowed2
0x1400e8560  mov     edi, eax
0x1400e8562  test    eax, eax
0x1400e8564  jns     short loc_1400E85AD
0x1400e8566  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e856d  lea     rax, WPP_GLOBAL_Control
0x1400e8574  cmp     rcx, rax
0x1400e8577  jz      loc_1400E8969
0x1400e857d  mov     edx, [rcx+2Ch]
0x1400e8580  test    r13b, dl
0x1400e8583  jz      loc_1400E8969
0x1400e8589  cmp     byte ptr [rcx+29h], 3
0x1400e858d  jb      loc_1400E8969
0x1400e8593  mov     rcx, [rcx+18h]
0x1400e8597  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400e859e  mov     edx, 50h ; 'P'
0x1400e85a3  call    WPP_SF_
0x1400e85a8  jmp     loc_1400E8962
0x1400e85ad  xor     r8d, r8d
0x1400e85b0  lea     rdx, [rbp+50h+var_B0]
0x1400e85b4  mov     rcx, rbx
0x1400e85b7  call    FvepAcquireDevFveLock
0x1400e85bc  cmp     dword ptr [rbx+5C0h], 0
0x1400e85c3  jnz     loc_1400E8903
0x1400e85c9  cmp     dword ptr [rbx+344h], 1
0x1400e85d0  jz      loc_1400E8903
0x1400e85d6  lea     rcx, [rbp+50h+var_B0]
0x1400e85da  call    FvepReleaseDevFveLock
0x1400e85df  mov     rax, [rbx+8]
0x1400e85e3  test    dword ptr [rax+25CCh], 8000000h
0x1400e85ed  jz      short loc_1400E8636
0x1400e85ef  xor     edi, edi
0x1400e85f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e85f8  lea     rax, WPP_GLOBAL_Control
0x1400e85ff  cmp     rcx, rax
0x1400e8602  jz      loc_1400E87CB
0x1400e8608  mov     eax, [rcx+2Ch]
0x1400e860b  test    r13b, al
0x1400e860e  jz      loc_1400E87CB
0x1400e8614  cmp     byte ptr [rcx+29h], 4
0x1400e8618  jb      loc_1400E87CB
0x1400e861e  mov     rcx, [rcx+18h]
0x1400e8622  lea     edx, [rdi+52h]
0x1400e8625  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400e862c  call    WPP_SF_
0x1400e8631  jmp     loc_1400E87CB
0x1400e8636  lea     rcx, [rsp+150h+var_F0]
0x1400e863b  call    FveAllocateUnicodePath
0x1400e8640  mov     edi, eax
0x1400e8642  test    eax, eax
0x1400e8644  js      loc_1400E8962
0x1400e864a  mov     rcx, [rbx+70h]; DeviceObject
0x1400e864e  lea     rdx, [rsp+150h+var_F0]
0x1400e8653  call    FveVolumeGetName
0x1400e8658  mov     edi, eax
0x1400e865a  test    eax, eax
0x1400e865c  js      loc_1400E8962
0x1400e8662  lea     rax, [rsp+150h+var_F0]
0x1400e8667  mov     [rsp+150h+OpenOptions], 20h ; ' '; OpenOptions
0x1400e866f  xorps   xmm0, xmm0
0x1400e8672  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x1400e8676  lea     r9, [rsp+150h+IoStatusBlock]; IoStatusBlock
0x1400e867b  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x1400e8683  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1400e8688  mov     [rsp+150h+ObjectAttributes.RootDirectory], 0
0x1400e8691  mov     edx, 120089h; DesiredAccess
0x1400e8696  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x1400e869d  lea     rcx, [rbp+50h+FileHandle]; FileHandle
0x1400e86a1  mov     [rsp+150h+ShareAccess], 3; ShareAccess
0x1400e86a9  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e86ae  call    cs:__imp_ZwOpenFile
0x1400e86b5  nop     dword ptr [rax+rax+00h]
0x1400e86ba  mov     edi, eax
0x1400e86bc  test    eax, eax
0x1400e86be  js      loc_1400E8962
0x1400e86c4  mov     rcx, [rbp+50h+FileHandle]; FileHandle
0x1400e86c8  mov     eax, 1
0x1400e86cd  mov     [rsp+150h+OutputBufferLength], 0; OutputBufferLength
0x1400e86d5  xorps   xmm0, xmm0
0x1400e86d8  mov     [rsp+150h+OutputBuffer], 0; OutputBuffer
0x1400e86e1  xor     r9d, r9d; ApcContext
0x1400e86e4  mov     dword ptr [rbp+50h+arg_8], eax
0x1400e86e7  xor     r8d, r8d; ApcRoutine
0x1400e86ea  mov     dword ptr [rbp+50h+arg_8+4], eax
0x1400e86ed  xor     edx, edx; Event
0x1400e86ef  mov     [rsp+150h+InputBufferLength], r13d; InputBufferLength
0x1400e86f4  lea     rax, [rbp+50h+arg_8]
0x1400e86f8  mov     [rsp+150h+InputBuffer], rax; InputBuffer
0x1400e86fd  lea     rax, [rsp+150h+IoStatusBlock]
0x1400e8702  mov     [rsp+150h+OpenOptions], 9031Fh; FsControlCode
0x1400e870a  mov     qword ptr [rsp+150h+ShareAccess], rax; IoStatusBlock
0x1400e870f  movups  xmmword ptr [rsp+150h+IoStatusBlock], xmm0
0x1400e8714  call    cs:__imp_ZwFsControlFile
0x1400e871b  nop     dword ptr [rax+rax+00h]
0x1400e8720  mov     edi, eax
0x1400e8722  cmp     eax, 0C00000BBh
0x1400e8727  jz      short loc_1400E8788
0x1400e8729  add     eax, 3FFFFFF1h
0x1400e872e  cmp     eax, 1
0x1400e8731  jbe     short loc_1400E8788
0x1400e8733  cmp     edi, 0C0000002h
0x1400e8739  jz      short loc_1400E8788
0x1400e873b  mov     r9d, 80000005h
0x1400e8741  cmp     edi, r9d
0x1400e8744  jnz     short loc_1400E877E
0x1400e8746  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e874d  lea     rax, WPP_GLOBAL_Control
0x1400e8754  cmp     rcx, rax
0x1400e8757  jz      short loc_1400E87C9
0x1400e8759  mov     eax, [rcx+2Ch]
0x1400e875c  test    r13b, al
0x1400e875f  jz      short loc_1400E87C9
0x1400e8761  cmp     byte ptr [rcx+29h], 4
0x1400e8765  jb      short loc_1400E87C9
0x1400e8767  mov     rcx, [rcx+18h]
0x1400e876b  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400e8772  mov     edx, 54h ; 'T'
0x1400e8777  call    WPP_SF_d
0x1400e877c  jmp     short loc_1400E87C9
0x1400e877e  test    edi, edi
0x1400e8780  js      loc_1400E8962
0x1400e8786  jmp     short loc_1400E87CB
0x1400e8788  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e878f  lea     rax, WPP_GLOBAL_Control
0x1400e8796  cmp     rcx, rax
0x1400e8799  jz      short loc_1400E87C1
0x1400e879b  mov     eax, [rcx+2Ch]
0x1400e879e  test    r13b, al
0x1400e87a1  jz      short loc_1400E87C1
0x1400e87a3  cmp     byte ptr [rcx+29h], 3
0x1400e87a7  jb      short loc_1400E87C1
0x1400e87a9  mov     rcx, [rcx+18h]
0x1400e87ad  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400e87b4  mov     edx, 53h ; 'S'
0x1400e87b9  mov     r9d, edi
0x1400e87bc  call    WPP_SF_d
0x1400e87c1  xorps   xmm0, xmm0
0x1400e87c4  movups  xmmword ptr [rsp+150h+IoStatusBlock], xmm0
0x1400e87c9  xor     edi, edi
0x1400e87cb  mov     r8b, 1
0x1400e87ce  lea     rdx, [rbp+50h+var_B0]
0x1400e87d2  mov     rcx, rbx
0x1400e87d5  call    FvepAcquireDevFveLock
0x1400e87da  cmp     [rsp+150h+IoStatusBlock.Information], 0
0x1400e87e0  mov     r14b, 1
0x1400e87e3  jnz     short loc_1400E8824
0x1400e87e5  mov     rax, [rbx+8]
0x1400e87e9  test    dword ptr [rax+25CCh], 8000000h
0x1400e87f3  jnz     short loc_1400E8824
0x1400e87f5  and     byte ptr [rbx+1130h], 0F7h
0x1400e87fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8803  lea     rax, WPP_GLOBAL_Control
0x1400e880a  cmp     rcx, rax
0x1400e880d  jz      short loc_1400E8864
0x1400e880f  mov     eax, [rcx+2Ch]
0x1400e8812  test    r13b, al
0x1400e8815  jz      short loc_1400E8864
0x1400e8817  cmp     byte ptr [rcx+29h], 4
0x1400e881b  jb      short loc_1400E8864
0x1400e881d  mov     edx, 56h ; 'V'
0x1400e8822  jmp     short loc_1400E8854
0x1400e8824  or      [rbx+1130h], r13b
0x1400e882b  mov     r15b, r14b
0x1400e882e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8835  lea     rax, WPP_GLOBAL_Control
0x1400e883c  cmp     rcx, rax
0x1400e883f  jz      short loc_1400E8864
0x1400e8841  mov     eax, [rcx+2Ch]
0x1400e8844  test    r13b, al
0x1400e8847  jz      short loc_1400E8864
0x1400e8849  cmp     byte ptr [rcx+29h], 4
0x1400e884d  jb      short loc_1400E8864
0x1400e884f  mov     edx, 55h ; 'U'
0x1400e8854  mov     rcx, [rcx+18h]
0x1400e8858  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400e885f  call    WPP_SF_
0x1400e8864  or      byte ptr [rbx+1130h], 4
0x1400e886b  test    [rbx+1130h], r13b
0x1400e8872  jnz     short loc_1400E88A0
0x1400e8874  mov     rcx, [rbx+1160h]
0x1400e887b  test    rcx, rcx
0x1400e887e  jz      short loc_1400E8897
0x1400e8880  call    cs:__imp_ExUnsubscribeWnfStateChange
0x1400e8887  nop     dword ptr [rax+rax+00h]
0x1400e888c  mov     qword ptr [rbx+1160h], 0
0x1400e8897  test    [rbx+1130h], r13b
0x1400e889e  jz      short loc_1400E88F9
0x1400e88a0  mov     eax, [rbx+328h]
0x1400e88a6  test    eax, 17Fh
0x1400e88ab  jz      short loc_1400E88B1
0x1400e88ad  test    al, 40h
0x1400e88af  jz      short loc_1400E88BD
0x1400e88b1  test    dword ptr [rbx+354h], 200h
0x1400e88bb  jz      short loc_1400E88F9
0x1400e88bd  test    dword ptr [rbx+354h], 4000000h
0x1400e88c7  jnz     short loc_1400E88F9
0x1400e88c9  mov     [rsp+150h+InputBuffer], 23C34600h
0x1400e88d2  lea     rdx, FveWimHashCheck
0x1400e88d9  mov     qword ptr [rsp+150h+OpenOptions], 0
0x1400e88e2  xor     r9d, r9d
0x1400e88e5  mov     r8, rbx
0x1400e88e8  mov     qword ptr [rsp+150h+ShareAccess], 0
0x1400e88f1  mov     rcx, rbx
0x1400e88f4  call    FveQueueDelayedAutoWorkItem
0x1400e88f9  test    edi, edi
0x1400e88fb  jns     loc_1400E89A0
0x1400e8901  jmp     short loc_1400E8962
0x1400e8903  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e890a  lea     rdi, WPP_GLOBAL_Control
0x1400e8911  mov     r14b, 1
0x1400e8914  cmp     rcx, rdi
0x1400e8917  jz      short loc_1400E895D
0x1400e8919  mov     eax, [rcx+2Ch]
0x1400e891c  test    r13b, al
0x1400e891f  jz      short loc_1400E895D
0x1400e8921  cmp     byte ptr [rcx+29h], 3
0x1400e8925  jb      short loc_1400E895D
0x1400e8927  mov     edx, 51h ; 'Q'
0x1400e892c  jmp     short loc_1400E894D
0x1400e892e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8935  cmp     rcx, rdi
0x1400e8938  jz      short loc_1400E895D
0x1400e893a  mov     eax, [rcx+2Ch]
0x1400e893d  test    r13b, al
0x1400e8940  jz      short loc_1400E895D
0x1400e8942  cmp     byte ptr [rcx+29h], 3
  ... truncated ...
```
