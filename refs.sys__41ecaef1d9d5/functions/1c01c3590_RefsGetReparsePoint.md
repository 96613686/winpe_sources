# RefsGetReparsePoint

- ea: `0x1c01c3590`
- end: `0x1c01c3dbb`
- name: `RefsGetReparsePoint`
- size: `2091`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1c015c128`

## callees

- `0x1c000193c`
- `0x1c0003658`
- `0x1c00045c4`
- `0x1c00049a0`
- `0x1c0005768`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003af60`
- `0x1c003b21c`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c00925e8`
- `0x1c00a29c4`
- `0x1c00ad610`
- `0x1c01c3590`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c01c3846`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c01c3846`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1c01c3b17`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1c01c3b17`

## string_xrefs

- `0x1c01c36ad`: `MountSup.c`
- `0x1c01c3704`: `MountSup.c`
- `0x1c01c376e`: `MountSup.c`
- `0x1c01c37e2`: `MountSup.c`
- `0x1c01c3873`: `MountSup.c`
- `0x1c01c3990`: `MountSup.c`
- `0x1c01c3a57`: `MountSup.c`
- `0x1c01c3abc`: `MountSup.c`
- `0x1c01c3b8b`: `MountSup.c`
- `0x1c01c3bf6`: `MountSup.c`
- `0x1c01c3c7a`: `MountSup.c`
- `0x1c01c3cf9`: `MountSup.c`
- `0x1c01c3d17`: `MountSup.c`

## pseudocode

```c
__int64 __fastcall RefsGetReparsePoint(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  unsigned int v5; // ebx
  size_t v6; // r12
  PVOID v7; // r15
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // rdx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // r8
  int v14; // eax
  signed int v15; // eax
  int v16; // r8d
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19; // ebx
  PREPARSE_DATA_BUFFER v20; // rsi
  size_t v21; // rbx
  char v23; // [rsp+50h] [rbp-158h]
  int Status; // [rsp+54h] [rbp-154h]
  ULONG BufferLength; // [rsp+58h] [rbp-150h] BYREF
  __int64 v26; // [rsp+60h] [rbp-148h] BYREF
  PREPARSE_DATA_BUFFER ReparseBuffer; // [rsp+68h] [rbp-140h] BYREF
  __int64 v28; // [rsp+70h] [rbp-138h] BYREF
  _QWORD v29[2]; // [rsp+78h] [rbp-130h] BYREF
  __int64 v30; // [rsp+88h] [rbp-120h] BYREF
  __int128 v31; // [rsp+90h] [rbp-118h] BYREF
  _BYTE v32[208]; // [rsp+A0h] [rbp-108h] BYREF

  v29[1] = a1;
  v30 = 0;
  v29[0] = 0;
  v26 = 0;
  v28 = 0;
  v23 = 0;
  memset(v32, 0, sizeof(v32));
  v31 = 0;
  BufferLength = 0;
  ReparseBuffer = 0;
  v4 = a2[23];
  if ( (unsigned int)RefsDecodeFileObject(
                       a1,
                       *(_QWORD *)(v4 + 48),
                       (unsigned int)&v30,
                       (unsigned int)v29,
                       (__int64)&v26,
                       (__int64)&v28,
                       1)
     - 2 > 1 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v5 = -1073741811;
    }
    else
    {
      v5 = -1073741811;
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    if ( !RefsStatusDebugEnabled )
      goto LABEL_105;
    goto LABEL_104;
  }
  if ( v28 && (*(_DWORD *)(v28 + 4) & 0x2000) != 0 )
  {
    v5 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v5;
    goto LABEL_20;
  }
  v6 = *(unsigned int *)(v4 + 8);
  if ( *(_DWORD *)(v4 + 16) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v5 = -1073741811;
    }
    else
    {
      v5 = -1073741811;
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    if ( !RefsStatusDebugEnabled )
      goto LABEL_105;
    goto LABEL_104;
  }
  v7 = (PVOID)a2[3];
  if ( !v7 )
  {
    v8 = a2[1];
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v5 = -1073741592;
      }
      else
      {
        v5 = -1073741592;
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225704LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741592);
      if ( !RefsStatusDebugEnabled )
        goto LABEL_105;
LABEL_104:
      RefsStatusDebug(v5);
LABEL_105:
      RefsExtendedCompleteRequestInternal(a1, a2, v5);
      return v5;
    }
    if ( (*(_BYTE *)(v8 + 10) & 5) != 0 )
      v7 = *(PVOID *)(v8 + 24);
    else
      v7 = MmMapLockedPagesSpecifyCache((PMDL)v8, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v7 )
    {
      v5 = -1073741670;
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741670);
      RefsExtendedCompleteRequestInternal(a1, a2, 3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225626LL);
      }
      if ( !RefsStatusDebugEnabled )
        return v5;
