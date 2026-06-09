# CJob::SaveP(ushort const *,int,ulong)

- ea: `0x180004590`
- end: `0x1800051cb`
- name: `?SaveP@CJob@@QEAAJPEBGHK@Z`
- size: `3131`
- prototype: `__int64 __fastcall(CJob *__hidden this, const unsigned __int16 *, int, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180004190`
- `0x180004220`

## callees

- `0x180001840`
- `0x180004590`
- `0x180007640`
- `0x180009b1c`
- `0x180009ef8`
- `0x180009f38`
- `0x18001aa82`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cba`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004b1c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004c2b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800050d9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004b1c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004c2b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800050d9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004682`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004682`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000469d`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000469d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180004cfe`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180004cfe`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180005100`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180005100`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180004c04`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180004c04`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180004d34`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180004d34`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800051b6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800051b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e50`
- `SspiCli!GetUserNameExW` at `0x180004d76`
- `SspiCli!GetUserNameExW` at `0x180004d76`
- `SHELL32!SHChangeNotify` at `0x180005120`
- `SHELL32!SHChangeNotify` at `0x180005149`
- `SHELL32!SHChangeNotify` at `0x180005120`
- `SHELL32!SHChangeNotify` at `0x180005149`

## pseudocode

```c
signed int __fastcall CJob::SaveP(CJob *this, const unsigned __int16 *a2, int a3, DWORD a4)
{
  char v4; // r12
  CJob *v6; // r13
  LPCWSTR *v7; // rbx
  const unsigned __int16 *v8; // r15
  bool v9; // zf
  const WCHAR *v10; // rcx
  DWORD v11; // edi
  _DWORD *v12; // rsi
  HANDLE FileW; // rax
  HANDLE v14; // rdi
  __int64 v15; // r14
  int v16; // ecx
  signed int v17; // ebx
  int v18; // r8d
  int v19; // eax
  int v20; // edx
  int v21; // ecx
  int v22; // ecx
  __int128 v23; // xmm0
  DWORD v24; // esi
  __int128 v25; // xmm0
  __m256i *p_Buffer; // rdi
  _WORD *v27; // rcx
  __int64 v28; // rax
  unsigned __int16 v29; // ax
  int v30; // edx
  _WORD *v31; // rcx
  __int64 v32; // rax
  unsigned __int16 v33; // ax
  int v34; // r8d
  _WORD *v35; // rcx
  __int64 v36; // rax
  unsigned __int16 v37; // ax
  int v38; // edx
  _WORD *v39; // rcx
  __int64 v40; // rax
  unsigned __int16 v41; // ax
  int v42; // r8d
  _WORD *v43; // rcx
  __int64 v44; // rax
  unsigned __int16 v45; // ax
  unsigned __int16 v46; // cx
  __int64 v47; // r12
  int v48; // edx
  DWORD v49; // eax
  char *v50; // rax
  char *v51; // rbx
  unsigned int v52; // r14d
  unsigned int v53; // r15d
  unsigned int v54; // r14d
  char *v55; // rbx
  __int64 v56; // rax
  _QWORD *v57; // rcx
  char *v58; // rbx
  unsigned int v59; // r14d
  unsigned int v60; // r14d
  char *v61; // rbx
  __int64 v62; // rax
  unsigned int v63; // r14d
  char *v64; // rcx
  unsigned int v65; // r14d
  __int64 v66; // rbx
  _WORD *v67; // r15
  HANDLE v68; // r12
  signed int v69; // eax
  int v70; // esi
  const unsigned __int16 *v71; // rbx
  void **v72; // rdi
  signed int result; // eax
  DWORD v74; // r13d
  signed int LastError; // eax
  signed int v76; // eax
  unsigned __int16 *v77; // rax
  unsigned int v78; // r14d
  __int64 v79; // r13
  char *v80; // rbx
  unsigned int v81; // r14d
  char *v82; // rbx
  __int64 v83; // rax
  unsigned int v84; // r14d
  _WORD *v85; // rcx
  _OWORD *v86; // rax
  __int64 v87; // rcx
  unsigned __int16 *v88; // rax
  int v89; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h]
  __int64 Src; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v92; // [rsp+58h] [rbp-A8h]
  HANDLE hFile; // [rsp+60h] [rbp-A0h]
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwCreationDisposition; // [rsp+6Ch] [rbp-94h]
  CJob *v96; // [rsp+70h] [rbp-90h]
  LPCVOID *v97; // [rsp+78h] [rbp-88h]
  DWORD nNumberOfBytesToWrite; // [rsp+80h] [rbp-80h]
  int v99; // [rsp+84h] [rbp-7Ch]
  LPCVOID dwItem1; // [rsp+88h] [rbp-78h]
  __int64 v101; // [rsp+90h] [rbp-70h]
  __m256i Buffer; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v103; // [rsp+C0h] [rbp-40h]
  _BYTE v104[22]; // [rsp+D0h] [rbp-30h]
  __int16 v105; // [rsp+E6h] [rbp-1Ah]
  _OWORD FileInformation[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v107; // [rsp+110h] [rbp+10h]
  WCHAR NameBuffer[264]; // [rsp+120h] [rbp+20h] BYREF

  NumberOfBytesWritten = a4;
  v4 = a4;
  v99 = a3;
  dwItem1 = a2;
  v6 = this;
  v96 = this;
  v7 = (LPCWSTR *)((char *)this + 152);
  if ( a2 )
  {
    v8 = a2;
    lpFileName = a2;
  }
  else
  {
    v8 = *v7;
    lpFileName = *v7;
    if ( !*v7 )
      return -2147024809;
  }
  v9 = *v8 == 0;
  v97 = (LPCVOID *)((char *)this + 152);
  if ( v9 )
    return -2147024809;
  v10 = *v7;
  if ( v8 != *v7 || (v12 = (_DWORD *)((char *)v6 + 160), !*((_DWORD *)v6 + 40)) )
  {
    if ( (a4 & 1) != 0 )
    {
      v9 = (*((_DWORD *)v6 + 22) & 0x200) == 0;
      dwCreationDisposition = 1;
      v11 = 2;
      if ( v9 )
        v11 = 128;
      v4 = a4 | 2;
      NumberOfBytesWritten = a4 | 2;
      GenerateUniqueID((struct _GUID *)((char *)v6 + 44));
      v12 = (_DWORD *)((char *)v6 + 160);
      goto LABEL_9;
    }
    return -2147024809;
  }
  memset(FileInformation, 0, sizeof(FileInformation));
  v107 = 0;
  if ( !GetFileAttributesExW(v10, GetFileExInfoStandard, FileInformation) )
    goto LABEL_103;
  dwCreationDisposition = 3;
  v11 = FileInformation[0] & 0xFFFFFFFC | 2;
  if ( (*((_DWORD *)v6 + 22) & 0x200) == 0 )
    v11 = FileInformation[0] & 0xFFFFFFFE;
  if ( v11 != LODWORD(FileInformation[0]) )
    SetFileAttributesW(*v7, v11);
LABEL_9:
  FileW = CreateFileW(v8, 0x40000000u, 5u, 0, dwCreationDisposition, v11 | 0x8000000, 0);
  hFile = FileW;
  v14 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileType(FileW) != 1 )
    {
      CloseHandle(v14);
      return -2147024891;
    }
    if ( a3 || v8 == *v7 )
      *v12 = 1;
    v15 = -1;
    if ( !*((_QWORD *)v6 + 17) )
    {
      LODWORD(Src) = 257;
      if ( GetUserNameExW(NameSamCompatible, NameBuffer, (PULONG)&Src) )
      {
        v77 = (unsigned __int16 *)operator new(saturated_mul((unsigned int)(Src + 1), 2u));
        *((_QWORD *)v6 + 17) = v77;
        if ( !v77 )
          goto LABEL_98;
        StringCchCopyW(v77, (unsigned int)(Src + 1), NameBuffer);
      }
    }
    v16 = *((_DWORD *)v6 + 22);
    v17 = 0;
    v18 = *((_DWORD *)v6 + 21);
    v19 = 0;
    if ( (v16 & 4) != 0 )
    {
      v20 = 267009;
      if ( v18 != 267009 )
      {
        v20 = 267010;
        *((_DWORD *)v6 + 21) = 267010;
      }
    }
    else
    {
      v20 = 267010;
      if ( v18 == 267010 )
        v19 = 1;
      else
        v20 = *((_DWORD *)v6 + 21);
    }
    if ( v16 < 0 )
      v19 = 1;
    if ( (v16 & 0x10000000) != 0 )
    {
      *((_DWORD *)v6 + 22) = v16 & 0xCFFFFFFF;
    }
    else if ( !v19 )
    {
LABEL_21:
      v21 = *((_DWORD *)v6 + 22);
      if ( (v21 & 0x10000) != 0 )
      {
        GenerateUniqueID((struct _GUID *)((char *)v6 + 44));
        *((_DWORD *)v6 + 22) &= ~0x10000u;
        v21 = *((_DWORD *)v6 + 22);
        v20 = *((_DWORD *)v6 + 21);
      }
      if ( (v4 & 4) == 0 )
      {
        v21 &= ~0x200000u;
        *((_DWORD *)v6 + 22) = v21;
      }
      v22 = v21 & 0x3FFDFFFF;
      v23 = *(_OWORD *)((char *)v6 + 44);
      Buffer.m256i_i16[0] = *((_WORD *)v6 + 20);
      v24 = 70;
      Buffer.m256i_i16[1] = *((_WORD *)v6 + 21);
      *(__int32 *)((char *)&Buffer.m256i_i32[5] + 2) = *((_DWORD *)v6 + 15);
      Buffer.m256i_i16[13] = *((_WORD *)v6 + 32);
      Buffer.m256i_i16[15] = *((_WORD *)v6 + 34);
      Buffer.m256i_i16[14] = *((_WORD *)v6 + 35);
      *(_QWORD *)&v103 = *((_QWORD *)v6 + 9);
      DWORD2(v103) = *((_DWORD *)v6 + 20);
      *(_WORD *)&v104[20] = *((_WORD *)v6 + 33);
      Buffer.m256i_i16[10] = 70;
      if ( (v4 & 3) == 0 )
        v24 = 68;
      *(_OWORD *)((char *)Buffer.m256i_i64 + 4) = v23;
      v105 = 0;
      v25 = *((_OWORD *)v6 + 6);
      HIDWORD(v103) = v20;
      v89 = v4 & 1;
      *(_DWORD *)v104 = v22;
      *(_OWORD *)&v104[4] = v25;
      if ( (v4 & 1) == 0 )
      {
        p_Buffer = &Buffer;
        goto LABEL_153;
      }
      v27 = *(_WORD **)((char *)v6 + CJob::s_StringField[0]);
      if ( v27 && *v27 )
      {
        v28 = -1;
        do
          ++v28;
        while ( v27[v28] );
        v29 = v28 + 1;
      }
      else
      {
        v29 = 0;
      }
      v30 = v29;
      LOWORD(Src) = v29;
      v31 = *(_WORD **)((char *)v6 + dword_180023654);
      if ( v31 && *v31 )
      {
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        v33 = v32 + 1;
      }
      else
      {
        v33 = 0;
      }
      WORD1(Src) = v33;
      v34 = v33 + v30;
      v35 = *(_WORD **)((char *)v6 + dword_180023658);
      if ( v35 && *v35 )
      {
        v36 = -1;
        do
          ++v36;
        while ( v35[v36] );
        v37 = v36 + 1;
      }
      else
      {
        v37 = 0;
      }
      WORD2(Src) = v37;
      v38 = v37 + v34;
      v39 = *(_WORD **)((char *)v6 + dword_18002365C);
      if ( v39 && *v39 )
      {
        v40 = -1;
        do
          ++v40;
        while ( v39[v40] );
        v41 = v40 + 1;
      }
      else
      {
        v41 = 0;
      }
      HIWORD(Src) = v41;
      v42 = v41 + v38;
      v43 = *(_WORD **)((char *)v6 + dword_180023660);
      if ( v43 && *v43 )
      {
        v44 = -1;
        do
          ++v44;
        while ( v43[v44] );
        v45 = v44 + 1;
      }
      else
      {
        v45 = 0;
      }
      v46 = *((_WORD *)v6 + 89);
      v92 = v45;
      if ( v46 < 8u )
      {
        *((_WORD *)v6 + 89) = 8;
        v46 = 8;
      }
      v47 = *((unsigned __int16 *)v6 + 16);
      v48 = v46 + 14 + *((unsigned __int16 *)v6 + 88) + v24 + 2 * (v42 + v45);
      *((_WORD *)v6 + 30) = v48;
      v101 = (unsigned int)(48 * v47);
      Buffer.m256i_i16[11] = v48;
      v49 = v48 + v101 + 2 + 68;
      if ( !*((_QWORD *)v6 + 26) )
        v49 = v48 + v101 + 2;
      v24 = v49;
      v50 = (char *)operator new(v49);
      p_Buffer = (__m256i *)v50;
      if ( v50 )
      {
        if ( v24 < 0x46 )
        {
          v68 = hFile;
          v17 = -2147418113;
          goto LABEL_77;
        }
        *(_OWORD *)v50 = *(_OWORD *)Buffer.m256i_i8;
        v51 = v50 + 70;
        nNumberOfBytesToWrite = v24 - 70;
        v52 = v24 - 70;
        *((_OWORD *)v50 + 1) = *(_OWORD *)&Buffer.m256i_u64[2];
        v53 = 0;
        *((_OWORD *)v50 + 2) = v103;
        *((_OWORD *)v50 + 3) = *(_OWORD *)v104;
        *(_QWORD *)(v50 + 62) = *(_QWORD *)&v104[14];
        while ( v53 < 5 )
        {
          if ( v52 < 2
            || (v78 = v52 - 2,
                v79 = *((unsigned __int16 *)&Src + (int)v53),
                *(_WORD *)v51 = v79,
                2 * v79 > (unsigned __int64)v78) )
          {
            v6 = v96;
            v17 = -2147418113;
            v8 = lpFileName;
            v15 = -1;
            v68 = hFile;
            goto LABEL_77;
          }
          v80 = v51 + 2;
          memcpy_0(v80, *(const void **)((char *)v96 + CJob::s_StringField[v53]), 2 * v79);
          v51 = &v80[2 * v79];
          v52 = v78 - 2 * v79;
          ++v53;
        }
        v6 = v96;
        if ( v52 < 2 )
        {
          v8 = lpFileName;
          v17 = -2147418113;
          v68 = hFile;
          v15 = -1;
          goto LABEL_77;
        }
        v54 = v52 - 2;
        *(_WORD *)v51 = *((_WORD *)v96 + 88);
        if ( *((unsigned __int16 *)v6 + 88) > v54 )
        {
          v8 = lpFileName;
          v17 = -2147418113;
          v68 = hFile;
          v15 = -1;
          goto LABEL_77;
        }
        v55 = v51 + 2;
        memcpy_0(v55, *((const void **)v6 + 21), *((unsigned __int16 *)v6 + 88));
        v56 = *((unsigned __int16 *)v6 + 88);
        v57 = (_QWORD *)*((_QWORD *)v6 + 23);
        v58 = &v55[v56];
        v59 = v54 - v56;
        LODWORD(Src) = *((_DWORD *)v6 + 48);
        HIDWORD(Src) = *((_DWORD *)v6 + 23);
        if ( v57 )
        {
          *v57 = Src;
          if ( v59 < 2 )
          {
            v8 = lpFileName;
            v17 = -2147418113;
            v68 = hFile;
            v15 = -1;
            goto LABEL_77;
          }
          v81 = v59 - 2;
          *(_WORD *)v58 = *((_WORD *)v6 + 89);
          if ( *((unsigned __int16 *)v6 + 89) > v81 )
          {
            v8 = lpFileName;
            v17 = -2147418113;
            v68 = hFile;
            v15 = -1;
            goto LABEL_77;
          }
          v82 = v58 + 2;
          memcpy_0(v82, *((const void **)v6 + 23), *((unsigned __int16 *)v6 + 89));
          v83 = *((unsigned __int16 *)v6 + 89);
          v63 = v81 - v83;
          v64 = &v82[v83];
        }
        else
        {
          *((_WORD *)v6 + 89) = 8;
          if ( v59 < 2 )
          {
            v8 = lpFileName;
            v17 = -2147418113;
            v68 = hFile;
            v15 = -1;
            goto LABEL_77;
          }
          *(_WORD *)v58 = 8;
          v60 = v59 - 2;
          if ( *((unsigned __int16 *)v6 + 89) > v60 )
          {
            v8 = lpFileName;
            v17 = -2147418113;
            v68 = hFile;
            v15 = -1;
            goto LABEL_77;
          }
          v61 = v58 + 2;
          memcpy_0(v61, &Src, *((unsigned __int16 *)v6 + 89));
          v62 = *((unsigned __int16 *)v6 + 89);
          v63 = v60 - v62;
          v64 = &v61[v62];
          *((_WORD *)v6 + 89) = 0;
        }
        if ( v63 < 2 )
        {
          v8 = lpFileName;
          v17 = -2147418113;
          v68 = hFile;
          v15 = -1;
          goto LABEL_77;
        }
        v65 = v63 - 2;
        *(_WORD *)v64 = v47;
        v66 = 24 * v47;
        if ( 48 * v47 > (unsigned __int64)v65 )
        {
          v8 = lpFileName;
          v17 = -2147418113;
          v68 = hFile;
          v15 = -1;
          goto LABEL_77;
        }
        v67 = v64 + 2;
        memcpy_0(v64 + 2, *((const void **)v6 + 3), 48 * v47);
        if ( *((_QWORD *)v6 + 26) )
        {
          v84 = v65 - v101;
          LODWORD(Src) = 65537;
          if ( v84 < 4 )
          {
            v8 = lpFileName;
            v17 = -2147418113;
            v68 = hFile;
            v15 = -1;
            goto LABEL_77;
          }
          v85 = &v67[v66];
          *(_DWORD *)&v67[v66] = Src;
          if ( v84 - 4 < 0x40 )
          {
            v8 = lpFileName;
            v17 = -2147418113;
            v68 = hFile;
            v15 = -1;
            goto LABEL_77;
          }
          v86 = (_OWORD *)*((_QWORD *)v6 + 26);
          *(_OWORD *)(v85 + 2) = *v86;
          *(_OWORD *)(v85 + 10) = v86[1];
          *(_OWORD *)(v85 + 18) = v86[2];
          *(_OWORD *)(v85 + 26) = v86[3];
        }
        v17 = 0;
        if ( (NumberOfBytesWritten & 2) == 0 )
        {
          v68 = hFile;
          LODWORD(Src) = 0;
          if ( WriteFile(hFile, p_Buffer, 0x44u, (LPDWORD)&Src, 0)
            && (_DWORD)Src == 68
            && SetFilePointer(v68, 2, 0, 1u) != -1 )
          {
            v74 = nNumberOfBytesToWrite;
            if ( WriteFile(v68, &p_Buffer[2].m256i_u16[3], nNumberOfBytesToWrite, (LPDWORD)&Src, 0)
              && (_DWORD)Src == v74 )
            {
              v6 = v96;
              v15 = -1;
              v8 = lpFileName;
              goto LABEL_155;
            }
            LastError = GetLastError();
            v17 = LastError;
            if ( LastError > 0 )
              v17 = (unsigned __int16)LastError | 0x80070000;
            v6 = v96;
            v15 = -1;
            v8 = lpFileName;
          }
          else
          {
            v69 = GetLastError();
            v17 = v69;
            if ( v69 > 0 )
              v17 = (unsigned __int16)v69 | 0x80070000;
            v8 = lpFileName;
            v15 = -1;
          }
LABEL_77:
          v70 = v89;
          goto LABEL_78;
        }
        v8 = lpFileName;
        v15 = -1;
LABEL_153:
        v68 = hFile;
        NumberOfBytesWritten = 0;
        if ( WriteFile(hFile, p_Buffer, v24, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v24 )
        {
LABEL_155:
          v70 = v89;
          if ( v89 )
            SetEndOfFile(v68);
LABEL_78:
          CloseHandle(v68);
          if ( p_Buffer != &Buffer )
            operator delete(p_Buffer);
          if ( v17 >= 0 )
          {
            v71 = (const unsigned __int16 *)dwItem1;
            if ( NtCurrentPeb()->SessionId )
            {
              if ( !dwItem1 )
              {
                v72 = (void **)v97;
                if ( *v97 )
                  SHChangeNotify(0x2000, 5u, *v97, 0);
                goto LABEL_83;
              }
              SHChangeNotify(2, 5u, dwItem1, 0);
            }
            v72 = (void **)v97;
LABEL_83:
            if ( !v99 )
            {
              if ( v71 )
                return 0;
LABEL_85:
              *((_DWORD *)v6 + 22) &= ~0x40000000u;
              if ( v70 )
                *((_DWORD *)v6 + 22) &= ~0x80000000;
              return 0;
            }
            if ( !v71 )
              goto LABEL_85;
            operator delete(*v72);
            v87 = -1;
            do
              ++v87;
            while ( v71[v87] );
            v88 = (unsigned __int16 *)operator new(saturated_mul(v87 + 1, 2u));
            *v72 = v88;
            if ( v88 )
            {
              do
                v9 = v71[++v15] == 0;
              while ( !v9 );
              StringCchCopyW(v88, v15 + 1, v71);
              goto LABEL_85;
            }
            v17 = -2147024882;
          }
LABEL_100:
          if ( dwCreationDisposition == 1 )
            DeleteFileW(v8);
          return v17;
        }
        v76 = GetLastError();
        v17 = v76;
        if ( v76 > 0 )
          v17 = (unsigned __int16)v76 | 0x80070000;
        goto LABEL_77;
      }
      v14 = hFile;
LABEL_98:
      v17 = -2147024882;
      if ( v14 )
        CloseHandle(v14);
      goto LABEL_100;
    }
    CJob::UpdateJobState(v6, v20);
    v20 = *((_DWORD *)v6 + 21);
    goto LABEL_21;
  }
