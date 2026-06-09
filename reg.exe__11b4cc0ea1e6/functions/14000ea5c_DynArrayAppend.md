# __DynArrayAppend

- ea: `0x14000ea5c`
- end: `0x14000ead9`
- name: `__DynArrayAppend`
- size: `125`
- prototype: `__int64 __fastcall(__int64, int, int, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e6bc`
- `0x14000e718`
- `0x14000e7a4`

## callees

- `0x14000c62c`
- `0x14000ea5c`

## pseudocode

```c
__int64 __fastcall _DynArrayAppend(__int64 a1, int a2, int a3, __int64 a4)
{
  _QWORD *Memory; // rax

  if ( !a1 )
    return 0xFFFFFFFFLL;
  if ( *(_DWORD *)a1 != 9 )
    return 0xFFFFFFFFLL;
  if ( *(_DWORD *)(a1 + 4) == -1 )
    return 0xFFFFFFFFLL;
  Memory = AllocateMemory(0x20u);
  if ( !Memory )
    return 0xFFFFFFFFLL;
  Memory[3] = 0;
  *((_DWORD *)Memory + 1) = a2;
  *((_DWORD *)Memory + 2) = a3;
  Memory[2] = a4;
  *(_DWORD *)Memory = 99;
  ++*(_DWORD *)(a1 + 4);
  if ( *(_QWORD *)(a1 + 8) )
    *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) = Memory;
  else
    *(_QWORD *)(a1 + 8) = Memory;
  *(_QWORD *)(a1 + 16) = Memory;
  return (unsigned int)(*(_DWORD *)(a1 + 4) - 1);
}

```

## disassembly

```asm
0x14000ea5c  push    rbx
0x14000ea5e  push    rbp
0x14000ea5f  push    rsi
0x14000ea60  push    rdi
0x14000ea61  sub     rsp, 28h
0x14000ea65  mov     rdi, r9
0x14000ea68  mov     esi, r8d
0x14000ea6b  mov     ebp, edx
0x14000ea6d  mov     rbx, rcx
0x14000ea70  test    rcx, rcx
0x14000ea73  jz      short loc_14000EACD
0x14000ea75  cmp     dword ptr [rcx], 9
0x14000ea78  jnz     short loc_14000EACD
0x14000ea7a  cmp     dword ptr [rcx+4], 0FFFFFFFFh
0x14000ea7e  jz      short loc_14000EACD
0x14000ea80  mov     ecx, 20h ; ' '; dwBytes
0x14000ea85  call    AllocateMemory
0x14000ea8a  mov     rcx, rax
0x14000ea8d  test    rax, rax
0x14000ea90  jz      short loc_14000EACD
0x14000ea92  mov     qword ptr [rax+18h], 0
0x14000ea9a  mov     [rax+4], ebp
0x14000ea9d  mov     [rax+8], esi
0x14000eaa0  mov     [rax+10h], rdi
0x14000eaa4  mov     dword ptr [rax], 63h ; 'c'
0x14000eaaa  inc     dword ptr [rbx+4]
0x14000eaad  cmp     qword ptr [rbx+8], 0
0x14000eab2  jnz     short loc_14000EABA
0x14000eab4  mov     [rbx+8], rax
0x14000eab8  jmp     short loc_14000EAC2
0x14000eaba  mov     rax, [rbx+10h]
0x14000eabe  mov     [rax+18h], rcx
0x14000eac2  mov     [rbx+10h], rcx
0x14000eac6  mov     eax, [rbx+4]
0x14000eac9  dec     eax
0x14000eacb  jmp     short loc_14000EAD0
0x14000eacd  or      eax, 0FFFFFFFFh
0x14000ead0  add     rsp, 28h
0x14000ead4  pop     rdi
0x14000ead5  pop     rsi
0x14000ead6  pop     rbp
0x14000ead7  pop     rbx
0x14000ead8  retn
```
