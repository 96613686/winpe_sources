# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x180181250`
- end: `0x18018126f`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180183170`
- `0x1801831c8`
- `0x180183220`

## callees

- `0x180181250`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180181259`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180181259`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180181263`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180181263`

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
0x180181250  push    rbx
0x180181252  sub     rsp, 20h
0x180181256  mov     ebx, [rcx+8]
0x180181259  call    cs:__imp_GetCurrentThreadId
0x18018125f  cmp     eax, ebx
0x180181261  jz      short loc_180181269
0x180181263  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180181269  add     rsp, 20h
0x18018126d  pop     rbx
0x18018126e  retn
```
