# WorkbookCellRead(x,x,x,x,x)

- ea: `0x1001bc80`
- end: `0x1001bd42`
- name: `_WorkbookCellRead@20`
- size: `194`
- prototype: `int __fastcall(int *, DispatchDriver *, unsigned int, int, char)`
- caller_count: `7`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x10028701`
- `0x1002cc39`
- `0x1002e5d0`
- `0x10032387`
- `0x10032468`
- `0x1003257a`
- `0x10032602`

## callees

- `0x10013490`
- `0x1001bc80`
- `0x1001c2b0`
- `0x10020780`
- `0x10025ab7`

## pseudocode

```c
int __fastcall WorkbookCellRead(int *a1, DispatchDriver *a2, unsigned int a3, int a4, char a5)
{
  int Cell; // eax
  int result; // eax
  int v8; // ecx
  int v9; // [esp+8h] [ebp-4h]
  int savedregs; // [esp+Ch] [ebp+0h] BYREF

  if ( a1[3] )
  {
    Cell = XLOLECellRead(a2, (int)a1, (int)&savedregs, a3, (__int16 *)a4, a5);
    if ( Cell != 2 )
      return TranslateEXErrorToJETError(Cell);
    return 1;
  }
  LOWORD(v9) = a3 + *(_WORD *)a2;
  HIWORD(v9) = HIWORD(a3) + *((_WORD *)a2 + 1);
  Cell = ExcelReadCell(a1[2], (__int16 *)a4, v9);
  if ( Cell < 0 )
    return TranslateEXErrorToJETError(Cell);
  if ( Cell == 2 )
    return 1;
  if ( (*(_WORD *)a4 & 0x100) != 0 )
    MemFree(*(_DWORD **)(a4 + 40));
  v8 = 0;
  result = *(_DWORD *)(a1[201] + 72);
  if ( result )
  {
    while ( v8 != *(_DWORD *)(a4 + 4) )
    {
      result = *(_DWORD *)result;
      ++v8;
      if ( !result )
        return result;
    }
    if ( (*(_BYTE *)(result + 12) & 1) != 0 )
      *(_WORD *)a4 |= 0x200u;
  }
  return 0;
}

```

## disassembly

```asm
0x1001bc80  mov     edi, edi
0x1001bc82  push    ebp
0x1001bc83  mov     ebp, esp
0x1001bc85  push    ecx
0x1001bc86  push    esi
0x1001bc87  push    edi
0x1001bc88  mov     edi, ecx
0x1001bc8a  cmp     dword ptr [edi+0Ch], 0
0x1001bc8e  jz      short loc_1001BCB2
0x1001bc90  push    [ebp+arg_8]
0x1001bc93  push    [ebp+arg_4]
0x1001bc96  push    [ebp+arg_0]
0x1001bc99  call    _XLOLECellRead@20; XLOLECellRead(x,x,x,x,x)
0x1001bc9e  cmp     eax, 2
0x1001bca1  jz      short loc_1001BCE2
0x1001bca3  mov     ecx, eax
0x1001bca5  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001bcaa  pop     edi
0x1001bcab  pop     esi
0x1001bcac  mov     esp, ebp
0x1001bcae  pop     ebp
0x1001bcaf  retn    0Ch
0x1001bcb2  movzx   eax, word ptr [edx]
0x1001bcb5  add     ax, word ptr [ebp+arg_0]
0x1001bcb9  mov     esi, [ebp+arg_4]
0x1001bcbc  mov     ecx, [edi+8]
0x1001bcbf  mov     word ptr [ebp+var_4], ax
0x1001bcc3  movzx   eax, word ptr [edx+2]
0x1001bcc7  mov     edx, esi
0x1001bcc9  add     ax, word ptr [ebp+arg_0+2]
0x1001bccd  mov     word ptr [ebp+var_4+2], ax
0x1001bcd1  push    [ebp+var_4]
0x1001bcd4  call    _ExcelReadCell@12; ExcelReadCell(x,x,x)
0x1001bcd9  test    eax, eax
0x1001bcdb  js      short loc_1001BCA3
0x1001bcdd  cmp     eax, 2
0x1001bce0  jnz     short loc_1001BCEF
0x1001bce2  mov     eax, 1
0x1001bce7  pop     edi
0x1001bce8  pop     esi
0x1001bce9  mov     esp, ebp
0x1001bceb  pop     ebp
0x1001bcec  retn    0Ch
0x1001bcef  mov     eax, 100h
0x1001bcf4  test    [esi], ax
0x1001bcf7  jz      short loc_1001BD01
0x1001bcf9  mov     ecx, [esi+28h]
0x1001bcfc  call    _MemFree@4; MemFree(x)
0x1001bd01  mov     eax, [edi+324h]
0x1001bd07  xor     ecx, ecx
0x1001bd09  mov     eax, [eax+48h]
0x1001bd0c  test    eax, eax
0x1001bd0e  jz      short loc_1001BD38
0x1001bd10  mov     edx, [esi+4]
0x1001bd13  cmp     ecx, edx
0x1001bd15  jz      short loc_1001BD26
0x1001bd17  mov     eax, [eax]
0x1001bd19  inc     ecx
0x1001bd1a  test    eax, eax
0x1001bd1c  jnz     short loc_1001BD13
0x1001bd1e  pop     edi
0x1001bd1f  pop     esi
0x1001bd20  mov     esp, ebp
0x1001bd22  pop     ebp
0x1001bd23  retn    0Ch
0x1001bd26  test    eax, eax
0x1001bd28  jz      short loc_1001BD38
0x1001bd2a  test    byte ptr [eax+0Ch], 1
0x1001bd2e  jz      short loc_1001BD38
0x1001bd30  mov     eax, 200h
0x1001bd35  or      [esi], ax
0x1001bd38  pop     edi
0x1001bd39  xor     eax, eax
0x1001bd3b  pop     esi
0x1001bd3c  mov     esp, ebp
0x1001bd3e  pop     ebp
0x1001bd3f  retn    0Ch
```
