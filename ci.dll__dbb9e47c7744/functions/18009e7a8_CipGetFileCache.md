# CipGetFileCache

- ea: `0x18009e7a8`
- end: `0x18009f03b`
- name: `CipGetFileCache`
- size: `2195`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180059944`
- `0x180060b54`
- `0x18009e540`
- `0x1800a9740`
- `0x1800c77c0`

## callees

- `0x180010094`
- `0x18002bf20`
- `0x18002c080`
- `0x180057134`
- `0x18005a4e4`
- `0x180060cc0`
- `0x18009b440`
- `0x18009b7b0`
- `0x18009d394`
- `0x18009dee0`
- `0x18009e7a8`
- `0x18009f044`
- `0x18009f2fc`
- `0x18009f3c8`
- `0x18009f844`
- `0x1800a4098`
- `0x1800d398c`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x18009ef99`
- `ntoskrnl!FsRtlGetFileSize` at `0x18009ef99`
- `ntoskrnl!ObfDereferenceObject` at `0x18009f01c`
- `ntoskrnl!ObfDereferenceObject` at `0x18009f01c`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18009ed87`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18009ed87`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x18009e9b3`
- `ntoskrnl!FsRtlQueryKernelEaFile` at `0x18009e9b3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009e922`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009e922`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009e9f5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009e9f5`

## string_xrefs

- `0x18009e95f`: `$Kernel.Purge.ESBCache`
- `0x18009ed5a`: `$Kernel.Purge.CIpCache`

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
0x18009e7a8  push    rbp
0x18009e7aa  push    rbx
0x18009e7ab  push    rsi
0x18009e7ac  push    rdi
0x18009e7ad  push    r12
0x18009e7af  push    r13
0x18009e7b1  push    r14
0x18009e7b3  push    r15
0x18009e7b5  lea     rbp, [rsp-68h]
0x18009e7ba  sub     rsp, 168h
0x18009e7c1  mov     rax, cs:__security_cookie
0x18009e7c8  xor     rax, rsp
0x18009e7cb  mov     [rbp+0A0h+var_50], rax
0x18009e7cf  mov     rax, [rbp+0A0h+arg_80]
0x18009e7d6  xorps   xmm0, xmm0
0x18009e7d9  mov     r14, [rbp+0A0h+arg_20]
0x18009e7e0  mov     r15, rcx
0x18009e7e3  mov     r12, [rbp+0A0h+arg_68]
0x18009e7ea  mov     rsi, r9
0x18009e7ed  mov     [rbp+0A0h+var_A8], rax
0x18009e7f1  mov     rax, [rbp+0A0h+arg_28]
0x18009e7f8  mov     [rbp+0A0h+var_F0], rax
0x18009e7fc  mov     rax, [rbp+0A0h+arg_30]
0x18009e803  mov     [rbp+0A0h+var_D0], rax
0x18009e807  mov     rax, [rbp+0A0h+arg_38]
0x18009e80e  mov     [rbp+0A0h+var_C8], rax
0x18009e812  mov     rax, [rbp+0A0h+arg_40]
0x18009e819  mov     [rbp+0A0h+var_E8], rax
0x18009e81d  mov     rax, [rbp+0A0h+arg_48]
0x18009e824  mov     [rbp+0A0h+var_E0], rax
0x18009e828  mov     rax, [rbp+0A0h+arg_50]
0x18009e82f  mov     [rbp+0A0h+var_100], rax
0x18009e833  mov     rax, [rbp+0A0h+arg_58]
0x18009e83a  mov     [rbp+0A0h+var_120], rax
0x18009e83e  mov     rax, [rbp+0A0h+arg_70]
0x18009e845  mov     [rbp+0A0h+var_B8], rax
0x18009e849  mov     rax, [rbp+0A0h+arg_78]
0x18009e850  mov     [rbp+0A0h+FileObject], rcx
0x18009e854  mov     rcx, [rbp+0A0h+arg_60]
0x18009e85b  mov     [rbp+0A0h+var_B0], rax
0x18009e85f  xor     eax, eax
0x18009e861  mov     byte ptr [rsp+1A0h+var_14F], dl
0x18009e865  mov     edi, eax
0x18009e867  mov     [rbp+0A0h+var_C0], rcx
0x18009e86b  lea     rdx, CiGetFileCacheStart
0x18009e872  lea     rcx, [r15+58h]
0x18009e876  mov     [rbp+0A0h+var_110], eax
0x18009e879  mov     qword ptr [rbp+0A0h+var_118], rax
0x18009e87d  mov     ebx, eax
0x18009e87f  mov     [rsp+1A0h+var_128], eax
0x18009e883  mov     r13b, al
0x18009e886  mov     [rsp+1A0h+var_140], eax
0x18009e88a  mov     [rsp+1A0h+var_150], al
0x18009e88e  mov     [rsp+1A0h+var_12C], eax
0x18009e892  mov     byte ptr [rsp+1A0h+var_14F+1], al
0x18009e896  mov     [rbp+0A0h+Object], rax
0x18009e89a  mov     qword ptr [rbp+0A0h+FileSize], rax
0x18009e89e  mov     [rsp+1A0h+var_148], rax
0x18009e8a3  mov     [rsp+1A0h+var_130], r8d
0x18009e8a8  mov     [rsp+1A0h+var_138], r14
0x18009e8ad  movups  xmmword ptr [rbp+0A0h+var_A0], xmm0
0x18009e8b1  movups  [rbp+0A0h+var_90], xmm0
0x18009e8b5  movups  [rbp+0A0h+var_80], xmm0
0x18009e8b9  movups  [rbp+0A0h+var_70], xmm0
0x18009e8bd  movups  [rbp+0A0h+var_60], xmm0
0x18009e8c1  call    CiLogFileEvent
0x18009e8c6  mov     dword ptr [rsi], 1
0x18009e8cc  test    r12, r12
0x18009e8cf  jnz     loc_18009EAF6
0x18009e8d5  mov     rax, [r15+8]
0x18009e8d9  mov     edx, 100h
0x18009e8de  test    [rax+30h], edx
0x18009e8e1  jz      loc_18009EB9B
0x18009e8e7  mov     rax, [r15+8]
0x18009e8eb  mov     qword ptr [rsp+1A0h+var_140], 0
0x18009e8f4  test    [rax+30h], edx
0x18009e8f7  jz      loc_18009EB3E
0x18009e8fd  lea     r8, [rbp+0A0h+Object]
0x18009e901  mov     rcx, r15
0x18009e904  lea     rdx, [rsp+1A0h+var_14F+1]
0x18009e909  xor     r14d, r14d
0x18009e90c  call    CipIsCimBackedFile
0x18009e911  mov     edi, eax
0x18009e913  test    eax, eax
0x18009e915  js      loc_18009ED44
0x18009e91b  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18009e922  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18009e929  nop     dword ptr [rax+rax+00h]
0x18009e92e  xor     edi, edi
0x18009e930  mov     qword ptr [rsp+1A0h+var_140], rax
0x18009e935  mov     rbx, rax
0x18009e938  test    rax, rax
0x18009e93b  jz      loc_18009EAFF
0x18009e941  mov     al, byte ptr [rsp+1A0h+var_14F+1]
0x18009e945  mov     byte ptr [rbp+0A0h+var_70+4], 16h
0x18009e949  mov     dword ptr [rbp+0A0h+var_70], edi
0x18009e94c  cmp     byte ptr [rsp+1A0h+var_14F], dil
0x18009e951  jnz     loc_18009ED52
0x18009e957  movsd   xmm1, qword ptr cs:aKernelPurgeEsb+0Fh; "SBCache"
0x18009e95f  movups  xmm0, xmmword ptr cs:aKernelPurgeEsb; "$Kernel.Purge.ESBCache"
0x18009e966  movups  [rbp+0A0h+var_70+5], xmm0
0x18009e96a  movsd   qword ptr [rbp+0A0h+var_60+4], xmm1
0x18009e96f  test    al, al
0x18009e971  jz      short loc_18009E977
0x18009e973  mov     r15, [rbp+0A0h+Object]
0x18009e977  test    r13b, r13b
0x18009e97a  jnz     loc_18009ED77
0x18009e980  lea     rax, [rbp+0A0h+var_110]
0x18009e984  xor     r9d, r9d
0x18009e987  mov     [rsp+1A0h+var_160], rax
0x18009e98c  mov     r8d, 1CCh
0x18009e992  mov     byte ptr [rsp+1A0h+var_168], 1
0x18009e997  lea     rax, [rbp+0A0h+var_70]
0x18009e99b  mov     [rsp+1A0h+EventDescriptor], rdi
0x18009e9a0  mov     rdx, rbx
0x18009e9a3  mov     dword ptr [rsp+1A0h+var_178], 20h ; ' '
0x18009e9ab  mov     rcx, r15
0x18009e9ae  mov     [rsp+1A0h+var_180], rax
0x18009e9b3  call    cs:__imp_FsRtlQueryKernelEaFile
0x18009e9ba  nop     dword ptr [rax+rax+00h]
0x18009e9bf  mov     edi, eax
0x18009e9c1  test    eax, eax
0x18009e9c3  jns     loc_18009EA65
0x18009e9c9  mov     dword ptr [rsi], 2
0x18009e9cf  mov     r13, [rsp+1A0h+var_138]
0x18009e9d4  mov     r12, [rsp+1A0h+var_148]
0x18009e9d9  mov     rax, [rbp+0A0h+Object]
0x18009e9dd  test    rax, rax
0x18009e9e0  jnz     loc_18009F019
0x18009e9e6  test    rbx, rbx
0x18009e9e9  jz      short loc_18009EA01
0x18009e9eb  mov     rdx, rbx; Entry
0x18009e9ee  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18009e9f5  call    cs:__imp_ExFreeToPagedLookasideList
0x18009e9fc  nop     dword ptr [rax+rax+00h]
0x18009ea01  test    r12, r12
0x18009ea04  jnz     loc_18009F02D
0x18009ea0a  mov     ecx, [rsi]
0x18009ea0c  test    edi, edi
0x18009ea0e  js      loc_18009EB79
0x18009ea14  mov     edx, [r13+0]; int
0x18009ea18  lea     rax, CiGetFileCacheComplete
0x18009ea1f  mov     [rsp+1A0h+EventDescriptor], rax; EventDescriptor
0x18009ea24  mov     r9d, r14d; int
0x18009ea27  mov     rax, qword ptr [rbp+0A0h+var_118]
0x18009ea2b  mov     qword ptr [rsp+1A0h+var_178], rax; char
0x18009ea30  mov     rax, [rbp+0A0h+var_F0]
0x18009ea34  mov     r8b, [rax]; int
0x18009ea37  mov     dword ptr [rsp+1A0h+var_180], ecx; char
0x18009ea3b  mov     ecx, edi; int
0x18009ea3d  call    CiLogCacheEvent
0x18009ea42  mov     eax, edi
0x18009ea44  mov     rcx, [rbp+0A0h+var_50]
0x18009ea48  xor     rcx, rsp; StackCookie
0x18009ea4b  call    __security_check_cookie
0x18009ea50  add     rsp, 168h
0x18009ea57  pop     r15
0x18009ea59  pop     r14
0x18009ea5b  pop     r13
0x18009ea5d  pop     r12
0x18009ea5f  pop     rdi
0x18009ea60  pop     rsi
0x18009ea61  pop     rbx
0x18009ea62  pop     rbp
0x18009ea63  retn
0x18009ea65  xor     r13b, r13b
0x18009ea68  mov     [rsp+1A0h+var_150], r13b
0x18009ea6d  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x18009ea72  test    eax, eax
0x18009ea74  jnz     loc_18009EB0F
0x18009ea7a  mov     dl, byte ptr [rsp+1A0h+var_14F]; int
0x18009ea7e  lea     r9, [rbp+0A0h+var_118]; int
0x18009ea82  mov     rcx, qword ptr [rsp+1A0h+var_140]; int
0x18009ea87  add     rbx, 238h
0x18009ea8e  mov     r8, rsi; int
0x18009ea91  mov     [rsp+1A0h+var_180], rbx; void *
0x18009ea96  call    CipParseFileCache
0x18009ea9b  mov     edi, eax
0x18009ea9d  test    eax, eax
0x18009ea9f  js      short loc_18009EAEC
0x18009eaa1  mov     r9d, [rsp+1A0h+var_130]
0x18009eaa6  lea     rax, [rbp+0A0h+var_118]
0x18009eaaa  mov     rdx, qword ptr [rsp+1A0h+var_140]
0x18009eaaf  mov     r8, r15
0x18009eab2  mov     [rsp+1A0h+var_168], rax
0x18009eab7  mov     rcx, rbx
0x18009eaba  lea     rax, [rsp+1A0h+var_12C]
0x18009eabf  mov     [rsp+1A0h+EventDescriptor], rsi
0x18009eac4  mov     qword ptr [rsp+1A0h+var_178], rax
0x18009eac9  mov     rax, [rbp+0A0h+var_120]
0x18009eacd  mov     [rsp+1A0h+var_180], rax
0x18009ead2  call    CipVerifyFileCache
0x18009ead7  mov     edi, eax
0x18009ead9  test    eax, eax
0x18009eadb  jns     loc_18009EBE5
0x18009eae1  cmp     eax, 0C0000225h
0x18009eae6  jz      loc_18009EDD5
0x18009eaec  mov     rbx, qword ptr [rsp+1A0h+var_140]
0x18009eaf1  jmp     loc_18009E9CF
0x18009eaf6  mov     [r12], rbx
0x18009eafa  jmp     loc_18009E8D5
0x18009eaff  mov     dword ptr [rsi], 1Ch
0x18009eb05  mov     edi, 0C0000017h
0x18009eb0a  jmp     loc_18009E9CF
0x18009eb0f  test    r12, r12
0x18009eb12  jz      loc_18009EA7A
0x18009eb18  mov     edx, [rsp+1A0h+var_130]
0x18009eb1c  lea     r8, [rsp+1A0h+var_150]
0x18009eb21  mov     rcx, [rbp+0A0h+var_120]
0x18009eb25  call    CipIsTrustedLaunch
0x18009eb2a  mov     edi, eax
0x18009eb2c  test    eax, eax
0x18009eb2e  js      loc_18009EDAB
0x18009eb34  mov     r13b, [rsp+1A0h+var_150]
0x18009eb39  jmp     loc_18009EA7A
0x18009eb3e  test    r13b, r13b
0x18009eb41  jnz     loc_18009E8FD
0x18009eb47  test    cs:g_CiOptions, edx
0x18009eb4d  jnz     loc_18009ECDC
0x18009eb53  bt      ebx, 11h
0x18009eb57  jb      loc_18009ECF7
0x18009eb5d  mov     eax, edi
0x18009eb5f  mov     edi, 0C00000BBh
0x18009eb64  mov     ecx, ebx
0x18009eb66  shl     rcx, 20h
0x18009eb6a  or      rcx, rax
0x18009eb6d  mov     dword ptr [rsi], 5
0x18009eb73  mov     qword ptr [rbp+0A0h+var_118], rcx
0x18009eb77  mov     ecx, [rsi]
0x18009eb79  lea     rax, CiGetFileCacheComplete
0x18009eb80  xor     r9d, r9d
0x18009eb83  mov     [rsp+1A0h+EventDescriptor], rax
0x18009eb88  xor     r8d, r8d
0x18009eb8b  mov     rax, qword ptr [rbp+0A0h+var_118]
0x18009eb8f  xor     edx, edx
0x18009eb91  mov     qword ptr [rsp+1A0h+var_178], rax
0x18009eb96  jmp     loc_18009EA37
0x18009eb9b  lea     rdx, [rsp+1A0h+var_128]
0x18009eba0  mov     rcx, r15
0x18009eba3  call    CipGetFileAttributes
0x18009eba8  mov     edi, eax
0x18009ebaa  test    eax, eax
0x18009ebac  js      loc_18009ECC6
0x18009ebb2  lea     r8, [rsp+1A0h+var_150]
0x18009ebb7  mov     rcx, r15; FileObject
0x18009ebba  lea     rdx, [rsp+1A0h+var_140]
0x18009ebbf  call    CipGetVolumeFlags
0x18009ebc4  mov     edi, eax
0x18009ebc6  test    eax, eax
0x18009ebc8  js      loc_18009ECD1
0x18009ebce  mov     edi, [rsp+1A0h+var_128]
0x18009ebd2  mov     edx, 100h
0x18009ebd7  mov     ebx, [rsp+1A0h+var_140]
0x18009ebdb  mov     r13b, [rsp+1A0h+var_150]
0x18009ebe0  jmp     loc_18009E8E7
0x18009ebe5  mov     rax, [rbx]
0x18009ebe8  mov     ecx, [rax+18h]
0x18009ebeb  test    cl, 10h
0x18009ebee  jnz     loc_18009EDB6
0x18009ebf4  mov     r15, [rbp+0A0h+FileObject]
0x18009ebf8  mov     eax, cs:g_CiPolicyState
0x18009ebfe  mov     ecx, [rsp+1A0h+var_130]
0x18009ec02  bt      eax, 0Fh
0x18009ec06  jb      loc_18009EE78
0x18009ec0c  test    r13b, r13b
0x18009ec0f  jnz     loc_18009EE98
0x18009ec15  mov     r9, [rbp+0A0h+var_C8]
0x18009ec19  test    r9, r9
0x18009ec1c  jnz     loc_18009EEB5
0x18009ec22  mov     rcx, [rbp+0A0h+var_C0]
0x18009ec26  test    rcx, rcx
0x18009ec29  jnz     loc_18009EF1E
0x18009ec2f  mov     rcx, [rbp+0A0h+var_B8]
0x18009ec33  test    rcx, rcx
0x18009ec36  jnz     loc_18009EF43
0x18009ec3c  mov     rcx, [rbp+0A0h+var_B0]
0x18009ec40  test    rcx, rcx
0x18009ec43  jnz     loc_18009EF4F
0x18009ec49  mov     r14, [rbp+0A0h+var_A8]
0x18009ec4d  test    r14, r14
0x18009ec50  jnz     loc_18009EF59
0x18009ec56  cmp     byte ptr [rsp+1A0h+var_14F+1], 0
0x18009ec5b  mov     rax, [rbx]
0x18009ec5e  mov     r13, [rsp+1A0h+var_138]
0x18009ec63  mov     cl, [rax+7]
0x18009ec66  mov     rax, [rbp+0A0h+var_F0]
0x18009ec6a  mov     [rax], cl
0x18009ec6c  mov     dword ptr [r13+0], 0
0x18009ec74  mov     rax, [rbx]
0x18009ec77  mov     r14d, [rax+18h]
0x18009ec7b  jnz     loc_18009EF87
0x18009ec81  mov     r12, [rsp+1A0h+var_148]
0x18009ec86  or      r14d, [rsp+1A0h+var_12C]
0x18009ec8b  mov     rax, [rbp+0A0h+var_D0]
0x18009ec8f  mov     rbx, qword ptr [rsp+1A0h+var_140]
0x18009ec94  test    rax, rax
0x18009ec97  jz      loc_18009E9D9
0x18009ec9d  mov     [rax], r14d
0x18009eca0  jmp     loc_18009E9D9
0x18009eca5  mov     rbx, qword ptr [rbp+0A0h+FileSize]
  ... truncated ...
```
