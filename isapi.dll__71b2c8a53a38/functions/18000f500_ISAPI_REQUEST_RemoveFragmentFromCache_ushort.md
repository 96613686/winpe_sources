# ISAPI_REQUEST::RemoveFragmentFromCache(ushort *)

- ea: `0x18000f500`
- end: `0x18000f516`
- name: `?RemoveFragmentFromCache@ISAPI_REQUEST@@UEAAJPEAG@Z`
- size: `22`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::RemoveFragmentFromCache(ISAPI_REQUEST *this, unsigned __int16 *a2)
{
  return (*(__int64 (__fastcall **)(struct IHttpServer *, unsigned __int16 *))(*(_QWORD *)g_pGlobalInfo + 152LL))(
           g_pGlobalInfo,
           a2);
}

```

## disassembly

```asm
0x18000f500  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000f507  mov     rax, [rcx]
0x18000f50a  mov     rax, [rax+98h]
0x18000f511  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
