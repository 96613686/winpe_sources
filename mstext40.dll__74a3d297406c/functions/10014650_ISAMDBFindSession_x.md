# ISAMDBFindSession(x)

- ea: `0x10014650`
- end: `0x1001468c`
- name: `_ISAMDBFindSession@4`
- size: `60`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1000fee0`
- `0x10011d90`
- `0x10014820`
- `0x10014ea0`
- `0x10016d90`
- `0x100170e0`
- `0x10017670`
- `0x100178b0`
- `0x10017ea0`
- `0x10018160`
- `0x10018200`
- `0x100186d0`
- `0x10018850`
- `0x10018950`

## callees

- `0x1000a3d0`
- `0x10014650`

## pseudocode

```c
_DWORD *__stdcall ISAMDBFindSession(int a1)
{
  _DWORD *v1; // eax
  _DWORD *v2; // esi

  v1 = (_DWORD *)dword_10040FBC;
  if ( !dword_10040FBC )
    return 0;
  while ( 1 )
  {
    v2 = (_DWORD *)v1[1];
    if ( v2 )
      break;
LABEL_5:
    v1 = (_DWORD *)*v1;
    if ( !v1 )
      return 0;
  }
  while ( v2[3] != a1 )
  {
    v2 = (_DWORD *)*v2;
    if ( !v2 )
      goto LABEL_5;
  }
  ErrorSetSession(v2[4]);
  return v2;
}

```

## disassembly

```asm
0x10014650  mov     eax, dword_10040FBC
0x10014655  push    esi
0x10014656  test    eax, eax
0x10014658  jz      short loc_10014678
0x1001465a  mov     ecx, [esp+4+arg_0]
0x1001465e  mov     edi, edi
0x10014660  mov     esi, [eax+4]
0x10014663  test    esi, esi
0x10014665  jz      short loc_10014672
0x10014667  cmp     [esi+0Ch], ecx
0x1001466a  jz      short loc_1001467E
0x1001466c  mov     esi, [esi]
0x1001466e  test    esi, esi
0x10014670  jnz     short loc_10014667
0x10014672  mov     eax, [eax]
0x10014674  test    eax, eax
0x10014676  jnz     short loc_10014660
0x10014678  xor     eax, eax
0x1001467a  pop     esi
0x1001467b  retn    4
0x1001467e  push    dword ptr [esi+10h]
0x10014681  call    _ErrorSetSession@4; ErrorSetSession(x)
0x10014686  mov     eax, esi
0x10014688  pop     esi
0x10014689  retn    4
```
