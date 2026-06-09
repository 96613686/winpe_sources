# acmFilterDetailsW

- ea: `0x18000b8d0`
- end: `0x18000bb8e`
- name: `acmFilterDetailsW`
- size: `702`
- prototype: `MMRESULT __stdcall(HACMDRIVER had, LPACMFILTERDETAILSW pafd, DWORD fdwDetails)`
- caller_count: `5`
- callee_count: `14`
- tags: ``

## callers

- `0x18000b588`
- `0x18000b7d0`
- `0x18000e608`
- `0x180010548`
- `0x1800119c0`

## callees

- `0x1800018e0`
- `0x1800021e0`
- `0x180002220`
- `0x180002a80`
- `0x180003e80`
- `0x180003ec0`
- `0x180003f40`
- `0x1800043d0`
- `0x180004ab0`
- `0x180004af0`
- `0x180009270`
- `0x180009afa`
- `0x18000b8d0`
- `0x18000c130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bab3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bab3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ba4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ba94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ba4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ba94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb1a`

## pseudocode

```c
MMRESULT __stdcall acmFilterDetailsW(HACMDRIVER had, LPACMFILTERDETAILSW pafd, DWORD fdwDetails)
{
  __int64 v3; // r12
  __int64 v6; // r15
  MMRESULT result; // eax
  DWORD cbwfltr; // edx
  int v9; // r14d
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  MMRESULT v11; // eax
  MMRESULT v12; // esi
  __int64 v13; // rsi
  MMRESULT v14; // r12d
  __int64 v16; // [rsp+28h] [rbp-D0h] BYREF
  struct tACMFILTERTAGDETAILSW paftd; // [rsp+30h] [rbp-C8h] BYREF

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
  cbwfltr = pafd->cbwfltr;
  if ( cbwfltr < 0x20 || !(unsigned int)ValidateWritePointer(pafd->pwfltr, cbwfltr) || pafd->fdwSupport )
    return 11;
  v9 = v3 & 0xF;
  if ( (v3 & 0xF) != 0 )
  {
    if ( (v3 & 0xF) != 1 )
      return 8;
    if ( pafd->dwFilterTag != pafd->pwfltr->dwFilterTag )
      return 11;
  }
  if ( !pafd->dwFilterTag )
    return 11;
  if ( (v3 & 0xF) == 0 )
  {
    if ( !ValidateHandle((int *)had, 0) )
      return 5;
    memset_0(&paftd, 0, sizeof(paftd));
    paftd.dwFilterTag = pafd->dwFilterTag;
    paftd.cbStruct = 120;
    result = acmFilterTagDetailsW(had, &paftd, 1u);
    if ( result )
      return result;
    if ( pafd->dwFilterIndex >= paftd.cStandardFilters )
      return 11;
  }
  if ( had )
  {
    if ( *(_DWORD *)had == 1 )
    {
      if ( ValidateHandle((int *)had, 1) )
      {
        if ( ((_DWORD)had[15] & 4) != 0 )
        {
          v10 = (struct _RTL_CRITICAL_SECTION *)(had - 10);
          EnterCriticalSection((LPCRITICAL_SECTION)had - 1);
          v11 = IDriverMessageId(had, 24627, pafd, v3);
LABEL_29:
          v12 = v11;
          LeaveCriticalSection(v10);
          if ( !v12 && v9 == 1 )
            pafd->dwFilterIndex = 0;
          return v12;
        }
        return 11;
      }
    }
    else if ( ValidateHandle((int *)had, 2) )
    {
      if ( (*(_DWORD *)(*(_QWORD *)(had + 5) + 60LL) & 4) != 0 )
      {
        v10 = (struct _RTL_CRITICAL_SECTION *)(had - 10);
        EnterCriticalSection((LPCRITICAL_SECTION)had - 1);
        v11 = IDriverMessage(had, 24627, pafd, v3);
        goto LABEL_29;
      }
      return 11;
    }
    return 5;
  }
  v13 = 0;
  v16 = 0;
  v14 = 6;
  AcquireLockShared((LPCRITICAL_SECTION)(v6 + 128));
  threadEnterListShared(v6);
  while ( !(unsigned int)IDriverGetNext(v6, &v16, v13, 0) )
  {
    v13 = v16;
    if ( (*(_DWORD *)(v16 + 60) & 4) != 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 - 40));
      v14 = IDriverMessageId(v13, 24627, pafd, fdwDetails);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v13 - 40));
      if ( !v14 )
      {
        if ( v9 == 1 )
          pafd->dwFilterIndex = 0;
        break;
      }
    }
  }
  threadLeaveListShared(v6);
  ReleaseLock(v6 + 128);
  return v14;
}

```

## disassembly

