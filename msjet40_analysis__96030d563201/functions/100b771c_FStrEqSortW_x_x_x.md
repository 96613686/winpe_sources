# FStrEqSortW(x,x,x)

- ea: `0x100b771c`
- end: `0x100b77f8`
- name: `_FStrEqSortW@12`
- size: `220`
- prototype: ``
- caller_count: `37`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10089b20`
- `0x10094fc8`
- `0x10095b60`
- `0x10097a4d`
- `0x10098400`
- `0x10099cda`
- `0x1009a875`
- `0x1009be85`
- `0x1009d559`
- `0x1009ef22`
- `0x100a0ef9`
- `0x100aa33f`
- `0x100b0fe2`
- `0x100b118b`
- `0x100b259b`
- `0x100b61b3`
- `0x100b8566`
- `0x100bc842`
- `0x100bd0c6`
- `0x100bd53a`
- `0x100bd88a`
- `0x100c6742`
- `0x100d4b9b`
- `0x100d6120`
- `0x100d8f44`
- `0x100dcf7a`
- `0x100de043`
- `0x100de9f3`
- `0x100df158`
- `0x100dfe64`
- `0x100e0560`
- `0x100e264e`
- `0x100e3841`
- `0x100e8111`
- `0x100f4cb6`
- `0x100f5ffa`
- `0x100ff872`

## callees

- `0x100b771c`
- `0x10123ebc`

## import_xrefs

- `mswstr10!__imp__DBCompareStringW@24` at `0x100b77d7`
- `mswstr10!__imp__DBCompareStringW@24` at `0x100b77d7`

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
0x100b771c  mov     edi, edi
0x100b771e  push    ebp
0x100b771f  mov     ebp, esp
0x100b7721  push    ecx
0x100b7722  push    ecx
0x100b7723  push    ebx
0x100b7724  push    esi
0x100b7725  mov     eax, ecx
0x100b7727  xor     ebx, ebx
0x100b7729  mov     ecx, _lcidGlobal
0x100b772f  push    edi
0x100b7730  mov     edi, eax
0x100b7732  mov     [ebp+Buf1], eax
0x100b7735  mov     [ebp+var_8], ebx
0x100b7738  lea     esi, [edi+2]
0x100b773b  mov     ax, [edi]
0x100b773e  add     edi, 2
0x100b7741  cmp     ax, bx
0x100b7744  jnz     short loc_100B773B
0x100b7746  sub     edi, esi
0x100b7748  mov     esi, edx
0x100b774a  sar     edi, 1
0x100b774c  lea     ebx, [esi+2]
0x100b774f  mov     ax, [esi]
0x100b7752  add     esi, 2
0x100b7755  cmp     ax, word ptr [ebp+var_8]
0x100b7759  jnz     short loc_100B774F
0x100b775b  sub     esi, ebx
0x100b775d  mov     ebx, ecx
0x100b775f  sar     esi, 1
0x100b7761  and     ebx, 80000000h
0x100b7767  mov     [ebp+var_8], ebx
0x100b776a  jnz     short loc_100B779B
0x100b776c  push    20h ; ' '
0x100b776e  pop     eax
0x100b776f  test    edi, edi
0x100b7771  jz      short loc_100B778B
0x100b7773  mov     eax, [ebp+Buf1]
0x100b7776  push    20h ; ' '
0x100b7778  pop     ebx
0x100b7779  cmp     [eax+edi*2-2], bx
0x100b777e  jnz     short loc_100B7785
0x100b7780  sub     edi, 1
0x100b7783  jnz     short loc_100B7779
0x100b7785  mov     ebx, [ebp+var_8]
0x100b7788  push    20h ; ' '
0x100b778a  pop     eax
0x100b778b  test    esi, esi
0x100b778d  jz      short loc_100B779B
0x100b778f  cmp     [edx+esi*2-2], ax
0x100b7794  jnz     short loc_100B779B
0x100b7796  sub     esi, 1
0x100b7799  jnz     short loc_100B778F
0x100b779b  and     ecx, 0FFFEFFh
0x100b77a1  jnz     short loc_100B77C9
0x100b77a3  cmp     edi, esi
0x100b77a5  mov     eax, esi
0x100b77a7  cmovbe  eax, edi
0x100b77aa  add     eax, eax
0x100b77ac  push    eax; Size
0x100b77ad  push    edx; Buf2
0x100b77ae  push    [ebp+Buf1]; Buf1
0x100b77b1  call    _memcmp
0x100b77b6  mov     ecx, eax
0x100b77b8  add     esp, 0Ch
0x100b77bb  test    ecx, ecx
0x100b77bd  jnz     short loc_100B77EA
0x100b77bf  cmp     edi, esi
0x100b77c1  jz      short loc_100B77EA
0x100b77c3  test    ebx, ebx
0x100b77c5  jnz     short loc_100B77EA
0x100b77c7  jmp     short loc_100B77F1
0x100b77c9  push    esi
0x100b77ca  push    edx
0x100b77cb  push    edi
0x100b77cc  push    [ebp+Buf1]
0x100b77cf  lea     eax, [ebx+30001h]
0x100b77d5  push    eax
0x100b77d6  push    ecx
0x100b77d7  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x100b77dd  mov     ecx, eax
0x100b77df  test    ecx, ecx
0x100b77e1  jz      short loc_100B77EA
0x100b77e3  xor     eax, eax
0x100b77e5  cmp     ecx, 2
0x100b77e8  jmp     short loc_100B77EE
0x100b77ea  xor     eax, eax
0x100b77ec  test    ecx, ecx
0x100b77ee  setz    al
0x100b77f1  pop     edi
0x100b77f2  pop     esi
0x100b77f3  pop     ebx
0x100b77f4  leave
0x100b77f5  retn    4
```
