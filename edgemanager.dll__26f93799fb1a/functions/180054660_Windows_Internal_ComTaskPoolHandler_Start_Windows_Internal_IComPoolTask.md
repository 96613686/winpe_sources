# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x180054660`
- end: `0x1800546a3`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180053770`
- `0x180053820`
- `0x1800538d0`
- `0x180056580`
- `0x18005ff70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054670`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054670`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180054692`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180054692`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::Start(
        Windows::Internal::ComTaskPoolHandler *this,
        struct Windows::Internal::IComPoolTask *a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx

  CurrentThreadId = GetCurrentThreadId();
  v5 = *((unsigned int *)this + 1);
  v6 = *(unsigned int *)this;
  *((_DWORD *)this + 2) = CurrentThreadId;
  return SHTaskPoolQueueTask(v6, v5, CurrentThreadId, 0, a2, 0);
}

```

## disassembly

```asm
0x180054660  mov     [rsp+arg_0], rbx
0x180054665  push    rdi
0x180054666  sub     rsp, 30h
0x18005466a  mov     rbx, rdx
0x18005466d  mov     rdi, rcx
0x180054670  call    cs:__imp_GetCurrentThreadId
0x180054676  mov     edx, [rdi+4]
0x180054679  xor     r9d, r9d
0x18005467c  mov     ecx, [rdi]
0x18005467e  mov     r8d, eax
0x180054681  mov     [rsp+38h+var_10], 0
0x18005468a  mov     [rdi+8], eax
0x18005468d  mov     [rsp+38h+var_18], rbx
0x180054692  call    cs:__imp_SHTaskPoolQueueTask
0x180054698  mov     rbx, [rsp+38h+arg_0]
0x18005469d  add     rsp, 30h
0x1800546a1  pop     rdi
0x1800546a2  retn
```