```asm
0x18000b8d0  push    rbx
0x18000b8d2  push    rsi
0x18000b8d3  push    rdi
0x18000b8d4  push    r12
0x18000b8d6  push    r13
0x18000b8d8  push    r14
0x18000b8da  push    r15
0x18000b8dc  sub     rsp, 0C0h
0x18000b8e3  mov     rax, cs:__security_cookie
0x18000b8ea  xor     rax, rsp
0x18000b8ed  mov     [rsp+0F8h+var_48], rax
0x18000b8f5  mov     r12d, r8d
0x18000b8f8  mov     rdi, rdx
0x18000b8fb  mov     [rsp+0F8h+var_D8], r12d
0x18000b900  mov     rsi, rcx
0x18000b903  call    pagFindAndBoot
0x18000b908  xor     r13d, r13d
0x18000b90b  mov     r15, rax
0x18000b90e  test    rax, rax
0x18000b911  jnz     short loc_18000B91C
0x18000b913  lea     eax, [r15+1]
0x18000b917  jmp     loc_18000BB6B
0x18000b91c  test    r12d, 0FFFFFFF0h
0x18000b923  jz      short loc_18000B92F
0x18000b925  mov     eax, 0Ah
0x18000b92a  jmp     loc_18000BB6B
0x18000b92f  mov     edx, 4
0x18000b934  mov     rcx, rdi
0x18000b937  call    ValidateWritePointer
0x18000b93c  test    eax, eax
0x18000b93e  jz      loc_18000BB66
0x18000b944  cmp     dword ptr [rdi], 11Ch
0x18000b94a  jb      loc_18000BB66
0x18000b950  mov     edx, [rdi]
0x18000b952  mov     rcx, rdi
0x18000b955  call    ValidateWritePointer
0x18000b95a  test    eax, eax
0x18000b95c  jz      loc_18000BB66
0x18000b962  mov     edx, [rdi+18h]
0x18000b965  cmp     edx, 20h ; ' '
0x18000b968  jb      loc_18000BB66
0x18000b96e  mov     rcx, [rdi+10h]
0x18000b972  call    ValidateWritePointer
0x18000b977  test    eax, eax
0x18000b979  jz      loc_18000BB66
0x18000b97f  cmp     [rdi+0Ch], r13d
0x18000b983  jnz     loc_18000BB66
0x18000b989  mov     r14d, r12d
0x18000b98c  and     r14d, 0Fh
0x18000b990  mov     eax, r14d
0x18000b993  jz      short loc_18000B9B4
0x18000b995  cmp     eax, 1
0x18000b998  jz      short loc_18000B9A4
0x18000b99a  mov     eax, 8
0x18000b99f  jmp     loc_18000BB6B
0x18000b9a4  mov     rax, [rdi+10h]
0x18000b9a8  mov     ecx, [rax+4]
0x18000b9ab  cmp     [rdi+8], ecx
0x18000b9ae  jnz     loc_18000BB66
0x18000b9b4  cmp     [rdi+8], r13d
0x18000b9b8  jz      loc_18000BB66
0x18000b9be  test    r14d, r14d
0x18000b9c1  jnz     short loc_18000BA19
0x18000b9c3  xor     edx, edx
0x18000b9c5  mov     rcx, rsi
0x18000b9c8  call    ValidateHandle
0x18000b9cd  test    eax, eax
0x18000b9cf  jz      loc_18000BA73
0x18000b9d5  lea     ebx, [r14+78h]
0x18000b9d9  xor     edx, edx; Val
0x18000b9db  mov     r8d, ebx; Size
0x18000b9de  lea     rcx, [rsp+0F8h+paftd]; void *
0x18000b9e3  call    memset_0
0x18000b9e8  mov     eax, [rdi+8]
0x18000b9eb  lea     r8d, [r14+1]; fdwDetails
0x18000b9ef  lea     rdx, [rsp+0F8h+paftd]; paftd
0x18000b9f4  mov     [rsp+0F8h+paftd.dwFilterTag], eax
0x18000b9f8  mov     rcx, rsi; had
0x18000b9fb  mov     [rsp+0F8h+paftd.cbStruct], ebx
0x18000b9ff  call    acmFilterTagDetailsW
0x18000ba04  test    eax, eax
0x18000ba06  jnz     loc_18000BB6B
0x18000ba0c  mov     eax, [rsp+0F8h+paftd.cStandardFilters]
0x18000ba10  cmp     [rdi+4], eax
0x18000ba13  jnb     loc_18000BB66
0x18000ba19  test    rsi, rsi
0x18000ba1c  jz      loc_18000BACE
0x18000ba22  cmp     dword ptr [rsi], 1
0x18000ba25  mov     rcx, rsi
0x18000ba28  jnz     short loc_18000BA65
0x18000ba2a  mov     edx, 1
0x18000ba2f  call    ValidateHandle
0x18000ba34  test    eax, eax
0x18000ba36  jz      short loc_18000BA73
0x18000ba38  mov     eax, [rsi+3Ch]
0x18000ba3b  test    al, 4
0x18000ba3d  jz      loc_18000BB66
0x18000ba43  lea     rbx, [rsi-28h]
0x18000ba47  mov     rcx, rbx; lpCriticalSection
0x18000ba4a  call    cs:__imp_EnterCriticalSection
0x18000ba50  mov     r9, r12
0x18000ba53  mov     r8, rdi
0x18000ba56  mov     edx, 6033h
0x18000ba5b  mov     rcx, rsi
0x18000ba5e  call    IDriverMessageId
0x18000ba63  jmp     short loc_18000BAAD
0x18000ba65  mov     edx, 2
0x18000ba6a  call    ValidateHandle
0x18000ba6f  test    eax, eax
0x18000ba71  jnz     short loc_18000BA7D
0x18000ba73  mov     eax, 5
0x18000ba78  jmp     loc_18000BB6B
0x18000ba7d  mov     rax, [rsi+14h]
0x18000ba81  mov     ecx, [rax+3Ch]
0x18000ba84  test    cl, 4
0x18000ba87  jz      loc_18000BB66
0x18000ba8d  lea     rbx, [rsi-28h]
0x18000ba91  mov     rcx, rbx; lpCriticalSection
0x18000ba94  call    cs:__imp_EnterCriticalSection
0x18000ba9a  mov     r9, r12
0x18000ba9d  mov     r8, rdi
0x18000baa0  mov     edx, 6033h
0x18000baa5  mov     rcx, rsi
0x18000baa8  call    IDriverMessage
0x18000baad  mov     rcx, rbx; lpCriticalSection
0x18000bab0  mov     rsi, rax
0x18000bab3  call    cs:__imp_LeaveCriticalSection
0x18000bab9  test    esi, esi
0x18000babb  jnz     short loc_18000BAC7
0x18000babd  cmp     r14d, 1
0x18000bac1  jnz     short loc_18000BAC7
0x18000bac3  mov     [rdi+4], r13d
0x18000bac7  mov     eax, esi
0x18000bac9  jmp     loc_18000BB6B
0x18000bace  mov     rsi, r13
0x18000bad1  mov     [rsp+0F8h+var_D0], r13
0x18000bad6  lea     r13, [r15+80h]
0x18000badd  mov     r12d, 6
0x18000bae3  mov     rcx, r13; lpCriticalSection
0x18000bae6  call    AcquireLockShared
0x18000baeb  mov     rcx, r15
0x18000baee  call    threadEnterListShared
0x18000baf3  xor     r9d, r9d
0x18000baf6  lea     rdx, [rsp+0F8h+var_D0]
0x18000bafb  mov     r8, rsi
0x18000bafe  mov     rcx, r15
0x18000bb01  call    IDriverGetNext
0x18000bb06  test    eax, eax
0x18000bb08  jnz     short loc_18000BB51
0x18000bb0a  mov     rsi, [rsp+0F8h+var_D0]
0x18000bb0f  mov     eax, [rsi+3Ch]
0x18000bb12  test    al, 4
0x18000bb14  jz      short loc_18000BAF3
0x18000bb16  lea     rcx, [rsi-28h]; lpCriticalSection
0x18000bb1a  call    cs:__imp_EnterCriticalSection
0x18000bb20  mov     r9d, [rsp+0F8h+var_D8]
0x18000bb25  mov     r8, rdi
0x18000bb28  mov     edx, 6033h
0x18000bb2d  mov     rcx, rsi
0x18000bb30  call    IDriverMessageId
0x18000bb35  lea     rcx, [rsi-28h]; lpCriticalSection
0x18000bb39  mov     r12, rax
0x18000bb3c  call    cs:__imp_LeaveCriticalSection
0x18000bb42  test    r12d, r12d
0x18000bb45  jnz     short loc_18000BAF3
0x18000bb47  cmp     r14d, 1
0x18000bb4b  jnz     short loc_18000BB51
0x18000bb4d  mov     [rdi+4], r12d
0x18000bb51  mov     rcx, r15
0x18000bb54  call    threadLeaveListShared
0x18000bb59  mov     rcx, r13
0x18000bb5c  call    ReleaseLock
0x18000bb61  mov     eax, r12d
0x18000bb64  jmp     short loc_18000BB6B
0x18000bb66  mov     eax, 0Bh
0x18000bb6b  mov     rcx, [rsp+0F8h+var_48]
0x18000bb73  xor     rcx, rsp; StackCookie
0x18000bb76  call    __security_check_cookie
0x18000bb7b  add     rsp, 0C0h
0x18000bb82  pop     r15
0x18000bb84  pop     r14
0x18000bb86  pop     r13
0x18000bb88  pop     r12
0x18000bb8a  pop     rdi
0x18000bb8b  pop     rsi
0x18000bb8c  pop     rbx
0x18000bb8d  retn
```
