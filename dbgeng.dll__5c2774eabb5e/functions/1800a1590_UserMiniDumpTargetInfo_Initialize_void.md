# UserMiniDumpTargetInfo::Initialize(void)

- ea: `0x1800a1590`
- end: `0x1800a1fda`
- name: `?Initialize@UserMiniDumpTargetInfo@@UEAAJXZ`
- size: `2634`
- prototype: `__int64 __fastcall(UserMiniDumpTargetInfo *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180072800`
- `0x18020c680`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x1800986ec`
- `0x1800a1590`
- `0x1800c12b8`
- `0x1800e846c`
- `0x1800f16fc`
- `0x1801fdcdc`
- `0x180207c84`
- `0x18020aa80`
- `0x180298728`
- `0x1802988cc`
- `0x1802be854`
- `0x1802d0780`
- `0x1804da4c0`
- `0x1804da880`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1800a1f35`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1800a1f6f`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1800a1f35`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1800a1f6f`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800a1d45`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800a1d63`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800a1d45`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800a1d63`

## string_xrefs

- `0x1800a1784`: `Directory`
- `0x1800a19a5`: `Comment: '%hs'\n`
- `0x1800a197d`: `Comment: '%ls'\n`
- `0x1800a1bcc`: `The stack provider .dll could not be loaded. The corresponding stack metadata will not be decoded. \n`
- `0x1800a1bd5`: `Stack provider was already loaded. Skipping new load.\n`
- `0x1800a1dfd`: `WARNING: Ignoring invalid thread ID %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserMiniDumpTargetInfo::Initialize(UserMiniDumpTargetInfo *this)
{
  __int64 v2; // rdx
  _DWORD *v3; // rcx
  _DWORD *v4; // rcx
  int *v5; // r8
  int *v6; // rcx
  int *v7; // r8
  int *v8; // rcx
  int *v9; // r8
  struct _MINIDUMP_DIRECTORY *v10; // rsi
  __int64 result; // rax
  __int64 v12; // rcx
  unsigned int i; // r14d
  void **v14; // r9
  unsigned int **v15; // rdi
  unsigned int *v16; // r8
  __int64 v17; // rdx
  char v18; // al
  int **v19; // rdi
  int *v20; // rcx
  int v21; // eax
  _QWORD **v22; // rdi
  _QWORD *v23; // r8
  __int64 v24; // rdx
  char v25; // al
  char *v26; // rdi
  unsigned int *v27; // rax
  unsigned __int64 v28; // r9
  __int64 v29; // rdx
  char v30; // al
  size_t DataSize; // r8
  StackProvider *v32; // rax
  unsigned __int16 *v33; // rdx
  const unsigned __int16 *v34; // r8
  StackProvider *v35; // rax
  unsigned int v36; // edx
  int v37; // eax
  __int64 v38; // rcx
  int v39; // eax
  int v40; // edx
  __int64 v41; // rdx
  int v42; // ecx
  wint_t *v43; // rdi
  __int64 v44; // rsi
  wint_t *v45; // r14
  int v46; // esi
  wint_t j; // ax
  int v48; // eax
  int *v49; // rax
  int v50; // eax
  __int64 v51; // rcx
  _DWORD *v52; // rcx
  size_t *v53; // rdi
  size_t v54; // rdi
  void *v55; // rax
  void *v56; // rax
  __int64 v57; // r8
  unsigned int k; // edx
  __int128 v59; // [rsp+48h] [rbp-21h] BYREF
  __int128 v60; // [rsp+58h] [rbp-11h]
  __int128 v61; // [rsp+68h] [rbp-1h] BYREF
  __int64 v62; // [rsp+78h] [rbp+Fh]
  void *v63; // [rsp+D0h] [rbp+67h] BYREF
  void *Src; // [rsp+D8h] [rbp+6Fh] BYREF
  void *v65; // [rsp+E0h] [rbp+77h] BYREF
  StackProvider *v66; // [rsp+E8h] [rbp+7Fh]

  v2 = *((_QWORD *)this + 272);
  *((_QWORD *)this + 559) = v2;
  *((_QWORD *)this + 560) = 0;
  *((_DWORD *)this + 1106) = *(unsigned __int16 *)(v2 + 4);
  *((_DWORD *)this + 1107) = *(unsigned __int16 *)(v2 + 6);
  v3 = (_DWORD *)((char *)this + 4216);
  if ( (*(_BYTE *)(v2 + 24) & 2) != 0 )
    *v3 |= 1u;
  if ( (*(_DWORD *)(v2 + 24) & 0x20000) != 0 )
    *v3 |= 0x8000000u;
  if ( (*(_BYTE *)(v2 + 24) & 4) != 0 )
    *v3 |= 2u;
  if ( (*(_BYTE *)(v2 + 24) & 0x20) != 0 )
    *v3 |= 4u;
  if ( (*(_BYTE *)(v2 + 24) & 0x40) != 0 )
    *v3 |= 8u;
  if ( (*(_DWORD *)(v2 + 24) & 0x2000LL) != 0 )
    *v3 |= 0x1000u;
  if ( (*(_BYTE *)(v2 + 24) & 1) != 0 )
    *((_DWORD *)this + 1054) = *v3 | 0x10;
  v4 = (_DWORD *)((char *)this + 4216);
  if ( (*(_BYTE *)(v2 + 24) & 8) != 0 )
    *v4 |= 0x20u;
  if ( *(char *)(v2 + 24) < 0 )
    *v4 |= 0x40u;
  v5 = (int *)((char *)this + 4216);
  if ( (*(_DWORD *)(v2 + 24) & 0x100LL) != 0 )
    *v4 |= 0x80u;
  else
    v5 = (int *)((char *)this + 4216);
  if ( (*(_DWORD *)(v2 + 24) & 0x200LL) != 0 )
  {
    *v5 = *v4 | 0x100;
    v6 = (int *)((char *)this + 4216);
  }
  else
  {
    v6 = v5;
  }
  if ( (*(_DWORD *)(v2 + 24) & 0x80000) != 0 )
    *v5 |= 0x8000u;
  else
    v6 = v5;
  if ( (*(_DWORD *)(v2 + 24) & 0x100000) != 0 )
  {
    *v6 = *v5 | 0x10000;
    v7 = (int *)((char *)this + 4216);
  }
  else
  {
    v7 = v6;
  }
  if ( (*(_DWORD *)(v2 + 24) & 0x400LL) != 0 )
    *v6 |= 0x200u;
  else
    v7 = v6;
  if ( (*(_DWORD *)(v2 + 24) & 0x800LL) != 0 )
  {
    *v7 = *v6 | 0x400;
    v8 = (int *)((char *)this + 4216);
  }
  else
  {
    v8 = v7;
  }
  if ( (*(_DWORD *)(v2 + 24) & 0x1000LL) != 0 )
    *v7 |= 0x800u;
  else
    v8 = v7;
  if ( (*(_DWORD *)(v2 + 24) & 0x4000LL) != 0 )
  {
    *v8 = *v7 | 0x2000;
    v9 = (int *)((char *)this + 4216);
  }
  else
  {
    v9 = v8;
  }
  if ( (*(_DWORD *)(v2 + 24) & 0x8000LL) != 0 )
    *v8 |= 0x4000u;
  else
    v9 = v8;
  if ( (*(_DWORD *)(v2 + 24) & 0x200000) != 0 )
    *v9 = *v8 | 0x20000;
  Src = 0;
  v65 = 0;
  v10 = (struct _MINIDUMP_DIRECTORY *)(*(__int64 (__fastcall **)(UserMiniDumpTargetInfo *, __int64, _QWORD, _QWORD, _DWORD, const wchar_t *))(*(_QWORD *)this + 1576LL))(
                                        this,
                                        v2,
                                        *(unsigned int *)(v2 + 12),
                                        (unsigned int)(12 * *(_DWORD *)(v2 + 8)),
                                        0,
                                        L"Directory");
  if ( !v10 )
    return 2147943792LL;
  v12 = *((_QWORD *)this + 559);
  if ( *(_DWORD *)(v12 + 8) )
  {
    for ( i = 0; i < *(_DWORD *)(v12 + 8); ++i )
    {
      if ( v10->StreamType > 0xE )
      {
        if ( v10->StreamType > 0x7000 )
        {
          if ( v10->StreamType <= 0xFFFF )
LABEL_142:
            WarnOut(L"WARNING: Minidump contains unknown stream type 0x%x\n", v10->StreamType);
        }
        else
        {
          if ( v10->StreamType == 28672 )
            goto LABEL_143;
          if ( v10->StreamType > 0x14 )
          {
            if ( v10->StreamType == 21 || v10->StreamType == 22 || v10->StreamType == 23 )
              goto LABEL_143;
            if ( v10->StreamType == 24 )
            {
              v14 = (void **)((char *)this + 6072);
              goto LABEL_63;
            }
            if ( v10->StreamType != 25 )
              goto LABEL_142;
          }
          else
          {
            if ( v10->StreamType != 20 )
            {
              switch ( v10->StreamType )
              {
                case 0xFu:
                  if ( DumpTargetInfo::IndexDirectory(this, i, v10, &Src) )
                  {
                    DataSize = 1364;
                    if ( v10->Location.DataSize < 0x554 )
                      DataSize = v10->Location.DataSize;
                    memmove((char *)this + 4488, Src, DataSize);
                  }
                  goto LABEL_143;
                case 0x10u:
                  v26 = (char *)this + 6048;
                  if ( DumpTargetInfo::IndexDirectory(this, i, v10, (void **)this + 756) )
                  {
                    v28 = *(_QWORD *)(*(_QWORD *)v26 + 8LL);
                    if ( v28 <= 1 )
                    {
LABEL_116:
                      v30 = 1;
                    }
                    else
                    {
                      v29 = 1;
                      while ( 1 )
                      {
                        v27 = *(unsigned int **)v26;
                        if ( *(_QWORD *)((char *)v27 + *v27 + v27[1] * (v29 - 1)) > *(_QWORD *)((char *)v27
                                                                                              + *v27
                                                                                              + v29 * v27[1]) )
                          break;
                        if ( ++v29 >= v28 )
                          goto LABEL_116;
                      }
                      v30 = 0;
                    }
                    *((_BYTE *)this + 6056) = v30;
                  }
                  goto LABEL_143;
                case 0x11u:
                  v14 = (void **)((char *)this + 6064);
                  break;
                case 0x12u:
                  v14 = (void **)((char *)this + 6080);
                  break;
                case 0x13u:
                  v14 = (void **)((char *)this + 6088);
                  break;
                default:
                  goto LABEL_142;
              }
              goto LABEL_63;
            }
            if ( DumpTargetInfo::IndexDirectory(this, i, v10, &v65) )
            {
              if ( *((_QWORD *)this + 1084) )
              {
                ErrOut(L"Stack provider was already loaded. Skipping new load.\n");
              }
              else
              {
                v32 = (StackProvider *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
                v66 = v32;
                if ( v32 )
                  v35 = StackProvider::StackProvider(v32, v33, v34);
                else
                  v35 = 0;
                *((_QWORD *)this + 1084) = v35;
                if ( !v35 )
                {
                  ErrOut(L"Failed to allocate enough memory for the JavaScript stack provider.\n");
                  return 2147942414LL;
                }
                if ( (int)StackProvider::Load(v35, (struct TargetInfo *)v33) < 0 )
                {
                  ErrOut(
                    L"The stack provider .dll could not be loaded. The corresponding stack metadata will not be decoded. \n");
                }
                else
                {
                  v37 = StackProvider::BeginThreadStackReconstruction(
                          *((StackProvider **)this + 1084),
                          v36,
                          v65,
                          v10->Location.DataSize);
                  if ( v37 < 0 )
                    ErrOut(L"Stack provider threw error parsing JavaScript dmp stream: 0x%x\n", (unsigned int)v37);
                }
              }
            }
          }
        }
      }
      else
      {
        if ( v10->StreamType == 14 )
        {
          v14 = (void **)((char *)this + 5952);
          goto LABEL_63;
        }
        if ( v10->StreamType > 8 )
        {
          if ( v10->StreamType != 9 )
          {
            switch ( v10->StreamType )
            {
              case 0xAu:
                v63 = 0;
                if ( DumpTargetInfo::IndexDirectory(this, i, v10, &v63) )
                  dprintf(L"Comment: '%hs'\n", v63);
                goto LABEL_143;
              case 0xBu:
                v63 = 0;
                if ( DumpTargetInfo::IndexDirectory(this, i, v10, &v63) )
                  dprintf(L"Comment: '%ls'\n", v63);
                goto LABEL_143;
              case 0xCu:
                v14 = (void **)((char *)this + 5968);
                break;
              case 0xDu:
                v14 = (void **)((char *)this + 6040);
                break;
              default:
                goto LABEL_142;
            }
            goto LABEL_63;
          }
          if ( (*(_BYTE *)(v12 + 24) & 2) == 0 )
          {
            ErrOut(L"Partial memory minidumps can't have Memory64ListStreams\n");
            return 2147943792LL;
          }
          v22 = (_QWORD **)((char *)this + 5888);
          if ( DumpTargetInfo::IndexDirectory(this, i, v10, (void **)this + 736) )
          {
            v23 = *v22;
            v24 = 1;
            if ( **v22 <= 1u )
            {
LABEL_95:
              v25 = 1;
            }
            else
            {
              while ( v23[2 * v24] <= v23[2 * v24 + 2] )
              {
                if ( (unsigned __int64)++v24 >= *v23 )
                  goto LABEL_95;
              }
              v25 = 0;
            }
            *((_BYTE *)this + 5896) = v25;
          }
        }
        else
        {
          if ( v10->StreamType == 8 )
          {
            v19 = (int **)((char *)this + 5864);
            if ( !DumpTargetInfo::IndexDirectory(this, i, v10, (void **)this + 733) )
              goto LABEL_143;
            v20 = *v19;
            v21 = **v19;
            *((_DWORD *)this + 1464) = 64;
            goto LABEL_76;
          }
          if ( v10->StreamType )
          {
            if ( v10->StreamType == 3 )
            {
              v19 = (int **)((char *)this + 5864);
              if ( DumpTargetInfo::IndexDirectory(this, i, v10, (void **)this + 733) )
              {
                v20 = *v19;
                v21 = **v19;
                *((_DWORD *)this + 1464) = 48;
LABEL_76:
                *((_DWORD *)this + 1463) = v21;
                *v19 = v20 + 1;
              }
            }
            else
            {
              if ( v10->StreamType == 4 )
              {
                v14 = (void **)((char *)this + 5944);
LABEL_63:
                DumpTargetInfo::IndexDirectory(this, i, v10, v14);
                goto LABEL_143;
              }
              if ( v10->StreamType != 5 )
              {
                if ( v10->StreamType == 6 )
                {
                  v14 = (void **)((char *)this + 5960);
                }
                else
                {
                  if ( v10->StreamType != 7 )
                    goto LABEL_142;
                  v14 = (void **)((char *)this + 4480);
                }
                goto LABEL_63;
              }
              if ( (*(_BYTE *)(v12 + 24) & 2) != 0 )
              {
                ErrOut(L"Full memory minidumps can't have MemoryListStreams\n");
                return 2147943792LL;
              }
              v15 = (unsigned int **)((char *)this + 5872);
              if ( DumpTargetInfo::IndexDirectory(this, i, v10, (void **)this + 734) )
              {
                v16 = *v15;
                v17 = 1;
                if ( **v15 <= 1 )
                {
LABEL_70:
                  v18 = 1;
                }
                else
                {
                  while ( *(_QWORD *)&v16[4 * v17 - 3] <= *(_QWORD *)&v16[4 * v17 + 1] )
                  {
                    if ( ++v17 >= (unsigned __int64)*v16 )
                      goto LABEL_70;
                  }
                  v18 = 0;
                }
                *((_BYTE *)this + 5880) = v18;
              }
            }
          }
        }
      }
LABEL_143:
      ++v10;
      v12 = *((_QWORD *)this + 559);
    }
  }
  v38 = *((_QWORD *)this + 560);
  if ( !v38 )
  {
    ErrOut(L"Unable to locate system info\n");
    return 2147943792LL;
  }
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  LODWORD(v59) = *(_DWORD *)(v38 + 16);
  HIDWORD(v59) = *((_DWORD *)this + 1524);
  LODWORD(v60) = *(_DWORD *)(v38 + 20);
  *(_QWORD *)((char *)&v60 + 4) = *(_QWORD *)(v38 + 8);
  v39 = 0;
  if ( *(_WORD *)(v38 + 30) == 12 )
    v39 = 12;
  DWORD2(v59) = v39;
  v40 = *(_DWORD *)(v38 + 24);
  if ( v40 )
    UserMiniDumpTargetInfo::GetStringAtRva((_DWORD)this, v40, (_DWORD)this + 6104, (unsigned int)&v61 + 8, 0);
  result = TargetInfo::InitFixedVersionInfo(this, (struct TARGET_VERSION_INFO *)&v59);
  if ( !(_DWORD)result )
  {
    v41 = *((_QWORD *)this + 560);
    v42 = *(unsigned __int8 *)(v41 + 6);
    if ( !*(_BYTE *)(v41 + 6) )
      v42 = 1;
    *((_DWORD *)this + 132) = v42;
    if ( *(_DWORD *)(v41 + 24) )
    {
      v43 = (wint_t *)*((_QWORD *)&v61 + 1);
      v44 = -1;
      do
        ++v44;
      while ( *(_WORD *)(*((_QWORD *)&v61 + 1) + 2 * v44) );
      if ( (unsigned int)(*((_DWORD *)this + 51) - 8193) <= 3 )
      {
        while ( iswspace(*v43) )
          ++v43;
        v45 = v43;
        v46 = 0;
        for ( j = *v43; j && !iswspace(j); j = *v45 )
        {
          ++v46;
          ++v45;
        }
      }
      CopyNStringW((char *)this + 2776);
    }
    if ( (*((_BYTE *)this + 4492) & 1) != 0 )
    {
      v48 = *((_DWORD *)this + 1124);
      *((_DWORD *)this + 1115) = v48;
      if ( !v48 )
      {
        WarnOut(L"WARNING: Ignoring invalid event process ID %d\n", 0);
        *((_DWORD *)this + 1115) = -252645136;
      }
    }
    else
    {
      *((_DWORD *)this + 1115) = *((_DWORD *)this + 48) - 252645136;
    }
    v49 = (int *)*((_QWORD *)this + 745);
    if ( v49 )
    {
      v50 = *v49;
      *((_DWORD *)this + 1116) = v50;
      if ( !v50 )
      {
        WarnOut(L"WARNING: Ignoring invalid thread ID %d\n", 0);
        *((_DWORD *)this + 1116) = -1;
      }
      v51 = *((_QWORD *)this + 745);
      *((_OWORD *)this + 266) = *(_OWORD *)(v51 + 8);
      *((_OWORD *)this + 267) = *(_OWORD *)(v51 + 24);
      *((_OWORD *)this + 268) = *(_OWORD *)(v51 + 40);
      *((_OWORD *)this + 269) = *(_OWORD *)(v51 + 56);
      *((_OWORD *)this + 270) = *(_OWORD *)(v51 + 72);
      *((_OWORD *)this + 271) = *(_OWORD *)(v51 + 88);
      *((_OWORD *)this + 272) = *(_OWORD *)(v51 + 104);
      *((_OWORD *)this + 273) = *(_OWORD *)(v51 + 120);
      *((_OWORD *)this + 274) = *(_OWORD *)(v51 + 136);
      *((_QWORD *)this + 550) = *(_QWORD *)(v51 + 152);
      *((_BYTE *)this + 4413) = *(_DWORD *)(v51 + 164) != 0;
      *((_DWORD *)this + 1104) = *((_DWORD *)this + 1064);
    }
    else
    {
      *((_DWORD *)this + 1116) = 1;
      memset((char *)this + 4260, 0, 0x94u);
      *((_DWORD *)this + 1064) = -2147483645;
    }
    *((_DWORD *)this + 1102) = 0;
    *((_BYTE *)this + 4412) = 0;
    v52 = (_DWORD *)*((_QWORD *)this + 733);
    if ( v52 )
    {
      *((_DWORD *)this + 1117) = *((_DWORD *)this + 1463);
      if ( !*((_QWORD *)this + 745) )
        *((_DWORD *)this + 1116) = *v52;
    }
    else
    {
      *((_DWORD *)this + 1117) = 1;
    }
    v53 = (size_t *)*((_QWORD *)this + 736);
    if ( !v53 )
      return TargetInfo::Initialize(this);
    v54 = *v53;
    if ( !*((_BYTE *)this + 5896) )
    {
      v55 = calloc(v54, 8u);
      *((_QWORD *)this + 739) = v55;
      if ( !v55 )
        return 2147942414LL;
      UserMiniDumpTargetInfo::MemoryInfoHelper::SortMemRangeIndex<_MINIDUMP_MEMORY_DESCRIPTOR64>(
        *((_QWORD *)this + 736) + 16LL,
        v55,
        v54);
    }
    v56 = calloc(v54, 8u);
    *((_QWORD *)this + 738) = v56;
    if ( v56 )
    {
      v57 = 0;
      for ( k = 0; k < v54; ++k )
      {
        *(_QWORD *)(*((_QWORD *)this + 738) + 8LL * k) = v57;
        v57 += *(_QWORD *)(16LL * k + *((_QWORD *)this + 736) + 24);
      }
      return TargetInfo::Initialize(this);
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800a1590  push    rbp
0x1800a1592  push    rbx
0x1800a1593  push    rsi
0x1800a1594  push    rdi
0x1800a1595  push    r12
0x1800a1597  push    r13
0x1800a1599  push    r14
0x1800a159b  push    r15
0x1800a159d  lea     rbp, [rsp-1Fh]
0x1800a15a2  sub     rsp, 88h
0x1800a15a9  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x1800a15b1  mov     rbx, rcx
0x1800a15b4  mov     rdx, [rcx+880h]
0x1800a15bb  mov     [rcx+1178h], rdx
0x1800a15c2  xor     r15d, r15d
0x1800a15c5  mov     [rcx+1180h], r15
0x1800a15cc  movzx   eax, word ptr [rdx+4]
0x1800a15d0  mov     [rcx+1148h], eax
0x1800a15d6  movzx   eax, word ptr [rdx+6]
0x1800a15da  mov     [rcx+114Ch], eax
0x1800a15e0  add     rcx, 1078h
0x1800a15e7  lea     r13d, [r15+1]
0x1800a15eb  test    byte ptr [rdx+18h], 2
0x1800a15ef  jz      short loc_1800A15F4
0x1800a15f1  or      [rcx], r13d
0x1800a15f4  mov     eax, [rdx+18h]
0x1800a15f7  mov     r12d, 20000h
0x1800a15fd  test    r12, rax
0x1800a1600  jz      short loc_1800A1606
0x1800a1602  bts     dword ptr [rcx], 1Bh
0x1800a1606  test    byte ptr [rdx+18h], 4
0x1800a160a  jz      short loc_1800A160F
0x1800a160c  or      dword ptr [rcx], 2
0x1800a160f  test    byte ptr [rdx+18h], 20h
0x1800a1613  jz      short loc_1800A1618
0x1800a1615  or      dword ptr [rcx], 4
0x1800a1618  test    byte ptr [rdx+18h], 40h
0x1800a161c  jz      short loc_1800A1621
0x1800a161e  or      dword ptr [rcx], 8
0x1800a1621  mov     eax, [rdx+18h]
0x1800a1624  mov     esi, 1000h
0x1800a1629  mov     r14d, 2000h
0x1800a162f  test    r14, rax
0x1800a1632  jz      short loc_1800A1636
0x1800a1634  or      [rcx], esi
0x1800a1636  test    [rdx+18h], r13b
0x1800a163a  jz      short loc_1800A1647
0x1800a163c  mov     eax, [rcx]
0x1800a163e  or      eax, 10h
0x1800a1641  mov     [rbx+1078h], eax
0x1800a1647  lea     rcx, [rbx+1078h]
0x1800a164e  test    byte ptr [rdx+18h], 8
0x1800a1652  jz      short loc_1800A1657
0x1800a1654  or      dword ptr [rcx], 20h
0x1800a1657  test    byte ptr [rdx+18h], 80h
0x1800a165b  jz      short loc_1800A1669
0x1800a165d  or      dword ptr [rcx], 40h
0x1800a1660  lea     r8, [rbx+1078h]
0x1800a1667  jmp     short loc_1800A166C
0x1800a1669  mov     r8, rcx
0x1800a166c  mov     eax, [rdx+18h]
0x1800a166f  mov     r9d, 100h
0x1800a1675  test    r9, rax
0x1800a1678  jz      short loc_1800A1680
0x1800a167a  bts     dword ptr [rcx], 7
0x1800a167e  jmp     short loc_1800A1683
0x1800a1680  mov     r8, rcx
0x1800a1683  mov     eax, [rdx+18h]
0x1800a1686  mov     r11d, 200h
0x1800a168c  test    r11, rax
0x1800a168f  jz      short loc_1800A16A2
0x1800a1691  mov     eax, [rcx]
0x1800a1693  or      eax, r9d
0x1800a1696  mov     [r8], eax
0x1800a1699  lea     rcx, [rbx+1078h]
0x1800a16a0  jmp     short loc_1800A16A5
0x1800a16a2  mov     rcx, r8
0x1800a16a5  mov     eax, [rdx+18h]
0x1800a16a8  mov     edi, 8000h
0x1800a16ad  bt      rax, 13h
0x1800a16b2  jnb     short loc_1800A16B9
0x1800a16b4  or      [r8], edi
0x1800a16b7  jmp     short loc_1800A16BC
0x1800a16b9  mov     rcx, r8
0x1800a16bc  mov     eax, [rdx+18h]
0x1800a16bf  bt      rax, 14h
0x1800a16c4  jnb     short loc_1800A16D8
0x1800a16c6  mov     eax, [r8]
0x1800a16c9  bts     eax, 10h
0x1800a16cd  mov     [rcx], eax
0x1800a16cf  lea     r8, [rbx+1078h]
0x1800a16d6  jmp     short loc_1800A16DB
0x1800a16d8  mov     r8, rcx
0x1800a16db  mov     eax, [rdx+18h]
0x1800a16de  mov     r10d, 400h
0x1800a16e4  test    r10, rax
0x1800a16e7  jz      short loc_1800A16EE
0x1800a16e9  or      [rcx], r11d
0x1800a16ec  jmp     short loc_1800A16F1
0x1800a16ee  mov     r8, rcx
0x1800a16f1  mov     eax, [rdx+18h]
0x1800a16f4  mov     r9d, 800h
0x1800a16fa  test    r9, rax
0x1800a16fd  jz      short loc_1800A1710
0x1800a16ff  mov     eax, [rcx]
0x1800a1701  or      eax, r10d
0x1800a1704  mov     [r8], eax
0x1800a1707  lea     rcx, [rbx+1078h]
0x1800a170e  jmp     short loc_1800A1713
0x1800a1710  mov     rcx, r8
0x1800a1713  mov     eax, [rdx+18h]
0x1800a1716  test    rsi, rax
0x1800a1719  jz      short loc_1800A1720
0x1800a171b  or      [r8], r9d
0x1800a171e  jmp     short loc_1800A1723
0x1800a1720  mov     rcx, r8
0x1800a1723  mov     eax, [rdx+18h]
0x1800a1726  mov     r9d, 4000h
0x1800a172c  test    r9, rax
0x1800a172f  jz      short loc_1800A1742
0x1800a1731  mov     eax, [r8]
0x1800a1734  or      eax, r14d
0x1800a1737  mov     [rcx], eax
0x1800a1739  lea     r8, [rbx+1078h]
0x1800a1740  jmp     short loc_1800A1745
0x1800a1742  mov     r8, rcx
0x1800a1745  mov     eax, [rdx+18h]
0x1800a1748  test    rdi, rax
0x1800a174b  jz      short loc_1800A1752
0x1800a174d  or      [rcx], r9d
0x1800a1750  jmp     short loc_1800A1755
0x1800a1752  mov     r8, rcx
0x1800a1755  mov     eax, [rdx+18h]
0x1800a1758  bt      rax, 15h
0x1800a175d  jnb     short loc_1800A1767
0x1800a175f  mov     eax, [rcx]
0x1800a1761  or      eax, r12d
0x1800a1764  mov     [r8], eax
0x1800a1767  mov     [rbp+57h+Src], r15
0x1800a176b  mov     [rbp+57h+arg_10], r15
0x1800a176f  mov     rcx, [rbx]
0x1800a1772  mov     eax, [rdx+8]
0x1800a1775  lea     r9d, [rax+rax*2]
0x1800a1779  shl     r9d, 2
0x1800a177d  mov     rax, [rcx+628h]
0x1800a1784  lea     rcx, String2; "Directory"
0x1800a178b  mov     [rsp+0C0h+var_98], rcx
0x1800a1790  mov     dword ptr [rsp+0C0h+var_A0], r15d
0x1800a1795  mov     r8d, [rdx+0Ch]
0x1800a1799  mov     rcx, rbx
0x1800a179c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a17a1  mov     rsi, rax
0x1800a17a4  test    rax, rax
0x1800a17a7  jnz     short loc_1800A17B3
0x1800a17a9  mov     eax, 80070570h
0x1800a17ae  jmp     loc_1800A1FC5
0x1800a17b3  mov     rcx, [rbx+1178h]
0x1800a17ba  mov     r12d, 0Ch
0x1800a17c0  cmp     [rcx+8], r15d
0x1800a17c4  jbe     loc_1800A1C39
0x1800a17ca  mov     r14d, r15d
0x1800a17cd  cmp     dword ptr [rsi], 0Eh
0x1800a17d0  ja      loc_1800A1A28
0x1800a17d6  jz      loc_1800A1A1C
0x1800a17dc  cmp     dword ptr [rsi], 8
0x1800a17df  ja      loc_1800A1923
0x1800a17e5  jz      loc_1800A18F1
0x1800a17eb  mov     eax, [rsi]
0x1800a17ed  test    eax, eax
0x1800a17ef  jz      loc_1800A1C22
0x1800a17f5  sub     eax, 3
0x1800a17f8  jz      loc_1800A18AF
0x1800a17fe  sub     eax, 1
0x1800a1801  jz      loc_1800A18A3
0x1800a1807  sub     eax, 1
0x1800a180a  jz      short loc_1800A183D
0x1800a180c  sub     eax, 1
0x1800a180f  jz      short loc_1800A1834
0x1800a1811  cmp     eax, 1
0x1800a1814  jnz     loc_1800A1C14
0x1800a181a  lea     r9, [rbx+1180h]; void **
0x1800a1821  mov     r8, rsi; struct _MINIDUMP_DIRECTORY *
0x1800a1824  mov     edx, r14d; unsigned int
0x1800a1827  mov     rcx, rbx; this
0x1800a182a  call    ?IndexDirectory@DumpTargetInfo@@QEAAPEAXKPEFAU_MINIDUMP_DIRECTORY@@PEAPEAX@Z; DumpTargetInfo::IndexDirectory(ulong,_MINIDUMP_DIRECTORY *,void * *)
0x1800a182f  jmp     loc_1800A1C22
0x1800a1834  lea     r9, [rbx+1748h]
0x1800a183b  jmp     short loc_1800A1821
0x1800a183d  test    byte ptr [rcx+18h], 2
0x1800a1841  jnz     loc_1800A1C4E
0x1800a1847  lea     rdi, [rbx+16F0h]
0x1800a184e  mov     r9, rdi; void **
0x1800a1851  mov     r8, rsi; struct _MINIDUMP_DIRECTORY *
0x1800a1854  mov     edx, r14d; unsigned int
0x1800a1857  mov     rcx, rbx; this
0x1800a185a  call    ?IndexDirectory@DumpTargetInfo@@QEAAPEAXKPEFAU_MINIDUMP_DIRECTORY@@PEAPEAX@Z; DumpTargetInfo::IndexDirectory(ulong,_MINIDUMP_DIRECTORY *,void * *)
0x1800a185f  test    rax, rax
0x1800a1862  jz      loc_1800A1C22
0x1800a1868  mov     r8, [rdi]
0x1800a186b  mov     rdx, r13
0x1800a186e  cmp     [r8], r13d
0x1800a1871  jbe     short loc_1800A1890
0x1800a1873  mov     rcx, rdx
0x1800a1876  add     rcx, rcx
0x1800a1879  mov     rax, [r8+rcx*8+4]
0x1800a187e  cmp     [r8+rcx*8-0Ch], rax
0x1800a1883  ja      short loc_1800A189E
0x1800a1885  add     rdx, r13
0x1800a1888  mov     eax, [r8]
0x1800a188b  cmp     rdx, rax
0x1800a188e  jb      short loc_1800A1873
0x1800a1890  mov     al, r13b
0x1800a1893  mov     [rbx+16F8h], al
0x1800a1899  jmp     loc_1800A1C22
0x1800a189e  mov     al, r15b
0x1800a18a1  jmp     short loc_1800A1893
0x1800a18a3  lea     r9, [rbx+1738h]
0x1800a18aa  jmp     loc_1800A1821
0x1800a18af  lea     rdi, [rbx+16E8h]
0x1800a18b6  mov     r9, rdi; void **
0x1800a18b9  mov     r8, rsi; struct _MINIDUMP_DIRECTORY *
0x1800a18bc  mov     edx, r14d; unsigned int
0x1800a18bf  mov     rcx, rbx; this
0x1800a18c2  call    ?IndexDirectory@DumpTargetInfo@@QEAAPEAXKPEFAU_MINIDUMP_DIRECTORY@@PEAPEAX@Z; DumpTargetInfo::IndexDirectory(ulong,_MINIDUMP_DIRECTORY *,void * *)
0x1800a18c7  test    rax, rax
0x1800a18ca  jz      loc_1800A1C22
0x1800a18d0  mov     rcx, [rdi]
0x1800a18d3  mov     eax, [rcx]
0x1800a18d5  mov     dword ptr [rbx+16E0h], 30h ; '0'
0x1800a18df  mov     [rbx+16DCh], eax
0x1800a18e5  lea     rax, [rcx+4]
0x1800a18e9  mov     [rdi], rax
0x1800a18ec  jmp     loc_1800A1C22
0x1800a18f1  lea     rdi, [rbx+16E8h]
0x1800a18f8  mov     r9, rdi; void **
0x1800a18fb  mov     r8, rsi; struct _MINIDUMP_DIRECTORY *
0x1800a18fe  mov     edx, r14d; unsigned int
0x1800a1901  mov     rcx, rbx; this
0x1800a1904  call    ?IndexDirectory@DumpTargetInfo@@QEAAPEAXKPEFAU_MINIDUMP_DIRECTORY@@PEAPEAX@Z; DumpTargetInfo::IndexDirectory(ulong,_MINIDUMP_DIRECTORY *,void * *)
0x1800a1909  test    rax, rax
0x1800a190c  jz      loc_1800A1C22
0x1800a1912  mov     rcx, [rdi]
0x1800a1915  mov     eax, [rcx]
0x1800a1917  mov     dword ptr [rbx+16E0h], 40h ; '@'
0x1800a1921  jmp     short loc_1800A18DF
0x1800a1923  mov     eax, [rsi]
0x1800a1925  sub     eax, 9
0x1800a1928  jz      loc_1800A19BA
0x1800a192e  sub     eax, 1
0x1800a1931  jz      short loc_1800A1986
0x1800a1933  sub     eax, 1
0x1800a1936  jz      short loc_1800A195E
0x1800a1938  sub     eax, 1
0x1800a193b  jz      short loc_1800A1952
0x1800a193d  cmp     eax, 1
0x1800a1940  jnz     loc_1800A1C14
0x1800a1946  lea     r9, [rbx+1798h]
0x1800a194d  jmp     loc_1800A1821
0x1800a1952  lea     r9, [rbx+1750h]
0x1800a1959  jmp     loc_1800A1821
0x1800a195e  mov     [rbp+57h+arg_0], r15
0x1800a1962  lea     r9, [rbp+57h+arg_0]; void **
0x1800a1966  mov     r8, rsi; struct _MINIDUMP_DIRECTORY *
0x1800a1969  mov     edx, r14d; unsigned int
0x1800a196c  mov     rcx, rbx; this
0x1800a196f  call    ?IndexDirectory@DumpTargetInfo@@QEAAPEAXKPEFAU_MINIDUMP_DIRECTORY@@PEAPEAX@Z; DumpTargetInfo::IndexDirectory(ulong,_MINIDUMP_DIRECTORY *,void * *)
0x1800a1974  test    rax, rax
0x1800a1977  jz      loc_1800A1C22
0x1800a197d  lea     rcx, aCommentLs; "Comment: '%ls'\n"
0x1800a1984  jmp     short loc_1800A19AC
0x1800a1986  mov     [rbp+57h+arg_0], r15
0x1800a198a  lea     r9, [rbp+57h+arg_0]; void **
0x1800a198e  mov     r8, rsi; struct _MINIDUMP_DIRECTORY *
0x1800a1991  mov     edx, r14d; unsigned int
0x1800a1994  mov     rcx, rbx; this
0x1800a1997  call    ?IndexDirectory@DumpTargetInfo@@QEAAPEAXKPEFAU_MINIDUMP_DIRECTORY@@PEAPEAX@Z; DumpTargetInfo::IndexDirectory(ulong,_MINIDUMP_DIRECTORY *,void * *)
0x1800a199c  test    rax, rax
0x1800a199f  jz      loc_1800A1C22
0x1800a19a5  lea     rcx, aCommentHs_0; "Comment: '%hs'\n"
0x1800a19ac  mov     rdx, [rbp+57h+arg_0]
0x1800a19b0  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800a19b5  jmp     loc_1800A1C22
0x1800a19ba  test    byte ptr [rcx+18h], 2
0x1800a19be  jz      loc_1800A1C5F
0x1800a19c4  lea     rdi, [rbx+1700h]
0x1800a19cb  mov     r9, rdi; void **
0x1800a19ce  mov     r8, rsi; struct _MINIDUMP_DIRECTORY *
0x1800a19d1  mov     edx, r14d; unsigned int
0x1800a19d4  mov     rcx, rbx; this
0x1800a19d7  call    ?IndexDirectory@DumpTargetInfo@@QEAAPEAXKPEFAU_MINIDUMP_DIRECTORY@@PEAPEAX@Z; DumpTargetInfo::IndexDirectory(ulong,_MINIDUMP_DIRECTORY *,void * *)
0x1800a19dc  test    rax, rax
0x1800a19df  jz      loc_1800A1C22
0x1800a19e5  mov     r8, [rdi]
0x1800a19e8  mov     rdx, r13
0x1800a19eb  cmp     [r8], r13
0x1800a19ee  jbe     short loc_1800A1A09
0x1800a19f0  mov     rcx, rdx
0x1800a19f3  add     rcx, rcx
0x1800a19f6  mov     rax, [r8+rcx*8+10h]
0x1800a19fb  cmp     [r8+rcx*8], rax
  ... truncated ...
```