LABEL_103:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004590  mov     [rsp-8+arg_10], rbx
0x180004595  push    rbp
0x180004596  push    rsi
0x180004597  push    rdi
0x180004598  push    r12
0x18000459a  push    r13
0x18000459c  push    r14
0x18000459e  push    r15
0x1800045a0  lea     rbp, [rsp-240h]
0x1800045a8  sub     rsp, 340h
0x1800045af  mov     rax, cs:__security_cookie
0x1800045b6  xor     rax, rsp
0x1800045b9  mov     [rbp+270h+var_40], rax
0x1800045c0  mov     [rsp+370h+NumberOfBytesWritten], r9d
0x1800045c5  mov     r12d, r9d
0x1800045c8  mov     [rbp+270h+var_2EC], r8d
0x1800045cc  mov     r14d, r8d
0x1800045cf  mov     [rbp+270h+dwItem1], rdx
0x1800045d3  mov     r13, rcx
0x1800045d6  mov     [rsp+370h+var_300], rcx
0x1800045db  lea     rbx, [rcx+98h]
0x1800045e2  test    rdx, rdx
0x1800045e5  jnz     loc_1800047E3
0x1800045eb  mov     r15, [rbx]
0x1800045ee  mov     [rsp+370h+lpFileName], r15
0x1800045f3  test    r15, r15
0x1800045f6  jz      loc_1800051C1
0x1800045fc  cmp     word ptr [r15], 0
0x180004601  mov     [rsp+370h+var_2F8], rbx
0x180004606  jz      loc_1800051C1
0x18000460c  mov     rcx, [rbx]; lpFileName
0x18000460f  cmp     r15, rcx
0x180004612  jz      loc_180004CD8
0x180004618  test    r12b, 1
0x18000461c  jz      loc_1800051C1
0x180004622  test    dword ptr [r13+58h], 200h
0x18000462a  lea     rcx, [r13+2Ch]; struct _GUID *
0x18000462e  mov     eax, 80h
0x180004633  mov     [rsp+370h+var_304], 1
0x18000463b  mov     edi, 2
0x180004640  cmovz   edi, eax
0x180004643  or      r12d, 2
0x180004647  mov     [rsp+370h+NumberOfBytesWritten], r12d
0x18000464c  call    ?GenerateUniqueID@@YAXPEAU_GUID@@@Z; GenerateUniqueID(_GUID *)
0x180004651  lea     rsi, [r13+0A0h]
0x180004658  mov     eax, [rsp+370h+var_304]
0x18000465c  bts     edi, 1Bh
0x180004660  mov     [rsp+370h+hTemplateFile], 0; hTemplateFile
0x180004669  xor     r9d, r9d; lpSecurityAttributes
0x18000466c  mov     [rsp+370h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180004670  mov     edx, 40000000h; dwDesiredAccess
0x180004675  mov     r8d, 5; dwShareMode
0x18000467b  mov     [rsp+370h+dwCreationDisposition], eax; dwCreationDisposition
0x18000467f  mov     rcx, r15; lpFileName
0x180004682  call    cs:__imp_CreateFileW
0x180004688  mov     [rsp+370h+hFile], rax
0x18000468d  mov     rdi, rax
0x180004690  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004694  jz      loc_180004C89
0x18000469a  mov     rcx, rax; hFile
0x18000469d  call    cs:__imp_GetFileType
0x1800046a3  cmp     eax, 1
0x1800046a6  jnz     loc_180004D3F
0x1800046ac  test    r14d, r14d
0x1800046af  jnz     loc_180004D52
0x1800046b5  cmp     r15, [rbx]
0x1800046b8  jz      loc_180004D52
0x1800046be  mov     r9d, eax
0x1800046c1  cmp     qword ptr [r13+88h], 0
0x1800046c9  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800046d0  jz      loc_180004D60
0x1800046d6  mov     ecx, [r13+58h]
0x1800046da  xor     ebx, ebx
0x1800046dc  mov     r8d, [r13+54h]
0x1800046e0  mov     eax, ebx
0x1800046e2  test    cl, 4
0x1800046e5  jz      loc_180004CA4
0x1800046eb  mov     edx, 41301h
0x1800046f0  cmp     r8d, edx
0x1800046f3  jz      short loc_1800046FE
0x1800046f5  mov     edx, 41302h; int
0x1800046fa  mov     [r13+54h], edx
0x1800046fe  test    ecx, ecx
0x180004700  cmovs   eax, r9d
0x180004704  bt      ecx, 1Ch
0x180004708  jb      loc_180004DCF
0x18000470e  test    eax, eax
0x180004710  jnz     loc_180004DD9
0x180004716  mov     ecx, [r13+58h]
0x18000471a  bt      ecx, 10h
0x18000471e  jb      loc_180004DEA
0x180004724  mov     eax, 2Ch ; ','
0x180004729  mov     r8, r13
0x18000472c  lea     r9, [r13+rax+0]
0x180004731  test    r12b, 4
0x180004735  jz      loc_180004E08
0x18000473b  movzx   eax, word ptr [r13+28h]
0x180004740  and     ecx, 3FFDFFFFh
0x180004746  movups  xmm0, xmmword ptr [r9]
0x18000474a  mov     word ptr [rbp+270h+Buffer], ax
0x18000474e  mov     esi, 46h ; 'F'
0x180004753  movzx   eax, word ptr [r13+2Ah]
0x180004758  test    r12b, 3
0x18000475c  mov     word ptr [rbp+270h+Buffer+2], ax
0x180004760  movzx   eax, word ptr [r13+3Ch]
0x180004765  mov     [rbp+270h+var_2BA], ax
0x180004769  movzx   eax, word ptr [r13+3Eh]
0x18000476e  mov     [rbp+270h+var_2B8], ax
0x180004772  movzx   eax, word ptr [r13+40h]
0x180004777  mov     [rbp+270h+var_2B6], ax
0x18000477b  movzx   eax, word ptr [r13+44h]
0x180004780  mov     [rbp+270h+var_2B2], ax
0x180004784  movzx   eax, word ptr [r13+46h]
0x180004789  mov     [rbp+270h+var_2B4], ax
0x18000478d  mov     eax, [r13+48h]
0x180004791  mov     dword ptr [rbp+270h+var_2B0], eax
0x180004794  mov     eax, [r13+4Ch]
0x180004798  mov     dword ptr [rbp+270h+var_2B0+4], eax
0x18000479b  mov     eax, [r13+50h]
0x18000479f  mov     dword ptr [rbp+270h+var_2B0+8], eax
0x1800047a2  movzx   eax, word ptr [r13+42h]
0x1800047a7  mov     [rbp+270h+var_28C], ax
0x1800047ab  mov     eax, 44h ; 'D'
0x1800047b0  mov     [rbp+270h+var_2BC], si
0x1800047b4  cmovz   esi, eax
0x1800047b7  movups  [rbp+270h+Buffer+4], xmm0
0x1800047bb  mov     eax, r12d
0x1800047be  mov     [rbp+270h+var_28A], bx
0x1800047c2  movups  xmm0, xmmword ptr [r13+60h]
0x1800047c7  and     eax, 1
0x1800047ca  mov     dword ptr [rbp+270h+var_2B0+0Ch], edx
0x1800047cd  mov     [rsp+370h+var_330], eax
0x1800047d1  mov     dword ptr [rbp+270h+var_2A0], ecx
0x1800047d4  movups  [rbp+270h+var_2A0+4], xmm0
0x1800047d8  jnz     short loc_1800047F0
0x1800047da  lea     rdi, [rbp+270h+Buffer]
0x1800047de  jmp     loc_1800050BD
0x1800047e3  mov     r15, rdx
0x1800047e6  mov     [rsp+370h+lpFileName], rdx
0x1800047eb  jmp     loc_1800045FC
0x1800047f0  movsxd  rax, cs:?s_StringField@CJob@@0QBQEQ1@PEAGB; ushort * CJob::* const near * const CJob::s_StringField
0x1800047f7  mov     rcx, [rax+r13]
0x1800047fb  test    rcx, rcx
0x1800047fe  jz      loc_180004E15
0x180004804  cmp     [rcx], bx
0x180004807  jz      loc_180004E15
0x18000480d  mov     rax, r14
0x180004810  inc     rax
0x180004813  cmp     [rcx+rax*2], bx
0x180004817  jnz     short loc_180004810
0x180004819  inc     rax
0x18000481c  movzx   edx, ax
0x18000481f  movsxd  rax, cs:dword_180023654
0x180004826  mov     word ptr [rsp+370h+Src], dx
0x18000482b  mov     rcx, [rax+r13]
0x18000482f  test    rcx, rcx
0x180004832  jz      loc_180004E1D
0x180004838  cmp     [rcx], bx
0x18000483b  jz      loc_180004E1D
0x180004841  mov     rax, r14
0x180004844  inc     rax
0x180004847  cmp     [rcx+rax*2], bx
0x18000484b  jnz     short loc_180004844
0x18000484d  inc     rax
0x180004850  movzx   eax, ax
0x180004853  mov     word ptr [rsp+370h+Src+2], ax
0x180004858  lea     r8d, [rax+rdx]
0x18000485c  movsxd  rax, cs:dword_180023658
0x180004863  mov     rcx, [rax+r13]
0x180004867  test    rcx, rcx
0x18000486a  jz      loc_180004E25
0x180004870  cmp     [rcx], bx
0x180004873  jz      loc_180004E25
0x180004879  mov     rax, r14
0x18000487c  nop     dword ptr [rax+00h]
0x180004880  inc     rax
0x180004883  cmp     [rcx+rax*2], bx
0x180004887  jnz     short loc_180004880
0x180004889  inc     rax
0x18000488c  movzx   eax, ax
0x18000488f  mov     word ptr [rsp+370h+Src+4], ax
0x180004894  lea     edx, [rax+r8]
0x180004898  movsxd  rax, cs:dword_18002365C
0x18000489f  mov     rcx, [rax+r13]
0x1800048a3  test    rcx, rcx
0x1800048a6  jz      loc_180004E2D
0x1800048ac  cmp     [rcx], bx
0x1800048af  jz      loc_180004E2D
0x1800048b5  mov     rax, r14
0x1800048b8  nop     dword ptr [rax+rax+00000000h]
0x1800048c0  inc     rax
0x1800048c3  cmp     [rcx+rax*2], bx
0x1800048c7  jnz     short loc_1800048C0
0x1800048c9  inc     rax
0x1800048cc  movzx   eax, ax
0x1800048cf  mov     word ptr [rsp+370h+Src+6], ax
0x1800048d4  lea     r8d, [rax+rdx]
0x1800048d8  movsxd  rax, cs:dword_180023660
0x1800048df  mov     rcx, [rax+r13]
0x1800048e3  test    rcx, rcx
0x1800048e6  jz      loc_180004E35
0x1800048ec  cmp     [rcx], bx
0x1800048ef  jz      loc_180004E35
0x1800048f5  mov     rax, r14
0x1800048f8  nop     dword ptr [rax+rax+00000000h]
0x180004900  inc     rax
0x180004903  cmp     [rcx+rax*2], bx
0x180004907  jnz     short loc_180004900
0x180004909  inc     rax
0x18000490c  movzx   ecx, word ptr [r13+0B2h]
0x180004914  movzx   eax, ax
0x180004917  mov     [rsp+370h+var_318], ax
0x18000491c  add     eax, r8d
0x18000491f  lea     edx, [rsi+rax*2]
0x180004922  mov     eax, 8
0x180004927  cmp     cx, ax
0x18000492a  jb      loc_180004E3D
0x180004930  movzx   eax, word ptr [r13+0B0h]
0x180004938  movzx   r12d, word ptr [r13+20h]
0x18000493d  add     edx, eax
0x18000493f  movzx   ecx, cx
0x180004942  add     ecx, 0Eh
0x180004945  add     edx, ecx
0x180004947  lea     eax, [r12+r12*2]
0x18000494b  mov     [r13+3Ch], dx
0x180004950  shl     eax, 4
0x180004953  mov     [rbp+270h+var_2E0], rax
0x180004957  mov     [rbp+270h+var_2BA], dx
0x18000495b  lea     ecx, [rax+2]
0x18000495e  add     ecx, edx
0x180004960  cmp     [r13+0D0h], rbx
0x180004967  lea     eax, [rcx+44h]
0x18000496a  cmovz   eax, ecx
0x18000496d  mov     ecx, eax; Size
0x18000496f  mov     esi, eax
0x180004971  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004976  mov     rdi, rax
0x180004979  test    rax, rax
0x18000497c  jz      loc_180004C64
0x180004982  cmp     esi, 46h ; 'F'
0x180004985  jb      loc_180004E5B
0x18000498b  movaps  xmm0, [rbp+270h+Buffer]
0x18000498f  lea     r13d, [rsi-46h]
0x180004993  movups  xmmword ptr [rax], xmm0
0x180004996  lea     rbx, [rax+46h]
0x18000499a  mov     [rbp+270h+nNumberOfBytesToWrite], r13d
0x18000499e  movaps  xmm1, xmmword ptr [rbp-50h]
0x1800049a2  mov     r14d, r13d
0x1800049a5  movups  xmmword ptr [rax+10h], xmm1
0x1800049a9  xor     r15d, r15d
0x1800049ac  movaps  xmm0, [rbp+270h+var_2B0]
0x1800049b0  movups  xmmword ptr [rax+20h], xmm0
0x1800049b4  movaps  xmm1, [rbp+270h+var_2A0]
0x1800049b8  movups  xmmword ptr [rax+30h], xmm1
0x1800049bc  movsd   xmm0, qword ptr [rbp+270h+var_2A0+0Eh]
0x1800049c1  movsd   qword ptr [rax+3Eh], xmm0
0x1800049c6  lea     r8, ?s_StringField@CJob@@0QBQEQ1@PEAGB; ushort * CJob::* const near * const CJob::s_StringField
0x1800049cd  cmp     r15d, 5
0x1800049d1  jb      loc_180004E6A
0x1800049d7  mov     r13, [rsp+370h+var_300]
0x1800049dc  cmp     r14d, 2
0x1800049e0  jb      loc_180004EE1
0x1800049e6  movzx   eax, word ptr [r13+0B0h]
0x1800049ee  add     r14d, 0FFFFFFFEh
0x1800049f2  mov     [rbx], ax
0x1800049f5  movzx   eax, word ptr [r13+0B0h]
0x1800049fd  cmp     eax, r14d
0x180004a00  ja      loc_180004EFC
0x180004a06  mov     rdx, [r13+0A8h]; Src
0x180004a0d  add     rbx, 2
0x180004a11  mov     rcx, rbx; void *
0x180004a14  mov     r8d, eax; Size
0x180004a17  call    memcpy_0
0x180004a1c  movzx   eax, word ptr [r13+0B0h]
0x180004a24  mov     rcx, [r13+0B8h]
0x180004a2b  add     rbx, rax
0x180004a2e  sub     r14d, eax
0x180004a31  mov     eax, [r13+0C0h]
0x180004a38  mov     dword ptr [rsp+370h+Src], eax
0x180004a3c  mov     eax, [r13+5Ch]
0x180004a40  mov     dword ptr [rsp+370h+Src+4], eax
0x180004a44  test    rcx, rcx
0x180004a47  jnz     loc_180004F4D
0x180004a4d  mov     eax, 8
0x180004a52  mov     [r13+0B2h], ax
0x180004a5a  cmp     r14d, 2
0x180004a5e  jb      loc_180004F17
0x180004a64  mov     [rbx], ax
0x180004a67  add     r14d, 0FFFFFFFEh
0x180004a6b  movzx   eax, word ptr [r13+0B2h]
0x180004a73  cmp     eax, r14d
0x180004a76  ja      loc_180004F32
0x180004a7c  add     rbx, 2
0x180004a80  lea     rdx, [rsp+370h+Src]; Src
0x180004a85  mov     rcx, rbx; void *
0x180004a88  mov     r8d, eax; Size
0x180004a8b  call    memcpy_0
0x180004a90  movzx   eax, word ptr [r13+0B2h]
0x180004a98  sub     r14d, eax
0x180004a9b  lea     rcx, [rbx+rax]
  ... truncated ...
```
