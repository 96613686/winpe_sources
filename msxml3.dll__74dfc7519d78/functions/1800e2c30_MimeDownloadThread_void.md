# MimeDownloadThread(void *)

- ea: `0x1800e2c30`
- end: `0x1800e2e4b`
- name: `?MimeDownloadThread@@YAKPEAX@Z`
- size: `539`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000fb70`
- `0x1800107c0`
- `0x180026de4`
- `0x180036da8`
- `0x1800e2570`
- `0x1800e2844`
- `0x1800e2be0`
- `0x1800e2c30`
- `0x1800e3240`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e2dc5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e2e1b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e2dc5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800e2e1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e2c3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e2c3c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800e2c6d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800e2c6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e2c61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e2c61`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800e2c5b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800e2c5b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e2e30`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e2e30`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800e2c8d`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1800e2c8d`

## pseudocode

```c
__int64 __fastcall MimeDownloadThread(PVOID Parameter)
{
  HANDLE CurrentThread; // rax
  DWORD v2; // eax
  DWORD v3; // eax
  MimeDwnQueue *v4; // rbx
  __int64 *v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  MimeDwnQueue *v10; // rdi
  struct MimeThreadAction *v11; // rax
  struct MimeThreadAction *v12; // rax
  __int64 v13; // rbx
  int v14; // eax
  __int64 v16; // [rsp+30h] [rbp-18h] BYREF
  int v17; // [rsp+38h] [rbp-10h]
  int v18; // [rsp+3Ch] [rbp-Ch]
  __int64 v19; // [rsp+78h] [rbp+30h] BYREF

  if ( _InterlockedCompareExchange(&dword_1801F44E0, GetCurrentThreadId(), 0) )
    return 0;
  CoInitializeEx(0, 2u);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, -1);
  while ( 1 )
  {
LABEL_3:
    v2 = MsgWaitForMultipleObjects(2u, &g_MimeDwnEvents, 0, 0xFFFFFFFF, 0x1CFFu);
    if ( !v2 )
    {
      while ( 1 )
      {
        v4 = g_pMimeDwnQueue;
        v5 = 0;
        X_CRITICAL_SECTION::Enter((MimeDwnQueue *)((char *)g_pMimeDwnQueue + 8));
        if ( *((_DWORD *)v4 + 16) )
          v5 = **(__int64 ***)v4;
        X_CRITICAL_SECTION::Leave((MimeDwnQueue *)((char *)v4 + 8));
        if ( !v5 )
        {
          ResetEvent(g_MimeDwnEvents);
          goto LABEL_3;
        }
        EnsureTls::EnsureTls((EnsureTls *)&v19);
        v6 = v19;
        if ( v19 )
          break;
LABEL_22:
        MimeDownloadMsgLoop();
        ((void (__fastcall *)(__int64))g_pfnExit)(v6);
      }
      v17 = *(_DWORD *)(v19 + 76);
      *(_DWORD *)(v19 + 76) = 0;
      v7 = *v5;
      v16 = v6;
      v18 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64 *))(v7 + 8))(v5);
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 == 1 )
          {
            v10 = g_pMimeDwnQueue;
            X_CRITICAL_SECTION::Enter((MimeDwnQueue *)((char *)g_pMimeDwnQueue + 8));
            v11 = MimeDwnQueue::Remove(v10);
            if ( v11 )
              MimeDwnQueue::Add(v10, v11);
            X_CRITICAL_SECTION::Leave((MimeDwnQueue *)((char *)v10 + 8));
          }
LABEL_21:
          Model::~Model((Model *)&v16);
          goto LABEL_22;
        }
        (*(void (__fastcall **)(__int64 *))(*v5 + 24))(v5);
      }
      else
      {
        (*(void (__fastcall **)(__int64 *))(*v5 + 16))(v5);
      }
      v12 = MimeDwnQueue::Remove(g_pMimeDwnQueue);
      if ( v12 )
        (**(void (__fastcall ***)(struct MimeThreadAction *, __int64))v12)(v12, 1);
      goto LABEL_21;
    }
    v3 = v2 - 1;
    if ( !v3 )
      break;
    if ( v3 != 1 )
      goto LABEL_27;
    MimeDownloadMsgLoop();
  }
  EnsureTls::EnsureTls((EnsureTls *)&v19);
  v13 = v19;
  if ( v19 )
  {
    v14 = *(_DWORD *)(v19 + 76);
    *(_DWORD *)(v19 + 76) = 0;
    v16 = v13;
    v17 = v14;
    v18 = 0;
    MimeDwnQueue::Clear(g_pMimeDwnQueue);
    Model::~Model((Model *)&v16);
  }
  MimeDownloadMsgLoop();
  ResetEvent(hEvent);
  ((void (__fastcall *)(__int64))g_pfnExit)(v13);
LABEL_27:
  CoUninitialize();
  dword_1801F44E0 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800e2c30  push    rbp
0x1800e2c32  push    rbx
0x1800e2c33  push    rsi
0x1800e2c34  push    rdi
0x1800e2c35  mov     rbp, rsp
0x1800e2c38  sub     rsp, 48h
0x1800e2c3c  call    cs:__imp_GetCurrentThreadId
0x1800e2c42  mov     ecx, eax
0x1800e2c44  xor     eax, eax
0x1800e2c46  lock cmpxchg cs:dword_1801F44E0, ecx
0x1800e2c4e  jnz     loc_1800E2E40
0x1800e2c54  mov     edx, 2; dwCoInit
0x1800e2c59  xor     ecx, ecx; pvReserved
0x1800e2c5b  call    cs:__imp_CoInitializeEx
0x1800e2c61  call    cs:__imp_GetCurrentThread
0x1800e2c67  mov     rcx, rax; hThread
0x1800e2c6a  or      edx, 0FFFFFFFFh; nPriority
0x1800e2c6d  call    cs:__imp_SetThreadPriority
0x1800e2c73  xor     r8d, r8d; fWaitAll
0x1800e2c76  mov     [rsp+48h+dwWakeMask], 1CFFh; dwWakeMask
0x1800e2c7e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800e2c82  lea     rdx, ?g_MimeDwnEvents@@3PAPEAXA; pHandles
0x1800e2c89  lea     ecx, [r8+2]; nCount
0x1800e2c8d  call    cs:__imp_MsgWaitForMultipleObjects
0x1800e2c93  test    eax, eax
0x1800e2c95  jz      short loc_1800E2CB0
0x1800e2c97  sub     eax, 1
0x1800e2c9a  jz      loc_1800E2DD0
0x1800e2ca0  cmp     eax, 1
0x1800e2ca3  jnz     loc_1800E2E30
0x1800e2ca9  call    ?MimeDownloadMsgLoop@@YAXXZ; MimeDownloadMsgLoop(void)
0x1800e2cae  jmp     short loc_1800E2C73
0x1800e2cb0  mov     rbx, cs:?g_pMimeDwnQueue@@3PEAVMimeDwnQueue@@EA; MimeDwnQueue * g_pMimeDwnQueue
0x1800e2cb7  xor     edi, edi
0x1800e2cb9  lea     rcx, [rbx+8]; this
0x1800e2cbd  call    ?Enter@X_CRITICAL_SECTION@@QEAAXXZ; X_CRITICAL_SECTION::Enter(void)
0x1800e2cc2  cmp     [rbx+40h], edi
0x1800e2cc5  jz      short loc_1800E2CCD
0x1800e2cc7  mov     rax, [rbx]
0x1800e2cca  mov     rdi, [rax]
0x1800e2ccd  lea     rcx, [rbx+8]; this
0x1800e2cd1  call    ?Leave@X_CRITICAL_SECTION@@QEAAXXZ; X_CRITICAL_SECTION::Leave(void)
0x1800e2cd6  test    rdi, rdi
0x1800e2cd9  jz      loc_1800E2DBE
0x1800e2cdf  lea     rcx, [rbp+arg_8]; this
0x1800e2ce3  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800e2ce8  mov     rbx, [rbp+arg_8]
0x1800e2cec  test    rbx, rbx
0x1800e2cef  jz      loc_1800E2DA5
0x1800e2cf5  mov     eax, [rbx+4Ch]
0x1800e2cf8  mov     rcx, rdi
0x1800e2cfb  mov     [rbp+var_10], eax
0x1800e2cfe  mov     dword ptr [rbx+4Ch], 0
0x1800e2d05  mov     rax, [rdi]
0x1800e2d08  mov     [rbp+var_18], rbx
0x1800e2d0c  mov     [rbp+var_C], 0
0x1800e2d13  mov     rax, [rax+8]
0x1800e2d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2d1c  test    eax, eax
0x1800e2d1e  jz      short loc_1800E2D66
0x1800e2d20  sub     eax, 1
0x1800e2d23  jz      short loc_1800E2D5D
0x1800e2d25  cmp     eax, 1
0x1800e2d28  jnz     short loc_1800E2D9C
0x1800e2d2a  mov     rdi, cs:?g_pMimeDwnQueue@@3PEAVMimeDwnQueue@@EA; MimeDwnQueue * g_pMimeDwnQueue
0x1800e2d31  lea     rcx, [rdi+8]; this
0x1800e2d35  call    ?Enter@X_CRITICAL_SECTION@@QEAAXXZ; X_CRITICAL_SECTION::Enter(void)
0x1800e2d3a  mov     rcx, rdi; this
0x1800e2d3d  call    ?Remove@MimeDwnQueue@@QEAAPEAVMimeThreadAction@@XZ; MimeDwnQueue::Remove(void)
0x1800e2d42  test    rax, rax
0x1800e2d45  jz      short loc_1800E2D52
0x1800e2d47  mov     rdx, rax; struct MimeThreadAction *
0x1800e2d4a  mov     rcx, rdi; this
0x1800e2d4d  call    ?Add@MimeDwnQueue@@QEAAPEAVMimeThreadAction@@PEAV2@@Z; MimeDwnQueue::Add(MimeThreadAction *)
0x1800e2d52  lea     rcx, [rdi+8]; this
0x1800e2d56  call    ?Leave@X_CRITICAL_SECTION@@QEAAXXZ; X_CRITICAL_SECTION::Leave(void)
0x1800e2d5b  jmp     short loc_1800E2D9C
0x1800e2d5d  mov     rax, [rdi]
0x1800e2d60  mov     rax, [rax+18h]
0x1800e2d64  jmp     short loc_1800E2D6D
0x1800e2d66  mov     rax, [rdi]
0x1800e2d69  mov     rax, [rax+10h]
0x1800e2d6d  mov     rcx, rdi
0x1800e2d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2d75  mov     rcx, cs:?g_pMimeDwnQueue@@3PEAVMimeDwnQueue@@EA; this
0x1800e2d7c  call    ?Remove@MimeDwnQueue@@QEAAPEAVMimeThreadAction@@XZ; MimeDwnQueue::Remove(void)
0x1800e2d81  mov     r8, rax
0x1800e2d84  test    rax, rax
0x1800e2d87  jz      short loc_1800E2D9C
0x1800e2d89  mov     rcx, [rax]
0x1800e2d8c  mov     edx, 1
0x1800e2d91  mov     rax, [rcx]
0x1800e2d94  mov     rcx, r8
0x1800e2d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2d9c  lea     rcx, [rbp+var_18]; this
0x1800e2da0  call    ??1Model@@QEAA@XZ; Model::~Model(void)
0x1800e2da5  call    ?MimeDownloadMsgLoop@@YAXXZ; MimeDownloadMsgLoop(void)
0x1800e2daa  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x1800e2db1  mov     rcx, rbx
0x1800e2db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2db9  jmp     loc_1800E2CB0
0x1800e2dbe  mov     rcx, cs:?g_MimeDwnEvents@@3PAPEAXA; hEvent
0x1800e2dc5  call    cs:__imp_ResetEvent
0x1800e2dcb  jmp     loc_1800E2C73
0x1800e2dd0  lea     rcx, [rbp+arg_8]; this
0x1800e2dd4  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800e2dd9  mov     rbx, [rbp+arg_8]
0x1800e2ddd  test    rbx, rbx
0x1800e2de0  jz      short loc_1800E2E0F
0x1800e2de2  mov     eax, [rbx+4Ch]
0x1800e2de5  mov     dword ptr [rbx+4Ch], 0
0x1800e2dec  mov     rcx, cs:?g_pMimeDwnQueue@@3PEAVMimeDwnQueue@@EA; this
0x1800e2df3  mov     [rbp+var_18], rbx
0x1800e2df7  mov     [rbp+var_10], eax
0x1800e2dfa  mov     [rbp+var_C], 0
0x1800e2e01  call    ?Clear@MimeDwnQueue@@QEAAXXZ; MimeDwnQueue::Clear(void)
0x1800e2e06  lea     rcx, [rbp+var_18]; this
0x1800e2e0a  call    ??1Model@@QEAA@XZ; Model::~Model(void)
0x1800e2e0f  call    ?MimeDownloadMsgLoop@@YAXXZ; MimeDownloadMsgLoop(void)
0x1800e2e14  mov     rcx, cs:hEvent; hEvent
0x1800e2e1b  call    cs:__imp_ResetEvent
0x1800e2e21  mov     rax, cs:?g_pfnExit@@3P6AXPEAUTLSDATA@@@ZEA; void (*g_pfnExit)(TLSDATA *)
0x1800e2e28  mov     rcx, rbx
0x1800e2e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2e30  call    cs:__imp_CoUninitialize
0x1800e2e36  mov     cs:dword_1801F44E0, 0
0x1800e2e40  xor     eax, eax
0x1800e2e42  add     rsp, 48h
0x1800e2e46  pop     rdi
0x1800e2e47  pop     rsi
0x1800e2e48  pop     rbx
0x1800e2e49  pop     rbp
0x1800e2e4a  retn
```
