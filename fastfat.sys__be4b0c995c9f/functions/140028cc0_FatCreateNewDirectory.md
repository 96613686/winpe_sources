# FatCreateNewDirectory

- ea: `0x140028cc0`
- end: `0x14002976e`
- name: `FatCreateNewDirectory`
- size: `2734`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops`

## callers

- `0x1400268c0`

## callees

- `0x140002ed8`
- `0x140002f68`
- `0x140005288`
- `0x14000c230`
- `0x14000c380`
- `0x14000c680`
- `0x140023ad4`
- `0x140024228`
- `0x14002486c`
- `0x140028cc0`
- `0x14002ca48`
- `0x1400302d8`
- `0x14003062c`
- `0x140031468`
- `0x140031a40`
- `0x140035234`
- `0x14003db44`
- `0x14004498c`
- `0x140044bac`
- `0x1400475e8`
- `0x14004763c`
- `0x14004814c`
- `0x140048184`

## import_xrefs

- `ntoskrnl!RtlClearBits` at `0x140029537`
- `ntoskrnl!RtlClearBits` at `0x140029537`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400296c4`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400296c4`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140029141`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400291a1`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140029141`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400291a1`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x1400292bd`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x1400292bd`
- `ntoskrnl!IoSetShareAccess` at `0x1400292e5`
- `ntoskrnl!IoSetShareAccess` at `0x1400292e5`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x140029170`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x140029170`
- `ntoskrnl!CcUnpinData` at `0x1400295d0`
- `ntoskrnl!CcUnpinData` at `0x1400295ec`
- `ntoskrnl!CcUnpinData` at `0x1400295d0`
- `ntoskrnl!CcUnpinData` at `0x1400295ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029604`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029604`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028fc1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028fc1`
- `ntoskrnl!CcSetFileSizes` at `0x140029664`
- `ntoskrnl!CcSetFileSizes` at `0x140029664`
- `ntoskrnl!ExRaiseStatus` at `0x1400291ba`
- `ntoskrnl!ExRaiseStatus` at `0x14002940b`
- `ntoskrnl!ExRaiseStatus` at `0x14002943e`
- `ntoskrnl!ExRaiseStatus` at `0x140029761`
- `ntoskrnl!ExRaiseStatus` at `0x1400291ba`
- `ntoskrnl!ExRaiseStatus` at `0x14002940b`
- `ntoskrnl!ExRaiseStatus` at `0x14002943e`
- `ntoskrnl!ExRaiseStatus` at `0x140029761`
- `ntoskrnl!ObfDereferenceObject` at `0x14002972a`
- `ntoskrnl!ObfDereferenceObject` at `0x14002972a`

## pseudocode

```c
_OWORD *__fastcall FatCreateNewDirectory(
        _OWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        struct _RTL_BITMAP *a6,
        __int64 a7,
        unsigned __int16 *a8,
        ACCESS_MASK *a9,
        unsigned __int16 a10,
        __int64 a11,
        int a12,
        __int16 a13,
        char a14,
        char a15,
        char a16)
{
  _OWORD *v18; // r15
  ULONG v20; // r12d
  unsigned int NewDirent; // eax
  __int64 v22; // rbx
  int v23; // r9d
  char *PoolWithTag; // rax
  char *v25; // r14
  __int64 v26; // rbx
  __int64 v27; // rbx
  size_t v28; // r8
  char *v29; // rdx
  void *v30; // r14
  __int64 Dcb; // r14
  NTSTATUS v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 Ccb; // rbx
  __int64 v36; // rdx
  __int64 v37; // rcx
  PVOID v38; // r8
  _BYTE *v39; // r9
  __int64 v40; // rdx
  int v41; // eax
  struct _RTL_BITMAP *v42; // r10
  int v43; // r8d
  int Callback; // eax
  _BYTE *v45; // rbx
  unsigned int v46; // r15d
  char v47; // r14
  _BYTE *v48; // r10
  PFILE_OBJECT *v49; // r12
  struct _FILE_OBJECT *v50; // rbx
  __int64 v51; // r9
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rcx
  int Action; // [rsp+38h] [rbp-150h]
  char v57; // [rsp+60h] [rbp-128h] BYREF
  char v58; // [rsp+61h] [rbp-127h] BYREF
  char v59; // [rsp+62h] [rbp-126h]
  char v60; // [rsp+63h] [rbp-125h] BYREF
  char v61[4]; // [rsp+64h] [rbp-124h] BYREF
  __int16 v62; // [rsp+68h] [rbp-120h] BYREF
  unsigned int v63; // [rsp+6Ch] [rbp-11Ch]
  unsigned int v64; // [rsp+70h] [rbp-118h]
  struct _RTL_BITMAP *v65; // [rsp+78h] [rbp-110h]
  __int64 v66; // [rsp+80h] [rbp-108h]
  __int64 v67; // [rsp+88h] [rbp-100h]
  __int64 v68; // [rsp+90h] [rbp-F8h] BYREF
  unsigned int Size; // [rsp+98h] [rbp-F0h]
  ULONG Size_4; // [rsp+9Ch] [rbp-ECh]
  unsigned int v71; // [rsp+A0h] [rbp-E8h]
  char *v72; // [rsp+A8h] [rbp-E0h] BYREF
  PVOID P; // [rsp+B0h] [rbp-D8h]
  PVOID Bcb; // [rsp+B8h] [rbp-D0h] BYREF
  __int64 v75; // [rsp+C0h] [rbp-C8h] BYREF
  unsigned __int64 v76; // [rsp+C8h] [rbp-C0h]
  __int64 v77; // [rsp+D0h] [rbp-B8h]
  void *v78; // [rsp+D8h] [rbp-B0h] BYREF
  void *v79; // [rsp+E0h] [rbp-A8h]
  PVOID v80[2]; // [rsp+E8h] [rbp-A0h] BYREF
  __int64 v81; // [rsp+F8h] [rbp-90h]
  _QWORD v82[2]; // [rsp+100h] [rbp-88h] BYREF
  __int64 v83; // [rsp+110h] [rbp-78h]
  __int64 v84; // [rsp+118h] [rbp-70h]
  __int64 v85; // [rsp+120h] [rbp-68h]
  ACCESS_MASK *v86; // [rsp+128h] [rbp-60h]
  __int64 v87; // [rsp+130h] [rbp-58h] BYREF

  v81 = a3;
  v18 = a1;
  v76 = (unsigned __int64)a8;
  v67 = a2;
  v80[1] = (PVOID)a4;
  v66 = a5;
  v65 = a6;
  v86 = a9;
  v85 = a11;
  *a1 = 0;
  v68 = 0;
  v75 = 0;
  v72 = 0;
  Bcb = 0;
  v61[0] = 0;
  v60 = 0;
  v57 = 0;
  v80[0] = 0;
  v78 = 0;
  v58 = 0;
  v82[0] = 786432;
  v82[1] = &v87;
  v62 = 0;
  if ( a14 && a12 )
  {
    *(_DWORD *)a1 = -1073741790;
    return v18;
  }
  if ( a15 && (a13 & 1) != 0 )
  {
    *(_DWORD *)a1 = -1073741535;
    return v18;
  }
  Size = 0;
  v63 = 0;
  v71 = 0;
  v79 = 0;
  v59 = 0;
  FatSelectNames(a2, a6, a7, a8, v82, 0, v61, &v60, &v57);
  if ( (byte_140017D4C & 1) == 0 )
  {
    v61[0] = 0;
    v60 = 0;
    v57 = 0;
  }
  if ( v57 )
    v20 = (((unsigned __int64)*a8 >> 1) + 12) / 0xD + 1;
  else
    v20 = 1;
  Size_4 = v20;
  NewDirent = FatCreateNewDirent(a2, (int)a6, v20);
  v22 = NewDirent;
  v64 = NewDirent;
  FatPrepareWriteDirectoryFile(a2, a6, NewDirent, 32, &Bcb, &v72);
  v84 = v22 + 32LL * (v20 - 1);
  if ( ((v22 ^ v84) & 0xFFFFFFFFFFFFF000uLL) != 0 )
  {
    Size = (v22 & 0xFFFFF000) + 4096 - v22;
    v63 = Size >> 5;
    v71 = Size >> 5;
    FatPrepareWriteDirectoryFile(a2, a6, ((unsigned int)v22 & 0xFFFFF000) + 4096, 32, v80, &v78);
    v79 = v72;
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, 32LL * v20, 0x44746146u);
    v25 = PoolWithTag;
    P = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, 32LL * v20);
    v72 = v25;
    v59 = 1;
  }
  else
  {
    v25 = v72;
    P = v72;
  }
  v83 = 32LL * v20;
  v26 = (__int64)&v25[v83 - 32];
  v77 = v26;
  LOBYTE(v23) = v61[0];
  FatConstructDirent(
    v57 != 0 ? v76 : 0,
    v83 + (_DWORD)v25 - 32,
    (unsigned int)v82,
    v23,
    v60,
    v76 & -(__int64)(v57 != 0),
    a13 | 0x10,
    1,
    0);
  if ( v59 )
  {
    v27 = Size;
    memmove(v79, v25, Size);
    v28 = v83 - v27;
    LODWORD(v27) = v63;
    v29 = &v25[32 * v63];
    v30 = v78;
    memmove(v78, v29, v28);
    v26 = (__int64)v30 + 32 * (v20 - (unsigned int)v27) - 32;
    v77 = v26;
  }
  Dcb = FatCreateDcb(v57 != 0 ? v76 : 0, v66, (_DWORD)v65, v64, v84, v26, v76 & -(__int64)(v57 != 0));
  v68 = Dcb;
  v32 = FsRtlCheckOplockEx((POPLOCK)(Dcb + 88), *(PIRP *)(a2 + 40), 2u, 0, 0, 0);
  *(_DWORD *)v18 = v32;
  if ( a16 )
  {
    if ( v32 )
      goto LABEL_26;
    v32 = FsRtlOplockFsctrl((POPLOCK)(Dcb + 88), *(PIRP *)(a2 + 40), *(_DWORD *)(Dcb + 228) + 1);
    *(_DWORD *)v18 = v32;
  }
  if ( v32
    || (v32 = FsRtlCheckOplockEx((POPLOCK)&v65[5].Buffer, *(PIRP *)(a2 + 40), 0x10u, 0, 0, 0),
        (*(_DWORD *)v18 = v32) != 0) )
  {
LABEL_26:
    *(_DWORD *)(a2 + 72) = v32;
    ExRaiseStatus(*(_DWORD *)v18);
  }
  if ( a12 )
    FatCreateEa(a2, *(_QWORD *)(Dcb + 184), Dcb + 480, (__int64)&v62);
  if ( *(_BYTE *)(*(_QWORD *)(Dcb + 184) + 376LL) != 32 )
    *(_WORD *)(v26 + 20) = v62;
  FatInitializeDirectoryDirent(a2, Dcb, v26);
  Ccb = FatCreateCcb(v34, v33);
  v75 = Ccb;
  FatSetFileObject(a4, v36, Dcb, Ccb);
  if ( !*(_QWORD *)(Dcb + 536) )
  {
    FatSetFullNameInFcb(a2, Dcb, v76);
    if ( !*(_QWORD *)(Dcb + 536) )
      FatSetFullFileNameInFcb(a2);
  }
  FsRtlNotifyFullReportChange(
    *(PNOTIFY_SYNC *)(v66 + 816),
    (PLIST_ENTRY)(v66 + 800),
    (PSTRING)(Dcb + 528),
    *(_WORD *)(Dcb + 528) - *(_WORD *)(Dcb + 544),
    0,
    0,
    2u,
    1u,
    0);
  IoSetShareAccess(*v86, a10, (PFILE_OBJECT)a4, (PSHARE_ACCESS)(Dcb + 200));
  v40 = v66;
  if ( (*(_DWORD *)(v66 + 200) & 0x400000) != 0 )
  {
    LOBYTE(v38) = 1;
    v41 = EfsFileRequiresEncryptionCallback(v81, *(_QWORD *)(a2 + 40), v38, &v58);
    *(_DWORD *)v18 = v41;
    if ( v41 == -1073741808 )
    {
      *(_DWORD *)v18 = 0;
      v58 = 0;
    }
    else if ( v41 )
    {
      *(_DWORD *)(a2 + 72) = v41;
      ExRaiseStatus(*(_DWORD *)v18);
    }
    v42 = v65;
    if ( (v65[12].SizeOfBitMap & 0x60000) != 0 || (a13 & 0x4000) != 0 || v58 )
    {
      v58 = 1;
      v43 = v81;
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v81 + 8) + 8LL) + 20LL) |= *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v81 + 8) + 8LL)
                                                                               + 16LL);
      *(_DWORD *)(Dcb + 192) |= 0x100000u;
      *(_DWORD *)(a2 + 136) = 65540;
      *(_BYTE *)(v77 + 12) |= 1u;
      Callback = EfsFileCreateCallback(
                   Dcb,
                   (_DWORD)v42,
                   v43,
                   *(_DWORD *)(a2 + 136),
                   (*(_DWORD *)(v66 + 200) >> 14) & 1,
                   a2,
                   v66 - 416,
                   Action,
                   Dcb + 144,
                   a2 + 128);
      if ( *(_QWORD *)(a2 + 128) )
      {
        *(_DWORD *)(a2 + 68) |= 0x8000u;
      }
      else
      {
        *(_DWORD *)(Dcb + 192) &= ~0x100000u;
        v37 = v77;
        *(_BYTE *)(v77 + 12) &= ~1u;
        *(_DWORD *)(a2 + 68) &= ~0x8000u;
      }
      if ( Callback < 0 )
      {
        *(_DWORD *)v18 = Callback;
        *(_DWORD *)(a2 + 72) = Callback;
        ExRaiseStatus(*(_DWORD *)v18);
      }
      Ccb = v75;
      v42 = v65;
    }
    v40 = v66;
  }
  else
  {
    v42 = v65;
  }
  ++*(_DWORD *)(Dcb + 228);
  ++*(_DWORD *)(Dcb + 232);
  ++*(_DWORD *)(v40 + 272);
  if ( !*(_WORD *)(a4 + 75) )
    ++*(_DWORD *)(v40 + 276);
  if ( a15 )
    *(_DWORD *)(Ccb + 4) |= 0x400u;
  *(_DWORD *)v18 = 0;
  *((_QWORD *)v18 + 1) = 2;
  v45 = P;
  if ( *(int *)v18 < 0 )
  {
    if ( v75 )
    {
      FatDeleteCcb(v37, &v75, v38, v39);
      v42 = v65;
    }
    if ( !Dcb )
    {
      RtlClearBits(v42 + 25, v64 >> 5, v20);
      if ( v45 )
      {
        v40 = 0;
        if ( v20 )
        {
          v46 = v63;
          v47 = v59;
          v38 = v80[0];
          v39 = v78;
          v48 = v79;
          while ( 1 )
          {
            if ( v47 )
            {
              if ( !v38 && (_DWORD)v40 == v46 )
              {
LABEL_69:
                Dcb = v68;
                v18 = a1;
                break;
              }
              if ( (unsigned int)v40 >= v46 )
                v39[32 * ((unsigned int)v40 - v46)] = -27;
              else
                v48[32 * (unsigned int)v40] = -27;
            }
            else
            {
              v45[32 * (unsigned int)v40] = -27;
            }
            v40 = (unsigned int)(v40 + 1);
            if ( (unsigned int)v40 >= v20 )
              goto LABEL_69;
          }
        }
      }
    }
  }
  if ( Bcb )
    CcUnpinData(Bcb);
  if ( v80[0] )
    CcUnpinData(v80[0]);
  if ( v59 )
    ExFreePoolWithTag(v45, 0);
  if ( *(int *)v18 < 0 )
  {
    if ( Dcb )
    {
      v49 = (PFILE_OBJECT *)(Dcb + 344);
      P = (PVOID)(Dcb + 344);
      v50 = *(struct _FILE_OBJECT **)(Dcb + 344);
      Bcb = v50;
      *(_DWORD *)(a2 + 68) |= 0x800u;
      FatUnpinRepinnedBcbs(a2, v40, v38, v39);
      *(_DWORD *)(a2 + 68) &= ~0x800u;
      if ( *(_DWORD *)(Dcb + 128) )
      {
        *(_DWORD *)(Dcb + 32) = 0;
        CcSetFileSizes(*v49, (PCC_FILE_SIZES)(Dcb + 24));
        FatTruncateFileAllocation(a2, Dcb, 0);
      }
      if ( v50 )
        CcUninitializeCacheMap(v50, &FatLargeZero, 0);
      LOBYTE(v51) = 1;
      FatDeleteDirent(a2, Dcb, 0, v51);
      FatUnpinRepinnedBcbs(a2, v52, v53, v54);
      if ( v50 )
      {
        *v49 = 0;
        ObfDereferenceObject(v50);
      }
      else
      {
        if ( a4 )
        {
          *(_QWORD *)(a4 + 40) = 0;
          if ( *(_QWORD *)(a4 + 24) == Dcb )
            *(_QWORD *)(a4 + 24) = 0;
        }
        FatDeleteFcb(v55, &v68);
      }
    }
    *(_DWORD *)(a2 + 72) = *(_DWORD *)v18;
    ExRaiseStatus(*(_DWORD *)v18);
  }
  return v18;
}

