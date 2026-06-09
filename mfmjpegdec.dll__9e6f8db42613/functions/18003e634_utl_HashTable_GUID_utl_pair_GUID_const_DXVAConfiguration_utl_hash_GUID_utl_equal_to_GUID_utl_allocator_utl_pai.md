# utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindFirst<utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindFirstFull,_GUID>(_GUID const &)

- ea: `0x18003e634`
- end: `0x18003e6d5`
- name: `??$_FindFirst@U_FindFirstFull@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@U_GUID@@@?$_HashTable@U_GUID@@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@UDXVAConfiguration@@@utl@@@3@$0A@@utl@@AEBA?AU_FindFirstFull@01@AEBU_GUID@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180040020`
- `0x1800434f0`
- `0x180043e00`
- `0x18004dea0`

## callees

- `0x18003e634`

## pseudocode

```c
_QWORD *__fastcall utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindFirst<utl::_HashTable<_GUID,utl::pair<_GUID const,DXVAConfiguration>,utl::hash<_GUID>,utl::equal_to<_GUID>,utl::allocator<utl::pair<_GUID const,DXVAConfiguration>>,0>::_FindFirstFull,_GUID>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3)
{
  __int64 v3; // r11
  unsigned __int64 v4; // r10
  __int64 v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // r9
  __int64 v8; // rax

  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
  {
    v4 = *a3
       ^ (*((unsigned __int16 *)a3 + 3) | ((unsigned __int64)*((unsigned __int16 *)a3 + 2) << 16))
       ^ (*((unsigned __int8 *)a3 + 15) | ((unsigned __int64)*((unsigned __int8 *)a3 + 10) << 24));
    v5 = 2 * (v4 & ((8LL << *(_BYTE *)(a1 + 32)) - 1));
    v6 = *(_QWORD **)(v3 + 16 * (v4 & ((8LL << *(_BYTE *)(a1 + 32)) - 1)));
    if ( v6 )
    {
      v7 = **(_QWORD ***)(v3 + 8 * v5 + 8);
      while ( v6 != v7 )
      {
        if ( v6[2] >= v4 )
        {
          if ( v6[2] > v4 )
            break;
          v8 = *(_QWORD *)a3 - v6[3];
          if ( *(_QWORD *)a3 == v6[3] )
            v8 = *((_QWORD *)a3 + 1) - v6[4];
          if ( !v8 )
          {
            *a2 = v6;
            a2[1] = v4;
            return a2;
          }
        }
        v6 = (_QWORD *)*v6;
      }
    }
  }
  *a2 = 0;
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x18003e634  mov     r11, [rcx+10h]
0x18003e638  test    r11, r11
0x18003e63b  jz      loc_18003E6C2
0x18003e641  movzx   eax, byte ptr [r8+0Fh]
0x18003e646  mov     cl, [rcx+20h]
0x18003e649  movzx   r10d, byte ptr [r8+0Ah]
0x18003e64e  movzx   r9d, word ptr [r8+4]
0x18003e653  shl     r10, 18h
0x18003e657  or      r10, rax
0x18003e65a  shl     r9, 10h
0x18003e65e  movzx   eax, word ptr [r8+6]
0x18003e663  or      r9, rax
0x18003e666  mov     eax, [r8]
0x18003e669  xor     r10, r9
0x18003e66c  xor     r10, rax
0x18003e66f  mov     eax, 8
0x18003e674  shl     rax, cl
0x18003e677  dec     rax
0x18003e67a  and     rax, r10
0x18003e67d  add     rax, rax
0x18003e680  mov     rcx, [r11+rax*8]
0x18003e684  test    rcx, rcx
0x18003e687  jz      short loc_18003E6C2
0x18003e689  mov     rax, [r11+rax*8+8]
0x18003e68e  mov     r9, [rax]
0x18003e691  cmp     rcx, r9
0x18003e694  jz      short loc_18003E6C2
0x18003e696  cmp     [rcx+10h], r10
0x18003e69a  jb      short loc_18003E6B4
0x18003e69c  ja      short loc_18003E6C2
0x18003e69e  mov     rax, [r8]
0x18003e6a1  sub     rax, [rcx+18h]
0x18003e6a5  jnz     short loc_18003E6AF
0x18003e6a7  mov     rax, [r8+8]
0x18003e6ab  sub     rax, [rcx+20h]
0x18003e6af  test    rax, rax
0x18003e6b2  jz      short loc_18003E6B9
0x18003e6b4  mov     rcx, [rcx]
0x18003e6b7  jmp     short loc_18003E691
0x18003e6b9  mov     [rdx], rcx
0x18003e6bc  mov     [rdx+8], r10
0x18003e6c0  jmp     short loc_18003E6D1
0x18003e6c2  mov     qword ptr [rdx], 0
0x18003e6c9  mov     qword ptr [rdx+8], 0
0x18003e6d1  mov     rax, rdx
0x18003e6d4  retn
```
