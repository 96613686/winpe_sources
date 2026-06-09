# CIISHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180006a90`
- end: `0x180006ab5`
- name: `?OnPostResolveRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001020`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnPostResolveRequestCache(__int64 a1, struct IHttpContext *a2)
{
  return RequestDoWork(8, 1, a2);
}

```

## disassembly

```asm
0x180006a90  sub     rsp, 38h
0x180006a94  mov     r9, r8
0x180006a97  mov     [rsp+38h+var_18], 0
0x180006aa0  mov     r8, rdx
0x180006aa3  mov     edx, 1
0x180006aa8  lea     ecx, [rdx+7]
0x180006aab  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180006ab0  add     rsp, 38h
0x180006ab4  retn
```
