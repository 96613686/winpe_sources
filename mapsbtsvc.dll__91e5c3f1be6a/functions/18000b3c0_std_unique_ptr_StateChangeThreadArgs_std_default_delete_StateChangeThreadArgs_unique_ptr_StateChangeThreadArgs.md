# std::unique_ptr<StateChangeThreadArgs,std::default_delete<StateChangeThreadArgs>>::~unique_ptr<StateChangeThreadArgs,std::default_delete<StateChangeThreadArgs>>(void)

- ea: `0x18000b3c0`
- end: `0x18000b3d6`
- name: `??1?$unique_ptr@UStateChangeThreadArgs@@U?$default_delete@UStateChangeThreadArgs@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009610`
- `0x18000d3dc`
- `0x1800140ba`
- `0x1800144e5`

## callees

- `0x18000b3c0`
- `0x18000b8a4`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<StateChangeThreadArgs>::~unique_ptr<StateChangeThreadArgs>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<StateChangeThreadArgs>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000b3c0  sub     rsp, 28h
0x18000b3c4  mov     rdx, [rcx]
0x18000b3c7  test    rdx, rdx
0x18000b3ca  jz      short loc_18000B3D1
0x18000b3cc  call    ??R?$default_delete@UStateChangeThreadArgs@@@std@@QEBAXPEAUStateChangeThreadArgs@@@Z; std::default_delete<StateChangeThreadArgs>::operator()(StateChangeThreadArgs *)
0x18000b3d1  add     rsp, 28h
0x18000b3d5  retn
```
