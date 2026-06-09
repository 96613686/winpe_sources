# ReadBufferClear(x)

- ea: `0x10016990`
- end: `0x100169e9`
- name: `_ReadBufferClear@4`
- size: `89`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1000fe70`
- `0x100136b0`
- `0x10013800`
- `0x10015740`

## callees

- `0x1000b200`
- `0x10016990`

## pseudocode

```c
int __stdcall ReadBufferClear(int a1)
{
  _DWORD *i; // esi
  int v2; // eax
  int result; // eax

  for ( i = *(_DWORD **)(a1 + 72); i; i = (_DWORD *)*i )
  {
    v2 = i[2];
    i[4] = 0;
    i[3] = 0;
    if ( v2 == 12 && i[7] || v2 == 9 && i[7] )
    {
      MemFree(i[7]);
      i[7] = 0;
    }
  }
  result = 0;
  *(_DWORD *)(a1 + 80) = 0;
  return result;
}

```

## disassembly

```asm
0x10016990  push    esi
0x10016991  push    edi
0x10016992  mov     edi, [esp+8+arg_0]
0x10016996  mov     esi, [edi+48h]
0x10016999  test    esi, esi
0x1001699b  jz      short loc_100169DF
0x1001699d  lea     ecx, [ecx+0]
0x100169a0  mov     eax, [esi+8]
0x100169a3  mov     dword ptr [esi+10h], 0
0x100169aa  mov     dword ptr [esi+0Ch], 0
0x100169b1  cmp     eax, 0Ch
0x100169b4  jnz     short loc_100169C0
0x100169b6  mov     ecx, [esi+1Ch]
0x100169b9  test    ecx, ecx
0x100169bb  jz      short loc_100169C0
0x100169bd  push    ecx
0x100169be  jmp     short loc_100169CD
0x100169c0  cmp     eax, 9
0x100169c3  jnz     short loc_100169D9
0x100169c5  mov     eax, [esi+1Ch]
0x100169c8  test    eax, eax
0x100169ca  jz      short loc_100169D9
0x100169cc  push    eax
0x100169cd  call    _MemFree@4; MemFree(x)
0x100169d2  mov     dword ptr [esi+1Ch], 0
0x100169d9  mov     esi, [esi]
0x100169db  test    esi, esi
0x100169dd  jnz     short loc_100169A0
0x100169df  xor     eax, eax
0x100169e1  mov     [edi+50h], eax
0x100169e4  pop     edi
0x100169e5  pop     esi
0x100169e6  retn    4
```
