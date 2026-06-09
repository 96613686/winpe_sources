# std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(void)

- ea: `0x18000a730`
- end: `0x18000a741`
- name: `??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `17`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `12`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009b28`
- `0x18000a7d4`
- `0x18000b3e8`
- `0x18000de50`
- `0x18000f58c`
- `0x18001029c`
- `0x180011a1c`
- `0x180011c34`
- `0x180013360`
- `0x180015cd0`
- `0x180015e98`
- `0x180017764`

## pseudocode

```c
_QWORD *__fastcall std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x18000a730  xor     eax, eax
0x18000a732  mov     [rcx], rax
0x18000a735  mov     [rcx+8], rax
0x18000a739  mov     [rcx+10h], rax
0x18000a73d  mov     rax, rcx
0x18000a740  retn
```
