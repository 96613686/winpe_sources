# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(uint)

- ea: `0x180009340`
- end: `0x180009374`
- name: `??_GExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z`
- size: `52`
- prototype: `HKEY *__fastcall(HKEY *this, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180008bd4`
- `0x18000a2ac`

## callees

- `0x1800067f4`
- `0x180008d50`
- `0x180009340`

## pseudocode

```c
HKEY *__fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(
        HKEY *this,
        char a2)
{
  Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::~ExtensionRegistrationCollectionRegistry(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009340  mov     [rsp+arg_0], rbx
0x180009345  push    rdi
0x180009346  sub     rsp, 20h
0x18000934a  mov     ebx, edx
0x18000934c  mov     rdi, rcx
0x18000934f  call    ??1ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEAA@XZ; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::~ExtensionRegistrationCollectionRegistry(void)
0x180009354  test    bl, 1
0x180009357  jz      short loc_180009366
0x180009359  mov     edx, 10h
0x18000935e  mov     rcx, rdi; Block
0x180009361  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009366  mov     rbx, [rsp+28h+arg_0]
0x18000936b  mov     rax, rdi
0x18000936e  add     rsp, 20h
0x180009372  pop     rdi
0x180009373  retn
```
