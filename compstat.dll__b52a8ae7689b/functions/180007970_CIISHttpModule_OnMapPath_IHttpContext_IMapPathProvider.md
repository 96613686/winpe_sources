# CIISHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180007970`
- end: `0x180007989`
- name: `?OnMapPath@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800010b0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnMapPath(__int64 a1, struct IHttpContext *a2, struct IMapHandlerProvider *a3)
{
  __int64 v4; // [rsp+20h] [rbp-18h]

  return RequestDoWork(0x80000000, (__int64)a2, a2, a3, v4);
}

```

## disassembly

```asm
0x180007970  sub     rsp, 38h
0x180007974  mov     r9, r8
0x180007977  mov     ecx, 80000000h
0x18000797c  mov     r8, rdx
0x18000797f  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180007984  add     rsp, 38h
0x180007988  retn
```
