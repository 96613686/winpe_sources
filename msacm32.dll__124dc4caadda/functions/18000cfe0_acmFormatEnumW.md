# acmFormatEnumW

- ea: `0x18000cfe0`
- end: `0x18000d6b3`
- name: `acmFormatEnumW`
- size: `1747`
- prototype: `MMRESULT __stdcall(HACMDRIVER had, LPACMFORMATDETAILSW pafd, ACMFORMATENUMCBW fnCallback, DWORD_PTR dwInstance, DWORD fdwEnum)`
- caller_count: `4`
- callee_count: `20`
- tags: ``

## callers

- `0x180006f00`
- `0x18000cef0`
- `0x18000ed40`
- `0x180010548`

## callees

- `0x180001940`
- `0x1800021e0`
- `0x180002220`
- `0x180002400`
- `0x180002470`
- `0x180002a80`
- `0x1800034e0`
- `0x180003e80`
- `0x180003ec0`
- `0x180003f40`
- `0x180003fc0`
- `0x180004ab0`
- `0x180004af0`
- `0x180009270`
- `0x180009afa`
- `0x18000c434`
- `0x18000c890`
- `0x18000cb04`
- `0x18000cfe0`
- `0x1800126b9`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000d301`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000d301`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000d1bd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000d1bd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d2e6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d2f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d2e6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000d2f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000d2ef`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000d2ef`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000d1c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000d1c6`
- `api-ms-win-mm-misc-l1-1-0!CloseDriver` at `0x18000d2dd`
- `api-ms-win-mm-misc-l1-1-0!CloseDriver` at `0x18000d2dd`
- `api-ms-win-mm-misc-l1-1-0!OpenDriver` at `0x18000d20c`
- `api-ms-win-mm-misc-l1-1-0!OpenDriver` at `0x18000d20c`

## pseudocode

```c
MMRESULT __stdcall acmFormatEnumW(
        HACMDRIVER had,
        LPACMFORMATDETAILSW pafd,
        ACMFORMATENUMCBW fnCallback,
        DWORD_PTR dwInstance,
        DWORD fdwEnum)
{
  int v5; // r12d
  MMRESULT result; // eax
  DWORD v10; // r13d
  __int64 cbwfx; // rdx
  unsigned int wFormatTag; // ecx
  SIZE_T v13; // rbx
  LPWAVEFORMATEX pwfx; // rcx
  HGLOBAL v15; // rax
  void *v16; // rax
  MMRESULT v17; // ebx
  __int64 v18; // r13
  __int64 i; // r14
  MMRESULT v20; // eax
  LPCVOID v21; // rsi
  HGLOBAL v22; // rax
  HGLOBAL v23; // rax
  BOOL v24; // r15d
  __int64 v25; // r14
  HACMDRIVERID v26; // r12
  unsigned int v27; // edi
  HACMDRIVERID v28; // r13
  __int64 j; // r14
  LPACMFORMATDETAILSW v30; // rdi
  HACMDRIVERID v31; // r14
  MMRESULT v32; // eax
  DWORD v33; // r12d
  DWORD v34; // r13d
  HACMDRIVERID v35; // r14
  HACMDRIVERID v36; // r8
  HACMDRIVERID v37; // r12
  __int64 k; // rdx
  unsigned int v39; // r13d
  MMRESULT v40; // eax
  unsigned int v41; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v42; // [rsp+44h] [rbp-BCh]
  DWORD v43; // [rsp+48h] [rbp-B8h]
  __int64 v44; // [rsp+50h] [rbp-B0h]
  LPCVOID pMem; // [rsp+58h] [rbp-A8h]
  HACMDRIVERID hadid; // [rsp+60h] [rbp-A0h] BYREF
  HACMDRIVER phad; // [rsp+68h] [rbp-98h] BYREF
  HDRVR hDriver; // [rsp+70h] [rbp-90h]
  __int64 v49; // [rsp+78h] [rbp-88h]
  __int64 v50; // [rsp+80h] [rbp-80h]
  __int64 v51; // [rsp+88h] [rbp-78h]
  LPACMFORMATDETAILSW v52; // [rsp+90h] [rbp-70h]
  int v53; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v54; // [rsp+A4h] [rbp-5Ch]
  unsigned int v55; // [rsp+B4h] [rbp-4Ch]

  v5 = 0;
  v50 = (__int64)fnCallback;
  v52 = pafd;
  v49 = dwInstance;
  v41 = 0;
  memset_0(&v53, 0, 0x78u);
  v44 = pagFindAndBoot();
  if ( !v44 )
    return 1;
  if ( !(unsigned int)ValidateWritePointer(pafd, 4)
    || pafd->cbStruct < 0x11C
    || !(unsigned int)ValidateWritePointer(pafd, pafd->cbStruct) )
  {
    return 11;
  }
  if ( had && !(unsigned int)ValidateHandle(had, 2) )
    return 5;
  if ( !fnCallback )
    return 11;
  v10 = fdwEnum;
  if ( (fdwEnum & 0xFE00FFFF) != 0 || (fdwEnum & 0x400000) != 0 && (fdwEnum & 0x1800000) == 0 )
    return 10;
  result = IMetricsMaxSizeFormat(v44, had, &v41);
  if ( !result )
  {
    cbwfx = pafd->cbwfx;
    if ( (unsigned int)cbwfx < v41 || !(unsigned int)ValidateWritePointer(pafd->pwfx, cbwfx) || pafd->fdwSupport )
      return 11;
    if ( (fdwEnum & 0x10000) != 0 )
    {
      wFormatTag = pafd->pwfx->wFormatTag;
      v41 = wFormatTag;
      if ( !wFormatTag )
        return 11;
      v5 = 1;
      if ( pafd->dwFormatTag != wFormatTag )
        return 11;
    }
    else
    {
      v41 = 0;
    }
    v43 = fdwEnum & 0x100000;
    v42 = fdwEnum & 0x200000;
    if ( (fdwEnum & 0x100000) != 0 || (fdwEnum & 0x200000) != 0 )
    {
      pwfx = pafd->pwfx;
      if ( pwfx->wFormatTag == 1 )
        v13 = 16;
      else
        v13 = pwfx->cbSize + 18LL;
      if ( !(unsigned int)ValidateReadWaveFormat(pwfx) || !pafd->pwfx->wFormatTag )
        return 11;
    }
    else
    {
      v13 = 16;
    }
    v15 = GlobalAlloc(0x42u, v13);
    v16 = GlobalLock(v15);
    pMem = v16;
    if ( !v16 )
      return 7;
    memcpy_0(v16, pafd->pwfx, v13);
    v17 = 0;
    hDriver = 0;
    if ( (fdwEnum & 0x400000) != 0 )
      hDriver = OpenDriver(L"wavemapper", L"Drivers32", 0);
    if ( had )
    {
      v18 = *(_QWORD *)(had + 5);
      for ( i = 0; (unsigned int)i < *(_DWORD *)(v18 + 64); i = (unsigned int)(i + 1) )
      {
        if ( !v5 || v41 == *(_DWORD *)(*(_QWORD *)(v18 + 68) + 8 * i) )
        {
          v53 = 120;
          v54 = i;
          v17 = IFormatTagDetails(v44, v18, &v53, 0);
          if ( !v17 )
          {
            if ( v42 )
              v20 = ISuggestEnum(hDriver, had, v50, v49, (LPWAVEFORMATEX)pMem, fdwEnum);
            else
              v20 = IFormatEnum(hDriver, had, &v53, pafd, v50, v49, pMem, fdwEnum);
            v17 = v20;
          }
          if ( v17 == 1 || v5 )
          {
            v17 = 0;
            goto LABEL_49;
          }
        }
      }
      goto LABEL_49;
    }
    if ( v5 )
    {
      LODWORD(phad) = 0;
      hadid = 0;
      v24 = !v43 && !v42;
      v25 = v44;
      v26 = 0;
      v51 = v44 + 128;
      AcquireLockShared((LPCRITICAL_SECTION)(v44 + 128));
      threadEnterListShared(v25);
      if ( !(unsigned int)IDriverGetNext(v25, &hadid, 0, 0) )
      {
        v27 = 0;
        do
        {
          v28 = hadid;
          v24 = 0;
          for ( j = 0; (unsigned int)j < *((_DWORD *)hadid + 16); j = (unsigned int)(j + 1) )
          {
            if ( v41 == *(_DWORD *)(*(_QWORD *)(hadid + 17) + 8 * j) )
            {
              v53 = 120;
              v54 = j;
              v17 = IFormatTagDetails(v44, hadid, &v53, 0);
              if ( !v17 && (!v26 || v55 > v27) )
              {
                v27 = v55;
                v26 = v28;
                LODWORD(phad) = j;
                goto LABEL_69;
              }
              break;
            }
          }
          LODWORD(j) = (_DWORD)phad;
LABEL_69:
          ;
        }
        while ( !(unsigned int)IDriverGetNext(v44, &hadid, v28, 0) );
        v30 = v52;
        if ( v26 )
        {
          v54 = j;
          v25 = v44;
          hadid = 0;
          v53 = 120;
          v17 = IFormatTagDetails(v44, v26, &v53, 0);
          if ( !v17 )
          {
            v10 = fdwEnum;
            v17 = acmDriverOpen((LPHACMDRIVER)&hadid, v26, 0);
            if ( !v17 )
            {
              v31 = hadid;
              v32 = v42
                  ? ISuggestEnum(hDriver, (HACMDRIVER)hadid, v50, v49, (LPWAVEFORMATEX)pMem, fdwEnum)
                  : IFormatEnum(hDriver, hadid, &v53, v30, v50, v49, pMem, fdwEnum);
              v17 = v32;
              acmDriverClose((HACMDRIVER)v31, 0);
              v25 = v44;
              if ( v17 == 1 )
                v17 = 0;
            }
            goto LABEL_110;
          }
        }
        else
        {
LABEL_108:
          v25 = v44;
        }
LABEL_109:
        v10 = fdwEnum;
        goto LABEL_110;
      }
      if ( v24 && v41 != 1 )
        v24 = 0;
LABEL_110:
      threadLeaveListShared(v25);
      ReleaseLock(v51);
      if ( v24 )
      {
        v21 = pMem;
        IHardwareEnum(hDriver, (__int64)pMem, v10);
        goto LABEL_50;
      }
LABEL_49:
      v21 = pMem;
LABEL_50:
      if ( hDriver )
        CloseDriver(hDriver, 0, 0);
      v22 = GlobalHandle(v21);
      GlobalUnlock(v22);
      v23 = GlobalHandle(v21);
      GlobalFree(v23);
      return v17;
    }
    v33 = v43;
    v34 = v42;
    v24 = !v43 && !v42;
    v35 = 0;
    hadid = 0;
    v51 = v44 + 128;
    AcquireLockShared((LPCRITICAL_SECTION)(v44 + 128));
    threadEnterListShared(v44);
    while ( 1 )
    {
      v36 = v35;
      v25 = v44;
      if ( (unsigned int)IDriverGetNext(v44, &hadid, v36, 0) )
        goto LABEL_109;
      v35 = hadid;
      v24 = 0;
      phad = 0;
      v41 = 0;
      if ( !v33 && !v34 )
        break;
      v37 = hadid + 16;
      for ( k = 0; (unsigned int)k < *(_DWORD *)v37; k = (unsigned int)(k + 1) )
      {
        if ( *(unsigned __int16 *)pMem == *(_DWORD *)(*(_QWORD *)(hadid + 17) + 8 * k) )
          goto LABEL_96;
      }
      if ( *(_WORD *)pMem )
      {
LABEL_86:
        v33 = v43;
      }
      else
      {
LABEL_96:
        v17 = acmDriverOpen(&phad, hadid, 0);
        if ( v17 )
          goto LABEL_86;
        v39 = 0;
        if ( *(_DWORD *)v37 )
        {
          do
          {
            v53 = 120;
            v54 = v39;
            v17 = IFormatTagDetails(v44, v35, &v53, 0);
            if ( !v17 )
            {
              if ( v42 )
                v40 = ISuggestEnum(hDriver, phad, v50, v49, (LPWAVEFORMATEX)pMem, fdwEnum);
              else
                v40 = IFormatEnum(hDriver, phad, &v53, pafd, v50, v49, pMem, fdwEnum);
              v17 = v40;
            }
            if ( v17 == 1 )
              break;
            ++v39;
          }
          while ( v39 < *((_DWORD *)v35 + 16) );
          v24 = v41;
        }
        acmDriverClose(phad, 0);
        v33 = v43;
        v34 = v42;
        if ( v17 == 1 )
        {
          v17 = 0;
          goto LABEL_108;
        }
      }
    }
    v37 = hadid + 16;
    goto LABEL_96;
  }
  return result;
}

