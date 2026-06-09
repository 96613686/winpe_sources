# AslpFileGetImageResourceDirectoryRoot

- ea: `0x14082c0dc`
- end: `0x14082c2a4`
- name: `AslpFileGetImageResourceDirectoryRoot`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x14082ced0`

## callees

- `0x1406ce66c`
- `0x14082bf9c`
- `0x14082c0dc`
- `0x14082e044`
- `0x1408c2f88`

## string_xrefs

- `0x14082c26c`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`
- `0x14082c1a0`: `Image PE optional header outside image`
- `0x14082c115`: `AslpFileGetImageResourceDirectoryRoot`
- `0x14082c1ac`: `AslpFileGetImageResourceDirectoryRoot`
- `0x14082c27d`: `AslpFileGetImageResourceDirectoryRoot`

## pseudocode

```c
__int64 __fastcall AslpFileGetImageResourceDirectoryRoot(__int64 *a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  __int64 v7; // rsi
  __int64 v8; // rbp
  int ImageNtHeader; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r11
  __int64 v13; // rcx
  __int16 v14; // ax
  __int64 v15; // r11
  int v16; // r8d
  unsigned int v17; // eax
  unsigned int *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // [rsp+58h] [rbp+10h] BYREF

  v20 = a2;
  v3 = *(_DWORD *)(a3 + 64) == 6;
  v20 = 0;
  if ( !v3 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetImageResourceDirectoryRoot",
      1924,
      (unsigned int)"File is not a PE image");
    return 3221225659LL;
  }
  v7 = *(_QWORD *)(a3 + 32);
  v8 = *(_QWORD *)(a3 + 40);
  ImageNtHeader = AslpFileGetImageNtHeader(&v20, a3);
  if ( ImageNtHeader < 0 )
    goto LABEL_26;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v20, 8, v7, v8) )
  {
    ImageNtHeader = -1073741266;
LABEL_26:
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetImageResourceDirectoryRoot",
      1937,
      (unsigned int)"AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]");
    return (unsigned int)ImageNtHeader;
  }
  v13 = v12 + 24;
  v14 = *(_WORD *)(v12 + 24);
  if ( v14 != 267 )
  {
    if ( v14 == 523 && *(_WORD *)(v12 + 20) >= 0x70u )
    {
      if ( !(unsigned __int8)AslpMemoryCheckBounds(v13, 240, v10, v11) )
      {
        v16 = 1971;
        goto LABEL_9;
      }
      v17 = *(_DWORD *)(v15 + 132);
      v18 = (unsigned int *)(v15 + 152);
      goto LABEL_16;
    }
    return 3221225595LL;
  }
  if ( *(_WORD *)(v12 + 20) < 0x60u )
    return 3221225595LL;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v13, 224, v10, v11) )
  {
    v16 = 1955;
LABEL_9:
    AslLogCallPrintf(
      1,
      (unsigned int)"AslpFileGetImageResourceDirectoryRoot",
      v16,
      (unsigned int)"Image PE optional header outside image");
    return 3221226030LL;
  }
  v17 = *(_DWORD *)(v15 + 116);
  v18 = (unsigned int *)(v15 + 136);
LABEL_16:
  if ( v17 <= 2 || v18[1] < 0x10 || !*v18 )
    return 3221225609LL;
  v19 = AslpImageRvaToVa(v15, a3, *v18);
  if ( !v19 || !(unsigned __int8)AslpMemoryCheckBounds(v19, v18[1], v7, v8) )
    return v19 != 0 ? -1073741266 : -1073741687;
  *a1 = v19;
  return 0;
}

```

## disassembly

