# WriteBytes

- ea: `0x10028ee0`
- end: `0x10028f72`
- name: `WriteBytes`
- size: `146`
- prototype: `int __stdcall(int, int, void *, int, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x10026500`
- `0x10028f80`
- `0x10029000`

## callees

- `0x10028bb0`
- `0x10028ee0`

## pseudocode

```c
int __stdcall WriteBytes(int a1, int a2, unsigned __int16 *a3, int a4, char a5, int a6)
{
  int v6; // esi
  unsigned __int16 *i; // edi
  int result; // eax
  unsigned int v9; // eax

  if ( (a5 & 2) != 0 )
  {
    v6 = 0;
    if ( a4 > 0 )
    {
      for ( i = a3; ; ++i )
      {
        result = TextWriteHTMLFile(a1, a2, i, 1, a6, a5);
        if ( result )
          break;
        if ( ++v6 >= a4 )
          return result;
      }
      goto LABEL_7;
    }
    return 0;
  }
  result = TextWriteHTMLFile(a1, a2, a3, a4, a6, a5);
  if ( !result )
    return 0;
LABEL_7:
  v9 = -result;
  if ( v9 >= 0x10 )
    return -5016;
  else
    return dword_100038B8[v9];
}

```

## disassembly

```asm
0x10028ee0  push    ebx
0x10028ee1  mov     ebx, [esp+4+arg_10]
0x10028ee5  push    ebp
0x10028ee6  push    esi
0x10028ee7  push    edi
0x10028ee8  test    bl, 2
0x10028eeb  jz      short loc_10028F4B
0x10028eed  mov     ebp, [esp+10h+arg_C]
0x10028ef1  xor     esi, esi
0x10028ef3  test    ebp, ebp
0x10028ef5  jle     short loc_10028F69
0x10028ef7  mov     edi, [esp+10h+arg_8]
0x10028efb  jmp     short loc_10028F00
0x10028f00  push    ebx; int
0x10028f01  push    [esp+14h+arg_14]; int
0x10028f05  push    1; int
0x10028f07  push    edi; void *
0x10028f08  push    [esp+20h+arg_4]; int
0x10028f0c  push    [esp+24h+arg_0]; int
0x10028f10  call    TextWriteHTMLFile
0x10028f15  test    eax, eax
0x10028f17  jnz     short loc_10028F28
0x10028f19  inc     esi
0x10028f1a  add     edi, 2
0x10028f1d  cmp     esi, ebp
0x10028f1f  jl      short loc_10028F00
0x10028f21  pop     edi
0x10028f22  pop     esi
0x10028f23  pop     ebp
0x10028f24  pop     ebx
0x10028f25  retn    18h
0x10028f28  neg     eax
0x10028f2a  js      short loc_10028F3F
0x10028f2c  cmp     eax, 0Fh
0x10028f2f  ja      short loc_10028F3F
0x10028f31  mov     eax, ds:dword_100038B8[eax*4]
0x10028f38  pop     edi
0x10028f39  pop     esi
0x10028f3a  pop     ebp
0x10028f3b  pop     ebx
0x10028f3c  retn    18h
0x10028f3f  pop     edi
0x10028f40  pop     esi
0x10028f41  pop     ebp
0x10028f42  mov     eax, 0FFFFEC68h
0x10028f47  pop     ebx
0x10028f48  retn    18h
0x10028f4b  push    ebx; int
0x10028f4c  push    [esp+14h+arg_14]; int
0x10028f50  push    [esp+18h+arg_C]; int
0x10028f54  push    [esp+1Ch+arg_8]; void *
0x10028f58  push    [esp+20h+arg_4]; int
0x10028f5c  push    [esp+24h+arg_0]; int
0x10028f60  call    TextWriteHTMLFile
0x10028f65  test    eax, eax
0x10028f67  jnz     short loc_10028F28
0x10028f69  pop     edi
0x10028f6a  pop     esi
0x10028f6b  pop     ebp
0x10028f6c  xor     eax, eax
0x10028f6e  pop     ebx
0x10028f6f  retn    18h
```
