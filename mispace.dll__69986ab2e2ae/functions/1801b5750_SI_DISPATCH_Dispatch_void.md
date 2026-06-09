# SI_DISPATCH::Dispatch(void)

- ea: `0x1801b5750`
- end: `0x1801b584d`
- name: `?Dispatch@SI_DISPATCH@@QEAAHXZ`
- size: `253`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1801b7130`

## callees

- `0x1801b5750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b57a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b57a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b57bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b57bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b5779`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b5779`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b5794`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b5794`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801b57de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801b57de`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801b580c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801b580c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801b5826`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801b5826`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801b5835`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801b5835`

## pseudocode

```c
__int64 __fastcall SI_DISPATCH::Dispatch(PVOID pv)
{
  _QWORD *v1; // rax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  struct _TP_WORK *ThreadpoolWork; // rbp
  _QWORD *v6; // rcx
  _QWORD *v7; // rsi

  v1 = (_QWORD *)*((_QWORD *)pv + 1);
  v3 = 1;
  if ( v1 && (_QWORD *)*v1 != v1 )
  {
    CurrentThread = GetCurrentThread();
    v3 = OpenThreadToken(CurrentThread, 0x2000Cu, 0, (PHANDLE)pv + 7);
    if ( !v3 )
    {
      if ( GetLastError() != 1008 )
        return v3;
      SetLastError(0);
      v3 = 1;
    }
    ThreadpoolWork = CreateThreadpoolWork(SI_DISPATCH::Callback, pv, &ThreadpoolEnv);
    if ( ThreadpoolWork )
    {
      v6 = (_QWORD *)*((_QWORD *)pv + 1);
      *((_QWORD *)pv + 6) = *v6;
      v7 = (_QWORD *)*v6;
      if ( (_QWORD *)*v6 != v6 )
      {
        do
        {
          SubmitThreadpoolWork(ThreadpoolWork);
          v7 = (_QWORD *)*v7;
        }
        while ( v7 != *((_QWORD **)pv + 1) );
      }
      WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
      CloseThreadpoolWork(ThreadpoolWork);
    }
    else
    {
      return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1801b5750  push    rbx
0x1801b5752  push    rbp
0x1801b5753  push    rsi
0x1801b5754  push    rdi
0x1801b5755  sub     rsp, 28h
0x1801b5759  mov     rax, [rcx+8]
0x1801b575d  mov     esi, 1
0x1801b5762  mov     rdi, rcx
0x1801b5765  mov     ebx, esi
0x1801b5767  test    rax, rax
0x1801b576a  jz      loc_1801B5841
0x1801b5770  cmp     [rax], rax
0x1801b5773  jz      loc_1801B5841
0x1801b5779  call    cs:__imp_GetCurrentThread
0x1801b5780  nop     dword ptr [rax+rax+00h]
0x1801b5785  lea     r9, [rdi+38h]; TokenHandle
0x1801b5789  xor     r8d, r8d; OpenAsSelf
0x1801b578c  mov     rcx, rax; ThreadHandle
0x1801b578f  mov     edx, 2000Ch; DesiredAccess
0x1801b5794  call    cs:__imp_OpenThreadToken
0x1801b579b  nop     dword ptr [rax+rax+00h]
0x1801b57a0  mov     ebx, eax
0x1801b57a2  test    eax, eax
0x1801b57a4  jnz     short loc_1801B57CD
0x1801b57a6  call    cs:__imp_GetLastError
0x1801b57ad  nop     dword ptr [rax+rax+00h]
0x1801b57b2  cmp     eax, 3F0h
0x1801b57b7  jnz     loc_1801B5841
0x1801b57bd  xor     ecx, ecx; dwErrCode
0x1801b57bf  call    cs:__imp_SetLastError
0x1801b57c6  nop     dword ptr [rax+rax+00h]
0x1801b57cb  mov     ebx, esi
0x1801b57cd  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1801b57d4  mov     rdx, rdi; pv
0x1801b57d7  lea     rcx, ?Callback@SI_DISPATCH@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801b57de  call    cs:__imp_CreateThreadpoolWork
0x1801b57e5  nop     dword ptr [rax+rax+00h]
0x1801b57ea  mov     rbp, rax
0x1801b57ed  test    rax, rax
0x1801b57f0  jnz     short loc_1801B57F6
0x1801b57f2  xor     ebx, ebx
0x1801b57f4  jmp     short loc_1801B5841
0x1801b57f6  mov     rcx, [rdi+8]
0x1801b57fa  mov     rax, [rcx]
0x1801b57fd  mov     [rdi+30h], rax
0x1801b5801  mov     rsi, [rcx]
0x1801b5804  cmp     rsi, rcx
0x1801b5807  jz      short loc_1801B5821
0x1801b5809  mov     rcx, rbp; pwk
0x1801b580c  call    cs:__imp_SubmitThreadpoolWork
0x1801b5813  nop     dword ptr [rax+rax+00h]
0x1801b5818  mov     rsi, [rsi]
0x1801b581b  cmp     rsi, [rdi+8]
0x1801b581f  jnz     short loc_1801B5809
0x1801b5821  xor     edx, edx; fCancelPendingCallbacks
0x1801b5823  mov     rcx, rbp; pwk
0x1801b5826  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1801b582d  nop     dword ptr [rax+rax+00h]
0x1801b5832  mov     rcx, rbp; pwk
0x1801b5835  call    cs:__imp_CloseThreadpoolWork
0x1801b583c  nop     dword ptr [rax+rax+00h]
0x1801b5841  mov     eax, ebx
0x1801b5843  add     rsp, 28h
0x1801b5847  pop     rdi
0x1801b5848  pop     rsi
0x1801b5849  pop     rbp
0x1801b584a  pop     rbx
0x1801b584b  retn
```
