# RfcommDispatch

- ea: `0x140001ec0`
- end: `0x140001ee3`
- name: `RfcommDispatch`
- size: `35`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001ec0`
- `0x14000256c`
- `0x140005cfc`

## pseudocode

```c
__int64 __fastcall RfcommDispatch(__int64 a1)
{
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 64) + 16LL) == 541672532 )
    return RfcommDispatchTdi();
  else
    return RfcommDispatchFdo();
}

```

## disassembly

```asm
0x140001ec0  sub     rsp, 28h
0x140001ec4  mov     rax, [rcx+40h]
0x140001ec8  cmp     dword ptr [rax+10h], 20494454h
0x140001ecf  jnz     short loc_140001ED8
0x140001ed1  call    RfcommDispatchTdi
0x140001ed6  jmp     short loc_140001EDD
0x140001ed8  call    RfcommDispatchFdo
0x140001edd  add     rsp, 28h
0x140001ee1  retn
```
