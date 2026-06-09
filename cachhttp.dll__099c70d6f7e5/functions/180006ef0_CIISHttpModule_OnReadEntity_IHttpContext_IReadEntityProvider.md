# CIISHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180006ef0`
- end: `0x180006f09`
- name: `?OnReadEntity@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnReadEntity(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(0x40000000, (__int64)a2, a2, a3);
}

```

## disassembly

```asm
0x180006ef0  sub     rsp, 38h
0x180006ef4  mov     r9, r8
0x180006ef7  mov     ecx, 40000000h
0x180006efc  mov     r8, rdx
0x180006eff  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180006f04  add     rsp, 38h
0x180006f08  retn
```
