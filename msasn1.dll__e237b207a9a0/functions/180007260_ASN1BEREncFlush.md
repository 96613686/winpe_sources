# ASN1BEREncFlush

- ea: `0x180007260`
- end: `0x180007298`
- name: `ASN1BEREncFlush`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f30`
- `0x1800070f0`

## callees

- `0x180007260`
- `0x180007c70`

## pseudocode

```c
__int64 __fastcall ASN1BEREncFlush(__int64 a1)
{
  _BYTE *v1; // rax
  __int64 result; // rax

  if ( !*(_QWORD *)(a1 + 16) )
    return ASN1EncCheck(a1, 1u);
  v1 = *(_BYTE **)(a1 + 40);
  if ( *(_BYTE **)(a1 + 16) == v1 )
  {
    *v1 = 0;
    ++*(_QWORD *)(a1 + 40);
  }
  result = 1;
  *(_DWORD *)(a1 + 28) = *(_DWORD *)(a1 + 40) - *(_DWORD *)(a1 + 16);
  return result;
}

```

## disassembly

```asm
0x180007260  cmp     qword ptr [rcx+10h], 0
0x180007265  mov     r8, rcx
0x180007268  jz      short loc_180007285
0x18000726a  mov     rax, [rcx+28h]
0x18000726e  cmp     [rcx+10h], rax
0x180007272  jz      short loc_18000728F
0x180007274  mov     ecx, [rcx+28h]
0x180007277  mov     eax, 1
0x18000727c  sub     ecx, [r8+10h]
0x180007280  mov     [r8+1Ch], ecx
0x180007284  retn
0x180007285  mov     edx, 1
0x18000728a  jmp     ASN1EncCheck
0x18000728f  mov     byte ptr [rax], 0
0x180007292  inc     qword ptr [rcx+28h]
0x180007296  jmp     short loc_180007274
```
