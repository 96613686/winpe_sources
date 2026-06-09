# CIISHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800021a0`
- end: `0x1800021b5`
- name: `?OnAsyncCompletion@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002acc`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnAsyncCompletion(
        __int64 a1,
        struct IHttpContext *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        void (__fastcall ***a6)(_QWORD))
{
  return RequestDoWork(a3, (__int64)a2, a2, a4, a6);
}

```

## disassembly

```asm
0x1800021a0  mov     rax, [rsp+arg_28]
0x1800021a5  mov     ecx, r8d
0x1800021a8  mov     r8, rdx
0x1800021ab  mov     [rsp+arg_20], rax
0x1800021b0  jmp     ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
```
