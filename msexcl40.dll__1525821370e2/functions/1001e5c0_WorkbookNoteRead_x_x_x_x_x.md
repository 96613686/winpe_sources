# WorkbookNoteRead(x,x,x,x,x)

- ea: `0x1001e5c0`
- end: `0x1001e665`
- name: `_WorkbookNoteRead@20`
- size: `165`
- prototype: `int __fastcall(int, wchar_t *, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10027e33`

## callees

- `0x10012270`
- `0x1001c2b0`
- `0x1001e5c0`
- `0x10025ab7`
- `0x10036678`

## pseudocode

```c
int __fastcall WorkbookNoteRead(int a1, wchar_t *a2, int a3, int a4, int a5)
{
  int *v7; // ecx
  int v8; // eax
  wchar_t *v9; // esi
  signed int v10; // ecx

  if ( *(_DWORD *)(a1 + 12) )
    return TranslateEXErrorToJETError(-30);
  v7 = *(int **)(a1 + 8);
  dword_1003ABE8 = a3;
  dword_1003ABEC = 0;
  v8 = ExcelScanFile(v7, dword_10038660, 0);
  if ( v8 < 0 )
    return TranslateEXErrorToJETError(v8);
  if ( !v8 )
    return -1305;
  v9 = dword_1003ABEC;
  if ( !dword_1003ABEC )
    return -1305;
  v10 = wcslen(dword_1003ABEC) + 1;
  if ( a2 )
  {
    if ( v10 > 600 )
      v10 = 600;
    wcsncpy(a2, dword_1003ABEC, v10);
  }
  MemFree(v9);
  return 0;
}

```

## disassembly

```asm
0x1001e5c0  mov     edi, edi
0x1001e5c2  push    ebp
0x1001e5c3  mov     ebp, esp
0x1001e5c5  cmp     dword ptr [ecx+0Ch], 0
0x1001e5c9  push    esi
0x1001e5ca  push    edi
0x1001e5cb  mov     edi, edx
0x1001e5cd  jz      short loc_1001E5DF
0x1001e5cf  mov     ecx, 0FFFFFFE2h
0x1001e5d4  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001e5d9  pop     edi
0x1001e5da  pop     esi
0x1001e5db  pop     ebp
0x1001e5dc  retn    0Ch
0x1001e5df  mov     eax, [ebp+arg_0]
0x1001e5e2  mov     edx, offset dword_10038660
0x1001e5e7  mov     ecx, [ecx+8]
0x1001e5ea  push    0
0x1001e5ec  mov     dword_1003ABE8, eax
0x1001e5f1  mov     dword_1003ABEC, 0
0x1001e5fb  call    _ExcelScanFile@12; ExcelScanFile(x,x,x)
0x1001e600  test    eax, eax
0x1001e602  jns     short loc_1001E611
0x1001e604  mov     ecx, eax
0x1001e606  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001e60b  pop     edi
0x1001e60c  pop     esi
0x1001e60d  pop     ebp
0x1001e60e  retn    0Ch
0x1001e611  jz      short loc_1001E65A
0x1001e613  mov     esi, dword_1003ABEC
0x1001e619  test    esi, esi
0x1001e61b  jz      short loc_1001E65A
0x1001e61d  mov     ecx, esi
0x1001e61f  lea     edx, [ecx+2]
0x1001e622  mov     ax, [ecx]
0x1001e625  add     ecx, 2
0x1001e628  test    ax, ax
0x1001e62b  jnz     short loc_1001E622
0x1001e62d  sub     ecx, edx
0x1001e62f  sar     ecx, 1
0x1001e631  inc     ecx
0x1001e632  test    edi, edi
0x1001e634  jz      short loc_1001E64B
0x1001e636  mov     eax, 258h
0x1001e63b  cmp     ecx, eax
0x1001e63d  cmovg   ecx, eax
0x1001e640  push    ecx; Count
0x1001e641  push    esi; Source
0x1001e642  push    edi; Destination
0x1001e643  call    _wcsncpy
0x1001e648  add     esp, 0Ch
0x1001e64b  mov     ecx, esi
0x1001e64d  call    _MemFree@4; MemFree(x)
0x1001e652  xor     eax, eax
0x1001e654  pop     edi
0x1001e655  pop     esi
0x1001e656  pop     ebp
0x1001e657  retn    0Ch
0x1001e65a  pop     edi
0x1001e65b  mov     eax, 0FFFFFAE7h
0x1001e660  pop     esi
0x1001e661  pop     ebp
0x1001e662  retn    0Ch
```
