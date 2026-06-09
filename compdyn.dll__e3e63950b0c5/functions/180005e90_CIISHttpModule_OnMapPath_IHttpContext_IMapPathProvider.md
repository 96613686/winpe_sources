# CIISHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180005e90`
- end: `0x180005eb2`
- name: `?OnMapPath@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001a60`

## pseudocode

```c
_BOOL8 __fastcall CIISHttpModule::OnMapPath(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(0x80000000, (__int64)a2, a2, a3, 0);
}

```

## disassembly

```asm
0x180005e90  sub     rsp, 38h
0x180005e94  mov     r9, r8
0x180005e97  mov     [rsp+38h+var_18], 0
0x180005ea0  mov     r8, rdx
0x180005ea3  mov     ecx, 80000000h
0x180005ea8  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180005ead  add     rsp, 38h
0x180005eb1  retn
```
