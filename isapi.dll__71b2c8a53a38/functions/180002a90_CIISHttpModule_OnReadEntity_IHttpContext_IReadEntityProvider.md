# CIISHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180002a90`
- end: `0x180002ab2`
- name: `?OnReadEntity@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002d9c`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnReadEntity(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(0x40000000, (__int64)a2, a2, a3, 0);
}

```

## disassembly

```asm
0x180002a90  sub     rsp, 38h
0x180002a94  mov     r9, r8
0x180002a97  mov     [rsp+38h+var_18], 0
0x180002aa0  mov     r8, rdx
0x180002aa3  mov     ecx, 40000000h
0x180002aa8  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180002aad  add     rsp, 38h
0x180002ab1  retn
```
