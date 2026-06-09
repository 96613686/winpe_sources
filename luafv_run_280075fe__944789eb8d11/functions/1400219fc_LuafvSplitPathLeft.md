# LuafvSplitPathLeft

- ea: `0x1400219fc`
- end: `0x140021a5c`
- name: `LuafvSplitPathLeft`
- size: `96`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a3c8`
- `0x14002199c`
- `0x140022784`
- `0x14002814c`

## callees

- `0x1400219fc`

## pseudocode

```c
char __fastcall LuafvSplitPathLeft(unsigned __int16 *a1, __int64 a2)
{
  __int16 v2; // r11
  __int64 v3; // r8
  __int64 *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  char result; // al

  v2 = *a1;
  v3 = *a1 >> 1;
  if ( !(_DWORD)v3 )
    return 0;
  v4 = (__int64 *)(a1 + 4);
  do
  {
    if ( !(_DWORD)v3 )
      break;
    v4 = (__int64 *)(a1 + 4);
    v3 = (unsigned int)(v3 - 1);
  }
  while ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v3) != 92 );
  v5 = *v4;
  *a1 = 2 * v3;
  *(_WORD *)a2 += v2 - 2 * v3;
  v6 = v5 + 2 * v3;
  *(_WORD *)(a2 + 2) = *(_WORD *)a2;
  result = 1;
  *(_QWORD *)(a2 + 8) = v6;
  return result;
}

```

## disassembly

```asm
0x1400219fc  mov     [rsp+arg_0], rbx
0x140021a01  movzx   r11d, word ptr [rcx]
0x140021a05  mov     rbx, rdx
0x140021a08  mov     r8d, r11d
0x140021a0b  shr     r8d, 1
0x140021a0e  jz      short loc_140021A58
0x140021a10  lea     r9, [rcx+8]
0x140021a14  test    r8d, r8d
0x140021a17  jz      short loc_140021A2B
0x140021a19  lea     r9, [rcx+8]
0x140021a1d  dec     r8d
0x140021a20  mov     rax, [r9]
0x140021a23  cmp     word ptr [rax+r8*2], 5Ch ; '\'
0x140021a29  jnz     short loc_140021A14
0x140021a2b  mov     rax, [r9]
0x140021a2e  movzx   edx, r8w
0x140021a32  add     dx, dx
0x140021a35  mov     [rcx], dx
0x140021a38  sub     r11w, dx
0x140021a3c  add     [rbx], r11w
0x140021a40  lea     rcx, [rax+r8*2]
0x140021a44  movzx   eax, word ptr [rbx]
0x140021a47  mov     [rbx+2], ax
0x140021a4b  mov     al, 1
0x140021a4d  mov     [rbx+8], rcx
0x140021a51  mov     rbx, [rsp+arg_0]
0x140021a56  retn
0x140021a58  xor     al, al
0x140021a5a  jmp     short loc_140021A51
```
