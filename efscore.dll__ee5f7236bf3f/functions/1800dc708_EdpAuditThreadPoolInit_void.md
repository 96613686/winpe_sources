# EdpAuditThreadPoolInit(void)

- ea: `0x1800dc708`
- end: `0x1800dc7d1`
- name: `?EdpAuditThreadPoolInit@@YAKXZ`
- size: `201`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800dc8c4`

## callees

- `0x1800dc708`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc756`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800dc714`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800dc714`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800dc74b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800dc74b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800dc737`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800dc737`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800dc745`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800dc745`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800dc761`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800dc761`

## pseudocode

```c
__int64 EdpAuditThreadPoolInit(void)
{
  struct _TP_POOL *Threadpool; // rax
  struct _TP_POOL *v1; // rbx
  DWORD LastError; // edi
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax

  Threadpool = CreateThreadpool(0);
  v1 = Threadpool;
  if ( Threadpool )
  {
    SetThreadpoolThreadMinimum(Threadpool, 1u);
    SetThreadpoolThreadMaximum(v1, 0x14u);
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    if ( ThreadpoolCleanupGroup )
    {
      LastError = 0;
      g_callBackEnviron.Version = 3;
      g_callBackEnviron.FinalizationCallback = 0;
      *(_OWORD *)&g_callBackEnviron.RaceDll = 0;
      g_callBackEnviron.u.Flags = 0;
      g_callBackEnviron.CleanupGroupCancelCallback = 0;
      g_callBackEnviron.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
      g_callBackEnviron.Size = 72;
      g_callBackEnviron.Pool = v1;
      g_callBackEnviron.CleanupGroup = ThreadpoolCleanupGroup;
      g_cleanupGroup = ThreadpoolCleanupGroup;
      g_edpAuditThreadPool = v1;
    }
    else
    {
      LastError = GetLastError();
      CloseThreadpool(v1);
    }
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x1800dc708  mov     [rsp+arg_0], rbx
0x1800dc70d  push    rdi
0x1800dc70e  sub     rsp, 20h
0x1800dc712  xor     ecx, ecx; reserved
0x1800dc714  call    cs:__imp_CreateThreadpool
0x1800dc71a  mov     rbx, rax
0x1800dc71d  test    rax, rax
0x1800dc720  jnz     short loc_1800DC72F
0x1800dc722  call    cs:__imp_GetLastError
0x1800dc728  mov     edi, eax
0x1800dc72a  jmp     loc_1800DC7C4
0x1800dc72f  mov     edx, 1; cthrdMic
0x1800dc734  mov     rcx, rbx; ptpp
0x1800dc737  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800dc73d  mov     edx, 14h; cthrdMost
0x1800dc742  mov     rcx, rbx; ptpp
0x1800dc745  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800dc74b  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800dc751  test    rax, rax
0x1800dc754  jnz     short loc_1800DC769
0x1800dc756  call    cs:__imp_GetLastError
0x1800dc75c  mov     rcx, rbx; ptpp
0x1800dc75f  mov     edi, eax
0x1800dc761  call    cs:__imp_CloseThreadpool
0x1800dc767  jmp     short loc_1800DC7C4
0x1800dc769  xor     edi, edi
0x1800dc76b  mov     cs:?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_callBackEnviron ...
0x1800dc775  xorps   xmm0, xmm0
0x1800dc778  mov     cs:?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rdi; _TP_CALLBACK_ENVIRON_V3 g_callBackEnviron ...
0x1800dc77f  movdqa  xmmword ptr cs:?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_callBackEnviron ...
0x1800dc787  mov     dword ptr cs:?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, edi; _TP_CALLBACK_ENVIRON_V3 g_callBackEnviron ...
0x1800dc78d  mov     cs:?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 g_callBackEnviron ...
0x1800dc794  mov     cs:?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 g_callBackEnviron ...
0x1800dc79e  mov     cs:?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_callBackEnviron ...
0x1800dc7a8  mov     cs:?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rbx; _TP_CALLBACK_ENVIRON_V3 g_callBackEnviron ...
0x1800dc7af  mov     cs:?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 g_callBackEnviron ...
0x1800dc7b6  mov     cs:?g_cleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * g_cleanupGroup
0x1800dc7bd  mov     cs:?g_edpAuditThreadPool@@3PEAU_TP_POOL@@EA, rbx; _TP_POOL * g_edpAuditThreadPool
0x1800dc7c4  mov     rbx, [rsp+28h+arg_0]
0x1800dc7c9  mov     eax, edi
0x1800dc7cb  add     rsp, 20h
0x1800dc7cf  pop     rdi
0x1800dc7d0  retn
```
