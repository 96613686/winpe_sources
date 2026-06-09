# ISAMDBDeleteSession(x,x)

- ea: `0x10014200`
- end: `0x10014262`
- name: `_ISAMDBDeleteSession@8`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10014820`
- `0x10014ea0`

## callees

- `0x1000b200`
- `0x10014200`

## pseudocode

```c
void __stdcall ISAMDBDeleteSession(int a1, _DWORD *a2)
{
  _DWORD *v2; // ebx
  _DWORD *v3; // esi
  _DWORD *v4; // eax
  _DWORD *v5; // edi
  int v6; // eax

  v2 = 0;
  v3 = *(_DWORD **)(a1 + 4);
  if ( v3 )
  {
    while ( v3 != a2 )
    {
      v2 = v3;
      v3 = (_DWORD *)*v3;
      if ( !v3 )
        return;
    }
    v4 = (_DWORD *)v3[2];
    if ( v4 )
    {
      do
      {
        v5 = (_DWORD *)*v4;
        MemFree(v4);
        v4 = v5;
      }
      while ( v5 );
    }
    v6 = *v3;
    if ( v2 )
      *v2 = v6;
    else
      *(_DWORD *)(a1 + 4) = v6;
    MemFree(v3);
  }
}

```

## disassembly

```asm
0x10014200  push    ebx
0x10014201  push    ebp
0x10014202  mov     ebp, [esp+8+arg_0]
0x10014206  xor     ebx, ebx
0x10014208  push    esi
0x10014209  mov     esi, [ebp+4]
0x1001420c  test    esi, esi
0x1001420e  jz      short loc_1001425C
0x10014210  mov     eax, [esp+0Ch+arg_4]
0x10014214  cmp     esi, eax
0x10014216  jz      short loc_10014226
0x10014218  mov     ebx, esi
0x1001421a  mov     esi, [esi]
0x1001421c  test    esi, esi
0x1001421e  jnz     short loc_10014214
0x10014220  pop     esi
0x10014221  pop     ebp
0x10014222  pop     ebx
0x10014223  retn    8
0x10014226  mov     eax, [esi+8]
0x10014229  test    eax, eax
0x1001422b  jz      short loc_1001423F
0x1001422d  push    edi
0x1001422e  mov     edi, edi
0x10014230  mov     edi, [eax]
0x10014232  push    eax
0x10014233  call    _MemFree@4; MemFree(x)
0x10014238  mov     eax, edi
0x1001423a  test    edi, edi
0x1001423c  jnz     short loc_10014230
0x1001423e  pop     edi
0x1001423f  mov     eax, [esi]
0x10014241  test    ebx, ebx
0x10014243  jnz     short loc_10014254
0x10014245  push    esi
0x10014246  mov     [ebp+4], eax
0x10014249  call    _MemFree@4; MemFree(x)
0x1001424e  pop     esi
0x1001424f  pop     ebp
0x10014250  pop     ebx
0x10014251  retn    8
0x10014254  push    esi
0x10014255  mov     [ebx], eax
0x10014257  call    _MemFree@4; MemFree(x)
0x1001425c  pop     esi
0x1001425d  pop     ebp
0x1001425e  pop     ebx
0x1001425f  retn    8
```
