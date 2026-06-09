# ActiveThreadsTracker

- ea: `0x140076320`
- end: `0x14007655e`
- name: `ActiveThreadsTracker`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14006b020`

## callees

- `0x140076320`
- `0x1400e9dc6`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x140076507`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x140076507`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x140076421`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x1400764dd`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x140076421`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x1400764dd`
- `mmcbase!?GetMainThreadID@SC@mmcerror@@SAKXZ` at `0x1400764f0`
- `mmcbase!?GetMainThreadID@SC@mmcerror@@SAKXZ` at `0x1400764f0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400763e1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14007649b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1400763e1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14007649b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400764f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400764f8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1400763cb`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x140076482`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1400763cb`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x140076482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007640b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400764c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007640b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400764c8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140076348`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400763a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14007645b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140076348`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400763a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14007645b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14007654d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400eef29`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14007654d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400eef29`

## pseudocode

```c
__int64 __fastcall ActiveThreadsTracker(__int64 a1, DWORD a2, char a3)
{
  int v6; // esi
  __int64 v8; // rbx
  __int64 v9; // rdi
  HANDLE v10; // r14
  DWORD v11; // eax
  void *v12; // rcx
  __int64 v13; // rbx
  HANDLE v14; // r14
  DWORD v15; // eax
  int MainThreadID; // ebx
  _QWORD *v17; // rcx
  __int64 v18; // [rsp+0h] [rbp-68h] BYREF
  int v19; // [rsp+20h] [rbp-48h]
  __int64 v20; // [rsp+28h] [rbp-40h]
  __int64 v21; // [rsp+30h] [rbp-38h]
  __int64 *v22; // [rsp+38h] [rbp-30h]
  DWORD ExitCode; // [rsp+78h] [rbp+10h] BYREF
  DWORD v24; // [rsp+88h] [rbp+20h] BYREF

  v22 = &v18;
  v6 = 0;
  if ( WaitForSingleObject(g_hThreadTrackerMutex, a2) )
    return 0xFFFFFFFFLL;
  if ( a1 )
  {
    MainThreadID = mmcerror::SC::GetMainThreadID();
    if ( GetCurrentThreadId() != MainThreadID )
    {
      v17 = operator new(0x18u);
      if ( v17 )
      {
        *(_OWORD *)v17 = 0;
        v17[2] = 0;
      }
      else
      {
        v17 = 0;
      }
      *v17 = a1;
      v17[2] = qword_140161B98;
      *((_WORD *)v17 + 4) = 0;
      qword_140161B98 = (__int64)v17;
      ++dword_140161B90;
    }
  }
  else
  {
    v8 = qword_140161B98;
    if ( !qword_140161B98 )
    {
      local_unwind_0(v22, &loc_14007638E);
      return 0;
    }
    v20 = qword_140161B98;
    v9 = 0;
    v21 = 0;
    do
    {
      v10 = *(HANDLE *)v8;
      if ( !WaitForSingleObject(*(HANDLE *)v8, a2) )
        goto LABEL_41;
      v11 = 259;
      ExitCode = 259;
      if ( a3 )
      {
        if ( !*(_BYTE *)(v8 + 9) )
          *(_BYTE *)(v8 + 9) = TerminateThread(v10, 0xFFFFFFFF);
        GetExitCodeThread(v10, &ExitCode);
        v11 = ExitCode;
      }
      if ( v11 == 259 )
      {
        v19 = ++v6;
        v9 = v8;
        v21 = v8;
      }
      else
      {
LABEL_41:
        if ( !*(_BYTE *)(v8 + 8) )
        {
          CloseHandle(v10);
          *(_BYTE *)(v8 + 8) = 1;
        }
        v12 = (void *)v8;
        v8 = *(_QWORD *)(v8 + 16);
        v20 = v8;
        operator delete(v12);
      }
    }
    while ( !v9 && v8 );
    qword_140161B98 = v9;
    while ( v9 )
    {
      v13 = *(_QWORD *)(v9 + 16);
      if ( !v13 )
        break;
      v14 = *(HANDLE *)v13;
      if ( !WaitForSingleObject(*(HANDLE *)v13, a2) )
        goto LABEL_42;
      v15 = 259;
      v24 = 259;
      if ( a3 )
      {
        if ( !*(_BYTE *)(v13 + 9) )
          *(_BYTE *)(v13 + 9) = TerminateThread(v14, 0xFFFFFFFF);
        GetExitCodeThread(v14, &v24);
        v15 = v24;
      }
      if ( v15 == 259 )
      {
        v19 = ++v6;
        v9 = v13;
        v21 = v13;
      }
      else
      {
LABEL_42:
        if ( !*(_BYTE *)(v13 + 8) )
        {
          CloseHandle(v14);
          *(_BYTE *)(v13 + 8) = 1;
        }
        *(_QWORD *)(v9 + 16) = *(_QWORD *)(v13 + 16);
        operator delete((void *)v13);
      }
    }
    dword_140161B90 = v6;
  }
  ReleaseMutex(g_hThreadTrackerMutex);
  return (unsigned int)dword_140161B90;
}

