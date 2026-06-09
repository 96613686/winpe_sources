# mwSaveData

- ea: `0x180002320`
- end: `0x180002766`
- name: `mwSaveData`
- size: `1094`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180005170`

## callees

- `0x180001558`
- `0x180002320`
- `0x1800031c4`
- `0x180003a44`
- `0x180005c29`
- `0x180005c60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000269d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000269d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002449`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002449`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800023e2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800023e2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002390`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002390`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800026c0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002723`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800026c0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002723`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800026b4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800026b4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800026c9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000273d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800026c9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000273d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180002378`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180002378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002689`
- `WINMM!mmioRenameW` at `0x1800025c5`
- `WINMM!mmioRenameW` at `0x1800025c5`
- `WINMM!mmioDescend` at `0x180002653`
- `WINMM!mmioDescend` at `0x180002672`
- `WINMM!mmioDescend` at `0x180002653`
- `WINMM!mmioDescend` at `0x180002672`
- `WINMM!mmioClose` at `0x1800024e6`
- `WINMM!mmioClose` at `0x18000252c`
- `WINMM!mmioClose` at `0x1800024e6`
- `WINMM!mmioClose` at `0x18000252c`
- `WINMM!mmioSeek` at `0x180002402`
- `WINMM!mmioSeek` at `0x180002402`
- `WINMM!mmioRead` at `0x180002495`
- `WINMM!mmioRead` at `0x180002495`
- `WINMM!mmioOpenW` at `0x180002599`
- `WINMM!mmioOpenW` at `0x180002627`
- `WINMM!mmioOpenW` at `0x180002599`
- `WINMM!mmioOpenW` at `0x180002627`
- `WINMM!mmioWrite` at `0x1800024af`
- `WINMM!mmioWrite` at `0x1800024af`

## pseudocode

