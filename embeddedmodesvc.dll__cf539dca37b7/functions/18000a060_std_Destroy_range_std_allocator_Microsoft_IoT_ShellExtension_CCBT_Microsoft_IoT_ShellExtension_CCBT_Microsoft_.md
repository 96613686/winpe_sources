# std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)

- ea: `0x18000a060`
- end: `0x18000a091`
- name: `??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z`
- size: `49`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CCBT *this, Microsoft::IoT::ShellExtension::CCBT *)`
- caller_count: `19`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ac14`
- `0x18000b3e8`
- `0x18000fc68`
- `0x18000fcd4`
- `0x180010510`
- `0x1800106fc`
- `0x180010948`
- `0x180011134`
- `0x1800114f0`
- `0x180011a1c`
- `0x180011c34`
- `0x180013360`
- `0x180014ed4`
- `0x180014fd0`
- `0x18001533c`
- `0x180015690`
- `0x180015cd0`
- `0x180015e98`
- `0x180017c44`

## callees

- `0x18000a060`
- `0x18000acf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(
        Microsoft::IoT::ShellExtension::CCBT *this,
        Microsoft::IoT::ShellExtension::CCBT *a2)
{
  Microsoft::IoT::ShellExtension::CCBT *v3; // rbx

  if ( this != a2 )
  {
    v3 = this;
    do
    {
      Microsoft::IoT::ShellExtension::CCBT::~CCBT(v3);
      v3 = (Microsoft::IoT::ShellExtension::CCBT *)((char *)v3 + 88);
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x18000a060  cmp     rcx, rdx
0x18000a063  jz      short locret_18000A090
0x18000a065  mov     [rsp+arg_0], rbx
0x18000a06a  push    rdi
0x18000a06b  sub     rsp, 20h
0x18000a06f  mov     rdi, rdx
0x18000a072  mov     rbx, rcx
0x18000a075  mov     rcx, rbx; this
0x18000a078  call    ??1CCBT@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CCBT::~CCBT(void)
0x18000a07d  add     rbx, 58h ; 'X'
0x18000a081  cmp     rbx, rdi
0x18000a084  jnz     short loc_18000A075
0x18000a086  mov     rbx, [rsp+28h+arg_0]
0x18000a08b  add     rsp, 20h
0x18000a08f  pop     rdi
0x18000a090  retn
```
