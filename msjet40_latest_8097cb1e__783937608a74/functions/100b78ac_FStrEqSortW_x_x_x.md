# FStrEqSortW(x,x,x)

- ea: `0x100b78ac`
- end: `0x100b7988`
- name: `_FStrEqSortW@12`
- size: `220`
- prototype: `int __thiscall(_DWORD, _DWORD)`
- caller_count: `37`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10089cb0`
- `0x10095158`
- `0x10095cf0`
- `0x10097bdd`
- `0x10098590`
- `0x10099e6a`
- `0x1009aa05`
- `0x1009c015`
- `0x1009d6e9`
- `0x1009f0b2`
- `0x100a1089`
- `0x100aa4cf`
- `0x100b1171`
- `0x100b131a`
- `0x100b272a`
- `0x100b6343`
- `0x100b86f6`
- `0x100bc9d2`
- `0x100bd256`
- `0x100bd6ca`
- `0x100bda1a`
- `0x100c68d2`
- `0x100d4d2b`
- `0x100d62b0`
- `0x100d90d4`
- `0x100dd10a`
- `0x100de1d3`
- `0x100deb83`
- `0x100df2e8`
- `0x100dfff4`
- `0x100e06f0`
- `0x100e27de`
- `0x100e39d1`
- `0x100e82a1`
- `0x100f4e46`
- `0x100f618a`
- `0x100ffa12`

## callees

- `0x100b78ac`
- `0x1012406c`

## import_xrefs

- `mswstr10!__imp__DBCompareStringW@24` at `0x100b7967`
- `mswstr10!__imp__DBCompareStringW@24` at `0x100b7967`

## pseudocode

```c
char __fastcall FStrEqSortW(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  unsigned int v3; // edi
  unsigned int v4; // esi
  unsigned int v5; // ebx
  unsigned int v6; // eax
  int v7; // eax
  int v8; // ecx
  bool v9; // zf

  v3 = wcslen(a1);
  v4 = wcslen(a2);
  v5 = lcidGlobal & 0x80000000;
  if ( lcidGlobal >= 0 )
  {
    if ( v3 )
    {
      do
      {
        if ( a1[v3 - 1] != 32 )
          break;
        --v3;
      }
      while ( v3 );
      v5 = lcidGlobal & 0x80000000;
    }
    for ( ; v4; --v4 )
    {
      if ( a2[v4 - 1] != 32 )
        break;
    }
  }
  if ( (lcidGlobal & 0xFFFEFF) != 0 )
  {
    v8 = DBCompareStringW(lcidGlobal & 0xFFFEFF, v5 + 196609, a1, v3, a2, v4);
    if ( v8 )
    {
      v9 = v8 == 2;
LABEL_19:
      LOBYTE(v7) = v9;
      return v7;
    }
LABEL_18:
    v9 = v8 == 0;
    goto LABEL_19;
  }
  v6 = v4;
  if ( v3 <= v4 )
    v6 = v3;
  v7 = memcmp(a1, a2, 2 * v6);
  v8 = v7;
  if ( v7 || v3 == v4 || v5 )
    goto LABEL_18;
  return v7;
}

```

## disassembly

```asm
0x100b78ac  mov     edi, edi
0x100b78ae  push    ebp
0x100b78af  mov     ebp, esp
0x100b78b1  push    ecx
0x100b78b2  push    ecx
0x100b78b3  push    ebx
0x100b78b4  push    esi
0x100b78b5  mov     eax, ecx
0x100b78b7  xor     ebx, ebx
0x100b78b9  mov     ecx, _lcidGlobal
0x100b78bf  push    edi
0x100b78c0  mov     edi, eax
0x100b78c2  mov     [ebp+Buf1], eax
0x100b78c5  mov     [ebp+var_8], ebx
0x100b78c8  lea     esi, [edi+2]
0x100b78cb  mov     ax, [edi]
0x100b78ce  add     edi, 2
0x100b78d1  cmp     ax, bx
0x100b78d4  jnz     short loc_100B78CB
0x100b78d6  sub     edi, esi
0x100b78d8  mov     esi, edx
0x100b78da  sar     edi, 1
0x100b78dc  lea     ebx, [esi+2]
0x100b78df  mov     ax, [esi]
0x100b78e2  add     esi, 2
0x100b78e5  cmp     ax, word ptr [ebp+var_8]
0x100b78e9  jnz     short loc_100B78DF
0x100b78eb  sub     esi, ebx
0x100b78ed  mov     ebx, ecx
0x100b78ef  sar     esi, 1
0x100b78f1  and     ebx, 80000000h
0x100b78f7  mov     [ebp+var_8], ebx
0x100b78fa  jnz     short loc_100B792B
0x100b78fc  push    20h ; ' '
0x100b78fe  pop     eax
0x100b78ff  test    edi, edi
0x100b7901  jz      short loc_100B791B
0x100b7903  mov     eax, [ebp+Buf1]
0x100b7906  push    20h ; ' '
0x100b7908  pop     ebx
0x100b7909  cmp     [eax+edi*2-2], bx
0x100b790e  jnz     short loc_100B7915
0x100b7910  sub     edi, 1
0x100b7913  jnz     short loc_100B7909
0x100b7915  mov     ebx, [ebp+var_8]
0x100b7918  push    20h ; ' '
0x100b791a  pop     eax
0x100b791b  test    esi, esi
0x100b791d  jz      short loc_100B792B
0x100b791f  cmp     [edx+esi*2-2], ax
0x100b7924  jnz     short loc_100B792B
0x100b7926  sub     esi, 1
0x100b7929  jnz     short loc_100B791F
0x100b792b  and     ecx, 0FFFEFFh
0x100b7931  jnz     short loc_100B7959
0x100b7933  cmp     edi, esi
0x100b7935  mov     eax, esi
0x100b7937  cmovbe  eax, edi
0x100b793a  add     eax, eax
0x100b793c  push    eax; Size
0x100b793d  push    edx; Buf2
0x100b793e  push    [ebp+Buf1]; Buf1
0x100b7941  call    _memcmp
0x100b7946  mov     ecx, eax
0x100b7948  add     esp, 0Ch
0x100b794b  test    ecx, ecx
0x100b794d  jnz     short loc_100B797A
0x100b794f  cmp     edi, esi
0x100b7951  jz      short loc_100B797A
0x100b7953  test    ebx, ebx
0x100b7955  jnz     short loc_100B797A
0x100b7957  jmp     short loc_100B7981
0x100b7959  push    esi
0x100b795a  push    edx
0x100b795b  push    edi
0x100b795c  push    [ebp+Buf1]
0x100b795f  lea     eax, [ebx+30001h]
0x100b7965  push    eax
0x100b7966  push    ecx
0x100b7967  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x100b796d  mov     ecx, eax
0x100b796f  test    ecx, ecx
0x100b7971  jz      short loc_100B797A
0x100b7973  xor     eax, eax
0x100b7975  cmp     ecx, 2
0x100b7978  jmp     short loc_100B797E
0x100b797a  xor     eax, eax
0x100b797c  test    ecx, ecx
0x100b797e  setz    al
0x100b7981  pop     edi
0x100b7982  pop     esi
0x100b7983  pop     ebx
0x100b7984  leave
0x100b7985  retn    4
```
