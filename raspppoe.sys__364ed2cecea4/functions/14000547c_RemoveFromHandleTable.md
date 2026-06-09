# RemoveFromHandleTable

- ea: `0x14000547c`
- end: `0x1400054ba`
- name: `RemoveFromHandleTable`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e0c`
- `0x140005f90`
- `0x140014884`

## callees

- `0x14000547c`

## pseudocode

```c
void __fastcall RemoveFromHandleTable(__int64 *a1, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rdx

  if ( a1 )
  {
    v3 = WORD1(a2);
    if ( (unsigned int)v3 < *((_DWORD *)a1 + 2) )
    {
      v4 = *a1;
      v5 = 3 * v3;
      if ( *(_BYTE *)(*a1 + 8 * v5) )
      {
        if ( *(_QWORD *)(v4 + 8 * v5 + 16) == a2 )
        {
          *(_OWORD *)(v4 + 8 * v5) = 0;
          *(_QWORD *)(v4 + 8 * v5 + 16) = 0;
          --*((_DWORD *)a1 + 3);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000547c  mov     r8, rdx
0x14000547f  test    rcx, rcx
0x140005482  jz      short locret_1400054B9
0x140005484  mov     rax, rdx
0x140005487  shr     rax, 10h
0x14000548b  movzx   edx, ax
0x14000548e  cmp     edx, [rcx+8]
0x140005491  jnb     short locret_1400054B9
0x140005493  mov     rax, [rcx]
0x140005496  lea     rdx, [rdx+rdx*2]
0x14000549a  cmp     byte ptr [rax+rdx*8], 0
0x14000549e  jz      short locret_1400054B9
0x1400054a0  cmp     [rax+rdx*8+10h], r8
0x1400054a5  jnz     short locret_1400054B9
0x1400054a7  xor     r8d, r8d
0x1400054aa  xorps   xmm0, xmm0
0x1400054ad  movups  xmmword ptr [rax+rdx*8], xmm0
0x1400054b1  mov     [rax+rdx*8+10h], r8
0x1400054b6  dec     dword ptr [rcx+0Ch]
0x1400054b9  retn
```
