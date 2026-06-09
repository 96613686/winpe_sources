# acmStreamOpen

- ea: `0x180002e70`
- end: `0x1800034da`
- name: `acmStreamOpen`
- size: `1642`
- prototype: `MMRESULT __stdcall(LPHACMSTREAM phas, HACMDRIVER had, LPWAVEFORMATEX pwfxSrc, LPWAVEFORMATEX pwfxDst, LPWAVEFILTER pwfltr, DWORD_PTR dwCallback, DWORD_PTR dwInstance, DWORD fdwOpen)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x18000c434`

## callees

- `0x1800017f0`
- `0x180001e60`
- `0x1800021e0`
- `0x180002a80`
- `0x180002b00`
- `0x180002e70`
- `0x1800034e0`
- `0x180003e80`
- `0x180003ec0`
- `0x180003f40`
- `0x180004ab0`
- `0x180004af0`
- `0x180005530`
- `0x180005700`
- `0x180009270`
- `0x180009afa`
- `0x1800124c8`
- `0x1800126b9`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000339e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000339e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003305`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003344`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000336a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000345d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003305`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003344`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000336a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000345d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000316d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000331c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003356`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003439`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800034bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000316d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000331c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003356`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003439`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800034bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800031e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800031e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031f0`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800033ec`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800033ec`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x180003215`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x180003215`

## pseudocode

```c
MMRESULT __stdcall acmStreamOpen(
        LPHACMSTREAM phas,
        HACMDRIVER had,
        LPWAVEFORMATEX pwfxSrc,
        LPWAVEFORMATEX pwfxDst,
        LPWAVEFILTER pwfltr,
        DWORD_PTR dwCallback,
        DWORD_PTR dwInstance,
        DWORD fdwOpen)
{
  int v8; // r12d
  WORD *p_wFormatTag; // rdi
  HACMDRIVER v10; // r15
  MMRESULT v12; // r14d
  LPWAVEFORMATEX v13; // rbx
  __int64 v14; // rsi
  int v15; // ebp
  int v16; // ebp
  WORD wFormatTag; // ax
  int v18; // ebp
  unsigned int v19; // ebp
  size_t v20; // rdi
  DWORD cbStruct; // esi
  int v22; // eax
  __int64 v23; // rcx
  __int64 v25; // rax
  __int64 v26; // rbx
  void *v27; // rdx
  void *v28; // rcx
  __int64 (__fastcall *v29)(_QWORD, _QWORD, __int64, __int64, _QWORD); // rax
  _QWORD *v30; // rax
  HDRVR v31; // rcx
  DWORD v32; // edi
  HACMDRIVER v33; // rbx
  __int64 CurrentThreadId; // rax
  int v35; // ecx
  int v36; // edi
  int v37; // edi
  __int64 v38; // rax
  MMRESULT v39; // edi
  void *v40; // rcx
  __int64 v41; // rbx
  int v42; // [rsp+30h] [rbp-118h]
  DWORD v43; // [rsp+38h] [rbp-110h]
  HACMDRIVER v45; // [rsp+50h] [rbp-F8h] BYREF
  void *Src; // [rsp+58h] [rbp-F0h]
  __int64 v47; // [rsp+60h] [rbp-E8h]
  LPHACMSTREAM v48; // [rsp+68h] [rbp-E0h]
  struct tACMFORMATTAGDETAILSW paftd; // [rsp+70h] [rbp-D8h] BYREF

  v8 = 0;
  p_wFormatTag = &pwfxSrc->wFormatTag;
  Src = pwfxSrc;
  v10 = had;
  v48 = phas;
  v45 = had;
  if ( phas )
  {
    if ( !(unsigned int)ValidateWritePointer(phas, 8) )
      return 11;
    *phas = 0;
  }
  if ( (fdwOpen & 0xFFF8FFF8) != 0 )
    return 10;
  v12 = 1;
  if ( (fdwOpen & 1) != 0 )
  {
    v42 = 1;
    v48 = 0;
  }
  else
  {
    v42 = 0;
    if ( !phas && !(unsigned int)ValidateWritePointer(0, 8) )
      return 11;
  }
  if ( !(unsigned int)ValidateReadWaveFormat(p_wFormatTag) )
    return 11;
  v13 = pwfxDst;
  if ( !(unsigned int)ValidateReadWaveFormat(pwfxDst) )
    return 11;
  v47 = pagFindAndBoot();
  v14 = v47;
  if ( !v47 )
    return v12;
  if ( (fdwOpen & 2) != 0 )
  {
    v15 = 1;
  }
  else
  {
    if ( dwCallback )
      return 11;
    v15 = 0;
    if ( dwInstance )
      return 11;
  }
  if ( (HIWORD(fdwOpen) & 7) == 1 )
  {
    if ( !IsWindow((HWND)dwCallback) )
      return 11;
  }
  else if ( (HIWORD(fdwOpen) & 7) == 3 && !dwCallback )
  {
    return 11;
  }
  v16 = 16 * v15;
  LOBYTE(v8) = v10 != 0;
  if ( !pwfltr )
  {
    wFormatTag = *p_wFormatTag;
    if ( *p_wFormatTag == pwfxDst->wFormatTag )
    {
      v18 = v16 | 2;
    }
    else
    {
      v18 = v16 | 1;
      if ( wFormatTag == 1 )
        wFormatTag = pwfxDst->wFormatTag;
    }
    goto LABEL_17;
  }
  if ( !(unsigned int)ValidateReadWaveFilter(pwfltr) )
    return 11;
  v38 = *(_QWORD *)p_wFormatTag - *(_QWORD *)&pwfxDst->wFormatTag;
  if ( *(_QWORD *)p_wFormatTag == *(_QWORD *)&pwfxDst->wFormatTag )
    v38 = *((_QWORD *)p_wFormatTag + 1) - *(_QWORD *)&pwfxDst->nAvgBytesPerSec;
  if ( v38 )
    return 512;
  wFormatTag = *p_wFormatTag;
  v18 = v16 | 4;
LABEL_17:
  if ( !v10 )
  {
    v32 = wFormatTag;
    v43 = wFormatTag;
    v33 = 0;
    AcquireLockShared((LPCRITICAL_SECTION)(v47 + 128));
    threadEnterListShared(v47);
    while ( !v33 )
    {
      v33 = *(HACMDRIVER *)(v14 + 96);
      CurrentThreadId = GetCurrentThreadId();
      while ( 1 )
      {
LABEL_61:
        while ( !v33 )
        {
          if ( !CurrentThreadId )
            goto LABEL_37;
          v33 = *(HACMDRIVER *)(v14 + 96);
          CurrentThreadId = 0;
        }
        if ( *(_QWORD *)(v33 + 9) == CurrentThreadId )
        {
          v35 = *((_DWORD *)v33 + 14);
          if ( (v35 & 0x10000000) == 0 && v35 >= 0 && !*((_DWORD *)v33 + 3) )
            break;
        }
        v33 = *(HACMDRIVER *)(v33 + 5);
      }
      memset_0(&paftd, 0, sizeof(paftd));
      if ( v18 == (v18 & (_DWORD)v33[15]) )
      {
        paftd.cbStruct = 120;
        paftd.dwFormatTag = v32;
        paftd.fdwSupport = 0;
        if ( !acmFormatTagDetailsW(v33, &paftd, 1u) && v18 == (v18 & paftd.fdwSupport) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)v33 - 1);
          v36 = IDriverOpen((__int64 *)&v45, (__int64)v33, 0);
          LeaveCriticalSection((LPCRITICAL_SECTION)v33 - 1);
          v10 = v45;
          if ( v36 )
          {
            v32 = v43;
          }
          else
          {
            EnterCriticalSection((LPCRITICAL_SECTION)v45 - 1);
            v37 = IStreamOpenQuery((_DWORD)v10, (_DWORD)Src, (_DWORD)pwfxDst, (_DWORD)pwfltr, fdwOpen);
            LeaveCriticalSection((LPCRITICAL_SECTION)v10 - 1);
            if ( !v37 )
            {
              v14 = v47;
              goto LABEL_37;
            }
            EnterCriticalSection((LPCRITICAL_SECTION)v33 - 1);
            IDriverClose(v10, 0);
            LeaveCriticalSection((LPCRITICAL_SECTION)v33 - 1);
            v14 = v47;
            v10 = 0;
            v32 = v43;
            v45 = 0;
          }
        }
      }
    }
    if ( v14 == *(_QWORD *)(v33 + 1) )
    {
      CurrentThreadId = *(_QWORD *)(v33 + 9);
      v33 = *(HACMDRIVER *)(v33 + 5);
      goto LABEL_61;
    }
