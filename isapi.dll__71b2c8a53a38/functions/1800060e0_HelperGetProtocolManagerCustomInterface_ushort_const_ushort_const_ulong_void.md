# HelperGetProtocolManagerCustomInterface(ushort const *,ushort const *,ulong,void * *)

- ea: `0x1800060e0`
- end: `0x180006110`
- name: `?HelperGetProtocolManagerCustomInterface@@YAJPEBG0KPEAPEAX@Z`
- size: `48`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall HelperGetProtocolManagerCustomInterface(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        void **a4)
{
  return (*(__int64 (__fastcall **)(struct IHttpServer *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, void **))(*(_QWORD *)g_pGlobalInfo + 168LL))(
           g_pGlobalInfo,
           a1,
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x1800060e0  sub     rsp, 38h
0x1800060e4  mov     r10, rcx
0x1800060e7  mov     [rsp+38h+var_18], r9
0x1800060ec  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800060f3  mov     r9d, r8d
0x1800060f6  mov     r8, rdx
0x1800060f9  mov     rdx, r10
0x1800060fc  mov     rax, [rcx]
0x1800060ff  mov     rax, [rax+0A8h]
0x180006106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610b  add     rsp, 38h
0x18000610f  retn
```
