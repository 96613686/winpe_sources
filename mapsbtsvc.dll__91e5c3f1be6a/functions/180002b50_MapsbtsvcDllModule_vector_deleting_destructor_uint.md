# MapsbtsvcDllModule::`vector deleting destructor'(uint)

- ea: `0x180002b50`
- end: `0x180002b7f`
- name: `??_EMapsbtsvcDllModule@@UEAAPEAXI@Z`
- size: `47`
- prototype: `MapsbtsvcDllModule *__fastcall(MapsbtsvcDllModule *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180001e54`
- `0x180002a3c`
- `0x180002b50`

## pseudocode

```c
MapsbtsvcDllModule *__fastcall MapsbtsvcDllModule::`vector deleting destructor'(MapsbtsvcDllModule *this, char a2)
{
  ATL::CAtlDllModuleT<MapsbtsvcDllModule>::~CAtlDllModuleT<MapsbtsvcDllModule>(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002b50  mov     [rsp+arg_0], rbx
0x180002b55  push    rdi
0x180002b56  sub     rsp, 20h
0x180002b5a  mov     ebx, edx
0x180002b5c  mov     rdi, rcx
0x180002b5f  call    ??1?$CAtlDllModuleT@VMapsbtsvcDllModule@@@ATL@@UEAA@XZ; ATL::CAtlDllModuleT<MapsbtsvcDllModule>::~CAtlDllModuleT<MapsbtsvcDllModule>(void)
0x180002b64  test    bl, 1
0x180002b67  jz      short loc_180002B71
0x180002b69  mov     rcx, rdi; Block
0x180002b6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002b71  mov     rbx, [rsp+28h+arg_0]
0x180002b76  mov     rax, rdi
0x180002b79  add     rsp, 20h
0x180002b7d  pop     rdi
0x180002b7e  retn
```
