# CiSetFileCache

- ea: `0x180096f80`
- end: `0x1800978c0`
- name: `CiSetFileCache`
- size: `2368`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, HANDLE, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18002bf20`
- `0x18002c000`
- `0x180059944`
- `0x18005a470`
- `0x180060b54`
- `0x180072d54`
- `0x18009679c`
- `0x180096bb8`
- `0x180096f80`
- `0x1800985d4`
- `0x18009860c`
- `0x180099118`
- `0x180099aa4`
- `0x18009e068`
- `0x18009e498`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180097063`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800970ca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180097063`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800970ca`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180097078`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180097078`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180097096`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180097096`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180097183`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180097183`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800977a0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800977a0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800970df`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1800970df`
- `ntoskrnl!ZwClose` at `0x1800971d9`
- `ntoskrnl!ZwClose` at `0x1800971ee`
- `ntoskrnl!ZwClose` at `0x1800973a9`
- `ntoskrnl!ZwClose` at `0x1800971d9`
- `ntoskrnl!ZwClose` at `0x1800971ee`
- `ntoskrnl!ZwClose` at `0x1800973a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800970a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009718f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800970a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009718f`
- `ntoskrnl!ObfDereferenceObject` at `0x1800971b0`
- `ntoskrnl!ObfDereferenceObject` at `0x1800971c4`
- `ntoskrnl!ObfDereferenceObject` at `0x1800976f9`
- `ntoskrnl!ObfDereferenceObject` at `0x1800971b0`
- `ntoskrnl!ObfDereferenceObject` at `0x1800971c4`
- `ntoskrnl!ObfDereferenceObject` at `0x1800976f9`
- `ntoskrnl!IoFileObjectType` at `0x1800972ea`
- `ntoskrnl!IoFileObjectType` at `0x1800973ed`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18009730f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18009741b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18009730f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18009741b`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x1800972d0`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x1800973d3`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x1800972d0`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x1800973d3`

## pseudocode

```c
__int64 __fastcall CiSetFileCache(
        int a1,
        char a2,
        unsigned __int8 a3,
        bool a4,
        HANDLE *a5,
        unsigned int a6,
        HANDLE a7,
        __int64 a8)
{
  HANDLE v8; // r13
  unsigned __int8 v9; // bl
  char v10; // di
  char *v11; // r14
  unsigned int v12; // r12d
  int FileCache2; // ebx
  struct _FILE_OBJECT *v14; // r15
  int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // r8
  int *v18; // rsi
  int v19; // ecx
  int v20; // ecx
  char v22; // r12
  __int64 v23; // rcx
  char v24; // al
  NTSTATUS v25; // eax
  char v26; // r13
  unsigned int i; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  bool v30; // zf
  HANDLE v31; // rbx
  bool *v32; // rcx
  int v33; // eax
  int v34; // ecx
  int v35; // r9d
  int v36; // eax
  __int128 *v37; // rax
  __int128 v38; // xmm0
  __int64 v39; // rcx
  __int16 v40; // r8
  unsigned __int8 j; // dl
  int v42; // eax
  int v43; // ecx
  __int64 CurrentProcess; // rax
  char ActionsForImage; // al
  int v46; // eax
  unsigned int v47; // [rsp+48h] [rbp-B8h]
  char v48; // [rsp+80h] [rbp-80h] BYREF
  bool v49; // [rsp+81h] [rbp-7Fh]
  char v50; // [rsp+82h] [rbp-7Eh]
  char v51; // [rsp+83h] [rbp-7Dh]
  bool v52; // [rsp+84h] [rbp-7Ch] BYREF
  _WORD v53[2]; // [rsp+88h] [rbp-78h] BYREF
  char v54; // [rsp+8Ch] [rbp-74h] BYREF
  char v55[3]; // [rsp+8Dh] [rbp-73h] BYREF
  __int16 v56[2]; // [rsp+90h] [rbp-70h]
  unsigned int v57; // [rsp+94h] [rbp-6Ch]
  int v58; // [rsp+98h] [rbp-68h]
  struct _FILE_OBJECT *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h] BYREF
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp-48h] BYREF
  PVOID Entry; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v65; // [rsp+C8h] [rbp-38h]
  PVOID Object; // [rsp+D0h] [rbp-30h]
  int v67; // [rsp+D8h] [rbp-28h]
  HANDLE v68; // [rsp+E0h] [rbp-20h] BYREF
  PVOID v69; // [rsp+E8h] [rbp-18h] BYREF
  HANDLE *v70; // [rsp+F0h] [rbp-10h]
  PVOID v71; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v72[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v73; // [rsp+110h] [rbp+10h]
  __int128 v74; // [rsp+120h] [rbp+20h]
  __int64 v75; // [rsp+130h] [rbp+30h]
  __int128 v76; // [rsp+138h] [rbp+38h] BYREF
  __int64 v77[2]; // [rsp+148h] [rbp+48h] BYREF
  __int128 v78; // [rsp+158h] [rbp+58h]
  __int128 v79; // [rsp+168h] [rbp+68h]
  __int64 v80; // [rsp+178h] [rbp+78h]
  __int64 v81; // [rsp+180h] [rbp+80h] BYREF
  int v82; // [rsp+188h] [rbp+88h]
  __int128 v83; // [rsp+190h] [rbp+90h] BYREF
  __int128 v84; // [rsp+1A0h] [rbp+A0h]
  __int64 v85; // [rsp+1B0h] [rbp+B0h]
  __int64 v86[8]; // [rsp+1C0h] [rbp+C0h] BYREF

  v8 = a7;
  v70 = a5;
  v9 = a4;
  v75 = a8;
  v10 = a1;
  v49 = a4;
  v11 = 0;
  v12 = a3;
  v50 = a2;
  v67 = a1;
  v48 = 0;
  *(_OWORD *)v72 = 0;
  v60 = 64;
  v73 = 0;
  LODWORD(v62) = 0;
  v74 = 0;
  v80 = 0;
  v76 = 0;
  v52 = 0;
  *(_OWORD *)v77 = 0;
  v54 = 0;
  v78 = 0;
  Entry = 0;
  v79 = 0;
  v81 = 0;
  v82 = 0;
  Handle = 0;
  v68 = 0;
  v83 = 0;
  v85 = 0;
  v84 = 0;
  if ( g_CiIsWinPE && !byte_180049570 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&g_CipPolicyLock, 0);
    FileCache2 = CipLoadAndValidateRevocationList(0);
    ExReleasePushLockExclusiveEx(&g_CipPolicyLock, 0);
    KeLeaveCriticalRegion();
    if ( FileCache2 < 0 )
      return (unsigned int)FileCache2;
    v9 = v49;
    byte_180049570 = 1;
  }
  Object = 0;
  v14 = 0;
  v15 = v10 & 7;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&g_CipPolicyLock, 0);
  v18 = (int *)qword_180031FE0;
  do
  {
    if ( v15 == *v18 )
      break;
    v18 += 5;
  }
  while ( v18 != &dword_18003201C );
  if ( v18 == &dword_18003201C )
  {
    FileCache2 = -1073741637;
    goto LABEL_20;
  }
  if ( v18[1] )
  {
    LODWORD(v14) = 1;
  }
  else
  {
    if ( a6 != 1 || a7 != *v70 )
    {
      FileCache2 = -1073741811;
      goto LABEL_20;
    }
    LOBYTE(v14) = v50 == 1;
  }
  v19 = v18[2];
  LOBYTE(v17) = v9;
  v58 = v17;
  if ( v19 )
  {
    v51 = 0;
    if ( v19 == 2 )
    {
      if ( (_BYTE)v12 )
        goto LABEL_18;
    }
    else
    {
      v17 = v9;
      if ( v19 == 1 )
        v17 = v12;
      v58 = v17;
    }
  }
  else
  {
    v16 = v12 & 0xF;
    v20 = *((_DWORD *)g_CipWhichLevelComparisons + 8);
    if ( _bittest(&v20, v16) )
    {
LABEL_18:
      FileCache2 = -1073741811;
LABEL_19:
      v14 = 0;
      goto LABEL_20;
    }
    v51 = v12;
  }
  v22 = 15;
  if ( v18[4] )
    v22 = v9;
  v55[0] = v22;
  v23 = *((unsigned int *)g_CipWhichLevelComparisons + (v17 & 0xF));
  if ( (v23 & 2) != 0 )
  {
    v24 = (*((__int64 (__fastcall **)(__int64, __int64, __int64, __int64))&xmmword_18004A5B0 + 1))(v23, v16, v17, 2);
    v16 = (unsigned __int8)v58;
    if ( v24 == 2 )
      v16 = 2;
    LOBYTE(v58) = v16;
  }
  if ( v50 == 1 )
  {
    LOBYTE(v16) = 1;
    FileCache2 = IoConvertFileHandleToKernelHandle(a7, v16, (unsigned int)v14, 0, &v68);
    if ( FileCache2 < 0 )
      goto LABEL_19;
    v8 = v68;
  }
  v69 = 0;
  v25 = ObReferenceObjectByHandle(v8, (ACCESS_MASK)v14, (POBJECT_TYPE)IoFileObjectType, 0, &v69, 0);
  v14 = (struct _FILE_OBJECT *)v69;
  FileCache2 = v25;
  v59 = (struct _FILE_OBJECT *)v69;
  if ( v25 < 0 )
    goto LABEL_20;
  *(_DWORD *)v56 = 0;
  v61 = 0;
  v26 = 0;
  v49 = 0;
  v65 = 0;
  for ( i = 0; ; i = v57 + 1 )
  {
    v57 = i;
    if ( i >= a6 )
      break;
    MincryptFreePolicyInfo(v77);
    if ( LODWORD(v72[0]) )
    {
      I_MincryptFreeChainInfo(v73);
      *(_OWORD *)v72 = 0;
      LODWORD(v72[0]) = 0;
      v73 = 0;
      v74 = 0;
    }
    v30 = v18[1] == 1;
    v53[0] = 0;
    if ( v30 )
    {
      v31 = v70[v57];
      if ( v50 == 1 )
      {
        if ( Handle )
        {
          ZwClose(Handle);
          Handle = 0;
        }
        LOBYTE(v28) = 1;
        FileCache2 = IoConvertFileHandleToKernelHandle(v31, v28, 1, 0, &Handle);
        if ( FileCache2 < 0 )
          goto LABEL_20;
        v31 = Handle;
      }
      v71 = 0;
      FileCache2 = ObReferenceObjectByHandle(v31, 1u, (POBJECT_TYPE)IoFileObjectType, 0, &v71, 0);
      Object = v71;
      if ( FileCache2 < 0 )
        goto LABEL_20;
      v14 = (struct _FILE_OBJECT *)v71;
    }
    if ( !v18[3] )
    {
      v48 = 0;
      FileCache2 = CiGetFileCache2(v14, (__int64)&v48, 0, 0, 0, 0, (__int64)v53);
      if ( FileCache2 < 0 )
        goto LABEL_68;
      if ( v18[1] )
        goto LABEL_67;
      LOBYTE(v29) = v51;
      if ( (unsigned __int8)CipIsSigningLevelSatisfiedByCachedSigningLevels(v29, v53[0], &v48) )
        goto LABEL_108;
    }
    if ( FileCache2 >= 0 )
    {
LABEL_67:
      if ( v18[3] != 1 )
        goto LABEL_92;
    }
LABEL_68:
    if ( v18[2] )
    {
      v32 = (bool *)&v54;
      v60 = 64;
      if ( v18[4] )
        v32 = 0;
      v33 = CipValidateFileObjectByFileOrPageHash(
              v14,
              0,
              v58,
              0,
              v75,
              v72,
              (__int64)v77,
              &v48,
              v86,
              &v60,
              &v62,
              &v52,
              v32,
              &Entry);
      FileCache2 = v33;
      if ( v33 < 0 )
      {
        CipQueryAndLogFileEventWithStatus(v14, (unsigned int)v33, CiSetFileCacheFailedValidation);
        v11 = (char *)Entry;
        goto LABEL_108;
      }
      if ( v54 )
        v15 |= 0x40u;
      else
        v15 &= ~0x40u;
      if ( v52 )
      {
        v49 = v52;
        v52 = 0;
      }
      CipSignatureValidityPeriod(v72, &v76);
      v11 = (char *)Entry;
      LOBYTE(v34) = v48;
      LOBYTE(v35) = 1;
      CipGetValidatedSigningLevels(v34, (_DWORD)Entry, 0, v35, v14, (__int64)v53);
      if ( v11 )
      {
        v36 = *((_DWORD *)v11 + 590);
        if ( (v36 & 0x400) != 0 )
        {
          if ( !v26 || *(_QWORD *)(v11 + 2108) < v81 )
          {
            v26 = 1;
            v81 = *(_QWORD *)(v11 + 2108);
            v82 = *((_DWORD *)v11 + 529);
          }
        }
        else if ( (v36 & 0x1000) != 0 )
        {
          if ( !v26 || *(_QWORD *)(v11 + 2186) < v81 )
          {
            v26 = 1;
            v81 = *(_QWORD *)(v11 + 2186);
            v82 = *(_DWORD *)(v11 + 2194);
          }
          if ( !v18[1] )
          {
            v37 = &v83;
            v38 = *(_OWORD *)(v11 + 3340);
            v61 = *((_DWORD *)v11 + 524);
            if ( v61 >= 0 )
              v37 = (__int128 *)v65;
            v83 = v38;
            v65 = (__int64)v37;
            v84 = *(_OWORD *)(v11 + 3356);
            v85 = *(_QWORD *)(v11 + 3372);
          }
        }
        CiFreeValidationContext((void (***)(void))v11);
        v11 = 0;
        Entry = 0;
      }
    }
    else
    {
      v48 = v51;
    }
LABEL_92:
    LOBYTE(v29) = v22;
    if ( !(unsigned __int8)CipIsSigningLevelSatisfiedByCachedSigningLevels(v29, v53[0], &v48) )
    {
      if ( v57 )
      {
        LOBYTE(v39) = v48;
        if ( !(unsigned __int8)CipIsSigningLevelSatisfiedByCachedSigningLevels(v39, *(unsigned int *)v56, v55) )
        {
          FileCache2 = -1073740760;
          CipQueryAndLogFileEventWithStatus(v14, 3221226536LL, CiSetFileCacheFailedSigningLevel);
LABEL_108:
          v14 = v59;
          goto LABEL_20;
        }
      }
      v22 = v48;
      v55[0] = v48;
    }
    if ( v57 )
    {
      v40 = 0;
      for ( j = 15; j >= 2u; --j )
      {
        v42 = v53[0];
        if ( _bittest(&v42, j) )
          v40 |= *((_WORD *)g_CipWhichLevelComparisons + 2 * j);
      }
      v56[0] &= v40;
    }
    else
    {
      *(_DWORD *)v56 = v53[0];
    }
    if ( Object )
    {
      ObfDereferenceObject(Object);
      Object = 0;
    }
    v14 = v59;
  }
  if ( (unsigned __int8)v22 >= 2u )
  {
    if ( v18[1] )
    {
      v43 = *((_DWORD *)g_CipWhichLevelComparisons + 12);
      if ( _bittest(&v43, v22 & 0xF) )
        v22 = 8;
    }
    else
    {
      v15 = v15 & 0xFFFFFFFC | 2;
    }
    CurrentProcess = PsGetCurrentProcess();
    ActionsForImage = CiGetActionsForImage(CurrentProcess, v14, 0, 0, v22);
    if ( !v49 && (ActionsForImage & 2) != 0 )
    {
      v46 = (v15 & 1) == 0 && (_QWORD)v73 && *(_DWORD *)(v73 + 48)
          ? CipSetFileCache(
              v14,
              v15,
              v22,
              *(_QWORD *)(v73 + 40) + 8LL,
              *(_DWORD *)(*(_QWORD *)(v73 + 40) + 4LL),
              **(_DWORD **)(v73 + 40),
              (__int64)v86,
              v60,
              v62,
              v47,
              0,
              (unsigned __int64)&v81 & -(__int64)(v26 != 0),
              v56[0],
              v61,
              v65)
          : CipSetFileCache(
              v14,
              v15,
              v22,
              0,
              0,
              0,
              0,
              0,
              0,
              v47,
              0,
              (unsigned __int64)&v81 & -(__int64)(v26 != 0),
              v56[0],
              v61,
              v65);
      FileCache2 = v46;
      if ( (v67 & 0x800) != 0 )
        FileCache2 = 0;
    }
  }
  else
  {
    FileCache2 = -1073740760;
    CipQueryAndLogFileEventWithStatus(v14, 3221226536LL, CiSetFileCacheFailedSigningLevel);
  }
