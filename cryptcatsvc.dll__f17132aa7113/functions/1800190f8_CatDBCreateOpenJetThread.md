# _CatDBCreateOpenJetThread

- ea: `0x1800190f8`
- end: `0x18001930e`
- name: `_CatDBCreateOpenJetThread`
- size: `534`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002fd0`
- `0x18001b1c4`
- `0x18001c6b4`

## callees

- `0x1800015b0`
- `0x180003538`
- `0x18000a59c`
- `0x18000be40`
- `0x1800190f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001918d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001918d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800192da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800192da`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800191ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800191ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800191ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800191ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019291`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019291`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192ea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180019257`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180019257`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001927d`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001927d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019226`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019226`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800192bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800192bf`

## pseudocode

```c
__int64 __fastcall CatDBCreateOpenJetThread(int a1, int a2, int a3)
{
  _DWORD *v6; // rax
  unsigned int v7; // edx
  unsigned __int16 *v8; // rcx
  _DWORD *v9; // rbx
  HMODULE Library; // rax
  unsigned int v11; // edx
  unsigned __int16 *v12; // rcx
  HANDLE Thread; // rax
  unsigned int v14; // edx
  unsigned __int16 *v15; // rcx
  unsigned int v16; // edx
  unsigned __int16 *v17; // rcx
  unsigned int v18; // edi
  unsigned int v19; // edx
  unsigned __int16 *v20; // rcx
  DWORD LastError; // esi
  HMODULE v22; // rcx
  int lpThreadId; // [rsp+28h] [rbp-260h]
  int lpThreadIda; // [rsp+28h] [rbp-260h]
  DWORD ThreadId[4]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-248h] BYREF

  if ( g_dwJetDBState != 2 || g_hJetDBOpenThread || g_hJetDBOpenThreadWaitEvent )
  {
    v9 = 0;
    SetLastError(0x8000FFFF);
    ErrLog_LogError(v20, v19, 0x1E6Eu, 0, 0, lpThreadId);
    goto LABEL_22;
  }
  v6 = _CatDBAlloc(0x18u);
  v9 = v6;
  if ( !v6 )
  {
    ErrLog_LogError(v8, v7, 0x1E74u, 0, 0, lpThreadId);
LABEL_22:
    v18 = 0;
    LastError = GetLastError();
    if ( g_hJetDBOpenThreadWaitEvent )
    {
      CloseHandle(g_hJetDBOpenThreadWaitEvent);
      g_hJetDBOpenThreadWaitEvent = 0;
    }
    if ( v9 )
    {
      v22 = (HMODULE)*((_QWORD *)v9 + 1);
      if ( v22 )
        FreeLibrary(v22);
      _CatDBFree(v9);
    }
    SetLastError(LastError);
    return v18;
  }
  *(_OWORD *)v6 = 0;
  *((_QWORD *)v6 + 2) = 0;
  Library = g_hInst;
  if ( g_hInst )
  {
    if ( !GetModuleFileNameW(g_hInst, Filename, 0x104u)
      || (Filename[260] = 0, (Library = LoadLibraryExW(Filename, 0, 0x11u)) == 0) )
    {
      Library = 0;
    }
  }
  *((_QWORD *)v9 + 1) = Library;
  v9[4] = a1;
  if ( a2 )
  {
    g_hJetDBOpenThreadWaitEvent = CreateEventW(0, 0, 0, 0);
    if ( !g_hJetDBOpenThreadWaitEvent )
    {
      ErrLog_LogError(v12, v11, 0x1E86u, 0, 0, lpThreadId);
      goto LABEL_22;
    }
    *v9 = a2;
  }
  ThreadId[0] = 0;
  g_dwJetDBState = 3;
  Thread = CreateThread(0, 0x5000u, CatDBOpenJetThreadProc, v9, 4u, ThreadId);
  g_hJetDBOpenThread = Thread;
  if ( !Thread )
  {
    g_dwJetDBState = 2;
    ErrLog_LogError(v15, v14, 0x1E9Cu, 0, 0, lpThreadIda);
    goto LABEL_22;
  }
  if ( a3 )
  {
    if ( !SetThreadPriority(Thread, a3) )
      ErrLog_LogError(v17, v16, 0x1EA7u, 0, 0, lpThreadIda);
    Thread = g_hJetDBOpenThread;
  }
  ResumeThread(Thread);
  return 1;
}

