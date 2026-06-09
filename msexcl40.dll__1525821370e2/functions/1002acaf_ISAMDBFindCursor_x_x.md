# ISAMDBFindCursor(x,x)

- ea: `0x1002acaf`
- end: `0x1002ad08`
- name: `_ISAMDBFindCursor@8`
- size: `89`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x10029590`
- `0x10029730`
- `0x1002a000`
- `0x1002a3f0`
- `0x1002a420`
- `0x1002a450`
- `0x1002a480`
- `0x1002a4b0`
- `0x1002a500`
- `0x1002a530`
- `0x1002b0c0`
- `0x1002ba40`
- `0x1002cd40`
- `0x1002ce20`
- `0x1002ceb0`
- `0x1002cee0`
- `0x1002d380`
- `0x1002d880`
- `0x1002d8c0`
- `0x1002d910`
- `0x1002d950`
- `0x1002da00`
- `0x1002dac0`
- `0x1002e5d0`
- `0x1002e8f0`
- `0x1002e9f0`

## callees

- `0x1002acaf`

## pseudocode

```c
_DWORD *__fastcall ISAMDBFindCursor(int a1, int a2)
{
  _DWORD *v2; // esi
  _DWORD *i; // eax
  _DWORD *j; // edx
  _DWORD *k; // ecx
  _DWORD *result; // eax

  v2 = (_DWORD *)dword_1003AE68;
LABEL_7:
  if ( v2 )
  {
    for ( i = (_DWORD *)v2[1]; ; i = (_DWORD *)*i )
    {
      if ( !i )
      {
        v2 = (_DWORD *)*v2;
        goto LABEL_7;
      }
      if ( i[3] == a1 )
        break;
    }
    dword_1003AE5C = i[4];
    for ( j = (_DWORD *)v2[2]; j; j = (_DWORD *)*j )
    {
      for ( k = (_DWORD *)j[12]; k; k = (_DWORD *)*k )
      {
        for ( result = (_DWORD *)k[5]; result; result = (_DWORD *)*result )
        {
          if ( result[3] == a2 )
            return result;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1002acaf  mov     edi, edi
0x1002acb1  push    esi
0x1002acb2  mov     esi, dword_1003AE68
0x1002acb8  push    edi
0x1002acb9  mov     edi, edx
0x1002acbb  jmp     short loc_1002ACCF
0x1002acbd  mov     eax, [esi+4]
0x1002acc0  jmp     short loc_1002ACC9
0x1002acc2  cmp     [eax+0Ch], ecx
0x1002acc5  jz      short loc_1002ACD5
0x1002acc7  mov     eax, [eax]
0x1002acc9  test    eax, eax
0x1002accb  jnz     short loc_1002ACC2
0x1002accd  mov     esi, [esi]
0x1002accf  test    esi, esi
0x1002acd1  jnz     short loc_1002ACBD
0x1002acd3  jmp     short loc_1002AD03
0x1002acd5  mov     eax, [eax+10h]
0x1002acd8  mov     dword_1003AE5C, eax
0x1002acdd  mov     edx, [esi+8]
0x1002ace0  jmp     short loc_1002ACFF
0x1002ace2  mov     ecx, [edx+30h]
0x1002ace5  jmp     short loc_1002ACF9
0x1002ace7  mov     eax, [ecx+14h]
0x1002acea  jmp     short loc_1002ACF3
0x1002acec  cmp     [eax+0Ch], edi
0x1002acef  jz      short loc_1002AD05
0x1002acf1  mov     eax, [eax]
0x1002acf3  test    eax, eax
0x1002acf5  jnz     short loc_1002ACEC
0x1002acf7  mov     ecx, [ecx]
0x1002acf9  test    ecx, ecx
0x1002acfb  jnz     short loc_1002ACE7
0x1002acfd  mov     edx, [edx]
0x1002acff  test    edx, edx
0x1002ad01  jnz     short loc_1002ACE2
0x1002ad03  xor     eax, eax
0x1002ad05  pop     edi
0x1002ad06  pop     esi
0x1002ad07  retn
```
