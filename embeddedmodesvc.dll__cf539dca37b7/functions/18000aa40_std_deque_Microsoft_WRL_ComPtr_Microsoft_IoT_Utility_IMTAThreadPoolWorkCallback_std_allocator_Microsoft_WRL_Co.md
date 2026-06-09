# std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>::~deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>(void)

- ea: `0x18000aa40`
- end: `0x18000aa67`
- name: `??1?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ab20`
- `0x18000adbc`
- `0x18000e450`

## callees

- `0x180009f7c`
- `0x18000c5e4`

## pseudocode

```c
void __fastcall std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::~deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>(
        _QWORD **a1)
{
  _QWORD *v2; // rcx

  std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Tidy();
  v2 = *a1;
  *a1 = 0;
  std::_Deallocate<16>(v2, 0x10u);
}

```

## disassembly

```asm
0x18000aa40  push    rbx
0x18000aa42  sub     rsp, 20h
0x18000aa46  mov     rbx, rcx
0x18000aa49  call    ?_Tidy@?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::_Tidy(void)
0x18000aa4e  mov     rcx, [rbx]
0x18000aa51  mov     edx, 10h
0x18000aa56  mov     qword ptr [rbx], 0
0x18000aa5d  add     rsp, 20h
0x18000aa61  pop     rbx
0x18000aa62  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
