# RefsGetVolumeBitmap

- ea: `0x1c01ac238`
- end: `0x1c01ac9f4`
- name: `RefsGetVolumeBitmap`
- size: `1980`
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
- `0x1c00b2ba0`
- `0x1c016154c`
- `0x1c01ac238`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x1c01ac566`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c01ac566`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ac615`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ac7d7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ac9dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ac615`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ac7d7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01ac9dd`
- `ntoskrnl!ProbeForWrite` at `0x1c01ac453`
- `ntoskrnl!ProbeForWrite` at `0x1c01ac453`
- `ntoskrnl!ProbeForRead` at `0x1c01ac43e`
- `ntoskrnl!ProbeForRead` at `0x1c01ac43e`

## pseudocode

```c
__int64 __fastcall RefsGetVolumeBitmap(__int64 a1, __int64 a2)
{
  unsigned int v3; // r14d
  __int64 v4; // rbx
  SIZE_T v5; // rdi
  _BYTE *v6; // r12
  SIZE_T v7; // r15
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r9
  ULONG *v13; // r13
  unsigned int v14; // edi
  __int64 v16; // rbx
  __int64 v17; // rdi
  unsigned int v18; // r15d
  PDEVICE_OBJECT *v19; // rbx
  unsigned int v20; // r12d
  int VolumeBitmap; // eax
  __int64 v22; // rcx
  __int64 v23; // r15
  BOOL v24; // eax
  int v25; // [rsp+20h] [rbp-98h]
  char v26; // [rsp+40h] [rbp-78h]
  int Status; // [rsp+44h] [rbp-74h]
  __int64 v28; // [rsp+60h] [rbp-58h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+68h] [rbp-50h] BYREF
  __int64 v30; // [rsp+78h] [rbp-40h] BYREF
  __int64 v33; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v34; // [rsp+D8h] [rbp+20h] BYREF

  v33 = 0;
  v28 = 0;
  v34 = 0;
  BitMapHeader = 0;
  v3 = 0;
  *(_DWORD *)(a1 + 8) |= 1u;
  v4 = *(_QWORD *)(a2 + 184);
  RefsDecodeFileObject(
    a1,
    *(_QWORD *)(v4 + 48),
    (unsigned int)&v33,
    (unsigned int)&v30,
    (__int64)&v28,
    (__int64)&v34,
    0);
  v5 = *(unsigned int *)(v4 + 16);
  v6 = *(_BYTE **)(v4 + 32);
  v7 = *(unsigned int *)(v4 + 8);
  v13 = (ULONG *)RefsMapUserBuffer(a2, v8, v9, v10);
  if ( !v34 || (*(_WORD *)(v34 + 88) & 0x200) == 0 )
  {
    v14 = -1073741790;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225506LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225506LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v14;
LABEL_94:
    RefsStatusDebug(v14);
    return v14;
  }
  if ( (unsigned int)v7 < 0x18 )
  {
    v14 = -1073741789;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225507LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225507LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v14;
    goto LABEL_94;
  }
  if ( (unsigned int)v5 < 8 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    return 3221225485LL;
  }
  if ( *(_BYTE *)(a2 + 64) )
  {
    ProbeForRead(v6, v5, 1u);
    ProbeForWrite(v13, v7, 1u);
  }
  v16 = *(_QWORD *)v6;
  if ( (unsigned int)v5 >= 0x10 && (v6[8] & 1) != 0 )
    v3 = 1;
  LOBYTE(v11) = 1;
  v17 = v33;
  RefsAcquireSharedVcb(a1, v33, v11, v12);
  v26 = 1;
  if ( (*(_DWORD *)(v17 + 4) & 1) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221226094LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741202);
    Status = -1073741202;
LABEL_71:
    v23 = a2;
    v17 = v33;
    goto LABEL_72;
  }
  if ( v16 < 0 || v16 >= *(_QWORD *)(v17 + 240) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    Status = -1073741811;
    goto LABEL_71;
  }
  v18 = v7 - 16;
  if ( v18 > 0x1FFFFFFF )
    v18 = 0x1FFFFFFF;
  v19 = (PDEVICE_OBJECT *)(v16 & 0x7FFFFFFFFFFFFFF8LL);
  v20 = v18;
  RtlInitializeBitMap(&BitMapHeader, v13 + 4, 8 * v18);
  Status = RefsBindMinstoreTransactionNoRaise(a1);
  if ( Status < 0 )
    goto LABEL_62;
  VolumeBitmap = MsQueryVolumeBitmap(*(struct CmsTransactionContext **)(a1 + 24), *(CmsVolume **)(v17 + 104), v25, v3);
  Status = VolumeBitmap;
  if ( VolumeBitmap < 0 )
  {
    v19 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        83,
        WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
        (unsigned int)VolumeBitmap);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsRaiseStatusInternal(a1, (unsigned int)Status);
  }
  ExReleaseResourceLite((PERESOURCE)(v17 + 1424));
  v26 = 0;
  *(_QWORD *)v13 = v19;
  *((_QWORD *)v13 + 1) = *(_QWORD *)(v17 + 240) - (_QWORD)v19;
  v22 = v18 + 16;
  v23 = a2;
  *(_QWORD *)(a2 + 56) = v22;
  if ( *(_QWORD *)(v17 + 240) > (__int64)&v19[v20] )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 2147483653LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-2147483643);
    RefsRaiseStatusInternal(a1, 2147483653LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225704LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741592);
    RefsRaiseStatusInternal(a1, 3221225704LL);
