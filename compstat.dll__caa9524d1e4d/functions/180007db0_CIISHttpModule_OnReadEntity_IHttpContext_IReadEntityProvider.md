# CIISHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180007db0`
- end: `0x180007dc9`
- name: `?OnReadEntity@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800010b0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnReadEntity(__int64 a1, struct IHttpContext *a2, struct IMapHandlerProvider *a3)
{
  __int64 v4; // [rsp+20h] [rbp-18h]

  return RequestDoWork(0x40000000, (__int64)a2, a2, a3, v4);
}

```

## disassembly

```asm
0x180007db0  sub     rsp, 38h
0x180007db4  mov     r9, r8
0x180007db7  mov     ecx, 40000000h
0x180007dbc  mov     r8, rdx
0x180007dbf  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180007dc4  add     rsp, 38h
0x180007dc8  retn
```
