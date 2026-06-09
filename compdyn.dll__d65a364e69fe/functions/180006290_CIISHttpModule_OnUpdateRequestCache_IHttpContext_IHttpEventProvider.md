# CIISHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180006290`
- end: `0x1800062b2`
- name: `?OnUpdateRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180001a60`

## pseudocode

```c
_BOOL8 __fastcall CIISHttpModule::OnUpdateRequestCache(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(512, (__int64)a2, a2, a3, 0);
}

```

## disassembly

```asm
0x180006290  sub     rsp, 38h
0x180006294  mov     r9, r8
0x180006297  mov     [rsp+38h+var_18], 0
0x1800062a0  mov     r8, rdx
0x1800062a3  mov     ecx, 200h
0x1800062a8  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x1800062ad  add     rsp, 38h
0x1800062b1  retn
```
