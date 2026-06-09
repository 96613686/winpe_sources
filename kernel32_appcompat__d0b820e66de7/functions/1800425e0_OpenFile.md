# OpenFile

- ea: `0x1800425e0`
- end: `0x180042bd7`
- name: `OpenFile`
- size: `1527`
- prototype: `HFILE __stdcall(LPCSTR lpFileName, LPOFSTRUCT lpReOpenBuff, UINT uStyle)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800552a0`
- `0x180066de0`

## callees

- `0x18000caa0`
- `0x18000ccf0`
- `0x1800425e0`
- `0x180059f74`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x180042a5d`
- `ntdll!NtQueryVolumeInformationFile` at `0x180042a5d`
- `ntdll!NtRaiseHardError` at `0x1800429da`
- `ntdll!NtRaiseHardError` at `0x1800429da`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004299d`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004299d`
- `ntdll!RtlFreeUnicodeString` at `0x1800429ed`
- `ntdll!RtlFreeUnicodeString` at `0x1800429ed`
- `ntdll!RtlSetLastWin32Error` at `0x1800426d4`
- `ntdll!RtlSetLastWin32Error` at `0x18004270e`
- `ntdll!RtlSetLastWin32Error` at `0x1800426d4`
- `ntdll!RtlSetLastWin32Error` at `0x18004270e`
- `ntdll!RtlInitAnsiString` at `0x180042981`
- `ntdll!RtlInitAnsiString` at `0x180042981`
- `ntdll!RtlGetThreadErrorMode` at `0x18004291c`
- `ntdll!RtlGetThreadErrorMode` at `0x18004291c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042b6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042b6e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800426f9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800427f4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800426f9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800427f4`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180042aba`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180042aba`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180042884`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x180042884`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800428dd`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800428dd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18004284c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18004284c`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x1800427ce`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x1800427ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetErrorMode` at `0x180042906`
- `api-ms-win-core-errorhandling-l1-1-0!GetErrorMode` at `0x180042906`

## pseudocode

```c
HFILE __stdcall OpenFile(LPCSTR lpFileName, LPOFSTRUCT lpReOpenBuff, UINT uStyle)
{
  int v6; // r13d
  __m128i v7; // xmm6
  __int128 v8; // xmm7
  __int128 v9; // xmm8
  __int128 v10; // xmm9
  __int128 v11; // xmm10
  __int128 v12; // xmm11
  __int128 v13; // xmm12
  __int128 v14; // xmm13
  ULONG v15; // ecx
  void *v16; // rdi
  DWORD v17; // r15d
  DWORD v18; // edx
  int v19; // r8d
  DWORD v20; // r9d
  UINT v21; // eax
  DWORD v22; // ecx
  DWORD v23; // eax
  DWORD FullPathNameA; // eax
  DWORD FileAttributesA; // eax
  HANDLE FileA; // rax
  ULONG LastErrorValue; // eax
  NTSTATUS v28; // ebx
  NTSTATUS v29; // ebx
  NTSTATUS v30; // ebx
  WORD *p_Reserved2; // r15
  WORD *p_Reserved1; // rbx
  ULONG Response; // [rsp+40h] [rbp-1A8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-1A0h] BYREF
  DWORD v36; // [rsp+58h] [rbp-190h]
  DWORD v37; // [rsp+5Ch] [rbp-18Ch]
  UINT v38; // [rsp+60h] [rbp-188h]
  LPSTR FilePart; // [rsp+68h] [rbp-180h] BYREF
  __int64 FsInformation; // [rsp+70h] [rbp-178h] BYREF
  unsigned __int64 Parameters; // [rsp+78h] [rbp-170h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp-168h] BYREF
  __int64 v43; // [rsp+88h] [rbp-160h]
  struct _STRING DestinationString; // [rsp+90h] [rbp-158h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-148h] BYREF
  _OWORD v46[8]; // [rsp+B0h] [rbp-138h] BYREF
  __int64 v47; // [rsp+130h] [rbp-B8h]
  DWORD v48; // [rsp+208h] [rbp+20h]

  LastWriteTime = 0;
  FilePart = 0;
  IoStatusBlock = 0;
  FsInformation = 0;
  v6 = 0;
  v7 = *(__m128i *)&lpReOpenBuff->cBytes;
  v46[0] = *(_OWORD *)&lpReOpenBuff->cBytes;
  v8 = *(_OWORD *)&lpReOpenBuff->szPathName[8];
  v46[1] = v8;
  v9 = *(_OWORD *)&lpReOpenBuff->szPathName[24];
  v46[2] = v9;
  v10 = *(_OWORD *)&lpReOpenBuff->szPathName[40];
  v46[3] = v10;
  v11 = *(_OWORD *)&lpReOpenBuff->szPathName[56];
  v46[4] = v11;
  v12 = *(_OWORD *)&lpReOpenBuff->szPathName[72];
  v46[5] = v12;
  v13 = *(_OWORD *)&lpReOpenBuff->szPathName[88];
  v46[6] = v13;
  v14 = *(_OWORD *)&lpReOpenBuff->szPathName[104];
  v46[7] = v14;
  v43 = *(_QWORD *)&lpReOpenBuff->szPathName[120];
  v47 = v43;
  RtlSetLastWin32Error(0);
  if ( (uStyle & 0x100) == 0 )
  {
    v17 = (uStyle & 1) != 0 ? 0x40000000 : 0x80000000;
    v37 = v17;
    if ( (uStyle & 2) != 0 )
    {
      v17 |= 0xC0000000;
      v37 = v17;
    }
    v18 = BasepOfShareToWin32Share(uStyle);
    v36 = v18;
    v21 = uStyle & 0x1000;
    Response = v21;
    if ( (uStyle & 0x1000) != 0 )
      v17 = v20;
    v37 = v17;
    v22 = 3 - (v21 != 0);
    v48 = v22;
    if ( (uStyle & 0x8000) == 0 )
    {
      v23 = SearchPathA(0, lpFileName, 0, 0x7Fu, lpReOpenBuff->szPathName, &FilePart);
      if ( v23 > 0x7F )
        goto LABEL_3;
      if ( !v23 )
      {
        FullPathNameA = GetFullPathNameA(lpFileName, 0x7Fu, lpReOpenBuff->szPathName, &FilePart);
        if ( !FullPathNameA )
          goto LABEL_3;
        v6 = 1;
        if ( FullPathNameA > 0x7F )
          goto LABEL_3;
      }
      v19 = 2;
      v18 = v36;
      v22 = v48;
      v21 = Response;
    }
    v38 = uStyle & 0x4000;
    if ( (uStyle & 0x4000) == 0 || v21 )
    {
      if ( (uStyle & 0x200) != 0 )
      {
        if ( !DeleteFileA(lpReOpenBuff->szPathName) )
        {
          lpReOpenBuff->nErrCode = 2;
          goto LABEL_5;
        }
        lpReOpenBuff->nErrCode = 0;
        lpReOpenBuff->cBytes = -120;
        LODWORD(v16) = 1;
        *(_QWORD *)&UnicodeString.Length = 1;
        goto LABEL_59;
      }
      while ( 1 )
      {
        FileA = CreateFileA(lpReOpenBuff->szPathName, v17, v18, 0, v22, 0, 0);
        v16 = FileA;
        *(_QWORD *)&UnicodeString.Length = FileA;
        if ( FileA != (HANDLE)-1LL )
          break;
        if ( (uStyle & 0x2000) == 0 || (GetErrorMode() & 0x8000) != 0 || (RtlGetThreadErrorMode() & 0x40) != 0 )
          goto LABEL_59;
        Parameters = 0;
        Response = 0;
        DestinationString = 0;
        UnicodeString = 0;
        LastErrorValue = NtCurrentTeb()->LastErrorValue;
        if ( LastErrorValue == 2 )
        {
          v28 = -805306353;
        }
        else
        {
          if ( LastErrorValue != 3 )
            goto LABEL_59;
          v28 = -805306310;
        }
        RtlInitAnsiString(&DestinationString, lpReOpenBuff->szPathName);
        if ( RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u) < 0 )
          goto LABEL_59;
        Parameters = (unsigned __int64)&UnicodeString;
        v29 = NtRaiseHardError(v28, 1u, 1u, &Parameters, 3u, &Response);
        RtlFreeUnicodeString(&UnicodeString);
        if ( v29 < 0 || Response != 7 )
          goto LABEL_59;
        v22 = v48;
        v18 = v36;
      }
      if ( !v38 )
      {
        v30 = NtQueryVolumeInformationFile(FileA, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
        if ( v30 < 0 )
        {
          CloseHandle(v16);
          BaseSetLastNTError((unsigned int)v30);
          goto LABEL_5;
        }
        lpReOpenBuff->fFixedDisk = ((_DWORD)FsInformation == 7 || (_DWORD)FsInformation == 8)
                                && (FsInformation & 0x100000000LL) == 0;
        p_Reserved2 = &lpReOpenBuff->Reserved2;
        p_Reserved1 = &lpReOpenBuff->Reserved1;
        if ( !GetFileTime(v16, 0, 0, &LastWriteTime)
          || !FileTimeToDosDateTime(&LastWriteTime, &lpReOpenBuff->Reserved1, &lpReOpenBuff->Reserved2) )
        {
          *p_Reserved1 = 0;
          *p_Reserved2 = 0;
        }
        lpReOpenBuff->cBytes = -120;
        if ( (uStyle & 0x400) != 0
          && ((unsigned __int16)_mm_extract_epi16(v7, 2) != *p_Reserved1
           || (unsigned __int16)_mm_extract_epi16(v7, 3) != *p_Reserved2
           || strcmp((const char *)v46 + 8, lpReOpenBuff->szPathName)) )
        {
          *(__m128i *)&lpReOpenBuff->cBytes = v7;
          *(_OWORD *)&lpReOpenBuff->szPathName[8] = v8;
          *(_OWORD *)&lpReOpenBuff->szPathName[24] = v9;
          *(_OWORD *)&lpReOpenBuff->szPathName[40] = v10;
          *(_OWORD *)&lpReOpenBuff->szPathName[56] = v11;
          *(_OWORD *)&lpReOpenBuff->szPathName[72] = v12;
          *(_OWORD *)&lpReOpenBuff->szPathName[88] = v13;
          *(_OWORD *)&lpReOpenBuff->szPathName[104] = v14;
          *(_QWORD *)&lpReOpenBuff->szPathName[120] = v43;
          CloseHandle(v16);
          LODWORD(v16) = -1;
          goto LABEL_58;
        }
        goto LABEL_59;
      }
      CloseHandle(FileA);
    }
    else
    {
      if ( v6 )
      {
        v15 = v19;
        goto LABEL_4;
      }
      FileAttributesA = GetFileAttributesA(lpReOpenBuff->szPathName);
      if ( FileAttributesA == -1 )
      {
        v15 = 2;
        goto LABEL_4;
      }
      if ( (FileAttributesA & 0x10) != 0 )
      {
        v15 = 5;
        goto LABEL_4;
      }
    }
    LODWORD(v16) = 1;
    *(_QWORD *)&UnicodeString.Length = 1;
    lpReOpenBuff->cBytes = -120;
    goto LABEL_59;
  }
  if ( GetFullPathNameA(lpFileName, 0x7Fu, lpReOpenBuff->szPathName, &FilePart) > 0x7F )
  {
LABEL_3:
    v15 = 13;
LABEL_4:
    RtlSetLastWin32Error(v15);
LABEL_5:
    LODWORD(v16) = -1;
LABEL_58:
    *(_QWORD *)&UnicodeString.Length = -1;
    goto LABEL_59;
  }
  *(_QWORD *)&lpReOpenBuff->cBytes = 392;
  LODWORD(v16) = 0;
  *(_QWORD *)&UnicodeString.Length = 0;
LABEL_59:
  lpReOpenBuff->nErrCode = NtCurrentTeb()->LastErrorValue;
  return (int)v16;
}

