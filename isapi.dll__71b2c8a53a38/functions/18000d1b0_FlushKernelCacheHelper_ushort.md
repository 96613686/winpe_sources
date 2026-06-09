# FlushKernelCacheHelper(ushort *)

- ea: `0x18000d1b0`
- end: `0x18000d1c6`
- name: `?FlushKernelCacheHelper@@YAJPEAG@Z`
- size: `22`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall FlushKernelCacheHelper(unsigned __int16 *a1)
{
  return (*(__int64 (__fastcall **)(struct IHttpServer *, unsigned __int16 *))(*(_QWORD *)g_pGlobalInfo + 72LL))(
           g_pGlobalInfo,
           a1);
}

```

## disassembly

```asm
0x18000d1b0  mov     rdx, rcx
0x18000d1b3  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000d1ba  mov     rax, [rcx]
0x18000d1bd  mov     rax, [rax+48h]
0x18000d1c1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
