# RefsGetVolumeMetadataBitmap

- ea: `0x1c01acda4`
- end: `0x1c01ad5a6`
- name: `RefsGetVolumeMetadataBitmap`
- size: `2050`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1c015c128`

## callees

- `0x1c0004330`
- `0x1c00049a0`
- `0x1c0004a30`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c009df4c`
- `0x1c00b2ce8`
- `0x1c016154c`
- `0x1c01acda4`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x1c01ad135`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c01ad135`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ad1db`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ad389`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ad58f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ad1db`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ad389`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ad58f`
- `ntoskrnl!ProbeForWrite` at `0x1c01ad04b`
- `ntoskrnl!ProbeForWrite` at `0x1c01ad04b`
- `ntoskrnl!ProbeForRead` at `0x1c01ad033`
- `ntoskrnl!ProbeForRead` at `0x1c01ad033`

## pseudocode

```c
__int64 __fastcall RefsGetVolumeMetadataBitmap(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // rbx
  SIZE_T v6; // rdi
  _QWORD *v7; // r13
  SIZE_T v8; // r15
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // r9
  ULONG *v14; // r12
  __int64 v16; // rbx
  __int64 v17; // rdi
  unsigned int v18; // r15d
  PDEVICE_OBJECT *v19; // rbx
  __int64 v20; // rcx
  int v21; // eax
  BOOL v22; // eax
  char v23; // [rsp+40h] [rbp-78h]
  int Status; // [rsp+44h] [rbp-74h]
  __int64 v25; // [rsp+50h] [rbp-68h] BYREF
  _QWORD *v26; // [rsp+58h] [rbp-60h]
  char v27; // [rsp+60h] [rbp-58h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+68h] [rbp-50h] BYREF
  __int64 v30; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v31; // [rsp+D8h] [rbp+20h] BYREF

  v30 = 0;
  v25 = 0;
  v31 = 0;
  v26 = 0;
  BitMapHeader = 0;
  if ( (dword_1C012E0B0 & 0x20000) == 0 )
  {
    v4 = -1073741637;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741637);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225659LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225659LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v4;
    goto LABEL_99;
  }
  *(_DWORD *)(a1 + 8) |= 1u;
  v5 = *(_QWORD *)(a2 + 184);
  RefsDecodeFileObject(
    a1,
    *(_QWORD *)(v5 + 48),
    (unsigned int)&v30,
    (unsigned int)&v27,
    (__int64)&v25,
    (__int64)&v31,
    0);
  v6 = *(unsigned int *)(v5 + 16);
  v7 = *(_QWORD **)(v5 + 32);
  v8 = *(unsigned int *)(v5 + 8);
  v14 = (ULONG *)RefsMapUserBuffer(a2, v9, v10, v11);
  if ( !v31 || (*(_WORD *)(v31 + 88) & 0x200) == 0 )
  {
    v4 = -1073741790;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225506LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225506LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v4;
LABEL_99:
    RefsStatusDebug(v4);
    return v4;
  }
  if ( (unsigned int)v8 < 0x18 )
  {
    v4 = -1073741789;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225507LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225507LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v4;
    goto LABEL_99;
  }
  if ( (unsigned int)v6 < 8 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    return 3221225485LL;
  }
  if ( *(_BYTE *)(a2 + 64) )
  {
    ProbeForRead(v7, v6, 1u);
    ProbeForWrite(v14, v8, 1u);
  }
  v16 = *v7;
  v26 = v14 + 4;
  LOBYTE(v12) = 1;
  v17 = v30;
  RefsAcquireSharedVcb(a1, v30, v12, v13);
  v23 = 1;
  if ( (*(_DWORD *)(v17 + 4) & 1) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221226094LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741202);
    Status = -1073741202;