LABEL_37:
    threadLeaveListShared(v14);
    ReleaseLock(v14 + 128);
    if ( v10 )
    {
      if ( !v42 )
      {
        p_wFormatTag = (WORD *)Src;
        v13 = pwfxDst;
LABEL_21:
        v19 = 16;
        if ( *p_wFormatTag == 1 )
          v20 = 16;
        else
          v20 = (unsigned int)p_wFormatTag[8] + 18;
        if ( v13->wFormatTag != 1 )
          v19 = v13->cbSize + 18;
        if ( pwfltr )
          cbStruct = pwfltr->cbStruct;
        else
          cbStruct = 0;
        v22 = v20 + 96;
        if ( (unsigned int)v20 < 0xFFFFFFA0
          && v22 + v19 >= v19
          && (v23 = cbStruct + v22 + v19, (unsigned int)v23 >= cbStruct)
          && (v25 = NewHandle(v23), (v26 = v25) != 0) )
        {
          *(_QWORD *)(v25 + 32) = v25 + 96;
          *(_DWORD *)v25 = 3;
          *(_DWORD *)(v25 + 4) = v8;
          *(_QWORD *)(v25 + 16) = v10;
          *(_DWORD *)(v25 + 28) = 68;
          *(_QWORD *)(v25 + 40) = v25 + v20 + 96;
          if ( pwfltr )
          {
            v40 = (void *)(v25 + v20 + v19 + 96LL);
            *(_QWORD *)(v25 + 48) = v40;
            memcpy_0(v40, pwfltr, cbStruct);
          }
          v27 = Src;
          v28 = *(void **)(v26 + 32);
          *(_QWORD *)(v26 + 56) = dwCallback;
          *(_QWORD *)(v26 + 64) = dwInstance;
          *(_DWORD *)(v26 + 72) = fdwOpen;
          *(_QWORD *)(v26 + 88) = v26;
          memcpy_0(v28, v27, v20);
          memcpy_0(*(void **)(v26 + 40), pwfxDst, v19);
          EnterCriticalSection((LPCRITICAL_SECTION)v10 - 1);
          v29 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64, _QWORD))*((_QWORD *)v10 + 6);
          if ( v29 )
          {
            if ( v29 != (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64, _QWORD))-1LL )
              v12 = v29(*((_QWORD *)v10 + 7), *(_QWORD *)(v10 + 5), 24652, v26 + 28, 0);
          }
          else
          {
            v31 = (HDRVR)*((_QWORD *)v10 + 5);
            if ( v31 )
              v12 = SendDriverMessage(v31, 0x604Cu, v26 + 28, 0);
            else
              v12 = 5;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)v10 - 1);
          if ( !v12 )
          {
            *(_QWORD *)(v26 + 8) = *(_QWORD *)(v10 + 3);
            v30 = v48;
            *(_QWORD *)(v10 + 3) = v26;
            *v30 = v26;
            return 0;
          }
          *(_DWORD *)v26 = 666;
          DeleteCriticalSection((LPCRITICAL_SECTION)(v26 - 40));
          LocalFree((HLOCAL)(v26 - 40));
        }
        else
        {
          v12 = 7;
        }
        goto LABEL_31;
      }
