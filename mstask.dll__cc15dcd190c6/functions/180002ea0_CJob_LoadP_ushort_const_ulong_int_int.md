# CJob::LoadP(ushort const *,ulong,int,int)

- ea: `0x180002ea0`
- end: `0x18000360c`
- name: `?LoadP@CJob@@QEAAJPEBGKHH@Z`
- size: `1900`
- prototype: `__int64 __fastcall(CJob *__hidden this, LPCWSTR lpFileName, unsigned int, int, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180002530`
- `0x18000c93c`
- `0x18000d760`
- `0x18000f100`

## callees

- `0x180002ea0`
- `0x180003620`
- `0x180007560`
- `0x180009ef8`
- `0x180009f38`
- `0x18001aa82`

## import_xrefs

- `msvcrt!rand` at `0x1800033fe`
- `msvcrt!rand` at `0x1800033fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000350d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000350d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003425`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003425`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003006`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003006`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000301c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000301c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000304c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000304c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800030a6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800030a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003539`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800033ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800033ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000339e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000339e`

## pseudocode

```c
__int64 __fastcall CJob::LoadP(CJob *this, LPCWSTR lpFileName, DWORD a3, int a4)
{
  __int64 v7; // rdi
  __int64 v8; // rax
  _WORD *v10; // rsi
  unsigned int v12; // ebx
  void *v13; // rcx
  unsigned __int64 v14; // rdi
  _WORD *v15; // rcx
  __int64 v16; // rax
  LPCWSTR v17; // rdx
  _WORD *v18; // rax
  signed int LastError; // edi
  int v20; // r12d
  HANDLE FileW; // rsi
  DWORD FileSize; // eax
  size_t v23; // rdi
  char *v24; // rax
  char *v25; // r15
  unsigned __int64 v26; // rdx
  __int16 v27; // ax
  unsigned __int16 *v28; // r9
  char *v29; // r8
  __int64 v30; // rax
  char *v31; // rcx
  unsigned __int16 *v32; // r8
  __int64 v33; // rax
  unsigned __int16 *v34; // rcx
  unsigned __int16 *v35; // r8
  __int64 v36; // rax
  unsigned __int16 *v37; // rcx
  unsigned __int16 *v38; // r8
  __int64 v39; // rax
  unsigned __int16 *v40; // rcx
  unsigned __int16 *v41; // r8
  __int64 v42; // rax
  unsigned __int16 *v43; // rcx
  unsigned __int16 *v44; // r8
  __int64 v45; // rax
  unsigned __int16 *v46; // rcx
  _QWORD *v47; // rcx
  __int64 v48; // rax
  unsigned __int16 *v49; // r8
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // rax
  char *v52; // r15
  __int64 v53; // r12
  HLOCAL v54; // rax
  _WORD *v55; // r13
  signed int v56; // eax
  __int64 *v57; // rsi
  int v58; // eax
  bool v59; // sf
  signed int v60; // eax
  char *v61; // rax
  signed int v62; // eax
  __int64 v63; // r8
  unsigned __int16 v64; // dx
  char *v65; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int64 v66; // [rsp+48h] [rbp-40h]
  DWORD FileSizeHigh; // [rsp+A0h] [rbp+18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+20h] BYREF

  FileSizeHigh = a3;
  if ( a4 )
  {
    v7 = -1;
    v8 = -1;
    while ( lpFileName[++v8] != 0 )
      ;
    v10 = operator new(saturated_mul(v8 + 1, 2u));
    if ( !v10 )
      return 2147942414LL;
    v13 = (void *)*((_QWORD *)this + 19);
    if ( v13 )
      operator delete(v13);
    *((_QWORD *)this + 19) = v10;
    *v10 = 0;
    do
      ++v7;
    while ( lpFileName[v7] );
    v14 = v7 + 1;
    if ( v14 )
    {
      v15 = (_WORD *)*((_QWORD *)this + 19);
      if ( v14 > 0x7FFFFFFF )
      {
        *v15 = 0;
      }
      else
      {
        v16 = 2147483646;
        v17 = lpFileName;
        do
        {
          if ( !v16 )
            break;
          if ( !*v17 )
            break;
          *v15++ = *v17++;
          --v16;
          --v14;
        }
        while ( v14 );
        v18 = v15 - 1;
        if ( v14 )
          v18 = v15;
        *v18 = 0;
      }
    }
  }
  LastError = 0;
  v20 = 3;
  FileW = 0;
  while ( v20 )
  {
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
    if ( FileW != (HANDLE)-1LL )
      goto LABEL_26;
    LastError = GetLastError();
    if ( LastError != 32 )
      break;
    v58 = rand();
    Sleep(v58 % 250 + 250);
    --v20;
  }
  v59 = LastError < 0;
  if ( LastError )
  {
    FileW = 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v59 = LastError < 0;
    }
    if ( v59 )
      return (unsigned int)LastError;
  }
