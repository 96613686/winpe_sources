# mciStreamCycle

- ea: `0x180002a90`
- end: `0x180002d87`
- name: `mciStreamCycle`
- size: `759`
- prototype: `void __fastcall(DWORD_PTR dwInst)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180002a90`
- `0x180002d90`
- `0x180005270`
- `0x180005e7c`
- `0x180005ea4`
- `0x180005ff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ad0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ad0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cf5`
- `USER32!GetDesktopWindow` at `0x180002ad6`
- `USER32!GetDesktopWindow` at `0x180002ad6`
- `USER32!PostThreadMessageW` at `0x180002b57`
- `USER32!PostThreadMessageW` at `0x180002b57`
- `WINMM!mmioRead` at `0x180002c36`
- `WINMM!mmioRead` at `0x180002c36`
- `WINMM!mmGetCurrentTask` at `0x180002ae5`
- `WINMM!mmGetCurrentTask` at `0x180002ae5`
- `WINMM!mmioClose` at `0x180002d49`
- `WINMM!mmioClose` at `0x180002d49`
- `WINMM!mmioSeek` at `0x180002be8`
- `WINMM!mmioSeek` at `0x180002be8`

## pseudocode

```c
void __fastcall mciStreamCycle(DWORD_PTR dwInst)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 i; // rdi
  __int64 j; // rsi
  __int64 v8; // rdi
  int v9; // edx
  __int64 v10; // rax
  _DWORD *v11; // rdi
  __int64 v12; // r14
  __int64 v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  LONG v17; // ebp
  __int64 v18; // r8
  DWORD_PTR v19; // rdx
  __int64 v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  struct _MMCKINFO pmmcki; // [rsp+20h] [rbp-88h] BYREF
  _OWORD v25[3]; // [rsp+38h] [rbp-70h] BYREF
  __int64 v26; // [rsp+68h] [rbp-40h]

  memset(&pmmcki, 0, sizeof(pmmcki));
  EnterCriticalSection(&SeqCritSec);
  GetDesktopWindow();
  if ( !*(_DWORD *)(dwInst + 304) )
    *(_DWORD *)(dwInst + 304) = mmGetCurrentTask();
  *(_QWORD *)(dwInst + 264) = msOpenFile((LPWSTR)dwInst, &pmmcki, *(MMIOPROC **)(dwInst + 272));
  v4 = *(&arrayOfLists + 2 * *(unsigned int *)(dwInst + 296) + 1);
  v5 = v4 + 16;
  for ( i = (v4 + 16) & -(__int64)(v4 != 0); i; i = v8 + 16 )
  {
    for ( j = 0; j != 2; ++j )
    {
      *(_WORD *)(*(_QWORD *)(i + 8 * j + 16) + 12LL) |= 1u;
      PostThreadMessageW(*(_DWORD *)(dwInst + 304), 0x402u, 0, 0);
    }
    v8 = *(_QWORD *)(i - 16);
    if ( !v8 )
      break;
  }
  TaskBlock(v5, v2, v3);
  v9 = *(_DWORD *)(dwInst + 300);
  do
  {
    v10 = *(&arrayOfLists + 2 * *(unsigned int *)(dwInst + 296) + 1);
    v11 = (_DWORD *)((v10 + 16) & -(__int64)(v10 != 0));
    while ( v11 )
    {
      v9 = *(_DWORD *)(dwInst + 300);
      if ( !v9 )
        break;
      v12 = 0;
      v13 = 2;
      do
      {
        if ( (*(_BYTE *)(*(_QWORD *)&v11[2 * v13] + 12LL) & 1) != 0 && *(_DWORD *)(dwInst + 300) )
        {
          mmioSeek(*(HMMIO *)(dwInst + 264), v11[2], 0);
          v16 = 65528;
          v17 = v11[1] - v11[2] + 1;
          if ( (unsigned int)v17 > 0x200 )
            v17 = 512;
          *(_WORD *)(*(_QWORD *)&v11[2 * v13] + 12LL) &= 0xFFF8u;
          if ( v17 <= 0 )
          {
LABEL_27:
            while ( *(_DWORD *)(dwInst + 300) )
            {
              memset(v25, 0, sizeof(v25));
              v26 = 0;
              if ( (unsigned int)TaskBlock(v16, v14, v15) != 1024 )
                break;
              midiSeqMessage(*(_QWORD *)(dwInst + 256), 0xBu, (__int64)v25, 0);
              if ( !DWORD2(v25[0]) )
              {
                v18 = 0;
                v19 = 13;
                goto LABEL_26;
              }
            }
            if ( *(_DWORD *)(dwInst + 300) )
            {
              LeaveSeq(v16, v14, v15);
              EnterCriticalSection(&SeqCritSec);
            }
          }
          else
          {
            if ( v11[2] == *v11 )
              *(_WORD *)(*(_QWORD *)&v11[2 * v13] + 12LL) |= 2u;
            mmioRead(*(HMMIO *)(dwInst + 264), **(HPSTR **)&v11[2 * v13], v17);
            *(_DWORD *)(*(_QWORD *)&v11[2 * v13] + 8LL) = v17;
            v11[2] += v17;
            *(_DWORD *)(*(_QWORD *)&v11[2 * v13] + 24LL) = v11[2] + ~*v11;
            if ( v11[2] > v11[1] )
              *(_WORD *)(*(_QWORD *)&v11[2 * v13] + 12LL) |= 4u;
            if ( *(_DWORD *)(dwInst + 300) )
            {
              v18 = *(_QWORD *)&v11[2 * v13];
              v19 = 10;
LABEL_26:
              midiSeqMessage(*(_QWORD *)(dwInst + 256), v19, v18, 0);
              goto LABEL_27;
            }
          }
        }
        ++v12;
        ++v13;
      }
      while ( v12 != 2 );
      v9 = *(_DWORD *)(dwInst + 300);
      if ( v9 )
      {
        v20 = *((_QWORD *)v11 - 2);
        if ( v20 )
          v11 = (_DWORD *)(v20 + 16);
        else
          v11 = 0;
      }
    }
  }
  while ( v9 );
  mmioClose(*(HMMIO *)(dwInst + 264), 0);
  *(_DWORD *)(dwInst + 304) = 0;
  LeaveSeq(v22, v21, v23);
}

```

