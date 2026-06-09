# NFMcompress_uninit

- ea: `0x180012630`
- end: `0x180012712`
- name: `NFMcompress_uninit`
- size: `226`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012414`
- `0x180012578`
- `0x1800125e0`

## callees

- `0x180012630`
- `0x180012718`

## pseudocode

```c
__int64 __fastcall NFMcompress_uninit(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  if ( a1 )
  {
    if ( a1[1526] )
    {
      NFMcompress_PickFreeRoutineAndFreeMemory(a2, a3, a4);
      a1[1526] = 0;
    }
    if ( a1[1527] )
    {
      NFMcompress_PickFreeRoutineAndFreeMemory(a2, a3, a4);
      a1[1527] = 0;
    }
    if ( a1[1528] )
    {
      NFMcompress_PickFreeRoutineAndFreeMemory(a2, a3, a4);
      a1[1528] = 0;
    }
    if ( a1[1529] )
    {
      NFMcompress_PickFreeRoutineAndFreeMemory(a2, a3, a4);
      a1[1529] = 0;
    }
    if ( a1[1530] )
    {
      NFMcompress_PickFreeRoutineAndFreeMemory(a2, a3, a4);
      a1[1530] = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012630  push    rbx
0x180012632  push    rbp
0x180012633  push    rsi
0x180012634  push    rdi
0x180012635  sub     rsp, 28h
0x180012639  mov     rdi, r9
0x18001263c  mov     rsi, r8
0x18001263f  mov     rbp, rdx
0x180012642  mov     rbx, rcx
0x180012645  test    rcx, rcx
0x180012648  jz      loc_180012707
0x18001264e  mov     r9, [rcx+2FB0h]
0x180012655  test    r9, r9
0x180012658  jz      short loc_180012673
0x18001265a  mov     r8, rdi
0x18001265d  mov     rdx, rsi
0x180012660  mov     rcx, rbp
0x180012663  call    NFMcompress_PickFreeRoutineAndFreeMemory
0x180012668  mov     qword ptr [rbx+2FB0h], 0
0x180012673  mov     r9, [rbx+2FB8h]
0x18001267a  test    r9, r9
0x18001267d  jz      short loc_180012698
0x18001267f  mov     r8, rdi
0x180012682  mov     rdx, rsi
0x180012685  mov     rcx, rbp
0x180012688  call    NFMcompress_PickFreeRoutineAndFreeMemory
0x18001268d  mov     qword ptr [rbx+2FB8h], 0
0x180012698  mov     r9, [rbx+2FC0h]
0x18001269f  test    r9, r9
0x1800126a2  jz      short loc_1800126BD
0x1800126a4  mov     r8, rdi
0x1800126a7  mov     rdx, rsi
0x1800126aa  mov     rcx, rbp
0x1800126ad  call    NFMcompress_PickFreeRoutineAndFreeMemory
0x1800126b2  mov     qword ptr [rbx+2FC0h], 0
0x1800126bd  mov     r9, [rbx+2FC8h]
0x1800126c4  test    r9, r9
0x1800126c7  jz      short loc_1800126E2
0x1800126c9  mov     r8, rdi
0x1800126cc  mov     rdx, rsi
0x1800126cf  mov     rcx, rbp
0x1800126d2  call    NFMcompress_PickFreeRoutineAndFreeMemory
0x1800126d7  mov     qword ptr [rbx+2FC8h], 0
0x1800126e2  mov     r9, [rbx+2FD0h]
0x1800126e9  test    r9, r9
0x1800126ec  jz      short loc_180012707
0x1800126ee  mov     r8, rdi
0x1800126f1  mov     rdx, rsi
0x1800126f4  mov     rcx, rbp
0x1800126f7  call    NFMcompress_PickFreeRoutineAndFreeMemory
0x1800126fc  mov     qword ptr [rbx+2FD0h], 0
0x180012707  xor     eax, eax
0x180012709  add     rsp, 28h
0x18001270d  pop     rdi
0x18001270e  pop     rsi
0x18001270f  pop     rbp
0x180012710  pop     rbx
0x180012711  retn
```
