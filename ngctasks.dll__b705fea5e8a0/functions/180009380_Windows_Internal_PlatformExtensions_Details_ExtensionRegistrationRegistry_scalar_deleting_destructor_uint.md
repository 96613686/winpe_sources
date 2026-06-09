# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(uint)

- ea: `0x180009380`
- end: `0x1800093b4`
- name: `??_GExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z`
- size: `52`
- prototype: `HKEY *__fastcall(HKEY *this, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180008c00`
- `0x180009e70`

## callees

- `0x1800067f4`
- `0x180008d84`
- `0x180009380`

## pseudocode

```c
HKEY *__fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(
        HKEY *this,
        char a2)
{
  Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::~ExtensionRegistrationRegistry(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009380  mov     [rsp+arg_0], rbx
0x180009385  push    rdi
0x180009386  sub     rsp, 20h
0x18000938a  mov     ebx, edx
0x18000938c  mov     rdi, rcx
0x18000938f  call    ??1ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAA@XZ; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::~ExtensionRegistrationRegistry(void)
0x180009394  test    bl, 1
0x180009397  jz      short loc_1800093A6
0x180009399  mov     edx, 118h
0x18000939e  mov     rcx, rdi; Block
0x1800093a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800093a6  mov     rbx, [rsp+28h+arg_0]
0x1800093ab  mov     rax, rdi
0x1800093ae  add     rsp, 20h
0x1800093b2  pop     rdi
0x1800093b3  retn
```
