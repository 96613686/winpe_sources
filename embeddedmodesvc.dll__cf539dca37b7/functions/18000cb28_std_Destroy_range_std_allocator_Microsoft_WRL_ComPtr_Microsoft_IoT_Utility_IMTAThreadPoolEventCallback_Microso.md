# std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> *,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> * const,std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>> &)

- ea: `0x18000cb28`
- end: `0x18000cb6d`
- name: `??$_Destroy_range@V?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@0@@Z`
- size: `69`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cc3c`
- `0x18000d064`
- `0x18000d430`
- `0x18000d508`
- `0x18000de50`

## callees

- `0x18000cb28`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(
        __int64 *a1,
        __int64 *a2)
{
  __int64 *v3; // rbx
  __int64 v4; // rcx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      v4 = *v3;
      if ( *v3 )
      {
        *v3 = 0;
        result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
      ++v3;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x18000cb28  cmp     rcx, rdx
0x18000cb2b  jz      short locret_18000CB6C
0x18000cb2d  mov     [rsp+arg_0], rbx
0x18000cb32  push    rdi
0x18000cb33  sub     rsp, 20h
0x18000cb37  mov     rdi, rdx
0x18000cb3a  mov     rbx, rcx
0x18000cb3d  mov     rcx, [rbx]
0x18000cb40  test    rcx, rcx
0x18000cb43  jz      short loc_18000CB59
0x18000cb45  mov     qword ptr [rbx], 0
0x18000cb4c  mov     rax, [rcx]
0x18000cb4f  mov     rax, [rax+10h]
0x18000cb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb58  nop
0x18000cb59  add     rbx, 8
0x18000cb5d  cmp     rbx, rdi
0x18000cb60  jnz     short loc_18000CB3D
0x18000cb62  mov     rbx, [rsp+28h+arg_0]
0x18000cb67  add     rsp, 20h
0x18000cb6b  pop     rdi
0x18000cb6c  retn
```
