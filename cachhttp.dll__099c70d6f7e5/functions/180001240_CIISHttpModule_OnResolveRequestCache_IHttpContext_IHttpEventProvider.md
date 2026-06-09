# CIISHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001240`
- end: `0x180001259`
- name: `?OnResolveRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(__int64, struct IHttpContext *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnResolveRequestCache(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(8, (__int64)a2, a2, a3);
}

```

## disassembly

```asm
0x180001240  sub     rsp, 38h
0x180001244  mov     r9, r8
0x180001247  mov     ecx, 8
0x18000124c  mov     r8, rdx
0x18000124f  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180001254  add     rsp, 38h
0x180001258  retn
```
