# CSettableProperties::SetPropertiesReadOnly(void)

- ea: `0x10020c40`
- end: `0x10020c82`
- name: `?SetPropertiesReadOnly@CSettableProperties@@QAEJXZ`
- size: `66`
- prototype: `int __thiscall(CSettableProperties *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x10018f30`
- `0x1001e350`
- `0x10022540`
- `0x10028340`

## callees

- `0x10020c40`

## pseudocode

```c
int __thiscall CSettableProperties::SetPropertiesReadOnly(CSettableProperties *this)
{
  int v1; // esi
  int v3; // edi
  int v4; // edx
  unsigned int i; // eax
  int v6; // ecx

  v1 = 2;
  v3 = 2;
  do
  {
    v4 = *((_DWORD *)this + v1);
    if ( v4 )
    {
      for ( i = 0; i < *(_DWORD *)(v4 + 8); *(_DWORD *)(*(_DWORD *)(v4 + 16) + 16 * v6 + 32) &= ~0x400u )
        v6 = 3 * i++;
    }
    ++v1;
    --v3;
  }
  while ( v3 );
  return 0;
}

```

## disassembly

```asm
0x10020c40  mov     edi, edi
0x10020c42  push    ebx
0x10020c43  push    esi
0x10020c44  mov     esi, 2
0x10020c49  mov     ebx, ecx
0x10020c4b  push    edi
0x10020c4c  mov     edi, esi
0x10020c4e  mov     edi, edi
0x10020c50  mov     edx, [ebx+esi*4]
0x10020c53  test    edx, edx
0x10020c55  jz      short loc_10020C76
0x10020c57  xor     eax, eax
0x10020c59  cmp     [edx+8], eax
0x10020c5c  jbe     short loc_10020C76
0x10020c5e  mov     edi, edi
0x10020c60  lea     ecx, [eax+eax*2]
0x10020c63  inc     eax
0x10020c64  shl     ecx, 4
0x10020c67  add     ecx, [edx+10h]
0x10020c6a  and     dword ptr [ecx+20h], 0FFFFFBFFh
0x10020c71  cmp     eax, [edx+8]
0x10020c74  jb      short loc_10020C60
0x10020c76  inc     esi
0x10020c77  add     edi, 0FFFFFFFFh
0x10020c7a  jnz     short loc_10020C50
0x10020c7c  pop     edi
0x10020c7d  pop     esi
0x10020c7e  pop     ebx
0x10020c7f  xor     eax, eax
0x10020c81  retn
```
