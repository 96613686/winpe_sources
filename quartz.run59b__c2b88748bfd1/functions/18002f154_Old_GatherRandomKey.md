# Old_GatherRandomKey

- ea: `0x18002f154`
- end: `0x18002fad6`
- name: `Old_GatherRandomKey`
- size: `2434`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180021928`
- `0x18013b98c`

## callees

- `0x180020158`
- `0x18002c750`
- `0x18002e9c4`
- `0x18002f154`
- `0x1800388a0`
- `0x180039250`
- `0x18013bc78`
- `0x18013bd64`
- `0x18013dd80`
- `0x18013e470`
- `0x18013e490`
- `0x18013e530`
- `0x18013f790`
- `0x18013f7c0`
- `0x18013f928`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18002f3b3`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18002f3b3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002f39a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002f39a`
- `KERNEL32!GetProcessHeap` at `0x18002f1a6`
- `KERNEL32!GetProcessHeap` at `0x18002fa90`
- `KERNEL32!GetProcessHeap` at `0x18002f1a6`
- `KERNEL32!GetProcessHeap` at `0x18002fa90`
- `KERNEL32!HeapAlloc` at `0x18002f1c0`
- `KERNEL32!HeapAlloc` at `0x18002f1c0`
- `KERNEL32!HeapFree` at `0x18002faa4`
- `KERNEL32!HeapFree` at `0x18002faa4`
- `KERNEL32!GetTickCount` at `0x18002f23f`
- `KERNEL32!GetTickCount` at `0x18002f23f`
- `KERNEL32!GetDiskFreeSpaceW` at `0x18002f301`
- `KERNEL32!GetDiskFreeSpaceW` at `0x18002f301`
- `KERNEL32!GetCurrentThreadId` at `0x18002f226`
- `KERNEL32!GetCurrentThreadId` at `0x18002f226`
- `KERNEL32!GetCurrentProcessId` at `0x18002f20e`
- `KERNEL32!GetCurrentProcessId` at `0x18002f20e`
- `KERNEL32!QueryPerformanceCounter` at `0x18002f291`
- `KERNEL32!QueryPerformanceCounter` at `0x18002f291`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsA` at `0x18002f400`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsA` at `0x18002f400`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x18002f329`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x18002f33d`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x18002f329`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x18002f33d`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x18002f3f2`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x18002f3f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002f268`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002f268`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18002f2c1`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18002f2c1`

## pseudocode

