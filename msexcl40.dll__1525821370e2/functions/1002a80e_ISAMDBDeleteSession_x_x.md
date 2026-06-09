# ISAMDBDeleteSession(x,x)

- ea: `0x1002a80e`
- end: `0x1002a863`
- name: `_ISAMDBDeleteSession@8`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10006a60`

## callees

- `0x10025ab7`
- `0x1002a80e`

## pseudocode

```c
void __fastcall ISAMDBDeleteSession(int a1, _DWORD *a2)
{
  int v3; // edx
  _DWORD *v4; // ebx
  _DWORD *i; // edi
  _DWORD *v6; // ecx
  _DWORD *v7; // esi
  _DWORD *v8; // eax

  v3 = a1;
  v4 = 0;
  for ( i = *(_DWORD **)(a1 + 4); i; i = (_DWORD *)*i )
  {
    if ( i == a2 )
    {
      v6 = (_DWORD *)i[2];
      if ( v6 )
      {
        do
        {
          v7 = (_DWORD *)*v6;
          MemFree(v6);
          v6 = v7;
        }
        while ( v7 );
        v3 = a1;
      }
      v8 = (_DWORD *)*i;
      if ( v4 )
        *v4 = v8;
      else
        *(_DWORD *)(v3 + 4) = v8;
      MemFree(i);
      return;
    }
    v4 = i;
  }
}

```

## disassembly

```asm
0x1002a80e  mov     edi, edi
0x1002a810  push    ebp
0x1002a811  mov     ebp, esp
0x1002a813  push    ecx
0x1002a814  mov     eax, edx
0x1002a816  mov     edx, ecx
0x1002a818  push    ebx
0x1002a819  push    edi
0x1002a81a  mov     [ebp+var_4], edx
0x1002a81d  xor     ebx, ebx
0x1002a81f  mov     edi, [edx+4]
0x1002a822  jmp     short loc_1002A82C
0x1002a824  cmp     edi, eax
0x1002a826  jz      short loc_1002A832
0x1002a828  mov     ebx, edi
0x1002a82a  mov     edi, [edi]
0x1002a82c  test    edi, edi
0x1002a82e  jnz     short loc_1002A824
0x1002a830  jmp     short loc_1002A85F
0x1002a832  mov     ecx, [edi+8]
0x1002a835  test    ecx, ecx
0x1002a837  jz      short loc_1002A84B
0x1002a839  push    esi
0x1002a83a  mov     esi, [ecx]
0x1002a83c  call    _MemFree@4; MemFree(x)
0x1002a841  mov     ecx, esi
0x1002a843  test    esi, esi
0x1002a845  jnz     short loc_1002A83A
0x1002a847  mov     edx, [ebp+var_4]
0x1002a84a  pop     esi
0x1002a84b  mov     eax, [edi]
0x1002a84d  test    ebx, ebx
0x1002a84f  jnz     short loc_1002A856
0x1002a851  mov     [edx+4], eax
0x1002a854  jmp     short loc_1002A858
0x1002a856  mov     [ebx], eax
0x1002a858  mov     ecx, edi
0x1002a85a  call    _MemFree@4; MemFree(x)
0x1002a85f  pop     edi
0x1002a860  pop     ebx
0x1002a861  leave
0x1002a862  retn
```
