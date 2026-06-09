# CSettableProperties::SetPropertiesToTemplateRW(void)

- ea: `0x10020c90`
- end: `0x10020d10`
- name: `?SetPropertiesToTemplateRW@CSettableProperties@@QAEJXZ`
- size: `128`
- prototype: `int __thiscall(CSettableProperties *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10018f30`
- `0x1001ebc0`

## callees

- `0x10020c90`

## pseudocode

```c
int __thiscall CSettableProperties::SetPropertiesToTemplateRW(CSettableProperties *this)
{
  int v1; // eax
  int v3; // ecx
  int v4; // ebx
  unsigned int v5; // eax
  int v6; // edi
  unsigned int v7; // esi
  bool v8; // zf
  CSettableProperties *v10; // [esp+Ch] [ebp-Ch]
  int v11; // [esp+10h] [ebp-8h]
  int v12; // [esp+14h] [ebp-4h]

  v1 = 2;
  v3 = 2;
  v10 = this;
  v12 = 2;
  v11 = 2;
  do
  {
    v4 = *((_DWORD *)this + v1);
    v5 = 0;
    if ( *(_DWORD *)(v4 + 8) )
    {
      do
      {
        v6 = *(_DWORD *)(v4 + 16) + 48 * v5;
        v7 = *(_DWORD *)(v6 + 32) | 0x400;
        if ( (*(_DWORD *)(*(_DWORD *)(v6 + 36) + 20) & 0x400) == 0 )
          v7 = *(_DWORD *)(v6 + 32) & 0xFFFFFBFF;
        ++v5;
        *(_DWORD *)(v6 + 32) = v7;
      }
      while ( v5 < *(_DWORD *)(v4 + 8) );
      v3 = v11;
      this = v10;
    }
    v1 = v12 + 1;
    v8 = v3-- == 1;
    ++v12;
    v11 = v3;
  }
  while ( !v8 );
  return 0;
}

```

## disassembly

```asm
0x10020c90  mov     edi, edi
0x10020c92  push    ebp
0x10020c93  mov     ebp, esp
0x10020c95  sub     esp, 0Ch
0x10020c98  mov     eax, 2
0x10020c9d  mov     edx, ecx
0x10020c9f  push    ebx
0x10020ca0  mov     ecx, eax
0x10020ca2  mov     [ebp+var_C], edx
0x10020ca5  push    esi
0x10020ca6  mov     [ebp+var_4], eax
0x10020ca9  mov     [ebp+var_8], ecx
0x10020cac  push    edi
0x10020cad  nop     dword ptr [eax]
0x10020cb0  mov     ebx, [edx+eax*4]
0x10020cb3  xor     eax, eax
0x10020cb5  cmp     [ebx+8], eax
0x10020cb8  jbe     short loc_10020CF8
0x10020cba  nop     word ptr [eax+eax+00h]
0x10020cc0  lea     edi, [eax+eax*2]
0x10020cc3  shl     edi, 4
0x10020cc6  add     edi, [ebx+10h]
0x10020cc9  mov     ecx, [edi+24h]
0x10020ccc  mov     esi, [edi+20h]
0x10020ccf  mov     edx, [ecx+14h]
0x10020cd2  mov     ecx, esi
0x10020cd4  and     ecx, 0FFFFFBFFh
0x10020cda  or      esi, 400h
0x10020ce0  test    edx, 400h
0x10020ce6  cmovz   esi, ecx
0x10020ce9  inc     eax
0x10020cea  mov     [edi+20h], esi
0x10020ced  cmp     eax, [ebx+8]
0x10020cf0  jb      short loc_10020CC0
0x10020cf2  mov     ecx, [ebp+var_8]
0x10020cf5  mov     edx, [ebp+var_C]
0x10020cf8  mov     eax, [ebp+var_4]
0x10020cfb  inc     eax
0x10020cfc  add     ecx, 0FFFFFFFFh
0x10020cff  mov     [ebp+var_4], eax
0x10020d02  mov     [ebp+var_8], ecx
0x10020d05  jnz     short loc_10020CB0
0x10020d07  pop     edi
0x10020d08  pop     esi
0x10020d09  pop     ebx
0x10020d0a  xor     eax, eax
0x10020d0c  mov     esp, ebp
0x10020d0e  pop     ebp
0x10020d0f  retn
```
