# acmFormatDetailsW

- ea: `0x180008160`
- end: `0x1800084b3`
- name: `acmFormatDetailsW`
- size: `851`
- prototype: `MMRESULT __stdcall(HACMDRIVER had, LPACMFORMATDETAILSW pafd, DWORD fdwDetails)`
- caller_count: `7`
- callee_count: `15`
- tags: ``

## callers

- `0x180005990`
- `0x180006f00`
- `0x18000c434`
- `0x18000cb04`
- `0x18000cdf0`
- `0x18000e7d4`
- `0x180010548`

## callees

- `0x1800018e0`
- `0x1800021e0`
- `0x180002220`
- `0x180002a80`
- `0x180002b00`
- `0x180003e80`
- `0x180003ec0`
- `0x180003f40`
- `0x1800043d0`
- `0x180004ab0`
- `0x180004af0`
- `0x1800079f0`
- `0x180008160`
- `0x180009270`
- `0x180009afa`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800083dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800083dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800083ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800082c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800083ba`

## pseudocode

```c
MMRESULT __stdcall acmFormatDetailsW(HACMDRIVER had, LPACMFORMATDETAILSW pafd, DWORD fdwDetails)
{
  __int64 v3; // rbp
  __int64 v6; // rdi
  MMRESULT result; // eax
  DWORD cbwfx; // edx
  int v9; // r15d
  MMRESULT v10; // eax
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  MMRESULT v12; // ebx
  MMRESULT v13; // ebx
  __int64 v14; // r13
  bool v15; // cc
  int v16; // [rsp+20h] [rbp-E8h]
  __int64 v17; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D8h]
  struct tACMFORMATTAGDETAILSW paftd; // [rsp+40h] [rbp-C8h] BYREF

  v3 = fdwDetails;
  v6 = pagFindAndBoot();
  if ( !v6 )
    return 1;
  if ( (v3 & 0xFFFFFFF0) != 0 )
    return 10;
  if ( !(unsigned int)ValidateWritePointer(pafd, 4) )
    return 11;
  if ( pafd->cbStruct < 0x11C )
    return 11;
  if ( !(unsigned int)ValidateWritePointer(pafd, pafd->cbStruct) )
    return 11;
  cbwfx = pafd->cbwfx;
  if ( cbwfx < 0x10 || !(unsigned int)ValidateWritePointer(pafd->pwfx, cbwfx) || pafd->fdwSupport )
    return 11;
  v9 = v3 & 0xF;
  if ( (v3 & 0xF) != 0 )
  {
    if ( (v3 & 0xF) != 1 )
      return 8;
    if ( pafd->dwFormatTag != pafd->pwfx->wFormatTag )
      return 11;
  }
  if ( !pafd->dwFormatTag )
    return 11;
  if ( (v3 & 0xF) == 0 )
  {
    if ( !(unsigned int)ValidateHandle(had, 0) )
      return 5;
    memset_0(&paftd, 0, sizeof(paftd));
    paftd.dwFormatTag = pafd->dwFormatTag;
    paftd.cbStruct = 120;
    result = acmFormatTagDetailsW(had, &paftd, 1u);
    if ( result )
      return result;
    if ( pafd->dwFormatIndex >= paftd.cStandardFormats )
      return 11;
  }
  if ( had )
  {
    pafd->szFormat[0] = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)had - 1);
    if ( *(_DWORD *)had == 1 )
    {
      if ( (unsigned int)ValidateHandle(had, 1) )
      {
        v10 = IDriverMessageId(had, 24602, pafd, v3);
LABEL_27:
        v11 = (struct _RTL_CRITICAL_SECTION *)(had - 10);
        v12 = v10;
        LeaveCriticalSection(v11);
        if ( !v12 )
        {
          if ( !pafd->szFormat[0] )
            IFormatDetailsToString((__int64)pafd);
          if ( v9 == 1 )
            pafd->dwFormatIndex = 0;
        }
        return v12;
      }
    }
    else if ( (unsigned int)ValidateHandle(had, 2) )
    {
      v10 = IDriverMessage(had, 24602, pafd, v3);
      goto LABEL_27;
    }
    return 5;
  }
  v13 = 6;
  v14 = 0;
  v16 = 1;
  v17 = 0;
  AcquireLockShared((LPCRITICAL_SECTION)(v6 + 128));
  threadEnterListShared(v6);
  do
  {
    if ( (unsigned int)IDriverGetNext(v6, &v17, v14, 0) )
      goto LABEL_42;
    v14 = v17;
    v16 = 0;
    pafd->szFormat[0] = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v14 - 40));
    v18 = IDriverMessageId(v14, 24602, pafd, v3);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 - 40));
    v13 = v18;
  }
  while ( (_DWORD)v18 );
  if ( !pafd->szFormat[0] )
    IFormatDetailsToString((__int64)pafd);
  if ( v9 == 1 )
  {
    pafd->dwFormatIndex = 0;
    threadLeaveListShared(v6);
    ReleaseLock(v6 + 128);
    return v13;
  }