```c
HGLOBAL __fastcall mwSaveData(__int64 a1)
{
  unsigned int v1; // edx
  unsigned int v3; // ecx
  unsigned int v4; // eax
  HGLOBAL result; // rax
  void *v6; // r13
  HPSTR v7; // r14
  __int64 i; // rbx
  int *v9; // rbx
  int v10; // ecx
  int v11; // eax
  HMMIO *v12; // r15
  DWORD v13; // r12d
  DWORD v14; // esi
  void *v15; // rcx
  HMMIO *v16; // r14
  unsigned int v17; // eax
  HMMIO v18; // rcx
  _WORD *v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rax
  _WORD *v22; // rdx
  __int64 v23; // rcx
  WCHAR *v24; // r8
  _WORD *v25; // rcx
  HMMIO v26; // rax
  HMMIO v27; // rcx
  void *v28; // rcx
  const void *v29; // rcx
  HGLOBAL v30; // rbx
  _DWORD *v31; // rcx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+34h] [rbp-CCh]
  HPSTR pch; // [rsp+38h] [rbp-C8h]
  HMMIO hmmio; // [rsp+40h] [rbp-C0h]
  struct _MMCKINFO pmmcki; // [rsp+48h] [rbp-B8h] BYREF
  struct _MMCKINFO v37; // [rsp+60h] [rbp-A0h] BYREF
  struct _MMIOINFO pmmioinfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszFileName[264]; // [rsp+F0h] [rbp-10h] BYREF

  v1 = *(_DWORD *)(a1 + 76);
  v3 = *(_DWORD *)(a1 + 148);
  v4 = v3;
  if ( v3 >= v1 )
    v4 = v1;
  if ( v4 <= 1 )
  {
    v3 = 1;
  }
  else if ( v3 >= v1 )
  {
    v3 = v1;
  }
  result = GlobalAlloc(2u, v3);
  v6 = result;
  if ( !result || (result = GlobalLock(result), pch = (HPSTR)result, (v7 = (HPSTR)result) == 0) )
  {
    *(_DWORD *)(a1 + 140) = 264;
    if ( !v6 )
      return result;
    return GlobalFree(v6);
  }
  hmmio = (HMMIO)CreateSaveFile(a1, pszFileName);
  if ( hmmio )
  {
    for ( i = *(unsigned int *)(a1 + 116); ; i = v17 )
    {
      v9 = (int *)(*(_QWORD *)(a1 + 104) + 16 * i);
      v10 = *v9;
      if ( *v9 >= 0 )
      {
        v12 = (HMMIO *)(a1 + 80);
        mmioSeek(*(HMMIO *)(a1 + 80), v10 + *(_DWORD *)(a1 + 112), 0);
        v11 = 0;
      }
      else
      {
        SetFilePointer(*(HANDLE *)(a1 + 88), v10 & 0x7FFFFFFF, 0, 0);
        v11 = 1;
        v12 = (HMMIO *)(a1 + 80);
      }
      v13 = v9[1];
      v33 = v11;
      if ( v13 )
      {
        while ( 1 )
        {
          v14 = *(_DWORD *)(a1 + 148);
          if ( v14 >= v13 )
            v14 = v13;
          if ( v11 )
          {
            v15 = *(void **)(a1 + 88);
            NumberOfBytesRead = 0;
            if ( !ReadFile(v15, v7, v14, &NumberOfBytesRead, 0) || NumberOfBytesRead != v14 )
            {
              *(_DWORD *)(a1 + 140) = 348;
              break;
            }
          }
          else
          {
            v16 = (HMMIO *)(a1 + 80);
            if ( mmioRead(*(HMMIO *)(a1 + 80), pch, v14) != v14 )
            {
              *(_DWORD *)(a1 + 140) = 348;
              goto LABEL_23;
            }
            v7 = pch;
          }
          if ( mmioWrite(hmmio, v7, v14) != v14 )
          {
            *(_DWORD *)(a1 + 140) = 349;
            break;
          }
          v13 -= v14;
          if ( !v13 )
            break;
          v11 = v33;
        }
      }
      v16 = v12;
LABEL_23:
      if ( *(_DWORD *)(a1 + 140) )
        break;
      v17 = v9[3];
      v16 = v12;
      if ( v17 == -1 )
        break;
      v7 = pch;
    }
    mmioClose(hmmio, 0);
    if ( !*(_DWORD *)(a1 + 140) )
    {
      memset_0(&pmmioinfo, 0, sizeof(pmmioinfo));
      v18 = *v16;
      memset(&pmmcki, 0, sizeof(pmmcki));
      memset(&v37, 0, sizeof(v37));
      if ( v18 )
        mmioClose(v18, 0);
      InitMMIOOpen(a1, &pmmioinfo);
      v19 = *(_WORD **)(a1 + 152);
      if ( v19 )
      {
        v20 = 2147483646;
        v21 = 260;
        v22 = (_WORD *)(a1 + 256);
        do
        {
          if ( !v20 )
            break;
          if ( !*v19 )
            break;
          *v22++ = *v19++;
          --v20;
          --v21;
        }
        while ( v21 );
      }
      else
      {
        if ( !mmioOpenW((LPWSTR)(a1 + 256), &pmmioinfo, 0x200u) )
          *(_DWORD *)(a1 + 140) = 349;
        if ( *(_DWORD *)(a1 + 140) || !mmioRenameW(pszFileName, (LPCWSTR)(a1 + 256), &pmmioinfo, 0) )
          goto LABEL_54;
        v23 = 2147483646;
        v24 = pszFileName;
        v21 = 260;
        v22 = (_WORD *)(a1 + 256);
        do
        {
          if ( !v23 )
            break;
          if ( !*v24 )
            break;
          *v22++ = *v24++;
          --v23;
          --v21;
        }
        while ( v21 );
        pszFileName[0] = 0;
      }
      v25 = v22 - 1;
      if ( v21 )
        v25 = v22;
      *v25 = 0;
LABEL_54:
      v26 = mmioOpenW((LPWSTR)(a1 + 256), &pmmioinfo, 0x20u);
      *v16 = v26;
      if ( !*(_DWORD *)(a1 + 140) )
      {
        pmmcki.fccType = 1163280727;
        mmioDescend(v26, &pmmcki, 0, 0x20u);
        v27 = *v16;
        v37.ckid = 1635017060;
        mmioDescend(v27, &v37, &pmmcki, 0x10u);
        v28 = *(void **)(a1 + 88);
        *(_DWORD *)(a1 + 112) = v37.dwDataOffset;
        if ( v28 != (void *)-1LL )
        {
          CloseHandle(v28);
          *(_DWORD *)(a1 + 132) = 0;
          DeleteFileW((LPCWSTR)(a1 + 776));
          *(_QWORD *)(a1 + 88) = -1;
        }
        v29 = *(const void **)(a1 + 104);
        if ( v29 )
        {
          v30 = GlobalHandle(v29);
          GlobalUnlock(v30);
          GlobalFree(v30);
          *(_QWORD *)(a1 + 104) = 0;
          *(_DWORD *)(a1 + 128) = 0;
        }
        *(_QWORD *)(a1 + 120) = 0;
        *(_DWORD *)(a1 + 116) = 0;
        if ( (unsigned int)mwAllocMoreBlockNodes(a1) != -1 )
        {
          v31 = *(_DWORD **)(a1 + 104);
          v31[3] = -1;
          v31[1] = *(_DWORD *)(a1 + 76);
          v31[2] = *(_DWORD *)(a1 + 76);
          if ( !*(_QWORD *)(a1 + 152) && !pszFileName[0] )
            *(_DWORD *)(a1 + 140) = 349;
        }
      }
    }
  }
  GlobalUnlock(v6);
  return GlobalFree(v6);
}

```

