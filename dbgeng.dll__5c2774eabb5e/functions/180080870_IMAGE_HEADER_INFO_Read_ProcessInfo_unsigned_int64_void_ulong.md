# IMAGE_HEADER_INFO::Read(ProcessInfo *,unsigned __int64,void *,ulong)

- ea: `0x180080870`
- end: `0x180081911`
- name: `?Read@IMAGE_HEADER_INFO@@QEAAKPEAVProcessInfo@@_KPEAXK@Z`
- size: `4257`
- prototype: `unsigned int __fastcall(IMAGE_HEADER_INFO *__hidden this, struct ProcessInfo *, unsigned __int64, void *, unsigned int)`
- caller_count: `8`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800804c4`
- `0x1800d9bf0`
- `0x18019776c`
- `0x180206450`
- `0x18023be00`
- `0x18023ca8c`
- `0x18028b194`
- `0x1803a55f0`

## callees

- `0x180080870`
- `0x180081918`
- `0x180086560`
- `0x1800879a4`
- `0x1800b94c4`
- `0x1800f0f40`
- `0x18027d540`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180080c6e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180081758`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180080c6e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180081758`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180080d5f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800811b3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800811c8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800817d1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180080d5f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800811b3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800811c8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800817d1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180081219`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180081279`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008135a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800813b9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800814d9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800815eb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180081727`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180081219`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180081279`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008135a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800813b9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800814d9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800815eb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180081727`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800811ed`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18008124c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18008132b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18008138d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800814ab`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800815c2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800816f5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800811ed`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18008124c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18008132b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18008138d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800814ab`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800815c2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800816f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IMAGE_HEADER_INFO::Read(
        IMAGE_HEADER_INFO *this,
        struct ProcessInfo *a2,
        unsigned __int64 a3,
        void *a4,
        __int16 a5)
{
  void *v5; // rsi
  struct ProcessInfo *v7; // r13
  __int64 v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  unsigned __int64 v12; // r15
  unsigned int v13; // ebx
  int v14; // r9d
  int v15; // r12d
  unsigned __int64 v16; // r15
  unsigned int v17; // r8d
  unsigned int v18; // ecx
  unsigned int v19; // r14d
  unsigned __int64 v20; // rcx
  int v21; // eax
  int v22; // edx
  struct _IMAGE_SECTION_HEADER *v23; // rsi
  size_t v24; // r11
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  unsigned int *v27; // r8
  unsigned __int64 v28; // rcx
  struct ImageInfo *ImageByOffset; // rax
  unsigned __int64 v31; // r9
  __int64 v32; // rdx
  unsigned int *v33; // r8
  unsigned __int64 v34; // rcx
  __int64 v35; // rax
  unsigned int *Name; // r8
  unsigned __int64 v37; // rdx
  HANDLE v38; // r10
  unsigned __int64 v39; // r12
  unsigned __int64 v40; // r12
  unsigned __int64 v41; // r13
  DWORD v42; // r15d
  unsigned __int64 v43; // r12
  unsigned __int64 v44; // r12
  unsigned int v45; // r15d
  int v46; // ebx
  unsigned __int64 v47; // rbx
  unsigned int v48; // ecx
  unsigned int v49; // eax
  unsigned __int64 v50; // r15
  unsigned int v51; // edx
  int v52; // r8d
  LONG v53; // edx
  HANDLE v54; // r15
  HANDLE v55; // r15
  unsigned int v56; // eax
  unsigned __int64 v57; // rdx
  __int64 v58; // rax
  HANDLE v59; // r12
  LONG v60; // edx
  int v61; // eax
  unsigned __int64 v62; // r12
  void *v63; // r13
  unsigned __int64 v64; // rdx
  unsigned int ImageData; // edx
  _DWORD *i; // r8
  __int64 v67; // rcx
  unsigned __int64 v68; // rbx
  unsigned int lpOverlapped; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-A8h]
  DWORD nNumberOfBytesToRead[2]; // [rsp+60h] [rbp-A0h]
  struct ProcessInfo *v73; // [rsp+68h] [rbp-98h]
  unsigned __int64 v74; // [rsp+70h] [rbp-90h]
  int v75; // [rsp+78h] [rbp-88h]
  int v76; // [rsp+7Ch] [rbp-84h] BYREF
  int v77; // [rsp+80h] [rbp-80h]
  unsigned int v78; // [rsp+84h] [rbp-7Ch]
  __int64 v79; // [rsp+88h] [rbp-78h]
  __int64 v80; // [rsp+90h] [rbp-70h]
  _OWORD v81[2]; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v82[20]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD Buffer[3]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v84; // [rsp+140h] [rbp+40h]
  _QWORD v85[42]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v86[32]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v80 = -2;
  v5 = a4;
  hFile = a4;
  v74 = a3;
  v7 = a2;
  v73 = a2;
  memset(v86, 0, 0xF8u);
  memset(Buffer, 0, sizeof(Buffer));
  v84 = 0;
  v76 = 17740;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = -1;
  *((_DWORD *)this + 4) = -2;
  *(_QWORD *)((char *)this + 20) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_DWORD *)this + 11) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 16) = -2;
  v9 = *((_QWORD *)this + 16);
  if ( v9 )
  {
    *((_QWORD *)this + 16) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = (void *)*((_QWORD *)this + 12);
  if ( v10 )
  {
    free(v10);
    *((_QWORD *)this + 12) = 0;
  }
  *((_DWORD *)this + 27) = 0;
  v11 = (void *)*((_QWORD *)this + 14);
  if ( v11 )
  {
    free(v11);
    *((_QWORD *)this + 14) = 0;
  }
  *((_DWORD *)this + 30) = 0;
  *((_BYTE *)this + 70) = 0;
  if ( v7 && (ImageByOffset = ProcessInfo::FindImageByOffset(v7, a3, 0, 0)) != 0 && *((_BYTE *)ImageByOffset + 1936) )
  {
    v5 = 0;
  }
  else
  {
    if ( v5 )
    {
      NumberOfBytesRead = 0;
      if ( SetFilePointer(v5, 0, 0, 0) == -1 )
        return *((unsigned int *)this + 2);
      if ( !ReadFile(v5, Buffer, 0x40u, &NumberOfBytesRead, 0) )
        return *((unsigned int *)this + 2);
      v12 = 0;
      if ( NumberOfBytesRead < 0x40 )
        return *((unsigned int *)this + 2);
      goto LABEL_12;
    }
    if ( !v7 )
      return *((unsigned int *)this + 2);
  }
  NumberOfBytesRead = 0;
  if ( (*(unsigned int (__fastcall **)(_QWORD, struct ProcessInfo *, unsigned __int64, _OWORD *, int, DWORD *, _DWORD))(**((_QWORD **)v7 + 11) + 240LL))(
         *((_QWORD *)v7 + 11),
         v7,
         a3,
         Buffer,
         64,
         &NumberOfBytesRead,
         0) )
  {
    return *((unsigned int *)this + 2);
  }
  hFile = 0;
  v12 = a3;
  if ( NumberOfBytesRead < 0x40 )
    return *((unsigned int *)this + 2);
LABEL_12:
  if ( LOWORD(Buffer[0]) == 23117 )
    v12 += SHIDWORD(v84);
  NumberOfBytesRead = 0;
  if ( v5 )
  {
    if ( SetFilePointer(v5, v12, 0, 0) == -1 || !ReadFile(v5, &v76, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead < 4 )
      return *((unsigned int *)this + 2);
  }
  else if ( !v7
         || (*(unsigned int (__fastcall **)(_QWORD, struct ProcessInfo *, unsigned __int64, int *, int, DWORD *, _DWORD))(**((_QWORD **)v7 + 11) + 240LL))(
              *((_QWORD *)v7 + 11),
              v7,
              v12,
              &v76,
              4,
              &NumberOfBytesRead,
              0)
         || NumberOfBytesRead < 4 )
  {
    return *((unsigned int *)this + 2);
  }
  if ( v76 == 17744 )
  {
    NumberOfBytesRead = 0;
    if ( v5 )
    {
      if ( SetFilePointer(v5, v12, 0, 0) == -1
        || !ReadFile(v5, v86, 0xF8u, &NumberOfBytesRead, 0)
        || NumberOfBytesRead < 0xF8 )
      {
        return *((unsigned int *)this + 2);
      }
    }
    else if ( !v7
           || (*(unsigned int (__fastcall **)(_QWORD, struct ProcessInfo *, unsigned __int64, _QWORD *, int, DWORD *, _DWORD))(**((_QWORD **)v7 + 11) + 240LL))(
                *((_QWORD *)v7 + 11),
                v7,
                v12,
                v86,
                248,
                &NumberOfBytesRead,
                0)
           || NumberOfBytesRead < 0xF8 )
    {
      return *((unsigned int *)this + 2);
    }
    v13 = 0;
    v79 = 0;
    v77 = 0;
    v14 = 0;
    v75 = 0;
    v15 = 0;
    if ( LOWORD(v86[3]) == 523 )
    {
      *((_BYTE *)this + 68) = 0;
      memset(v85, 0, 0x108u);
      NumberOfBytesRead = 0;
      if ( v5 )
      {
        if ( SetFilePointer(v5, v12, 0, 0) == -1
          || !ReadFile(v5, v85, 0x108u, &NumberOfBytesRead, 0)
          || NumberOfBytesRead < 0x108 )
        {
          return *((unsigned int *)this + 2);
        }
      }
      else if ( !v7
             || (*(unsigned int (__fastcall **)(_QWORD, struct ProcessInfo *, unsigned __int64, _QWORD *, int, DWORD *, _DWORD))(**((_QWORD **)v7 + 11) + 240LL))(
                  *((_QWORD *)v7 + 11),
                  v7,
                  v12,
                  v85,
                  264,
                  &NumberOfBytesRead,
                  0)
             || NumberOfBytesRead < 0x108 )
      {
        return *((unsigned int *)this + 2);
      }
      v16 = v12 + 264;
      *((_DWORD *)this + 3) = v85[11];
      *((_DWORD *)this + 4) = v85[1];
      *((_DWORD *)this + 5) = v85[10];
      *((_DWORD *)this + 7) = WORD2(v85[8]);
      *((_DWORD *)this + 8) = HIWORD(v85[8]);
      v17 = WORD2(v85[0]);
      *((_DWORD *)this + 9) = WORD2(v85[0]);
      *((_DWORD *)this + 10) = HIDWORD(v85[3]);
      *((_DWORD *)this + 11) = v85[4];
      v18 = HIDWORD(v85[16]);
      if ( HIDWORD(v85[16]) <= 0xE )
      {
        v14 = 0;
      }
      else
      {
        v14 = 1;
        v75 = 1;
        *((_QWORD *)this + 6) = v85[31];
      }
      v19 = HIWORD(v85[0]);
      if ( v18 > 6 )
      {
        v77 = 1;
        v13 = v85[23];
        v79 = v85[23];
      }
      if ( v18 > 0xA )
      {
        v15 = 1;
        *((_QWORD *)this + 7) = v85[27];
      }
      v20 = v74;
      if ( v5 )
        v20 = v85[6];
      v74 = v20;
    }
    else
    {
      *((_BYTE *)this + 68) = 1;
      v16 = v12 + 248;
      *((_DWORD *)this + 3) = v86[11];
      *((_DWORD *)this + 4) = v86[1];
      *((_DWORD *)this + 5) = v86[10];
      *((_DWORD *)this + 7) = WORD2(v86[8]);
      *((_DWORD *)this + 8) = HIWORD(v86[8]);
      v17 = WORD2(v86[0]);
      *((_DWORD *)this + 9) = WORD2(v86[0]);
      *((_DWORD *)this + 10) = HIDWORD(v86[3]);
      *((_DWORD *)this + 11) = v86[4];
      v48 = HIDWORD(v86[14]);
      if ( HIDWORD(v86[14]) > 0xE )
      {
        v14 = 1;
        v75 = 1;
        *((_QWORD *)this + 6) = v86[29];
      }
      v19 = HIWORD(v86[0]);
      if ( v48 > 6 )
      {
        v77 = 1;
        v13 = v86[21];
        v79 = v86[21];
      }
      if ( v48 > 0xA )
      {
        v15 = 1;
        *((_QWORD *)this + 7) = v86[25];
      }
      if ( v5 )
        v74 = HIDWORD(v86[6]);
    }
    v21 = 479;
    if ( !v14 )
      v21 = 223;
    v22 = *((_DWORD *)this + 2) | v21 | (v15 != 0 ? 0x800 : 0);
    *((_DWORD *)this + 2) = v22;
    if ( v17 == 34404 )
      goto LABEL_40;
    if ( v17 <= 0x266 )
    {
      if ( v17 != 614 )
      {
        switch ( v17 )
        {
          case 0x14Cu:
          case 0x162u:
          case 0x166u:
          case 0x168u:
          case 0x169u:
          case 0x1A2u:
          case 0x1A3u:
          case 0x1A4u:
          case 0x1A6u:
          case 0x1A8u:
          case 0x1C0u:
          case 0x1C2u:
          case 0x1C4u:
          case 0x1F2u:
          case 0x200u:
            break;
          default:
            goto LABEL_155;
        }
      }
    }
    else if ( v17 > 0x3A64 )
    {
      if ( v17 != 42561 && v17 != 43620 && v17 != 49201 )
      {
LABEL_155:
        *((_DWORD *)this + 9) = 0;
LABEL_41:
        *(_QWORD *)nNumberOfBytesToRead = 40 * v19;
        v23 = (struct _IMAGE_SECTION_HEADER *)malloc(*(size_t *)nNumberOfBytesToRead);
        if ( v23 )
        {
          NumberOfBytesRead = 0;
          if ( hFile )
          {
            v53 = v16;
            v54 = hFile;
            if ( SetFilePointer(hFile, v53, 0, 0) == -1 )
              goto LABEL_46;
            if ( !ReadFile(v54, v23, nNumberOfBytesToRead[0], &NumberOfBytesRead, 0) )
              goto LABEL_46;
            v24 = *(_QWORD *)nNumberOfBytesToRead;
            if ( NumberOfBytesRead < nNumberOfBytesToRead[0] )
              goto LABEL_46;
          }
          else
          {
            if ( !v7
              || (*(unsigned int (__fastcall **)(_QWORD, struct ProcessInfo *, unsigned __int64, struct _IMAGE_SECTION_HEADER *, DWORD, DWORD *, _DWORD))(**((_QWORD **)v7 + 11) + 240LL))(
                   *((_QWORD *)v7 + 11),
                   v7,
                   v16,
                   v23,
                   nNumberOfBytesToRead[0],
                   &NumberOfBytesRead,
                   0)
              || (v24 = *(_QWORD *)nNumberOfBytesToRead, NumberOfBytesRead < nNumberOfBytesToRead[0]) )
            {
LABEL_46:
              v24 = 0;
              *((_BYTE *)this + 70) = *((_DWORD *)this + 9) == 14948;
LABEL_47:
              *(_QWORD *)nNumberOfBytesToRead = v24;
LABEL_48:
              if ( (a5 & 0x400) == 0 )
                goto LABEL_70;
LABEL_67:
              v35 = 0;
              if ( !v19 )
                goto LABEL_70;
              while ( 1 )
              {
                Name = (unsigned int *)v23[v35].Name;
                v37 = Name[3];
                if ( v13 >= v37 && v13 < (unsigned __int64)((unsigned int)v37 + Name[4]) )
                  break;
                v35 = (unsigned int)(v35 + 1);
                if ( (unsigned int)v35 >= v19 )
                  goto LABEL_70;
              }
              v38 = hFile;
              if ( hFile )
                v43 = Name[5] - v37;
              else
                v43 = v74;
              v44 = v13 + v43;
              *((_DWORD *)this + 2) |= 0x400u;
              v45 = HIDWORD(v79) / 0x1C;
              v46 = 0;
              *(_QWORD *)nNumberOfBytesToRead = v24;
              hFile = v38;
              if ( HIDWORD(v79) / 0x1C )
              {
                while ( 1 )
                {
                  memset(v81, 0, 28);
                  NumberOfBytesRead = 0;
                  if ( v38 )
                  {
                    if ( SetFilePointer(v38, v44, 0, 0) == -1
                      || !ReadFile(hFile, v81, 0x1Cu, &NumberOfBytesRead, 0)
                      || NumberOfBytesRead < 0x1C )
                    {
                      goto LABEL_70;
                    }
                  }
                  else
                  {
                    if ( !v7 )
                      goto LABEL_106;
                    if ( (*(unsigned int (__fastcall **)(_QWORD, struct ProcessInfo *, unsigned __int64, _OWORD *, int, DWORD *, _DWORD))(**((_QWORD **)v7 + 11) + 240LL))(
                           *((_QWORD *)v7 + 11),
                           v7,
                           v44,
                           v81,
                           28,
                           &NumberOfBytesRead,
                           0)
                      || NumberOfBytesRead < 0x1C )
                    {
                      goto LABEL_70;
                    }
                  }
                  if ( HIDWORD(v81[0]) == 16 )
                    break;
                  if ( HIDWORD(v81[0]) != 4 )
                    goto LABEL_104;
                  v78 = v81[1];
                  v38 = hFile;
                  if ( LODWORD(v81[1]) )
                  {
                    if ( hFile )
                    {
                      if ( DWORD2(v81[1]) )
                      {
LABEL_191:
                        v63 = malloc(LODWORD(v81[1]));
                        if ( !v63 )
                        {
                          v7 = v73;
LABEL_70:
                          v38 = hFile;
                          goto LABEL_106;
                        }
                        if ( hFile )
                          v64 = DWORD2(v81[1]);
                        else
                          v64 = v74 + DWORD1(v81[1]);
                        ImageData = ReadImageData(v73, v64, hFile, v63, v78);
                        for ( i = v63; ImageData >= 0x10; i = (_DWORD *)((char *)i + v67) )
                        {
                          v67 = (unsigned int)i[1];
                          if ( !(_DWORD)v67 || ImageData < (unsigned int)v67 )
                            break;
                          if ( *i == 1 )
                          {
                            *((_DWORD *)this + 16) = DWORD1(v81[0]);
                            *((_DWORD *)this + 2) |= 0x200u;
                            break;
                          }
                          ImageData -= v67;
                        }
                        free(v63);
                        v7 = v73;
                        goto LABEL_104;
                      }
                    }
                    else if ( DWORD1(v81[1]) )
                    {
                      goto LABEL_191;
                    }
                  }
LABEL_105:
                  if ( ++v46 >= v45 )
                    goto LABEL_106;
                  v44 += 28LL;
                }
                *((_BYTE *)this + 69) = 1;
LABEL_104:
                v38 = hFile;
                goto LABEL_105;
              }
LABEL_106:
              if ( nNumberOfBytesToRead[0] )
              {
                if ( v75 )
                {
                  if ( (a5 & 0x100) != 0 )
                  {
                    v25 = *((unsigned int *)this + 12);
                    v26 = 0;
                    if ( v19 )
                    {
                      while ( 1 )
                      {
                        v27 = (unsigned int *)v23[v26].Name;
                        v28 = v27[3];
                        if ( v25 >= v28 && v25 < (unsigned int)v28 + v27[4] )
                          break;
                        v26 = (unsigned int)(v26 + 1);
                        if ( (unsigned int)v26 >= v19 )
                          goto LABEL_55;
                      }
                      if ( v38 )
                        v47 = v27[5] - v28;
                      else
                        v47 = v74;
                      v68 = v25 + v47;
                      memset(v82, 0, 0x48u);
                      if ( ReadImageData(v7, v68, hFile, v82, 0x48u) )
                      {
                        if ( v82[0] >= 0x48u )
                        {
                          *((_DWORD *)this + 18) = v82[4];
                          *((_DWORD *)this + 2) |= 0x2000u;
                        }
                      }
                    }
                  }
                }
              }
LABEL_55:
              free(v23);
              return *((unsigned int *)this + 2);
            }
            v54 = hFile;
          }
          v78 = *((_DWORD *)this + 9);
          *((_BYTE *)this + 70) = v78 == 14948;
          if ( !(_DWORD)v24 )
            goto LABEL_47;
          if ( !v15 || (v31 = *((unsigned int *)this + 14), v32 = 0, !v19) )
          {
LABEL_75:
            *(_QWORD *)nNumberOfBytesToRead = v24;
LABEL_65:
            if ( v77 && (a5 & 0x200) != 0 )
              goto LABEL_67;
            goto LABEL_48;
          }
          while ( 1 )
          {
            v33 = (unsigned int *)v23[v32].Name;
            v34 = v33[3];
            if ( v31 >= v34 && v31 < (unsigned int)v34 + v33[4] )
              break;
            v32 = (unsigned int)(v32 + 1);
            if ( (unsigned int)v32 >= v19 )
              goto LABEL_65;
          }
          if ( v54 )
            v39 = v33[5] - v34;
          else
            v39 = v74;
          v40 = v31 + v39;
          v41 = *((unsigned int *)this + 5);
          v42 = *((_DWORD *)this + 15);
          if ( *((_BYTE *)this + 68) )
          {
            memset(v85, 0, 0xC4u);
            if ( v42 > 0xC4 )
              v42 = 196;
            lpOverlapped = v42;
            v55 = hFile;
            if ( !ReadImageData(v73, v40, hFile, v85, lpOverlapped) )
            {
              hFile = v55;
              goto LABEL_73;
            }
            v56 = *((_DWORD *)this + 15);
            if ( v56 < 0x80 )
            {
              v50 = 0;
              if ( v56 < 0x5C )
              {
                v59 = hFile;
                goto LABEL_72;
              }
            }
            else
            {
              v50 = HIDWORD(v85[15]);
            }
            *((_DWORD *)this + 34) = v85[11];
            v57 = v74;
            *((_QWORD *)this + 18) = LODWORD(v85[10]) - v74;
            v58 = HIDWORD(v85[10]);
            v59 = hFile;
LABEL_71:
            *((_QWORD *)this + 19) = v58;
            if ( v50 )
            {
              v61 = *((_DWORD *)this + 9);
              if ( v61 == 332 || v61 == 34404 || v61 == 43620 )
              {
                hFile = v59;
                *((_BYTE *)this + 70) = 1;
                *((_DWORD *)this + 2) |= 0x800u;
                v62 = v41;
                if ( v50 < v57 || v50 >= v57 + v41 )
                {
                  MicrosoftTelemetryAssertTriggeredNoArgs();
                  v57 = v74;
                }
                v7 = v73;
                *((_DWORD *)v73 + 98) |= 0x8000u;
                IMAGE_HEADER_INFO::ReadCHPEMetadata(this, v7, v57, v62, v78, hFile, v19, v23, v50 - v57);
                goto LABEL_74;
              }
            }
            goto LABEL_72;
          }
          memset(v85, 0, 0x148u);
          if ( v42 > 0x148 )
            v42 = 328;
          NumberOfBytesRead = 0;
          if ( hFile )
          {
            v60 = v40;
            v59 = hFile;
            if ( SetFilePointer(hFile, v60, 0, 0) == -1
              || !ReadFile(v59, v85, v42, &NumberOfBytesRead, 0)
              || NumberOfBytesRead < v42 )
            {
              goto LABEL_174;
            }
          }
          else
          {
            if ( !v73
              || (*(unsigned int (__fastcall **)(_QWORD, struct ProcessInfo *, unsigned __int64, _QWORD *, DWORD, DWORD *, _DWORD))(**((_QWORD **)v73 + 11) + 240LL))(
                   *((_QWORD *)v73 + 11),
                   v73,
                   v40,
                   v85,
                   v42,
                   &NumberOfBytesRead,
                   0)
              || NumberOfBytesRead < v42 )
            {
              goto LABEL_73;
            }
            v59 = hFile;
          }
          if ( v42 )
          {
            v49 = *((_DWORD *)this + 15);
            if ( v49 >= 0xD0 )
            {
              v50 = v85[25];
LABEL_177:
              *((_DWORD *)this + 34) = v85[18];
              v57 = v74;
              *((_QWORD *)this + 18) = v85[16] - v74;
              v58 = v85[17];
              goto LABEL_71;
            }
            v50 = 0;
            if ( v49 >= 0x94 )
              goto LABEL_177;
LABEL_72:
            *((_BYTE *)this + 70) = 0;
            *((_DWORD *)this + 2) |= 0x800u;
            hFile = v59;
LABEL_73:
            v7 = v73;
LABEL_74:
            v24 = *(_QWORD *)nNumberOfBytesToRead;
            goto LABEL_75;
          }
LABEL_174:
          hFile = v59;
          goto LABEL_73;
        }
        return *((unsigned int *)this + 2);
      }
    }
    else if ( v17 != 14948 && v17 != 870 && v17 != 1126 && v17 != 3772 )
    {
      *((_DWORD *)this + 9) = 0;
      goto LABEL_41;
    }
LABEL_40:
    *((_DWORD *)this + 2) = v22 | 0x20;
    goto LABEL_41;
  }
  memset(v82, 0, 0x4Cu);
  if ( !ReadImageData(v7, v12, v5, v82, 0x4Cu) || LOWORD(v82[5]) != 263 )
    return *((unsigned int *)this + 2);
  *((_DWORD *)this + 4) = v82[1];
  *((_DWORD *)this + 10) = v82[6];
  *((_DWORD *)this + 11) = v82[7];
  *((_DWORD *)this + 2) |= 0xC2u;
  if ( IsValidMachineType(LOWORD(v82[0])) )
  {
    *((_DWORD *)this + 9) = v52;
    v51 |= 0x20u;
    *((_DWORD *)this + 2) = v51;
  }
  return v51;
}

```

