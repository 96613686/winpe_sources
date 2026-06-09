# wistd::unique_ptr<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0],wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>>::reset(std::nullptr_t)

- ea: `0x180043300`
- end: `0x18004331d`
- name: `?reset@?$unique_ptr@$$BY0A@V?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@U?$default_delete@$$BY0A@V?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@wistd@@@wistd@@QEAAX$$T@Z`
- size: `29`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003f12c`
- `0x18003f15c`
- `0x180048ac4`
- `0x18004a1b8`

## callees

- `0x18003e5ec`
- `0x180043300`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0],wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>>::reset(
        __int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    return wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>::operator()<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands>>();
  return result;
}

```

## disassembly

```asm
0x180043300  sub     rsp, 28h
0x180043304  mov     rdx, [rcx]
0x180043307  mov     qword ptr [rcx], 0
0x18004330e  test    rdx, rdx
0x180043311  jz      short loc_180043318
0x180043313  call    ??$?RV?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@?$default_delete@$$BY0A@V?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@wistd@@QEBAXPEAV?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@Z; wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>::operator()<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands>>(Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> *)
0x180043318  add     rsp, 28h
0x18004331c  retn
```
