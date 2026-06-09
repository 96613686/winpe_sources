# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x180182928`
- end: `0x18018296b`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180181280`
- `0x180181330`
- `0x1801813e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180182938`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180182938`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18018295a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18018295a`

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
0x180182928  mov     [rsp+arg_0], rbx
0x18018292d  push    rdi
0x18018292e  sub     rsp, 30h
0x180182932  mov     rbx, rdx
0x180182935  mov     rdi, rcx
0x180182938  call    cs:__imp_GetCurrentThreadId
0x18018293e  mov     edx, [rdi+4]
0x180182941  xor     r9d, r9d
0x180182944  mov     ecx, [rdi]
0x180182946  mov     r8d, eax
0x180182949  mov     [rsp+38h+var_10], 0
0x180182952  mov     [rdi+8], eax
0x180182955  mov     [rsp+38h+var_18], rbx
0x18018295a  call    cs:__imp_SHTaskPoolQueueTask
0x180182960  mov     rbx, [rsp+38h+arg_0]
0x180182965  add     rsp, 30h
0x180182969  pop     rdi
0x18018296a  retn
```
