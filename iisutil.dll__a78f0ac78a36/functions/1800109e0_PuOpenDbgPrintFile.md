# PuOpenDbgPrintFile

- ea: `0x1800109e0`
- end: `0x180010b1d`
- name: `PuOpenDbgPrintFile`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800109e0`
- `0x18001ecc8`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180010a94`
- `msvcrt!strcpy_s` at `0x180010ab3`
- `msvcrt!strcpy_s` at `0x180010a94`
- `msvcrt!strcpy_s` at `0x180010ab3`
- `msvcrt!strcat_s` at `0x180010ae6`
- `msvcrt!strcat_s` at `0x180010afb`
- `msvcrt!strcat_s` at `0x180010ae6`
- `msvcrt!strcat_s` at `0x180010afb`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x180010a7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x180010a7b`

## pseudocode

```c
__int64 __fastcall PuOpenDbgPrintFile(__int64 a1, const char *a2, const char *a3)
{
  __int64 v5; // r14
  char *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v10; // rax

  if ( !a2 || !a1 )
    return 87;
  v5 = -1;
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    if ( v10 < 0x104 )
    {
      v6 = (char *)(a1 + 100);
      goto LABEL_17;
    }
    return 87;
  }
  v6 = (char *)(a1 + 100);
  if ( *(_BYTE *)(a1 + 100) || GetWindowsDirectoryA((LPSTR)(a1 + 100), 0x104u) )
    goto LABEL_5;
  a3 = ".";
LABEL_17:
  strcpy_s(v6, 0x104u, a3);
LABEL_5:
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = -1;
  do
    ++v8;
  while ( v6[v8] );
  if ( (unsigned __int64)(v7 + v8) >= 0x104 )
    return 8;
  strcpy_s((char *)(a1 + 360), 0x104u, v6);
  while ( *(_BYTE *)(a1 + v5++ + 361) != 0 )
    ;
  if ( *(_BYTE *)(v5 + a1 + 359) != 92 )
    strcat_s((char *)(a1 + 360), 0x104u, "\\");
  strcat_s((char *)(a1 + 360), 0x104u, a2);
  return PuOpenDbgFileLocal(a1);
}

```

## disassembly

```asm
0x1800109e0  push    rbx
0x1800109e2  push    rbp
0x1800109e3  push    rdi
0x1800109e4  push    r14
0x1800109e6  sub     rsp, 28h
0x1800109ea  mov     rbx, rdx
0x1800109ed  mov     rbp, rcx
0x1800109f0  test    rdx, rdx
0x1800109f3  jz      loc_180010B13
0x1800109f9  test    rcx, rcx
0x1800109fc  jz      loc_180010B13
0x180010a02  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180010a09  test    r8, r8
0x180010a0c  jnz     short loc_180010A54
0x180010a0e  cmp     [rcx+64h], r8b
0x180010a12  lea     rdi, [rcx+64h]
0x180010a16  jz      short loc_180010A73
0x180010a18  mov     rax, r14
0x180010a1b  nop     dword ptr [rax+rax+00h]
0x180010a20  inc     rax
0x180010a23  cmp     byte ptr [rbx+rax], 0
0x180010a27  jnz     short loc_180010A20
0x180010a29  mov     rcx, r14
0x180010a2c  nop     dword ptr [rax+00h]
0x180010a30  inc     rcx
0x180010a33  cmp     byte ptr [rdi+rcx], 0
0x180010a37  jnz     short loc_180010A30
0x180010a39  add     rcx, rax
0x180010a3c  cmp     rcx, 104h
0x180010a43  jb      short loc_180010A9F
0x180010a45  mov     eax, 8
0x180010a4a  add     rsp, 28h
0x180010a4e  pop     r14
0x180010a50  pop     rdi
0x180010a51  pop     rbp
0x180010a52  pop     rbx
0x180010a53  retn
0x180010a54  mov     rax, r14
0x180010a57  inc     rax
0x180010a5a  cmp     byte ptr [r8+rax], 0
0x180010a5f  jnz     short loc_180010A57
0x180010a61  cmp     rax, 104h
0x180010a67  jnb     loc_180010B13
0x180010a6d  lea     rdi, [rcx+64h]
0x180010a71  jmp     short loc_180010A8C
0x180010a73  mov     edx, 104h; uSize
0x180010a78  mov     rcx, rdi; lpBuffer
0x180010a7b  call    cs:__imp_GetWindowsDirectoryA
0x180010a81  test    eax, eax
0x180010a83  jnz     short loc_180010A18
0x180010a85  lea     r8, Source; "."
0x180010a8c  mov     edx, 104h; SizeInBytes
0x180010a91  mov     rcx, rdi; Destination
0x180010a94  call    cs:__imp_strcpy_s
0x180010a9a  jmp     loc_180010A18
0x180010a9f  mov     r8, rdi; Source
0x180010aa2  mov     [rsp+48h+arg_0], rsi
0x180010aa7  mov     edx, 104h; SizeInBytes
0x180010aac  lea     rcx, [rbp+168h]; Destination
0x180010ab3  call    cs:__imp_strcpy_s
0x180010ab9  cmp     byte ptr [rbp+r14+169h], 0
0x180010ac2  lea     r14, [r14+1]
0x180010ac6  jnz     short loc_180010AB9
0x180010ac8  cmp     byte ptr [r14+rbp+167h], 5Ch ; '\'
0x180010ad1  jz      short loc_180010AEC
0x180010ad3  lea     r8, asc_180031FEC; "\\"
0x180010ada  mov     edx, 104h; SizeInBytes
0x180010adf  lea     rcx, [rbp+168h]; Destination
0x180010ae6  call    cs:__imp_strcat_s
0x180010aec  mov     r8, rbx; Source
0x180010aef  lea     rcx, [rbp+168h]; Destination
0x180010af6  mov     edx, 104h; SizeInBytes
0x180010afb  call    cs:__imp_strcat_s
0x180010b01  mov     rcx, rbp
0x180010b04  call    PuOpenDbgFileLocal
0x180010b09  mov     rsi, [rsp+48h+arg_0]
0x180010b0e  jmp     loc_180010A4A
0x180010b13  mov     eax, 57h ; 'W'
0x180010b18  jmp     loc_180010A4A
```
