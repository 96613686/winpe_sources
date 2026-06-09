# tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)

- ea: `0x18002b3bc`
- end: `0x18002b3ee`
- name: `?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z`
- size: `50`
- prototype: `char __fastcall(tson::read_buffer **)`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x1800203e8`
- `0x1800204e8`
- `0x18002057c`
- `0x1800205e4`
- `0x180020648`
- `0x18002071c`
- `0x1800207d0`
- `0x180020e9c`
- `0x180020f58`
- `0x18002110c`
- `0x1800211c8`
- `0x180021594`
- `0x180021680`
- `0x180021758`
- `0x18002180c`
- `0x1800218c8`
- `0x180021ad4`
- `0x180021b98`
- `0x180021c7c`
- `0x180021d20`
- `0x18002272c`
- `0x18002b548`
- `0x18002bed0`
- `0x18002cc9c`

## callees

- `0x18002b000`
- `0x18002b3bc`

## pseudocode

```c
char __fastcall tson::input_archive::consume_expected_marker(tson::read_buffer **a1)
{
  unsigned __int8 *v1; // rax
  int v2; // r8d
  __int64 v3; // r9
  char v4; // r10

  v1 = tson::read_buffer::advance(*a1);
  if ( v1 )
  {
    if ( v4 == *v1 )
      return 1;
    if ( *(int *)(v3 + 8) >= 0 )
      *(_DWORD *)(v3 + 8) = v2;
  }
  return 0;
}

```

## disassembly

```asm
0x18002b3bc  sub     rsp, 28h
0x18002b3c0  mov     r9, rcx
0x18002b3c3  mov     r10b, dl
0x18002b3c6  mov     rcx, [rcx]; this
0x18002b3c9  call    ?advance@read_buffer@tson@@QEAAPEAEXZ; tson::read_buffer::advance(void)
0x18002b3ce  test    rax, rax
0x18002b3d1  jz      short loc_18002B3E7
0x18002b3d3  cmp     r10b, [rax]
0x18002b3d6  jnz     short loc_18002B3DC
0x18002b3d8  mov     al, 1
0x18002b3da  jmp     short loc_18002B3E9
0x18002b3dc  cmp     dword ptr [r9+8], 0
0x18002b3e1  jl      short loc_18002B3E7
0x18002b3e3  mov     [r9+8], r8d
0x18002b3e7  xor     al, al
0x18002b3e9  add     rsp, 28h
0x18002b3ed  retn
```