```c
__int64 __fastcall Old_GatherRandomKey(void *Src, size_t Size, void *a3, DWORD *a4)
{
  void *v4; // r15
  size_t v6; // rdi
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  __int64 v9; // r13
  _BYTE *v10; // r12
  unsigned int v11; // ebx
  __int64 v12; // r14
  unsigned int v13; // eax
  __int64 v14; // rdi
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  char *v18; // r15
  CHAR *EnvironmentStringsW; // rsi
  unsigned int v20; // edi
  const char *v21; // r14
  const char *v22; // r14
  unsigned int v23; // eax
  __int64 v24; // rdi
  unsigned int v25; // ecx
  __int64 v26; // rax
  unsigned int v27; // ecx
  __int64 v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  __int64 v31; // rdi
  __int64 v32; // rdx
  unsigned int v33; // ebx
  __int64 v34; // rcx
  BYTE *v35; // rax
  __int128 *v36; // rax
  _BYTE *v37; // rax
  _BYTE *v38; // rax
  HANDLE v39; // rax
  unsigned int v40; // [rsp+30h] [rbp-D0h] BYREF
  void *v41; // [rsp+38h] [rbp-C8h]
  DWORD *v42; // [rsp+40h] [rbp-C0h]
  __int128 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v44; // [rsp+60h] [rbp-A0h]
  __int128 v45; // [rsp+70h] [rbp-90h]
  __int128 v46; // [rsp+80h] [rbp-80h]
  __int128 v47; // [rsp+90h] [rbp-70h]
  BYTE Data[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+E0h] [rbp-20h]
  __int128 v50; // [rsp+F0h] [rbp-10h]
  __int128 v51; // [rsp+100h] [rbp+0h]
  __int128 v52; // [rsp+110h] [rbp+10h]
  _BYTE v53[4]; // [rsp+150h] [rbp+50h] BYREF
  int v54; // [rsp+154h] [rbp+54h]
  _BYTE v55[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v56; // [rsp+1D4h] [rbp+D4h]
  _BYTE v57[4]; // [rsp+250h] [rbp+150h] BYREF
  int v58; // [rsp+254h] [rbp+154h]
  _BYTE v59[4]; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v60; // [rsp+2D4h] [rbp+1D4h]
  _BYTE v61[272]; // [rsp+350h] [rbp+250h] BYREF

  v42 = a4;
  v4 = a3;
  v41 = a3;
  v6 = (unsigned int)Size;
  if ( (unsigned int)Old_GatherRandomKeyFastUserMode(Src, Size, a3, a4) )
    return 1;
  ProcessHeap = GetProcessHeap();
  v9 = 3584;
  result = (__int64)HeapAlloc(ProcessHeap, 0, 0xE00u);
  v10 = (_BYTE *)result;
  if ( result )
  {
    v11 = 3584;
    v12 = 80;
    if ( (unsigned int)v6 <= 0xE00 )
    {
      memcpy_0((void *)result, Src, v6);
      v13 = (v6 + 8) & 0xFFFFFFF8;
      if ( v13 > 0xE00 )
        goto LABEL_6;
      v14 = v13;
      v15 = 3584 - v13;
      *(_DWORD *)&v10[v13] = GetCurrentProcessId();
      if ( v15 < 8 )
        goto LABEL_6;
      v16 = v15 - 8;
      *(_DWORD *)&v10[v14 + 8] = GetCurrentThreadId();
      if ( v16 < 8 )
        goto LABEL_6;
      v17 = v16 - 8;
      *(_DWORD *)&v10[v14 + 16] = GetTickCount();
      if ( v17 < 8 )
        goto LABEL_6;
      v11 = v17 - 8;
      if ( v11 < 0x10 )
        goto LABEL_87;
      GetLocalTime((LPSYSTEMTIME)&v10[v14 + 24]);
      if ( v11 < 0x18 )
      {
LABEL_6:
        v11 = 0;
      }
      else
      {
        v11 -= 24;
        if ( v11 >= 8 )
        {
          v18 = &v10[v14];
          QueryPerformanceCounter((LARGE_INTEGER *)&v10[v14 + 48]);
          if ( v11 >= 0x10 )
          {
            v11 -= 16;
            if ( v11 < 0x40 )
              goto LABEL_86;
            *((_DWORD *)v18 + 16) = 64;
            GlobalMemoryStatusEx((LPMEMORYSTATUSEX)v18 + 1);
            if ( v11 >= 0x48 )
            {
              v11 -= 72;
              if ( v11 < 0x10 )
                goto LABEL_86;
              GetDiskFreeSpaceW(0, (LPDWORD)v18 + 34, (LPDWORD)v18 + 35, (LPDWORD)v18 + 36, (LPDWORD)v18 + 37);
              if ( v11 >= 0x18 )
              {
                v11 -= 24;
                if ( !dword_1801A1FE0 )
                {
                  v40 = 0;
                  EnvironmentStringsW = (CHAR *)GetEnvironmentStringsW();
                  if ( EnvironmentStringsW || (v40 = 1, (EnvironmentStringsW = (CHAR *)GetEnvironmentStringsW()) != 0) )
                  {
                    *(_DWORD *)&Data[4] = 0;
                    memset_0(Data, 0, 0x6Cu);
                    SymCryptMd4Init(Data);
                    v20 = 0;
                    v21 = EnvironmentStringsW;
                    do
                    {
                      v22 = &v21[v20];
                      if ( v40 )
                      {
                        v21 = v22 + 1;
                        v20 = strnlen(v21, 0x7FFFu);
                      }
                      else
                      {
                        v21 = v22 + 2;
                        v20 = 2 * wcsnlen((const wchar_t *)v21, 0x7FFFu);
                      }
                      SymCryptMd4Append(Data, v21, v20);
                    }
                    while ( v20 );
                    SymCryptMd4Result(Data, &xmmword_1801A2160);
                    v9 = 3584;
                    if ( v40 )
                      FreeEnvironmentStringsA(EnvironmentStringsW);
                    else
                      FreeEnvironmentStringsW((LPWCH)EnvironmentStringsW);
                    v12 = 80;
                  }
                  dword_1801A1FE0 = 1;
                }
                if ( v11 < 0x10 )
                  goto LABEL_86;
                *((_OWORD *)v18 + 10) = xmmword_1801A2160;
                if ( v11 >= 0x18 )
                {
                  v11 -= 24;
                  if ( !(unsigned int)Old_IsRNGWinNT() )
                    goto LABEL_86;
                  if ( v11 < 0x40 )
                    goto LABEL_86;
                  if ( !__NtQuerySystemInformationRNG )
                    goto LABEL_86;
                  v40 = v11;
                  __NtQuerySystemInformationRNG(5, v18 + 184, v11);
                  *(_DWORD *)&Data[4] = 0;
                  memset_0(Data, 0, 0x7Cu);
                  SymCryptSha1Init(Data);
                  SymCryptSha1Append(Data, v18 + 184, v11);
                  SymCryptSha1Result(Data, v18 + 184);
                  v11 -= 24;
                  if ( v11 < 0x30 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, char *, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              3,
                              v18 + 208,
                              48,
                              &v40) < 0 )
                  {
                    v24 = (__int64)(v18 + 208);
                  }
                  else
                  {
                    v23 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v23 > v11 )
                      goto LABEL_14;
                    v11 -= v23;
                    v24 = (__int64)&v18[v23 + 208];
                    if ( v11 < 0x18 )
                      goto LABEL_86;
                  }
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              7,
                              v24,
                              24,
                              &v40) >= 0 )
                  {
                    v25 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v25 > v11 )
                      goto LABEL_14;
                    v24 += v25;
                    v11 -= v25;
                  }
                  if ( v11 < 0xB0 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              80,
                              v24,
                              176,
                              &v40) >= 0 )
                  {
                    v26 = (v40 + 8) & 0xFFFFFFF8;
                    if ( (unsigned int)v26 > v11 )
                      goto LABEL_14;
                    v11 -= v26;
                    if ( v11 < 0x40 )
                      goto LABEL_86;
                    v24 += v26;
                  }
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              21,
                              v24,
                              64,
                              &v40) >= 0 )
                  {
                    v27 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v27 > v11 )
                      goto LABEL_14;
                    v24 += v27;
                    v11 -= v27;
                  }
                  if ( v11 < 0x178 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              2,
                              v24,
                              376,
                              &v40) >= 0 )
                  {
                    v28 = (v40 + 8) & 0xFFFFFFF8;
                    if ( (unsigned int)v28 > v11 )
                      goto LABEL_14;
                    v11 -= v28;
                    if ( v11 < 0x10 )
                      goto LABEL_86;
                    v24 += v28;
                  }
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              33,
                              v24,
                              16,
                              &v40) >= 0 )
                  {
                    v29 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v29 > v11 )
                      goto LABEL_14;
                    v24 += v29;
                    v11 -= v29;
                  }
                  if ( v11 < 0x20 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              45,
                              v24,
                              32,
                              &v40) >= 0 )
                  {
                    v30 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v30 > v11 )
                      goto LABEL_14;
                    v24 += v30;
                    v11 -= v30;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              8,
                              v24,
                              v11,
                              &v40) >= 0 )
                  {
                    DWORD1(v43) = 0;
                    memset_0(&v43, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    SymCryptSha1Init(&v43);
                    SymCryptSha1Append(&v43, v24, v40);
                    SymCryptSha1Result(&v43, v24);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v24 += 24;
                    v11 -= 24;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              61,
                              v24,
                              v11,
                              &v40) >= 0 )
                  {
                    v54 = 0;
                    memset_0(v53, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    SymCryptSha1Init(v53);
                    SymCryptSha1Append(v53, v24, v40);
                    SymCryptSha1Result(v53, v24);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v24 += 24;
                    v11 -= 24;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              18,
                              v24,
                              v11,
                              &v40) >= 0 )
                  {
                    v56 = 0;
                    memset_0(v55, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    SymCryptSha1Init(v55);
                    SymCryptSha1Append(v55, v24, v40);
                    SymCryptSha1Result(v55, v24);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v24 += 24;
                    v11 -= 24;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              23,
                              v24,
                              v11,
                              &v40) >= 0 )
                  {
                    v58 = 0;
                    memset_0(v57, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    SymCryptSha1Init(v57);
                    SymCryptSha1Append(v57, v24, v40);
                    SymCryptSha1Result(v57, v24);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v24 += 24;
                    v11 -= 24;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              42,
                              v24,
                              v11,
                              &v40) < 0 )
                    goto LABEL_86;
                  v60 = 0;
                  memset_0(v59, 0, 0x7Cu);
                  if ( v11 < 0x14 )
                    goto LABEL_86;
                  SymCryptSha1Init(v59);
                  SymCryptSha1Append(v59, v24, v40);
                  SymCryptSha1Result(v59, v24);
                  if ( v11 >= 0x18 )
                  {
                    v11 -= 24;
                    goto LABEL_86;
                  }
                }
              }
            }
          }
LABEL_14:
          v11 = 0;
LABEL_86:
          v4 = v41;
        }
      }
    }
LABEL_87:
    v31 = 272;
    memset_0(v61, 0, sizeof(v61));
    v43 = *(_OWORD *)&::Data;
    v45 = xmmword_1801A2010;
    v44 = xmmword_1801A2000;
    v47 = xmmword_1801A2030;
    v46 = xmmword_1801A2020;
    SymCryptRc4Init(v61, &v43, 80);
    v32 = 3584;
    if ( 3584 - v11 <= 0xE00 )
      v32 = 3584 - v11;
    v33 = VeryLargeHashUpdate(v10, v32, &v43);
    *(_OWORD *)Data = v43;
    v49 = v44;
    v50 = v45;
    v51 = v46;
    v52 = v47;
    *(_OWORD *)&::Data = v43;
    xmmword_1801A2000 = v44;
    xmmword_1801A2010 = v45;
    xmmword_1801A2020 = v46;
    xmmword_1801A2030 = v47;
    SymCryptRc4Crypt(v61, Data, Data, 80);
    WriteSeed(Data);
    v34 = 80;
    v35 = Data;
    do
    {
      *v35++ = 0;
      --v34;
    }
    while ( v34 );
    SymCryptRc4Init(v61, &v43, 80);
    v36 = &v43;
    do
    {
      *(_BYTE *)v36 = 0;
      v36 = (__int128 *)((char *)v36 + 1);
      --v12;
    }
    while ( v12 );
    SymCryptRc4Crypt(v61, v4, v4, *v42);
    v37 = v61;
    do
    {
      *v37++ = 0;
      --v31;
    }
    while ( v31 );
    v38 = v10;
    do
    {
      *v38++ = 0;
      --v9;
    }
    while ( v9 );
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v10);
    return v33;
  }
  return result;
}

```

