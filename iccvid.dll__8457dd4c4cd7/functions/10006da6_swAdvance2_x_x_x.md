# swAdvance2(x,x,x)

- ea: `0x10006da6`
- end: `0x10006e0c`
- name: `_swAdvance2@12`
- size: `102`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x10006e20`
- `0x100072f0`
- `0x100077a0`
- `0x10007aa0`
- `0x10007cf0`
- `0x10008170`
- `0x100084b0`
- `0x10008860`
- `0x10008b00`
- `0x10009010`
- `0x1000a640`
- `0x1000af30`
- `0x1000b8e0`
- `0x1000c2a0`
- `0x1000ccf0`
- `0x1000d260`
- `0x1000d7d0`
- `0x1000e120`
- `0x1000e2f0`
- `0x1000e870`
- `0x1000ea40`

## callees

- `0x10006da6`

## pseudocode

```c
unsigned int __fastcall swAdvance2(_DWORD *a1, unsigned __int8 **a2, int *a3)
{
  unsigned int result; // eax
  unsigned __int8 *v4; // edx
  int v5; // esi

  if ( *a3 >= 4 )
  {
    v4 = *a2;
    *a3 -= 4;
    *a1 = 0x80000000;
    v5 = v4[3] | ((v4[2] | (((*v4 << 8) | v4[1]) << 8)) << 8);
    a1[1] = v5;
    *a2 = v4 + 4;
    return v5 & 0x80000000;
  }
  else
  {
    result = 0;
    *a3 = 0;
    *a1 = 0;
    a1[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x10006da6  mov     edi, edi
0x10006da8  push    ebp
0x10006da9  mov     ebp, esp
0x10006dab  push    ecx
0x10006dac  push    ebx
0x10006dad  mov     ebx, [ebp+arg_0]
0x10006db0  mov     eax, edx
0x10006db2  push    edi
0x10006db3  mov     [ebp+var_4], eax
0x10006db6  mov     edi, ecx
0x10006db8  cmp     dword ptr [ebx], 4
0x10006dbb  jge     short loc_10006DC8
0x10006dbd  xor     eax, eax
0x10006dbf  mov     [ebx], eax
0x10006dc1  mov     [edi], eax
0x10006dc3  mov     [edi+4], eax
0x10006dc6  jmp     short loc_10006E06
0x10006dc8  mov     edx, [eax]
0x10006dca  add     dword ptr [ebx], 0FFFFFFFCh
0x10006dcd  push    esi
0x10006dce  mov     dword ptr [edi], 80000000h
0x10006dd4  movzx   eax, byte ptr [edx]
0x10006dd7  movzx   esi, byte ptr [edx+1]
0x10006ddb  movzx   ecx, byte ptr [edx+3]
0x10006ddf  shl     eax, 8
0x10006de2  or      esi, eax
0x10006de4  movzx   eax, byte ptr [edx+2]
0x10006de8  shl     esi, 8
0x10006deb  or      esi, eax
0x10006ded  mov     eax, [ebp+var_4]
0x10006df0  shl     esi, 8
0x10006df3  or      esi, ecx
0x10006df5  lea     ecx, [edx+4]
0x10006df8  mov     [edi+4], esi
0x10006dfb  and     esi, 80000000h
0x10006e01  mov     [eax], ecx
0x10006e03  mov     eax, esi
0x10006e05  pop     esi
0x10006e06  pop     edi
0x10006e07  pop     ebx
0x10006e08  leave
0x10006e09  retn    4
```
