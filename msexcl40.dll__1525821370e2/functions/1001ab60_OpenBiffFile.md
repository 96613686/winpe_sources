# OpenBiffFile

- ea: `0x1001ab60`
- end: `0x1001abea`
- name: `OpenBiffFile`
- size: `138`
- prototype: `int __thiscall(LPCWSTR lpFileName, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1001abf0`

## callees

- `0x10011280`
- `0x1001ab60`

## pseudocode

```c
int __thiscall OpenBiffFile(LPCWSTR lpFileName, __int16 a2, _DWORD *a3)
{
  int result; // eax
  int v5; // ecx
  int v6; // ecx
  int v7; // eax

  if ( (a2 & 0x100) != 0 )
  {
    result = ExcelOpenFile(lpFileName, (unsigned __int8)a2 | 0x2900, (int)lpFileName, a3);
    if ( result == -20 )
    {
      result = ExcelOpenFile(lpFileName, (unsigned __int8)a2, v5, a3);
      if ( result )
        return -20;
    }
  }
  else
  {
    result = ExcelOpenFile(lpFileName, (unsigned __int8)a2, (int)lpFileName, a3);
    if ( result == -10 )
    {
      v7 = 10496;
      if ( (a2 & 3) == 0 )
        v7 = 12544;
      result = ExcelOpenFile(lpFileName, (unsigned __int8)a2 | v7, v6, a3);
      if ( result )
        return -10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1001ab60  mov     edi, edi
0x1001ab62  push    ebp
0x1001ab63  mov     ebp, esp
0x1001ab65  push    ecx
0x1001ab66  mov     eax, [ebp+arg_0]
0x1001ab69  push    ebx
0x1001ab6a  movzx   ebx, al
0x1001ab6d  push    esi
0x1001ab6e  mov     esi, ecx
0x1001ab70  push    edi
0x1001ab71  mov     edi, [ebp+arg_4]
0x1001ab74  push    edi; int
0x1001ab75  push    ecx; int
0x1001ab76  test    eax, 100h
0x1001ab7b  jz      short loc_1001ABAE
0x1001ab7d  mov     eax, ebx
0x1001ab7f  or      eax, 2900h
0x1001ab84  push    eax; int
0x1001ab85  call    _ExcelOpenFile@20; ExcelOpenFile(x,x,x,x,x)
0x1001ab8a  test    eax, eax
0x1001ab8c  jz      short loc_1001ABE2
0x1001ab8e  cmp     eax, 0FFFFFFECh
0x1001ab91  jnz     short loc_1001ABE2
0x1001ab93  push    edi; int
0x1001ab94  push    ecx; int
0x1001ab95  push    ebx; int
0x1001ab96  mov     ecx, esi; lpFileName
0x1001ab98  call    _ExcelOpenFile@20; ExcelOpenFile(x,x,x,x,x)
0x1001ab9d  test    eax, eax
0x1001ab9f  jz      short loc_1001ABE2
0x1001aba1  mov     eax, 0FFFFFFECh
0x1001aba6  pop     edi
0x1001aba7  pop     esi
0x1001aba8  pop     ebx
0x1001aba9  pop     ecx
0x1001abaa  pop     ebp
0x1001abab  retn    8
0x1001abae  push    ebx; int
0x1001abaf  call    _ExcelOpenFile@20; ExcelOpenFile(x,x,x,x,x)
0x1001abb4  test    eax, eax
0x1001abb6  jz      short loc_1001ABE2
0x1001abb8  cmp     eax, 0FFFFFFF6h
0x1001abbb  jnz     short loc_1001ABE2
0x1001abbd  push    edi; int
0x1001abbe  push    ecx; int
0x1001abbf  test    bl, 3
0x1001abc2  mov     ecx, 3100h
0x1001abc7  mov     eax, 2900h
0x1001abcc  cmovz   eax, ecx
0x1001abcf  mov     ecx, esi; lpFileName
0x1001abd1  or      eax, ebx
0x1001abd3  push    eax; int
0x1001abd4  call    _ExcelOpenFile@20; ExcelOpenFile(x,x,x,x,x)
0x1001abd9  test    eax, eax
0x1001abdb  jz      short loc_1001ABE2
0x1001abdd  mov     eax, 0FFFFFFF6h
0x1001abe2  pop     edi
0x1001abe3  pop     esi
0x1001abe4  pop     ebx
0x1001abe5  pop     ecx
0x1001abe6  pop     ebp
0x1001abe7  retn    8
```
