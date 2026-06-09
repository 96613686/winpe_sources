# CS_PathXtraCross

- ea: `0x1400595cc`
- end: `0x14005961d`
- name: `CS_PathXtraCross`
- size: `81`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140059324`
- `0x14005935c`
- `0x140059594`
- `0x140059734`
- `0x140064ea4`
- `0x14006a71c`
- `0x14006ab90`
- `0x14006b1bc`
- `0x14008d20c`
- `0x14008da34`

## callees

- `0x1400595cc`
- `0x1400675a0`

## pseudocode

```c
__int64 __fastcall CS_PathXtraCross(__int64 a1, int a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  if ( a2 == 1 )
  {
    v3 = a1 + 24;
    if ( (*(_WORD *)v3 & 0x1000) != 0 )
    {
      v4 = *(int *)(v3 + 16);
      return v3 + v4;
    }
  }
  else
  {
    if ( a2 != 2 )
      os_raise(0xFFFFFFFFLL, 0);
    v3 = a1 - 24;
    if ( (*(_WORD *)(a1 - 24) & 0x1000) != 0 )
    {
      v4 = *(int *)(v3 + 20);
      return v3 + v4;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1400595cc  push    rbx
0x1400595ce  sub     rsp, 20h
0x1400595d2  mov     rbx, rcx
0x1400595d5  cmp     edx, 1
0x1400595d8  jz      short loc_1400595FD
0x1400595da  cmp     edx, 2
0x1400595dd  jz      short loc_1400595E9
0x1400595df  xor     edx, edx
0x1400595e1  or      ecx, 0FFFFFFFFh
0x1400595e4  call    os_raise
0x1400595e9  lea     rcx, [rbx-18h]
0x1400595ed  mov     eax, 1000h
0x1400595f2  test    [rcx], ax
0x1400595f5  jz      short loc_140059614
0x1400595f7  movsxd  rax, dword ptr [rcx+14h]
0x1400595fb  jmp     short loc_14005960F
0x1400595fd  add     rcx, 18h
0x140059601  mov     eax, 1000h
0x140059606  test    [rcx], ax
0x140059609  jz      short loc_140059614
0x14005960b  movsxd  rax, dword ptr [rcx+10h]
0x14005960f  add     rax, rcx
0x140059612  jmp     short loc_140059617
0x140059614  mov     rax, rcx
0x140059617  add     rsp, 20h
0x14005961b  pop     rbx
0x14005961c  retn
```
