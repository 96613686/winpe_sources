# CipGetFileCache

- ea: `0x18008fa34`
- end: `0x1800902c7`
- name: `CipGetFileCache`
- size: `2195`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005986c`
- `0x180060af4`
- `0x18008f7cc`
- `0x1800a8a90`
- `0x1800c77d0`

## callees

- `0x1800100a4`
- `0x18002c0d0`
- `0x18002c200`
- `0x180057134`
- `0x18005a40c`
- `0x180060c60`
- `0x18008fa34`
- `0x1800902d0`
- `0x180090588`
- `0x180090654`
- `0x180090ad0`
- `0x1800912c0`
- `0x180091eb8`
- `0x1800a0780`
- `0x1800a0af0`
- `0x1800a4538`
- `0x1800d399c`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x180090225`
- `ntoskrnl!FsRtlGetFileSize` at `0x180090225`
- `ntoskrnl!ObfDereferenceObject` at `0x1800902a8`
- `ntoskrnl!ObfDereferenceObject` at `0x1800902a8`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180090013`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x180090013`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x18008fc3f`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x18008fc3f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18008fbae`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18008fbae`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18008fc81`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18008fc81`

## string_xrefs

- `0x18008fbeb`: `$Kernel.Purge.ESBCache`
- `0x18008ffe6`: `$Kernel.Purge.CIpCache`

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
0x18008fa34  push    rbp
0x18008fa36  push    rbx
0x18008fa37  push    rsi
0x18008fa38  push    rdi
0x18008fa39  push    r12
0x18008fa3b  push    r13
0x18008fa3d  push    r14
0x18008fa3f  push    r15
0x18008fa41  lea     rbp, [rsp-68h]
0x18008fa46  sub     rsp, 168h
0x18008fa4d  mov     rax, cs:__security_cookie
0x18008fa54  xor     rax, rsp
0x18008fa57  mov     [rbp+0A0h+var_50], rax
0x18008fa5b  mov     rax, [rbp+0A0h+arg_80]
0x18008fa62  xorps   xmm0, xmm0
0x18008fa65  mov     r14, [rbp+0A0h+arg_20]
0x18008fa6c  mov     r15, rcx
0x18008fa6f  mov     r12, [rbp+0A0h+arg_68]
0x18008fa76  mov     rsi, r9
0x18008fa79  mov     [rbp+0A0h+var_A8], rax
0x18008fa7d  mov     rax, [rbp+0A0h+arg_28]
0x18008fa84  mov     [rbp+0A0h+var_F0], rax
0x18008fa88  mov     rax, [rbp+0A0h+arg_30]
0x18008fa8f  mov     [rbp+0A0h+var_D0], rax
0x18008fa93  mov     rax, [rbp+0A0h+arg_38]
0x18008fa9a  mov     [rbp+0A0h+var_C8], rax
0x18008fa9e  mov     rax, [rbp+0A0h+arg_40]
0x18008faa5  mov     [rbp+0A0h+var_E8], rax
0x18008faa9  mov     rax, [rbp+0A0h+arg_48]
0x18008fab0  mov     [rbp+0A0h+var_E0], rax
0x18008fab4  mov     rax, [rbp+0A0h+arg_50]
0x18008fabb  mov     [rbp+0A0h+var_100], rax
0x18008fabf  mov     rax, [rbp+0A0h+arg_58]
0x18008fac6  mov     [rbp+0A0h+var_120], rax
0x18008faca  mov     rax, [rbp+0A0h+arg_70]
0x18008fad1  mov     [rbp+0A0h+var_B8], rax
0x18008fad5  mov     rax, [rbp+0A0h+arg_78]
0x18008fadc  mov     [rbp+0A0h+FileObject], rcx
0x18008fae0  mov     rcx, [rbp+0A0h+arg_60]
0x18008fae7  mov     [rbp+0A0h+var_B0], rax
0x18008faeb  xor     eax, eax
0x18008faed  mov     byte ptr [rsp+1A0h+var_14F], dl
0x18008faf1  mov     edi, eax
0x18008faf3  mov     [rbp+0A0h+var_C0], rcx
0x18008faf7  lea     rdx, CiGetFileCacheStart
0x18008fafe  lea     rcx, [r15+58h]
0x18008fb02  mov     [rbp+0A0h+var_110], eax
0x18008fb05  mov     qword ptr [rbp+0A0h+var_118], rax
0x18008fb09  mov     ebx, eax
0x18008fb0b  mov     [rsp+1A0h+var_128], eax
0x18008fb0f  mov     r13b, al
0x18008fb12  mov     [rsp+1A0h+var_140], eax
0x18008fb16  mov     [rsp+1A0h+var_150], al
0x18008fb1a  mov     [rsp+1A0h+var_12C], eax
0x18008fb1e  mov     byte ptr [rsp+1A0h+var_14F+1], al
0x18008fb22  mov     [rbp+0A0h+Object], rax
0x18008fb26  mov     qword ptr [rbp+0A0h+FileSize], rax
0x18008fb2a  mov     [rsp+1A0h+var_148], rax
0x18008fb2f  mov     [rsp+1A0h+var_130], r8d
0x18008fb34  mov     [rsp+1A0h+var_138], r14
0x18008fb39  movups  xmmword ptr [rbp+0A0h+var_A0], xmm0
0x18008fb3d  movups  [rbp+0A0h+var_90], xmm0
0x18008fb41  movups  [rbp+0A0h+var_80], xmm0
0x18008fb45  movups  [rbp+0A0h+var_70], xmm0
0x18008fb49  movups  [rbp+0A0h+var_60], xmm0
0x18008fb4d  call    CiLogFileEvent
0x18008fb52  mov     dword ptr [rsi], 1
0x18008fb58  test    r12, r12
0x18008fb5b  jnz     loc_18008FD82
0x18008fb61  mov     rax, [r15+8]
0x18008fb65  mov     edx, 100h
0x18008fb6a  test    [rax+30h], edx
0x18008fb6d  jz      loc_18008FE27
0x18008fb73  mov     rax, [r15+8]
0x18008fb77  mov     qword ptr [rsp+1A0h+var_140], 0
0x18008fb80  test    [rax+30h], edx
0x18008fb83  jz      loc_18008FDCA
0x18008fb89  lea     r8, [rbp+0A0h+Object]
0x18008fb8d  mov     rcx, r15
0x18008fb90  lea     rdx, [rsp+1A0h+var_14F+1]
0x18008fb95  xor     r14d, r14d
0x18008fb98  call    CipIsCimBackedFile
0x18008fb9d  mov     edi, eax
0x18008fb9f  test    eax, eax
0x18008fba1  js      loc_18008FFD0
0x18008fba7  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18008fbae  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18008fbb5  nop     dword ptr [rax+rax+00h]
0x18008fbba  xor     edi, edi
0x18008fbbc  mov     qword ptr [rsp+1A0h+var_140], rax
0x18008fbc1  mov     rbx, rax
0x18008fbc4  test    rax, rax
0x18008fbc7  jz      loc_18008FD8B
0x18008fbcd  mov     al, byte ptr [rsp+1A0h+var_14F+1]
0x18008fbd1  mov     byte ptr [rbp+0A0h+var_70+4], 16h
0x18008fbd5  mov     dword ptr [rbp+0A0h+var_70], edi
0x18008fbd8  cmp     byte ptr [rsp+1A0h+var_14F], dil
0x18008fbdd  jnz     loc_18008FFDE
0x18008fbe3  movsd   xmm1, qword ptr cs:aKernelPurgeEsb+0Fh; "SBCache"
0x18008fbeb  movups  xmm0, xmmword ptr cs:aKernelPurgeEsb; "$Kernel.Purge.ESBCache"
0x18008fbf2  movups  [rbp+0A0h+var_70+5], xmm0
0x18008fbf6  movsd   qword ptr [rbp+0A0h+var_60+4], xmm1
0x18008fbfb  test    al, al
0x18008fbfd  jz      short loc_18008FC03
0x18008fbff  mov     r15, [rbp+0A0h+Object]
0x18008fc03  test    r13b, r13b
0x18008fc06  jnz     loc_180090003
0x18008fc0c  lea     rax, [rbp+0A0h+var_110]
0x18008fc10  xor     r9d, r9d
0x18008fc13  mov     [rsp+1A0h+var_160], rax
0x18008fc18  mov     r8d, 1CCh
0x18008fc1e  mov     byte ptr [rsp+1A0h+var_168], 1
0x18008fc23  lea     rax, [rbp+0A0h+var_70]
0x18008fc27  mov     [rsp+1A0h+EventDescriptor], rdi
0x18008fc2c  mov     rdx, rbx
0x18008fc2f  mov     dword ptr [rsp+1A0h+var_178], 20h ; ' '
0x18008fc37  mov     rcx, r15
0x18008fc3a  mov     [rsp+1A0h+var_180], rax
0x18008fc3f  call    cs:__imp_FsRtlQueryKernelEaFile
0x18008fc46  nop     dword ptr [rax+rax+00h]
0x18008fc4b  mov     edi, eax
0x18008fc4d  test    eax, eax
0x18008fc4f  jns     loc_18008FCF1
0x18008fc55  mov     dword ptr [rsi], 2
0x18008fc5b  mov     r13, [rsp+1A0h+var_138]
0x18008fc60  mov     r12, [rsp+1A0h+var_148]
0x18008fc65  mov     rax, [rbp+0A0h+Object]
0x18008fc69  test    rax, rax
0x18008fc6c  jnz     loc_1800902A5
0x18008fc72  test    rbx, rbx
0x18008fc75  jz      short loc_18008FC8D
0x18008fc77  mov     rdx, rbx; Entry
0x18008fc7a  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18008fc81  call    cs:__imp_ExFreeToPagedLookasideList
0x18008fc88  nop     dword ptr [rax+rax+00h]
0x18008fc8d  test    r12, r12
0x18008fc90  jnz     loc_1800902B9
0x18008fc96  mov     ecx, [rsi]
0x18008fc98  test    edi, edi
0x18008fc9a  js      loc_18008FE05
0x18008fca0  mov     edx, [r13+0]; int
0x18008fca4  lea     rax, CiGetFileCacheComplete
0x18008fcab  mov     [rsp+1A0h+EventDescriptor], rax; EventDescriptor
0x18008fcb0  mov     r9d, r14d; int
0x18008fcb3  mov     rax, qword ptr [rbp+0A0h+var_118]
0x18008fcb7  mov     qword ptr [rsp+1A0h+var_178], rax; char
0x18008fcbc  mov     rax, [rbp+0A0h+var_F0]
0x18008fcc0  mov     r8b, [rax]; int
0x18008fcc3  mov     dword ptr [rsp+1A0h+var_180], ecx; char
0x18008fcc7  mov     ecx, edi; int
0x18008fcc9  call    CiLogCacheEvent
0x18008fcce  mov     eax, edi
0x18008fcd0  mov     rcx, [rbp+0A0h+var_50]
0x18008fcd4  xor     rcx, rsp; StackCookie
0x18008fcd7  call    __security_check_cookie
0x18008fcdc  add     rsp, 168h
0x18008fce3  pop     r15
0x18008fce5  pop     r14
0x18008fce7  pop     r13
0x18008fce9  pop     r12
0x18008fceb  pop     rdi
0x18008fcec  pop     rsi
0x18008fced  pop     rbx
0x18008fcee  pop     rbp
0x18008fcef  retn
0x18008fcf1  xor     r13b, r13b
0x18008fcf4  mov     [rsp+1A0h+var_150], r13b
0x18008fcf9  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x18008fcfe  test    eax, eax
0x18008fd00  jnz     loc_18008FD9B
0x18008fd06  mov     dl, byte ptr [rsp+1A0h+var_14F]; int
0x18008fd0a  lea     r9, [rbp+0A0h+var_118]; int
0x18008fd0e  mov     rcx, qword ptr [rsp+1A0h+var_140]; int
0x18008fd13  add     rbx, 238h
0x18008fd1a  mov     r8, rsi; int
0x18008fd1d  mov     [rsp+1A0h+var_180], rbx; void *
0x18008fd22  call    CipParseFileCache
0x18008fd27  mov     edi, eax
0x18008fd29  test    eax, eax
0x18008fd2b  js      short loc_18008FD78
0x18008fd2d  mov     r9d, [rsp+1A0h+var_130]
0x18008fd32  lea     rax, [rbp+0A0h+var_118]
0x18008fd36  mov     rdx, qword ptr [rsp+1A0h+var_140]
0x18008fd3b  mov     r8, r15
0x18008fd3e  mov     [rsp+1A0h+var_168], rax
0x18008fd43  mov     rcx, rbx
0x18008fd46  lea     rax, [rsp+1A0h+var_12C]
0x18008fd4b  mov     [rsp+1A0h+EventDescriptor], rsi
0x18008fd50  mov     qword ptr [rsp+1A0h+var_178], rax
0x18008fd55  mov     rax, [rbp+0A0h+var_120]
0x18008fd59  mov     [rsp+1A0h+var_180], rax
0x18008fd5e  call    CipVerifyFileCache
0x18008fd63  mov     edi, eax
0x18008fd65  test    eax, eax
0x18008fd67  jns     loc_18008FE71
0x18008fd6d  cmp     eax, 0C0000225h
0x18008fd72  jz      loc_180090061
0x18008fd78  mov     rbx, qword ptr [rsp+1A0h+var_140]
0x18008fd7d  jmp     loc_18008FC5B
0x18008fd82  mov     [r12], rbx
0x18008fd86  jmp     loc_18008FB61
0x18008fd8b  mov     dword ptr [rsi], 1Ch
0x18008fd91  mov     edi, 0C0000017h
0x18008fd96  jmp     loc_18008FC5B
0x18008fd9b  test    r12, r12
0x18008fd9e  jz      loc_18008FD06
0x18008fda4  mov     edx, [rsp+1A0h+var_130]
0x18008fda8  lea     r8, [rsp+1A0h+var_150]
0x18008fdad  mov     rcx, [rbp+0A0h+var_120]
0x18008fdb1  call    CipIsTrustedLaunch
0x18008fdb6  mov     edi, eax
0x18008fdb8  test    eax, eax
0x18008fdba  js      loc_180090037
0x18008fdc0  mov     r13b, [rsp+1A0h+var_150]
0x18008fdc5  jmp     loc_18008FD06
0x18008fdca  test    r13b, r13b
0x18008fdcd  jnz     loc_18008FB89
0x18008fdd3  test    cs:g_CiOptions, edx
0x18008fdd9  jnz     loc_18008FF68
0x18008fddf  bt      ebx, 11h
0x18008fde3  jb      loc_18008FF83
0x18008fde9  mov     eax, edi
0x18008fdeb  mov     edi, 0C00000BBh
0x18008fdf0  mov     ecx, ebx
0x18008fdf2  shl     rcx, 20h
0x18008fdf6  or      rcx, rax
0x18008fdf9  mov     dword ptr [rsi], 5
0x18008fdff  mov     qword ptr [rbp+0A0h+var_118], rcx
0x18008fe03  mov     ecx, [rsi]
0x18008fe05  lea     rax, CiGetFileCacheComplete
0x18008fe0c  xor     r9d, r9d
0x18008fe0f  mov     [rsp+1A0h+EventDescriptor], rax
0x18008fe14  xor     r8d, r8d
0x18008fe17  mov     rax, qword ptr [rbp+0A0h+var_118]
0x18008fe1b  xor     edx, edx
0x18008fe1d  mov     qword ptr [rsp+1A0h+var_178], rax
0x18008fe22  jmp     loc_18008FCC3
0x18008fe27  lea     rdx, [rsp+1A0h+var_128]
0x18008fe2c  mov     rcx, r15
0x18008fe2f  call    CipGetFileAttributes
0x18008fe34  mov     edi, eax
0x18008fe36  test    eax, eax
0x18008fe38  js      loc_18008FF52
0x18008fe3e  lea     r8, [rsp+1A0h+var_150]
0x18008fe43  mov     rcx, r15; FileObject
0x18008fe46  lea     rdx, [rsp+1A0h+var_140]
0x18008fe4b  call    CipGetVolumeFlags
0x18008fe50  mov     edi, eax
0x18008fe52  test    eax, eax
0x18008fe54  js      loc_18008FF5D
0x18008fe5a  mov     edi, [rsp+1A0h+var_128]
0x18008fe5e  mov     edx, 100h
0x18008fe63  mov     ebx, [rsp+1A0h+var_140]
0x18008fe67  mov     r13b, [rsp+1A0h+var_150]
0x18008fe6c  jmp     loc_18008FB73
0x18008fe71  mov     rax, [rbx]
0x18008fe74  mov     ecx, [rax+18h]
0x18008fe77  test    cl, 10h
0x18008fe7a  jnz     loc_180090042
0x18008fe80  mov     r15, [rbp+0A0h+FileObject]
0x18008fe84  mov     eax, cs:g_CiPolicyState
0x18008fe8a  mov     ecx, [rsp+1A0h+var_130]
0x18008fe8e  bt      eax, 0Fh
0x18008fe92  jb      loc_180090104
0x18008fe98  test    r13b, r13b
0x18008fe9b  jnz     loc_180090124
0x18008fea1  mov     r9, [rbp+0A0h+var_C8]
0x18008fea5  test    r9, r9
0x18008fea8  jnz     loc_180090141
0x18008feae  mov     rcx, [rbp+0A0h+var_C0]
0x18008feb2  test    rcx, rcx
0x18008feb5  jnz     loc_1800901AA
0x18008febb  mov     rcx, [rbp+0A0h+var_B8]
0x18008febf  test    rcx, rcx
0x18008fec2  jnz     loc_1800901CF
0x18008fec8  mov     rcx, [rbp+0A0h+var_B0]
0x18008fecc  test    rcx, rcx
0x18008fecf  jnz     loc_1800901DB
0x18008fed5  mov     r14, [rbp+0A0h+var_A8]
0x18008fed9  test    r14, r14
0x18008fedc  jnz     loc_1800901E5
0x18008fee2  cmp     byte ptr [rsp+1A0h+var_14F+1], 0
0x18008fee7  mov     rax, [rbx]
0x18008feea  mov     r13, [rsp+1A0h+var_138]
0x18008feef  mov     cl, [rax+7]
0x18008fef2  mov     rax, [rbp+0A0h+var_F0]
0x18008fef6  mov     [rax], cl
0x18008fef8  mov     dword ptr [r13+0], 0
0x18008ff00  mov     rax, [rbx]
0x18008ff03  mov     r14d, [rax+18h]
0x18008ff07  jnz     loc_180090213
0x18008ff0d  mov     r12, [rsp+1A0h+var_148]
0x18008ff12  or      r14d, [rsp+1A0h+var_12C]
0x18008ff17  mov     rax, [rbp+0A0h+var_D0]
0x18008ff1b  mov     rbx, qword ptr [rsp+1A0h+var_140]
0x18008ff20  test    rax, rax
0x18008ff23  jz      loc_18008FC65
0x18008ff29  mov     [rax], r14d
0x18008ff2c  jmp     loc_18008FC65
0x18008ff31  mov     rbx, qword ptr [rbp+0A0h+FileSize]
  ... truncated ...
```
