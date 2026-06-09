# acmFilterTagDetailsW

- ea: `0x18000c130`
- end: `0x18000c342`
- name: `acmFilterTagDetailsW`
- size: `530`
- prototype: `MMRESULT __stdcall(HACMDRIVER had, LPACMFILTERTAGDETAILSW paftd, DWORD fdwDetails)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x180006f00`
- `0x18000b8d0`
- `0x18000c040`
- `0x18000e608`
- `0x1800119c0`

## callees

- `0x1800021e0`
- `0x180002220`
- `0x180002a80`
- `0x180003e80`
- `0x180003ec0`
- `0x180003f40`
- `0x180004ab0`
- `0x180004af0`
- `0x18000b6bc`
- `0x18000c130`

## pseudocode

```c
MMRESULT __stdcall acmFilterTagDetailsW(HACMDRIVER had, LPACMFILTERTAGDETAILSW paftd, DWORD fdwDetails)
{
  __int64 v6; // r14
  DWORD v8; // ebp
  HACMDRIVER v9; // rsi
  __int64 v10; // rcx
  unsigned int v11; // ebx
  DWORD dwFilterTag; // r9d
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 i; // r9
  __int64 v17; // [rsp+68h] [rbp+20h] BYREF

  v6 = pagFindAndBoot();
  if ( !v6 )
    return 1;
  if ( (fdwDetails & 0xFFFFFFF0) != 0 )
    return 10;
  if ( !(unsigned int)ValidateWritePointer(paftd, 4)
    || paftd->cbStruct < 0x78
    || !(unsigned int)ValidateWritePointer(paftd, paftd->cbStruct)
    || paftd->fdwSupport )
  {
    return 11;
  }
  v8 = fdwDetails & 0xF;
  if ( (fdwDetails & 0xF) == 0 )
  {
    if ( !ValidateHandle((int *)had, 0) )
      return 5;
    if ( !paftd->dwFilterTag )
      goto LABEL_17;
    return 11;
  }
  if ( (fdwDetails & 0xF) == 1 )
  {
    if ( paftd->dwFilterTag )
      goto LABEL_17;
    return 11;
  }
  if ( (fdwDetails & 0xF) != 2 )
    return 8;
LABEL_17:
  v9 = 0;
  if ( had )
  {
    if ( ValidateHandle((int *)had, 0) )
    {
      if ( *(_DWORD *)had == 1 )
      {
        if ( *((int *)had + 14) < 0 )
          return 3;
        v9 = had;
        return IFilterTagDetails(v10, v9, paftd, fdwDetails);
      }
      if ( ValidateHandle((int *)had, 2) )
      {
        v9 = *(HACMDRIVER *)(had + 5);
        if ( v9 )
          return IFilterTagDetails(v10, v9, paftd, fdwDetails);
        goto LABEL_25;
      }
    }
    return 5;
  }
LABEL_25:
  v17 = 0;
  AcquireLockShared((LPCRITICAL_SECTION)(v6 + 128));
  threadEnterListShared(v6);
  if ( !(unsigned int)IDriverGetNext(v6, &v17, 0, 0) )
  {
    v11 = 0;
    do
    {
      if ( v8 == 1 )
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v17 + 76); i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v17 + 80) + 8 * i) == paftd->dwFilterTag )
          {
            v9 = (HACMDRIVER)v17;
            break;
          }
        }
      }
      else if ( v8 == 2 && *(_DWORD *)(v17 + 76) )
      {
        dwFilterTag = paftd->dwFilterTag;
        v13 = 0;
        do
        {
          v14 = 8 * v13;
          if ( !dwFilterTag || *(_DWORD *)(v14 + *(_QWORD *)(v17 + 80)) == dwFilterTag )
          {
            v15 = *(_QWORD *)(v17 + 80);
            if ( *(_DWORD *)(v15 + v14 + 4) > v11 )
            {
              v11 = *(_DWORD *)(v15 + v14 + 4);
              v9 = (HACMDRIVER)v17;
            }
          }
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (unsigned int)v13 < *(_DWORD *)(v17 + 76) );
      }
    }
    while ( !(unsigned int)IDriverGetNext(v6, &v17, v17, 0) );
  }
  threadLeaveListShared(v6);
  ReleaseLock(v6 + 128);
  if ( v9 )
    return IFilterTagDetails(v10, v9, paftd, fdwDetails);
  return 512;
}

```

