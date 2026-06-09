# CIISHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180006cc0`
- end: `0x180006ce2`
- name: `?OnResolveRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001020`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnResolveRequestCache(__int64 a1, struct IHttpContext *a2)
{
  return RequestDoWork(8, 0, a2);
}

```

## disassembly

```asm
0x180006cc0  sub     rsp, 38h
0x180006cc4  mov     r9, r8
0x180006cc7  mov     [rsp+38h+var_18], 0
0x180006cd0  mov     r8, rdx
0x180006cd3  xor     edx, edx
0x180006cd5  lea     ecx, [rdx+8]
0x180006cd8  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180006cdd  add     rsp, 38h
0x180006ce1  retn
```