LABEL_20:
      RefsStatusDebug(v5);
      return v5;
    }
  }
  a2[7] = 0;
  *(_DWORD *)(a1 + 8) |= 1u;
  v9 = v26;
  v10 = v29[0];
  RefsAcquireExclusiveFcb(a1, v29[0], v26, 0);
  v14 = *(_DWORD *)(v9 + 304);
  if ( (v14 & 0x10000) != 0 )
    v15 = -1073741202;
  else
    v15 = (v14 & 0x1000000) != 0 ? 0xC0000008 : 0;
  Status = v15;
  if ( v15 >= 0 )
  {
    if ( (unsigned __int8)RefsIsFileOpen(v10, v11, v13) )
    {
      RefsInitializeAttributeContext(v32);
      v23 = 1;
      if ( (unsigned __int8)RefsLookupInFileRecord(a1, v10, v16, 192, 0) )
      {
        RefsMapAttributeValue(
          a1,
          v10,
          (unsigned int)&ReparseBuffer,
          (unsigned int)&BufferLength,
          (__int64)&v31,
          (__int64)v32);
        v20 = ReparseBuffer;
        v21 = BufferLength;
        Status = FsRtlValidateReparsePointBuffer(BufferLength, ReparseBuffer);
        if ( Status >= 0 )
        {
          if ( (unsigned int)v21 > (unsigned int)v6 )
          {
            if ( (unsigned int)v6 < 0x1C )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  43,
                  WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
                  3221225507LL);
              }
              if ( RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741789);
              Status = -1073741789;
              goto LABEL_91;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                44,
                WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
                2147483653LL);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(-2147483643);
            Status = -2147483643;
            v21 = v6;
            BufferLength = v6;
            v20 = ReparseBuffer;
          }
          memmove(v7, v20, v21);
          a2[7] = v21;
        }
      }
      else
      {
        if ( (*(_DWORD *)(v10 + 160) & 0x400) != 0 )
        {
          v19 = RefsQueueTriageForDeadFcb(a1, v10, v17, v18);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, v10, v19);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(v19);
          RefsRaiseStatusInternal(a1, v19);
        }
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            42,
            WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids,
            3221226101LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741195);
        Status = -1073741195;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids, 3221225768LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741528);
      Status = -1073741528;
    }
  }
