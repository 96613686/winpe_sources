# CIISHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800093f0`
- end: `0x180009410`
- name: `?OnAsyncCompletion@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800019c0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnAsyncCompletion(
        __int64 a1,
        __int64 *a2,
        int a3,
        int a4,
        struct ISendResponseProvider *a5,
        __int64 a6)
{
  return RequestDoWork(a3, a4, a2, a5, a6);
}

```

## disassembly

```asm
0x1800093f0  mov     rax, [rsp+arg_28]
0x1800093f5  mov     r10d, r9d
0x1800093f8  mov     r9, [rsp+arg_20]
0x1800093fd  mov     ecx, r8d
0x180009400  mov     r8, rdx
0x180009403  mov     [rsp+arg_20], rax
0x180009408  mov     edx, r10d
0x18000940b  jmp     ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
```
