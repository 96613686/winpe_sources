# IoctlFveStdMdSet

- ea: `0x14006a2c4`
- end: `0x14006a96b`
- name: `IoctlFveStdMdSet`
- size: `1703`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x14006aad0`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000bc14`
- `0x14000e5b0`
- `0x140016f20`
- `0x140017198`
- `0x1400187dc`
- `0x1400189f8`
- `0x140022d40`
- `0x140023040`
- `0x140067b98`
- `0x14006a2c4`
- `0x14006d324`
- `0x140089c90`
- `0x14008b614`
- `0x140090230`
- `0x140090750`
- `0x140092a9c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14006a3fb`
- `ntoskrnl!ProbeForRead` at `0x14006a3fb`
- `ntoskrnl!ZwWriteFile` at `0x14006a7fd`
- `ntoskrnl!ZwWriteFile` at `0x14006a7fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a8b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a91b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a8b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a91b`
- `ntoskrnl!ExAllocatePool2` at `0x14006a41f`
- `ntoskrnl!ExAllocatePool2` at `0x14006a6f5`
- `ntoskrnl!ExAllocatePool2` at `0x14006a41f`
- `ntoskrnl!ExAllocatePool2` at `0x14006a6f5`

## pseudocode

```c
__int64 __fastcall IoctlFveStdMdSet(unsigned int *a1, __int64 a2)
{
  char *v4; // r13
  __int64 v5; // rax
  int inited; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  char *Pool2; // rax
  int StandaloneMetadata; // eax
  __int64 v11; // r9
  __int64 v12; // r12
  void *v13; // rax
  void *v14; // r12
  ULONG v16; // [rsp+30h] [rbp-148h]
  HANDLE FileHandle; // [rsp+68h] [rbp-110h] BYREF
  PVOID P; // [rsp+70h] [rbp-108h]
  volatile void *Address; // [rsp+78h] [rbp-100h]
  char *v20; // [rsp+80h] [rbp-F8h]
  union _LARGE_INTEGER ByteOffset; // [rsp+88h] [rbp-F0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-E0h] BYREF
  UNICODE_STRING SourceString[12]; // [rsp+B0h] [rbp-C8h] BYREF
  PVOID Buffer; // [rsp+180h] [rbp+8h]
  unsigned int Length; // [rsp+188h] [rbp+10h]
  ULONG v27; // [rsp+190h] [rbp+18h] BYREF
  void *Src; // [rsp+198h] [rbp+20h]

  Src = 0;
  memset(SourceString, 0, 0x90u);
  FileHandle = 0;
  IoStatusBlock = 0;
  ByteOffset.QuadPart = 0;
  v4 = 0;
  v20 = 0;
  v27 = 0;
  P = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 179, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
  }
  v5 = *(_QWORD *)(a2 + 184);
  Address = *(volatile void **)(v5 + 32);
  Length = *(_DWORD *)(v5 + 16);
  inited = FveKickAllSystemsGo(a1);
  if ( inited < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_73;
    }
    v8 = 180;
    goto LABEL_10;
  }
  if ( *(_BYTE *)(a2 + 64) )
    ProbeForRead(Address, Length, 8u);
  Pool2 = (char *)ExAllocatePool2(256, Length, 809850438);
  v4 = Pool2;
  v20 = Pool2;
  if ( Pool2 )
    memmove(Pool2, (const void *)Address, Length);
  else
    inited = -1073741670;
  if ( inited < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_73;
    }
    v8 = 182;
    goto LABEL_10;
  }
  inited = FveValidateStandaloneMetadataSetRequest(v4, Length);
  if ( inited < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_73;
    }
    v8 = 183;
    goto LABEL_10;
  }
  inited = FveVolumeInitInfo(a1, SourceString);
  if ( inited < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_73;
    }
    v8 = 184;
    goto LABEL_10;
  }
  inited = FveFsCreateSystemVolumeInformationFolder(SourceString);
  if ( inited < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_73;
    }
    v8 = 185;
    goto LABEL_10;
  }
  StandaloneMetadata = FveReadStandaloneMetadata(SourceString, (GUID *)(v4 + 8));
  inited = StandaloneMetadata;
  if ( StandaloneMetadata < 0 && StandaloneMetadata != -1073741772 && StandaloneMetadata != -1071579126 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_73;
    }
    v8 = 186;
    goto LABEL_10;
  }
  if ( StandaloneMetadata < 0 )
  {
    v11 = *((_QWORD *)v4 + 3);
    if ( v11 )
    {
      inited = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qd(
          WPP_GLOBAL_Control->AttachedDevice,
          188,
          WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
          v11,
          -1073741811);
      }
      goto LABEL_73;
    }
  }
  else if ( *((_QWORD *)P + 2) + 1LL != *((_QWORD *)v4 + 3) )
  {
    inited = -1071579121;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_IId(WPP_GLOBAL_Control->AttachedDevice);
    }
    goto LABEL_73;
  }
  inited = FveCreateStandaloneMetadataFromDataSet(v4 + 32);
  if ( inited < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_73;
    }
    v8 = 189;
LABEL_10:
    WPP_SF_d(v7->AttachedDevice, v8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, (unsigned int)inited);
LABEL_73:
    v14 = 0;
    goto LABEL_74;
  }
  inited = FveLibULongAlignUp(*(unsigned int *)Src, a1[327], &v27);
  if ( inited < 0 )
    goto LABEL_73;
  v12 = v27;
  v13 = (void *)ExAllocatePool2(264, v27, 809850438);
  Buffer = v13;
  if ( v13 )
  {
    memmove(v13, Src, *(unsigned int *)Src);
    inited = FveFileOpenEx(
               SourceString,
               (GUID *)(v4 + 8),
               0,
               (__int64)L"FVESTDMD.",
               0,
               0,
               5u,
               0x886Au,
               0,
               v12,
               0,
               &FileHandle);
    if ( inited >= 0 )
    {
      v16 = v12;
      v14 = Buffer;
      inited = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, v16, &ByteOffset, 0);
      if ( inited < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          191,
          WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
          (unsigned int)inited);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          190,
          WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
          (unsigned int)inited);
      }
      v14 = Buffer;
    }
  }
  else
  {
    inited = -1073741670;
    v14 = 0;
  }
LABEL_74:
  if ( v4 )
    ExFreePoolWithTag(v4, 0x30455646u);
  FveVolumeCleanupInfo(SourceString);
  if ( FileHandle )
    FveFileClose(FileHandle);
  if ( Src )
    FveLibClientFree(Src, *(unsigned int *)Src);
  if ( P )
    ExFreePoolWithTag(P, 0x30455646u);
  if ( v14 )
    ExFreePoolWithTag(v14, 0x30455646u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      192,
      WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids,
      (unsigned int)inited);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14006a2c4  mov     rax, rsp
0x14006a2c7  mov     [rax+8], rcx
0x14006a2cb  push    rbx
0x14006a2cc  push    rsi
0x14006a2cd  push    rdi
0x14006a2ce  push    r12
0x14006a2d0  push    r13
0x14006a2d2  push    r14
0x14006a2d4  push    r15
0x14006a2d6  sub     rsp, 140h
0x14006a2dd  mov     r12, rdx
0x14006a2e0  mov     rbx, rcx
0x14006a2e3  xor     edi, edi
0x14006a2e5  mov     [rax+20h], rdi
0x14006a2e9  xor     edx, edx; Val
0x14006a2eb  mov     r8d, 90h; Size
0x14006a2f1  lea     rcx, [rax-0C8h]; void *
0x14006a2f8  call    memset
0x14006a2fd  mov     [rsp+178h+FileHandle], rdi
0x14006a302  xorps   xmm0, xmm0
0x14006a305  movups  xmmword ptr [rsp+178h+var_E0], xmm0
0x14006a30d  mov     qword ptr [rsp+178h+var_F0], rdi
0x14006a315  mov     r13d, edi
0x14006a318  mov     [rsp+178h+var_F8], rdi
0x14006a320  mov     [rsp+178h+arg_10], edi
0x14006a327  mov     [rsp+178h+P], rdi
0x14006a32c  lea     r15, WPP_GLOBAL_Control
0x14006a333  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a33a  mov     sil, 10h
0x14006a33d  cmp     rcx, r15
0x14006a340  jz      short loc_14006A36A
0x14006a342  mov     eax, [rcx+2Ch]
0x14006a345  test    sil, al
0x14006a348  jz      short loc_14006A36A
0x14006a34a  lea     r14, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006a351  cmp     byte ptr [rcx+29h], 5
0x14006a355  jb      short loc_14006A371
0x14006a357  mov     edx, 0B3h
0x14006a35c  mov     r8, r14
0x14006a35f  mov     rcx, [rcx+18h]
0x14006a363  call    WPP_SF_
0x14006a368  jmp     short loc_14006A371
0x14006a36a  lea     r14, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x14006a371  mov     rax, [r12+0B8h]
0x14006a379  mov     rcx, [rax+20h]
0x14006a37d  mov     [rsp+178h+Address], rcx
0x14006a382  mov     eax, [rax+10h]
0x14006a385  mov     dword ptr [rsp+178h+Length], eax
0x14006a38c  xor     edx, edx
0x14006a38e  mov     rcx, rbx
0x14006a391  call    FveKickAllSystemsGo
0x14006a396  mov     ebx, eax
0x14006a398  test    eax, eax
0x14006a39a  jns     short loc_14006A3DB
0x14006a39c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a3a3  cmp     rcx, r15
0x14006a3a6  jz      loc_14006A8A5
0x14006a3ac  mov     eax, [rcx+2Ch]
0x14006a3af  test    sil, al
0x14006a3b2  jz      loc_14006A8A5
0x14006a3b8  cmp     byte ptr [rcx+29h], 2
0x14006a3bc  jb      loc_14006A8A5
0x14006a3c2  mov     edx, 0B4h
0x14006a3c7  mov     r9d, ebx
0x14006a3ca  mov     r8, r14
0x14006a3cd  mov     rcx, [rcx+18h]
0x14006a3d1  call    WPP_SF_d
0x14006a3d6  jmp     loc_14006A8A5
0x14006a3db  cmp     [r12+40h], dil
0x14006a3e0  mov     r12, [rsp+178h+Address]
0x14006a3e5  jz      short loc_14006A409
0x14006a3e7  mov     r13d, dword ptr [rsp+178h+Length]
0x14006a3ef  mov     edx, r13d; Length
0x14006a3f2  mov     r8d, 8; Alignment
0x14006a3f8  mov     rcx, r12; Address
0x14006a3fb  call    cs:__imp_ProbeForRead
0x14006a402  nop     dword ptr [rax+rax+00h]
0x14006a407  jmp     short loc_14006A411
0x14006a409  mov     r13d, dword ptr [rsp+178h+Length]
0x14006a411  mov     edx, r13d
0x14006a414  mov     ecx, 100h
0x14006a419  mov     r8d, 30455646h
0x14006a41f  call    cs:__imp_ExAllocatePool2
0x14006a426  nop     dword ptr [rax+rax+00h]
0x14006a42b  mov     r13, rax
0x14006a42e  mov     [rsp+178h+var_F8], rax
0x14006a436  test    rax, rax
0x14006a439  jnz     short loc_14006A446
0x14006a43b  mov     ebx, 0C000009Ah
0x14006a440  mov     [rsp+178h+var_118], ebx
0x14006a444  jmp     short loc_14006A45A
0x14006a446  mov     r8d, dword ptr [rsp+178h+Length]; Size
0x14006a44e  mov     rdx, r12; Src
0x14006a451  mov     rcx, r13; void *
0x14006a454  call    memmove
0x14006a459  nop
0x14006a45a  test    ebx, ebx
0x14006a45c  jns     short loc_14006A48E
0x14006a45e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a465  cmp     rcx, r15
0x14006a468  jz      loc_14006A8A5
0x14006a46e  mov     eax, [rcx+2Ch]
0x14006a471  test    sil, al
0x14006a474  jz      loc_14006A8A5
0x14006a47a  cmp     byte ptr [rcx+29h], 2
0x14006a47e  jb      loc_14006A8A5
0x14006a484  mov     edx, 0B6h
0x14006a489  jmp     loc_14006A3C7
0x14006a48e  mov     edx, dword ptr [rsp+178h+Length]
0x14006a495  mov     rcx, r13
0x14006a498  call    FveValidateStandaloneMetadataSetRequest
0x14006a49d  mov     ebx, eax
0x14006a49f  test    eax, eax
0x14006a4a1  jns     short loc_14006A4D3
0x14006a4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a4aa  cmp     rcx, r15
0x14006a4ad  jz      loc_14006A8A5
0x14006a4b3  mov     eax, [rcx+2Ch]
0x14006a4b6  test    sil, al
0x14006a4b9  jz      loc_14006A8A5
0x14006a4bf  cmp     byte ptr [rcx+29h], 2
0x14006a4c3  jb      loc_14006A8A5
0x14006a4c9  mov     edx, 0B7h
0x14006a4ce  jmp     loc_14006A3C7
0x14006a4d3  lea     rdx, [rsp+178h+SourceString]
0x14006a4db  mov     r12, [rsp+178h+arg_0]
0x14006a4e3  mov     rcx, r12
0x14006a4e6  call    FveVolumeInitInfo
0x14006a4eb  mov     ebx, eax
0x14006a4ed  test    eax, eax
0x14006a4ef  jns     short loc_14006A521
0x14006a4f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a4f8  cmp     rcx, r15
0x14006a4fb  jz      loc_14006A8A5
0x14006a501  mov     eax, [rcx+2Ch]
0x14006a504  test    sil, al
0x14006a507  jz      loc_14006A8A5
0x14006a50d  cmp     byte ptr [rcx+29h], 2
0x14006a511  jb      loc_14006A8A5
0x14006a517  mov     edx, 0B8h
0x14006a51c  jmp     loc_14006A3C7
0x14006a521  lea     rcx, [rsp+178h+SourceString]; SourceString
0x14006a529  call    FveFsCreateSystemVolumeInformationFolder
0x14006a52e  mov     ebx, eax
0x14006a530  test    eax, eax
0x14006a532  jns     short loc_14006A564
0x14006a534  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a53b  cmp     rcx, r15
0x14006a53e  jz      loc_14006A8A5
0x14006a544  mov     eax, [rcx+2Ch]
0x14006a547  test    sil, al
0x14006a54a  jz      loc_14006A8A5
0x14006a550  cmp     byte ptr [rcx+29h], 2
0x14006a554  jb      loc_14006A8A5
0x14006a55a  mov     edx, 0B9h
0x14006a55f  jmp     loc_14006A3C7
0x14006a564  lea     rdx, [r13+8]; Guid
0x14006a568  lea     r8, [rsp+178h+P]
0x14006a56d  lea     rcx, [rsp+178h+SourceString]; SourceString
0x14006a575  call    FveReadStandaloneMetadata
0x14006a57a  mov     ebx, eax
0x14006a57c  test    eax, eax
0x14006a57e  jns     short loc_14006A5BE
0x14006a580  cmp     eax, 0C0000034h
0x14006a585  jz      short loc_14006A5BE
0x14006a587  cmp     eax, 0C021000Ah
0x14006a58c  jz      short loc_14006A5BE
0x14006a58e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a595  cmp     rcx, r15
0x14006a598  jz      loc_14006A8A5
0x14006a59e  mov     eax, [rcx+2Ch]
0x14006a5a1  test    sil, al
0x14006a5a4  jz      loc_14006A8A5
0x14006a5aa  cmp     byte ptr [rcx+29h], 2
0x14006a5ae  jb      loc_14006A8A5
0x14006a5b4  mov     edx, 0BAh
0x14006a5b9  jmp     loc_14006A3C7
0x14006a5be  test    ebx, ebx
0x14006a5c0  js      short loc_14006A61E
0x14006a5c2  mov     rax, [rsp+178h+P]
0x14006a5c7  mov     r9, [rax+10h]
0x14006a5cb  mov     rdx, [r13+18h]
0x14006a5cf  lea     rax, [r9+1]
0x14006a5d3  cmp     rax, rdx
0x14006a5d6  jz      loc_14006A66F
0x14006a5dc  mov     ebx, 0C021000Fh
0x14006a5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a5e8  cmp     rcx, r15
0x14006a5eb  jz      loc_14006A8A5
0x14006a5f1  mov     eax, [rcx+2Ch]
0x14006a5f4  test    sil, al
0x14006a5f7  jz      loc_14006A8A5
0x14006a5fd  cmp     byte ptr [rcx+29h], 2
0x14006a601  jb      loc_14006A8A5
0x14006a607  mov     dword ptr [rsp+178h+Buffer], ebx
0x14006a60b  mov     [rsp+178h+IoStatusBlock], rdx
0x14006a610  mov     rcx, [rcx+18h]
0x14006a614  call    WPP_SF_IId
0x14006a619  jmp     loc_14006A8A5
0x14006a61e  mov     r9, [r13+18h]
0x14006a622  test    r9, r9
0x14006a625  jz      short loc_14006A66C
0x14006a627  mov     ebx, 0C000000Dh
0x14006a62c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a633  cmp     rcx, r15
0x14006a636  jz      loc_14006A8A5
0x14006a63c  mov     eax, [rcx+2Ch]
0x14006a63f  test    sil, al
0x14006a642  jz      loc_14006A8A5
0x14006a648  cmp     byte ptr [rcx+29h], 2
0x14006a64c  jb      loc_14006A8A5
0x14006a652  mov     edx, 0BCh
0x14006a657  mov     dword ptr [rsp+178h+IoStatusBlock], ebx
0x14006a65b  mov     r8, r14
0x14006a65e  mov     rcx, [rcx+18h]
0x14006a662  call    WPP_SF_qd
0x14006a667  jmp     loc_14006A8A5
0x14006a66c  mov     rdx, rdi
0x14006a66f  lea     rcx, [r13+20h]; Src
0x14006a673  lea     r8, [rsp+178h+Src]
0x14006a67b  call    FveCreateStandaloneMetadataFromDataSet
0x14006a680  mov     ebx, eax
0x14006a682  test    eax, eax
0x14006a684  jns     short loc_14006A6B6
0x14006a686  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a68d  cmp     rcx, r15
0x14006a690  jz      loc_14006A8A5
0x14006a696  mov     eax, [rcx+2Ch]
0x14006a699  test    sil, al
0x14006a69c  jz      loc_14006A8A5
0x14006a6a2  cmp     byte ptr [rcx+29h], 2
0x14006a6a6  jb      loc_14006A8A5
0x14006a6ac  mov     edx, 0BDh
0x14006a6b1  jmp     loc_14006A3C7
0x14006a6b6  lea     r8, [rsp+178h+arg_10]
0x14006a6be  mov     edx, [r12+51Ch]
0x14006a6c6  mov     rcx, [rsp+178h+Src]
0x14006a6ce  mov     ecx, [rcx]
0x14006a6d0  call    FveLibULongAlignUp
0x14006a6d5  mov     ebx, eax
0x14006a6d7  test    eax, eax
0x14006a6d9  js      loc_14006A8A5
0x14006a6df  mov     r12d, [rsp+178h+arg_10]
0x14006a6e7  mov     r8d, 30455646h
0x14006a6ed  mov     edx, r12d
0x14006a6f0  mov     ecx, 108h
0x14006a6f5  call    cs:__imp_ExAllocatePool2
0x14006a6fc  nop     dword ptr [rax+rax+00h]
0x14006a701  mov     [rsp+178h+arg_0], rax
0x14006a709  test    rax, rax
0x14006a70c  jnz     short loc_14006A71B
0x14006a70e  mov     ebx, 0C000009Ah
0x14006a713  mov     r12, rax
0x14006a716  jmp     loc_14006A8A8
0x14006a71b  mov     rcx, [rsp+178h+Src]
0x14006a723  mov     r8d, [rcx]; Size
0x14006a726  mov     rdx, rcx; Src
0x14006a729  mov     rcx, rax; void *
0x14006a72c  call    memmove
0x14006a731  lea     rdx, [r13+8]; Guid
0x14006a735  lea     rax, [rsp+178h+FileHandle]
0x14006a73a  mov     [rsp+178h+var_120], rax; __int64
0x14006a73f  mov     [rsp+178h+var_128], rdi; __int64
0x14006a744  mov     [rsp+178h+var_130], r12; __int64
0x14006a749  mov     byte ptr [rsp+178h+Key], dil; char
0x14006a74e  mov     dword ptr [rsp+178h+ByteOffset], 886Ah; ULONG
0x14006a756  mov     [rsp+178h+var_148], 5; ULONG
0x14006a75e  mov     dword ptr [rsp+178h+Buffer], edi; ULONG
0x14006a762  mov     byte ptr [rsp+178h+IoStatusBlock], dil; char
0x14006a767  lea     r9, aFvestdmd; "FVESTDMD."
0x14006a76e  xor     r8d, r8d
0x14006a771  lea     rcx, [rsp+178h+SourceString]; SourceString
0x14006a779  call    FveFileOpenEx
0x14006a77e  mov     ebx, eax
0x14006a780  test    eax, eax
0x14006a782  jns     short loc_14006A7BF
0x14006a784  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a78b  cmp     rcx, r15
0x14006a78e  jz      short loc_14006A7B2
0x14006a790  mov     eax, [rcx+2Ch]
0x14006a793  test    sil, al
0x14006a796  jz      short loc_14006A7B2
0x14006a798  cmp     byte ptr [rcx+29h], 2
0x14006a79c  jb      short loc_14006A7B2
0x14006a79e  mov     edx, 0BEh
0x14006a7a3  mov     r9d, ebx
0x14006a7a6  mov     r8, r14
0x14006a7a9  mov     rcx, [rcx+18h]
0x14006a7ad  call    WPP_SF_d
0x14006a7b2  mov     r12, [rsp+178h+arg_0]
0x14006a7ba  jmp     loc_14006A8A8
0x14006a7bf  mov     [rsp+178h+Key], rdi; Key
0x14006a7c4  lea     rax, [rsp+178h+var_F0]
0x14006a7cc  mov     [rsp+178h+ByteOffset], rax; ByteOffset
0x14006a7d1  mov     [rsp+178h+var_148], r12d; Length
0x14006a7d6  mov     r12, [rsp+178h+arg_0]
0x14006a7de  mov     [rsp+178h+Buffer], r12; Buffer
0x14006a7e3  lea     rax, [rsp+178h+var_E0]
0x14006a7eb  mov     [rsp+178h+IoStatusBlock], rax; IoStatusBlock
0x14006a7f0  xor     r9d, r9d; ApcContext
  ... truncated ...
```
