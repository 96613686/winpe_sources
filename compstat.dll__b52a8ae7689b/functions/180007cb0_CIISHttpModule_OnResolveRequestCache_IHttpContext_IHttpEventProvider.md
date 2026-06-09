# CIISHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180007cb0`
- end: `0x180007cc9`
- name: `?OnResolveRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800010b0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnResolveRequestCache(
        __int64 a1,
        struct IHttpContext *a2,
        struct IMapHandlerProvider *a3)
{
  __int64 v4; // [rsp+20h] [rbp-18h]

  return RequestDoWork(8, (__int64)a2, a2, a3, v4);
}

```

## disassembly

```asm
0x180007cb0  sub     rsp, 38h
0x180007cb4  mov     r9, r8
0x180007cb7  mov     ecx, 8
0x180007cbc  mov     r8, rdx
0x180007cbf  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180007cc4  add     rsp, 38h
0x180007cc8  retn
```
