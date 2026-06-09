# LString::Compare(ushort *,uint)

- ea: `0x10062ca3`
- end: `0x10062d36`
- name: `?Compare@LString@@QAE?AW4LCmp@@PAGI@Z`
- size: `147`
- prototype: `int __thiscall(_DWORD, _DWORD, _DWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1001b310`
- `0x10047b50`
- `0x1004f2df`
- `0x1004fc6d`
- `0x1005a127`
- `0x1005ae65`
- `0x1005b336`
- `0x1005c239`
- `0x1005c2fb`
- `0x1007779d`

## callees

- `0x10062ca3`

## import_xrefs

- `mswstr10!__imp__DBCompareStringW@24` at `0x10062d21`
- `mswstr10!__imp__DBCompareStringW@24` at `0x10062d21`

## pseudocode

```c
int __thiscall LString::Compare(_DWORD *this, int a2, unsigned int a3)
{
  int v4; // edi
  int v5; // eax
  unsigned int v6; // esi
  int v7; // ecx
  int v8; // eax
  int v9; // eax

  v4 = this[2];
  v5 = this[3];
  if ( v5 == -1 )
  {
    v5 = 196609;
    this[3] = 196609;
  }
  v6 = v5 + (v4 & 0x80000000);
  v7 = this[1] >> 1;
  v8 = a3 >> 1;
  if ( (v4 & 0xA0000000) == 0 )
  {
    if ( v7 )
    {
      do
      {
        if ( *(_WORD *)(*this + 2 * v7 - 2) != 32 )
          break;
        --v7;
      }
      while ( v7 > 0 );
    }
    if ( v8 )
    {
      do
      {
        if ( *(_WORD *)(a2 + 2 * v8 - 2) != 32 )
          break;
        --v8;
      }
      while ( v8 > 0 );
    }
  }
  v9 = DBCompareStringW(v4 & 0xFFFEFF, v6, *this, v7, a2, v8);
  return v9 != 0 ? v9 - 2 : 0;
}

```

## disassembly

```asm
0x10062ca3  mov     edi, edi
0x10062ca5  push    ebp
0x10062ca6  mov     ebp, esp
0x10062ca8  push    ecx
0x10062ca9  mov     edx, ecx
0x10062cab  push    esi
0x10062cac  push    edi
0x10062cad  mov     edi, [edx+8]
0x10062cb0  mov     esi, edi
0x10062cb2  mov     eax, [edx+0Ch]
0x10062cb5  and     esi, 80000000h
0x10062cbb  cmp     eax, 0FFFFFFFFh
0x10062cbe  jnz     short loc_10062CC8
0x10062cc0  mov     eax, 30001h
0x10062cc5  mov     [edx+0Ch], eax
0x10062cc8  mov     ecx, [edx+4]
0x10062ccb  add     esi, eax
0x10062ccd  mov     eax, [ebp+arg_4]
0x10062cd0  shr     ecx, 1
0x10062cd2  shr     eax, 1
0x10062cd4  mov     [ebp+var_4], esi
0x10062cd7  test    edi, 0A0000000h
0x10062cdd  jnz     short loc_10062D12
0x10062cdf  push    ebx
0x10062ce0  test    ecx, ecx
0x10062ce2  jz      short loc_10062CF8
0x10062ce4  mov     ebx, [edx]
0x10062ce6  push    20h ; ' '
0x10062ce8  pop     esi
0x10062ce9  cmp     [ebx+ecx*2-2], si
0x10062cee  jnz     short loc_10062CF5
0x10062cf0  dec     ecx
0x10062cf1  test    ecx, ecx
0x10062cf3  jg      short loc_10062CE9
0x10062cf5  mov     esi, [ebp+var_4]
0x10062cf8  test    eax, eax
0x10062cfa  jz      short loc_10062D11
0x10062cfc  mov     ebx, [ebp+arg_0]
0x10062cff  push    20h ; ' '
0x10062d01  pop     esi
0x10062d02  cmp     [ebx+eax*2-2], si
0x10062d07  jnz     short loc_10062D0E
0x10062d09  dec     eax
0x10062d0a  test    eax, eax
0x10062d0c  jg      short loc_10062D02
0x10062d0e  mov     esi, [ebp+var_4]
0x10062d11  pop     ebx
0x10062d12  push    eax
0x10062d13  push    [ebp+arg_0]
0x10062d16  and     edi, 0FFFEFFh
0x10062d1c  push    ecx
0x10062d1d  push    dword ptr [edx]
0x10062d1f  push    esi
0x10062d20  push    edi
0x10062d21  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x10062d27  pop     edi
0x10062d28  pop     esi
0x10062d29  lea     ecx, [eax-2]
0x10062d2c  neg     eax
0x10062d2e  sbb     eax, eax
0x10062d30  and     eax, ecx
0x10062d32  leave
0x10062d33  retn    8
```
