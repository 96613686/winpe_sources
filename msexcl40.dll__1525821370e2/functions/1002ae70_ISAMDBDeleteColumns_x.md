# ISAMDBDeleteColumns(x)

- ea: `0x1002ae70`
- end: `0x1002ae9b`
- name: `_ISAMDBDeleteColumns@4`
- size: `43`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10028701`
- `0x1002ab35`

## callees

- `0x10025ab7`
- `0x1002ae70`

## pseudocode

```c
void __thiscall ISAMDBDeleteColumns(_DWORD *this)
{
  _DWORD *v2; // ecx
  _DWORD *v3; // esi

  v2 = (_DWORD *)this[10];
  if ( v2 )
  {
    do
    {
      v3 = (_DWORD *)*v2;
      MemFree(v2);
      v2 = v3;
    }
    while ( v3 );
  }
  this[10] = 0;
  this[9] = 0;
}

```

## disassembly

```asm
0x1002ae70  mov     edi, edi
0x1002ae72  push    edi
0x1002ae73  mov     edi, ecx
0x1002ae75  mov     ecx, [edi+28h]
0x1002ae78  test    ecx, ecx
0x1002ae7a  jz      short loc_1002AE8B
0x1002ae7c  push    esi
0x1002ae7d  mov     esi, [ecx]
0x1002ae7f  call    _MemFree@4; MemFree(x)
0x1002ae84  mov     ecx, esi
0x1002ae86  test    esi, esi
0x1002ae88  jnz     short loc_1002AE7D
0x1002ae8a  pop     esi
0x1002ae8b  mov     dword ptr [edi+28h], 0
0x1002ae92  mov     dword ptr [edi+24h], 0
0x1002ae99  pop     edi
0x1002ae9a  retn
```
