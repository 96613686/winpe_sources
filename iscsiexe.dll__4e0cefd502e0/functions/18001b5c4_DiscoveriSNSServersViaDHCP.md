# DiscoveriSNSServersViaDHCP

- ea: `0x18001b5c4`
- end: `0x18001b779`
- name: `DiscoveriSNSServersViaDHCP`
- size: `437`
- prototype: `__int64 __fastcall(__int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009408`

## callees

- `0x180001cfe`
- `0x18001b5c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b6da`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b719`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b6da`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b719`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b633`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b680`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b633`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001b680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b70a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b70a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b601`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b601`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b645`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b74f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b75d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b645`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b74f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b75d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001b6b4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001b6b4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001b6fa`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001b6fa`

## pseudocode

```c
__int64 __fastcall DiscoveriSNSServersViaDHCP(__int64 *a1, _DWORD *a2)
{
  unsigned int v5; // ebp
  __int64 *v6; // rax
  HANDLE *v7; // rax
  HANDLE *v8; // r12
  DWORD LastError; // edi
  __int64 *v10; // r14
  __int64 v11; // rsi
  _QWORD *v12; // rax
  void *v13; // r13
  HANDLE v14; // rax
  __int64 v15; // rbp
  __int64 *v16; // rcx
  int v17; // edx
  bool v18; // zf
  int v19; // eax
  DWORD ThreadId; // [rsp+80h] [rbp+8h] BYREF

  ThreadId = 0;
  if ( !a1 )
    return 87;
  v5 = 0;
  if ( a2 )
    *a2 = 0;
  WaitForSingleObject((HANDLE)a1[2], 0xFFFFFFFF);
  v6 = (__int64 *)*a1;
  if ( !*a1 )
    goto LABEL_33;
  do
  {
    if ( v6 == a1 )
      break;
    v6 = (__int64 *)*v6;
    ++v5;
  }
  while ( v6 );
  if ( v5 )
  {
    v7 = (HANDLE *)malloc(8LL * v5);
    v8 = v7;
    if ( v7 )
    {
      LastError = 0;
      memset_0(v7, 0, 8LL * v5);
      v10 = (__int64 *)*a1;
      v11 = 0;
      if ( *a1 )
      {
        while ( v10 != a1 && (unsigned int)v11 < v5 )
        {
          v12 = malloc(0x10u);
          v13 = v12;
          if ( !v12 )
          {
            LastError = 8;
            break;
          }
          *v12 = a1;
          v12[1] = v10;
          v14 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)DiscoveriSNSServersThreadRoutine, v12, 0, &ThreadId);
          v8[v11] = v14;
          if ( !v14 )
          {
            LastError = GetLastError();
            free(v13);
            break;
          }
          v10 = (__int64 *)*v10;
          v11 = (unsigned int)(v11 + 1);
          if ( !v10 )
            break;
        }
        if ( (_DWORD)v11 )
        {
          WaitForMultipleObjects(v11, v8, 1, 0xFFFFFFFF);
          v15 = 0;
          do
          {
            CloseHandle(v8[v15]);
            v15 = (unsigned int)(v15 + 1);
          }
          while ( (unsigned int)v15 < (unsigned int)v11 );
        }
      }
      free(v8);
      if ( !LastError && a2 )
      {
        v16 = (__int64 *)*a1;
        v17 = 0;
        while ( v16 && v16 != a1 )
        {
          v18 = *((_DWORD *)v16 + 7) == 0;
          v19 = v17 + 1;
          v16 = (__int64 *)*v16;
          if ( v18 )
            v19 = v17;
          v17 = v19;
        }
        *a2 = v17;
      }
      ReleaseMutex((HANDLE)a1[2]);
      return LastError;
    }
    else
    {
      ReleaseMutex((HANDLE)a1[2]);
      return 8;
    }
  }
  else
  {
LABEL_33:
    ReleaseMutex((HANDLE)a1[2]);
    return 232;
  }
}

```

## disassembly

