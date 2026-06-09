# CIISHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180006b00`
- end: `0x180006b27`
- name: `?OnPostUpdateRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180001020`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnPostUpdateRequestCache(__int64 a1, struct IHttpContext *a2)
{
  return RequestDoWork(512, 1, a2);
}

```

## disassembly

```asm
0x180006b00  sub     rsp, 38h
0x180006b04  mov     r9, r8
0x180006b07  mov     [rsp+38h+var_18], 0
0x180006b10  mov     r8, rdx
0x180006b13  mov     ecx, 200h
0x180006b18  mov     edx, 1
0x180006b1d  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180006b22  add     rsp, 38h
0x180006b26  retn
```
