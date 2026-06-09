# CSOperationDispatcher::_TryEnsureThreadpoolWorkCreated(void)

- ea: `0x1800139d0`
- end: `0x180013a6e`
- name: `?_TryEnsureThreadpoolWorkCreated@CSOperationDispatcher@@AEAA_NXZ`
- size: `158`
- prototype: `bool __fastcall(struct _TP_WORK **pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000c63c`
- `0x180020354`
- `0x180020660`

## callees

- `0x1800133fc`
- `0x1800139d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a1b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180013a2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180013a4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180013a2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180013a4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180013a34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180013a58`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180013a34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180013a58`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800139ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800139ef`

## pseudocode

```c
bool __fastcall CSOperationDispatcher::_TryEnsureThreadpoolWorkCreated(struct _TP_WORK **pv)
{
  void *v2; // rdx
  struct _TP_WORK *ThreadpoolWork; // rsi
  unsigned int v4; // r8d
  const char *v5; // r9
  struct _TP_WORK *v6; // rbp
  DWORD LastError; // ebx
  char v9; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !*pv )
  {
    ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)CSOperationDispatcher::_ThreadpoolWorkCallback, pv, 0);
    if ( ThreadpoolWork )
    {
      if ( pv == (struct _TP_WORK **)&v9 )
      {
        WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 1);
        CloseThreadpoolWork(ThreadpoolWork);
      }
      else
      {
        v6 = *pv;
        if ( *pv )
        {
          LastError = GetLastError();
          WaitForThreadpoolWorkCallbacks(v6, 1);
          CloseThreadpoolWork(v6);
          SetLastError(LastError);
        }
        *pv = ThreadpoolWork;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(retaddr, v2, v4, v5);
    }
  }
  return *pv != 0;
}

```

## disassembly

```asm
0x1800139d0  push    rbx
0x1800139d2  push    rbp
0x1800139d3  push    rsi
0x1800139d4  push    rdi
0x1800139d5  sub     rsp, 38h
0x1800139d9  cmp     qword ptr [rcx], 0
0x1800139dd  mov     rdi, rcx
0x1800139e0  jnz     short loc_180013A5E
0x1800139e2  mov     rdx, rcx; pv
0x1800139e5  xor     r8d, r8d; pcbe
0x1800139e8  lea     rcx, ?_ThreadpoolWorkCallback@CSOperationDispatcher@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800139ef  call    cs:__imp_CreateThreadpoolWork
0x1800139f5  mov     rcx, [rsp+58h]; this
0x1800139fa  mov     rsi, rax
0x1800139fd  test    rax, rax
0x180013a00  jnz     short loc_180013A09
0x180013a02  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180013a07  jmp     short loc_180013A5E
0x180013a09  lea     rax, [rsp+58h+var_38]
0x180013a0e  cmp     rdi, rax
0x180013a11  jz      short loc_180013A47
0x180013a13  mov     rbp, [rdi]
0x180013a16  test    rbp, rbp
0x180013a19  jz      short loc_180013A42
0x180013a1b  call    cs:__imp_GetLastError
0x180013a21  mov     edx, 1; fCancelPendingCallbacks
0x180013a26  mov     rcx, rbp; pwk
0x180013a29  mov     ebx, eax
0x180013a2b  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180013a31  mov     rcx, rbp; pwk
0x180013a34  call    cs:__imp_CloseThreadpoolWork
0x180013a3a  mov     ecx, ebx; dwErrCode
0x180013a3c  call    cs:__imp_SetLastError
0x180013a42  mov     [rdi], rsi
0x180013a45  jmp     short loc_180013A5E
0x180013a47  mov     edx, 1; fCancelPendingCallbacks
0x180013a4c  mov     rcx, rsi; pwk
0x180013a4f  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180013a55  mov     rcx, rsi; pwk
0x180013a58  call    cs:__imp_CloseThreadpoolWork
0x180013a5e  cmp     qword ptr [rdi], 0
0x180013a62  setnz   al
0x180013a65  add     rsp, 38h
0x180013a69  pop     rdi
0x180013a6a  pop     rsi
0x180013a6b  pop     rbp
0x180013a6c  pop     rbx
0x180013a6d  retn
```