```

## disassembly

```asm
0x18000cfe0  mov     [rsp-8+arg_10], rbx
0x18000cfe5  push    rbp
0x18000cfe6  push    rsi
0x18000cfe7  push    rdi
0x18000cfe8  push    r12
0x18000cfea  push    r13
0x18000cfec  push    r14
0x18000cfee  push    r15
0x18000cff0  lea     rbp, [rsp-30h]
0x18000cff5  sub     rsp, 130h
0x18000cffc  mov     rax, cs:__security_cookie
0x18000d003  xor     rax, rsp
0x18000d006  mov     [rbp+60h+var_40], rax
0x18000d00a  xor     r12d, r12d
0x18000d00d  mov     [rbp+60h+var_E0], r8
0x18000d011  mov     rsi, r8
0x18000d014  mov     [rbp+60h+var_D0], rdx
0x18000d018  mov     rdi, rdx
0x18000d01b  mov     [rsp+160h+var_E8], r9
0x18000d020  mov     r15, rcx
0x18000d023  mov     [rsp+160h+var_120], r12d
0x18000d028  lea     r8d, [r12+78h]; Size
0x18000d02d  xor     edx, edx; Val
0x18000d02f  lea     rcx, [rbp+60h+var_C0]; void *
0x18000d033  call    memset_0
0x18000d038  call    pagFindAndBoot
0x18000d03d  mov     [rsp+160h+var_110], rax
0x18000d042  mov     rbx, rax
0x18000d045  test    rax, rax
0x18000d048  jnz     short loc_18000D052
0x18000d04a  lea     eax, [rbx+1]
0x18000d04d  jmp     loc_18000D133
0x18000d052  mov     edx, 4
0x18000d057  mov     rcx, rdi
0x18000d05a  call    ValidateWritePointer
0x18000d05f  test    eax, eax
0x18000d061  jz      loc_18000D12E
0x18000d067  cmp     dword ptr [rdi], 11Ch
0x18000d06d  jb      loc_18000D12E
0x18000d073  mov     edx, [rdi]
0x18000d075  mov     rcx, rdi
0x18000d078  call    ValidateWritePointer
0x18000d07d  test    eax, eax
0x18000d07f  jz      loc_18000D12E
0x18000d085  test    r15, r15
0x18000d088  jz      short loc_18000D0A5
0x18000d08a  mov     edx, 2
0x18000d08f  mov     rcx, r15
0x18000d092  call    ValidateHandle
0x18000d097  test    eax, eax
0x18000d099  jnz     short loc_18000D0A5
0x18000d09b  mov     eax, 5
0x18000d0a0  jmp     loc_18000D133
0x18000d0a5  test    rsi, rsi
0x18000d0a8  jz      loc_18000D12E
0x18000d0ae  mov     r13d, [rbp+60h+fdwEnum]
0x18000d0b5  test    r13d, 0FE00FFFFh
0x18000d0bc  jnz     loc_18000D6A9
0x18000d0c2  mov     r14d, r13d
0x18000d0c5  and     r14d, 400000h
0x18000d0cc  jz      short loc_18000D0DB
0x18000d0ce  test    r13d, 1800000h
0x18000d0d5  jz      loc_18000D6A9
0x18000d0db  lea     r8, [rsp+160h+var_120]
0x18000d0e0  mov     rdx, r15
0x18000d0e3  mov     rcx, rbx
0x18000d0e6  call    IMetricsMaxSizeFormat
0x18000d0eb  test    eax, eax
0x18000d0ed  jnz     short loc_18000D133
0x18000d0ef  mov     edx, [rdi+18h]
0x18000d0f2  cmp     edx, [rsp+160h+var_120]
0x18000d0f6  jb      short loc_18000D12E
0x18000d0f8  mov     rcx, [rdi+10h]
0x18000d0fc  call    ValidateWritePointer
0x18000d101  test    eax, eax
0x18000d103  jz      short loc_18000D12E
0x18000d105  cmp     [rdi+0Ch], r12d
0x18000d109  jnz     short loc_18000D12E
0x18000d10b  mov     esi, 1
0x18000d110  bt      r13d, 10h
0x18000d115  jnb     short loc_18000D15A
0x18000d117  mov     rax, [rdi+10h]
0x18000d11b  movzx   ecx, word ptr [rax]
0x18000d11e  mov     [rsp+160h+var_120], ecx
0x18000d122  test    ecx, ecx
0x18000d124  jz      short loc_18000D12E
0x18000d126  mov     r12d, esi
0x18000d129  cmp     [rdi+8], ecx
0x18000d12c  jz      short loc_18000D15F
0x18000d12e  mov     eax, 0Bh
0x18000d133  mov     rcx, [rbp+60h+var_40]
0x18000d137  xor     rcx, rsp; StackCookie
0x18000d13a  call    __security_check_cookie
0x18000d13f  mov     rbx, [rsp+160h+arg_10]
0x18000d147  add     rsp, 130h
0x18000d14e  pop     r15
0x18000d150  pop     r14
0x18000d152  pop     r13
0x18000d154  pop     r12
0x18000d156  pop     rdi
0x18000d157  pop     rsi
0x18000d158  pop     rbp
0x18000d159  retn
0x18000d15a  mov     [rsp+160h+var_120], r12d
0x18000d15f  mov     eax, r13d
0x18000d162  mov     ecx, r13d
0x18000d165  and     eax, 100000h
0x18000d16a  and     ecx, 200000h
0x18000d170  mov     [rsp+160h+var_118], eax
0x18000d174  mov     [rsp+160h+var_11C], ecx
0x18000d178  test    eax, eax
0x18000d17a  jnz     short loc_18000D185
0x18000d17c  test    ecx, ecx
0x18000d17e  jnz     short loc_18000D185
0x18000d180  lea     ebx, [rax+10h]
0x18000d183  jmp     short loc_18000D1B5
0x18000d185  mov     rcx, [rdi+10h]
0x18000d189  cmp     si, [rcx]
0x18000d18c  jnz     short loc_18000D195
0x18000d18e  mov     ebx, 10h
0x18000d193  jmp     short loc_18000D19D
0x18000d195  movzx   ebx, word ptr [rcx+10h]
0x18000d199  add     rbx, 12h
0x18000d19d  call    ValidateReadWaveFormat
0x18000d1a2  test    eax, eax
0x18000d1a4  jz      short loc_18000D12E
0x18000d1a6  mov     rcx, [rdi+10h]
0x18000d1aa  xor     eax, eax
0x18000d1ac  cmp     ax, [rcx]
0x18000d1af  jz      loc_18000D12E
0x18000d1b5  mov     rdx, rbx; dwBytes
0x18000d1b8  mov     ecx, 42h ; 'B'; uFlags
0x18000d1bd  call    cs:__imp_GlobalAlloc
0x18000d1c3  mov     rcx, rax; hMem
0x18000d1c6  call    cs:__imp_GlobalLock
0x18000d1cc  mov     [rsp+160h+pMem], rax
0x18000d1d1  test    rax, rax
0x18000d1d4  jnz     short loc_18000D1E0
0x18000d1d6  mov     eax, 7
0x18000d1db  jmp     loc_18000D133
0x18000d1e0  mov     rdx, [rdi+10h]; Src
0x18000d1e4  mov     r8, rbx; Size
0x18000d1e7  mov     rcx, rax; void *
0x18000d1ea  call    memcpy_0
0x18000d1ef  xor     ebx, ebx
0x18000d1f1  mov     [rsp+160h+hDriver], rbx
0x18000d1f6  test    r14d, r14d
0x18000d1f9  jz      short loc_18000D217
0x18000d1fb  xor     r8d, r8d; lParam2
0x18000d1fe  lea     rdx, gszSecDriversW; "Drivers32"
0x18000d205  lea     rcx, gszWavemapper; "wavemapper"
0x18000d20c  call    cs:__imp_OpenDriver
0x18000d212  mov     [rsp+160h+hDriver], rax
0x18000d217  test    r15, r15
0x18000d21a  jz      loc_18000D30E
0x18000d220  mov     r13, [r15+14h]
0x18000d224  xor     r14d, r14d
0x18000d227  cmp     r14d, [r13+40h]
0x18000d22b  jnb     loc_18000D2C6
0x18000d231  test    r12d, r12d
0x18000d234  jz      short loc_18000D244
0x18000d236  mov     rax, [r13+44h]
0x18000d23a  mov     edx, [rsp+160h+var_120]
0x18000d23e  cmp     edx, [rax+r14*8]
0x18000d242  jnz     short loc_18000D2BC
0x18000d244  mov     rcx, [rsp+160h+var_110]
0x18000d249  lea     r8, [rbp+60h+var_C0]
0x18000d24d  xor     r9d, r9d
0x18000d250  mov     [rbp+60h+var_C0], 78h ; 'x'
0x18000d257  mov     rdx, r13
0x18000d25a  mov     [rbp+60h+var_BC], r14d
0x18000d25e  call    IFormatTagDetails
0x18000d263  mov     ebx, eax
0x18000d265  test    eax, eax
0x18000d267  jnz     short loc_18000D2B3
0x18000d269  lea     r8, [rbp+60h+var_C0]
0x18000d26d  mov     eax, [rbp+60h+fdwEnum]
0x18000d273  mov     r9, rdi
0x18000d276  mov     rcx, [rsp+160h+hDriver]; hDriver
0x18000d27b  mov     rdx, r15; had
0x18000d27e  mov     [rsp+160h+var_128], eax; int
0x18000d282  mov     rax, [rsp+160h+pMem]
0x18000d287  mov     [rsp+160h+pwfxSrc], rax; pwfxSrc
0x18000d28c  mov     rax, [rsp+160h+var_E8]
0x18000d291  mov     [rsp+160h+var_138], rax; __int64
0x18000d296  mov     rax, [rbp+60h+var_E0]
0x18000d29a  mov     [rsp+160h+var_140], rax; __int64
0x18000d29f  cmp     [rsp+160h+var_11C], ebx
0x18000d2a3  jz      short loc_18000D2AC
0x18000d2a5  call    ISuggestEnum
0x18000d2aa  jmp     short loc_18000D2B1
0x18000d2ac  call    IFormatEnum
0x18000d2b1  mov     ebx, eax
0x18000d2b3  cmp     ebx, esi
0x18000d2b5  jz      short loc_18000D2C4
0x18000d2b7  test    r12d, r12d
0x18000d2ba  jnz     short loc_18000D2C4
0x18000d2bc  add     r14d, esi
0x18000d2bf  jmp     loc_18000D227
0x18000d2c4  xor     ebx, ebx
0x18000d2c6  mov     rsi, [rsp+160h+pMem]
0x18000d2cb  mov     rax, [rsp+160h+hDriver]
0x18000d2d0  test    rax, rax
0x18000d2d3  jz      short loc_18000D2E3
0x18000d2d5  xor     r8d, r8d; lParam2
0x18000d2d8  xor     edx, edx; lParam1
0x18000d2da  mov     rcx, rax; hDriver
0x18000d2dd  call    cs:__imp_CloseDriver
0x18000d2e3  mov     rcx, rsi; pMem
0x18000d2e6  call    cs:__imp_GlobalHandle
0x18000d2ec  mov     rcx, rax; hMem
0x18000d2ef  call    cs:__imp_GlobalUnlock
0x18000d2f5  mov     rcx, rsi; pMem
0x18000d2f8  call    cs:__imp_GlobalHandle
0x18000d2fe  mov     rcx, rax; hMem
0x18000d301  call    cs:__imp_GlobalFree
0x18000d307  mov     eax, ebx
0x18000d309  jmp     loc_18000D133
0x18000d30e  test    r12d, r12d
0x18000d311  jz      loc_18000D4D5
0x18000d317  mov     dword ptr [rsp+160h+phad], ebx
0x18000d31b  mov     [rsp+160h+hadid], rbx
0x18000d320  cmp     [rsp+160h+var_118], ebx
0x18000d324  jnz     short loc_18000D331
0x18000d326  cmp     [rsp+160h+var_11C], ebx
0x18000d32a  jnz     short loc_18000D331
0x18000d32c  mov     r15d, esi
0x18000d32f  jmp     short loc_18000D334
0x18000d331  xor     r15d, r15d
0x18000d334  mov     r14, [rsp+160h+var_110]
0x18000d339  xor     r12d, r12d
0x18000d33c  lea     rax, [r14+80h]
0x18000d343  mov     rcx, rax; lpCriticalSection
0x18000d346  mov     [rbp+60h+var_D8], rax
0x18000d34a  call    AcquireLockShared
0x18000d34f  mov     rcx, r14
0x18000d352  call    threadEnterListShared
0x18000d357  xor     r9d, r9d
0x18000d35a  lea     rdx, [rsp+160h+hadid]
0x18000d35f  xor     r8d, r8d
0x18000d362  mov     rcx, r14
0x18000d365  call    IDriverGetNext
0x18000d36a  test    eax, eax
0x18000d36c  jnz     loc_18000D4BA
0x18000d372  mov     edi, ebx
0x18000d374  mov     r13, [rsp+160h+hadid]
0x18000d379  xor     r15d, r15d
0x18000d37c  mov     edx, [rsp+160h+var_120]
0x18000d380  xor     r14d, r14d
0x18000d383  cmp     r14d, [r13+40h]
0x18000d387  jnb     short loc_18000D3D4
0x18000d389  mov     rax, [r13+44h]
0x18000d38d  cmp     edx, [rax+r14*8]
0x18000d391  jz      short loc_18000D398
0x18000d393  add     r14d, esi
0x18000d396  jmp     short loc_18000D383
0x18000d398  mov     rcx, [rsp+160h+var_110]
0x18000d39d  lea     r8, [rbp+60h+var_C0]
0x18000d3a1  xor     r9d, r9d
0x18000d3a4  mov     [rbp+60h+var_C0], 78h ; 'x'
0x18000d3ab  mov     rdx, r13
0x18000d3ae  mov     [rbp+60h+var_BC], r14d
0x18000d3b2  call    IFormatTagDetails
0x18000d3b7  mov     ebx, eax
0x18000d3b9  test    eax, eax
0x18000d3bb  jnz     short loc_18000D3D4
0x18000d3bd  test    r12, r12
0x18000d3c0  jz      short loc_18000D3C7
0x18000d3c2  cmp     [rbp+60h+var_AC], edi
0x18000d3c5  jbe     short loc_18000D3D4
0x18000d3c7  mov     edi, [rbp+60h+var_AC]
0x18000d3ca  mov     r12, r13
0x18000d3cd  mov     dword ptr [rsp+160h+phad], r14d
0x18000d3d2  jmp     short loc_18000D3D9
0x18000d3d4  mov     r14d, dword ptr [rsp+160h+phad]
0x18000d3d9  mov     rcx, [rsp+160h+var_110]
0x18000d3de  lea     rdx, [rsp+160h+hadid]
0x18000d3e3  xor     r9d, r9d
0x18000d3e6  mov     r8, r13
0x18000d3e9  call    IDriverGetNext
0x18000d3ee  test    eax, eax
0x18000d3f0  jz      short loc_18000D374
0x18000d3f2  mov     rdi, [rbp+60h+var_D0]
0x18000d3f6  test    r12, r12
0x18000d3f9  jz      loc_18000D659
0x18000d3ff  mov     [rbp+60h+var_BC], r14d
0x18000d403  lea     r8, [rbp+60h+var_C0]
0x18000d407  mov     r14, [rsp+160h+var_110]
0x18000d40c  xor     r9d, r9d
0x18000d40f  mov     rcx, r14
0x18000d412  mov     [rsp+160h+hadid], r15
0x18000d417  mov     rdx, r12
0x18000d41a  mov     [rbp+60h+var_C0], 78h ; 'x'
0x18000d421  call    IFormatTagDetails
0x18000d426  mov     ebx, eax
0x18000d428  test    eax, eax
0x18000d42a  jnz     loc_18000D65E
0x18000d430  xor     r8d, r8d; fdwOpen
0x18000d433  lea     rcx, [rsp+160h+hadid]; phad
0x18000d438  mov     rdx, r12; hadid
  ... truncated ...
```
