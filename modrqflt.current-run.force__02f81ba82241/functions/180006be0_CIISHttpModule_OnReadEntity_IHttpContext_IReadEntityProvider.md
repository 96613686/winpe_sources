# CIISHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180006be0`
- end: `0x180006c04`
- name: `?OnReadEntity@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001020`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnReadEntity(__int64 a1, struct IHttpContext *a2)
{
  return RequestDoWork(0x40000000, 0, a2);
}

```

## disassembly

```asm
0x180006be0  sub     rsp, 38h
0x180006be4  mov     r9, r8
0x180006be7  mov     [rsp+38h+var_18], 0
0x180006bf0  mov     r8, rdx
0x180006bf3  mov     ecx, 40000000h
0x180006bf8  xor     edx, edx
0x180006bfa  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180006bff  add     rsp, 38h
0x180006c03  retn
```
