# imaadpcmIsValidFormat

- ea: `0x180002ccc`
- end: `0x180002d68`
- name: `imaadpcmIsValidFormat`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002460`
- `0x1800025f8`
- `0x180002988`

## callees

- `0x180002ccc`

## pseudocode

```c
_BOOL8 __fastcall imaadpcmIsValidFormat(_WORD *a1)
{
  unsigned int v1; // r9d
  _BOOL8 result; // rax

  result = 0;
  if ( a1 )
  {
    if ( *a1 == 17 && a1[7] == 4 )
    {
      v1 = (unsigned __int16)a1[1];
      if ( (unsigned __int16)(v1 - 1) <= 1u
        && !((unsigned __int16)a1[6] % (4 * (unsigned __int64)(unsigned __int16)v1))
        && a1[8] == 2
        && a1[9] >= 5u
        && (a1[9] & 3) == 1
        && a1[9] == (unsigned __int16)(8 * ((unsigned int)(unsigned __int16)a1[6] - (4 << (v1 >> 1))) / (4 << (v1 >> 1)))
                  + 1 )
      {
        return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002ccc  mov     [rsp+arg_0], rbx
0x180002cd1  mov     r8, rcx
0x180002cd4  test    rcx, rcx
0x180002cd7  jz      loc_180002D60
0x180002cdd  mov     eax, 11h
0x180002ce2  cmp     ax, [rcx]
0x180002ce5  jnz     short loc_180002D60
0x180002ce7  lea     r10d, [rax-0Dh]
0x180002ceb  cmp     r10w, [rcx+0Eh]
0x180002cf0  jnz     short loc_180002D60
0x180002cf2  movzx   r9d, word ptr [rcx+2]
0x180002cf7  lea     ebx, [r10-3]
0x180002cfb  movzx   eax, r9w
0x180002cff  sub     ax, bx
0x180002d02  cmp     ax, bx
0x180002d05  ja      short loc_180002D60
0x180002d07  movzx   r11d, word ptr [rcx+0Ch]
0x180002d0c  xor     edx, edx
0x180002d0e  movzx   ecx, r9w
0x180002d12  mov     eax, r11d
0x180002d15  shl     rcx, 2
0x180002d19  div     rcx
0x180002d1c  test    rdx, rdx
0x180002d1f  jnz     short loc_180002D60
0x180002d21  lea     eax, [rbx+1]
0x180002d24  cmp     ax, [r8+10h]
0x180002d29  jnz     short loc_180002D60
0x180002d2b  cmp     word ptr [r8+12h], 5
0x180002d31  jb      short loc_180002D60
0x180002d33  mov     al, [r8+12h]
0x180002d37  and     al, 3
0x180002d39  cmp     al, bl
0x180002d3b  jnz     short loc_180002D60
0x180002d3d  shr     r9d, 1
0x180002d40  mov     eax, r11d
0x180002d43  mov     cl, r9b
0x180002d46  shl     r10d, cl
0x180002d49  sub     eax, r10d
0x180002d4c  shl     eax, 3
0x180002d4f  div     r10d
0x180002d52  add     ax, bx
0x180002d55  cmp     [r8+12h], ax
0x180002d5a  jnz     short loc_180002D60
0x180002d5c  mov     eax, ebx
0x180002d5e  jmp     short loc_180002D62
0x180002d60  xor     eax, eax
0x180002d62  mov     rbx, [rsp+arg_0]
0x180002d67  retn
```
