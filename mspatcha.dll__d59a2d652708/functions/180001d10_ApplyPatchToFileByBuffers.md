# ApplyPatchToFileByBuffers

- ea: `0x180001d10`
- end: `0x1800026e3`
- name: `ApplyPatchToFileByBuffers`
- size: `2515`
- prototype: `BOOL __stdcall(PBYTE PatchFileMapped, ULONG PatchFileSize, PBYTE OldFileMapped, ULONG OldFileSize, PBYTE *NewFileBuffer, ULONG NewFileBufferSize, ULONG *NewFileActualSize, FILETIME *NewFileTime, ULONG ApplyOptionFlags, PPATCH_PROGRESS_CALLBACK ProgressCallback, PVOID CallbackContext)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, installer_update`

## callers

- `0x180004880`

## callees

- `0x180001cae`
- `0x180001d10`
- `0x180003348`
- `0x18000380c`
- `0x180004520`
- `0x180004678`
- `0x1800046e0`
- `0x180004940`
- `0x180006d9c`
- `0x180006dd4`
- `0x180007034`
- `0x180009061`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002603`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002603`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800026c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800026c2`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800021bc`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800025ae`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000263d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180002653`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180002675`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800026ac`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800021bc`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800025ae`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000263d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180002653`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180002675`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800026ac`

## pseudocode

```c
BOOL __stdcall ApplyPatchToFileByBuffers(
        PBYTE PatchFileMapped,
        ULONG PatchFileSize,
        PBYTE OldFileMapped,
        ULONG OldFileSize,
        PBYTE *NewFileBuffer,
        ULONG NewFileBufferSize,
        ULONG *NewFileActualSize,
        FILETIME *NewFileTime,
        ULONG ApplyOptionFlags,
        PPATCH_PROGRESS_CALLBACK ProgressCallback,
        PVOID CallbackContext)
{
  size_t v11; // r15
  __int64 v14; // r13
  char *v15; // r12
  char *v16; // r14
  int v17; // esi
  DWORD v18; // ecx
  __int64 SubAllocator; // rax
  __int64 v20; // r13
  void *v21; // rax
  char *v22; // rax
  size_t v23; // rcx
  unsigned int v24; // edx
  __int64 v25; // rax
  __int64 i; // rax
  size_t v27; // r8
  unsigned int v28; // r11d
  INT v29; // eax
  __int64 v30; // rcx
  int v31; // r11d
  int v32; // ecx
  __int64 j; // r15
  unsigned __int64 v34; // rdx
  __int64 v35; // rsi
  size_t v36; // r8
  __int64 k; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  ULONG v40; // ecx
  __int64 v41; // rax
  unsigned int v42; // eax
  __int64 v43; // rcx
  int v44; // eax
  int v45; // eax
  __int64 m; // r15
  unsigned __int64 OffsetInNewFile; // rdx
  struct _PATCH_RETAIN_RANGE *v48; // rsi
  size_t LengthInBytes; // r8
  int v50; // r10d
  __int64 v51; // rax
  __int64 v52; // r9
  DWORD LastError; // r15d
  _QWORD *v54; // rcx
  _QWORD *v55; // rbx
  DWORD v56; // ecx
  __int64 v57; // [rsp+58h] [rbp-D0h]
  int v58; // [rsp+80h] [rbp-A8h]
  int v59; // [rsp+80h] [rbp-A8h]
  __int64 v60; // [rsp+90h] [rbp-98h] BYREF
  __int64 v61; // [rsp+98h] [rbp-90h]
  char *v62; // [rsp+A0h] [rbp-88h]
  int v63[2]; // [rsp+A8h] [rbp-80h]
  int v64; // [rsp+B0h] [rbp-78h] BYREF
  int v65; // [rsp+B4h] [rbp-74h]
  void *v66; // [rsp+B8h] [rbp-70h]
  __int64 v67; // [rsp+C0h] [rbp-68h]
  PPATCH_RETAIN_RANGE RetainRangeArray; // [rsp+C8h] [rbp-60h]
  LPVOID lpAddress; // [rsp+D0h] [rbp-58h]
  char *v70; // [rsp+D8h] [rbp-50h]
  __int64 v71; // [rsp+E0h] [rbp-48h]
  __int64 v72; // [rsp+E8h] [rbp-40h]
  __int64 v73; // [rsp+F0h] [rbp-38h]
  int NewFileActualSizea; // [rsp+160h] [rbp+38h]
  ULONG *NewFileActualSizeb; // [rsp+160h] [rbp+38h]
  ULONG *NewFileActualSizec; // [rsp+160h] [rbp+38h]
  FILETIME *NewFileTimea; // [rsp+168h] [rbp+40h]
  unsigned int NewFileTimeb; // [rsp+168h] [rbp+40h]
  ULONG NewFileTimec; // [rsp+168h] [rbp+40h]

  v11 = OldFileSize;
  v60 = 0;
  v64 = 0;
  if ( NewFileActualSize )
    *NewFileActualSize = 0;
  if ( NewFileTime )
    *NewFileTime = 0;
  if ( NewFileBuffer )
  {
    NewFileTimea = (FILETIME *)*NewFileBuffer;
  }
  else
  {
    if ( (ApplyOptionFlags & 4) == 0 )
    {
      SetLastError(0x57u);
      return 0;
    }
    NewFileTimea = 0;
  }
  lpAddress = 0;
  LODWORD(v14) = 0;
  v65 = 0;
  v71 = 0;
  v15 = 0;
  v70 = 0;
  v16 = 0;
  v62 = 0;
  v17 = 0;
  if ( ~(unsigned int)Crc32(PatchFileMapped, PatchFileMapped, PatchFileSize) != -1 )
    goto LABEL_12;
  SubAllocator = CreateSubAllocator(0x10000);
  v71 = SubAllocator;
  if ( !SubAllocator )
    goto LABEL_105;
  if ( !(unsigned int)DecodePatchHeader(
                        (_DWORD)PatchFileMapped,
                        PatchFileSize,
                        SubAllocator,
                        (unsigned int)&v64,
                        (__int64)&v60) )
  {
LABEL_12:
    v18 = -1072807678;
LABEL_104:
    SetLastError(v18);
    goto LABEL_105;
  }
  v20 = v60;
  if ( (*(_DWORD *)(v60 + 4) & 0x800000) == 0 && *(_DWORD *)(v60 + 24) && NewFileTime )
    *NewFileTime = (FILETIME)(10000000 * (*(unsigned int *)(v60 + 24) + 0x2B6109100LL));
  v14 = *(unsigned int *)(v20 + 28);
  v65 = v14;
  if ( NewFileActualSize )
    *NewFileActualSize = v14;
  if ( (ApplyOptionFlags & 4) != 0 )
    goto LABEL_22;
  if ( NewFileTimea )
  {
    if ( NewFileBufferSize < (unsigned int)v14 )
    {
      v18 = 122;
      goto LABEL_104;
    }
  }
  else if ( (_DWORD)v14 )
  {
    v21 = (void *)MyVirtualAlloc(v14);
    lpAddress = v21;
    if ( !v21 )
      goto LABEL_105;
    goto LABEL_30;
  }
  v21 = lpAddress;
LABEL_30:
  if ( NewFileTimea )
    v21 = NewFileTimea;
  v66 = v21;
  if ( !(unsigned int)ProgressCallbackWrapper(ProgressCallback, CallbackContext, 0, (unsigned int)v14) )
    goto LABEL_105;
  if ( (_DWORD)v11 )
  {
    v22 = (char *)MyVirtualAlloc(v11);
    v15 = v22;
    v70 = v22;
    if ( !v22 )
      goto LABEL_105;
    memcpy_0(v22, OldFileMapped, v11);
  }
  NewFileActualSizea = 0;
  if ( (_DWORD)v11 == (_DWORD)v14 )
  {
    v23 = *(_QWORD *)(v60 + 40);
    v24 = *(_DWORD *)(v23 + 32);
    NewFileTimeb = v24;
    v25 = *(_QWORD *)(v23 + 40);
    *(_QWORD *)v63 = v25;
    if ( v24 )
    {
      v16 = (char *)SaveRetainRanges((_DWORD)v15, v11, v24, v25, 1);
      v62 = v16;
      if ( !v16 )
        goto LABEL_105;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v58 = i;
        if ( (unsigned int)i >= NewFileTimeb )
          break;
        v23 = *(unsigned int *)(*(_QWORD *)v63 + 12 * i + 8);
        if ( v23 <= v11 )
        {
          v27 = *(unsigned int *)(*(_QWORD *)v63 + 12 * i + 4);
          if ( v27 <= v11 - v23 )
          {
            memset_0(&v15[v23], 0, v27);
            NewFileActualSizea = 1;
            LODWORD(i) = v58;
          }
        }
      }
    }
    v28 = ~(unsigned int)Crc32(v23, v15, (unsigned int)v11);
    if ( v28 == *(_DWORD *)(v60 + 32) )
    {
      v32 = 0;
    }
    else
    {
      v29 = NormalizeOldFileImageForPatching(
              v15,
              v11,
              *(_DWORD *)(v60 + 4),
              0,
              *(_DWORD *)(v60 + 12),
              *(_DWORD *)(v60 + 16),
              0,
              0,
              0,
              0);
      LODWORD(v61) = v29;
      if ( !v29 )
        goto LABEL_105;
      v31 = NewFileActualSizea;
      if ( v29 > 1 )
        v31 = 1;
      NewFileActualSizea = v31;
      v28 = ~(unsigned int)Crc32(v30, v15, (unsigned int)v11);
      v32 = v61;
    }
    if ( v28 == *(_DWORD *)(v60 + 32) )
    {
      if ( (ApplyOptionFlags & 2) == 0 && ((ApplyOptionFlags & 1) == 0 || v32 >= 2) )
      {
        if ( (_DWORD)v14 )
        {
          NewFileActualSizeb = (ULONG *)v11;
          memcpy_0(v66, v15, v11);
          for ( j = 0; (unsigned int)j < NewFileTimeb; j = (unsigned int)(j + 1) )
          {
            v34 = *(unsigned int *)(*(_QWORD *)v63 + 12 * j + 8);
            v35 = *(_QWORD *)v63 + 12 * j;
            if ( v34 <= (unsigned __int64)NewFileActualSizeb )
            {
              v36 = *(unsigned int *)(v35 + 4);
              if ( v36 <= (unsigned __int64)NewFileActualSizeb - v34 )
                memcpy_0((char *)v66 + v34, v16, v36);
            }
            v16 += *(unsigned int *)(v35 + 4);
            v62 = v16;
          }
        }
        goto LABEL_22;
      }
LABEL_53:
      v18 = -1072807675;
      goto LABEL_104;
    }
  }
  if ( v16 )
  {
    VirtualFree(v16, 0, 0x8000u);
    v16 = 0;
    v62 = 0;
  }
  *(_QWORD *)v63 = &PatchFileMapped[v64];
  v73 = *(_QWORD *)v63;
  for ( k = 0; ; k = (unsigned int)(v59 + 1) )
  {
    v59 = k;
    if ( (unsigned int)k >= *(_DWORD *)(v60 + 36) )
    {
      v18 = -1072807676;
      goto LABEL_104;
    }
    v72 = k;
    v38 = 9 * k;
    v61 = 9 * k;
    v39 = *(_QWORD *)(v60 + 40);
    v67 = v39;
    if ( *(_DWORD *)(v39 + 72 * k + 8) == (_DWORD)v11 )
    {
      v40 = *(_DWORD *)(v39 + 72 * k + 32);
      NewFileTimec = v40;
      v41 = *(_QWORD *)(v39 + 72 * k + 40);
      RetainRangeArray = *(PPATCH_RETAIN_RANGE *)(v39 + 8 * v38 + 40);
      if ( NewFileActualSizea )
      {
        memcpy_0(v15, OldFileMapped, v11);
        NewFileActualSizea = 0;
        v38 = v61;
        v39 = v67;
        LODWORD(v41) = (_DWORD)RetainRangeArray;
        v40 = NewFileTimec;
      }
      if ( *(_DWORD *)(v39 + 8 * v38 + 32) )
      {
        v16 = (char *)SaveRetainRanges((_DWORD)v15, v11, v40, v41, 0);
        v62 = v16;
        if ( !v16 )
          goto LABEL_105;
        v38 = v61;
        v39 = v67;
      }
      v42 = NormalizeOldFileImageForPatching(
              v15,
              v11,
              *(_DWORD *)(v60 + 4),
              0,
              *(_DWORD *)(v60 + 12),
              *(_DWORD *)(v60 + 16),
              *(_DWORD *)(v39 + 8 * v38 + 20),
              *(PPATCH_IGNORE_RANGE *)(v39 + 8 * v38 + 24),
              NewFileTimec,
              RetainRangeArray);
      v43 = v42;
      if ( !v42 )
        goto LABEL_105;
      v44 = NewFileActualSizea;
      if ( (int)v43 > 1 )
        v44 = 1;
      NewFileActualSizea = v44;
      v45 = Crc32(v43, v15, (unsigned int)v11);
      v38 = v61;
      v39 = v67;
      if ( ~v45 == *(_DWORD *)(v67 + 8 * v61 + 12) )
        break;
    }
LABEL_100:
    *(_QWORD *)v63 += *(unsigned int *)(v39 + 8 * v38 + 16);
    v73 = *(_QWORD *)v63;
    if ( v16 )
    {
      VirtualFree(v16, 0, 0x8000u);
      v16 = 0;
      v62 = 0;
    }
  }
  if ( !(_DWORD)v14 )
  {
    if ( (_DWORD)v11 || (ApplyOptionFlags & 3) == 0 )
      goto LABEL_22;
    goto LABEL_53;
  }
  if ( *(_DWORD *)(v67 + 8 * v61 + 16) )
  {
    v50 = v63[0];
    if ( *(_QWORD *)v63 + (unsigned __int64)*(unsigned int *)(v67 + 8 * v61 + 16) > (unsigned __int64)&PatchFileMapped[PatchFileSize] )
    {
      v18 = -1072807674;
      goto LABEL_104;
    }
    if ( *(_DWORD *)(v67 + 8 * (v61 + 6)) )
    {
      NewFileActualSizea = 1;
      if ( !(unsigned int)TransformOldFileImageForPatching(
                            (int)v60 + 8,
                            (_DWORD)v15,
                            v11,
                            *(_DWORD *)(v60 + 20),
                            v67 + 8 * (v61 + 6)) )
        goto LABEL_105;
      v38 = v61;
      v39 = v67;
      v50 = v63[0];
    }
    v51 = *(_QWORD *)(v60 + 48);
    if ( v51 )
      v52 = *(_QWORD *)(v51 + 8 * v72);
    else
      v52 = 0;
    if ( (unsigned int)CreateNewFileBufferFromPatchData(
                         (int)v15,
                         v11,
                         v50,
                         *(_DWORD *)(v39 + 8 * v38 + 16),
                         (__int64)v66,
                         v14,
                         *(_DWORD *)(v60 + 32),
                         NewFileTimec,
                         (__int64)RetainRangeArray,
                         v16,
                         *(_DWORD *)(v60 + 4),
                         v57,
                         *(_DWORD *)(v60 + 56),
                         v52) )
      goto LABEL_22;
    v38 = v61;
    v39 = v67;
    goto LABEL_100;
  }
  if ( (_DWORD)v11 == (_DWORD)v14 && (ApplyOptionFlags & 2) != 0 )
    goto LABEL_53;
  NewFileActualSizec = (ULONG *)v11;
  memcpy_0(v66, v15, v11);
  for ( m = 0; (unsigned int)m < NewFileTimec; m = (unsigned int)(m + 1) )
  {
    OffsetInNewFile = RetainRangeArray[m].OffsetInNewFile;
    v48 = &RetainRangeArray[m];
    if ( OffsetInNewFile <= (unsigned __int64)NewFileActualSizec )
    {
      LengthInBytes = v48->LengthInBytes;
      if ( LengthInBytes <= (unsigned __int64)NewFileActualSizec - OffsetInNewFile )
        memcpy_0((char *)v66 + OffsetInNewFile, v16, LengthInBytes);
    }
    v16 += v48->LengthInBytes;
    v62 = v16;
  }
