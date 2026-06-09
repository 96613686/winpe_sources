# binary_search_remove_node

- ea: `0x180010fd8`
- end: `0x180011062`
- name: `binary_search_remove_node`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010130`

## callees

- `0x180010fd8`

## pseudocode

```c
__int64 __fastcall binary_search_remove_node(_QWORD *a1, unsigned int a2, unsigned int a3)
{
  __int64 v3; // r10
  __int64 result; // rax
  unsigned int *v5; // r11
  __int64 v6; // r9
  __int64 v7; // rbx
  unsigned int v8; // ecx
  unsigned int v9; // edx

  v3 = a2;
  result = a1[2];
  v5 = (unsigned int *)(result + 4LL * *(unsigned __int16 *)(*a1 + a2));
  if ( *v5 == a2 )
  {
    v6 = a1[3];
    v7 = a1[4];
    v8 = 0;
    if ( *v5 <= a3 )
    {
      *v5 = 0;
      *(_DWORD *)(v7 + 4LL * a2) = 0;
      *(_DWORD *)(v6 + 4LL * a2) = 0;
    }
    else
    {
      v9 = *(_DWORD *)(v6 + 4LL * a2);
      if ( v9 <= a3 )
      {
        *(_DWORD *)(v6 + 4 * v3) = 0;
        v9 = 0;
      }
      if ( *(_DWORD *)(v7 + 4 * v3) <= a3 )
        *(_DWORD *)(v7 + 4 * v3) = 0;
      else
        v8 = *(_DWORD *)(v7 + 4 * v3);
      while ( 1 )
      {
        while ( v9 > v8 )
        {
          result = a3 < v9 ? v9 : 0;
          *v5 = result;
          if ( (a3 < v9 ? v9 : 0) == 0 )
            return result;
          v5 = (unsigned int *)(v7 + 4 * result);
          v9 = *v5;
        }
        result = a3 < v8 ? v8 : 0;
        *v5 = result;
        if ( (a3 < v8 ? v8 : 0) == 0 )
          break;
        v5 = (unsigned int *)(v6 + 4 * result);
        v8 = *v5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010fd8  mov     [rsp+arg_0], rbx
0x180010fdd  mov     rax, [rcx]
0x180010fe0  mov     r10d, edx
0x180010fe3  movzx   r9d, word ptr [rax+r10]
0x180010fe8  mov     rax, [rcx+10h]
0x180010fec  lea     r11, [rax+r9*4]
0x180010ff0  cmp     [r11], edx
0x180010ff3  jnz     short loc_180011056
0x180010ff5  mov     r9, [rcx+18h]
0x180010ff9  mov     rbx, [rcx+20h]
0x180010ffd  xor     ecx, ecx
0x180010fff  cmp     [r11], r8d
0x180011002  jbe     short loc_18001104B
0x180011004  mov     edx, [r9+r10*4]
0x180011008  cmp     edx, r8d
0x18001100b  ja      short loc_180011013
0x18001100d  mov     [r9+r10*4], ecx
0x180011011  mov     edx, ecx
0x180011013  cmp     [rbx+r10*4], r8d
0x180011017  jbe     short loc_18001105C
0x180011019  mov     ecx, [rbx+r10*4]
0x18001101d  cmp     edx, ecx
0x18001101f  jbe     short loc_180011036
0x180011021  cmp     r8d, edx
0x180011024  sbb     eax, eax
0x180011026  and     eax, edx
0x180011028  mov     [r11], eax
0x18001102b  jz      short loc_180011056
0x18001102d  lea     r11, [rbx+rax*4]
0x180011031  mov     edx, [r11]
0x180011034  jmp     short loc_18001101D
0x180011036  cmp     r8d, ecx
0x180011039  sbb     eax, eax
0x18001103b  and     eax, ecx
0x18001103d  mov     [r11], eax
0x180011040  jz      short loc_180011056
0x180011042  lea     r11, [r9+rax*4]
0x180011046  mov     ecx, [r11]
0x180011049  jmp     short loc_18001101D
0x18001104b  mov     [r11], ecx
0x18001104e  mov     [rbx+r10*4], ecx
0x180011052  mov     [r9+r10*4], ecx
0x180011056  mov     rbx, [rsp+arg_0]
0x18001105b  retn
0x18001105c  mov     [rbx+r10*4], ecx
0x180011060  jmp     short loc_18001101D
```
