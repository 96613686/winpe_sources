# LKRhash::CLKRLinearHashTable::DeleteRecord(void const *)

- ea: `0x1800025c4`
- end: `0x180002638`
- name: `?DeleteRecord@CLKRLinearHashTable@LKRhash@@QEAA?AW4LK_RETCODE@2@PEBX@Z`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001230`
- `0x18000d0f4`

## callees

- `0x1800025c4`
- `0x1800029d0`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall LKRhash::CLKRLinearHashTable::DeleteRecord(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // eax

  result = *(unsigned int *)(a1 + 20);
  if ( !(_DWORD)result )
  {
    if ( a2 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(a1 + 32))(a2);
      v6 = (*(__int64 (__fastcall **)(__int64))(a1 + 40))(v5);
      return LKRhash::CLKRLinearHashTable::_DeleteRecord(
               a1,
               a2,
               (69069 * v6 + 1) & 0xFFFF0000 | ((unsigned int)(1103515245 * v6 + 12345) >> 16));
    }
    else
    {
      return 4294967200LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800025c4  mov     [rsp+arg_0], rbx
0x1800025c9  push    rdi
0x1800025ca  sub     rsp, 20h
0x1800025ce  mov     eax, [rcx+14h]
0x1800025d1  mov     rdi, rdx
0x1800025d4  mov     rbx, rcx
0x1800025d7  test    eax, eax
0x1800025d9  jnz     short loc_180002626
0x1800025db  test    rdx, rdx
0x1800025de  jz      short loc_180002631
0x1800025e0  mov     rax, [rbx+20h]
0x1800025e4  mov     rcx, rdx
0x1800025e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ec  mov     rcx, rax
0x1800025ef  mov     rax, [rbx+28h]
0x1800025f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025f8  imul    ecx, eax, 10DCDh
0x1800025fe  mov     rdx, rdi
0x180002601  imul    r8d, eax, 41C64E6Dh
0x180002608  inc     ecx
0x18000260a  add     r8d, 3039h
0x180002611  and     ecx, 0FFFF0000h
0x180002617  shr     r8d, 10h
0x18000261b  or      r8d, ecx
0x18000261e  mov     rcx, rbx
0x180002621  call    ?_DeleteRecord@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@PEBXK@Z; LKRhash::CLKRLinearHashTable::_DeleteRecord(void const *,ulong)
0x180002626  mov     rbx, [rsp+28h+arg_0]
0x18000262b  add     rsp, 20h
0x18000262f  pop     rdi
0x180002630  retn
0x180002631  mov     eax, 0FFFFFFA0h
0x180002636  jmp     short loc_180002626
```
