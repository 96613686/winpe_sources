# ISAPI_REQUEST::GetCacheInvalidationCallback(unsigned __int64 *)

- ea: `0x18000d750`
- end: `0x18000d75d`
- name: `?GetCacheInvalidationCallback@ISAPI_REQUEST@@UEAAJPEA_K@Z`
- size: `13`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::GetCacheInvalidationCallback(ISAPI_REQUEST *this, unsigned __int64 *a2)
{
  *a2 = (unsigned __int64)FlushKernelCacheHelper;
  return 0;
}

```

## disassembly

```asm
0x18000d750  lea     rax, ?FlushKernelCacheHelper@@YAJPEAG@Z; FlushKernelCacheHelper(ushort *)
0x18000d757  mov     [rdx], rax
0x18000d75a  xor     eax, eax
0x18000d75c  retn
```
