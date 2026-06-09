# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180010948`
- end: `0x180010979`
- name: `??1_Reallocation_guard@?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f9a4`
- `0x18000fae0`
- `0x180019593`

## callees

- `0x180009f7c`
- `0x18000a060`
- `0x180010948`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::_Reallocation_guard::~_Reallocation_guard(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 8) )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(
      *(Microsoft::IoT::ShellExtension::CCBT **)(a1 + 24),
      *(Microsoft::IoT::ShellExtension::CCBT **)(a1 + 32));
    std::_Deallocate<16>(*(_QWORD **)(a1 + 8), 88LL * *(_QWORD *)(a1 + 16));
  }
}

```

## disassembly

```asm
0x180010948  push    rbx
0x18001094a  sub     rsp, 20h
0x18001094e  cmp     qword ptr [rcx+8], 0
0x180010953  mov     rbx, rcx
0x180010956  jz      short loc_180010973
0x180010958  mov     rdx, [rcx+20h]
0x18001095c  mov     rcx, [rcx+18h]; this
0x180010960  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x180010965  imul    rdx, [rbx+10h], 58h ; 'X'
0x18001096a  mov     rcx, [rbx+8]
0x18001096e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010973  add     rsp, 20h
0x180010977  pop     rbx
0x180010978  retn
```