## disassembly

```asm
0x180080870  push    rbp
0x180080872  push    rbx
0x180080873  push    rsi
0x180080874  push    rdi
0x180080875  push    r12
0x180080877  push    r13
0x180080879  push    r14
0x18008087b  push    r15
0x18008087d  lea     rbp, [rsp-2B8h]
0x180080885  sub     rsp, 3B8h
0x18008088c  mov     [rbp+2F0h+var_360], 0FFFFFFFFFFFFFFFEh
0x180080894  mov     rax, cs:__security_cookie
0x18008089b  xor     rax, rsp
0x18008089e  mov     [rbp+2F0h+var_50], rax
0x1800808a5  mov     rsi, r9
0x1800808a8  mov     [rsp+3F0h+hFile], r9
0x1800808ad  mov     rbx, r8
0x1800808b0  mov     [rsp+3F0h+var_380], rbx
0x1800808b5  mov     r13, rdx
0x1800808b8  mov     [rsp+3F0h+var_388], rdx
0x1800808bd  mov     rdi, rcx
0x1800808c0  xor     edx, edx; Val
0x1800808c2  mov     r8d, 0F8h; Size
0x1800808c8  lea     rcx, [rbp+2F0h+var_150]; void *
0x1800808cf  call    memset
0x1800808d4  xorps   xmm0, xmm0
0x1800808d7  movups  [rbp+2F0h+Buffer], xmm0
0x1800808db  movups  [rbp+2F0h+var_2D0], xmm0
0x1800808df  movups  [rbp+2F0h+var_2C0], xmm0
0x1800808e3  movups  [rbp+2F0h+var_2B0], xmm0
0x1800808e7  mov     [rsp+3F0h+var_374], 454Ch
0x1800808ef  xor     r14d, r14d
0x1800808f2  mov     [rdi+8], r14d
0x1800808f6  mov     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x1800808fd  mov     dword ptr [rdi+10h], 0FFFFFFFEh
0x180080904  mov     [rdi+14h], r14
0x180080908  mov     [rdi+1Ch], r14
0x18008090c  mov     [rdi+24h], r14
0x180080910  mov     [rdi+2Ch], r14d
0x180080914  mov     [rdi+88h], r14d
0x18008091b  mov     [rdi+90h], r14
0x180080922  mov     [rdi+98h], r14
0x180080929  xor     eax, eax
0x18008092b  mov     [rdi+30h], rax
0x18008092f  mov     dword ptr [rdi+40h], 0FFFFFFFEh
0x180080936  mov     rcx, [rdi+80h]
0x18008093d  test    rcx, rcx
0x180080940  jz      short loc_180080956
0x180080942  mov     [rdi+80h], r14
0x180080949  mov     rax, [rcx]
0x18008094c  mov     rax, [rax+10h]
0x180080950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080955  nop
0x180080956  mov     rcx, [rdi+60h]; Block
0x18008095a  test    rcx, rcx
0x18008095d  jnz     loc_1800811B3
0x180080963  mov     [rdi+6Ch], r14d
0x180080967  mov     rcx, [rdi+70h]; Block
0x18008096b  test    rcx, rcx
0x18008096e  jnz     loc_1800811C8
0x180080974  mov     [rdi+78h], r14d
0x180080978  mov     byte ptr [rdi+46h], 0
0x18008097c  test    r13, r13
0x18008097f  jnz     loc_180080D92
0x180080985  test    rsi, rsi
0x180080988  jnz     loc_1800811DD
0x18008098e  test    r13, r13
0x180080991  jz      loc_180080D6B
0x180080997  mov     [rsp+3F0h+NumberOfBytesRead], r14d
0x18008099c  test    r13, r13
0x18008099f  jz      loc_180080D6B
0x1800809a5  mov     rcx, [r13+58h]
0x1800809a9  mov     rax, [rcx]
0x1800809ac  mov     [rsp+3F0h+var_3C0], r14d
0x1800809b1  lea     rdx, [rsp+3F0h+NumberOfBytesRead]
0x1800809b6  mov     [rsp+3F0h+var_3C8], rdx
0x1800809bb  mov     dword ptr [rsp+3F0h+lpOverlapped], 40h ; '@'
0x1800809c3  lea     r9, [rbp+2F0h+Buffer]
0x1800809c7  mov     r8, rbx
0x1800809ca  mov     rdx, r13
0x1800809cd  mov     rax, [rax+0F0h]
0x1800809d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800809d9  test    eax, eax
0x1800809db  jnz     loc_180080D6B
0x1800809e1  mov     [rsp+3F0h+hFile], rsi
0x1800809e6  mov     r15, rbx
0x1800809e9  cmp     [rsp+3F0h+NumberOfBytesRead], 40h ; '@'
0x1800809ee  jb      loc_180080D6B
0x1800809f4  mov     eax, 5A4Dh
0x1800809f9  cmp     word ptr [rbp+2F0h+Buffer], ax
0x1800809fd  jnz     short loc_180080A06
0x1800809ff  movsxd  rax, dword ptr [rbp+2F0h+var_2B0+0Ch]
0x180080a03  add     r15, rax
0x180080a06  mov     [rsp+3F0h+NumberOfBytesRead], r14d
0x180080a0b  test    rsi, rsi
0x180080a0e  jnz     loc_180081240
0x180080a14  test    r13, r13
0x180080a17  jz      loc_180080D6B
0x180080a1d  mov     rcx, [r13+58h]
0x180080a21  mov     rax, [rcx]
0x180080a24  mov     [rsp+3F0h+var_3C0], r14d
0x180080a29  lea     rdx, [rsp+3F0h+NumberOfBytesRead]
0x180080a2e  mov     [rsp+3F0h+var_3C8], rdx
0x180080a33  mov     dword ptr [rsp+3F0h+lpOverlapped], 4
0x180080a3b  lea     r9, [rsp+3F0h+var_374]
0x180080a40  mov     r8, r15
0x180080a43  mov     rdx, r13
0x180080a46  mov     rax, [rax+0F0h]
0x180080a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080a52  test    eax, eax
0x180080a54  jnz     loc_180080D6B
0x180080a5a  cmp     [rsp+3F0h+NumberOfBytesRead], 4
0x180080a5f  jb      loc_180080D6B
0x180080a65  cmp     [rsp+3F0h+var_374], 4550h
0x180080a6d  jnz     loc_18008129D
0x180080a73  mov     [rsp+3F0h+NumberOfBytesRead], r14d
0x180080a78  test    rsi, rsi
0x180080a7b  jnz     loc_18008131F
0x180080a81  test    r13, r13
0x180080a84  jz      loc_180080D6B
0x180080a8a  mov     rcx, [r13+58h]
0x180080a8e  mov     rax, [rcx]
0x180080a91  mov     [rsp+3F0h+var_3C0], r14d
0x180080a96  lea     rdx, [rsp+3F0h+NumberOfBytesRead]
0x180080a9b  mov     [rsp+3F0h+var_3C8], rdx
0x180080aa0  mov     dword ptr [rsp+3F0h+lpOverlapped], 0F8h
0x180080aa8  lea     r9, [rbp+2F0h+var_150]
0x180080aaf  mov     r8, r15
0x180080ab2  mov     rdx, r13
0x180080ab5  mov     rax, [rax+0F0h]
0x180080abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080ac1  test    eax, eax
0x180080ac3  jnz     loc_180080D6B
0x180080ac9  cmp     [rsp+3F0h+NumberOfBytesRead], 0F8h
0x180080ad1  jb      loc_180080D6B
0x180080ad7  mov     rbx, r14
0x180080ada  mov     [rbp+2F0h+var_368], rbx
0x180080ade  mov     [rbp+2F0h+var_370], r14d
0x180080ae2  mov     r9d, r14d
0x180080ae5  mov     [rsp+3F0h+var_378], r14d
0x180080aea  mov     r12d, r14d
0x180080aed  mov     eax, 20Bh
0x180080af2  cmp     [rbp+2F0h+var_138], ax
0x180080af9  jnz     loc_1800810EF
0x180080aff  mov     [rdi+44h], bl
0x180080b02  xor     edx, edx; Val
0x180080b04  mov     r8d, 108h; Size
0x180080b0a  lea     rcx, [rbp+2F0h+var_2A0]; void *
0x180080b0e  call    memset
0x180080b13  mov     [rsp+3F0h+NumberOfBytesRead], r14d
0x180080b18  test    rsi, rsi
0x180080b1b  jnz     loc_180081381
0x180080b21  test    r13, r13
0x180080b24  jz      loc_180080D6B
0x180080b2a  mov     rcx, [r13+58h]
0x180080b2e  mov     rax, [rcx]
0x180080b31  mov     [rsp+3F0h+var_3C0], r14d
0x180080b36  lea     rdx, [rsp+3F0h+NumberOfBytesRead]
0x180080b3b  mov     [rsp+3F0h+var_3C8], rdx
0x180080b40  mov     dword ptr [rsp+3F0h+lpOverlapped], 108h
0x180080b48  lea     r9, [rbp+2F0h+var_2A0]
0x180080b4c  mov     r8, r15
0x180080b4f  mov     rdx, r13
0x180080b52  mov     rax, [rax+0F0h]
0x180080b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080b5e  test    eax, eax
0x180080b60  jnz     loc_180080D6B
0x180080b66  cmp     [rsp+3F0h+NumberOfBytesRead], 108h
0x180080b6e  jb      loc_180080D6B
0x180080b74  add     r15, 108h
0x180080b7b  mov     eax, [rbp+2F0h+var_248]
0x180080b81  mov     [rdi+0Ch], eax
0x180080b84  mov     eax, [rbp+2F0h+var_298]
0x180080b87  mov     [rdi+10h], eax
0x180080b8a  mov     eax, [rbp+2F0h+var_250]
0x180080b90  mov     [rdi+14h], eax
0x180080b93  movzx   eax, [rbp+2F0h+var_25C]
0x180080b9a  mov     [rdi+1Ch], eax
0x180080b9d  movzx   eax, [rbp+2F0h+var_25A]
0x180080ba4  mov     [rdi+20h], eax
0x180080ba7  movzx   r8d, [rbp+2F0h+var_29C]
0x180080bac  mov     [rdi+24h], r8d
0x180080bb0  mov     eax, [rbp+2F0h+var_284]
0x180080bb3  mov     [rdi+28h], eax
0x180080bb6  mov     eax, [rbp+2F0h+var_280]
0x180080bb9  mov     [rdi+2Ch], eax
0x180080bbc  mov     ecx, [rbp+2F0h+var_21C]
0x180080bc2  cmp     ecx, 0Eh
0x180080bc5  jbe     loc_1800813E0
0x180080bcb  mov     r9d, 1
0x180080bd1  mov     [rsp+3F0h+var_378], r9d
0x180080bd6  mov     rax, [rbp+2F0h+var_1A8]
0x180080bdd  mov     [rdi+30h], rax
0x180080be1  movzx   r14d, [rbp+2F0h+var_29A]
0x180080be6  cmp     ecx, 6
0x180080be9  jbe     short loc_180080BFD
0x180080beb  mov     [rbp+2F0h+var_370], 1
0x180080bf2  mov     rbx, [rbp+2F0h+var_1E8]
0x180080bf9  mov     [rbp+2F0h+var_368], rbx
0x180080bfd  cmp     ecx, 0Ah
0x180080c00  jbe     short loc_180080C13
0x180080c02  mov     r12d, 1
0x180080c08  mov     rax, [rbp+2F0h+var_1C8]
0x180080c0f  mov     [rdi+38h], rax
0x180080c13  mov     rcx, [rsp+3F0h+var_380]
0x180080c18  test    rsi, rsi
0x180080c1b  cmovnz  rcx, [rbp+2F0h+var_270]
0x180080c23  mov     [rsp+3F0h+var_380], rcx
0x180080c28  mov     eax, r12d
0x180080c2b  neg     eax
0x180080c2d  sbb     edx, edx
0x180080c2f  and     edx, 800h
0x180080c35  mov     eax, 1DFh
0x180080c3a  mov     ecx, 0DFh
0x180080c3f  test    r9d, r9d
0x180080c42  cmovz   eax, ecx
0x180080c45  or      edx, eax
0x180080c47  or      edx, [rdi+8]
0x180080c4a  mov     [rdi+8], edx
0x180080c4d  cmp     r8d, 8664h
0x180080c54  jnz     loc_180080E97
0x180080c5a  or      edx, 20h; jumptable 0000000180081461 cases 332,354,358,360,361,418-420,422,424,448,450,452,498,512
0x180080c5d  mov     [rdi+8], edx
0x180080c60  lea     eax, [r14+r14*4]
0x180080c64  shl     eax, 3
0x180080c67  mov     qword ptr [rsp+3F0h+nNumberOfBytesToRead], rax
0x180080c6c  mov     ecx, eax; Size
0x180080c6e  call    cs:__imp_malloc
0x180080c75  nop     dword ptr [rax+rax+00h]
0x180080c7a  mov     rsi, rax
0x180080c7d  test    rax, rax
0x180080c80  jz      loc_180080D6B
0x180080c86  mov     [rsp+3F0h+NumberOfBytesRead], 0
0x180080c8e  cmp     [rsp+3F0h+hFile], 0
0x180080c94  jnz     loc_18008149A
0x180080c9a  test    r13, r13
0x180080c9d  jz      short loc_180080CEA
0x180080c9f  mov     rcx, [r13+58h]
0x180080ca3  mov     rax, [rcx]
0x180080ca6  mov     [rsp+3F0h+var_3C0], 0
0x180080cae  lea     rdx, [rsp+3F0h+NumberOfBytesRead]
0x180080cb3  mov     [rsp+3F0h+var_3C8], rdx
0x180080cb8  mov     rdx, qword ptr [rsp+3F0h+nNumberOfBytesToRead]
0x180080cbd  mov     dword ptr [rsp+3F0h+lpOverlapped], edx
0x180080cc1  mov     r9, rsi
0x180080cc4  mov     r8, r15
0x180080cc7  mov     rdx, r13
0x180080cca  mov     rax, [rax+0F0h]
0x180080cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080cd6  test    eax, eax
0x180080cd8  jnz     short loc_180080CEA
0x180080cda  mov     r11, qword ptr [rsp+3F0h+nNumberOfBytesToRead]
0x180080cdf  cmp     [rsp+3F0h+NumberOfBytesRead], r11d
0x180080ce4  jnb     loc_180081502
0x180080cea  xor     r11d, r11d
0x180080ced  cmp     dword ptr [rdi+24h], 3A64h
0x180080cf4  setz    al
0x180080cf7  mov     [rdi+46h], al
0x180080cfa  mov     qword ptr [rsp+3F0h+nNumberOfBytesToRead], r11
0x180080cff  test    [rbp+2F0h+arg_20], 400h
0x180080d09  jz      loc_180080E5C
0x180080d0f  jmp     loc_180080E36
0x180080d14  cmp     [rsp+3F0h+var_378], 0
0x180080d19  jz      short loc_180080D5C
0x180080d1b  test    [rbp+2F0h+arg_20], 100h
0x180080d25  jz      short loc_180080D5C
0x180080d27  mov     r9d, [rdi+30h]
0x180080d2b  xor     edx, edx
0x180080d2d  test    r14d, r14d
0x180080d30  jz      short loc_180080D5C
0x180080d32  nop     dword ptr [rax+00h]
0x180080d36  nop     word ptr [rax+rax+00000000h]
0x180080d40  lea     rcx, [rdx+rdx*4]
0x180080d44  lea     r8, [rsi+rcx*8]
0x180080d48  mov     ecx, [r8+0Ch]
0x180080d4c  cmp     r9, rcx
0x180080d4f  jnb     loc_1800810A2
0x180080d55  inc     edx
0x180080d57  cmp     edx, r14d
0x180080d5a  jb      short loc_180080D40
0x180080d5c  mov     rcx, rsi; Block
0x180080d5f  call    cs:__imp_free
0x180080d66  nop     dword ptr [rax+rax+00h]
0x180080d6b  mov     eax, [rdi+8]
0x180080d6e  mov     rcx, [rbp+2F0h+var_50]
0x180080d75  xor     rcx, rsp; StackCookie
0x180080d78  call    __security_check_cookie
0x180080d7d  add     rsp, 3B8h
0x180080d84  pop     r15
0x180080d86  pop     r14
0x180080d88  pop     r13
0x180080d8a  pop     r12
0x180080d8c  pop     rdi
0x180080d8d  pop     rsi
0x180080d8e  pop     rbx
0x180080d8f  pop     rbp
0x180080d90  retn
0x180080d92  xor     r9d, r9d; int
0x180080d95  xor     r8d, r8d; int
0x180080d98  mov     rdx, rbx; unsigned __int64
  ... truncated ...
```
