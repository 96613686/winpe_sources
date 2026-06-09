# CiSetFileCache

- ea: `0x180095950`
- end: `0x180096290`
- name: `CiSetFileCache`
- size: `2368`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, HANDLE, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18002bef0`
- `0x18002bfd0`
- `0x180058c2c`
- `0x180059758`
- `0x1800603a0`
- `0x180071aa4`
- `0x18009516c`
- `0x180095588`
- `0x180095950`
- `0x180096fa4`
- `0x180096fdc`
- `0x180097ae8`
- `0x180098474`
- `0x18009ca38`
- `0x18009ce68`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180095a33`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180095a9a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180095a33`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180095a9a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180095a48`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180095a48`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180095a66`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180095a66`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180095b53`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x180095b53`
- `ntoskrnl!PsGetCurrentProcess` at `0x180096170`
- `ntoskrnl!PsGetCurrentProcess` at `0x180096170`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180095aaf`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180095aaf`
- `ntoskrnl!ZwClose` at `0x180095ba9`
- `ntoskrnl!ZwClose` at `0x180095bbe`
- `ntoskrnl!ZwClose` at `0x180095d79`
- `ntoskrnl!ZwClose` at `0x180095ba9`
- `ntoskrnl!ZwClose` at `0x180095bbe`
- `ntoskrnl!ZwClose` at `0x180095d79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180095a72`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180095b5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180095a72`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180095b5f`
- `ntoskrnl!ObfDereferenceObject` at `0x180095b80`
- `ntoskrnl!ObfDereferenceObject` at `0x180095b94`
- `ntoskrnl!ObfDereferenceObject` at `0x1800960c9`
- `ntoskrnl!ObfDereferenceObject` at `0x180095b80`
- `ntoskrnl!ObfDereferenceObject` at `0x180095b94`
- `ntoskrnl!ObfDereferenceObject` at `0x1800960c9`
- `ntoskrnl!IoFileObjectType` at `0x180095cba`
- `ntoskrnl!IoFileObjectType` at `0x180095dbd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180095cdf`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180095deb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180095cdf`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180095deb`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x180095ca0`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x180095da3`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x180095ca0`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x180095da3`

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
  if ( g_CiIsWinPE && !byte_180048980 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&g_CipPolicyLock, 0);
    FileCache2 = CipLoadAndValidateRevocationList(0);
    ExReleasePushLockExclusiveEx(&g_CipPolicyLock, 0);
    KeLeaveCriticalRegion();
    if ( FileCache2 < 0 )
      return (unsigned int)FileCache2;
    v9 = v49;
    byte_180048980 = 1;
  }
  Object = 0;
  v14 = 0;
  v15 = v10 & 7;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&g_CipPolicyLock, 0);
  v18 = (int *)qword_180031EE0;
  do
  {
    if ( v15 == *v18 )
      break;
    v18 += 5;
  }
  while ( v18 != &dword_180031F1C );
  if ( v18 == &dword_180031F1C )
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
    v24 = (*((__int64 (__fastcall **)(__int64, __int64, __int64, __int64))&xmmword_180049650 + 1))(v23, v16, v17, 2);
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
0x180095950  mov     [rsp-8+arg_8], rbx
0x180095955  push    rbp
0x180095956  push    rsi
0x180095957  push    rdi
0x180095958  push    r12
0x18009595a  push    r13
0x18009595c  push    r14
0x18009595e  push    r15
0x180095960  lea     rbp, [rsp-110h]
0x180095968  sub     rsp, 210h
0x18009596f  mov     rax, cs:__security_cookie
0x180095976  xor     rax, rsp
0x180095979  mov     [rbp+140h+var_40], rax
0x180095980  mov     rax, [rbp+140h+arg_20]
0x180095987  xor     esi, esi
0x180095989  mov     r13, [rbp+140h+arg_30]
0x180095990  xorps   xmm0, xmm0
0x180095993  xorps   xmm1, xmm1
0x180095996  mov     [rbp+140h+var_150], rax
0x18009599a  mov     rax, [rbp+140h+arg_38]
0x1800959a1  mov     bl, r9b
0x1800959a4  mov     [rbp+140h+var_110], rax
0x1800959a8  mov     edi, ecx
0x1800959aa  xor     eax, eax
0x1800959ac  mov     byte ptr [rbp+140h+var_1C0+1], bl
0x1800959af  cmp     cs:g_CiIsWinPE, sil
0x1800959b6  mov     r14d, esi
0x1800959b9  movzx   r12d, r8b
0x1800959bd  mov     byte ptr [rbp+140h+var_1C0+2], dl
0x1800959c0  mov     [rbp+140h+var_168], ecx
0x1800959c3  mov     byte ptr [rbp+140h+var_1C0], sil
0x1800959c7  movups  xmmword ptr [rbp+140h+var_140], xmm0
0x1800959cb  mov     dword ptr [rbp+140h+var_198], 40h ; '@'
0x1800959d2  movups  [rbp+140h+var_130], xmm0
0x1800959d6  mov     dword ptr [rbp+140h+var_190], esi
0x1800959d9  movups  [rbp+140h+var_120], xmm0
0x1800959dd  mov     [rbp+140h+var_C8], rax
0x1800959e1  movups  [rbp+140h+var_108], xmm0
0x1800959e5  mov     byte ptr [rbp+140h+var_1C0+4], sil
0x1800959e9  movups  xmmword ptr [rbp+140h+var_F8], xmm1
0x1800959ed  mov     [rbp+140h+var_1B4], sil
0x1800959f1  movups  [rbp+140h+var_E8], xmm1
0x1800959f5  mov     [rbp+140h+Entry], rsi
0x1800959f9  movups  [rbp+140h+var_D8], xmm1
0x1800959fd  mov     [rbp+140h+var_C0], rax
0x180095a04  mov     [rbp+140h+var_B8], eax
0x180095a0a  mov     [rbp+140h+Handle], rsi
0x180095a0e  mov     [rbp+140h+var_160], rsi
0x180095a12  movups  [rbp+140h+var_B0], xmm0
0x180095a19  mov     [rbp+140h+var_90], rax
0x180095a20  movups  [rbp+140h+var_A0], xmm0
0x180095a27  jz      short loc_180095A90
0x180095a29  mov     al, cs:byte_180048980
0x180095a2f  test    al, al
0x180095a31  jnz     short loc_180095A90
0x180095a33  call    cs:__imp_KeEnterCriticalRegion
0x180095a3a  nop     dword ptr [rax+rax+00h]
0x180095a3f  xor     edx, edx
0x180095a41  lea     rcx, g_CipPolicyLock
0x180095a48  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x180095a4f  nop     dword ptr [rax+rax+00h]
0x180095a54  xor     ecx, ecx
0x180095a56  call    CipLoadAndValidateRevocationList
0x180095a5b  xor     edx, edx
0x180095a5d  lea     rcx, g_CipPolicyLock
0x180095a64  mov     ebx, eax
0x180095a66  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180095a6d  nop     dword ptr [rax+rax+00h]
0x180095a72  call    cs:__imp_KeLeaveCriticalRegion
0x180095a79  nop     dword ptr [rax+rax+00h]
0x180095a7e  test    ebx, ebx
0x180095a80  js      loc_180095BE6
0x180095a86  mov     bl, byte ptr [rbp+140h+var_1C0+1]
0x180095a89  mov     cs:byte_180048980, 1
0x180095a90  mov     [rbp+140h+Object], rsi
0x180095a94  mov     r15, rsi
0x180095a97  and     edi, 7
0x180095a9a  call    cs:__imp_KeEnterCriticalRegion
0x180095aa1  nop     dword ptr [rax+rax+00h]
0x180095aa6  xor     edx, edx
0x180095aa8  lea     rcx, g_CipPolicyLock
0x180095aaf  call    cs:__imp_ExAcquirePushLockSharedEx
0x180095ab6  nop     dword ptr [rax+rax+00h]
0x180095abb  lea     rax, dword_180031F1C
0x180095ac2  lea     rsi, qword_180031EE0
0x180095ac9  cmp     edi, [rsi]
0x180095acb  jz      short loc_180095AD6
0x180095acd  add     rsi, 14h
0x180095ad1  cmp     rsi, rax
0x180095ad4  jnz     short loc_180095AC9
0x180095ad6  cmp     rsi, rax
0x180095ad9  jnz     short loc_180095AE2
0x180095adb  mov     ebx, 0C00000BBh
0x180095ae0  jmp     short loc_180095B4A
0x180095ae2  cmp     [rsi+4], r14d
0x180095ae6  jnz     short loc_180095B0B
0x180095ae8  cmp     [rbp+140h+arg_28], 1
0x180095aef  jnz     short loc_180095B04
0x180095af1  mov     rax, [rbp+140h+var_150]
0x180095af5  cmp     r13, [rax]
0x180095af8  jnz     short loc_180095B04
0x180095afa  cmp     byte ptr [rbp+140h+var_1C0+2], 1
0x180095afe  setz    r15b
0x180095b02  jmp     short loc_180095B11
0x180095b04  mov     ebx, 0C000000Dh
0x180095b09  jmp     short loc_180095B4A
0x180095b0b  mov     r15d, 1
0x180095b11  mov     ecx, [rsi+8]
0x180095b14  mov     r8b, bl
0x180095b17  mov     [rbp+140h+var_1A8], r8d
0x180095b1b  mov     r9d, 2
0x180095b21  test    ecx, ecx
0x180095b23  jnz     loc_180095C19
0x180095b29  mov     rax, cs:g_CipWhichLevelComparisons
0x180095b30  mov     edx, r12d
0x180095b33  and     edx, 0Fh
0x180095b36  mov     ecx, [rax+20h]
0x180095b39  bt      ecx, edx
0x180095b3c  jnb     loc_180095C13
0x180095b42  mov     ebx, 0C000000Dh
0x180095b47  mov     r15, r14
0x180095b4a  xor     edx, edx
0x180095b4c  lea     rcx, g_CipPolicyLock
0x180095b53  call    cs:__imp_ExReleasePushLockSharedEx
0x180095b5a  nop     dword ptr [rax+rax+00h]
0x180095b5f  call    cs:__imp_KeLeaveCriticalRegion
0x180095b66  nop     dword ptr [rax+rax+00h]
0x180095b6b  lea     rcx, [rbp+140h+var_F8]
0x180095b6f  call    MincryptFreePolicyInfo
0x180095b74  mov     rax, [rbp+140h+Object]
0x180095b78  test    rax, rax
0x180095b7b  jz      short loc_180095B8C
0x180095b7d  mov     rcx, rax; Object
0x180095b80  call    cs:__imp_ObfDereferenceObject
0x180095b87  nop     dword ptr [rax+rax+00h]
0x180095b8c  test    r15, r15
0x180095b8f  jz      short loc_180095BA0
0x180095b91  mov     rcx, r15; Object
0x180095b94  call    cs:__imp_ObfDereferenceObject
0x180095b9b  nop     dword ptr [rax+rax+00h]
0x180095ba0  mov     rcx, [rbp+140h+Handle]; Handle
0x180095ba4  test    rcx, rcx
0x180095ba7  jz      short loc_180095BB5
0x180095ba9  call    cs:__imp_ZwClose
0x180095bb0  nop     dword ptr [rax+rax+00h]
0x180095bb5  mov     rcx, [rbp+140h+var_160]; Handle
0x180095bb9  test    rcx, rcx
0x180095bbc  jz      short loc_180095BCA
0x180095bbe  call    cs:__imp_ZwClose
0x180095bc5  nop     dword ptr [rax+rax+00h]
0x180095bca  cmp     dword ptr [rbp+140h+var_140], 0
0x180095bce  jz      short loc_180095BD9
0x180095bd0  mov     rcx, qword ptr [rbp+140h+var_130]
0x180095bd4  call    I_MincryptFreeChainInfo
0x180095bd9  test    r14, r14
0x180095bdc  jz      short loc_180095BE6
0x180095bde  mov     rcx, r14; Entry
0x180095be1  call    CiFreeValidationContext
0x180095be6  mov     eax, ebx
0x180095be8  mov     rcx, [rbp+140h+var_40]
0x180095bef  xor     rcx, rsp; StackCookie
0x180095bf2  call    __security_check_cookie
0x180095bf7  mov     rbx, [rsp+240h+arg_8]
0x180095bff  add     rsp, 210h
0x180095c06  pop     r15
0x180095c08  pop     r14
0x180095c0a  pop     r13
0x180095c0c  pop     r12
0x180095c0e  pop     rdi
0x180095c0f  pop     rsi
0x180095c10  pop     rbp
0x180095c11  retn
0x180095c13  mov     byte ptr [rbp+140h+var_1C0+3], r12b
0x180095c17  jmp     short loc_180095C3B
0x180095c19  mov     byte ptr [rbp+140h+var_1C0+3], r14b
0x180095c1d  cmp     ecx, r9d
0x180095c20  jnz     short loc_180095C2C
0x180095c22  test    r12b, r12b
0x180095c25  jz      short loc_180095C3B
0x180095c27  jmp     loc_180095B42
0x180095c2c  cmp     ecx, 1
0x180095c2f  movzx   r8d, r8b
0x180095c33  cmovz   r8d, r12d
0x180095c37  mov     [rbp+140h+var_1A8], r8d
0x180095c3b  cmp     [rsi+10h], r14d
0x180095c3f  mov     r12d, 0Fh
0x180095c45  movzx   eax, bl
0x180095c48  cmovnz  r12d, eax
0x180095c4c  movzx   ecx, r8b
0x180095c50  mov     rax, cs:g_CipWhichLevelComparisons
0x180095c57  and     ecx, 0Fh
0x180095c5a  mov     [rbp+140h+var_1B3], r12b
0x180095c5e  mov     ecx, [rax+rcx*4]
0x180095c61  test    r9b, cl
0x180095c64  jz      short loc_180095C86
0x180095c66  mov     rax, qword ptr cs:xmmword_180049650+8
0x180095c6d  call    _guard_dispatch_icall
0x180095c72  movzx   edx, byte ptr [rbp+140h+var_1A8]
0x180095c76  mov     r9d, 2
0x180095c7c  cmp     al, r9b
0x180095c7f  cmovz   edx, r9d
0x180095c83  mov     byte ptr [rbp+140h+var_1A8], dl
0x180095c86  cmp     byte ptr [rbp+140h+var_1C0+2], 1
0x180095c8a  jnz     short loc_180095CBA
0x180095c8c  lea     rax, [rbp+140h+var_160]
0x180095c90  xor     r9d, r9d
0x180095c93  mov     r8d, r15d
0x180095c96  mov     [rsp+240h+var_220], rax
0x180095c9b  mov     dl, 1
0x180095c9d  mov     rcx, r13
0x180095ca0  call    cs:__imp_IoConvertFileHandleToKernelHandle
0x180095ca7  nop     dword ptr [rax+rax+00h]
0x180095cac  mov     ebx, eax
0x180095cae  test    eax, eax
0x180095cb0  js      loc_180095B47
0x180095cb6  mov     r13, [rbp+140h+var_160]
0x180095cba  mov     r8, cs:__imp_IoFileObjectType
0x180095cc1  lea     rax, [rbp+140h+var_158]
0x180095cc5  mov     [rsp+240h+HandleInformation], r14; HandleInformation
0x180095cca  xor     r9d, r9d; AccessMode
0x180095ccd  mov     edx, r15d; DesiredAccess
0x180095cd0  mov     [rbp+140h+var_158], r14
0x180095cd4  mov     rcx, r13; Handle
0x180095cd7  mov     [rsp+240h+var_220], rax; Object
0x180095cdc  mov     r8, [r8]; ObjectType
0x180095cdf  call    cs:__imp_ObReferenceObjectByHandle
0x180095ce6  nop     dword ptr [rax+rax+00h]
0x180095ceb  mov     r15, [rbp+140h+var_158]
0x180095cef  mov     ebx, eax
0x180095cf1  mov     [rbp+140h+var_1A0], r15
0x180095cf5  test    eax, eax
0x180095cf7  js      loc_180095B4A
0x180095cfd  xor     edx, edx
0x180095cff  mov     dword ptr [rbp+140h+var_1B0], r14d
0x180095d03  xor     cl, cl
0x180095d05  mov     dword ptr [rbp+140h+var_198+4], edx
0x180095d08  xor     r13b, r13b
0x180095d0b  mov     byte ptr [rbp+140h+var_1C0+1], cl
0x180095d0e  mov     [rbp+140h+var_178], rdx
0x180095d12  xor     eax, eax
0x180095d14  mov     [rbp+140h+var_1AC], eax
0x180095d17  cmp     eax, [rbp+140h+arg_28]
0x180095d1d  jnb     loc_18009611F
0x180095d23  lea     rcx, [rbp+140h+var_F8]
0x180095d27  call    MincryptFreePolicyInfo
0x180095d2c  cmp     dword ptr [rbp+140h+var_140], 0
0x180095d30  jz      short loc_180095D4F
0x180095d32  mov     rcx, qword ptr [rbp+140h+var_130]
0x180095d36  call    I_MincryptFreeChainInfo
0x180095d3b  xorps   xmm0, xmm0
0x180095d3e  movups  xmmword ptr [rbp+140h+var_140], xmm0
0x180095d42  movss   dword ptr [rbp+140h+var_140], xmm0
0x180095d47  movups  [rbp+140h+var_130], xmm0
0x180095d4b  movups  [rbp+140h+var_120], xmm0
0x180095d4f  xor     eax, eax
0x180095d51  cmp     dword ptr [rsi+4], 1
0x180095d55  mov     [rbp+140h+var_1B8], ax
0x180095d59  jnz     loc_180095E0C
0x180095d5f  cmp     byte ptr [rbp+140h+var_1C0+2], 1
0x180095d63  mov     eax, [rbp+140h+var_1AC]
0x180095d66  mov     rcx, [rbp+140h+var_150]
0x180095d6a  mov     rbx, [rcx+rax*8]
0x180095d6e  jnz     short loc_180095DBD
0x180095d70  mov     rcx, [rbp+140h+Handle]; Handle
0x180095d74  test    rcx, rcx
0x180095d77  jz      short loc_180095D8D
0x180095d79  call    cs:__imp_ZwClose
0x180095d80  nop     dword ptr [rax+rax+00h]
0x180095d85  mov     [rbp+140h+Handle], 0
0x180095d8d  xor     r9d, r9d
0x180095d90  lea     rax, [rbp+140h+Handle]
0x180095d94  mov     rcx, rbx
0x180095d97  mov     [rsp+240h+var_220], rax
0x180095d9c  lea     r8d, [r9+1]
0x180095da0  mov     dl, r8b
0x180095da3  call    cs:__imp_IoConvertFileHandleToKernelHandle
0x180095daa  nop     dword ptr [rax+rax+00h]
0x180095daf  mov     ebx, eax
0x180095db1  test    eax, eax
0x180095db3  js      loc_180095B4A
0x180095db9  mov     rbx, [rbp+140h+Handle]
0x180095dbd  mov     r8, cs:__imp_IoFileObjectType
0x180095dc4  lea     rax, [rbp+140h+var_148]
0x180095dc8  xor     r9d, r9d; AccessMode
0x180095dcb  mov     [rsp+240h+HandleInformation], 0; HandleInformation
0x180095dd4  mov     rcx, rbx; Handle
0x180095dd7  mov     [rbp+140h+var_148], 0
0x180095ddf  mov     [rsp+240h+var_220], rax; Object
0x180095de4  mov     r8, [r8]; ObjectType
0x180095de7  lea     edx, [r9+1]; DesiredAccess
0x180095deb  call    cs:__imp_ObReferenceObjectByHandle
0x180095df2  nop     dword ptr [rax+rax+00h]
0x180095df7  mov     ebx, eax
0x180095df9  mov     rax, [rbp+140h+var_148]
0x180095dfd  mov     [rbp+140h+Object], rax
0x180095e01  test    ebx, ebx
0x180095e03  js      loc_180095B4A
0x180095e09  mov     r15, rax
0x180095e0c  cmp     dword ptr [rsi+0Ch], 0
0x180095e10  jnz     short loc_180095E67
  ... truncated ...
```
