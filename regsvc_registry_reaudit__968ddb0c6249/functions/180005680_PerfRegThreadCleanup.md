# PerfRegThreadCleanup

- ea: `0x180005680`
- end: `0x180005785`
- name: `PerfRegThreadCleanup`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180008534`

## callees

- `0x180005680`
- `0x1800072d0`
- `0x180007300`
- `0x180008050`
- `0x1800163f4`
- `0x180016544`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056bc`

## pseudocode

```c
void PerfRegThreadCleanup()
{
  DWORD CurrentThreadId; // esi
  void *v1; // rbx
  _QWORD *v2; // rdi

  if ( g_QueryList )
  {
    if ( NtCurrentTeb()->EtwLocalData )
    {
      if ( g_hGlobalMutex )
      {
        CurrentThreadId = GetCurrentThreadId();
        if ( !PerflibciLocalWaitForMutex(g_hGlobalMutex) )
        {
          v1 = g_QueryList;
          v2 = 0;
          while ( v1 )
          {
            if ( *((_DWORD *)v1 + 6) == CurrentThreadId )
            {
              PerflibciCloseLocalQueryHandle(*(struct _PERF_QUERY **)v1);
              PerflibciFreeLocalQueryHandle(*(void **)v1);
              operator delete(*((void **)v1 + 9));
              operator delete(*((void **)v1 + 7));
              operator delete(*((void **)v1 + 11));
              operator delete(*((void **)v1 + 5));
              if ( v2 )
              {
                v2[1] = *((_QWORD *)v1 + 1);
                operator delete(v1);
                v1 = (void *)v2[1];
              }
              else
              {
                g_QueryList = (void *)*((_QWORD *)v1 + 1);
                operator delete(v1);
                v1 = g_QueryList;
              }
            }
            else
            {
              v2 = v1;
              v1 = (void *)*((_QWORD *)v1 + 1);
            }
          }
          PerflibciLocalReleaseMutex(g_hGlobalMutex);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180005680  sub     rsp, 28h
0x180005684  cmp     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, 0; PERFI_THREAD_QUERY * g_QueryList
0x18000568c  jz      loc_180005780
0x180005692  mov     rax, gs:30h
0x18000569b  cmp     qword ptr [rax+1728h], 0
0x1800056a3  jz      loc_180005780
0x1800056a9  cmp     cs:?g_hGlobalMutex@@3PEAXEA, 0; void * g_hGlobalMutex
0x1800056b1  jz      loc_180005780
0x1800056b7  mov     [rsp+28h+arg_8], rsi
0x1800056bc  call    cs:__imp_GetCurrentThreadId
0x1800056c2  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x1800056c9  mov     esi, eax
0x1800056cb  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x1800056d0  test    eax, eax
0x1800056d2  jnz     loc_18000577B
0x1800056d8  mov     [rsp+28h+arg_0], rbx
0x1800056dd  mov     rbx, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x1800056e4  mov     [rsp+28h+var_8], rdi
0x1800056e9  xor     edi, edi
0x1800056eb  test    rbx, rbx
0x1800056ee  jz      short loc_180005765
0x1800056f0  cmp     [rbx+18h], esi
0x1800056f3  jnz     short loc_180005759
0x1800056f5  mov     rcx, [rbx]; struct _PERF_QUERY *
0x1800056f8  call    PerflibciCloseLocalQueryHandle
0x1800056fd  mov     rcx, [rbx]; Block
0x180005700  call    PerflibciFreeLocalQueryHandle
0x180005705  mov     rcx, [rbx+48h]; Block
0x180005709  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000570e  mov     rcx, [rbx+38h]; Block
0x180005712  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005717  mov     rcx, [rbx+58h]; Block
0x18000571b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005720  mov     rcx, [rbx+28h]; Block
0x180005724  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005729  mov     rax, [rbx+8]
0x18000572d  mov     rcx, rbx; Block
0x180005730  test    rdi, rdi
0x180005733  jnz     short loc_18000574A
0x180005735  mov     cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA, rax; PERFI_THREAD_QUERY * g_QueryList
0x18000573c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005741  mov     rbx, cs:?g_QueryList@@3PEAUPERFI_THREAD_QUERY@@EA; PERFI_THREAD_QUERY * g_QueryList
0x180005748  jmp     short loc_180005760
0x18000574a  mov     [rdi+8], rax
0x18000574e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005753  mov     rbx, [rdi+8]
0x180005757  jmp     short loc_180005760
0x180005759  mov     rdi, rbx
0x18000575c  mov     rbx, [rbx+8]
0x180005760  test    rbx, rbx
0x180005763  jnz     short loc_1800056F0
0x180005765  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x18000576c  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x180005771  mov     rdi, [rsp+28h+var_8]
0x180005776  mov     rbx, [rsp+28h+arg_0]
0x18000577b  mov     rsi, [rsp+28h+arg_8]
0x180005780  add     rsp, 28h
0x180005784  retn
```
