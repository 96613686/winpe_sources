# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x18002b7a8`
- end: `0x18002b7eb`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180029470`
- `0x180029520`
- `0x1800295d0`
- `0x180032e80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b7b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b7b8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002b7da`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002b7da`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::Start(
        Windows::Internal::ComTaskPoolHandler *this,
        struct Windows::Internal::IComPoolTask *a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx

  CurrentThreadId = GetCurrentThreadId();
  v4 = *((unsigned int *)this + 1);
  v5 = *(unsigned int *)this;
  *((_DWORD *)this + 2) = CurrentThreadId;
  return SHTaskPoolQueueTask(v5, v4, CurrentThreadId, 0);
}

```

## disassembly

```asm
0x18002b7a8  mov     [rsp+arg_0], rbx
0x18002b7ad  push    rdi
0x18002b7ae  sub     rsp, 30h
0x18002b7b2  mov     rbx, rdx
0x18002b7b5  mov     rdi, rcx
0x18002b7b8  call    cs:__imp_GetCurrentThreadId
0x18002b7be  mov     edx, [rdi+4]
0x18002b7c1  xor     r9d, r9d
0x18002b7c4  mov     ecx, [rdi]
0x18002b7c6  mov     r8d, eax
0x18002b7c9  mov     [rsp+38h+var_10], 0
0x18002b7d2  mov     [rdi+8], eax
0x18002b7d5  mov     [rsp+38h+var_18], rbx
0x18002b7da  call    cs:__imp_SHTaskPoolQueueTask
0x18002b7e0  mov     rbx, [rsp+38h+arg_0]
0x18002b7e5  add     rsp, 30h
0x18002b7e9  pop     rdi
0x18002b7ea  retn
```
