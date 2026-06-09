# _tsopen_nolock

- ea: `0x180020ee8`
- end: `0x1800216df`
- name: `_tsopen_nolock`
- size: `2039`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180020c70`
- `0x180020dc4`

## callees

- `0x180007e80`
- `0x180007ea8`
- `0x180007f00`
- `0x18001df6c`
- `0x18001e308`
- `0x18001f9f0`
- `0x18001fd30`
- `0x18001ff14`
- `0x1800201cc`
- `0x180020854`
- `0x1800209f8`
- `0x180020ee8`
- `0x180021c08`
- `0x180023210`
- `0x18002f050`
- `0x18002f05c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002123c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002123c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021674`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18002116e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800211bc`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180021668`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18002116e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800211bc`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180021668`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180021210`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180021210`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002124e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002128b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002163a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002124e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002128b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002163a`

## pseudocode

```c
__int64 __fastcall tsopen_nolock(_DWORD *a1, int *a2, const CHAR *a3, unsigned int a4, int a5, char a6)
{
  unsigned int v6; // r14d
  unsigned int v7; // r12d
  int v8; // r9d
  char v10; // si
  DWORD v11; // r15d
  __int64 v12; // rcx
  int v13; // eax
  DWORD v14; // ebx
  __int64 v15; // rdx
  int v16; // eax
  DWORD v18; // r12d
  HANDLE v19; // rax
  HANDLE v20; // r12
  DWORD v21; // eax
  unsigned int v22; // ebx
  DWORD FileType; // eax
  DWORD LastError; // ebx
  char v25; // si
  unsigned __int8 v26; // r12
  int v27; // ecx
  int v28; // ecx
  unsigned int v29; // eax
  DWORD v30; // ebx
  DWORD v31; // ebx
  DWORD v32; // ebx
  DWORD v33; // ebx
  int v34; // esi
  int nolock; // eax
  bool v36; // zf
  DWORD v37; // ebx
  DWORD v38; // ebx
  DWORD v39; // ebx
  int v40; // eax
  int v41; // ebx
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  HANDLE v47; // rax
  DWORD v48; // eax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-58h]
  char v50; // [rsp+40h] [rbp-40h]
  DWORD dwShareMode; // [rsp+44h] [rbp-3Ch]
  int v52; // [rsp+48h] [rbp-38h] BYREF
  int PMode; // [rsp+4Ch] [rbp-34h] BYREF
  DWORD v54; // [rsp+50h] [rbp-30h]
  HANDLE hObject; // [rsp+58h] [rbp-28h]
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-20h] BYREF
  WCHAR v59; // [rsp+D8h] [rbp+58h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  LOBYTE(v59) = 0;
  v6 = a4;
  PMode = 0;
  v7 = 128;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v8 = a4 & 0x80;
  SecurityAttributes.bInheritHandle = v8 == 0;
  v10 = v8 != 0 ? 0x10 : 0;
  if ( get_fmode(&PMode) )
    invoke_watson(0, 0, 0, 0, 0);
  if ( (v6 & 0x8000) == 0 && ((v6 & 0x74000) != 0 || PMode != 0x8000) )
    v10 |= 0x80u;
  if ( (v6 & 3) != 0 )
  {
    if ( (v6 & 3) == 1 )
    {
      v11 = (((v6 & 8) != 0 && (v6 & 0x70000) != 0) << 31) + 0x40000000;
    }
    else
    {
      if ( (v6 & 3) != 2 )
        goto LABEL_10;
      v11 = -1073741824;
    }
  }
  else
  {
    v11 = 0x80000000;
  }
  if ( a5 == 16 )
  {
    v12 = 0;
    dwShareMode = 0;
  }
  else
  {
    switch ( a5 )
    {
      case 32:
        v12 = 1;
        break;
      case 48:
        v12 = 2;
        break;
      case 64:
        v12 = 3;
        break;
      case 128:
        v12 = v11 == 0x80000000;
        break;
      default:
        goto LABEL_10;
    }
    dwShareMode = v12;
  }
  v13 = v6 & 0x700;
  if ( (v6 & 0x700) != 0 )
  {
    switch ( v13 )
    {
      case 256:
        v14 = 4;
        goto LABEL_38;
      case 512:
LABEL_35:
        v14 = 5;
        goto LABEL_38;
      case 768:
        v14 = 2;
        goto LABEL_38;
    }
    if ( v13 != 1024 )
    {
      if ( v13 == 1280 )
      {
LABEL_33:
        v14 = 1;
        goto LABEL_38;
      }
      if ( v13 != 1536 )
      {
        if ( v13 == 1792 )
          goto LABEL_33;
LABEL_10:
        *_doserrno() = 0;
        *a2 = -1;
        *errno() = 22;
        invalid_parameter(0, 0, 0, 0, 0);
      }
      goto LABEL_35;
    }
  }
  v14 = 3;
LABEL_38:
  if ( (v6 & 0x100) != 0 )
    v7 = (a6 & ~(_BYTE)umaskval & 0x80u) != 0 ? 128 : 1;
  if ( (v6 & 0x40) != 0 )
  {
    v7 |= 0x4000000u;
    v11 |= 0x10000u;
    v12 = (unsigned int)v12 | 4;
    dwShareMode = v12;
  }
  v15 = v7 | 0x100;
  if ( (v6 & 0x1000) == 0 )
    v15 = v7;
  if ( (v6 & 0x20) != 0 )
  {
    LODWORD(v15) = v15 | 0x8000000;
    v54 = v15;
  }
  else
  {
    v12 = (unsigned int)v15;
    LODWORD(v12) = v15 | 0x10000000;
    if ( (v6 & 0x10) == 0 )
      v12 = (unsigned int)v15;
    v54 = v12;
  }
  v16 = alloc_osfhnd(v12, v15, 256, 1);
  *a2 = v16;
  if ( v16 == -1 )
  {
    *_doserrno() = 0;
    *a2 = -1;
    *errno() = 24;
    return 24;
  }
  v18 = v54;
  dwFlagsAndAttributes = v54;
  *a1 = 1;
  v19 = CreateFileA(a3, v11, dwShareMode, &SecurityAttributes, v14, dwFlagsAndAttributes, 0);
  hObject = v19;
  if ( v19 != (HANDLE)-1LL )
  {
    v20 = v19;
    goto LABEL_58;
  }
  if ( (v11 & 0xC0000000) == 0xC0000000 && (v6 & 1) != 0 )
  {
    v11 &= ~0x80000000;
    hObject = CreateFileA(a3, v11, dwShareMode, &SecurityAttributes, v14, v18, 0);
    v20 = hObject;
    if ( hObject != (HANDLE)-1LL )
    {
LABEL_58:
      FileType = GetFileType(v20);
      switch ( FileType )
      {
        case 0u:
          *(_BYTE *)(_pioinfo[(__int64)*a2 >> 5] + 56LL * (*a2 & 0x1F) + 8) &= ~1u;
          LastError = GetLastError();
          dosmaperr(LastError);
          CloseHandle(v20);
          if ( !LastError )
            *errno() = 13;
          return (unsigned int)*errno();
        case 2u:
          v10 |= 0x40u;
          break;
        case 3u:
          v10 |= 8u;
          break;
      }
      if ( (unsigned int)set_osfhnd((unsigned int)*a2, v20) == -1 )
      {
        CloseHandle(v20);
        return 0xFFFFFFFFLL;
      }
      v25 = v10 | 1;
      *(_BYTE *)(_pioinfo[(__int64)*a2 >> 5] + 56LL * (*a2 & 0x1F) + 8) = v25;
      *(_DWORD *)(_pioinfo[(__int64)*a2 >> 5] + 56LL * (*a2 & 0x1F) + 12) &= 0xFFFFFFFC;
      v50 = v25 & 0x48;
      if ( (v25 & 0x48) == 0 && v25 < 0 && (v6 & 2) != 0 )
      {
        if ( (unsigned int)lseek_nolock((unsigned int)*a2, 0xFFFFFFFFLL, 2) == -1 )
        {
          if ( *_doserrno() != 131 )
          {
LABEL_72:
            close_nolock((unsigned int)*a2);
            return (unsigned int)*errno();
          }
          v26 = 0;
          goto LABEL_79;
        }
        v27 = *a2;
        LOBYTE(v59) = 0;
        if ( !(unsigned int)read_nolock(v27, &v59, 1u) && (_BYTE)v59 == 26 && (unsigned int)chsize_nolock(*a2) == -1
          || (unsigned int)lseek_nolock((unsigned int)*a2, 0, 0) == -1 )
        {
          goto LABEL_72;
        }
      }
      v26 = 0;
      if ( v25 >= 0 )
        goto LABEL_130;
LABEL_79:
      if ( (v6 & 0x74000) == 0 )
      {
        if ( (PMode & 0x74000) != 0 )
          v6 |= PMode & 0x74000;
        else
          v6 |= 0x4000u;
      }
      v28 = v6 & 0x74000;
      if ( (v6 & 0x74000) == 0x4000 )
      {
        v26 = 0;
      }
      else if ( ((v28 - 0x10000) & 0xFFFFBFFF) != 0 )
      {
        if ( ((v28 - 0x20000) & 0xFFFFBFFF) != 0 )
        {
          if ( ((v28 - 0x40000) & 0xFFFFBFFF) == 0 )
            v26 = 1;
        }
        else
        {
          v26 = 2;
        }
      }
      else
      {
        v26 = (v6 & 0x301) != 769 ? 0 : 2;
      }
      if ( (v6 & 0x70000) == 0 )
        goto LABEL_130;
      v52 = 0;
      if ( (v25 & 0x40) != 0 )
        goto LABEL_130;
      v29 = v11 & 0xC0000000;
      if ( (v11 & 0xC0000000) == 0x40000000 )
      {
        v37 = v14 - 1;
        if ( !v37 || (v38 = v37 - 1) == 0 )
        {
LABEL_118:
          v34 = 2;
          goto LABEL_119;
        }
        v39 = v38 - 1;
        if ( !v39 || (v33 = v39 - 1) == 0 )
        {
          v34 = 2;
          if ( lseeki64_nolock((unsigned int)*a2, 0, 2) )
          {
            v36 = lseeki64_nolock((unsigned int)*a2, 0, 0) == -1;
LABEL_124:
            if ( v36 )
              goto LABEL_72;
            goto LABEL_130;
          }
          goto LABEL_119;
        }
      }
      else
      {
        if ( v29 == 0x80000000 )
          goto LABEL_102;
        if ( v29 != -1073741824 )
          goto LABEL_130;
        v30 = v14 - 1;
        if ( !v30 )
          goto LABEL_118;
        v31 = v30 - 1;
        if ( !v31 )
          goto LABEL_118;
        v32 = v31 - 1;
        if ( !v32 || (v33 = v32 - 1) == 0 )
        {
          v34 = 2;
          if ( lseeki64_nolock((unsigned int)*a2, 0, 2) )
          {
            if ( lseeki64_nolock((unsigned int)*a2, 0, 0) == -1 )
              goto LABEL_72;
LABEL_102:
            nolock = read_nolock(*a2, (WCHAR *)&v52, 3u);
            if ( nolock == -1 )
              goto LABEL_72;
            if ( nolock != 2 )
            {
              if ( nolock != 3 )
              {
LABEL_112:
                v36 = (unsigned int)lseek_nolock((unsigned int)*a2, 0, 0) == -1;
                goto LABEL_124;
              }
              if ( v52 == 12565487 )
              {
                v26 = 1;
                goto LABEL_130;
              }
            }
            if ( (unsigned __int16)v52 == 65534 )
            {
              close_nolock((unsigned int)*a2);
              v22 = 22;
              *errno() = 22;
              return v22;
            }
            if ( (unsigned __int16)v52 == 65279 )
            {
              if ( (unsigned int)lseek_nolock((unsigned int)*a2, 2, 0) == -1 )
                goto LABEL_72;
              v26 = 2;
LABEL_130:
              v22 = 0;
              v43 = *a2;
              v44 = 56 * (v43 & 0x1F);
              v45 = _pioinfo[v43 >> 5];
              *(_DWORD *)(v45 + v44 + 12) &= 0xFFFFFFFC;
              *(_DWORD *)(v45 + v44 + 12) |= v26;
              v46 = *a2;
              *(_DWORD *)(_pioinfo[v46 >> 5] + 56 * (v46 & 0x1F) + 12) ^= (*(_DWORD *)(_pioinfo[v46 >> 5]
                                                                                     + 56 * (v46 & 0x1F)
                                                                                     + 12)
                                                                         ^ (v6 >> 13))
                                                                        & 8;
              if ( !v50 && (v6 & 8) != 0 )
                *(_BYTE *)(_pioinfo[(__int64)*a2 >> 5] + 56LL * (*a2 & 0x1F) + 8) |= 0x20u;
              if ( (v11 & 0xC0000000) != 0xC0000000 || (v6 & 1) == 0 )
                return v22;
              CloseHandle(hObject);
              v47 = CreateFileA(a3, v11 & 0x7FFFFFFF, dwShareMode, &SecurityAttributes, 3u, v54, 0);
              if ( v47 != (HANDLE)-1LL )
              {
                *(_QWORD *)(56LL * (*a2 & 0x1F) + _pioinfo[(__int64)*a2 >> 5]) = v47;
                return v22;
              }
              v48 = GetLastError();
              dosmaperr(v48);
              *(_BYTE *)(_pioinfo[(__int64)*a2 >> 5] + 56LL * (*a2 & 0x1F) + 8) &= ~1u;
              free_osfhnd((unsigned int)*a2);
              return (unsigned int)*errno();
            }
            goto LABEL_112;
          }
LABEL_119:
          if ( v26 == 1 )
          {
            v34 = 3;
            v40 = 12565487;
          }
          else
          {
            if ( v26 != 2 )
              goto LABEL_130;
            v40 = 65279;
          }
          v41 = 0;
          v52 = v40;
          while ( 1 )
          {
            v42 = write(*a2, (char *)&v52 + v41, v34 - v41);
            if ( v42 == -1 )
              goto LABEL_72;
            v41 += v42;
            if ( v34 <= v41 )
              goto LABEL_130;
          }
        }
      }
      if ( v33 != 1 )
        goto LABEL_130;
      goto LABEL_118;
    }
  }
  *(_BYTE *)(_pioinfo[(__int64)*a2 >> 5] + 56LL * (*a2 & 0x1F) + 8) &= ~1u;
  v21 = GetLastError();
  dosmaperr(v21);
  return (unsigned int)*errno();
}

```

