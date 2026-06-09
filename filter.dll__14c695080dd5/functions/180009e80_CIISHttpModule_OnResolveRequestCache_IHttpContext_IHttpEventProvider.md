# CIISHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180009e80`
- end: `0x180009ea2`
- name: `?OnResolveRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800019c0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnResolveRequestCache(__int64 a1, __int64 *a2, struct ISendResponseProvider *a3)
{
  return RequestDoWork(8, 0, a2, a3, 0);
}

```

## disassembly

```asm
0x180009e80  sub     rsp, 38h
0x180009e84  mov     r9, r8
0x180009e87  mov     [rsp+38h+var_18], 0
0x180009e90  mov     r8, rdx
0x180009e93  xor     edx, edx
0x180009e95  lea     ecx, [rdx+8]
0x180009e98  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180009e9d  add     rsp, 38h
0x180009ea1  retn
```
