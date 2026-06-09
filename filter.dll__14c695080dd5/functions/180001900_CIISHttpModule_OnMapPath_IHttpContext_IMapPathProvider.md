# CIISHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180001900`
- end: `0x180001924`
- name: `?OnMapPath@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800019c0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnMapPath(__int64 a1, __int64 *a2, struct ISendResponseProvider *a3)
{
  return RequestDoWork(0x80000000, 0, a2, a3, 0);
}

```

## disassembly

```asm
0x180001900  sub     rsp, 38h
0x180001904  mov     r9, r8
0x180001907  mov     [rsp+38h+var_18], 0
0x180001910  mov     r8, rdx
0x180001913  mov     ecx, 80000000h
0x180001918  xor     edx, edx
0x18000191a  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x18000191f  add     rsp, 38h
0x180001923  retn
```
