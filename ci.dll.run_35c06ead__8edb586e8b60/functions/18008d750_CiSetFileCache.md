# CiSetFileCache

- ea: `0x18008d750`
- end: `0x18008e090`
- name: `CiSetFileCache`
- size: `2368`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, HANDLE, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18002c0d0`
- `0x18002c1b0`
- `0x18005986c`
- `0x18005a398`
- `0x180060af4`
- `0x180073034`
- `0x18008c95c`
- `0x18008cd10`
- `0x18008d750`
- `0x18008eda4`
- `0x18008eddc`
- `0x18008f2f4`
- `0x18008f724`
- `0x18009df48`
- `0x18009e9b0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18008d833`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18008d89a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18008d833`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18008d89a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18008d848`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18008d848`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18008d866`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18008d866`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18008d953`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18008d953`
- `ntoskrnl!PsGetCurrentProcess` at `0x18008df70`
- `ntoskrnl!PsGetCurrentProcess` at `0x18008df70`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18008d8af`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x18008d8af`
- `ntoskrnl!ZwClose` at `0x18008d9a9`
- `ntoskrnl!ZwClose` at `0x18008d9be`
- `ntoskrnl!ZwClose` at `0x18008db79`
- `ntoskrnl!ZwClose` at `0x18008d9a9`
- `ntoskrnl!ZwClose` at `0x18008d9be`
- `ntoskrnl!ZwClose` at `0x18008db79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008d872`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008d95f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008d872`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008d95f`
- `ntoskrnl!ObfDereferenceObject` at `0x18008d980`
- `ntoskrnl!ObfDereferenceObject` at `0x18008d994`
- `ntoskrnl!ObfDereferenceObject` at `0x18008dec9`
- `ntoskrnl!ObfDereferenceObject` at `0x18008d980`
- `ntoskrnl!ObfDereferenceObject` at `0x18008d994`
- `ntoskrnl!ObfDereferenceObject` at `0x18008dec9`
- `ntoskrnl!IoFileObjectType` at `0x18008daba`
- `ntoskrnl!IoFileObjectType` at `0x18008dbbd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18008dadf`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18008dbeb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18008dadf`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18008dbeb`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x18008daa0`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x18008dba3`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x18008daa0`
- `ntoskrnl!IoConvertFileHandleToKernelHandle` at `0x18008dba3`

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
  int v47; // [rsp+48h] [rbp-B8h]
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
  if ( g_CiIsWinPE && !byte_180049980 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&g_CipPolicyLock, 0);
    FileCache2 = CipLoadAndValidateRevocationList(0);
    ExReleasePushLockExclusiveEx(&g_CipPolicyLock, 0);
    KeLeaveCriticalRegion();
    if ( FileCache2 < 0 )
      return (unsigned int)FileCache2;
    v9 = v49;
    byte_180049980 = 1;
  }
  Object = 0;
  v14 = 0;
  v15 = v10 & 7;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&g_CipPolicyLock, 0);
  v18 = (int *)qword_180031E30;
  do
  {
    if ( v15 == *v18 )
      break;
    v18 += 5;
  }
  while ( v18 != &dword_180031E6C );
  if ( v18 == &dword_180031E6C )
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
    v24 = (*((__int64 (__fastcall **)(__int64, __int64, __int64, __int64))&xmmword_18004A650 + 1))(v23, v16, v17, 2);
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
        v36 = *((_DWORD *)v11 + 592);
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
            v38 = *(_OWORD *)(v11 + 3356);
            v61 = *((_DWORD *)v11 + 524);
            if ( v61 >= 0 )
              v37 = (__int128 *)v65;
            v83 = v38;
            v65 = (__int64)v37;
            v84 = *(_OWORD *)(v11 + 3372);
            v85 = *(_QWORD *)(v11 + 3388);
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
    ActionsForImage = CiGetActionsForImage(CurrentProcess, (__int64)v14, 0, 0, v22);
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
0x18008d750  mov     [rsp-8+arg_8], rbx
0x18008d755  push    rbp
0x18008d756  push    rsi
0x18008d757  push    rdi
0x18008d758  push    r12
0x18008d75a  push    r13
0x18008d75c  push    r14
0x18008d75e  push    r15
0x18008d760  lea     rbp, [rsp-110h]
0x18008d768  sub     rsp, 210h
0x18008d76f  mov     rax, cs:__security_cookie
0x18008d776  xor     rax, rsp
0x18008d779  mov     [rbp+140h+var_40], rax
0x18008d780  mov     rax, [rbp+140h+arg_20]
0x18008d787  xor     esi, esi
0x18008d789  mov     r13, [rbp+140h+arg_30]
0x18008d790  xorps   xmm0, xmm0
0x18008d793  xorps   xmm1, xmm1
0x18008d796  mov     [rbp+140h+var_150], rax
0x18008d79a  mov     rax, [rbp+140h+arg_38]
0x18008d7a1  mov     bl, r9b
0x18008d7a4  mov     [rbp+140h+var_110], rax
0x18008d7a8  mov     edi, ecx
0x18008d7aa  xor     eax, eax
0x18008d7ac  mov     byte ptr [rbp+140h+var_1C0+1], bl
0x18008d7af  cmp     cs:g_CiIsWinPE, sil
0x18008d7b6  mov     r14d, esi
0x18008d7b9  movzx   r12d, r8b
0x18008d7bd  mov     byte ptr [rbp+140h+var_1C0+2], dl
0x18008d7c0  mov     [rbp+140h+var_168], ecx
0x18008d7c3  mov     byte ptr [rbp+140h+var_1C0], sil
0x18008d7c7  movups  xmmword ptr [rbp+140h+var_140], xmm0
0x18008d7cb  mov     dword ptr [rbp+140h+var_198], 40h ; '@'
0x18008d7d2  movups  [rbp+140h+var_130], xmm0
0x18008d7d6  mov     dword ptr [rbp+140h+var_190], esi
0x18008d7d9  movups  [rbp+140h+var_120], xmm0
0x18008d7dd  mov     [rbp+140h+var_C8], rax
0x18008d7e1  movups  [rbp+140h+var_108], xmm0
0x18008d7e5  mov     byte ptr [rbp+140h+var_1C0+4], sil
0x18008d7e9  movups  xmmword ptr [rbp+140h+var_F8], xmm1
0x18008d7ed  mov     [rbp+140h+var_1B4], sil
0x18008d7f1  movups  [rbp+140h+var_E8], xmm1
0x18008d7f5  mov     [rbp+140h+Entry], rsi
0x18008d7f9  movups  [rbp+140h+var_D8], xmm1
0x18008d7fd  mov     [rbp+140h+var_C0], rax
0x18008d804  mov     [rbp+140h+var_B8], eax
0x18008d80a  mov     [rbp+140h+Handle], rsi
0x18008d80e  mov     [rbp+140h+var_160], rsi
0x18008d812  movups  [rbp+140h+var_B0], xmm0
0x18008d819  mov     [rbp+140h+var_90], rax
0x18008d820  movups  [rbp+140h+var_A0], xmm0
0x18008d827  jz      short loc_18008D890
0x18008d829  mov     al, cs:byte_180049980
0x18008d82f  test    al, al
0x18008d831  jnz     short loc_18008D890
0x18008d833  call    cs:__imp_KeEnterCriticalRegion
0x18008d83a  nop     dword ptr [rax+rax+00h]
0x18008d83f  xor     edx, edx
0x18008d841  lea     rcx, g_CipPolicyLock
0x18008d848  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18008d84f  nop     dword ptr [rax+rax+00h]
0x18008d854  xor     ecx, ecx
0x18008d856  call    CipLoadAndValidateRevocationList
0x18008d85b  xor     edx, edx
0x18008d85d  lea     rcx, g_CipPolicyLock
0x18008d864  mov     ebx, eax
0x18008d866  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18008d86d  nop     dword ptr [rax+rax+00h]
0x18008d872  call    cs:__imp_KeLeaveCriticalRegion
0x18008d879  nop     dword ptr [rax+rax+00h]
0x18008d87e  test    ebx, ebx
0x18008d880  js      loc_18008D9E6
0x18008d886  mov     bl, byte ptr [rbp+140h+var_1C0+1]
0x18008d889  mov     cs:byte_180049980, 1
0x18008d890  mov     [rbp+140h+Object], rsi
0x18008d894  mov     r15, rsi
0x18008d897  and     edi, 7
0x18008d89a  call    cs:__imp_KeEnterCriticalRegion
0x18008d8a1  nop     dword ptr [rax+rax+00h]
0x18008d8a6  xor     edx, edx
0x18008d8a8  lea     rcx, g_CipPolicyLock
0x18008d8af  call    cs:__imp_ExAcquirePushLockSharedEx
0x18008d8b6  nop     dword ptr [rax+rax+00h]
0x18008d8bb  lea     rax, dword_180031E6C
0x18008d8c2  lea     rsi, qword_180031E30
0x18008d8c9  cmp     edi, [rsi]
0x18008d8cb  jz      short loc_18008D8D6
0x18008d8cd  add     rsi, 14h
0x18008d8d1  cmp     rsi, rax
0x18008d8d4  jnz     short loc_18008D8C9
0x18008d8d6  cmp     rsi, rax
0x18008d8d9  jnz     short loc_18008D8E2
0x18008d8db  mov     ebx, 0C00000BBh
0x18008d8e0  jmp     short loc_18008D94A
0x18008d8e2  cmp     [rsi+4], r14d
0x18008d8e6  jnz     short loc_18008D90B
0x18008d8e8  cmp     [rbp+140h+arg_28], 1
0x18008d8ef  jnz     short loc_18008D904
0x18008d8f1  mov     rax, [rbp+140h+var_150]
0x18008d8f5  cmp     r13, [rax]
0x18008d8f8  jnz     short loc_18008D904
0x18008d8fa  cmp     byte ptr [rbp+140h+var_1C0+2], 1
0x18008d8fe  setz    r15b
0x18008d902  jmp     short loc_18008D911
0x18008d904  mov     ebx, 0C000000Dh
0x18008d909  jmp     short loc_18008D94A
0x18008d90b  mov     r15d, 1
0x18008d911  mov     ecx, [rsi+8]
0x18008d914  mov     r8b, bl
0x18008d917  mov     [rbp+140h+var_1A8], r8d
0x18008d91b  mov     r9d, 2
0x18008d921  test    ecx, ecx
0x18008d923  jnz     loc_18008DA19
0x18008d929  mov     rax, cs:g_CipWhichLevelComparisons
0x18008d930  mov     edx, r12d
0x18008d933  and     edx, 0Fh
0x18008d936  mov     ecx, [rax+20h]
0x18008d939  bt      ecx, edx
0x18008d93c  jnb     loc_18008DA13
0x18008d942  mov     ebx, 0C000000Dh
0x18008d947  mov     r15, r14
0x18008d94a  xor     edx, edx
0x18008d94c  lea     rcx, g_CipPolicyLock
0x18008d953  call    cs:__imp_ExReleasePushLockSharedEx
0x18008d95a  nop     dword ptr [rax+rax+00h]
0x18008d95f  call    cs:__imp_KeLeaveCriticalRegion
0x18008d966  nop     dword ptr [rax+rax+00h]
0x18008d96b  lea     rcx, [rbp+140h+var_F8]
0x18008d96f  call    MincryptFreePolicyInfo
0x18008d974  mov     rax, [rbp+140h+Object]
0x18008d978  test    rax, rax
0x18008d97b  jz      short loc_18008D98C
0x18008d97d  mov     rcx, rax; Object
0x18008d980  call    cs:__imp_ObfDereferenceObject
0x18008d987  nop     dword ptr [rax+rax+00h]
0x18008d98c  test    r15, r15
0x18008d98f  jz      short loc_18008D9A0
0x18008d991  mov     rcx, r15; Object
0x18008d994  call    cs:__imp_ObfDereferenceObject
0x18008d99b  nop     dword ptr [rax+rax+00h]
0x18008d9a0  mov     rcx, [rbp+140h+Handle]; Handle
0x18008d9a4  test    rcx, rcx
0x18008d9a7  jz      short loc_18008D9B5
0x18008d9a9  call    cs:__imp_ZwClose
0x18008d9b0  nop     dword ptr [rax+rax+00h]
0x18008d9b5  mov     rcx, [rbp+140h+var_160]; Handle
0x18008d9b9  test    rcx, rcx
0x18008d9bc  jz      short loc_18008D9CA
0x18008d9be  call    cs:__imp_ZwClose
0x18008d9c5  nop     dword ptr [rax+rax+00h]
0x18008d9ca  cmp     dword ptr [rbp+140h+var_140], 0
0x18008d9ce  jz      short loc_18008D9D9
0x18008d9d0  mov     rcx, qword ptr [rbp+140h+var_130]
0x18008d9d4  call    I_MincryptFreeChainInfo
0x18008d9d9  test    r14, r14
0x18008d9dc  jz      short loc_18008D9E6
0x18008d9de  mov     rcx, r14; Entry
0x18008d9e1  call    CiFreeValidationContext
0x18008d9e6  mov     eax, ebx
0x18008d9e8  mov     rcx, [rbp+140h+var_40]
0x18008d9ef  xor     rcx, rsp; StackCookie
0x18008d9f2  call    __security_check_cookie
0x18008d9f7  mov     rbx, [rsp+240h+arg_8]
0x18008d9ff  add     rsp, 210h
0x18008da06  pop     r15
0x18008da08  pop     r14
0x18008da0a  pop     r13
0x18008da0c  pop     r12
0x18008da0e  pop     rdi
0x18008da0f  pop     rsi
0x18008da10  pop     rbp
0x18008da11  retn
0x18008da13  mov     byte ptr [rbp+140h+var_1C0+3], r12b
0x18008da17  jmp     short loc_18008DA3B
0x18008da19  mov     byte ptr [rbp+140h+var_1C0+3], r14b
0x18008da1d  cmp     ecx, r9d
0x18008da20  jnz     short loc_18008DA2C
0x18008da22  test    r12b, r12b
0x18008da25  jz      short loc_18008DA3B
0x18008da27  jmp     loc_18008D942
0x18008da2c  cmp     ecx, 1
0x18008da2f  movzx   r8d, r8b
0x18008da33  cmovz   r8d, r12d
0x18008da37  mov     [rbp+140h+var_1A8], r8d
0x18008da3b  cmp     [rsi+10h], r14d
0x18008da3f  mov     r12d, 0Fh
0x18008da45  movzx   eax, bl
0x18008da48  cmovnz  r12d, eax
0x18008da4c  movzx   ecx, r8b
0x18008da50  mov     rax, cs:g_CipWhichLevelComparisons
0x18008da57  and     ecx, 0Fh
0x18008da5a  mov     [rbp+140h+var_1B3], r12b
0x18008da5e  mov     ecx, [rax+rcx*4]
0x18008da61  test    r9b, cl
0x18008da64  jz      short loc_18008DA86
0x18008da66  mov     rax, qword ptr cs:xmmword_18004A650+8
0x18008da6d  call    _guard_dispatch_icall
0x18008da72  movzx   edx, byte ptr [rbp+140h+var_1A8]
0x18008da76  mov     r9d, 2
0x18008da7c  cmp     al, r9b
0x18008da7f  cmovz   edx, r9d
0x18008da83  mov     byte ptr [rbp+140h+var_1A8], dl
0x18008da86  cmp     byte ptr [rbp+140h+var_1C0+2], 1
0x18008da8a  jnz     short loc_18008DABA
0x18008da8c  lea     rax, [rbp+140h+var_160]
0x18008da90  xor     r9d, r9d
0x18008da93  mov     r8d, r15d
0x18008da96  mov     [rsp+240h+var_220], rax
0x18008da9b  mov     dl, 1
0x18008da9d  mov     rcx, r13
0x18008daa0  call    cs:__imp_IoConvertFileHandleToKernelHandle
0x18008daa7  nop     dword ptr [rax+rax+00h]
0x18008daac  mov     ebx, eax
0x18008daae  test    eax, eax
0x18008dab0  js      loc_18008D947
0x18008dab6  mov     r13, [rbp+140h+var_160]
0x18008daba  mov     r8, cs:__imp_IoFileObjectType
0x18008dac1  lea     rax, [rbp+140h+var_158]
0x18008dac5  mov     [rsp+240h+HandleInformation], r14; HandleInformation
0x18008daca  xor     r9d, r9d; AccessMode
0x18008dacd  mov     edx, r15d; DesiredAccess
0x18008dad0  mov     [rbp+140h+var_158], r14
0x18008dad4  mov     rcx, r13; Handle
0x18008dad7  mov     [rsp+240h+var_220], rax; Object
0x18008dadc  mov     r8, [r8]; ObjectType
0x18008dadf  call    cs:__imp_ObReferenceObjectByHandle
0x18008dae6  nop     dword ptr [rax+rax+00h]
0x18008daeb  mov     r15, [rbp+140h+var_158]
0x18008daef  mov     ebx, eax
0x18008daf1  mov     [rbp+140h+var_1A0], r15
0x18008daf5  test    eax, eax
0x18008daf7  js      loc_18008D94A
0x18008dafd  xor     edx, edx
0x18008daff  mov     dword ptr [rbp+140h+var_1B0], r14d
0x18008db03  xor     cl, cl
0x18008db05  mov     dword ptr [rbp+140h+var_198+4], edx
0x18008db08  xor     r13b, r13b
0x18008db0b  mov     byte ptr [rbp+140h+var_1C0+1], cl
0x18008db0e  mov     [rbp+140h+var_178], rdx
0x18008db12  xor     eax, eax
0x18008db14  mov     [rbp+140h+var_1AC], eax
0x18008db17  cmp     eax, [rbp+140h+arg_28]
0x18008db1d  jnb     loc_18008DF1F
0x18008db23  lea     rcx, [rbp+140h+var_F8]
0x18008db27  call    MincryptFreePolicyInfo
0x18008db2c  cmp     dword ptr [rbp+140h+var_140], 0
0x18008db30  jz      short loc_18008DB4F
0x18008db32  mov     rcx, qword ptr [rbp+140h+var_130]
0x18008db36  call    I_MincryptFreeChainInfo
0x18008db3b  xorps   xmm0, xmm0
0x18008db3e  movups  xmmword ptr [rbp+140h+var_140], xmm0
0x18008db42  movss   dword ptr [rbp+140h+var_140], xmm0
0x18008db47  movups  [rbp+140h+var_130], xmm0
0x18008db4b  movups  [rbp+140h+var_120], xmm0
0x18008db4f  xor     eax, eax
0x18008db51  cmp     dword ptr [rsi+4], 1
0x18008db55  mov     [rbp+140h+var_1B8], ax
0x18008db59  jnz     loc_18008DC0C
0x18008db5f  cmp     byte ptr [rbp+140h+var_1C0+2], 1
0x18008db63  mov     eax, [rbp+140h+var_1AC]
0x18008db66  mov     rcx, [rbp+140h+var_150]
0x18008db6a  mov     rbx, [rcx+rax*8]
0x18008db6e  jnz     short loc_18008DBBD
0x18008db70  mov     rcx, [rbp+140h+Handle]; Handle
0x18008db74  test    rcx, rcx
0x18008db77  jz      short loc_18008DB8D
0x18008db79  call    cs:__imp_ZwClose
0x18008db80  nop     dword ptr [rax+rax+00h]
0x18008db85  mov     [rbp+140h+Handle], 0
0x18008db8d  xor     r9d, r9d
0x18008db90  lea     rax, [rbp+140h+Handle]
0x18008db94  mov     rcx, rbx
0x18008db97  mov     [rsp+240h+var_220], rax
0x18008db9c  lea     r8d, [r9+1]
0x18008dba0  mov     dl, r8b
0x18008dba3  call    cs:__imp_IoConvertFileHandleToKernelHandle
0x18008dbaa  nop     dword ptr [rax+rax+00h]
0x18008dbaf  mov     ebx, eax
0x18008dbb1  test    eax, eax
0x18008dbb3  js      loc_18008D94A
0x18008dbb9  mov     rbx, [rbp+140h+Handle]
0x18008dbbd  mov     r8, cs:__imp_IoFileObjectType
0x18008dbc4  lea     rax, [rbp+140h+var_148]
0x18008dbc8  xor     r9d, r9d; AccessMode
0x18008dbcb  mov     [rsp+240h+HandleInformation], 0; HandleInformation
0x18008dbd4  mov     rcx, rbx; Handle
0x18008dbd7  mov     [rbp+140h+var_148], 0
0x18008dbdf  mov     [rsp+240h+var_220], rax; Object
0x18008dbe4  mov     r8, [r8]; ObjectType
0x18008dbe7  lea     edx, [r9+1]; DesiredAccess
0x18008dbeb  call    cs:__imp_ObReferenceObjectByHandle
0x18008dbf2  nop     dword ptr [rax+rax+00h]
0x18008dbf7  mov     ebx, eax
0x18008dbf9  mov     rax, [rbp+140h+var_148]
0x18008dbfd  mov     [rbp+140h+Object], rax
0x18008dc01  test    ebx, ebx
0x18008dc03  js      loc_18008D94A
0x18008dc09  mov     r15, rax
0x18008dc0c  cmp     dword ptr [rsi+0Ch], 0
0x18008dc10  jnz     short loc_18008DC67
  ... truncated ...
```
