# ParveEncryptBlock

- ea: `0x1800065e8`
- end: `0x180006656`
- name: `ParveEncryptBlock`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005984`
- `0x180006558`

## callees

- `0x1800065e8`

## pseudocode

```c
__int64 __fastcall ParveEncryptBlock(__int64 a1, _BYTE *a2, __int64 a3)
{
  char v3; // r11
  int v4; // ebx
  __int64 v5; // r10
  __int64 result; // rax

  v3 = 8;
  do
  {
    v4 = 0;
    v5 = 0;
    do
    {
      ++v4;
      a2[v5 + 1] = __ROR1__(a2[v5 + 1] + *(_BYTE *)((unsigned __int8)(v3 + *(_BYTE *)(a1 + v5) + a2[v5]) + a3), 7);
      ++v5;
    }
    while ( v4 < 7 );
    result = (unsigned __int8)(v3 + *(_BYTE *)(v4 + a1) + a2[v4]);
    *a2 = __ROR1__(*a2 + *(_BYTE *)(result + a3), 7);
    --v3;
  }
  while ( v3 );
  return result;
}

```

## disassembly

```asm
0x1800065e8  push    rbx
0x1800065ea  push    rsi
0x1800065eb  push    rdi
0x1800065ec  mov     r9, rdx
0x1800065ef  mov     rsi, rcx
0x1800065f2  mov     r11b, 8
0x1800065f5  xor     ebx, ebx
0x1800065f7  movzx   edi, r11b
0x1800065fb  xor     r10d, r10d
0x1800065fe  movzx   eax, byte ptr [rsi+r10]
0x180006603  inc     ebx
0x180006605  movzx   ecx, byte ptr [r10+r9]
0x18000660a  add     eax, edi
0x18000660c  add     ecx, eax
0x18000660e  movzx   eax, cl
0x180006611  mov     dl, [rax+r8]
0x180006615  add     dl, [r10+r9+1]
0x18000661a  ror     dl, 7
0x18000661d  mov     [r10+r9+1], dl
0x180006622  inc     r10
0x180006625  cmp     ebx, 7
0x180006628  jl      short loc_1800065FE
0x18000662a  movsxd  rax, ebx
0x18000662d  movzx   edx, byte ptr [rax+r9]
0x180006632  movzx   ecx, byte ptr [rax+rsi]
0x180006636  lea     eax, [rdi+rcx]
0x180006639  add     edx, eax
0x18000663b  movzx   eax, dl
0x18000663e  mov     dl, [rax+r8]
0x180006642  add     dl, [r9]
0x180006645  ror     dl, 7
0x180006648  mov     [r9], dl
0x18000664b  add     r11b, 0FFh
0x18000664f  jnz     short loc_1800065F5
0x180006651  pop     rdi
0x180006652  pop     rsi
0x180006653  pop     rbx
0x180006654  retn
```