LABEL_76:
    v17 = v30;
    goto LABEL_77;
  }
  if ( v16 < 0 || v16 >= *(_QWORD *)(v17 + 240) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    Status = -1073741811;
    goto LABEL_76;
  }
  v18 = v8 - 16;
  if ( v18 > 0x1FFFFFFF )
    v18 = 0x1FFFFFFF;
  v19 = (PDEVICE_OBJECT *)(v16 & 0x7FFFFFFFFFFFFFF8LL);
  RtlInitializeBitMap(&BitMapHeader, v14 + 4, 8 * v18);
  Status = RefsBindMinstoreTransactionNoRaise(a1);
  if ( Status >= 0 )
  {
    v21 = MsQueryVolumeMetadataBitmap(v20, *(_QWORD *)(v17 + 104), v19, &BitMapHeader);
    Status = v21;
    if ( v21 < 0 )
    {
      v19 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          94,
          WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
          (unsigned int)v21);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(Status);
      RefsRaiseStatusInternal(a1, (unsigned int)Status);
    }
    ExReleaseResourceLite((PERESOURCE)(v17 + 1424));
    v23 = 0;
    *(_QWORD *)v14 = v19;
    *((_QWORD *)v14 + 1) = *(_QWORD *)(v17 + 240) - (_QWORD)v19;
    *(_QWORD *)(a2 + 56) = v18 + 16;
    if ( *(_QWORD *)(v17 + 240) > (__int64)&v19[v18] )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 2147483653LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-2147483643);
      RefsRaiseStatusInternal(a1, 2147483653LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225704LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741592);
      RefsRaiseStatusInternal(a1, 3221225704LL);
    }
  }
LABEL_77:
  if ( v23 )
    ExReleaseResourceLite((PERESOURCE)(v17 + 1424));
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  RefsExtendedCompleteRequestInternal(a1, a2, (unsigned int)Status);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    goto LABEL_89;
  if ( Status < 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
LABEL_88:
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        97,
        WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
        (unsigned int)Status);
      goto LABEL_89;
    }
    v22 = 0;
  }
  else
  {
    v22 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  }
  if ( v22 )
    goto LABEL_88;
