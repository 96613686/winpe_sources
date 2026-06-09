# _tsopen_nolock_0

- ea: `0x1800227c0`
- end: `0x180022fbc`
- name: `_tsopen_nolock_0`
- size: `2044`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180022fd0`
- `0x1800230dc`

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
- `0x180021c08`
- `0x1800227c0`
- `0x180023210`
- `0x18002f050`
- `0x18002f05c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022f51`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022a4a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022a98`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022f45`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022a4a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022a98`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022f45`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180022aec`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180022aec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022f17`

## pseudocode

```c
__int64 __fastcall tsopen_nolock_0(_DWORD *a1, int *a2, const WCHAR *a3, unsigned int a4, int a5, char a6)
{
  unsigned int v6; // r12d
  unsigned int v7; // r14d
  char v9; // si
  DWORD v10; // r15d
  __int64 v11; // rcx
  int v12; // eax
  DWORD v13; // ebx
  __int64 v14; // rdx
  int v15; // eax
  DWORD v17; // r12d
  DWORD v18; // r8d
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
  WCHAR v50[2]; // [rsp+40h] [rbp-40h] BYREF
  DWORD dwShareMode; // [rsp+44h] [rbp-3Ch]
  int v52; // [rsp+48h] [rbp-38h] BYREF
  int PMode; // [rsp+4Ch] [rbp-34h] BYREF
  DWORD v54; // [rsp+50h] [rbp-30h]
  HANDLE hObject; // [rsp+58h] [rbp-28h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-20h] BYREF
  char v59; // [rsp+D8h] [rbp+58h]

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  v50[0] = 0;
  PMode = 0;
  v6 = 128;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v7 = a4;
  SecurityAttributes.bInheritHandle = (a4 & 0x80) == 0;
  v9 = (a4 & 0x80) != 0 ? 0x10 : 0;
  if ( get_fmode(&PMode) )
    invoke_watson(0, 0, 0, 0, 0);
  if ( (v7 & 0x8000) == 0 && ((v7 & 0x74000) != 0 || PMode != 0x8000) )
    v9 |= 0x80u;
  if ( (v7 & 3) != 0 )
  {
    if ( (v7 & 3) == 1 )
    {
      v10 = (((v7 & 8) != 0 && (v7 & 0x70000) != 0) << 31) + 0x40000000;
    }
    else
    {
      if ( (v7 & 3) != 2 )
        goto LABEL_10;
      v10 = -1073741824;
    }
  }
  else
  {
    v10 = 0x80000000;
  }
  if ( a5 == 16 )
  {
    v11 = 0;
    dwShareMode = 0;
  }
  else
  {
    switch ( a5 )
    {
      case 32:
        v11 = 1;
        break;
      case 48:
        v11 = 2;
        break;
      case 64:
        v11 = 3;
        break;
      case 128:
        v11 = v10 == 0x80000000;
        break;
      default:
        goto LABEL_10;
    }
    dwShareMode = v11;
  }
  v12 = v7 & 0x700;
  if ( (v7 & 0x700) != 0 )
  {
    switch ( v12 )
    {
      case 256:
        v13 = 4;
        goto LABEL_38;
      case 512:
LABEL_35:
        v13 = 5;
        goto LABEL_38;
      case 768:
        v13 = 2;
        goto LABEL_38;
    }
    if ( v12 != 1024 )
    {
      if ( v12 == 1280 )
      {
LABEL_33:
        v13 = 1;
        goto LABEL_38;
      }
      if ( v12 != 1536 )
      {
        if ( v12 == 1792 )
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
  v13 = 3;
LABEL_38:
  if ( (v7 & 0x100) != 0 )
    v6 = (a6 & ~(_BYTE)umaskval & 0x80u) != 0 ? 128 : 1;
  if ( (v7 & 0x40) != 0 )
  {
    v6 |= 0x4000000u;
    v10 |= 0x10000u;
    v11 = (unsigned int)v11 | 4;
    dwShareMode = v11;
  }
  v14 = v6 | 0x100;
  if ( (v7 & 0x1000) == 0 )
    v14 = v6;
  if ( (v7 & 0x20) != 0 )
  {
    LODWORD(v14) = v14 | 0x8000000;
    v54 = v14;
  }
  else
  {
    v11 = (unsigned int)v14;
    LODWORD(v11) = v14 | 0x10000000;
    if ( (v7 & 0x10) == 0 )
      v11 = (unsigned int)v14;
    v54 = v11;
  }
  v15 = alloc_osfhnd(v11, v14, 256, 1);
  *a2 = v15;
  if ( v15 == -1 )
  {
    *_doserrno() = 0;
    *a2 = -1;
    *errno() = 24;
    return 24;
  }
  v17 = v54;
  v18 = dwShareMode;
  dwFlagsAndAttributes = v54;
  *a1 = 1;
  v19 = CreateFileW(a3, v10, v18, &SecurityAttributes, v13, dwFlagsAndAttributes, 0);
  hObject = v19;
  if ( v19 != (HANDLE)-1LL )
  {
    v20 = v19;
    goto LABEL_58;
  }
  if ( (v10 & 0xC0000000) == 0xC0000000 && (v7 & 1) != 0 )
  {
    v10 &= ~0x80000000;
    hObject = CreateFileW(a3, v10, dwShareMode, &SecurityAttributes, v13, v17, 0);
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
          v9 |= 0x40u;
          break;
        case 3u:
          v9 |= 8u;
          break;
      }
      if ( (unsigned int)set_osfhnd((unsigned int)*a2, v20) == -1 )
      {
        CloseHandle(v20);
        return 0xFFFFFFFFLL;
      }
      v25 = v9 | 1;
      *(_BYTE *)(_pioinfo[(__int64)*a2 >> 5] + 56LL * (*a2 & 0x1F) + 8) = v25;
      *(_DWORD *)(_pioinfo[(__int64)*a2 >> 5] + 56LL * (*a2 & 0x1F) + 12) &= 0xFFFFFFFC;
      v59 = v25 & 0x48;
      if ( (v25 & 0x48) == 0 && v25 < 0 && (v7 & 2) != 0 )
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
        v50[0] = 0;
        if ( !(unsigned int)read_nolock(v27, v50, 1u) && v50[0] == 26 && (unsigned int)chsize_nolock(*a2) == -1
          || (unsigned int)lseek_nolock((unsigned int)*a2, 0, 0) == -1 )
        {
          goto LABEL_72;
        }
      }
      v26 = 0;
      if ( v25 >= 0 )
        goto LABEL_130;
LABEL_79:
      if ( (v7 & 0x74000) == 0 )
      {
        if ( (PMode & 0x74000) != 0 )
          v7 |= PMode & 0x74000;
        else
          v7 |= 0x4000u;
      }
      v28 = v7 & 0x74000;
      if ( (v7 & 0x74000) == 0x4000 )
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
        v26 = (v7 & 0x301) != 769 ? 0 : 2;
      }
      if ( (v7 & 0x70000) == 0 )
        goto LABEL_130;
      v52 = 0;
      if ( (v25 & 0x40) != 0 )
        goto LABEL_130;
      v29 = v10 & 0xC0000000;
      if ( (v10 & 0xC0000000) == 0x40000000 )
      {
        v37 = v13 - 1;
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
        v30 = v13 - 1;
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
                                                                         ^ (v7 >> 13))
                                                                        & 8;
              if ( !v59 && (v7 & 8) != 0 )
                *(_BYTE *)(_pioinfo[(__int64)*a2 >> 5] + 56LL * (*a2 & 0x1F) + 8) |= 0x20u;
              if ( (v10 & 0xC0000000) != 0xC0000000 || (v7 & 1) == 0 )
                return v22;
              CloseHandle(hObject);
              v47 = CreateFileW(a3, v10 & 0x7FFFFFFF, dwShareMode, &SecurityAttributes, 3u, v54, 0);
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
0x1800227c0  mov     [rsp-38h+arg_8], rbx
0x1800227c5  mov     [rsp-38h+lpFileName], r8
0x1800227ca  mov     [rsp-38h+arg_0], rcx
0x1800227cf  push    rbp
0x1800227d0  push    rsi
0x1800227d1  push    rdi
0x1800227d2  push    r12
0x1800227d4  push    r13
0x1800227d6  push    r14
0x1800227d8  push    r15
0x1800227da  mov     rbp, rsp
0x1800227dd  sub     rsp, 80h
0x1800227e4  xor     ebx, ebx
0x1800227e6  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x1800227ee  xor     eax, eax
0x1800227f0  mov     [rbp+var_40], bx
0x1800227f4  mov     r8d, r9d
0x1800227f7  mov     [rbp+PMode], ebx
0x1800227fa  mov     r12d, 80h
0x180022800  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rbx
0x180022804  and     r8d, r12d
0x180022807  lea     rcx, [rbp+PMode]; PMode
0x18002280b  mov     r14d, r9d
0x18002280e  mov     rdi, rdx
0x180022811  setz    al
0x180022814  neg     r8d
0x180022817  mov     [rbp+SecurityAttributes.bInheritHandle], eax
0x18002281a  sbb     sil, sil
0x18002281d  and     sil, 10h
0x180022821  call    _get_fmode
0x180022826  test    eax, eax
0x180022828  jz      short loc_18002283E
0x18002282a  xor     r9d, r9d; LineNo
0x18002282d  mov     [rsp+80h+Reserved], rbx; Reserved
0x180022832  xor     r8d, r8d; FileName
0x180022835  xor     edx, edx; FunctionName
0x180022837  xor     ecx, ecx; Expression
0x180022839  call    _invoke_watson
0x18002283e  mov     eax, 8000h
0x180022843  test    eax, r14d
0x180022846  jnz     short loc_18002285A
0x180022848  test    r14d, 74000h
0x18002284f  jnz     short loc_180022856
0x180022851  cmp     [rbp+PMode], eax
0x180022854  jz      short loc_18002285A
0x180022856  or      sil, 80h
0x18002285a  mov     ecx, r14d
0x18002285d  mov     r10d, 3
0x180022863  mov     edx, 80000000h
0x180022868  and     ecx, r10d
0x18002286b  jz      short loc_1800228DD
0x18002286d  sub     ecx, 1
0x180022870  jz      short loc_1800228B5
0x180022872  cmp     ecx, 1
0x180022875  jz      short loc_1800228AD
0x180022877  call    __doserrno
0x18002287c  mov     [rax], ebx
0x18002287e  mov     dword ptr [rdi], 0FFFFFFFFh
0x180022884  call    _errno
0x180022889  mov     ebx, 16h
0x18002288e  mov     [rsp+80h+Reserved], 0; Reserved
0x180022897  xor     r9d, r9d; LineNo
0x18002289a  xor     r8d, r8d; FileName
0x18002289d  xor     edx, edx; FunctionName
0x18002289f  xor     ecx, ecx; Expression
0x1800228a1  mov     [rax], ebx
0x1800228a3  call    _invalid_parameter
0x1800228a8  jmp     loc_180022F9F
0x1800228ad  mov     r15d, 0C0000000h
0x1800228b3  jmp     short loc_1800228E0
0x1800228b5  test    r14d, 70000h
0x1800228bc  mov     r15d, ebx
0x1800228bf  setnz   r15b
0x1800228c3  test    r14b, 8
0x1800228c7  setnz   al
0x1800228ca  movzx   ecx, al
0x1800228cd  and     r15d, ecx
0x1800228d0  shl     r15d, 1Fh
0x1800228d4  add     r15d, 40000000h
0x1800228db  jmp     short loc_1800228E0
0x1800228dd  mov     r15d, edx
0x1800228e0  mov     ecx, [rbp+arg_20]
0x1800228e3  mov     r13d, 2
0x1800228e9  lea     r9d, [r13-1]
0x1800228ed  sub     ecx, 10h
0x1800228f0  jz      short loc_180022926
0x1800228f2  sub     ecx, 10h
0x1800228f5  jz      short loc_18002291E
0x1800228f7  sub     ecx, 10h
0x1800228fa  jz      short loc_180022919
0x1800228fc  sub     ecx, 10h
0x1800228ff  jz      short loc_180022914
0x180022901  cmp     ecx, 40h ; '@'
0x180022904  jnz     loc_180022877
0x18002290a  cmp     r15d, edx
0x18002290d  mov     ecx, ebx
0x18002290f  setz    cl
0x180022912  jmp     short loc_180022921
0x180022914  mov     ecx, r10d
0x180022917  jmp     short loc_180022921
0x180022919  mov     ecx, r13d
0x18002291c  jmp     short loc_180022921
0x18002291e  mov     ecx, r9d
0x180022921  mov     [rbp+dwShareMode], ecx
0x180022924  jmp     short loc_18002292B
0x180022926  mov     ecx, ebx
0x180022928  mov     [rbp+dwShareMode], ebx
0x18002292b  mov     eax, r14d
0x18002292e  mov     edx, 700h
0x180022933  mov     r8d, 100h
0x180022939  and     eax, edx
0x18002293b  jz      short loc_180022985
0x18002293d  cmp     eax, r8d
0x180022940  jz      short loc_18002297E
0x180022942  cmp     eax, 200h
0x180022947  jz      short loc_180022977
0x180022949  cmp     eax, 300h
0x18002294e  jz      short loc_180022972
0x180022950  cmp     eax, 400h
0x180022955  jz      short loc_180022985
0x180022957  cmp     eax, 500h
0x18002295c  jz      short loc_18002296D
0x18002295e  cmp     eax, 600h
0x180022963  jz      short loc_180022977
0x180022965  cmp     eax, edx
0x180022967  jnz     loc_180022877
0x18002296d  mov     ebx, r9d
0x180022970  jmp     short loc_180022988
0x180022972  mov     ebx, r13d
0x180022975  jmp     short loc_180022988
0x180022977  mov     ebx, 5
0x18002297c  jmp     short loc_180022988
0x18002297e  mov     ebx, 4
0x180022983  jmp     short loc_180022988
0x180022985  mov     ebx, r10d
0x180022988  test    r8d, r14d
0x18002298b  jz      short loc_1800229A7
0x18002298d  mov     eax, cs:_umaskval
0x180022993  not     eax
0x180022995  and     eax, [rbp+arg_28]
0x180022998  and     al, r12b
0x18002299b  neg     al
0x18002299d  sbb     r12d, r12d
0x1800229a0  and     r12d, 7Fh
0x1800229a4  add     r12d, r9d
0x1800229a7  test    r14b, 40h
0x1800229ab  jz      short loc_1800229BD
0x1800229ad  bts     r12d, 1Ah
0x1800229b2  bts     r15d, 10h
0x1800229b7  or      ecx, 4
0x1800229ba  mov     [rbp+dwShareMode], ecx
0x1800229bd  mov     edx, r12d
0x1800229c0  or      edx, r8d
0x1800229c3  bt      r14d, 0Ch
0x1800229c8  cmovnb  edx, r12d
0x1800229cc  test    r14b, 20h
0x1800229d0  jz      short loc_1800229DB
0x1800229d2  bts     edx, 1Bh
0x1800229d6  mov     [rbp+var_30], edx
0x1800229d9  jmp     short loc_1800229EB
0x1800229db  mov     ecx, edx
0x1800229dd  bts     ecx, 1Ch
0x1800229e1  test    r14b, 10h
0x1800229e5  cmovz   ecx, edx
0x1800229e8  mov     [rbp+var_30], ecx
0x1800229eb  call    _alloc_osfhnd
0x1800229f0  mov     [rdi], eax
0x1800229f2  cmp     eax, 0FFFFFFFFh
0x1800229f5  jnz     short loc_180022A1B
0x1800229f7  call    __doserrno
0x1800229fc  mov     dword ptr [rax], 0
0x180022a02  mov     dword ptr [rdi], 0FFFFFFFFh
0x180022a08  call    _errno
0x180022a0d  mov     ecx, 18h
0x180022a12  mov     [rax], ecx
0x180022a14  mov     eax, ecx
0x180022a16  jmp     loc_180022FA1
0x180022a1b  mov     rax, [rbp+arg_0]
0x180022a1f  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x180022a23  mov     r12d, [rbp+var_30]
0x180022a27  mov     edx, r15d; dwDesiredAccess
0x180022a2a  mov     r8d, [rbp+dwShareMode]; dwShareMode
0x180022a2e  mov     rcx, [rbp+lpFileName]; lpFileName
0x180022a32  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180022a3b  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180022a40  mov     dword ptr [rax], 1
0x180022a46  mov     dword ptr [rsp+80h+Reserved], ebx; dwCreationDisposition
0x180022a4a  call    cs:__imp_CreateFileW
0x180022a50  mov     [rbp+hObject], rax
0x180022a54  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022a58  jnz     loc_180022AE6
0x180022a5e  mov     ecx, 0C0000000h
0x180022a63  mov     eax, r15d
0x180022a66  and     eax, ecx
0x180022a68  cmp     eax, ecx
0x180022a6a  jnz     short loc_180022AAB
0x180022a6c  test    r14b, 1
0x180022a70  jz      short loc_180022AAB
0x180022a72  mov     r8d, [rbp+dwShareMode]; dwShareMode
0x180022a76  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x180022a7a  mov     rcx, [rbp+lpFileName]; lpFileName
0x180022a7e  btr     r15d, 1Fh
0x180022a83  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180022a8c  mov     edx, r15d; dwDesiredAccess
0x180022a8f  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180022a94  mov     dword ptr [rsp+80h+Reserved], ebx; dwCreationDisposition
0x180022a98  call    cs:__imp_CreateFileW
0x180022a9e  mov     [rbp+hObject], rax
0x180022aa2  mov     r12, rax
0x180022aa5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022aa9  jnz     short loc_180022AE9
0x180022aab  movsxd  rcx, dword ptr [rdi]
0x180022aae  lea     r13, __pioinfo
0x180022ab5  mov     rax, rcx
0x180022ab8  and     ecx, 1Fh
0x180022abb  imul    rcx, 38h ; '8'
0x180022abf  sar     rax, 5
0x180022ac3  mov     rax, [r13+rax*8+0]
0x180022ac8  and     byte ptr [rax+rcx+8], 0FEh
0x180022acd  call    cs:__imp_GetLastError
0x180022ad3  mov     ecx, eax
0x180022ad5  call    _dosmaperr
0x180022ada  call    _errno
0x180022adf  mov     ebx, [rax]
0x180022ae1  jmp     loc_180022F9F
0x180022ae6  mov     r12, rax
0x180022ae9  mov     rcx, r12; hFile
0x180022aec  call    cs:__imp_GetFileType
0x180022af2  test    eax, eax
0x180022af4  jnz     short loc_180022B41
0x180022af6  movsxd  rcx, dword ptr [rdi]
0x180022af9  lea     r13, __pioinfo
0x180022b00  mov     rax, rcx
0x180022b03  and     ecx, 1Fh
0x180022b06  imul    rcx, 38h ; '8'
0x180022b0a  sar     rax, 5
0x180022b0e  mov     rax, [r13+rax*8+0]
0x180022b13  and     byte ptr [rax+rcx+8], 0FEh
0x180022b18  call    cs:__imp_GetLastError
0x180022b1e  mov     ecx, eax
0x180022b20  mov     ebx, eax
0x180022b22  call    _dosmaperr
0x180022b27  mov     rcx, r12; hObject
0x180022b2a  call    cs:__imp_CloseHandle
0x180022b30  test    ebx, ebx
0x180022b32  jnz     short loc_180022ADA
0x180022b34  call    _errno
0x180022b39  mov     dword ptr [rax], 0Dh
0x180022b3f  jmp     short loc_180022ADA
0x180022b41  cmp     eax, r13d
0x180022b44  jnz     short loc_180022B4C
0x180022b46  or      sil, 40h
0x180022b4a  jmp     short loc_180022B55
0x180022b4c  cmp     eax, 3
0x180022b4f  jnz     short loc_180022B55
0x180022b51  or      sil, 8
0x180022b55  mov     ecx, [rdi]
0x180022b57  mov     rdx, r12
0x180022b5a  call    _set_osfhnd
0x180022b5f  cmp     eax, 0FFFFFFFFh
0x180022b62  jnz     short loc_180022B75
0x180022b64  mov     rcx, r12; hObject
0x180022b67  call    cs:__imp_CloseHandle
0x180022b6d  or      eax, 0FFFFFFFFh
0x180022b70  jmp     loc_180022FA1
0x180022b75  movsxd  rcx, dword ptr [rdi]
0x180022b78  lea     r13, __pioinfo
0x180022b7f  mov     rax, rcx
0x180022b82  or      sil, 1
0x180022b86  sar     rax, 5
0x180022b8a  and     ecx, 1Fh
0x180022b8d  imul    rcx, 38h ; '8'
0x180022b91  mov     rax, [r13+rax*8+0]
0x180022b96  mov     [rax+rcx+8], sil
0x180022b9b  movsxd  rcx, dword ptr [rdi]
0x180022b9e  mov     rax, rcx
0x180022ba1  and     ecx, 1Fh
0x180022ba4  sar     rax, 5
0x180022ba8  imul    rcx, 38h ; '8'
0x180022bac  mov     rax, [r13+rax*8+0]
0x180022bb1  and     dword ptr [rax+rcx+0Ch], 0FFFFFFFCh
0x180022bb6  mov     al, sil
0x180022bb9  and     al, 48h
0x180022bbb  mov     [rbp+arg_18], al
0x180022bbe  jnz     loc_180022C47
0x180022bc4  test    sil, sil
0x180022bc7  jns     short loc_180022C47
0x180022bc9  mov     eax, 2
0x180022bce  test    al, r14b
0x180022bd1  jz      short loc_180022C47
0x180022bd3  mov     ecx, [rdi]
0x180022bd5  mov     r8d, eax
0x180022bd8  or      edx, 0FFFFFFFFh
0x180022bdb  call    _lseek_nolock
0x180022be0  movsxd  r12, eax
0x180022be3  cmp     r12d, 0FFFFFFFFh
0x180022be7  jnz     short loc_180022C07
0x180022be9  call    __doserrno
0x180022bee  cmp     dword ptr [rax], 83h
0x180022bf4  jz      short loc_180022C02
  ... truncated ...
```
