# ClassReleaseRemoveLock

- ea: `0x1400134a0`
- end: `0x1400134ea`
- name: `ClassReleaseRemoveLock`
- size: `74`
- prototype: `void __stdcall(PDEVICE_OBJECT DeviceObject, PVOID Tag)`
- caller_count: `78`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400029d0`
- `0x14000f630`
- `0x140010400`
- `0x140011ba0`
- `0x140012a00`
- `0x140012e40`
- `0x140012f10`
- `0x140013000`
- `0x140013240`
- `0x140013530`
- `0x140013690`
- `0x140013e10`
- `0x140014418`
- `0x140014860`
- `0x140014aa0`
- `0x14001522c`
- `0x140015710`
- `0x1400171d0`
- `0x140019de0`
- `0x14001c9e0`
- `0x14001ccb0`
- `0x14001e86c`
- `0x14001ecc0`
- `0x140020278`
- `0x140022920`
- `0x140023020`
- `0x1400231f0`
- `0x140023e3c`
- `0x140025f80`
- `0x140026020`
- `0x140028ee0`
- `0x140029040`
- `0x140029f80`
- `0x14002a410`
- `0x14002a460`
- `0x14002a47c`
- `0x14002a8d0`
- `0x14002b450`
- `0x14002b700`
- `0x14002b800`
- `0x14002b8b0`
- `0x14002ba00`
- `0x14002cf20`
- `0x14002d800`
- `0x14002e3f0`
- `0x14002f308`
- `0x14002f690`
- `0x14002f7f4`
- `0x14002f9fc`
- `0x14002fdd8`

## callees

- `0x1400134a0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400134c0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400134c0`

## pseudocode

```c
void __stdcall ClassReleaseRemoveLock(PDEVICE_OBJECT DeviceObject, PVOID Tag)
{
  _DWORD **DeviceExtension; // rcx
  signed __int32 v3; // eax
  signed __int32 v4; // ett

  DeviceExtension = (_DWORD **)DeviceObject->DeviceExtension;
  v3 = *DeviceExtension[55];
  if ( v3 )
  {
    while ( 1 )
    {
      v4 = v3;
      v3 = _InterlockedCompareExchange(DeviceExtension[55], v3 - 1, v3);
      if ( v4 == v3 )
        break;
      if ( !v3 )
        goto LABEL_2;
    }
  }
  else
  {
LABEL_2:
    ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(DeviceExtension[55] + 2));
  }
}

```

## disassembly

```asm
0x1400134a0  sub     rsp, 28h
0x1400134a4  mov     rcx, [rcx+40h]
0x1400134a8  mov     rax, [rcx+1B8h]
0x1400134af  mov     eax, [rax]
0x1400134b1  test    eax, eax
0x1400134b3  jnz     short loc_1400134D2
0x1400134b5  mov     rcx, [rcx+1B8h]
0x1400134bc  add     rcx, 8; RunRefCacheAware
0x1400134c0  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400134c7  nop     dword ptr [rax+rax+00h]
0x1400134cc  add     rsp, 28h
0x1400134d0  retn
0x1400134d2  mov     rdx, [rcx+1B8h]
0x1400134d9  lea     r8d, [rax-1]
0x1400134dd  lock cmpxchg [rdx], r8d
0x1400134e2  jz      short loc_1400134CC
0x1400134e4  test    eax, eax
0x1400134e6  jnz     short loc_1400134D2
0x1400134e8  jmp     short loc_1400134B5
```
