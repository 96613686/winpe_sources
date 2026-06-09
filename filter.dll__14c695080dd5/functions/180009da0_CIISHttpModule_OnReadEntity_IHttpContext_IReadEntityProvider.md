# CIISHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180009da0`
- end: `0x180009dc4`
- name: `?OnReadEntity@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800019c0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnReadEntity(__int64 a1, __int64 *a2, struct ISendResponseProvider *a3)
{
  return RequestDoWork(0x40000000, 0, a2, a3, 0);
}

```

## disassembly

```asm
0x180009da0  sub     rsp, 38h
0x180009da4  mov     r9, r8
0x180009da7  mov     [rsp+38h+var_18], 0
0x180009db0  mov     r8, rdx
0x180009db3  mov     ecx, 40000000h
0x180009db8  xor     edx, edx
0x180009dba  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180009dbf  add     rsp, 38h
0x180009dc3  retn
```
