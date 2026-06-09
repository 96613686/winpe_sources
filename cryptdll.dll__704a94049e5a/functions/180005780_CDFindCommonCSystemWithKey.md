# CDFindCommonCSystemWithKey

- ea: `0x180005780`
- end: `0x1800057f1`
- name: `CDFindCommonCSystemWithKey`
- size: `113`
- prototype: `__int64 __fastcall(unsigned int, __int64, unsigned int, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005780`

## pseudocode

```c
__int64 __fastcall CDFindCommonCSystemWithKey(unsigned int a1, __int64 a2, unsigned int a3, __int64 a4, _DWORD *a5)
{
  __int64 v8; // r10
  unsigned int i; // r8d
  int v10; // edx
  __int64 j; // rcx

  v8 = 0;
  *a5 = 0;
  while ( (unsigned int)v8 < a1 )
  {
    for ( i = 0; i < cCSystems; ++i )
    {
      v10 = *(_DWORD *)(a2 + 4 * v8);
      if ( v10 == LODWORD(CSystems[16 * (unsigned __int64)i]) )
      {
        for ( j = 0; (unsigned int)j < a3; j = (unsigned int)(j + 1) )
        {
          if ( *(_DWORD *)(a4 + 4 * j) == v10 )
          {
            *a5 = v10;
            return 0;
          }
        }
      }
    }
    v8 = (unsigned int)(v8 + 1);
  }
  return 2148008769LL;
}

```

## disassembly

```asm
0x180005780  push    rbx
0x180005782  push    rsi
0x180005783  push    rdi
0x180005784  push    r14
0x180005786  mov     r11, [rsp+20h+arg_20]
0x18000578b  mov     edi, r8d
0x18000578e  mov     r14, rdx
0x180005791  mov     ebx, ecx
0x180005793  xor     r10d, r10d
0x180005796  mov     dword ptr [r11], 0
0x18000579d  cmp     r10d, ebx
0x1800057a0  jnb     short loc_1800057E6
0x1800057a2  xor     r8d, r8d
0x1800057a5  cmp     r8d, cs:cCSystems
0x1800057ac  jnb     short loc_1800057DA
0x1800057ae  mov     edx, [r14+r10*4]
0x1800057b2  lea     rcx, CSystems
0x1800057b9  mov     eax, r8d
0x1800057bc  shl     rax, 7
0x1800057c0  cmp     edx, [rax+rcx]
0x1800057c3  jnz     short loc_1800057D5
0x1800057c5  xor     ecx, ecx
0x1800057c7  cmp     ecx, edi
0x1800057c9  jnb     short loc_1800057D5
0x1800057cb  cmp     [r9+rcx*4], edx
0x1800057cf  jz      short loc_1800057DF
0x1800057d1  inc     ecx
0x1800057d3  jmp     short loc_1800057C7
0x1800057d5  inc     r8d
0x1800057d8  jmp     short loc_1800057A5
0x1800057da  inc     r10d
0x1800057dd  jmp     short loc_18000579D
0x1800057df  mov     [r11], edx
0x1800057e2  xor     eax, eax
0x1800057e4  jmp     short loc_1800057EB
0x1800057e6  mov     eax, 80080341h
0x1800057eb  pop     r14
0x1800057ed  pop     rdi
0x1800057ee  pop     rsi
0x1800057ef  pop     rbx
0x1800057f0  retn
```
