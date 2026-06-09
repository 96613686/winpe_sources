# SI_DISPATCH::Dispatch(void)

- ea: `0x1801afa60`
- end: `0x1801afb28`
- name: `?Dispatch@SI_DISPATCH@@QEAAHXZ`
- size: `200`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1801b11f0`

## callees

- `0x1801afa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801afaaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801afaaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801afab9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801afab9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801afa89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801afa89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801afa9e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801afa9e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801afad2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801afad2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801afafa`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801afafa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801afb0e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801afb0e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801afb17`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801afb17`

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
0x1801afa60  push    rbx
0x1801afa62  push    rbp
0x1801afa63  push    rsi
0x1801afa64  push    rdi
0x1801afa65  sub     rsp, 28h
0x1801afa69  mov     rax, [rcx+8]
0x1801afa6d  mov     esi, 1
0x1801afa72  mov     rdi, rcx
0x1801afa75  mov     ebx, esi
0x1801afa77  test    rax, rax
0x1801afa7a  jz      loc_1801AFB1D
0x1801afa80  cmp     [rax], rax
0x1801afa83  jz      loc_1801AFB1D
0x1801afa89  call    cs:__imp_GetCurrentThread
0x1801afa8f  lea     r9, [rdi+38h]; TokenHandle
0x1801afa93  xor     r8d, r8d; OpenAsSelf
0x1801afa96  mov     rcx, rax; ThreadHandle
0x1801afa99  mov     edx, 2000Ch; DesiredAccess
0x1801afa9e  call    cs:__imp_OpenThreadToken
0x1801afaa4  mov     ebx, eax
0x1801afaa6  test    eax, eax
0x1801afaa8  jnz     short loc_1801AFAC1
0x1801afaaa  call    cs:__imp_GetLastError
0x1801afab0  cmp     eax, 3F0h
0x1801afab5  jnz     short loc_1801AFB1D
0x1801afab7  xor     ecx, ecx; dwErrCode
0x1801afab9  call    cs:__imp_SetLastError
0x1801afabf  mov     ebx, esi
0x1801afac1  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1801afac8  mov     rdx, rdi; pv
0x1801afacb  lea     rcx, ?Callback@SI_DISPATCH@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801afad2  call    cs:__imp_CreateThreadpoolWork
0x1801afad8  mov     rbp, rax
0x1801afadb  test    rax, rax
0x1801afade  jnz     short loc_1801AFAE4
0x1801afae0  xor     ebx, ebx
0x1801afae2  jmp     short loc_1801AFB1D
0x1801afae4  mov     rcx, [rdi+8]
0x1801afae8  mov     rax, [rcx]
0x1801afaeb  mov     [rdi+30h], rax
0x1801afaef  mov     rsi, [rcx]
0x1801afaf2  cmp     rsi, rcx
0x1801afaf5  jz      short loc_1801AFB09
0x1801afaf7  mov     rcx, rbp; pwk
0x1801afafa  call    cs:__imp_SubmitThreadpoolWork
0x1801afb00  mov     rsi, [rsi]
0x1801afb03  cmp     rsi, [rdi+8]
0x1801afb07  jnz     short loc_1801AFAF7
0x1801afb09  xor     edx, edx; fCancelPendingCallbacks
0x1801afb0b  mov     rcx, rbp; pwk
0x1801afb0e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1801afb14  mov     rcx, rbp; pwk
0x1801afb17  call    cs:__imp_CloseThreadpoolWork
0x1801afb1d  mov     eax, ebx
0x1801afb1f  add     rsp, 28h
0x1801afb23  pop     rdi
0x1801afb24  pop     rsi
0x1801afb25  pop     rbp
0x1801afb26  pop     rbx
0x1801afb27  retn
```
