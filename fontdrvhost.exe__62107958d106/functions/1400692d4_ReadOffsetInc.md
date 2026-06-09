# ReadOffsetInc

- ea: `0x1400692d4`
- end: `0x14006934a`
- name: `ReadOffsetInc`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14005cbd8`
- `0x14008ac70`

## callees

- `0x14005ca2c`
- `0x1400675a0`
- `0x1400692d4`

## pseudocode

```c
__int64 __fastcall ReadOffsetInc(_DWORD *a1, char a2)
{
  unsigned __int8 *v4; // rcx
  unsigned __int8 *v5; // rcx

  if ( a2 == 1 )
  {
    ValidateRange(a1, (unsigned int)(a1[6] - *a1), 1);
    v5 = (unsigned __int8 *)*((_QWORD *)a1 + 3);
    *((_QWORD *)a1 + 3) = v5 + 1;
    return *v5;
  }
  else if ( a2 == 2 )
  {
    ValidateRange(a1, (unsigned int)(a1[6] - *a1), 2);
    v4 = (unsigned __int8 *)*((_QWORD *)a1 + 3);
    *((_QWORD *)a1 + 3) = v4 + 2;
    return (*v4 << 8) | (unsigned int)v4[1];
  }
  else
  {
    os_raise(0xFFFFFFFFLL, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x1400692d4  push    rbx
0x1400692d6  sub     rsp, 20h
0x1400692da  movzx   r8d, dl
0x1400692de  mov     rbx, rcx
0x1400692e1  sub     r8d, 1
0x1400692e5  jz      short loc_140069325
0x1400692e7  cmp     r8d, 1
0x1400692eb  jz      short loc_1400692FB
0x1400692ed  xor     edx, edx
0x1400692ef  or      ecx, 0FFFFFFFFh
0x1400692f2  call    os_raise
0x1400692f7  xor     eax, eax
0x1400692f9  jmp     short loc_140069344
0x1400692fb  mov     edx, [rcx+18h]
0x1400692fe  mov     r8d, 2
0x140069304  sub     edx, [rcx]
0x140069306  call    ValidateRange
0x14006930b  mov     rcx, [rbx+18h]
0x14006930f  lea     rax, [rcx+2]
0x140069313  mov     [rbx+18h], rax
0x140069317  movzx   ecx, byte ptr [rcx]
0x14006931a  movzx   eax, byte ptr [rax-1]
0x14006931e  shl     ecx, 8
0x140069321  or      eax, ecx
0x140069323  jmp     short loc_140069344
0x140069325  mov     edx, [rcx+18h]
0x140069328  mov     r8d, 1
0x14006932e  sub     edx, [rcx]
0x140069330  call    ValidateRange
0x140069335  mov     rcx, [rbx+18h]
0x140069339  lea     rax, [rcx+1]
0x14006933d  mov     [rbx+18h], rax
0x140069341  movzx   eax, byte ptr [rcx]
0x140069344  add     rsp, 20h
0x140069348  pop     rbx
0x140069349  retn
```