LABEL_42:
  threadLeaveListShared(v6);
  ReleaseLock(v6 + 128);
  if ( !v16 || v9 != 1 || pafd->dwFormatTag != 1 )
    return v13;
  v15 = (signed int)pafd->cbStruct <= 28;
  pafd->dwFormatIndex = 0;
  *(_QWORD *)&pafd->dwFormatTag = 1;
  pafd->cbwfx = 16;
  if ( !v15 )
  {
    pafd->szFormat[0] = 0;
    IFormatDetailsToString((__int64)pafd);
  }
  return 0;
}

```

## disassembly

```asm
0x180008160  push    rbx
0x180008162  push    rbp
0x180008163  push    rsi
0x180008164  push    rdi
0x180008165  sub     rsp, 0E8h
0x18000816c  mov     rax, cs:__security_cookie
0x180008173  xor     rax, rsp
0x180008176  mov     [rsp+108h+var_48], rax
0x18000817e  mov     ebp, r8d
0x180008181  mov     rsi, rdx
0x180008184  mov     rbx, rcx
0x180008187  call    pagFindAndBoot
0x18000818c  mov     rdi, rax
0x18000818f  test    rax, rax
0x180008192  jnz     short loc_18000819E
0x180008194  mov     eax, 1
0x180008199  jmp     loc_18000843A
0x18000819e  test    ebp, 0FFFFFFF0h
0x1800081a4  jz      short loc_1800081B0
0x1800081a6  mov     eax, 0Ah
0x1800081ab  jmp     loc_18000843A
0x1800081b0  mov     [rsp+108h+var_30], r14
0x1800081b8  mov     edx, 4
0x1800081bd  mov     rcx, rsi
0x1800081c0  mov     [rsp+108h+var_38], r15
0x1800081c8  call    ValidateWritePointer
0x1800081cd  test    eax, eax
0x1800081cf  jz      loc_1800084A9
0x1800081d5  mov     edx, [rsi]
0x1800081d7  cmp     edx, 11Ch
0x1800081dd  jb      loc_1800084A9
0x1800081e3  mov     rcx, rsi
0x1800081e6  call    ValidateWritePointer
0x1800081eb  test    eax, eax
0x1800081ed  jz      loc_1800084A9
0x1800081f3  mov     edx, [rsi+18h]
0x1800081f6  cmp     edx, 10h
0x1800081f9  jb      loc_1800084A9
0x1800081ff  mov     rcx, [rsi+10h]
0x180008203  call    ValidateWritePointer
0x180008208  test    eax, eax
0x18000820a  jz      loc_1800084A9
0x180008210  cmp     dword ptr [rsi+0Ch], 0
0x180008214  jnz     loc_1800084A9
0x18000821a  mov     r15d, ebp
0x18000821d  and     r15d, 0Fh
0x180008221  mov     eax, r15d
0x180008224  jz      short loc_180008245
0x180008226  cmp     eax, 1
0x180008229  jz      short loc_180008235
0x18000822b  mov     eax, 8
0x180008230  jmp     loc_18000842A
0x180008235  mov     rax, [rsi+10h]
0x180008239  movzx   ecx, word ptr [rax]
0x18000823c  cmp     [rsi+8], ecx
0x18000823f  jnz     loc_1800084A9
0x180008245  cmp     dword ptr [rsi+8], 0
0x180008249  jz      loc_1800084A9
0x18000824f  test    r15d, r15d
0x180008252  jnz     short loc_1800082AF
0x180008254  xor     edx, edx
0x180008256  mov     rcx, rbx
0x180008259  call    ValidateHandle
0x18000825e  test    eax, eax
0x180008260  jz      loc_180008306
0x180008266  xor     edx, edx; Val
0x180008268  lea     rcx, [rsp+108h+paftd]; void *
0x18000826d  mov     r8d, 78h ; 'x'; Size
0x180008273  call    memset_0
0x180008278  mov     eax, [rsi+8]
0x18000827b  lea     rdx, [rsp+108h+paftd]; paftd
0x180008280  mov     r8d, 1; fdwDetails
0x180008286  mov     [rsp+108h+paftd.dwFormatTag], eax
0x18000828a  mov     rcx, rbx; had
0x18000828d  mov     [rsp+108h+paftd.cbStruct], 78h ; 'x'
0x180008295  call    acmFormatTagDetailsW
0x18000829a  test    eax, eax
0x18000829c  jnz     loc_18000842A
0x1800082a2  mov     eax, [rsp+108h+paftd.cStandardFormats]
0x1800082a6  cmp     [rsi+4], eax
0x1800082a9  jnb     loc_1800084A9
0x1800082af  xor     r14d, r14d
0x1800082b2  test    rbx, rbx
0x1800082b5  jz      loc_180008353
0x1800082bb  lea     rdi, [rbx-28h]
0x1800082bf  mov     [rsi+1Ch], r14w
0x1800082c4  mov     rcx, rdi; lpCriticalSection
0x1800082c7  call    cs:__imp_EnterCriticalSection
0x1800082cd  cmp     dword ptr [rbx], 1
0x1800082d0  mov     rcx, rbx
0x1800082d3  jnz     short loc_1800082F8
0x1800082d5  mov     edx, 1
0x1800082da  call    ValidateHandle
0x1800082df  test    eax, eax
0x1800082e1  jz      short loc_180008306
0x1800082e3  mov     r9, rbp
0x1800082e6  mov     r8, rsi
0x1800082e9  mov     edx, 601Ah
0x1800082ee  mov     rcx, rbx
0x1800082f1  call    IDriverMessageId
0x1800082f6  jmp     short loc_180008323
0x1800082f8  mov     edx, 2
0x1800082fd  call    ValidateHandle
0x180008302  test    eax, eax
0x180008304  jnz     short loc_180008310
0x180008306  mov     eax, 5
0x18000830b  jmp     loc_18000842A
0x180008310  mov     r9, rbp
0x180008313  mov     r8, rsi
0x180008316  mov     edx, 601Ah
0x18000831b  mov     rcx, rbx
0x18000831e  call    IDriverMessage
0x180008323  mov     rcx, rdi; lpCriticalSection
0x180008326  mov     rbx, rax
0x180008329  call    cs:__imp_LeaveCriticalSection
0x18000832f  test    ebx, ebx
0x180008331  jnz     short loc_18000834C
0x180008333  cmp     r14w, [rsi+1Ch]
0x180008338  jnz     short loc_180008342
0x18000833a  mov     rcx, rsi
0x18000833d  call    IFormatDetailsToString
0x180008342  cmp     r15d, 1
0x180008346  jnz     short loc_18000834C
0x180008348  mov     [rsi+4], r14d
0x18000834c  mov     eax, ebx
0x18000834e  jmp     loc_18000842A
0x180008353  mov     [rsp+108h+arg_18], r12
0x18000835b  lea     rcx, [rdi+80h]; lpCriticalSection
0x180008362  mov     [rsp+108h+var_28], r13
0x18000836a  mov     ebx, 6
0x18000836f  mov     r13, r14
0x180008372  mov     [rsp+108h+var_E8], 1
0x18000837a  mov     [rsp+108h+var_E0], r14
0x18000837f  call    AcquireLockShared
0x180008384  mov     rcx, rdi
0x180008387  call    threadEnterListShared
0x18000838c  xor     r9d, r9d
0x18000838f  lea     rdx, [rsp+108h+var_E0]
0x180008394  mov     r8, r13
0x180008397  mov     rcx, rdi
0x18000839a  call    IDriverGetNext
0x18000839f  test    eax, eax
0x1800083a1  jnz     loc_180008456
0x1800083a7  mov     r13, [rsp+108h+var_E0]
0x1800083ac  mov     [rsp+108h+var_E8], r14d
0x1800083b1  mov     [rsi+1Ch], r14w
0x1800083b6  lea     rcx, [r13-28h]; lpCriticalSection
0x1800083ba  call    cs:__imp_EnterCriticalSection
0x1800083c0  mov     r9, rbp
0x1800083c3  mov     r8, rsi
0x1800083c6  mov     edx, 601Ah
0x1800083cb  mov     rcx, r13
0x1800083ce  call    IDriverMessageId
0x1800083d3  lea     rcx, [r13-28h]; lpCriticalSection
0x1800083d7  mov     [rsp+108h+var_D8], rax
0x1800083dc  call    cs:__imp_LeaveCriticalSection
0x1800083e2  mov     rbx, [rsp+108h+var_D8]
0x1800083e7  test    ebx, ebx
0x1800083e9  jnz     short loc_18000838C
0x1800083eb  cmp     r14w, [rsi+1Ch]
0x1800083f0  jnz     short loc_1800083FA
0x1800083f2  mov     rcx, rsi
0x1800083f5  call    IFormatDetailsToString
0x1800083fa  cmp     r15d, 1
0x1800083fe  jnz     short loc_180008456
0x180008400  mov     rcx, rdi
0x180008403  mov     [rsi+4], r14d
0x180008407  call    threadLeaveListShared
0x18000840c  lea     rcx, [rdi+80h]
0x180008413  call    ReleaseLock
0x180008418  mov     eax, ebx
0x18000841a  mov     r13, [rsp+108h+var_28]
0x180008422  mov     r12, [rsp+108h+arg_18]
0x18000842a  mov     r14, [rsp+108h+var_30]
0x180008432  mov     r15, [rsp+108h+var_38]
0x18000843a  mov     rcx, [rsp+108h+var_48]
0x180008442  xor     rcx, rsp; StackCookie
0x180008445  call    __security_check_cookie
0x18000844a  add     rsp, 0E8h
0x180008451  pop     rdi
0x180008452  pop     rsi
0x180008453  pop     rbp
0x180008454  pop     rbx
0x180008455  retn
0x180008456  mov     rcx, rdi
0x180008459  call    threadLeaveListShared
0x18000845e  lea     rcx, [rdi+80h]
0x180008465  call    ReleaseLock
0x18000846a  cmp     [rsp+108h+var_E8], r14d
0x18000846f  jz      short loc_180008418
0x180008471  cmp     r15d, 1
0x180008475  jnz     short loc_180008418
0x180008477  cmp     [rsi+8], r15d
0x18000847b  jnz     short loc_180008418
0x18000847d  cmp     dword ptr [rsi], 1Ch
0x180008480  mov     [rsi+4], r14d
0x180008484  mov     qword ptr [rsi+8], 1
0x18000848c  mov     dword ptr [rsi+18h], 10h
0x180008493  jle     short loc_1800084A2
0x180008495  mov     rcx, rsi
0x180008498  mov     [rsi+1Ch], r14w
0x18000849d  call    IFormatDetailsToString
0x1800084a2  xor     eax, eax
0x1800084a4  jmp     loc_18000841A
0x1800084a9  mov     eax, 0Bh
0x1800084ae  jmp     loc_18000842A
```