```asm
0x14082c0dc  mov     rax, rsp
0x14082c0df  mov     [rax+8], rbx
0x14082c0e3  mov     [rax+18h], rbp
0x14082c0e7  mov     [rax+10h], rdx
0x14082c0eb  push    rsi
0x14082c0ec  push    rdi
0x14082c0ed  push    r14
0x14082c0ef  sub     rsp, 30h
0x14082c0f3  cmp     dword ptr [r8+40h], 6
0x14082c0f8  mov     rdi, r8
0x14082c0fb  mov     r14, rcx
0x14082c0fe  mov     qword ptr [rax+10h], 0
0x14082c106  jz      short loc_14082C130
0x14082c108  lea     r9, aFileIsNotAPeIm; "File is not a PE image"
0x14082c10f  mov     r8d, 784h
0x14082c115  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x14082c11c  mov     ecx, 1
0x14082c121  call    AslLogCallPrintf
0x14082c126  mov     eax, 0C00000BBh
0x14082c12b  jmp     loc_14082C290
0x14082c130  mov     rsi, [r8+20h]
0x14082c134  lea     rcx, [rsp+48h+arg_8]
0x14082c139  mov     rbp, [r8+28h]
0x14082c13d  mov     rdx, rdi
0x14082c140  call    AslpFileGetImageNtHeader
0x14082c145  mov     ebx, eax
0x14082c147  test    eax, eax
0x14082c149  js      loc_14082C26C
0x14082c14f  mov     r11, [rsp+48h+arg_8]
0x14082c154  mov     r9, rbp
0x14082c157  mov     rcx, r11
0x14082c15a  mov     r8, rsi
0x14082c15d  mov     edx, 8
0x14082c162  call    AslpMemoryCheckBounds
0x14082c167  test    al, al
0x14082c169  jz      loc_14082C267
0x14082c16f  lea     rcx, [r11+18h]
0x14082c173  mov     edx, 10Bh
0x14082c178  movzx   eax, word ptr [rcx]
0x14082c17b  cmp     ax, dx
0x14082c17e  jnz     short loc_14082C1CF
0x14082c180  cmp     word ptr [r11+14h], 60h ; '`'
0x14082c186  jb      loc_14082C260
0x14082c18c  mov     edx, 0E0h
0x14082c191  call    AslpMemoryCheckBounds
0x14082c196  test    al, al
0x14082c198  jnz     short loc_14082C1C2
0x14082c19a  mov     r8d, 7A3h
0x14082c1a0  lea     r9, aImagePeOptiona; "Image PE optional header outside image"
0x14082c1a7  mov     ecx, 1
0x14082c1ac  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x14082c1b3  call    AslLogCallPrintf
0x14082c1b8  mov     eax, 0C000022Eh
0x14082c1bd  jmp     loc_14082C290
0x14082c1c2  mov     eax, [r11+74h]
0x14082c1c6  lea     rbx, [r11+88h]
0x14082c1cd  jmp     short loc_14082C209
0x14082c1cf  mov     edx, 20Bh
0x14082c1d4  cmp     ax, dx
0x14082c1d7  jnz     loc_14082C260
0x14082c1dd  cmp     word ptr [r11+14h], 70h ; 'p'
0x14082c1e3  jb      short loc_14082C260
0x14082c1e5  mov     edx, 0F0h
0x14082c1ea  call    AslpMemoryCheckBounds
0x14082c1ef  test    al, al
0x14082c1f1  jnz     short loc_14082C1FB
0x14082c1f3  mov     r8d, 7B3h
0x14082c1f9  jmp     short loc_14082C1A0
0x14082c1fb  mov     eax, [r11+84h]
0x14082c202  lea     rbx, [r11+98h]
0x14082c209  cmp     eax, 2
0x14082c20c  jbe     short loc_14082C259
0x14082c20e  cmp     dword ptr [rbx+4], 10h
0x14082c212  jb      short loc_14082C259
0x14082c214  mov     r8d, [rbx]
0x14082c217  test    r8d, r8d
0x14082c21a  jz      short loc_14082C259
0x14082c21c  mov     rdx, rdi
0x14082c21f  mov     rcx, r11
0x14082c222  call    AslpImageRvaToVa
0x14082c227  mov     rcx, rax
0x14082c22a  test    rax, rax
0x14082c22d  jz      short loc_14082C248
0x14082c22f  mov     edx, [rbx+4]
0x14082c232  mov     r9, rbp
0x14082c235  mov     r8, rsi
0x14082c238  call    AslpMemoryCheckBounds
0x14082c23d  test    al, al
0x14082c23f  jz      short loc_14082C248
0x14082c241  mov     [r14], rcx
0x14082c244  xor     eax, eax
0x14082c246  jmp     short loc_14082C290
0x14082c248  neg     rcx
0x14082c24b  sbb     eax, eax
0x14082c24d  and     eax, 1A5h
0x14082c252  add     eax, 0C0000089h
0x14082c257  jmp     short loc_14082C290
0x14082c259  mov     eax, 0C0000089h
0x14082c25e  jmp     short loc_14082C290
0x14082c260  mov     eax, 0C000007Bh
0x14082c265  jmp     short loc_14082C290
0x14082c267  mov     ebx, 0C000022Eh
0x14082c26c  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x14082c273  mov     [rsp+48h+var_28], ebx
0x14082c277  mov     r8d, 791h
0x14082c27d  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x14082c284  mov     ecx, 1
0x14082c289  call    AslLogCallPrintf
0x14082c28e  mov     eax, ebx
0x14082c290  mov     rbx, [rsp+48h+arg_0]
0x14082c295  mov     rbp, [rsp+48h+arg_10]
0x14082c29a  add     rsp, 30h
0x14082c29e  pop     r14
0x14082c2a0  pop     rdi
0x14082c2a1  pop     rsi
0x14082c2a2  retn
```
