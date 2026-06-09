# FMTDeleteFormat(x)

- ea: `0x1002edd2`
- end: `0x1002ee3d`
- name: `_FMTDeleteFormat@4`
- size: `107`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1001b2f0`
- `0x100200c0`

## callees

- `0x10025ab7`
- `0x1002edd2`

## pseudocode

```c
int __thiscall FMTDeleteFormat(_DWORD *this)
{
  int i; // edi
  _DWORD *v3; // ebx
  _DWORD *v4; // ecx
  _DWORD *v5; // ecx
  _DWORD *v6; // eax

  if ( this )
  {
    for ( i = 0; i < this[1]; ++i )
    {
      v3 = (_DWORD *)this[i + 2];
      if ( v3 )
      {
        if ( *(_BYTE *)v3 == 2 )
        {
          v4 = (_DWORD *)v3[3];
          if ( v4 )
            MemFree(v4);
        }
        MemFree(v3);
      }
    }
    v5 = (_DWORD *)CustomFormatDatabase;
    v6 = 0;
    while ( v5 )
    {
      if ( v5 == this )
      {
        if ( v6 )
          *v6 = *v5;
        else
          CustomFormatDatabase = *v5;
        MemFree(v5);
        return 0;
      }
      v6 = v5;
      v5 = (_DWORD *)*v5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1002edd2  mov     edi, edi
0x1002edd4  push    esi
0x1002edd5  mov     esi, ecx
0x1002edd7  test    esi, esi
0x1002edd9  jz      short loc_1002EE39
0x1002eddb  push    edi
0x1002eddc  xor     edi, edi
0x1002edde  cmp     [esi+4], edi
0x1002ede1  jle     short loc_1002EE0B
0x1002ede3  push    ebx
0x1002ede4  mov     ebx, [esi+edi*4+8]
0x1002ede8  test    ebx, ebx
0x1002edea  jz      short loc_1002EE04
0x1002edec  cmp     byte ptr [ebx], 2
0x1002edef  jnz     short loc_1002EDFD
0x1002edf1  mov     ecx, [ebx+0Ch]
0x1002edf4  test    ecx, ecx
0x1002edf6  jz      short loc_1002EDFD
0x1002edf8  call    _MemFree@4; MemFree(x)
0x1002edfd  mov     ecx, ebx
0x1002edff  call    _MemFree@4; MemFree(x)
0x1002ee04  inc     edi
0x1002ee05  cmp     edi, [esi+4]
0x1002ee08  jl      short loc_1002EDE4
0x1002ee0a  pop     ebx
0x1002ee0b  mov     ecx, _CustomFormatDatabase
0x1002ee11  xor     eax, eax
0x1002ee13  pop     edi
0x1002ee14  jmp     short loc_1002EE20
0x1002ee16  mov     edx, [ecx]
0x1002ee18  cmp     ecx, esi
0x1002ee1a  jz      short loc_1002EE26
0x1002ee1c  mov     eax, ecx
0x1002ee1e  mov     ecx, edx
0x1002ee20  test    ecx, ecx
0x1002ee22  jnz     short loc_1002EE16
0x1002ee24  jmp     short loc_1002EE39
0x1002ee26  test    eax, eax
0x1002ee28  jnz     short loc_1002EE32
0x1002ee2a  mov     _CustomFormatDatabase, edx
0x1002ee30  jmp     short loc_1002EE34
0x1002ee32  mov     [eax], edx
0x1002ee34  call    _MemFree@4; MemFree(x)
0x1002ee39  xor     eax, eax
0x1002ee3b  pop     esi
0x1002ee3c  retn
```