LABEL_62:
    v23 = a2;
  }
LABEL_72:
  if ( v26 )
    ExReleaseResourceLite((PERESOURCE)(v17 + 1424));
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  RefsExtendedCompleteRequestInternal(a1, v23, (unsigned int)Status);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    goto LABEL_84;
  if ( Status < 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
LABEL_83:
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        86,
        WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
        (unsigned int)Status);
      goto LABEL_84;
    }
    v24 = 0;
  }
  else
  {
    v24 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  }
  if ( v24 )
    goto LABEL_83;
LABEL_84:
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1c01ac238  mov     r11, rsp
0x1c01ac23b  mov     [r11+10h], rdx
0x1c01ac23f  mov     [r11+8], rcx
0x1c01ac243  push    rbx
0x1c01ac244  push    rsi
0x1c01ac245  push    rdi
0x1c01ac246  push    r12
0x1c01ac248  push    r13
0x1c01ac24a  push    r14
0x1c01ac24c  push    r15
0x1c01ac24e  sub     rsp, 80h
0x1c01ac255  mov     rsi, rcx
0x1c01ac258  xor     eax, eax
0x1c01ac25a  mov     [r11+18h], rax
0x1c01ac25e  mov     [r11-58h], rax
0x1c01ac262  mov     [r11+20h], rax
0x1c01ac266  mov     [r11-60h], rax
0x1c01ac26a  mov     [r11-68h], rax
0x1c01ac26e  xorps   xmm0, xmm0
0x1c01ac271  movups  xmmword ptr [rsp+0B8h+BitMapHeader.SizeOfBitMap], xmm0
0x1c01ac276  mov     [rsp+0B8h+var_77], al
0x1c01ac27a  mov     r14d, eax
0x1c01ac27d  mov     [r11-70h], eax
0x1c01ac281  lea     ecx, [rax+1]
0x1c01ac284  or      [rsi+8], ecx
0x1c01ac287  mov     rbx, [rdx+0B8h]
0x1c01ac28e  mov     rdx, [rbx+30h]
0x1c01ac292  mov     [rsp+0B8h+var_88], al
0x1c01ac296  lea     rax, [r11+20h]
0x1c01ac29a  mov     [rsp+0B8h+var_90], rax
0x1c01ac29f  lea     rax, [r11-58h]
0x1c01ac2a3  mov     [rsp+0B8h+var_98], rax
0x1c01ac2a8  lea     r9, [r11-40h]
0x1c01ac2ac  lea     r8, [r11+18h]
0x1c01ac2b0  mov     rcx, rsi
0x1c01ac2b3  call    RefsDecodeFileObject
0x1c01ac2b8  mov     edi, [rbx+10h]
0x1c01ac2bb  mov     r12, [rbx+20h]
0x1c01ac2bf  mov     r15d, [rbx+8]
0x1c01ac2c3  mov     rbx, [rsp+0B8h+arg_8]
0x1c01ac2cb  mov     rcx, rbx
0x1c01ac2ce  call    RefsMapUserBuffer
0x1c01ac2d3  mov     r13, rax
0x1c01ac2d6  mov     rax, [rsp+0B8h+arg_18]
0x1c01ac2de  test    rax, rax
0x1c01ac2e1  jz      loc_1C01AC8F9
0x1c01ac2e7  movzx   ecx, word ptr [rax+58h]
0x1c01ac2eb  mov     eax, 200h
0x1c01ac2f0  test    ax, cx
0x1c01ac2f3  jz      loc_1C01AC8F9
0x1c01ac2f9  cmp     r15d, 18h
0x1c01ac2fd  jnb     loc_1C01AC387
0x1c01ac303  mov     al, cs:RefsStatusDebugEnabled
0x1c01ac309  mov     edi, 0C0000023h
0x1c01ac30e  test    al, al
0x1c01ac310  jz      short loc_1C01AC326
0x1c01ac312  mov     r8d, 1347h
0x1c01ac318  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ac31f  mov     ecx, edi; Status
0x1c01ac321  call    RefsStatusDebug
0x1c01ac326  mov     r8d, edi
0x1c01ac329  mov     rdx, rbx
0x1c01ac32c  mov     rcx, rsi
0x1c01ac32f  call    RefsExtendedCompleteRequestInternal
0x1c01ac334  lea     rbx, WPP_GLOBAL_Control
0x1c01ac33b  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ac342  cmp     rcx, rbx
0x1c01ac345  jz      short loc_1C01AC36E
0x1c01ac347  test    dword ptr [rcx+2Ch], 100h
0x1c01ac34e  jz      short loc_1C01AC36E
0x1c01ac350  cmp     byte ptr [rcx+29h], 4
0x1c01ac354  jb      short loc_1C01AC36E
0x1c01ac356  mov     edx, 4Eh ; 'N'
0x1c01ac35b  mov     r9d, edi
0x1c01ac35e  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ac365  mov     rcx, [rcx+18h]
0x1c01ac369  call    WPP_SF_D
0x1c01ac36e  mov     cl, cs:RefsStatusDebugEnabled
0x1c01ac374  test    cl, cl
0x1c01ac376  jz      loc_1C01AC982
0x1c01ac37c  mov     r8d, 1348h
0x1c01ac382  jmp     loc_1C01AC974
0x1c01ac387  cmp     edi, 8
0x1c01ac38a  jnb     loc_1C01AC42A
0x1c01ac390  mov     al, cs:RefsStatusDebugEnabled
0x1c01ac396  test    al, al
0x1c01ac398  jz      short loc_1C01AC3B1
0x1c01ac39a  mov     r8d, 134Ch
0x1c01ac3a0  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ac3a7  mov     ecx, 0C000000Dh; Status
0x1c01ac3ac  call    RefsStatusDebug
0x1c01ac3b1  mov     r8d, 0C000000Dh
0x1c01ac3b7  mov     rdx, rbx
0x1c01ac3ba  mov     rcx, rsi
0x1c01ac3bd  call    RefsExtendedCompleteRequestInternal
0x1c01ac3c2  lea     rbx, WPP_GLOBAL_Control
0x1c01ac3c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ac3d0  cmp     rcx, rbx
0x1c01ac3d3  jz      short loc_1C01AC3FF
0x1c01ac3d5  test    dword ptr [rcx+2Ch], 100h
0x1c01ac3dc  jz      short loc_1C01AC3FF
0x1c01ac3de  cmp     byte ptr [rcx+29h], 4
0x1c01ac3e2  jb      short loc_1C01AC3FF
0x1c01ac3e4  mov     edx, 4Fh ; 'O'
0x1c01ac3e9  mov     r9d, 0C000000Dh
0x1c01ac3ef  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ac3f6  mov     rcx, [rcx+18h]
0x1c01ac3fa  call    WPP_SF_D
0x1c01ac3ff  mov     cl, cs:RefsStatusDebugEnabled
0x1c01ac405  test    cl, cl
0x1c01ac407  jz      short loc_1C01AC420
0x1c01ac409  mov     r8d, 134Dh
0x1c01ac40f  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ac416  mov     ecx, 0C000000Dh; Status
0x1c01ac41b  call    RefsStatusDebug
0x1c01ac420  mov     eax, 0C000000Dh
0x1c01ac425  jmp     loc_1C01AC984
0x1c01ac42a  cmp     byte ptr [rbx+40h], 0
0x1c01ac42e  jz      short loc_1C01AC45F
0x1c01ac430  mov     rdx, rdi; Length
0x1c01ac433  mov     ebx, 1
0x1c01ac438  mov     r8d, ebx; Alignment
0x1c01ac43b  mov     rcx, r12; Address
0x1c01ac43e  call    cs:__imp_ProbeForRead
0x1c01ac445  nop     dword ptr [rax+rax+00h]
0x1c01ac44a  mov     rdx, r15; Length
0x1c01ac44d  mov     r8d, ebx; Alignment
0x1c01ac450  mov     rcx, r13; Address
0x1c01ac453  call    cs:__imp_ProbeForWrite
0x1c01ac45a  nop     dword ptr [rax+rax+00h]
0x1c01ac45f  mov     rbx, [r12]
0x1c01ac463  mov     [rsp+0B8h+var_68], rbx
0x1c01ac468  lea     rax, [r13+10h]
0x1c01ac46c  mov     [rsp+0B8h+BitMapBuffer], rax
0x1c01ac471  cmp     edi, 10h
0x1c01ac474  jb      short loc_1C01AC48F
0x1c01ac476  mov     al, [r12+8]
0x1c01ac47b  mov     r12d, 1
0x1c01ac481  test    r12b, al
0x1c01ac484  cmovnz  r14d, r12d
0x1c01ac488  mov     [rsp+0B8h+var_70], r14d
0x1c01ac48d  jmp     short loc_1C01AC495
0x1c01ac48f  mov     r12d, 1
0x1c01ac495  mov     r8b, r12b
0x1c01ac498  mov     rdi, [rsp+0B8h+arg_10]
0x1c01ac4a0  mov     rdx, rdi
0x1c01ac4a3  mov     rcx, rsi
0x1c01ac4a6  call    RefsAcquireSharedVcb
0x1c01ac4ab  mov     [rsp+0B8h+var_78], r12b
0x1c01ac4b0  mov     eax, [rdi+4]
0x1c01ac4b3  test    r12b, al
0x1c01ac4b6  jnz     short loc_1C01AC523
0x1c01ac4b8  lea     rbx, WPP_GLOBAL_Control
0x1c01ac4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ac4c6  cmp     rcx, rbx
0x1c01ac4c9  jz      short loc_1C01AC4F5
0x1c01ac4cb  mov     eax, [rcx+2Ch]
0x1c01ac4ce  bt      eax, 8
0x1c01ac4d2  jnb     short loc_1C01AC4F5
0x1c01ac4d4  cmp     byte ptr [rcx+29h], 4
0x1c01ac4d8  jb      short loc_1C01AC4F5
0x1c01ac4da  mov     edx, 51h ; 'Q'
0x1c01ac4df  mov     r9d, 0C000026Eh
0x1c01ac4e5  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ac4ec  mov     rcx, [rcx+18h]
0x1c01ac4f0  call    WPP_SF_D
0x1c01ac4f5  mov     al, cs:RefsStatusDebugEnabled
0x1c01ac4fb  test    al, al
0x1c01ac4fd  jz      short loc_1C01AC516
0x1c01ac4ff  mov     r8d, 137Fh
0x1c01ac505  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ac50c  mov     ecx, 0C000026Eh; Status
0x1c01ac511  call    RefsStatusDebug
0x1c01ac516  mov     [rsp+0B8h+Status], 0C000026Eh
0x1c01ac51e  jmp     loc_1C01AC7B9
0x1c01ac523  test    rbx, rbx
0x1c01ac526  js      loc_1C01AC753
0x1c01ac52c  cmp     rbx, [rdi+0F0h]
0x1c01ac533  jge     loc_1C01AC753
0x1c01ac539  add     r15d, 0FFFFFFF0h
0x1c01ac53d  mov     eax, 1FFFFFFFh
0x1c01ac542  cmp     r15d, eax
0x1c01ac545  cmova   r15d, eax
0x1c01ac549  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1c01ac54d  mov     [rsp+0B8h+var_68], rbx
0x1c01ac552  mov     r12d, r15d
0x1c01ac555  shl     r12d, 3
0x1c01ac559  mov     r8d, r12d; SizeOfBitMap
0x1c01ac55c  mov     rdx, [rsp+0B8h+BitMapBuffer]; BitMapBuffer
0x1c01ac561  lea     rcx, [rsp+0B8h+BitMapHeader]; BitMapHeader
0x1c01ac566  call    cs:__imp_RtlInitializeBitMap
0x1c01ac56d  nop     dword ptr [rax+rax+00h]
0x1c01ac572  mov     rcx, rsi
0x1c01ac575  call    RefsBindMinstoreTransactionNoRaise
0x1c01ac57a  mov     [rsp+0B8h+Status], eax
0x1c01ac57e  test    eax, eax
0x1c01ac580  js      loc_1C01AC742
0x1c01ac586  mov     dword ptr [rsp+0B8h+var_90], r14d
0x1c01ac58b  lea     r9, [rsp+0B8h+BitMapHeader]
0x1c01ac590  mov     r8, rbx
0x1c01ac593  mov     rdx, [rdi+68h]
0x1c01ac597  mov     rcx, [rsi+18h]
0x1c01ac59b  call    MsQueryVolumeBitmap
0x1c01ac5a0  mov     [rsp+0B8h+Status], eax
0x1c01ac5a4  test    eax, eax
0x1c01ac5a6  jns     short loc_1C01AC60E
0x1c01ac5a8  lea     rbx, WPP_GLOBAL_Control
0x1c01ac5af  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ac5b6  cmp     rcx, rbx
0x1c01ac5b9  jz      short loc_1C01AC5E2
0x1c01ac5bb  test    dword ptr [rcx+2Ch], 100h
0x1c01ac5c2  jz      short loc_1C01AC5E2
0x1c01ac5c4  cmp     byte ptr [rcx+29h], 4
0x1c01ac5c8  jb      short loc_1C01AC5E2
0x1c01ac5ca  mov     edx, 53h ; 'S'
0x1c01ac5cf  mov     r9d, eax
0x1c01ac5d2  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ac5d9  mov     rcx, [rcx+18h]
0x1c01ac5dd  call    WPP_SF_D
0x1c01ac5e2  mov     al, cs:RefsStatusDebugEnabled
0x1c01ac5e8  test    al, al
0x1c01ac5ea  jz      short loc_1C01AC602
0x1c01ac5ec  mov     r8d, 13B2h
0x1c01ac5f2  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ac5f9  mov     ecx, [rsp+0B8h+Status]; Status
0x1c01ac5fd  call    RefsStatusDebug
0x1c01ac602  mov     edx, [rsp+0B8h+Status]
0x1c01ac606  mov     rcx, rsi
0x1c01ac609  call    RefsRaiseStatusInternal
0x1c01ac60e  lea     rcx, [rdi+590h]; Resource
0x1c01ac615  call    cs:__imp_ExReleaseResourceLite
0x1c01ac61c  nop     dword ptr [rax+rax+00h]
0x1c01ac621  mov     [rsp+0B8h+var_78], 0
0x1c01ac626  mov     [rsp+0B8h+var_77], 1
0x1c01ac62b  mov     [r13+0], rbx
0x1c01ac62f  mov     rax, [rdi+0F0h]
0x1c01ac636  sub     rax, rbx
0x1c01ac639  mov     [r13+8], rax
0x1c01ac63d  mov     [rsp+0B8h+var_77], 0
0x1c01ac642  lea     ecx, [r15+10h]
0x1c01ac646  mov     r15, [rsp+0B8h+arg_8]
0x1c01ac64e  mov     [r15+38h], rcx
0x1c01ac652  mov     eax, r12d
0x1c01ac655  add     rax, rbx
0x1c01ac658  cmp     [rdi+0F0h], rax
0x1c01ac65f  jle     loc_1C01AC74A
0x1c01ac665  lea     rbx, WPP_GLOBAL_Control
0x1c01ac66c  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ac673  cmp     rcx, rbx
0x1c01ac676  jz      short loc_1C01AC6A2
0x1c01ac678  mov     eax, [rcx+2Ch]
0x1c01ac67b  bt      eax, 8
0x1c01ac67f  jnb     short loc_1C01AC6A2
0x1c01ac681  cmp     byte ptr [rcx+29h], 4
0x1c01ac685  jb      short loc_1C01AC6A2
0x1c01ac687  mov     edx, 55h ; 'U'
0x1c01ac68c  mov     r9d, 80000005h
0x1c01ac692  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ac699  mov     rcx, [rcx+18h]
0x1c01ac69d  call    WPP_SF_D
0x1c01ac6a2  mov     al, cs:RefsStatusDebugEnabled
0x1c01ac6a8  test    al, al
0x1c01ac6aa  jz      short loc_1C01AC6C3
0x1c01ac6ac  mov     r8d, 13E1h
0x1c01ac6b2  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ac6b9  mov     ecx, 80000005h; Status
0x1c01ac6be  call    RefsStatusDebug
0x1c01ac6c3  mov     edx, 80000005h
0x1c01ac6c8  mov     rcx, rsi
0x1c01ac6cb  call    RefsRaiseStatusInternal
0x1c01ac6d0  nop
0x1c01ac6d1  lea     rax, WPP_GLOBAL_Control
0x1c01ac6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01ac6df  cmp     rcx, rax
0x1c01ac6e2  jz      short loc_1C01AC70E
0x1c01ac6e4  mov     eax, [rcx+2Ch]
0x1c01ac6e7  bt      eax, 8
0x1c01ac6eb  jnb     short loc_1C01AC70E
0x1c01ac6ed  cmp     byte ptr [rcx+29h], 4
0x1c01ac6f1  jb      short loc_1C01AC70E
0x1c01ac6f3  mov     edx, 54h ; 'T'
0x1c01ac6f8  mov     r9d, 0C00000E8h
0x1c01ac6fe  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01ac705  mov     rcx, [rcx+18h]
0x1c01ac709  call    WPP_SF_D
0x1c01ac70e  mov     al, cs:RefsStatusDebugEnabled
0x1c01ac714  test    al, al
0x1c01ac716  jz      short loc_1C01AC72F
0x1c01ac718  mov     r8d, 13D7h
0x1c01ac71e  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01ac725  mov     ecx, 0C00000E8h; Status
0x1c01ac72a  call    RefsStatusDebug
0x1c01ac72f  mov     edx, 0C00000E8h
0x1c01ac734  mov     rcx, [rsp+0B8h+arg_0]
0x1c01ac73c  call    RefsRaiseStatusInternal
0x1c01ac741  nop
0x1c01ac742  mov     r15, [rsp+0B8h+arg_8]
0x1c01ac74a  lea     rbx, WPP_GLOBAL_Control
0x1c01ac751  jmp     short loc_1C01AC7C9
0x1c01ac753  lea     rbx, WPP_GLOBAL_Control
  ... truncated ...
```
