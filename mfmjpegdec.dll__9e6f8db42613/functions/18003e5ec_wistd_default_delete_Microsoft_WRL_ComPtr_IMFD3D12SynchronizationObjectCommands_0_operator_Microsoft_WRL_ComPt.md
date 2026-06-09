# wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>::operator()<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands>>(Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> *)

- ea: `0x18003e5ec`
- end: `0x18003e62d`
- name: `??$?RV?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@?$default_delete@$$BY0A@V?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@wistd@@QEBAXPEAV?$ComPtr@UIMFD3D12SynchronizationObjectCommands@@@WRL@Microsoft@@@Z`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180043300`
- `0x180048ac4`

## callees

- `0x180021694`
- `0x180024de0`
- `0x18003e5ec`

## pseudocode

```c
void __fastcall wistd::default_delete<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands> [0]>::operator()<Microsoft::WRL::ComPtr<IMFD3D12SynchronizationObjectCommands>>(
        __int64 a1,
        char *a2)
{
  char *v2; // rbx

  if ( a2 )
  {
    v2 = a2 - 8;
    `vector destructor iterator'(
      a2,
      8u,
      *((_QWORD *)a2 - 1),
      (void (*)(void *))Microsoft::WRL::ComPtr<ID3D12CommandAllocator>::~ComPtr<ID3D12CommandAllocator>);
    operator delete[](v2, 8LL * *(_QWORD *)v2 + 8);
  }
}

```

## disassembly

```asm
0x18003e5ec  test    rdx, rdx
0x18003e5ef  jz      short locret_18003E62C
0x18003e5f1  push    rbx
0x18003e5f2  sub     rsp, 20h
0x18003e5f6  mov     rax, rdx
0x18003e5f9  lea     rbx, [rdx-8]
0x18003e5fd  mov     r8, [rbx]; unsigned __int64
0x18003e600  lea     r9, ??1?$ComPtr@UID3D12CommandAllocator@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x18003e607  mov     rcx, rax; void *
0x18003e60a  mov     edx, 8; unsigned __int64
0x18003e60f  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003e614  mov     rdx, [rbx]
0x18003e617  mov     rcx, rbx; void *
0x18003e61a  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x18003e622  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x18003e627  add     rsp, 20h
0x18003e62b  pop     rbx
0x18003e62c  retn
```
