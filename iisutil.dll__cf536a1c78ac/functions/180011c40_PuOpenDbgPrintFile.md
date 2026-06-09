# PuOpenDbgPrintFile

- ea: `0x180011c40`
- end: `0x180011d9c`
- name: `PuOpenDbgPrintFile`
- size: `348`
- prototype: `__int64 __fastcall(__int64, const char *, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011c40`
- `0x18001fed8`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180011cfb`
- `msvcrt!strcpy_s` at `0x180011d20`
- `msvcrt!strcpy_s` at `0x180011cfb`
- `msvcrt!strcpy_s` at `0x180011d20`
- `msvcrt!strcat_s` at `0x180011d59`
- `msvcrt!strcat_s` at `0x180011d74`
- `msvcrt!strcat_s` at `0x180011d59`
- `msvcrt!strcat_s` at `0x180011d74`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x180011cdc`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x180011cdc`

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
0x180011c40  push    rbx
0x180011c42  push    rbp
0x180011c43  push    rdi
0x180011c44  push    r14
0x180011c46  sub     rsp, 28h
0x180011c4a  mov     rbx, rdx
0x180011c4d  mov     rbp, rcx
0x180011c50  test    rdx, rdx
0x180011c53  jz      loc_180011D92
0x180011c59  test    rcx, rcx
0x180011c5c  jz      loc_180011D92
0x180011c62  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180011c69  test    r8, r8
0x180011c6c  jnz     short loc_180011CB5
0x180011c6e  cmp     [rcx+64h], r8b
0x180011c72  lea     rdi, [rcx+64h]
0x180011c76  jz      short loc_180011CD4
0x180011c78  mov     rax, r14
0x180011c7b  nop     dword ptr [rax+rax+00h]
0x180011c80  inc     rax
0x180011c83  cmp     byte ptr [rbx+rax], 0
0x180011c87  jnz     short loc_180011C80
0x180011c89  mov     rcx, r14
0x180011c8c  nop     dword ptr [rax+00h]
0x180011c90  inc     rcx
0x180011c93  cmp     byte ptr [rdi+rcx], 0
0x180011c97  jnz     short loc_180011C90
0x180011c99  add     rcx, rax
0x180011c9c  cmp     rcx, 104h
0x180011ca3  jb      short loc_180011D0C
0x180011ca5  mov     eax, 8
0x180011caa  add     rsp, 28h
0x180011cae  pop     r14
0x180011cb0  pop     rdi
0x180011cb1  pop     rbp
0x180011cb2  pop     rbx
0x180011cb3  retn
0x180011cb5  mov     rax, r14
0x180011cb8  inc     rax
0x180011cbb  cmp     byte ptr [r8+rax], 0
0x180011cc0  jnz     short loc_180011CB8
0x180011cc2  cmp     rax, 104h
0x180011cc8  jnb     loc_180011D92
0x180011cce  lea     rdi, [rcx+64h]
0x180011cd2  jmp     short loc_180011CF3
0x180011cd4  mov     edx, 104h; uSize
0x180011cd9  mov     rcx, rdi; lpBuffer
0x180011cdc  call    cs:__imp_GetWindowsDirectoryA
0x180011ce3  nop     dword ptr [rax+rax+00h]
0x180011ce8  test    eax, eax
0x180011cea  jnz     short loc_180011C78
0x180011cec  lea     r8, Source; "."
0x180011cf3  mov     edx, 104h; SizeInBytes
0x180011cf8  mov     rcx, rdi; Destination
0x180011cfb  call    cs:__imp_strcpy_s
0x180011d02  nop     dword ptr [rax+rax+00h]
0x180011d07  jmp     loc_180011C78
0x180011d0c  mov     r8, rdi; Source
0x180011d0f  mov     [rsp+48h+arg_0], rsi
0x180011d14  mov     edx, 104h; SizeInBytes
0x180011d19  lea     rcx, [rbp+168h]; Destination
0x180011d20  call    cs:__imp_strcpy_s
0x180011d27  nop     dword ptr [rax+rax+00h]
0x180011d2c  cmp     byte ptr [rbp+r14+169h], 0
0x180011d35  lea     r14, [r14+1]
0x180011d39  jnz     short loc_180011D2C
0x180011d3b  cmp     byte ptr [r14+rbp+167h], 5Ch ; '\'
0x180011d44  jz      short loc_180011D65
0x180011d46  lea     r8, asc_180033FEC; "\\"
0x180011d4d  mov     edx, 104h; SizeInBytes
0x180011d52  lea     rcx, [rbp+168h]; Destination
0x180011d59  call    cs:__imp_strcat_s
0x180011d60  nop     dword ptr [rax+rax+00h]
0x180011d65  mov     r8, rbx; Source
0x180011d68  lea     rcx, [rbp+168h]; Destination
0x180011d6f  mov     edx, 104h; SizeInBytes
0x180011d74  call    cs:__imp_strcat_s
0x180011d7b  nop     dword ptr [rax+rax+00h]
0x180011d80  mov     rcx, rbp
0x180011d83  call    PuOpenDbgFileLocal
0x180011d88  mov     rsi, [rsp+48h+arg_0]
0x180011d8d  jmp     loc_180011CAA
0x180011d92  mov     eax, 57h ; 'W'
0x180011d97  jmp     loc_180011CAA
```
