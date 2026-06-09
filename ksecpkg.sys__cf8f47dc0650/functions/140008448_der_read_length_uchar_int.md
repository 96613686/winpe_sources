# der_read_length(uchar * *,int *)

- ea: `0x140008448`
- end: `0x1400084ba`
- name: `?der_read_length@@YAHPEAPEAEPEAH@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned __int8 **, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400085dc`
- `0x140026e3c`

## callees

- `0x140008448`

## pseudocode

```c
__int64 __fastcall der_read_length(unsigned __int8 **a1, int *a2)
{
  int v3; // r8d
  int v4; // r9d
  unsigned __int8 *v5; // r10
  unsigned __int8 v6; // r9
  int v7; // ecx

  if ( *a2 < 1 )
    return 0xFFFFFFFFLL;
  v3 = *a2 - 1;
  v4 = **a1;
  v5 = *a1 + 1;
  *a1 = v5;
  *a2 = v3;
  if ( (v4 & 0x80u) != 0 )
  {
    v6 = v4 & 0x7F;
    if ( v6 + 1 <= v3 && v6 <= 4u )
    {
      v7 = 0;
      if ( v6 )
      {
        do
        {
          v7 = *v5++ + (v7 << 8);
          *a2 = --v3;
          --v6;
        }
        while ( v6 );
        *a1 = v5;
      }
      goto LABEL_9;
    }
    return 0xFFFFFFFFLL;
  }
  v7 = v4;
LABEL_9:
  if ( v7 > v3 )
    return (unsigned int)-1;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008448  mov     r8d, [rdx]
0x14000844b  mov     r11, rcx
0x14000844e  cmp     r8d, 1
0x140008452  jl      short loc_1400084B6
0x140008454  mov     rax, [rcx]
0x140008457  dec     r8d
0x14000845a  movzx   r9d, byte ptr [rax]
0x14000845e  lea     r10, [rax+1]
0x140008462  mov     [rcx], r10
0x140008465  mov     [rdx], r8d
0x140008468  test    r9b, r9b
0x14000846b  jns     short loc_1400084A6
0x14000846d  and     r9b, 7Fh
0x140008471  movzx   eax, r9b
0x140008475  inc     eax
0x140008477  cmp     eax, r8d
0x14000847a  jg      short loc_1400084B6
0x14000847c  cmp     r9b, 4
0x140008480  ja      short loc_1400084B6
0x140008482  xor     ecx, ecx
0x140008484  test    r9b, r9b
0x140008487  jz      short loc_1400084A9
0x140008489  movzx   eax, byte ptr [r10]
0x14000848d  shl     ecx, 8
0x140008490  add     ecx, eax
0x140008492  inc     r10
0x140008495  dec     r8d
0x140008498  mov     [rdx], r8d
0x14000849b  add     r9b, 0FFh
0x14000849f  jnz     short loc_140008489
0x1400084a1  mov     [r11], r10
0x1400084a4  jmp     short loc_1400084A9
0x1400084a6  mov     ecx, r9d
0x1400084a9  or      eax, 0FFFFFFFFh
0x1400084ac  cmp     ecx, r8d
0x1400084af  cmovg   ecx, eax
0x1400084b2  mov     eax, ecx
0x1400084b4  retn
0x1400084b6  or      eax, 0FFFFFFFFh
0x1400084b9  retn
```
