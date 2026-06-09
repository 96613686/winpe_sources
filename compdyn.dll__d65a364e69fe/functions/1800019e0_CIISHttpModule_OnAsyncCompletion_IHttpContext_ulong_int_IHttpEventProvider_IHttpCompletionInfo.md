# CIISHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800019e0`
- end: `0x1800019fa`
- name: `?OnAsyncCompletion@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001a60`

## pseudocode

```c
_BOOL8 __fastcall CIISHttpModule::OnAsyncCompletion(
        __int64 a1,
        struct IHttpContext *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  return RequestDoWork(a3, (__int64)a2, a2, a5, a6);
}

```

## disassembly

```asm
0x1800019e0  mov     rax, [rsp+arg_28]
0x1800019e5  mov     ecx, r8d
0x1800019e8  mov     r9, [rsp+arg_20]
0x1800019ed  mov     r8, rdx
0x1800019f0  mov     [rsp+arg_20], rax
0x1800019f5  jmp     ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
```
