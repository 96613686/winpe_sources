# PlayFile

- ea: `0x180002d40`
- end: `0x180002fef`
- name: `PlayFile`
- size: `687`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180005170`

## callees

- `0x180002d40`
- `0x180005b1c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002e67`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180002e67`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002e41`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002e41`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002fc0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002fc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002fcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002fcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fb5`
- `WINMM!mciDriverNotify` at `0x180002f59`
- `WINMM!mciDriverNotify` at `0x180002f94`
- `WINMM!mciDriverNotify` at `0x180002f59`
- `WINMM!mciDriverNotify` at `0x180002f94`
- `WINMM!waveOutWrite` at `0x180002f04`
- `WINMM!waveOutWrite` at `0x180002f04`
- `WINMM!waveOutPause` at `0x180002d81`
- `WINMM!waveOutPause` at `0x180002d81`
- `WINMM!mmioSeek` at `0x180002eb0`
- `WINMM!mmioSeek` at `0x180002eb0`
- `WINMM!mmioRead` at `0x180002ec5`
- `WINMM!mmioRead` at `0x180002ec5`

## pseudocode

```c
__int64 __fastcall PlayFile(__int64 a1)
{
  LPWAVEHDR *v1; // r14
  unsigned int v2; // edi
  LPWAVEHDR *v3; // rsi
  int v5; // eax
  MMRESULT v6; // eax
  unsigned int v7; // ecx
  DWORD v8; // ecx
  DWORD v9; // ebp
  DWORD v10; // r12d
  int *v11; // r15
  char *lpData; // r13
  int v13; // edx
  unsigned int v14; // r8d
  int v15; // r8d
  int v16; // eax
  DWORD v17; // r14d
  DWORD v18; // ecx
  MMRESULT v19; // eax
  void *v20; // rcx
  void *v21; // rcx
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 4) |= 1u;
  v1 = (LPWAVEHDR *)(a1 + 184);
  v2 = 0;
  v3 = (LPWAVEHDR *)(a1 + 184);
  while ( 1 )
  {
    v5 = *(_DWORD *)(a1 + 4);
    if ( (v5 & 0x100) != 0 )
    {
      if ( (v5 & 0x1000) != 0 )
        goto LABEL_47;
      if ( (v5 & 0x2000) != 0 )
      {
        v6 = waveOutPause(*(HWAVEOUT *)(a1 + 48));
        *(_DWORD *)(a1 + 140) = v6;
        if ( v6 )
          goto LABEL_47;
      }
      *(_DWORD *)(a1 + 4) &= ~0x100u;
      v5 = *(_DWORD *)(a1 + 4);
    }
    if ( v2 < *(_DWORD *)(a1 + 144) )
    {
      v7 = *(_DWORD *)(a1 + 72);
      if ( *(_DWORD *)(a1 + 64) < v7 )
        break;
    }
    if ( v2 )
    {
      if ( (v5 & 0x2000) != 0 )
      {
        v20 = *(void **)(a1 + 16);
        *(_DWORD *)(a1 + 4) = v5 | 0x10;
        if ( v20 )
        {
          mciDriverNotify(v20, *(_DWORD *)a1, 1u);
          *(_QWORD *)(a1 + 16) = 0;
        }
      }
      if ( (unsigned int)TaskBlock() == 1024 )
        --v2;
    }
    else
    {
      if ( (v5 & 0x4000) == 0 )
        goto LABEL_47;
      v21 = *(void **)(a1 + 16);
      *(_DWORD *)(a1 + 4) = v5 | 0x20;
      if ( v21 )
      {
        mciDriverNotify(v21, *(_DWORD *)a1, 1u);
        *(_QWORD *)(a1 + 16) = 0;
      }
      while ( (unsigned int)TaskBlock() != 1025 )
        ;
    }
LABEL_46:
    LeaveCriticalSection(&CritSec);
    Sleep(0xAu);
    EnterCriticalSection(&CritSec);
  }
  v8 = v7 - *(_DWORD *)(a1 + 64);
  v9 = *(_DWORD *)(a1 + 148);
  if ( v9 >= v8 )
    v9 = v8;
  v10 = 0;
  if ( !v9 )
    goto LABEL_31;
  v11 = (int *)(*(_QWORD *)(a1 + 104) + 16LL * *(unsigned int *)(a1 + 120));
  lpData = (*v3)->lpData;
  while ( 1 )
  {
    v13 = *(_DWORD *)(a1 + 124);
    v14 = *(_DWORD *)(a1 + 64);
    NumberOfBytesRead = 0;
    if ( v13 + v11[1] <= v14 )
    {
      *(_DWORD *)(a1 + 120) = v11[3];
      v13 += v11[1];
      *(_DWORD *)(a1 + 124) = v13;
      v11 = (int *)(*(_QWORD *)(a1 + 104) + 16LL * (unsigned int)v11[3]);
    }
    v15 = v14 - v13;
    v16 = *v11;
    v17 = v11[1] - v15;
    if ( v9 < v17 )
      v17 = v9;
    if ( v16 >= 0 )
    {
      if ( mmioSeek(*(HMMIO *)(a1 + 80), v15 + v16 + *(_DWORD *)(a1 + 112), 0) == -1 )
        goto LABEL_21;
      v18 = mmioRead(*(HMMIO *)(a1 + 80), lpData, v17);
    }
    else if ( SetFilePointer(*(HANDLE *)(a1 + 88), v15 + (v16 & 0x7FFFFFFF), 0, 0) == -1
           || !ReadFile(*(HANDLE *)(a1 + 88), lpData, v17, &NumberOfBytesRead, 0)
           || (v18 = NumberOfBytesRead, NumberOfBytesRead != v17) )
    {
LABEL_21:
      v18 = -1;
    }
    if ( v18 != -1 )
    {
      v10 += v18;
      lpData += v18;
      v9 -= v18;
      *(_DWORD *)(a1 + 64) += v18;
    }
    if ( v18 != v17 )
      break;
    if ( !v9 )
      goto LABEL_30;
  }
  *(_DWORD *)(a1 + 140) = 348;