```

## disassembly

```asm
0x140028cc0  mov     r11, rsp
0x140028cc3  mov     [r11+8], rcx
0x140028cc7  push    rbx
0x140028cc8  push    rsi
0x140028cc9  push    rdi
0x140028cca  push    r12
0x140028ccc  push    r13
0x140028cce  push    r14
0x140028cd0  push    r15
0x140028cd2  sub     rsp, 150h
0x140028cd9  mov     rax, cs:__security_cookie
0x140028ce0  xor     rax, rsp
0x140028ce3  mov     [rsp+188h+var_48], rax
0x140028ceb  mov     r13, r9
0x140028cee  mov     [rsp+188h+var_90], r8
0x140028cf6  mov     rsi, rdx
0x140028cf9  mov     r15, rcx
0x140028cfc  mov     rbx, [rsp+188h+arg_38]
0x140028d04  mov     [rsp+188h+var_C0], rbx
0x140028d0c  mov     [rsp+188h+var_100], rdx
0x140028d14  mov     [rsp+188h+var_98], r9
0x140028d1c  mov     rax, [rsp+188h+arg_20]
0x140028d24  mov     [rsp+188h+var_108], rax
0x140028d2c  mov     r14, [rsp+188h+arg_28]
0x140028d34  mov     [rsp+188h+var_110], r14
0x140028d39  mov     r8, [rsp+188h+arg_30]
0x140028d41  mov     rax, [rsp+188h+arg_40]
0x140028d49  mov     [rsp+188h+var_60], rax
0x140028d51  mov     rax, [rsp+188h+arg_50]
0x140028d59  mov     [rsp+188h+var_68], rax
0x140028d61  xorps   xmm0, xmm0
0x140028d64  movups  xmmword ptr [rcx], xmm0
0x140028d67  xor     edi, edi
0x140028d69  mov     [r11-0F8h], rdi
0x140028d70  mov     [r11-0C8h], rdi
0x140028d77  mov     [r11-0E0h], rdi
0x140028d7e  mov     [r11-0D0h], rdi
0x140028d85  mov     [rsp+188h+var_124], dil
0x140028d8a  mov     [rsp+188h+var_125], dil
0x140028d8f  mov     [rsp+188h+var_128], dil
0x140028d94  mov     [r11-0A0h], rdi
0x140028d9b  mov     [r11-0B0h], rdi
0x140028da2  mov     [rsp+188h+var_127], dil
0x140028da7  mov     qword ptr [r11-88h], 0C0000h
0x140028db2  lea     r12d, [rdi+0Ch]
0x140028db6  lea     rax, [r11-58h]
0x140028dba  mov     [r11-80h], rax
0x140028dbe  mov     word ptr [rsp+188h+var_120], di
0x140028dc3  cmp     [rsp+188h+arg_68], dil
0x140028dcb  jz      short loc_140028E03
0x140028dcd  cmp     [rsp+188h+arg_58], edi
0x140028dd4  jbe     short loc_140028E03
0x140028dd6  mov     dword ptr [rcx], 0C0000022h
0x140028ddc  mov     rax, r15
0x140028ddf  mov     rcx, [rsp+188h+var_48]
0x140028de7  xor     rcx, rsp; StackCookie
0x140028dea  call    __security_check_cookie
0x140028def  add     rsp, 150h
0x140028df6  pop     r15
0x140028df8  pop     r14
0x140028dfa  pop     r13
0x140028dfc  pop     r12
0x140028dfe  pop     rdi
0x140028dff  pop     rsi
0x140028e00  pop     rbx
0x140028e01  retn
0x140028e03  cmp     [rsp+188h+arg_70], dil
0x140028e0b  jz      short loc_140028E1F
0x140028e0d  test    byte ptr [rsp+188h+arg_60], 1
0x140028e15  jz      short loc_140028E1F
0x140028e17  mov     dword ptr [rcx], 0C0000121h
0x140028e1d  jmp     short loc_140028DDC
0x140028e1f  mov     dword ptr [rsp+188h+Size], edi
0x140028e26  mov     eax, edi
0x140028e28  mov     dword ptr [rsp+188h+var_120+4], eax
0x140028e2c  mov     [rsp+188h+var_E8], eax
0x140028e33  mov     [rsp+188h+var_A8], rdi
0x140028e3b  mov     [rsp+188h+var_126], dil
0x140028e40  lea     rax, [rsp+188h+var_128]
0x140028e45  mov     [rsp+188h+TargetContext], rax
0x140028e4a  lea     rax, [rsp+188h+var_125]
0x140028e4f  mov     qword ptr [rsp+188h+Action], rax
0x140028e54  lea     rax, [rsp+188h+var_124]
0x140028e59  mov     qword ptr [rsp+188h+FilterMatch], rax
0x140028e5e  mov     [rsp+188h+PostIrpRoutine], rdi
0x140028e63  lea     rax, [rsp+188h+var_88]
0x140028e6b  mov     [rsp+188h+CompletionRoutine], rax
0x140028e70  mov     r9, rbx
0x140028e73  mov     rdx, r14
0x140028e76  mov     rcx, rsi
0x140028e79  call    FatSelectNames
0x140028e7e  test    cs:byte_140017D4C, 1
0x140028e85  jnz     short loc_140028E96
0x140028e87  mov     [rsp+188h+var_124], dil
0x140028e8c  mov     [rsp+188h+var_125], dil
0x140028e91  mov     [rsp+188h+var_128], dil
0x140028e96  cmp     [rsp+188h+var_128], dil
0x140028e9b  jz      short loc_140028EBF
0x140028e9d  movzx   ecx, word ptr [rbx]
0x140028ea0  shr     rcx, 1
0x140028ea3  add     rcx, r12
0x140028ea6  mov     rax, 4EC4EC4EC4EC4EC5h
0x140028eb0  mul     rcx
0x140028eb3  mov     r12, rdx
0x140028eb6  shr     r12, 2
0x140028eba  inc     r12d
0x140028ebd  jmp     short loc_140028EC5
0x140028ebf  mov     r12d, 1
0x140028ec5  mov     dword ptr [rsp+188h+Size+4], r12d
0x140028ecd  mov     r8d, r12d; NumberToSet
0x140028ed0  mov     rdx, r14; int
0x140028ed3  mov     rcx, rsi; int
0x140028ed6  call    FatCreateNewDirent
0x140028edb  mov     ebx, eax
0x140028edd  mov     [rsp+188h+var_118], ebx
0x140028ee1  mov     [rsp+188h+TargetContext], r15
0x140028ee6  mov     byte ptr [rsp+188h+Action], 1
0x140028eeb  lea     rax, [rsp+188h+var_E0]
0x140028ef3  mov     [rsp+188h+PostIrpRoutine], rax
0x140028ef8  lea     rax, [rsp+188h+Bcb]
0x140028f00  mov     [rsp+188h+CompletionRoutine], rax
0x140028f05  mov     r9d, 20h ; ' '
0x140028f0b  mov     r8d, ebx
0x140028f0e  mov     rdx, r14
0x140028f11  mov     rcx, rsi
0x140028f14  call    FatPrepareWriteDirectoryFile
0x140028f19  lea     eax, [r12-1]
0x140028f1e  shl     rax, 5
0x140028f22  add     rax, rbx
0x140028f25  mov     [rsp+188h+var_70], rax
0x140028f2d  xor     rax, rbx
0x140028f30  test    rax, 0FFFFFFFFFFFFF000h
0x140028f36  jz      loc_140029002
0x140028f3c  mov     r8d, ebx
0x140028f3f  and     r8d, 0FFFFF000h
0x140028f46  add     r8d, 1000h
0x140028f4d  mov     eax, r8d
0x140028f50  sub     eax, ebx
0x140028f52  mov     dword ptr [rsp+188h+Size], eax
0x140028f59  shr     eax, 5
0x140028f5c  mov     dword ptr [rsp+188h+var_120+4], eax
0x140028f60  mov     [rsp+188h+var_E8], eax
0x140028f67  mov     [rsp+188h+TargetContext], r15
0x140028f6c  mov     byte ptr [rsp+188h+Action], 1
0x140028f71  lea     rax, [rsp+188h+var_B0]
0x140028f79  mov     [rsp+188h+PostIrpRoutine], rax
0x140028f7e  lea     rax, [rsp+188h+var_A0]
0x140028f86  mov     [rsp+188h+CompletionRoutine], rax
0x140028f8b  mov     r9d, 20h ; ' '
0x140028f91  mov     rdx, r14
0x140028f94  mov     rcx, rsi
0x140028f97  call    FatPrepareWriteDirectoryFile
0x140028f9c  mov     rax, [rsp+188h+var_E0]
0x140028fa4  mov     [rsp+188h+var_A8], rax
0x140028fac  mov     ebx, r12d
0x140028faf  shl     rbx, 5
0x140028fb3  mov     r8d, 44746146h; Tag
0x140028fb9  mov     rdx, rbx; NumberOfBytes
0x140028fbc  mov     ecx, 411h; PoolType
0x140028fc1  call    cs:__imp_ExAllocatePoolWithTag
0x140028fc8  nop     dword ptr [rax+rax+00h]
0x140028fcd  mov     r14, rax
0x140028fd0  mov     [rsp+188h+P], rax
0x140028fd8  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140028fdf  jnz     short loc_140028FF3
0x140028fe1  test    rax, rax
0x140028fe4  jz      short loc_140028FF3
0x140028fe6  mov     r8, rbx; Size
0x140028fe9  xor     edx, edx; Val
0x140028feb  mov     rcx, rax; void *
0x140028fee  call    memset
0x140028ff3  mov     [rsp+188h+var_E0], r14
0x140028ffb  mov     [rsp+188h+var_126], 1
0x140029000  jmp     short loc_140029012
0x140029002  mov     r14, [rsp+188h+var_E0]
0x14002900a  mov     [rsp+188h+P], r14
0x140029012  mov     eax, r12d
0x140029015  shl     rax, 5
0x140029019  mov     [rsp+188h+var_78], rax
0x140029021  lea     rbx, [r14-20h]
0x140029025  add     rbx, rax
0x140029028  mov     [rsp+188h+var_B8], rbx
0x140029030  mov     al, [rsp+188h+var_128]
0x140029034  neg     al
0x140029036  sbb     rcx, rcx
0x140029039  and     rcx, [rsp+188h+var_C0]
0x140029041  movzx   eax, [rsp+188h+arg_60]
0x140029049  or      ax, 10h
0x14002904d  mov     [rsp+188h+TargetContext], rdi
0x140029052  mov     byte ptr [rsp+188h+Action], 1
0x140029057  mov     word ptr [rsp+188h+FilterMatch], ax
0x14002905c  mov     [rsp+188h+PostIrpRoutine], rcx
0x140029061  mov     al, [rsp+188h+var_125]
0x140029065  mov     byte ptr [rsp+188h+CompletionRoutine], al
0x140029069  mov     r9b, [rsp+188h+var_124]
0x14002906e  lea     r8, [rsp+188h+var_88]
0x140029076  mov     rdx, rbx
0x140029079  call    FatConstructDirent
0x14002907e  cmp     [rsp+188h+var_126], dil
0x140029083  jz      short loc_1400290DF
0x140029085  mov     ebx, dword ptr [rsp+188h+Size]
0x14002908c  mov     r8d, ebx; Size
0x14002908f  mov     rdx, r14; Src
0x140029092  mov     rcx, [rsp+188h+var_A8]; void *
0x14002909a  call    memmove
0x14002909f  mov     r8, [rsp+188h+var_78]
0x1400290a7  sub     r8, rbx; Size
0x1400290aa  mov     ebx, dword ptr [rsp+188h+var_120+4]
0x1400290ae  mov     edx, ebx
0x1400290b0  shl     rdx, 5
0x1400290b4  add     rdx, r14; Src
0x1400290b7  mov     r14, [rsp+188h+var_B0]
0x1400290bf  mov     rcx, r14; void *
0x1400290c2  call    memmove
0x1400290c7  mov     ecx, r12d
0x1400290ca  sub     ecx, ebx
0x1400290cc  shl     rcx, 5
0x1400290d0  lea     rbx, [r14-20h]
0x1400290d4  add     rbx, rcx
0x1400290d7  mov     [rsp+188h+var_B8], rbx
0x1400290df  mov     al, [rsp+188h+var_128]
0x1400290e3  neg     al
0x1400290e5  sbb     rcx, rcx
0x1400290e8  and     rcx, [rsp+188h+var_C0]
0x1400290f0  mov     qword ptr [rsp+188h+FilterMatch], rcx
0x1400290f5  mov     [rsp+188h+PostIrpRoutine], rbx
0x1400290fa  mov     rax, [rsp+188h+var_70]
0x140029102  mov     dword ptr [rsp+188h+CompletionRoutine], eax
0x140029106  mov     r9d, [rsp+188h+var_118]
0x14002910b  mov     r8, [rsp+188h+var_110]
0x140029110  mov     rdx, [rsp+188h+var_108]
0x140029118  call    FatCreateDcb
0x14002911d  mov     r14, rax
0x140029120  mov     [rsp+188h+var_F8], rax
0x140029128  lea     rcx, [rax+58h]; Oplock
0x14002912c  mov     [rsp+188h+PostIrpRoutine], rdi; PostIrpRoutine
0x140029131  mov     [rsp+188h+CompletionRoutine], rdi; CompletionRoutine
0x140029136  xor     r9d, r9d; Context
0x140029139  lea     r8d, [r9+2]; Flags
0x14002913d  mov     rdx, [rsi+28h]; Irp
0x140029141  call    cs:__imp_FsRtlCheckOplockEx
0x140029148  nop     dword ptr [rax+rax+00h]
0x14002914d  mov     [r15], eax
0x140029150  cmp     [rsp+188h+arg_78], dil
0x140029158  jz      short loc_14002917F
0x14002915a  test    eax, eax
0x14002915c  jnz     short loc_1400291B4
0x14002915e  mov     r8d, [r14+0E4h]
0x140029165  inc     r8d; OpenCount
0x140029168  mov     rdx, [rsi+28h]; Irp
0x14002916c  lea     rcx, [r14+58h]; Oplock
0x140029170  call    cs:__imp_FsRtlOplockFsctrl
0x140029177  nop     dword ptr [rax+rax+00h]
0x14002917c  mov     [r15], eax
0x14002917f  test    eax, eax
0x140029181  jnz     short loc_1400291B4
0x140029183  mov     rcx, [rsp+188h+var_110]
0x140029188  add     rcx, 58h ; 'X'; Oplock
0x14002918c  mov     [rsp+188h+PostIrpRoutine], rdi; PostIrpRoutine
0x140029191  mov     [rsp+188h+CompletionRoutine], rdi; CompletionRoutine
0x140029196  xor     r9d, r9d; Context
0x140029199  lea     r8d, [rax+10h]; Flags
0x14002919d  mov     rdx, [rsi+28h]; Irp
0x1400291a1  call    cs:__imp_FsRtlCheckOplockEx
0x1400291a8  nop     dword ptr [rax+rax+00h]
0x1400291ad  mov     [r15], eax
0x1400291b0  test    eax, eax
0x1400291b2  jz      short loc_1400291C6
0x1400291b4  mov     [rsi+48h], eax
0x1400291b7  mov     ecx, [r15]; Status
0x1400291ba  call    cs:__imp_ExRaiseStatus
0x1400291c6  mov     r9d, [rsp+188h+arg_58]
0x1400291ce  test    r9d, r9d
0x1400291d1  jz      short loc_140029200
0x1400291d3  lea     rax, [r14+1E0h]
0x1400291da  lea     rcx, [rsp+188h+var_120]
0x1400291df  mov     [rsp+188h+PostIrpRoutine], rcx; __int64
0x1400291e4  mov     [rsp+188h+CompletionRoutine], rax; __int64
0x1400291e9  mov     r8, [rsp+188h+var_68]
0x1400291f1  mov     rdx, [r14+0B8h]; int
0x1400291f8  mov     rcx, rsi; int
0x1400291fb  call    FatCreateEa
0x140029200  mov     rax, [r14+0B8h]
0x140029207  cmp     byte ptr [rax+178h], 20h ; ' '
0x14002920e  jz      short loc_140029219
0x140029210  movzx   eax, word ptr [rsp+188h+var_120]
0x140029215  mov     [rbx+14h], ax
0x140029219  mov     r8, rbx
0x14002921c  mov     rdx, r14
0x14002921f  mov     rcx, rsi
0x140029222  call    FatInitializeDirectoryDirent
0x140029227  call    FatCreateCcb
0x14002922c  mov     rbx, rax
0x14002922f  mov     [rsp+188h+var_C8], rax
0x140029237  mov     r9, rax
0x14002923a  mov     r8, r14
0x14002923d  mov     rcx, r13
0x140029240  call    FatSetFileObject
0x140029245  cmp     [r14+218h], rdi
0x14002924c  jnz     short loc_140029275
  ... truncated ...
```
