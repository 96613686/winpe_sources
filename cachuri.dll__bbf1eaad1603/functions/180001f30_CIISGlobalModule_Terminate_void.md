# CIISGlobalModule::Terminate(void)

- ea: `0x180001f30`
- end: `0x180001f9f`
- name: `?Terminate@CIISGlobalModule@@UEAAXXZ`
- size: `111`
- prototype: `void __fastcall(CIISGlobalModule *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800014d0`
- `0x180001bf8`
- `0x180001f30`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001f58`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180001f58`

## pseudocode

```c
void __fastcall CIISGlobalModule::Terminate(CIISGlobalModule *this)
{
  W3_URL_INFO_CACHE *v1; // rbx
  void *v3; // rdx

  v1 = (W3_URL_INFO_CACHE *)g_pUriCache;
  if ( g_pUriCache )
  {
    v3 = (void *)*((_QWORD *)g_pUriCache + 5);
    if ( v3 )
    {
      DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)v1 + 5) = 0;
      v1 = (W3_URL_INFO_CACHE *)g_pUriCache;
    }
    if ( v1 )
    {
      W3_URL_INFO_CACHE::~W3_URL_INFO_CACHE(v1);
      operator delete(v1);
    }
    g_pUriCache = 0;
  }
  operator delete(this);
}

```

## disassembly

```asm
0x180001f30  mov     [rsp+arg_0], rbx
0x180001f35  push    rdi
0x180001f36  sub     rsp, 20h
0x180001f3a  mov     rbx, cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA; W3_URL_INFO_CACHE * g_pUriCache
0x180001f41  mov     rdi, rcx
0x180001f44  test    rbx, rbx
0x180001f47  jz      short loc_180001F8D
0x180001f49  mov     rdx, [rbx+28h]; Timer
0x180001f4d  test    rdx, rdx
0x180001f50  jz      short loc_180001F6D
0x180001f52  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180001f56  xor     ecx, ecx; TimerQueue
0x180001f58  call    cs:__imp_DeleteTimerQueueTimer
0x180001f5e  mov     qword ptr [rbx+28h], 0
0x180001f66  mov     rbx, cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA; W3_URL_INFO_CACHE * g_pUriCache
0x180001f6d  test    rbx, rbx
0x180001f70  jz      short loc_180001F82
0x180001f72  mov     rcx, rbx; this
0x180001f75  call    ??1W3_URL_INFO_CACHE@@QEAA@XZ; W3_URL_INFO_CACHE::~W3_URL_INFO_CACHE(void)
0x180001f7a  mov     rcx, rbx; Block
0x180001f7d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001f82  mov     cs:?g_pUriCache@@3PEAVW3_URL_INFO_CACHE@@EA, 0; W3_URL_INFO_CACHE * g_pUriCache
0x180001f8d  mov     rcx, rdi; Block
0x180001f90  mov     rbx, [rsp+28h+arg_0]
0x180001f95  add     rsp, 20h
0x180001f99  pop     rdi
0x180001f9a  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