## disassembly

```asm
0x180020ee8  mov     [rsp-38h+arg_8], rbx
0x180020eed  mov     [rsp-38h+lpFileName], r8
0x180020ef2  mov     [rsp-38h+arg_0], rcx
0x180020ef7  push    rbp
0x180020ef8  push    rsi
0x180020ef9  push    rdi
0x180020efa  push    r12
0x180020efc  push    r13
0x180020efe  push    r14
0x180020f00  push    r15
0x180020f02  mov     rbp, rsp
0x180020f05  sub     rsp, 80h
0x180020f0c  xor     ebx, ebx
0x180020f0e  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x180020f16  xor     eax, eax
0x180020f18  mov     byte ptr [rbp+arg_18], bl
0x180020f1b  mov     r14d, r9d
0x180020f1e  mov     [rbp+PMode], ebx
0x180020f21  mov     r12d, 80h
0x180020f27  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rbx
0x180020f2b  and     r9d, r12d
0x180020f2e  lea     rcx, [rbp+PMode]; PMode
0x180020f32  mov     rdi, rdx
0x180020f35  setz    al
0x180020f38  neg     r9d
0x180020f3b  mov     [rbp+SecurityAttributes.bInheritHandle], eax
0x180020f3e  sbb     sil, sil
0x180020f41  and     sil, 10h
0x180020f45  call    _get_fmode
0x180020f4a  test    eax, eax
0x180020f4c  jz      short loc_180020F62
0x180020f4e  xor     r9d, r9d; LineNo
0x180020f51  mov     [rsp+80h+Reserved], rbx; Reserved
0x180020f56  xor     r8d, r8d; FileName
0x180020f59  xor     edx, edx; FunctionName
0x180020f5b  xor     ecx, ecx; Expression
0x180020f5d  call    _invoke_watson
0x180020f62  mov     eax, 8000h
0x180020f67  test    eax, r14d
0x180020f6a  jnz     short loc_180020F7E
0x180020f6c  test    r14d, 74000h
0x180020f73  jnz     short loc_180020F7A
0x180020f75  cmp     [rbp+PMode], eax
0x180020f78  jz      short loc_180020F7E
0x180020f7a  or      sil, 80h
0x180020f7e  mov     ecx, r14d
0x180020f81  mov     r10d, 3
0x180020f87  mov     edx, 80000000h
0x180020f8c  and     ecx, r10d
0x180020f8f  jz      short loc_180021001
0x180020f91  sub     ecx, 1
0x180020f94  jz      short loc_180020FD9
0x180020f96  cmp     ecx, 1
0x180020f99  jz      short loc_180020FD1
0x180020f9b  call    __doserrno
0x180020fa0  mov     [rax], ebx
0x180020fa2  mov     dword ptr [rdi], 0FFFFFFFFh
0x180020fa8  call    _errno
0x180020fad  mov     ebx, 16h
0x180020fb2  mov     [rsp+80h+Reserved], 0; Reserved
0x180020fbb  xor     r9d, r9d; LineNo
0x180020fbe  xor     r8d, r8d; FileName
0x180020fc1  xor     edx, edx; FunctionName
0x180020fc3  xor     ecx, ecx; Expression
0x180020fc5  mov     [rax], ebx
0x180020fc7  call    _invalid_parameter
0x180020fcc  jmp     loc_1800216C2
0x180020fd1  mov     r15d, 0C0000000h
0x180020fd7  jmp     short loc_180021004
0x180020fd9  test    r14d, 70000h
0x180020fe0  mov     r15d, ebx
0x180020fe3  setnz   r15b
0x180020fe7  test    r14b, 8
0x180020feb  setnz   al
0x180020fee  movzx   ecx, al
0x180020ff1  and     r15d, ecx
0x180020ff4  shl     r15d, 1Fh
0x180020ff8  add     r15d, 40000000h
0x180020fff  jmp     short loc_180021004
0x180021001  mov     r15d, edx
0x180021004  mov     ecx, [rbp+arg_20]
0x180021007  mov     r13d, 2
0x18002100d  lea     r9d, [r13-1]
0x180021011  sub     ecx, 10h
0x180021014  jz      short loc_18002104A
0x180021016  sub     ecx, 10h
0x180021019  jz      short loc_180021042
0x18002101b  sub     ecx, 10h
0x18002101e  jz      short loc_18002103D
0x180021020  sub     ecx, 10h
0x180021023  jz      short loc_180021038
0x180021025  cmp     ecx, 40h ; '@'
0x180021028  jnz     loc_180020F9B
0x18002102e  cmp     r15d, edx
0x180021031  mov     ecx, ebx
0x180021033  setz    cl
0x180021036  jmp     short loc_180021045
0x180021038  mov     ecx, r10d
0x18002103b  jmp     short loc_180021045
0x18002103d  mov     ecx, r13d
0x180021040  jmp     short loc_180021045
0x180021042  mov     ecx, r9d
0x180021045  mov     [rbp+dwShareMode], ecx
0x180021048  jmp     short loc_18002104F
0x18002104a  mov     ecx, ebx
0x18002104c  mov     [rbp+dwShareMode], ebx
0x18002104f  mov     eax, r14d
0x180021052  mov     edx, 700h
0x180021057  mov     r8d, 100h
0x18002105d  and     eax, edx
0x18002105f  jz      short loc_1800210A9
0x180021061  cmp     eax, r8d
0x180021064  jz      short loc_1800210A2
0x180021066  cmp     eax, 200h
0x18002106b  jz      short loc_18002109B
0x18002106d  cmp     eax, 300h
0x180021072  jz      short loc_180021096
0x180021074  cmp     eax, 400h
0x180021079  jz      short loc_1800210A9
0x18002107b  cmp     eax, 500h
0x180021080  jz      short loc_180021091
0x180021082  cmp     eax, 600h
0x180021087  jz      short loc_18002109B
0x180021089  cmp     eax, edx
0x18002108b  jnz     loc_180020F9B
0x180021091  mov     ebx, r9d
0x180021094  jmp     short loc_1800210AC
0x180021096  mov     ebx, r13d
0x180021099  jmp     short loc_1800210AC
0x18002109b  mov     ebx, 5
0x1800210a0  jmp     short loc_1800210AC
0x1800210a2  mov     ebx, 4
0x1800210a7  jmp     short loc_1800210AC
0x1800210a9  mov     ebx, r10d
0x1800210ac  test    r8d, r14d
0x1800210af  jz      short loc_1800210CB
0x1800210b1  mov     eax, cs:_umaskval
0x1800210b7  not     eax
0x1800210b9  and     eax, [rbp+arg_28]
0x1800210bc  and     al, r12b
0x1800210bf  neg     al
0x1800210c1  sbb     r12d, r12d
0x1800210c4  and     r12d, 7Fh
0x1800210c8  add     r12d, r9d
0x1800210cb  test    r14b, 40h
0x1800210cf  jz      short loc_1800210E1
0x1800210d1  bts     r12d, 1Ah
0x1800210d6  bts     r15d, 10h
0x1800210db  or      ecx, 4
0x1800210de  mov     [rbp+dwShareMode], ecx
0x1800210e1  mov     edx, r12d
0x1800210e4  or      edx, r8d
0x1800210e7  bt      r14d, 0Ch
0x1800210ec  cmovnb  edx, r12d
0x1800210f0  test    r14b, 20h
0x1800210f4  jz      short loc_1800210FF
0x1800210f6  bts     edx, 1Bh
0x1800210fa  mov     [rbp+var_30], edx
0x1800210fd  jmp     short loc_18002110F
0x1800210ff  mov     ecx, edx
0x180021101  bts     ecx, 1Ch
0x180021105  test    r14b, 10h
0x180021109  cmovz   ecx, edx
0x18002110c  mov     [rbp+var_30], ecx
0x18002110f  call    _alloc_osfhnd
0x180021114  mov     [rdi], eax
0x180021116  cmp     eax, 0FFFFFFFFh
0x180021119  jnz     short loc_18002113F
0x18002111b  call    __doserrno
0x180021120  mov     dword ptr [rax], 0
0x180021126  mov     dword ptr [rdi], 0FFFFFFFFh
0x18002112c  call    _errno
0x180021131  mov     ecx, 18h
0x180021136  mov     [rax], ecx
0x180021138  mov     eax, ecx
0x18002113a  jmp     loc_1800216C4
0x18002113f  mov     rax, [rbp+arg_0]
0x180021143  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x180021147  mov     r12d, [rbp+var_30]
0x18002114b  mov     edx, r15d; dwDesiredAccess
0x18002114e  mov     r8d, [rbp+dwShareMode]; dwShareMode
0x180021152  mov     rcx, [rbp+lpFileName]; lpFileName
0x180021156  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18002115f  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180021164  mov     dword ptr [rax], 1
0x18002116a  mov     dword ptr [rsp+80h+Reserved], ebx; dwCreationDisposition
0x18002116e  call    cs:__imp_CreateFileA
0x180021174  mov     [rbp+hObject], rax
0x180021178  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002117c  jnz     loc_18002120A
0x180021182  mov     ecx, 0C0000000h
0x180021187  mov     eax, r15d
0x18002118a  and     eax, ecx
0x18002118c  cmp     eax, ecx
0x18002118e  jnz     short loc_1800211CF
0x180021190  test    r14b, 1
0x180021194  jz      short loc_1800211CF
0x180021196  mov     r8d, [rbp+dwShareMode]; dwShareMode
0x18002119a  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x18002119e  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800211a2  btr     r15d, 1Fh
0x1800211a7  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1800211b0  mov     edx, r15d; dwDesiredAccess
0x1800211b3  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800211b8  mov     dword ptr [rsp+80h+Reserved], ebx; dwCreationDisposition
0x1800211bc  call    cs:__imp_CreateFileA
0x1800211c2  mov     [rbp+hObject], rax
0x1800211c6  mov     r12, rax
0x1800211c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800211cd  jnz     short loc_18002120D
0x1800211cf  movsxd  rcx, dword ptr [rdi]
0x1800211d2  lea     r13, __pioinfo
0x1800211d9  mov     rax, rcx
0x1800211dc  and     ecx, 1Fh
0x1800211df  imul    rcx, 38h ; '8'
0x1800211e3  sar     rax, 5
0x1800211e7  mov     rax, [r13+rax*8+0]
0x1800211ec  and     byte ptr [rax+rcx+8], 0FEh
0x1800211f1  call    cs:__imp_GetLastError
0x1800211f7  mov     ecx, eax
0x1800211f9  call    _dosmaperr
0x1800211fe  call    _errno
0x180021203  mov     ebx, [rax]
0x180021205  jmp     loc_1800216C2
0x18002120a  mov     r12, rax
0x18002120d  mov     rcx, r12; hFile
0x180021210  call    cs:__imp_GetFileType
0x180021216  test    eax, eax
0x180021218  jnz     short loc_180021265
0x18002121a  movsxd  rcx, dword ptr [rdi]
0x18002121d  lea     r13, __pioinfo
0x180021224  mov     rax, rcx
0x180021227  and     ecx, 1Fh
0x18002122a  imul    rcx, 38h ; '8'
0x18002122e  sar     rax, 5
0x180021232  mov     rax, [r13+rax*8+0]
0x180021237  and     byte ptr [rax+rcx+8], 0FEh
0x18002123c  call    cs:__imp_GetLastError
0x180021242  mov     ecx, eax
0x180021244  mov     ebx, eax
0x180021246  call    _dosmaperr
0x18002124b  mov     rcx, r12; hObject
0x18002124e  call    cs:__imp_CloseHandle
0x180021254  test    ebx, ebx
0x180021256  jnz     short loc_1800211FE
0x180021258  call    _errno
0x18002125d  mov     dword ptr [rax], 0Dh
0x180021263  jmp     short loc_1800211FE
0x180021265  cmp     eax, r13d
0x180021268  jnz     short loc_180021270
0x18002126a  or      sil, 40h
0x18002126e  jmp     short loc_180021279
0x180021270  cmp     eax, 3
0x180021273  jnz     short loc_180021279
0x180021275  or      sil, 8
0x180021279  mov     ecx, [rdi]
0x18002127b  mov     rdx, r12
0x18002127e  call    _set_osfhnd
0x180021283  cmp     eax, 0FFFFFFFFh
0x180021286  jnz     short loc_180021299
0x180021288  mov     rcx, r12; hObject
0x18002128b  call    cs:__imp_CloseHandle
0x180021291  or      eax, 0FFFFFFFFh
0x180021294  jmp     loc_1800216C4
0x180021299  movsxd  rcx, dword ptr [rdi]
0x18002129c  lea     r13, __pioinfo
0x1800212a3  mov     rax, rcx
0x1800212a6  or      sil, 1
0x1800212aa  sar     rax, 5
0x1800212ae  and     ecx, 1Fh
0x1800212b1  imul    rcx, 38h ; '8'
0x1800212b5  mov     rax, [r13+rax*8+0]
0x1800212ba  mov     [rax+rcx+8], sil
0x1800212bf  movsxd  rcx, dword ptr [rdi]
0x1800212c2  mov     rax, rcx
0x1800212c5  and     ecx, 1Fh
0x1800212c8  sar     rax, 5
0x1800212cc  imul    rcx, 38h ; '8'
0x1800212d0  mov     rax, [r13+rax*8+0]
0x1800212d5  and     dword ptr [rax+rcx+0Ch], 0FFFFFFFCh
0x1800212da  mov     al, sil
0x1800212dd  and     al, 48h
0x1800212df  mov     [rbp+var_40], al
0x1800212e2  jnz     loc_18002136A
0x1800212e8  test    sil, sil
0x1800212eb  jns     short loc_18002136A
0x1800212ed  mov     eax, 2
0x1800212f2  test    al, r14b
0x1800212f5  jz      short loc_18002136A
0x1800212f7  mov     ecx, [rdi]
0x1800212f9  mov     r8d, eax
0x1800212fc  or      edx, 0FFFFFFFFh
0x1800212ff  call    _lseek_nolock
0x180021304  movsxd  r12, eax
0x180021307  cmp     r12d, 0FFFFFFFFh
0x18002130b  jnz     short loc_18002132B
0x18002130d  call    __doserrno
0x180021312  cmp     dword ptr [rax], 83h
0x180021318  jz      short loc_180021326
0x18002131a  mov     ecx, [rdi]
  ... truncated ...
```