LABEL_22:
  v17 = 1;
LABEL_105:
  LastError = GetLastError();
  if ( v17 )
    v17 = ProgressCallbackWrapper(ProgressCallback, CallbackContext, (unsigned int)v14, (unsigned int)v14);
  if ( v16 )
    VirtualFree(v16, 0, 0x8000u);
  if ( v15 )
    VirtualFree(v15, 0, 0x8000u);
  if ( v71 )
  {
    v54 = *(_QWORD **)(v71 + 8);
    do
    {
      v55 = (_QWORD *)*v54;
      VirtualFree(v54, 0, 0x8000u);
      v54 = v55;
    }
    while ( v55 );
  }
  if ( lpAddress )
  {
    if ( v17 )
      *NewFileBuffer = (PBYTE)lpAddress;
    else
      VirtualFree(lpAddress, 0, 0x8000u);
  }
  if ( !v17 )
  {
    v56 = 1208;
    if ( LastError )
      v56 = LastError;
    SetLastError(v56);
  }
  return v17;
}

```

## disassembly

```asm
0x180001d10  mov     rax, rsp
0x180001d13  mov     [rax+20h], rbx
0x180001d17  mov     [rax+18h], r8
0x180001d1b  mov     [rax+10h], edx
0x180001d1e  mov     [rax+8], rcx
0x180001d22  push    rsi
0x180001d23  push    r12
0x180001d25  push    r13
0x180001d27  push    r14
0x180001d29  push    r15
0x180001d2b  sub     rsp, 100h
0x180001d32  mov     r15d, r9d
0x180001d35  mov     qword ptr [rax-98h], 0
0x180001d40  mov     dword ptr [rax-78h], 0
0x180001d47  mov     rax, [rsp+128h+NewFileActualSize]
0x180001d4f  test    rax, rax
0x180001d52  jz      short loc_180001D5A
0x180001d54  mov     dword ptr [rax], 0
0x180001d5a  mov     rbx, [rsp+128h+NewFileTime]
0x180001d62  test    rbx, rbx
0x180001d65  jz      short loc_180001D6E
0x180001d67  mov     qword ptr [rbx], 0
0x180001d6e  mov     rax, [rsp+128h+NewFileBuffer]
0x180001d76  test    rax, rax
0x180001d79  jnz     short loc_180001D9A
0x180001d7b  test    byte ptr [rsp+128h+ApplyOptionFlags], 4
0x180001d83  jnz     short loc_180001D95
0x180001d85  lea     ecx, [rax+57h]; dwErrCode
0x180001d88  call    cs:__imp_SetLastError
0x180001d8e  xor     eax, eax
0x180001d90  jmp     loc_1800026CA
0x180001d95  test    rax, rax
0x180001d98  jz      short loc_180001DA7
0x180001d9a  mov     rax, [rax]
0x180001d9d  mov     [rsp+128h+NewFileTime], rax
0x180001da5  jmp     short loc_180001DB3
0x180001da7  mov     [rsp+128h+NewFileTime], 0
0x180001db3  mov     [rsp+128h+lpAddress], 0
0x180001dbf  xor     r13d, r13d
0x180001dc2  mov     [rsp+128h+var_74], r13d
0x180001dca  mov     [rsp+128h+var_48], r13
0x180001dd2  xor     r12d, r12d
0x180001dd5  mov     [rsp+128h+var_50], r12
0x180001ddd  xor     r14d, r14d
0x180001de0  mov     [rsp+128h+var_88], r14
0x180001de8  xor     esi, esi
0x180001dea  mov     r8d, edx
0x180001ded  mov     rdx, rcx
0x180001df0  call    Crc32
0x180001df5  not     eax
0x180001df7  cmp     eax, 0FFFFFFFFh
0x180001dfa  jz      short loc_180001E06
0x180001dfc  mov     ecx, 0C00E4102h
0x180001e01  jmp     loc_1800025D2
0x180001e06  mov     ecx, 10000h
0x180001e0b  call    CreateSubAllocator
0x180001e10  mov     [rsp+128h+var_48], rax
0x180001e18  test    rax, rax
0x180001e1b  jz      loc_1800025D8
0x180001e21  lea     rcx, [rsp+128h+var_98]
0x180001e29  mov     qword ptr [rsp+128h+NewFileCoffBase], rcx
0x180001e2e  lea     r9, [rsp+128h+var_78]
0x180001e36  mov     r8, rax
0x180001e39  mov     edx, [rsp+128h+arg_8]
0x180001e40  mov     rcx, [rsp+128h+arg_0]
0x180001e48  call    DecodePatchHeader
0x180001e4d  test    eax, eax
0x180001e4f  jz      short loc_180001DFC
0x180001e51  mov     r13, [rsp+128h+var_98]
0x180001e59  test    dword ptr [r13+4], 800000h
0x180001e61  jnz     short loc_180001E8A
0x180001e63  cmp     dword ptr [r13+18h], 0
0x180001e68  jz      short loc_180001E8A
0x180001e6a  test    rbx, rbx
0x180001e6d  jz      short loc_180001E8A
0x180001e6f  mov     eax, [r13+18h]
0x180001e73  mov     rcx, 2B6109100h
0x180001e7d  add     rax, rcx
0x180001e80  imul    rax, 989680h
0x180001e87  mov     [rbx], rax
0x180001e8a  mov     r13d, [r13+1Ch]
0x180001e8e  mov     [rsp+128h+var_74], r13d
0x180001e96  mov     rax, [rsp+128h+NewFileActualSize]
0x180001e9e  test    rax, rax
0x180001ea1  jz      short loc_180001EA6
0x180001ea3  mov     [rax], r13d
0x180001ea6  test    byte ptr [rsp+128h+ApplyOptionFlags], 4
0x180001eae  jz      short loc_180001EC3
0x180001eb0  mov     ebx, 1
0x180001eb5  mov     esi, ebx
0x180001eb7  mov     [rsp+128h+var_A4], ebx
0x180001ebe  jmp     loc_1800025D8
0x180001ec3  mov     rbx, [rsp+128h+NewFileTime]
0x180001ecb  test    rbx, rbx
0x180001ece  jz      short loc_180001EE4
0x180001ed0  cmp     [rsp+128h+NewFileBufferSize], r13d
0x180001ed8  jnb     short loc_180001F04
0x180001eda  mov     ecx, 7Ah ; 'z'
0x180001edf  jmp     loc_1800025D2
0x180001ee4  test    r13d, r13d
0x180001ee7  jz      short loc_180001F04
0x180001ee9  mov     rcx, r13
0x180001eec  call    MyVirtualAlloc
0x180001ef1  mov     [rsp+128h+lpAddress], rax
0x180001ef9  test    rax, rax
0x180001efc  jz      loc_1800025D8
0x180001f02  jmp     short loc_180001F0C
0x180001f04  mov     rax, [rsp+128h+lpAddress]
0x180001f0c  test    rbx, rbx
0x180001f0f  cmovnz  rax, rbx
0x180001f13  mov     [rsp+128h+var_70], rax
0x180001f1b  mov     r9d, r13d
0x180001f1e  xor     r8d, r8d
0x180001f21  mov     rdx, [rsp+128h+CallbackContext]
0x180001f29  mov     rcx, [rsp+128h+ProgressCallback]
0x180001f31  call    ProgressCallbackWrapper
0x180001f36  test    eax, eax
0x180001f38  jz      loc_1800025D8
0x180001f3e  test    r15d, r15d
0x180001f41  jz      short loc_180001F72
0x180001f43  mov     rcx, r15
0x180001f46  call    MyVirtualAlloc
0x180001f4b  mov     r12, rax
0x180001f4e  mov     [rsp+128h+var_50], rax
0x180001f56  test    rax, rax
0x180001f59  jz      loc_1800025D8
0x180001f5f  mov     r8, r15; Size
0x180001f62  mov     rdx, [rsp+128h+Src]; Src
0x180001f6a  mov     rcx, rax; void *
0x180001f6d  call    memcpy_0
0x180001f72  xor     eax, eax
0x180001f74  mov     dword ptr [rsp+128h+NewFileActualSize], eax
0x180001f7b  mov     [rsp+128h+var_A0], eax
0x180001f82  lea     ebx, [rax+1]
0x180001f85  cmp     r15d, r13d
0x180001f88  jnz     loc_1800021AC
0x180001f8e  mov     rax, [rsp+128h+var_98]
0x180001f96  mov     rcx, [rax+28h]
0x180001f9a  mov     edx, [rcx+20h]
0x180001f9d  mov     dword ptr [rsp+128h+NewFileTime], edx
0x180001fa4  mov     rax, [rcx+28h]
0x180001fa8  mov     qword ptr [rsp+128h+var_80], rax
0x180001fb0  test    edx, edx
0x180001fb2  jz      loc_18000203C
0x180001fb8  mov     [rsp+128h+NewFileCoffBase], ebx
0x180001fbc  mov     r9, rax
0x180001fbf  mov     r8d, edx
0x180001fc2  mov     edx, r15d
0x180001fc5  mov     rcx, r12
0x180001fc8  call    SaveRetainRanges
0x180001fcd  mov     r14, rax
0x180001fd0  mov     [rsp+128h+var_88], rax
0x180001fd8  test    rax, rax
0x180001fdb  jz      loc_1800025D8
0x180001fe1  xor     eax, eax
0x180001fe3  mov     [rsp+128h+var_A8], eax
0x180001fea  cmp     eax, dword ptr [rsp+128h+NewFileTime]
0x180001ff1  jnb     short loc_18000203C
0x180001ff3  mov     rdx, r15
0x180001ff6  lea     r9, [rax+rax*2]
0x180001ffa  mov     r8, qword ptr [rsp+128h+var_80]
0x180002002  mov     ecx, [r8+r9*4+8]
0x180002007  cmp     rcx, r15
0x18000200a  ja      short loc_180002038
0x18000200c  mov     r8d, [r8+r9*4+4]; Size
0x180002011  sub     rdx, rcx
0x180002014  cmp     r8, rdx
0x180002017  ja      short loc_180002038
0x180002019  add     rcx, r12; void *
0x18000201c  xor     edx, edx; Val
0x18000201e  call    memset_0
0x180002023  mov     dword ptr [rsp+128h+NewFileActualSize], ebx
0x18000202a  mov     [rsp+128h+var_A0], ebx
0x180002031  mov     eax, [rsp+128h+var_A8]
0x180002038  add     eax, ebx
0x18000203a  jmp     short loc_180001FE3
0x18000203c  mov     r8d, r15d
0x18000203f  mov     rdx, r12
0x180002042  call    Crc32
0x180002047  mov     r11d, eax
0x18000204a  not     r11d
0x18000204d  mov     r8, [rsp+128h+var_98]
0x180002055  cmp     r11d, [r8+20h]
0x180002059  jz      loc_1800020EA
0x18000205f  mov     [rsp+128h+RetainRangeArray], 0; RetainRangeArray
0x180002068  mov     [rsp+128h+RetainRangeCount], 0; RetainRangeCount
0x180002070  mov     [rsp+128h+IgnoreRangeArray], 0; IgnoreRangeArray
0x180002079  mov     [rsp+128h+IgnoreRangeCount], 0; IgnoreRangeCount
0x180002081  mov     eax, [r8+10h]
0x180002085  mov     [rsp+128h+NewFileCoffTime], eax; NewFileCoffTime
0x180002089  mov     eax, [r8+0Ch]
0x18000208d  mov     [rsp+128h+NewFileCoffBase], eax; NewFileCoffBase
0x180002091  xor     r9d, r9d; OptionData
0x180002094  mov     r8d, [r8+4]; OptionFlags
0x180002098  mov     edx, r15d; FileSize
0x18000209b  mov     rcx, r12; FileBuffer
0x18000209e  call    NormalizeOldFileImageForPatching
0x1800020a3  mov     dword ptr [rsp+128h+var_90], eax
0x1800020aa  test    eax, eax
0x1800020ac  jz      loc_1800025D8
0x1800020b2  mov     r11d, dword ptr [rsp+128h+NewFileActualSize]
0x1800020ba  cmp     eax, ebx
0x1800020bc  cmovg   r11d, ebx
0x1800020c0  mov     dword ptr [rsp+128h+NewFileActualSize], r11d
0x1800020c8  mov     [rsp+128h+var_A0], r11d
0x1800020d0  mov     r8d, r15d
0x1800020d3  mov     rdx, r12
0x1800020d6  call    Crc32
0x1800020db  mov     r11d, eax
0x1800020de  not     r11d
0x1800020e1  mov     ecx, dword ptr [rsp+128h+var_90]
0x1800020e8  jmp     short loc_1800020EC
0x1800020ea  xor     ecx, ecx
0x1800020ec  mov     rax, [rsp+128h+var_98]
0x1800020f4  cmp     r11d, [rax+20h]
0x1800020f8  jnz     loc_1800021AC
0x1800020fe  mov     eax, [rsp+128h+ApplyOptionFlags]
0x180002105  test    al, 2
0x180002107  jz      short loc_180002113
0x180002109  mov     ecx, 0C00E4105h
0x18000210e  jmp     loc_1800025D2
0x180002113  test    bl, al
0x180002115  jz      short loc_18000211C
0x180002117  cmp     ecx, 2
0x18000211a  jl      short loc_180002109
0x18000211c  test    r13d, r13d
0x18000211f  jz      loc_180001EB5
0x180002125  mov     [rsp+128h+NewFileActualSize], r15
0x18000212d  mov     r8, r15; Size
0x180002130  mov     rdx, r12; Src
0x180002133  mov     rcx, [rsp+128h+var_70]; void *
0x18000213b  call    memcpy_0
0x180002140  xor     r15d, r15d
0x180002143  mov     [rsp+128h+var_A8], r15d
0x18000214b  cmp     r15d, dword ptr [rsp+128h+NewFileTime]
0x180002153  jnb     loc_180001EB5
0x180002159  lea     rcx, [r15+r15*2]
0x18000215d  mov     rax, qword ptr [rsp+128h+var_80]
0x180002165  mov     edx, [rax+rcx*4+8]
0x180002169  lea     rsi, [rax+rcx*4]
0x18000216d  mov     rax, [rsp+128h+NewFileActualSize]
0x180002175  cmp     rdx, rax
0x180002178  ja      short loc_180002199
0x18000217a  mov     r8d, [rsi+4]; Size
0x18000217e  sub     rax, rdx
0x180002181  cmp     r8, rax
0x180002184  ja      short loc_180002199
0x180002186  mov     rcx, [rsp+128h+var_70]
0x18000218e  add     rcx, rdx; void *
0x180002191  mov     rdx, r14; Src
0x180002194  call    memcpy_0
0x180002199  mov     eax, [rsi+4]
0x18000219c  add     r14, rax
0x18000219f  mov     [rsp+128h+var_88], r14
0x1800021a7  add     r15d, ebx
0x1800021aa  jmp     short loc_180002143
0x1800021ac  test    r14, r14
0x1800021af  jz      short loc_1800021CD
0x1800021b1  xor     edx, edx; dwSize
0x1800021b3  mov     r8d, 8000h; dwFreeType
0x1800021b9  mov     rcx, r14; lpAddress
0x1800021bc  call    cs:__imp_VirtualFree
0x1800021c2  xor     r14d, r14d
0x1800021c5  mov     [rsp+128h+var_88], r14
0x1800021cd  mov     edx, [rsp+128h+var_78]
0x1800021d4  add     rdx, [rsp+128h+arg_0]
0x1800021dc  mov     qword ptr [rsp+128h+var_80], rdx
0x1800021e4  mov     [rsp+128h+var_38], rdx
0x1800021ec  xor     eax, eax
0x1800021ee  mov     [rsp+128h+var_A8], eax
0x1800021f5  mov     r8, [rsp+128h+var_98]
0x1800021fd  cmp     eax, [r8+24h]
0x180002201  jnb     loc_1800025CD
0x180002207  mov     [rsp+128h+var_40], rax
0x18000220f  lea     rdx, [rax+rax*8]
0x180002213  mov     [rsp+128h+var_90], rdx
0x18000221b  mov     r8, [r8+28h]
0x18000221f  mov     [rsp+128h+var_68], r8
0x180002227  cmp     [r8+rdx*8+8], r15d
0x18000222c  jnz     loc_18000257E
0x180002232  mov     ecx, [r8+rdx*8+20h]
0x180002237  mov     dword ptr [rsp+128h+NewFileTime], ecx
0x18000223e  mov     rax, [r8+rdx*8+28h]
0x180002243  mov     [rsp+128h+var_60], rax
0x18000224b  cmp     dword ptr [rsp+128h+NewFileActualSize], 0
0x180002253  jz      short loc_180002297
0x180002255  mov     r8, r15; Size
0x180002258  mov     rdx, [rsp+128h+Src]; Src
0x180002260  mov     rcx, r12; void *
0x180002263  call    memcpy_0
0x180002268  xor     eax, eax
0x18000226a  mov     dword ptr [rsp+128h+NewFileActualSize], eax
0x180002271  mov     [rsp+128h+var_A0], eax
0x180002278  mov     rdx, [rsp+128h+var_90]
0x180002280  mov     r8, [rsp+128h+var_68]
0x180002288  mov     rax, [rsp+128h+var_60]
0x180002290  mov     ecx, dword ptr [rsp+128h+NewFileTime]
0x180002297  cmp     dword ptr [r8+rdx*8+20h], 0
0x18000229d  jz      short loc_1800022DC
0x18000229f  mov     [rsp+128h+NewFileCoffBase], 0
  ... truncated ...
```
