# CIISHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800062a0`
- end: `0x1800062c0`
- name: `?OnAsyncCompletion@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001020`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnAsyncCompletion(__int64 a1, struct IHttpContext *a2, int a3, int a4)
{
  return RequestDoWork(a3, a4, a2);
}

```

## disassembly

```asm
0x1800062a0  mov     rax, [rsp+arg_28]
0x1800062a5  mov     r10d, r9d
0x1800062a8  mov     r9, [rsp+arg_20]
0x1800062ad  mov     ecx, r8d
0x1800062b0  mov     r8, rdx
0x1800062b3  mov     [rsp+arg_20], rax
0x1800062b8  mov     edx, r10d
0x1800062bb  jmp     ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
```
