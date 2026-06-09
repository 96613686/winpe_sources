# CscQueryDirectory

- ea: `0x14008ee80`
- end: `0x14008f953`
- name: `CscQueryDirectory`
- size: `2771`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `installer_update`

## callees

- `0x140003a00`
- `0x1400084f0`
- `0x14000e100`
- `0x140012860`
- `0x1400169d4`
- `0x140018930`
- `0x1400190ec`
- `0x140019204`
- `0x14001a494`
- `0x14001fec4`
- `0x14002f010`
- `0x14002f040`
- `0x14002f0f0`
- `0x14002f440`
- `0x14006e884`
- `0x1400779f4`
- `0x140077c94`
- `0x1400787d0`
- `0x140078fd0`
- `0x1400798f8`
- `0x140080560`
- `0x14008ee80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008f54b`
- `ntoskrnl!ExAllocatePool2` at `0x14008f54b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008f8e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008f8e0`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14008ef34`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14008ef34`
- `rdbss!RxDowngradeFcbToSharedInMRx` at `0x14008f322`
- `rdbss!RxDowngradeFcbToSharedInMRx` at `0x14008f322`
- `rdbss!RxSubjectContextFromRxContext` at `0x14008f43c`
- `rdbss!RxSubjectContextFromRxContext` at `0x14008f43c`

## pseudocode

