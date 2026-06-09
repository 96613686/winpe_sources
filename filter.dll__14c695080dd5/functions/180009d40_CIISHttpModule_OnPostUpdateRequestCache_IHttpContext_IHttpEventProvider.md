# CIISHttpModule::OnPostUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180009d40`
- end: `0x180009d67`
- name: `?OnPostUpdateRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800019c0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnPostUpdateRequestCache(__int64 a1, __int64 *a2, struct ISendResponseProvider *a3)
{
  return RequestDoWork(512, 1, a2, a3, 0);
}

```

## disassembly

```asm
0x180009d40  sub     rsp, 38h
0x180009d44  mov     r9, r8
0x180009d47  mov     [rsp+38h+var_18], 0
0x180009d50  mov     r8, rdx
0x180009d53  mov     ecx, 200h
0x180009d58  mov     edx, 1
0x180009d5d  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180009d62  add     rsp, 38h
0x180009d66  retn
```
