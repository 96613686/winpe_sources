# Mode::~Mode(void)

- ea: `0x140027d18`
- end: `0x140027f3f`
- name: `??1Mode@@UEAA@XZ`
- size: `551`
- prototype: `void __fastcall(Mode *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x140008380`
- `0x140027f48`

## callees

- `0x140001d94`
- `0x14001c154`
- `0x140020420`
- `0x140027d18`
- `0x1400481f8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140027d73`
- `KERNEL32!WaitForSingleObject` at `0x140027dd9`
- `KERNEL32!WaitForSingleObject` at `0x140027e31`
- `KERNEL32!WaitForSingleObject` at `0x140027d73`
- `KERNEL32!WaitForSingleObject` at `0x140027dd9`
- `KERNEL32!WaitForSingleObject` at `0x140027e31`
- `KERNEL32!GetLastError` at `0x140027d90`
- `KERNEL32!GetLastError` at `0x140027d90`
- `KERNEL32!CloseHandle` at `0x140027d82`
- `KERNEL32!CloseHandle` at `0x140027df6`
- `KERNEL32!CloseHandle` at `0x140027e4b`
- `KERNEL32!CloseHandle` at `0x140027e96`
- `KERNEL32!CloseHandle` at `0x140027ec8`
- `KERNEL32!CloseHandle` at `0x140027d82`
- `KERNEL32!CloseHandle` at `0x140027df6`
- `KERNEL32!CloseHandle` at `0x140027e4b`
- `KERNEL32!CloseHandle` at `0x140027e96`
- `KERNEL32!CloseHandle` at `0x140027ec8`
- `KERNEL32!SetEvent` at `0x140027e19`
- `KERNEL32!SetEvent` at `0x140027e19`
- `KERNEL32!CreateThread` at `0x140027d54`
- `KERNEL32!CreateThread` at `0x140027d54`
- `DUI70!UnInitThread` at `0x140027f0c`
- `DUI70!UnInitThread` at `0x140027f0c`
- `DUI70!UnInitProcessPriv` at `0x140027f21`
- `DUI70!UnInitProcessPriv` at `0x140027f21`

## pseudocode