## disassembly

```asm
0x18002f154  push    rbp
0x18002f156  push    rbx
0x18002f157  push    rsi
0x18002f158  push    rdi
0x18002f159  push    r12
0x18002f15b  push    r13
0x18002f15d  push    r14
0x18002f15f  push    r15
0x18002f161  lea     rbp, [rsp-378h]
0x18002f169  sub     rsp, 478h
0x18002f170  mov     rax, cs:__security_cookie
0x18002f177  xor     rax, rsp
0x18002f17a  mov     [rbp+3B0h+var_50], rax
0x18002f181  mov     [rsp+4B0h+var_470], r9
0x18002f186  mov     r15, r8
0x18002f189  mov     [rsp+4B0h+var_478], r8
0x18002f18e  mov     rsi, rcx
0x18002f191  mov     edi, edx
0x18002f193  call    Old_GatherRandomKeyFastUserMode
0x18002f198  test    eax, eax
0x18002f19a  jz      short loc_18002F1A6
0x18002f19c  mov     eax, 1
0x18002f1a1  jmp     loc_18002FAB2
0x18002f1a6  call    cs:__imp_GetProcessHeap
0x18002f1ad  nop     dword ptr [rax+rax+00h]
0x18002f1b2  mov     r13d, 0E00h
0x18002f1b8  xor     edx, edx; dwFlags
0x18002f1ba  mov     rcx, rax; hHeap
0x18002f1bd  mov     r8d, r13d; dwBytes
0x18002f1c0  call    cs:__imp_HeapAlloc
0x18002f1c7  nop     dword ptr [rax+rax+00h]
0x18002f1cc  mov     r12, rax
0x18002f1cf  test    rax, rax
0x18002f1d2  jz      loc_18002FAB2
0x18002f1d8  mov     ebx, r13d
0x18002f1db  mov     r14d, 50h ; 'P'
0x18002f1e1  cmp     edi, r13d
0x18002f1e4  ja      loc_18002F92D
0x18002f1ea  mov     r8, rdi; Size
0x18002f1ed  mov     rdx, rsi; Src
0x18002f1f0  mov     rcx, r12; void *
0x18002f1f3  call    memcpy_0
0x18002f1f8  lea     eax, [rdi+8]
0x18002f1fb  and     eax, 0FFFFFFF8h
0x18002f1fe  cmp     eax, r13d
0x18002f201  jbe     short loc_18002F20A
0x18002f203  xor     ebx, ebx
0x18002f205  jmp     loc_18002F92D
0x18002f20a  mov     edi, eax
0x18002f20c  sub     ebx, eax
0x18002f20e  call    cs:__imp_GetCurrentProcessId
0x18002f215  nop     dword ptr [rax+rax+00h]
0x18002f21a  mov     [rdi+r12], eax
0x18002f21e  cmp     ebx, 8
0x18002f221  jb      short loc_18002F203
0x18002f223  add     ebx, 0FFFFFFF8h
0x18002f226  call    cs:__imp_GetCurrentThreadId
0x18002f22d  nop     dword ptr [rax+rax+00h]
0x18002f232  mov     [rdi+r12+8], eax
0x18002f237  cmp     ebx, 8
0x18002f23a  jb      short loc_18002F203
0x18002f23c  add     ebx, 0FFFFFFF8h
0x18002f23f  call    cs:__imp_GetTickCount
0x18002f246  nop     dword ptr [rax+rax+00h]
0x18002f24b  mov     [rdi+r12+10h], eax
0x18002f250  cmp     ebx, 8
0x18002f253  jb      short loc_18002F203
0x18002f255  add     ebx, 0FFFFFFF8h
0x18002f258  cmp     ebx, 10h
0x18002f25b  jb      loc_18002F92D
0x18002f261  lea     rcx, [rdi+18h]
0x18002f265  add     rcx, r12; lpSystemTime
0x18002f268  call    cs:__imp_GetLocalTime
0x18002f26f  nop     dword ptr [rax+rax+00h]
0x18002f274  cmp     ebx, 18h
0x18002f277  jb      short loc_18002F203
0x18002f279  mov     esi, 0FFFFFFE8h
0x18002f27e  add     ebx, esi
0x18002f280  cmp     ebx, 8
0x18002f283  jb      loc_18002F92D
0x18002f289  lea     r15, [rdi+r12]
0x18002f28d  lea     rcx, [r15+30h]; lpPerformanceCount
0x18002f291  call    cs:__imp_QueryPerformanceCounter
0x18002f298  nop     dword ptr [rax+rax+00h]
0x18002f29d  cmp     ebx, 10h
0x18002f2a0  jnb     short loc_18002F2A9
0x18002f2a2  xor     ebx, ebx
0x18002f2a4  jmp     loc_18002F928
0x18002f2a9  add     ebx, 0FFFFFFF0h
0x18002f2ac  cmp     ebx, 40h ; '@'
0x18002f2af  jb      loc_18002F928
0x18002f2b5  lea     rcx, [r15+40h]; lpBuffer
0x18002f2b9  mov     dword ptr [r15+40h], 40h ; '@'
0x18002f2c1  call    cs:__imp_GlobalMemoryStatusEx
0x18002f2c8  nop     dword ptr [rax+rax+00h]
0x18002f2cd  cmp     ebx, 48h ; 'H'
0x18002f2d0  jb      short loc_18002F2A2
0x18002f2d2  add     ebx, 0FFFFFFB8h
0x18002f2d5  cmp     ebx, 10h
0x18002f2d8  jb      loc_18002F928
0x18002f2de  lea     rax, [r15+94h]
0x18002f2e5  xor     ecx, ecx; lpRootPathName
0x18002f2e7  lea     r9, [r15+90h]; lpNumberOfFreeClusters
0x18002f2ee  mov     [rsp+4B0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x18002f2f3  lea     r8, [r15+8Ch]; lpBytesPerSector
0x18002f2fa  lea     rdx, [r15+88h]; lpSectorsPerCluster
0x18002f301  call    cs:__imp_GetDiskFreeSpaceW
0x18002f308  nop     dword ptr [rax+rax+00h]
0x18002f30d  cmp     ebx, 18h
0x18002f310  jb      short loc_18002F2A2
0x18002f312  add     ebx, esi
0x18002f314  cmp     cs:dword_1801A1FE0, 0
0x18002f31b  jnz     loc_18002F421
0x18002f321  mov     [rsp+4B0h+var_480], 0
0x18002f329  call    cs:__imp_GetEnvironmentStringsW
0x18002f330  nop     dword ptr [rax+rax+00h]
0x18002f335  mov     rsi, rax
0x18002f338  test    rax, rax
0x18002f33b  jnz     short loc_18002F35D
0x18002f33d  call    cs:__imp_GetEnvironmentStringsW
0x18002f344  nop     dword ptr [rax+rax+00h]
0x18002f349  mov     [rsp+4B0h+var_480], 1
0x18002f351  mov     rsi, rax
0x18002f354  test    rax, rax
0x18002f357  jz      loc_18002F412
0x18002f35d  xor     eax, eax
0x18002f35f  lea     rcx, [rbp+3B0h+Data]; void *
0x18002f363  xor     edx, edx; Val
0x18002f365  mov     dword ptr [rbp+3B0h+Data+4], eax
0x18002f368  lea     r8d, [rax+6Ch]; Size
0x18002f36c  call    memset_0
0x18002f371  lea     rcx, [rbp+3B0h+Data]
0x18002f375  call    SymCryptMd4Init
0x18002f37a  mov     r13d, [rsp+4B0h+var_480]
0x18002f37f  xor     edi, edi
0x18002f381  mov     r14, rsi
0x18002f384  mov     eax, edi
0x18002f386  mov     edx, 7FFFh; MaxCount
0x18002f38b  add     r14, rax
0x18002f38e  test    r13d, r13d
0x18002f391  jnz     short loc_18002F3AD
0x18002f393  add     r14, 2
0x18002f397  mov     rcx, r14; Source
0x18002f39a  call    cs:__imp_wcsnlen
0x18002f3a1  nop     dword ptr [rax+rax+00h]
0x18002f3a6  mov     rdi, rax
0x18002f3a9  add     edi, edi
0x18002f3ab  jmp     short loc_18002F3C1
0x18002f3ad  inc     r14
0x18002f3b0  mov     rcx, r14; String
0x18002f3b3  call    cs:__imp_strnlen
0x18002f3ba  nop     dword ptr [rax+rax+00h]
0x18002f3bf  mov     edi, eax
0x18002f3c1  mov     r8d, edi
0x18002f3c4  lea     rcx, [rbp+3B0h+Data]
0x18002f3c8  mov     rdx, r14
0x18002f3cb  call    SymCryptMd4Append
0x18002f3d0  test    edi, edi
0x18002f3d2  jnz     short loc_18002F384
0x18002f3d4  lea     rdx, xmmword_1801A2160
0x18002f3db  lea     rcx, [rbp+3B0h+Data]
0x18002f3df  call    SymCryptMd4Result
0x18002f3e4  cmp     r13d, edi
0x18002f3e7  mov     rcx, rsi; penv
0x18002f3ea  mov     r13d, 0E00h
0x18002f3f0  jnz     short loc_18002F400
0x18002f3f2  call    cs:__imp_FreeEnvironmentStringsW
0x18002f3f9  nop     dword ptr [rax+rax+00h]
0x18002f3fe  jmp     short loc_18002F40C
0x18002f400  call    cs:__imp_FreeEnvironmentStringsA
0x18002f407  nop     dword ptr [rax+rax+00h]
0x18002f40c  mov     r14d, 50h ; 'P'
0x18002f412  mov     cs:dword_1801A1FE0, 1
0x18002f41c  mov     esi, 0FFFFFFE8h
0x18002f421  cmp     ebx, 10h
0x18002f424  jb      loc_18002F928
0x18002f42a  movups  xmm0, cs:xmmword_1801A2160
0x18002f431  movdqu  xmmword ptr [r15+0A0h], xmm0
0x18002f43a  cmp     ebx, 18h
0x18002f43d  jb      loc_18002F2A2
0x18002f443  add     ebx, esi
0x18002f445  call    Old_IsRNGWinNT
0x18002f44a  test    eax, eax
0x18002f44c  jz      loc_18002F928
0x18002f452  cmp     ebx, 40h ; '@'
0x18002f455  jb      loc_18002F928
0x18002f45b  mov     rax, cs:___NtQuerySystemInformationRNG
0x18002f462  test    rax, rax
0x18002f465  jz      loc_18002F928
0x18002f46b  xor     r9d, r9d
0x18002f46e  mov     [rsp+4B0h+var_480], ebx
0x18002f472  lea     rsi, [r15+0B8h]
0x18002f479  mov     r8d, ebx
0x18002f47c  mov     rdx, rsi
0x18002f47f  lea     ecx, [r9+5]
0x18002f483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f488  xor     eax, eax
0x18002f48a  lea     rcx, [rbp+3B0h+Data]; void *
0x18002f48e  xor     edx, edx; Val
0x18002f490  mov     dword ptr [rbp+3B0h+Data+4], eax
0x18002f493  lea     r8d, [rax+7Ch]; Size
0x18002f497  call    memset_0
0x18002f49c  lea     rcx, [rbp+3B0h+Data]
0x18002f4a0  call    SymCryptSha1Init
0x18002f4a5  mov     r8d, [rsp+4B0h+var_480]
0x18002f4aa  lea     rcx, [rbp+3B0h+Data]
0x18002f4ae  mov     rdx, rsi
0x18002f4b1  call    SymCryptSha1Append
0x18002f4b6  mov     rdx, rsi
0x18002f4b9  lea     rcx, [rbp+3B0h+Data]
0x18002f4bd  call    SymCryptSha1Result
0x18002f4c2  mov     r15d, 0FFFFFFE8h
0x18002f4c8  mov     r8d, 30h ; '0'
0x18002f4ce  add     ebx, r15d
0x18002f4d1  cmp     ebx, r8d
0x18002f4d4  jb      loc_18002F928
0x18002f4da  mov     rax, cs:___NtQuerySystemInformationRNG
0x18002f4e1  lea     r9, [rsp+4B0h+var_480]
0x18002f4e6  add     rsi, 18h
0x18002f4ea  lea     ecx, [r8-2Dh]
0x18002f4ee  mov     rdx, rsi
0x18002f4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4f6  test    eax, eax
0x18002f4f8  js      short loc_18002F51E
0x18002f4fa  mov     eax, [rsp+4B0h+var_480]
0x18002f4fe  add     eax, 8
0x18002f501  and     eax, 0FFFFFFF8h
0x18002f504  cmp     eax, ebx
0x18002f506  ja      loc_18002F2A2
0x18002f50c  mov     edi, eax
0x18002f50e  sub     ebx, eax
0x18002f510  add     rdi, rsi
0x18002f513  cmp     ebx, 18h
0x18002f516  jb      loc_18002F928
0x18002f51c  jmp     short loc_18002F521
0x18002f51e  mov     rdi, rsi
0x18002f521  mov     rax, cs:___NtQuerySystemInformationRNG
0x18002f528  lea     r9, [rsp+4B0h+var_480]
0x18002f52d  mov     r8d, 18h
0x18002f533  mov     rdx, rdi
0x18002f536  lea     ecx, [r8-11h]
0x18002f53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f53f  mov     esi, 0FFFFFFF8h
0x18002f544  test    eax, eax
0x18002f546  js      short loc_18002F560
0x18002f548  mov     ecx, [rsp+4B0h+var_480]
0x18002f54c  add     ecx, 8
0x18002f54f  and     ecx, esi
0x18002f551  cmp     ecx, ebx
0x18002f553  ja      loc_18002F2A2
0x18002f559  mov     eax, ecx
0x18002f55b  add     rdi, rax
0x18002f55e  sub     ebx, ecx
0x18002f560  mov     r8d, 0B0h
0x18002f566  cmp     ebx, r8d
0x18002f569  jb      loc_18002F928
0x18002f56f  mov     rax, cs:___NtQuerySystemInformationRNG
0x18002f576  lea     r9, [rsp+4B0h+var_480]
0x18002f57b  mov     rdx, rdi
0x18002f57e  mov     ecx, r14d
0x18002f581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f586  test    eax, eax
0x18002f588  js      short loc_18002F5A9
0x18002f58a  mov     eax, [rsp+4B0h+var_480]
0x18002f58e  add     eax, 8
0x18002f591  and     eax, esi
0x18002f593  cmp     eax, ebx
0x18002f595  ja      loc_18002F2A2
0x18002f59b  sub     ebx, eax
0x18002f59d  cmp     ebx, 40h ; '@'
0x18002f5a0  jb      loc_18002F928
0x18002f5a6  add     rdi, rax
0x18002f5a9  mov     rax, cs:___NtQuerySystemInformationRNG
0x18002f5b0  lea     r9, [rsp+4B0h+var_480]
0x18002f5b5  mov     r8d, 40h ; '@'
0x18002f5bb  mov     rdx, rdi
0x18002f5be  lea     ecx, [r8-2Bh]
0x18002f5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5c7  test    eax, eax
0x18002f5c9  js      short loc_18002F5E3
0x18002f5cb  mov     ecx, [rsp+4B0h+var_480]
0x18002f5cf  add     ecx, 8
0x18002f5d2  and     ecx, esi
0x18002f5d4  cmp     ecx, ebx
0x18002f5d6  ja      loc_18002F2A2
0x18002f5dc  mov     eax, ecx
0x18002f5de  add     rdi, rax
0x18002f5e1  sub     ebx, ecx
0x18002f5e3  mov     r8d, 178h
0x18002f5e9  cmp     ebx, r8d
0x18002f5ec  jb      loc_18002F928
0x18002f5f2  mov     rax, cs:___NtQuerySystemInformationRNG
0x18002f5f9  lea     r9, [rsp+4B0h+var_480]
0x18002f5fe  mov     rdx, rdi
0x18002f601  mov     ecx, 2
0x18002f606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f60b  test    eax, eax
0x18002f60d  js      short loc_18002F62E
0x18002f60f  mov     eax, [rsp+4B0h+var_480]
0x18002f613  add     eax, 8
  ... truncated ...
```
