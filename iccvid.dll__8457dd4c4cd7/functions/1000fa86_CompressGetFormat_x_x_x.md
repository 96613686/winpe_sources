# CompressGetFormat(x,x,x)

- ea: `0x1000fa86`
- end: `0x1000fb03`
- name: `_CompressGetFormat@12`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100093a0`

## callees

- `0x1000fa28`
- `0x1000fa86`

## pseudocode

```c
int __fastcall CompressGetFormat(int a1, int a2, int a3)
{
  int result; // eax
  __int16 v6; // ax
  unsigned int v7; // ecx

  result = CompressQuery(a1, a2, 0);
  if ( !result )
  {
    if ( a3 )
    {
      *(_DWORD *)a3 = 40;
      *(_DWORD *)(a3 + 4) = *(_DWORD *)(a2 + 4);
      *(_DWORD *)(a3 + 8) = *(_DWORD *)(a2 + 8);
      *(_WORD *)(a3 + 12) = 1;
      v6 = 24;
      if ( *(_BYTE *)(a1 + 5) )
        v6 = 40;
      *(_DWORD *)(a3 + 16) = 1684633187;
      *(_WORD *)(a3 + 14) = v6;
      v7 = *(_DWORD *)(a2 + 8) * *(_DWORD *)(a2 + 4);
      *(_DWORD *)(a3 + 36) = 0;
      *(_DWORD *)(a3 + 32) = 0;
      *(_DWORD *)(a3 + 28) = 0;
      *(_DWORD *)(a3 + 24) = 0;
      *(_DWORD *)(a3 + 20) = (v7 >> 2) + 9300 + (v7 >> 6);
      return 0;
    }
    else
    {
      return 40;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1000fa86  mov     edi, edi
0x1000fa88  push    ebp
0x1000fa89  mov     ebp, esp
0x1000fa8b  push    ebx
0x1000fa8c  push    esi
0x1000fa8d  push    edi
0x1000fa8e  xor     ebx, ebx
0x1000fa90  mov     esi, edx
0x1000fa92  push    ebx
0x1000fa93  mov     edi, ecx
0x1000fa95  call    _CompressQuery@12; CompressQuery(x,x,x)
0x1000fa9a  test    eax, eax
0x1000fa9c  jnz     short loc_1000FAFC
0x1000fa9e  mov     edx, [ebp+arg_0]
0x1000faa1  push    28h ; '('
0x1000faa3  test    edx, edx
0x1000faa5  jnz     short loc_1000FAAA
0x1000faa7  pop     eax
0x1000faa8  jmp     short loc_1000FAFC
0x1000faaa  pop     ecx
0x1000faab  mov     [edx], ecx
0x1000faad  mov     eax, [esi+4]
0x1000fab0  mov     [edx+4], eax
0x1000fab3  mov     eax, [esi+8]
0x1000fab6  mov     [edx+8], eax
0x1000fab9  xor     eax, eax
0x1000fabb  inc     eax
0x1000fabc  mov     [edx+0Ch], ax
0x1000fac0  cmp     [edi+5], bl
0x1000fac3  push    18h
0x1000fac5  pop     eax
0x1000fac6  cmovnz  eax, ecx
0x1000fac9  mov     dword ptr [edx+10h], 64697663h
0x1000fad0  mov     [edx+0Eh], ax
0x1000fad4  mov     ecx, [esi+4]
0x1000fad7  imul    ecx, [esi+8]
0x1000fadb  mov     [edx+24h], ebx
0x1000fade  mov     [edx+20h], ebx
0x1000fae1  mov     [edx+1Ch], ebx
0x1000fae4  mov     [edx+18h], ebx
0x1000fae7  mov     eax, ecx
0x1000fae9  shr     ecx, 2
0x1000faec  shr     eax, 6
0x1000faef  add     ecx, 2454h
0x1000faf5  add     eax, ecx
0x1000faf7  mov     [edx+14h], eax
0x1000fafa  xor     eax, eax
0x1000fafc  pop     edi
0x1000fafd  pop     esi
0x1000fafe  pop     ebx
0x1000faff  pop     ebp
0x1000fb00  retn    4
```