```asm
0x18001b5c4  mov     rax, rsp
0x18001b5c7  push    rbx
0x18001b5c8  push    rbp
0x18001b5c9  push    rsi
0x18001b5ca  push    rdi
0x18001b5cb  push    r12
0x18001b5cd  push    r13
0x18001b5cf  push    r14
0x18001b5d1  push    r15
0x18001b5d3  sub     rsp, 38h
0x18001b5d7  mov     dword ptr [rax+8], 0
0x18001b5de  mov     r15, rdx
0x18001b5e1  mov     rbx, rcx
0x18001b5e4  test    rcx, rcx
0x18001b5e7  jnz     short loc_18001B5F1
0x18001b5e9  lea     eax, [rcx+57h]
0x18001b5ec  jmp     loc_18001B768
0x18001b5f1  xor     ebp, ebp
0x18001b5f3  test    r15, r15
0x18001b5f6  jz      short loc_18001B5FA
0x18001b5f8  mov     [rdx], ebp
0x18001b5fa  mov     rcx, [rcx+10h]; hHandle
0x18001b5fe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b601  call    cs:__imp_WaitForSingleObject
0x18001b607  mov     rax, [rbx]
0x18001b60a  test    rax, rax
0x18001b60d  jz      loc_18001B759
0x18001b613  cmp     rax, rbx
0x18001b616  jz      short loc_18001B622
0x18001b618  mov     rax, [rax]
0x18001b61b  inc     ebp
0x18001b61d  test    rax, rax
0x18001b620  jnz     short loc_18001B613
0x18001b622  test    ebp, ebp
0x18001b624  jz      loc_18001B759
0x18001b62a  mov     esi, ebp
0x18001b62c  shl     rsi, 3
0x18001b630  mov     rcx, rsi; Size
0x18001b633  call    cs:__imp_malloc
0x18001b639  mov     r12, rax
0x18001b63c  test    rax, rax
0x18001b63f  jnz     short loc_18001B655
0x18001b641  mov     rcx, [rbx+10h]; hMutex
0x18001b645  call    cs:__imp_ReleaseMutex
0x18001b64b  lea     eax, [r12+8]
0x18001b650  jmp     loc_18001B768
0x18001b655  mov     r8, rsi; Size
0x18001b658  xor     edx, edx; Val
0x18001b65a  mov     rcx, r12; void *
0x18001b65d  xor     edi, edi
0x18001b65f  call    memset_0
0x18001b664  mov     r14, [rbx]
0x18001b667  xor     esi, esi
0x18001b669  test    r14, r14
0x18001b66c  jz      loc_18001B716
0x18001b672  cmp     r14, rbx
0x18001b675  jz      short loc_18001B6E7
0x18001b677  cmp     esi, ebp
0x18001b679  jnb     short loc_18001B6E7
0x18001b67b  mov     ecx, 10h; Size
0x18001b680  call    cs:__imp_malloc
0x18001b686  mov     r13, rax
0x18001b689  test    rax, rax
0x18001b68c  jz      short loc_18001B6E2
0x18001b68e  mov     [rax], rbx
0x18001b691  lea     r8, DiscoveriSNSServersThreadRoutine; lpStartAddress
0x18001b698  mov     [rax+8], r14
0x18001b69c  mov     r9, r13; lpParameter
0x18001b69f  lea     rax, [rsp+78h+ThreadId]
0x18001b6a7  xor     edx, edx; dwStackSize
0x18001b6a9  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18001b6ae  xor     ecx, ecx; lpThreadAttributes
0x18001b6b0  mov     [rsp+78h+dwCreationFlags], edi; dwCreationFlags
0x18001b6b4  call    cs:__imp_CreateThread
0x18001b6ba  mov     [r12+rsi*8], rax
0x18001b6be  test    rax, rax
0x18001b6c1  jz      short loc_18001B6CF
0x18001b6c3  mov     r14, [r14]
0x18001b6c6  inc     esi
0x18001b6c8  test    r14, r14
0x18001b6cb  jnz     short loc_18001B672
0x18001b6cd  jmp     short loc_18001B6E7
0x18001b6cf  call    cs:__imp_GetLastError
0x18001b6d5  mov     rcx, r13; Block
0x18001b6d8  mov     edi, eax
0x18001b6da  call    cs:__imp_free
0x18001b6e0  jmp     short loc_18001B6E7
0x18001b6e2  mov     edi, 8
0x18001b6e7  test    esi, esi
0x18001b6e9  jz      short loc_18001B716
0x18001b6eb  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001b6ef  mov     r8d, 1; bWaitAll
0x18001b6f5  mov     rdx, r12; lpHandles
0x18001b6f8  mov     ecx, esi; nCount
0x18001b6fa  call    cs:__imp_WaitForMultipleObjects
0x18001b700  xor     ebp, ebp
0x18001b702  test    esi, esi
0x18001b704  jz      short loc_18001B716
0x18001b706  mov     rcx, [r12+rbp*8]; hObject
0x18001b70a  call    cs:__imp_CloseHandle
0x18001b710  inc     ebp
0x18001b712  cmp     ebp, esi
0x18001b714  jb      short loc_18001B706
0x18001b716  mov     rcx, r12; Block
0x18001b719  call    cs:__imp_free
0x18001b71f  test    edi, edi
0x18001b721  jnz     short loc_18001B74B
0x18001b723  test    r15, r15
0x18001b726  jz      short loc_18001B74B
0x18001b728  mov     rcx, [rbx]
0x18001b72b  xor     edx, edx
0x18001b72d  jmp     short loc_18001B743
0x18001b72f  cmp     rcx, rbx
0x18001b732  jz      short loc_18001B748
0x18001b734  cmp     dword ptr [rcx+1Ch], 0
0x18001b738  lea     eax, [rdx+1]
0x18001b73b  mov     rcx, [rcx]
0x18001b73e  cmovz   eax, edx
0x18001b741  mov     edx, eax
0x18001b743  test    rcx, rcx
0x18001b746  jnz     short loc_18001B72F
0x18001b748  mov     [r15], edx
0x18001b74b  mov     rcx, [rbx+10h]; hMutex
0x18001b74f  call    cs:__imp_ReleaseMutex
0x18001b755  mov     eax, edi
0x18001b757  jmp     short loc_18001B768
0x18001b759  mov     rcx, [rbx+10h]; hMutex
0x18001b75d  call    cs:__imp_ReleaseMutex
0x18001b763  mov     eax, 0E8h
0x18001b768  add     rsp, 38h
0x18001b76c  pop     r15
0x18001b76e  pop     r14
0x18001b770  pop     r13
0x18001b772  pop     r12
0x18001b774  pop     rdi
0x18001b775  pop     rsi
0x18001b776  pop     rbp
0x18001b777  pop     rbx
0x18001b778  retn
```
