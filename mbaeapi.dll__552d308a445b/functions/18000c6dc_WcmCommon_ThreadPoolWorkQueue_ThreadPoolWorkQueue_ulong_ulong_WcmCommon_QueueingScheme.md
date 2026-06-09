# WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(ulong,ulong,WcmCommon::QueueingScheme)

- ea: `0x18000c6dc`
- end: `0x18000c933`
- name: `??0ThreadPoolWorkQueue@WcmCommon@@QEAA@KKW4QueueingScheme@1@@Z`
- size: `599`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c438`

## callees

- `0x1800028ec`
- `0x18000c6dc`
- `0x180013668`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000c718`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000c718`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c782`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c782`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c76f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c76f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8b1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000c8bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000c8e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000c8bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000c8e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000c8c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000c8f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000c8c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000c8f0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000c75d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18000c75d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000c7b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000c7b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18000c7a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18000c7a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000c77a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000c77a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000c87f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000c87f`

## pseudocode

```c
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(_QWORD *a1)
{
  struct _TP_POOL *Threadpool; // rdi
  unsigned int v3; // r8d
  const char *v4; // r9
  struct _TP_POOL *v5; // rbp
  DWORD LastError; // ebx
  unsigned int v7; // r8d
  const char *v8; // r9
  struct _TP_WORK **v9; // r15
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  struct _TP_WORK *ThreadpoolWork; // rdi
  unsigned int v14; // r8d
  const char *v15; // r9
  struct _TP_WORK *v16; // rsi
  DWORD v17; // ebx
  struct _TP_WORK *v19; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v20; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_DWORD *)a1 = 1;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 1), 0x1F4u, 0);
  v20 = a1 + 6;
  a1[6] = 3;
  a1[14] = 72;
  a1[15] = 0;
  a1[7] = 0;
  a1[8] = 0;
  a1[9] = 0;
  a1[10] = 0;
  a1[11] = 0;
  a1[12] = 0;
  *((_DWORD *)a1 + 26) = 0;
  *((_DWORD *)a1 + 27) = 1;
  Threadpool = CreateThreadpool(0);
  v5 = (struct _TP_POOL *)a1[15];
  if ( v5 )
  {
    LastError = GetLastError();
    CloseThreadpool(v5);
    SetLastError(LastError);
  }
  a1[15] = Threadpool;
  if ( !Threadpool )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6A, v3, v4);
  if ( !SetThreadpoolThreadMinimum(Threadpool, 0) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6D, v7, v8);
  SetThreadpoolThreadMaximum((PTP_POOL)a1[15], 1u);
  a1[7] = a1[15];
  v9 = (struct _TP_WORK **)(a1 + 16);
  a1[16] = 0;
  a1[17] = 0;
  *((_DWORD *)a1 + 36) = 0;
  v20 = a1 + 19;
  a1[19] = 0;
  a1[20] = 0;
  a1[21] = 0;
  a1[22] = 0;
  a1[23] = 0;
  v10 = operator new(0x10u);
  v10[1] = 0;
  a1[19] = v10;
  *v10 = a1 + 19;
  a1[24] = 0;
  a1[25] = 0;
  a1[26] = 0;
  a1[27] = 0;
  a1[28] = 0;
  v11 = operator new(0x10u);
  v11[1] = 0;
  a1[24] = v11;
  *v11 = a1 + 24;
  a1[29] = 0;
  a1[30] = 0;
  a1[31] = 0;
  a1[32] = 0;
  a1[33] = 0;
  v12 = operator new(0x10u);
  v12[1] = 0;
  a1[29] = v12;
  *v12 = a1 + 29;
  *((_BYTE *)a1 + 272) = 0;
  ThreadpoolWork = CreateThreadpoolWork(
                     WcmCommon::ThreadPoolWorkQueue::WorkCallback,
                     a1,
                     (PTP_CALLBACK_ENVIRON)((unsigned __int64)(a1 + 6) & -(__int64)(a1[15] != 0)));
  v19 = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x75, v14, v15);
  if ( v9 != &v19 )
  {
    v16 = *v9;
    if ( *v9 )
    {
      v17 = GetLastError();
      WaitForThreadpoolWorkCallbacks(v16, 1);
      CloseThreadpoolWork(v16);
      SetLastError(v17);
    }
    *v9 = ThreadpoolWork;
    ThreadpoolWork = 0;
  }
  if ( ThreadpoolWork )
  {
    WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 1);
    CloseThreadpoolWork(ThreadpoolWork);
  }
  return a1;
}

```

