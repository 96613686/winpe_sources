# sub_1001DFBD

- ea: `0x1001dfbd`
- end: `0x1001e079`
- name: `sub_1001DFBD`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1001dfbd`

## pseudocode

```c
int __cdecl sub_1001DFBD(unsigned int a1)
{
  int v1; // esi
  __int16 v2; // ax
  int v3; // ebx
  int v4; // eax

  v1 = 0;
  v2 = a1 & 0x8040;
  if ( (a1 & 0x8040) == 0x8000 )
  {
    v3 = 3072;
  }
  else if ( v2 == 64 )
  {
    v3 = 2048;
  }
  else
  {
    v3 = 1024;
    if ( v2 != -32704 )
      v3 = 0;
  }
  v4 = a1 & 0x6000;
  if ( (a1 & 0x6000) != 0 )
  {
    switch ( v4 )
    {
      case 8192:
        v1 = 256;
        break;
      case 16384:
        v1 = 512;
        break;
      case 24576:
        v1 = 768;
        break;
    }
  }
  return v3
       | v1
       | (a1 >> 12) & 1
       | (2 * ((a1 >> 11) & 1))
       | (8 * ((a1 >> 9) & 1))
       | (16 * ((a1 >> 7) & 1))
       | (32 * ((a1 >> 8) & 1))
       | (4 * ((a1 >> 10) & 1));
}

```

## disassembly

```asm
0x1001dfbd  mov     edi, edi
0x1001dfbf  push    ebp
0x1001dfc0  mov     ebp, esp
0x1001dfc2  push    ebx
0x1001dfc3  push    esi
0x1001dfc4  mov     edx, 8040h
0x1001dfc9  xor     esi, esi
0x1001dfcb  push    edi
0x1001dfcc  mov     edi, [ebp+arg_0]
0x1001dfcf  mov     eax, edi
0x1001dfd1  and     eax, edx
0x1001dfd3  lea     ecx, [edx-40h]
0x1001dfd6  cmp     ax, cx
0x1001dfd9  jnz     short loc_1001DFE2
0x1001dfdb  mov     ebx, 0C00h
0x1001dfe0  jmp     short loc_1001DFFB
0x1001dfe2  cmp     ax, 40h ; '@'
0x1001dfe6  jnz     short loc_1001DFEF
0x1001dfe8  mov     ebx, 800h
0x1001dfed  jmp     short loc_1001DFFB
0x1001dfef  mov     ebx, 400h
0x1001dff4  cmp     ax, dx
0x1001dff7  jz      short loc_1001DFFB
0x1001dff9  mov     ebx, esi
0x1001dffb  mov     eax, edi
0x1001dffd  mov     ecx, 6000h
0x1001e002  and     eax, ecx
0x1001e004  jz      short loc_1001E02B
0x1001e006  cmp     eax, 2000h
0x1001e00b  jz      short loc_1001E026
0x1001e00d  cmp     eax, 4000h
0x1001e012  jz      short loc_1001E01F
0x1001e014  cmp     eax, ecx
0x1001e016  jnz     short loc_1001E02B
0x1001e018  mov     esi, 300h
0x1001e01d  jmp     short loc_1001E02B
0x1001e01f  mov     esi, 200h
0x1001e024  jmp     short loc_1001E02B
0x1001e026  mov     esi, 100h
0x1001e02b  xor     ecx, ecx
0x1001e02d  mov     edx, edi
0x1001e02f  inc     ecx
0x1001e030  shr     edx, 8
0x1001e033  and     edx, ecx
0x1001e035  mov     eax, edi
0x1001e037  shr     eax, 7
0x1001e03a  and     eax, ecx
0x1001e03c  shl     edx, 5
0x1001e03f  shl     eax, 4
0x1001e042  or      edx, eax
0x1001e044  mov     eax, edi
0x1001e046  shr     eax, 9
0x1001e049  and     eax, ecx
0x1001e04b  shl     eax, 3
0x1001e04e  or      edx, eax
0x1001e050  mov     eax, edi
0x1001e052  shr     eax, 0Ah
0x1001e055  and     eax, ecx
0x1001e057  mov     ecx, edi
0x1001e059  shl     eax, 2
0x1001e05c  shr     ecx, 0Bh
0x1001e05f  or      eax, edx
0x1001e061  and     ecx, 1
0x1001e064  shr     edi, 0Ch
0x1001e067  add     ecx, ecx
0x1001e069  and     edi, 1
0x1001e06c  or      eax, ecx
0x1001e06e  or      eax, edi
0x1001e070  pop     edi
0x1001e071  or      eax, esi
0x1001e073  pop     esi
0x1001e074  or      eax, ebx
0x1001e076  pop     ebx
0x1001e077  pop     ebp
0x1001e078  retn
```
