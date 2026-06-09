# AddressCacherInit

- ea: `0x180002a00`
- end: `0x180002bab`
- name: `AddressCacherInit`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180069f98`

## callees

- `0x180002a00`
- `0x180025360`
- `0x180067fd0`
- `0x18007797c`

## import_xrefs

- `KERNEL32!CreateThreadpool` at `0x180002a96`
- `KERNEL32!CreateThreadpool` at `0x180002a96`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180002abc`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180002abc`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x180002ad1`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x180002ad1`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180002ae1`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180002ae1`
- `KERNEL32!CreateThreadpoolTimer` at `0x180002b2b`
- `KERNEL32!CreateThreadpoolTimer` at `0x180002b2b`
- `KERNEL32!CloseThreadpoolWork` at `0x180002b6b`
- `KERNEL32!CloseThreadpoolWork` at `0x180002b6b`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180002b7e`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180002b7e`
- `KERNEL32!CloseThreadpool` at `0x180002b91`
- `KERNEL32!CloseThreadpool` at `0x180002b91`

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
  DhcpAddressCacherCallBackEnviron.CleanupGroupCancelCallback = 0;
  DhcpAddressCacherCallBackEnviron.FinalizationCallback = 0;
  DhcpAddressCacherCallBackEnviron.u.Flags = 0;
  CacheRequestList = (__int64)&CacheRequestSpace;
  qword_180155918 = (__int64)&CacheRequestSpace;
  CacheRequestSpace = (__int64)&CacheRequestSpace;
  DhcpAddressCacherCallBackEnviron.Version = 3;
  *(_OWORD *)&DhcpAddressCacherCallBackEnviron.Pool = 0;
  DhcpAddressCacherCallBackEnviron.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  *(_OWORD *)&DhcpAddressCacherCallBackEnviron.RaceDll = 0;
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
    || (DhcpAddressCacherCallBackEnviron.CleanupGroupCancelCallback = 0,
        DhcpAddressCacherCallBackEnviron.Pool = DhcpAddressCacherThreadPool,
        v0 = 2,
        DhcpAddressCacherCallBackEnviron.CleanupGroup = ThreadpoolCleanupGroup,
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
0x180002a00  mov     [rsp+arg_0], rbx
0x180002a05  push    rdi
0x180002a06  sub     rsp, 20h
0x180002a0a  xor     ebx, ebx
0x180002a0c  call    DhcpSessionPoolInit
0x180002a11  test    eax, eax
0x180002a13  jnz     loc_180002B55
0x180002a19  and     cs:DhcpAddressCacherCallBackEnviron.CleanupGroupCancelCallback, rbx
0x180002a20  lea     rax, CacheRequestSpace
0x180002a27  and     cs:DhcpAddressCacherCallBackEnviron.FinalizationCallback, rbx
0x180002a2e  lea     edi, [rbx+1]
0x180002a31  and     dword ptr cs:DhcpAddressCacherCallBackEnviron.u, ebx
0x180002a37  xorps   xmm0, xmm0
0x180002a3a  cmp     cs:DhcpV6GlobalNumberOfNetsActive, ebx
0x180002a40  xorps   xmm1, xmm1
0x180002a43  mov     cs:CacheRequestList, rax
0x180002a4a  mov     cs:qword_180155918, rax
0x180002a51  mov     cs:CacheRequestSpace, rax
0x180002a58  mov     cs:DhcpAddressCacherCallBackEnviron.Version, 3
0x180002a62  movdqu  xmmword ptr cs:DhcpAddressCacherCallBackEnviron.Pool, xmm0
0x180002a6a  mov     cs:DhcpAddressCacherCallBackEnviron.CallbackPriority, edi
0x180002a70  movdqu  xmmword ptr cs:DhcpAddressCacherCallBackEnviron.RaceDll, xmm1
0x180002a78  mov     cs:DhcpAddressCacherCallBackEnviron.Size, 48h ; 'H'
0x180002a82  jnz     short loc_180002A94
0x180002a84  xor     r8d, r8d
0x180002a87  lea     edx, [rbx+2]
0x180002a8a  mov     ecx, 2724h
0x180002a8f  call    DhcpV6ServerEventLog
0x180002a94  xor     ecx, ecx; reserved
0x180002a96  call    cs:__imp_CreateThreadpool
0x180002a9d  nop     dword ptr [rax+rax+00h]
0x180002aa2  mov     cs:DhcpAddressCacherThreadPool, rax
0x180002aa9  test    rax, rax
0x180002aac  jz      loc_180002B55
0x180002ab2  mov     edx, 5; cthrdMost
0x180002ab7  mov     rcx, rax; ptpp
0x180002aba  mov     ebx, edi
0x180002abc  call    cs:__imp_SetThreadpoolThreadMaximum
0x180002ac3  nop     dword ptr [rax+rax+00h]
0x180002ac8  mov     rcx, cs:DhcpAddressCacherThreadPool; ptpp
0x180002acf  mov     edx, edi; cthrdMic
0x180002ad1  call    cs:__imp_SetThreadpoolThreadMinimum
0x180002ad8  nop     dword ptr [rax+rax+00h]
0x180002add  test    eax, eax
0x180002adf  jz      short loc_180002B55
0x180002ae1  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180002ae8  nop     dword ptr [rax+rax+00h]
0x180002aed  mov     cs:DhcpAddressCacherCleanupGroup, rax
0x180002af4  test    rax, rax
0x180002af7  jz      short loc_180002B55
0x180002af9  mov     rcx, cs:DhcpAddressCacherThreadPool
0x180002b00  lea     r8, DhcpAddressCacherCallBackEnviron; pcbe
0x180002b07  and     cs:DhcpAddressCacherCallBackEnviron.CleanupGroupCancelCallback, 0
0x180002b0f  xor     edx, edx; pv
0x180002b11  mov     cs:DhcpAddressCacherCallBackEnviron.Pool, rcx
0x180002b18  mov     ebx, 2
0x180002b1d  lea     rcx, AddressCacherTimer; pfnti
0x180002b24  mov     cs:DhcpAddressCacherCallBackEnviron.CleanupGroup, rax
0x180002b2b  call    cs:__imp_CreateThreadpoolTimer
0x180002b32  nop     dword ptr [rax+rax+00h]
0x180002b37  mov     cs:DhcpAddressCacherTime, rax
0x180002b3e  test    rax, rax
0x180002b41  jz      short loc_180002B55
0x180002b43  lea     rcx, DhcpAddressCacherReadWriteLock
0x180002b4a  call    RwLockInit
0x180002b4f  mov     edi, eax
0x180002b51  test    eax, eax
0x180002b53  jz      short loc_180002B9D
0x180002b55  mov     edi, 65Bh
0x180002b5a  sub     ebx, 1
0x180002b5d  jz      short loc_180002B8A
0x180002b5f  sub     ebx, 1
0x180002b62  jz      short loc_180002B77
0x180002b64  cmp     ebx, 1
0x180002b67  jnz     short loc_180002B9D
0x180002b69  xor     ecx, ecx; pwk
0x180002b6b  call    cs:__imp_CloseThreadpoolWork
0x180002b72  nop     dword ptr [rax+rax+00h]
0x180002b77  mov     rcx, cs:DhcpAddressCacherCleanupGroup; ptpcg
0x180002b7e  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180002b85  nop     dword ptr [rax+rax+00h]
0x180002b8a  mov     rcx, cs:DhcpAddressCacherThreadPool; ptpp
0x180002b91  call    cs:__imp_CloseThreadpool
0x180002b98  nop     dword ptr [rax+rax+00h]
0x180002b9d  mov     rbx, [rsp+28h+arg_0]
0x180002ba2  mov     eax, edi
0x180002ba4  add     rsp, 20h
0x180002ba8  pop     rdi
0x180002ba9  retn
```
