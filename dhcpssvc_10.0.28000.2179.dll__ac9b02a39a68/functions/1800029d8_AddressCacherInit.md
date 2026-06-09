# AddressCacherInit

- ea: `0x1800029d8`
- end: `0x180002b86`
- name: `AddressCacherInit`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180069d98`

## callees

- `0x1800029d8`
- `0x18002489c`
- `0x180067d7c`
- `0x18007782c`

## import_xrefs

- `KERNEL32!CreateThreadpool` at `0x180002a6e`
- `KERNEL32!CreateThreadpool` at `0x180002a6e`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180002a94`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180002a94`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x180002aa9`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x180002aa9`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180002ab9`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180002ab9`
- `KERNEL32!CreateThreadpoolTimer` at `0x180002b06`
- `KERNEL32!CreateThreadpoolTimer` at `0x180002b06`
- `KERNEL32!CloseThreadpoolWork` at `0x180002b46`
- `KERNEL32!CloseThreadpoolWork` at `0x180002b46`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180002b59`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180002b59`
- `KERNEL32!CloseThreadpool` at `0x180002b6c`
- `KERNEL32!CloseThreadpool` at `0x180002b6c`

## pseudocode

```c
__int64 AddressCacherInit()
{
  int v0; // ebx
  struct _TP_POOL *Threadpool; // rax
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  unsigned int v3; // edi
  int v4; // ebx
  int v5; // ebx

  v0 = 0;
  if ( (unsigned int)DhcpSessionPoolInit() )
    goto LABEL_9;
  CacheRequestList = (__int64)&CacheRequestSpace;
  qword_1801578B8 = (__int64)&CacheRequestSpace;
  CacheRequestSpace = (__int64)&CacheRequestSpace;
  *(_OWORD *)&DhcpAddressCacherCallBackEnviron.Pool = 0;
  DhcpAddressCacherCallBackEnviron.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  *(_OWORD *)&DhcpAddressCacherCallBackEnviron.RaceDll = 0;
  DhcpAddressCacherCallBackEnviron.Version = 3;
  DhcpAddressCacherCallBackEnviron.CleanupGroupCancelCallback = 0;
  DhcpAddressCacherCallBackEnviron.FinalizationCallback = 0;
  DhcpAddressCacherCallBackEnviron.u.Flags = 0;
  DhcpAddressCacherCallBackEnviron.Size = 72;
  if ( !DhcpV6GlobalNumberOfNetsActive )
    DhcpV6ServerEventLog(10020, 2, 0);
  Threadpool = CreateThreadpool(0);
  DhcpAddressCacherThreadPool = Threadpool;
  if ( !Threadpool )
    goto LABEL_9;
  v0 = 1;
  SetThreadpoolThreadMaximum(Threadpool, 5u);
  if ( !SetThreadpoolThreadMinimum(DhcpAddressCacherThreadPool, 1u) )
    goto LABEL_9;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  DhcpAddressCacherCleanupGroup = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup
    || (DhcpAddressCacherCallBackEnviron.Pool = DhcpAddressCacherThreadPool,
        DhcpAddressCacherCallBackEnviron.CleanupGroup = ThreadpoolCleanupGroup,
        v0 = 2,
        DhcpAddressCacherCallBackEnviron.CleanupGroupCancelCallback = 0,
        (DhcpAddressCacherTime = CreateThreadpoolTimer(AddressCacherTimer, 0, &DhcpAddressCacherCallBackEnviron)) == 0)
    || (v3 = RwLockInit(&DhcpAddressCacherReadWriteLock)) != 0 )
  {
LABEL_9:
    v3 = 1627;
    v4 = v0 - 1;
    if ( !v4 )
    {
LABEL_14:
      CloseThreadpool(DhcpAddressCacherThreadPool);
      return v3;
    }
    v5 = v4 - 1;
    if ( !v5 )
    {
LABEL_13:
      CloseThreadpoolCleanupGroup(DhcpAddressCacherCleanupGroup);
      goto LABEL_14;
    }
    if ( v5 == 1 )
    {
      CloseThreadpoolWork(0);
      goto LABEL_13;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800029d8  mov     [rsp+arg_0], rbx
0x1800029dd  push    rdi
0x1800029de  sub     rsp, 20h
0x1800029e2  xor     ebx, ebx
0x1800029e4  call    DhcpSessionPoolInit
0x1800029e9  test    eax, eax
0x1800029eb  jnz     loc_180002B30
0x1800029f1  cmp     cs:DhcpV6GlobalNumberOfNetsActive, ebx
0x1800029f7  lea     rax, CacheRequestSpace
0x1800029fe  xorps   xmm0, xmm0
0x180002a01  mov     cs:CacheRequestList, rax
0x180002a08  xorps   xmm1, xmm1
0x180002a0b  mov     cs:qword_1801578B8, rax
0x180002a12  lea     edi, [rbx+1]
0x180002a15  mov     cs:CacheRequestSpace, rax
0x180002a1c  movdqu  xmmword ptr cs:DhcpAddressCacherCallBackEnviron.Pool, xmm0
0x180002a24  mov     cs:DhcpAddressCacherCallBackEnviron.CallbackPriority, edi
0x180002a2a  movdqu  xmmword ptr cs:DhcpAddressCacherCallBackEnviron.RaceDll, xmm1
0x180002a32  mov     cs:DhcpAddressCacherCallBackEnviron.Version, 3
0x180002a3c  mov     cs:DhcpAddressCacherCallBackEnviron.CleanupGroupCancelCallback, rbx
0x180002a43  mov     cs:DhcpAddressCacherCallBackEnviron.FinalizationCallback, rbx
0x180002a4a  mov     dword ptr cs:DhcpAddressCacherCallBackEnviron.u, ebx
0x180002a50  mov     cs:DhcpAddressCacherCallBackEnviron.Size, 48h ; 'H'
0x180002a5a  jnz     short loc_180002A6C
0x180002a5c  xor     r8d, r8d
0x180002a5f  lea     edx, [rbx+2]
0x180002a62  mov     ecx, 2724h
0x180002a67  call    DhcpV6ServerEventLog
0x180002a6c  xor     ecx, ecx; reserved
0x180002a6e  call    cs:__imp_CreateThreadpool
0x180002a75  nop     dword ptr [rax+rax+00h]
0x180002a7a  mov     cs:DhcpAddressCacherThreadPool, rax
0x180002a81  test    rax, rax
0x180002a84  jz      loc_180002B30
0x180002a8a  mov     edx, 5; cthrdMost
0x180002a8f  mov     rcx, rax; ptpp
0x180002a92  mov     ebx, edi
0x180002a94  call    cs:__imp_SetThreadpoolThreadMaximum
0x180002a9b  nop     dword ptr [rax+rax+00h]
0x180002aa0  mov     rcx, cs:DhcpAddressCacherThreadPool; ptpp
0x180002aa7  mov     edx, edi; cthrdMic
0x180002aa9  call    cs:__imp_SetThreadpoolThreadMinimum
0x180002ab0  nop     dword ptr [rax+rax+00h]
0x180002ab5  test    eax, eax
0x180002ab7  jz      short loc_180002B30
0x180002ab9  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180002ac0  nop     dword ptr [rax+rax+00h]
0x180002ac5  mov     cs:DhcpAddressCacherCleanupGroup, rax
0x180002acc  test    rax, rax
0x180002acf  jz      short loc_180002B30
0x180002ad1  mov     rcx, cs:DhcpAddressCacherThreadPool
0x180002ad8  lea     r8, DhcpAddressCacherCallBackEnviron; pcbe
0x180002adf  mov     cs:DhcpAddressCacherCallBackEnviron.Pool, rcx
0x180002ae6  xor     edx, edx; pv
0x180002ae8  lea     rcx, AddressCacherTimer; pfnti
0x180002aef  mov     cs:DhcpAddressCacherCallBackEnviron.CleanupGroup, rax
0x180002af6  mov     ebx, 2
0x180002afb  mov     cs:DhcpAddressCacherCallBackEnviron.CleanupGroupCancelCallback, 0
0x180002b06  call    cs:__imp_CreateThreadpoolTimer
0x180002b0d  nop     dword ptr [rax+rax+00h]
0x180002b12  mov     cs:DhcpAddressCacherTime, rax
0x180002b19  test    rax, rax
0x180002b1c  jz      short loc_180002B30
0x180002b1e  lea     rcx, DhcpAddressCacherReadWriteLock
0x180002b25  call    RwLockInit
0x180002b2a  mov     edi, eax
0x180002b2c  test    eax, eax
0x180002b2e  jz      short loc_180002B78
0x180002b30  mov     edi, 65Bh
0x180002b35  sub     ebx, 1
0x180002b38  jz      short loc_180002B65
0x180002b3a  sub     ebx, 1
0x180002b3d  jz      short loc_180002B52
0x180002b3f  cmp     ebx, 1
0x180002b42  jnz     short loc_180002B78
0x180002b44  xor     ecx, ecx; pwk
0x180002b46  call    cs:__imp_CloseThreadpoolWork
0x180002b4d  nop     dword ptr [rax+rax+00h]
0x180002b52  mov     rcx, cs:DhcpAddressCacherCleanupGroup; ptpcg
0x180002b59  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180002b60  nop     dword ptr [rax+rax+00h]
0x180002b65  mov     rcx, cs:DhcpAddressCacherThreadPool; ptpp
0x180002b6c  call    cs:__imp_CloseThreadpool
0x180002b73  nop     dword ptr [rax+rax+00h]
0x180002b78  mov     rbx, [rsp+28h+arg_0]
0x180002b7d  mov     eax, edi
0x180002b7f  add     rsp, 20h
0x180002b83  pop     rdi
0x180002b84  retn
```
