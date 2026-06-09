# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x180029440`
- end: `0x18002945f`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c258`
- `0x18002c2b0`
- `0x18002c308`
- `0x180033700`

## callees

- `0x180029440`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029449`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029449`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180029453`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180029453`

## pseudocode

```c
void __fastcall Windows::Internal::ComTaskPoolHandler::OnComplete(Windows::Internal::ComTaskPoolHandler *this)
{
  int v1; // ebx

  v1 = *((_DWORD *)this + 2);
  if ( GetCurrentThreadId() != v1 )
    SHTaskPoolAllowThreadReuse();
}

```

## disassembly

```asm
0x180029440  push    rbx
0x180029442  sub     rsp, 20h
0x180029446  mov     ebx, [rcx+8]
0x180029449  call    cs:__imp_GetCurrentThreadId
0x18002944f  cmp     eax, ebx
0x180029451  jz      short loc_180029459
0x180029453  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180029459  add     rsp, 20h
0x18002945d  pop     rbx
0x18002945e  retn
```
