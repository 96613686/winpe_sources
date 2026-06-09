# ISAMDBDeleteCursor(x,x)

- ea: `0x1002ac5e`
- end: `0x1002aca9`
- name: `_ISAMDBDeleteCursor@8`
- size: `75`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x10029068`
- `0x10029730`
- `0x10029b60`
- `0x1002ab35`

## callees

- `0x10025ab7`
- `0x1002ac5e`

## pseudocode

```c
int __fastcall ISAMDBDeleteCursor(int a1, _DWORD *a2)
{
  _DWORD *v2; // edi
  _DWORD *v3; // esi
  int v4; // eax
  _DWORD *v6; // ecx
  _DWORD *v7; // esi

  v2 = *(_DWORD **)(a1 + 20);
  v3 = 0;
  while ( 1 )
  {
    if ( !v2 )
      return -1310;
    v4 = *v2;
    if ( v2 == a2 )
      break;
    v3 = v2;
    v2 = (_DWORD *)*v2;
  }
  if ( v3 )
    *v3 = v4;
  else
    *(_DWORD *)(a1 + 20) = v4;
  v6 = (_DWORD *)a2[13];
  if ( v6 )
  {
    do
    {
      v7 = (_DWORD *)*v6;
      MemFree(v6);
      v6 = v7;
    }
    while ( v7 );
  }
  MemFree(v2);
  return 0;
}

```

## disassembly

```asm
0x1002ac5e  mov     edi, edi
0x1002ac60  push    esi
0x1002ac61  push    edi
0x1002ac62  mov     edi, [ecx+14h]
0x1002ac65  xor     esi, esi
0x1002ac67  jmp     short loc_1002AC73
0x1002ac69  mov     eax, [edi]
0x1002ac6b  cmp     edi, edx
0x1002ac6d  jz      short loc_1002AC7F
0x1002ac6f  mov     esi, edi
0x1002ac71  mov     edi, eax
0x1002ac73  test    edi, edi
0x1002ac75  jnz     short loc_1002AC69
0x1002ac77  mov     eax, 0FFFFFAE2h
0x1002ac7c  pop     edi
0x1002ac7d  pop     esi
0x1002ac7e  retn
0x1002ac7f  test    esi, esi
0x1002ac81  jnz     short loc_1002AC88
0x1002ac83  mov     [ecx+14h], eax
0x1002ac86  jmp     short loc_1002AC8A
0x1002ac88  mov     [esi], eax
0x1002ac8a  mov     ecx, [edx+34h]
0x1002ac8d  test    ecx, ecx
0x1002ac8f  jz      short loc_1002AC9E
0x1002ac91  mov     esi, [ecx]
0x1002ac93  call    _MemFree@4; MemFree(x)
0x1002ac98  mov     ecx, esi
0x1002ac9a  test    esi, esi
0x1002ac9c  jnz     short loc_1002AC91
0x1002ac9e  mov     ecx, edi
0x1002aca0  call    _MemFree@4; MemFree(x)
0x1002aca5  xor     eax, eax
0x1002aca7  jmp     short loc_1002AC7C
```
