# CIISHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180006ab0`
- end: `0x180006ac9`
- name: `?OnMapPath@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnMapPath(__int64 a1, struct IHttpContext *a2, __int64 a3)
{
  return RequestDoWork(0x80000000, (__int64)a2, a2, a3);
}

```

## disassembly

```asm
0x180006ab0  sub     rsp, 38h
0x180006ab4  mov     r9, r8
0x180006ab7  mov     ecx, 80000000h
0x180006abc  mov     r8, rdx
0x180006abf  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180006ac4  add     rsp, 38h
0x180006ac8  retn
```
