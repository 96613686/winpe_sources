# ISAPI_REQUEST::AddFragmentToCache(_HTTP_DATA_CHUNK *,ushort *)

- ea: `0x18000c4d0`
- end: `0x18000c4e6`
- name: `?AddFragmentToCache@ISAPI_REQUEST@@UEAAJPEAU_HTTP_DATA_CHUNK@@PEAG@Z`
- size: `22`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this, struct _HTTP_DATA_CHUNK *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::AddFragmentToCache(
        ISAPI_REQUEST *this,
        struct _HTTP_DATA_CHUNK *a2,
        unsigned __int16 *a3)
{
  return (*(__int64 (__fastcall **)(struct IHttpServer *, struct _HTTP_DATA_CHUNK *, unsigned __int16 *))(*(_QWORD *)g_pGlobalInfo + 136LL))(
           g_pGlobalInfo,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000c4d0  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000c4d7  mov     rax, [rcx]
0x18000c4da  mov     rax, [rax+88h]
0x18000c4e1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
