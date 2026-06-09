# StringCchCatW(x,x,x)

- ea: `0x1000ad60`
- end: `0x1000ae1d`
- name: `_StringCchCatW@12`
- size: `189`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `38`
- callee_count: `1`
- tags: ``

## callers

- `0x1000aa30`
- `0x1000aed0`
- `0x1000bab0`
- `0x1000bfc0`
- `0x1000c370`
- `0x1000cbf0`
- `0x1000d130`
- `0x1000d8d0`
- `0x1000db20`
- `0x1000e3b0`
- `0x1000ed90`
- `0x1000f0e0`
- `0x1000fc70`
- `0x10010020`
- `0x10010450`
- `0x100108e0`
- `0x10010f00`
- `0x100113f0`
- `0x10011870`
- `0x10011d90`
- `0x10012e70`
- `0x100133f0`
- `0x100148d0`
- `0x10018b90`
- `0x10019b40`
- `0x1001b5d0`
- `0x1001c530`
- `0x1001c680`
- `0x1001db00`
- `0x1001eb30`
- `0x1001efc0`
- `0x1001f320`
- `0x1001fbb0`
- `0x10020470`
- `0x10023bb0`
- `0x10024d80`
- `0x10025a80`
- `0x10026500`

## callees

- `0x1000ad60`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx
  size_t v4; // ecx
  STRSAFE_LPWSTR v5; // eax
  size_t v6; // edi
  wchar_t *v7; // ecx
  HRESULT v8; // ebx
  size_t v9; // edx
  int v10; // eax
  char *v11; // edi
  wchar_t v12; // si

  v3 = 0;
  if ( (int)cchDest <= 0 )
    v3 = -2147024809;
  if ( v3 < 0 )
    goto LABEL_8;
  v3 = 0;
  v4 = cchDest;
  v5 = pszDest;
  if ( !cchDest )
    goto LABEL_7;
  while ( *v5 )
  {
    ++v5;
    if ( !--v4 )
      goto LABEL_7;
  }
  if ( !v4 )
  {
LABEL_7:
    v3 = -2147024809;
LABEL_8:
    v6 = 0;
    goto LABEL_9;
  }
  v6 = cchDest - v4;
LABEL_9:
  if ( v3 < 0 )
    return v3;
  v7 = &pszDest[v6];
  v8 = 0;
  v9 = cchDest - v6;
  if ( cchDest == v6 )
    goto LABEL_19;
  v10 = 2147483646;
  v11 = (char *)((char *)pszSrc - (char *)v7);
  while ( v10 )
  {
    v12 = *(wchar_t *)((char *)v7 + (_DWORD)v11);
    if ( !v12 )
      break;
    *v7 = v12;
    --v10;
    ++v7;
    if ( !--v9 )
    {
      *(v7 - 1) = 0;
      return -2147024774;
    }
  }
  if ( !v9 )
  {
LABEL_19:
    --v7;
    v8 = -2147024774;
  }
  *v7 = 0;
  return v8;
}

```

## disassembly

```asm
0x1000ad60  push    ebx
0x1000ad61  push    esi
0x1000ad62  mov     esi, [esp+8+cchDest]
0x1000ad66  xor     edx, edx
0x1000ad68  push    edi
0x1000ad69  test    esi, esi
0x1000ad6b  jz      short loc_1000AD75
0x1000ad6d  cmp     esi, 7FFFFFFFh
0x1000ad73  jbe     short loc_1000AD7A
0x1000ad75  mov     edx, 80070057h
0x1000ad7a  mov     ebx, [esp+0Ch+pszDest]
0x1000ad7e  test    edx, edx
0x1000ad80  js      short loc_1000ADA0
0x1000ad82  xor     edx, edx
0x1000ad84  mov     ecx, esi
0x1000ad86  mov     eax, ebx
0x1000ad88  test    esi, esi
0x1000ad8a  jz      short loc_1000AD9B
0x1000ad8c  lea     esp, [esp+0]
0x1000ad90  cmp     [eax], dx
0x1000ad93  jz      short loc_1000ADF2
0x1000ad95  add     eax, 2
0x1000ad98  dec     ecx
0x1000ad99  jnz     short loc_1000AD90
0x1000ad9b  mov     edx, 80070057h
0x1000ada0  xor     edi, edi
0x1000ada2  test    edx, edx
0x1000ada4  js      short loc_1000AE15
0x1000ada6  mov     edx, esi
0x1000ada8  lea     ecx, [ebx+edi*2]
0x1000adab  mov     ebx, 0
0x1000adb0  sub     edx, edi
0x1000adb2  jz      short loc_1000AE00
0x1000adb4  mov     eax, edx
0x1000adb6  add     edi, 7FFFFFFEh
0x1000adbc  sub     eax, esi
0x1000adbe  add     eax, edi
0x1000adc0  mov     edi, [esp+0Ch+pszSrc]
0x1000adc4  sub     edi, ecx
0x1000adc6  test    eax, eax
0x1000adc8  jz      short loc_1000ADFC
0x1000adca  movzx   esi, word ptr [edi+ecx]
0x1000adce  test    si, si
0x1000add1  jz      short loc_1000ADFC
0x1000add3  mov     [ecx], si
0x1000add6  dec     eax
0x1000add7  add     ecx, 2
0x1000adda  dec     edx
0x1000addb  jnz     short loc_1000ADC6
0x1000addd  sub     ecx, 2
0x1000ade0  mov     ebx, 8007007Ah
0x1000ade5  xor     eax, eax
0x1000ade7  pop     edi
0x1000ade8  pop     esi
0x1000ade9  mov     [ecx], ax
0x1000adec  mov     eax, ebx
0x1000adee  pop     ebx
0x1000adef  retn    0Ch
0x1000adf2  test    ecx, ecx
0x1000adf4  jz      short loc_1000AD9B
0x1000adf6  mov     edi, esi
0x1000adf8  sub     edi, ecx
0x1000adfa  jmp     short loc_1000ADA2
0x1000adfc  test    edx, edx
0x1000adfe  jnz     short loc_1000AE08
0x1000ae00  sub     ecx, 2
0x1000ae03  mov     ebx, 8007007Ah
0x1000ae08  xor     eax, eax
0x1000ae0a  pop     edi
0x1000ae0b  mov     [ecx], ax
0x1000ae0e  mov     eax, ebx
0x1000ae10  pop     esi
0x1000ae11  pop     ebx
0x1000ae12  retn    0Ch
0x1000ae15  pop     edi
0x1000ae16  pop     esi
0x1000ae17  mov     eax, edx
0x1000ae19  pop     ebx
0x1000ae1a  retn    0Ch
```
