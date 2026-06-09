# CIISHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180004300`
- end: `0x180004322`
- name: `?OnResolveRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001080`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnResolveRequestCache(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(8, (__int64)a2, a2, a3, 0);
}

```

## disassembly

```asm
0x180004300  sub     rsp, 38h
0x180004304  mov     r9, r8
0x180004307  mov     [rsp+38h+var_18], 0
0x180004310  mov     r8, rdx
0x180004313  mov     ecx, 8
0x180004318  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x18000431d  add     rsp, 38h
0x180004321  retn
```
