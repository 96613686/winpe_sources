# _LocaleUpdate::_LocaleUpdate(localeinfo_struct *)

- ea: `0x1002b67a`
- end: `0x1002b702`
- name: `??0_LocaleUpdate@@QAE@PAUlocaleinfo_struct@@@Z`
- size: `136`
- prototype: `_LocaleUpdate *__thiscall(_LocaleUpdate *__hidden this, struct localeinfo_struct *)`
- caller_count: `28`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1002b702`
- `0x1002ca0a`
- `0x1002cb69`
- `0x1002d562`
- `0x1002da74`
- `0x1002ddb3`
- `0x1002de05`
- `0x1002de57`
- `0x1002e869`
- `0x1002f856`
- `0x1002fbd0`
- `0x1002fdef`
- `0x100300ac`
- `0x10030197`
- `0x10030c59`
- `0x10031fcc`
- `0x1003207d`
- `0x100322cc`
- `0x10032382`
- `0x10032721`
- `0x100355ce`
- `0x100360c6`
- `0x10036457`
- `0x100364fb`
- `0x10036c5e`
- `0x10036d9d`
- `0x10038076`
- `0x1003a972`

## callees

- `0x1002b67a`
- `0x1002e746`
- `0x1002eac8`
- `0x1002f09b`

## pseudocode

```c
_LocaleUpdate *__thiscall _LocaleUpdate::_LocaleUpdate(_LocaleUpdate *this, struct localeinfo_struct *a2)
{
  _DWORD *v3; // edi
  int *v4; // edx
  int v5; // ecx
  int v6; // eax

  *((_BYTE *)this + 12) = 0;
  if ( a2 )
  {
    *(_DWORD *)this = *(_DWORD *)a2;
    *((_DWORD *)this + 1) = *((_DWORD *)a2 + 1);
  }
  else
  {
    v3 = (_DWORD *)_getptd();
    *((_DWORD *)this + 2) = v3;
    v4 = (int *)v3[27];
    *(_DWORD *)this = v4;
    *((_DWORD *)this + 1) = v3[26];
    if ( v4 != (int *)__ptlocinfo && (__globallocalestatus & v3[28]) == 0 )
      *(_DWORD *)this = __updatetlocinfo();
    if ( *((void **)this + 1) != __ptmbcinfo && (__globallocalestatus & *(_DWORD *)(*((_DWORD *)this + 2) + 112)) == 0 )
      *((_DWORD *)this + 1) = __updatetmbcinfo();
    v5 = *((_DWORD *)this + 2);
    v6 = *(_DWORD *)(v5 + 112);
    if ( (v6 & 2) == 0 )
    {
      *(_DWORD *)(v5 + 112) = v6 | 2;
      *((_BYTE *)this + 12) = 1;
    }
  }
  return this;
}

```

## disassembly

```asm
0x1002b67a  push    ebp
0x1002b67b  mov     ebp, esp
0x1002b67d  push    esi
0x1002b67e  mov     esi, ecx
0x1002b680  mov     ecx, [ebp+arg_0]
0x1002b683  mov     byte ptr [esi+0Ch], 0
0x1002b687  test    ecx, ecx
0x1002b689  jnz     short loc_1002B6F1
0x1002b68b  push    edi
0x1002b68c  call    __getptd
0x1002b691  mov     edi, eax
0x1002b693  mov     [esi+8], edi
0x1002b696  mov     edx, [edi+6Ch]
0x1002b699  mov     [esi], edx
0x1002b69b  mov     ecx, [edi+68h]
0x1002b69e  mov     [esi+4], ecx
0x1002b6a1  cmp     edx, ___ptlocinfo
0x1002b6a7  jz      short loc_1002B6BA
0x1002b6a9  mov     eax, ___globallocalestatus
0x1002b6ae  test    [edi+70h], eax
0x1002b6b1  jnz     short loc_1002B6BA
0x1002b6b3  call    ___updatetlocinfo
0x1002b6b8  mov     [esi], eax
0x1002b6ba  mov     eax, [esi+4]
0x1002b6bd  pop     edi
0x1002b6be  cmp     eax, ___ptmbcinfo
0x1002b6c4  jz      short loc_1002B6DB
0x1002b6c6  mov     ecx, [esi+8]
0x1002b6c9  mov     eax, ___globallocalestatus
0x1002b6ce  test    [ecx+70h], eax
0x1002b6d1  jnz     short loc_1002B6DB
0x1002b6d3  call    ___updatetmbcinfo
0x1002b6d8  mov     [esi+4], eax
0x1002b6db  mov     ecx, [esi+8]
0x1002b6de  mov     eax, [ecx+70h]
0x1002b6e1  test    al, 2
0x1002b6e3  jnz     short loc_1002B6FB
0x1002b6e5  or      eax, 2
0x1002b6e8  mov     [ecx+70h], eax
0x1002b6eb  mov     byte ptr [esi+0Ch], 1
0x1002b6ef  jmp     short loc_1002B6FB
0x1002b6f1  mov     eax, [ecx]
0x1002b6f3  mov     [esi], eax
0x1002b6f5  mov     eax, [ecx+4]
0x1002b6f8  mov     [esi+4], eax
0x1002b6fb  mov     eax, esi
0x1002b6fd  pop     esi
0x1002b6fe  pop     ebp
0x1002b6ff  retn    4
```
