# CGhostMgr::Initialize(void)

- ea: `0x180008140`
- end: `0x180008211`
- name: `?Initialize@CGhostMgr@@SAJXZ`
- size: `209`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008240`

## callees

- `0x1800079f4`
- `0x180008140`
- `0x18000a5d0`
- `0x18000a8a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000819b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000819b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000817b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000817b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800081a4`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x1800081bb`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x1800081bb`

## pseudocode

```c
__int64 CGhostMgr::Initialize(void)
{
  unsigned int v0; // ebx
  HANDLE Thread; // rax
  void *v2; // rdi
  UINT v3; // eax
  CGhostMgr *v4; // rax
  __int64 v5; // rcx
  void *retaddr; // [rsp+38h] [rbp+0h]

  v0 = -2147024882;
  if ( !CGhostMgr::s_bSuperclassed )
  {
    Thread = CreateThread(0, 0, SuperclassGhostsThreadProc, CGhostWindow::s_GhostWndProc, 0, 0);
    v2 = Thread;
    if ( Thread )
    {
      CGhostMgr::s_bSuperclassed = 1;
      SetThreadPriority(Thread, 2);
      CloseHandle(v2);
    }
  }
  v3 = CGhostMgr::s_uHangRepMsg;
  if ( !CGhostMgr::s_uHangRepMsg )
  {
    v3 = RegisterWindowMessageW(L"WerHangRepMessage");
    CGhostMgr::s_uHangRepMsg = v3;
  }
  if ( CGhostMgr::s_bSuperclassed && v3 )
  {
    v4 = (CGhostMgr *)DefaultHeap::AllocClear(0x78u);
    if ( !v4 )
      ModuleFailFastForHRESULT(v5, retaddr);
    CGhostMgr::s_pgm = CGhostMgr::CGhostMgr(v4);
    if ( CGhostMgr::s_pgm )
      return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x180008140  mov     [rsp+arg_0], rbx
0x180008145  push    rdi
0x180008146  sub     rsp, 30h
0x18000814a  cmp     cs:?s_bSuperclassed@CGhostMgr@@0HA, 0; int CGhostMgr::s_bSuperclassed
0x180008151  mov     ebx, 8007000Eh
0x180008156  jnz     short loc_1800081AA
0x180008158  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180008161  lea     r9, ?s_GhostWndProc@CGhostWindow@@SA_JPEAUHWND__@@I_K_J@Z; lpParameter
0x180008168  lea     r8, SuperclassGhostsThreadProc; lpStartAddress
0x18000816f  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180008177  xor     edx, edx; dwStackSize
0x180008179  xor     ecx, ecx; lpThreadAttributes
0x18000817b  call    cs:__imp_CreateThread
0x180008181  mov     rdi, rax
0x180008184  test    rax, rax
0x180008187  jz      short loc_1800081AA
0x180008189  mov     edx, 2; nPriority
0x18000818e  mov     cs:?s_bSuperclassed@CGhostMgr@@0HA, 1; int CGhostMgr::s_bSuperclassed
0x180008198  mov     rcx, rax; hThread
0x18000819b  call    cs:__imp_SetThreadPriority
0x1800081a1  mov     rcx, rdi; hObject
0x1800081a4  call    cs:__imp_CloseHandle
0x1800081aa  mov     eax, cs:?s_uHangRepMsg@CGhostMgr@@2IA; uint CGhostMgr::s_uHangRepMsg
0x1800081b0  test    eax, eax
0x1800081b2  jnz     short loc_1800081C7
0x1800081b4  lea     rcx, String; "WerHangRepMessage"
0x1800081bb  call    cs:__imp_RegisterWindowMessageW
0x1800081c1  mov     cs:?s_uHangRepMsg@CGhostMgr@@2IA, eax; uint CGhostMgr::s_uHangRepMsg
0x1800081c7  cmp     cs:?s_bSuperclassed@CGhostMgr@@0HA, 0; int CGhostMgr::s_bSuperclassed
0x1800081ce  jz      short loc_1800081F9
0x1800081d0  test    eax, eax
0x1800081d2  jz      short loc_1800081F9
0x1800081d4  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800081d9  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x1800081de  test    rax, rax
0x1800081e1  jz      short loc_180008206
0x1800081e3  mov     rcx, rax; this
0x1800081e6  call    ??0CGhostMgr@@QEAA@XZ; CGhostMgr::CGhostMgr(void)
0x1800081eb  mov     cs:?s_pgm@CGhostMgr@@0PEAV1@EA, rax; CGhostMgr * CGhostMgr::s_pgm
0x1800081f2  test    rax, rax
0x1800081f5  jz      short loc_1800081F9
0x1800081f7  xor     ebx, ebx
0x1800081f9  mov     eax, ebx
0x1800081fb  mov     rbx, [rsp+38h+arg_0]
0x180008200  add     rsp, 30h
0x180008204  pop     rdi
0x180008205  retn
0x180008206  mov     rdx, [rsp+38h]
0x18000820b  call    ModuleFailFastForHRESULT
```
