# CipGetFileCache

- ea: `0x18009d178`
- end: `0x18009da0b`
- name: `CipGetFileCache`
- size: `2195`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180058c2c`
- `0x1800603a0`
- `0x18009cf10`
- `0x1800a82c0`
- `0x1800c6340`

## callees

- `0x180010128`
- `0x18002bef0`
- `0x18002c040`
- `0x180056134`
- `0x1800597cc`
- `0x18006050c`
- `0x180099e10`
- `0x18009a180`
- `0x18009bd64`
- `0x18009c8b0`
- `0x18009d178`
- `0x18009da14`
- `0x18009dccc`
- `0x18009dd98`
- `0x18009e214`
- `0x1800a2a68`
- `0x1800d24cc`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x18009d969`
- `ntoskrnl!FsRtlGetFileSize` at `0x18009d969`
- `ntoskrnl!ObfDereferenceObject` at `0x18009d9ec`
- `ntoskrnl!ObfDereferenceObject` at `0x18009d9ec`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18009d757`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18009d757`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x18009d383`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x18009d383`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009d2f2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009d2f2`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009d3c5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009d3c5`

## string_xrefs

- `0x18009d32f`: `$Kernel.Purge.ESBCache`
- `0x18009d72a`: `$Kernel.Purge.CIpCache`

## pseudocode

