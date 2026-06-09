# CIISHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180007670`
- end: `0x180007680`
- name: `?OnAsyncCompletion@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800010b0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnAsyncCompletion(
        __int64 a1,
        struct IHttpContext *a2,
        int a3,
        __int64 a4,
        struct IMapHandlerProvider *a5)
{
  return RequestDoWork(a3, (__int64)a2, a2, a5, (__int64)a5);
}

```

## disassembly

```asm
0x180007670  mov     r9, [rsp+arg_20]
0x180007675  mov     ecx, r8d
0x180007678  mov     r8, rdx
0x18000767b  jmp     ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
```
