# std::vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>::~vector<Microsoft::IoT::ShellExtension::CCBT,std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(void)

- ea: `0x18000ac14`
- end: `0x18000ac70`
- name: `??1?$vector@VCCBT@ShellExtension@IoT@Microsoft@@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `92`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CCBT **)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018e4e`
- `0x180019837`
- `0x180019988`
- `0x180019c88`

## callees

- `0x180009f7c`
- `0x18000a060`
- `0x18000ac14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<Microsoft::IoT::ShellExtension::CCBT>::~vector<Microsoft::IoT::ShellExtension::CCBT>(
        Microsoft::IoT::ShellExtension::CCBT **a1)
{
  Microsoft::IoT::ShellExtension::CCBT *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(v2, a1[1]);
    std::_Deallocate<16>(*a1, 8 * ((a1[2] - *a1) >> 3));
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18000ac14  push    rbx
0x18000ac16  sub     rsp, 20h
0x18000ac1a  mov     rbx, rcx
0x18000ac1d  mov     rcx, [rcx]; this
0x18000ac20  test    rcx, rcx
0x18000ac23  jz      short loc_18000AC6A
0x18000ac25  mov     rdx, [rbx+8]
0x18000ac29  call    ??$_Destroy_range@V?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@std@@@std@@YAXPEAVCCBT@ShellExtension@IoT@Microsoft@@QEAV1234@AEAV?$allocator@VCCBT@ShellExtension@IoT@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::IoT::ShellExtension::CCBT>>(Microsoft::IoT::ShellExtension::CCBT *,Microsoft::IoT::ShellExtension::CCBT * const,std::allocator<Microsoft::IoT::ShellExtension::CCBT> &)
0x18000ac2e  mov     rax, [rbx+10h]
0x18000ac32  mov     rcx, 2E8BA2E8BA2E8BA3h
0x18000ac3c  sub     rax, [rbx]
0x18000ac3f  sar     rax, 3
0x18000ac43  imul    rax, rcx
0x18000ac47  mov     rcx, [rbx]
0x18000ac4a  imul    rdx, rax, 58h ; 'X'
0x18000ac4e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000ac53  mov     qword ptr [rbx], 0
0x18000ac5a  mov     qword ptr [rbx+8], 0
0x18000ac62  mov     qword ptr [rbx+10h], 0
0x18000ac6a  add     rsp, 20h
0x18000ac6e  pop     rbx
0x18000ac6f  retn
```
