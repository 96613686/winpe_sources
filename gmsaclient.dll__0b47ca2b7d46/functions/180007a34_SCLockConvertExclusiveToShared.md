# SCLockConvertExclusiveToShared

- ea: `0x180007a34`
- end: `0x180007a74`
- name: `SCLockConvertExclusiveToShared`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002e18`
- `0x180003e84`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180007a5b`
- `ntdll!RtlAcquireResourceShared` at `0x180007a5b`
- `ntdll!RtlReleaseResource` at `0x180007a46`
- `ntdll!RtlReleaseResource` at `0x180007a46`

## pseudocode

```c
BOOLEAN SCLockConvertExclusiveToShared()
{
  BOOLEAN result; // al

  _InterlockedIncrement(&dword_18000B670);
  RtlReleaseResource(&Resource);
  result = RtlAcquireResourceShared(&Resource, 1u);
  _InterlockedDecrement(&dword_18000B670);
  return result;
}

```

## disassembly

```asm
0x180007a34  sub     rsp, 28h
0x180007a38  lock inc cs:dword_18000B670
0x180007a3f  lea     rcx, Resource; Resource
0x180007a46  call    cs:__imp_RtlReleaseResource
0x180007a4d  nop     dword ptr [rax+rax+00h]
0x180007a52  mov     dl, 1; Wait
0x180007a54  lea     rcx, Resource; Resource
0x180007a5b  call    cs:__imp_RtlAcquireResourceShared
0x180007a62  nop     dword ptr [rax+rax+00h]
0x180007a67  lock dec cs:dword_18000B670
0x180007a6e  add     rsp, 28h
0x180007a72  retn
```