```c
__int64 __fastcall CscQueryDirectory(__int64 a1)
{
  _WORD *v2; // rsi
  struct _UNICODE_STRING *v3; // rcx
  __int64 v4; // r13
  size_t v5; // r15
  bool v6; // bl
  bool v7; // r12
  __int64 v8; // r14
  int DirResetEnumContext; // ebx
  int v10; // esi
  unsigned __int8 v11; // r10
  char v12; // al
  int v13; // r8d
  int v14; // edx
  char v15; // cl
  int v16; // ebx
  int v17; // r8d
  char v18; // r8
  __int64 v19; // r9
  _DWORD *v20; // rdi
  __int64 v21; // r9
  PVOID Pool2; // rax
  void **v23; // r12
  char v24; // cl
  unsigned int v25; // edi
  char v26; // dl
  int v27; // eax
  PVOID v28; // rax
  char v30[8]; // [rsp+70h] [rbp-C8h] BYREF
  void *v31; // [rsp+78h] [rbp-C0h]
  void **v32; // [rsp+80h] [rbp-B8h]
  PVOID P; // [rsp+88h] [rbp-B0h]
  int v34; // [rsp+90h] [rbp-A8h]
  _DWORD *v35; // [rsp+98h] [rbp-A0h]
  __int64 v36; // [rsp+A0h] [rbp-98h] BYREF
  void *Src; // [rsp+A8h] [rbp-90h]
  size_t Size; // [rsp+B0h] [rbp-88h]
  __int128 v39; // [rsp+B8h] [rbp-80h] BYREF
  __int128 v40; // [rsp+C8h] [rbp-70h]
  __int64 v41; // [rsp+D8h] [rbp-60h]
  __int64 v42; // [rsp+E0h] [rbp-58h]
  __int64 v43; // [rsp+E8h] [rbp-50h]
  void *v44; // [rsp+F0h] [rbp-48h]
  __int128 v45; // [rsp+F8h] [rbp-40h] BYREF

  v2 = *(_WORD **)(a1 + 56);
  v3 = *(struct _UNICODE_STRING **)(a1 + 64);
  Src = v3;
  v4 = *(_QWORD *)(a1 + 72);
  v43 = v4;
  v35 = (_DWORD *)(a1 + 472);
  v5 = *(unsigned int *)(a1 + 472);
  Size = v5;
  v32 = (void **)(a1 + 456);
  v31 = *(void **)(a1 + 456);
  v44 = v31;
  P = 0;
  v6 = *(_QWORD *)(a1 + 80) != (_QWORD)CscDeviceObject;
  v7 = !v3[5].Buffer || FsRtlDoesNameContainWildCards(v3 + 5);
  v8 = 0;
  v36 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v45 = 0;
  CscGetContexts((_QWORD *)a1, &v39);
  CscUpdateAndCaptureConnectionStateEx((__int64)v2, v4, a1, 1u, (__int64)&v45, 1);
  if ( (BYTE1(v45) & 0x40) != 0 )
  {
    DirResetEnumContext = CscDetermineAbortStatus(&v45);
    v10 = 4467;
LABEL_105:
    Pool2 = 0;
    v23 = v32;
    goto LABEL_106;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
  {
    v16 = v43;
  }
  else
  {
    v11 = 89;
    v12 = 89;
    LODWORD(v42) = 78;
    if ( !*(_BYTE *)(a1 + 518) )
      v12 = 78;
    v13 = 89;
    if ( !*(_BYTE *)(a1 + 519) )
      v13 = 78;
    v14 = 89;
    if ( !*(_BYTE *)(a1 + 516) )
      v14 = 78;
    v15 = 89;
    if ( !*(_BYTE *)(a1 + 517) )
      v15 = v42;
    if ( !v6 )
      v11 = 78;
    v16 = v43;
    WPP_SF_cqqqcccdcZ(
      WPP_GLOBAL_Control->AttachedDevice,
      v14,
      v13,
      v11,
      (char)v2,
      v43,
      v39,
      v15,
      v14,
      v13,
      *(_DWORD *)(a1 + 512),
      v12,
      (__int64)Src + 80);
  }
  if ( *v2 != 0xEC21 )
  {
    v10 = 4484;
    DirResetEnumContext = -1073741811;
    goto LABEL_105;
  }
  if ( *(_BYTE *)(a1 + 518) )
  {
    v10 = 4491;
    DirResetEnumContext = -1073741822;
    goto LABEL_105;
  }
  v17 = (unsigned __int8)v45;
  if ( (v45 & 0x20) != 0 )
  {
    if ( (*(_DWORD *)(v40 + 24) & 0x801) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids);
        v17 = (unsigned __int8)v45;
      }
      LOBYTE(v17) = v17 | 0x10;
      LOBYTE(v45) = v17;
    }
    if ( *(_BYTE *)(a1 + 516) || *(_BYTE *)(a1 + 519) )
    {
      v19 = *((_QWORD *)&v39 + 1);
      if ( (*(_DWORD *)(*((_QWORD *)&v39 + 1) + 4LL) & 0x60) == 0 )
      {
        CscDirCtrlBackpatchIfPossible(a1, (_DWORD)v2, v16, (unsigned int)&v39, (__int64)&v45);
        v19 = *((_QWORD *)&v39 + 1);
        v17 = (unsigned __int8)v45;
      }
      LOBYTE(v17) = (v17 & 0x10) != 0;
      DirResetEnumContext = CscQueryDirResetEnumContext(
                              (unsigned int)&v39,
                              *(_DWORD *)(a1 + 448),
                              v17,
                              v7,
                              *(_BYTE *)(a1 + 517),
                              ((HIDWORD(v45) - 4) & 0xFFFFFFFB) == 0,
                              (__int64)Src + 80,
                              *(_DWORD *)(v19 + 36));
      if ( DirResetEnumContext )
      {
        if ( (v45 & 0x10) != 0 )
        {
          v10 = 4544;
          goto LABEL_105;
        }
        LOBYTE(v45) = v45 & 0xDF;
        *(_BYTE *)(v39 + 28) |= 4u;
      }
      switch ( *(_DWORD *)(a1 + 448) )
      {
        case 1:
        case 2:
        case 3:
        case 0xC:
        case 0x25:
        case 0x26:
          break;
        default:
          if ( (v45 & 0x10) != 0 )
          {
            DirResetEnumContext = -1073741108;
            v10 = 4568;
            goto LABEL_105;
          }
          LOBYTE(v45) = v45 & 0xDF;
          *(_BYTE *)(v39 + 28) |= 4u;
          break;
      }
    }
    else
    {
      if ( (*(_BYTE *)(v39 + 28) & 4) != 0 )
      {
        LOBYTE(v17) = v17 & 0xDF;
        LOBYTE(v45) = v17;
      }
      if ( (*(_BYTE *)(v39 + 28) & 2) != 0 )
      {
        LOBYTE(v17) = v17 | 0x10;
        LOBYTE(v45) = v17;
      }
      if ( (v17 & 0x10) != 0 )
        *(_BYTE *)(v39 + 28) |= 2u;
      v18 = *(_BYTE *)(v39 + 28);
      if ( (v18 & 4) == 0 && *(_DWORD *)(v39 + 24) != *(_DWORD *)(*((_QWORD *)&v39 + 1) + 36LL) )
      {
        *(_BYTE *)(v39 + 28) = v18 | 2;
        LOBYTE(v45) = v45 | 0x10;
      }
      if ( *(_DWORD *)(a1 + 448) != *(_DWORD *)(v39 + 8) )
      {
        DirResetEnumContext = -1073741811;
        v10 = 4631;
        goto LABEL_105;
      }
    }
  }
  RxDowngradeFcbToSharedInMRx(a1, v2);
  if ( (v45 & 0x30) != 0 )
  {
    v10 = 0;
    v8 = *(_QWORD *)(v39 + 16);
    v42 = v8;
    memset(*v32, 0, v5);
    if ( (*(_BYTE *)(v39 + 28) & 8) != 0 )
    {
      DirResetEnumContext = 0;
      goto LABEL_105;
    }
    DirResetEnumContext = RxSubjectContextFromRxContext(a1, &v36);
    if ( DirResetEnumContext < 0 )
    {
      v10 = 4723;
      goto LABEL_105;
    }
    if ( *(_BYTE *)(a1 + 516) || *(_BYTE *)(a1 + 519) )
    {
      v30[0] = 0;
      if ( (v45 & 0x10) == 0
        && ((*(_DWORD *)(*((_QWORD *)&v39 + 1) + 4LL) & 0x80u) != 0
         || (*(_DWORD *)(v40 + 24) & 1) == 0 && ((HIDWORD(v45) - 4) & 0xFFFFFFFB) == 0) )
      {
        v30[0] = 1;
      }
      DirResetEnumContext = CscStoreOpenEntryHandle(
                              v8,
                              *(_QWORD *)(*((_QWORD *)&v39 + 1) + 56LL),
                              0,
                              v36,
                              *(_DWORD *)(v43 + 120),
                              0,
                              (__int64)v30,
                              0);
      if ( DirResetEnumContext )
      {
        v10 = 4769;
        goto LABEL_105;
      }
      DirResetEnumContext = CscQueryDirGetNextLocalBuffer(&v39, (__int64)Src + 80, 1, *(_BYTE *)(a1 + 517), v36);
      if ( DirResetEnumContext )
      {
        v10 = 4786;
        goto LABEL_105;
      }
    }
    Pool2 = (PVOID)ExAllocatePool2(64, v5, 1917088579, v21);
    P = Pool2;
    Src = Pool2;
    v23 = v32;
    if ( !Pool2 )
    {
      DirResetEnumContext = -1073741670;
      v10 = 4809;
LABEL_106:
      v25 = 0;
      v26 = 0;
      goto LABEL_107;
    }
    v30[0] = 1;
    *v32 = Pool2;
    QueryDirEnumSet(v8 + 72, *(_DWORD *)(a1 + 448), (_DWORD)Pool2, v5, 0);
    v24 = v45;
    if ( (v45 & 0x10) != 0 )
      goto LABEL_99;
    if ( (*(_BYTE *)(v8 + 33008) & 1) == 0 )
    {
      DirResetEnumContext = CscQueryDirOnlineAndUpdateCache(a1, &v39, &v45, v36);
      v34 = DirResetEnumContext;
      if ( DirResetEnumContext < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            41,
            WPP_f1d0093ed16337749994f41f70b429cb_Traceguids,
            (unsigned int)DirResetEnumContext);
        }
        v10 = 4845;
        Pool2 = P;
        v25 = 0;
        v26 = v30[0];
        goto LABEL_107;
      }
      if ( (*(_BYTE *)(v8 + 33008) & 1) != 0 )
      {
        DirResetEnumContext = CscQueryDirRemoveStaleEntries(&v39, v36);
        if ( DirResetEnumContext )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              42,
              WPP_f1d0093ed16337749994f41f70b429cb_Traceguids,
              (unsigned int)DirResetEnumContext);
          }
          DirResetEnumContext = 0;
        }
      }
      if ( (DirResetEnumContext & 0xC0000000) == 0xC0000000 )
      {
        v10 = 4875;
        Pool2 = P;
        v25 = 0;
        v26 = v30[0];
LABEL_107:
        if ( v26 )
        {
          RtlCopyVolatileMemory(v31, Pool2, v25);
          *v23 = v31;
        }
        if ( DirResetEnumContext < 0 )
        {
          memset(*v23, 0, (unsigned int)v5);
          v20 = v35;
        }
        else if ( v25 )
        {
          if ( (_QWORD)v39 )
            *(_BYTE *)(v39 + 28) |= 1u;
          v27 = v5 - v25;
          v20 = v35;
          *v35 = v27;
          DirResetEnumContext = 0;
        }
        else
        {
          if ( (*(_DWORD *)(v40 + 24) & 0x801) != 0 || (_QWORD)v39 && (*(_BYTE *)(v39 + 28) & 1) != 0 )
            DirResetEnumContext = -2147483642;
          else
            DirResetEnumContext = -1073741809;
          v20 = v35;
          if ( (_QWORD)v39 )
            *(_BYTE *)(v39 + 28) |= 8u;
        }
        goto LABEL_122;
      }
      DirResetEnumContext = 0;
      v24 = v45;
    }
    if ( (v24 & 0x10) != 0 || (*(_BYTE *)(v8 + 33008) & 1) != 0 )
    {
LABEL_99:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids);
      DirResetEnumContext = CscQueryDirProcessRemainingLocal(&v39, &v45, v36);
      v34 = DirResetEnumContext;
      if ( DirResetEnumContext )
      {
        v10 = 4920;
        Pool2 = P;
        v25 = 0;
        v26 = v30[0];
        goto LABEL_107;
      }
    }
    v25 = *(_DWORD *)(v8 + 108);
    Pool2 = P;
    v26 = v30[0];
    goto LABEL_107;
  }
  if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 192LL) )
  {
    if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
    {
      DirResetEnumContext = -1073741536;
    }
    else
    {
      *(_OWORD *)(a1 + 208) = 0;
      *(_OWORD *)(a1 + 224) = 0;
      *(_QWORD *)(a1 + 240) = 0;
      DirResetEnumContext = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 192LL))(a1);
    }
  }
  else
  {
    DirResetEnumContext = -1073741822;
  }
  v20 = v35;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      40,
      WPP_f1d0093ed16337749994f41f70b429cb_Traceguids,
      (unsigned int)(v5 - *v35),
      DirResetEnumContext);
  CscCheckRdrStatusTransitionIfNetErr((unsigned int)DirResetEnumContext, &v45, v2);
  v10 = 4689;
LABEL_122:
  v28 = P;
  if ( P )
  {
    if ( v8 )
    {
      *(_OWORD *)(v8 + 72) = 0;
      *(_OWORD *)(v8 + 88) = 0;
      *(_OWORD *)(v8 + 104) = 0;
      *(_OWORD *)(v8 + 120) = 0;
    }
    ExFreePoolWithTag(v28, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_DDd(
      WPP_GLOBAL_Control->AttachedDevice,
      44,
      WPP_f1d0093ed16337749994f41f70b429cb_Traceguids,
      (unsigned int)DirResetEnumContext,
      v10,
      v5 - *v20);
  return (unsigned int)DirResetEnumContext;
}

```