```c
__int64 __fastcall CipGetFileCache(
        PFILE_OBJECT FileObject,
        unsigned __int8 a2,
        unsigned int a3,
        int *a4,
        int *a5,
        _BYTE *a6,
        int *a7,
        void *a8,
        _DWORD *a9,
        _DWORD *a10,
        __int64 a11,
        __int64 a12,
        _QWORD *a13,
        _QWORD *a14,
        _WORD *a15,
        _DWORD *a16,
        __int64 a17)
{
  PFILE_OBJECT v17; // r15
  unsigned int v19; // edi
  unsigned int v20; // ebx
  char v21; // r13
  int v22; // r8d
  PDEVICE_OBJECT DeviceObject; // rax
  int v24; // r14d
  NTSTATUS FileAttributes; // edi
  char *v26; // rbx
  int *v27; // r13
  __int64 v28; // r12
  int v29; // ecx
  char v31; // r13
  int v32; // edx
  const void **v33; // rbx
  int v34; // eax
  __int64 v35; // rax
  int v36; // ecx
  struct _FILE_OBJECT *v37; // r15
  unsigned int v38; // ecx
  _QWORD *v39; // rcx
  _DWORD *v40; // r14
  bool v41; // zf
  DWORD LowPart; // ebx
  _DWORD *v43; // rax
  unsigned __int64 v44; // rax
  __int64 v45; // rcx
  unsigned int v46; // edx
  int ContextForReplay; // eax
  _DWORD *v48; // r12
  _DWORD *v49; // r13
  _DWORD *v50; // rax
  const void *v51; // rdx
  int FileOpenWithFlags; // eax
  __int64 v53; // r9
  int v54; // [rsp+20h] [rbp-E0h]
  char v55; // [rsp+50h] [rbp-B0h] BYREF
  int v56; // [rsp+51h] [rbp-AFh] BYREF
  __int64 v57; // [rsp+58h] [rbp-A8h] BYREF
  int v58[2]; // [rsp+60h] [rbp-A0h]
  int *v59; // [rsp+68h] [rbp-98h]
  unsigned int v60; // [rsp+70h] [rbp-90h]
  int v61; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v62; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h]
  char v64[8]; // [rsp+88h] [rbp-78h] BYREF
  int v65; // [rsp+90h] [rbp-70h] BYREF
  PFILE_OBJECT FileObjecta; // [rsp+98h] [rbp-68h]
  __int64 v67; // [rsp+A0h] [rbp-60h]
  PVOID Object; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE *v69; // [rsp+B0h] [rbp-50h]
  _DWORD *v70; // [rsp+B8h] [rbp-48h]
  _DWORD *v71; // [rsp+C0h] [rbp-40h]
  union _LARGE_INTEGER FileSize; // [rsp+C8h] [rbp-38h] BYREF
  int *v73; // [rsp+D0h] [rbp-30h]
  void *v74; // [rsp+D8h] [rbp-28h]
  _QWORD *v75; // [rsp+E0h] [rbp-20h]
  _WORD *v76; // [rsp+E8h] [rbp-18h]
  _DWORD *v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  void *v79[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v80; // [rsp+110h] [rbp+10h]
  __int128 v81; // [rsp+120h] [rbp+20h]
  _OWORD v82[2]; // [rsp+130h] [rbp+30h] BYREF

  v17 = FileObject;
  v78 = a17;
  v69 = a6;
  v73 = a7;
  v74 = a8;
  v70 = a9;
  v71 = a10;
  v67 = a11;
  v63 = a12;
  v76 = a15;
  FileObjecta = FileObject;
  v77 = a16;
  LOWORD(v56) = a2;
  v19 = 0;
  v75 = a13;
  v65 = 0;
  *(_QWORD *)v64 = 0;
  v20 = 0;
  v62 = 0;
  v21 = 0;
  v58[0] = 0;
  v55 = 0;
  v61 = 0;
  Object = 0;
  FileSize.QuadPart = 0;
  v57 = 0;
  v60 = a3;
  v59 = a5;
  *(_OWORD *)v79 = 0;
  v80 = 0;
  v81 = 0;
  memset(v82, 0, sizeof(v82));
  CiLogFileEvent(&FileObject->FileName, CiGetFileCacheStart);
  *a4 = 1;
  if ( a14 )
    *a14 = 0;
  if ( (v17->DeviceObject->Flags & 0x100) == 0 )
  {
    FileAttributes = CipGetFileAttributes(v17, &v62);
    if ( FileAttributes < 0 )
    {
      *a4 = 26;
      goto LABEL_37;
    }
    FileAttributes = CipGetVolumeFlags(v17);
    if ( FileAttributes < 0 )
    {
      *a4 = 27;
      goto LABEL_37;
    }
    v19 = v62;
    v20 = v58[0];
    v21 = v55;
  }
  DeviceObject = v17->DeviceObject;
  *(_QWORD *)v58 = 0;
  if ( (DeviceObject->Flags & 0x100) == 0
    && !v21
    && ((g_CiOptions & 0x100) == 0 || (v20 & 0x20000) != 0 && (v19 & 0x4000) != 0) )
  {
    if ( (v20 & 0x20000) != 0 && (v19 & 0x4000) != 0 )
    {
      *v69 = 6;
      v43 = v70;
      *a5 = 0;
      v24 = 512;
      if ( v43 )
        *v43 = 0;
      if ( v71 )
        *v71 = 0;
      v28 = v57;
      FileAttributes = 0;
      v27 = v59;
      goto LABEL_56;
    }
    v35 = v19;
    FileAttributes = -1073741637;
    *a4 = 5;
    *(_QWORD *)v64 = v35 | ((unsigned __int64)v20 << 32);
LABEL_37:
    v29 = *a4;
LABEL_38:
    CiLogCacheEvent(FileAttributes, 0, 0, 0, v29, v64[0], &CiGetFileCacheComplete);
    return (unsigned int)FileAttributes;
  }
  v24 = 0;
  FileAttributes = CipIsCimBackedFile(v17, (char *)&v56 + 1, &Object);
  if ( FileAttributes < 0 )
  {
    *a4 = 36;
    v26 = 0;
    goto LABEL_13;
  }
  *(_QWORD *)v58 = ExAllocateFromPagedLookasideList(&g_CiEaCacheLookasideList);
  v26 = *(char **)v58;
  if ( !*(_QWORD *)v58 )
  {
    *a4 = 28;
    FileAttributes = -1073741801;
    goto LABEL_13;
  }
  BYTE4(v82[0]) = 22;
  LODWORD(v82[0]) = 0;
  if ( !(_BYTE)v56 || BYTE1(v56) )
  {
    strcpy((char *)v82 + 5, "$Kernel.Purge.ESBCache");
    if ( BYTE1(v56) )
      v17 = (PFILE_OBJECT)Object;
  }
  else
  {
    strcpy((char *)v82 + 5, "$Kernel.Purge.CIpCache");
  }
  if ( v21 && (g_CiOptions & 0x100) == 0 && !(unsigned __int8)PsIsCurrentThreadInServerSilo() )
  {
    *a4 = 40;
    FileAttributes = -1073741275;
    goto LABEL_13;
  }
  FileAttributes = FsRtlQueryKernelEaFile(v17, v26, 460, 0, v82, 32, 0, 1, &v65);
  if ( FileAttributes < 0 )
  {
    *a4 = 2;
LABEL_13:
    v27 = v59;
LABEL_14:
    v28 = v57;
    goto LABEL_15;
  }
  v31 = 0;
  v55 = 0;
  if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() && a14 )
  {
    FileAttributes = CipIsTrustedLaunch(v63, v60, &v55);
    if ( FileAttributes < 0 )
    {
      *a4 = 38;
      goto LABEL_13;
    }
    v31 = v55;
  }
  LOBYTE(v32) = v56;
  v33 = (const void **)(v26 + 568);
  FileAttributes = CipParseFileCache(v58[0], v32, (int)a4, (int)v64, v33);
  if ( FileAttributes < 0 )
  {
LABEL_28:
    v26 = *(char **)v58;
    goto LABEL_13;
  }
  v34 = CipVerifyFileCache((_DWORD)v33, v58[0], (_DWORD)v17, v60, v63, (__int64)&v61, (__int64)a4, (__int64)v64);
  FileAttributes = v34;
  if ( v34 < 0 )
  {
    if ( v34 != -1073741275 )
      goto LABEL_28;
    goto LABEL_82;
  }
  v36 = *((_DWORD *)*v33 + 6);
  if ( (v36 & 0x10) != 0 && a14 )
  {
    if ( (v36 & 2) != 0 && *((_BYTE *)v33 + 12) )
    {
      *a4 = 33;
      FileAttributes = -1073741275;
LABEL_82:
      if ( !*((_BYTE *)v33 + 12) )
        goto LABEL_28;
      if ( !a14 )
        goto LABEL_28;
      v44 = (unsigned int)*a4;
      if ( (unsigned int)v44 > 0x21 )
        goto LABEL_28;
      v45 = 0x2A0409000LL;
      if ( !_bittest64(&v45, v44) )
        goto LABEL_28;
      v46 = v60;
      goto LABEL_87;
    }
    v37 = FileObjecta;
    LOBYTE(v56) = 0;
    if ( (int)CipHasPerAppRules((int)FileObjecta) >= 0 && !(_BYTE)v56 )
      *((_DWORD *)*v33 + 6) &= ~0x10u;
  }
  else
  {
    v37 = FileObjecta;
  }
  v38 = v60;
  if ( (g_CiPolicyState & 0x8000) == 0 || (v60 & 0x10) == 0 && (g_CiPolicyState & 0x200000) == 0 || !a14 )
  {
    if ( v31 )
    {
      *a4 = 39;
      goto LABEL_97;
    }
    if ( v74 )
    {
      v48 = v70;
      if ( v70 )
      {
        v49 = v71;
        if ( v71 )
        {
          if ( (*((_BYTE *)*v33 + 24) & 2) != 0 )
          {
            if ( *v70 >= (unsigned int)*((unsigned __int8 *)v33 + 28) )
            {
              memmove(v74, v33[4], *((unsigned __int8 *)v33 + 28));
            }
            else
            {
              *a4 = 23;
              FileAttributes = -1073741789;
            }
            *v48 = *((unsigned __int8 *)v33 + 28);
            *v49 = *((_DWORD *)v33 + 6);
            if ( FileAttributes < 0 )
              goto LABEL_28;
          }
        }
      }
    }
    v39 = v75;
    if ( v75 && (v61 & 0x4000) != 0 )
    {
      v50 = v33[8];
      *v75 = *(_QWORD *)v50;
      *((_DWORD *)v39 + 2) = v50[2];
    }
    if ( v76 )
      *v76 = *((_WORD *)v33 + 36);
    if ( v77 )
      *v77 = *((_DWORD *)v33 + 19);
    v40 = (_DWORD *)v78;
    if ( v78 )
    {
      v51 = v33[11];
      if ( v51 )
      {
        memmove((void *)(v78 + 8), v51, *((unsigned __int8 *)v33 + 84));
        v40[1] = *((unsigned __int8 *)v33 + 84);
        *v40 = *((_DWORD *)v33 + 20);
      }
    }
    v41 = BYTE1(v56) == 0;
    v27 = v59;
    *v69 = *((_BYTE *)*v33 + 7);
    *v27 = 0;
    v24 = *((_DWORD *)*v33 + 6);
    if ( v41 || !v73 )
    {
      v28 = v57;
    }
    else
    {
      FileAttributes = FsRtlGetFileSize(v37, &FileSize);
      if ( FileAttributes < 0 )
        goto LABEL_60;
      LowPart = FileSize.LowPart;
      if ( FileSize.QuadPart > 0xFFFFFFFFuLL )
      {
        FileAttributes = -1073741701;
LABEL_60:
        v26 = *(char **)v58;
        goto LABEL_14;
      }
      FileOpenWithFlags = CiReadFileOpenWithFlags(v37, 0, FileSize.LowPart, 1, v79, (__int64)&v57);
      v28 = v57;
      FileAttributes = FileOpenWithFlags;
      if ( FileOpenWithFlags < 0 )
      {
        v26 = *(char **)v58;
        goto LABEL_15;
      }
      LOBYTE(v53) = 1;
      LOBYTE(v54) = 0;
      if ( (int)CipMitigatePPLBypassThroughInterpreters(v37, v57, LowPart, v53, v54) < 0 )
        v24 &= ~0x40u;
      else
        v24 |= 0x40u;
    }
    v24 |= v61;
LABEL_56:
    v26 = *(char **)v58;
    if ( v73 )
      *v73 = v24;
    goto LABEL_15;
  }
  *a4 = 34;
LABEL_97:
  if ( !*((_BYTE *)v33 + 12) )
  {
    FileAttributes = -1073741275;
    goto LABEL_28;
  }
  v46 = v38;
LABEL_87:
  ContextForReplay = CipCreateContextForReplay((_DWORD)v33, v46, v67, v63, (__int64)a14);
  v26 = *(char **)v58;
  FileAttributes = ContextForReplay;
  v28 = v57;
  v27 = v59;
  if ( ContextForReplay >= 0 )
    FileAttributes = -1073741267;
LABEL_15:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( v26 )
    ExFreeToPagedLookasideList(&g_CiEaCacheLookasideList, v26);
  if ( v28 )
    CiReadFileClose(v79);
  v29 = *a4;
  if ( FileAttributes < 0 )
    goto LABEL_38;
  LOBYTE(v22) = *v69;
  CiLogCacheEvent(FileAttributes, *v27, v22, v24, v29, v64[0], &CiGetFileCacheComplete);
  return (unsigned int)FileAttributes;
}

```

