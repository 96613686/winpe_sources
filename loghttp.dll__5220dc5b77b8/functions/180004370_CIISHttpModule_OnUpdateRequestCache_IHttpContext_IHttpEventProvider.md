# CIISHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180004370`
- end: `0x180004392`
- name: `?OnUpdateRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180001080`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnUpdateRequestCache(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(512, (__int64)a2, a2, a3, 0);
}

```

## disassembly

```asm
0x180004370  sub     rsp, 38h
0x180004374  mov     r9, r8
0x180004377  mov     [rsp+38h+var_18], 0
0x180004380  mov     r8, rdx
0x180004383  mov     ecx, 200h
0x180004388  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x18000438d  add     rsp, 38h
0x180004391  retn
```
