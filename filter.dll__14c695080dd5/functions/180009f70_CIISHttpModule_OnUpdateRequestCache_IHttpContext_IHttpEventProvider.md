# CIISHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180009f70`
- end: `0x180009f94`
- name: `?OnUpdateRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800019c0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnUpdateRequestCache(__int64 a1, __int64 *a2, struct ISendResponseProvider *a3)
{
  return RequestDoWork(512, 0, a2, a3, 0);
}

```

## disassembly

```asm
0x180009f70  sub     rsp, 38h
0x180009f74  mov     r9, r8
0x180009f77  mov     [rsp+38h+var_18], 0
0x180009f80  mov     r8, rdx
0x180009f83  mov     ecx, 200h
0x180009f88  xor     edx, edx
0x180009f8a  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180009f8f  add     rsp, 38h
0x180009f93  retn
```