```

## disassembly

```asm
0x1800425e0  mov     rax, rsp
0x1800425e3  mov     [rax+8], rbx
0x1800425e7  mov     [rax+18h], rsi
0x1800425eb  mov     [rax+10h], rdx
0x1800425ef  push    rdi
0x1800425f0  push    r12
0x1800425f2  push    r13
0x1800425f4  push    r14
0x1800425f6  push    r15
0x1800425f8  sub     rsp, 1C0h
0x1800425ff  movaps  xmmword ptr [rax-38h], xmm6
0x180042603  movaps  xmmword ptr [rax-48h], xmm7
0x180042607  movaps  xmmword ptr [rax-58h], xmm8
0x18004260c  movaps  xmmword ptr [rax-68h], xmm9
0x180042611  movaps  xmmword ptr [rax-78h], xmm10
0x180042616  movaps  xmmword ptr [rax-88h], xmm11
0x18004261e  movaps  xmmword ptr [rax-98h], xmm12
0x180042626  movaps  xmmword ptr [rax-0A8h], xmm13
0x18004262e  mov     r12d, r8d
0x180042631  mov     rsi, rdx
0x180042634  mov     rdi, rcx
0x180042637  xor     r15d, r15d
0x18004263a  mov     [rax-168h], r15
0x180042641  mov     [rsp+1E8h+FilePart], r15
0x180042646  xorps   xmm0, xmm0
0x180042649  movups  xmmword ptr [rax-148h], xmm0
0x180042650  mov     [rsp+1E8h+FsInformation], r15
0x180042655  mov     r13d, r15d
0x180042658  movups  xmm6, xmmword ptr [rdx]
0x18004265b  movaps  xmmword ptr [rax-138h], xmm6
0x180042662  movups  xmm7, xmmword ptr [rdx+10h]
0x180042666  movaps  xmmword ptr [rax-128h], xmm7
0x18004266d  movups  xmm8, xmmword ptr [rdx+20h]
0x180042672  movaps  xmmword ptr [rax-118h], xmm8
0x18004267a  movups  xmm9, xmmword ptr [rdx+30h]
0x18004267f  movaps  xmmword ptr [rax-108h], xmm9
0x180042687  movups  xmm10, xmmword ptr [rdx+40h]
0x18004268c  movaps  xmmword ptr [rax-0F8h], xmm10
0x180042694  movups  xmm11, xmmword ptr [rdx+50h]
0x180042699  movaps  xmmword ptr [rax-0E8h], xmm11
0x1800426a1  movups  xmm12, xmmword ptr [rdx+60h]
0x1800426a6  movaps  xmmword ptr [rax-0D8h], xmm12
0x1800426ae  movups  xmm13, xmmword ptr [rdx+70h]
0x1800426b3  movaps  xmmword ptr [rax-0C8h], xmm13
0x1800426bb  mov     rax, [rdx+80h]
0x1800426c2  mov     [rsp+1E8h+var_160], rax
0x1800426ca  mov     [rsp+1E8h+var_B8], rax
0x1800426d2  xor     ecx, ecx; LastError
0x1800426d4  call    cs:__imp_RtlSetLastWin32Error
0x1800426db  nop     dword ptr [rax+rax+00h]
0x1800426e0  bt      r12d, 8
0x1800426e5  jnb     short loc_18004273A
0x1800426e7  lea     r8, [rsi+8]; lpBuffer
0x1800426eb  lea     r9, [rsp+1E8h+FilePart]; lpFilePart
0x1800426f0  lea     ebx, [r15+7Fh]
0x1800426f4  mov     edx, ebx; nBufferLength
0x1800426f6  mov     rcx, rdi; lpFileName
0x1800426f9  call    cs:__imp_GetFullPathNameA
0x180042700  nop     dword ptr [rax+rax+00h]
0x180042705  cmp     eax, ebx
0x180042707  jbe     short loc_180042726
0x180042709  mov     ecx, 0Dh; LastError
0x18004270e  call    cs:__imp_RtlSetLastWin32Error
0x180042715  nop     dword ptr [rax+rax+00h]
0x18004271a  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180042721  jmp     loc_180042B7E
0x180042726  mov     qword ptr [rsi], 188h
0x18004272d  mov     rdi, r15
0x180042730  mov     qword ptr [rsp+1E8h+UnicodeString.Length], r15
0x180042735  jmp     loc_180042B83
0x18004273a  mov     al, r12b
0x18004273d  mov     r14d, 1
0x180042743  and     al, r14b
0x180042746  neg     al
0x180042748  sbb     r15d, r15d
0x18004274b  mov     r9d, 0C0000000h
0x180042751  and     r15d, r9d
0x180042754  add     r15d, 80000000h
0x18004275b  mov     [rsp+1E8h+var_18C], r15d
0x180042760  lea     r8d, [r14+1]
0x180042764  test    r8b, r12b
0x180042767  jz      short loc_180042771
0x180042769  or      r15d, r9d
0x18004276c  mov     [rsp+1E8h+var_18C], r15d
0x180042771  mov     ecx, r12d
0x180042774  call    BasepOfShareToWin32Share
0x180042779  mov     edx, eax
0x18004277b  mov     [rsp+1E8h+var_190], eax
0x18004277f  mov     eax, r12d
0x180042782  and     eax, 1000h
0x180042787  mov     [rsp+1E8h+Response], eax
0x18004278b  cmovnz  r15d, r9d
0x18004278f  mov     [rsp+1E8h+var_18C], r15d
0x180042794  mov     ecx, eax
0x180042796  neg     ecx
0x180042798  sbb     ecx, ecx
0x18004279a  add     ecx, 3
0x18004279d  mov     [rsp+1E8h+arg_18], ecx
0x1800427a4  bt      r12d, 0Fh
0x1800427a9  jb      short loc_180042828
0x1800427ab  lea     rax, [rsi+8]
0x1800427af  lea     rcx, [rsp+1E8h+FilePart]
0x1800427b4  mov     [rsp+1E8h+lpFilePart], rcx; lpFilePart
0x1800427b9  mov     [rsp+1E8h+lpBuffer], rax; lpBuffer
0x1800427be  mov     ebx, 7Fh
0x1800427c3  mov     r9d, ebx; nBufferLength
0x1800427c6  xor     r8d, r8d; lpExtension
0x1800427c9  mov     rdx, rdi; lpFileName
0x1800427cc  xor     ecx, ecx; lpPath
0x1800427ce  call    cs:__imp_SearchPathA
0x1800427d5  nop     dword ptr [rax+rax+00h]
0x1800427da  cmp     eax, ebx
0x1800427dc  ja      loc_180042709
0x1800427e2  test    eax, eax
0x1800427e4  jnz     short loc_180042813
0x1800427e6  lea     r9, [rsp+1E8h+FilePart]; lpFilePart
0x1800427eb  lea     r8, [rsi+8]; lpBuffer
0x1800427ef  mov     edx, ebx; nBufferLength
0x1800427f1  mov     rcx, rdi; lpFileName
0x1800427f4  call    cs:__imp_GetFullPathNameA
0x1800427fb  nop     dword ptr [rax+rax+00h]
0x180042800  test    eax, eax
0x180042802  jz      loc_180042709
0x180042808  mov     r13d, r14d
0x18004280b  cmp     eax, ebx
0x18004280d  ja      loc_180042709
0x180042813  mov     r8d, 2
0x180042819  mov     edx, [rsp+1E8h+var_190]
0x18004281d  mov     ecx, [rsp+1E8h+arg_18]
0x180042824  mov     eax, [rsp+1E8h+Response]
0x180042828  mov     ebx, r12d
0x18004282b  and     ebx, 4000h
0x180042831  mov     [rsp+1E8h+var_188], ebx
0x180042835  jz      short loc_180042879
0x180042837  test    eax, eax
0x180042839  jnz     short loc_180042879
0x18004283b  test    r13d, r13d
0x18004283e  jz      short loc_180042848
0x180042840  mov     ecx, r8d
0x180042843  jmp     loc_18004270E
0x180042848  lea     rcx, [rsi+8]; lpFileName
0x18004284c  call    cs:__imp_GetFileAttributesA
0x180042853  nop     dword ptr [rax+rax+00h]
0x180042858  cmp     eax, 0FFFFFFFFh
0x18004285b  jnz     short loc_180042867
0x18004285d  mov     ecx, 2
0x180042862  jmp     loc_18004270E
0x180042867  test    al, 10h
0x180042869  jz      loc_180042A32
0x18004286f  mov     ecx, 5
0x180042874  jmp     loc_18004270E
0x180042879  bt      r12d, 9
0x18004287e  jnb     short loc_1800428B8
0x180042880  lea     rcx, [rsi+8]; lpFileName
0x180042884  call    cs:__imp_DeleteFileA
0x18004288b  nop     dword ptr [rax+rax+00h]
0x180042890  test    eax, eax
0x180042892  jz      short loc_1800428AA
0x180042894  xor     eax, eax
0x180042896  mov     [rsi+2], ax
0x18004289a  mov     byte ptr [rsi], 88h
0x18004289d  mov     rdi, r14
0x1800428a0  mov     qword ptr [rsp+1E8h+UnicodeString.Length], r14
0x1800428a5  jmp     loc_180042B83
0x1800428aa  mov     eax, 2
0x1800428af  mov     [rsi+2], ax
0x1800428b3  jmp     loc_18004271A
0x1800428b8  lea     r13, [rsi+8]
0x1800428bc  mov     [rsp+1E8h+hTemplateFile], 0; hTemplateFile
0x1800428c5  mov     dword ptr [rsp+1E8h+lpFilePart], 0; dwFlagsAndAttributes
0x1800428cd  mov     dword ptr [rsp+1E8h+lpBuffer], ecx; dwCreationDisposition
0x1800428d1  xor     r9d, r9d; lpSecurityAttributes
0x1800428d4  mov     r8d, edx; dwShareMode
0x1800428d7  mov     edx, r15d; dwDesiredAccess
0x1800428da  mov     rcx, r13; lpFileName
0x1800428dd  call    cs:__imp_CreateFileA
0x1800428e4  nop     dword ptr [rax+rax+00h]
0x1800428e9  mov     rdi, rax
0x1800428ec  mov     qword ptr [rsp+1E8h+UnicodeString.Length], rax
0x1800428f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800428f5  jnz     loc_180042A1C
0x1800428fb  bt      r12d, 0Dh
0x180042900  jnb     loc_180042B83
0x180042906  call    cs:__imp_GetErrorMode
0x18004290d  nop     dword ptr [rax+rax+00h]
0x180042912  bt      eax, 0Fh
0x180042916  jb      loc_180042B83
0x18004291c  call    cs:__imp_RtlGetThreadErrorMode
0x180042923  nop     dword ptr [rax+rax+00h]
0x180042928  test    al, 40h
0x18004292a  jnz     loc_180042B83
0x180042930  mov     [rsp+1E8h+Parameters], 0
0x180042939  mov     [rsp+1E8h+Response], 0
0x180042941  xorps   xmm0, xmm0
0x180042944  movups  xmmword ptr [rsp+1E8h+DestinationString.Length], xmm0
0x18004294c  xorps   xmm1, xmm1
0x18004294f  movups  xmmword ptr [rsp+1E8h+UnicodeString.Length], xmm1
0x180042954  mov     eax, gs:68h
0x18004295c  cmp     eax, 2
0x18004295f  jnz     short loc_180042968
0x180042961  mov     ebx, 0D000000Fh
0x180042966  jmp     short loc_180042976
0x180042968  cmp     eax, 3
0x18004296b  jnz     loc_180042B83
0x180042971  mov     ebx, 0D000003Ah
0x180042976  mov     rdx, r13; SourceString
0x180042979  lea     rcx, [rsp+1E8h+DestinationString]; DestinationString
0x180042981  call    cs:__imp_RtlInitAnsiString
0x180042988  nop     dword ptr [rax+rax+00h]
0x18004298d  mov     r8b, r14b; AllocateDestinationString
0x180042990  lea     rdx, [rsp+1E8h+DestinationString]; SourceString
0x180042998  lea     rcx, [rsp+1E8h+UnicodeString]; DestinationString
0x18004299d  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800429a4  nop     dword ptr [rax+rax+00h]
0x1800429a9  test    eax, eax
0x1800429ab  js      loc_180042B83
0x1800429b1  lea     rax, [rsp+1E8h+UnicodeString]
0x1800429b6  mov     [rsp+1E8h+Parameters], rax
0x1800429bb  lea     rax, [rsp+1E8h+Response]
0x1800429c0  mov     [rsp+1E8h+lpFilePart], rax; Response
0x1800429c5  mov     dword ptr [rsp+1E8h+lpBuffer], 3; ValidResponseOptions
0x1800429cd  lea     r9, [rsp+1E8h+Parameters]; Parameters
0x1800429d2  mov     r8d, r14d; UnicodeStringParameterMask
0x1800429d5  mov     edx, r14d; NumberOfParameters
0x1800429d8  mov     ecx, ebx; ErrorStatus
0x1800429da  call    cs:__imp_NtRaiseHardError
0x1800429e1  nop     dword ptr [rax+rax+00h]
0x1800429e6  mov     ebx, eax
0x1800429e8  lea     rcx, [rsp+1E8h+UnicodeString]; UnicodeString
0x1800429ed  call    cs:__imp_RtlFreeUnicodeString
0x1800429f4  nop     dword ptr [rax+rax+00h]
0x1800429f9  test    ebx, ebx
0x1800429fb  js      loc_180042B83
0x180042a01  cmp     [rsp+1E8h+Response], 7
0x180042a06  jnz     loc_180042B83
0x180042a0c  mov     ecx, [rsp+1E8h+arg_18]
0x180042a13  mov     edx, [rsp+1E8h+var_190]
0x180042a17  jmp     loc_1800428B8
0x180042a1c  mov     rcx, rdi; FileHandle
0x180042a1f  cmp     [rsp+1E8h+var_188], 0
0x180042a24  jz      short loc_180042A42
0x180042a26  call    cs:__imp_CloseHandle
0x180042a2d  nop     dword ptr [rax+rax+00h]
0x180042a32  mov     rdi, r14
0x180042a35  mov     qword ptr [rsp+1E8h+UnicodeString.Length], r14
0x180042a3a  mov     byte ptr [rsi], 88h
0x180042a3d  jmp     loc_180042B83
0x180042a42  mov     dword ptr [rsp+1E8h+lpBuffer], 4; FsInformationClass
0x180042a4a  mov     r9d, 8; Length
0x180042a50  lea     r8, [rsp+1E8h+FsInformation]; FsInformation
0x180042a55  lea     rdx, [rsp+1E8h+IoStatusBlock]; IoStatusBlock
0x180042a5d  call    cs:__imp_NtQueryVolumeInformationFile
0x180042a64  nop     dword ptr [rax+rax+00h]
0x180042a69  mov     ebx, eax
0x180042a6b  test    eax, eax
0x180042a6d  jns     short loc_180042A8A
0x180042a6f  mov     rcx, rdi; hObject
0x180042a72  call    cs:__imp_CloseHandle
0x180042a79  nop     dword ptr [rax+rax+00h]
0x180042a7e  mov     ecx, ebx
0x180042a80  call    BaseSetLastNTError
0x180042a85  jmp     loc_18004271A
0x180042a8a  mov     eax, dword ptr [rsp+1E8h+FsInformation]
0x180042a8e  sub     eax, 7
0x180042a91  jz      short loc_180042A9E
0x180042a93  cmp     eax, r14d
0x180042a96  jz      short loc_180042A9E
0x180042a98  mov     byte ptr [rsi+1], 0
0x180042a9c  jmp     short loc_180042AAA
0x180042a9e  mov     al, byte ptr [rsp+1E8h+FsInformation+4]
0x180042aa2  not     al
0x180042aa4  and     al, r14b
0x180042aa7  mov     [rsi+1], al
0x180042aaa  lea     r9, [rsp+1E8h+LastWriteTime]; lpLastWriteTime
0x180042ab2  xor     r8d, r8d; lpLastAccessTime
0x180042ab5  xor     edx, edx; lpCreationTime
0x180042ab7  mov     rcx, rdi; hFile
0x180042aba  call    cs:__imp_GetFileTime
0x180042ac1  nop     dword ptr [rax+rax+00h]
0x180042ac6  lea     r15, [rsi+6]
0x180042aca  lea     rbx, [rsi+4]
0x180042ace  test    eax, eax
0x180042ad0  jz      short loc_180042AE9
0x180042ad2  mov     r8, r15; lpFatTime
0x180042ad5  mov     rdx, rbx; lpFatDate
0x180042ad8  lea     rcx, [rsp+1E8h+LastWriteTime]; lpFileTime
0x180042ae0  call    FileTimeToDosDateTime
0x180042ae5  test    eax, eax
0x180042ae7  jnz     short loc_180042AF2
0x180042ae9  xor     eax, eax
0x180042aeb  mov     [rbx], ax
0x180042aee  mov     [r15], ax
0x180042af2  mov     byte ptr [rsi], 88h
0x180042af5  bt      r12d, 0Ah
0x180042afa  jnb     loc_180042B83
0x180042b00  pextrw  eax, xmm6, 2
0x180042b05  cmp     ax, [rbx]
0x180042b08  jnz     short loc_180042B37
0x180042b0a  pextrw  eax, xmm6, 3
0x180042b0f  cmp     ax, [r15]
  ... truncated ...
```