```c
void __fastcall Mode::~Mode(Mode *this)
{
  char *Thread; // rax
  void *v3; // rbx
  unsigned int v4; // edx
  signed int LastError; // eax
  void *v6; // rcx
  char *v7; // rcx
  __int64 i; // rbx
  char *v9; // rcx
  PageManager *v10; // rbx

  *(_QWORD *)this = &Mode::`vftable';
  Thread = (char *)CreateThread(0, 0, CancelThread, 0, 0, 0);
  v3 = Thread;
  if ( (unsigned __int64)(Thread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Mode::~Mode", 517, LastError);
  }
  else
  {
    WaitForSingleObject(Thread, 0xFFFFFFFF);
    CloseHandle(v3);
  }
  if ( Mode::s_PipeThread )
  {
    WaitForSingleObject(Mode::s_PipeThread, 0xFFFFFFFF);
    if ( (char *)Mode::s_PipeThread - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(Mode::s_PipeThread);
      Mode::s_PipeThread = 0;
    }
  }
  if ( qword_140080088 )
  {
    SetEvent(qword_140080088);
    v6 = (void *)*((_QWORD *)this + 3);
    if ( v6 )
      WaitForSingleObject(v6, 0xFFFFFFFF);
  }
  v7 = (char *)*((_QWORD *)this + 3);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 3) = 0;
  }
  if ( TroubleshootingPackages::s_Instance )
  {
    TroubleshootingPackages::`scalar deleting destructor'(TroubleshootingPackages::s_Instance, v4);
    TroubleshootingPackages::s_Instance = 0;
  }
  for ( i = 0; i != 28; ++i )
  {
    v9 = (char *)*(&g_EventsToWorker + i);
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v9);
      *(&g_EventsToWorker + i) = 0;
    }
  }
  if ( (char *)g_ProgressPageLoaded - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_ProgressPageLoaded);
    g_ProgressPageLoaded = 0;
  }
  v10 = PageManager::s_Instance;
  if ( PageManager::s_Instance )
  {
    PageManager::~PageManager(PageManager::s_Instance);
    operator delete(v10);
    PageManager::s_Instance = 0;
  }
  if ( *((_DWORD *)this + 2) )
    UnInitThread();
  if ( *((_DWORD *)this + 3) )
    UnInitProcessPriv(0x140000000uLL);
}

```

## disassembly

```asm
0x140027d18  mov     [rsp+arg_0], rbx
0x140027d1d  mov     [rsp+arg_8], rdi
0x140027d22  push    r14
0x140027d24  sub     rsp, 30h
0x140027d28  lea     rax, ??_7Mode@@6B@; const Mode::`vftable'
0x140027d2f  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140027d38  mov     [rcx], rax
0x140027d3b  lea     r8, ?CancelThread@@YAKPEAX@Z; lpStartAddress
0x140027d42  mov     rdi, rcx
0x140027d45  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140027d4d  xor     ecx, ecx; lpThreadAttributes
0x140027d4f  xor     r9d, r9d; lpParameter
0x140027d52  xor     edx, edx; dwStackSize
0x140027d54  call    cs:__imp_CreateThread
0x140027d5b  nop     dword ptr [rax+rax+00h]
0x140027d60  mov     rbx, rax
0x140027d63  lea     rdx, [rax-1]
0x140027d67  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140027d6b  ja      short loc_140027D90
0x140027d6d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140027d70  mov     rcx, rax; hHandle
0x140027d73  call    cs:__imp_WaitForSingleObject
0x140027d7a  nop     dword ptr [rax+rax+00h]
0x140027d7f  mov     rcx, rbx; hObject
0x140027d82  call    cs:__imp_CloseHandle
0x140027d89  nop     dword ptr [rax+rax+00h]
0x140027d8e  jmp     short loc_140027DCA
0x140027d90  call    cs:__imp_GetLastError
0x140027d97  nop     dword ptr [rax+rax+00h]
0x140027d9c  test    eax, eax
0x140027d9e  jle     short loc_140027DA8
0x140027da0  movzx   eax, ax
0x140027da3  or      eax, 80070000h
0x140027da8  mov     r9d, 205h
0x140027dae  mov     [rsp+38h+dwCreationFlags], eax
0x140027db2  lea     r8, aModeMode; "Mode::~Mode"
0x140027db9  mov     ecx, 1; Level
0x140027dbe  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140027dc5  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140027dca  mov     rcx, cs:?s_PipeThread@Mode@@0PEAXEA; hHandle
0x140027dd1  test    rcx, rcx
0x140027dd4  jz      short loc_140027E0D
0x140027dd6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140027dd9  call    cs:__imp_WaitForSingleObject
0x140027de0  nop     dword ptr [rax+rax+00h]
0x140027de5  mov     rcx, cs:?s_PipeThread@Mode@@0PEAXEA; hObject
0x140027dec  lea     rax, [rcx-1]
0x140027df0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140027df4  ja      short loc_140027E0D
0x140027df6  call    cs:__imp_CloseHandle
0x140027dfd  nop     dword ptr [rax+rax+00h]
0x140027e02  mov     cs:?s_PipeThread@Mode@@0PEAXEA, 0; void * Mode::s_PipeThread
0x140027e0d  mov     rcx, cs:qword_140080088; hEvent
0x140027e14  test    rcx, rcx
0x140027e17  jz      short loc_140027E3D
0x140027e19  call    cs:__imp_SetEvent
0x140027e20  nop     dword ptr [rax+rax+00h]
0x140027e25  mov     rcx, [rdi+18h]; hHandle
0x140027e29  test    rcx, rcx
0x140027e2c  jz      short loc_140027E3D
0x140027e2e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140027e31  call    cs:__imp_WaitForSingleObject
0x140027e38  nop     dword ptr [rax+rax+00h]
0x140027e3d  mov     rcx, [rdi+18h]; hObject
0x140027e41  lea     rax, [rcx-1]
0x140027e45  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140027e49  ja      short loc_140027E5F
0x140027e4b  call    cs:__imp_CloseHandle
0x140027e52  nop     dword ptr [rax+rax+00h]
0x140027e57  mov     qword ptr [rdi+18h], 0
0x140027e5f  mov     rcx, cs:?s_Instance@TroubleshootingPackages@@0PEAV1@EA; this
0x140027e66  test    rcx, rcx
0x140027e69  jz      short loc_140027E7B
0x140027e6b  call    ??_GTroubleshootingPackages@@QEAAPEAXI@Z; TroubleshootingPackages::`scalar deleting destructor'(uint)
0x140027e70  mov     cs:?s_Instance@TroubleshootingPackages@@0PEAV1@EA, 0; TroubleshootingPackages * TroubleshootingPackages::s_Instance
0x140027e7b  xor     ebx, ebx
0x140027e7d  lea     r14, cs:140000000h
0x140027e84  mov     rcx, rva ?g_EventsToWorker@@3PAPEAXA[r14+rbx*8]; hObject
0x140027e8c  lea     rax, [rcx-1]
0x140027e90  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140027e94  ja      short loc_140027EAE
0x140027e96  call    cs:__imp_CloseHandle
0x140027e9d  nop     dword ptr [rax+rax+00h]
0x140027ea2  mov     rva ?g_EventsToWorker@@3PAPEAXA[r14+rbx*8], 0; void * near * g_EventsToWorker ...
0x140027eae  inc     rbx
0x140027eb1  cmp     rbx, 1Ch
0x140027eb5  jnz     short loc_140027E84
0x140027eb7  mov     rcx, cs:?g_ProgressPageLoaded@@3PEAXEA; hObject
0x140027ebe  lea     rax, [rcx-1]
0x140027ec2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140027ec6  ja      short loc_140027EDF
0x140027ec8  call    cs:__imp_CloseHandle
0x140027ecf  nop     dword ptr [rax+rax+00h]
0x140027ed4  mov     cs:?g_ProgressPageLoaded@@3PEAXEA, 0; void * g_ProgressPageLoaded
0x140027edf  mov     rbx, cs:?s_Instance@PageManager@@0PEAV1@EA; PageManager * PageManager::s_Instance
0x140027ee6  test    rbx, rbx
0x140027ee9  jz      short loc_140027F06
0x140027eeb  mov     rcx, rbx; this
0x140027eee  call    ??1PageManager@@QEAA@XZ; PageManager::~PageManager(void)
0x140027ef3  mov     rcx, rbx; Block
0x140027ef6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140027efb  mov     cs:?s_Instance@PageManager@@0PEAV1@EA, 0; PageManager * PageManager::s_Instance
0x140027f06  cmp     dword ptr [rdi+8], 0
0x140027f0a  jz      short loc_140027F18
0x140027f0c  call    cs:__imp_UnInitThread
0x140027f13  nop     dword ptr [rax+rax+00h]
0x140027f18  cmp     dword ptr [rdi+0Ch], 0
0x140027f1c  jz      short loc_140027F2D
0x140027f1e  mov     rcx, r14
0x140027f21  call    cs:__imp_UnInitProcessPriv
0x140027f28  nop     dword ptr [rax+rax+00h]
0x140027f2d  mov     rbx, [rsp+38h+arg_0]
0x140027f32  mov     rdi, [rsp+38h+arg_8]
0x140027f37  add     rsp, 30h
0x140027f3b  pop     r14
0x140027f3d  retn
```
