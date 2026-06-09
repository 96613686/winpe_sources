# CIISHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180007d10`
- end: `0x180007d29`
- name: `?OnUpdateRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800010b0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnUpdateRequestCache(
        __int64 a1,
        struct IHttpContext *a2,
        struct IMapHandlerProvider *a3)
{
  __int64 v4; // [rsp+20h] [rbp-18h]

  return RequestDoWork(512, (__int64)a2, a2, a3, v4);
}

```

## disassembly

```asm
0x180007d10  sub     rsp, 38h
0x180007d14  mov     r9, r8
0x180007d17  mov     ecx, 200h
0x180007d1c  mov     r8, rdx
0x180007d1f  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180007d24  add     rsp, 38h
0x180007d28  retn
```
