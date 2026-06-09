# AslpFileGetImageResourceDirectoryRoot

- ea: `0x1800108c4`
- end: `0x180010aff`
- name: `AslpFileGetImageResourceDirectoryRoot`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x180011990`

## callees

- `0x18000e240`
- `0x1800107f8`
- `0x1800108c4`
- `0x180013658`

## string_xrefs

- `0x1800108f8`: `AslpFileGetImageResourceDirectoryRoot`
- `0x1800109e2`: `AslpFileGetImageResourceDirectoryRoot`
- `0x180010adf`: `AslpFileGetImageResourceDirectoryRoot`
- `0x180010ace`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`
- `0x1800109d6`: `Image PE optional header outside image`

## pseudocode

```c
__int64 __fastcall AslpFileGetImageResourceDirectoryRoot(unsigned __int64 *a1, unsigned __int64 a2, __int64 a3)
{
  bool v3; // zf
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r14
  int ImageNtHeader; // ebx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rbx
  _WORD *v12; // rax
  unsigned __int64 v13; // rdx
  unsigned int v14; // eax
  _DWORD *v15; // rsi
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // [rsp+78h] [rbp+10h] BYREF

  v21 = a2;
  v3 = *(_DWORD *)(a3 + 56) == 6;
  v21 = 0;
  if ( !v3 )
  {
    AslLogCallPrintf(1, "AslpFileGetImageResourceDirectoryRoot", 1924, "File is not a PE image");
    return 3221225659LL;
  }
  v7 = *(_QWORD *)(a3 + 32);
  v8 = *(_QWORD *)(a3 + 40);
  ImageNtHeader = AslpFileGetImageNtHeader(&v21, a3);
  if ( ImageNtHeader < 0 )
    goto LABEL_47;
  if ( v21 < v7
    || (v10 = v21 + 8, v21 >= v21 + 8)
    || (v11 = v8 + v7, v21 > v8 + v7)
    || v10 < v7
    || v10 > v11
    || v7 > v11
    || v8 < 8 )
  {
    ImageNtHeader = -1073741266;
LABEL_47:
    AslLogCallPrintf(
      1,
      "AslpFileGetImageResourceDirectoryRoot",
      1937,
      "AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]",
      ImageNtHeader);
    return (unsigned int)ImageNtHeader;
  }
  v12 = (_WORD *)(v21 + 24);
  if ( *(_WORD *)(v21 + 24) != 267 )
  {
    if ( *v12 == 523 && *(_WORD *)(v21 + 20) >= 0x70u )
    {
      if ( (unsigned __int64)v12 >= v7 )
      {
        v17 = v21 + 264;
        if ( v21 + 24 < v21 + 264 && (unsigned __int64)v12 <= v11 && v17 >= v7 && v17 <= v11 && v8 >= 0xF0 )
        {
          v14 = *(_DWORD *)(v21 + 132);
          v15 = (_DWORD *)(v21 + 152);
          goto LABEL_31;
        }
      }
      v16 = 1971;
LABEL_21:
      AslLogCallPrintf(1, "AslpFileGetImageResourceDirectoryRoot", v16, "Image PE optional header outside image");
      return 3221226030LL;
    }
    return 3221225595LL;
  }
  if ( *(_WORD *)(v21 + 20) < 0x60u )
    return 3221225595LL;
  if ( (unsigned __int64)v12 < v7
    || (v13 = v21 + 248, v21 + 24 >= v21 + 248)
    || (unsigned __int64)v12 > v11
    || v13 < v7
    || v13 > v11
    || v8 < 0xE0 )
  {
    v16 = 1955;
    goto LABEL_21;
  }
  v14 = *(_DWORD *)(v21 + 116);
  v15 = (_DWORD *)(v21 + 136);
LABEL_31:
  if ( v14 <= 2 || v15[1] < 0x10u || !*v15 )
    return 3221225609LL;
  v18 = AslpImageRvaToVa(v21, a3);
  if ( !v18 )
    return v18 != 0 ? -1073741266 : -1073741687;
  if ( v18 < v7 )
    return v18 != 0 ? -1073741266 : -1073741687;
  v19 = (unsigned int)v15[1];
  v20 = v19 + v18;
  if ( v18 > v19 + v18 || v18 > v11 || v20 < v7 || v20 > v11 || v19 > v8 )
    return v18 != 0 ? -1073741266 : -1073741687;
  *a1 = v18;
  return 0;
}

```

