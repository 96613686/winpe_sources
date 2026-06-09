# CIISHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180001a80`
- end: `0x180001a90`
- name: `?OnAsyncCompletion@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800022a0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnAsyncCompletion(
        __int64 a1,
        struct IHttpContext *a2,
        int a3,
        __int64 a4,
        void (__fastcall ***a5)(_QWORD, __int64))
{
  return RequestDoWork(a3, (__int64)a2, a2, a5);
}

```

## disassembly

```asm
0x180001a80  mov     r9, [rsp+arg_20]
0x180001a85  mov     ecx, r8d
0x180001a88  mov     r8, rdx
0x180001a8b  jmp     ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
```