LABEL_91:
  RefsUnmapAttribute(v12, v32, &v31);
  if ( v23 )
    RefsCleanupAttributeContext(a1, v32);
  RefsReleaseFcb(a1, *(_QWORD *)(v26 + 120));
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  RefsExtendedCompleteRequestInternal(a1, a2, (unsigned int)Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1c01c3590  mov     r11, rsp
0x1c01c3593  mov     [r11+18h], rbx
0x1c01c3597  mov     [r11+20h], rsi
0x1c01c359b  push    rdi
0x1c01c359c  push    r12
0x1c01c359e  push    r13
0x1c01c35a0  push    r14
0x1c01c35a2  push    r15
0x1c01c35a4  sub     rsp, 180h
0x1c01c35ab  mov     rax, cs:__security_cookie
0x1c01c35b2  xor     rax, rsp
0x1c01c35b5  mov     [rsp+1A8h+var_38], rax
0x1c01c35bd  mov     r14, rdx
0x1c01c35c0  mov     rdi, rcx
0x1c01c35c3  mov     [rsp+1A8h+var_128], rcx
0x1c01c35cb  xor     r13d, r13d
0x1c01c35ce  mov     [r11-120h], r13
0x1c01c35d5  mov     [rsp+1A8h+var_130], r13
0x1c01c35da  mov     [rsp+1A8h+var_148], r13
0x1c01c35df  mov     [rsp+1A8h+var_138], r13
0x1c01c35e4  mov     [rsp+1A8h+var_158], r13b
0x1c01c35e9  xor     edx, edx; Val
0x1c01c35eb  mov     r8d, 0D0h; Size
0x1c01c35f1  lea     rcx, [r11-108h]; void *
0x1c01c35f8  call    memset
0x1c01c35fd  xorps   xmm0, xmm0
0x1c01c3600  movups  [rsp+1A8h+var_118], xmm0
0x1c01c3608  mov     [rsp+1A8h+BufferLength], r13d
0x1c01c360d  mov     [rsp+1A8h+ReparseBuffer], r13
0x1c01c3612  mov     [rsp+1A8h+var_157], r13b
0x1c01c3617  mov     rbx, [r14+0B8h]
0x1c01c361e  mov     [rsp+1A8h+var_178], 1
0x1c01c3623  lea     rax, [rsp+1A8h+var_138]
0x1c01c3628  mov     qword ptr [rsp+1A8h+Priority], rax
0x1c01c362d  lea     rax, [rsp+1A8h+var_148]
0x1c01c3632  mov     qword ptr [rsp+1A8h+BugCheckOnFailure], rax
0x1c01c3637  lea     r9, [rsp+1A8h+var_130]
0x1c01c363c  lea     r8, [rsp+1A8h+var_120]
0x1c01c3644  mov     rdx, [rbx+30h]
0x1c01c3648  mov     rcx, rdi
0x1c01c364b  call    RefsDecodeFileObject
0x1c01c3650  add     eax, 0FFFFFFFEh
0x1c01c3653  cmp     eax, 1
0x1c01c3656  jbe     short loc_1C01C36D4
0x1c01c3658  lea     rax, WPP_GLOBAL_Control
0x1c01c365f  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01c3666  cmp     rcx, rax
0x1c01c3669  jz      short loc_1C01C3698
0x1c01c366b  test    dword ptr [rcx+2Ch], 100h
0x1c01c3672  jz      short loc_1C01C3698
0x1c01c3674  cmp     byte ptr [rcx+29h], 4
0x1c01c3678  jb      short loc_1C01C3698
0x1c01c367a  lea     edx, [r13+23h]
0x1c01c367e  mov     ebx, 0C000000Dh
0x1c01c3683  mov     r9d, ebx
0x1c01c3686  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c01c368d  mov     rcx, [rcx+18h]
0x1c01c3691  call    WPP_SF_D
0x1c01c3696  jmp     short loc_1C01C369D
0x1c01c3698  mov     ebx, 0C000000Dh
0x1c01c369d  mov     al, cs:RefsStatusDebugEnabled
0x1c01c36a3  test    al, al
0x1c01c36a5  jz      short loc_1C01C36BB
0x1c01c36a7  mov     r8d, 48Ah
0x1c01c36ad  lea     rdx, aMountsupC; "MountSup.c"
0x1c01c36b4  mov     ecx, ebx; Status
0x1c01c36b6  call    RefsStatusDebug
0x1c01c36bb  mov     al, cs:RefsStatusDebugEnabled
0x1c01c36c1  test    al, al
0x1c01c36c3  jz      loc_1C01C3D25
0x1c01c36c9  mov     r8d, 490h
0x1c01c36cf  jmp     loc_1C01C3D17
0x1c01c36d4  mov     rax, [rsp+1A8h+var_138]
0x1c01c36d9  test    rax, rax
0x1c01c36dc  jz      loc_1C01C3781
0x1c01c36e2  mov     eax, [rax+4]
0x1c01c36e5  bt      eax, 0Dh
0x1c01c36e9  jnb     loc_1C01C3781
0x1c01c36ef  mov     al, cs:RefsStatusDebugEnabled
0x1c01c36f5  mov     ebx, 0C000000Dh
0x1c01c36fa  test    al, al
0x1c01c36fc  jz      short loc_1C01C3712
0x1c01c36fe  mov     r8d, 49Ch
0x1c01c3704  lea     rdx, aMountsupC; "MountSup.c"
0x1c01c370b  mov     ecx, ebx; Status
0x1c01c370d  call    RefsStatusDebug
0x1c01c3712  mov     r8d, ebx
0x1c01c3715  mov     rdx, r14
0x1c01c3718  mov     rcx, rdi
0x1c01c371b  call    RefsExtendedCompleteRequestInternal
0x1c01c3720  lea     rax, WPP_GLOBAL_Control
0x1c01c3727  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01c372e  cmp     rcx, rax
0x1c01c3731  jz      short loc_1C01C375A
0x1c01c3733  test    dword ptr [rcx+2Ch], 100h
0x1c01c373a  jz      short loc_1C01C375A
0x1c01c373c  cmp     byte ptr [rcx+29h], 4
0x1c01c3740  jb      short loc_1C01C375A
0x1c01c3742  mov     edx, 24h ; '$'
0x1c01c3747  mov     r9d, ebx
0x1c01c374a  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c01c3751  mov     rcx, [rcx+18h]
0x1c01c3755  call    WPP_SF_D
0x1c01c375a  mov     cl, cs:RefsStatusDebugEnabled
0x1c01c3760  test    cl, cl
0x1c01c3762  jz      loc_1C01C3D33
0x1c01c3768  mov     r8d, 49Dh
0x1c01c376e  lea     rdx, aMountsupC; "MountSup.c"
0x1c01c3775  mov     ecx, ebx; Status
0x1c01c3777  call    RefsStatusDebug
0x1c01c377c  jmp     loc_1C01C3D33
0x1c01c3781  mov     eax, [rbx+10h]
0x1c01c3784  mov     r12d, [rbx+8]
0x1c01c3788  test    eax, eax
0x1c01c378a  jz      short loc_1C01C3809
0x1c01c378c  lea     rax, WPP_GLOBAL_Control
0x1c01c3793  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01c379a  cmp     rcx, rax
0x1c01c379d  jz      short loc_1C01C37CD
0x1c01c379f  test    dword ptr [rcx+2Ch], 100h
0x1c01c37a6  jz      short loc_1C01C37CD
0x1c01c37a8  cmp     byte ptr [rcx+29h], 4
0x1c01c37ac  jb      short loc_1C01C37CD
0x1c01c37ae  mov     edx, 25h ; '%'
0x1c01c37b3  mov     ebx, 0C000000Dh
0x1c01c37b8  mov     r9d, ebx
0x1c01c37bb  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c01c37c2  mov     rcx, [rcx+18h]
0x1c01c37c6  call    WPP_SF_D
0x1c01c37cb  jmp     short loc_1C01C37D2
0x1c01c37cd  mov     ebx, 0C000000Dh
0x1c01c37d2  mov     al, cs:RefsStatusDebugEnabled
0x1c01c37d8  test    al, al
0x1c01c37da  jz      short loc_1C01C37F0
0x1c01c37dc  mov     r8d, 4B6h
0x1c01c37e2  lea     rdx, aMountsupC; "MountSup.c"
0x1c01c37e9  mov     ecx, ebx; Status
0x1c01c37eb  call    RefsStatusDebug
0x1c01c37f0  mov     al, cs:RefsStatusDebugEnabled
0x1c01c37f6  test    al, al
0x1c01c37f8  jz      loc_1C01C3D25
0x1c01c37fe  mov     r8d, 4BCh
0x1c01c3804  jmp     loc_1C01C3D17
0x1c01c3809  mov     r15, [r14+18h]
0x1c01c380d  test    r15, r15
0x1c01c3810  jnz     loc_1C01C38E2
0x1c01c3816  mov     rcx, [r14+8]; MemoryDescriptorList
0x1c01c381a  test    rcx, rcx
0x1c01c381d  jz      loc_1C01C3CA3
0x1c01c3823  mov     al, [rcx+0Ah]
0x1c01c3826  test    al, 5
0x1c01c3828  jz      short loc_1C01C3830
0x1c01c382a  mov     r15, [rcx+18h]
0x1c01c382e  jmp     short loc_1C01C3855
0x1c01c3830  mov     [rsp+1A8h+Priority], 40000010h; Priority
0x1c01c3838  mov     [rsp+1A8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1c01c383d  xor     r9d, r9d; RequestedAddress
0x1c01c3840  xor     edx, edx; AccessMode
0x1c01c3842  lea     r8d, [r9+1]; CacheType
0x1c01c3846  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1c01c384d  nop     dword ptr [rax+rax+00h]
0x1c01c3852  mov     r15, rax
0x1c01c3855  test    r15, r15
0x1c01c3858  jnz     loc_1C01C38E2
0x1c01c385e  mov     al, cs:RefsStatusDebugEnabled
0x1c01c3864  mov     ebx, 0C000009Ah
0x1c01c3869  test    al, al
0x1c01c386b  jz      short loc_1C01C3881
0x1c01c386d  mov     r8d, 4CFh
0x1c01c3873  lea     rdx, aMountsupC; "MountSup.c"
0x1c01c387a  mov     ecx, ebx; Status
0x1c01c387c  call    RefsStatusDebug
0x1c01c3881  mov     r8d, ebx
0x1c01c3884  mov     rdx, r14
0x1c01c3887  mov     rcx, rdi
0x1c01c388a  call    RefsExtendedCompleteRequestInternal
0x1c01c388f  lea     rax, WPP_GLOBAL_Control
0x1c01c3896  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01c389d  cmp     rcx, rax
0x1c01c38a0  jz      short loc_1C01C38C9
0x1c01c38a2  test    dword ptr [rcx+2Ch], 100h
0x1c01c38a9  jz      short loc_1C01C38C9
0x1c01c38ab  cmp     byte ptr [rcx+29h], 4
0x1c01c38af  jb      short loc_1C01C38C9
0x1c01c38b1  mov     edx, 26h ; '&'
0x1c01c38b6  mov     r9d, ebx
0x1c01c38b9  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c01c38c0  mov     rcx, [rcx+18h]
0x1c01c38c4  call    WPP_SF_D
0x1c01c38c9  mov     cl, cs:RefsStatusDebugEnabled
0x1c01c38cf  test    cl, cl
0x1c01c38d1  jz      loc_1C01C3D33
0x1c01c38d7  mov     r8d, 4D0h
0x1c01c38dd  jmp     loc_1C01C376E
0x1c01c38e2  mov     [r14+38h], r13
0x1c01c38e6  or      dword ptr [rdi+8], 1
0x1c01c38ea  xor     r9d, r9d
0x1c01c38ed  mov     rbx, [rsp+1A8h+var_148]
0x1c01c38f2  mov     r8, rbx
0x1c01c38f5  mov     rsi, [rsp+1A8h+var_130]
0x1c01c38fa  mov     rdx, rsi
0x1c01c38fd  mov     rcx, rdi
0x1c01c3900  call    RefsAcquireExclusiveFcb
0x1c01c3905  mov     [rsp+1A8h+var_157], 1
0x1c01c390a  mov     eax, [rbx+130h]
0x1c01c3910  bt      eax, 10h
0x1c01c3914  jnb     short loc_1C01C391D
0x1c01c3916  mov     eax, 0C000026Eh
0x1c01c391b  jmp     short loc_1C01C392B
0x1c01c391d  and     eax, 1000000h
0x1c01c3922  neg     eax
0x1c01c3924  sbb     eax, eax
0x1c01c3926  and     eax, 0C0000008h
0x1c01c392b  mov     [rsp+1A8h+Status], eax
0x1c01c392f  test    eax, eax
0x1c01c3931  js      loc_1C01C3C2D
0x1c01c3937  mov     rcx, rsi
0x1c01c393a  call    RefsIsFileOpen
0x1c01c393f  test    al, al
0x1c01c3941  jnz     short loc_1C01C39AE
0x1c01c3943  lea     rax, WPP_GLOBAL_Control
0x1c01c394a  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01c3951  cmp     rcx, rax
0x1c01c3954  jz      short loc_1C01C3980
0x1c01c3956  mov     eax, [rcx+2Ch]
0x1c01c3959  bt      eax, 8
0x1c01c395d  jnb     short loc_1C01C3980
0x1c01c395f  cmp     byte ptr [rcx+29h], 4
0x1c01c3963  jb      short loc_1C01C3980
0x1c01c3965  mov     edx, 28h ; '('
0x1c01c396a  mov     r9d, 0C0000128h
0x1c01c3970  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c01c3977  mov     rcx, [rcx+18h]
0x1c01c397b  call    WPP_SF_D
0x1c01c3980  mov     al, cs:RefsStatusDebugEnabled
0x1c01c3986  test    al, al
0x1c01c3988  jz      short loc_1C01C39A1
0x1c01c398a  mov     r8d, 500h
0x1c01c3990  lea     rdx, aMountsupC; "MountSup.c"
0x1c01c3997  mov     ecx, 0C0000128h; Status
0x1c01c399c  call    RefsStatusDebug
0x1c01c39a1  mov     [rsp+1A8h+Status], 0C0000128h
0x1c01c39a9  jmp     loc_1C01C3C2D
0x1c01c39ae  lea     rcx, [rsp+1A8h+var_108]
0x1c01c39b6  call    RefsInitializeAttributeContext
0x1c01c39bb  mov     [rsp+1A8h+var_158], 1
0x1c01c39c0  lea     rax, [rsp+1A8h+var_108]
0x1c01c39c8  mov     [rsp+1A8h+var_160], rax
0x1c01c39cd  mov     [rsp+1A8h+var_178], r13b
0x1c01c39d2  mov     qword ptr [rsp+1A8h+BugCheckOnFailure], r13
0x1c01c39d7  mov     r9d, 0C0h
0x1c01c39dd  mov     rdx, rsi
0x1c01c39e0  mov     rcx, rdi
0x1c01c39e3  call    RefsLookupInFileRecord
0x1c01c39e8  test    al, al
0x1c01c39ea  jnz     loc_1C01C3ADA
0x1c01c39f0  test    dword ptr [rsi+0A0h], 400h
0x1c01c39fa  jz      short loc_1C01C3A6F
0x1c01c39fc  mov     rdx, rsi
0x1c01c39ff  mov     rcx, rdi
0x1c01c3a02  call    RefsQueueTriageForDeadFcb
0x1c01c3a07  mov     ebx, eax
0x1c01c3a09  lea     rax, WPP_GLOBAL_Control
0x1c01c3a10  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01c3a17  cmp     rcx, rax
0x1c01c3a1a  jz      short loc_1C01C3A47
0x1c01c3a1c  test    dword ptr [rcx+2Ch], 100h
0x1c01c3a23  jz      short loc_1C01C3A47
0x1c01c3a25  cmp     byte ptr [rcx+29h], 4
0x1c01c3a29  jb      short loc_1C01C3A47
0x1c01c3a2b  mov     edx, 29h ; ')'
0x1c01c3a30  mov     [rsp+1A8h+BugCheckOnFailure], ebx
0x1c01c3a34  mov     r9, rsi
0x1c01c3a37  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c01c3a3e  mov     rcx, [rcx+18h]
0x1c01c3a42  call    WPP_SF_qd
0x1c01c3a47  mov     al, cs:RefsStatusDebugEnabled
0x1c01c3a4d  test    al, al
0x1c01c3a4f  jz      short loc_1C01C3A65
0x1c01c3a51  mov     r8d, 521h
0x1c01c3a57  lea     rdx, aMountsupC; "MountSup.c"
0x1c01c3a5e  mov     ecx, ebx; Status
0x1c01c3a60  call    RefsStatusDebug
0x1c01c3a65  mov     edx, ebx
0x1c01c3a67  mov     rcx, rdi
0x1c01c3a6a  call    RefsRaiseStatusInternal
0x1c01c3a6f  lea     rax, WPP_GLOBAL_Control
0x1c01c3a76  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01c3a7d  cmp     rcx, rax
0x1c01c3a80  jz      short loc_1C01C3AAC
0x1c01c3a82  mov     eax, [rcx+2Ch]
0x1c01c3a85  bt      eax, 8
0x1c01c3a89  jnb     short loc_1C01C3AAC
0x1c01c3a8b  cmp     byte ptr [rcx+29h], 4
0x1c01c3a8f  jb      short loc_1C01C3AAC
0x1c01c3a91  mov     edx, 2Ah ; '*'
0x1c01c3a96  mov     r9d, 0C0000275h
0x1c01c3a9c  lea     r8, WPP_3e5fcb63d1a135eac59067d9d65bc2e5_Traceguids
0x1c01c3aa3  mov     rcx, [rcx+18h]
0x1c01c3aa7  call    WPP_SF_D
  ... truncated ...
```
