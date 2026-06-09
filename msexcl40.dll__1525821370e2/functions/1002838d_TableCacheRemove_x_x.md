# TableCacheRemove(x,x)

- ea: `0x1002838d`
- end: `0x100283f6`
- name: `_TableCacheRemove@8`
- size: `105`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x10028701`
- `0x10029b60`
- `0x1002e5d0`

## callees

- `0x10025775`
- `0x10025ab7`
- `0x1002838d`

## pseudocode

```c
void __fastcall TableCacheRemove(int a1, int a2)
{
  int v2; // esi
  _DWORD *v3; // ebx
  _DWORD *v4; // edi
  int v5; // eax
  _DWORD *v6; // ecx
  _DWORD *v7; // esi
  int v8; // eax
  int v10; // [esp+10h] [ebp-4h]

  v2 = a1;
  v3 = 0;
  v4 = *(_DWORD **)(a1 + 56);
  if ( v4 )
  {
    v5 = a2 + 104;
    v10 = a2 + 104;
    while ( DBlstrcmpi((int)(v4 + 3), v5) )
    {
      v5 = v10;
      v3 = v4;
      v4 = (_DWORD *)*v4;
      if ( !v4 )
        return;
    }
    v6 = (_DWORD *)v4[1];
    if ( v6 )
    {
      do
      {
        v7 = (_DWORD *)*v6;
        MemFree(v6);
        v6 = v7;
      }
      while ( v7 );
      v2 = a1;
    }
    v8 = *v4;
    if ( v3 )
      *v3 = v8;
    else
      *(_DWORD *)(v2 + 56) = v8;
    MemFree(v4);
  }
}

```

## disassembly

```asm
0x1002838d  mov     edi, edi
0x1002838f  push    ebp
0x10028390  mov     ebp, esp
0x10028392  push    ecx
0x10028393  push    ecx
0x10028394  push    ebx
0x10028395  push    esi
0x10028396  mov     esi, ecx
0x10028398  xor     ebx, ebx
0x1002839a  push    edi
0x1002839b  mov     [ebp+var_8], esi
0x1002839e  mov     edi, [esi+38h]
0x100283a1  test    edi, edi
0x100283a3  jz      short loc_100283F1
0x100283a5  lea     eax, [edx+68h]
0x100283a8  mov     [ebp+var_4], eax
0x100283ab  lea     ecx, [edi+0Ch]
0x100283ae  mov     edx, eax
0x100283b0  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x100283b5  test    eax, eax
0x100283b7  jz      short loc_100283C6
0x100283b9  mov     eax, [ebp+var_4]
0x100283bc  mov     ebx, edi
0x100283be  mov     edi, [edi]
0x100283c0  test    edi, edi
0x100283c2  jnz     short loc_100283AB
0x100283c4  jmp     short loc_100283F1
0x100283c6  mov     ecx, [edi+4]
0x100283c9  test    ecx, ecx
0x100283cb  jz      short loc_100283DD
0x100283cd  mov     esi, [ecx]
0x100283cf  call    _MemFree@4; MemFree(x)
0x100283d4  mov     ecx, esi
0x100283d6  test    esi, esi
0x100283d8  jnz     short loc_100283CD
0x100283da  mov     esi, [ebp+var_8]
0x100283dd  mov     eax, [edi]
0x100283df  test    ebx, ebx
0x100283e1  jnz     short loc_100283E8
0x100283e3  mov     [esi+38h], eax
0x100283e6  jmp     short loc_100283EA
0x100283e8  mov     [ebx], eax
0x100283ea  mov     ecx, edi
0x100283ec  call    _MemFree@4; MemFree(x)
0x100283f1  pop     edi
0x100283f2  pop     esi
0x100283f3  pop     ebx
0x100283f4  leave
0x100283f5  retn
```