## disassembly

```asm
0x1800108c4  mov     [rsp+arg_8], rdx
0x1800108c9  push    rbx
0x1800108ca  push    rbp
0x1800108cb  push    rsi
0x1800108cc  push    rdi
0x1800108cd  push    r14
0x1800108cf  push    r15
0x1800108d1  sub     rsp, 38h
0x1800108d5  cmp     dword ptr [r8+38h], 6
0x1800108da  mov     rbp, r8
0x1800108dd  mov     r15, rcx
0x1800108e0  mov     [rsp+68h+arg_8], 0
0x1800108e9  jz      short loc_180010913
0x1800108eb  lea     r9, aFileIsNotAPeIm; "File is not a PE image"
0x1800108f2  mov     r8d, 784h
0x1800108f8  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x1800108ff  mov     ecx, 1
0x180010904  call    AslLogCallPrintf
0x180010909  mov     eax, 0C00000BBh
0x18001090e  jmp     loc_180010AF2
0x180010913  mov     rdi, [r8+20h]
0x180010917  lea     rcx, [rsp+68h+arg_8]
0x18001091c  mov     r14, [r8+28h]
0x180010920  mov     rdx, rbp
0x180010923  call    AslpFileGetImageNtHeader
0x180010928  mov     ebx, eax
0x18001092a  test    eax, eax
0x18001092c  js      loc_180010ACE
0x180010932  mov     rcx, [rsp+68h+arg_8]
0x180010937  cmp     rcx, rdi
0x18001093a  jb      loc_180010AC9
0x180010940  lea     rax, [rcx+8]
0x180010944  cmp     rcx, rax
0x180010947  ja      loc_180010AC9
0x18001094d  lea     rbx, [r14+rdi]
0x180010951  cmp     rcx, rbx
0x180010954  ja      loc_180010AC9
0x18001095a  cmp     rax, rdi
0x18001095d  jb      loc_180010AC9
0x180010963  cmp     rax, rbx
0x180010966  ja      loc_180010AC9
0x18001096c  cmp     rdi, rbx
0x18001096f  ja      loc_180010AC9
0x180010975  cmp     r14, 8
0x180010979  jb      loc_180010AC9
0x18001097f  lea     rax, [rcx+18h]
0x180010983  mov     edx, 10Bh
0x180010988  cmp     [rax], dx
0x18001098b  jnz     short loc_1800109F8
0x18001098d  cmp     word ptr [rcx+14h], 60h ; '`'
0x180010992  jb      loc_180010AC2
0x180010998  cmp     rax, rdi
0x18001099b  jb      short loc_1800109D0
0x18001099d  lea     rdx, [rax+0E0h]
0x1800109a4  cmp     rax, rdx
0x1800109a7  ja      short loc_1800109D0
0x1800109a9  cmp     rax, rbx
0x1800109ac  ja      short loc_1800109D0
0x1800109ae  cmp     rdx, rdi
0x1800109b1  jb      short loc_1800109D0
0x1800109b3  cmp     rdx, rbx
0x1800109b6  ja      short loc_1800109D0
0x1800109b8  cmp     r14, 0E0h
0x1800109bf  jb      short loc_1800109D0
0x1800109c1  mov     eax, [rcx+74h]
0x1800109c4  lea     rsi, [rcx+88h]
0x1800109cb  jmp     loc_180010A53
0x1800109d0  mov     r8d, 7A3h
0x1800109d6  lea     r9, aImagePeOptiona; "Image PE optional header outside image"
0x1800109dd  mov     ecx, 1
0x1800109e2  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x1800109e9  call    AslLogCallPrintf
0x1800109ee  mov     eax, 0C000022Eh
0x1800109f3  jmp     loc_180010AF2
0x1800109f8  mov     edx, 20Bh
0x1800109fd  cmp     [rax], dx
0x180010a00  jnz     loc_180010AC2
0x180010a06  cmp     word ptr [rcx+14h], 70h ; 'p'
0x180010a0b  jb      loc_180010AC2
0x180010a11  cmp     rax, rdi
0x180010a14  jb      loc_180010AB7
0x180010a1a  lea     rdx, [rax+0F0h]
0x180010a21  cmp     rax, rdx
0x180010a24  ja      loc_180010AB7
0x180010a2a  cmp     rax, rbx
0x180010a2d  ja      loc_180010AB7
0x180010a33  cmp     rdx, rdi
0x180010a36  jb      short loc_180010AB7
0x180010a38  cmp     rdx, rbx
0x180010a3b  ja      short loc_180010AB7
0x180010a3d  cmp     r14, 0F0h
0x180010a44  jb      short loc_180010AB7
0x180010a46  mov     eax, [rcx+84h]
0x180010a4c  lea     rsi, [rcx+98h]
0x180010a53  cmp     eax, 2
0x180010a56  jbe     short loc_180010AB0
0x180010a58  cmp     dword ptr [rsi+4], 10h
0x180010a5c  jb      short loc_180010AB0
0x180010a5e  mov     r8d, [rsi]
0x180010a61  test    r8d, r8d
0x180010a64  jz      short loc_180010AB0
0x180010a66  mov     rdx, rbp
0x180010a69  call    AslpImageRvaToVa
0x180010a6e  test    rax, rax
0x180010a71  jz      short loc_180010A9F
0x180010a73  cmp     rax, rdi
0x180010a76  jb      short loc_180010A9F
0x180010a78  mov     edx, [rsi+4]
0x180010a7b  lea     rcx, [rdx+rax]
0x180010a7f  cmp     rax, rcx
0x180010a82  ja      short loc_180010A9F
0x180010a84  cmp     rax, rbx
0x180010a87  ja      short loc_180010A9F
0x180010a89  cmp     rcx, rdi
0x180010a8c  jb      short loc_180010A9F
0x180010a8e  cmp     rcx, rbx
0x180010a91  ja      short loc_180010A9F
0x180010a93  cmp     rdx, r14
0x180010a96  ja      short loc_180010A9F
0x180010a98  mov     [r15], rax
0x180010a9b  xor     eax, eax
0x180010a9d  jmp     short loc_180010AF2
0x180010a9f  neg     rax
0x180010aa2  sbb     eax, eax
0x180010aa4  and     eax, 1A5h
0x180010aa9  add     eax, 0C0000089h
0x180010aae  jmp     short loc_180010AF2
0x180010ab0  mov     eax, 0C0000089h
0x180010ab5  jmp     short loc_180010AF2
0x180010ab7  mov     r8d, 7B3h
0x180010abd  jmp     loc_1800109D6
0x180010ac2  mov     eax, 0C000007Bh
0x180010ac7  jmp     short loc_180010AF2
0x180010ac9  mov     ebx, 0C000022Eh
0x180010ace  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x180010ad5  mov     [rsp+68h+var_48], ebx
0x180010ad9  mov     r8d, 791h
0x180010adf  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x180010ae6  mov     ecx, 1
0x180010aeb  call    AslLogCallPrintf
0x180010af0  mov     eax, ebx
0x180010af2  add     rsp, 38h
0x180010af6  pop     r15
0x180010af8  pop     r14
0x180010afa  pop     rdi
0x180010afb  pop     rsi
0x180010afc  pop     rbp
0x180010afd  pop     rbx
0x180010afe  retn
```
