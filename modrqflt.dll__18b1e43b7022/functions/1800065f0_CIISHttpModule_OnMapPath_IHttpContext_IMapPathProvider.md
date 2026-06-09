# CIISHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x1800065f0`
- end: `0x180006614`
- name: `?OnMapPath@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001020`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnMapPath(__int64 a1, struct IHttpContext *a2)
{
  return RequestDoWork(0x80000000, 0, a2);
}

```

## disassembly

```asm
0x1800065f0  sub     rsp, 38h
0x1800065f4  mov     r9, r8
0x1800065f7  mov     [rsp+38h+var_18], 0
0x180006600  mov     r8, rdx
0x180006603  mov     ecx, 80000000h
0x180006608  xor     edx, edx
0x18000660a  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x18000660f  add     rsp, 38h
0x180006613  retn
```
