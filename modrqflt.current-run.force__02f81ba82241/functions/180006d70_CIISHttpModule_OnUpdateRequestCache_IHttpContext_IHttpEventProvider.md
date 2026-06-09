# CIISHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180006d70`
- end: `0x180006d94`
- name: `?OnUpdateRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180001020`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnUpdateRequestCache(__int64 a1, struct IHttpContext *a2)
{
  return RequestDoWork(512, 0, a2);
}

```

## disassembly

```asm
0x180006d70  sub     rsp, 38h
0x180006d74  mov     r9, r8
0x180006d77  mov     [rsp+38h+var_18], 0
0x180006d80  mov     r8, rdx
0x180006d83  mov     ecx, 200h
0x180006d88  xor     edx, edx
0x180006d8a  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180006d8f  add     rsp, 38h
0x180006d93  retn
```
