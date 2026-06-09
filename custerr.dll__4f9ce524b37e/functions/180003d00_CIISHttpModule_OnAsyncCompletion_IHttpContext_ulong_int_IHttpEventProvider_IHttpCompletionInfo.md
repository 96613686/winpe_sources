# CIISHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180003d00`
- end: `0x180003d17`
- name: `?OnAsyncCompletion@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000471c`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnAsyncCompletion(
        int a1,
        struct IHttpContext *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  return RequestDoWork(a1, (int)a2, a2, a5, a6);
}

```

## disassembly

```asm
0x180003d00  mov     rax, [rsp+arg_28]
0x180003d05  mov     r8, rdx
0x180003d08  mov     r9, [rsp+arg_20]
0x180003d0d  mov     [rsp+arg_20], rax
0x180003d12  jmp     ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
```