LABEL_30:
  v1 = (LPWAVEHDR *)(a1 + 184);
LABEL_31:
  (*v3)->dwBufferLength = v10;
  if ( v10 )
  {
    (*v3)->dwFlags &= 0xFFFFFFF2;
    v19 = waveOutWrite(*(HWAVEOUT *)(a1 + 48), *v3, 0x30u);
    *(_DWORD *)(a1 + 140) = v19;
    if ( !v19 )
    {
      ++v2;
      if ( (unsigned __int64)v3 >= a1 + 8 * ((unsigned __int64)*(unsigned int *)(a1 + 144) + 22) )
        v3 = v1;
      else
        ++v3;
      goto LABEL_46;
    }
  }
LABEL_47:
  *(_DWORD *)(a1 + 4) &= ~1u;
  return v2;
}

```

## disassembly

```asm
0x180002d40  push    rbx
0x180002d42  push    rbp
0x180002d43  push    rsi
0x180002d44  push    rdi
0x180002d45  push    r12
0x180002d47  push    r13
0x180002d49  push    r14
0x180002d4b  push    r15
0x180002d4d  sub     rsp, 38h
0x180002d51  or      dword ptr [rcx+4], 1
0x180002d55  lea     r14, [rcx+0B8h]
0x180002d5c  xor     edi, edi
0x180002d5e  mov     rsi, r14
0x180002d61  mov     rbx, rcx
0x180002d64  mov     eax, [rbx+4]
0x180002d67  bt      eax, 8
0x180002d6b  jnb     short loc_180002D9D
0x180002d6d  bt      eax, 0Ch
0x180002d71  jb      loc_180002FD8
0x180002d77  bt      eax, 0Dh
0x180002d7b  jnb     short loc_180002D95
0x180002d7d  mov     rcx, [rbx+30h]; hwo
0x180002d81  call    cs:__imp_waveOutPause
0x180002d87  mov     [rbx+8Ch], eax
0x180002d8d  test    eax, eax
0x180002d8f  jnz     loc_180002FD8
0x180002d95  btr     dword ptr [rbx+4], 8
0x180002d9a  mov     eax, [rbx+4]
0x180002d9d  cmp     edi, [rbx+90h]
0x180002da3  jnb     loc_180002F38
0x180002da9  mov     ecx, [rbx+48h]
0x180002dac  cmp     [rbx+40h], ecx
0x180002daf  jnb     loc_180002F38
0x180002db5  sub     ecx, [rbx+40h]
0x180002db8  mov     ebp, [rbx+94h]
0x180002dbe  cmp     ebp, ecx
0x180002dc0  cmovnb  ebp, ecx
0x180002dc3  xor     r12d, r12d
0x180002dc6  test    ebp, ebp
0x180002dc8  jz      loc_180002EE0
0x180002dce  mov     rax, [rsi]
0x180002dd1  mov     r15d, [rbx+78h]
0x180002dd5  shl     r15, 4
0x180002dd9  add     r15, [rbx+68h]
0x180002ddd  mov     r13, [rax]
0x180002de0  mov     edx, [rbx+7Ch]
0x180002de3  mov     r8d, [rbx+40h]
0x180002de7  mov     [rsp+78h+NumberOfBytesRead], 0
0x180002df2  mov     ecx, [r15+4]
0x180002df6  add     ecx, edx
0x180002df8  cmp     ecx, r8d
0x180002dfb  ja      short loc_180002E17
0x180002dfd  mov     eax, [r15+0Ch]
0x180002e01  mov     [rbx+78h], eax
0x180002e04  add     edx, [r15+4]
0x180002e08  mov     [rbx+7Ch], edx
0x180002e0b  mov     r15d, [r15+0Ch]
0x180002e0f  shl     r15, 4
0x180002e13  add     r15, [rbx+68h]
0x180002e17  mov     r14d, [r15+4]
0x180002e1b  sub     r8d, edx
0x180002e1e  mov     eax, [r15]
0x180002e21  sub     r14d, r8d
0x180002e24  cmp     ebp, r14d
0x180002e27  cmovb   r14d, ebp
0x180002e2b  test    eax, eax
0x180002e2d  jns     short loc_180002EA1
0x180002e2f  mov     rcx, [rbx+58h]; hFile
0x180002e33  btr     eax, 1Fh
0x180002e37  xor     r9d, r9d; dwMoveMethod
0x180002e3a  lea     edx, [r8+rax]; lDistanceToMove
0x180002e3e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180002e41  call    cs:__imp_SetFilePointer
0x180002e47  cmp     eax, 0FFFFFFFFh
0x180002e4a  jz      short loc_180002E7D
0x180002e4c  mov     rcx, [rbx+58h]; hFile
0x180002e50  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180002e58  mov     r8d, r14d; nNumberOfBytesToRead
0x180002e5b  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180002e64  mov     rdx, r13; lpBuffer
0x180002e67  call    cs:__imp_ReadFile
0x180002e6d  test    eax, eax
0x180002e6f  jz      short loc_180002E7D
0x180002e71  mov     ecx, [rsp+78h+NumberOfBytesRead]
0x180002e78  cmp     ecx, r14d
0x180002e7b  jz      short loc_180002E80
0x180002e7d  or      ecx, 0FFFFFFFFh
0x180002e80  cmp     ecx, 0FFFFFFFFh
0x180002e83  jz      short loc_180002E92
0x180002e85  mov     eax, ecx
0x180002e87  add     r12d, ecx
0x180002e8a  add     r13, rax
0x180002e8d  sub     ebp, ecx
0x180002e8f  add     [rbx+40h], ecx
0x180002e92  cmp     ecx, r14d
0x180002e95  jnz     short loc_180002ECF
0x180002e97  test    ebp, ebp
0x180002e99  jnz     loc_180002DE0
0x180002e9f  jmp     short loc_180002ED9
0x180002ea1  mov     edx, [rbx+70h]
0x180002ea4  mov     rcx, [rbx+50h]; hmmio
0x180002ea8  add     edx, eax
0x180002eaa  add     edx, r8d; lOffset
0x180002ead  xor     r8d, r8d; iOrigin
0x180002eb0  call    cs:__imp_mmioSeek
0x180002eb6  cmp     eax, 0FFFFFFFFh
0x180002eb9  jz      short loc_180002E7D
0x180002ebb  mov     rcx, [rbx+50h]; hmmio
0x180002ebf  mov     r8d, r14d; cch
0x180002ec2  mov     rdx, r13; pch
0x180002ec5  call    cs:__imp_mmioRead
0x180002ecb  mov     ecx, eax
0x180002ecd  jmp     short loc_180002E80
0x180002ecf  mov     dword ptr [rbx+8Ch], 15Ch
0x180002ed9  lea     r14, [rbx+0B8h]
0x180002ee0  mov     rax, [rsi]
0x180002ee3  mov     [rax+8], r12d
0x180002ee7  test    r12d, r12d
0x180002eea  jz      loc_180002FD8
0x180002ef0  mov     rax, [rsi]
0x180002ef3  mov     r8d, 30h ; '0'; cbwh
0x180002ef9  and     dword ptr [rax+18h], 0FFFFFFF2h
0x180002efd  mov     rdx, [rsi]; pwh
0x180002f00  mov     rcx, [rbx+30h]; hwo
0x180002f04  call    cs:__imp_waveOutWrite
0x180002f0a  mov     [rbx+8Ch], eax
0x180002f10  test    eax, eax
0x180002f12  jnz     loc_180002FD8
0x180002f18  mov     ecx, [rbx+90h]
0x180002f1e  inc     edi
0x180002f20  add     rcx, 16h
0x180002f24  lea     rcx, [rbx+rcx*8]
0x180002f28  cmp     rsi, rcx
0x180002f2b  jnb     short loc_180002F33
0x180002f2d  add     rsi, 8
0x180002f31  jmp     short loc_180002FAE
0x180002f33  mov     rsi, r14
0x180002f36  jmp     short loc_180002FAE
0x180002f38  test    edi, edi
0x180002f3a  jz      short loc_180002F77
0x180002f3c  bt      eax, 0Dh
0x180002f40  jnb     short loc_180002F67
0x180002f42  mov     rcx, [rbx+10h]; hwndCallback
0x180002f46  or      eax, 10h
0x180002f49  mov     [rbx+4], eax
0x180002f4c  test    rcx, rcx
0x180002f4f  jz      short loc_180002F67
0x180002f51  mov     edx, [rbx]; wDeviceID
0x180002f53  mov     r8d, 1; uStatus
0x180002f59  call    cs:__imp_mciDriverNotify
0x180002f5f  mov     qword ptr [rbx+10h], 0
0x180002f67  call    TaskBlock
0x180002f6c  cmp     eax, 400h
0x180002f71  jnz     short loc_180002FAE
0x180002f73  dec     edi
0x180002f75  jmp     short loc_180002FAE
0x180002f77  bt      eax, 0Eh
0x180002f7b  jnb     short loc_180002FD8
0x180002f7d  mov     rcx, [rbx+10h]; hwndCallback
0x180002f81  or      eax, 20h
0x180002f84  mov     [rbx+4], eax
0x180002f87  test    rcx, rcx
0x180002f8a  jz      short loc_180002FA2
0x180002f8c  mov     edx, [rbx]; wDeviceID
0x180002f8e  mov     r8d, 1; uStatus
0x180002f94  call    cs:__imp_mciDriverNotify
0x180002f9a  mov     qword ptr [rbx+10h], 0
0x180002fa2  call    TaskBlock
0x180002fa7  cmp     eax, 401h
0x180002fac  jnz     short loc_180002FA2
0x180002fae  lea     rcx, CritSec; lpCriticalSection
0x180002fb5  call    cs:__imp_LeaveCriticalSection
0x180002fbb  mov     ecx, 0Ah; dwMilliseconds
0x180002fc0  call    cs:__imp_Sleep
0x180002fc6  lea     rcx, CritSec; lpCriticalSection
0x180002fcd  call    cs:__imp_EnterCriticalSection
0x180002fd3  jmp     loc_180002D64
0x180002fd8  and     dword ptr [rbx+4], 0FFFFFFFEh
0x180002fdc  mov     eax, edi
0x180002fde  add     rsp, 38h
0x180002fe2  pop     r15
0x180002fe4  pop     r14
0x180002fe6  pop     r13
0x180002fe8  pop     r12
0x180002fea  pop     rdi
0x180002feb  pop     rsi
0x180002fec  pop     rbp
0x180002fed  pop     rbx
0x180002fee  retn
```
