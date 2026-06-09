# IoctlFveStdMdSet

- ea: `0x140068234`
- end: `0x1400688db`
- name: `IoctlFveStdMdSet`
- size: `1703`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x140068a40`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000ba88`
- `0x14000e3c8`
- `0x140016568`
- `0x1400167e0`
- `0x140017dcc`
- `0x140017fe8`
- `0x140021a00`
- `0x140021d00`
- `0x140065b08`
- `0x140068234`
- `0x14006b294`
- `0x140087bf0`
- `0x140089574`
- `0x14008e180`
- `0x14008e6a0`
- `0x1400909ec`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14006836b`
- `ntoskrnl!ProbeForRead` at `0x14006836b`
- `ntoskrnl!ZwWriteFile` at `0x14006876d`
- `ntoskrnl!ZwWriteFile` at `0x14006876d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068825`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068872`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006888b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068825`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068872`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006888b`
- `ntoskrnl!ExAllocatePool2` at `0x14006838f`
- `ntoskrnl!ExAllocatePool2` at `0x140068665`
- `ntoskrnl!ExAllocatePool2` at `0x14006838f`
- `ntoskrnl!ExAllocatePool2` at `0x140068665`

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
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // r12
  void *v13; // rax
  void *v14; // r12
  ULONG v16; // [rsp+30h] [rbp-148h]
  HANDLE FileHandle; // [rsp+68h] [rbp-110h] BYREF
  PVOID P; // [rsp+70h] [rbp-108h] BYREF
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 179, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
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
  v10 = FveReadStandaloneMetadata(SourceString, (GUID *)(v4 + 8), &P);
  inited = v10;
  if ( v10 < 0 && v10 != -1073741772 && v10 != -1071579126 )
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
  if ( v10 < 0 )
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
          WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
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
    WPP_SF_d(v7->AttachedDevice, v8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)inited);
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
          WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
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
          WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
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
      WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids,
      (unsigned int)inited);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140068234  mov     rax, rsp
0x140068237  mov     [rax+8], rcx
0x14006823b  push    rbx
0x14006823c  push    rsi
0x14006823d  push    rdi
0x14006823e  push    r12
0x140068240  push    r13
0x140068242  push    r14
0x140068244  push    r15
0x140068246  sub     rsp, 140h
0x14006824d  mov     r12, rdx
0x140068250  mov     rbx, rcx
0x140068253  xor     edi, edi
0x140068255  mov     [rax+20h], rdi
0x140068259  xor     edx, edx; Val
0x14006825b  mov     r8d, 90h; Size
0x140068261  lea     rcx, [rax-0C8h]; void *
0x140068268  call    memset
0x14006826d  mov     [rsp+178h+FileHandle], rdi
0x140068272  xorps   xmm0, xmm0
0x140068275  movups  xmmword ptr [rsp+178h+var_E0], xmm0
0x14006827d  mov     qword ptr [rsp+178h+var_F0], rdi
0x140068285  mov     r13d, edi
0x140068288  mov     [rsp+178h+var_F8], rdi
0x140068290  mov     [rsp+178h+arg_10], edi
0x140068297  mov     [rsp+178h+P], rdi
0x14006829c  lea     r15, WPP_GLOBAL_Control
0x1400682a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400682aa  mov     sil, 10h
0x1400682ad  cmp     rcx, r15
0x1400682b0  jz      short loc_1400682DA
0x1400682b2  mov     eax, [rcx+2Ch]
0x1400682b5  test    sil, al
0x1400682b8  jz      short loc_1400682DA
0x1400682ba  lea     r14, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400682c1  cmp     byte ptr [rcx+29h], 5
0x1400682c5  jb      short loc_1400682E1
0x1400682c7  mov     edx, 0B3h
0x1400682cc  mov     r8, r14
0x1400682cf  mov     rcx, [rcx+18h]
0x1400682d3  call    WPP_SF_
0x1400682d8  jmp     short loc_1400682E1
0x1400682da  lea     r14, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x1400682e1  mov     rax, [r12+0B8h]
0x1400682e9  mov     rcx, [rax+20h]
0x1400682ed  mov     [rsp+178h+Address], rcx
0x1400682f2  mov     eax, [rax+10h]
0x1400682f5  mov     dword ptr [rsp+178h+Length], eax
0x1400682fc  xor     edx, edx
0x1400682fe  mov     rcx, rbx
0x140068301  call    FveKickAllSystemsGo
0x140068306  mov     ebx, eax
0x140068308  test    eax, eax
0x14006830a  jns     short loc_14006834B
0x14006830c  mov     rcx, cs:WPP_GLOBAL_Control
0x140068313  cmp     rcx, r15
0x140068316  jz      loc_140068815
0x14006831c  mov     eax, [rcx+2Ch]
0x14006831f  test    sil, al
0x140068322  jz      loc_140068815
0x140068328  cmp     byte ptr [rcx+29h], 2
0x14006832c  jb      loc_140068815
0x140068332  mov     edx, 0B4h
0x140068337  mov     r9d, ebx
0x14006833a  mov     r8, r14
0x14006833d  mov     rcx, [rcx+18h]
0x140068341  call    WPP_SF_d
0x140068346  jmp     loc_140068815
0x14006834b  cmp     [r12+40h], dil
0x140068350  mov     r12, [rsp+178h+Address]
0x140068355  jz      short loc_140068379
0x140068357  mov     r13d, dword ptr [rsp+178h+Length]
0x14006835f  mov     edx, r13d; Length
0x140068362  mov     r8d, 8; Alignment
0x140068368  mov     rcx, r12; Address
0x14006836b  call    cs:__imp_ProbeForRead
0x140068372  nop     dword ptr [rax+rax+00h]
0x140068377  jmp     short loc_140068381
0x140068379  mov     r13d, dword ptr [rsp+178h+Length]
0x140068381  mov     edx, r13d
0x140068384  mov     ecx, 100h
0x140068389  mov     r8d, 30455646h
0x14006838f  call    cs:__imp_ExAllocatePool2
0x140068396  nop     dword ptr [rax+rax+00h]
0x14006839b  mov     r13, rax
0x14006839e  mov     [rsp+178h+var_F8], rax
0x1400683a6  test    rax, rax
0x1400683a9  jnz     short loc_1400683B6
0x1400683ab  mov     ebx, 0C000009Ah
0x1400683b0  mov     [rsp+178h+var_118], ebx
0x1400683b4  jmp     short loc_1400683CA
0x1400683b6  mov     r8d, dword ptr [rsp+178h+Length]; Size
0x1400683be  mov     rdx, r12; Src
0x1400683c1  mov     rcx, r13; void *
0x1400683c4  call    memmove
0x1400683c9  nop
0x1400683ca  test    ebx, ebx
0x1400683cc  jns     short loc_1400683FE
0x1400683ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400683d5  cmp     rcx, r15
0x1400683d8  jz      loc_140068815
0x1400683de  mov     eax, [rcx+2Ch]
0x1400683e1  test    sil, al
0x1400683e4  jz      loc_140068815
0x1400683ea  cmp     byte ptr [rcx+29h], 2
0x1400683ee  jb      loc_140068815
0x1400683f4  mov     edx, 0B6h
0x1400683f9  jmp     loc_140068337
0x1400683fe  mov     edx, dword ptr [rsp+178h+Length]
0x140068405  mov     rcx, r13
0x140068408  call    FveValidateStandaloneMetadataSetRequest
0x14006840d  mov     ebx, eax
0x14006840f  test    eax, eax
0x140068411  jns     short loc_140068443
0x140068413  mov     rcx, cs:WPP_GLOBAL_Control
0x14006841a  cmp     rcx, r15
0x14006841d  jz      loc_140068815
0x140068423  mov     eax, [rcx+2Ch]
0x140068426  test    sil, al
0x140068429  jz      loc_140068815
0x14006842f  cmp     byte ptr [rcx+29h], 2
0x140068433  jb      loc_140068815
0x140068439  mov     edx, 0B7h
0x14006843e  jmp     loc_140068337
0x140068443  lea     rdx, [rsp+178h+SourceString]
0x14006844b  mov     r12, [rsp+178h+arg_0]
0x140068453  mov     rcx, r12
0x140068456  call    FveVolumeInitInfo
0x14006845b  mov     ebx, eax
0x14006845d  test    eax, eax
0x14006845f  jns     short loc_140068491
0x140068461  mov     rcx, cs:WPP_GLOBAL_Control
0x140068468  cmp     rcx, r15
0x14006846b  jz      loc_140068815
0x140068471  mov     eax, [rcx+2Ch]
0x140068474  test    sil, al
0x140068477  jz      loc_140068815
0x14006847d  cmp     byte ptr [rcx+29h], 2
0x140068481  jb      loc_140068815
0x140068487  mov     edx, 0B8h
0x14006848c  jmp     loc_140068337
0x140068491  lea     rcx, [rsp+178h+SourceString]; SourceString
0x140068499  call    FveFsCreateSystemVolumeInformationFolder
0x14006849e  mov     ebx, eax
0x1400684a0  test    eax, eax
0x1400684a2  jns     short loc_1400684D4
0x1400684a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400684ab  cmp     rcx, r15
0x1400684ae  jz      loc_140068815
0x1400684b4  mov     eax, [rcx+2Ch]
0x1400684b7  test    sil, al
0x1400684ba  jz      loc_140068815
0x1400684c0  cmp     byte ptr [rcx+29h], 2
0x1400684c4  jb      loc_140068815
0x1400684ca  mov     edx, 0B9h
0x1400684cf  jmp     loc_140068337
0x1400684d4  lea     rdx, [r13+8]; Guid
0x1400684d8  lea     r8, [rsp+178h+P]; P
0x1400684dd  lea     rcx, [rsp+178h+SourceString]; SourceString
0x1400684e5  call    FveReadStandaloneMetadata
0x1400684ea  mov     ebx, eax
0x1400684ec  test    eax, eax
0x1400684ee  jns     short loc_14006852E
0x1400684f0  cmp     eax, 0C0000034h
0x1400684f5  jz      short loc_14006852E
0x1400684f7  cmp     eax, 0C021000Ah
0x1400684fc  jz      short loc_14006852E
0x1400684fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140068505  cmp     rcx, r15
0x140068508  jz      loc_140068815
0x14006850e  mov     eax, [rcx+2Ch]
0x140068511  test    sil, al
0x140068514  jz      loc_140068815
0x14006851a  cmp     byte ptr [rcx+29h], 2
0x14006851e  jb      loc_140068815
0x140068524  mov     edx, 0BAh
0x140068529  jmp     loc_140068337
0x14006852e  test    ebx, ebx
0x140068530  js      short loc_14006858E
0x140068532  mov     rax, [rsp+178h+P]
0x140068537  mov     r9, [rax+10h]
0x14006853b  mov     rdx, [r13+18h]
0x14006853f  lea     rax, [r9+1]
0x140068543  cmp     rax, rdx
0x140068546  jz      loc_1400685DF
0x14006854c  mov     ebx, 0C021000Fh
0x140068551  mov     rcx, cs:WPP_GLOBAL_Control
0x140068558  cmp     rcx, r15
0x14006855b  jz      loc_140068815
0x140068561  mov     eax, [rcx+2Ch]
0x140068564  test    sil, al
0x140068567  jz      loc_140068815
0x14006856d  cmp     byte ptr [rcx+29h], 2
0x140068571  jb      loc_140068815
0x140068577  mov     dword ptr [rsp+178h+Buffer], ebx
0x14006857b  mov     [rsp+178h+IoStatusBlock], rdx
0x140068580  mov     rcx, [rcx+18h]
0x140068584  call    WPP_SF_IId
0x140068589  jmp     loc_140068815
0x14006858e  mov     r9, [r13+18h]
0x140068592  test    r9, r9
0x140068595  jz      short loc_1400685DC
0x140068597  mov     ebx, 0C000000Dh
0x14006859c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400685a3  cmp     rcx, r15
0x1400685a6  jz      loc_140068815
0x1400685ac  mov     eax, [rcx+2Ch]
0x1400685af  test    sil, al
0x1400685b2  jz      loc_140068815
0x1400685b8  cmp     byte ptr [rcx+29h], 2
0x1400685bc  jb      loc_140068815
0x1400685c2  mov     edx, 0BCh
0x1400685c7  mov     dword ptr [rsp+178h+IoStatusBlock], ebx
0x1400685cb  mov     r8, r14
0x1400685ce  mov     rcx, [rcx+18h]
0x1400685d2  call    WPP_SF_qd
0x1400685d7  jmp     loc_140068815
0x1400685dc  mov     rdx, rdi
0x1400685df  lea     rcx, [r13+20h]; Src
0x1400685e3  lea     r8, [rsp+178h+Src]
0x1400685eb  call    FveCreateStandaloneMetadataFromDataSet
0x1400685f0  mov     ebx, eax
0x1400685f2  test    eax, eax
0x1400685f4  jns     short loc_140068626
0x1400685f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400685fd  cmp     rcx, r15
0x140068600  jz      loc_140068815
0x140068606  mov     eax, [rcx+2Ch]
0x140068609  test    sil, al
0x14006860c  jz      loc_140068815
0x140068612  cmp     byte ptr [rcx+29h], 2
0x140068616  jb      loc_140068815
0x14006861c  mov     edx, 0BDh
0x140068621  jmp     loc_140068337
0x140068626  lea     r8, [rsp+178h+arg_10]
0x14006862e  mov     edx, [r12+51Ch]
0x140068636  mov     rcx, [rsp+178h+Src]
0x14006863e  mov     ecx, [rcx]
0x140068640  call    FveLibULongAlignUp
0x140068645  mov     ebx, eax
0x140068647  test    eax, eax
0x140068649  js      loc_140068815
0x14006864f  mov     r12d, [rsp+178h+arg_10]
0x140068657  mov     r8d, 30455646h
0x14006865d  mov     edx, r12d
0x140068660  mov     ecx, 108h
0x140068665  call    cs:__imp_ExAllocatePool2
0x14006866c  nop     dword ptr [rax+rax+00h]
0x140068671  mov     [rsp+178h+arg_0], rax
0x140068679  test    rax, rax
0x14006867c  jnz     short loc_14006868B
0x14006867e  mov     ebx, 0C000009Ah
0x140068683  mov     r12, rax
0x140068686  jmp     loc_140068818
0x14006868b  mov     rcx, [rsp+178h+Src]
0x140068693  mov     r8d, [rcx]; Size
0x140068696  mov     rdx, rcx; Src
0x140068699  mov     rcx, rax; void *
0x14006869c  call    memmove
0x1400686a1  lea     rdx, [r13+8]; Guid
0x1400686a5  lea     rax, [rsp+178h+FileHandle]
0x1400686aa  mov     [rsp+178h+var_120], rax; __int64
0x1400686af  mov     [rsp+178h+var_128], rdi; __int64
0x1400686b4  mov     [rsp+178h+var_130], r12; __int64
0x1400686b9  mov     byte ptr [rsp+178h+Key], dil; char
0x1400686be  mov     dword ptr [rsp+178h+ByteOffset], 886Ah; ULONG
0x1400686c6  mov     [rsp+178h+var_148], 5; ULONG
0x1400686ce  mov     dword ptr [rsp+178h+Buffer], edi; ULONG
0x1400686d2  mov     byte ptr [rsp+178h+IoStatusBlock], dil; char
0x1400686d7  lea     r9, aFvestdmd; "FVESTDMD."
0x1400686de  xor     r8d, r8d
0x1400686e1  lea     rcx, [rsp+178h+SourceString]; SourceString
0x1400686e9  call    FveFileOpenEx
0x1400686ee  mov     ebx, eax
0x1400686f0  test    eax, eax
0x1400686f2  jns     short loc_14006872F
0x1400686f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400686fb  cmp     rcx, r15
0x1400686fe  jz      short loc_140068722
0x140068700  mov     eax, [rcx+2Ch]
0x140068703  test    sil, al
0x140068706  jz      short loc_140068722
0x140068708  cmp     byte ptr [rcx+29h], 2
0x14006870c  jb      short loc_140068722
0x14006870e  mov     edx, 0BEh
0x140068713  mov     r9d, ebx
0x140068716  mov     r8, r14
0x140068719  mov     rcx, [rcx+18h]
0x14006871d  call    WPP_SF_d
0x140068722  mov     r12, [rsp+178h+arg_0]
0x14006872a  jmp     loc_140068818
0x14006872f  mov     [rsp+178h+Key], rdi; Key
0x140068734  lea     rax, [rsp+178h+var_F0]
0x14006873c  mov     [rsp+178h+ByteOffset], rax; ByteOffset
0x140068741  mov     [rsp+178h+var_148], r12d; Length
0x140068746  mov     r12, [rsp+178h+arg_0]
0x14006874e  mov     [rsp+178h+Buffer], r12; Buffer
0x140068753  lea     rax, [rsp+178h+var_E0]
0x14006875b  mov     [rsp+178h+IoStatusBlock], rax; IoStatusBlock
0x140068760  xor     r9d, r9d; ApcContext
  ... truncated ...
```
