# CEffectCompilationTask::Initialize(void)

- ea: `0x1801e38ec`
- end: `0x1801e392d`
- name: `?Initialize@CEffectCompilationTask@@AEAAJXZ`
- size: `65`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f5f88`

## callees

- `0x1801e38ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e3919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e3919`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801e3902`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801e3902`

## pseudocode

```c
signed int __fastcall CEffectCompilationTask::Initialize(PVOID pv)
{
  PTP_WORK ThreadpoolWork; // rax
  signed int result; // eax

  ThreadpoolWork = CreateThreadpoolWork(
                     CEffectCompilationTask::Initialize_::_2_::_lambda_1_::_lambda_invoker_cdecl_,
                     pv,
                     0);
  *((_QWORD *)pv + 8) = ThreadpoolWork;
  if ( ThreadpoolWork )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1801e38ec  push    rbx
0x1801e38ee  sub     rsp, 20h
0x1801e38f2  mov     rbx, rcx
0x1801e38f5  mov     rdx, rcx; pv
0x1801e38f8  lea     rcx, _CEffectCompilationTask__Initialize____2____lambda_1____lambda_invoker_cdecl_; pfnwk
0x1801e38ff  xor     r8d, r8d; pcbe
0x1801e3902  call    cs:__imp_CreateThreadpoolWork
0x1801e3908  mov     [rbx+40h], rax
0x1801e390c  test    rax, rax
0x1801e390f  jz      short loc_1801E3919
0x1801e3911  xor     eax, eax
0x1801e3913  add     rsp, 20h
0x1801e3917  pop     rbx
0x1801e3918  retn
0x1801e3919  call    cs:__imp_GetLastError
0x1801e391f  test    eax, eax
0x1801e3921  jle     short loc_1801E3913
0x1801e3923  movzx   eax, ax
0x1801e3926  or      eax, 80070000h
0x1801e392b  jmp     short loc_1801E3913
```