## disassembly

```asm
0x180002a90  mov     [rsp+arg_8], rbx
0x180002a95  mov     [rsp+arg_10], rbp
0x180002a9a  push    rsi
0x180002a9b  push    rdi
0x180002a9c  push    r12
0x180002a9e  push    r13
0x180002aa0  push    r14
0x180002aa2  sub     rsp, 80h
0x180002aa9  mov     rax, cs:__security_cookie
0x180002ab0  xor     rax, rsp
0x180002ab3  mov     [rsp+0A8h+var_38], rax
0x180002ab8  mov     rbx, rcx
0x180002abb  xorps   xmm0, xmm0
0x180002abe  xor     eax, eax
0x180002ac0  lea     rcx, SeqCritSec; lpCriticalSection
0x180002ac7  movups  xmmword ptr [rsp+0A8h+pmmcki.ckid], xmm0
0x180002acc  mov     [rsp+0A8h+pmmcki.dwFlags], eax
0x180002ad0  call    cs:__imp_EnterCriticalSection
0x180002ad6  call    cs:__imp_GetDesktopWindow
0x180002adc  cmp     dword ptr [rbx+130h], 0
0x180002ae3  jnz     short loc_180002AF1
0x180002ae5  call    cs:__imp_mmGetCurrentTask
0x180002aeb  mov     [rbx+130h], eax
0x180002af1  mov     r8, [rbx+110h]
0x180002af8  lea     rdx, [rsp+0A8h+pmmcki]; pmmcki
0x180002afd  mov     rcx, rbx; pszFileName
0x180002b00  call    msOpenFile
0x180002b05  mov     [rbx+108h], rax
0x180002b0c  lea     rsi, arrayOfLists
0x180002b13  mov     eax, [rbx+128h]
0x180002b19  mov     r13d, 1
0x180002b1f  add     rax, rax
0x180002b22  lea     r12d, [r13+1]
0x180002b26  mov     rax, [rsi+rax*8+8]
0x180002b2b  lea     rcx, [rax+10h]
0x180002b2f  neg     rax
0x180002b32  sbb     rdi, rdi
0x180002b35  and     rdi, rcx
0x180002b38  jz      short loc_180002B80
0x180002b3a  xor     esi, esi
0x180002b3c  mov     rax, [rdi+rsi*8+10h]
0x180002b41  xor     r9d, r9d; lParam
0x180002b44  xor     r8d, r8d; wParam
0x180002b47  mov     edx, 402h; Msg
0x180002b4c  or      [rax+0Ch], r13w
0x180002b51  mov     ecx, [rbx+130h]; idThread
0x180002b57  call    cs:__imp_PostThreadMessageW
0x180002b5d  add     rsi, r13
0x180002b60  cmp     rsi, r12
0x180002b63  jnz     short loc_180002B3C
0x180002b65  test    rdi, rdi
0x180002b68  jz      short loc_180002B79
0x180002b6a  mov     rdi, [rdi-10h]
0x180002b6e  test    rdi, rdi
0x180002b71  jz      short loc_180002B79
0x180002b73  add     rdi, 10h
0x180002b77  jnz     short loc_180002B3A
0x180002b79  lea     rsi, arrayOfLists
0x180002b80  call    TaskBlock
0x180002b85  mov     edx, [rbx+12Ch]
0x180002b8b  mov     eax, [rbx+128h]
0x180002b91  add     rax, rax
0x180002b94  mov     rax, [rsi+rax*8+8]
0x180002b99  lea     rcx, [rax+10h]
0x180002b9d  neg     rax
0x180002ba0  sbb     rdi, rdi
0x180002ba3  and     rdi, rcx
0x180002ba6  jz      loc_180002D3A
0x180002bac  mov     edx, [rbx+12Ch]
0x180002bb2  test    edx, edx
0x180002bb4  jz      loc_180002D33
0x180002bba  xor     r14d, r14d
0x180002bbd  mov     rsi, r12
0x180002bc0  mov     rax, [rdi+rsi*8]
0x180002bc4  test    [rax+0Ch], r13b
0x180002bc8  jz      loc_180002CFB
0x180002bce  cmp     dword ptr [rbx+12Ch], 0
0x180002bd5  jz      loc_180002CFB
0x180002bdb  mov     edx, [rdi+8]; lOffset
0x180002bde  xor     r8d, r8d; iOrigin
0x180002be1  mov     rcx, [rbx+108h]; hmmio
0x180002be8  call    cs:__imp_mmioSeek
0x180002bee  mov     ebp, [rdi+4]
0x180002bf1  mov     eax, 200h
0x180002bf6  sub     ebp, [rdi+8]
0x180002bf9  mov     ecx, 0FFF8h
0x180002bfe  inc     ebp
0x180002c00  cmp     ebp, eax
0x180002c02  cmova   ebp, eax
0x180002c05  mov     rax, [rdi+rsi*8]
0x180002c09  and     [rax+0Ch], cx
0x180002c0d  test    ebp, ebp
0x180002c0f  jle     loc_180002CD7
0x180002c15  mov     eax, [rdi]
0x180002c17  cmp     [rdi+8], eax
0x180002c1a  jnz     short loc_180002C25
0x180002c1c  mov     rax, [rdi+rsi*8]
0x180002c20  or      [rax+0Ch], r12w
0x180002c25  mov     rdx, [rdi+rsi*8]
0x180002c29  mov     r8d, ebp; cch
0x180002c2c  mov     rcx, [rbx+108h]; hmmio
0x180002c33  mov     rdx, [rdx]; pch
0x180002c36  call    cs:__imp_mmioRead
0x180002c3c  mov     rax, [rdi+rsi*8]
0x180002c40  mov     [rax+8], ebp
0x180002c43  add     [rdi+8], ebp
0x180002c46  mov     ecx, [rdi]
0x180002c48  mov     rax, [rdi+rsi*8]
0x180002c4c  not     ecx
0x180002c4e  add     ecx, [rdi+8]
0x180002c51  mov     [rax+18h], ecx
0x180002c54  mov     eax, [rdi+4]
0x180002c57  cmp     [rdi+8], eax
0x180002c5a  jbe     short loc_180002C65
0x180002c5c  mov     rax, [rdi+rsi*8]
0x180002c60  or      word ptr [rax+0Ch], 4
0x180002c65  cmp     dword ptr [rbx+12Ch], 0
0x180002c6c  jz      loc_180002CFB
0x180002c72  mov     r8, [rdi+rsi*8]
0x180002c76  mov     edx, 0Ah
0x180002c7b  jmp     short loc_180002CC8
0x180002c7d  xorps   xmm0, xmm0
0x180002c80  xor     eax, eax
0x180002c82  movups  [rsp+0A8h+var_70], xmm0
0x180002c87  mov     [rsp+0A8h+var_40], rax
0x180002c8c  movups  [rsp+0A8h+var_60], xmm0
0x180002c91  movups  [rsp+0A8h+var_50], xmm0
0x180002c96  call    TaskBlock
0x180002c9b  cmp     eax, 400h
0x180002ca0  jnz     short loc_180002CE0
0x180002ca2  mov     rcx, [rbx+100h]; dwUser
0x180002ca9  lea     r8, [rsp+0A8h+var_70]
0x180002cae  xor     r9d, r9d
0x180002cb1  lea     edx, [r9+0Bh]
0x180002cb5  call    midiSeqMessage
0x180002cba  cmp     dword ptr [rsp+0A8h+var_70+8], 0
0x180002cbf  jnz     short loc_180002CD7
0x180002cc1  xor     r8d, r8d
0x180002cc4  lea     edx, [r8+0Dh]
0x180002cc8  mov     rcx, [rbx+100h]; dwUser
0x180002ccf  xor     r9d, r9d
0x180002cd2  call    midiSeqMessage
0x180002cd7  cmp     dword ptr [rbx+12Ch], 0
0x180002cde  jnz     short loc_180002C7D
0x180002ce0  cmp     dword ptr [rbx+12Ch], 0
0x180002ce7  jz      short loc_180002CFB
0x180002ce9  call    LeaveSeq
0x180002cee  lea     rcx, SeqCritSec; lpCriticalSection
0x180002cf5  call    cs:__imp_EnterCriticalSection
0x180002cfb  inc     r14
0x180002cfe  inc     rsi
0x180002d01  cmp     r14, r12
0x180002d04  jnz     loc_180002BC0
0x180002d0a  mov     edx, [rbx+12Ch]; fuClose
0x180002d10  test    edx, edx
0x180002d12  jz      short loc_180002D2A
0x180002d14  test    rdi, rdi
0x180002d17  jz      short loc_180002D28
0x180002d19  mov     rdi, [rdi-10h]
0x180002d1d  test    rdi, rdi
0x180002d20  jz      short loc_180002D28
0x180002d22  add     rdi, 10h
0x180002d26  jmp     short loc_180002D2A
0x180002d28  xor     edi, edi
0x180002d2a  test    rdi, rdi
0x180002d2d  jnz     loc_180002BAC
0x180002d33  lea     rsi, arrayOfLists
0x180002d3a  test    edx, edx
0x180002d3c  jnz     loc_180002B8B
0x180002d42  mov     rcx, [rbx+108h]; hmmio
0x180002d49  call    cs:__imp_mmioClose
0x180002d4f  mov     dword ptr [rbx+130h], 0
0x180002d59  call    LeaveSeq
0x180002d5e  mov     rcx, [rsp+0A8h+var_38]
0x180002d63  xor     rcx, rsp; StackCookie
0x180002d66  call    __security_check_cookie
0x180002d6b  lea     r11, [rsp+0A8h+var_28]
0x180002d73  mov     rbx, [r11+38h]
0x180002d77  mov     rbp, [r11+40h]
0x180002d7b  mov     rsp, r11
0x180002d7e  pop     r14
0x180002d80  pop     r13
0x180002d82  pop     r12
0x180002d84  pop     rdi
0x180002d85  pop     rsi
0x180002d86  retn
```
