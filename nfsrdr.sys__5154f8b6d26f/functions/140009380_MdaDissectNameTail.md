# MdaDissectNameTail

- ea: `0x140009380`
- end: `0x14000942e`
- name: `MdaDissectNameTail`
- size: `174`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x140003510`
- `0x140004530`
- `0x1400070a0`
- `0x140008680`
- `0x14000be20`
- `0x14000c370`
- `0x14000fbc0`
- `0x1400146a0`
- `0x140018a7c`
- `0x14001bbbc`
- `0x14001c694`
- `0x14002030c`
- `0x1400273f0`
- `0x140030ef0`
- `0x1400316d0`
- `0x1400350d8`
- `0x140035384`

## callees

- `0x140009380`

## pseudocode

```c
__int64 __fastcall MdaDissectNameTail(unsigned __int16 *a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // r8
  __int16 v7; // cx
  __int64 v8; // rdx

  *(_OWORD *)a2 = *(_OWORD *)a1;
  *(_OWORD *)a3 = *(_OWORD *)a1;
  result = *a1;
  if ( (_WORD)result )
  {
    result = (unsigned int)result >> 1;
    if ( (_DWORD)result )
    {
      do
      {
        v6 = (unsigned int)(result - 1);
        if ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v6) != 92 )
          break;
        result = (unsigned int)v6;
      }
      while ( (_DWORD)v6 );
    }
    v7 = 2 * result;
    *(_WORD *)a2 = 2 * result;
    if ( 2 * (_WORD)result )
    {
      if ( (_DWORD)result )
      {
        do
        {
          v8 = (unsigned int)(result - 1);
          if ( *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * v8) == 92 )
            break;
          result = (unsigned int)v8;
        }
        while ( (_DWORD)v8 );
      }
      *(_WORD *)a3 = v7 - 2 * result;
      *(_WORD *)(a3 + 2) = *(_WORD *)(a2 + 2) - 2 * result;
      *(_QWORD *)(a3 + 8) = *(_QWORD *)(a2 + 8) + 2LL * (unsigned int)result;
      *(_WORD *)a2 = 2 * result;
      if ( (_DWORD)result )
        *(_WORD *)a2 = 2 * result - 2;
    }
    else
    {
      result = 0;
      *(_WORD *)a3 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140009380  movups  xmm0, xmmword ptr [rcx]
0x140009383  mov     r9, r8
0x140009386  mov     r10, rdx
0x140009389  movups  xmmword ptr [rdx], xmm0
0x14000938c  movups  xmm0, xmmword ptr [rcx]
0x14000938f  movups  xmmword ptr [r8], xmm0
0x140009393  movzx   eax, word ptr [rcx]
0x140009396  test    ax, ax
0x140009399  jz      short locret_1400093C1
0x14000939b  shr     eax, 1
0x14000939d  jz      short loc_1400093AF
0x14000939f  mov     rdx, [rcx+8]
0x1400093a3  lea     r8d, [rax-1]
0x1400093a7  cmp     word ptr [rdx+r8*2], 5Ch ; '\'
0x1400093ad  jz      short loc_140009420
0x1400093af  movzx   ecx, ax
0x1400093b2  add     cx, cx
0x1400093b5  mov     [r10], cx
0x1400093b9  jnz     short loc_1400093C3
0x1400093bb  xor     eax, eax
0x1400093bd  mov     [r9], ax
0x1400093c1  retn
0x1400093c3  test    eax, eax
0x1400093c5  jz      short loc_1400093E1
0x1400093c7  mov     r8, [r10+8]
0x1400093cb  nop     dword ptr [rax+rax+00h]
0x1400093d0  lea     edx, [rax-1]
0x1400093d3  cmp     word ptr [r8+rdx*2], 5Ch ; '\'
0x1400093d9  jz      short loc_1400093E1
0x1400093db  mov     eax, edx
0x1400093dd  test    edx, edx
0x1400093df  jnz     short loc_1400093D0
0x1400093e1  movzx   r8d, ax
0x1400093e5  mov     edx, eax
0x1400093e7  add     r8w, r8w
0x1400093eb  sub     cx, r8w
0x1400093ef  mov     [r9], cx
0x1400093f3  movzx   ecx, word ptr [r10+2]
0x1400093f8  sub     cx, r8w
0x1400093fc  mov     [r9+2], cx
0x140009401  mov     rcx, [r10+8]
0x140009405  lea     rdx, [rcx+rdx*2]
0x140009409  mov     [r9+8], rdx
0x14000940d  mov     [r10], r8w
0x140009411  test    eax, eax
0x140009413  jz      short locret_1400093C1
0x140009415  sub     r8w, 2
0x14000941a  mov     [r10], r8w
0x14000941e  retn
0x140009420  mov     eax, r8d
0x140009423  test    r8d, r8d
0x140009426  jnz     loc_1400093A3
0x14000942c  jmp     short loc_1400093AF
```
