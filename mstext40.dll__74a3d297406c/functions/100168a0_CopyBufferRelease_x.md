# CopyBufferRelease(x)

- ea: `0x100168a0`
- end: `0x100168f0`
- name: `_CopyBufferRelease@4`
- size: `80`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x10012e70`
- `0x100136b0`
- `0x10013800`
- `0x100154f0`
- `0x10015740`
- `0x100158b0`

## callees

- `0x1000b200`
- `0x100168a0`

## pseudocode

```c
int __stdcall CopyBufferRelease(int a1)
{
  _DWORD *v1; // esi
  _DWORD *v2; // edi
  int result; // eax

  v1 = *(_DWORD **)(a1 + 68);
  if ( v1 )
  {
    do
    {
      v2 = (_DWORD *)*v1;
      if ( v1[2] == 12 )
        MemFree(v1[7]);
      if ( v1[2] == 9 )
        MemFree(v1[7]);
      MemFree(v1);
      v1 = v2;
    }
    while ( v2 );
  }
  *(_DWORD *)(a1 + 68) = 0;
  result = 0;
  *(_DWORD *)(a1 + 76) = 0;
  return result;
}

```

## disassembly

```asm
0x100168a0  push    ebx
0x100168a1  mov     ebx, [esp+4+arg_0]
0x100168a5  push    esi
0x100168a6  mov     esi, [ebx+44h]
0x100168a9  test    esi, esi
0x100168ab  jz      short loc_100168DB
0x100168ad  push    edi
0x100168ae  mov     edi, edi
0x100168b0  cmp     dword ptr [esi+8], 0Ch
0x100168b4  mov     edi, [esi]
0x100168b6  jnz     short loc_100168C0
0x100168b8  push    dword ptr [esi+1Ch]
0x100168bb  call    _MemFree@4; MemFree(x)
0x100168c0  cmp     dword ptr [esi+8], 9
0x100168c4  jnz     short loc_100168CE
0x100168c6  push    dword ptr [esi+1Ch]
0x100168c9  call    _MemFree@4; MemFree(x)
0x100168ce  push    esi
0x100168cf  call    _MemFree@4; MemFree(x)
0x100168d4  mov     esi, edi
0x100168d6  test    edi, edi
0x100168d8  jnz     short loc_100168B0
0x100168da  pop     edi
0x100168db  pop     esi
0x100168dc  mov     dword ptr [ebx+44h], 0
0x100168e3  xor     eax, eax
0x100168e5  mov     dword ptr [ebx+4Ch], 0
0x100168ec  pop     ebx
0x100168ed  retn    4
```
