# __updatetlocinfoEx_nolock

- ea: `0x1002e7c6`
- end: `0x1002e811`
- name: `__updatetlocinfoEx_nolock`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1002e746`
- `0x10032330`

## callees

- `0x1002e4b7`
- `0x1002e54c`
- `0x1002e6a6`
- `0x1002e7c6`

## pseudocode

```c
int *__cdecl _updatetlocinfoEx_nolock(int **a1, int *a2)
{
  int *v2; // esi

  if ( !a2 || !a1 )
    return 0;
  v2 = *a1;
  if ( *a1 != a2 )
  {
    *a1 = a2;
    __addlocaleref(a2);
    if ( v2 )
    {
      __removelocaleref(v2);
      if ( !*v2 && v2 != __initiallocinfo )
        __freetlocinfo(v2);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1002e7c6  push    ebp
0x1002e7c7  mov     ebp, esp
0x1002e7c9  push    edi
0x1002e7ca  mov     edi, [ebp+arg_4]
0x1002e7cd  test    edi, edi
0x1002e7cf  jz      short loc_1002E80C
0x1002e7d1  mov     eax, [ebp+arg_0]
0x1002e7d4  test    eax, eax
0x1002e7d6  jz      short loc_1002E80C
0x1002e7d8  push    esi
0x1002e7d9  mov     esi, [eax]
0x1002e7db  cmp     esi, edi
0x1002e7dd  jz      short loc_1002E807
0x1002e7df  push    edi
0x1002e7e0  mov     [eax], edi
0x1002e7e2  call    ___addlocaleref
0x1002e7e7  pop     ecx
0x1002e7e8  test    esi, esi
0x1002e7ea  jz      short loc_1002E807
0x1002e7ec  push    esi
0x1002e7ed  call    ___removelocaleref
0x1002e7f2  cmp     dword ptr [esi], 0
0x1002e7f5  pop     ecx
0x1002e7f6  jnz     short loc_1002E807
0x1002e7f8  cmp     esi, offset ___initiallocinfo
0x1002e7fe  jz      short loc_1002E807
0x1002e800  push    esi; Block
0x1002e801  call    ___freetlocinfo
0x1002e806  pop     ecx
0x1002e807  mov     eax, edi
0x1002e809  pop     esi
0x1002e80a  jmp     short loc_1002E80E
0x1002e80c  xor     eax, eax
0x1002e80e  pop     edi
0x1002e80f  pop     ebp
0x1002e810  retn
```
