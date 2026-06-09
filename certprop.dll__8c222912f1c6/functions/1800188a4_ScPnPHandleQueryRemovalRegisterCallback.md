# ScPnPHandleQueryRemovalRegisterCallback

- ea: `0x1800188a4`
- end: `0x18001896e`
- name: `ScPnPHandleQueryRemovalRegisterCallback`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000aa00`

## callees

- `0x180004600`
- `0x1800188a4`
- `0x180018b58`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001895d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001895d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001892d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001892d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800188c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800188c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018950`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018938`

## pseudocode

```c
__int64 __fastcall ScPnPHandleQueryRemovalRegisterCallback(int a1, __int64 a2)
{
  DWORD LastError; // ebx
  LPVOID v5; // rax
  __int64 v6; // rcx
  void *v7; // rdi
  struct _TP_WORK *ThreadpoolWork; // rax

  LastError = 8;
  v5 = HeapAlloc(g_hHeap, 8u, 0x18u);
  v7 = v5;
  if ( v5 )
  {
    *((_DWORD *)v5 + 2) = a1;
    *((_QWORD *)v5 + 2) = a2;
    ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)ScPnPHandleQueryRemoval, v5, &g_TpEnvironment);
    if ( ThreadpoolWork )
    {
      LastError = 0;
      SubmitThreadpoolWork(ThreadpoolWork);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
        HeapFree(g_hHeap, 0, v7);
    }
  }
  else
  {
    WppTraceIndent(v6, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800188a4  push    rbx
0x1800188a6  push    rbp
0x1800188a7  push    rsi
0x1800188a8  push    rdi
0x1800188a9  sub     rsp, 28h
0x1800188ad  mov     ebx, 8
0x1800188b2  mov     rsi, rdx
0x1800188b5  mov     ebp, ecx
0x1800188b7  mov     edx, ebx; dwFlags
0x1800188b9  mov     rcx, cs:g_hHeap; hHeap
0x1800188c0  lea     r8d, [rbx+10h]; dwBytes
0x1800188c4  call    cs:__imp_HeapAlloc
0x1800188ca  mov     rdi, rax
0x1800188cd  test    rax, rax
0x1800188d0  jnz     short loc_180018915
0x1800188d2  lea     edx, [rbx-6]
0x1800188d5  call    WppTraceIndent
0x1800188da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188e1  lea     rax, WPP_GLOBAL_Control
0x1800188e8  cmp     rcx, rax
0x1800188eb  jz      short loc_180018963
0x1800188ed  test    byte ptr [rcx+1Ch], 1
0x1800188f1  jz      short loc_180018963
0x1800188f3  cmp     byte ptr [rcx+19h], 2
0x1800188f7  jb      short loc_180018963
0x1800188f9  mov     r9, cs:WPP_pszIndent
0x180018900  lea     edx, [rbx+41h]
0x180018903  mov     rcx, [rcx+10h]
0x180018907  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18001890e  call    WPP_SF_s
0x180018913  jmp     short loc_180018963
0x180018915  lea     r8, g_TpEnvironment; pcbe
0x18001891c  mov     [rax+8], ebp
0x18001891f  mov     rdx, rdi; pv
0x180018922  mov     [rax+10h], rsi
0x180018926  lea     rcx, ScPnPHandleQueryRemoval; pfnwk
0x18001892d  call    cs:__imp_CreateThreadpoolWork
0x180018933  test    rax, rax
0x180018936  jnz     short loc_180018958
0x180018938  call    cs:__imp_GetLastError
0x18001893e  mov     ebx, eax
0x180018940  test    eax, eax
0x180018942  jz      short loc_180018963
0x180018944  mov     rcx, cs:g_hHeap; hHeap
0x18001894b  mov     r8, rdi; lpMem
0x18001894e  xor     edx, edx; dwFlags
0x180018950  call    cs:__imp_HeapFree
0x180018956  jmp     short loc_180018963
0x180018958  xor     ebx, ebx
0x18001895a  mov     rcx, rax; pwk
0x18001895d  call    cs:__imp_SubmitThreadpoolWork
0x180018963  mov     eax, ebx
0x180018965  add     rsp, 28h
0x180018969  pop     rdi
0x18001896a  pop     rsi
0x18001896b  pop     rbp
0x18001896c  pop     rbx
0x18001896d  retn
```
