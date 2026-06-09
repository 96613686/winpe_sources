# SQLInstallDriverManager

- ea: `0x18000f530`
- end: `0x18000f5d5`
- name: `SQLInstallDriverManager`
- size: `165`
- prototype: `BOOL __stdcall(LPSTR lpszPath, WORD cchPathMax, WORD *pcchPathOut)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002940`
- `0x1800091f0`
- `0x18000f530`
- `0x180013c2c`

## import_xrefs

- `msvcrt!calloc` at `0x18000f576`
- `msvcrt!calloc` at `0x18000f576`

## pseudocode

```c
BOOL __stdcall SQLInstallDriverManager(LPSTR lpszPath, WORD cchPathMax, WORD *pcchPathOut)
{
  WORD *v4; // rsi
  WCHAR *v5; // rbx
  BOOL v6; // ebp
  __int64 v7; // rcx
  LPSTR v9; // [rsp+60h] [rbp+8h] BYREF
  __int16 v10; // [rsp+68h] [rbp+10h] BYREF

  v9 = lpszPath;
  v10 = 0;
  v4 = (WORD *)&v10;
  v5 = 0;
  if ( pcchPathOut )
    v4 = pcchPathOut;
  if ( !cchPathMax || !lpszPath || (v6 = 0, (v5 = (WCHAR *)calloc(2LL * cchPathMax, 1u)) != 0) )
  {
    v6 = SQLInstallDriverManagerW(v5, cchPathMax, v4);
    if ( v6 && cchPathMax )
      LConvertToAnsiWordLengths(v7, v5, *v4, &v9, cchPathMax, v4);
  }
  OFree(v5);
  return v6;
}

```

## disassembly

```asm
0x18000f530  mov     rax, rsp
0x18000f533  mov     [rax+18h], rbx
0x18000f537  mov     [rax+20h], rbp
0x18000f53b  mov     [rax+8], rcx
0x18000f53f  push    rsi
0x18000f540  push    rdi
0x18000f541  push    r14
0x18000f543  sub     rsp, 40h
0x18000f547  xor     r14d, r14d
0x18000f54a  movzx   edi, dx
0x18000f54d  test    r8, r8
0x18000f550  mov     [rax+10h], r14w
0x18000f555  lea     rsi, [rax+10h]
0x18000f559  mov     ebx, r14d
0x18000f55c  cmovnz  rsi, r8
0x18000f560  test    di, di
0x18000f563  jz      short loc_18000F584
0x18000f565  test    rcx, rcx
0x18000f568  jz      short loc_18000F584
0x18000f56a  mov     ecx, edi
0x18000f56c  lea     edx, [r14+1]; Size
0x18000f570  add     rcx, rcx; Count
0x18000f573  mov     ebp, r14d
0x18000f576  call    cs:__imp_calloc
0x18000f57c  mov     rbx, rax
0x18000f57f  test    rax, rax
0x18000f582  jz      short loc_18000F5B8
0x18000f584  mov     r8, rsi; pcchPathOut
0x18000f587  movzx   edx, di; cchPathMax
0x18000f58a  mov     rcx, rbx; lpszPath
0x18000f58d  call    SQLInstallDriverManagerW
0x18000f592  mov     ebp, eax
0x18000f594  test    eax, eax
0x18000f596  jz      short loc_18000F5B8
0x18000f598  test    di, di
0x18000f59b  jz      short loc_18000F5B8
0x18000f59d  movzx   r8d, word ptr [rsi]
0x18000f5a1  lea     r9, [rsp+58h+arg_0]
0x18000f5a6  mov     [rsp+58h+var_30], rsi
0x18000f5ab  mov     rdx, rbx
0x18000f5ae  mov     [rsp+58h+var_38], di
0x18000f5b3  call    LConvertToAnsiWordLengths
0x18000f5b8  mov     rcx, rbx
0x18000f5bb  call    OFree
0x18000f5c0  mov     rbx, [rsp+58h+arg_10]
0x18000f5c5  mov     eax, ebp
0x18000f5c7  mov     rbp, [rsp+58h+arg_18]
0x18000f5cc  add     rsp, 40h
0x18000f5d0  pop     r14
0x18000f5d2  pop     rdi
0x18000f5d3  pop     rsi
0x18000f5d4  retn
```