## disassembly

```asm
0x18000c6dc  mov     rax, rsp
0x18000c6df  mov     [rax+10h], rbx
0x18000c6e3  mov     [rax+20h], r9d
0x18000c6e7  mov     [rax+8], rcx
0x18000c6eb  push    rbp
0x18000c6ec  push    rsi
0x18000c6ed  push    rdi
0x18000c6ee  push    r12
0x18000c6f0  push    r13
0x18000c6f2  push    r14
0x18000c6f4  push    r15
0x18000c6f6  sub     rsp, 30h
0x18000c6fa  mov     r14, rcx
0x18000c6fd  xor     r12d, r12d
0x18000c700  mov     [rax+20h], r12d
0x18000c704  lea     r13d, [r12+1]
0x18000c709  mov     [rcx], r13d
0x18000c70c  add     rcx, 8; lpCriticalSection
0x18000c710  xor     r8d, r8d; Flags
0x18000c713  mov     edx, 1F4h; dwSpinCount
0x18000c718  call    cs:__imp_InitializeCriticalSectionEx
0x18000c71e  nop
0x18000c71f  lea     rsi, [r14+30h]
0x18000c723  mov     [rsp+68h+var_40], rsi
0x18000c728  mov     qword ptr [rsi], 3
0x18000c72f  mov     qword ptr [rsi+40h], 48h ; 'H'
0x18000c737  mov     [rsi+48h], r12
0x18000c73b  mov     [rsi+8], r12
0x18000c73f  mov     [rsi+10h], r12
0x18000c743  mov     [rsi+18h], r12
0x18000c747  mov     [rsi+20h], r12
0x18000c74b  mov     [rsi+28h], r12
0x18000c74f  mov     [rsi+30h], r12
0x18000c753  mov     [rsi+38h], r12d
0x18000c757  mov     [rsi+3Ch], r13d
0x18000c75b  xor     ecx, ecx; reserved
0x18000c75d  call    cs:__imp_CreateThreadpool
0x18000c763  mov     rdi, rax
0x18000c766  mov     rbp, [rsi+48h]
0x18000c76a  test    rbp, rbp
0x18000c76d  jz      short loc_18000C788
0x18000c76f  call    cs:__imp_GetLastError
0x18000c775  mov     ebx, eax
0x18000c777  mov     rcx, rbp; ptpp
0x18000c77a  call    cs:__imp_CloseThreadpool
0x18000c780  mov     ecx, ebx; dwErrCode
0x18000c782  call    cs:__imp_SetLastError
0x18000c788  mov     [rsi+48h], rdi
0x18000c78c  mov     rcx, [rsp+68h]; this
0x18000c791  test    rdi, rdi
0x18000c794  jz      loc_18000C91A
0x18000c79a  mov     rbx, [rsp+68h]
0x18000c79f  xor     edx, edx; cthrdMic
0x18000c7a1  mov     rcx, rdi; ptpp
0x18000c7a4  call    cs:__imp_SetThreadpoolThreadMinimum
0x18000c7aa  test    eax, eax
0x18000c7ac  jz      loc_18000C925
0x18000c7b2  mov     edx, r13d; cthrdMost
0x18000c7b5  mov     rcx, [rsi+48h]; ptpp
0x18000c7b9  call    cs:__imp_SetThreadpoolThreadMaximum
0x18000c7bf  mov     rax, [rsi+48h]
0x18000c7c3  mov     [rsi+8], rax
0x18000c7c7  lea     r15, [r14+80h]
0x18000c7ce  mov     [r15], r12
0x18000c7d1  mov     [r14+88h], r12
0x18000c7d8  mov     [r14+90h], r12d
0x18000c7df  lea     rdi, [r14+98h]
0x18000c7e6  mov     [rsp+68h+var_40], rdi
0x18000c7eb  mov     [rdi], r12
0x18000c7ee  mov     [rdi+8], r12
0x18000c7f2  mov     [rdi+10h], r12
0x18000c7f6  mov     [rdi+18h], r12
0x18000c7fa  mov     [rdi+20h], r12
0x18000c7fe  mov     ebp, 10h
0x18000c803  mov     ecx, ebp; Size
0x18000c805  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c80a  mov     [rax+8], r12
0x18000c80e  mov     [rdi], rax
0x18000c811  mov     [rax], rdi
0x18000c814  lea     rbx, [rdi+28h]
0x18000c818  mov     [rbx], r12
0x18000c81b  mov     [rbx+8], r12
0x18000c81f  mov     [rbx+10h], r12
0x18000c823  mov     [rbx+18h], r12
0x18000c827  mov     [rbx+20h], r12
0x18000c82b  mov     ecx, ebp; Size
0x18000c82d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c832  mov     [rax+8], r12
0x18000c836  mov     [rbx], rax
0x18000c839  mov     [rax], rbx
0x18000c83c  lea     rbx, [rdi+50h]
0x18000c840  mov     [rbx], r12
0x18000c843  mov     [rbx+8], r12
0x18000c847  mov     [rbx+10h], r12
0x18000c84b  mov     [rbx+18h], r12
0x18000c84f  mov     [rbx+20h], r12
0x18000c853  mov     ecx, ebp; Size
0x18000c855  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c85a  mov     [rax+8], r12
0x18000c85e  mov     [rbx], rax
0x18000c861  mov     [rax], rbx
0x18000c864  mov     [rdi+78h], r12b
0x18000c868  mov     rax, [rsi+48h]
0x18000c86c  neg     rax
0x18000c86f  sbb     r8, r8
0x18000c872  and     r8, rsi; pcbe
0x18000c875  mov     rdx, r14; pv
0x18000c878  lea     rcx, ?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000c87f  call    cs:__imp_CreateThreadpoolWork
0x18000c885  mov     rdi, rax
0x18000c888  mov     [rsp+68h+var_48], rax
0x18000c88d  mov     [rsp+68h+arg_18], r13d
0x18000c895  mov     rcx, [rsp+68h]; this
0x18000c89a  test    rax, rax
0x18000c89d  jz      short loc_18000C90F
0x18000c89f  lea     rax, [rsp+68h+var_48]
0x18000c8a4  cmp     r15, rax
0x18000c8a7  jz      short loc_18000C8DC
0x18000c8a9  mov     rsi, [r15]
0x18000c8ac  test    rsi, rsi
0x18000c8af  jz      short loc_18000C8D6
0x18000c8b1  call    cs:__imp_GetLastError
0x18000c8b7  mov     ebx, eax
0x18000c8b9  mov     edx, r13d; fCancelPendingCallbacks
0x18000c8bc  mov     rcx, rsi; pwk
0x18000c8bf  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000c8c5  mov     rcx, rsi; pwk
0x18000c8c8  call    cs:__imp_CloseThreadpoolWork
0x18000c8ce  mov     ecx, ebx; dwErrCode
0x18000c8d0  call    cs:__imp_SetLastError
0x18000c8d6  mov     [r15], rdi
0x18000c8d9  mov     rdi, r12
0x18000c8dc  test    rdi, rdi
0x18000c8df  jz      short loc_18000C8F7
0x18000c8e1  mov     edx, r13d; fCancelPendingCallbacks
0x18000c8e4  mov     rcx, rdi; pwk
0x18000c8e7  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000c8ed  mov     rcx, rdi; pwk
0x18000c8f0  call    cs:__imp_CloseThreadpoolWork
0x18000c8f6  nop
0x18000c8f7  mov     rax, r14
0x18000c8fa  mov     rbx, [rsp+68h+arg_8]
0x18000c8ff  add     rsp, 30h
0x18000c903  pop     r15
0x18000c905  pop     r14
0x18000c907  pop     r13
0x18000c909  pop     r12
0x18000c90b  pop     rdi
0x18000c90c  pop     rsi
0x18000c90d  pop     rbp
0x18000c90e  retn
0x18000c90f  mov     edx, 75h ; 'u'; void *
0x18000c914  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c91a  mov     edx, 6Ah ; 'j'; void *
0x18000c91f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c925  mov     edx, 6Dh ; 'm'; void *
0x18000c92a  mov     rcx, rbx; this
0x18000c92d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