## disassembly

```asm
0x14008ee80  mov     [rsp+arg_8], rbx
0x14008ee85  mov     [rsp+arg_10], rsi
0x14008ee8a  push    rdi
0x14008ee8b  push    r12
0x14008ee8d  push    r13
0x14008ee8f  push    r14
0x14008ee91  push    r15
0x14008ee93  sub     rsp, 110h
0x14008ee9a  mov     rax, cs:__security_cookie
0x14008eea1  xor     rax, rsp
0x14008eea4  mov     [rsp+138h+var_30], rax
0x14008eeac  mov     rdi, rcx
0x14008eeaf  mov     rsi, [rcx+38h]
0x14008eeb3  mov     rcx, [rcx+40h]
0x14008eeb7  mov     [rsp+138h+Src], rcx
0x14008eebf  mov     r13, [rdi+48h]
0x14008eec3  mov     [rsp+138h+var_50], r13
0x14008eecb  lea     rax, [rdi+1D8h]
0x14008eed2  mov     [rsp+138h+var_A0], rax
0x14008eeda  mov     r15d, [rax]
0x14008eedd  mov     dword ptr [rsp+138h+Size], r15d
0x14008eee5  mov     dword ptr [rsp+138h+Size+4], 0
0x14008eef0  lea     rax, [rdi+1C8h]
0x14008eef7  mov     [rsp+138h+var_B8], rax
0x14008eeff  mov     rdx, [rax]
0x14008ef02  mov     [rsp+138h+var_C0], rdx
0x14008ef07  mov     [rsp+138h+var_48], rdx
0x14008ef0f  mov     [rsp+138h+P], 0
0x14008ef1b  mov     rax, cs:CscDeviceObject
0x14008ef22  cmp     [rdi+50h], rax
0x14008ef26  setnz   bl
0x14008ef29  cmp     qword ptr [rcx+58h], 0
0x14008ef2e  jz      short loc_14008EF49
0x14008ef30  add     rcx, 50h ; 'P'; Name
0x14008ef34  call    cs:__imp_FsRtlDoesNameContainWildCards
0x14008ef3b  nop     dword ptr [rax+rax+00h]
0x14008ef40  test    al, al
0x14008ef42  jnz     short loc_14008EF49
0x14008ef44  xor     r12b, r12b
0x14008ef47  jmp     short loc_14008EF4C
0x14008ef49  mov     r12b, 1
0x14008ef4c  xor     r14d, r14d
0x14008ef4f  mov     [rsp+138h+var_98], r14
0x14008ef57  xorps   xmm0, xmm0
0x14008ef5a  xor     eax, eax
0x14008ef5c  movups  [rsp+138h+var_80], xmm0
0x14008ef64  movups  [rsp+138h+var_70], xmm0
0x14008ef6c  mov     [rsp+138h+var_60], rax
0x14008ef74  movups  [rsp+138h+var_40], xmm0
0x14008ef7c  lea     rdx, [rsp+138h+var_80]
0x14008ef84  mov     rcx, rdi
0x14008ef87  call    CscGetContexts
0x14008ef8c  mov     byte ptr [rsp+138h+var_110], 1
0x14008ef91  lea     rax, [rsp+138h+var_40]
0x14008ef99  mov     [rsp+138h+var_118], rax
0x14008ef9e  mov     r9b, 1
0x14008efa1  mov     r8, rdi
0x14008efa4  mov     rdx, r13
0x14008efa7  mov     rcx, rsi
0x14008efaa  call    CscUpdateAndCaptureConnectionStateEx
0x14008efaf  test    byte ptr [rsp+138h+var_40+1], 40h
0x14008efb7  jz      short loc_14008EFD9
0x14008efb9  lea     rcx, [rsp+138h+var_40]
0x14008efc1  call    CscDetermineAbortStatus
0x14008efc6  mov     ebx, eax
0x14008efc8  mov     esi, 1173h
0x14008efcd  lea     r13, WPP_GLOBAL_Control
0x14008efd4  jmp     loc_14008F7FA
0x14008efd9  lea     r13, WPP_GLOBAL_Control
0x14008efe0  mov     r11, cs:WPP_GLOBAL_Control
0x14008efe7  cmp     r11, r13
0x14008efea  jz      loc_14008F0AD
0x14008eff0  mov     eax, [r11+2Ch]
0x14008eff4  test    al, 20h
0x14008eff6  jz      loc_14008F0AD
0x14008effc  mov     r9, [rsp+138h+Src]
0x14008f004  add     r9, 50h ; 'P'
0x14008f008  mov     r10d, 59h ; 'Y'
0x14008f00e  mov     eax, r10d
0x14008f011  mov     ecx, 4Eh ; 'N'
0x14008f016  mov     dword ptr [rsp+138h+var_58], ecx
0x14008f01d  cmp     [rdi+206h], r14b
0x14008f024  cmovz   eax, ecx
0x14008f027  mov     r8d, r10d
0x14008f02a  cmp     [rdi+207h], r14b
0x14008f031  cmovz   r8d, ecx
0x14008f035  mov     edx, r10d
0x14008f038  cmp     [rdi+204h], r14b
0x14008f03f  cmovz   edx, ecx
0x14008f042  mov     ecx, r10d
0x14008f045  cmp     [rdi+205h], r14b
0x14008f04c  cmovz   ecx, dword ptr [rsp+138h+var_58]
0x14008f054  test    bl, bl
0x14008f056  mov     ebx, 4Eh ; 'N'
0x14008f05b  cmovz   r10d, ebx
0x14008f05f  mov     [rsp+138h+var_D8], r9
0x14008f064  mov     [rsp+138h+var_E0], al
0x14008f068  mov     eax, [rdi+200h]
0x14008f06e  mov     [rsp+138h+var_E8], eax
0x14008f072  mov     [rsp+138h+var_F0], r8b
0x14008f077  mov     [rsp+138h+var_F8], dl
0x14008f07b  mov     byte ptr [rsp+138h+var_100], cl
0x14008f07f  mov     rax, qword ptr [rsp+138h+var_80]
0x14008f087  mov     [rsp+138h+var_108], rax
0x14008f08c  mov     rbx, [rsp+138h+var_50]
0x14008f094  mov     [rsp+138h+var_110], rbx
0x14008f099  mov     [rsp+138h+var_118], rsi
0x14008f09e  movzx   r9d, r10b
0x14008f0a2  mov     rcx, [r11+18h]
0x14008f0a6  call    WPP_SF_cqqqcccdcZ
0x14008f0ab  jmp     short loc_14008F0B5
0x14008f0ad  mov     rbx, [rsp+138h+var_50]
0x14008f0b5  mov     eax, 0EC21h
0x14008f0ba  cmp     [rsi], ax
0x14008f0bd  jz      short loc_14008F0CE
0x14008f0bf  mov     esi, 1184h
0x14008f0c4  mov     ebx, 0C000000Dh
0x14008f0c9  jmp     loc_14008F7FA
0x14008f0ce  cmp     [rdi+206h], r14b
0x14008f0d5  jz      short loc_14008F0E6
0x14008f0d7  mov     esi, 118Bh
0x14008f0dc  mov     ebx, 0C0000002h
0x14008f0e1  jmp     loc_14008F7FA
0x14008f0e6  movzx   r8d, byte ptr [rsp+138h+var_40]
0x14008f0ef  test    r8b, 20h
0x14008f0f3  jz      loc_14008F31C; jumptable 000000014008F2E6 cases 1-3,12,37,38
0x14008f0f9  mov     rax, qword ptr [rsp+138h+var_70]
0x14008f101  test    dword ptr [rax+18h], 801h
0x14008f108  jz      short loc_14008F147
0x14008f10a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f111  cmp     rcx, r13
0x14008f114  jz      short loc_14008F13B
0x14008f116  mov     eax, [rcx+2Ch]
0x14008f119  test    al, 40h
0x14008f11b  jz      short loc_14008F13B
0x14008f11d  mov     edx, 27h ; '''
0x14008f122  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x14008f129  mov     rcx, [rcx+18h]
0x14008f12d  call    WPP_SF_
0x14008f132  movzx   r8d, byte ptr [rsp+138h+var_40]
0x14008f13b  or      r8b, 10h
0x14008f13f  mov     byte ptr [rsp+138h+var_40], r8b
0x14008f147  cmp     [rdi+204h], r14b
0x14008f14e  jnz     loc_14008F1F0
0x14008f154  cmp     [rdi+207h], r14b
0x14008f15b  jnz     loc_14008F1F0
0x14008f161  mov     rcx, qword ptr [rsp+138h+var_80]
0x14008f169  test    byte ptr [rcx+1Ch], 4
0x14008f16d  jz      short loc_14008F17B
0x14008f16f  and     r8b, 0DFh
0x14008f173  mov     byte ptr [rsp+138h+var_40], r8b
0x14008f17b  test    byte ptr [rcx+1Ch], 2
0x14008f17f  jz      short loc_14008F18D
0x14008f181  or      r8b, 10h
0x14008f185  mov     byte ptr [rsp+138h+var_40], r8b
0x14008f18d  test    r8b, 10h
0x14008f191  jz      short loc_14008F197
0x14008f193  or      byte ptr [rcx+1Ch], 2
0x14008f197  mov     rdx, qword ptr [rsp+138h+var_80]
0x14008f19f  movzx   r8d, byte ptr [rdx+1Ch]
0x14008f1a4  test    r8b, 4
0x14008f1a8  jnz     short loc_14008F1CA
0x14008f1aa  mov     rax, qword ptr [rsp+138h+var_80+8]
0x14008f1b2  mov     ecx, [rax+24h]
0x14008f1b5  cmp     [rdx+18h], ecx
0x14008f1b8  jz      short loc_14008F1CA
0x14008f1ba  or      r8b, 2
0x14008f1be  mov     [rdx+1Ch], r8b
0x14008f1c2  or      byte ptr [rsp+138h+var_40], 10h
0x14008f1ca  mov     rax, qword ptr [rsp+138h+var_80]
0x14008f1d2  mov     ecx, [rax+8]
0x14008f1d5  cmp     [rdi+1C0h], ecx
0x14008f1db  jz      loc_14008F31C; jumptable 000000014008F2E6 cases 1-3,12,37,38
0x14008f1e1  mov     ebx, 0C000000Dh
0x14008f1e6  mov     esi, 1217h
0x14008f1eb  jmp     loc_14008F7FA
0x14008f1f0  mov     r9, qword ptr [rsp+138h+var_80+8]
0x14008f1f8  mov     eax, [r9+4]
0x14008f1fc  test    al, 60h
0x14008f1fe  jnz     short loc_14008F234
0x14008f200  lea     rax, [rsp+138h+var_40]
0x14008f208  mov     [rsp+138h+var_118], rax
0x14008f20d  lea     r9, [rsp+138h+var_80]
0x14008f215  mov     r8, rbx
0x14008f218  mov     rdx, rsi
0x14008f21b  mov     rcx, rdi
0x14008f21e  call    CscDirCtrlBackpatchIfPossible
0x14008f223  mov     r9, qword ptr [rsp+138h+var_80+8]
0x14008f22b  movzx   r8d, byte ptr [rsp+138h+var_40]
0x14008f234  mov     eax, dword ptr [rsp+138h+var_40+0Ch]
0x14008f23b  add     eax, 0FFFFFFFCh
0x14008f23e  test    eax, 0FFFFFFFBh
0x14008f243  setz    dl
0x14008f246  mov     rcx, [rsp+138h+Src]
0x14008f24e  add     rcx, 50h ; 'P'
0x14008f252  shr     r8b, 4
0x14008f256  and     r8b, 1
0x14008f25a  mov     eax, [r9+24h]
0x14008f25e  mov     dword ptr [rsp+138h+var_100], eax
0x14008f262  mov     [rsp+138h+var_108], rcx
0x14008f267  mov     byte ptr [rsp+138h+var_110], dl
0x14008f26b  movzx   eax, byte ptr [rdi+205h]
0x14008f272  mov     byte ptr [rsp+138h+var_118], al
0x14008f276  movzx   r9d, r12b
0x14008f27a  mov     edx, [rdi+1C0h]
0x14008f280  lea     rcx, [rsp+138h+var_80]
0x14008f288  call    CscQueryDirResetEnumContext
0x14008f28d  mov     ebx, eax
0x14008f28f  test    eax, eax
0x14008f291  jz      short loc_14008F2BE
0x14008f293  movzx   eax, byte ptr [rsp+138h+var_40]
0x14008f29b  test    al, 10h
0x14008f29d  jz      short loc_14008F2A9
0x14008f29f  mov     esi, 11C0h
0x14008f2a4  jmp     loc_14008F7FA
0x14008f2a9  and     al, 0DFh
0x14008f2ab  mov     byte ptr [rsp+138h+var_40], al
0x14008f2b2  mov     rax, qword ptr [rsp+138h+var_80]
0x14008f2ba  or      byte ptr [rax+1Ch], 4
0x14008f2be  mov     eax, [rdi+1C0h]
0x14008f2c4  dec     eax; switch 38 cases
0x14008f2c6  cmp     eax, 25h
0x14008f2c9  ja      short def_14008F2E6; jumptable 000000014008F2E6 default case, cases 4-11,13-36
0x14008f2cb  cdqe
0x14008f2cd  lea     rdx, cs:140000000h
0x14008f2d4  movzx   eax, ds:(byte_140033850 - 140000000h)[rdx+rax]
0x14008f2dc  mov     ecx, ds:(jpt_14008F2E6 - 140000000h)[rdx+rax*4]
0x14008f2e3  add     rcx, rdx
0x14008f2e6  jmp     rcx; switch jump
0x14008f2ec  movzx   eax, byte ptr [rsp+138h+var_40]; jumptable 000000014008F2E6 default case, cases 4-11,13-36
0x14008f2f4  test    al, 10h
0x14008f2f6  jz      short loc_14008F307
0x14008f2f8  mov     ebx, 0C00002CCh
0x14008f2fd  mov     esi, 11D8h
0x14008f302  jmp     loc_14008F7FA
0x14008f307  and     al, 0DFh
0x14008f309  mov     byte ptr [rsp+138h+var_40], al
0x14008f310  mov     rax, qword ptr [rsp+138h+var_80]
0x14008f318  or      byte ptr [rax+1Ch], 4
0x14008f31c  mov     rdx, rsi; jumptable 000000014008F2E6 cases 1-3,12,37,38
0x14008f31f  mov     rcx, rdi
0x14008f322  call    cs:__imp_RxDowngradeFcbToSharedInMRx
0x14008f329  nop     dword ptr [rax+rax+00h]
0x14008f32e  test    byte ptr [rsp+138h+var_40], 30h
0x14008f336  jnz     loc_14008F3F4
0x14008f33c  mov     rax, [rdi+50h]
0x14008f340  mov     rcx, [rax+160h]
0x14008f347  cmp     [rcx+0C0h], r14
0x14008f34e  jnz     short loc_14008F357
0x14008f350  mov     ebx, 0C0000002h
0x14008f355  jmp     short loc_14008F39E
0x14008f357  mov     eax, [rdi+80h]
0x14008f35d  test    al, 2
0x14008f35f  jnz     short loc_14008F399
0x14008f361  xorps   xmm0, xmm0
0x14008f364  xor     eax, eax
0x14008f366  movups  xmmword ptr [rdi+0D0h], xmm0
0x14008f36d  movups  xmmword ptr [rdi+0E0h], xmm0
0x14008f374  mov     [rdi+0F0h], rax
0x14008f37b  mov     rax, [rdi+50h]
0x14008f37f  mov     rdx, [rax+160h]
0x14008f386  mov     rax, [rdx+0C0h]
0x14008f38d  mov     rcx, rdi
0x14008f390  call    _guard_dispatch_icall
0x14008f395  mov     ebx, eax
0x14008f397  jmp     short loc_14008F39E
0x14008f399  mov     ebx, 0C0000120h
0x14008f39e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f3a5  mov     rdi, [rsp+138h+var_A0]
0x14008f3ad  cmp     rcx, r13
0x14008f3b0  jz      short loc_14008F3D8
0x14008f3b2  mov     eax, [rcx+2Ch]
0x14008f3b5  test    al, 40h
0x14008f3b7  jz      short loc_14008F3D8
0x14008f3b9  mov     r9d, r15d
0x14008f3bc  sub     r9d, [rdi]
0x14008f3bf  mov     edx, 28h ; '('
0x14008f3c4  mov     dword ptr [rsp+138h+var_118], ebx
0x14008f3c8  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x14008f3cf  mov     rcx, [rcx+18h]
0x14008f3d3  call    WPP_SF_Dd
0x14008f3d8  mov     r8, rsi
0x14008f3db  lea     rdx, [rsp+138h+var_40]
0x14008f3e3  mov     ecx, ebx
0x14008f3e5  call    CscCheckRdrStatusTransitionIfNetErr
0x14008f3ea  mov     esi, 1251h
0x14008f3ef  jmp     loc_14008F8B2
0x14008f3f4  xor     esi, esi
0x14008f3f6  mov     rax, qword ptr [rsp+138h+var_80]
0x14008f3fe  mov     r14, [rax+10h]
0x14008f402  mov     [rsp+138h+var_58], r14
0x14008f40a  mov     r8, r15; Size
0x14008f40d  xor     edx, edx; Val
0x14008f40f  mov     rcx, [rsp+138h+var_B8]
0x14008f417  mov     rcx, [rcx]; void *
0x14008f41a  call    memset
0x14008f41f  mov     rax, qword ptr [rsp+138h+var_80]
0x14008f427  test    byte ptr [rax+1Ch], 8
0x14008f42b  jnz     loc_14008F7F8
0x14008f431  lea     rdx, [rsp+138h+var_98]
  ... truncated ...
```
