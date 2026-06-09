# __DynArrayAppend

- ea: `0x14000f708`
- end: `0x14000f786`
- name: `__DynArrayAppend`
- size: `126`
- prototype: `__int64 __fastcall(__int64, int, int, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f350`
- `0x14000f3b0`
- `0x14000f43c`

## callees

- `0x14000ce50`
- `0x14000f708`

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
0x14000f708  push    rbx
0x14000f70a  push    rbp
0x14000f70b  push    rsi
0x14000f70c  push    rdi
0x14000f70d  sub     rsp, 28h
0x14000f711  mov     rdi, r9
0x14000f714  mov     esi, r8d
0x14000f717  mov     ebp, edx
0x14000f719  mov     rbx, rcx
0x14000f71c  test    rcx, rcx
0x14000f71f  jz      short loc_14000F779
0x14000f721  cmp     dword ptr [rcx], 9
0x14000f724  jnz     short loc_14000F779
0x14000f726  cmp     dword ptr [rcx+4], 0FFFFFFFFh
0x14000f72a  jz      short loc_14000F779
0x14000f72c  mov     ecx, 20h ; ' '; dwBytes
0x14000f731  call    AllocateMemory
0x14000f736  mov     rcx, rax
0x14000f739  test    rax, rax
0x14000f73c  jz      short loc_14000F779
0x14000f73e  mov     qword ptr [rax+18h], 0
0x14000f746  mov     [rax+4], ebp
0x14000f749  mov     [rax+8], esi
0x14000f74c  mov     [rax+10h], rdi
0x14000f750  mov     dword ptr [rax], 63h ; 'c'
0x14000f756  inc     dword ptr [rbx+4]
0x14000f759  cmp     qword ptr [rbx+8], 0
0x14000f75e  jnz     short loc_14000F766
0x14000f760  mov     [rbx+8], rax
0x14000f764  jmp     short loc_14000F76E
0x14000f766  mov     rax, [rbx+10h]
0x14000f76a  mov     [rax+18h], rcx
0x14000f76e  mov     [rbx+10h], rcx
0x14000f772  mov     eax, [rbx+4]
0x14000f775  dec     eax
0x14000f777  jmp     short loc_14000F77C
0x14000f779  or      eax, 0FFFFFFFFh
0x14000f77c  add     rsp, 28h
0x14000f780  pop     rdi
0x14000f781  pop     rsi
0x14000f782  pop     rbp
0x14000f783  pop     rbx
0x14000f784  retn
```
