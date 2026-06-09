# CIISHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800029e0`
- end: `0x180002a02`
- name: `?OnUpdateRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180002d9c`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnUpdateRequestCache(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(512, (__int64)a2, a2, a3, 0);
}

```

## disassembly

```asm
0x1800029e0  sub     rsp, 38h
0x1800029e4  mov     r9, r8
0x1800029e7  mov     [rsp+38h+var_18], 0
0x1800029f0  mov     r8, rdx
0x1800029f3  mov     ecx, 200h
0x1800029f8  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x1800029fd  add     rsp, 38h
0x180002a01  retn
```
