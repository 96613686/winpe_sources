# CIISHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180006340`
- end: `0x180006362`
- name: `?OnReadEntity@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001a60`

## pseudocode

```c
_BOOL8 __fastcall CIISHttpModule::OnReadEntity(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(0x40000000, (__int64)a2, a2, a3, 0);
}

```

## disassembly

```asm
0x180006340  sub     rsp, 38h
0x180006344  mov     r9, r8
0x180006347  mov     [rsp+38h+var_18], 0
0x180006350  mov     r8, rdx
0x180006353  mov     ecx, 40000000h
0x180006358  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x18000635d  add     rsp, 38h
0x180006361  retn
```
