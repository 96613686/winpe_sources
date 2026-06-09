# ClassAcquireRemoveLockEx

- ea: `0x1400157d0`
- end: `0x14001584c`
- name: `ClassAcquireRemoveLockEx`
- size: `124`
- prototype: `ULONG __stdcall(PDEVICE_OBJECT DeviceObject, PVOID Tag, PCSTR File, ULONG Line)`
- caller_count: `24`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001130`
- `0x14000be64`
- `0x14000fd00`
- `0x140014aa0`
- `0x140015710`
- `0x140016ea0`
- `0x140019de0`
- `0x14001c9e0`
- `0x14001e2f0`
- `0x140021710`
- `0x140023020`
- `0x1400231f0`
- `0x140025f80`
- `0x14002a8d0`
- `0x14002bdd0`
- `0x14002bebc`
- `0x14002bfa8`
- `0x14002c094`
- `0x140037e10`
- `0x140055c70`
- `0x14005d0d0`
- `0x14005eb30`
- `0x14005f210`
- `0x14005fe50`

## callees

- `0x1400157d0`
- `0x14001fbf4`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400157e5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400157e5`

## pseudocode

```c
ULONG __stdcall ClassAcquireRemoveLockEx(PDEVICE_OBJECT DeviceObject, PVOID Tag, PCSTR File, ULONG Line)
{
  unsigned int **DeviceExtension; // rbx

  DeviceExtension = (unsigned int **)DeviceObject->DeviceExtension;
  if ( !ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(DeviceExtension[55] + 2)) )
  {
    _InterlockedIncrement((volatile signed __int32 *)DeviceExtension[55]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_a22cc05f221e30b8049471910da99059_Traceguids,
        *DeviceExtension[55]);
    }
  }
  return *((_DWORD *)DeviceExtension + 27);
}

```

## disassembly

```asm
0x1400157d0  push    rbx
0x1400157d2  sub     rsp, 20h
0x1400157d6  mov     rbx, [rcx+40h]
0x1400157da  mov     rcx, [rbx+1B8h]
0x1400157e1  add     rcx, 8; RunRefCacheAware
0x1400157e5  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400157ec  nop     dword ptr [rax+rax+00h]
0x1400157f1  test    al, al
0x1400157f3  jz      short loc_1400157FF
0x1400157f5  mov     eax, [rbx+6Ch]
0x1400157f8  add     rsp, 20h
0x1400157fc  pop     rbx
0x1400157fd  retn
0x1400157ff  mov     rax, [rbx+1B8h]
0x140015806  lock inc dword ptr [rax]
0x140015809  mov     rcx, cs:WPP_GLOBAL_Control
0x140015810  lea     rax, WPP_GLOBAL_Control
0x140015817  cmp     rcx, rax
0x14001581a  jz      short loc_1400157F5
0x14001581c  test    dword ptr [rcx+2Ch], 200h
0x140015823  jz      short loc_1400157F5
0x140015825  cmp     byte ptr [rcx+29h], 5
0x140015829  jb      short loc_1400157F5
0x14001582b  mov     r9, [rbx+1B8h]
0x140015832  lea     r8, WPP_a22cc05f221e30b8049471910da99059_Traceguids
0x140015839  mov     rcx, [rcx+18h]
0x14001583d  mov     edx, 0Eh
0x140015842  mov     r9d, [r9]
0x140015845  call    WPP_SF_d
0x14001584a  jmp     short loc_1400157F5
```
