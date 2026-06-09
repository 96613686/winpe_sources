# ISAMDBDeleteTable(x,x)

- ea: `0x1002ab35`
- end: `0x1002ab98`
- name: `_ISAMDBDeleteTable@8`
- size: `99`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x10027e33`
- `0x10029068`
- `0x10029730`
- `0x10029b60`
- `0x1002a907`
- `0x1002df60`

## callees

- `0x10025ab7`
- `0x1002ab35`
- `0x1002ac5e`
- `0x1002ae70`

## pseudocode

```c
int __fastcall ISAMDBDeleteTable(int a1, _DWORD *a2)
{
  int v2; // esi
  _DWORD *v3; // ebx
  _DWORD *i; // edi
  _DWORD *v6; // edx
  _DWORD *v7; // esi
  int v8; // eax

  v2 = a1;
  v3 = 0;
  for ( i = *(_DWORD **)(a1 + 48); ; i = (_DWORD *)*i )
  {
    if ( !i )
      return -1310;
    if ( i == a2 )
      break;
    v3 = i;
  }
  ISAMDBDeleteColumns(i);
  v6 = (_DWORD *)i[5];
  if ( v6 )
  {
    do
    {
      v7 = (_DWORD *)*v6;
      ISAMDBDeleteCursor(i, v6);
      v6 = v7;
    }
    while ( v7 );
    v2 = a1;
  }
  v8 = *i;
  if ( v3 )
    *v3 = v8;
  else
    *(_DWORD *)(v2 + 48) = v8;
  MemFree(i);
  return 0;
}

```

## disassembly

```asm
0x1002ab35  mov     edi, edi
0x1002ab37  push    ebp
0x1002ab38  mov     ebp, esp
0x1002ab3a  push    ecx
0x1002ab3b  push    ebx
0x1002ab3c  push    esi
0x1002ab3d  mov     esi, ecx
0x1002ab3f  xor     ebx, ebx
0x1002ab41  push    edi
0x1002ab42  mov     [ebp+var_4], esi
0x1002ab45  mov     edi, [esi+30h]
0x1002ab48  jmp     short loc_1002AB52
0x1002ab4a  cmp     edi, edx
0x1002ab4c  jz      short loc_1002AB60
0x1002ab4e  mov     ebx, edi
0x1002ab50  mov     edi, [edi]
0x1002ab52  test    edi, edi
0x1002ab54  jnz     short loc_1002AB4A
0x1002ab56  mov     eax, 0FFFFFAE2h
0x1002ab5b  pop     edi
0x1002ab5c  pop     esi
0x1002ab5d  pop     ebx
0x1002ab5e  leave
0x1002ab5f  retn
0x1002ab60  mov     ecx, edi
0x1002ab62  call    _ISAMDBDeleteColumns@4; ISAMDBDeleteColumns(x)
0x1002ab67  mov     edx, [edi+14h]
0x1002ab6a  test    edx, edx
0x1002ab6c  jz      short loc_1002AB80
0x1002ab6e  mov     esi, [edx]
0x1002ab70  mov     ecx, edi
0x1002ab72  call    _ISAMDBDeleteCursor@8; ISAMDBDeleteCursor(x,x)
0x1002ab77  mov     edx, esi
0x1002ab79  test    esi, esi
0x1002ab7b  jnz     short loc_1002AB6E
0x1002ab7d  mov     esi, [ebp+var_4]
0x1002ab80  mov     eax, [edi]
0x1002ab82  test    ebx, ebx
0x1002ab84  jnz     short loc_1002AB8B
0x1002ab86  mov     [esi+30h], eax
0x1002ab89  jmp     short loc_1002AB8D
0x1002ab8b  mov     [ebx], eax
0x1002ab8d  mov     ecx, edi
0x1002ab8f  call    _MemFree@4; MemFree(x)
0x1002ab94  xor     eax, eax
0x1002ab96  jmp     short loc_1002AB5B
```