LABEL_77:
      v12 = 0;
LABEL_31:
      if ( !v8 )
      {
        v41 = *(_QWORD *)(v10 + 5);
        EnterCriticalSection((LPCRITICAL_SECTION)(v41 - 40));
        IDriverClose(v10, 0);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v41 - 40));
      }
      return v12;
    }
    return 512;
  }
  if ( !(unsigned int)ValidateHandle(v10, 2) )
    return 5;
  if ( v18 != (v18 & *(_DWORD *)(*(_QWORD *)(v10 + 5) + 60LL)) )
    return 512;
  if ( !v42 )
    goto LABEL_21;
  EnterCriticalSection((LPCRITICAL_SECTION)v10 - 1);
  v39 = IStreamOpenQuery((_DWORD)v10, (_DWORD)p_wFormatTag, (_DWORD)pwfxDst, (_DWORD)pwfltr, fdwOpen);
  LeaveCriticalSection((LPCRITICAL_SECTION)v10 - 1);
  if ( !v39 )
    goto LABEL_77;
  return v39;
}

```

## disassembly

```asm
0x180002e70  push    rbx
0x180002e72  push    rbp
0x180002e73  push    rsi
0x180002e74  push    rdi
0x180002e75  push    r12
0x180002e77  push    r13
0x180002e79  push    r14
0x180002e7b  push    r15
0x180002e7d  sub     rsp, 108h
0x180002e84  mov     rax, cs:__security_cookie
0x180002e8b  xor     rax, rsp
0x180002e8e  mov     [rsp+148h+var_58], rax
0x180002e96  mov     rax, [rsp+148h+pwfltr]
0x180002e9e  xor     r12d, r12d
0x180002ea1  mov     [rsp+148h+var_100], r9
0x180002ea6  mov     rdi, r8
0x180002ea9  mov     [rsp+148h+Src], r8
0x180002eae  mov     r15, rdx
0x180002eb1  mov     [rsp+148h+var_E0], rcx
0x180002eb6  mov     rbx, rcx
0x180002eb9  mov     [rsp+148h+var_108], rax
0x180002ebe  mov     [rsp+148h+var_F8], rdx
0x180002ec3  test    rcx, rcx
0x180002ec6  jnz     loc_18000304E
0x180002ecc  mov     r13d, [rsp+148h+fdwOpen]
0x180002ed4  test    r13d, 0FFF8FFF8h
0x180002edb  jnz     loc_180003220
0x180002ee1  mov     r14d, 1
0x180002ee7  test    r14b, r13b
0x180002eea  jnz     loc_1800030BB
0x180002ef0  mov     [rsp+148h+var_118], r12d
0x180002ef5  test    rbx, rbx
0x180002ef8  jz      loc_1800033C3
0x180002efe  mov     rcx, rdi
0x180002f01  call    ValidateReadWaveFormat
0x180002f06  test    eax, eax
0x180002f08  jz      loc_1800033D7
0x180002f0e  mov     rbx, [rsp+148h+var_100]
0x180002f13  mov     rcx, rbx
0x180002f16  call    ValidateReadWaveFormat
0x180002f1b  test    eax, eax
0x180002f1d  jz      loc_1800033D7
0x180002f23  call    pagFindAndBoot
0x180002f28  mov     [rsp+148h+var_E8], rax
0x180002f2d  mov     rsi, rax
0x180002f30  test    rax, rax
0x180002f33  jz      loc_180003049
0x180002f39  mov     rcx, [rsp+148h+dwCallback]; hWnd
0x180002f41  test    r13b, 2
0x180002f45  jnz     loc_1800030CA
0x180002f4b  test    rcx, rcx
0x180002f4e  jnz     loc_1800033D7
0x180002f54  mov     ebp, r12d
0x180002f57  cmp     [rsp+148h+dwInstance], rbp
0x180002f5f  jnz     loc_1800033D7
0x180002f65  mov     eax, r13d
0x180002f68  shr     eax, 10h
0x180002f6b  and     eax, 7
0x180002f6e  sub     eax, r14d
0x180002f71  jz      loc_1800033EC
0x180002f77  cmp     eax, 2
0x180002f7a  jz      loc_1800033E1
0x180002f80  mov     rax, [rsp+148h+var_108]
0x180002f85  shl     ebp, 4
0x180002f88  test    r15, r15
0x180002f8b  setnz   r12b
0x180002f8f  mov     [rsp+148h+var_114], r12d
0x180002f94  test    rax, rax
0x180002f97  jnz     loc_1800033FB
0x180002f9d  movzx   ecx, word ptr [rbx]
0x180002fa0  movzx   eax, word ptr [rdi]
0x180002fa3  cmp     ax, cx
0x180002fa6  jz      loc_1800030B3
0x180002fac  or      ebp, r14d
0x180002faf  cmp     r14w, ax
0x180002fb3  cmovz   ax, cx
0x180002fb7  test    r15, r15
0x180002fba  jz      loc_18000322A
0x180002fc0  mov     edx, 2
0x180002fc5  mov     rcx, r15
0x180002fc8  call    ValidateHandle
0x180002fcd  test    eax, eax
0x180002fcf  jz      loc_18000342B
0x180002fd5  mov     rax, [r15+14h]
0x180002fd9  mov     ecx, [rax+3Ch]
0x180002fdc  and     ecx, ebp
0x180002fde  cmp     ebp, ecx
0x180002fe0  jnz     loc_18000308A
0x180002fe6  cmp     [rsp+148h+var_118], 0
0x180002feb  jnz     loc_180003435
0x180002ff1  mov     ebp, 10h
0x180002ff6  cmp     r14w, [rdi]
0x180002ffa  jz      loc_1800030D2
0x180003000  movzx   edi, word ptr [rdi+10h]
0x180003004  add     edi, 12h
0x180003007  cmp     r14w, [rbx]
0x18000300b  jnz     loc_18000348A
0x180003011  mov     rax, [rsp+148h+var_108]
0x180003016  test    rax, rax
0x180003019  jnz     loc_1800030D9
0x18000301f  xor     esi, esi
0x180003021  lea     eax, [rdi+60h]
0x180003024  cmp     eax, 60h ; '`'
0x180003027  jb      short loc_18000303A
0x180003029  lea     ecx, [rax+rbp]
0x18000302c  cmp     ecx, ebp
0x18000302e  jb      short loc_18000303A
0x180003030  add     ecx, esi
0x180003032  cmp     ecx, esi
0x180003034  jnb     loc_1800030E0
0x18000303a  mov     r14d, 7
0x180003040  test    r12d, r12d
0x180003043  jz      loc_1800034B3
0x180003049  mov     eax, r14d
0x18000304c  jmp     short loc_18000308F
0x18000304e  mov     edx, 8
0x180003053  call    ValidateWritePointer
0x180003058  test    eax, eax
0x18000305a  jz      loc_1800033D7
0x180003060  mov     [rbx], r12
0x180003063  jmp     loc_180002ECC
0x180003068  mov     rsi, [rsp+148h+var_E8]
0x18000306d  mov     rcx, rsi
0x180003070  call    threadLeaveListShared
0x180003075  lea     rcx, [rsi+80h]
0x18000307c  call    ReleaseLock
0x180003081  test    r15, r15
0x180003084  jnz     loc_1800033AB
0x18000308a  mov     eax, 200h
0x18000308f  mov     rcx, [rsp+148h+var_58]
0x180003097  xor     rcx, rsp; StackCookie
0x18000309a  call    __security_check_cookie
0x18000309f  add     rsp, 108h
0x1800030a6  pop     r15
0x1800030a8  pop     r14
0x1800030aa  pop     r13
0x1800030ac  pop     r12
0x1800030ae  pop     rdi
0x1800030af  pop     rsi
0x1800030b0  pop     rbp
0x1800030b1  pop     rbx
0x1800030b2  retn
0x1800030b3  or      ebp, 2
0x1800030b6  jmp     loc_180002FB7
0x1800030bb  mov     [rsp+148h+var_118], r14d
0x1800030c0  mov     [rsp+148h+var_E0], r12
0x1800030c5  jmp     loc_180002EFE
0x1800030ca  mov     ebp, r14d
0x1800030cd  jmp     loc_180002F65
0x1800030d2  mov     edi, ebp
0x1800030d4  jmp     loc_180003007
0x1800030d9  mov     esi, [rax]
0x1800030db  jmp     loc_180003021
0x1800030e0  call    NewHandle
0x1800030e5  mov     rbx, rax
0x1800030e8  test    rax, rax
0x1800030eb  jz      loc_18000303A
0x1800030f1  mov     rdx, [rsp+148h+var_108]; Src
0x1800030f6  lea     rcx, [rax+60h]
0x1800030fa  mov     [rax+20h], rcx
0x1800030fe  lea     rcx, [rdi+60h]
0x180003102  add     rcx, rax
0x180003105  mov     dword ptr [rax], 3
0x18000310b  mov     [rax+4], r12d
0x18000310f  mov     [rax+10h], r15
0x180003113  mov     dword ptr [rax+1Ch], 44h ; 'D'
0x18000311a  mov     [rax+28h], rcx
0x18000311e  test    rdx, rdx
0x180003121  jnz     loc_180003496
0x180003127  mov     rax, [rsp+148h+dwCallback]
0x18000312f  mov     r8, rdi; Size
0x180003132  mov     rdx, [rsp+148h+Src]; Src
0x180003137  mov     rcx, [rbx+20h]; void *
0x18000313b  mov     [rbx+38h], rax
0x18000313f  mov     rax, [rsp+148h+dwInstance]
0x180003147  mov     [rbx+40h], rax
0x18000314b  mov     [rbx+48h], r13d
0x18000314f  mov     [rbx+58h], rbx
0x180003153  call    memcpy_0
0x180003158  mov     rdx, [rsp+148h+var_100]; Src
0x18000315d  mov     rcx, [rbx+28h]; void *
0x180003161  mov     r8d, ebp; Size
0x180003164  call    memcpy_0
0x180003169  lea     rcx, [r15-28h]; lpCriticalSection
0x18000316d  call    cs:__imp_EnterCriticalSection
0x180003173  test    r15, r15
0x180003176  jz      short loc_1800031AC
0x180003178  mov     rax, [r15+30h]
0x18000317c  test    rax, rax
0x18000317f  jz      short loc_180003200
0x180003181  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003185  jz      short loc_1800031B2
0x180003187  mov     rdx, [r15+14h]
0x18000318b  lea     r9, [rbx+1Ch]
0x18000318f  mov     rcx, [r15+38h]
0x180003193  mov     r8d, 604Ch
0x180003199  mov     [rsp+148h+var_128], 0
0x1800031a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a7  mov     r14, rax
0x1800031aa  jmp     short loc_1800031B2
0x1800031ac  mov     r14d, 5
0x1800031b2  lea     rcx, [r15-28h]; lpCriticalSection
0x1800031b6  call    cs:__imp_LeaveCriticalSection
0x1800031bc  test    r14d, r14d
0x1800031bf  jnz     short loc_1800031DC
0x1800031c1  mov     rax, [r15+0Ch]
0x1800031c5  mov     [rbx+8], rax
0x1800031c9  mov     rax, [rsp+148h+var_E0]
0x1800031ce  mov     [r15+0Ch], rbx
0x1800031d2  mov     [rax], rbx
0x1800031d5  xor     eax, eax
0x1800031d7  jmp     loc_18000308F
0x1800031dc  lea     rcx, [rbx-28h]; lpCriticalSection
0x1800031e0  mov     dword ptr [rbx], 29Ah
0x1800031e6  call    cs:__imp_DeleteCriticalSection
0x1800031ec  lea     rcx, [rbx-28h]; hMem
0x1800031f0  call    cs:__imp_LocalFree
0x1800031f6  mov     r12d, [rsp+148h+var_114]
0x1800031fb  jmp     loc_180003040
0x180003200  mov     rcx, [r15+28h]; hDriver
0x180003204  test    rcx, rcx
0x180003207  jz      short loc_1800031AC
0x180003209  xor     r9d, r9d; lParam2
0x18000320c  lea     r8, [rbx+1Ch]; lParam1
0x180003210  mov     edx, 604Ch; message
0x180003215  call    cs:__imp_SendDriverMessage
0x18000321b  mov     r14, rax
0x18000321e  jmp     short loc_1800031B2
0x180003220  mov     eax, 0Ah
0x180003225  jmp     loc_18000308F
0x18000322a  movzx   edi, ax
0x18000322d  lea     rcx, [rsi+80h]; lpCriticalSection
0x180003234  mov     [rsp+148h+var_110], edi
0x180003238  xor     ebx, ebx
0x18000323a  call    AcquireLockShared
0x18000323f  mov     rcx, rsi
0x180003242  call    threadEnterListShared
0x180003247  test    rbx, rbx
0x18000324a  jz      loc_18000339A
0x180003250  cmp     rsi, [rbx+4]
0x180003254  jnz     loc_18000306D
0x18000325a  mov     rax, [rbx+24h]
0x18000325e  mov     rbx, [rbx+14h]
0x180003262  test    rbx, rbx
0x180003265  jz      loc_180003386
0x18000326b  cmp     [rbx+24h], rax
0x18000326f  jz      short loc_180003277
0x180003271  mov     rbx, [rbx+14h]
0x180003275  jmp     short loc_180003262
0x180003277  mov     ecx, [rbx+38h]
0x18000327a  bt      ecx, 1Ch
0x18000327e  jb      short loc_180003271
0x180003280  test    ecx, ecx
0x180003282  js      short loc_180003271
0x180003284  cmp     dword ptr [rbx+0Ch], 0
0x180003288  jnz     short loc_180003271
0x18000328a  xor     edx, edx; Val
0x18000328c  lea     rcx, [rsp+148h+paftd]; void *
0x180003291  mov     r8d, 78h ; 'x'; Size
0x180003297  call    memset_0
0x18000329c  mov     eax, [rbx+3Ch]
0x18000329f  and     eax, ebp
0x1800032a1  cmp     ebp, eax
0x1800032a3  jnz     short loc_180003247
0x1800032a5  mov     r8d, r14d; fdwDetails
0x1800032a8  mov     [rsp+148h+paftd.cbStruct], 78h ; 'x'
0x1800032b0  lea     rdx, [rsp+148h+paftd]; paftd
0x1800032b5  mov     [rsp+148h+paftd.dwFormatTag], edi
0x1800032b9  mov     rcx, rbx; had
0x1800032bc  mov     [rsp+148h+paftd.fdwSupport], 0
0x1800032c7  call    acmFormatTagDetailsW
0x1800032cc  test    eax, eax
0x1800032ce  jnz     loc_180003247
0x1800032d4  mov     eax, [rsp+148h+paftd.fdwSupport]
0x1800032db  and     eax, ebp
0x1800032dd  cmp     ebp, eax
0x1800032df  jnz     loc_180003247
0x1800032e5  lea     rcx, [rbx-28h]; lpCriticalSection
0x1800032e9  call    cs:__imp_EnterCriticalSection
0x1800032ef  xor     r8d, r8d
0x1800032f2  lea     rcx, [rsp+148h+var_F8]
0x1800032f7  mov     rdx, rbx
0x1800032fa  call    IDriverOpen
0x1800032ff  lea     rcx, [rbx-28h]; lpCriticalSection
0x180003303  mov     edi, eax
0x180003305  call    cs:__imp_LeaveCriticalSection
0x18000330b  mov     r15, [rsp+148h+var_F8]
0x180003310  test    edi, edi
0x180003312  jnz     loc_180003472
0x180003318  lea     rcx, [r15-28h]; lpCriticalSection
0x18000331c  call    cs:__imp_EnterCriticalSection
0x180003322  mov     r9, [rsp+148h+var_108]
0x180003327  mov     rcx, r15
0x18000332a  mov     r8, [rsp+148h+var_100]
0x18000332f  mov     rdx, [rsp+148h+Src]
0x180003334  mov     dword ptr [rsp+148h+var_128], r13d
0x180003339  call    IStreamOpenQuery
0x18000333e  lea     rcx, [r15-28h]; lpCriticalSection
0x180003342  mov     edi, eax
0x180003344  call    cs:__imp_LeaveCriticalSection
  ... truncated ...
```
