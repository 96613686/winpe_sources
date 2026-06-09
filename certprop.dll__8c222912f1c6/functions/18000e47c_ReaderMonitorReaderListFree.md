# ReaderMonitorReaderListFree

- ea: `0x18000e47c`
- end: `0x18000e4a5`
- name: `ReaderMonitorReaderListFree`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180019fa4`

## callees

- `0x18000e47c`
- `0x180014a04`

## pseudocode

```c
__int64 __fastcall ReaderMonitorReaderListFree(__int64 a1)
{
  _QWORD *v2; // rcx
  __int64 result; // rax

  if ( a1 )
  {
    v2 = *(_QWORD **)(a1 + 112);
    if ( v2 )
    {
      result = I_ReaderListFree(v2);
      *(_QWORD *)(a1 + 112) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e47c  test    rcx, rcx
0x18000e47f  jz      short locret_18000E4A4
0x18000e481  push    rbx
0x18000e482  sub     rsp, 20h
0x18000e486  mov     rbx, rcx
0x18000e489  mov     rcx, [rcx+70h]
0x18000e48d  test    rcx, rcx
0x18000e490  jz      short loc_18000E49F
0x18000e492  call    I_ReaderListFree
0x18000e497  mov     qword ptr [rbx+70h], 0
0x18000e49f  add     rsp, 20h
0x18000e4a3  pop     rbx
0x18000e4a4  retn
```
