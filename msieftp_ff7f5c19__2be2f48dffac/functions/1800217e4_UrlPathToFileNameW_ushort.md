# UrlPathToFileNameW(ushort *)

- ea: `0x1800217e4`
- end: `0x180021881`
- name: `?UrlPathToFileNameW@@YAJPEAG@Z`
- size: `157`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c5dc`
- `0x1800219cc`

## callees

- `0x1800217e4`
- `0x180027040`

## import_xrefs

- `SHLWAPI!PathRemoveBlanksW` at `0x1800217f0`
- `SHLWAPI!PathRemoveBlanksW` at `0x1800217f0`
- `SHLWAPI!__imp_PathIsValidCharW` at `0x180021832`
- `SHLWAPI!__imp_PathIsValidCharW` at `0x180021832`

## pseudocode

```c
__int64 __fastcall UrlPathToFileNameW(unsigned __int16 *a1)
{
  WCHAR v2; // ax
  int v3; // eax
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // rdi

  PathRemoveBlanksW(a1);
  v2 = *a1;
  if ( *a1 )
  {
    if ( v2 == 46 && (!a1[1] || a1[1] == 46 && !a1[2]) )
    {
      *a1 = 45;
      v2 = 45;
    }
    v4 = a1;
    do
    {
      if ( !(unsigned int)PathIsValidCharW(v2, 484) )
        *v4 = 45;
      v2 = *++v4;
    }
    while ( *v4 );
    v5 = a1;
    while ( (unsigned int)PathIsInvalidW(a1) )
    {
      if ( !*v5 )
        goto LABEL_2;
      *v5++ = 45;
    }
    v3 = 1;
  }
  else
  {
LABEL_2:
    v3 = 0;
  }
  return v3 == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800217e4  push    rbx
0x1800217e6  push    rbp
0x1800217e7  push    rsi
0x1800217e8  push    rdi
0x1800217e9  sub     rsp, 28h
0x1800217ed  mov     rbx, rcx
0x1800217f0  call    cs:__imp_PathRemoveBlanksW
0x1800217f6  movzx   eax, word ptr [rbx]
0x1800217f9  xor     esi, esi
0x1800217fb  test    ax, ax
0x1800217fe  jnz     short loc_180021804
0x180021800  mov     eax, esi
0x180021802  jmp     short loc_18002186D
0x180021804  mov     ebp, 2Dh ; '-'
0x180021809  cmp     ax, 2Eh ; '.'
0x18002180d  jnz     short loc_180021827
0x18002180f  cmp     [rbx+2], si
0x180021813  jz      short loc_180021821
0x180021815  cmp     [rbx+2], ax
0x180021819  jnz     short loc_180021827
0x18002181b  cmp     [rbx+4], si
0x18002181f  jnz     short loc_180021827
0x180021821  mov     [rbx], bp
0x180021824  movzx   eax, bp
0x180021827  mov     rdi, rbx
0x18002182a  mov     edx, 1E4h
0x18002182f  movzx   ecx, ax
0x180021832  call    cs:__imp_PathIsValidCharW
0x180021838  test    eax, eax
0x18002183a  jnz     short loc_18002183F
0x18002183c  mov     [rdi], bp
0x18002183f  add     rdi, 2
0x180021843  movzx   eax, word ptr [rdi]
0x180021846  test    ax, ax
0x180021849  jnz     short loc_18002182A
0x18002184b  mov     rdi, rbx
0x18002184e  jmp     short loc_18002185C
0x180021850  cmp     [rdi], si
0x180021853  jz      short loc_180021800
0x180021855  mov     [rdi], bp
0x180021858  add     rdi, 2
0x18002185c  mov     rcx, rbx; unsigned __int16 *
0x18002185f  call    PathIsInvalidW
0x180021864  test    eax, eax
0x180021866  jnz     short loc_180021850
0x180021868  mov     eax, 1
0x18002186d  neg     eax
0x18002186f  sbb     eax, eax
0x180021871  not     eax
0x180021873  and     eax, 80004005h
0x180021878  add     rsp, 28h
0x18002187c  pop     rdi
0x18002187d  pop     rsi
0x18002187e  pop     rbp
0x18002187f  pop     rbx
0x180021880  retn
```