## disassembly

```asm
0x180002320  push    rbp
0x180002322  push    rbx
0x180002323  push    rsi
0x180002324  push    rdi
0x180002325  push    r12
0x180002327  push    r13
0x180002329  push    r14
0x18000232b  push    r15
0x18000232d  lea     rbp, [rsp-218h]
0x180002335  sub     rsp, 318h
0x18000233c  mov     rax, cs:__security_cookie
0x180002343  xor     rax, rsp
0x180002346  mov     [rbp+250h+var_50], rax
0x18000234d  mov     edx, [rcx+4Ch]
0x180002350  mov     rdi, rcx
0x180002353  mov     ecx, [rcx+94h]
0x180002359  cmp     ecx, edx
0x18000235b  mov     eax, ecx
0x18000235d  cmovnb  eax, edx
0x180002360  cmp     eax, 1
0x180002363  jbe     short loc_18000236C
0x180002365  cmp     ecx, edx
0x180002367  cmovnb  ecx, edx
0x18000236a  jmp     short loc_180002371
0x18000236c  mov     ecx, 1
0x180002371  mov     edx, ecx; dwBytes
0x180002373  mov     ecx, 2; uFlags
0x180002378  call    cs:__imp_GlobalAlloc
0x18000237e  xor     r12d, r12d
0x180002381  mov     r13, rax
0x180002384  test    rax, rax
0x180002387  jz      loc_18000272B
0x18000238d  mov     rcx, rax; hMem
0x180002390  call    cs:__imp_GlobalLock
0x180002396  mov     [rsp+350h+pch], rax
0x18000239b  mov     r14, rax
0x18000239e  test    rax, rax
0x1800023a1  jz      loc_18000272B
0x1800023a7  lea     rdx, [rbp+250h+pszFileName]
0x1800023ab  mov     rcx, rdi
0x1800023ae  call    CreateSaveFile
0x1800023b3  mov     [rsp+350h+hmmio], rax
0x1800023b8  test    rax, rax
0x1800023bb  jz      loc_180002720
0x1800023c1  mov     ebx, [rdi+74h]
0x1800023c4  shl     rbx, 4
0x1800023c8  add     rbx, [rdi+68h]
0x1800023cc  mov     ecx, [rbx]
0x1800023ce  test    ecx, ecx
0x1800023d0  jns     short loc_1800023F3
0x1800023d2  btr     ecx, 1Fh
0x1800023d6  xor     r9d, r9d; dwMoveMethod
0x1800023d9  mov     edx, ecx; lDistanceToMove
0x1800023db  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800023de  mov     rcx, [rdi+58h]; hFile
0x1800023e2  call    cs:__imp_SetFilePointer
0x1800023e8  mov     eax, 1
0x1800023ed  lea     r15, [rdi+50h]
0x1800023f1  jmp     short loc_18000240B
0x1800023f3  mov     edx, [rdi+70h]
0x1800023f6  lea     r15, [rdi+50h]
0x1800023fa  add     edx, ecx; lOffset
0x1800023fc  xor     r8d, r8d; iOrigin
0x1800023ff  mov     rcx, [r15]; hmmio
0x180002402  call    cs:__imp_mmioSeek
0x180002408  mov     eax, r12d
0x18000240b  mov     r12d, [rbx+4]
0x18000240f  mov     [rsp+350h+var_31C], eax
0x180002413  test    r12d, r12d
0x180002416  jz      short loc_180002463
0x180002418  mov     esi, [rdi+94h]
0x18000241e  cmp     esi, r12d
0x180002421  cmovnb  esi, r12d
0x180002425  mov     r8d, esi; cch
0x180002428  test    eax, eax
0x18000242a  jz      short loc_180002489
0x18000242c  mov     rcx, [rdi+58h]; hFile
0x180002430  lea     r9, [rsp+350h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180002435  mov     rdx, r14; lpBuffer
0x180002438  mov     [rsp+350h+NumberOfBytesRead], 0
0x180002440  mov     [rsp+350h+lpOverlapped], 0; lpOverlapped
0x180002449  call    cs:__imp_ReadFile
0x18000244f  test    eax, eax
0x180002451  jz      short loc_180002459
0x180002453  cmp     [rsp+350h+NumberOfBytesRead], esi
0x180002457  jz      short loc_1800024A4
0x180002459  mov     dword ptr [rdi+8Ch], 15Ch
0x180002463  mov     r14, r15
0x180002466  xor     r12d, r12d
0x180002469  cmp     [rdi+8Ch], r12d
0x180002470  jnz     short loc_1800024DF
0x180002472  mov     eax, [rbx+0Ch]
0x180002475  mov     r14, r15
0x180002478  cmp     eax, 0FFFFFFFFh
0x18000247b  jz      short loc_1800024DF
0x18000247d  mov     r14, [rsp+350h+pch]
0x180002482  mov     ebx, eax
0x180002484  jmp     loc_1800023C4
0x180002489  mov     rdx, [rsp+350h+pch]; pch
0x18000248e  lea     r14, [rdi+50h]
0x180002492  mov     rcx, [r14]; hmmio
0x180002495  call    cs:__imp_mmioRead
0x18000249b  cmp     eax, esi
0x18000249d  jnz     short loc_1800024D3
0x18000249f  mov     r14, [rsp+350h+pch]
0x1800024a4  mov     rcx, [rsp+350h+hmmio]; hmmio
0x1800024a9  mov     r8d, esi; cch
0x1800024ac  mov     rdx, r14; pch
0x1800024af  call    cs:__imp_mmioWrite
0x1800024b5  cmp     eax, esi
0x1800024b7  jnz     short loc_1800024C7
0x1800024b9  sub     r12d, esi
0x1800024bc  jz      short loc_180002463
0x1800024be  mov     eax, [rsp+350h+var_31C]
0x1800024c2  jmp     loc_180002418
0x1800024c7  mov     dword ptr [rdi+8Ch], 15Dh
0x1800024d1  jmp     short loc_180002463
0x1800024d3  mov     dword ptr [rdi+8Ch], 15Ch
0x1800024dd  jmp     short loc_180002466
0x1800024df  mov     rcx, [rsp+350h+hmmio]; hmmio
0x1800024e4  xor     edx, edx; fuClose
0x1800024e6  call    cs:__imp_mmioClose
0x1800024ec  cmp     [rdi+8Ch], r12d
0x1800024f3  jnz     loc_180002720
0x1800024f9  xor     edx, edx; Val
0x1800024fb  lea     rcx, [rbp+250h+pmmioinfo]; void *
0x1800024ff  lea     r8d, [rdx+64h]; Size
0x180002503  call    memset_0
0x180002508  mov     rcx, [r14]; hmmio
0x18000250b  xor     eax, eax
0x18000250d  mov     [rsp+350h+pmmcki.dwFlags], eax
0x180002511  xorps   xmm0, xmm0
0x180002514  mov     [rsp+350h+var_2F0.dwFlags], eax
0x180002518  xorps   xmm1, xmm1
0x18000251b  movups  xmmword ptr [rsp+350h+pmmcki.ckid], xmm0
0x180002520  movups  xmmword ptr [rsp+350h+var_2F0.ckid], xmm1
0x180002525  test    rcx, rcx
0x180002528  jz      short loc_180002532
0x18000252a  xor     edx, edx; fuClose
0x18000252c  call    cs:__imp_mmioClose
0x180002532  lea     rdx, [rbp+250h+pmmioinfo]
0x180002536  mov     rcx, rdi
0x180002539  call    InitMMIOOpen
0x18000253e  mov     r8, [rdi+98h]
0x180002545  lea     rbx, [rdi+100h]
0x18000254c  test    r8, r8
0x18000254f  jz      short loc_18000258C
0x180002551  mov     ecx, 7FFFFFFEh
0x180002556  mov     eax, 104h
0x18000255b  mov     rdx, rbx
0x18000255e  test    rcx, rcx
0x180002561  jz      loc_180002609
0x180002567  movzx   r9d, word ptr [r8]
0x18000256b  test    r9w, r9w
0x18000256f  jz      loc_180002609
0x180002575  mov     [rdx], r9w
0x180002579  add     r8, 2
0x18000257d  add     rdx, 2
0x180002581  dec     rcx
0x180002584  sub     rax, 1
0x180002588  jnz     short loc_18000255E
0x18000258a  jmp     short loc_180002609
0x18000258c  mov     r8d, 200h; fdwOpen
0x180002592  lea     rdx, [rbp+250h+pmmioinfo]; pmmioinfo
0x180002596  mov     rcx, rbx; pszFileName
0x180002599  call    cs:__imp_mmioOpenW
0x18000259f  test    rax, rax
0x1800025a2  jnz     short loc_1800025AE
0x1800025a4  mov     dword ptr [rdi+8Ch], 15Dh
0x1800025ae  cmp     [rdi+8Ch], r12d
0x1800025b5  jnz     short loc_180002618
0x1800025b7  xor     r9d, r9d; fdwRename
0x1800025ba  lea     r8, [rbp+250h+pmmioinfo]; pmmioinfo
0x1800025be  mov     rdx, rbx; pszNewFileName
0x1800025c1  lea     rcx, [rbp+250h+pszFileName]; pszFileName
0x1800025c5  call    cs:__imp_mmioRenameW
0x1800025cb  test    eax, eax
0x1800025cd  jz      short loc_180002618
0x1800025cf  mov     ecx, 7FFFFFFEh
0x1800025d4  lea     r8, [rbp+250h+pszFileName]
0x1800025d8  mov     eax, 104h
0x1800025dd  mov     rdx, rbx
0x1800025e0  test    rcx, rcx
0x1800025e3  jz      short loc_180002604
0x1800025e5  movzx   r9d, word ptr [r8]
0x1800025e9  test    r9w, r9w
0x1800025ed  jz      short loc_180002604
0x1800025ef  mov     [rdx], r9w
0x1800025f3  add     r8, 2
0x1800025f7  add     rdx, 2
0x1800025fb  dec     rcx
0x1800025fe  sub     rax, 1
0x180002602  jnz     short loc_1800025E0
0x180002604  mov     [rbp+250h+pszFileName], r12w
0x180002609  test    rax, rax
0x18000260c  lea     rcx, [rdx-2]
0x180002610  cmovnz  rcx, rdx
0x180002614  mov     [rcx], r12w
0x180002618  mov     esi, 20h ; ' '
0x18000261d  lea     rdx, [rbp+250h+pmmioinfo]; pmmioinfo
0x180002621  mov     r8d, esi; fdwOpen
0x180002624  mov     rcx, rbx; pszFileName
0x180002627  call    cs:__imp_mmioOpenW
0x18000262d  mov     [r14], rax
0x180002630  cmp     [rdi+8Ch], r12d
0x180002637  jnz     loc_180002720
0x18000263d  mov     r9d, esi; fuDescend
0x180002640  mov     [rsp+350h+pmmcki.fccType], 45564157h
0x180002648  xor     r8d, r8d; pmmckiParent
0x18000264b  lea     rdx, [rsp+350h+pmmcki]; pmmcki
0x180002650  mov     rcx, rax; hmmio
0x180002653  call    cs:__imp_mmioDescend
0x180002659  mov     rcx, [r14]; hmmio
0x18000265c  lea     r9d, [rsi-10h]; fuDescend
0x180002660  lea     r8, [rsp+350h+pmmcki]; pmmckiParent
0x180002665  mov     [rsp+350h+var_2F0.ckid], 61746164h
0x18000266d  lea     rdx, [rsp+350h+var_2F0]; pmmcki
0x180002672  call    cs:__imp_mmioDescend
0x180002678  mov     rcx, [rdi+58h]; hObject
0x18000267c  mov     eax, [rsp+350h+var_2F0.dwDataOffset]
0x180002680  mov     [rdi+70h], eax
0x180002683  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002687  jz      short loc_1800026AB
0x180002689  call    cs:__imp_CloseHandle
0x18000268f  lea     rcx, [rdi+308h]; lpFileName
0x180002696  mov     [rdi+84h], r12d
0x18000269d  call    cs:__imp_DeleteFileW
0x1800026a3  mov     qword ptr [rdi+58h], 0FFFFFFFFFFFFFFFFh
0x1800026ab  mov     rcx, [rdi+68h]; pMem
0x1800026af  test    rcx, rcx
0x1800026b2  jz      short loc_1800026DA
0x1800026b4  call    cs:__imp_GlobalHandle
0x1800026ba  mov     rcx, rax; hMem
0x1800026bd  mov     rbx, rax
0x1800026c0  call    cs:__imp_GlobalUnlock
0x1800026c6  mov     rcx, rbx; hMem
0x1800026c9  call    cs:__imp_GlobalFree
0x1800026cf  mov     [rdi+68h], r12
0x1800026d3  mov     [rdi+80h], r12d
0x1800026da  mov     rcx, rdi
0x1800026dd  mov     [rdi+78h], r12
0x1800026e1  mov     [rdi+74h], r12d
0x1800026e5  call    mwAllocMoreBlockNodes
0x1800026ea  cmp     eax, 0FFFFFFFFh
0x1800026ed  jz      short loc_180002720
0x1800026ef  mov     rcx, [rdi+68h]
0x1800026f3  mov     dword ptr [rcx+0Ch], 0FFFFFFFFh
0x1800026fa  mov     eax, [rdi+4Ch]
0x1800026fd  mov     [rcx+4], eax
0x180002700  mov     eax, [rdi+4Ch]
0x180002703  mov     [rcx+8], eax
0x180002706  cmp     [rdi+98h], r12
0x18000270d  jnz     short loc_180002720
0x18000270f  cmp     [rbp+250h+pszFileName], r12w
0x180002714  jnz     short loc_180002720
0x180002716  mov     dword ptr [rdi+8Ch], 15Dh
0x180002720  mov     rcx, r13; hMem
0x180002723  call    cs:__imp_GlobalUnlock
0x180002729  jmp     short loc_18000273A
0x18000272b  mov     dword ptr [rdi+8Ch], 108h
0x180002735  test    r13, r13
0x180002738  jz      short loc_180002743
0x18000273a  mov     rcx, r13; hMem
0x18000273d  call    cs:__imp_GlobalFree
0x180002743  mov     rcx, [rbp+250h+var_50]
0x18000274a  xor     rcx, rsp; StackCookie
0x18000274d  call    __security_check_cookie
0x180002752  add     rsp, 318h
0x180002759  pop     r15
0x18000275b  pop     r14
0x18000275d  pop     r13
0x18000275f  pop     r12
0x180002761  pop     rdi
0x180002762  pop     rsi
0x180002763  pop     rbx
0x180002764  pop     rbp
0x180002765  retn
```