## disassembly

```asm
0x18009d178  push    rbp
0x18009d17a  push    rbx
0x18009d17b  push    rsi
0x18009d17c  push    rdi
0x18009d17d  push    r12
0x18009d17f  push    r13
0x18009d181  push    r14
0x18009d183  push    r15
0x18009d185  lea     rbp, [rsp-68h]
0x18009d18a  sub     rsp, 168h
0x18009d191  mov     rax, cs:__security_cookie
0x18009d198  xor     rax, rsp
0x18009d19b  mov     [rbp+0A0h+var_50], rax
0x18009d19f  mov     rax, [rbp+0A0h+arg_80]
0x18009d1a6  xorps   xmm0, xmm0
0x18009d1a9  mov     r14, [rbp+0A0h+arg_20]
0x18009d1b0  mov     r15, rcx
0x18009d1b3  mov     r12, [rbp+0A0h+arg_68]
0x18009d1ba  mov     rsi, r9
0x18009d1bd  mov     [rbp+0A0h+var_A8], rax
0x18009d1c1  mov     rax, [rbp+0A0h+arg_28]
0x18009d1c8  mov     [rbp+0A0h+var_F0], rax
0x18009d1cc  mov     rax, [rbp+0A0h+arg_30]
0x18009d1d3  mov     [rbp+0A0h+var_D0], rax
0x18009d1d7  mov     rax, [rbp+0A0h+arg_38]
0x18009d1de  mov     [rbp+0A0h+var_C8], rax
0x18009d1e2  mov     rax, [rbp+0A0h+arg_40]
0x18009d1e9  mov     [rbp+0A0h+var_E8], rax
0x18009d1ed  mov     rax, [rbp+0A0h+arg_48]
0x18009d1f4  mov     [rbp+0A0h+var_E0], rax
0x18009d1f8  mov     rax, [rbp+0A0h+arg_50]
0x18009d1ff  mov     [rbp+0A0h+var_100], rax
0x18009d203  mov     rax, [rbp+0A0h+arg_58]
0x18009d20a  mov     [rbp+0A0h+var_120], rax
0x18009d20e  mov     rax, [rbp+0A0h+arg_70]
0x18009d215  mov     [rbp+0A0h+var_B8], rax
0x18009d219  mov     rax, [rbp+0A0h+arg_78]
0x18009d220  mov     [rbp+0A0h+FileObject], rcx
0x18009d224  mov     rcx, [rbp+0A0h+arg_60]
0x18009d22b  mov     [rbp+0A0h+var_B0], rax
0x18009d22f  xor     eax, eax
0x18009d231  mov     byte ptr [rsp+1A0h+var_14F], dl
0x18009d235  mov     edi, eax
0x18009d237  mov     [rbp+0A0h+var_C0], rcx
0x18009d23b  lea     rdx, CiGetFileCacheStart
0x18009d242  lea     rcx, [r15+58h]
0x18009d246  mov     [rbp+0A0h+var_110], eax
0x18009d249  mov     qword ptr [rbp+0A0h+var_118], rax
0x18009d24d  mov     ebx, eax
0x18009d24f  mov     [rsp+1A0h+var_128], eax
0x18009d253  mov     r13b, al
0x18009d256  mov     [rsp+1A0h+var_140], eax
0x18009d25a  mov     [rsp+1A0h+var_150], al
0x18009d25e  mov     [rsp+1A0h+var_12C], eax
0x18009d262  mov     byte ptr [rsp+1A0h+var_14F+1], al
0x18009d266  mov     [rbp+0A0h+Object], rax
0x18009d26a  mov     qword ptr [rbp+0A0h+FileSize], rax
0x18009d26e  mov     [rsp+1A0h+var_148], rax
0x18009d273  mov     [rsp+1A0h+var_130], r8d
0x18009d278  mov     [rsp+1A0h+var_138], r14
0x18009d27d  movups  xmmword ptr [rbp+0A0h+var_A0], xmm0
0x18009d281  movups  [rbp+0A0h+var_90], xmm0
0x18009d285  movups  [rbp+0A0h+var_80], xmm0
0x18009d289  movups  [rbp+0A0h+var_70], xmm0
0x18009d28d  movups  [rbp+0A0h+var_60], xmm0
0x18009d291  call    CiLogFileEvent
0x18009d296  mov     dword ptr [rsi], 1
0x18009d29c  test    r12, r12
0x18009d29f  jnz     loc_18009D4C6
0x18009d2a5  mov     rax, [r15+8]
0x18009d2a9  mov     edx, 100h
0x18009d2ae  test    [rax+30h], edx
0x18009d2b1  jz      loc_18009D56B
0x18009d2b7  mov     rax, [r15+8]
0x18009d2bb  mov     qword ptr [rsp+1A0h+var_140], 0
0x18009d2c4  test    [rax+30h], edx
0x18009d2c7  jz      loc_18009D50E
0x18009d2cd  lea     r8, [rbp+0A0h+Object]
0x18009d2d1  mov     rcx, r15
0x18009d2d4  lea     rdx, [rsp+1A0h+var_14F+1]
0x18009d2d9  xor     r14d, r14d
0x18009d2dc  call    CipIsCimBackedFile
0x18009d2e1  mov     edi, eax
0x18009d2e3  test    eax, eax
0x18009d2e5  js      loc_18009D714
0x18009d2eb  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18009d2f2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18009d2f9  nop     dword ptr [rax+rax+00h]
0x18009d2fe  xor     edi, edi
0x18009d300  mov     qword ptr [rsp+1A0h+var_140], rax
0x18009d305  mov     rbx, rax
0x18009d308  test    rax, rax
0x18009d30b  jz      loc_18009D4CF
0x18009d311  mov     al, byte ptr [rsp+1A0h+var_14F+1]
0x18009d315  mov     byte ptr [rbp+0A0h+var_70+4], 16h
0x18009d319  mov     dword ptr [rbp+0A0h+var_70], edi
0x18009d31c  cmp     byte ptr [rsp+1A0h+var_14F], dil
0x18009d321  jnz     loc_18009D722
0x18009d327  movsd   xmm1, qword ptr cs:aKernelPurgeEsb+0Fh; "SBCache"
0x18009d32f  movups  xmm0, xmmword ptr cs:aKernelPurgeEsb; "$Kernel.Purge.ESBCache"
0x18009d336  movups  [rbp+0A0h+var_70+5], xmm0
0x18009d33a  movsd   qword ptr [rbp+0A0h+var_60+4], xmm1
0x18009d33f  test    al, al
0x18009d341  jz      short loc_18009D347
0x18009d343  mov     r15, [rbp+0A0h+Object]
0x18009d347  test    r13b, r13b
0x18009d34a  jnz     loc_18009D747
0x18009d350  lea     rax, [rbp+0A0h+var_110]
0x18009d354  xor     r9d, r9d
0x18009d357  mov     [rsp+1A0h+var_160], rax
0x18009d35c  mov     r8d, 1CCh
0x18009d362  mov     byte ptr [rsp+1A0h+var_168], 1
0x18009d367  lea     rax, [rbp+0A0h+var_70]
0x18009d36b  mov     [rsp+1A0h+EventDescriptor], rdi
0x18009d370  mov     rdx, rbx
0x18009d373  mov     dword ptr [rsp+1A0h+var_178], 20h ; ' '
0x18009d37b  mov     rcx, r15
0x18009d37e  mov     [rsp+1A0h+var_180], rax
0x18009d383  call    cs:__imp_FsRtlQueryKernelEaFile
0x18009d38a  nop     dword ptr [rax+rax+00h]
0x18009d38f  mov     edi, eax
0x18009d391  test    eax, eax
0x18009d393  jns     loc_18009D435
0x18009d399  mov     dword ptr [rsi], 2
0x18009d39f  mov     r13, [rsp+1A0h+var_138]
0x18009d3a4  mov     r12, [rsp+1A0h+var_148]
0x18009d3a9  mov     rax, [rbp+0A0h+Object]
0x18009d3ad  test    rax, rax
0x18009d3b0  jnz     loc_18009D9E9
0x18009d3b6  test    rbx, rbx
0x18009d3b9  jz      short loc_18009D3D1
0x18009d3bb  mov     rdx, rbx; Entry
0x18009d3be  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18009d3c5  call    cs:__imp_ExFreeToPagedLookasideList
0x18009d3cc  nop     dword ptr [rax+rax+00h]
0x18009d3d1  test    r12, r12
0x18009d3d4  jnz     loc_18009D9FD
0x18009d3da  mov     ecx, [rsi]
0x18009d3dc  test    edi, edi
0x18009d3de  js      loc_18009D549
0x18009d3e4  mov     edx, [r13+0]; int
0x18009d3e8  lea     rax, CiGetFileCacheComplete
0x18009d3ef  mov     [rsp+1A0h+EventDescriptor], rax; EventDescriptor
0x18009d3f4  mov     r9d, r14d; int
0x18009d3f7  mov     rax, qword ptr [rbp+0A0h+var_118]
0x18009d3fb  mov     qword ptr [rsp+1A0h+var_178], rax; char
0x18009d400  mov     rax, [rbp+0A0h+var_F0]
0x18009d404  mov     r8b, [rax]; int
0x18009d407  mov     dword ptr [rsp+1A0h+var_180], ecx; char
0x18009d40b  mov     ecx, edi; int
0x18009d40d  call    CiLogCacheEvent
0x18009d412  mov     eax, edi
0x18009d414  mov     rcx, [rbp+0A0h+var_50]
0x18009d418  xor     rcx, rsp; StackCookie
0x18009d41b  call    __security_check_cookie
0x18009d420  add     rsp, 168h
0x18009d427  pop     r15
0x18009d429  pop     r14
0x18009d42b  pop     r13
0x18009d42d  pop     r12
0x18009d42f  pop     rdi
0x18009d430  pop     rsi
0x18009d431  pop     rbx
0x18009d432  pop     rbp
0x18009d433  retn
0x18009d435  xor     r13b, r13b
0x18009d438  mov     [rsp+1A0h+var_150], r13b
0x18009d43d  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x18009d442  test    eax, eax
0x18009d444  jnz     loc_18009D4DF
0x18009d44a  mov     dl, byte ptr [rsp+1A0h+var_14F]; int
0x18009d44e  lea     r9, [rbp+0A0h+var_118]; int
0x18009d452  mov     rcx, qword ptr [rsp+1A0h+var_140]; int
0x18009d457  add     rbx, 238h
0x18009d45e  mov     r8, rsi; int
0x18009d461  mov     [rsp+1A0h+var_180], rbx; void *
0x18009d466  call    CipParseFileCache
0x18009d46b  mov     edi, eax
0x18009d46d  test    eax, eax
0x18009d46f  js      short loc_18009D4BC
0x18009d471  mov     r9d, [rsp+1A0h+var_130]
0x18009d476  lea     rax, [rbp+0A0h+var_118]
0x18009d47a  mov     rdx, qword ptr [rsp+1A0h+var_140]
0x18009d47f  mov     r8, r15
0x18009d482  mov     [rsp+1A0h+var_168], rax
0x18009d487  mov     rcx, rbx
0x18009d48a  lea     rax, [rsp+1A0h+var_12C]
0x18009d48f  mov     [rsp+1A0h+EventDescriptor], rsi
0x18009d494  mov     qword ptr [rsp+1A0h+var_178], rax
0x18009d499  mov     rax, [rbp+0A0h+var_120]
0x18009d49d  mov     [rsp+1A0h+var_180], rax
0x18009d4a2  call    CipVerifyFileCache
0x18009d4a7  mov     edi, eax
0x18009d4a9  test    eax, eax
0x18009d4ab  jns     loc_18009D5B5
0x18009d4b1  cmp     eax, 0C0000225h
0x18009d4b6  jz      loc_18009D7A5
0x18009d4bc  mov     rbx, qword ptr [rsp+1A0h+var_140]
0x18009d4c1  jmp     loc_18009D39F
0x18009d4c6  mov     [r12], rbx
0x18009d4ca  jmp     loc_18009D2A5
0x18009d4cf  mov     dword ptr [rsi], 1Ch
0x18009d4d5  mov     edi, 0C0000017h
0x18009d4da  jmp     loc_18009D39F
0x18009d4df  test    r12, r12
0x18009d4e2  jz      loc_18009D44A
0x18009d4e8  mov     edx, [rsp+1A0h+var_130]
0x18009d4ec  lea     r8, [rsp+1A0h+var_150]
0x18009d4f1  mov     rcx, [rbp+0A0h+var_120]
0x18009d4f5  call    CipIsTrustedLaunch
0x18009d4fa  mov     edi, eax
0x18009d4fc  test    eax, eax
0x18009d4fe  js      loc_18009D77B
0x18009d504  mov     r13b, [rsp+1A0h+var_150]
0x18009d509  jmp     loc_18009D44A
0x18009d50e  test    r13b, r13b
0x18009d511  jnz     loc_18009D2CD
0x18009d517  test    cs:g_CiOptions, edx
0x18009d51d  jnz     loc_18009D6AC
0x18009d523  bt      ebx, 11h
0x18009d527  jb      loc_18009D6C7
0x18009d52d  mov     eax, edi
0x18009d52f  mov     edi, 0C00000BBh
0x18009d534  mov     ecx, ebx
0x18009d536  shl     rcx, 20h
0x18009d53a  or      rcx, rax
0x18009d53d  mov     dword ptr [rsi], 5
0x18009d543  mov     qword ptr [rbp+0A0h+var_118], rcx
0x18009d547  mov     ecx, [rsi]
0x18009d549  lea     rax, CiGetFileCacheComplete
0x18009d550  xor     r9d, r9d
0x18009d553  mov     [rsp+1A0h+EventDescriptor], rax
0x18009d558  xor     r8d, r8d
0x18009d55b  mov     rax, qword ptr [rbp+0A0h+var_118]
0x18009d55f  xor     edx, edx
0x18009d561  mov     qword ptr [rsp+1A0h+var_178], rax
0x18009d566  jmp     loc_18009D407
0x18009d56b  lea     rdx, [rsp+1A0h+var_128]
0x18009d570  mov     rcx, r15
0x18009d573  call    CipGetFileAttributes
0x18009d578  mov     edi, eax
0x18009d57a  test    eax, eax
0x18009d57c  js      loc_18009D696
0x18009d582  lea     r8, [rsp+1A0h+var_150]
0x18009d587  mov     rcx, r15; FileObject
0x18009d58a  lea     rdx, [rsp+1A0h+var_140]
0x18009d58f  call    CipGetVolumeFlags
0x18009d594  mov     edi, eax
0x18009d596  test    eax, eax
0x18009d598  js      loc_18009D6A1
0x18009d59e  mov     edi, [rsp+1A0h+var_128]
0x18009d5a2  mov     edx, 100h
0x18009d5a7  mov     ebx, [rsp+1A0h+var_140]
0x18009d5ab  mov     r13b, [rsp+1A0h+var_150]
0x18009d5b0  jmp     loc_18009D2B7
0x18009d5b5  mov     rax, [rbx]
0x18009d5b8  mov     ecx, [rax+18h]
0x18009d5bb  test    cl, 10h
0x18009d5be  jnz     loc_18009D786
0x18009d5c4  mov     r15, [rbp+0A0h+FileObject]
0x18009d5c8  mov     eax, cs:g_CiPolicyState
0x18009d5ce  mov     ecx, [rsp+1A0h+var_130]
0x18009d5d2  bt      eax, 0Fh
0x18009d5d6  jb      loc_18009D848
0x18009d5dc  test    r13b, r13b
0x18009d5df  jnz     loc_18009D868
0x18009d5e5  mov     r9, [rbp+0A0h+var_C8]
0x18009d5e9  test    r9, r9
0x18009d5ec  jnz     loc_18009D885
0x18009d5f2  mov     rcx, [rbp+0A0h+var_C0]
0x18009d5f6  test    rcx, rcx
0x18009d5f9  jnz     loc_18009D8EE
0x18009d5ff  mov     rcx, [rbp+0A0h+var_B8]
0x18009d603  test    rcx, rcx
0x18009d606  jnz     loc_18009D913
0x18009d60c  mov     rcx, [rbp+0A0h+var_B0]
0x18009d610  test    rcx, rcx
0x18009d613  jnz     loc_18009D91F
0x18009d619  mov     r14, [rbp+0A0h+var_A8]
0x18009d61d  test    r14, r14
0x18009d620  jnz     loc_18009D929
0x18009d626  cmp     byte ptr [rsp+1A0h+var_14F+1], 0
0x18009d62b  mov     rax, [rbx]
0x18009d62e  mov     r13, [rsp+1A0h+var_138]
0x18009d633  mov     cl, [rax+7]
0x18009d636  mov     rax, [rbp+0A0h+var_F0]
0x18009d63a  mov     [rax], cl
0x18009d63c  mov     dword ptr [r13+0], 0
0x18009d644  mov     rax, [rbx]
0x18009d647  mov     r14d, [rax+18h]
0x18009d64b  jnz     loc_18009D957
0x18009d651  mov     r12, [rsp+1A0h+var_148]
0x18009d656  or      r14d, [rsp+1A0h+var_12C]
0x18009d65b  mov     rax, [rbp+0A0h+var_D0]
0x18009d65f  mov     rbx, qword ptr [rsp+1A0h+var_140]
0x18009d664  test    rax, rax
0x18009d667  jz      loc_18009D3A9
0x18009d66d  mov     [rax], r14d
0x18009d670  jmp     loc_18009D3A9
0x18009d675  mov     rbx, qword ptr [rbp+0A0h+FileSize]
  ... truncated ...
```
