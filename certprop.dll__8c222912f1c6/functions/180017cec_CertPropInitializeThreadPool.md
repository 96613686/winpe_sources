# CertPropInitializeThreadPool

- ea: `0x180017cec`
- end: `0x180017d89`
- name: `CertPropInitializeThreadPool`
- size: `157`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017d90`

## callees

- `0x180017cec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180017d48`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180017d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d5a`

## pseudocode

```c
__int64 CertPropInitializeThreadPool()
{
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  unsigned int v1; // ecx

  g_TpEnvironment.Version = 3;
  g_TpEnvironment.CleanupGroupCancelCallback = 0;
  *(_OWORD *)&g_TpEnvironment.Pool = 0;
  g_TpEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  *(_OWORD *)&g_TpEnvironment.RaceDll = 0;
  g_fInitializedTpEnvironment = 1;
  g_TpEnvironment.FinalizationCallback = 0;
  g_TpEnvironment.u.Flags = 0;
  g_TpEnvironment.Size = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  g_pTpCleanupGroup = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    g_TpEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
    v1 = 0;
    g_TpEnvironment.RaceDll = (PVOID)g_hInst;
    g_TpEnvironment.CleanupGroupCancelCallback = 0;
  }
  else
  {
    return GetLastError();
  }
  return v1;
}

```

## disassembly

```asm
0x180017cec  sub     rsp, 28h
0x180017cf0  xorps   xmm0, xmm0
0x180017cf3  mov     cs:g_TpEnvironment.Version, 3
0x180017cfd  mov     eax, 1
0x180017d02  mov     cs:g_TpEnvironment.CleanupGroupCancelCallback, 0
0x180017d0d  movdqu  xmmword ptr cs:g_TpEnvironment.Pool, xmm0
0x180017d15  mov     cs:g_TpEnvironment.CallbackPriority, eax
0x180017d1b  movdqu  xmmword ptr cs:g_TpEnvironment.RaceDll, xmm0
0x180017d23  mov     cs:g_fInitializedTpEnvironment, eax
0x180017d29  mov     cs:g_TpEnvironment.FinalizationCallback, 0
0x180017d34  mov     dword ptr cs:g_TpEnvironment.u, 0
0x180017d3e  mov     cs:g_TpEnvironment.Size, 48h ; 'H'
0x180017d48  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180017d4e  mov     cs:g_pTpCleanupGroup, rax
0x180017d55  test    rax, rax
0x180017d58  jnz     short loc_180017D64
0x180017d5a  call    cs:__imp_GetLastError
0x180017d60  mov     ecx, eax
0x180017d62  jmp     short loc_180017D82
0x180017d64  mov     cs:g_TpEnvironment.CleanupGroup, rax
0x180017d6b  xor     ecx, ecx
0x180017d6d  mov     rax, cs:g_hInst
0x180017d74  mov     cs:g_TpEnvironment.RaceDll, rax
0x180017d7b  mov     cs:g_TpEnvironment.CleanupGroupCancelCallback, rcx
0x180017d82  mov     eax, ecx
0x180017d84  add     rsp, 28h
0x180017d88  retn
```