LABEL_89:
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1c01acda4  mov     rax, rsp
0x1c01acda7  mov     [rax+8], rcx
0x1c01acdab  push    rbx
0x1c01acdac  push    rsi
0x1c01acdad  push    rdi
0x1c01acdae  push    r12
0x1c01acdb0  push    r13
0x1c01acdb2  push    r14
0x1c01acdb4  push    r15
0x1c01acdb6  sub     rsp, 80h
0x1c01acdbd  mov     r14, rdx
0x1c01acdc0  mov     rsi, rcx
0x1c01acdc3  xor     r15d, r15d
0x1c01acdc6  mov     [rax+18h], r15
0x1c01acdca  mov     [rax-68h], r15
0x1c01acdce  mov     [rax+20h], r15
0x1c01acdd2  mov     [rax-60h], r15
0x1c01acdd6  mov     [rax-70h], r15
0x1c01acdda  xorps   xmm0, xmm0
0x1c01acddd  movups  xmmword ptr [rax-50h], xmm0
0x1c01acde1  mov     [rax-77h], r15b
0x1c01acde5  test    cs:dword_1C012E0B0, 20000h
0x1c01acdef  jnz     loc_1C01ACE79
0x1c01acdf5  mov     al, cs:RefsStatusDebugEnabled
0x1c01acdfb  mov     edi, 0C00000BBh
0x1c01ace00  test    al, al
0x1c01ace02  jz      short loc_1C01ACE18
0x1c01ace04  mov     r8d, 1429h
0x1c01ace0a  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ace11  mov     ecx, edi; Status
0x1c01ace13  call    RefsStatusDebug
0x1c01ace18  mov     r8d, edi
0x1c01ace1b  mov     rdx, r14
0x1c01ace1e  mov     rcx, rsi
0x1c01ace21  call    RefsExtendedCompleteRequestInternal
0x1c01ace26  lea     rbx, WPP_GLOBAL_Control
0x1c01ace2d  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ace34  cmp     rcx, rbx
0x1c01ace37  jz      short loc_1C01ACE60
0x1c01ace39  test    dword ptr [rcx+2Ch], 100h
0x1c01ace40  jz      short loc_1C01ACE60
0x1c01ace42  cmp     byte ptr [rcx+29h], 4
0x1c01ace46  jb      short loc_1C01ACE60
0x1c01ace48  mov     edx, 57h ; 'W'
0x1c01ace4d  mov     r9d, edi
0x1c01ace50  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ace57  mov     rcx, [rcx+18h]
0x1c01ace5b  call    WPP_SF_D
0x1c01ace60  mov     cl, cs:RefsStatusDebugEnabled
0x1c01ace66  test    cl, cl
0x1c01ace68  jz      loc_1C01AD534
0x1c01ace6e  mov     r8d, 142Ah
0x1c01ace74  jmp     loc_1C01AD526
0x1c01ace79  or      dword ptr [rcx+8], 1
0x1c01ace7d  mov     rbx, [rdx+0B8h]
0x1c01ace84  mov     rdx, [rbx+30h]
0x1c01ace88  mov     [rsp+0B8h+var_88], r15b
0x1c01ace8d  lea     rax, [rsp+0B8h+arg_18]
0x1c01ace95  mov     [rsp+0B8h+var_90], rax
0x1c01ace9a  lea     rax, [rsp+0B8h+var_68]
0x1c01ace9f  mov     [rsp+0B8h+var_98], rax
0x1c01acea4  lea     r9, [rsp+0B8h+var_58]
0x1c01acea9  lea     r8, [rsp+0B8h+arg_10]
0x1c01aceb1  call    RefsDecodeFileObject
0x1c01aceb6  mov     edi, [rbx+10h]
0x1c01aceb9  mov     r13, [rbx+20h]
0x1c01acebd  mov     r15d, [rbx+8]
0x1c01acec1  mov     rcx, r14
0x1c01acec4  call    RefsMapUserBuffer
0x1c01acec9  mov     r12, rax
0x1c01acecc  mov     rax, [rsp+0B8h+arg_18]
0x1c01aced4  test    rax, rax
0x1c01aced7  jz      loc_1C01AD4AB
0x1c01acedd  movzx   ecx, word ptr [rax+58h]
0x1c01acee1  mov     eax, 200h
0x1c01acee6  test    ax, cx
0x1c01acee9  jz      loc_1C01AD4AB
0x1c01aceef  cmp     r15d, 18h
0x1c01acef3  jnb     loc_1C01ACF7D
0x1c01acef9  mov     al, cs:RefsStatusDebugEnabled
0x1c01aceff  mov     edi, 0C0000023h
0x1c01acf04  test    al, al
0x1c01acf06  jz      short loc_1C01ACF1C
0x1c01acf08  mov     r8d, 1459h
0x1c01acf0e  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01acf15  mov     ecx, edi; Status
0x1c01acf17  call    RefsStatusDebug
0x1c01acf1c  mov     r8d, edi
0x1c01acf1f  mov     rdx, r14
0x1c01acf22  mov     rcx, rsi
0x1c01acf25  call    RefsExtendedCompleteRequestInternal
0x1c01acf2a  lea     rbx, WPP_GLOBAL_Control
0x1c01acf31  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01acf38  cmp     rcx, rbx
0x1c01acf3b  jz      short loc_1C01ACF64
0x1c01acf3d  test    dword ptr [rcx+2Ch], 100h
0x1c01acf44  jz      short loc_1C01ACF64
0x1c01acf46  cmp     byte ptr [rcx+29h], 4
0x1c01acf4a  jb      short loc_1C01ACF64
0x1c01acf4c  mov     edx, 59h ; 'Y'
0x1c01acf51  mov     r9d, edi
0x1c01acf54  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01acf5b  mov     rcx, [rcx+18h]
0x1c01acf5f  call    WPP_SF_D
0x1c01acf64  mov     cl, cs:RefsStatusDebugEnabled
0x1c01acf6a  test    cl, cl
0x1c01acf6c  jz      loc_1C01AD534
0x1c01acf72  mov     r8d, 145Ah
0x1c01acf78  jmp     loc_1C01AD526
0x1c01acf7d  cmp     edi, 8
0x1c01acf80  jnb     loc_1C01AD020
0x1c01acf86  mov     al, cs:RefsStatusDebugEnabled
0x1c01acf8c  test    al, al
0x1c01acf8e  jz      short loc_1C01ACFA7
0x1c01acf90  mov     r8d, 145Eh
0x1c01acf96  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01acf9d  mov     ecx, 0C000000Dh; Status
0x1c01acfa2  call    RefsStatusDebug
0x1c01acfa7  mov     r8d, 0C000000Dh
0x1c01acfad  mov     rdx, r14
0x1c01acfb0  mov     rcx, rsi
0x1c01acfb3  call    RefsExtendedCompleteRequestInternal
0x1c01acfb8  lea     rbx, WPP_GLOBAL_Control
0x1c01acfbf  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01acfc6  cmp     rcx, rbx
0x1c01acfc9  jz      short loc_1C01ACFF5
0x1c01acfcb  test    dword ptr [rcx+2Ch], 100h
0x1c01acfd2  jz      short loc_1C01ACFF5
0x1c01acfd4  cmp     byte ptr [rcx+29h], 4
0x1c01acfd8  jb      short loc_1C01ACFF5
0x1c01acfda  mov     edx, 5Ah ; 'Z'
0x1c01acfdf  mov     r9d, 0C000000Dh
0x1c01acfe5  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01acfec  mov     rcx, [rcx+18h]
0x1c01acff0  call    WPP_SF_D
0x1c01acff5  mov     cl, cs:RefsStatusDebugEnabled
0x1c01acffb  test    cl, cl
0x1c01acffd  jz      short loc_1C01AD016
0x1c01acfff  mov     r8d, 145Fh
0x1c01ad005  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ad00c  mov     ecx, 0C000000Dh; Status
0x1c01ad011  call    RefsStatusDebug
0x1c01ad016  mov     eax, 0C000000Dh
0x1c01ad01b  jmp     loc_1C01AD536
0x1c01ad020  cmp     byte ptr [r14+40h], 0
0x1c01ad025  jz      short loc_1C01AD057
0x1c01ad027  mov     rdx, rdi; Length
0x1c01ad02a  mov     r8d, 1; Alignment
0x1c01ad030  mov     rcx, r13; Address
0x1c01ad033  call    cs:__imp_ProbeForRead
0x1c01ad03a  nop     dword ptr [rax+rax+00h]
0x1c01ad03f  mov     rdx, r15; Length
0x1c01ad042  mov     r8d, 1; Alignment
0x1c01ad048  mov     rcx, r12; Address
0x1c01ad04b  call    cs:__imp_ProbeForWrite
0x1c01ad052  nop     dword ptr [rax+rax+00h]
0x1c01ad057  mov     rbx, [r13+0]
0x1c01ad05b  mov     [rsp+0B8h+var_70], rbx
0x1c01ad060  lea     r13, [r12+10h]
0x1c01ad065  mov     [rsp+0B8h+var_60], r13
0x1c01ad06a  mov     r8b, 1
0x1c01ad06d  mov     rdi, [rsp+0B8h+arg_10]
0x1c01ad075  mov     rdx, rdi
0x1c01ad078  mov     rcx, rsi
0x1c01ad07b  call    RefsAcquireSharedVcb
0x1c01ad080  mov     [rsp+0B8h+var_78], 1
0x1c01ad085  mov     eax, [rdi+4]
0x1c01ad088  test    al, 1
0x1c01ad08a  jnz     short loc_1C01AD0F7
0x1c01ad08c  lea     rbx, WPP_GLOBAL_Control
0x1c01ad093  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ad09a  cmp     rcx, rbx
0x1c01ad09d  jz      short loc_1C01AD0C9
0x1c01ad09f  mov     eax, [rcx+2Ch]
0x1c01ad0a2  bt      eax, 8
0x1c01ad0a6  jnb     short loc_1C01AD0C9
0x1c01ad0a8  cmp     byte ptr [rcx+29h], 4
0x1c01ad0ac  jb      short loc_1C01AD0C9
0x1c01ad0ae  mov     edx, 5Ch ; '\'
0x1c01ad0b3  mov     r9d, 0C000026Eh
0x1c01ad0b9  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ad0c0  mov     rcx, [rcx+18h]
0x1c01ad0c4  call    WPP_SF_D
0x1c01ad0c9  mov     al, cs:RefsStatusDebugEnabled
0x1c01ad0cf  test    al, al
0x1c01ad0d1  jz      short loc_1C01AD0EA
0x1c01ad0d3  mov     r8d, 1484h
0x1c01ad0d9  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ad0e0  mov     ecx, 0C000026Eh; Status
0x1c01ad0e5  call    RefsStatusDebug
0x1c01ad0ea  mov     [rsp+0B8h+Status], 0C000026Eh
0x1c01ad0f2  jmp     loc_1C01AD373
0x1c01ad0f7  test    rbx, rbx
0x1c01ad0fa  js      loc_1C01AD30D
0x1c01ad100  cmp     rbx, [rdi+0F0h]
0x1c01ad107  jge     loc_1C01AD30D
0x1c01ad10d  add     r15d, 0FFFFFFF0h
0x1c01ad111  mov     eax, 1FFFFFFFh
0x1c01ad116  cmp     r15d, eax
0x1c01ad119  cmova   r15d, eax
0x1c01ad11d  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1c01ad121  mov     [rsp+0B8h+var_70], rbx
0x1c01ad126  mov     r8d, r15d
0x1c01ad129  shl     r8d, 3; SizeOfBitMap
0x1c01ad12d  mov     rdx, r13; BitMapBuffer
0x1c01ad130  lea     rcx, [rsp+0B8h+BitMapHeader]; BitMapHeader
0x1c01ad135  call    cs:__imp_RtlInitializeBitMap
0x1c01ad13c  nop     dword ptr [rax+rax+00h]
0x1c01ad141  mov     rcx, rsi
0x1c01ad144  call    RefsBindMinstoreTransactionNoRaise
0x1c01ad149  mov     [rsp+0B8h+Status], eax
0x1c01ad14d  test    eax, eax
0x1c01ad14f  js      loc_1C01AD304
0x1c01ad155  lea     r9, [rsp+0B8h+BitMapHeader]
0x1c01ad15a  mov     r8, rbx
0x1c01ad15d  mov     rdx, [rdi+68h]
0x1c01ad161  call    MsQueryVolumeMetadataBitmap
0x1c01ad166  mov     [rsp+0B8h+Status], eax
0x1c01ad16a  test    eax, eax
0x1c01ad16c  jns     short loc_1C01AD1D4
0x1c01ad16e  lea     rbx, WPP_GLOBAL_Control
0x1c01ad175  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ad17c  cmp     rcx, rbx
0x1c01ad17f  jz      short loc_1C01AD1A8
0x1c01ad181  test    dword ptr [rcx+2Ch], 100h
0x1c01ad188  jz      short loc_1C01AD1A8
0x1c01ad18a  cmp     byte ptr [rcx+29h], 4
0x1c01ad18e  jb      short loc_1C01AD1A8
0x1c01ad190  mov     edx, 5Eh ; '^'
0x1c01ad195  mov     r9d, eax
0x1c01ad198  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ad19f  mov     rcx, [rcx+18h]
0x1c01ad1a3  call    WPP_SF_D
0x1c01ad1a8  mov     al, cs:RefsStatusDebugEnabled
0x1c01ad1ae  test    al, al
0x1c01ad1b0  jz      short loc_1C01AD1C8
0x1c01ad1b2  mov     r8d, 14B6h
0x1c01ad1b8  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ad1bf  mov     ecx, [rsp+0B8h+Status]; Status
0x1c01ad1c3  call    RefsStatusDebug
0x1c01ad1c8  mov     edx, [rsp+0B8h+Status]
0x1c01ad1cc  mov     rcx, rsi
0x1c01ad1cf  call    RefsRaiseStatusInternal
0x1c01ad1d4  lea     rcx, [rdi+590h]; Resource
0x1c01ad1db  call    cs:__imp_ExReleaseResourceLite
0x1c01ad1e2  nop     dword ptr [rax+rax+00h]
0x1c01ad1e7  mov     [rsp+0B8h+var_78], 0
0x1c01ad1ec  mov     [rsp+0B8h+var_77], 1
0x1c01ad1f1  mov     [r12], rbx
0x1c01ad1f5  mov     rax, [rdi+0F0h]
0x1c01ad1fc  sub     rax, rbx
0x1c01ad1ff  mov     [r12+8], rax
0x1c01ad204  mov     [rsp+0B8h+var_77], 0
0x1c01ad209  lea     ecx, [r15+10h]
0x1c01ad20d  mov     [r14+38h], rcx
0x1c01ad211  mov     eax, r15d
0x1c01ad214  shl     eax, 3
0x1c01ad217  add     rax, rbx
0x1c01ad21a  cmp     [rdi+0F0h], rax
0x1c01ad221  jle     loc_1C01AD304
0x1c01ad227  lea     rbx, WPP_GLOBAL_Control
0x1c01ad22e  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ad235  cmp     rcx, rbx
0x1c01ad238  jz      short loc_1C01AD264
0x1c01ad23a  mov     eax, [rcx+2Ch]
0x1c01ad23d  bt      eax, 8
0x1c01ad241  jnb     short loc_1C01AD264
0x1c01ad243  cmp     byte ptr [rcx+29h], 4
0x1c01ad247  jb      short loc_1C01AD264
0x1c01ad249  mov     edx, 60h ; '`'
0x1c01ad24e  mov     r9d, 80000005h
0x1c01ad254  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ad25b  mov     rcx, [rcx+18h]
0x1c01ad25f  call    WPP_SF_D
0x1c01ad264  mov     al, cs:RefsStatusDebugEnabled
0x1c01ad26a  test    al, al
0x1c01ad26c  jz      short loc_1C01AD285
0x1c01ad26e  mov     r8d, 14E5h
0x1c01ad274  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ad27b  mov     ecx, 80000005h; Status
0x1c01ad280  call    RefsStatusDebug
0x1c01ad285  mov     edx, 80000005h
0x1c01ad28a  mov     rcx, rsi
0x1c01ad28d  call    RefsRaiseStatusInternal
0x1c01ad292  nop
0x1c01ad293  lea     rax, WPP_GLOBAL_Control
0x1c01ad29a  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ad2a1  cmp     rcx, rax
0x1c01ad2a4  jz      short loc_1C01AD2D0
0x1c01ad2a6  mov     eax, [rcx+2Ch]
0x1c01ad2a9  bt      eax, 8
0x1c01ad2ad  jnb     short loc_1C01AD2D0
0x1c01ad2af  cmp     byte ptr [rcx+29h], 4
0x1c01ad2b3  jb      short loc_1C01AD2D0
0x1c01ad2b5  mov     edx, 5Fh ; '_'
0x1c01ad2ba  mov     r9d, 0C00000E8h
0x1c01ad2c0  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ad2c7  mov     rcx, [rcx+18h]
0x1c01ad2cb  call    WPP_SF_D
0x1c01ad2d0  mov     al, cs:RefsStatusDebugEnabled
  ... truncated ...
```