```

## disassembly

```asm
0x1800190f8  push    rbx
0x1800190fa  push    rbp
0x1800190fb  push    rsi
0x1800190fc  push    rdi
0x1800190fd  sub     rsp, 268h
0x180019104  mov     rax, cs:__security_cookie
0x18001910b  xor     rax, rsp
0x18001910e  mov     [rsp+288h+var_38], rax
0x180019116  cmp     cs:?g_dwJetDBState@@3KA, 2; ulong g_dwJetDBState
0x18001911d  mov     edi, r8d
0x180019120  mov     esi, edx
0x180019122  mov     ebp, ecx
0x180019124  jnz     loc_18001928A
0x18001912a  cmp     cs:?g_hJetDBOpenThread@@3PEAXEA, 0; void * g_hJetDBOpenThread
0x180019132  jnz     loc_18001928A
0x180019138  cmp     cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA, 0; void * g_hJetDBOpenThreadWaitEvent
0x180019140  jnz     loc_18001928A
0x180019146  mov     ecx, 18h; uBytes
0x18001914b  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x180019150  mov     rbx, rax
0x180019153  test    rax, rax
0x180019156  jnz     short loc_180019167
0x180019158  mov     [rsp+288h+dwCreationFlags], eax
0x18001915c  mov     r8d, 1E74h
0x180019162  jmp     loc_1800192A1
0x180019167  xor     eax, eax
0x180019169  xorps   xmm0, xmm0
0x18001916c  movups  xmmword ptr [rbx], xmm0
0x18001916f  mov     [rbx+10h], rax
0x180019173  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18001917a  test    rax, rax
0x18001917d  jz      short loc_1800191B9
0x18001917f  mov     r8d, 104h; nSize
0x180019185  lea     rdx, [rsp+288h+Filename]; lpFilename
0x18001918a  mov     rcx, rax; hModule
0x18001918d  call    cs:__imp_GetModuleFileNameW
0x180019193  test    eax, eax
0x180019195  jz      short loc_1800191B7
0x180019197  xor     eax, eax
0x180019199  lea     rcx, [rsp+288h+Filename]; lpLibFileName
0x18001919e  xor     edx, edx; hFile
0x1800191a0  mov     [rsp+288h+var_40], ax
0x1800191a8  lea     r8d, [rax+11h]; dwFlags
0x1800191ac  call    cs:__imp_LoadLibraryExW
0x1800191b2  test    rax, rax
0x1800191b5  jnz     short loc_1800191B9
0x1800191b7  xor     eax, eax
0x1800191b9  mov     [rbx+8], rax
0x1800191bd  mov     [rbx+10h], ebp
0x1800191c0  test    esi, esi
0x1800191c2  jz      short loc_1800191F1
0x1800191c4  xor     r9d, r9d; lpName
0x1800191c7  xor     r8d, r8d; bInitialState
0x1800191ca  xor     edx, edx; bManualReset
0x1800191cc  xor     ecx, ecx; lpEventAttributes
0x1800191ce  call    cs:__imp_CreateEventW
0x1800191d4  mov     cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA, rax; void * g_hJetDBOpenThreadWaitEvent
0x1800191db  test    rax, rax
0x1800191de  jnz     short loc_1800191EF
0x1800191e0  mov     [rsp+288h+dwCreationFlags], eax
0x1800191e4  mov     r8d, 1E86h
0x1800191ea  jmp     loc_1800192A1
0x1800191ef  mov     [rbx], esi
0x1800191f1  lea     rax, [rsp+288h+ThreadId]
0x1800191f6  mov     [rsp+288h+ThreadId], 0
0x1800191fe  mov     [rsp+288h+lpThreadId], rax; int
0x180019203  lea     r8, _CatDBOpenJetThreadProc; lpStartAddress
0x18001920a  mov     r9, rbx; lpParameter
0x18001920d  mov     [rsp+288h+dwCreationFlags], 4; dwCreationFlags
0x180019215  mov     edx, 5000h; dwStackSize
0x18001921a  mov     cs:?g_dwJetDBState@@3KA, 3; ulong g_dwJetDBState
0x180019224  xor     ecx, ecx; lpThreadAttributes
0x180019226  call    cs:__imp_CreateThread
0x18001922c  mov     cs:?g_hJetDBOpenThread@@3PEAXEA, rax; void * g_hJetDBOpenThread
0x180019233  test    rax, rax
0x180019236  jnz     short loc_18001924E
0x180019238  mov     cs:?g_dwJetDBState@@3KA, 2; ulong g_dwJetDBState
0x180019242  mov     r8d, 1E9Ch
0x180019248  mov     [rsp+288h+dwCreationFlags], eax
0x18001924c  jmp     short loc_1800192A1
0x18001924e  test    edi, edi
0x180019250  jz      short loc_18001927A
0x180019252  mov     edx, edi; nPriority
0x180019254  mov     rcx, rax; hThread
0x180019257  call    cs:__imp_SetThreadPriority
0x18001925d  test    eax, eax
0x18001925f  jnz     short loc_180019273
0x180019261  xor     r9d, r9d; unsigned int
0x180019264  mov     [rsp+288h+dwCreationFlags], eax; int
0x180019268  mov     r8d, 1EA7h; unsigned int
0x18001926e  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180019273  mov     rax, cs:?g_hJetDBOpenThread@@3PEAXEA; void * g_hJetDBOpenThread
0x18001927a  mov     rcx, rax; hThread
0x18001927d  call    cs:__imp_ResumeThread
0x180019283  mov     edi, 1
0x180019288  jmp     short loc_1800192F0
0x18001928a  xor     ebx, ebx
0x18001928c  mov     ecx, 8000FFFFh; dwErrCode
0x180019291  call    cs:__imp_SetLastError
0x180019297  mov     r8d, 1E6Eh; unsigned int
0x18001929d  mov     [rsp+288h+dwCreationFlags], ebx; int
0x1800192a1  xor     r9d, r9d; unsigned int
0x1800192a4  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800192a9  call    cs:__imp_GetLastError
0x1800192af  mov     rcx, cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA; hObject
0x1800192b6  xor     edi, edi
0x1800192b8  mov     esi, eax
0x1800192ba  test    rcx, rcx
0x1800192bd  jz      short loc_1800192CC
0x1800192bf  call    cs:__imp_CloseHandle
0x1800192c5  mov     cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA, rdi; void * g_hJetDBOpenThreadWaitEvent
0x1800192cc  test    rbx, rbx
0x1800192cf  jz      short loc_1800192E8
0x1800192d1  mov     rcx, [rbx+8]; hLibModule
0x1800192d5  test    rcx, rcx
0x1800192d8  jz      short loc_1800192E0
0x1800192da  call    cs:__imp_FreeLibrary
0x1800192e0  mov     rcx, rbx; void *
0x1800192e3  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x1800192e8  mov     ecx, esi; dwErrCode
0x1800192ea  call    cs:__imp_SetLastError
0x1800192f0  mov     eax, edi
0x1800192f2  mov     rcx, [rsp+288h+var_38]
0x1800192fa  xor     rcx, rsp; StackCookie
0x1800192fd  call    __security_check_cookie
0x180019302  add     rsp, 268h
0x180019309  pop     rdi
0x18001930a  pop     rsi
0x18001930b  pop     rbp
0x18001930c  pop     rbx
0x18001930d  retn
```
