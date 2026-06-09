# ISAPI_REQUEST::ReadFragmentFromCache(ushort *,uchar *,ulong,ulong *)

- ea: `0x18000f3c0`
- end: `0x18000f3e9`
- name: `?ReadFragmentFromCache@ISAPI_REQUEST@@UEAAJPEAGPEAEKPEAK@Z`
- size: `41`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this, unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::ReadFragmentFromCache(ISAPI_REQUEST *this, unsigned __int16 *a2, unsigned __int8 *a3)
{
  return (*(__int64 (__fastcall **)(struct IHttpServer *, unsigned __int16 *, unsigned __int8 *))(*(_QWORD *)g_pGlobalInfo
                                                                                                + 144LL))(
           g_pGlobalInfo,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000f3c0  sub     rsp, 38h
0x18000f3c4  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000f3cb  mov     r10, [rsp+38h+arg_20]
0x18000f3d0  mov     [rsp+38h+var_18], r10
0x18000f3d5  mov     rax, [rcx]
0x18000f3d8  mov     rax, [rax+90h]
0x18000f3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3e4  add     rsp, 38h
0x18000f3e8  retn
```