LABEL_20:
  ExReleasePushLockSharedEx(&g_CipPolicyLock, 0);
  KeLeaveCriticalRegion();
  MincryptFreePolicyInfo(v77);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v14 )
    ObfDereferenceObject(v14);
  if ( Handle )
    ZwClose(Handle);
  if ( v68 )
    ZwClose(v68);
  if ( LODWORD(v72[0]) )
    I_MincryptFreeChainInfo(v73);
  if ( v11 )
    CiFreeValidationContext((void (***)(void))v11);
  return (unsigned int)FileCache2;
}

```

## disassembly

```asm
0x180096f80  mov     [rsp-8+arg_8], rbx
0x180096f85  push    rbp
0x180096f86  push    rsi
0x180096f87  push    rdi
0x180096f88  push    r12
0x180096f8a  push    r13
0x180096f8c  push    r14
0x180096f8e  push    r15
0x180096f90  lea     rbp, [rsp-110h]
0x180096f98  sub     rsp, 210h
0x180096f9f  mov     rax, cs:__security_cookie
0x180096fa6  xor     rax, rsp
0x180096fa9  mov     [rbp+140h+var_40], rax
0x180096fb0  mov     rax, [rbp+140h+arg_20]
0x180096fb7  xor     esi, esi
0x180096fb9  mov     r13, [rbp+140h+arg_30]
0x180096fc0  xorps   xmm0, xmm0
0x180096fc3  xorps   xmm1, xmm1
0x180096fc6  mov     [rbp+140h+var_150], rax
0x180096fca  mov     rax, [rbp+140h+arg_38]
0x180096fd1  mov     bl, r9b
0x180096fd4  mov     [rbp+140h+var_110], rax
0x180096fd8  mov     edi, ecx
0x180096fda  xor     eax, eax
0x180096fdc  mov     byte ptr [rbp+140h+var_1C0+1], bl
0x180096fdf  cmp     cs:g_CiIsWinPE, sil
0x180096fe6  mov     r14d, esi
0x180096fe9  movzx   r12d, r8b
0x180096fed  mov     byte ptr [rbp+140h+var_1C0+2], dl
0x180096ff0  mov     [rbp+140h+var_168], ecx
0x180096ff3  mov     byte ptr [rbp+140h+var_1C0], sil
0x180096ff7  movups  xmmword ptr [rbp+140h+var_140], xmm0
0x180096ffb  mov     dword ptr [rbp+140h+var_198], 40h ; '@'
0x180097002  movups  [rbp+140h+var_130], xmm0
0x180097006  mov     dword ptr [rbp+140h+var_190], esi
0x180097009  movups  [rbp+140h+var_120], xmm0
0x18009700d  mov     [rbp+140h+var_C8], rax
0x180097011  movups  [rbp+140h+var_108], xmm0
0x180097015  mov     byte ptr [rbp+140h+var_1C0+4], sil
0x180097019  movups  xmmword ptr [rbp+140h+var_F8], xmm1
0x18009701d  mov     [rbp+140h+var_1B4], sil
0x180097021  movups  [rbp+140h+var_E8], xmm1
0x180097025  mov     [rbp+140h+Entry], rsi
0x180097029  movups  [rbp+140h+var_D8], xmm1
0x18009702d  mov     [rbp+140h+var_C0], rax
0x180097034  mov     [rbp+140h+var_B8], eax
0x18009703a  mov     [rbp+140h+Handle], rsi
0x18009703e  mov     [rbp+140h+var_160], rsi
0x180097042  movups  [rbp+140h+var_B0], xmm0
0x180097049  mov     [rbp+140h+var_90], rax
0x180097050  movups  [rbp+140h+var_A0], xmm0
0x180097057  jz      short loc_1800970C0
0x180097059  mov     al, cs:byte_180049570
0x18009705f  test    al, al
0x180097061  jnz     short loc_1800970C0
0x180097063  call    cs:__imp_KeEnterCriticalRegion
0x18009706a  nop     dword ptr [rax+rax+00h]
0x18009706f  xor     edx, edx
0x180097071  lea     rcx, g_CipPolicyLock
0x180097078  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18009707f  nop     dword ptr [rax+rax+00h]
0x180097084  xor     ecx, ecx
0x180097086  call    CipLoadAndValidateRevocationList
0x18009708b  xor     edx, edx
0x18009708d  lea     rcx, g_CipPolicyLock
0x180097094  mov     ebx, eax
0x180097096  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18009709d  nop     dword ptr [rax+rax+00h]
0x1800970a2  call    cs:__imp_KeLeaveCriticalRegion
0x1800970a9  nop     dword ptr [rax+rax+00h]
0x1800970ae  test    ebx, ebx
0x1800970b0  js      loc_180097216
0x1800970b6  mov     bl, byte ptr [rbp+140h+var_1C0+1]
0x1800970b9  mov     cs:byte_180049570, 1
0x1800970c0  mov     [rbp+140h+Object], rsi
0x1800970c4  mov     r15, rsi
0x1800970c7  and     edi, 7
0x1800970ca  call    cs:__imp_KeEnterCriticalRegion
0x1800970d1  nop     dword ptr [rax+rax+00h]
0x1800970d6  xor     edx, edx
0x1800970d8  lea     rcx, g_CipPolicyLock
0x1800970df  call    cs:__imp_ExAcquirePushLockSharedEx
0x1800970e6  nop     dword ptr [rax+rax+00h]
0x1800970eb  lea     rax, dword_18003201C
0x1800970f2  lea     rsi, qword_180031FE0
0x1800970f9  cmp     edi, [rsi]
0x1800970fb  jz      short loc_180097106
0x1800970fd  add     rsi, 14h
0x180097101  cmp     rsi, rax
0x180097104  jnz     short loc_1800970F9
0x180097106  cmp     rsi, rax
0x180097109  jnz     short loc_180097112
0x18009710b  mov     ebx, 0C00000BBh
0x180097110  jmp     short loc_18009717A
0x180097112  cmp     [rsi+4], r14d
0x180097116  jnz     short loc_18009713B
0x180097118  cmp     [rbp+140h+arg_28], 1
0x18009711f  jnz     short loc_180097134
0x180097121  mov     rax, [rbp+140h+var_150]
0x180097125  cmp     r13, [rax]
0x180097128  jnz     short loc_180097134
0x18009712a  cmp     byte ptr [rbp+140h+var_1C0+2], 1
0x18009712e  setz    r15b
0x180097132  jmp     short loc_180097141
0x180097134  mov     ebx, 0C000000Dh
0x180097139  jmp     short loc_18009717A
0x18009713b  mov     r15d, 1
0x180097141  mov     ecx, [rsi+8]
0x180097144  mov     r8b, bl
0x180097147  mov     [rbp+140h+var_1A8], r8d
0x18009714b  mov     r9d, 2
0x180097151  test    ecx, ecx
0x180097153  jnz     loc_180097249
0x180097159  mov     rax, cs:g_CipWhichLevelComparisons
0x180097160  mov     edx, r12d
0x180097163  and     edx, 0Fh
0x180097166  mov     ecx, [rax+20h]
0x180097169  bt      ecx, edx
0x18009716c  jnb     loc_180097243
0x180097172  mov     ebx, 0C000000Dh
0x180097177  mov     r15, r14
0x18009717a  xor     edx, edx
0x18009717c  lea     rcx, g_CipPolicyLock
0x180097183  call    cs:__imp_ExReleasePushLockSharedEx
0x18009718a  nop     dword ptr [rax+rax+00h]
0x18009718f  call    cs:__imp_KeLeaveCriticalRegion
0x180097196  nop     dword ptr [rax+rax+00h]
0x18009719b  lea     rcx, [rbp+140h+var_F8]
0x18009719f  call    MincryptFreePolicyInfo
0x1800971a4  mov     rax, [rbp+140h+Object]
0x1800971a8  test    rax, rax
0x1800971ab  jz      short loc_1800971BC
0x1800971ad  mov     rcx, rax; Object
0x1800971b0  call    cs:__imp_ObfDereferenceObject
0x1800971b7  nop     dword ptr [rax+rax+00h]
0x1800971bc  test    r15, r15
0x1800971bf  jz      short loc_1800971D0
0x1800971c1  mov     rcx, r15; Object
0x1800971c4  call    cs:__imp_ObfDereferenceObject
0x1800971cb  nop     dword ptr [rax+rax+00h]
0x1800971d0  mov     rcx, [rbp+140h+Handle]; Handle
0x1800971d4  test    rcx, rcx
0x1800971d7  jz      short loc_1800971E5
0x1800971d9  call    cs:__imp_ZwClose
0x1800971e0  nop     dword ptr [rax+rax+00h]
0x1800971e5  mov     rcx, [rbp+140h+var_160]; Handle
0x1800971e9  test    rcx, rcx
0x1800971ec  jz      short loc_1800971FA
0x1800971ee  call    cs:__imp_ZwClose
0x1800971f5  nop     dword ptr [rax+rax+00h]
0x1800971fa  cmp     dword ptr [rbp+140h+var_140], 0
0x1800971fe  jz      short loc_180097209
0x180097200  mov     rcx, qword ptr [rbp+140h+var_130]
0x180097204  call    I_MincryptFreeChainInfo
0x180097209  test    r14, r14
0x18009720c  jz      short loc_180097216
0x18009720e  mov     rcx, r14; Entry
0x180097211  call    CiFreeValidationContext
0x180097216  mov     eax, ebx
0x180097218  mov     rcx, [rbp+140h+var_40]
0x18009721f  xor     rcx, rsp; StackCookie
0x180097222  call    __security_check_cookie
0x180097227  mov     rbx, [rsp+240h+arg_8]
0x18009722f  add     rsp, 210h
0x180097236  pop     r15
0x180097238  pop     r14
0x18009723a  pop     r13
0x18009723c  pop     r12
0x18009723e  pop     rdi
0x18009723f  pop     rsi
0x180097240  pop     rbp
0x180097241  retn
0x180097243  mov     byte ptr [rbp+140h+var_1C0+3], r12b
0x180097247  jmp     short loc_18009726B
0x180097249  mov     byte ptr [rbp+140h+var_1C0+3], r14b
0x18009724d  cmp     ecx, r9d
0x180097250  jnz     short loc_18009725C
0x180097252  test    r12b, r12b
0x180097255  jz      short loc_18009726B
0x180097257  jmp     loc_180097172
0x18009725c  cmp     ecx, 1
0x18009725f  movzx   r8d, r8b
0x180097263  cmovz   r8d, r12d
0x180097267  mov     [rbp+140h+var_1A8], r8d
0x18009726b  cmp     [rsi+10h], r14d
0x18009726f  mov     r12d, 0Fh
0x180097275  movzx   eax, bl
0x180097278  cmovnz  r12d, eax
0x18009727c  movzx   ecx, r8b
0x180097280  mov     rax, cs:g_CipWhichLevelComparisons
0x180097287  and     ecx, 0Fh
0x18009728a  mov     [rbp+140h+var_1B3], r12b
0x18009728e  mov     ecx, [rax+rcx*4]
0x180097291  test    r9b, cl
0x180097294  jz      short loc_1800972B6
0x180097296  mov     rax, qword ptr cs:xmmword_18004A5B0+8
0x18009729d  call    _guard_dispatch_icall
0x1800972a2  movzx   edx, byte ptr [rbp+140h+var_1A8]
0x1800972a6  mov     r9d, 2
0x1800972ac  cmp     al, r9b
0x1800972af  cmovz   edx, r9d
0x1800972b3  mov     byte ptr [rbp+140h+var_1A8], dl
0x1800972b6  cmp     byte ptr [rbp+140h+var_1C0+2], 1
0x1800972ba  jnz     short loc_1800972EA
0x1800972bc  lea     rax, [rbp+140h+var_160]
0x1800972c0  xor     r9d, r9d
0x1800972c3  mov     r8d, r15d
0x1800972c6  mov     [rsp+240h+var_220], rax
0x1800972cb  mov     dl, 1
0x1800972cd  mov     rcx, r13
0x1800972d0  call    cs:__imp_IoConvertFileHandleToKernelHandle
0x1800972d7  nop     dword ptr [rax+rax+00h]
0x1800972dc  mov     ebx, eax
0x1800972de  test    eax, eax
0x1800972e0  js      loc_180097177
0x1800972e6  mov     r13, [rbp+140h+var_160]
0x1800972ea  mov     r8, cs:__imp_IoFileObjectType
0x1800972f1  lea     rax, [rbp+140h+var_158]
0x1800972f5  mov     [rsp+240h+HandleInformation], r14; HandleInformation
0x1800972fa  xor     r9d, r9d; AccessMode
0x1800972fd  mov     edx, r15d; DesiredAccess
0x180097300  mov     [rbp+140h+var_158], r14
0x180097304  mov     rcx, r13; Handle
0x180097307  mov     [rsp+240h+var_220], rax; Object
0x18009730c  mov     r8, [r8]; ObjectType
0x18009730f  call    cs:__imp_ObReferenceObjectByHandle
0x180097316  nop     dword ptr [rax+rax+00h]
0x18009731b  mov     r15, [rbp+140h+var_158]
0x18009731f  mov     ebx, eax
0x180097321  mov     [rbp+140h+var_1A0], r15
0x180097325  test    eax, eax
0x180097327  js      loc_18009717A
0x18009732d  xor     edx, edx
0x18009732f  mov     dword ptr [rbp+140h+var_1B0], r14d
0x180097333  xor     cl, cl
0x180097335  mov     dword ptr [rbp+140h+var_198+4], edx
0x180097338  xor     r13b, r13b
0x18009733b  mov     byte ptr [rbp+140h+var_1C0+1], cl
0x18009733e  mov     [rbp+140h+var_178], rdx
0x180097342  xor     eax, eax
0x180097344  mov     [rbp+140h+var_1AC], eax
0x180097347  cmp     eax, [rbp+140h+arg_28]
0x18009734d  jnb     loc_18009774F
0x180097353  lea     rcx, [rbp+140h+var_F8]
0x180097357  call    MincryptFreePolicyInfo
0x18009735c  cmp     dword ptr [rbp+140h+var_140], 0
0x180097360  jz      short loc_18009737F
0x180097362  mov     rcx, qword ptr [rbp+140h+var_130]
0x180097366  call    I_MincryptFreeChainInfo
0x18009736b  xorps   xmm0, xmm0
0x18009736e  movups  xmmword ptr [rbp+140h+var_140], xmm0
0x180097372  movss   dword ptr [rbp+140h+var_140], xmm0
0x180097377  movups  [rbp+140h+var_130], xmm0
0x18009737b  movups  [rbp+140h+var_120], xmm0
0x18009737f  xor     eax, eax
0x180097381  cmp     dword ptr [rsi+4], 1
0x180097385  mov     [rbp+140h+var_1B8], ax
0x180097389  jnz     loc_18009743C
0x18009738f  cmp     byte ptr [rbp+140h+var_1C0+2], 1
0x180097393  mov     eax, [rbp+140h+var_1AC]
0x180097396  mov     rcx, [rbp+140h+var_150]
0x18009739a  mov     rbx, [rcx+rax*8]
0x18009739e  jnz     short loc_1800973ED
0x1800973a0  mov     rcx, [rbp+140h+Handle]; Handle
0x1800973a4  test    rcx, rcx
0x1800973a7  jz      short loc_1800973BD
0x1800973a9  call    cs:__imp_ZwClose
0x1800973b0  nop     dword ptr [rax+rax+00h]
0x1800973b5  mov     [rbp+140h+Handle], 0
0x1800973bd  xor     r9d, r9d
0x1800973c0  lea     rax, [rbp+140h+Handle]
0x1800973c4  mov     rcx, rbx
0x1800973c7  mov     [rsp+240h+var_220], rax
0x1800973cc  lea     r8d, [r9+1]
0x1800973d0  mov     dl, r8b
0x1800973d3  call    cs:__imp_IoConvertFileHandleToKernelHandle
0x1800973da  nop     dword ptr [rax+rax+00h]
0x1800973df  mov     ebx, eax
0x1800973e1  test    eax, eax
0x1800973e3  js      loc_18009717A
0x1800973e9  mov     rbx, [rbp+140h+Handle]
0x1800973ed  mov     r8, cs:__imp_IoFileObjectType
0x1800973f4  lea     rax, [rbp+140h+var_148]
0x1800973f8  xor     r9d, r9d; AccessMode
0x1800973fb  mov     [rsp+240h+HandleInformation], 0; HandleInformation
0x180097404  mov     rcx, rbx; Handle
0x180097407  mov     [rbp+140h+var_148], 0
0x18009740f  mov     [rsp+240h+var_220], rax; Object
0x180097414  mov     r8, [r8]; ObjectType
0x180097417  lea     edx, [r9+1]; DesiredAccess
0x18009741b  call    cs:__imp_ObReferenceObjectByHandle
0x180097422  nop     dword ptr [rax+rax+00h]
0x180097427  mov     ebx, eax
0x180097429  mov     rax, [rbp+140h+var_148]
0x18009742d  mov     [rbp+140h+Object], rax
0x180097431  test    ebx, ebx
0x180097433  js      loc_18009717A
0x180097439  mov     r15, rax
0x18009743c  cmp     dword ptr [rsi+0Ch], 0
0x180097440  jnz     short loc_180097497
  ... truncated ...
```