## disassembly

```asm
0x18000c130  mov     [rsp+arg_0], rbx
0x18000c135  mov     [rsp+arg_8], rbp
0x18000c13a  push    rsi
0x18000c13b  push    rdi
0x18000c13c  push    r12
0x18000c13e  push    r14
0x18000c140  push    r15
0x18000c142  sub     rsp, 20h
0x18000c146  mov     r15d, r8d
0x18000c149  mov     rdi, rdx
0x18000c14c  mov     rbx, rcx
0x18000c14f  call    pagFindAndBoot
0x18000c154  mov     r14, rax
0x18000c157  test    rax, rax
0x18000c15a  jnz     short loc_18000C162
0x18000c15c  lea     eax, [r14+1]
0x18000c160  jmp     short loc_18000C1C2
0x18000c162  test    r15d, 0FFFFFFF0h
0x18000c169  jz      short loc_18000C172
0x18000c16b  mov     eax, 0Ah
0x18000c170  jmp     short loc_18000C1C2
0x18000c172  mov     edx, 4
0x18000c177  mov     rcx, rdi
0x18000c17a  call    ValidateWritePointer
0x18000c17f  test    eax, eax
0x18000c181  jz      short loc_18000C1BD
0x18000c183  cmp     dword ptr [rdi], 78h ; 'x'
0x18000c186  jb      short loc_18000C1BD
0x18000c188  mov     edx, [rdi]
0x18000c18a  mov     rcx, rdi
0x18000c18d  call    ValidateWritePointer
0x18000c192  test    eax, eax
0x18000c194  jz      short loc_18000C1BD
0x18000c196  cmp     dword ptr [rdi+10h], 0
0x18000c19a  jnz     short loc_18000C1BD
0x18000c19c  mov     ebp, r15d
0x18000c19f  and     ebp, 0Fh
0x18000c1a2  mov     eax, ebp
0x18000c1a4  jz      short loc_18000C1D9
0x18000c1a6  sub     eax, 1
0x18000c1a9  jz      short loc_18000C1B7
0x18000c1ab  cmp     eax, 1
0x18000c1ae  jz      short loc_18000C1F1
0x18000c1b0  mov     eax, 8
0x18000c1b5  jmp     short loc_18000C1C2
0x18000c1b7  cmp     dword ptr [rdi+8], 0
0x18000c1bb  jnz     short loc_18000C1F1
0x18000c1bd  mov     eax, 0Bh
0x18000c1c2  mov     rbx, [rsp+48h+arg_0]
0x18000c1c7  mov     rbp, [rsp+48h+arg_8]
0x18000c1cc  add     rsp, 20h
0x18000c1d0  pop     r15
0x18000c1d2  pop     r14
0x18000c1d4  pop     r12
0x18000c1d6  pop     rdi
0x18000c1d7  pop     rsi
0x18000c1d8  retn
0x18000c1d9  xor     edx, edx
0x18000c1db  mov     rcx, rbx
0x18000c1de  call    ValidateHandle
0x18000c1e3  test    eax, eax
0x18000c1e5  jz      loc_18000C338
0x18000c1eb  cmp     dword ptr [rdi+8], 0
0x18000c1ef  jnz     short loc_18000C1BD
0x18000c1f1  xor     esi, esi
0x18000c1f3  test    rbx, rbx
0x18000c1f6  jz      short loc_18000C243
0x18000c1f8  xor     edx, edx
0x18000c1fa  mov     rcx, rbx
0x18000c1fd  call    ValidateHandle
0x18000c202  test    eax, eax
0x18000c204  jz      loc_18000C338
0x18000c20a  cmp     dword ptr [rbx], 1
0x18000c20d  jnz     short loc_18000C221
0x18000c20f  cmp     [rbx+38h], esi
0x18000c212  jge     short loc_18000C219
0x18000c214  lea     eax, [rsi+3]
0x18000c217  jmp     short loc_18000C1C2
0x18000c219  mov     rsi, rbx
0x18000c21c  jmp     loc_18000C31B
0x18000c221  mov     edx, 2
0x18000c226  mov     rcx, rbx
0x18000c229  call    ValidateHandle
0x18000c22e  test    eax, eax
0x18000c230  jz      loc_18000C338
0x18000c236  mov     rsi, [rbx+14h]
0x18000c23a  test    rsi, rsi
0x18000c23d  jnz     loc_18000C31B
0x18000c243  lea     r12, [r14+80h]
0x18000c24a  mov     [rsp+48h+arg_18], 0
0x18000c253  mov     rcx, r12; lpCriticalSection
0x18000c256  call    AcquireLockShared
0x18000c25b  mov     rcx, r14
0x18000c25e  call    threadEnterListShared
0x18000c263  xor     r9d, r9d
0x18000c266  lea     rdx, [rsp+48h+arg_18]
0x18000c26b  xor     r8d, r8d
0x18000c26e  mov     rcx, r14
0x18000c271  call    IDriverGetNext
0x18000c276  test    eax, eax
0x18000c278  jnz     loc_18000C306
0x18000c27e  xor     ebx, ebx
0x18000c280  mov     r8, [rsp+48h+arg_18]
0x18000c285  mov     eax, ebp
0x18000c287  sub     eax, 1
0x18000c28a  jz      short loc_18000C2D0
0x18000c28c  cmp     eax, 1
0x18000c28f  jnz     short loc_18000C2EE
0x18000c291  cmp     dword ptr [r8+4Ch], 0
0x18000c296  jbe     short loc_18000C2EE
0x18000c298  mov     r9d, [rdi+8]
0x18000c29c  xor     edx, edx
0x18000c29e  lea     rcx, ds:0[rdx*8]
0x18000c2a6  test    r9d, r9d
0x18000c2a9  jz      short loc_18000C2B5
0x18000c2ab  mov     rax, [r8+50h]
0x18000c2af  cmp     [rcx+rax], r9d
0x18000c2b3  jnz     short loc_18000C2C6
0x18000c2b5  mov     rax, [r8+50h]
0x18000c2b9  cmp     [rax+rcx+4], ebx
0x18000c2bd  jbe     short loc_18000C2C6
0x18000c2bf  mov     ebx, [rax+rcx+4]
0x18000c2c3  mov     rsi, r8
0x18000c2c6  inc     edx
0x18000c2c8  cmp     edx, [r8+4Ch]
0x18000c2cc  jb      short loc_18000C29E
0x18000c2ce  jmp     short loc_18000C2EE
0x18000c2d0  xor     r9d, r9d
0x18000c2d3  cmp     r9d, [r8+4Ch]
0x18000c2d7  jnb     short loc_18000C2EE
0x18000c2d9  mov     rcx, [r8+50h]
0x18000c2dd  mov     eax, [rdi+8]
0x18000c2e0  cmp     [rcx+r9*8], eax
0x18000c2e4  jz      short loc_18000C2EB
0x18000c2e6  inc     r9d
0x18000c2e9  jmp     short loc_18000C2D3
0x18000c2eb  mov     rsi, r8
0x18000c2ee  xor     r9d, r9d
0x18000c2f1  lea     rdx, [rsp+48h+arg_18]
0x18000c2f6  mov     rcx, r14
0x18000c2f9  call    IDriverGetNext
0x18000c2fe  test    eax, eax
0x18000c300  jz      loc_18000C280
0x18000c306  mov     rcx, r14
0x18000c309  call    threadLeaveListShared
0x18000c30e  mov     rcx, r12
0x18000c311  call    ReleaseLock
0x18000c316  test    rsi, rsi
0x18000c319  jz      short loc_18000C32E
0x18000c31b  mov     r9d, r15d
0x18000c31e  mov     r8, rdi
0x18000c321  mov     rdx, rsi
0x18000c324  call    IFilterTagDetails
0x18000c329  jmp     loc_18000C1C2
0x18000c32e  mov     eax, 200h
0x18000c333  jmp     loc_18000C1C2
0x18000c338  mov     eax, 5
0x18000c33d  jmp     loc_18000C1C2
```
