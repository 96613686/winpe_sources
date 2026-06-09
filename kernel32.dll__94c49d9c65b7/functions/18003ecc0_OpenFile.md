# OpenFile

- ea: `0x18003ecc0`
- end: `0x18003f240`
- name: `OpenFile`
- size: `1408`
- prototype: `HFILE __stdcall(LPCSTR lpFileName, LPOFSTRUCT lpReOpenBuff, UINT uStyle)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180050230`
- `0x180060600`

## callees

- `0x18000f700`
- `0x18000f920`
- `0x18003ecc0`
- `0x180055ef0`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x18003f0e3`
- `ntdll!NtQueryVolumeInformationFile` at `0x18003f0e3`
- `ntdll!NtRaiseHardError` at `0x18003f072`
- `ntdll!NtRaiseHardError` at `0x18003f072`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003f03b`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18003f03b`
- `ntdll!RtlFreeUnicodeString` at `0x18003f07f`
- `ntdll!RtlFreeUnicodeString` at `0x18003f07f`
- `ntdll!RtlSetLastWin32Error` at `0x18003edb4`
- `ntdll!RtlSetLastWin32Error` at `0x18003ede2`
- `ntdll!RtlSetLastWin32Error` at `0x18003edb4`
- `ntdll!RtlSetLastWin32Error` at `0x18003ede2`
- `ntdll!RtlInitAnsiString` at `0x18003f025`
- `ntdll!RtlInitAnsiString` at `0x18003f025`
- `ntdll!RtlGetThreadErrorMode` at `0x18003efc6`
- `ntdll!RtlGetThreadErrorMode` at `0x18003efc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f1de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f1de`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18003edd3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18003eebc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18003edd3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18003eebc`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18003f134`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18003f134`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18003ef40`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x18003ef40`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003ef93`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18003ef93`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18003ef0e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18003ef0e`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x18003ee9c`
- `api-ms-win-core-processenvironment-l1-2-0!SearchPathA` at `0x18003ee9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetErrorMode` at `0x18003efb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetErrorMode` at `0x18003efb6`

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
0x18003ecc0  mov     rax, rsp
0x18003ecc3  mov     [rax+8], rbx
0x18003ecc7  mov     [rax+18h], rsi
0x18003eccb  mov     [rax+10h], rdx
0x18003eccf  push    rdi
0x18003ecd0  push    r12
0x18003ecd2  push    r13
0x18003ecd4  push    r14
0x18003ecd6  push    r15
0x18003ecd8  sub     rsp, 1C0h
0x18003ecdf  movaps  xmmword ptr [rax-38h], xmm6
0x18003ece3  movaps  xmmword ptr [rax-48h], xmm7
0x18003ece7  movaps  xmmword ptr [rax-58h], xmm8
0x18003ecec  movaps  xmmword ptr [rax-68h], xmm9
0x18003ecf1  movaps  xmmword ptr [rax-78h], xmm10
0x18003ecf6  movaps  xmmword ptr [rax-88h], xmm11
0x18003ecfe  movaps  xmmword ptr [rax-98h], xmm12
0x18003ed06  movaps  xmmword ptr [rax-0A8h], xmm13
0x18003ed0e  mov     r12d, r8d
0x18003ed11  mov     rsi, rdx
0x18003ed14  mov     rdi, rcx
0x18003ed17  xor     r15d, r15d
0x18003ed1a  mov     [rax-168h], r15
0x18003ed21  mov     [rsp+1E8h+FilePart], r15
0x18003ed26  xorps   xmm0, xmm0
0x18003ed29  movups  xmmword ptr [rax-148h], xmm0
0x18003ed30  mov     [rsp+1E8h+FsInformation], r15
0x18003ed35  mov     r13d, r15d
0x18003ed38  movups  xmm6, xmmword ptr [rdx]
0x18003ed3b  movaps  xmmword ptr [rax-138h], xmm6
0x18003ed42  movups  xmm7, xmmword ptr [rdx+10h]
0x18003ed46  movaps  xmmword ptr [rax-128h], xmm7
0x18003ed4d  movups  xmm8, xmmword ptr [rdx+20h]
0x18003ed52  movaps  xmmword ptr [rax-118h], xmm8
0x18003ed5a  movups  xmm9, xmmword ptr [rdx+30h]
0x18003ed5f  movaps  xmmword ptr [rax-108h], xmm9
0x18003ed67  movups  xmm10, xmmword ptr [rdx+40h]
0x18003ed6c  movaps  xmmword ptr [rax-0F8h], xmm10
0x18003ed74  movups  xmm11, xmmword ptr [rdx+50h]
0x18003ed79  movaps  xmmword ptr [rax-0E8h], xmm11
0x18003ed81  movups  xmm12, xmmword ptr [rdx+60h]
0x18003ed86  movaps  xmmword ptr [rax-0D8h], xmm12
0x18003ed8e  movups  xmm13, xmmword ptr [rdx+70h]
0x18003ed93  movaps  xmmword ptr [rax-0C8h], xmm13
0x18003ed9b  mov     rax, [rdx+80h]
0x18003eda2  mov     [rsp+1E8h+var_160], rax
0x18003edaa  mov     [rsp+1E8h+var_B8], rax
0x18003edb2  xor     ecx, ecx; LastError
0x18003edb4  call    cs:__imp_RtlSetLastWin32Error
0x18003edba  bt      r12d, 8
0x18003edbf  jnb     short loc_18003EE08
0x18003edc1  lea     r8, [rsi+8]; lpBuffer
0x18003edc5  lea     r9, [rsp+1E8h+FilePart]; lpFilePart
0x18003edca  lea     ebx, [r15+7Fh]
0x18003edce  mov     edx, ebx; nBufferLength
0x18003edd0  mov     rcx, rdi; lpFileName
0x18003edd3  call    cs:__imp_GetFullPathNameA
0x18003edd9  cmp     eax, ebx
0x18003eddb  jbe     short loc_18003EDF4
0x18003eddd  mov     ecx, 0Dh; LastError
0x18003ede2  call    cs:__imp_RtlSetLastWin32Error
0x18003ede8  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18003edef  jmp     loc_18003F1E8
0x18003edf4  mov     qword ptr [rsi], 188h
0x18003edfb  mov     rdi, r15
0x18003edfe  mov     qword ptr [rsp+1E8h+UnicodeString.Length], r15
0x18003ee03  jmp     loc_18003F1ED
0x18003ee08  mov     al, r12b
0x18003ee0b  mov     r14d, 1
0x18003ee11  and     al, r14b
0x18003ee14  neg     al
0x18003ee16  sbb     r15d, r15d
0x18003ee19  mov     r9d, 0C0000000h
0x18003ee1f  and     r15d, r9d
0x18003ee22  add     r15d, 80000000h
0x18003ee29  mov     [rsp+1E8h+var_18C], r15d
0x18003ee2e  lea     r8d, [r14+1]
0x18003ee32  test    r8b, r12b
0x18003ee35  jz      short loc_18003EE3F
0x18003ee37  or      r15d, r9d
0x18003ee3a  mov     [rsp+1E8h+var_18C], r15d
0x18003ee3f  mov     ecx, r12d
0x18003ee42  call    BasepOfShareToWin32Share
0x18003ee47  mov     edx, eax
0x18003ee49  mov     [rsp+1E8h+var_190], eax
0x18003ee4d  mov     eax, r12d
0x18003ee50  and     eax, 1000h
0x18003ee55  mov     [rsp+1E8h+Response], eax
0x18003ee59  cmovnz  r15d, r9d
0x18003ee5d  mov     [rsp+1E8h+var_18C], r15d
0x18003ee62  mov     ecx, eax
0x18003ee64  neg     ecx
0x18003ee66  sbb     ecx, ecx
0x18003ee68  add     ecx, 3
0x18003ee6b  mov     [rsp+1E8h+arg_18], ecx
0x18003ee72  bt      r12d, 0Fh
0x18003ee77  jb      short loc_18003EEEA
0x18003ee79  lea     rax, [rsi+8]
0x18003ee7d  lea     rcx, [rsp+1E8h+FilePart]
0x18003ee82  mov     [rsp+1E8h+lpFilePart], rcx; lpFilePart
0x18003ee87  mov     [rsp+1E8h+lpBuffer], rax; lpBuffer
0x18003ee8c  mov     ebx, 7Fh
0x18003ee91  mov     r9d, ebx; nBufferLength
0x18003ee94  xor     r8d, r8d; lpExtension
0x18003ee97  mov     rdx, rdi; lpFileName
0x18003ee9a  xor     ecx, ecx; lpPath
0x18003ee9c  call    cs:__imp_SearchPathA
0x18003eea2  cmp     eax, ebx
0x18003eea4  ja      loc_18003EDDD
0x18003eeaa  test    eax, eax
0x18003eeac  jnz     short loc_18003EED5
0x18003eeae  lea     r9, [rsp+1E8h+FilePart]; lpFilePart
0x18003eeb3  lea     r8, [rsi+8]; lpBuffer
0x18003eeb7  mov     edx, ebx; nBufferLength
0x18003eeb9  mov     rcx, rdi; lpFileName
0x18003eebc  call    cs:__imp_GetFullPathNameA
0x18003eec2  test    eax, eax
0x18003eec4  jz      loc_18003EDDD
0x18003eeca  mov     r13d, r14d
0x18003eecd  cmp     eax, ebx
0x18003eecf  ja      loc_18003EDDD
0x18003eed5  mov     r8d, 2
0x18003eedb  mov     edx, [rsp+1E8h+var_190]
0x18003eedf  mov     ecx, [rsp+1E8h+arg_18]
0x18003eee6  mov     eax, [rsp+1E8h+Response]
0x18003eeea  mov     ebx, r12d
0x18003eeed  and     ebx, 4000h
0x18003eef3  mov     [rsp+1E8h+var_188], ebx
0x18003eef7  jz      short loc_18003EF35
0x18003eef9  test    eax, eax
0x18003eefb  jnz     short loc_18003EF35
0x18003eefd  test    r13d, r13d
0x18003ef00  jz      short loc_18003EF0A
0x18003ef02  mov     ecx, r8d
0x18003ef05  jmp     loc_18003EDE2
0x18003ef0a  lea     rcx, [rsi+8]; lpFileName
0x18003ef0e  call    cs:__imp_GetFileAttributesA
0x18003ef14  cmp     eax, 0FFFFFFFFh
0x18003ef17  jnz     short loc_18003EF23
0x18003ef19  mov     ecx, 2
0x18003ef1e  jmp     loc_18003EDE2
0x18003ef23  test    al, 10h
0x18003ef25  jz      loc_18003F0B8
0x18003ef2b  mov     ecx, 5
0x18003ef30  jmp     loc_18003EDE2
0x18003ef35  bt      r12d, 9
0x18003ef3a  jnb     short loc_18003EF6E
0x18003ef3c  lea     rcx, [rsi+8]; lpFileName
0x18003ef40  call    cs:__imp_DeleteFileA
0x18003ef46  test    eax, eax
0x18003ef48  jz      short loc_18003EF60
0x18003ef4a  xor     eax, eax
0x18003ef4c  mov     [rsi+2], ax
0x18003ef50  mov     byte ptr [rsi], 88h
0x18003ef53  mov     rdi, r14
0x18003ef56  mov     qword ptr [rsp+1E8h+UnicodeString.Length], r14
0x18003ef5b  jmp     loc_18003F1ED
0x18003ef60  mov     eax, 2
0x18003ef65  mov     [rsi+2], ax
0x18003ef69  jmp     loc_18003EDE8
0x18003ef6e  lea     r13, [rsi+8]
0x18003ef72  mov     [rsp+1E8h+hTemplateFile], 0; hTemplateFile
0x18003ef7b  mov     dword ptr [rsp+1E8h+lpFilePart], 0; dwFlagsAndAttributes
0x18003ef83  mov     dword ptr [rsp+1E8h+lpBuffer], ecx; dwCreationDisposition
0x18003ef87  xor     r9d, r9d; lpSecurityAttributes
0x18003ef8a  mov     r8d, edx; dwShareMode
0x18003ef8d  mov     edx, r15d; dwDesiredAccess
0x18003ef90  mov     rcx, r13; lpFileName
0x18003ef93  call    cs:__imp_CreateFileA
0x18003ef99  mov     rdi, rax
0x18003ef9c  mov     qword ptr [rsp+1E8h+UnicodeString.Length], rax
0x18003efa1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003efa5  jnz     loc_18003F0A8
0x18003efab  bt      r12d, 0Dh
0x18003efb0  jnb     loc_18003F1ED
0x18003efb6  call    cs:__imp_GetErrorMode
0x18003efbc  bt      eax, 0Fh
0x18003efc0  jb      loc_18003F1ED
0x18003efc6  call    cs:__imp_RtlGetThreadErrorMode
0x18003efcc  test    al, 40h
0x18003efce  jnz     loc_18003F1ED
0x18003efd4  mov     [rsp+1E8h+Parameters], 0
0x18003efdd  mov     [rsp+1E8h+Response], 0
0x18003efe5  xorps   xmm0, xmm0
0x18003efe8  movups  xmmword ptr [rsp+1E8h+DestinationString.Length], xmm0
0x18003eff0  xorps   xmm1, xmm1
0x18003eff3  movups  xmmword ptr [rsp+1E8h+UnicodeString.Length], xmm1
0x18003eff8  mov     eax, gs:68h
0x18003f000  cmp     eax, 2
0x18003f003  jnz     short loc_18003F00C
0x18003f005  mov     ebx, 0D000000Fh
0x18003f00a  jmp     short loc_18003F01A
0x18003f00c  cmp     eax, 3
0x18003f00f  jnz     loc_18003F1ED
0x18003f015  mov     ebx, 0D000003Ah
0x18003f01a  mov     rdx, r13; SourceString
0x18003f01d  lea     rcx, [rsp+1E8h+DestinationString]; DestinationString
0x18003f025  call    cs:__imp_RtlInitAnsiString
0x18003f02b  mov     r8b, r14b; AllocateDestinationString
0x18003f02e  lea     rdx, [rsp+1E8h+DestinationString]; SourceString
0x18003f036  lea     rcx, [rsp+1E8h+UnicodeString]; DestinationString
0x18003f03b  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18003f041  test    eax, eax
0x18003f043  js      loc_18003F1ED
0x18003f049  lea     rax, [rsp+1E8h+UnicodeString]
0x18003f04e  mov     [rsp+1E8h+Parameters], rax
0x18003f053  lea     rax, [rsp+1E8h+Response]
0x18003f058  mov     [rsp+1E8h+lpFilePart], rax; Response
0x18003f05d  mov     dword ptr [rsp+1E8h+lpBuffer], 3; ValidResponseOptions
0x18003f065  lea     r9, [rsp+1E8h+Parameters]; Parameters
0x18003f06a  mov     r8d, r14d; UnicodeStringParameterMask
0x18003f06d  mov     edx, r14d; NumberOfParameters
0x18003f070  mov     ecx, ebx; ErrorStatus
0x18003f072  call    cs:__imp_NtRaiseHardError
0x18003f078  mov     ebx, eax
0x18003f07a  lea     rcx, [rsp+1E8h+UnicodeString]; UnicodeString
0x18003f07f  call    cs:__imp_RtlFreeUnicodeString
0x18003f085  test    ebx, ebx
0x18003f087  js      loc_18003F1ED
0x18003f08d  cmp     [rsp+1E8h+Response], 7
0x18003f092  jnz     loc_18003F1ED
0x18003f098  mov     ecx, [rsp+1E8h+arg_18]
0x18003f09f  mov     edx, [rsp+1E8h+var_190]
0x18003f0a3  jmp     loc_18003EF6E
0x18003f0a8  mov     rcx, rdi; FileHandle
0x18003f0ab  cmp     [rsp+1E8h+var_188], 0
0x18003f0b0  jz      short loc_18003F0C8
0x18003f0b2  call    cs:__imp_CloseHandle
0x18003f0b8  mov     rdi, r14
0x18003f0bb  mov     qword ptr [rsp+1E8h+UnicodeString.Length], r14
0x18003f0c0  mov     byte ptr [rsi], 88h
0x18003f0c3  jmp     loc_18003F1ED
0x18003f0c8  mov     dword ptr [rsp+1E8h+lpBuffer], 4; FsInformationClass
0x18003f0d0  mov     r9d, 8; Length
0x18003f0d6  lea     r8, [rsp+1E8h+FsInformation]; FsInformation
0x18003f0db  lea     rdx, [rsp+1E8h+IoStatusBlock]; IoStatusBlock
0x18003f0e3  call    cs:__imp_NtQueryVolumeInformationFile
0x18003f0e9  mov     ebx, eax
0x18003f0eb  test    eax, eax
0x18003f0ed  jns     short loc_18003F104
0x18003f0ef  mov     rcx, rdi; hObject
0x18003f0f2  call    cs:__imp_CloseHandle
0x18003f0f8  mov     ecx, ebx
0x18003f0fa  call    BaseSetLastNTError
0x18003f0ff  jmp     loc_18003EDE8
0x18003f104  mov     eax, dword ptr [rsp+1E8h+FsInformation]
0x18003f108  sub     eax, 7
0x18003f10b  jz      short loc_18003F118
0x18003f10d  cmp     eax, r14d
0x18003f110  jz      short loc_18003F118
0x18003f112  mov     byte ptr [rsi+1], 0
0x18003f116  jmp     short loc_18003F124
0x18003f118  mov     al, byte ptr [rsp+1E8h+FsInformation+4]
0x18003f11c  not     al
0x18003f11e  and     al, r14b
0x18003f121  mov     [rsi+1], al
0x18003f124  lea     r9, [rsp+1E8h+LastWriteTime]; lpLastWriteTime
0x18003f12c  xor     r8d, r8d; lpLastAccessTime
0x18003f12f  xor     edx, edx; lpCreationTime
0x18003f131  mov     rcx, rdi; hFile
0x18003f134  call    cs:__imp_GetFileTime
0x18003f13a  lea     r15, [rsi+6]
0x18003f13e  lea     rbx, [rsi+4]
0x18003f142  test    eax, eax
0x18003f144  jz      short loc_18003F15D
0x18003f146  mov     r8, r15; lpFatTime
0x18003f149  mov     rdx, rbx; lpFatDate
0x18003f14c  lea     rcx, [rsp+1E8h+LastWriteTime]; lpFileTime
0x18003f154  call    FileTimeToDosDateTime
0x18003f159  test    eax, eax
0x18003f15b  jnz     short loc_18003F166
0x18003f15d  xor     eax, eax
0x18003f15f  mov     [rbx], ax
0x18003f162  mov     [r15], ax
0x18003f166  mov     byte ptr [rsi], 88h
0x18003f169  bt      r12d, 0Ah
0x18003f16e  jnb     short loc_18003F1ED
0x18003f170  pextrw  eax, xmm6, 2
0x18003f175  cmp     ax, [rbx]
0x18003f178  jnz     short loc_18003F1A7
0x18003f17a  pextrw  eax, xmm6, 3
0x18003f17f  cmp     ax, [r15]
0x18003f183  jnz     short loc_18003F1A7
0x18003f185  lea     rax, [rsp+1E8h+var_130]
0x18003f18d  sub     r13, rax
0x18003f190  movzx   ecx, byte ptr [rax]
0x18003f193  movzx   edx, byte ptr [rax+r13]
0x18003f198  sub     ecx, edx
0x18003f19a  jnz     short loc_18003F1A3
0x18003f19c  add     rax, r14
0x18003f19f  test    edx, edx
0x18003f1a1  jnz     short loc_18003F190
0x18003f1a3  test    ecx, ecx
0x18003f1a5  jz      short loc_18003F1ED
0x18003f1a7  movups  xmmword ptr [rsi], xmm6
0x18003f1aa  movups  xmmword ptr [rsi+10h], xmm7
0x18003f1ae  movups  xmmword ptr [rsi+20h], xmm8
0x18003f1b3  movups  xmmword ptr [rsi+30h], xmm9
0x18003f1b8  movups  xmmword ptr [rsi+40h], xmm10
0x18003f1bd  movups  xmmword ptr [rsi+50h], xmm11
  ... truncated ...
```
