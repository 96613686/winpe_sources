# GetOleErrorFromHRESULT(long)

- ea: `0x18001e3a0`
- end: `0x18001e4b0`
- name: `?GetOleErrorFromHRESULT@@YAJJ@Z`
- size: `272`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180023547`
- `0x18002363d`
- `0x1800238d9`
- `0x18002393b`
- `0x18002399d`
- `0x1800239ff`
- `0x180024841`

## callees

- `0x180010288`
- `0x18001e3a0`

## string_xrefs

- `0x18001e490`: `onecoreuap\base\appmodel\Search\common\include\OleError.h`

## pseudocode

```c
__int64 __fastcall GetOleErrorFromHRESULT(wchar_t *a1)
{
  if ( ((unsigned int)a1 & 0x80070000) != 0x80070000 )
  {
    if ( ((unsigned int)a1 & 0x80030000) == 0x80030000 )
      goto LABEL_5;
    if ( ((unsigned int)a1 & 0xFFF00000) != 0x80000000 )
    {
      if ( (int)a1 < 0 )
        goto LABEL_5;
      if ( ((unsigned int)a1 & 0xFFFFF000) == 0 )
      {
LABEL_23:
        SearchIndexerDebug::Information(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\common\\include\\OleError.h",
          (const wchar_t *)0x41,
          (unsigned int)L"[Exceptions] GetOleError - mapping %08x to E_FAIL\n",
          (const wchar_t *)(unsigned int)a1);
        return 2147500037LL;
      }
    }
    return (unsigned int)a1;
  }
  if ( (_DWORD)a1 == -2147024882 || (unsigned int)((_DWORD)a1 + 2147024891) <= 1 || (_DWORD)a1 == -2147024809 )
    return (unsigned int)a1;
LABEL_5:
  if ( (_DWORD)a1 != -1073741801
    && (_DWORD)a1 != -1073741523
    && (_DWORD)a1 != -1073741670
    && (_DWORD)a1 != -2147023441
    && (_DWORD)a1 != -2147023446
    && (_DWORD)a1 != -2147287036
    && (_DWORD)a1 != -2147287032 )
  {
    switch ( (_DWORD)a1 )
    {
      case 0xC0000022:
        return 2147942405LL;
      case 0xC0000008:
        return 2147942406LL;
      case 0xC000000D:
        return 2147942487LL;
    }
    goto LABEL_23;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001e3a0  sub     rsp, 28h
0x18001e3a4  mov     edx, 80070000h
0x18001e3a9  mov     eax, ecx
0x18001e3ab  mov     r8d, 8007000Eh
0x18001e3b1  and     eax, edx
0x18001e3b3  lea     r9d, [r8+49h]
0x18001e3b7  cmp     eax, edx
0x18001e3b9  jnz     loc_18001E43F
0x18001e3bf  cmp     ecx, r8d
0x18001e3c2  jz      loc_18001E466
0x18001e3c8  lea     eax, [rcx+7FF8FFFBh]
0x18001e3ce  cmp     eax, 1
0x18001e3d1  jbe     loc_18001E466
0x18001e3d7  cmp     ecx, r9d
0x18001e3da  jz      loc_18001E466
0x18001e3e0  cmp     ecx, 0C0000017h
0x18001e3e6  jz      loc_18001E4A8
0x18001e3ec  cmp     ecx, 0C000012Dh
0x18001e3f2  jz      loc_18001E4A8
0x18001e3f8  cmp     ecx, 0C000009Ah
0x18001e3fe  jz      loc_18001E4A8
0x18001e404  cmp     ecx, 800705AFh
0x18001e40a  jz      loc_18001E4A8
0x18001e410  cmp     ecx, 800705AAh
0x18001e416  jz      loc_18001E4A8
0x18001e41c  cmp     ecx, 80030004h
0x18001e422  jz      loc_18001E4A8
0x18001e428  cmp     ecx, 80030008h
0x18001e42e  jz      short loc_18001E4A8
0x18001e430  cmp     ecx, 0C0000022h
0x18001e436  jnz     short loc_18001E46A
0x18001e438  mov     eax, 80070005h
0x18001e43d  jmp     short loc_18001E4AB
0x18001e43f  mov     edx, 80030000h
0x18001e444  mov     eax, ecx
0x18001e446  and     eax, edx
0x18001e448  cmp     eax, edx
0x18001e44a  jz      short loc_18001E3E0
0x18001e44c  mov     eax, ecx
0x18001e44e  and     eax, 0FFF00000h
0x18001e453  cmp     eax, 80000000h
0x18001e458  jz      short loc_18001E466
0x18001e45a  test    ecx, ecx
0x18001e45c  js      short loc_18001E3E0
0x18001e45e  test    ecx, 0FFFFF000h
0x18001e464  jz      short loc_18001E486
0x18001e466  mov     eax, ecx
0x18001e468  jmp     short loc_18001E4AB
0x18001e46a  cmp     ecx, 0C0000008h
0x18001e470  jnz     short loc_18001E479
0x18001e472  mov     eax, 80070006h
0x18001e477  jmp     short loc_18001E4AB
0x18001e479  cmp     ecx, 0C000000Dh
0x18001e47f  jnz     short loc_18001E486
0x18001e481  mov     eax, r9d
0x18001e484  jmp     short loc_18001E4AB
0x18001e486  mov     r9d, ecx; wchar_t *
0x18001e489  lea     r8, aExceptionsGeto; "[Exceptions] GetOleError - mapping %08x"...
0x18001e490  lea     rcx, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18001e497  mov     edx, 41h ; 'A'; wchar_t *
0x18001e49c  call    ?Information@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Information(wchar_t const *,uint,wchar_t const *,...)
0x18001e4a1  mov     eax, 80004005h
0x18001e4a6  jmp     short loc_18001E4AB
0x18001e4a8  mov     eax, r8d
0x18001e4ab  add     rsp, 28h
0x18001e4af  retn
```
