# std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> *,Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher> * const,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>> &)

- ea: `0x180009fb0`
- end: `0x180009fe1`
- name: `??$_Destroy_range@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a098`
- `0x18000a248`
- `0x18000ad2c`
- `0x18000ae94`
- `0x18000c1a4`

## callees

- `0x180009fb0`
- `0x18000ba64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(v3);
      v3 += 8;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180009fb0  cmp     rcx, rdx
0x180009fb3  jz      short locret_180009FE0
0x180009fb5  mov     [rsp+arg_0], rbx
0x180009fba  push    rdi
0x180009fbb  sub     rsp, 20h
0x180009fbf  mov     rdi, rdx
0x180009fc2  mov     rbx, rcx
0x180009fc5  mov     rcx, rbx
0x180009fc8  call    ?InternalRelease@?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(void)
0x180009fcd  add     rbx, 8
0x180009fd1  cmp     rbx, rdi
0x180009fd4  jnz     short loc_180009FC5
0x180009fd6  mov     rbx, [rsp+28h+arg_0]
0x180009fdb  add     rsp, 20h
0x180009fdf  pop     rdi
0x180009fe0  retn
```