LABEL_26:
  if ( GetFileType(FileW) == 1 )
  {
    if ( a4 )
      *((_DWORD *)this + 40) = 1;
    FileSizeHigh = 0;
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    v23 = FileSize;
    if ( FileSize == -1 )
    {
      v62 = GetLastError();
      v12 = v62;
      if ( v62 )
      {
        if ( v62 > 0 )
          v12 = (unsigned __int16)v62 | 0x80070000;
        goto LABEL_7;
      }
    }
    if ( FileSizeHigh )
    {
      v12 = -2147024883;
    }
    else if ( (unsigned int)v23 < 0x44 )
    {
      v12 = -2147024883;
    }
    else
    {
      v24 = (char *)operator new(v23);
      v25 = v24;
      if ( v24 )
      {
        NumberOfBytesRead = 0;
        if ( ReadFile(FileW, v24, v23, &NumberOfBytesRead, 0) )
        {
          if ( NumberOfBytesRead == (_DWORD)v23 )
          {
            CloseHandle(FileW);
            CJob::FreeProperties(this);
            operator delete(*((void **)this + 28));
            v26 = (unsigned __int64)&v25[v23];
            *((_QWORD *)this + 28) = v25;
            *((_QWORD *)this + 29) = &v25[v23];
            v27 = *((_WORD *)v25 + 1);
            v65 = v25 + 68;
            v66 = (unsigned __int64)&v25[v23];
            if ( *((_WORD *)this + 21) != v27 )
              return (unsigned int)-2147216621;
            v28 = (unsigned __int16 *)(v25 + 70);
            *((_WORD *)this + 20) = *(_WORD *)v25;
            v12 = -2147024883;
            *((_WORD *)this + 21) = *((_WORD *)v25 + 1);
            *(_OWORD *)((char *)this + 44) = *(_OWORD *)(v25 + 4);
            *((_WORD *)this + 30) = *((_WORD *)v25 + 11);
            *((_WORD *)this + 31) = *((_WORD *)v25 + 12);
            *((_WORD *)this + 32) = *((_WORD *)v25 + 13);
            *((_WORD *)this + 34) = *((_WORD *)v25 + 15);
            *((_WORD *)this + 35) = *((_WORD *)v25 + 14);
            *((_DWORD *)this + 18) = *((_DWORD *)v25 + 8);
            *((_DWORD *)this + 19) = *((_DWORD *)v25 + 9);
            *((_DWORD *)this + 20) = *((_DWORD *)v25 + 10);
            *((_DWORD *)this + 21) = *((_DWORD *)v25 + 11);
            *((_DWORD *)this + 22) = *((_DWORD *)v25 + 12);
            *((_OWORD *)this + 6) = *(_OWORD *)(v25 + 52);
            if ( (unsigned __int64)(v25 + 70) > v26 )
              return v12;
            v29 = v25 + 72;
            *((_WORD *)this + 33) = *((_WORD *)v25 + 34);
            if ( (unsigned __int64)(v25 + 72) > v26 )
              return v12;
            v30 = *v28;
            v31 = v25 + 72;
            if ( (_WORD)v30 )
            {
              v31 = &v29[(unsigned int)(2 * v30)];
              if ( (unsigned __int64)v31 > v26 || v28[v30] )
                return v12;
              *((_QWORD *)this + 14) = v29;
            }
            v32 = (unsigned __int16 *)(v31 + 2);
            if ( (unsigned __int64)(v31 + 2) <= v26 )
            {
              v33 = *(unsigned __int16 *)v31;
              v34 = (unsigned __int16 *)(v31 + 2);
              if ( (_WORD)v33 )
              {
                v34 = (unsigned __int16 *)((char *)v32 + (unsigned int)(2 * v33));
                if ( (unsigned __int64)v34 > v26 || v32[v33 - 1] )
                  return v12;
                *((_QWORD *)this + 15) = v32;
              }
              v35 = v34 + 1;
              if ( (unsigned __int64)(v34 + 1) <= v26 )
              {
                v36 = *v34;
                v37 = v34 + 1;
                if ( (_WORD)v36 )
                {
                  v37 = (unsigned __int16 *)((char *)v35 + (unsigned int)(2 * v36));
                  if ( (unsigned __int64)v37 > v26 || v35[v36 - 1] )
                    return v12;
                  *((_QWORD *)this + 16) = v35;
                }
                v38 = v37 + 1;
                if ( (unsigned __int64)(v37 + 1) <= v26 )
                {
                  v39 = *v37;
                  v40 = v37 + 1;
                  if ( (_WORD)v39 )
                  {
                    v40 = (unsigned __int16 *)((char *)v38 + (unsigned int)(2 * v39));
                    if ( (unsigned __int64)v40 > v26 || v38[v39 - 1] )
                      return v12;
                    *((_QWORD *)this + 17) = v38;
                  }
                  v41 = v40 + 1;
                  if ( (unsigned __int64)(v40 + 1) <= v26 )
                  {
                    v42 = *v40;
                    v43 = v40 + 1;
                    if ( (_WORD)v42 )
                    {
                      v43 = (unsigned __int16 *)((char *)v41 + (unsigned int)(2 * v42));
                      if ( (unsigned __int64)v43 > v26 || v41[v42 - 1] )
                        return v12;
                      *((_QWORD *)this + 18) = v41;
                    }
                    v44 = v43 + 1;
                    *((_QWORD *)this + 21) = 0;
                    *((_WORD *)this + 88) = 0;
                    if ( (unsigned __int64)(v43 + 1) <= v26 )
                    {
                      v45 = *v43;
                      *((_WORD *)this + 88) = v45;
                      if ( (_WORD)v45 )
                      {
                        v46 = (unsigned __int16 *)((char *)v44 + v45);
                        *((_QWORD *)this + 21) = v44;
                        v44 = v46;
                        if ( (unsigned __int64)v46 > v26 )
                          return v12;
                      }
                      else
                      {
                        v46 = v43 + 1;
                      }
                      v47 = v46 + 1;
                      *((_QWORD *)this + 23) = 0;
                      *((_WORD *)this + 89) = 0;
                      if ( (unsigned __int64)v47 <= v26 )
                      {
                        v48 = *v44;
                        v49 = (unsigned __int16 *)v47;
                        *((_WORD *)this + 89) = v48;
                        if ( !(_WORD)v48 )
                        {
                          *((_DWORD *)this + 48) = 267011;
                          LODWORD(v51) = 0;
                          goto LABEL_70;
                        }
                        if ( (unsigned int)v48 < 8 )
                        {
                          *((_WORD *)this + 89) = 0;
                          return v12;
                        }
                        v49 = (unsigned __int16 *)((char *)v47 + v48);
                        *((_QWORD *)this + 23) = v47;
                        if ( (unsigned __int64)v47 + v48 <= v26 )
                        {
                          v50 = *v47;
                          v47 = v49;
                          *((_DWORD *)this + 48) = v50;
                          v51 = HIDWORD(v50);
LABEL_70:
                          v52 = (char *)v47 + 2;
                          *((_DWORD *)this + 23) = v51;
                          if ( (unsigned __int64)v47 + 2 <= v26 )
                          {
                            v53 = *v49;
                            v65 = &v52[48 * v53];
                            if ( (unsigned __int64)v65 <= v26 )
                            {
                              v54 = (HLOCAL)*((_QWORD *)this + 3);
                              v55 = (_WORD *)((char *)this + 34);
                              if ( v54 && *v55 >= (unsigned __int16)v53 )
                              {
                                v57 = (__int64 *)((char *)this + 24);
                              }
                              else
                              {
                                LocalFree(*((HLOCAL *)this + 3));
                                *v55 = v53;
                                v54 = LocalAlloc(0, 48 * v53);
                                *((_QWORD *)this + 3) = v54;
                                if ( !v54 )
                                {
                                  v56 = GetLastError();
                                  v12 = v56;
                                  if ( v56 > 0 )
                                    v12 = (unsigned __int16)v56 | 0x80070000;
                                  if ( (v12 & 0x80000000) != 0 )
                                    return v12;
                                  v57 = (__int64 *)((char *)this + 24);
                                  goto LABEL_110;
                                }
                                v57 = (__int64 *)((char *)this + 24);
                              }
                              memcpy_0(v54, v52, 48 * v53);
                              *((_WORD *)this + 16) = v53;
LABEL_110:
                              if ( (_WORD)v53 )
                              {
                                v63 = *v57;
                                v64 = 0;
                                do
                                {
                                  *(_WORD *)(v63 + 48LL * v64 + 2) = v64;
                                  ++v64;
                                }
                                while ( v64 < (unsigned __int16)v53 );
                                *((_DWORD *)this + 22) |= 0x800000u;
                              }
                              else
                              {
                                *((_DWORD *)this + 22) &= ~0x800000u;
                              }
                              FileSizeHigh = 0;
                              if ( CInputBuffer::Read((CInputBuffer *)&v65, &FileSizeHigh, 4u)
                                && HIWORD(FileSizeHigh) <= 1u )
                              {
                                v61 = v65;
                                *((_QWORD *)this + 26) = v65;
                                if ( (unsigned __int64)(v61 + 64) > v66 )
                                  *((_QWORD *)this + 26) = 0;
                              }
                              return 0;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            return v12;
          }
          v12 = -2147024883;
        }
        else
        {
          v60 = GetLastError();
          v12 = v60;
          if ( v60 > 0 )
            v12 = (unsigned __int16)v60 | 0x80070000;
        }
        operator delete(v25);
      }
      else
      {
        v12 = -2147024882;
      }
    }
LABEL_7:
    if ( FileW != (HANDLE)-1LL )
      CloseHandle(FileW);
    return v12;
  }
  CloseHandle(FileW);
  return 2147942405LL;
}

```

## disassembly

```asm
0x180002ea0  mov     [rsp+FileSizeHigh], r8d
0x180002ea5  push    rbx
0x180002ea6  push    rbp
0x180002ea7  push    rsi
0x180002ea8  push    rdi
0x180002ea9  push    r14
0x180002eab  push    r15
0x180002ead  sub     rsp, 58h
0x180002eb1  mov     r15d, r9d
0x180002eb4  mov     rbx, rdx
0x180002eb7  mov     rbp, rcx
0x180002eba  test    r9d, r9d
0x180002ebd  jz      loc_180003433
0x180002ec3  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180002eca  mov     rax, rdi
0x180002ecd  nop     dword ptr [rax]
0x180002ed0  cmp     word ptr [rdx+rax*2+2], 0
0x180002ed6  lea     rax, [rax+1]
0x180002eda  jnz     short loc_180002ED0
0x180002edc  lea     rcx, [rax+1]
0x180002ee0  mov     eax, 2
0x180002ee5  mul     rcx
0x180002ee8  cmovb   rax, rdi
0x180002eec  mov     rcx, rax; Size
0x180002eef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ef4  mov     rsi, rax
0x180002ef7  test    rax, rax
0x180002efa  jnz     short loc_180002F39
0x180002efc  mov     eax, 8007000Eh
0x180002f01  add     rsp, 58h
0x180002f05  pop     r15
0x180002f07  pop     r14
0x180002f09  pop     rdi
0x180002f0a  pop     rsi
0x180002f0b  pop     rbp
0x180002f0c  pop     rbx
0x180002f0d  retn
0x180002f0e  mov     ebx, 8007000Dh
0x180002f13  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180002f17  jnz     loc_180003536
0x180002f1d  mov     r13, [rsp+88h+var_38]
0x180002f22  mov     eax, ebx
0x180002f24  mov     r12, [rsp+88h+arg_0]
0x180002f2c  add     rsp, 58h
0x180002f30  pop     r15
0x180002f32  pop     r14
0x180002f34  pop     rdi
0x180002f35  pop     rsi
0x180002f36  pop     rbp
0x180002f37  pop     rbx
0x180002f38  retn
0x180002f39  mov     rcx, [rbp+98h]; Block
0x180002f40  test    rcx, rcx
0x180002f43  jnz     loc_1800034D8
0x180002f49  xor     r14d, r14d
0x180002f4c  mov     [rbp+98h], rsi
0x180002f53  mov     [rsi], r14w
0x180002f57  nop     word ptr [rax+rax+00000000h]
0x180002f60  inc     rdi
0x180002f63  cmp     [rbx+rdi*2], r14w
0x180002f68  jnz     short loc_180002F60
0x180002f6a  add     rdi, 1
0x180002f6e  jz      short loc_180002FC3
0x180002f70  mov     rcx, [rbp+98h]
0x180002f77  cmp     rdi, 7FFFFFFFh
0x180002f7e  ja      loc_1800034E2
0x180002f84  mov     eax, 7FFFFFFEh
0x180002f89  mov     rdx, rbx
0x180002f8c  nop     dword ptr [rax+00h]
0x180002f90  test    rax, rax
0x180002f93  jz      short loc_180002FB4
0x180002f95  movzx   r8d, word ptr [rdx]
0x180002f99  test    r8w, r8w
0x180002f9d  jz      short loc_180002FB4
0x180002f9f  mov     [rcx], r8w
0x180002fa3  add     rdx, 2
0x180002fa7  add     rcx, 2
0x180002fab  dec     rax
0x180002fae  sub     rdi, 1
0x180002fb2  jnz     short loc_180002F90
0x180002fb4  test    rdi, rdi
0x180002fb7  lea     rax, [rcx-2]
0x180002fbb  cmovnz  rax, rcx
0x180002fbf  mov     [rax], r14w
0x180002fc3  mov     [rsp+88h+arg_0], r12
0x180002fcb  mov     edi, r14d
0x180002fce  mov     r12d, 3
0x180002fd4  mov     rsi, r14
0x180002fd7  test    r12d, r12d
0x180002fda  jz      loc_18000343B
0x180002fe0  mov     [rsp+88h+hTemplateFile], r14; hTemplateFile
0x180002fe5  xor     r9d, r9d; lpSecurityAttributes
0x180002fe8  mov     [rsp+88h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180002ff0  mov     edx, 80000000h; dwDesiredAccess
0x180002ff5  mov     r8d, 1; dwShareMode
0x180002ffb  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180003003  mov     rcx, rbx; lpFileName
0x180003006  call    cs:__imp_CreateFileW
0x18000300c  mov     rsi, rax
0x18000300f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003013  jz      loc_1800033F1
0x180003019  mov     rcx, rsi; hFile
0x18000301c  call    cs:__imp_GetFileType
0x180003022  cmp     eax, 1
0x180003025  jnz     loc_1800034EB
0x18000302b  test    r15d, r15d
0x18000302e  jnz     loc_1800034FE
0x180003034  lea     rdx, [rsp+88h+FileSizeHigh]; lpFileSizeHigh
0x18000303c  mov     [rsp+88h+var_38], r13
0x180003041  mov     rcx, rsi; hFile
0x180003044  mov     [rsp+88h+FileSizeHigh], r14d
0x18000304c  call    cs:__imp_GetFileSize
0x180003052  mov     edi, eax
0x180003054  cmp     eax, 0FFFFFFFFh
0x180003057  jz      loc_18000350D
0x18000305d  cmp     [rsp+88h+FileSizeHigh], 0
0x180003065  ja      loc_180002F0E
0x18000306b  cmp     edi, 44h ; 'D'
0x18000306e  jb      loc_1800033E7
0x180003074  mov     rcx, rdi; Size
0x180003077  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000307c  mov     r15, rax
0x18000307f  test    rax, rax
0x180003082  jz      loc_180003522
0x180003088  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180003090  mov     [rsp+88h+NumberOfBytesRead], r14d
0x180003098  mov     r8d, edi; nNumberOfBytesToRead
0x18000309b  mov     qword ptr [rsp+88h+dwCreationDisposition], r14; lpOverlapped
0x1800030a0  mov     rdx, rax; lpBuffer
0x1800030a3  mov     rcx, rsi; hFile
0x1800030a6  call    cs:__imp_ReadFile
0x1800030ac  test    eax, eax
0x1800030ae  jz      loc_180003474
0x1800030b4  cmp     [rsp+88h+NumberOfBytesRead], edi
0x1800030bb  jnz     loc_18000352C
0x1800030c1  mov     rcx, rsi; hObject
0x1800030c4  call    cs:__imp_CloseHandle
0x1800030ca  mov     rcx, rbp; this
0x1800030cd  call    ?FreeProperties@CJob@@AEAAXXZ; CJob::FreeProperties(void)
0x1800030d2  mov     rcx, [rbp+0E0h]; Block
0x1800030d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800030de  lea     rdx, [r15+rdi]
0x1800030e2  mov     [rbp+0E0h], r15
0x1800030e9  mov     [rbp+0E8h], rdx
0x1800030f0  lea     rcx, [r15+44h]
0x1800030f4  movzx   eax, word ptr [r15+2]
0x1800030f9  mov     [rsp+88h+var_48], rcx
0x1800030fe  mov     [rsp+88h+var_40], rdx
0x180003103  cmp     [rbp+2Ah], ax
0x180003107  jnz     loc_180003544
0x18000310d  movzx   eax, word ptr [r15]
0x180003111  lea     r9, [rcx+2]
0x180003115  mov     [rbp+28h], ax
0x180003119  mov     ebx, 8007000Dh
0x18000311e  movzx   eax, word ptr [r15+2]
0x180003123  mov     [rbp+2Ah], ax
0x180003127  movups  xmm0, xmmword ptr [r15+4]
0x18000312c  movups  xmmword ptr [rbp+2Ch], xmm0
0x180003130  movzx   eax, word ptr [r15+16h]
0x180003135  mov     [rbp+3Ch], ax
0x180003139  movzx   eax, word ptr [r15+18h]
0x18000313e  mov     [rbp+3Eh], ax
0x180003142  movzx   eax, word ptr [r15+1Ah]
0x180003147  mov     [rbp+40h], ax
0x18000314b  movzx   eax, word ptr [r15+1Eh]
0x180003150  mov     [rbp+44h], ax
0x180003154  movzx   eax, word ptr [r15+1Ch]
0x180003159  mov     [rbp+46h], ax
0x18000315d  mov     eax, [r15+20h]
0x180003161  mov     [rbp+48h], eax
0x180003164  mov     eax, [r15+24h]
0x180003168  mov     [rbp+4Ch], eax
0x18000316b  mov     eax, [r15+28h]
0x18000316f  mov     [rbp+50h], eax
0x180003172  mov     eax, [r15+2Ch]
0x180003176  mov     [rbp+54h], eax
0x180003179  mov     eax, [r15+30h]
0x18000317d  mov     [rbp+58h], eax
0x180003180  movups  xmm0, xmmword ptr [r15+34h]
0x180003185  movups  xmmword ptr [rbp+60h], xmm0
0x180003189  cmp     r9, rdx
0x18000318c  ja      loc_180002F1D
0x180003192  movzx   eax, word ptr [rcx]
0x180003195  lea     r8, [r9+2]
0x180003199  mov     [rbp+42h], ax
0x18000319d  cmp     r8, rdx
0x1800031a0  ja      loc_180002F1D
0x1800031a6  movzx   eax, word ptr [r9]
0x1800031aa  mov     rcx, r8
0x1800031ad  test    ax, ax
0x1800031b0  jz      short loc_1800031D2
0x1800031b2  lea     ecx, [rax+rax]
0x1800031b5  add     rcx, r8
0x1800031b8  cmp     rcx, rdx
0x1800031bb  ja      loc_180002F1D
0x1800031c1  cmp     word ptr [r8+rax*2-2], 0
0x1800031c8  jnz     loc_180002F1D
0x1800031ce  mov     [rbp+70h], r8
0x1800031d2  lea     r8, [rcx+2]
0x1800031d6  cmp     r8, rdx
0x1800031d9  ja      loc_180002F1D
0x1800031df  movzx   eax, word ptr [rcx]
0x1800031e2  mov     rcx, r8
0x1800031e5  test    ax, ax
0x1800031e8  jz      short loc_18000320A
0x1800031ea  lea     ecx, [rax+rax]
0x1800031ed  add     rcx, r8
0x1800031f0  cmp     rcx, rdx
0x1800031f3  ja      loc_180002F1D
0x1800031f9  cmp     word ptr [r8+rax*2-2], 0
0x180003200  jnz     loc_180002F1D
0x180003206  mov     [rbp+78h], r8
0x18000320a  lea     r8, [rcx+2]
0x18000320e  cmp     r8, rdx
0x180003211  ja      loc_180002F1D
0x180003217  movzx   eax, word ptr [rcx]
0x18000321a  mov     rcx, r8
0x18000321d  test    ax, ax
0x180003220  jz      short loc_180003245
0x180003222  lea     ecx, [rax+rax]
0x180003225  add     rcx, r8
0x180003228  cmp     rcx, rdx
0x18000322b  ja      loc_180002F1D
0x180003231  cmp     word ptr [r8+rax*2-2], 0
0x180003238  jnz     loc_180002F1D
0x18000323e  mov     [rbp+80h], r8
0x180003245  lea     r8, [rcx+2]
0x180003249  cmp     r8, rdx
0x18000324c  ja      loc_180002F1D
0x180003252  movzx   eax, word ptr [rcx]
0x180003255  mov     rcx, r8
0x180003258  test    ax, ax
0x18000325b  jz      short loc_180003280
0x18000325d  lea     ecx, [rax+rax]
0x180003260  add     rcx, r8
0x180003263  cmp     rcx, rdx
0x180003266  ja      loc_180002F1D
0x18000326c  cmp     word ptr [r8+rax*2-2], 0
0x180003273  jnz     loc_180002F1D
0x180003279  mov     [rbp+88h], r8
0x180003280  lea     r8, [rcx+2]
0x180003284  cmp     r8, rdx
0x180003287  ja      loc_180002F1D
0x18000328d  movzx   eax, word ptr [rcx]
0x180003290  mov     rcx, r8
0x180003293  test    ax, ax
0x180003296  jz      short loc_1800032BB
0x180003298  lea     ecx, [rax+rax]
0x18000329b  add     rcx, r8
0x18000329e  cmp     rcx, rdx
0x1800032a1  ja      loc_180002F1D
0x1800032a7  cmp     word ptr [r8+rax*2-2], 0
0x1800032ae  jnz     loc_180002F1D
0x1800032b4  mov     [rbp+90h], r8
0x1800032bb  lea     r8, [rcx+2]
0x1800032bf  mov     [rbp+0A8h], r14
0x1800032c6  mov     [rbp+0B0h], r14w
0x1800032ce  cmp     r8, rdx
0x1800032d1  ja      loc_180002F1D
0x1800032d7  movzx   eax, word ptr [rcx]
0x1800032da  mov     [rbp+0B0h], ax
0x1800032e1  test    ax, ax
0x1800032e4  jnz     loc_180003496
0x1800032ea  mov     rcx, r8
0x1800032ed  add     rcx, 2
0x1800032f1  mov     [rbp+0B8h], r14
0x1800032f8  mov     [rbp+0B2h], r14w
0x180003300  cmp     rcx, rdx
0x180003303  ja      loc_180002F1D
0x180003309  movzx   eax, word ptr [r8]
0x18000330d  mov     r8, rcx
0x180003310  mov     [rbp+0B2h], ax
0x180003317  test    ax, ax
0x18000331a  jz      loc_18000354E
0x180003320  cmp     eax, 8
0x180003323  jb      loc_180003560
0x180003329  lea     r8, [rcx+rax]
0x18000332d  mov     [rbp+0B8h], rcx
0x180003334  cmp     r8, rdx
0x180003337  ja      loc_180002F1D
0x18000333d  mov     rax, [rcx]
0x180003340  mov     rcx, r8
0x180003343  mov     [rbp+0C0h], eax
0x180003349  shr     rax, 20h
0x18000334d  mov     r9d, 5Ch ; '\'
0x180003353  lea     r15, [rcx+2]
0x180003357  mov     r10, rbp
0x18000335a  mov     [r9+rbp], eax
0x18000335e  cmp     r15, rdx
0x180003361  ja      loc_180002F1D
0x180003367  movzx   r12d, word ptr [r8]
0x18000336b  lea     rdi, [r12+r12*2]
0x18000336f  shl     rdi, 4
0x180003373  lea     rax, [rdi+r15]
0x180003377  mov     [rsp+88h+var_48], rax
0x18000337c  cmp     rax, rdx
0x18000337f  ja      loc_180002F1D
0x180003385  mov     rax, [rbp+18h]
0x180003389  lea     r13, [rbp+22h]
0x18000338d  test    rax, rax
  ... truncated ...
```
