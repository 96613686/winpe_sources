# AslpFileGetImageResourceDirectoryRoot

- ea: `0x14000dd40`
- end: `0x14000df7b`
- name: `AslpFileGetImageResourceDirectoryRoot`
- size: `571`
- prototype: `__int64 __fastcall(unsigned __int64 *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x14000ee0c`

## callees

- `0x140007074`
- `0x14000dc74`
- `0x14000dd40`
- `0x1400101cc`

## string_xrefs

- `0x14000dd74`: `AslpFileGetImageResourceDirectoryRoot`
- `0x14000de5e`: `AslpFileGetImageResourceDirectoryRoot`
- `0x14000df5b`: `AslpFileGetImageResourceDirectoryRoot`
- `0x14000df4a`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`
- `0x14000de52`: `Image PE optional header outside image`

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
0x14000dd40  mov     [rsp+arg_8], rdx
0x14000dd45  push    rbx
0x14000dd46  push    rbp
0x14000dd47  push    rsi
0x14000dd48  push    rdi
0x14000dd49  push    r14
0x14000dd4b  push    r15
0x14000dd4d  sub     rsp, 38h
0x14000dd51  cmp     dword ptr [r8+38h], 6
0x14000dd56  mov     rbp, r8
0x14000dd59  mov     r15, rcx
0x14000dd5c  mov     [rsp+68h+arg_8], 0
0x14000dd65  jz      short loc_14000DD8F
0x14000dd67  lea     r9, aFileIsNotAPeIm; "File is not a PE image"
0x14000dd6e  mov     r8d, 784h
0x14000dd74  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x14000dd7b  mov     ecx, 1
0x14000dd80  call    AslLogCallPrintf
0x14000dd85  mov     eax, 0C00000BBh
0x14000dd8a  jmp     loc_14000DF6E
0x14000dd8f  mov     rdi, [r8+20h]
0x14000dd93  lea     rcx, [rsp+68h+arg_8]
0x14000dd98  mov     r14, [r8+28h]
0x14000dd9c  mov     rdx, rbp
0x14000dd9f  call    AslpFileGetImageNtHeader
0x14000dda4  mov     ebx, eax
0x14000dda6  test    eax, eax
0x14000dda8  js      loc_14000DF4A
0x14000ddae  mov     rcx, [rsp+68h+arg_8]
0x14000ddb3  cmp     rcx, rdi
0x14000ddb6  jb      loc_14000DF45
0x14000ddbc  lea     rax, [rcx+8]
0x14000ddc0  cmp     rcx, rax
0x14000ddc3  ja      loc_14000DF45
0x14000ddc9  lea     rbx, [r14+rdi]
0x14000ddcd  cmp     rcx, rbx
0x14000ddd0  ja      loc_14000DF45
0x14000ddd6  cmp     rax, rdi
0x14000ddd9  jb      loc_14000DF45
0x14000dddf  cmp     rax, rbx
0x14000dde2  ja      loc_14000DF45
0x14000dde8  cmp     rdi, rbx
0x14000ddeb  ja      loc_14000DF45
0x14000ddf1  cmp     r14, 8
0x14000ddf5  jb      loc_14000DF45
0x14000ddfb  lea     rax, [rcx+18h]
0x14000ddff  mov     edx, 10Bh
0x14000de04  cmp     [rax], dx
0x14000de07  jnz     short loc_14000DE74
0x14000de09  cmp     word ptr [rcx+14h], 60h ; '`'
0x14000de0e  jb      loc_14000DF3E
0x14000de14  cmp     rax, rdi
0x14000de17  jb      short loc_14000DE4C
0x14000de19  lea     rdx, [rax+0E0h]
0x14000de20  cmp     rax, rdx
0x14000de23  ja      short loc_14000DE4C
0x14000de25  cmp     rax, rbx
0x14000de28  ja      short loc_14000DE4C
0x14000de2a  cmp     rdx, rdi
0x14000de2d  jb      short loc_14000DE4C
0x14000de2f  cmp     rdx, rbx
0x14000de32  ja      short loc_14000DE4C
0x14000de34  cmp     r14, 0E0h
0x14000de3b  jb      short loc_14000DE4C
0x14000de3d  mov     eax, [rcx+74h]
0x14000de40  lea     rsi, [rcx+88h]
0x14000de47  jmp     loc_14000DECF
0x14000de4c  mov     r8d, 7A3h
0x14000de52  lea     r9, aImagePeOptiona; "Image PE optional header outside image"
0x14000de59  mov     ecx, 1
0x14000de5e  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x14000de65  call    AslLogCallPrintf
0x14000de6a  mov     eax, 0C000022Eh
0x14000de6f  jmp     loc_14000DF6E
0x14000de74  mov     edx, 20Bh
0x14000de79  cmp     [rax], dx
0x14000de7c  jnz     loc_14000DF3E
0x14000de82  cmp     word ptr [rcx+14h], 70h ; 'p'
0x14000de87  jb      loc_14000DF3E
0x14000de8d  cmp     rax, rdi
0x14000de90  jb      loc_14000DF33
0x14000de96  lea     rdx, [rax+0F0h]
0x14000de9d  cmp     rax, rdx
0x14000dea0  ja      loc_14000DF33
0x14000dea6  cmp     rax, rbx
0x14000dea9  ja      loc_14000DF33
0x14000deaf  cmp     rdx, rdi
0x14000deb2  jb      short loc_14000DF33
0x14000deb4  cmp     rdx, rbx
0x14000deb7  ja      short loc_14000DF33
0x14000deb9  cmp     r14, 0F0h
0x14000dec0  jb      short loc_14000DF33
0x14000dec2  mov     eax, [rcx+84h]
0x14000dec8  lea     rsi, [rcx+98h]
0x14000decf  cmp     eax, 2
0x14000ded2  jbe     short loc_14000DF2C
0x14000ded4  cmp     dword ptr [rsi+4], 10h
0x14000ded8  jb      short loc_14000DF2C
0x14000deda  mov     r8d, [rsi]
0x14000dedd  test    r8d, r8d
0x14000dee0  jz      short loc_14000DF2C
0x14000dee2  mov     rdx, rbp
0x14000dee5  call    AslpImageRvaToVa
0x14000deea  test    rax, rax
0x14000deed  jz      short loc_14000DF1B
0x14000deef  cmp     rax, rdi
0x14000def2  jb      short loc_14000DF1B
0x14000def4  mov     edx, [rsi+4]
0x14000def7  lea     rcx, [rdx+rax]
0x14000defb  cmp     rax, rcx
0x14000defe  ja      short loc_14000DF1B
0x14000df00  cmp     rax, rbx
0x14000df03  ja      short loc_14000DF1B
0x14000df05  cmp     rcx, rdi
0x14000df08  jb      short loc_14000DF1B
0x14000df0a  cmp     rcx, rbx
0x14000df0d  ja      short loc_14000DF1B
0x14000df0f  cmp     rdx, r14
0x14000df12  ja      short loc_14000DF1B
0x14000df14  mov     [r15], rax
0x14000df17  xor     eax, eax
0x14000df19  jmp     short loc_14000DF6E
0x14000df1b  neg     rax
0x14000df1e  sbb     eax, eax
0x14000df20  and     eax, 1A5h
0x14000df25  add     eax, 0C0000089h
0x14000df2a  jmp     short loc_14000DF6E
0x14000df2c  mov     eax, 0C0000089h
0x14000df31  jmp     short loc_14000DF6E
0x14000df33  mov     r8d, 7B3h
0x14000df39  jmp     loc_14000DE52
0x14000df3e  mov     eax, 0C000007Bh
0x14000df43  jmp     short loc_14000DF6E
0x14000df45  mov     ebx, 0C000022Eh
0x14000df4a  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x14000df51  mov     [rsp+68h+var_48], ebx
0x14000df55  mov     r8d, 791h
0x14000df5b  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x14000df62  mov     ecx, 1
0x14000df67  call    AslLogCallPrintf
0x14000df6c  mov     eax, ebx
0x14000df6e  add     rsp, 38h
0x14000df72  pop     r15
0x14000df74  pop     r14
0x14000df76  pop     rdi
0x14000df77  pop     rsi
0x14000df78  pop     rbp
0x14000df79  pop     rbx
0x14000df7a  retn
```