```

## disassembly

```asm
0x140076320  mov     [rsp+arg_0], rbx
0x140076325  push    rsi
0x140076326  push    rdi
0x140076327  push    r12
0x140076329  push    r14
0x14007632b  push    r15
0x14007632d  sub     rsp, 40h
0x140076331  mov     [rsp+68h+var_30], rsp
0x140076336  mov     r12b, r8b
0x140076339  mov     r15d, edx
0x14007633c  mov     rdi, rcx
0x14007633f  xor     esi, esi
0x140076341  mov     rcx, cs:?g_hThreadTrackerMutex@@3PEAXEA; hHandle
0x140076348  call    cs:__imp_WaitForSingleObject
0x14007634e  test    eax, eax
0x140076350  jz      short loc_140076367
0x140076352  or      eax, 0FFFFFFFFh
0x140076355  mov     rbx, [rsp+68h+arg_0]
0x14007635a  add     rsp, 40h
0x14007635e  pop     r15
0x140076360  pop     r14
0x140076362  pop     r12
0x140076364  pop     rdi
0x140076365  pop     rsi
0x140076366  retn
0x140076367  test    rdi, rdi
0x14007636a  jnz     loc_1400764F0
0x140076370  mov     rbx, cs:qword_140161B98
0x140076377  test    rbx, rbx
0x14007637a  jnz     short loc_140076392
0x14007637c  lea     rdx, loc_14007638E
0x140076383  mov     rcx, [rsp+68h+var_30]
0x140076388  call    _local_unwind_0
0x14007638d  nop
0x14007638e  xor     eax, eax
0x140076390  jmp     short loc_140076355
0x140076392  mov     [rsp+68h+var_40], rbx
0x140076397  xor     edi, edi
0x140076399  mov     [rsp+68h+var_38], rdi
0x14007639e  mov     r14, [rbx]
0x1400763a1  mov     edx, r15d; dwMilliseconds
0x1400763a4  mov     rcx, r14; hHandle
0x1400763a7  call    cs:__imp_WaitForSingleObject
0x1400763ad  test    eax, eax
0x1400763af  jz      short loc_140076402
0x1400763b1  mov     eax, 103h
0x1400763b6  mov     [rsp+68h+ExitCode], eax
0x1400763ba  test    r12b, r12b
0x1400763bd  jz      short loc_1400763EB
0x1400763bf  cmp     byte ptr [rbx+9], 0
0x1400763c3  jnz     short loc_1400763D9
0x1400763c5  or      edx, 0FFFFFFFFh; dwExitCode
0x1400763c8  mov     rcx, r14; hThread
0x1400763cb  call    cs:__imp_TerminateThread
0x1400763d1  test    eax, eax
0x1400763d3  setnz   al
0x1400763d6  mov     [rbx+9], al
0x1400763d9  lea     rdx, [rsp+68h+ExitCode]; lpExitCode
0x1400763de  mov     rcx, r14; hThread
0x1400763e1  call    cs:__imp_GetExitCodeThread
0x1400763e7  mov     eax, [rsp+68h+ExitCode]
0x1400763eb  cmp     eax, 103h
0x1400763f0  jnz     short loc_140076402
0x1400763f2  inc     esi
0x1400763f4  mov     [rsp+68h+var_48], esi
0x1400763f8  mov     rdi, rbx
0x1400763fb  mov     [rsp+68h+var_38], rbx
0x140076400  jmp     short loc_140076427
0x140076402  cmp     byte ptr [rbx+8], 0
0x140076406  jnz     short loc_140076415
0x140076408  mov     rcx, r14; hObject
0x14007640b  call    cs:__imp_CloseHandle
0x140076411  mov     byte ptr [rbx+8], 1
0x140076415  mov     rcx, rbx
0x140076418  mov     rbx, [rbx+10h]
0x14007641c  mov     [rsp+68h+var_40], rbx
0x140076421  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140076427  test    rdi, rdi
0x14007642a  jnz     short loc_140076435
0x14007642c  test    rbx, rbx
0x14007642f  jnz     loc_14007639E
0x140076435  mov     cs:qword_140161B98, rdi
0x14007643c  test    rdi, rdi
0x14007643f  jz      loc_1400764E8
0x140076445  mov     rbx, [rdi+10h]
0x140076449  test    rbx, rbx
0x14007644c  jz      loc_1400764E8
0x140076452  mov     r14, [rbx]
0x140076455  mov     edx, r15d; dwMilliseconds
0x140076458  mov     rcx, r14; hHandle
0x14007645b  call    cs:__imp_WaitForSingleObject
0x140076461  test    eax, eax
0x140076463  jz      short loc_1400764BF
0x140076465  mov     eax, 103h
0x14007646a  mov     [rsp+68h+arg_18], eax
0x140076471  test    r12b, r12b
0x140076474  jz      short loc_1400764A8
0x140076476  cmp     byte ptr [rbx+9], 0
0x14007647a  jnz     short loc_140076490
0x14007647c  or      edx, 0FFFFFFFFh; dwExitCode
0x14007647f  mov     rcx, r14; hThread
0x140076482  call    cs:__imp_TerminateThread
0x140076488  test    eax, eax
0x14007648a  setnz   al
0x14007648d  mov     [rbx+9], al
0x140076490  lea     rdx, [rsp+68h+arg_18]; lpExitCode
0x140076498  mov     rcx, r14; hThread
0x14007649b  call    cs:__imp_GetExitCodeThread
0x1400764a1  mov     eax, [rsp+68h+arg_18]
0x1400764a8  cmp     eax, 103h
0x1400764ad  jnz     short loc_1400764BF
0x1400764af  inc     esi
0x1400764b1  mov     [rsp+68h+var_48], esi
0x1400764b5  mov     rdi, rbx
0x1400764b8  mov     [rsp+68h+var_38], rbx
0x1400764bd  jmp     short loc_1400764E3
0x1400764bf  cmp     byte ptr [rbx+8], 0
0x1400764c3  jnz     short loc_1400764D2
0x1400764c5  mov     rcx, r14; hObject
0x1400764c8  call    cs:__imp_CloseHandle
0x1400764ce  mov     byte ptr [rbx+8], 1
0x1400764d2  mov     rax, [rbx+10h]
0x1400764d6  mov     rcx, rbx
0x1400764d9  mov     [rdi+10h], rax
0x1400764dd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400764e3  jmp     loc_14007643C
0x1400764e8  mov     cs:dword_140161B90, esi
0x1400764ee  jmp     short loc_140076546
0x1400764f0  call    cs:__imp_?GetMainThreadID@SC@mmcerror@@SAKXZ; mmcerror::SC::GetMainThreadID(void)
0x1400764f6  mov     ebx, eax
0x1400764f8  call    cs:__imp_GetCurrentThreadId
0x1400764fe  cmp     eax, ebx
0x140076500  jz      short loc_140076546
0x140076502  mov     ecx, 18h
0x140076507  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007650d  mov     rcx, rax
0x140076510  test    rax, rax
0x140076513  jz      short loc_140076523
0x140076515  xorps   xmm0, xmm0
0x140076518  xor     eax, eax
0x14007651a  movups  xmmword ptr [rcx], xmm0
0x14007651d  mov     [rcx+10h], rax
0x140076521  jmp     short loc_140076525
0x140076523  xor     ecx, ecx
0x140076525  mov     [rcx], rdi
0x140076528  mov     rax, cs:qword_140161B98
0x14007652f  mov     [rcx+10h], rax
0x140076533  mov     word ptr [rcx+8], 0
0x140076539  mov     cs:qword_140161B98, rcx
0x140076540  inc     cs:dword_140161B90
0x140076546  mov     rcx, cs:?g_hThreadTrackerMutex@@3PEAXEA; hMutex
0x14007654d  call    cs:__imp_ReleaseMutex
0x140076553  mov     eax, cs:dword_140161B90
0x140076559  jmp     loc_140076355
0x1400eef19  push    rbp
0x1400eef1b  sub     rsp, 20h
0x1400eef1f  mov     rbp, rdx
0x1400eef22  mov     rcx, cs:?g_hThreadTrackerMutex@@3PEAXEA; hMutex
0x1400eef29  call    cs:__imp_ReleaseMutex
0x1400eef2f  nop
0x1400eef30  add     rsp, 20h
0x1400eef34  pop     rbp
0x1400eef35  retn
```
